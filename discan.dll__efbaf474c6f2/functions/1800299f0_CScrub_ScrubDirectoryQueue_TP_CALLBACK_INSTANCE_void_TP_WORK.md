# CScrub::_ScrubDirectoryQueue(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800299f0`
- end: `0x18002a2d5`
- name: `?_ScrubDirectoryQueue@CScrub@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `2277`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WORK Work)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024b24`

## callees

- `0x1800032f8`
- `0x180006688`
- `0x180012048`
- `0x180012158`
- `0x1800137d4`
- `0x180021aac`
- `0x18002226c`
- `0x180027798`
- `0x180027858`
- `0x1800293d4`
- `0x1800299f0`
- `0x18002bb08`
- `0x18002c6f8`
- `0x180037620`

## import_xrefs

- `ntdll!NtWaitForMultipleObjects` at `0x180029cb6`
- `ntdll!NtWaitForMultipleObjects` at `0x180029de0`
- `ntdll!NtWaitForMultipleObjects` at `0x180029cb6`
- `ntdll!NtWaitForMultipleObjects` at `0x180029de0`
- `ntdll!NtClearEvent` at `0x180029c0a`
- `ntdll!NtClearEvent` at `0x180029c0a`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029c90`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029dba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002a094`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002a188`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002a230`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029c90`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180029dba`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002a094`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002a188`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18002a230`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180029bbc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180029cc5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002a155`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002a1fd`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180029bbc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180029cc5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002a155`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002a1fd`
- `KERNEL32!QueryPerformanceCounter` at `0x180029ac7`
- `KERNEL32!QueryPerformanceCounter` at `0x180029bdf`
- `KERNEL32!QueryPerformanceCounter` at `0x180029d69`
- `KERNEL32!QueryPerformanceCounter` at `0x18002a0e6`
- `KERNEL32!QueryPerformanceCounter` at `0x18002a1e4`
- `KERNEL32!QueryPerformanceCounter` at `0x180029ac7`
- `KERNEL32!QueryPerformanceCounter` at `0x180029bdf`
- `KERNEL32!QueryPerformanceCounter` at `0x180029d69`
- `KERNEL32!QueryPerformanceCounter` at `0x18002a0e6`
- `KERNEL32!QueryPerformanceCounter` at `0x18002a1e4`

## string_xrefs

- `0x180029a36`: `CScrub::_ScrubDirectoryQueue`

## pseudocode

```c
void __fastcall CScrub::_ScrubDirectoryQueue(PTP_CALLBACK_INSTANCE Instance, char *Context, PTP_WORK Work)
{
  __int64 v4; // rsi
  __int64 v5; // rdx
  USHORT v6; // dx
  USHORT Length; // cx
  USHORT v8; // ax
  const struct _UNICODE_STRING *v9; // r9
  BOOL v10; // r15d
  char v11; // r13
  signed __int32 v12; // ecx
  signed __int32 v13; // eax
  const struct _UNICODE_STRING *v14; // r8
  struct CFileName ***v15; // r12
  RTL_SRWLOCK *v16; // rbx
  NTSTATUS v17; // r15d
  PVOID *v18; // r11
  BOOL v19; // r13d
  struct CFileName **v20; // r15
  struct CFileName *v21; // rax
  __int64 FullPathName; // r10
  const UNICODE_STRING *v23; // rax
  int v24; // eax
  char v25; // bl
  const struct _UNICODE_STRING *v26; // rax
  _QWORD *v27; // rax
  __int64 v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // rcx
  _QWORD *v31; // rcx
  unsigned __int64 v32; // r8
  int v33; // edx
  _QWORD *v34; // rax
  __int64 v35; // rcx
  BOOL v36; // [rsp+40h] [rbp-59h]
  LARGE_INTEGER v37; // [rsp+48h] [rbp-51h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-49h] BYREF
  union _LARGE_INTEGER Time; // [rsp+58h] [rbp-41h] BYREF
  RTL_SRWLOCK *v40; // [rsp+60h] [rbp-39h] BYREF
  __int64 v41; // [rsp+68h] [rbp-31h]
  struct CFileName **v42; // [rsp+70h] [rbp-29h]
  char *v43; // [rsp+78h] [rbp-21h]
  const char *v44; // [rsp+80h] [rbp-19h] BYREF
  int v45; // [rsp+88h] [rbp-11h]
  HANDLE Object[3]; // [rsp+90h] [rbp-9h] BYREF

  v4 = *((_QWORD *)Context + 8);
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v5 + 16) = "CScrub::_ScrubDirectoryQueue";
  v44 = "CScrub::_ScrubDirectoryQueue";
  v45 = 0;
  v6 = ++*(_WORD *)(v5 + 8);
  Length = GlobalIndentString.Length;
  v8 = GlobalIndentString.Length;
  if ( v6 < GlobalIndentString.Length )
    v8 = v6;
  LOWORD(v42) = v8;
  if ( v6 < GlobalIndentString.Length )
    Length = v6;
  WORD1(v42) = Length;
  HIDWORD(v42) = 0;
  v43 = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrub::_ScrubDirectoryQueue");
  }
  PerformanceCount.QuadPart = 0;
  v37.QuadPart = 0;
  v10 = QueryPerformanceCounter(&PerformanceCount);
  v36 = v10;
  v11 = 1;
  ++*((_DWORD *)Context + 10);
  v12 = _InterlockedIncrement((volatile signed __int32 *)(v4 + 1336));
  do
    v13 = *(_DWORD *)(v4 + 1340);
  while ( v12 > v13 && v13 != _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 1340), v12, v13) );
  Object[0] = *(HANDLE *)(v4 + 16);
  Object[1] = *(HANDLE *)(v4 + 1216);
  Object[2] = *(HANDLE *)(v4 + 1168);
  if ( !Context[24] )
  {
    v14 = *(const struct _UNICODE_STRING **)(*(_QWORD *)v4 + 64LL);
    *((_WORD *)Context + 44) = 0;
    CScrubPath::PushNameEx((struct _UNICODE_STRING *)(Context + 88), &EmptyUnicodeString, v14, v9);
    Context[24] = 1;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DDZd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      78,
      (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
      *(_DWORD *)(**(_QWORD **)v4 + 16LL),
      *(_DWORD *)(**(_QWORD **)v4 + 36LL),
      *(_QWORD *)(*(_QWORD *)v4 + 64LL),
      (unsigned __int64)&Context[-*(_QWORD *)(v4 + 1416)] / 0x88D0);
  }
  v15 = (struct CFileName ***)(v4 + 1432);
  while ( 1 )
  {
    v16 = (RTL_SRWLOCK *)(v4 + 1448);
    AcquireSRWLockExclusive((PSRWLOCK)(v4 + 1448));
    if ( *v15 != (struct CFileName **)v15 )
    {
      v19 = v36;
      goto LABEL_38;
    }
    if ( v11 )
      ++*((_DWORD *)Context + 9);
    if ( v10 && QueryPerformanceCounter(&v37) )
      *((_QWORD *)Context + 7) += v37.QuadPart - PerformanceCount.QuadPart;
    if ( *(_DWORD *)(*(_QWORD *)(v4 + 8) + 8LL) != 1 )
      goto LABEL_68;
    NtClearEvent(*(HANDLE *)(v4 + 1168));
    ++*(_DWORD *)(v4 + 1344);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        79,
        (unsigned __int64)&Context[-*(_QWORD *)(v4 + 1416)] / 0x88D0,
        *(_DWORD *)(**(_QWORD **)v4 + 16LL),
        *(_DWORD *)(**(_QWORD **)v4 + 36LL),
        *(_QWORD *)(*(_QWORD *)v4 + 64LL),
        (unsigned __int64)&Context[-*(_QWORD *)(v4 + 1416)] / 0x88D0,
        *(_DWORD *)(v4 + 1344));
    }
    ReleaseSRWLockExclusive((PSRWLOCK)(v4 + 1448));
    Time.QuadPart = -50000000;
    v17 = NtWaitForMultipleObjects(3u, Object, WaitAny, 0, &Time);
    v16 = (RTL_SRWLOCK *)(v4 + 1448);
    AcquireSRWLockExclusive((PSRWLOCK)(v4 + 1448));
    --*(_DWORD *)(v4 + 1344);
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZdd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        (unsigned __int64)&Context[-*(_QWORD *)(v4 + 1416)] / 0x88D0,
        *(_DWORD *)(**(_QWORD **)v4 + 16LL),
        *(_DWORD *)(**(_QWORD **)v4 + 36LL),
        *(_QWORD *)(*(_QWORD *)v4 + 64LL),
        (unsigned __int64)&Context[-*(_QWORD *)(v4 + 1416)] / 0x88D0,
        *(_DWORD *)(v4 + 1344));
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( ((v17 - 2) & 0xFFFFFEFF) != 0 )
      break;
    if ( *v15 == (struct CFileName **)v15 )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 4u )
        WPP_SF_DDZd(
          (unsigned int)v18[2],
          81,
          (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
          *(_DWORD *)(**(_QWORD **)v4 + 16LL),
          *(_DWORD *)(**(_QWORD **)v4 + 36LL),
          *(_QWORD *)(*(_QWORD *)v4 + 64LL),
          (unsigned __int64)&Context[-*(_QWORD *)(v4 + 1416)] / 0x88D0);
      goto LABEL_68;
    }
    ++*((_DWORD *)Context + 8);
    v19 = QueryPerformanceCounter(&PerformanceCount);
    v36 = v19;
