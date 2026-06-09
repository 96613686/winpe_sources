# CVideoMixerStream::CVideoMixerStream(ulong,long *)

- ea: `0x1800b8350`
- end: `0x1800b8484`
- name: `??0CVideoMixerStream@@QEAA@KPEAJ@Z`
- size: `308`
- prototype: `CVideoMixerStream *(CVideoMixerStream *__hidden this, unsigned int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800b7380`

## callees

- `0x180039250`
- `0x1800b8350`
- `0x1800b93f0`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800b8423`
- `KERNEL32!CreateEventW` at `0x1800b8445`
- `KERNEL32!CreateEventW` at `0x1800b8423`
- `KERNEL32!CreateEventW` at `0x1800b8445`
- `KERNEL32!InitializeCriticalSection` at `0x1800b8361`
- `KERNEL32!InitializeCriticalSection` at `0x1800b8361`
- `KERNEL32!GetLastError` at `0x1800b845d`
- `KERNEL32!GetLastError` at `0x1800b845d`

## pseudocode

```c
CVideoMixerStream *__fastcall CVideoMixerStream::CVideoMixerStream(CVideoMixerStream *this, int a2, int *a3)
{
  HANDLE EventW; // rax
  HANDLE v7; // rax
  signed int LastError; // eax

  InitializeCriticalSection((LPCRITICAL_SECTION)this);
  *((_DWORD *)this + 10) = a2;
  *((_QWORD *)this + 7) = 1065353216;
  *(_QWORD *)((char *)this + 44) = 0;
  *((_DWORD *)this + 13) = 0;
  VMR9::CVMRMixerQueue::CVMRMixerQueue((CVideoMixerStream *)((char *)this + 88), a3);
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 43) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)this + 44) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_DWORD *)this + 84) = 0;
  memset_0((char *)this + 160, 0, 0x58u);
  *((_OWORD *)this + 18) = 0;
  *((_OWORD *)this + 19) = 0;
  *((_OWORD *)this + 20) = 0;
  *(_OWORD *)((char *)this + 372) = 0;
  *((_DWORD *)this + 18) = 1065353216;
  *((_DWORD *)this + 19) = 1065353216;
  *((_DWORD *)this + 20) = -1;
  *((_DWORD *)this + 21) = -1;
  *((_QWORD *)this + 8) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 32) = EventW;
  if ( !EventW || (v7 = CreateEventW(0, 1, 1, 0), (*((_QWORD *)this + 31) = v7) == 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    *a3 = LastError;
  }
  return this;
}

```

## disassembly

```asm
0x1800b8350  push    rbx
0x1800b8352  push    rbp
0x1800b8353  push    rsi
0x1800b8354  push    rdi
0x1800b8355  sub     rsp, 28h
0x1800b8359  mov     rsi, r8
0x1800b835c  mov     ebx, edx
0x1800b835e  mov     rdi, rcx
0x1800b8361  call    cs:__imp_InitializeCriticalSection
0x1800b8368  nop     dword ptr [rax+rax+00h]
0x1800b836d  mov     [rdi+28h], ebx
0x1800b8370  lea     rcx, [rdi+58h]; this
0x1800b8374  xor     ebp, ebp
0x1800b8376  mov     ebx, 3F800000h
0x1800b837b  mov     rdx, rsi; int *
0x1800b837e  mov     [rdi+38h], rbx
0x1800b8382  mov     [rdi+2Ch], rbp
0x1800b8386  mov     [rdi+34h], ebp
0x1800b8389  call    ??0CVMRMixerQueue@VMR9@@QEAA@PEAJ@Z; VMR9::CVMRMixerQueue::CVMRMixerQueue(long *)
0x1800b838e  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800b8398  mov     [rdi+0F8h], rbp
0x1800b839f  lea     rcx, [rdi+0A0h]; void *
0x1800b83a6  mov     [rdi+158h], rax
0x1800b83ad  xor     edx, edx; Val
0x1800b83af  mov     [rdi+160h], rax
0x1800b83b6  lea     r8d, [rbp+58h]; Size
0x1800b83ba  mov     [rdi+100h], rbp
0x1800b83c1  mov     [rdi+108h], rbp
0x1800b83c8  mov     [rdi+110h], rbp
0x1800b83cf  mov     [rdi+118h], rbp
0x1800b83d6  mov     [rdi+150h], ebp
0x1800b83dc  call    memset_0
0x1800b83e1  xorps   xmm0, xmm0
0x1800b83e4  xorps   xmm1, xmm1
0x1800b83e7  movups  xmmword ptr [rdi+120h], xmm0
0x1800b83ee  or      eax, 0FFFFFFFFh
0x1800b83f1  xor     r9d, r9d; lpName
0x1800b83f4  movups  xmmword ptr [rdi+130h], xmm1
0x1800b83fb  xor     r8d, r8d; bInitialState
0x1800b83fe  xor     ecx, ecx; lpEventAttributes
0x1800b8400  movups  xmmword ptr [rdi+140h], xmm1
0x1800b8407  movups  xmmword ptr [rdi+174h], xmm0
0x1800b840e  mov     [rdi+48h], ebx
0x1800b8411  mov     [rdi+4Ch], ebx
0x1800b8414  lea     ebx, [rbp+1]
0x1800b8417  mov     edx, ebx; bManualReset
0x1800b8419  mov     [rdi+50h], eax
0x1800b841c  mov     [rdi+54h], eax
0x1800b841f  mov     [rdi+40h], rbp
0x1800b8423  call    cs:__imp_CreateEventW
0x1800b842a  nop     dword ptr [rax+rax+00h]
0x1800b842f  mov     [rdi+100h], rax
0x1800b8436  test    rax, rax
0x1800b8439  jz      short loc_1800B845D
0x1800b843b  xor     r9d, r9d; lpName
0x1800b843e  mov     r8d, ebx; bInitialState
0x1800b8441  mov     edx, ebx; bManualReset
0x1800b8443  xor     ecx, ecx; lpEventAttributes
0x1800b8445  call    cs:__imp_CreateEventW
0x1800b844c  nop     dword ptr [rax+rax+00h]
0x1800b8451  mov     [rdi+0F8h], rax
0x1800b8458  test    rax, rax
0x1800b845b  jnz     short loc_1800B8477
0x1800b845d  call    cs:__imp_GetLastError
0x1800b8464  nop     dword ptr [rax+rax+00h]
0x1800b8469  test    eax, eax
0x1800b846b  jle     short loc_1800B8475
0x1800b846d  movzx   eax, ax
0x1800b8470  or      eax, 80070000h
0x1800b8475  mov     [rsi], eax
0x1800b8477  mov     rax, rdi
0x1800b847a  add     rsp, 28h
0x1800b847e  pop     rdi
0x1800b847f  pop     rsi
0x1800b8480  pop     rbp
0x1800b8481  pop     rbx
0x1800b8482  retn
```
