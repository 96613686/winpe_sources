# COutputQueue::COutputQueue(IPin *,long *,int,int,long,int,long,ulong,bool)

- ea: `0x18014bbf8`
- end: `0x18014bdb4`
- name: `??0COutputQueue@@QEAA@PEAUIPin@@PEAJHHJHJK_N@Z`
- size: `444`
- prototype: `COutputQueue *__usercall@<rax>(COutputQueue *__hidden this@<rcx>, struct IPin *@<rdx>, int *@<r8>, int@<r9d>, int, int, int, int, unsigned int, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800f1520`

## callees

- `0x180024d78`
- `0x180038458`
- `0x1800384a4`
- `0x18014bbf8`
- `0x18015e010`

## import_xrefs

- `KERNEL32!CreateSemaphoreW` at `0x18014bcf5`
- `KERNEL32!CreateSemaphoreW` at `0x18014bcf5`
- `KERNEL32!SetThreadPriority` at `0x18014bd8b`
- `KERNEL32!SetThreadPriority` at `0x18014bd8b`
- `KERNEL32!CreateThread` at `0x18014bd71`
- `KERNEL32!CreateThread` at `0x18014bd71`
- `KERNEL32!InitializeCriticalSection` at `0x18014bc0e`
- `KERNEL32!InitializeCriticalSection` at `0x18014bc0e`
- `KERNEL32!GetLastError` at `0x18014bd0a`
- `KERNEL32!GetLastError` at `0x18014bd0a`

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
  BOOL v13; // esi
  int v14; // eax
  int v15; // eax
  void *v16; // rax
  HANDLE SemaphoreW; // rax
  _QWORD *v18; // rax
  HANDLE v19; // rax

  InitializeCriticalSection((LPCRITICAL_SECTION)this);
  *((_QWORD *)this + 5) = a2;
  *((_DWORD *)this + 15) = 50;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 8) = 0;
  v13 = 1;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 14) = 1;
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
    v14 = ((__int64 (__fastcall *)(struct IPin *, GUID *, char *))a2->lpVtbl->QueryInterface)(
            a2,
            &IID_IMemInputPin,
            (char *)this + 48);
    *a3 = v14;
    if ( v14 >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6));
      if ( v15 >= 0 )
        v13 = v15 == 0;
      v16 = operator new[](saturated_mul(*((int *)this + 15), 8u));
      *((_QWORD *)this + 12) = v16;
      if ( !v16 )
        goto LABEL_13;
      if ( v13 )
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
          v18[3] = 50;
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
0x18014bbf8  push    rbx
0x18014bbfa  push    rbp
0x18014bbfb  push    rsi
0x18014bbfc  push    rdi
0x18014bbfd  push    r14
0x18014bbff  push    r15
0x18014bc01  sub     rsp, 38h
0x18014bc05  mov     rdi, r8
0x18014bc08  mov     r15, rdx
0x18014bc0b  mov     rbx, rcx
0x18014bc0e  call    cs:__imp_InitializeCriticalSection
0x18014bc15  nop     dword ptr [rax+rax+00h]
0x18014bc1a  xor     ebp, ebp
0x18014bc1c  mov     [rbx+28h], r15
0x18014bc20  lea     r14, [rbx+30h]
0x18014bc24  mov     dword ptr [rbx+3Ch], 32h ; '2'
0x18014bc2b  lea     rcx, [rbx+50h]; this
0x18014bc2f  mov     [r14], rbp
0x18014bc32  mov     r8, rdi; int *
0x18014bc35  mov     [rbx+40h], rbp
0x18014bc39  lea     esi, [rbp+1]
0x18014bc3c  mov     [rbx+48h], rbp
0x18014bc40  xor     edx, edx; int
0x18014bc42  mov     [rbx+38h], esi
0x18014bc45  call    ??0CAMEvent@@QEAA@HPEAJ@Z; CAMEvent::CAMEvent(int,long *)
0x18014bc4a  mov     [rbx+58h], rbp
0x18014bc4e  mov     [rbx+60h], rbp
0x18014bc52  mov     [rbx+68h], rbp
0x18014bc56  mov     [rbx+70h], ebp
0x18014bc59  mov     [rbx+74h], esi
0x18014bc5c  mov     [rbx+78h], bpl
0x18014bc60  mov     [rbx+7Ch], rbp
0x18014bc64  mov     [rbx+84h], ebp
0x18014bc6a  mov     [rbx+88h], rbp
0x18014bc71  cmp     [rdi], ebp
0x18014bc73  jl      loc_18014BDA3
0x18014bc79  mov     rax, [r15]
0x18014bc7c  lea     rdx, IID_IMemInputPin
0x18014bc83  mov     r8, r14
0x18014bc86  mov     rcx, r15
0x18014bc89  mov     rax, [rax]
0x18014bc8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014bc91  mov     [rdi], eax
0x18014bc93  test    eax, eax
0x18014bc95  js      loc_18014BDA3
0x18014bc9b  mov     rcx, [r14]
0x18014bc9e  mov     rax, [rcx]
0x18014bca1  mov     rax, [rax+40h]
0x18014bca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014bcaa  test    eax, eax
0x18014bcac  js      short loc_18014BCB4
0x18014bcae  mov     esi, ebp
0x18014bcb0  setz    sil
0x18014bcb4  movsxd  rcx, dword ptr [rbx+3Ch]
0x18014bcb8  mov     eax, 8
0x18014bcbd  mul     rcx
0x18014bcc0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18014bcc7  cmovb   rax, rcx
0x18014bccb  mov     rcx, rax; unsigned __int64
0x18014bcce  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18014bcd3  mov     [rbx+60h], rax
0x18014bcd7  test    rax, rax
0x18014bcda  jz      loc_18014BD9D
0x18014bce0  test    esi, esi
0x18014bce2  jz      loc_18014BDA3
0x18014bce8  xor     r9d, r9d; lpName
0x18014bceb  xor     edx, edx; lInitialCount
0x18014bced  xor     ecx, ecx; lpSemaphoreAttributes
0x18014bcef  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18014bcf5  call    cs:__imp_CreateSemaphoreW
0x18014bcfc  nop     dword ptr [rax+rax+00h]
0x18014bd01  mov     [rbx+48h], rax
0x18014bd05  test    rax, rax
0x18014bd08  jnz     short loc_18014BD22
0x18014bd0a  call    cs:__imp_GetLastError
0x18014bd11  nop     dword ptr [rax+rax+00h]
0x18014bd16  or      eax, 80070000h
0x18014bd1b  mov     [rdi], eax
0x18014bd1d  jmp     loc_18014BDA3
0x18014bd22  mov     ecx, 28h ; '('; Size
0x18014bd27  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18014bd2c  test    rax, rax
0x18014bd2f  jz      short loc_18014BD99
0x18014bd31  mov     [rax], rbp
0x18014bd34  lea     r8, ?InitialThreadProc@COutputQueue@@KAKPEAX@Z; lpStartAddress
0x18014bd3b  mov     [rax+8], rbp
0x18014bd3f  mov     r9, rbx; lpParameter
0x18014bd42  mov     [rax+10h], ebp
0x18014bd45  xor     edx, edx; dwStackSize
0x18014bd47  mov     qword ptr [rax+18h], 32h ; '2'
0x18014bd4f  xor     ecx, ecx; lpThreadAttributes
0x18014bd51  mov     [rax+20h], rbp
0x18014bd55  mov     [rbx+40h], rax
0x18014bd59  lea     rax, [rsp+68h+ThreadId]
0x18014bd61  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x18014bd66  mov     [rsp+68h+dwCreationFlags], ebp; dwCreationFlags
0x18014bd6a  mov     [rsp+68h+ThreadId], ebp
0x18014bd71  call    cs:__imp_CreateThread
0x18014bd78  nop     dword ptr [rax+rax+00h]
0x18014bd7d  mov     [rbx+58h], rax
0x18014bd81  test    rax, rax
0x18014bd84  jz      short loc_18014BD0A
0x18014bd86  xor     edx, edx; nPriority
0x18014bd88  mov     rcx, rax; hThread
0x18014bd8b  call    cs:__imp_SetThreadPriority
0x18014bd92  nop     dword ptr [rax+rax+00h]
0x18014bd97  jmp     short loc_18014BDA3
0x18014bd99  mov     [rbx+40h], rbp
0x18014bd9d  mov     dword ptr [rdi], 8007000Eh
0x18014bda3  mov     rax, rbx
0x18014bda6  add     rsp, 38h
0x18014bdaa  pop     r15
0x18014bdac  pop     r14
0x18014bdae  pop     rdi
0x18014bdaf  pop     rsi
0x18014bdb0  pop     rbp
0x18014bdb1  pop     rbx
0x18014bdb2  retn
```
