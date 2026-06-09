# CIVIAudioCodec::DecodeAACFrame(uchar *,long,ulong,ushort *)

- ea: `0x18001a6b0`
- end: `0x18001ab78`
- name: `?DecodeAACFrame@CIVIAudioCodec@@IEAAJPEAEJKPEAG@Z`
- size: `1224`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, unsigned __int8 *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000dcc0`
- `0x180019d60`

## callees

- `0x1800017b0`
- `0x1800196c0`
- `0x18001a6b0`
- `0x180033bf0`
- `0x180033d00`
- `0x180034030`
- `0x180034760`
- `0x1800743e0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a847`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a8de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a969`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a847`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a8de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a969`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a811`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a8a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a933`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a811`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a8a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a933`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18001aa93`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18001aa93`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001a837`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001a8ce`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001a959`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001a837`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001a8ce`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001a959`

## pseudocode

```c
__int64 __fastcall CIVIAudioCodec::DecodeAACFrame(struct _RTL_CRITICAL_SECTION *this, unsigned __int8 *a2, int a3)
{
  LONG *p_LockCount; // rsi
  int v5; // r15d
  int DebugInfo_high; // eax
  _DWORD *p_OwningThread; // rcx
  int v9; // ebx
  HANDLE LockSemaphore; // rdx
  int v11; // r15d
  __int64 v12; // rax
  int v13; // r14d
  HANDLE *p_LockSemaphore; // rbx
  LONG v16; // edx
  int v17; // eax
  int v18; // r9d
  __int64 v19; // rax
  __int64 v20; // rcx
  int v21; // ecx
  LONG v22; // ecx
  int LockSemaphore_high; // ebx
  BOOL v24; // ecx
  int v25; // r8d
  __int64 OwningThread_high; // rdx
  int v27; // [rsp+60h] [rbp-11h] BYREF
  unsigned int v28; // [rsp+64h] [rbp-Dh] BYREF
  int v29; // [rsp+68h] [rbp-9h] BYREF
  __int64 v30; // [rsp+70h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp+7h] BYREF

  p_LockCount = &this[160].LockCount;
  v29 = 1;
  v5 = (int)a2;
  v30 = 0;
  v28 = 0;
  if ( !*(_QWORD *)&this[160].LockCount )
  {
    DebugInfo_high = HIDWORD(this[171].DebugInfo);
    p_OwningThread = &this[159].OwningThread;
    HIDWORD(this[159].OwningThread) = 0;
    this[159].SpinCount = 0;
    this[160].DebugInfo = 0;
    *p_OwningThread = DebugInfo_high;
    LODWORD(this[159].LockSemaphore) = 1;
    v9 = AACAudioDecoderCreate(p_OwningThread, p_LockCount);
    if ( v9 )
    {
      if ( *(_QWORD *)p_LockCount )
        AACAudioDecoderClose(p_LockCount);
      return (unsigned int)v9;
    }
    this[171].LockCount = 1;
  }
  LockSemaphore = this[160].LockSemaphore;
  if ( (LockSemaphore || this[160].SpinCount)
    && (unsigned int)CAacDecoderSetTransportStreamChannelConfig(
                       *(_QWORD *)(*(_QWORD *)p_LockCount + 8LL),
                       LockSemaphore,
                       this[160].SpinCount) )
  {
    return (unsigned int)-2147467259;
  }
  v11 = AACAudioDecoderDecode(*(_QWORD *)p_LockCount, v5, a3, (unsigned int)&v28, (__int64)&v29);
  v12 = *(_QWORD *)p_LockCount;
  if ( !*(_QWORD *)p_LockCount )
  {
    v13 = 0;
    goto LABEL_17;
  }
  v13 = *(_DWORD *)(v12 + 604);
  if ( !*(_DWORD *)(v12 + 600) )
  {
LABEL_17:
    p_LockSemaphore = &this->LockSemaphore;
    goto LABEL_18;
  }
  p_LockSemaphore = &this->LockSemaphore;
  v27 = v11;
  *(_QWORD *)&UserData.Size = 4;
  UserData.Ptr = (ULONGLONG)&v27;
  if ( this != (struct _RTL_CRITICAL_SECTION *)-24LL )
  {
    EnterCriticalSection(this + 1);
    if ( !*(_DWORD *)p_LockSemaphore )
      EventWrite(this->SpinCount, &MSMPEG2ADEC_AUDDECODE_FRAME_ERROR, 1u, &UserData);
    LeaveCriticalSection(this + 1);
  }
  ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, __int64, _QWORD))this->DebugInfo[1].ProcessLocksList.Blink)(
    this,
    7,
    -2147024809,
    0);
LABEL_18:
  if ( v13 )
  {
    p_LockSemaphore = &this->LockSemaphore;
    v27 = v11;
    *(_QWORD *)&UserData.Size = 4;
    UserData.Ptr = (ULONGLONG)&v27;
    if ( this != (struct _RTL_CRITICAL_SECTION *)-24LL )
    {
      EnterCriticalSection(this + 1);
      if ( !*(_DWORD *)p_LockSemaphore )
        EventWrite(this->SpinCount, &MSMPEG2ADEC_AUDDECODE_FRAME_ERROR, 1u, &UserData);
      LeaveCriticalSection(this + 1);
    }
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, __int64, _QWORD))this->DebugInfo[1].ProcessLocksList.Blink)(
      this,
      7,
      -2147024809,
      0);
  }
  if ( v11 != 1502 )
  {
    v27 = v11;
    UserData.Ptr = (ULONGLONG)&v27;
    *(_QWORD *)&UserData.Size = 4;
    if ( p_LockSemaphore )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(p_LockSemaphore + 2));
      if ( !*(_DWORD *)p_LockSemaphore )
        EventWrite((REGHANDLE)p_LockSemaphore[1], &MSMPEG2ADEC_AUDDECODE_FRAME_ERROR, 1u, &UserData);
      LeaveCriticalSection((LPCRITICAL_SECTION)(p_LockSemaphore + 2));
    }
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, __int64, _QWORD))this->DebugInfo[1].ProcessLocksList.Blink)(
      this,
      7,
      -2147024809,
      0);
    return (unsigned int)-2147467259;
  }
  v16 = v29;
  v17 = 1024;
  v18 = 2048;
  if ( v29 )
    v17 = 2048;
  if ( v17 != v28 )
    return (unsigned int)-2147467259;
  v19 = *(_QWORD *)p_LockCount;
  if ( !*(_DWORD *)(*(_QWORD *)p_LockCount + 440LL) )
    return (unsigned int)-2147467259;
  v20 = *(_QWORD *)(v19 + 8);
  if ( v20 )
  {
    v21 = *(_DWORD *)(v20 + 604);
    if ( v21 )
    {
      if ( v21 != LODWORD(this[161].DebugInfo) )
      {
        LODWORD(this[161].DebugInfo) = v21;
        this->LockCount = 1;
      }
    }
  }
  this[161].RecursionCount = v16;
  v22 = *(_DWORD *)(v19 + 596) == 29;
  if ( this[161].LockCount != v22 )
  {
    this[161].LockCount = v22;
    this->LockCount = 1;
  }
  LockSemaphore_high = HIDWORD(this[155].LockSemaphore);
  v24 = LODWORD(this[161].DebugInfo) == 6;
  this[156].RecursionCount = v24;
  this[156].LockCount = *(_DWORD *)(v19 + 440) - v24;
  v25 = LODWORD(this[159].OwningThread) * ((v16 != 0) + 1);
  if ( !v16 )
    v18 = 1024;
  LODWORD(this[147].LockSemaphore) = v18;
  HIDWORD(this[155].LockSemaphore) = v25;
  this[2].SpinCount = MulDiv(v18, 10000000, v25);
  if ( LockSemaphore_high != HIDWORD(this[155].LockSemaphore) )
    this->LockCount = 1;
  v9 = CIVIAudioCodec::CheckModeChange((CIVIAudioCodec *)this);
  if ( v9 >= 0 )
  {
    if ( this[171].LockCount )
    {
      v9 = 0;
      this[8].LockSemaphore = (char *)this[8].LockSemaphore + this[2].SpinCount;
      this[171].LockCount = 0;
      return (unsigned int)v9;
    }
    v9 = (*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *, _QWORD, __int64 *))&this->DebugInfo->EntryCount)(
           this,
           HIDWORD(this[147].OwningThread),
           &v30);
    if ( v9 < 0 )
      return (unsigned int)v9;
    AACAudioDecoderGetOutput(
      *(_QWORD *)&this[160].LockCount,
      v30,
      HIDWORD(this[147].OwningThread),
      this[160].OwningThread,
      LODWORD(this[148].DebugInfo) != 32,
      (__int64)&v28);
    OwningThread_high = SHIDWORD(this[147].OwningThread);
    if ( OwningThread_high == 4LL * v28 )
      return ((unsigned int (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64, ULONG_PTR))this->DebugInfo[1].ProcessLocksList.Flink)(
               this,
               OwningThread_high,
               this[2].SpinCount);
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001a6b0  mov     [rsp-8+arg_18], rbx
0x18001a6b5  push    rbp
0x18001a6b6  push    rsi
0x18001a6b7  push    rdi
0x18001a6b8  push    r12
0x18001a6ba  push    r13
0x18001a6bc  push    r14
0x18001a6be  push    r15
0x18001a6c0  lea     rbp, [rsp-1Fh]
0x18001a6c5  sub     rsp, 90h
0x18001a6cc  mov     rax, cs:__security_cookie
0x18001a6d3  xor     rax, rsp
0x18001a6d6  mov     [rbp+4Fh+var_38], rax
0x18001a6da  mov     r13, [rbp+4Fh+arg_20]
0x18001a6de  lea     rsi, [rcx+1908h]
0x18001a6e5  xor     ebx, ebx
0x18001a6e7  mov     [rbp+4Fh+var_58], 1
0x18001a6ee  mov     r14d, r9d
0x18001a6f1  mov     r12d, r8d
0x18001a6f4  mov     r15, rdx
0x18001a6f7  mov     rdi, rcx
0x18001a6fa  mov     [rbp+4Fh+var_50], rbx
0x18001a6fe  mov     [rbp+4Fh+var_5C], ebx
0x18001a701  cmp     [rsi], rbx
0x18001a704  jnz     short loc_18001A764
0x18001a706  mov     eax, [rdi+1ABCh]
0x18001a70c  add     rcx, 18E8h
0x18001a713  mov     rdx, rsi
0x18001a716  mov     [rdi+18ECh], ebx
0x18001a71c  mov     [rdi+18F8h], rbx
0x18001a723  mov     [rdi+1900h], rbx
0x18001a72a  mov     [rcx], eax
0x18001a72c  mov     dword ptr [rdi+18F0h], 1
0x18001a736  call    AACAudioDecoderCreate
0x18001a73b  mov     ebx, eax
0x18001a73d  test    eax, eax
0x18001a73f  jz      short loc_18001A758
0x18001a741  cmp     qword ptr [rsi], 0
0x18001a745  jz      loc_18001A999
0x18001a74b  mov     rcx, rsi
0x18001a74e  call    AACAudioDecoderClose
0x18001a753  jmp     loc_18001A999
0x18001a758  mov     dword ptr [rdi+1AC0h], 1
0x18001a762  xor     ebx, ebx
0x18001a764  mov     rdx, [rdi+1918h]
0x18001a76b  test    rdx, rdx
0x18001a76e  jnz     short loc_18001A779
0x18001a770  cmp     [rdi+1920h], rdx
0x18001a777  jz      short loc_18001A794
0x18001a779  mov     rcx, [rsi]
0x18001a77c  mov     r8, [rdi+1920h]
0x18001a783  mov     rcx, [rcx+8]
0x18001a787  call    CAacDecoderSetTransportStreamChannelConfig
0x18001a78c  test    eax, eax
0x18001a78e  jnz     loc_18001A994
0x18001a794  mov     eax, [rdi+1898h]
0x18001a79a  lea     r9, [rbp+4Fh+var_5C]
0x18001a79e  mov     rcx, [rsi]
0x18001a7a1  mov     r8d, r12d
0x18001a7a4  mov     [rsp+0C0h+var_70], eax
0x18001a7a8  mov     rdx, r15
0x18001a7ab  mov     eax, [rdi+188Ch]
0x18001a7b1  mov     [rsp+0C0h+var_80], eax
0x18001a7b5  lea     rax, [rbp+4Fh+var_58]
0x18001a7b9  mov     [rsp+0C0h+var_88], r13
0x18001a7be  mov     [rsp+0C0h+var_90], r14d
0x18001a7c3  mov     [rsp+0C0h+var_A0], rax
0x18001a7c8  call    AACAudioDecoderDecode
0x18001a7cd  mov     r15d, eax
0x18001a7d0  mov     rax, [rsi]
0x18001a7d3  test    rax, rax
0x18001a7d6  jz      loc_18001A874
0x18001a7dc  mov     r14d, [rax+25Ch]
0x18001a7e3  cmp     dword ptr [rax+258h], 0
0x18001a7ea  jz      loc_18001A877
0x18001a7f0  lea     rbx, [rdi+18h]
0x18001a7f4  mov     [rbp+4Fh+var_60], r15d
0x18001a7f8  mov     qword ptr [rbp+4Fh+UserData.Size], 4
0x18001a800  lea     rax, [rbp+4Fh+var_60]
0x18001a804  mov     [rbp+4Fh+UserData.Ptr], rax
0x18001a808  test    rbx, rbx
0x18001a80b  jz      short loc_18001A853
0x18001a80d  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001a811  call    cs:__imp_EnterCriticalSection
0x18001a818  nop     dword ptr [rax+rax+00h]
0x18001a81d  cmp     dword ptr [rbx], 0
0x18001a820  jnz     short loc_18001A843
0x18001a822  mov     rcx, [rbx+8]; RegHandle
0x18001a826  lea     r9, [rbp+4Fh+UserData]; UserData
0x18001a82a  mov     r8d, 1; UserDataCount
0x18001a830  lea     rdx, MSMPEG2ADEC_AUDDECODE_FRAME_ERROR; EventDescriptor
0x18001a837  call    cs:__imp_EventWrite
0x18001a83e  nop     dword ptr [rax+rax+00h]
0x18001a843  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001a847  call    cs:__imp_LeaveCriticalSection
0x18001a84e  nop     dword ptr [rax+rax+00h]
0x18001a853  mov     rax, [rdi]
0x18001a856  xor     r9d, r9d
0x18001a859  mov     edx, 7
0x18001a85e  mov     r8, 0FFFFFFFF80070057h
0x18001a865  mov     rcx, rdi
0x18001a868  mov     rax, [rax+48h]
0x18001a86c  call    cs:__guard_dispatch_icall_fptr
0x18001a872  jmp     short loc_18001A87B
0x18001a874  mov     r14d, ebx
0x18001a877  lea     rbx, [rdi+18h]
0x18001a87b  xor     r12d, r12d
0x18001a87e  test    r14d, r14d
0x18001a881  jz      loc_18001A909
0x18001a887  lea     rbx, [rdi+18h]
0x18001a88b  mov     [rbp+4Fh+var_60], r15d
0x18001a88f  mov     qword ptr [rbp+4Fh+UserData.Size], 4
0x18001a897  lea     rax, [rbp+4Fh+var_60]
0x18001a89b  mov     [rbp+4Fh+UserData.Ptr], rax
0x18001a89f  test    rbx, rbx
0x18001a8a2  jz      short loc_18001A8EA
0x18001a8a4  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001a8a8  call    cs:__imp_EnterCriticalSection
0x18001a8af  nop     dword ptr [rax+rax+00h]
0x18001a8b4  cmp     [rbx], r12d
0x18001a8b7  jnz     short loc_18001A8DA
0x18001a8b9  mov     rcx, [rbx+8]; RegHandle
0x18001a8bd  lea     r9, [rbp+4Fh+UserData]; UserData
0x18001a8c1  mov     r8d, 1; UserDataCount
0x18001a8c7  lea     rdx, MSMPEG2ADEC_AUDDECODE_FRAME_ERROR; EventDescriptor
0x18001a8ce  call    cs:__imp_EventWrite
0x18001a8d5  nop     dword ptr [rax+rax+00h]
0x18001a8da  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001a8de  call    cs:__imp_LeaveCriticalSection
0x18001a8e5  nop     dword ptr [rax+rax+00h]
0x18001a8ea  mov     rax, [rdi]
0x18001a8ed  xor     r9d, r9d
0x18001a8f0  mov     edx, 7
0x18001a8f5  mov     r8, 0FFFFFFFF80070057h
0x18001a8fc  mov     rcx, rdi
0x18001a8ff  mov     rax, [rax+48h]
0x18001a903  call    cs:__guard_dispatch_icall_fptr
0x18001a909  cmp     r15d, 5DEh
0x18001a910  jz      loc_18001A9C3
0x18001a916  mov     [rbp+4Fh+var_60], r15d
0x18001a91a  lea     rax, [rbp+4Fh+var_60]
0x18001a91e  mov     [rbp+4Fh+UserData.Ptr], rax
0x18001a922  mov     qword ptr [rbp+4Fh+UserData.Size], 4
0x18001a92a  test    rbx, rbx
0x18001a92d  jz      short loc_18001A975
0x18001a92f  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001a933  call    cs:__imp_EnterCriticalSection
0x18001a93a  nop     dword ptr [rax+rax+00h]
0x18001a93f  cmp     dword ptr [rbx], 0
0x18001a942  jnz     short loc_18001A965
0x18001a944  mov     rcx, [rbx+8]; RegHandle
0x18001a948  lea     r9, [rbp+4Fh+UserData]; UserData
0x18001a94c  mov     r8d, 1; UserDataCount
0x18001a952  lea     rdx, MSMPEG2ADEC_AUDDECODE_FRAME_ERROR; EventDescriptor
0x18001a959  call    cs:__imp_EventWrite
0x18001a960  nop     dword ptr [rax+rax+00h]
0x18001a965  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001a969  call    cs:__imp_LeaveCriticalSection
0x18001a970  nop     dword ptr [rax+rax+00h]
0x18001a975  mov     rax, [rdi]
0x18001a978  xor     r9d, r9d
0x18001a97b  mov     edx, 7
0x18001a980  mov     r8, 0FFFFFFFF80070057h
0x18001a987  mov     rcx, rdi
0x18001a98a  mov     rax, [rax+48h]
0x18001a98e  call    cs:__guard_dispatch_icall_fptr
0x18001a994  mov     ebx, 80004005h
0x18001a999  mov     eax, ebx
0x18001a99b  mov     rcx, [rbp+4Fh+var_38]
0x18001a99f  xor     rcx, rsp; StackCookie
0x18001a9a2  call    __security_check_cookie
0x18001a9a7  mov     rbx, [rsp+0C0h+arg_18]
0x18001a9af  add     rsp, 90h
0x18001a9b6  pop     r15
0x18001a9b8  pop     r14
0x18001a9ba  pop     r13
0x18001a9bc  pop     r12
0x18001a9be  pop     rdi
0x18001a9bf  pop     rsi
0x18001a9c0  pop     rbp
0x18001a9c1  retn
0x18001a9c3  mov     edx, [rbp+4Fh+var_58]
0x18001a9c6  mov     r10d, 400h
0x18001a9cc  test    edx, edx
0x18001a9ce  mov     eax, r10d
0x18001a9d1  mov     r9d, 800h
0x18001a9d7  cmovnz  eax, r9d
0x18001a9db  cmp     eax, [rbp+4Fh+var_5C]
0x18001a9de  jnz     short loc_18001A994
0x18001a9e0  mov     rax, [rsi]
0x18001a9e3  cmp     dword ptr [rax+1B8h], 0
0x18001a9ea  jz      short loc_18001A994
0x18001a9ec  mov     rcx, [rax+8]
0x18001a9f0  test    rcx, rcx
0x18001a9f3  jz      short loc_18001AA14
0x18001a9f5  mov     ecx, [rcx+25Ch]
0x18001a9fb  test    ecx, ecx
0x18001a9fd  jz      short loc_18001AA14
0x18001a9ff  cmp     ecx, [rdi+1928h]
0x18001aa05  jz      short loc_18001AA14
0x18001aa07  mov     [rdi+1928h], ecx
0x18001aa0d  mov     dword ptr [rdi+8], 1
0x18001aa14  mov     ecx, r12d
0x18001aa17  mov     [rdi+1934h], edx
0x18001aa1d  cmp     dword ptr [rax+254h], 1Dh
0x18001aa24  setz    cl
0x18001aa27  cmp     [rdi+1930h], ecx
0x18001aa2d  jz      short loc_18001AA3C
0x18001aa2f  mov     [rdi+1930h], ecx
0x18001aa35  mov     dword ptr [rdi+8], 1
0x18001aa3c  cmp     dword ptr [rdi+1928h], 6
0x18001aa43  mov     ecx, r12d
0x18001aa46  mov     ebx, [rdi+1854h]
0x18001aa4c  mov     r8d, r12d
0x18001aa4f  setz    cl
0x18001aa52  mov     [rdi+186Ch], ecx
0x18001aa58  mov     eax, [rax+1B8h]
0x18001aa5e  sub     eax, ecx
0x18001aa60  test    edx, edx
0x18001aa62  mov     [rdi+1868h], eax
0x18001aa68  setnz   r8b
0x18001aa6c  inc     r8d
0x18001aa6f  imul    r8d, [rdi+18E8h]; nDenominator
0x18001aa77  test    edx, edx
0x18001aa79  mov     edx, 989680h; nNumerator
0x18001aa7e  cmovz   r9d, r10d
0x18001aa82  mov     ecx, r9d; nNumber
0x18001aa85  mov     [rdi+1710h], r9d
0x18001aa8c  mov     [rdi+1854h], r8d
0x18001aa93  call    cs:__imp_MulDiv
0x18001aa9a  nop     dword ptr [rax+rax+00h]
0x18001aa9f  movsxd  rcx, eax
0x18001aaa2  mov     [rdi+70h], rcx
0x18001aaa6  cmp     ebx, [rdi+1854h]
0x18001aaac  jz      short loc_18001AAB5
0x18001aaae  mov     dword ptr [rdi+8], 1
0x18001aab5  mov     rcx, rdi; this
0x18001aab8  call    ?CheckModeChange@CIVIAudioCodec@@IEAAJXZ; CIVIAudioCodec::CheckModeChange(void)
0x18001aabd  mov     ebx, eax
0x18001aabf  test    eax, eax
0x18001aac1  js      loc_18001A999
0x18001aac7  cmp     dword ptr [rdi+1AC0h], 0
0x18001aace  jz      short loc_18001AAEA
0x18001aad0  mov     rax, [rdi+70h]
0x18001aad4  mov     ebx, r12d
0x18001aad7  add     [rdi+158h], rax
0x18001aade  mov     [rdi+1AC0h], r12d
0x18001aae5  jmp     loc_18001A999
0x18001aaea  mov     rax, [rdi]
0x18001aaed  lea     r8, [rbp+4Fh+var_50]
0x18001aaf1  mov     edx, [rdi+170Ch]
0x18001aaf7  mov     rcx, rdi
0x18001aafa  mov     rax, [rax+20h]
0x18001aafe  call    cs:__guard_dispatch_icall_fptr
0x18001ab04  mov     ebx, eax
0x18001ab06  test    eax, eax
0x18001ab08  js      loc_18001A999
0x18001ab0e  cmp     dword ptr [rdi+1720h], 20h ; ' '
0x18001ab15  lea     rcx, [rbp+4Fh+var_5C]
0x18001ab19  mov     r9d, [rdi+1910h]
0x18001ab20  mov     eax, r12d
0x18001ab23  mov     r8d, [rdi+170Ch]
0x18001ab2a  setnz   al
0x18001ab2d  mov     rdx, [rbp+4Fh+var_50]
0x18001ab31  mov     [rsp+0C0h+var_98], rcx
0x18001ab36  mov     rcx, [rdi+1908h]
0x18001ab3d  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18001ab41  call    AACAudioDecoderGetOutput
0x18001ab46  mov     ecx, [rbp+4Fh+var_5C]
0x18001ab49  movsxd  rdx, dword ptr [rdi+170Ch]
0x18001ab50  shl     rcx, 2
0x18001ab54  cmp     rdx, rcx
0x18001ab57  jnz     loc_18001A994
0x18001ab5d  mov     rax, [rdi]
0x18001ab60  mov     rcx, rdi
0x18001ab63  mov     r8, [rdi+70h]
0x18001ab67  mov     rax, [rax+40h]
0x18001ab6b  call    cs:__guard_dispatch_icall_fptr
0x18001ab71  mov     ebx, eax
0x18001ab73  jmp     loc_18001A999
```
