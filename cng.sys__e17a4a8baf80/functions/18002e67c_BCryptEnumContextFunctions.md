# BCryptEnumContextFunctions

- ea: `0x18002e67c`
- end: `0x18002e93b`
- name: `BCryptEnumContextFunctions`
- size: `703`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, ULONG *pcbBuffer, PCRYPT_CONTEXT_FUNCTIONS *ppBuffer)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f7f8`

## callees

- `0x180025b70`
- `0x180025fb0`
- `0x18002e4a0`
- `0x18002e67c`
- `0x18002ee00`
- `0x18002effc`
- `0x180032b10`
- `0x180033840`
- `0x180036f30`
- `0x18005072c`
- `0x180052e40`
- `0x180056428`
- `0x18007d578`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x18002e900`
- `ntoskrnl!ExReleaseResourceLite` at `0x18002e900`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18002e90c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18002e90c`

## string_xrefs

- `0x18002e784`: `\Registry\Machine\Software\Policies\Microsoft\Cryptography\Configuration\SSL\00010002\`
- `0x18002e7a8`: `\Registry\Machine\System\CurrentControlSet\Control\Cryptography\MDMPolicies\SSL\`

## pseudocode

```c
NTSTATUS __stdcall BCryptEnumContextFunctions(
        ULONG dwTable,
        LPCWSTR pszContext,
        ULONG dwInterface,
        ULONG *pcbBuffer,
        PCRYPT_CONTEXT_FUNCTIONS *ppBuffer)
{
  unsigned int v5; // ebx
  _DWORD *v8; // r14
  int v9; // r13d
  struct _CNG_CONFIG_CONTEXT *ConfigContext; // rdi
  struct _ERESOURCE *v11; // rdi
  NTSTATUS v12; // esi
  _DWORD *v13; // rax
  unsigned int v14; // ecx
  int v15; // edx
  PCRYPT_CONTEXT_FUNCTIONS v16; // r15
  ULONG v17; // eax
  BOOLEAN pfEnabled[4]; // [rsp+60h] [rbp-20h] BYREF
  int v20; // [rsp+64h] [rbp-1Ch] BYREF
  int v21; // [rsp+68h] [rbp-18h]
  _QWORD v22[2]; // [rsp+70h] [rbp-10h] BYREF

  v5 = 0;
  v21 = 0;
  v20 = 0;
  v22[0] = 0;
  v8 = 0;
  v9 = 0;
  ConfigContext = CfgGetConfigContext();
  if ( !(unsigned int)ValidateTableId(dwTable) || !(unsigned int)ValidateInterfaceId(dwInterface, 0) || !pcbBuffer )
  {
    v11 = (struct _ERESOURCE *)((char *)ConfigContext + 136);
    goto LABEL_38;
  }
  v11 = (struct _ERESOURCE *)((char *)ConfigContext + 136);
  v12 = CfgReg_Acquire(v11, 0, 0x20019u);
  if ( v12 )
    goto LABEL_39;
  v21 = 1;
  v12 = _CfgFind(65568, (unsigned int)v22, 0, 0);
  if ( v12 )
    goto LABEL_39;
  v8 = *(_DWORD **)(v22[0] + 16LL);
  if ( dwInterface == 65538 )
  {
    v22[0] = 0;
    pfEnabled[0] = 0;
    if ( (int)CfgGetCachedSslCipherSuiteOrder(
                (wchar_t *)L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Cryptography\\Configuration\\SSL\\00010002\\",
                L"Functions",
                v22) >= 0
      && (v13 = (_DWORD *)v22[0]) != 0
      || (int)CfgGetCachedSslCipherSuiteOrder(
                (wchar_t *)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Cryptography\\MDMPolicies\\SSL\\",
                L"CipherSuites",
                v22) >= 0
      && (v13 = (_DWORD *)v22[0]) != 0 )
    {
      v9 = 1;
      v8 = v13;
    }
    if ( BCryptGetFipsAlgorithmMode(pfEnabled) >= 0 )
    {
      if ( pfEnabled[0] )
      {
        v22[0] = 0;
        if ( (int)CfgFilterFipsCipherSuites(v8, v22) >= 0 )
        {
          if ( v9 )
            DataBlock_Free(v8);
          v8 = (_DWORD *)v22[0];
          v9 = 1;
        }
      }
    }
  }
  if ( v8 )
  {
    v14 = v8[5];
    if ( v14 )
    {
      if ( *(_QWORD *)v8 )
      {
        if ( v8[2] )
        {
          if ( v14 < 0x20000000 )
          {
            v15 = v8[3];
            if ( (unsigned int)(v15 - 1) <= 0x7FFFFFFE )
            {
              v5 = 8 * v14 + 2 * v15;
              if ( v5 >= 8 * v14 )
              {
                v20 = 8 * v14 + 2 * v15;
                v12 = 0;
                goto LABEL_26;
              }
            }
          }
        }
      }
LABEL_38:
      v12 = 87;
      goto LABEL_39;
    }
  }
LABEL_26:
  if ( !ppBuffer )
  {
    v12 = 0;
    *pcbBuffer = v5 + 16;
    goto LABEL_39;
  }
  v16 = *ppBuffer;
  if ( *ppBuffer )
  {
    if ( *pcbBuffer < v5 + 16 )
    {
      *pcbBuffer = v5 + 16;
      v12 = 122;
      goto LABEL_39;
    }
  }
  else
  {
    v16 = (PCRYPT_CONTEXT_FUNCTIONS)BCryptAlloc(v5 + 16);
    if ( !v16 )
    {
      v12 = 8;
      goto LABEL_39;
    }
  }
  if ( v5 )
  {
    WideMultiString_Copy_ToSzStringArray(v8, &v16[1], &v20);
    v16->rgpszFunctions = (PWSTR *)&v16[1];
    v17 = v8[5];
    v5 = v20;
  }
  else
  {
    v16->rgpszFunctions = 0;
    v17 = 0;
  }
  v16->cFunctions = v17;
  *ppBuffer = v16;
  *pcbBuffer = v5 + 16;
LABEL_39:
  if ( v9 )
    DataBlock_Free(v8);
  if ( v21 )
  {
    ExReleaseResourceLite(v11);
    KeLeaveCriticalRegion();
  }
  return WinErrorToNtStatus(v12);
}

