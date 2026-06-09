# DShow::COutputQueue::COutputQueue(IPin *,long *,int,int,long,int,long,ulong,bool)

- ea: `0x18003ee24`
- end: `0x18003f035`
- name: `??0COutputQueue@DShow@@QEAA@PEAUIPin@@PEAJHHJHJK_N@Z`
- size: `529`
- prototype: `__int64 __usercall@<rax>(DShow::COutputQueue *__hidden this@<rcx>, struct IPin *@<rdx>, int *@<r8>, int@<r9d>, int, int, int, int, unsigned int, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003eb58`

## callees

- `0x18003ee24`
- `0x180073d0c`
- `0x180073d58`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003ee45`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18003ee45`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ee7d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003ee7d`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18003ef66`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18003ef66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ef7b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003efea`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003efea`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003f008`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18003f008`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
DShow::COutputQueue *__fastcall DShow::COutputQueue::COutputQueue(
        DShow::COutputQueue *this,
        struct IPin *a2,
        DWORD *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        unsigned int a9,
        DWORD ThreadId)
{
  HANDLE EventW; // rax
  int v15; // eax
  int v16; // esi
  int v17; // eax
  void *v18; // rax
  HANDLE Semaphore; // rax
  _QWORD *v20; // rax
  HANDLE v21; // rax

  InitializeCriticalSection((LPCRITICAL_SECTION)this);
  *((_QWORD *)this + 5) = a2;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_DWORD *)this + 15) = 1;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 10) = EventW;
  if ( !EventW && a3 && (*a3 & 0x80000000) == 0 )
    *a3 = -2147024882;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_DWORD *)this + 29) = 1;
  *((_BYTE *)this + 120) = 0;
  *(_QWORD *)((char *)this + 124) = 0;
  *((_DWORD *)this + 33) = 0;
  *((_QWORD *)this + 17) = 0;
  if ( (*a3 & 0x80000000) == 0 )
  {
    v15 = ((__int64 (__fastcall *)(struct IPin *, GUID *, char *))a2->lpVtbl->QueryInterface)(
            a2,
            &IID_IMemInputPin,
            (char *)this + 48);
    *a3 = v15;
    if ( v15 >= 0 )
    {
      v16 = 0;
      if ( a4 )
      {
        v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
        if ( v17 >= 0 )
          LOBYTE(v16) = v17 == 0;
      }
      v18 = operator new[](saturated_mul(*((int *)this + 15), 8u));
      *((_QWORD *)this + 12) = v18;
      if ( !v18 )
        goto LABEL_18;
      if ( v16 )
      {
        Semaphore = CreateSemaphoreExW(0, 0, 0x7FFFFFFF, 0, 0, 0x1F0003u);
        *((_QWORD *)this + 9) = Semaphore;
        if ( !Semaphore )
        {
LABEL_13:
          *a3 = GetLastError() | 0x80070000;
          return this;
        }
        v20 = operator new(0x28u);
        if ( v20 )
        {
          *v20 = 0;
          v20[1] = 0;
          *((_DWORD *)v20 + 4) = 0;
          v20[3] = 10;
          v20[4] = 0;
          *((_QWORD *)this + 8) = v20;
          ThreadId = 0;
          v21 = CreateThread(0, 0, DShow::COutputQueue::InitialThreadProc, this, 0, &ThreadId);
          *((_QWORD *)this + 11) = v21;
          if ( v21 )
          {
            SetThreadPriority(v21, 0);
            return this;
          }
          goto LABEL_13;
        }
        *((_QWORD *)this + 8) = 0;
LABEL_18:
        *a3 = -2147024882;
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x18003ee24  mov     [rsp+arg_10], rbx
0x18003ee29  mov     [rsp+arg_0], rcx
0x18003ee2e  push    rbp
0x18003ee2f  push    rsi
0x18003ee30  push    rdi
0x18003ee31  push    r14
0x18003ee33  push    r15
0x18003ee35  sub     rsp, 30h
0x18003ee39  mov     ebp, r9d
0x18003ee3c  mov     rdi, r8
0x18003ee3f  mov     rsi, rdx
0x18003ee42  mov     rbx, rcx
0x18003ee45  call    cs:__imp_InitializeCriticalSection
0x18003ee4c  nop     dword ptr [rax+rax+00h]
0x18003ee51  nop
0x18003ee52  mov     [rbx+28h], rsi
0x18003ee56  lea     r14, [rbx+30h]
0x18003ee5a  xor     r15d, r15d
0x18003ee5d  mov     [r14], r15
0x18003ee60  mov     [rbx+38h], r15d
0x18003ee64  mov     dword ptr [rbx+3Ch], 1
0x18003ee6b  mov     [rbx+40h], r15
0x18003ee6f  mov     [rbx+48h], r15
0x18003ee73  xor     r9d, r9d; lpName
0x18003ee76  xor     r8d, r8d; bInitialState
0x18003ee79  xor     edx, edx; bManualReset
0x18003ee7b  xor     ecx, ecx; lpEventAttributes
0x18003ee7d  call    cs:__imp_CreateEventW
0x18003ee84  nop     dword ptr [rax+rax+00h]
0x18003ee89  mov     [rbx+50h], rax
0x18003ee8d  test    rax, rax
0x18003ee90  jnz     short loc_18003EEA2
0x18003ee92  test    rdi, rdi
0x18003ee95  jz      short loc_18003EEA2
0x18003ee97  cmp     [rdi], r15d
0x18003ee9a  jl      short loc_18003EEA2
0x18003ee9c  mov     dword ptr [rdi], 8007000Eh
0x18003eea2  mov     [rbx+58h], r15
0x18003eea6  mov     [rbx+60h], r15
0x18003eeaa  mov     [rbx+68h], r15
0x18003eeae  mov     [rbx+70h], r15d
0x18003eeb2  mov     dword ptr [rbx+74h], 1
0x18003eeb9  mov     [rbx+78h], r15b
0x18003eebd  mov     [rbx+7Ch], r15
0x18003eec1  mov     [rbx+84h], r15d
0x18003eec8  mov     [rbx+88h], r15
0x18003eecf  cmp     [rdi], r15d
0x18003eed2  jl      loc_18003F020
0x18003eed8  mov     rax, [rsi]
0x18003eedb  mov     r8, r14
0x18003eede  lea     rdx, IID_IMemInputPin
0x18003eee5  mov     rcx, rsi
0x18003eee8  mov     rax, [rax]
0x18003eeeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eef0  mov     [rdi], eax
0x18003eef2  test    eax, eax
0x18003eef4  js      loc_18003F020
0x18003eefa  mov     esi, r15d
0x18003eefd  test    ebp, ebp
0x18003eeff  jz      short loc_18003EF18
0x18003ef01  mov     rcx, [r14]
0x18003ef04  mov     rax, [rcx]
0x18003ef07  mov     rax, [rax+40h]
0x18003ef0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef10  test    eax, eax
0x18003ef12  js      short loc_18003EF18
0x18003ef14  setz    sil
0x18003ef18  movsxd  rcx, dword ptr [rbx+3Ch]
0x18003ef1c  mov     eax, 8
0x18003ef21  mul     rcx
0x18003ef24  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18003ef2b  cmovb   rax, rcx
0x18003ef2f  mov     rcx, rax; unsigned __int64
0x18003ef32  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003ef37  mov     [rbx+60h], rax
0x18003ef3b  test    rax, rax
0x18003ef3e  jz      loc_18003F01A
0x18003ef44  test    esi, esi
0x18003ef46  jz      loc_18003F020
0x18003ef4c  mov     [rsp+58h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18003ef54  mov     [rsp+58h+dwFlags], r15d; dwFlags
0x18003ef59  xor     r9d, r9d; lpName
0x18003ef5c  xor     edx, edx; lInitialCount
0x18003ef5e  xor     ecx, ecx; lpSemaphoreAttributes
0x18003ef60  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18003ef66  call    cs:__imp_CreateSemaphoreExW
0x18003ef6d  nop     dword ptr [rax+rax+00h]
0x18003ef72  mov     [rbx+48h], rax
0x18003ef76  test    rax, rax
0x18003ef79  jnz     short loc_18003EF93
0x18003ef7b  call    cs:__imp_GetLastError
0x18003ef82  nop     dword ptr [rax+rax+00h]
0x18003ef87  or      eax, 80070000h
0x18003ef8c  mov     [rdi], eax
0x18003ef8e  jmp     loc_18003F020
0x18003ef93  mov     ecx, 28h ; '('; Size
0x18003ef98  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ef9d  mov     [rsp+58h+arg_8], rax
0x18003efa2  test    rax, rax
0x18003efa5  jz      short loc_18003F016
0x18003efa7  mov     [rax], r15
0x18003efaa  mov     [rax+8], r15
0x18003efae  mov     [rax+10h], r15d
0x18003efb2  mov     qword ptr [rax+18h], 0Ah
0x18003efba  mov     [rax+20h], r15
0x18003efbe  mov     [rbx+40h], rax
0x18003efc2  mov     [rsp+58h+ThreadId], r15d
0x18003efca  lea     rax, [rsp+58h+ThreadId]
0x18003efd2  mov     qword ptr [rsp+58h+dwDesiredAccess], rax; lpThreadId
0x18003efd7  mov     [rsp+58h+dwFlags], r15d; dwCreationFlags
0x18003efdc  mov     r9, rbx; lpParameter
0x18003efdf  lea     r8, ?InitialThreadProc@COutputQueue@DShow@@KAKPEAX@Z; lpStartAddress
0x18003efe6  xor     edx, edx; dwStackSize
0x18003efe8  xor     ecx, ecx; lpThreadAttributes
0x18003efea  call    cs:__imp_CreateThread
0x18003eff1  nop     dword ptr [rax+rax+00h]
0x18003eff6  mov     [rbx+58h], rax
0x18003effa  test    rax, rax
0x18003effd  jz      loc_18003EF7B
0x18003f003  xor     edx, edx; nPriority
0x18003f005  mov     rcx, rax; hThread
0x18003f008  call    cs:__imp_SetThreadPriority
0x18003f00f  nop     dword ptr [rax+rax+00h]
0x18003f014  jmp     short loc_18003F020
0x18003f016  mov     [rbx+40h], r15
0x18003f01a  mov     dword ptr [rdi], 8007000Eh
0x18003f020  mov     rax, rbx
0x18003f023  mov     rbx, [rsp+58h+arg_10]
0x18003f028  add     rsp, 30h
0x18003f02c  pop     r15
0x18003f02e  pop     r14
0x18003f030  pop     rdi
0x18003f031  pop     rsi
0x18003f032  pop     rbp
0x18003f033  retn
```
