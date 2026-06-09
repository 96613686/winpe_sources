# FwhcIsNonNAPCertMMSaPresent

- ea: `0x18000c63c`
- end: `0x18000c862`
- name: `FwhcIsNonNAPCertMMSaPresent`
- size: `550`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008540`

## callees

- `0x18000bad0`
- `0x18000c63c`
- `0x180010e94`
- `0x180010f48`

## import_xrefs

- `WS2_32!__imp_ntohl` at `0x18000c69d`
- `WS2_32!__imp_ntohl` at `0x18000c6b9`
- `WS2_32!__imp_ntohl` at `0x18000c69d`
- `WS2_32!__imp_ntohl` at `0x18000c6b9`
- `fwpuclnt!FwpmEngineClose0` at `0x18000c828`
- `fwpuclnt!FwpmEngineClose0` at `0x18000c828`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000c810`
- `fwpuclnt!FwpmFreeMemory0` at `0x18000c810`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000c72f`
- `fwpuclnt!FwpmEngineOpen0` at `0x18000c72f`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x18000c75c`
- `fwpuclnt!IkeextSaCreateEnumHandle0` at `0x18000c75c`
- `fwpuclnt!IkeextSaEnum2` at `0x18000c793`
- `fwpuclnt!IkeextSaEnum2` at `0x18000c793`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x18000c81e`
- `fwpuclnt!IkeextSaDestroyEnumHandle0` at `0x18000c81e`

## string_xrefs

- `0x18000c739`: `FwpmEngineOpen0`
- `0x18000c771`: `IkeextSaCreateEnumHandle0`

## pseudocode

```c
__int64 __fastcall FwhcIsNonNAPCertMMSaPresent(_WORD *a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  u_long v6; // ecx
  u_long v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  DWORD v10; // eax
  __int64 v11; // rcx
  const char *v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // edx
  unsigned int v16; // ebx
  __int64 v17; // r8
  __int64 v18; // rax
  int v19; // r9d
  int DoesPolicyEnableNap; // eax
  __int64 v21; // rcx
  HANDLE engineHandle; // [rsp+30h] [rbp-50h] BYREF
  void *p; // [rsp+38h] [rbp-48h] BYREF
  HANDLE enumHandle; // [rsp+40h] [rbp-40h] BYREF
  IKEEXT_SA_ENUM_TEMPLATE0 enumTemplate; // [rsp+48h] [rbp-38h] BYREF
  char v27; // [rsp+A0h] [rbp+20h] BYREF
  unsigned int v28; // [rsp+B8h] [rbp+38h] BYREF

  engineHandle = 0;
  enumHandle = 0;
  p = 0;
  v28 = 0;
  v27 = 0;
  *a4 = 0;
  memset(&enumTemplate, 0, sizeof(enumTemplate));
  if ( a1 )
  {
    if ( *a1 == 2 )
    {
      if ( a2 )
      {
        v6 = *(_DWORD *)(a2 + 4);
        if ( v6 )
        {
          enumTemplate.localSubNet.type = FWP_UINT32;
          enumTemplate.localSubNet.uint32 = ntohl(v6);
        }
      }
      if ( a3 )
      {
        v7 = *(_DWORD *)(a3 + 4);
        if ( v7 )
        {
          enumTemplate.remoteSubNet.type = FWP_UINT32;
          enumTemplate.remoteSubNet.uint32 = ntohl(v7);
        }
      }
    }
    else if ( *a1 == 23 )
    {
      if ( a2 )
      {
        v8 = 0;
        while ( !*(_WORD *)(a2 + 2LL * v8 + 8) )
        {
          if ( (int)++v8 >= 8 )
            goto LABEL_16;
        }
        enumTemplate.localSubNet.type = FWP_BYTE_ARRAY16_TYPE;
        enumTemplate.localSubNet.uint64 = (UINT64 *)(a2 + 8);
      }
LABEL_16:
      if ( a3 )
      {
        v9 = 0;
        while ( !*(_WORD *)(a3 + 2LL * v9 + 8) )
        {
          if ( (int)++v9 >= 8 )
            goto LABEL_22;
        }
        enumTemplate.remoteSubNet.type = FWP_BYTE_ARRAY16_TYPE;
        enumTemplate.remoteSubNet.uint64 = (UINT64 *)(a3 + 8);
      }
    }
  }
LABEL_22:
  v10 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  if ( v10 )
  {
    v12 = "FwpmEngineOpen0";
LABEL_24:
    v13 = WfpReportSysErrorAsWinError(v11, v12, v10);
    goto LABEL_25;
  }
  v10 = IkeextSaCreateEnumHandle0(engineHandle, &enumTemplate, &enumHandle);
  if ( v10 == -2144206780 )
    goto LABEL_40;
  if ( v10 )
  {
    v12 = "IkeextSaCreateEnumHandle0";
    goto LABEL_24;
  }
  v10 = IkeextSaEnum2(engineHandle, enumHandle, 0xFFFFFFFFLL, &p, &v28);
  if ( v10 )
  {
    v12 = "IkeextSaEnum2";
    goto LABEL_24;
  }
  v15 = v28;
  v16 = 0;
  if ( !v28 )
  {
LABEL_40:
    v14 = 0;
    goto LABEL_41;
  }
  while ( 1 )
  {
    v17 = *((_QWORD *)p + v16);
    v18 = *(_QWORD *)(v17 + 128);
    if ( *(_DWORD *)v18 > 0xAu )
      goto LABEL_39;
    v19 = 1938;
    if ( !_bittest(&v19, *(_DWORD *)v18) || *(_DWORD *)(v18 + 4) || (*(_BYTE *)(*(_QWORD *)(v18 + 8) + 32LL) & 1) != 0 )
      goto LABEL_39;
    DoesPolicyEnableNap = FwhcDoesPolicyEnableNap(engineHandle, v17 + 136, &v27);
    if ( DoesPolicyEnableNap < 0 )
      break;
    if ( v27 )
    {
      *a4 = 1;
      goto LABEL_40;
    }
    v15 = v28;
LABEL_39:
    if ( ++v16 >= v15 )
      goto LABEL_40;
  }
  v13 = WfpReportSysErrorAsHResult(v21, "FwhcDoesPolicyEnableNap", (unsigned int)DoesPolicyEnableNap, 1);
LABEL_25:
  v14 = v13;
LABEL_41:
  FwpmFreeMemory0(&p);
  IkeextSaDestroyEnumHandle0(engineHandle, enumHandle);
  FwpmEngineClose0(engineHandle);
  return v14;
}