```

## disassembly

```asm
0x18002e67c  mov     rax, rsp
0x18002e67f  mov     [rax+18h], rbx
0x18002e683  mov     [rax+20h], r9
0x18002e687  mov     [rax+10h], rdx
0x18002e68b  mov     [rax+8], ecx
0x18002e68e  push    rbp
0x18002e68f  push    rsi
0x18002e690  push    rdi
0x18002e691  push    r12
0x18002e693  push    r13
0x18002e695  push    r14
0x18002e697  push    r15
0x18002e699  mov     rbp, rsp
0x18002e69c  sub     rsp, 80h
0x18002e6a3  xor     ebx, ebx
0x18002e6a5  xor     r12d, r12d
0x18002e6a8  mov     [rbp+var_18], r12d
0x18002e6ac  mov     rsi, r9
0x18002e6af  mov     [rbp+var_1C], ebx
0x18002e6b2  mov     r15d, r8d
0x18002e6b5  mov     [rbp+var_10], rbx
0x18002e6b9  xor     r14d, r14d
0x18002e6bc  xor     r13d, r13d
0x18002e6bf  call    ?CfgGetConfigContext@@YAPEAU_CNG_CONFIG_CONTEXT@@XZ; CfgGetConfigContext(void)
0x18002e6c4  mov     ecx, [rbp+arg_0]
0x18002e6c7  mov     rdi, rax
0x18002e6ca  call    ValidateTableId
0x18002e6cf  test    eax, eax
0x18002e6d1  jz      loc_18002E8DE
0x18002e6d7  xor     edx, edx
0x18002e6d9  mov     ecx, r15d
0x18002e6dc  call    ValidateInterfaceId
0x18002e6e1  test    eax, eax
0x18002e6e3  jz      loc_18002E8DE
0x18002e6e9  test    rsi, rsi
0x18002e6ec  jz      loc_18002E8DE
0x18002e6f2  add     rdi, 88h
0x18002e6f9  xor     edx, edx
0x18002e6fb  mov     rcx, rdi; Resource
0x18002e6fe  mov     r8d, 20019h
0x18002e704  call    CfgReg_Acquire
0x18002e709  mov     esi, eax
0x18002e70b  test    eax, eax
0x18002e70d  jnz     loc_18002E8EA
0x18002e713  mov     rax, [rbp+arg_8]
0x18002e717  lea     r12d, [rbx+1]
0x18002e71b  mov     [rsp+80h+var_30], rbx
0x18002e720  lea     rdx, [rbp+var_10]
0x18002e724  mov     [rsp+80h+var_38], rbx
0x18002e729  xor     r9d, r9d
0x18002e72c  mov     [rsp+80h+var_40], r15d
0x18002e731  xor     r8d, r8d
0x18002e734  mov     [rsp+80h+var_48], rax
0x18002e739  mov     ecx, 10020h
0x18002e73e  mov     eax, [rbp+arg_0]
0x18002e741  mov     [rsp+80h+var_50], eax
0x18002e745  mov     [rsp+80h+var_58], rdi
0x18002e74a  mov     [rbp+var_18], r12d
0x18002e74e  call    __CfgFind
0x18002e753  mov     esi, eax
0x18002e755  test    eax, eax
0x18002e757  jnz     loc_18002E8EA
0x18002e75d  mov     rax, [rbp+var_10]
0x18002e761  mov     r14, [rax+10h]
0x18002e765  cmp     r15d, 10002h
0x18002e76c  jnz     loc_18002E801
0x18002e772  lea     r8, [rbp+var_10]
0x18002e776  mov     [rbp+var_10], rbx
0x18002e77a  lea     rdx, aFunctions; "Functions"
0x18002e781  mov     [rbp+pfEnabled], bl
0x18002e784  lea     rcx, aRegistryMachin_6; "\\Registry\\Machine\\Software\\Policies"...
0x18002e78b  call    CfgGetCachedSslCipherSuiteOrder
0x18002e790  test    eax, eax
0x18002e792  js      short loc_18002E79D
0x18002e794  mov     rax, [rbp+var_10]
0x18002e798  test    rax, rax
0x18002e79b  jnz     short loc_18002E7C1
0x18002e79d  lea     r8, [rbp+var_10]
0x18002e7a1  lea     rdx, aCiphersuites; "CipherSuites"
0x18002e7a8  lea     rcx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x18002e7af  call    CfgGetCachedSslCipherSuiteOrder
0x18002e7b4  test    eax, eax
0x18002e7b6  js      short loc_18002E7C7
0x18002e7b8  mov     rax, [rbp+var_10]
0x18002e7bc  test    rax, rax
0x18002e7bf  jz      short loc_18002E7C7
0x18002e7c1  mov     r13d, r12d
0x18002e7c4  mov     r14, rax
0x18002e7c7  lea     rcx, [rbp+pfEnabled]; pfEnabled
0x18002e7cb  call    BCryptGetFipsAlgorithmMode
0x18002e7d0  test    eax, eax
0x18002e7d2  js      short loc_18002E801
0x18002e7d4  cmp     [rbp+pfEnabled], bl
0x18002e7d7  jz      short loc_18002E801
0x18002e7d9  lea     rdx, [rbp+var_10]
0x18002e7dd  mov     [rbp+var_10], rbx
0x18002e7e1  mov     rcx, r14
0x18002e7e4  call    CfgFilterFipsCipherSuites
0x18002e7e9  test    eax, eax
0x18002e7eb  js      short loc_18002E801
0x18002e7ed  test    r13d, r13d
0x18002e7f0  jz      short loc_18002E7FA
0x18002e7f2  mov     rcx, r14; P
0x18002e7f5  call    DataBlock_Free
0x18002e7fa  mov     r14, [rbp+var_10]
0x18002e7fe  mov     r13d, r12d
0x18002e801  test    r14, r14
0x18002e804  jz      short loc_18002E856
0x18002e806  mov     ecx, [r14+14h]
0x18002e80a  test    ecx, ecx
0x18002e80c  jz      short loc_18002E856
0x18002e80e  cmp     [r14], rbx
0x18002e811  jz      loc_18002E8E5
0x18002e817  cmp     [r14+8], ebx
0x18002e81b  jz      loc_18002E8E5
0x18002e821  cmp     ecx, 20000000h
0x18002e827  jnb     loc_18002E8E5
0x18002e82d  mov     edx, [r14+0Ch]
0x18002e831  lea     eax, [rdx-1]
0x18002e834  cmp     eax, 7FFFFFFEh
0x18002e839  ja      loc_18002E8E5
0x18002e83f  lea     eax, ds:0[rcx*8]
0x18002e846  lea     ebx, [rax+rdx*2]
0x18002e849  cmp     ebx, eax
0x18002e84b  jb      loc_18002E8E5
0x18002e851  mov     [rbp+var_1C], ebx
0x18002e854  xor     esi, esi
0x18002e856  mov     r12, [rbp+ppBuffer]
0x18002e85a  test    r12, r12
0x18002e85d  jnz     short loc_18002E86C
0x18002e85f  mov     rcx, [rbp+arg_18]
0x18002e863  lea     eax, [rbx+10h]
0x18002e866  xor     esi, esi
0x18002e868  mov     [rcx], eax
0x18002e86a  jmp     short loc_18002E8EA
0x18002e86c  mov     r15, [r12]
0x18002e870  test    r15, r15
0x18002e873  jz      short loc_18002E889
0x18002e875  mov     rcx, [rbp+arg_18]
0x18002e879  lea     eax, [rbx+10h]
0x18002e87c  cmp     [rcx], eax
0x18002e87e  jnb     short loc_18002E89E
0x18002e880  mov     [rcx], eax
0x18002e882  mov     esi, 7Ah ; 'z'
0x18002e887  jmp     short loc_18002E8EA
0x18002e889  lea     ecx, [rbx+10h]
0x18002e88c  call    BCryptAlloc
0x18002e891  mov     r15, rax
0x18002e894  test    rax, rax
0x18002e897  jnz     short loc_18002E89E
0x18002e899  lea     esi, [rax+8]
0x18002e89c  jmp     short loc_18002E8EA
0x18002e89e  test    ebx, ebx
0x18002e8a0  jz      short loc_18002E8C2
0x18002e8a2  lea     rbx, [r15+10h]
0x18002e8a6  mov     rcx, r14
0x18002e8a9  mov     rdx, rbx
0x18002e8ac  lea     r8, [rbp+var_1C]
0x18002e8b0  call    WideMultiString_Copy_ToSzStringArray
0x18002e8b5  mov     [r15+8], rbx
0x18002e8b9  mov     eax, [r14+14h]
0x18002e8bd  mov     ebx, [rbp+var_1C]
0x18002e8c0  jmp     short loc_18002E8CC
0x18002e8c2  mov     qword ptr [r15+8], 0
0x18002e8ca  xor     eax, eax
0x18002e8cc  mov     [r15], eax
0x18002e8cf  lea     eax, [rbx+10h]
0x18002e8d2  mov     rcx, [rbp+arg_18]
0x18002e8d6  mov     [r12], r15
0x18002e8da  mov     [rcx], eax
0x18002e8dc  jmp     short loc_18002E8EA
0x18002e8de  add     rdi, 88h
0x18002e8e5  mov     esi, 57h ; 'W'
0x18002e8ea  test    r13d, r13d
0x18002e8ed  jz      short loc_18002E8F7
0x18002e8ef  mov     rcx, r14; P
0x18002e8f2  call    DataBlock_Free
0x18002e8f7  cmp     [rbp+var_18], 0
0x18002e8fb  jz      short loc_18002E918
0x18002e8fd  mov     rcx, rdi; Resource
0x18002e900  call    cs:__imp_ExReleaseResourceLite
0x18002e907  nop     dword ptr [rax+rax+00h]
0x18002e90c  call    cs:__imp_KeLeaveCriticalRegion
0x18002e913  nop     dword ptr [rax+rax+00h]
0x18002e918  mov     ecx, esi; Status
0x18002e91a  call    WinErrorToNtStatus
0x18002e91f  mov     rbx, [rsp+80h+arg_10]
0x18002e927  add     rsp, 80h
0x18002e92e  pop     r15
0x18002e930  pop     r14
0x18002e932  pop     r13
0x18002e934  pop     r12
0x18002e936  pop     rdi
0x18002e937  pop     rsi
0x18002e938  pop     rbp
0x18002e939  retn
```
