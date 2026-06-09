# BCryptEnumContextFunctions

- ea: `0x18002454c`
- end: `0x18002480b`
- name: `BCryptEnumContextFunctions`
- size: `703`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, ULONG *pcbBuffer, PCRYPT_CONTEXT_FUNCTIONS *ppBuffer)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800256c8`

## callees

- `0x18001ba40`
- `0x18001be80`
- `0x180024370`
- `0x18002454c`
- `0x180024cd0`
- `0x180024ecc`
- `0x1800289e0`
- `0x180029710`
- `0x18002ce00`
- `0x18004663c`
- `0x180048d50`
- `0x18004c328`
- `0x1800733d8`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1800247d0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800247d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800247dc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800247dc`

## string_xrefs

- `0x180024654`: `\Registry\Machine\Software\Policies\Microsoft\Cryptography\Configuration\SSL\00010002\`
- `0x180024678`: `\Registry\Machine\System\CurrentControlSet\Control\Cryptography\MDMPolicies\SSL\`

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
0x18002454c  mov     rax, rsp
0x18002454f  mov     [rax+18h], rbx
0x180024553  mov     [rax+20h], r9
0x180024557  mov     [rax+10h], rdx
0x18002455b  mov     [rax+8], ecx
0x18002455e  push    rbp
0x18002455f  push    rsi
0x180024560  push    rdi
0x180024561  push    r12
0x180024563  push    r13
0x180024565  push    r14
0x180024567  push    r15
0x180024569  mov     rbp, rsp
0x18002456c  sub     rsp, 80h
0x180024573  xor     ebx, ebx
0x180024575  xor     r12d, r12d
0x180024578  mov     [rbp+var_18], r12d
0x18002457c  mov     rsi, r9
0x18002457f  mov     [rbp+var_1C], ebx
0x180024582  mov     r15d, r8d
0x180024585  mov     [rbp+var_10], rbx
0x180024589  xor     r14d, r14d
0x18002458c  xor     r13d, r13d
0x18002458f  call    ?CfgGetConfigContext@@YAPEAU_CNG_CONFIG_CONTEXT@@XZ; CfgGetConfigContext(void)
0x180024594  mov     ecx, [rbp+arg_0]
0x180024597  mov     rdi, rax
0x18002459a  call    ValidateTableId
0x18002459f  test    eax, eax
0x1800245a1  jz      loc_1800247AE
0x1800245a7  xor     edx, edx
0x1800245a9  mov     ecx, r15d
0x1800245ac  call    ValidateInterfaceId
0x1800245b1  test    eax, eax
0x1800245b3  jz      loc_1800247AE
0x1800245b9  test    rsi, rsi
0x1800245bc  jz      loc_1800247AE
0x1800245c2  add     rdi, 88h
0x1800245c9  xor     edx, edx
0x1800245cb  mov     rcx, rdi; Resource
0x1800245ce  mov     r8d, 20019h
0x1800245d4  call    CfgReg_Acquire
0x1800245d9  mov     esi, eax
0x1800245db  test    eax, eax
0x1800245dd  jnz     loc_1800247BA
0x1800245e3  mov     rax, [rbp+arg_8]
0x1800245e7  lea     r12d, [rbx+1]
0x1800245eb  mov     [rsp+80h+var_30], rbx
0x1800245f0  lea     rdx, [rbp+var_10]
0x1800245f4  mov     [rsp+80h+var_38], rbx
0x1800245f9  xor     r9d, r9d
0x1800245fc  mov     [rsp+80h+var_40], r15d
0x180024601  xor     r8d, r8d
0x180024604  mov     [rsp+80h+var_48], rax
0x180024609  mov     ecx, 10020h
0x18002460e  mov     eax, [rbp+arg_0]
0x180024611  mov     [rsp+80h+var_50], eax
0x180024615  mov     [rsp+80h+var_58], rdi
0x18002461a  mov     [rbp+var_18], r12d
0x18002461e  call    __CfgFind
0x180024623  mov     esi, eax
0x180024625  test    eax, eax
0x180024627  jnz     loc_1800247BA
0x18002462d  mov     rax, [rbp+var_10]
0x180024631  mov     r14, [rax+10h]
0x180024635  cmp     r15d, 10002h
0x18002463c  jnz     loc_1800246D1
0x180024642  lea     r8, [rbp+var_10]
0x180024646  mov     [rbp+var_10], rbx
0x18002464a  lea     rdx, aFunctions; "Functions"
0x180024651  mov     [rbp+pfEnabled], bl
0x180024654  lea     rcx, aRegistryMachin_6; "\\Registry\\Machine\\Software\\Policies"...
0x18002465b  call    CfgGetCachedSslCipherSuiteOrder
0x180024660  test    eax, eax
0x180024662  js      short loc_18002466D
0x180024664  mov     rax, [rbp+var_10]
0x180024668  test    rax, rax
0x18002466b  jnz     short loc_180024691
0x18002466d  lea     r8, [rbp+var_10]
0x180024671  lea     rdx, aCiphersuites; "CipherSuites"
0x180024678  lea     rcx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x18002467f  call    CfgGetCachedSslCipherSuiteOrder
0x180024684  test    eax, eax
0x180024686  js      short loc_180024697
0x180024688  mov     rax, [rbp+var_10]
0x18002468c  test    rax, rax
0x18002468f  jz      short loc_180024697
0x180024691  mov     r13d, r12d
0x180024694  mov     r14, rax
0x180024697  lea     rcx, [rbp+pfEnabled]; pfEnabled
0x18002469b  call    BCryptGetFipsAlgorithmMode
0x1800246a0  test    eax, eax
0x1800246a2  js      short loc_1800246D1
0x1800246a4  cmp     [rbp+pfEnabled], bl
0x1800246a7  jz      short loc_1800246D1
0x1800246a9  lea     rdx, [rbp+var_10]
0x1800246ad  mov     [rbp+var_10], rbx
0x1800246b1  mov     rcx, r14
0x1800246b4  call    CfgFilterFipsCipherSuites
0x1800246b9  test    eax, eax
0x1800246bb  js      short loc_1800246D1
0x1800246bd  test    r13d, r13d
0x1800246c0  jz      short loc_1800246CA
0x1800246c2  mov     rcx, r14; P
0x1800246c5  call    DataBlock_Free
0x1800246ca  mov     r14, [rbp+var_10]
0x1800246ce  mov     r13d, r12d
0x1800246d1  test    r14, r14
0x1800246d4  jz      short loc_180024726
0x1800246d6  mov     ecx, [r14+14h]
0x1800246da  test    ecx, ecx
0x1800246dc  jz      short loc_180024726
0x1800246de  cmp     [r14], rbx
0x1800246e1  jz      loc_1800247B5
0x1800246e7  cmp     [r14+8], ebx
0x1800246eb  jz      loc_1800247B5
0x1800246f1  cmp     ecx, 20000000h
0x1800246f7  jnb     loc_1800247B5
0x1800246fd  mov     edx, [r14+0Ch]
0x180024701  lea     eax, [rdx-1]
0x180024704  cmp     eax, 7FFFFFFEh
0x180024709  ja      loc_1800247B5
0x18002470f  lea     eax, ds:0[rcx*8]
0x180024716  lea     ebx, [rax+rdx*2]
0x180024719  cmp     ebx, eax
0x18002471b  jb      loc_1800247B5
0x180024721  mov     [rbp+var_1C], ebx
0x180024724  xor     esi, esi
0x180024726  mov     r12, [rbp+ppBuffer]
0x18002472a  test    r12, r12
0x18002472d  jnz     short loc_18002473C
0x18002472f  mov     rcx, [rbp+arg_18]
0x180024733  lea     eax, [rbx+10h]
0x180024736  xor     esi, esi
0x180024738  mov     [rcx], eax
0x18002473a  jmp     short loc_1800247BA
0x18002473c  mov     r15, [r12]
0x180024740  test    r15, r15
0x180024743  jz      short loc_180024759
0x180024745  mov     rcx, [rbp+arg_18]
0x180024749  lea     eax, [rbx+10h]
0x18002474c  cmp     [rcx], eax
0x18002474e  jnb     short loc_18002476E
0x180024750  mov     [rcx], eax
0x180024752  mov     esi, 7Ah ; 'z'
0x180024757  jmp     short loc_1800247BA
0x180024759  lea     ecx, [rbx+10h]
0x18002475c  call    BCryptAlloc
0x180024761  mov     r15, rax
0x180024764  test    rax, rax
0x180024767  jnz     short loc_18002476E
0x180024769  lea     esi, [rax+8]
0x18002476c  jmp     short loc_1800247BA
0x18002476e  test    ebx, ebx
0x180024770  jz      short loc_180024792
0x180024772  lea     rbx, [r15+10h]
0x180024776  mov     rcx, r14
0x180024779  mov     rdx, rbx
0x18002477c  lea     r8, [rbp+var_1C]
0x180024780  call    WideMultiString_Copy_ToSzStringArray
0x180024785  mov     [r15+8], rbx
0x180024789  mov     eax, [r14+14h]
0x18002478d  mov     ebx, [rbp+var_1C]
0x180024790  jmp     short loc_18002479C
0x180024792  mov     qword ptr [r15+8], 0
0x18002479a  xor     eax, eax
0x18002479c  mov     [r15], eax
0x18002479f  lea     eax, [rbx+10h]
0x1800247a2  mov     rcx, [rbp+arg_18]
0x1800247a6  mov     [r12], r15
0x1800247aa  mov     [rcx], eax
0x1800247ac  jmp     short loc_1800247BA
0x1800247ae  add     rdi, 88h
0x1800247b5  mov     esi, 57h ; 'W'
0x1800247ba  test    r13d, r13d
0x1800247bd  jz      short loc_1800247C7
0x1800247bf  mov     rcx, r14; P
0x1800247c2  call    DataBlock_Free
0x1800247c7  cmp     [rbp+var_18], 0
0x1800247cb  jz      short loc_1800247E8
0x1800247cd  mov     rcx, rdi; Resource
0x1800247d0  call    cs:__imp_ExReleaseResourceLite
0x1800247d7  nop     dword ptr [rax+rax+00h]
0x1800247dc  call    cs:__imp_KeLeaveCriticalRegion
0x1800247e3  nop     dword ptr [rax+rax+00h]
0x1800247e8  mov     ecx, esi; Status
0x1800247ea  call    WinErrorToNtStatus
0x1800247ef  mov     rbx, [rsp+80h+arg_10]
0x1800247f7  add     rsp, 80h
0x1800247fe  pop     r15
0x180024800  pop     r14
0x180024802  pop     r13
0x180024804  pop     r12
0x180024806  pop     rdi
0x180024807  pop     rsi
0x180024808  pop     rbp
0x180024809  retn
```
