# VMR9::CVideoMixer::SetNumberOfStreams(ulong)

- ea: `0x1800e0350`
- end: `0x1800e0586`
- name: `?SetNumberOfStreams@CVideoMixer@VMR9@@UEAAJK@Z`
- size: `566`
- prototype: `__int64 __fastcall(VMR9::CVideoMixer *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180038458`
- `0x180038498`
- `0x1800384a4`
- `0x180039250`
- `0x1800db3fc`
- `0x1800e0350`
- `0x1800e18cc`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1800e04de`
- `KERNEL32!CreateThread` at `0x1800e04de`
- `KERNEL32!SetEvent` at `0x1800e0525`
- `KERNEL32!SetEvent` at `0x18015d11c`
- `KERNEL32!SetEvent` at `0x1800e0525`
- `KERNEL32!SetEvent` at `0x18015d11c`
- `KERNEL32!CreateEventW` at `0x1800e0482`
- `KERNEL32!CreateEventW` at `0x1800e04a6`
- `KERNEL32!CreateEventW` at `0x1800e0482`
- `KERNEL32!CreateEventW` at `0x1800e04a6`
- `KERNEL32!LeaveCriticalSection` at `0x1800e0391`
- `KERNEL32!LeaveCriticalSection` at `0x1800e0573`
- `KERNEL32!LeaveCriticalSection` at `0x1800e0391`
- `KERNEL32!LeaveCriticalSection` at `0x1800e0573`
- `KERNEL32!EnterCriticalSection` at `0x1800e0377`
- `KERNEL32!EnterCriticalSection` at `0x1800e0377`
- `KERNEL32!GetLastError` at `0x1800e04f6`
- `KERNEL32!GetLastError` at `0x1800e04f6`

## pseudocode

```c
__int64 __fastcall VMR9::CVideoMixer::SetNumberOfStreams(VMR9::CVideoMixer *this, unsigned int a2)
{
  unsigned __int64 v2; // r15
  struct _RTL_CRITICAL_SECTION *v4; // r12
  __int64 v5; // rdx
  signed int v6; // ebx
  void *v8; // rax
  __int64 i; // rsi
  int v10; // r14d
  VMR9::CVideoMixerStream *v11; // rax
  HANDLE EventW; // rax
  HANDLE v13; // rax
  HANDLE Thread; // rax
  signed int LastError; // eax
  void *v16; // rcx
  __int64 j; // rsi
  VMR9::CVideoMixerStream *v18; // rcx
  int v19; // [rsp+80h] [rbp+18h] BYREF

  v2 = a2;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v6 = 0;
  if ( *((_DWORD *)this + 26) )
  {
    LeaveCriticalSection(v4);
    return 2147500037LL;
  }
  else
  {
    if ( (unsigned int)v2 <= 0x10 )
    {
      v8 = operator new[](saturated_mul(v2, 8u));
      *((_QWORD *)this + 14) = v8;
      if ( v8 )
      {
        memset_0(v8, 0, 8 * v2);
        for ( i = 0; (unsigned int)i < (unsigned int)v2; i = (unsigned int)(i + 1) )
        {
          v10 = 0;
          v19 = 0;
          v11 = (VMR9::CVideoMixerStream *)operator new(0x648u);
          if ( v11 )
          {
            v5 = VMR9::CVideoMixerStream::CVideoMixerStream(v11, i, &v19);
            v10 = v19;
          }
          else
          {
            v5 = 0;
          }
          *(_QWORD *)(*((_QWORD *)this + 14) + 8 * i) = v5;
          if ( !*(_QWORD *)(*((_QWORD *)this + 14) + 8 * i) )
            goto LABEL_6;
          if ( v10 < 0 )
          {
            v6 = v10;
            goto LABEL_21;
          }
        }
        *((_DWORD *)this + 26) = v2;
        EventW = CreateEventW(0, 1, 0, 0);
        *((_QWORD *)this + 16) = EventW;
        if ( !EventW
          || (v13 = CreateEventW(0, 1, 0, 0), (*((_QWORD *)this + 15) = v13) == 0)
          || (Thread = CreateThread(0, 0, VMR9::CVideoMixer::MixerThreadProc, (char *)this - 24, 0, (LPDWORD)this + 36),
              (*((_QWORD *)this + 17) = Thread) == 0) )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
LABEL_6:
        v6 = -2147024882;
      }
    }
    else
    {
      v6 = -2147024809;
    }
LABEL_21:
    if ( v6 < 0 )
    {
      v16 = (void *)*((_QWORD *)this + 16);
      if ( v16 )
        SetEvent(v16);
      if ( *((_QWORD *)this + 14) )
      {
        for ( j = 0; (unsigned int)j < (unsigned int)v2; j = (unsigned int)(j + 1) )
        {
          v18 = *(VMR9::CVideoMixerStream **)(*((_QWORD *)this + 14) + 8 * j);
          if ( v18 )
            VMR9::CVideoMixerStream::`scalar deleting destructor'(v18, v5);
        }
      }
      operator delete(*((void **)this + 14));
      *((_QWORD *)this + 14) = 0;
      *((_DWORD *)this + 26) = 0;
    }
    LeaveCriticalSection(v4);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x1800e0350  mov     [rsp+arg_18], rbx
0x1800e0355  mov     [rsp+arg_8], edx
0x1800e0359  mov     [rsp+arg_0], rcx
0x1800e035e  push    rsi
0x1800e035f  push    rdi
0x1800e0360  push    r12
0x1800e0362  push    r14
0x1800e0364  push    r15
0x1800e0366  sub     rsp, 40h
0x1800e036a  mov     r15d, edx
0x1800e036d  mov     rdi, rcx
0x1800e0370  lea     r12, [rcx+18h]
0x1800e0374  mov     rcx, r12; lpCriticalSection
0x1800e0377  call    cs:__imp_EnterCriticalSection
0x1800e037e  nop     dword ptr [rax+rax+00h]
0x1800e0383  xor     ebx, ebx
0x1800e0385  mov     [rsp+68h+var_38], ebx
0x1800e0389  cmp     [rdi+68h], ebx
0x1800e038c  jz      short loc_1800E03B8
0x1800e038e  mov     rcx, r12; lpCriticalSection
0x1800e0391  call    cs:__imp_LeaveCriticalSection
0x1800e0398  nop     dword ptr [rax+rax+00h]
0x1800e039d  mov     eax, 80004005h
0x1800e03a2  mov     rbx, [rsp+68h+arg_18]
0x1800e03aa  add     rsp, 40h
0x1800e03ae  pop     r15
0x1800e03b0  pop     r14
0x1800e03b2  pop     r12
0x1800e03b4  pop     rdi
0x1800e03b5  pop     rsi
0x1800e03b6  retn
0x1800e03b8  cmp     r15d, 10h
0x1800e03bc  jbe     short loc_1800E03C8
0x1800e03be  mov     ebx, 80070057h
0x1800e03c3  jmp     loc_1800E0511
0x1800e03c8  mov     eax, 8
0x1800e03cd  mul     r15
0x1800e03d0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800e03d7  cmovb   rax, rcx
0x1800e03db  mov     rcx, rax; unsigned __int64
0x1800e03de  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800e03e3  mov     [rdi+70h], rax
0x1800e03e7  test    rax, rax
0x1800e03ea  jnz     short loc_1800E03F6
0x1800e03ec  mov     ebx, 8007000Eh
0x1800e03f1  jmp     loc_1800E0511
0x1800e03f6  lea     r8, ds:0[r15*8]; Size
0x1800e03fe  xor     edx, edx; Val
0x1800e0400  mov     rcx, rax; void *
0x1800e0403  call    memset_0
0x1800e0408  xor     esi, esi
0x1800e040a  mov     [rsp+68h+var_34], esi
0x1800e040e  cmp     esi, r15d
0x1800e0411  jnb     short loc_1800E0472
0x1800e0413  xor     r14d, r14d
0x1800e0416  mov     [rsp+68h+arg_10], r14d
0x1800e041e  mov     ecx, 648h; Size
0x1800e0423  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e0428  test    rax, rax
0x1800e042b  jz      short loc_1800E044C
0x1800e042d  lea     r8, [rsp+68h+arg_10]; int *
0x1800e0435  mov     edx, esi; unsigned int
0x1800e0437  mov     rcx, rax; this
0x1800e043a  call    ??0CVideoMixerStream@VMR9@@QEAA@KPEAJ@Z; VMR9::CVideoMixerStream::CVideoMixerStream(ulong,long *)
0x1800e043f  mov     rdx, rax
0x1800e0442  mov     r14d, [rsp+68h+arg_10]
0x1800e044a  jmp     short loc_1800E044E
0x1800e044c  xor     edx, edx
0x1800e044e  mov     rax, [rdi+70h]
0x1800e0452  mov     [rax+rsi*8], rdx
0x1800e0456  mov     rax, [rdi+70h]
0x1800e045a  cmp     qword ptr [rax+rsi*8], 0
0x1800e045f  jz      short loc_1800E03EC
0x1800e0461  test    r14d, r14d
0x1800e0464  jns     short loc_1800E046E
0x1800e0466  mov     ebx, r14d
0x1800e0469  jmp     loc_1800E0511
0x1800e046e  inc     esi
0x1800e0470  jmp     short loc_1800E040A
0x1800e0472  mov     [rdi+68h], r15d
0x1800e0476  xor     r9d, r9d; lpName
0x1800e0479  xor     r8d, r8d; bInitialState
0x1800e047c  lea     edx, [r9+1]; bManualReset
0x1800e0480  xor     ecx, ecx; lpEventAttributes
0x1800e0482  call    cs:__imp_CreateEventW
0x1800e0489  nop     dword ptr [rax+rax+00h]
0x1800e048e  mov     [rdi+80h], rax
0x1800e0495  test    rax, rax
0x1800e0498  jz      short loc_1800E04F6
0x1800e049a  xor     r9d, r9d; lpName
0x1800e049d  xor     r8d, r8d; bInitialState
0x1800e04a0  lea     edx, [r9+1]; bManualReset
0x1800e04a4  xor     ecx, ecx; lpEventAttributes
0x1800e04a6  call    cs:__imp_CreateEventW
0x1800e04ad  nop     dword ptr [rax+rax+00h]
0x1800e04b2  mov     [rdi+78h], rax
0x1800e04b6  test    rax, rax
0x1800e04b9  jz      short loc_1800E04F6
0x1800e04bb  lea     rax, [rdi+90h]
0x1800e04c2  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x1800e04c7  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x1800e04cf  lea     r9, [rdi-18h]; lpParameter
0x1800e04d3  lea     r8, ?MixerThreadProc@CVideoMixer@VMR9@@SAKPEAX@Z; lpStartAddress
0x1800e04da  xor     edx, edx; dwStackSize
0x1800e04dc  xor     ecx, ecx; lpThreadAttributes
0x1800e04de  call    cs:__imp_CreateThread
0x1800e04e5  nop     dword ptr [rax+rax+00h]
0x1800e04ea  mov     [rdi+88h], rax
0x1800e04f1  test    rax, rax
0x1800e04f4  jnz     short loc_1800E0515
0x1800e04f6  call    cs:__imp_GetLastError
0x1800e04fd  nop     dword ptr [rax+rax+00h]
0x1800e0502  mov     ebx, eax
0x1800e0504  test    eax, eax
0x1800e0506  jle     short loc_1800E0511
0x1800e0508  movzx   ebx, ax
0x1800e050b  or      ebx, 80070000h
0x1800e0511  mov     [rsp+68h+var_38], ebx
0x1800e0515  test    ebx, ebx
0x1800e0517  jns     short loc_1800E0570
0x1800e0519  mov     rcx, [rdi+80h]; hEvent
0x1800e0520  test    rcx, rcx
0x1800e0523  jz      short loc_1800E0531
0x1800e0525  call    cs:__imp_SetEvent
0x1800e052c  nop     dword ptr [rax+rax+00h]
0x1800e0531  cmp     qword ptr [rdi+70h], 0
0x1800e0536  jz      short loc_1800E0558
0x1800e0538  xor     esi, esi
0x1800e053a  test    r15d, r15d
0x1800e053d  jz      short loc_1800E0558
0x1800e053f  mov     rax, [rdi+70h]
0x1800e0543  mov     rcx, [rax+rsi*8]; this
0x1800e0547  test    rcx, rcx
0x1800e054a  jz      short loc_1800E0551
0x1800e054c  call    ??_GCVideoMixerStream@VMR9@@QEAAPEAXI@Z; VMR9::CVideoMixerStream::`scalar deleting destructor'(uint)
0x1800e0551  inc     esi
0x1800e0553  cmp     esi, r15d
0x1800e0556  jb      short loc_1800E053F
0x1800e0558  mov     rcx, [rdi+70h]; Block
0x1800e055c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800e0561  mov     qword ptr [rdi+70h], 0
0x1800e0569  mov     dword ptr [rdi+68h], 0
0x1800e0570  mov     rcx, r12; lpCriticalSection
0x1800e0573  call    cs:__imp_LeaveCriticalSection
0x1800e057a  nop     dword ptr [rax+rax+00h]
0x1800e057f  mov     eax, ebx
0x1800e0581  jmp     loc_1800E03A2
0x18015d0f5  push    rbx
0x18015d0f7  push    rbp
0x18015d0f8  push    rsi
0x18015d0f9  push    rdi
0x18015d0fa  sub     rsp, 38h
0x18015d0fe  mov     rbp, rdx
0x18015d101  cmp     dword ptr [rbp+30h], 0
0x18015d105  jge     short loc_18015D170
0x18015d107  mov     rbx, [rbp+70h]
0x18015d10b  cmp     qword ptr [rbx+80h], 0
0x18015d113  jz      short loc_18015D129
0x18015d115  mov     rcx, [rbx+80h]; hEvent
0x18015d11c  call    cs:__imp_SetEvent
0x18015d123  nop     dword ptr [rax+rax+00h]
0x18015d128  nop
0x18015d129  cmp     qword ptr [rbx+70h], 0
0x18015d12e  jz      short loc_18015D158
0x18015d130  xor     edi, edi
0x18015d132  mov     [rbp+34h], edi
0x18015d135  mov     esi, [rbp+78h]
0x18015d138  test    esi, esi
0x18015d13a  jz      short loc_18015D158
0x18015d13c  mov     rax, [rbx+70h]
0x18015d140  mov     rcx, [rax+rdi*8]; this
0x18015d144  test    rcx, rcx
0x18015d147  jz      short loc_18015D14F
0x18015d149  call    ??_GCVideoMixerStream@VMR9@@QEAAPEAXI@Z; VMR9::CVideoMixerStream::`scalar deleting destructor'(uint)
0x18015d14e  nop
0x18015d14f  inc     edi
0x18015d151  cmp     edi, esi
0x18015d153  jb      short loc_18015D13C
0x18015d155  mov     [rbp+34h], edi
0x18015d158  mov     rcx, [rbx+70h]; Block
0x18015d15c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18015d161  mov     qword ptr [rbx+70h], 0
0x18015d169  mov     dword ptr [rbx+68h], 0
0x18015d170  add     rsp, 38h
0x18015d174  pop     rdi
0x18015d175  pop     rsi
0x18015d176  pop     rbp
0x18015d177  pop     rbx
0x18015d178  retn
```
