# FTP_ENDPOINT::ListenAndUpdateSettings(ulong)

- ea: `0x180031df8`
- end: `0x180031f79`
- name: `?ListenAndUpdateSettings@FTP_ENDPOINT@@QEAAJK@Z`
- size: `385`
- prototype: `__int64 __fastcall(FTP_ENDPOINT *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180031f80`

## callees

- `0x180006fc0`
- `0x180007578`
- `0x1800076b8`
- `0x180031aa0`
- `0x180031df8`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x180031e94`
- `KERNEL32!GetSystemInfo` at `0x180031ebe`
- `KERNEL32!GetSystemInfo` at `0x180031f1e`
- `KERNEL32!GetSystemInfo` at `0x180031f48`
- `KERNEL32!GetSystemInfo` at `0x180031e94`
- `KERNEL32!GetSystemInfo` at `0x180031ebe`
- `KERNEL32!GetSystemInfo` at `0x180031f1e`
- `KERNEL32!GetSystemInfo` at `0x180031f48`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180031e19`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180031e19`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180031f62`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180031f62`

## pseudocode

```c
__int64 __fastcall FTP_ENDPOINT::ListenAndUpdateSettings(struct sockaddr *this, unsigned int a2)
{
  CReaderWriterLock3 *v2; // r12
  int v5; // esi
  DWORD dwNumberOfProcessors; // eax
  DWORD v7; // eax
  struct _SYSTEM_INFO SystemInfo; // [rsp+20h] [rbp-30h] BYREF

  v2 = (CReaderWriterLock3 *)&this[59].sa_data[6];
  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)&this[59].sa_data[6]);
  if ( *(_QWORD *)&this[10].sa_data[6] == -1 )
  {
    v5 = FTP_ASYNC_SOCKET::Initialize((FTP_ASYNC_SOCKET *)&this[9].sa_data[6], this[1].sa_family);
    if ( v5 >= 0 )
    {
      v5 = FTP_ASYNC_SOCKET::Bind((FTP_ASYNC_SOCKET *)&this[9].sa_data[6], this + 1);
      if ( v5 >= 0 )
      {
        v5 = FTP_ASYNC_SOCKET::Listen((FTP_ASYNC_SOCKET *)&this[9].sa_data[6], a2);
        if ( v5 >= 0 )
        {
          dwNumberOfProcessors = `NumProcessors'::`2'::s_nCPUs;
          *(_DWORD *)&this[60].sa_family = a2;
          if ( !dwNumberOfProcessors )
          {
            memset(&SystemInfo, 0, sizeof(SystemInfo));
            GetSystemInfo(&SystemInfo);
            dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
            `NumProcessors'::`2'::s_nCPUs = SystemInfo.dwNumberOfProcessors;
          }
          if ( a2 >= dwNumberOfProcessors )
          {
            if ( !dwNumberOfProcessors )
            {
              memset(&SystemInfo, 0, sizeof(SystemInfo));
              GetSystemInfo(&SystemInfo);
              dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
              `NumProcessors'::`2'::s_nCPUs = SystemInfo.dwNumberOfProcessors;
            }
            a2 = dwNumberOfProcessors;
          }
          *(_DWORD *)&this[62].sa_data[10] = a2;
          FTP_ENDPOINT::AddOnePendingConnection((FTP_ENDPOINT *)this, 0);
        }
      }
    }
  }
  else
  {
    v5 = 0;
    if ( a2 > *(_DWORD *)&this[60].sa_family )
    {
      v5 = FTP_ASYNC_SOCKET::Listen((FTP_ASYNC_SOCKET *)&this[9].sa_data[6], a2);
      if ( v5 >= 0 )
      {
        v7 = `NumProcessors'::`2'::s_nCPUs;
        *(_DWORD *)&this[60].sa_family = a2;
        if ( !v7 )
        {
          memset(&SystemInfo, 0, sizeof(SystemInfo));
          GetSystemInfo(&SystemInfo);
          v7 = SystemInfo.dwNumberOfProcessors;
          `NumProcessors'::`2'::s_nCPUs = SystemInfo.dwNumberOfProcessors;
        }
        if ( a2 >= v7 )
        {
          if ( !v7 )
          {
            memset(&SystemInfo, 0, sizeof(SystemInfo));
            GetSystemInfo(&SystemInfo);
            v7 = SystemInfo.dwNumberOfProcessors;
            `NumProcessors'::`2'::s_nCPUs = SystemInfo.dwNumberOfProcessors;
          }
          a2 = v7;
        }
        *(_DWORD *)&this[62].sa_data[10] = a2;
      }
    }
  }
  CReaderWriterLock3::WriteUnlock(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180031df8  push    rbp
0x180031dfa  push    rbx
0x180031dfb  push    rsi
0x180031dfc  push    rdi
0x180031dfd  push    r12
0x180031dff  push    r14
0x180031e01  push    r15
0x180031e03  mov     rbp, rsp
0x180031e06  sub     rsp, 50h
0x180031e0a  lea     r12, [rcx+3B8h]
0x180031e11  mov     rdi, rcx
0x180031e14  mov     rcx, r12
0x180031e17  mov     ebx, edx
0x180031e19  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180031e1f  lea     r14, [rdi+98h]
0x180031e26  cmp     qword ptr [r14+10h], 0FFFFFFFFFFFFFFFFh
0x180031e2b  jnz     loc_180031EE1
0x180031e31  movzx   edx, word ptr [rdi+10h]; af
0x180031e35  mov     rcx, r14; this
0x180031e38  call    ?Initialize@FTP_ASYNC_SOCKET@@QEAAJK@Z; FTP_ASYNC_SOCKET::Initialize(ulong)
0x180031e3d  mov     esi, eax
0x180031e3f  test    eax, eax
0x180031e41  js      loc_180031F5F
0x180031e47  lea     rdx, [rdi+10h]; struct sockaddr *
0x180031e4b  mov     rcx, r14; this
0x180031e4e  call    ?Bind@FTP_ASYNC_SOCKET@@QEAAJPEAUsockaddr@@@Z; FTP_ASYNC_SOCKET::Bind(sockaddr *)
0x180031e53  mov     esi, eax
0x180031e55  test    eax, eax
0x180031e57  js      loc_180031F5F
0x180031e5d  mov     edx, ebx; unsigned int
0x180031e5f  mov     rcx, r14; this
0x180031e62  call    ?Listen@FTP_ASYNC_SOCKET@@QEAAJK@Z; FTP_ASYNC_SOCKET::Listen(ulong)
0x180031e67  mov     esi, eax
0x180031e69  test    eax, eax
0x180031e6b  js      loc_180031F5F
0x180031e71  mov     eax, cs:?s_nCPUs@?1??NumProcessors@@9@4HA; int `NumProcessors'::`2'::s_nCPUs
0x180031e77  mov     [rdi+3C0h], ebx
0x180031e7d  test    eax, eax
0x180031e7f  jnz     short loc_180031EA3
0x180031e81  xorps   xmm0, xmm0
0x180031e84  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x180031e88  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180031e8c  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180031e90  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180031e94  call    cs:__imp_GetSystemInfo
0x180031e9a  mov     eax, [rbp+SystemInfo.dwNumberOfProcessors]
0x180031e9d  mov     cs:?s_nCPUs@?1??NumProcessors@@9@4HA, eax; int `NumProcessors'::`2'::s_nCPUs
0x180031ea3  cmp     ebx, eax
0x180031ea5  jb      short loc_180031ECF
0x180031ea7  test    eax, eax
0x180031ea9  jnz     short loc_180031ECD
0x180031eab  xorps   xmm0, xmm0
0x180031eae  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x180031eb2  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180031eb6  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180031eba  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180031ebe  call    cs:__imp_GetSystemInfo
0x180031ec4  mov     eax, [rbp+SystemInfo.dwNumberOfProcessors]
0x180031ec7  mov     cs:?s_nCPUs@?1??NumProcessors@@9@4HA, eax; int `NumProcessors'::`2'::s_nCPUs
0x180031ecd  mov     ebx, eax
0x180031ecf  xor     edx, edx; int *
0x180031ed1  mov     [rdi+3ECh], ebx
0x180031ed7  mov     rcx, rdi; this
0x180031eda  call    ?AddOnePendingConnection@FTP_ENDPOINT@@AEAAJPEAH@Z; FTP_ENDPOINT::AddOnePendingConnection(int *)
0x180031edf  jmp     short loc_180031F5F
0x180031ee1  xor     esi, esi
0x180031ee3  cmp     ebx, [rdi+3C0h]
0x180031ee9  jbe     short loc_180031F5F
0x180031eeb  mov     edx, ebx; unsigned int
0x180031eed  mov     rcx, r14; this
0x180031ef0  call    ?Listen@FTP_ASYNC_SOCKET@@QEAAJK@Z; FTP_ASYNC_SOCKET::Listen(ulong)
0x180031ef5  mov     esi, eax
0x180031ef7  test    eax, eax
0x180031ef9  js      short loc_180031F5F
0x180031efb  mov     eax, cs:?s_nCPUs@?1??NumProcessors@@9@4HA; int `NumProcessors'::`2'::s_nCPUs
0x180031f01  mov     [rdi+3C0h], ebx
0x180031f07  test    eax, eax
0x180031f09  jnz     short loc_180031F2D
0x180031f0b  xorps   xmm0, xmm0
0x180031f0e  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x180031f12  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180031f16  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180031f1a  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180031f1e  call    cs:__imp_GetSystemInfo
0x180031f24  mov     eax, [rbp+SystemInfo.dwNumberOfProcessors]
0x180031f27  mov     cs:?s_nCPUs@?1??NumProcessors@@9@4HA, eax; int `NumProcessors'::`2'::s_nCPUs
0x180031f2d  cmp     ebx, eax
0x180031f2f  jb      short loc_180031F59
0x180031f31  test    eax, eax
0x180031f33  jnz     short loc_180031F57
0x180031f35  xorps   xmm0, xmm0
0x180031f38  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x180031f3c  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180031f40  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180031f44  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180031f48  call    cs:__imp_GetSystemInfo
0x180031f4e  mov     eax, [rbp+SystemInfo.dwNumberOfProcessors]
0x180031f51  mov     cs:?s_nCPUs@?1??NumProcessors@@9@4HA, eax; int `NumProcessors'::`2'::s_nCPUs
0x180031f57  mov     ebx, eax
0x180031f59  mov     [rdi+3ECh], ebx
0x180031f5f  mov     rcx, r12
0x180031f62  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180031f68  mov     eax, esi
0x180031f6a  add     rsp, 50h
0x180031f6e  pop     r15
0x180031f70  pop     r14
0x180031f72  pop     r12
0x180031f74  pop     rdi
0x180031f75  pop     rsi
0x180031f76  pop     rbx
0x180031f77  pop     rbp
0x180031f78  retn
```
