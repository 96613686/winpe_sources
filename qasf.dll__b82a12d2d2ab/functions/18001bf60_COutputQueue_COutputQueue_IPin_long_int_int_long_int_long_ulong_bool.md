# COutputQueue::COutputQueue(IPin *,long *,int,int,long,int,long,ulong,bool)

- ea: `0x18001bf60`
- end: `0x18001c102`
- name: `??0COutputQueue@@QEAA@PEAUIPin@@PEAJHHJHJK_N@Z`
- size: `418`
- prototype: `COutputQueue *__usercall@<rax>(COutputQueue *__hidden this@<rcx>, struct IPin *@<rdx>, int *@<r8>, int@<r9d>, int, int, int, int, unsigned int, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800081a0`

## callees

- `0x180001014`
- `0x180001020`
- `0x18000770c`
- `0x18001bf60`
- `0x18001f010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18001bf75`
- `KERNEL32!InitializeCriticalSection` at `0x18001bf75`
- `KERNEL32!GetLastError` at `0x18001c06c`
- `KERNEL32!GetLastError` at `0x18001c06c`
- `KERNEL32!CreateThread` at `0x18001c0cd`
- `KERNEL32!CreateThread` at `0x18001c0cd`
- `KERNEL32!SetThreadPriority` at `0x18001c0e1`
- `KERNEL32!SetThreadPriority` at `0x18001c0e1`
- `KERNEL32!CreateSemaphoreW` at `0x18001c05d`
- `KERNEL32!CreateSemaphoreW` at `0x18001c05d`

## pseudocode

