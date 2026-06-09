# NcaEtwPerfTrackGetHashId

- ea: `0x180018c40`
- end: `0x180018d7d`
- name: `NcaEtwPerfTrackGetHashId`
- size: `317`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800161c8`
- `0x180018b60`
- `0x180018d84`

## callees

- `0x180003770`
- `0x18000673c`
- `0x180018c40`
- `0x180019100`
- `0x18001c9e8`
- `0x18001cc70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018c83`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180018c83`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180018d10`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180018d10`
- `KERNEL32!GetComputerNameW` at `0x180018d00`
- `KERNEL32!GetComputerNameW` at `0x180018d3c`
- `KERNEL32!GetComputerNameW` at `0x180018d00`
- `KERNEL32!GetComputerNameW` at `0x180018d3c`

## pseudocode

```c
__int64 __fastcall NcaEtwPerfTrackGetHashId(int a1)
{
  int v1; // ecx
  __int64 v2; // rcx
  void *v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rcx
  DWORD nSize; // [rsp+20h] [rbp-50h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-48h] BYREF
  WCHAR Buffer[8]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v10; // [rsp+40h] [rbp-30h]
  struct _SYSTEMTIME SystemTime; // [rsp+50h] [rbp-20h] BYREF

  if ( !a1 )
  {
    nSize = 16;
    *(_OWORD *)Buffer = 0;
    v10 = 0;
    SystemTime = 0;
    GetComputerNameW(Buffer, &nSize);
    goto LABEL_10;
  }
  v1 = a1 - 1;
  if ( !v1 )
  {
    nSize = 16;
    *(_OWORD *)Buffer = 0;
    v10 = 0;
    SystemTime = 0;
    GetComputerNameW(Buffer, &nSize);
    GetSystemTime(&SystemTime);
LABEL_10:
    SymCryptMarvin32(v5, Buffer, 48, &lpMem);
    return (unsigned int)lpMem;
  }
  if ( v1 == 1 )
  {
    lpMem = 0;
    AcquireSRWLockShared(&SRWLock);
    NcaConfigMgrGetString(2, (__int64)&lpMem);
    NcaExcludeShareLockLeave(1, &SRWLock);
    v3 = lpMem;
    if ( lpMem )
    {
      v4 = -1;
      do
        ++v4;
      while ( *((_WORD *)lpMem + v4) );
      SymCryptMarvin32(v2, lpMem, (unsigned int)(2 * v4 + 2), &lpMem);
      NcaFree(v3);
    }
  }
  return (unsigned int)lpMem;
}

```

## disassembly

```asm
0x180018c40  mov     [rsp-8+arg_0], rbx
0x180018c45  mov     [rsp-8+arg_8], rdi
0x180018c4a  push    rbp
0x180018c4b  mov     rbp, rsp
0x180018c4e  sub     rsp, 70h
0x180018c52  mov     rax, cs:__security_cookie
0x180018c59  xor     rax, rsp
0x180018c5c  mov     [rbp+var_10], rax
0x180018c60  xor     edi, edi
0x180018c62  test    ecx, ecx
0x180018c64  jz      loc_180018D1E
0x180018c6a  sub     ecx, 1
0x180018c6d  jz      short loc_180018CE2
0x180018c6f  cmp     ecx, 1
0x180018c72  jnz     loc_180018D5B
0x180018c78  lea     rcx, SRWLock; SRWLock
0x180018c7f  mov     [rbp+lpMem], rdi
0x180018c83  call    cs:__imp_AcquireSRWLockShared
0x180018c8a  nop     dword ptr [rax+rax+00h]
0x180018c8f  lea     rdx, [rbp+lpMem]
0x180018c93  lea     ecx, [rdi+2]
0x180018c96  call    NcaConfigMgrGetString
0x180018c9b  lea     rdx, SRWLock
0x180018ca2  lea     ecx, [rdi+1]
0x180018ca5  call    NcaExcludeShareLockLeave
0x180018caa  mov     rbx, [rbp+lpMem]
0x180018cae  test    rbx, rbx
0x180018cb1  jz      loc_180018D5B
0x180018cb7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180018cbb  inc     rax
0x180018cbe  cmp     [rbx+rax*2], di
0x180018cc2  jnz     short loc_180018CBB
0x180018cc4  lea     r8d, ds:2[rax*2]
0x180018ccc  mov     rdx, rbx
0x180018ccf  lea     r9, [rbp+lpMem]
0x180018cd3  call    SymCryptMarvin32
0x180018cd8  mov     rcx, rbx; lpMem
0x180018cdb  call    NcaFree
0x180018ce0  jmp     short loc_180018D5B
0x180018ce2  xorps   xmm0, xmm0
0x180018ce5  mov     [rbp+nSize], 10h
0x180018cec  lea     rdx, [rbp+nSize]; nSize
0x180018cf0  lea     rcx, [rbp+Buffer]; lpBuffer
0x180018cf4  movups  xmmword ptr [rbp+Buffer], xmm0
0x180018cf8  movups  [rbp+var_30], xmm0
0x180018cfc  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180018d00  call    cs:__imp_GetComputerNameW
0x180018d07  nop     dword ptr [rax+rax+00h]
0x180018d0c  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180018d10  call    cs:__imp_GetSystemTime
0x180018d17  nop     dword ptr [rax+rax+00h]
0x180018d1c  jmp     short loc_180018D48
0x180018d1e  xorps   xmm0, xmm0
0x180018d21  mov     [rbp+nSize], 10h
0x180018d28  lea     rdx, [rbp+nSize]; nSize
0x180018d2c  lea     rcx, [rbp+Buffer]; lpBuffer
0x180018d30  movups  xmmword ptr [rbp+Buffer], xmm0
0x180018d34  movups  [rbp+var_30], xmm0
0x180018d38  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180018d3c  call    cs:__imp_GetComputerNameW
0x180018d43  nop     dword ptr [rax+rax+00h]
0x180018d48  lea     r9, [rbp+lpMem]
0x180018d4c  mov     r8d, 30h ; '0'
0x180018d52  lea     rdx, [rbp+Buffer]
0x180018d56  call    SymCryptMarvin32
0x180018d5b  mov     eax, dword ptr [rbp+lpMem]
0x180018d5e  mov     rcx, [rbp+var_10]
0x180018d62  xor     rcx, rsp; StackCookie
0x180018d65  call    __security_check_cookie
0x180018d6a  lea     r11, [rsp+70h+var_s0]
0x180018d6f  mov     rbx, [r11+10h]
0x180018d73  mov     rdi, [r11+18h]
0x180018d77  mov     rsp, r11
0x180018d7a  pop     rbp
0x180018d7b  retn
```