LABEL_38:
    ++*((_QWORD *)Context + 6);
    v20 = *v15;
    if ( (*v15)[1] != (struct CFileName *)v15 )
      goto LABEL_94;
    v21 = *v20;
    if ( *((struct CFileName ***)*v20 + 1) != v20 )
      goto LABEL_94;
    *v15 = (struct CFileName **)v21;
    *((_QWORD *)v21 + 1) = v15;
    v42 = v20;
    if ( *(_DWORD *)(*(_QWORD *)(v4 + 8) + 8LL) != 1 )
      *((_QWORD *)Context + 4304) = v15;
    ReleaseSRWLockExclusive(v16);
    v40 = 0;
    if ( NtWaitForMultipleObjects(2u, Object, WaitAny, 0, &LiZero) != 258 )
    {
      if ( v19 && QueryPerformanceCounter(&v37) )
        *((_QWORD *)Context + 7) += v37.QuadPart - PerformanceCount.QuadPart;
      AcquireSRWLockExclusive((PSRWLOCK)(v4 + 1448));
      CScrub::_DrainDirectoryQueue((CScrub *)v4);
      v34 = (_QWORD *)(v4 + 1352);
      v35 = *(_QWORD *)(v4 + 1352);
      if ( *(_QWORD *)(v35 + 8) == v4 + 1352 )
      {
        *(_QWORD *)Context = v35;
        *((_QWORD *)Context + 1) = v34;
        *(_QWORD *)(v35 + 8) = Context;
        *v34 = Context;
        ReleaseSRWLockExclusive((PSRWLOCK)(v4 + 1448));
        Time.QuadPart = 0;
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_92;
        }
        v32 = ((unsigned __int64)&Context[-*(_QWORD *)(v4 + 1416)] * (unsigned __int128)0x77C150CFB348283BuLL) >> 64;
        v33 = 83;
        goto LABEL_91;
      }