```c
COutputQueue *__fastcall COutputQueue::COutputQueue(
        COutputQueue *this,
        struct IPin *a2,
        int *a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        unsigned int a9,
        DWORD ThreadId)
{
  int v13; // eax
  int v14; // esi
  int v15; // eax
  void *v16; // rax
  HANDLE SemaphoreW; // rax
  _QWORD *v18; // rax
  HANDLE v19; // rax

  InitializeCriticalSection((LPCRITICAL_SECTION)this);
  *((_QWORD *)this + 5) = a2;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 15) = 1;
  CAMEvent::CAMEvent((COutputQueue *)((char *)this + 80), 0, a3);
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *((_DWORD *)this + 29) = 1;
  *((_BYTE *)this + 120) = 0;
  *(_QWORD *)((char *)this + 124) = 0;
  *((_DWORD *)this + 33) = 0;
  *((_QWORD *)this + 17) = 0;
  if ( *a3 >= 0 )
  {
    v13 = ((__int64 (__fastcall *)(struct IPin *, GUID *, char *))a2->lpVtbl->QueryInterface)(
            a2,
            &IID_IMemInputPin,
            (char *)this + 48);
    *a3 = v13;
    if ( v13 >= 0 )
    {
      v14 = 0;
      v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
      if ( v15 >= 0 )
        LOBYTE(v14) = v15 == 0;
      v16 = operator new[](saturated_mul(*((int *)this + 15), 8u));
      *((_QWORD *)this + 12) = v16;
      if ( !v16 )
        goto LABEL_13;
      if ( v14 )
      {
        SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
        *((_QWORD *)this + 9) = SemaphoreW;
        if ( !SemaphoreW )
        {
LABEL_8:
          *a3 = GetLastError() | 0x80070000;
          return this;
        }
        v18 = operator new(0x28u);
        if ( v18 )
        {
          *v18 = 0;
          v18[1] = 0;
          *((_DWORD *)v18 + 4) = 0;
          v18[3] = 10;
          v18[4] = 0;
          *((_QWORD *)this + 8) = v18;
          ThreadId = 0;
          v19 = CreateThread(0, 0, COutputQueue::InitialThreadProc, this, 0, &ThreadId);
          *((_QWORD *)this + 11) = v19;
          if ( v19 )
          {
            SetThreadPriority(v19, 0);
            return this;
          }
          goto LABEL_8;
        }
        *((_QWORD *)this + 8) = 0;
LABEL_13:
        *a3 = -2147024882;
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x18001bf60  push    rbx
0x18001bf62  push    rsi
0x18001bf63  push    rdi
0x18001bf64  push    r14
0x18001bf66  push    r15
0x18001bf68  sub     rsp, 30h
0x18001bf6c  mov     rdi, r8
0x18001bf6f  mov     rsi, rdx
0x18001bf72  mov     rbx, rcx
0x18001bf75  call    cs:__imp_InitializeCriticalSection
0x18001bf7b  xor     r15d, r15d
0x18001bf7e  mov     [rbx+28h], rsi
0x18001bf82  lea     r14, [rbx+30h]
0x18001bf86  mov     [rbx+38h], r15d
0x18001bf8a  lea     rcx, [rbx+50h]; this
0x18001bf8e  mov     [r14], r15
0x18001bf91  mov     r8, rdi; int *
0x18001bf94  mov     [rbx+40h], r15
0x18001bf98  xor     edx, edx; int
0x18001bf9a  mov     [rbx+48h], r15
0x18001bf9e  mov     dword ptr [rbx+3Ch], 1
0x18001bfa5  call    ??0CAMEvent@@QEAA@HPEAJ@Z; CAMEvent::CAMEvent(int,long *)
0x18001bfaa  mov     [rbx+58h], r15
0x18001bfae  mov     [rbx+60h], r15
0x18001bfb2  mov     [rbx+68h], r15
0x18001bfb6  mov     [rbx+70h], r15d
0x18001bfba  mov     dword ptr [rbx+74h], 1
0x18001bfc1  mov     [rbx+78h], r15b
0x18001bfc5  mov     [rbx+7Ch], r15
0x18001bfc9  mov     [rbx+84h], r15d
0x18001bfd0  mov     [rbx+88h], r15
0x18001bfd7  cmp     [rdi], r15d
0x18001bfda  jl      loc_18001C0F3
0x18001bfe0  mov     rax, [rsi]
0x18001bfe3  lea     rdx, IID_IMemInputPin
0x18001bfea  mov     r8, r14
0x18001bfed  mov     rcx, rsi
0x18001bff0  mov     rax, [rax]
0x18001bff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bff8  mov     [rdi], eax
0x18001bffa  test    eax, eax
0x18001bffc  js      loc_18001C0F3
0x18001c002  mov     rcx, [r14]
0x18001c005  mov     esi, r15d
0x18001c008  mov     rax, [rcx]
0x18001c00b  mov     rax, [rax+40h]
0x18001c00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c014  test    eax, eax
0x18001c016  js      short loc_18001C01C
0x18001c018  setz    sil
0x18001c01c  movsxd  rcx, dword ptr [rbx+3Ch]
0x18001c020  mov     eax, 8
0x18001c025  mul     rcx
0x18001c028  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001c02f  cmovb   rax, rcx
0x18001c033  mov     rcx, rax; unsigned __int64
0x18001c036  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001c03b  mov     [rbx+60h], rax
0x18001c03f  test    rax, rax
0x18001c042  jz      loc_18001C0ED
0x18001c048  test    esi, esi
0x18001c04a  jz      loc_18001C0F3
0x18001c050  xor     r9d, r9d; lpName
0x18001c053  xor     edx, edx; lInitialCount
0x18001c055  xor     ecx, ecx; lpSemaphoreAttributes
0x18001c057  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18001c05d  call    cs:__imp_CreateSemaphoreW
0x18001c063  mov     [rbx+48h], rax
0x18001c067  test    rax, rax
0x18001c06a  jnz     short loc_18001C07B
0x18001c06c  call    cs:__imp_GetLastError
0x18001c072  or      eax, 80070000h
0x18001c077  mov     [rdi], eax
0x18001c079  jmp     short loc_18001C0F3
0x18001c07b  mov     ecx, 28h ; '('; Size
0x18001c080  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c085  test    rax, rax
0x18001c088  jz      short loc_18001C0E9
0x18001c08a  mov     [rax], r15
0x18001c08d  lea     r8, ?InitialThreadProc@COutputQueue@@KAKPEAX@Z; lpStartAddress
0x18001c094  mov     [rax+8], r15
0x18001c098  mov     r9, rbx; lpParameter
0x18001c09b  mov     [rax+10h], r15d
0x18001c09f  xor     edx, edx; dwStackSize
0x18001c0a1  mov     qword ptr [rax+18h], 0Ah
0x18001c0a9  xor     ecx, ecx; lpThreadAttributes
0x18001c0ab  mov     [rax+20h], r15
0x18001c0af  mov     [rbx+40h], rax
0x18001c0b3  lea     rax, [rsp+58h+ThreadId]
0x18001c0bb  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18001c0c0  mov     [rsp+58h+dwCreationFlags], r15d; dwCreationFlags
0x18001c0c5  mov     [rsp+58h+ThreadId], r15d
0x18001c0cd  call    cs:__imp_CreateThread
0x18001c0d3  mov     [rbx+58h], rax
0x18001c0d7  test    rax, rax
0x18001c0da  jz      short loc_18001C06C
0x18001c0dc  xor     edx, edx; nPriority
0x18001c0de  mov     rcx, rax; hThread
0x18001c0e1  call    cs:__imp_SetThreadPriority
0x18001c0e7  jmp     short loc_18001C0F3
0x18001c0e9  mov     [rbx+40h], r15
0x18001c0ed  mov     dword ptr [rdi], 8007000Eh
0x18001c0f3  mov     rax, rbx
0x18001c0f6  add     rsp, 30h
0x18001c0fa  pop     r15
0x18001c0fc  pop     r14
0x18001c0fe  pop     rdi
0x18001c0ff  pop     rsi
0x18001c100  pop     rbx
0x18001c101  retn
```
