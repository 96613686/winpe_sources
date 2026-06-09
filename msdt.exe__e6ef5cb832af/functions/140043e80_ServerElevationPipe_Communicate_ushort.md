# ServerElevationPipe::Communicate(ushort * *)

- ea: `0x140043e80`
- end: `0x140044157`
- name: `?Communicate@ServerElevationPipe@@UEAAJPEAPEAG@Z`
- size: `727`
- prototype: `__int64 __fastcall(ServerElevationPipe *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140006fe0`
- `0x140010eb4`
- `0x140020420`
- `0x140043e80`
- `0x140049d88`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140044024`
- `KERNEL32!GetLastError` at `0x14004407d`
- `KERNEL32!GetLastError` at `0x140044090`
- `KERNEL32!GetLastError` at `0x140044024`
- `KERNEL32!GetLastError` at `0x14004407d`
- `KERNEL32!GetLastError` at `0x140044090`
- `KERNEL32!HeapAlloc` at `0x140043ef8`
- `KERNEL32!HeapAlloc` at `0x140043ef8`
- `KERNEL32!HeapFree` at `0x14004410d`
- `KERNEL32!HeapFree` at `0x140044136`
- `KERNEL32!HeapFree` at `0x14004410d`
- `KERNEL32!HeapFree` at `0x140044136`
- `KERNEL32!GetProcessHeap` at `0x140043ee1`
- `KERNEL32!GetProcessHeap` at `0x1400440f9`
- `KERNEL32!GetProcessHeap` at `0x140044120`
- `KERNEL32!GetProcessHeap` at `0x140043ee1`
- `KERNEL32!GetProcessHeap` at `0x1400440f9`
- `KERNEL32!GetProcessHeap` at `0x140044120`
- `KERNEL32!WriteFile` at `0x14004400e`
- `KERNEL32!WriteFile` at `0x14004400e`
- `KERNEL32!ReadFile` at `0x14004406b`
- `KERNEL32!ReadFile` at `0x14004406b`

## string_xrefs

- `0x140043ec4`: `ServerElevationPipe::Communicate`
- `0x1400440e1`: `ServerElevationPipe::Communicate`

## pseudocode

```c
__int64 __fastcall ServerElevationPipe::Communicate(ServerElevationPipe *this, unsigned __int16 **a2)
{
  int v3; // eax
  signed int v4; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rsi
  int ResolutionsRun; // eax
  int v9; // r9d
  const unsigned __int16 *v10; // r8
  __int64 v11; // rdi
  __int64 v12; // rax
  signed int LastError; // eax
  BOOL v14; // edi
  signed int v15; // eax
  HANDLE v16; // rax
  HANDLE v17; // rax
  LPVOID lpMem; // [rsp+30h] [rbp-38h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+70h] [rbp+8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+18h] BYREF
  char Buffer; // [rsp+88h] [rbp+20h] BYREF

  NumberOfBytesWritten = 0;
  nNumberOfBytesToWrite = 0;
  lpMem = 0;
  v3 = (*(__int64 (__fastcall **)(ServerElevationPipe *, __int64))(*(_QWORD *)this + 32LL))(this, 0xFFFFFFFFLL);
  v4 = v3;
  if ( v3 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ServerElevationPipe::Communicate", 353, v3);
    return (unsigned int)v4;
  }
  ProcessHeap = GetProcessHeap();
  v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x1000u);
  v7 = v6;
  if ( !v6 )
  {
    v4 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ServerElevationPipe::Communicate", 355, -2147024882);
    return (unsigned int)v4;
  }
  *v6 = 0;
  ResolutionsRun = Packages_GetResolutionsRun((unsigned __int16 **)&lpMem);
  v4 = ResolutionsRun;
  if ( ResolutionsRun < 0 )
  {
    v9 = 363;
LABEL_36:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ServerElevationPipe::Communicate", v9, ResolutionsRun);
    goto LABEL_37;
  }
  if ( lpMem )
  {
    ResolutionsRun = StringCchCatW(v7, 0x800u, (const unsigned __int16 *)lpMem);
    v4 = ResolutionsRun;
    if ( ResolutionsRun < 0 )
    {
      v9 = 367;
      goto LABEL_36;
    }
  }
  ResolutionsRun = StringCchCatW(v7, 0x800u, L";");
  v4 = ResolutionsRun;
  if ( ResolutionsRun < 0 )
  {
    v9 = 371;
    goto LABEL_36;
  }
  v10 = (const unsigned __int16 *)*((_QWORD *)this + 4);
  v11 = -1;
  if ( v10 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v10[v12] );
    if ( v12 )
    {
      ResolutionsRun = StringCchCatW(v7, 0x800u, v10);
      v4 = ResolutionsRun;
      if ( ResolutionsRun < 0 )
      {
        v9 = 375;
        goto LABEL_36;
      }
    }
  }
  do
    ++v11;
  while ( v7[v11] );
  ResolutionsRun = ULongLongToULong(2 * v11 + 2, &nNumberOfBytesToWrite);
  v4 = ResolutionsRun;
  if ( ResolutionsRun < 0 )
  {
    v9 = 379;
    goto LABEL_36;
  }
  if ( !WriteFile(*((HANDLE *)this + 1), v7, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ServerElevationPipe::Communicate", 386, v4);
      goto LABEL_37;
    }
  }
  v14 = ReadFile(*((HANDLE *)this + 1), &Buffer, 4u, 0, (LPOVERLAPPED)((char *)this + 40));
  if ( v14 || GetLastError() == 997 )
  {
    v4 = 0;
    if ( v14 )
      goto LABEL_37;
  }
  else
  {
    v15 = GetLastError();
    v4 = v15;
    if ( v15 > 0 )
      v4 = (unsigned __int16)v15 | 0x80070000;
    if ( v4 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "ServerElevationPipe::Communicate", 398, v4);
      goto LABEL_37;
    }
  }
  ResolutionsRun = (*(__int64 (__fastcall **)(ServerElevationPipe *, __int64))(*(_QWORD *)this + 32LL))(
                     this,
                     0xFFFFFFFFLL);
  v4 = ResolutionsRun;
  if ( ResolutionsRun < 0 )
  {
    v9 = 405;
    goto LABEL_36;
  }