LABEL_93:
      __fastfail(3u);
    }
    FullPathName = (__int64)CScrub::_GetFullPathName((CScrub *)v4, (struct _SCRUB_THREAD_CONTEXT *)Context, v20[5], 0);
    v41 = FullPathName;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZZZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)v4 + 36LL),
        *(_QWORD *)(*(_QWORD *)v4 + 64LL),
        *(_QWORD *)(*(_QWORD *)v4 + 64LL),
        FullPathName);
      FullPathName = v41;
    }
    *((_WORD *)Context + 17248) = 0;
    v23 = 0;
    if ( *((struct CFileName ***)Context + 4311) == v20 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZZZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(**(_QWORD **)v4 + 36LL),
          *(_QWORD *)(*(_QWORD *)v4 + 64LL),
          *((_QWORD *)Context + 4310),
          FullPathName);
      }
      *((_QWORD *)Context + 4311) = 0;
      v23 = (const UNICODE_STRING *)*((_QWORD *)Context + 4310);
      *((_QWORD *)Context + 4310) = 0;
    }
    v24 = CScrub::_ScrubDirectoryInternal(
            v4,
            (__int64)Context,
            v20 + 3,
            v20[5],
            *((_DWORD *)v20 + 4),
            *((_DWORD *)v20 + 5),
            v23);
    v25 = v24;
    v45 = v24;
    if ( v24 == -805306102 )
    {
      if ( v36 && QueryPerformanceCounter(&v37) )
        *((_QWORD *)Context + 7) += v37.QuadPart - PerformanceCount.QuadPart;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZZZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(**(_QWORD **)v4 + 36LL),
          *(_QWORD *)(*(_QWORD *)v4 + 64LL),
          v41,
          (__int64)(Context + 34496));
      }
      AcquireSRWLockExclusive((PSRWLOCK)(v4 + 1448));
      CScrub::_DrainDirectoryQueue((CScrub *)v4);
      v29 = (_QWORD *)(v4 + 1352);
      v30 = *(_QWORD *)(v4 + 1352);
      if ( *(_QWORD *)(v30 + 8) == v4 + 1352 )
      {
        *(_QWORD *)Context = v30;
        *((_QWORD *)Context + 1) = v29;
        *(_QWORD *)(v30 + 8) = Context;
        *v29 = Context;
        ReleaseSRWLockExclusive((PSRWLOCK)(v4 + 1448));
        Time.QuadPart = 0;
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_92;
        }
        v32 = ((unsigned __int64)&Context[-*(_QWORD *)(v4 + 1416)] * (unsigned __int128)0x77C150CFB348283BuLL) >> 64;
        v33 = 87;
