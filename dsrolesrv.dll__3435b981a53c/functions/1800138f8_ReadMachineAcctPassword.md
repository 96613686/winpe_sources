# ReadMachineAcctPassword

- ea: `0x1800138f8`
- end: `0x180013a06`
- name: `ReadMachineAcctPassword`
- size: `270`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003ff0`

## callees

- `0x1800138f8`
- `0x18002c012`
- `0x18002c01e`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013967`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013978`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x180013925`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x180013925`
- `LSASRV!LsarRetrievePrivateData` at `0x18001394f`
- `LSASRV!LsarRetrievePrivateData` at `0x18001394f`
- `ADVAPI32!LsaNtStatusToWinError` at `0x1800139e9`
- `ADVAPI32!LsaNtStatusToWinError` at `0x1800139e9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800139b3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800139b3`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800139dd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800139dd`

## pseudocode

```c
__int64 __fastcall ReadMachineAcctPassword(_QWORD *a1)
{
  unsigned int v2; // edi
  NTSTATUS LastError; // ebx
  HLOCAL v4; // rax
  void *v5; // rsi
  PVOID v6; // rcx
  __int64 v7; // rax
  _BYTE *v8; // rdx
  __int128 v10; // [rsp+20h] [rbp-10h] BYREF
  PVOID Buffer; // [rsp+58h] [rbp+28h] BYREF
  LSA_HANDLE ObjectHandle; // [rsp+60h] [rbp+30h] BYREF

  v2 = 0;
  ObjectHandle = 0;
  Buffer = 0;
  v10 = 0;
  LastError = LsaIOpenPolicyTrusted(&ObjectHandle);
  if ( LastError >= 0 )
  {
    *((_QWORD *)&v10 + 1) = L"$MACHINE.ACC";
    LODWORD(v10) = 1703960;
    LastError = LsarRetrievePrivateData(ObjectHandle, &v10, &Buffer);
    if ( LastError >= 0 )
    {
      v4 = LocalAlloc(0, *(unsigned int *)Buffer + 2LL);
      *a1 = v4;
      v5 = v4;
      if ( v4 )
      {
        memset_0(v4, 0, *(unsigned int *)Buffer + 2LL);
        memcpy_0(v5, *((const void **)Buffer + 1), *(unsigned int *)Buffer);
      }
      else
      {
        LastError = GetLastError();
      }
    }
  }
  if ( ObjectHandle )
    LsaClose(ObjectHandle);
  v6 = Buffer;
  if ( Buffer )
  {
    v7 = *(unsigned int *)Buffer;
    v8 = (_BYTE *)*((_QWORD *)Buffer + 1);
    if ( *(_DWORD *)Buffer )
    {
      do
      {
        *v8++ = 0;
        --v7;
      }
      while ( v7 );
      v6 = Buffer;
    }
    LsaFreeMemory(v6);
  }
  if ( LastError < 0 )
    return LsaNtStatusToWinError(LastError);
  return v2;
}

```

## disassembly

```asm
0x1800138f8  mov     [rsp-18h+arg_0], rbx
0x1800138fd  mov     [rsp-18h+arg_18], rsi
0x180013902  push    rbp
0x180013903  push    rdi
0x180013904  push    r14
0x180013906  mov     rbp, rsp
0x180013909  sub     rsp, 30h
0x18001390d  mov     r14, rcx
0x180013910  xor     edi, edi
0x180013912  xorps   xmm0, xmm0
0x180013915  mov     [rbp+ObjectHandle], rdi
0x180013919  lea     rcx, [rbp+ObjectHandle]
0x18001391d  mov     [rbp+Buffer], rdi
0x180013921  movups  [rbp+var_10], xmm0
0x180013925  call    cs:__imp_LsaIOpenPolicyTrusted
0x18001392b  mov     ebx, eax
0x18001392d  test    eax, eax
0x18001392f  js      short loc_1800139AA
0x180013931  mov     rcx, [rbp+ObjectHandle]
0x180013935  lea     rax, aMachineAcc; "$MACHINE.ACC"
0x18001393c  lea     r8, [rbp+Buffer]
0x180013940  mov     qword ptr [rbp+var_10+8], rax
0x180013944  lea     rdx, [rbp+var_10]
0x180013948  mov     dword ptr [rbp+var_10], 1A0018h
0x18001394f  call    cs:__imp_LsarRetrievePrivateData
0x180013955  mov     ebx, eax
0x180013957  test    eax, eax
0x180013959  js      short loc_1800139AA
0x18001395b  mov     rax, [rbp+Buffer]
0x18001395f  xor     ecx, ecx; uFlags
0x180013961  mov     edx, [rax]
0x180013963  add     rdx, 2; uBytes
0x180013967  call    cs:__imp_LocalAlloc
0x18001396d  mov     [r14], rax
0x180013970  mov     rsi, rax
0x180013973  test    rax, rax
0x180013976  jnz     short loc_180013982
0x180013978  call    cs:__imp_GetLastError
0x18001397e  mov     ebx, eax
0x180013980  jmp     short loc_1800139AA
0x180013982  mov     rax, [rbp+Buffer]
0x180013986  xor     edx, edx; Val
0x180013988  mov     rcx, rsi; void *
0x18001398b  mov     r8d, [rax]
0x18001398e  add     r8, 2; Size
0x180013992  call    memset_0
0x180013997  mov     rdx, [rbp+Buffer]
0x18001399b  mov     rcx, rsi; void *
0x18001399e  mov     r8d, [rdx]; Size
0x1800139a1  mov     rdx, [rdx+8]; Src
0x1800139a5  call    memcpy_0
0x1800139aa  mov     rcx, [rbp+ObjectHandle]; ObjectHandle
0x1800139ae  test    rcx, rcx
0x1800139b1  jz      short loc_1800139B9
0x1800139b3  call    cs:__imp_LsaClose
0x1800139b9  mov     rcx, [rbp+Buffer]
0x1800139bd  test    rcx, rcx
0x1800139c0  jz      short loc_1800139E3
0x1800139c2  mov     eax, [rcx]
0x1800139c4  mov     rdx, [rcx+8]
0x1800139c8  test    rax, rax
0x1800139cb  jz      short loc_1800139DD
0x1800139cd  mov     [rdx], dil
0x1800139d0  inc     rdx
0x1800139d3  sub     rax, 1
0x1800139d7  jnz     short loc_1800139CD
0x1800139d9  mov     rcx, [rbp+Buffer]; Buffer
0x1800139dd  call    cs:__imp_LsaFreeMemory
0x1800139e3  test    ebx, ebx
0x1800139e5  jns     short loc_1800139F1
0x1800139e7  mov     ecx, ebx; Status
0x1800139e9  call    cs:__imp_LsaNtStatusToWinError
0x1800139ef  mov     edi, eax
0x1800139f1  mov     rbx, [rsp+30h+arg_0]
0x1800139f6  mov     eax, edi
0x1800139f8  mov     rsi, [rsp+30h+arg_18]
0x1800139fd  add     rsp, 30h
0x180013a01  pop     r14
0x180013a03  pop     rdi
0x180013a04  pop     rbp
0x180013a05  retn
```