```

## disassembly

```asm
0x18000c63c  mov     [rsp-18h+arg_8], rbx
0x18000c641  push    rbp
0x18000c642  push    rsi
0x18000c643  push    rdi
0x18000c644  mov     rbp, rsp
0x18000c647  sub     rsp, 80h
0x18000c64e  xor     esi, esi
0x18000c650  xorps   xmm0, xmm0
0x18000c653  mov     [rbp+var_50], rsi
0x18000c657  mov     rdi, r9
0x18000c65a  mov     [rbp+enumHandle], rsi
0x18000c65e  mov     rbx, r8
0x18000c661  mov     [rbp+p], rsi
0x18000c665  mov     [rbp+arg_18], esi
0x18000c668  mov     [rbp+arg_0], sil
0x18000c66c  mov     [r9], sil
0x18000c66f  movups  xmmword ptr [rbp+enumTemplate.localSubNet.type], xmm0
0x18000c673  movups  xmmword ptr [rbp+enumTemplate.remoteSubNet.type], xmm0
0x18000c677  movups  xmmword ptr [rbp+enumTemplate.localMainModeCertHash.size], xmm0
0x18000c67b  test    rcx, rcx
0x18000c67e  jz      loc_18000C71A
0x18000c684  cmp     word ptr [rcx], 2
0x18000c688  jnz     short loc_18000C6C4
0x18000c68a  test    rdx, rdx
0x18000c68d  jz      short loc_18000C6A6
0x18000c68f  mov     ecx, [rdx+4]; netlong
0x18000c692  test    ecx, ecx
0x18000c694  jz      short loc_18000C6A6
0x18000c696  mov     [rbp+enumTemplate.localSubNet.type], 3
0x18000c69d  call    cs:__imp_ntohl
0x18000c6a3  mov     dword ptr [rbp+enumTemplate.localSubNet.8], eax
0x18000c6a6  test    rbx, rbx
0x18000c6a9  jz      short loc_18000C71A
0x18000c6ab  mov     ecx, [rbx+4]; netlong
0x18000c6ae  test    ecx, ecx
0x18000c6b0  jz      short loc_18000C71A
0x18000c6b2  mov     [rbp+enumTemplate.remoteSubNet.type], 3
0x18000c6b9  call    cs:__imp_ntohl
0x18000c6bf  mov     dword ptr [rbp+enumTemplate.remoteSubNet.8], eax
0x18000c6c2  jmp     short loc_18000C71A
0x18000c6c4  cmp     word ptr [rcx], 17h
0x18000c6c8  jnz     short loc_18000C71A
0x18000c6ca  mov     r8d, 0Bh
0x18000c6d0  test    rdx, rdx
0x18000c6d3  jz      short loc_18000C6F5
0x18000c6d5  mov     ecx, esi
0x18000c6d7  mov     eax, ecx
0x18000c6d9  cmp     [rdx+rax*2+8], si
0x18000c6de  jnz     short loc_18000C6E9
0x18000c6e0  inc     ecx
0x18000c6e2  cmp     ecx, 8
0x18000c6e5  jl      short loc_18000C6D7
0x18000c6e7  jmp     short loc_18000C6F5
0x18000c6e9  lea     rax, [rdx+8]
0x18000c6ed  mov     [rbp+enumTemplate.localSubNet.type], r8d
0x18000c6f1  mov     qword ptr [rbp+enumTemplate.localSubNet.8], rax
0x18000c6f5  test    rbx, rbx
0x18000c6f8  jz      short loc_18000C71A
0x18000c6fa  mov     ecx, esi
0x18000c6fc  mov     eax, ecx
0x18000c6fe  cmp     [rbx+rax*2+8], si
0x18000c703  jnz     short loc_18000C70E
0x18000c705  inc     ecx
0x18000c707  cmp     ecx, 8
0x18000c70a  jl      short loc_18000C6FC
0x18000c70c  jmp     short loc_18000C71A
0x18000c70e  lea     rax, [rbx+8]
0x18000c712  mov     [rbp+enumTemplate.remoteSubNet.type], r8d
0x18000c716  mov     qword ptr [rbp+enumTemplate.remoteSubNet.8], rax
0x18000c71a  xor     r9d, r9d; session
0x18000c71d  lea     rax, [rbp+var_50]
0x18000c721  xor     r8d, r8d; authIdentity
0x18000c724  mov     [rsp+80h+engineHandle], rax; engineHandle
0x18000c729  xor     ecx, ecx; serverName
0x18000c72b  lea     edx, [r9+0Ah]; authnService
0x18000c72f  call    cs:__imp_FwpmEngineOpen0
0x18000c735  test    eax, eax
0x18000c737  jz      short loc_18000C750
0x18000c739  lea     rdx, aFwpmengineopen; "FwpmEngineOpen0"
0x18000c740  mov     r8d, eax
0x18000c743  call    WfpReportSysErrorAsWinError
0x18000c748  mov     rbx, rax
0x18000c74b  jmp     loc_18000C80C
0x18000c750  mov     rcx, [rbp+var_50]; engineHandle
0x18000c754  lea     r8, [rbp+enumHandle]; enumHandle
0x18000c758  lea     rdx, [rbp+enumTemplate]; enumTemplate
0x18000c75c  call    cs:__imp_IkeextSaCreateEnumHandle0
0x18000c762  cmp     eax, 80320044h
0x18000c767  jz      loc_18000C809
0x18000c76d  test    eax, eax
0x18000c76f  jz      short loc_18000C77A
0x18000c771  lea     rdx, aIkeextsacreate; "IkeextSaCreateEnumHandle0"
0x18000c778  jmp     short loc_18000C740
0x18000c77a  mov     rdx, [rbp+enumHandle]
0x18000c77e  lea     rax, [rbp+arg_18]
0x18000c782  mov     rcx, [rbp+var_50]
0x18000c786  lea     r9, [rbp+p]
0x18000c78a  or      r8d, 0FFFFFFFFh
0x18000c78e  mov     [rsp+80h+engineHandle], rax
0x18000c793  call    cs:__imp_IkeextSaEnum2
0x18000c799  test    eax, eax
0x18000c79b  jz      short loc_18000C7A6
0x18000c79d  lea     rdx, aIkeextsaenum2; "IkeextSaEnum2"
0x18000c7a4  jmp     short loc_18000C740
0x18000c7a6  mov     edx, [rbp+arg_18]
0x18000c7a9  mov     ebx, esi
0x18000c7ab  test    edx, edx
0x18000c7ad  jz      short loc_18000C809
0x18000c7af  mov     rax, [rbp+p]
0x18000c7b3  mov     ecx, ebx
0x18000c7b5  mov     r8, [rax+rcx*8]
0x18000c7b9  mov     rax, [r8+80h]
0x18000c7c0  mov     ecx, [rax]
0x18000c7c2  cmp     ecx, 0Ah
0x18000c7c5  ja      short loc_18000C803
0x18000c7c7  mov     r9d, 792h
0x18000c7cd  bt      r9d, ecx
0x18000c7d1  jnb     short loc_18000C803
0x18000c7d3  cmp     [rax+4], esi
0x18000c7d6  jnz     short loc_18000C803
0x18000c7d8  mov     rax, [rax+8]
0x18000c7dc  test    byte ptr [rax+20h], 1
0x18000c7e0  jnz     short loc_18000C803
0x18000c7e2  mov     rcx, [rbp+var_50]
0x18000c7e6  lea     rdx, [r8+88h]
0x18000c7ed  lea     r8, [rbp+arg_0]
0x18000c7f1  call    FwhcDoesPolicyEnableNap
0x18000c7f6  test    eax, eax
0x18000c7f8  js      short loc_18000C848
0x18000c7fa  cmp     [rbp+arg_0], sil
0x18000c7fe  jnz     short loc_18000C843
0x18000c800  mov     edx, [rbp+arg_18]
0x18000c803  inc     ebx
0x18000c805  cmp     ebx, edx
0x18000c807  jb      short loc_18000C7AF
0x18000c809  mov     rbx, rsi
0x18000c80c  lea     rcx, [rbp+p]; p
0x18000c810  call    cs:__imp_FwpmFreeMemory0
0x18000c816  mov     rdx, [rbp+enumHandle]; enumHandle
0x18000c81a  mov     rcx, [rbp+var_50]; engineHandle
0x18000c81e  call    cs:__imp_IkeextSaDestroyEnumHandle0
0x18000c824  mov     rcx, [rbp+var_50]; engineHandle
0x18000c828  call    cs:__imp_FwpmEngineClose0
0x18000c82e  mov     eax, ebx
0x18000c830  mov     rbx, [rsp+80h+arg_8]
0x18000c838  add     rsp, 80h
0x18000c83f  pop     rdi
0x18000c840  pop     rsi
0x18000c841  pop     rbp
0x18000c842  retn
0x18000c843  mov     byte ptr [rdi], 1
0x18000c846  jmp     short loc_18000C809
0x18000c848  mov     r9d, 1
0x18000c84e  lea     rdx, aFwhcdoespolicy; "FwhcDoesPolicyEnableNap"
0x18000c855  mov     r8d, eax
0x18000c858  call    WfpReportSysErrorAsHResult
0x18000c85d  jmp     loc_18000C748
```
