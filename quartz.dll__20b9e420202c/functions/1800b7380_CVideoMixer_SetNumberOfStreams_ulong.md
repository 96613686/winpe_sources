# CVideoMixer::SetNumberOfStreams(ulong)

- ea: `0x1800b7380`
- end: `0x1800b75ce`
- name: `?SetNumberOfStreams@CVideoMixer@@UEAAJK@Z`
- size: `590`
- prototype: `__int64 __fastcall(CVideoMixer *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180038458`
- `0x180038498`
- `0x1800384a4`
- `0x180039250`
- `0x1800b2dfc`
- `0x1800b7380`
- `0x1800b8350`

## import_xrefs

- `KERNEL32!Sleep` at `0x1800b755a`
- `KERNEL32!Sleep` at `0x18015c818`
- `KERNEL32!Sleep` at `0x1800b755a`
- `KERNEL32!Sleep` at `0x18015c818`
- `KERNEL32!CreateThread` at `0x1800b74f6`
- `KERNEL32!CreateThread` at `0x1800b74f6`
- `KERNEL32!CreateEventW` at `0x1800b74bb`
- `KERNEL32!CreateEventW` at `0x1800b74bb`
- `KERNEL32!LeaveCriticalSection` at `0x1800b73c1`
- `KERNEL32!LeaveCriticalSection` at `0x1800b75bb`
- `KERNEL32!LeaveCriticalSection` at `0x1800b73c1`
- `KERNEL32!LeaveCriticalSection` at `0x1800b75bb`
- `KERNEL32!EnterCriticalSection` at `0x1800b73a7`
- `KERNEL32!EnterCriticalSection` at `0x1800b73a7`
- `KERNEL32!GetLastError` at `0x1800b750e`
- `KERNEL32!GetLastError` at `0x1800b750e`
- `USER32!PostThreadMessageW` at `0x1800b7548`
- `USER32!PostThreadMessageW` at `0x18015c806`
- `USER32!PostThreadMessageW` at `0x1800b7548`
- `USER32!PostThreadMessageW` at `0x18015c806`

## pseudocode

```c
__int64 __fastcall CVideoMixer::SetNumberOfStreams(CVideoMixer *this, unsigned int a2)
{
  unsigned __int64 v2; // r14
  struct _RTL_CRITICAL_SECTION *v4; // r12
  signed int v5; // ebx
  void *v7; // rax
  __int64 i; // rsi
  int v9; // r15d
  CVideoMixerStream *v10; // rax
  CVideoMixerStream *v11; // rdx
  HANDLE EventW; // rax
  HANDLE Thread; // rax
  signed int LastError; // eax
  unsigned int j; // esi
  unsigned int v16; // edx
  __int64 k; // rsi
  CVideoMixerStream *v18; // rcx
  int v19; // [rsp+80h] [rbp+18h] BYREF

  v2 = a2;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v5 = 0;
  if ( *((_DWORD *)this + 30) )
  {
    LeaveCriticalSection(v4);
    return 2147500037LL;
  }
  else
  {
    if ( (unsigned int)v2 <= 0x10 )
    {
      v7 = operator new[](saturated_mul(v2, 8u));
      *((_QWORD *)this + 16) = v7;
      if ( v7 )
      {
        memset_0(v7, 0, 8 * v2);
        for ( i = 0; (unsigned int)i < (unsigned int)v2; i = (unsigned int)(i + 1) )
        {
          v9 = 0;
          v19 = 0;
          v10 = (CVideoMixerStream *)operator new(0x188u);
          if ( v10 )
          {
            v11 = CVideoMixerStream::CVideoMixerStream(v10, i, &v19);
            v9 = v19;
          }
          else
          {
            v11 = 0;
          }
          *(_QWORD *)(*((_QWORD *)this + 16) + 8 * i) = v11;
          if ( !*(_QWORD *)(*((_QWORD *)this + 16) + 8 * i) )
            goto LABEL_6;
          if ( v9 < 0 )
          {
            v5 = v9;
            goto LABEL_20;
          }
        }
        *((_DWORD *)this + 30) = v2;
        EventW = CreateEventW(0, 1, 0, 0);
        *((_QWORD *)this + 17) = EventW;
        if ( !EventW
          || (Thread = CreateThread(0, 0, CVideoMixer::MixerThreadProc, (char *)this - 24, 0, (LPDWORD)this + 38),
              (*((_QWORD *)this + 18) = Thread) == 0) )
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      else
      {
LABEL_6:
        v5 = -2147024882;
      }
    }
    else
    {
      v5 = -2147024809;
    }
LABEL_20:
    if ( v5 < 0 )
    {
      for ( j = 0; j < 0x64; ++j )
      {
        if ( PostThreadMessageW(*((_DWORD *)this + 38), 0x400u, 0, 0) )
          break;
        Sleep(0);
      }
      if ( *((_QWORD *)this + 16) )
      {
        for ( k = 0; (unsigned int)k < (unsigned int)v2; k = (unsigned int)(k + 1) )
        {
          v18 = *(CVideoMixerStream **)(*((_QWORD *)this + 16) + 8 * k);
          if ( v18 )
            CVideoMixerStream::`scalar deleting destructor'(v18, v16);
        }
      }
      operator delete(*((void **)this + 16));
      *((_QWORD *)this + 16) = 0;
      *((_DWORD *)this + 30) = 0;
    }
    LeaveCriticalSection(v4);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x1800b7380  mov     [rsp+arg_18], rbx
