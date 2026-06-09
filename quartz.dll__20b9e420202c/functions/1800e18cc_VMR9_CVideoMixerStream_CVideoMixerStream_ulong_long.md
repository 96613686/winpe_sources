# VMR9::CVideoMixerStream::CVideoMixerStream(ulong,long *)

- ea: `0x1800e18cc`
- end: `0x1800e1aa5`
- name: `??0CVideoMixerStream@VMR9@@QEAA@KPEAJ@Z`
- size: `473`
- prototype: `_QWORD(VMR9::CVideoMixerStream *__hidden this, unsigned int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800e0350`

## callees

- `0x180039250`
- `0x1800b93f0`
- `0x1800e18cc`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800e1a43`
- `KERNEL32!CreateEventW` at `0x1800e1a65`
- `KERNEL32!CreateEventW` at `0x1800e1a43`
- `KERNEL32!CreateEventW` at `0x1800e1a65`
- `KERNEL32!InitializeCriticalSection` at `0x1800e18de`
- `KERNEL32!InitializeCriticalSection` at `0x1800e18de`
- `KERNEL32!GetLastError` at `0x1800e1a7d`
- `KERNEL32!GetLastError` at `0x1800e1a7d`

## pseudocode

```c
VMR9::CVideoMixerStream *__fastcall VMR9::CVideoMixerStream::CVideoMixerStream(
        VMR9::CVideoMixerStream *this,
        int a2,
        int *a3)
{
  HANDLE EventW; // rax
  HANDLE v7; // rax
  signed int LastError; // eax

  InitializeCriticalSection((LPCRITICAL_SECTION)this);
  *((_DWORD *)this + 10) = a2;
  *(_QWORD *)((char *)this + 44) = 0;
  *((_DWORD *)this + 13) = 0;
  *((_DWORD *)this + 14) = 1065353216;
  *((_DWORD *)this + 15) = 15 - a2;
  VMR9::CVMRMixerQueue::CVMRMixerQueue((VMR9::CVideoMixerStream *)((char *)this + 80), a3);
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 42) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)this + 43) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)this + 194) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)this + 195) = 0x7FFFFFFFFFFFFFFFLL;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_DWORD *)this + 82) = 0;
  *((_QWORD *)this + 172) = 0;
  *((_DWORD *)this + 351) = 0;
  *((_QWORD *)this + 178) = 0;
  *((_QWORD *)this + 190) = 0;
  *((_DWORD *)this + 386) = 0;
  *((_DWORD *)this + 392) = 0;
  *(_QWORD *)((char *)this + 1596) = 0;
  memset_0((char *)this + 152, 0, 0x58u);
  *(_OWORD *)((char *)this + 280) = 0;
  *((_OWORD *)this + 88) = 0;
  memset_0((char *)this + 352, 0, 0x400u);
  *(_OWORD *)((char *)this + 296) = 0;
  *(_OWORD *)((char *)this + 312) = 0;
  *(_OWORD *)((char *)this + 1388) = 0;
  *(_OWORD *)((char *)this + 1432) = 0;
  *((_DWORD *)this + 362) = 0;
  *(_OWORD *)((char *)this + 1572) = 0;
  *(_QWORD *)((char *)this + 1588) = 0;
  memset_0((char *)this + 1452, 0, 0x40u);
  *(_OWORD *)((char *)this + 1528) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 18) = 1065353216;
  *((_DWORD *)this + 19) = 1065353216;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 31) = EventW;
  if ( !EventW || (v7 = CreateEventW(0, 1, 1, 0), (*((_QWORD *)this + 30) = v7) == 0) )
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
0x1800e18cc  push    rbx
0x1800e18ce  push    rsi
0x1800e18cf  push    rdi
0x1800e18d0  push    r14
0x1800e18d2  sub     rsp, 28h
0x1800e18d6  mov     rsi, r8
0x1800e18d9  mov     ebx, edx
0x1800e18db  mov     rdi, rcx
0x1800e18de  call    cs:__imp_InitializeCriticalSection
0x1800e18e5  nop     dword ptr [rax+rax+00h]
0x1800e18ea  xor     r14d, r14d
0x1800e18ed  mov     [rdi+28h], ebx
0x1800e18f0  lea     rcx, [rdi+50h]; this
0x1800e18f4  mov     [rdi+2Ch], r14
0x1800e18f8  mov     rdx, rsi; int *
0x1800e18fb  mov     [rdi+34h], r14d
0x1800e18ff  mov     dword ptr [rdi+38h], 3F800000h
0x1800e1906  lea     eax, [r14+0Fh]
0x1800e190a  sub     eax, ebx
0x1800e190c  mov     [rdi+3Ch], eax
0x1800e190f  call    ??0CVMRMixerQueue@VMR9@@QEAA@PEAJ@Z; VMR9::CVMRMixerQueue::CVMRMixerQueue(long *)
0x1800e1914  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800e191e  mov     [rdi+0F0h], r14
0x1800e1925  lea     rcx, [rdi+98h]; void *
0x1800e192c  mov     [rdi+150h], rax
0x1800e1933  xor     edx, edx; Val
0x1800e1935  mov     [rdi+158h], rax
0x1800e193c  lea     r8d, [r14+58h]; Size
0x1800e1940  mov     [rdi+610h], rax
0x1800e1947  mov     [rdi+618h], rax
0x1800e194e  mov     [rdi+0F8h], r14
0x1800e1955  mov     [rdi+100h], r14
0x1800e195c  mov     [rdi+108h], r14
0x1800e1963  mov     [rdi+110h], r14
0x1800e196a  mov     [rdi+148h], r14d
0x1800e1971  mov     [rdi+560h], r14
0x1800e1978  mov     [rdi+57Ch], r14d
0x1800e197f  mov     [rdi+590h], r14
0x1800e1986  mov     [rdi+5F0h], r14
0x1800e198d  mov     [rdi+608h], r14d
0x1800e1994  mov     [rdi+620h], r14d
0x1800e199b  mov     [rdi+63Ch], r14
0x1800e19a2  call    memset_0
0x1800e19a7  xorps   xmm0, xmm0
0x1800e19aa  lea     rcx, [rdi+160h]; void *
0x1800e19b1  xorps   xmm1, xmm1
0x1800e19b4  xor     edx, edx; Val
0x1800e19b6  movups  xmmword ptr [rdi+118h], xmm0
0x1800e19bd  mov     r8d, 400h; Size
0x1800e19c3  movups  xmmword ptr [rdi+580h], xmm1
0x1800e19ca  call    memset_0
0x1800e19cf  xorps   xmm0, xmm0
0x1800e19d2  lea     rcx, [rdi+5ACh]; void *
0x1800e19d9  movups  xmmword ptr [rdi+128h], xmm0
0x1800e19e0  xor     eax, eax
0x1800e19e2  xor     edx, edx; Val
0x1800e19e4  movups  xmmword ptr [rdi+138h], xmm0
0x1800e19eb  lea     r8d, [r14+40h]; Size
0x1800e19ef  movups  xmmword ptr [rdi+56Ch], xmm0
0x1800e19f6  xorps   xmm1, xmm1
0x1800e19f9  movups  xmmword ptr [rdi+598h], xmm1
0x1800e1a00  mov     [rdi+5A8h], eax
0x1800e1a06  movups  xmmword ptr [rdi+624h], xmm0
0x1800e1a0d  mov     [rdi+634h], rax
0x1800e1a14  call    memset_0
0x1800e1a19  xorps   xmm0, xmm0
0x1800e1a1c  lea     ebx, [r14+1]
0x1800e1a20  movups  xmmword ptr [rdi+5F8h], xmm0
0x1800e1a27  xor     r9d, r9d; lpName
0x1800e1a2a  mov     [rdi+40h], r14
0x1800e1a2e  xor     r8d, r8d; bInitialState
0x1800e1a31  mov     dword ptr [rdi+48h], 3F800000h
0x1800e1a38  mov     edx, ebx; bManualReset
0x1800e1a3a  mov     dword ptr [rdi+4Ch], 3F800000h
0x1800e1a41  xor     ecx, ecx; lpEventAttributes
0x1800e1a43  call    cs:__imp_CreateEventW
0x1800e1a4a  nop     dword ptr [rax+rax+00h]
0x1800e1a4f  mov     [rdi+0F8h], rax
0x1800e1a56  test    rax, rax
0x1800e1a59  jz      short loc_1800E1A7D
0x1800e1a5b  xor     r9d, r9d; lpName
0x1800e1a5e  mov     r8d, ebx; bInitialState
0x1800e1a61  mov     edx, ebx; bManualReset
0x1800e1a63  xor     ecx, ecx; lpEventAttributes
0x1800e1a65  call    cs:__imp_CreateEventW
0x1800e1a6c  nop     dword ptr [rax+rax+00h]
0x1800e1a71  mov     [rdi+0F0h], rax
0x1800e1a78  test    rax, rax
0x1800e1a7b  jnz     short loc_1800E1A97
0x1800e1a7d  call    cs:__imp_GetLastError
0x1800e1a84  nop     dword ptr [rax+rax+00h]
0x1800e1a89  test    eax, eax
0x1800e1a8b  jle     short loc_1800E1A95
0x1800e1a8d  movzx   eax, ax
0x1800e1a90  or      eax, 80070000h
0x1800e1a95  mov     [rsi], eax
0x1800e1a97  mov     rax, rdi
0x1800e1a9a  add     rsp, 28h
0x1800e1a9e  pop     r14
0x1800e1aa0  pop     rdi
0x1800e1aa1  pop     rsi
0x1800e1aa2  pop     rbx
0x1800e1aa3  retn
```