LABEL_37:
  v16 = GetProcessHeap();
  HeapFree(v16, 0, v7);
  if ( lpMem )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, lpMem);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140043e80  mov     rax, rsp
0x140043e83  mov     [rax+10h], rbx
0x140043e87  push    rsi
0x140043e88  push    rdi
0x140043e89  push    r12
0x140043e8b  push    r14
0x140043e8d  push    r15
0x140043e8f  sub     rsp, 40h
0x140043e93  xor     r15d, r15d
0x140043e96  or      edx, 0FFFFFFFFh
0x140043e99  mov     [rax+18h], r15d
0x140043e9d  mov     r14, rcx
0x140043ea0  mov     [rax+8], r15d
0x140043ea4  mov     [rax-38h], r15
0x140043ea8  mov     rax, [rcx]
0x140043eab  mov     rax, [rax+20h]
0x140043eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043eb4  mov     ebx, eax
0x140043eb6  test    eax, eax
0x140043eb8  jns     short loc_140043EE1
0x140043eba  mov     dword ptr [rsp+68h+lpOverlapped], eax
0x140043ebe  mov     r9d, 161h
0x140043ec4  lea     r8, aServerelevatio_0; "ServerElevationPipe::Communicate"
0x140043ecb  mov     ecx, 1; Level
0x140043ed0  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140043ed7  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140043edc  jmp     loc_140044142
0x140043ee1  call    cs:__imp_GetProcessHeap
0x140043ee8  nop     dword ptr [rax+rax+00h]
0x140043eed  xor     edx, edx; dwFlags
0x140043eef  mov     r8d, 1000h; dwBytes
0x140043ef5  mov     rcx, rax; hHeap
0x140043ef8  call    cs:__imp_HeapAlloc
0x140043eff  nop     dword ptr [rax+rax+00h]
0x140043f04  mov     rsi, rax
0x140043f07  test    rax, rax
0x140043f0a  jnz     short loc_140043F1D
0x140043f0c  mov     ebx, 8007000Eh
0x140043f11  mov     r9d, 163h
0x140043f17  mov     dword ptr [rsp+68h+lpOverlapped], ebx
0x140043f1b  jmp     short loc_140043EC4
0x140043f1d  lea     rcx, [rsp+68h+lpMem]; unsigned __int16 **
0x140043f22  mov     [rax], r15w
0x140043f26  call    ?Packages_GetResolutionsRun@@YAJPEAPEAG@Z; Packages_GetResolutionsRun(ushort * *)
0x140043f2b  mov     ebx, eax
0x140043f2d  test    eax, eax
0x140043f2f  jns     short loc_140043F3C
0x140043f31  mov     r9d, 16Bh
0x140043f37  jmp     loc_1400440DD
0x140043f3c  mov     r12d, 800h
0x140043f42  cmp     [rsp+68h+lpMem], r15
0x140043f47  jz      short loc_140043F6A
0x140043f49  mov     r8, [rsp+68h+lpMem]; unsigned __int16 *
0x140043f4e  mov     edx, r12d; unsigned __int64
0x140043f51  mov     rcx, rsi; unsigned __int16 *
0x140043f54  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140043f59  mov     ebx, eax
0x140043f5b  test    eax, eax
0x140043f5d  jns     short loc_140043F6A
0x140043f5f  mov     r9d, 16Fh
0x140043f65  jmp     loc_1400440DD
0x140043f6a  lea     r8, asc_14006DF60; ";"
0x140043f71  mov     rdx, r12; unsigned __int64
0x140043f74  mov     rcx, rsi; unsigned __int16 *
0x140043f77  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140043f7c  mov     ebx, eax
0x140043f7e  test    eax, eax
0x140043f80  jns     short loc_140043F8D
0x140043f82  mov     r9d, 173h
0x140043f88  jmp     loc_1400440DD
0x140043f8d  mov     r8, [r14+20h]; unsigned __int16 *
0x140043f91  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140043f95  test    r8, r8
0x140043f98  jz      short loc_140043FC8
0x140043f9a  mov     rax, rdi
0x140043f9d  inc     rax
0x140043fa0  cmp     [r8+rax*2], r15w
0x140043fa5  jnz     short loc_140043F9D
0x140043fa7  test    rax, rax
0x140043faa  jz      short loc_140043FC8
0x140043fac  mov     rdx, r12; unsigned __int64
0x140043faf  mov     rcx, rsi; unsigned __int16 *
0x140043fb2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140043fb7  mov     ebx, eax
0x140043fb9  test    eax, eax
0x140043fbb  jns     short loc_140043FC8
0x140043fbd  mov     r9d, 177h
0x140043fc3  jmp     loc_1400440DD
0x140043fc8  inc     rdi
0x140043fcb  cmp     [rsi+rdi*2], r15w
0x140043fd0  jnz     short loc_140043FC8
0x140043fd2  lea     rcx, ds:2[rdi*2]; unsigned __int64
0x140043fda  lea     rdx, [rsp+68h+nNumberOfBytesToWrite]; unsigned int *
0x140043fdf  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140043fe4  mov     ebx, eax
0x140043fe6  test    eax, eax
0x140043fe8  jns     short loc_140043FF5
0x140043fea  mov     r9d, 17Bh
0x140043ff0  jmp     loc_1400440DD
0x140043ff5  mov     r8d, [rsp+68h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x140043ffa  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140044002  mov     rcx, [r14+8]; hFile
0x140044006  mov     rdx, rsi; lpBuffer
0x140044009  mov     [rsp+68h+lpOverlapped], r15; lpOverlapped
0x14004400e  call    cs:__imp_WriteFile
0x140044015  nop     dword ptr [rax+rax+00h]
0x14004401a  mov     r12d, 80070000h
0x140044020  test    eax, eax
0x140044022  jnz     short loc_14004404F
0x140044024  call    cs:__imp_GetLastError
0x14004402b  nop     dword ptr [rax+rax+00h]
0x140044030  mov     ebx, eax
0x140044032  test    eax, eax
0x140044034  jle     short loc_14004403C
0x140044036  movzx   ebx, ax
0x140044039  or      ebx, r12d
0x14004403c  test    ebx, ebx
0x14004403e  jns     short loc_14004404F
0x140044040  mov     dword ptr [rsp+68h+lpOverlapped], ebx
0x140044044  mov     r9d, 182h
0x14004404a  jmp     loc_1400440E1
0x14004404f  mov     rcx, [r14+8]; hFile
0x140044053  lea     rax, [r14+28h]
0x140044057  xor     r9d, r9d; lpNumberOfBytesRead
0x14004405a  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x14004405f  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x140044067  lea     r8d, [r9+4]; nNumberOfBytesToRead
0x14004406b  call    cs:__imp_ReadFile
0x140044072  nop     dword ptr [rax+rax+00h]
0x140044077  mov     edi, eax
0x140044079  test    eax, eax
0x14004407b  jnz     short loc_1400440B8
0x14004407d  call    cs:__imp_GetLastError
0x140044084  nop     dword ptr [rax+rax+00h]
0x140044089  cmp     eax, 3E5h
0x14004408e  jz      short loc_1400440B8
0x140044090  call    cs:__imp_GetLastError
0x140044097  nop     dword ptr [rax+rax+00h]
0x14004409c  mov     ebx, eax
0x14004409e  test    eax, eax
0x1400440a0  jle     short loc_1400440A8
0x1400440a2  movzx   ebx, ax
0x1400440a5  or      ebx, r12d
0x1400440a8  test    ebx, ebx
0x1400440aa  jns     short loc_1400440BF
0x1400440ac  mov     dword ptr [rsp+68h+lpOverlapped], ebx
0x1400440b0  mov     r9d, 18Eh
0x1400440b6  jmp     short loc_1400440E1
0x1400440b8  mov     ebx, r15d
0x1400440bb  test    edi, edi
0x1400440bd  jnz     short loc_1400440F9
0x1400440bf  mov     rax, [r14]
0x1400440c2  or      edx, 0FFFFFFFFh
0x1400440c5  mov     rcx, r14
0x1400440c8  mov     rax, [rax+20h]
0x1400440cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400440d1  mov     ebx, eax
0x1400440d3  test    eax, eax
0x1400440d5  jns     short loc_1400440F9
0x1400440d7  mov     r9d, 195h
0x1400440dd  mov     dword ptr [rsp+68h+lpOverlapped], eax
0x1400440e1  lea     r8, aServerelevatio_0; "ServerElevationPipe::Communicate"
0x1400440e8  mov     ecx, 1; Level
0x1400440ed  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400440f4  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400440f9  call    cs:__imp_GetProcessHeap
0x140044100  nop     dword ptr [rax+rax+00h]
0x140044105  mov     r8, rsi; lpMem
0x140044108  xor     edx, edx; dwFlags
0x14004410a  mov     rcx, rax; hHeap
0x14004410d  call    cs:__imp_HeapFree
0x140044114  nop     dword ptr [rax+rax+00h]
0x140044119  cmp     [rsp+68h+lpMem], r15
0x14004411e  jz      short loc_140044142
0x140044120  call    cs:__imp_GetProcessHeap
0x140044127  nop     dword ptr [rax+rax+00h]
0x14004412c  mov     r8, [rsp+68h+lpMem]; lpMem
0x140044131  xor     edx, edx; dwFlags
0x140044133  mov     rcx, rax; hHeap
0x140044136  call    cs:__imp_HeapFree
0x14004413d  nop     dword ptr [rax+rax+00h]
0x140044142  mov     eax, ebx
0x140044144  mov     rbx, [rsp+68h+arg_8]
0x140044149  add     rsp, 40h
0x14004414d  pop     r15
0x14004414f  pop     r14
0x140044151  pop     r12
0x140044153  pop     rdi
0x140044154  pop     rsi
0x140044155  retn
```