LABEL_91:
        WPP_SF_DDZd(
          v31[2],
          v33,
          (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
          *(_DWORD *)(**(_QWORD **)v4 + 16LL),
          *(_DWORD *)(**(_QWORD **)v4 + 36LL),
          *(_QWORD *)(*(_QWORD *)v4 + 64LL),
          v32 >> 14);
LABEL_92:
        _InterlockedDecrement((volatile signed __int32 *)(v4 + 1336));
        CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((RTL_SRWLOCK **)&Time);
        _SCRUB_DIRECTORY_ENTRY::`scalar deleting destructor'((_SCRUB_DIRECTORY_ENTRY *)v20);
        goto LABEL_70;
      }
      goto LABEL_93;
    }
    v11 = 0;
    if ( v24 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = CScrub::_GetFullPathName((CScrub *)v4, (struct _SCRUB_THREAD_CONTEXT *)Context, v20[5], 0);
      WPP_SF_DDZZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)v4 + 36LL),
        *(_QWORD *)(*(_QWORD *)v4 + 64LL),
        (__int64)v26,
        v25);
    }
    _SCRUB_DIRECTORY_ENTRY::`scalar deleting destructor'((_SCRUB_DIRECTORY_ENTRY *)v20);
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v40);
    v10 = v36;
  }
  CScrub::_DrainDirectoryQueue((CScrub *)v4);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DDZd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      82,
      (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
      *(_DWORD *)(**(_QWORD **)v4 + 16LL),
      *(_DWORD *)(**(_QWORD **)v4 + 36LL),
      *(_QWORD *)(*(_QWORD *)v4 + 64LL),
      (unsigned __int64)&Context[-*(_QWORD *)(v4 + 1416)] / 0x88D0);
  }
LABEL_68:
  v27 = (_QWORD *)(v4 + 1352);
  v28 = *(_QWORD *)(v4 + 1352);
  if ( *(_QWORD *)(v28 + 8) != v4 + 1352 )
LABEL_94:
    __fastfail(3u);
  *(_QWORD *)Context = v28;
  *((_QWORD *)Context + 1) = v27;
  *(_QWORD *)(v28 + 8) = Context;
  *v27 = Context;
  ReleaseSRWLockExclusive(v16);
  v40 = 0;
  _InterlockedDecrement((volatile signed __int32 *)(v4 + 1336));
LABEL_70:
  CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock(&v40);
  CHResultImp::~CHResultImp((CHResultImp *)&v44);
}