0x1800b7385  mov     [rsp+arg_8], edx
0x1800b7389  mov     [rsp+arg_0], rcx
0x1800b738e  push    rsi
0x1800b738f  push    rdi
0x1800b7390  push    r12
0x1800b7392  push    r14
0x1800b7394  push    r15
0x1800b7396  sub     rsp, 40h
0x1800b739a  mov     r14d, edx
0x1800b739d  mov     rdi, rcx
0x1800b73a0  lea     r12, [rcx+18h]
0x1800b73a4  mov     rcx, r12; lpCriticalSection
0x1800b73a7  call    cs:__imp_EnterCriticalSection
0x1800b73ae  nop     dword ptr [rax+rax+00h]
0x1800b73b3  xor     ebx, ebx
0x1800b73b5  mov     [rsp+68h+var_38], ebx
0x1800b73b9  cmp     [rdi+78h], ebx
0x1800b73bc  jz      short loc_1800B73E8
0x1800b73be  mov     rcx, r12; lpCriticalSection
0x1800b73c1  call    cs:__imp_LeaveCriticalSection
0x1800b73c8  nop     dword ptr [rax+rax+00h]
0x1800b73cd  mov     eax, 80004005h
0x1800b73d2  mov     rbx, [rsp+68h+arg_18]
0x1800b73da  add     rsp, 40h
0x1800b73de  pop     r15
0x1800b73e0  pop     r14
0x1800b73e2  pop     r12
0x1800b73e4  pop     rdi
0x1800b73e5  pop     rsi
0x1800b73e6  retn
0x1800b73e8  cmp     r14d, 10h
0x1800b73ec  jbe     short loc_1800B73F8
0x1800b73ee  mov     ebx, 80070057h
0x1800b73f3  jmp     loc_1800B7529
0x1800b73f8  mov     eax, 8
0x1800b73fd  mul     r14
0x1800b7400  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b7407  cmovb   rax, rcx
0x1800b740b  mov     rcx, rax; unsigned __int64
0x1800b740e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b7413  mov     [rdi+80h], rax
0x1800b741a  test    rax, rax
0x1800b741d  jnz     short loc_1800B7429
0x1800b741f  mov     ebx, 8007000Eh
0x1800b7424  jmp     loc_1800B7529
0x1800b7429  lea     r8, ds:0[r14*8]; Size
0x1800b7431  xor     edx, edx; Val
0x1800b7433  mov     rcx, rax; void *
0x1800b7436  call    memset_0
0x1800b743b  xor     esi, esi
0x1800b743d  mov     [rsp+68h+var_34], esi
0x1800b7441  cmp     esi, r14d
0x1800b7444  jnb     short loc_1800B74AB
0x1800b7446  xor     r15d, r15d
0x1800b7449  mov     [rsp+68h+arg_10], r15d
0x1800b7451  mov     ecx, 188h; Size
0x1800b7456  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b745b  test    rax, rax
0x1800b745e  jz      short loc_1800B747F
0x1800b7460  lea     r8, [rsp+68h+arg_10]; int *
0x1800b7468  mov     edx, esi; unsigned int
0x1800b746a  mov     rcx, rax; this
0x1800b746d  call    ??0CVideoMixerStream@@QEAA@KPEAJ@Z; CVideoMixerStream::CVideoMixerStream(ulong,long *)
0x1800b7472  mov     rdx, rax
0x1800b7475  mov     r15d, [rsp+68h+arg_10]
0x1800b747d  jmp     short loc_1800B7481
0x1800b747f  xor     edx, edx
0x1800b7481  mov     rax, [rdi+80h]
0x1800b7488  mov     [rax+rsi*8], rdx
0x1800b748c  mov     rax, [rdi+80h]
0x1800b7493  cmp     qword ptr [rax+rsi*8], 0
0x1800b7498  jz      short loc_1800B741F
0x1800b749a  test    r15d, r15d
0x1800b749d  jns     short loc_1800B74A7
0x1800b749f  mov     ebx, r15d
0x1800b74a2  jmp     loc_1800B7529
0x1800b74a7  inc     esi
0x1800b74a9  jmp     short loc_1800B743D
0x1800b74ab  mov     [rdi+78h], r14d
0x1800b74af  xor     r9d, r9d; lpName
0x1800b74b2  xor     r8d, r8d; bInitialState
0x1800b74b5  lea     edx, [r9+1]; bManualReset
0x1800b74b9  xor     ecx, ecx; lpEventAttributes
0x1800b74bb  call    cs:__imp_CreateEventW
0x1800b74c2  nop     dword ptr [rax+rax+00h]
0x1800b74c7  mov     [rdi+88h], rax
0x1800b74ce  test    rax, rax
0x1800b74d1  jz      short loc_1800B750E
0x1800b74d3  lea     rax, [rdi+98h]
0x1800b74da  mov     [rsp+68h+lpThreadId], rax; lpThreadId
0x1800b74df  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x1800b74e7  lea     r9, [rdi-18h]; lpParameter
0x1800b74eb  lea     r8, ?MixerThreadProc@CVideoMixer@@SAKPEAX@Z; lpStartAddress
0x1800b74f2  xor     edx, edx; dwStackSize
0x1800b74f4  xor     ecx, ecx; lpThreadAttributes
0x1800b74f6  call    cs:__imp_CreateThread
0x1800b74fd  nop     dword ptr [rax+rax+00h]
0x1800b7502  mov     [rdi+90h], rax
0x1800b7509  test    rax, rax
0x1800b750c  jnz     short loc_1800B752D
0x1800b750e  call    cs:__imp_GetLastError
0x1800b7515  nop     dword ptr [rax+rax+00h]
0x1800b751a  test    eax, eax
0x1800b751c  mov     ebx, eax
0x1800b751e  jle     short loc_1800B7529
0x1800b7520  movzx   ebx, ax
0x1800b7523  or      ebx, 80070000h
0x1800b7529  mov     [rsp+68h+var_38], ebx
0x1800b752d  test    ebx, ebx
0x1800b752f  jns     loc_1800B75B8
0x1800b7535  xor     esi, esi
0x1800b7537  xor     r9d, r9d; lParam
0x1800b753a  xor     r8d, r8d; wParam
0x1800b753d  mov     edx, 400h; Msg
0x1800b7542  mov     ecx, [rdi+98h]; idThread
0x1800b7548  call    cs:__imp_PostThreadMessageW
0x1800b754f  nop     dword ptr [rax+rax+00h]
0x1800b7554  test    eax, eax
0x1800b7556  jnz     short loc_1800B756D
0x1800b7558  xor     ecx, ecx; dwMilliseconds
0x1800b755a  call    cs:__imp_Sleep
0x1800b7561  nop     dword ptr [rax+rax+00h]
0x1800b7566  inc     esi
0x1800b7568  cmp     esi, 64h ; 'd'
0x1800b756b  jb      short loc_1800B7537
0x1800b756d  cmp     qword ptr [rdi+80h], 0
0x1800b7575  jz      short loc_1800B759A
0x1800b7577  xor     esi, esi
0x1800b7579  test    r14d, r14d
0x1800b757c  jz      short loc_1800B759A
0x1800b757e  mov     rax, [rdi+80h]
0x1800b7585  mov     rcx, [rax+rsi*8]; this
0x1800b7589  test    rcx, rcx
0x1800b758c  jz      short loc_1800B7593
0x1800b758e  call    ??_GCVideoMixerStream@@QEAAPEAXI@Z; CVideoMixerStream::`scalar deleting destructor'(uint)
0x1800b7593  inc     esi
0x1800b7595  cmp     esi, r14d
0x1800b7598  jb      short loc_1800B757E
0x1800b759a  mov     rcx, [rdi+80h]; Block
0x1800b75a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800b75a6  mov     qword ptr [rdi+80h], 0
0x1800b75b1  mov     dword ptr [rdi+78h], 0
0x1800b75b8  mov     rcx, r12; lpCriticalSection
0x1800b75bb  call    cs:__imp_LeaveCriticalSection
0x1800b75c2  nop     dword ptr [rax+rax+00h]
0x1800b75c7  mov     eax, ebx
0x1800b75c9  jmp     loc_1800B73D2
0x18015c7d6  push    rbx
0x18015c7d8  push    rbp
0x18015c7d9  push    rsi
0x18015c7da  push    rdi
0x18015c7db  sub     rsp, 38h
0x18015c7df  mov     rbp, rdx
0x18015c7e2  cmp     dword ptr [rbp+30h], 0
0x18015c7e6  jge     loc_18015C881
0x18015c7ec  xor     ebx, ebx
0x18015c7ee  mov     [rbp+34h], ebx
0x18015c7f1  mov     rdi, [rbp+70h]
0x18015c7f5  xor     r9d, r9d; lParam
0x18015c7f8  xor     r8d, r8d; wParam
0x18015c7fb  mov     edx, 400h; Msg
0x18015c800  mov     ecx, [rdi+98h]; idThread
0x18015c806  call    cs:__imp_PostThreadMessageW
0x18015c80d  nop     dword ptr [rax+rax+00h]
0x18015c812  test    eax, eax
0x18015c814  jnz     short loc_18015C82B
0x18015c816  xor     ecx, ecx; dwMilliseconds
0x18015c818  call    cs:__imp_Sleep
0x18015c81f  nop     dword ptr [rax+rax+00h]
0x18015c824  inc     ebx
0x18015c826  cmp     ebx, 64h ; 'd'
0x18015c829  jb      short loc_18015C7F5
0x18015c82b  mov     [rbp+34h], ebx
0x18015c82e  cmp     qword ptr [rdi+80h], 0
0x18015c836  jz      short loc_18015C863
0x18015c838  xor     ebx, ebx
0x18015c83a  mov     [rbp+34h], ebx
0x18015c83d  mov     esi, [rbp+78h]
0x18015c840  test    esi, esi
0x18015c842  jz      short loc_18015C863
0x18015c844  mov     rax, [rdi+80h]
0x18015c84b  mov     rcx, [rax+rbx*8]; this
0x18015c84f  test    rcx, rcx
0x18015c852  jz      short loc_18015C85A
0x18015c854  call    ??_GCVideoMixerStream@@QEAAPEAXI@Z; CVideoMixerStream::`scalar deleting destructor'(uint)
0x18015c859  nop
0x18015c85a  inc     ebx
0x18015c85c  cmp     ebx, esi
0x18015c85e  jb      short loc_18015C844
0x18015c860  mov     [rbp+34h], ebx
0x18015c863  mov     rcx, [rdi+80h]; Block
0x18015c86a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18015c86f  mov     qword ptr [rdi+80h], 0
0x18015c87a  mov     dword ptr [rdi+78h], 0
0x18015c881  add     rsp, 38h
0x18015c885  pop     rdi
0x18015c886  pop     rsi
0x18015c887  pop     rbp
0x18015c888  pop     rbx
0x18015c889  retn
```
