# BCryptEnumContextFunctions

- ea: `0x18002160c`
- end: `0x1800218cb`
- name: `BCryptEnumContextFunctions`
- size: `703`
- prototype: `NTSTATUS __stdcall(ULONG dwTable, LPCWSTR pszContext, ULONG dwInterface, ULONG *pcbBuffer, PCRYPT_CONTEXT_FUNCTIONS *ppBuffer)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022788`

## callees

- `0x180018af0`
- `0x180018f30`
- `0x180021430`
- `0x18002160c`
- `0x180021d90`
- `0x180021f8c`
- `0x180025aa0`
- `0x1800267d0`
- `0x180029ec0`
- `0x1800470cc`
- `0x1800497e0`
- `0x18004cb68`
- `0x180073dd8`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x180021890`
- `ntoskrnl!ExReleaseResourceLite` at `0x180021890`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18002189c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18002189c`

## string_xrefs

- `0x180021714`: `\Registry\Machine\Software\Policies\Microsoft\Cryptography\Configuration\SSL\00010002\`
- `0x180021738`: `\Registry\Machine\System\CurrentControlSet\Control\Cryptography\MDMPolicies\SSL\`

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
0x18002160c  mov     rax, rsp
0x18002160f  mov     [rax+18h], rbx
0x180021613  mov     [rax+20h], r9
0x180021617  mov     [rax+10h], rdx
0x18002161b  mov     [rax+8], ecx
0x18002161e  push    rbp
0x18002161f  push    rsi
0x180021620  push    rdi
0x180021621  push    r12
0x180021623  push    r13
0x180021625  push    r14
0x180021627  push    r15
0x180021629  mov     rbp, rsp
0x18002162c  sub     rsp, 80h
0x180021633  xor     ebx, ebx
0x180021635  xor     r12d, r12d
0x180021638  mov     [rbp+var_18], r12d
0x18002163c  mov     rsi, r9
0x18002163f  mov     [rbp+var_1C], ebx
0x180021642  mov     r15d, r8d
0x180021645  mov     [rbp+var_10], rbx
0x180021649  xor     r14d, r14d
0x18002164c  xor     r13d, r13d
0x18002164f  call    ?CfgGetConfigContext@@YAPEAU_CNG_CONFIG_CONTEXT@@XZ; CfgGetConfigContext(void)
0x180021654  mov     ecx, [rbp+arg_0]
0x180021657  mov     rdi, rax
0x18002165a  call    ValidateTableId
0x18002165f  test    eax, eax
0x180021661  jz      loc_18002186E
0x180021667  xor     edx, edx
0x180021669  mov     ecx, r15d
0x18002166c  call    ValidateInterfaceId
0x180021671  test    eax, eax
0x180021673  jz      loc_18002186E
0x180021679  test    rsi, rsi
0x18002167c  jz      loc_18002186E
0x180021682  add     rdi, 88h
0x180021689  xor     edx, edx
0x18002168b  mov     rcx, rdi; Resource
0x18002168e  mov     r8d, 20019h
0x180021694  call    CfgReg_Acquire
0x180021699  mov     esi, eax
0x18002169b  test    eax, eax
0x18002169d  jnz     loc_18002187A
0x1800216a3  mov     rax, [rbp+arg_8]
0x1800216a7  lea     r12d, [rbx+1]
0x1800216ab  mov     [rsp+80h+var_30], rbx
0x1800216b0  lea     rdx, [rbp+var_10]
0x1800216b4  mov     [rsp+80h+var_38], rbx
0x1800216b9  xor     r9d, r9d
0x1800216bc  mov     [rsp+80h+var_40], r15d
0x1800216c1  xor     r8d, r8d
0x1800216c4  mov     [rsp+80h+var_48], rax
0x1800216c9  mov     ecx, 10020h
0x1800216ce  mov     eax, [rbp+arg_0]
0x1800216d1  mov     [rsp+80h+var_50], eax
0x1800216d5  mov     [rsp+80h+var_58], rdi
0x1800216da  mov     [rbp+var_18], r12d
0x1800216de  call    __CfgFind
0x1800216e3  mov     esi, eax
0x1800216e5  test    eax, eax
0x1800216e7  jnz     loc_18002187A
0x1800216ed  mov     rax, [rbp+var_10]
0x1800216f1  mov     r14, [rax+10h]
0x1800216f5  cmp     r15d, 10002h
0x1800216fc  jnz     loc_180021791
0x180021702  lea     r8, [rbp+var_10]
0x180021706  mov     [rbp+var_10], rbx
0x18002170a  lea     rdx, aFunctions; "Functions"
0x180021711  mov     [rbp+pfEnabled], bl
0x180021714  lea     rcx, aRegistryMachin_6; "\\Registry\\Machine\\Software\\Policies"...
0x18002171b  call    CfgGetCachedSslCipherSuiteOrder
0x180021720  test    eax, eax
0x180021722  js      short loc_18002172D
0x180021724  mov     rax, [rbp+var_10]
0x180021728  test    rax, rax
0x18002172b  jnz     short loc_180021751
0x18002172d  lea     r8, [rbp+var_10]
0x180021731  lea     rdx, aCiphersuites; "CipherSuites"
0x180021738  lea     rcx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x18002173f  call    CfgGetCachedSslCipherSuiteOrder
0x180021744  test    eax, eax
0x180021746  js      short loc_180021757
0x180021748  mov     rax, [rbp+var_10]
0x18002174c  test    rax, rax
0x18002174f  jz      short loc_180021757
0x180021751  mov     r13d, r12d
0x180021754  mov     r14, rax
0x180021757  lea     rcx, [rbp+pfEnabled]; pfEnabled
0x18002175b  call    BCryptGetFipsAlgorithmMode
0x180021760  test    eax, eax
0x180021762  js      short loc_180021791
0x180021764  cmp     [rbp+pfEnabled], bl
0x180021767  jz      short loc_180021791
0x180021769  lea     rdx, [rbp+var_10]
0x18002176d  mov     [rbp+var_10], rbx
0x180021771  mov     rcx, r14
0x180021774  call    CfgFilterFipsCipherSuites
0x180021779  test    eax, eax
0x18002177b  js      short loc_180021791
0x18002177d  test    r13d, r13d
0x180021780  jz      short loc_18002178A
0x180021782  mov     rcx, r14; P
0x180021785  call    DataBlock_Free
0x18002178a  mov     r14, [rbp+var_10]
0x18002178e  mov     r13d, r12d
0x180021791  test    r14, r14
0x180021794  jz      short loc_1800217E6
0x180021796  mov     ecx, [r14+14h]
0x18002179a  test    ecx, ecx
0x18002179c  jz      short loc_1800217E6
0x18002179e  cmp     [r14], rbx
0x1800217a1  jz      loc_180021875
0x1800217a7  cmp     [r14+8], ebx
0x1800217ab  jz      loc_180021875
0x1800217b1  cmp     ecx, 20000000h
0x1800217b7  jnb     loc_180021875
0x1800217bd  mov     edx, [r14+0Ch]
0x1800217c1  lea     eax, [rdx-1]
0x1800217c4  cmp     eax, 7FFFFFFEh
0x1800217c9  ja      loc_180021875
0x1800217cf  lea     eax, ds:0[rcx*8]
0x1800217d6  lea     ebx, [rax+rdx*2]
0x1800217d9  cmp     ebx, eax
0x1800217db  jb      loc_180021875
0x1800217e1  mov     [rbp+var_1C], ebx
0x1800217e4  xor     esi, esi
0x1800217e6  mov     r12, [rbp+ppBuffer]
0x1800217ea  test    r12, r12
0x1800217ed  jnz     short loc_1800217FC
0x1800217ef  mov     rcx, [rbp+arg_18]
0x1800217f3  lea     eax, [rbx+10h]
0x1800217f6  xor     esi, esi
0x1800217f8  mov     [rcx], eax
0x1800217fa  jmp     short loc_18002187A
0x1800217fc  mov     r15, [r12]
0x180021800  test    r15, r15
0x180021803  jz      short loc_180021819
0x180021805  mov     rcx, [rbp+arg_18]
0x180021809  lea     eax, [rbx+10h]
0x18002180c  cmp     [rcx], eax
0x18002180e  jnb     short loc_18002182E
0x180021810  mov     [rcx], eax
0x180021812  mov     esi, 7Ah ; 'z'
0x180021817  jmp     short loc_18002187A
0x180021819  lea     ecx, [rbx+10h]
0x18002181c  call    BCryptAlloc
0x180021821  mov     r15, rax
0x180021824  test    rax, rax
0x180021827  jnz     short loc_18002182E
0x180021829  lea     esi, [rax+8]
0x18002182c  jmp     short loc_18002187A
0x18002182e  test    ebx, ebx
0x180021830  jz      short loc_180021852
0x180021832  lea     rbx, [r15+10h]
0x180021836  mov     rcx, r14
0x180021839  mov     rdx, rbx
0x18002183c  lea     r8, [rbp+var_1C]
0x180021840  call    WideMultiString_Copy_ToSzStringArray
0x180021845  mov     [r15+8], rbx
0x180021849  mov     eax, [r14+14h]
0x18002184d  mov     ebx, [rbp+var_1C]
0x180021850  jmp     short loc_18002185C
0x180021852  mov     qword ptr [r15+8], 0
0x18002185a  xor     eax, eax
0x18002185c  mov     [r15], eax
0x18002185f  lea     eax, [rbx+10h]
0x180021862  mov     rcx, [rbp+arg_18]
0x180021866  mov     [r12], r15
0x18002186a  mov     [rcx], eax
0x18002186c  jmp     short loc_18002187A
0x18002186e  add     rdi, 88h
0x180021875  mov     esi, 57h ; 'W'
0x18002187a  test    r13d, r13d
0x18002187d  jz      short loc_180021887
0x18002187f  mov     rcx, r14; P
0x180021882  call    DataBlock_Free
0x180021887  cmp     [rbp+var_18], 0
0x18002188b  jz      short loc_1800218A8
0x18002188d  mov     rcx, rdi; Resource
0x180021890  call    cs:__imp_ExReleaseResourceLite
0x180021897  nop     dword ptr [rax+rax+00h]
0x18002189c  call    cs:__imp_KeLeaveCriticalRegion
0x1800218a3  nop     dword ptr [rax+rax+00h]
0x1800218a8  mov     ecx, esi; Status
0x1800218aa  call    WinErrorToNtStatus
0x1800218af  mov     rbx, [rsp+80h+arg_10]
0x1800218b7  add     rsp, 80h
0x1800218be  pop     r15
0x1800218c0  pop     r14
0x1800218c2  pop     r13
0x1800218c4  pop     r12
0x1800218c6  pop     rdi
0x1800218c7  pop     rsi
0x1800218c8  pop     rbp
0x1800218c9  retn
```