```

## disassembly

```asm
0x1800299f0  push    rbp
0x1800299f2  push    rbx
0x1800299f3  push    rsi
0x1800299f4  push    rdi
0x1800299f5  push    r12
0x1800299f7  push    r13
0x1800299f9  push    r14
0x1800299fb  push    r15
0x1800299fd  lea     rbp, [rsp-1Fh]
0x180029a02  sub     rsp, 0B8h
0x180029a09  mov     rax, cs:__security_cookie
0x180029a10  xor     rax, rsp
0x180029a13  mov     [rbp+57h+var_48], rax
0x180029a17  mov     r14, rdx
0x180029a1a  mov     rsi, [rdx+40h]
0x180029a1e  mov     ecx, cs:_tls_index
0x180029a24  mov     rax, gs:58h
0x180029a2d  mov     rdx, [rax+rcx*8]
0x180029a31  mov     eax, 10h
0x180029a36  lea     r8, aCscrubScrubdir; "CScrub::_ScrubDirectoryQueue"
0x180029a3d  mov     [rax+rdx], r8
0x180029a41  mov     [rbp+57h+var_70], r8
0x180029a45  xor     edi, edi
0x180029a47  mov     [rbp+57h+var_68], edi
0x180029a4a  mov     eax, 8
0x180029a4f  lea     ebx, [rdi+1]
0x180029a52  add     [rax+rdx], bx
0x180029a56  movzx   edx, word ptr [rax+rdx]
0x180029a5a  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180029a61  movzx   eax, cx
0x180029a64  cmp     dx, cx
0x180029a67  cmovb   ax, dx
0x180029a6b  mov     word ptr [rbp+57h+var_80], ax
0x180029a6f  cmovb   cx, dx
0x180029a73  mov     word ptr [rbp+57h+var_80+2], cx
0x180029a77  xor     eax, eax
0x180029a79  mov     dword ptr [rbp+57h+var_80+4], eax
0x180029a7c  mov     rax, cs:off_180047060; "                                       "...
0x180029a83  mov     [rbp+57h+var_78], rax
0x180029a87  lea     r12, WPP_GLOBAL_Control
0x180029a8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a95  cmp     rcx, r12
0x180029a98  jz      short loc_180029ABB
0x180029a9a  test    [rcx+1Ch], bl
0x180029a9d  jz      short loc_180029ABB
0x180029a9f  cmp     byte ptr [rcx+19h], 5
0x180029aa3  jb      short loc_180029ABB
0x180029aa5  lea     edx, [rdi+0Dh]
0x180029aa8  mov     [rsp+0F0h+Time], r8; __int64
0x180029aad  lea     r9, [rbp+57h+var_80]
0x180029ab1  mov     rcx, [rcx+10h]; LoggerHandle
0x180029ab5  call    WPP_SF_aZs
0x180029aba  nop
0x180029abb  mov     qword ptr [rbp+57h+PerformanceCount], rdi
0x180029abf  mov     qword ptr [rbp+57h+var_A8], rdi
0x180029ac3  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180029ac7  call    cs:__imp_QueryPerformanceCounter
0x180029acd  mov     r15d, eax
0x180029ad0  mov     [rbp+57h+var_B0], eax
0x180029ad3  mov     r13b, bl
0x180029ad6  add     [r14+28h], ebx
0x180029ada  mov     ecx, ebx
0x180029adc  lock xadd [rsi+538h], ecx
0x180029ae4  add     ecx, ebx
0x180029ae6  jmp     short loc_180029AF2
0x180029ae8  lock cmpxchg [rsi+53Ch], ecx
0x180029af0  jz      short loc_180029AFC
0x180029af2  mov     eax, [rsi+53Ch]
0x180029af8  cmp     ecx, eax
0x180029afa  jg      short loc_180029AE8
0x180029afc  mov     rax, [rsi+10h]
0x180029b00  mov     [rbp+57h+Object], rax
0x180029b04  mov     rax, [rsi+4C0h]
0x180029b0b  mov     [rbp+57h+var_58], rax
0x180029b0f  mov     rax, [rsi+490h]
0x180029b16  mov     [rbp+57h+var_50], rax
0x180029b1a  cmp     [r14+18h], dil
0x180029b1e  jnz     short loc_180029B3E
0x180029b20  lea     rcx, [r14+58h]; this
0x180029b24  mov     rax, [rsi]
0x180029b27  mov     r8, [rax+40h]; struct _UNICODE_STRING *
0x180029b2b  mov     [rcx], di
0x180029b2e  lea     rdx, ?EmptyUnicodeString@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x180029b35  call    ?PushNameEx@CScrubPath@@QEAAGPEBU_UNICODE_STRING@@00@Z; CScrubPath::PushNameEx(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180029b3a  mov     [r14+18h], bl
0x180029b3e  mov     rax, 77C150CFB348283Bh
0x180029b48  mov     rcx, cs:WPP_GLOBAL_Control
0x180029b4f  cmp     rcx, r12
0x180029b52  jz      short loc_180029BA8
0x180029b54  test    [rcx+1Ch], bl
0x180029b57  jz      short loc_180029BA8
0x180029b59  cmp     byte ptr [rcx+19h], 4
0x180029b5d  jb      short loc_180029BA8
0x180029b5f  mov     r10, [rsi]
0x180029b62  mov     r9, [r10]
0x180029b65  mov     rdx, r14
0x180029b68  sub     rdx, [rsi+588h]
0x180029b6f  mul     rdx
0x180029b72  mov     r8, rdx
0x180029b75  shr     r8, 0Eh
0x180029b79  mov     edx, 4Eh ; 'N'
0x180029b7e  mov     dword ptr [rsp+0F0h+var_C0], r8d
0x180029b83  mov     rax, [r10+40h]
0x180029b87  mov     [rsp+0F0h+var_C8], rax
0x180029b8c  mov     eax, [r9+24h]
0x180029b90  mov     dword ptr [rsp+0F0h+Time], eax
0x180029b94  mov     r9d, [r9+10h]
0x180029b98  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180029b9f  mov     rcx, [rcx+10h]
0x180029ba3  call    WPP_SF_DDZd
0x180029ba8  lea     rdi, [rsi+5A8h]
0x180029baf  lea     r12, [rsi+598h]
0x180029bb6  mov     rbx, rdi
0x180029bb9  mov     rcx, rdi; SRWLock
0x180029bbc  call    cs:__imp_AcquireSRWLockExclusive
0x180029bc2  nop
0x180029bc3  cmp     [r12], r12
0x180029bc7  jnz     loc_180029D77
0x180029bcd  test    r13b, r13b
0x180029bd0  jz      short loc_180029BD6
0x180029bd2  inc     dword ptr [r14+24h]
0x180029bd6  test    r15d, r15d
0x180029bd9  jz      short loc_180029BF5
0x180029bdb  lea     rcx, [rbp+57h+var_A8]; lpPerformanceCount
0x180029bdf  call    cs:__imp_QueryPerformanceCounter
0x180029be5  test    eax, eax
0x180029be7  jz      short loc_180029BF5
0x180029be9  mov     rax, qword ptr [rbp+57h+var_A8]
0x180029bed  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x180029bf1  add     [r14+38h], rax
0x180029bf5  mov     rax, [rsi+8]
0x180029bf9  cmp     dword ptr [rax+8], 1
0x180029bfd  jnz     loc_18002A06F
0x180029c03  mov     rcx, [rsi+490h]; EventHandle
0x180029c0a  call    cs:__imp_NtClearEvent
0x180029c10  inc     dword ptr [rsi+540h]
0x180029c16  mov     r11d, [rsi+540h]
0x180029c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029c24  lea     r13, WPP_GLOBAL_Control
0x180029c2b  cmp     rcx, r13
0x180029c2e  jz      short loc_180029C8D
0x180029c30  test    byte ptr [rcx+1Ch], 1
0x180029c34  jz      short loc_180029C8D
0x180029c36  cmp     byte ptr [rcx+19h], 4
0x180029c3a  jb      short loc_180029C8D
0x180029c3c  mov     r10, [rsi]
0x180029c3f  mov     r9, [r10]
0x180029c42  mov     rdx, r14
0x180029c45  sub     rdx, [rsi+588h]
0x180029c4c  mov     rax, 77C150CFB348283Bh
0x180029c56  mul     rdx
0x180029c59  mov     r8, rdx
0x180029c5c  shr     r8, 0Eh
0x180029c60  mov     edx, 4Fh ; 'O'
0x180029c65  mov     dword ptr [rsp+0F0h+var_B8], r11d
0x180029c6a  mov     dword ptr [rsp+0F0h+var_C0], r8d
0x180029c6f  mov     rax, [r10+40h]
0x180029c73  mov     [rsp+0F0h+var_C8], rax
0x180029c78  mov     eax, [r9+24h]
0x180029c7c  mov     dword ptr [rsp+0F0h+Time], eax
0x180029c80  mov     r9d, [r9+10h]
0x180029c84  mov     rcx, [rcx+10h]
0x180029c88  call    WPP_SF_DDZdd
0x180029c8d  mov     rcx, rbx; SRWLock
0x180029c90  call    cs:__imp_ReleaseSRWLockExclusive
0x180029c96  mov     qword ptr [rbp+57h+var_98], 0FFFFFFFFFD050F80h
0x180029c9e  lea     rax, [rbp+57h+var_98]
0x180029ca2  mov     [rsp+0F0h+Time], rax; Time
0x180029ca7  xor     r9d, r9d; Alertable
0x180029caa  lea     r8d, [r9+1]; WaitType
0x180029cae  lea     rdx, [rbp+57h+Object]; Object
0x180029cb2  lea     ecx, [r9+3]; Count
0x180029cb6  call    cs:__imp_NtWaitForMultipleObjects
0x180029cbc  mov     r15d, eax
0x180029cbf  mov     rbx, rdi
0x180029cc2  mov     rcx, rdi; SRWLock
0x180029cc5  call    cs:__imp_AcquireSRWLockExclusive
0x180029ccb  dec     dword ptr [rsi+540h]
0x180029cd1  mov     ecx, [rsi+540h]
0x180029cd7  mov     r11, cs:WPP_GLOBAL_Control
0x180029cde  cmp     r11, r13
0x180029ce1  jz      short loc_180029D48
0x180029ce3  test    byte ptr [r11+1Ch], 1
0x180029ce8  jz      short loc_180029D48
0x180029cea  cmp     byte ptr [r11+19h], 4
0x180029cef  jb      short loc_180029D48
0x180029cf1  mov     r10, [rsi]
0x180029cf4  mov     r9, [r10]
0x180029cf7  mov     rdx, r14
0x180029cfa  sub     rdx, [rsi+588h]
0x180029d01  mov     rax, 77C150CFB348283Bh
0x180029d0b  mul     rdx
0x180029d0e  mov     r8, rdx
0x180029d11  shr     r8, 0Eh
0x180029d15  mov     edx, 50h ; 'P'
0x180029d1a  mov     dword ptr [rsp+0F0h+var_B8], ecx
0x180029d1e  mov     dword ptr [rsp+0F0h+var_C0], r8d
0x180029d23  mov     rax, [r10+40h]
0x180029d27  mov     [rsp+0F0h+var_C8], rax
0x180029d2c  mov     eax, [r9+24h]
0x180029d30  mov     dword ptr [rsp+0F0h+Time], eax
0x180029d34  mov     r9d, [r9+10h]
0x180029d38  mov     rcx, [r11+10h]
0x180029d3c  call    WPP_SF_DDZdd
0x180029d41  mov     r11, cs:WPP_GLOBAL_Control
0x180029d48  lea     eax, [r15-2]
0x180029d4c  test    eax, 0FFFFFEFFh
0x180029d51  jnz     loc_180029FFC
0x180029d57  cmp     [r12], r12
0x180029d5b  jz      loc_180029FB0
0x180029d61  inc     dword ptr [r14+20h]
0x180029d65  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180029d69  call    cs:__imp_QueryPerformanceCounter
0x180029d6f  mov     r13d, eax
0x180029d72  mov     [rbp+57h+var_B0], eax
0x180029d75  jmp     short loc_180029D7B
0x180029d77  mov     r13d, [rbp+57h+var_B0]
0x180029d7b  inc     qword ptr [r14+30h]
0x180029d7f  mov     r15, [r12]
0x180029d83  cmp     [r15+8], r12
0x180029d87  jnz     loc_18002A2CE
0x180029d8d  mov     rax, [r15]
0x180029d90  cmp     [rax+8], r15
0x180029d94  jnz     loc_18002A2CE
0x180029d9a  mov     [r12], rax
0x180029d9e  mov     [rax+8], r12
0x180029da2  mov     [rbp+57h+var_80], r15
0x180029da6  mov     rax, [rsi+8]
0x180029daa  cmp     dword ptr [rax+8], 1
0x180029dae  jz      short loc_180029DB7
0x180029db0  mov     [r14+8680h], r12
0x180029db7  mov     rcx, rbx; SRWLock
0x180029dba  call    cs:__imp_ReleaseSRWLockExclusive
0x180029dc0  xor     ebx, ebx
0x180029dc2  mov     [rbp+57h+var_90], rbx
0x180029dc6  lea     rax, ?LiZero@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER LiZero
0x180029dcd  mov     [rsp+0F0h+Time], rax; struct _UNICODE_STRING *
0x180029dd2  xor     r9d, r9d; Alertable
0x180029dd5  lea     r8d, [rbx+1]; WaitType
0x180029dd9  lea     rdx, [rbp+57h+Object]; Object
0x180029ddd  lea     ecx, [rbx+2]; Count
0x180029de0  call    cs:__imp_NtWaitForMultipleObjects
0x180029de6  cmp     eax, 102h
0x180029deb  jnz     loc_18002A1DB
0x180029df1  xor     r9d, r9d; struct _UNICODE_STRING *
0x180029df4  mov     r8, [r15+28h]; struct CFileName *
0x180029df8  mov     rdx, r14; struct _SCRUB_THREAD_CONTEXT *
0x180029dfb  mov     rcx, rsi; this
0x180029dfe  call    ?_GetFullPathName@CScrub@@AEAAPEBU_UNICODE_STRING@@PEAU_SCRUB_THREAD_CONTEXT@@PEAVCFileName@@PEBU2@2@Z; CScrub::_GetFullPathName(_SCRUB_THREAD_CONTEXT *,CFileName *,_UNICODE_STRING const *,_UNICODE_STRING const *)
0x180029e03  mov     r10, rax
0x180029e06  mov     [rbp+57h+var_88], rax
0x180029e0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e11  lea     rdx, WPP_GLOBAL_Control
0x180029e18  cmp     rcx, rdx
0x180029e1b  jz      short loc_180029E65
0x180029e1d  test    byte ptr [rcx+1Ch], 1
0x180029e21  jz      short loc_180029E65
0x180029e23  cmp     byte ptr [rcx+19h], 4
0x180029e27  jb      short loc_180029E65
0x180029e29  mov     rdx, [rsi]
0x180029e2c  mov     rax, [rdx+40h]
0x180029e30  mov     r9, [rdx]
0x180029e33  lea     edx, [rbx+54h]
0x180029e36  mov     qword ptr [rsp+0F0h+var_B8], r10; __int64
0x180029e3b  mov     [rsp+0F0h+var_C0], rax; __int64
0x180029e40  mov     [rsp+0F0h+var_C8], rax; __int64
0x180029e45  mov     eax, [r9+24h]
0x180029e49  mov     dword ptr [rsp+0F0h+Time], eax; char
0x180029e4d  mov     r9d, [r9+10h]
0x180029e51  mov     rcx, [rcx+10h]; LoggerHandle
0x180029e55  call    WPP_SF_DDZZZ
0x180029e5a  mov     r10, [rbp+57h+var_88]
0x180029e5e  lea     rdx, WPP_GLOBAL_Control
0x180029e65  lea     r13, [r14+86C0h]
0x180029e6c  mov     [r13+0], bx
0x180029e71  mov     rax, rbx
0x180029e74  cmp     [r14+86B8h], r15
0x180029e7b  jnz     short loc_180029EE4
0x180029e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e84  cmp     rcx, rdx
0x180029e87  jz      short loc_180029ECF
0x180029e89  test    byte ptr [rcx+1Ch], 1
0x180029e8d  jz      short loc_180029ECF
0x180029e8f  cmp     byte ptr [rcx+19h], 4
0x180029e93  jb      short loc_180029ECF
0x180029e95  mov     r8, [rsi]
0x180029e98  mov     r9, [r8]
0x180029e9b  mov     edx, 55h ; 'U'
0x180029ea0  mov     qword ptr [rsp+0F0h+var_B8], r10; __int64
0x180029ea5  mov     rax, [r14+86B0h]
0x180029eac  mov     [rsp+0F0h+var_C0], rax; __int64
0x180029eb1  mov     rax, [r8+40h]
0x180029eb5  mov     [rsp+0F0h+var_C8], rax; __int64
0x180029eba  mov     eax, [r9+24h]
0x180029ebe  mov     dword ptr [rsp+0F0h+Time], eax; char
0x180029ec2  mov     r9d, [r9+10h]
0x180029ec6  mov     rcx, [rcx+10h]; LoggerHandle
0x180029eca  call    WPP_SF_DDZZZ
0x180029ecf  mov     [r14+86B8h], rbx
0x180029ed6  mov     rax, [r14+86B0h]
  ... truncated ...
```
