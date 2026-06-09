# CSmbFile::AsyncCommit(void *,ulong)

- ea: `0x180062f88`
- end: `0x180063404`
- name: `?AsyncCommit@CSmbFile@@QEAAXPEAXK@Z`
- size: `1148`
- prototype: `void __fastcall(CSmbFile *this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18009a900`

## callees

- `0x180008b70`
- `0x18000f5f0`
- `0x180062f88`
- `0x18006a310`
- `0x18009a9d0`
- `0x18009d024`
- `0x1800ab7fc`
- `0x1800ee198`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800630a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800630ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800630b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800631d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800631dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800631e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006324e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800632d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800632dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800632e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800630a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800630ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800630b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800631d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800631dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800631e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006324e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063262`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800632d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800632dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800632e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062ff5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063166`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180062ff5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063166`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063374`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063374`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800633fd`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800631c8`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800632c9`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800631c8`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800632c9`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180063244`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180063244`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18006309a`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18006309a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CSmbFile::AsyncCommit(CSmbFile *this, void *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  unsigned int LastError; // ecx
  LARGE_INTEGER v6; // r15
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  EVENT_LOG *v10; // rcx
  int v11; // ebx
  EVENT_LOG *v12; // rcx
  DWORD v13; // eax
  ComError *v14; // rbx
  ComError *v15; // rax
  struct _RTL_CRITICAL_SECTION *v17; // [rsp+50h] [rbp-228h]
  ComError *v19; // [rsp+58h] [rbp-220h] BYREF
  ComError *v20; // [rsp+60h] [rbp-218h] BYREF
  void **pExceptionObject; // [rsp+70h] [rbp-208h] BYREF
  __int128 v22; // [rsp+78h] [rbp-200h]
  unsigned int v23; // [rsp+88h] [rbp-1F0h]
  int v24; // [rsp+8Ch] [rbp-1ECh]
  int v25; // [rsp+90h] [rbp-1E8h]
  void **v26; // [rsp+D0h] [rbp-1A8h] BYREF
  __int128 v27; // [rsp+D8h] [rbp-1A0h]
  unsigned int v28; // [rsp+E8h] [rbp-190h]
  int v29; // [rsp+ECh] [rbp-18Ch]
  int v30; // [rsp+F0h] [rbp-188h]
  void **v31; // [rsp+130h] [rbp-148h] BYREF
  __int128 v32; // [rsp+138h] [rbp-140h]
  unsigned int v33; // [rsp+148h] [rbp-130h]
  int v34; // [rsp+14Ch] [rbp-12Ch]
  int v35; // [rsp+150h] [rbp-128h]
  void **v36; // [rsp+190h] [rbp-E8h] BYREF
  __int128 v37; // [rsp+198h] [rbp-E0h]
  unsigned int v38; // [rsp+1A8h] [rbp-D0h]
  int v39; // [rsp+1ACh] [rbp-CCh]
  int v40; // [rsp+1B0h] [rbp-C8h]
  _BYTE v41[136]; // [rsp+1F0h] [rbp-88h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v17 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  if ( *((_BYTE *)this + 48)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v4);
  }
  EnterCriticalSection(v4);
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_544ed435ee403dfadff71ae516532c05_Traceguids);
  try
  {
    if ( !*((_BYTE *)this + 376) )
    {
      if ( *((_QWORD *)this + 48) )
      {
        CNestedImpersonation::CNestedImpersonation((CNestedImpersonation *)v41, (CSmbFile *)((char *)this + 392));
        CSmbFile::SetFileLength(this, *((_QWORD *)this + 19), 1);
        (*(void (__fastcall **)(CSmbFile *))(*(_QWORD *)this + 56LL))(this);
        if ( !MoveFileExW(
                (LPCWSTR)(*(_QWORD *)(*((_QWORD *)this + 48) + 24LL) + 12LL),
                (LPCWSTR)(*((_QWORD *)this + 13) + 12LL),
                1u) )
        {
          if ( (int)GetLastError() > 0 )
            LastError = (unsigned __int16)GetLastError() | 0x80070000;
          else
            LastError = GetLastError();
          v22 = 0;
          pExceptionObject = &ComError::`vftable';
          v23 = LastError;
          v24 = 1164;
          v25 = 1;
          throw (ComError *)&pExceptionObject;
        }
        try
        {
          CSmbFile::SetSecurity(this, a2);
        }
        catch ( ComError *v19 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                32,
                &WPP_544ed435ee403dfadff71ae516532c05_Traceguids,
                *((unsigned int *)v19 + 6));
              v10 = WPP_GLOBAL_Control;
            }
            if ( v10 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)v10 + 2), 33, &WPP_544ed435ee403dfadff71ae516532c05_Traceguids);
          }
          v11 = 0;
          while ( !MoveFileExW(
                     (LPCWSTR)(*((_QWORD *)this + 13) + 12LL),
                     (LPCWSTR)(*(_QWORD *)(*((_QWORD *)this + 48) + 24LL) + 12LL),
                     1u) )
          {
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v13 = GetLastError();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_544ed435ee403dfadff71ae516532c05_Traceguids, v13);
              v12 = WPP_GLOBAL_Control;
            }
            if ( ++v11 > 50 )
            {
              if ( v12 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 )
                WPP_SF_(*((_QWORD *)v12 + 2), 36, &WPP_544ed435ee403dfadff71ae516532c05_Traceguids);
              throw;
            }
            Sleep(1u);
          }
          if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_544ed435ee403dfadff71ae516532c05_Traceguids);
          throw;
        }
        CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)v41);
        goto LABEL_45;
      }
      v6 = *(LARGE_INTEGER *)((char *)this + 152);
      if ( LOBYTE(v4[1].DebugInfo)
        && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v4);
      }
      EnterCriticalSection(v4);
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qq)(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          &WPP_544ed435ee403dfadff71ae516532c05_Traceguids,
          *((_QWORD *)this + 19),
          (LARGE_INTEGER)v6.QuadPart);
      *((LARGE_INTEGER *)this + 19) = v6;
      if ( v6.QuadPart != -1 )
      {
        if ( !SetFilePointerEx(*((HANDLE *)this + 40), v6, 0, 0) )
        {
          if ( (int)GetLastError() > 0 )
            v7 = (unsigned __int16)GetLastError() | 0x80070000;
          else
            v7 = GetLastError();
          v27 = 0;
          v26 = &ComError::`vftable';
          v28 = v7;
          v29 = 1362;
          v30 = 1;
          throw (ComError *)&v26;
        }
        if ( !SetEndOfFile(*((HANDLE *)this + 40)) )
        {
          if ( (int)GetLastError() > 0 )
            v8 = (unsigned __int16)GetLastError() | 0x80070000;
          else
            v8 = GetLastError();
          v32 = 0;
          v31 = &ComError::`vftable';
          v33 = v8;
          v34 = 1367;
          v35 = 1;
          throw (ComError *)&v31;
        }
        if ( !SetFilePointerEx(*((HANDLE *)this + 40), 0, 0, 0) )
        {
          if ( (int)GetLastError() > 0 )
            v9 = (unsigned __int16)GetLastError() | 0x80070000;
          else
            v9 = GetLastError();
          v37 = 0;
          v36 = &ComError::`vftable';
          v38 = v9;
          v39 = 1376;
          v40 = 1;
          throw (ComError *)&v36;
        }
      }
      if ( LOBYTE(v4[1].DebugInfo)
        && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v4);
      }
      LeaveCriticalSection(v4);
    }
    (*(void (__fastcall **)(CSmbFile *))(*(_QWORD *)this + 56LL))(this);
LABEL_45:
    (*(void (__fastcall **)(CSmbFile *, _QWORD, _QWORD))(*(_QWORD *)this + 488LL))(this, 0, 0);
  }
  catch ( ComError *v20 )
  {
    v14 = v20;
    v15 = ComError::ComError((ComError *)v41, v20);
    LogException(v15);
    (*(void (__fastcall **)(CSmbFile *, _QWORD, _QWORD))(*(_QWORD *)this + 488LL))(this, *((unsigned int *)v14 + 6), 0);
    v4 = v17;
  }
  if ( LOBYTE(v4[1].DebugInfo)
    && WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids, v4);
  }
  LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x180062f88  mov     [rsp+arg_10], rbx
0x180062f8d  push    rsi
0x180062f8e  push    rdi
0x180062f8f  push    r12
0x180062f91  push    r14
0x180062f93  push    r15
0x180062f95  sub     rsp, 250h
0x180062f9c  mov     r15, rdx
0x180062f9f  mov     rdi, rcx
0x180062fa2  mov     [rsp+278h+var_248], rcx
0x180062fa7  lea     rsi, [rcx+8]
0x180062fab  mov     [rsp+278h+var_228], rsi
0x180062fb0  xor     ebx, ebx
0x180062fb2  cmp     [rsi+28h], bl
0x180062fb5  jz      short loc_180062FEB
0x180062fb7  lea     r14, WPP_GLOBAL_Control
0x180062fbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180062fc5  cmp     rcx, r14
0x180062fc8  jz      short loc_180062FF2
0x180062fca  test    dword ptr [rcx+1Ch], 100h
0x180062fd1  jz      short loc_180062FF2
0x180062fd3  lea     edx, [rbx+0Fh]
0x180062fd6  mov     r9, rsi
0x180062fd9  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x180062fe0  mov     rcx, [rcx+10h]
0x180062fe4  call    WPP_SF_q
0x180062fe9  jmp     short loc_180062FF2
0x180062feb  lea     r14, WPP_GLOBAL_Control
0x180062ff2  mov     rcx, rsi; lpCriticalSection
0x180062ff5  call    cs:__imp_EnterCriticalSection
0x180062ffb  mov     r12d, 1
0x180063001  mov     [rsp+278h+var_230], r12b
0x180063006  mov     rcx, cs:WPP_GLOBAL_Control
0x18006300d  cmp     rcx, r14
0x180063010  jz      short loc_180063031
0x180063012  test    dword ptr [rcx+1Ch], 800h
0x180063019  jz      short loc_180063031
0x18006301b  lea     edx, [r12+1Eh]
0x180063020  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x180063027  mov     rcx, [rcx+10h]
0x18006302b  call    WPP_SF_
0x180063030  nop
0x180063031  cmp     [rdi+178h], bl
0x180063037  jnz     loc_18006337A
0x18006303d  cmp     [rdi+180h], rbx
0x180063044  jz      loc_180063125
0x18006304a  lea     rdx, [rdi+188h]; struct TokenHandle *
0x180063051  lea     rcx, [rsp+278h+var_88]; this
0x180063059  call    ??0CNestedImpersonation@@QEAA@AEBVTokenHandle@@@Z; CNestedImpersonation::CNestedImpersonation(TokenHandle const &)
0x18006305e  nop
0x18006305f  mov     r8b, r12b; bool
0x180063062  mov     rdx, [rdi+98h]; unsigned __int64
0x180063069  mov     rcx, rdi; this
0x18006306c  call    ?SetFileLength@CSmbFile@@IEAAX_K_N@Z; CSmbFile::SetFileLength(unsigned __int64,bool)
0x180063071  mov     rax, [rdi]
0x180063074  mov     rcx, rdi
0x180063077  mov     rax, [rax+38h]
0x18006307b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063080  mov     rdx, [rdi+68h]
0x180063084  add     rdx, 0Ch; lpNewFileName
0x180063088  mov     rax, [rdi+180h]
0x18006308f  mov     rcx, [rax+18h]
0x180063093  add     rcx, 0Ch; lpExistingFileName
0x180063097  mov     r8d, r12d; dwFlags
0x18006309a  call    cs:__imp_MoveFileExW
0x1800630a0  test    eax, eax
0x1800630a2  jnz     short loc_180063107
0x1800630a4  call    cs:__imp_GetLastError
0x1800630aa  test    eax, eax
0x1800630ac  jg      short loc_1800630B8
0x1800630ae  call    cs:__imp_GetLastError
0x1800630b4  mov     ecx, eax
0x1800630b6  jmp     short loc_1800630C7
0x1800630b8  call    cs:__imp_GetLastError
0x1800630be  movzx   ecx, ax
0x1800630c1  or      ecx, 80070000h
0x1800630c7  xorps   xmm0, xmm0
0x1800630ca  movups  [rsp+278h+var_200], xmm0
0x1800630cf  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x1800630d6  mov     [rsp+278h+pExceptionObject], rax
0x1800630db  mov     [rsp+278h+var_1F0], ecx
0x1800630e2  mov     [rsp+278h+var_1EC], 48Ch
0x1800630ed  mov     [rsp+278h+var_1E8], r12d
0x1800630f5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800630fc  lea     rcx, [rsp+278h+pExceptionObject]; pExceptionObject
0x180063101  call    _CxxThrowException_0
0x180063107  mov     rdx, r15; void *
0x18006310a  mov     rcx, rdi; this
0x18006310d  call    ?SetSecurity@CSmbFile@@IEAAXPEAX@Z; CSmbFile::SetSecurity(void *)
0x180063112  nop
0x180063113  lea     rcx, [rsp+278h+var_88]; this
0x18006311b  call    ??1CNestedImpersonation@@QEAA@XZ; CNestedImpersonation::~CNestedImpersonation(void)
0x180063120  jmp     loc_180063389
0x180063125  mov     r15, [rdi+98h]
0x18006312c  mov     [rsp+278h+var_238], rsi
0x180063131  cmp     [rsi+28h], bl
0x180063134  jz      short loc_180063163
0x180063136  mov     rcx, cs:WPP_GLOBAL_Control
0x18006313d  cmp     rcx, r14
0x180063140  jz      short loc_180063163
0x180063142  test    dword ptr [rcx+1Ch], 100h
0x180063149  jz      short loc_180063163
0x18006314b  mov     edx, 0Fh
0x180063150  mov     r9, rsi
0x180063153  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x18006315a  mov     rcx, [rcx+10h]
0x18006315e  call    WPP_SF_q
0x180063163  mov     rcx, rsi; lpCriticalSection
0x180063166  call    cs:__imp_EnterCriticalSection
0x18006316c  mov     [rsp+278h+var_240], r12b
0x180063171  mov     rcx, cs:WPP_GLOBAL_Control
0x180063178  cmp     rcx, r14
0x18006317b  jz      short loc_1800631A7
0x18006317d  test    dword ptr [rcx+1Ch], 800h
0x180063184  jz      short loc_1800631A7
0x180063186  mov     edx, 26h ; '&'
0x18006318b  mov     [rsp+278h+var_258], r15
0x180063190  mov     r9, [rdi+98h]
0x180063197  lea     r8, WPP_544ed435ee403dfadff71ae516532c05_Traceguids
0x18006319e  mov     rcx, [rcx+10h]
0x1800631a2  call    WPP_SF_qq
0x1800631a7  mov     [rdi+98h], r15
0x1800631ae  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800631b2  jz      loc_18006333F
0x1800631b8  xor     r9d, r9d; dwMoveMethod
0x1800631bb  xor     r8d, r8d; lpNewFilePointer
0x1800631be  mov     rdx, r15; liDistanceToMove
0x1800631c1  mov     rcx, [rdi+140h]; hFile
0x1800631c8  call    cs:__imp_SetFilePointerEx
0x1800631ce  test    eax, eax
0x1800631d0  jnz     short loc_18006323D
0x1800631d2  call    cs:__imp_GetLastError
0x1800631d8  test    eax, eax
0x1800631da  jg      short loc_1800631E6
0x1800631dc  call    cs:__imp_GetLastError
0x1800631e2  mov     ecx, eax
0x1800631e4  jmp     short loc_1800631F5
0x1800631e6  call    cs:__imp_GetLastError
0x1800631ec  movzx   ecx, ax
0x1800631ef  or      ecx, 80070000h
0x1800631f5  xorps   xmm0, xmm0
0x1800631f8  movups  [rsp+278h+var_1A0], xmm0
0x180063200  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180063207  mov     [rsp+278h+var_1A8], rax
0x18006320f  mov     [rsp+278h+var_190], ecx
0x180063216  mov     [rsp+278h+var_18C], 552h
0x180063221  mov     [rsp+278h+var_188], r12d
0x180063229  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180063230  lea     rcx, [rsp+278h+var_1A8]; pExceptionObject
0x180063238  call    _CxxThrowException_0
0x18006323d  mov     rcx, [rdi+140h]; hFile
0x180063244  call    cs:__imp_SetEndOfFile
0x18006324a  test    eax, eax
0x18006324c  jnz     short loc_1800632B9
0x18006324e  call    cs:__imp_GetLastError
0x180063254  test    eax, eax
0x180063256  jg      short loc_180063262
0x180063258  call    cs:__imp_GetLastError
0x18006325e  mov     ecx, eax
0x180063260  jmp     short loc_180063271
0x180063262  call    cs:__imp_GetLastError
0x180063268  movzx   ecx, ax
0x18006326b  or      ecx, 80070000h
0x180063271  xorps   xmm0, xmm0
0x180063274  movups  [rsp+278h+var_140], xmm0
0x18006327c  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180063283  mov     [rsp+278h+var_148], rax
0x18006328b  mov     [rsp+278h+var_130], ecx
0x180063292  mov     [rsp+278h+var_12C], 557h
0x18006329d  mov     [rsp+278h+var_128], r12d
0x1800632a5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800632ac  lea     rcx, [rsp+278h+var_148]; pExceptionObject
0x1800632b4  call    _CxxThrowException_0
0x1800632b9  xor     r9d, r9d; dwMoveMethod
0x1800632bc  xor     r8d, r8d; lpNewFilePointer
0x1800632bf  mov     rdx, rbx; liDistanceToMove
0x1800632c2  mov     rcx, [rdi+140h]; hFile
0x1800632c9  call    cs:__imp_SetFilePointerEx
0x1800632cf  test    eax, eax
0x1800632d1  jnz     short loc_18006333F
0x1800632d3  call    cs:__imp_GetLastError
0x1800632d9  test    eax, eax
0x1800632db  jg      short loc_1800632E7
0x1800632dd  call    cs:__imp_GetLastError
0x1800632e3  mov     ecx, eax
0x1800632e5  jmp     short loc_1800632F6
0x1800632e7  call    cs:__imp_GetLastError
0x1800632ed  movzx   ecx, ax
0x1800632f0  or      ecx, 80070000h
0x1800632f6  xorps   xmm0, xmm0
0x1800632f9  movups  [rsp+278h+var_E0], xmm0
0x180063301  lea     rax, ??_7ComError@@6B@; const ComError::`vftable'
0x180063308  mov     [rsp+278h+var_E8], rax
0x180063310  mov     [rsp+278h+var_D0], ecx
0x180063317  mov     [rsp+278h+var_CC], 560h
0x180063322  mov     [rsp+278h+var_C8], r12d
0x18006332a  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180063331  lea     rcx, [rsp+278h+var_E8]; pExceptionObject
0x180063339  call    _CxxThrowException_0
0x18006333f  cmp     [rsi+28h], bl
0x180063342  jz      short loc_180063371
0x180063344  mov     rcx, cs:WPP_GLOBAL_Control
0x18006334b  cmp     rcx, r14
0x18006334e  jz      short loc_180063371
0x180063350  test    dword ptr [rcx+1Ch], 100h
0x180063357  jz      short loc_180063371
0x180063359  mov     edx, 10h
0x18006335e  mov     r9, rsi
0x180063361  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x180063368  mov     rcx, [rcx+10h]
0x18006336c  call    WPP_SF_q
0x180063371  mov     rcx, rsi; lpCriticalSection
0x180063374  call    cs:__imp_LeaveCriticalSection
0x18006337a  mov     rax, [rdi]
0x18006337d  mov     rcx, rdi
0x180063380  mov     rax, [rax+38h]
0x180063384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063389  mov     rax, [rdi]
0x18006338c  xor     r8d, r8d
0x18006338f  xor     edx, edx
0x180063391  mov     rcx, rdi
0x180063394  mov     rax, [rax+1E8h]
0x18006339b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800633a0  nop
0x1800633a1  jmp     short loc_1800633B1
0x1800633a3  xor     ebx, ebx
0x1800633a5  lea     r14, WPP_GLOBAL_Control
0x1800633ac  mov     rsi, [rsp+278h+var_228]
0x1800633b1  cmp     [rsi+28h], bl
0x1800633b4  jz      short loc_1800633E3
0x1800633b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800633bd  cmp     rcx, r14
0x1800633c0  jz      short loc_1800633E3
0x1800633c2  test    dword ptr [rcx+1Ch], 100h
0x1800633c9  jz      short loc_1800633E3
0x1800633cb  mov     edx, 10h
0x1800633d0  mov     r9, rsi
0x1800633d3  lea     r8, WPP_a9992ea4d18d3911b092fd3b6d6fa54a_Traceguids
0x1800633da  mov     rcx, [rcx+10h]
0x1800633de  call    WPP_SF_q
0x1800633e3  mov     rcx, rsi
0x1800633e6  mov     rbx, [rsp+278h+arg_10]
0x1800633ee  add     rsp, 250h
0x1800633f5  pop     r15
0x1800633f7  pop     r14
0x1800633f9  pop     r12
0x1800633fb  pop     rdi
0x1800633fc  pop     rsi
0x1800633fd  jmp     cs:__imp_LeaveCriticalSection
```
