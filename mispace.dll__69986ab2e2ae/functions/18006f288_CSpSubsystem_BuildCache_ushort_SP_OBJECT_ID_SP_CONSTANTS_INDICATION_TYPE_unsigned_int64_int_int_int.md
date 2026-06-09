# CSpSubsystem::BuildCache(ushort,_SP_OBJECT_ID *,SP_CONSTANTS::INDICATION_TYPE,unsigned __int64,int,int,int)

- ea: `0x18006f288`
- end: `0x18006f545`
- name: `?BuildCache@CSpSubsystem@@QEAA?AW4_MI_Result@@GPEAU_SP_OBJECT_ID@@W4INDICATION_TYPE@SP_CONSTANTS@@_KHHH@Z`
- size: `701`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180023e8c`
- `0x180080220`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x180013bf8`
- `0x18006f288`
- `0x18007ad00`
- `0x18007aec4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f41d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f41d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006f33e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006f33e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006f4e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006f4e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006f303`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006f303`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006f409`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006f409`

## string_xrefs

- `0x18006f2a8`: `CSpSubsystem::BuildCache`
- `0x18006f3ad`: `CSpSubsystem::BuildCache`
- `0x18006f49d`: `CSpSubsystem::BuildCache`
- `0x18006f4ee`: `CSpSubsystem::BuildCache`

## pseudocode

```c
__int64 __fastcall CSpSubsystem::BuildCache(
        RTL_SRWLOCK *a1,
        unsigned __int16 a2,
        _DWORD *a3,
        unsigned int a4,
        __int64 a5,
        int a6,
        int a7,
        unsigned int a8)
{
  enum _MI_Result updated; // ebx
  int v13; // r12d
  int v14; // esi
  int v15; // ecx
  DWORD LastError; // ebx
  int v17; // r8d
  int v18; // r9d
  char *v19; // rdx
  const char *v21; // [rsp+40h] [rbp-10h] BYREF
  const char *v22; // [rsp+48h] [rbp-8h] BYREF
  int v23; // [rsp+80h] [rbp+30h] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v23 = 633;
    v21 = "CSpSubsystem::BuildCache";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)byte_180317A1D,
      (_DWORD)a3,
      a4,
      (__int64)&v21,
      (__int64)&v23);
  }
  updated = MI_RESULT_OK;
  if ( *((_DWORD *)a1[1].Ptr + 8) == 2 )
  {
    v13 = 0;
    if ( a7 )
    {
      AcquireSRWLockExclusive(a1 + 4);
      v13 = 1;
    }
    if ( !a3 || ((*a3 - 5) & 0xFFFFFFF7) == 0 )
    {
      updated = (unsigned int)CSpSubsystem::_UpdateLeveledDiscoverCache((CSpSubsystem *)a1, a2, (int)a3, a4);
      if ( updated && (unsigned int)dword_18039EB68 > 2 )
      {
        v23 = updated;
        v22 = "CSpSubsystem::BuildCache";
        LODWORD(v21) = 691;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)a1,
          (unsigned int)byte_180317BC1,
          (_DWORD)a3,
          a4,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)&v23);
      }
      goto LABEL_35;
    }
    v14 = a6;
    if ( !a6 || SetThreadToken(0, a1[6].Ptr) )
    {
      CSpSubsystem::_UpdateRootedDiscoverCache(a1, a3, a4, a8, a5);
      if ( !v14 || RevertToSelf() )
      {
LABEL_35:
        if ( v13 )
          ReleaseSRWLockExclusive(a1 + 4);
        goto LABEL_37;
      }
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError == 122 )
        {
          if ( (unsigned int)dword_18039EB68 <= 3 )
            goto LABEL_20;
          v23 = 122;
          v19 = (char *)&word_180315EAE;
        }
        else
        {
          if ( (unsigned int)dword_18039EB68 <= 2 )
            goto LABEL_20;
          v23 = LastError;
          v19 = (char *)&word_180316BC6;
        }
      }
      else
      {
        v15 = dword_18039EB68;
        if ( (unsigned int)dword_18039EB68 <= 4 )
          goto LABEL_20;
        v23 = 0;
        v19 = byte_1803171CD;
      }
      LODWORD(v21) = 679;
      goto LABEL_19;
    }
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError == 122 )
      {
        if ( (unsigned int)dword_18039EB68 > 3 )
        {
          v23 = 122;
          v19 = byte_180315C39;
          goto LABEL_18;
        }
      }
      else if ( (unsigned int)dword_18039EB68 > 2 )
      {
        v23 = LastError;
        v19 = byte_180317465;
        goto LABEL_18;
      }
    }
    else
    {
      v15 = dword_18039EB68;
      if ( (unsigned int)dword_18039EB68 > 4 )
      {
        v23 = 0;
        v19 = byte_180316CD3;
LABEL_18:
        LODWORD(v21) = 664;
LABEL_19:
        v22 = "CSpSubsystem::BuildCache";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v15,
          (_DWORD)v19,
          v17,
          v18,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)&v23);
      }
    }
LABEL_20:
    updated = MI_FROM_WIN32(LastError);
    goto LABEL_35;
  }
LABEL_37:
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v23 = 702;
    v22 = "CSpSubsystem::BuildCache";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)byte_180318913,
      (_DWORD)a3,
      a4,
      (__int64)&v22,
      (__int64)&v23);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18006f288  mov     r11, rsp
0x18006f28b  mov     [r11+10h], rbx
0x18006f28f  mov     [r11+18h], rsi
0x18006f293  push    rbp
0x18006f294  push    rdi
0x18006f295  push    r12
0x18006f297  push    r14
0x18006f299  push    r15
0x18006f29b  mov     rbp, rsp
0x18006f29e  sub     rsp, 50h
0x18006f2a2  mov     eax, cs:dword_18039EB68
0x18006f2a8  lea     r12, aCspsubsystemBu; "CSpSubsystem::BuildCache"
0x18006f2af  mov     r15d, r9d
0x18006f2b2  mov     r14, r8
0x18006f2b5  movzx   esi, dx
0x18006f2b8  mov     rdi, rcx
0x18006f2bb  cmp     eax, 5
0x18006f2be  jbe     short loc_18006F2E7
0x18006f2c0  lea     rax, [rbp+arg_0]
0x18006f2c4  mov     [rbp+arg_0], 279h
0x18006f2cb  mov     [r11-50h], rax
0x18006f2cf  lea     rdx, byte_180317A1D
0x18006f2d6  lea     rax, [rbp+var_10]
0x18006f2da  mov     [rbp+var_10], r12
0x18006f2de  mov     [r11-58h], rax
0x18006f2e2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006f2e7  mov     rax, [rdi+8]
0x18006f2eb  xor     ebx, ebx
0x18006f2ed  cmp     dword ptr [rax+20h], 2
0x18006f2f1  jnz     loc_18006F4F5
0x18006f2f7  xor     r12d, r12d
0x18006f2fa  cmp     [rbp+arg_30], ebx
0x18006f2fd  jz      short loc_18006F313
0x18006f2ff  lea     rcx, [rdi+20h]; SRWLock
0x18006f303  call    cs:__imp_AcquireSRWLockExclusive
0x18006f30a  nop     dword ptr [rax+rax+00h]
0x18006f30f  lea     r12d, [rbx+1]
0x18006f313  test    r14, r14
0x18006f316  jz      loc_18006F481
0x18006f31c  mov     eax, [r14]
0x18006f31f  sub     eax, 5
0x18006f322  test    eax, 0FFFFFFF7h
0x18006f327  jz      loc_18006F481
0x18006f32d  mov     esi, [rbp+arg_28]
0x18006f330  test    esi, esi
0x18006f332  jz      loc_18006F3E6
0x18006f338  mov     rdx, [rdi+30h]; Token
0x18006f33c  xor     ecx, ecx; Thread
0x18006f33e  call    cs:__imp_SetThreadToken
0x18006f345  nop     dword ptr [rax+rax+00h]
0x18006f34a  test    eax, eax
0x18006f34c  jnz     loc_18006F3E6
0x18006f352  call    cs:__imp_GetLastError
0x18006f359  nop     dword ptr [rax+rax+00h]
0x18006f35e  mov     ebx, eax
0x18006f360  test    eax, eax
0x18006f362  jnz     short loc_18006F37B
0x18006f364  mov     ecx, cs:dword_18039EB68
0x18006f36a  cmp     ecx, 4
0x18006f36d  jbe     short loc_18006F3D8
0x18006f36f  mov     [rbp+arg_0], eax
0x18006f372  lea     rdx, byte_180316CD3
0x18006f379  jmp     short loc_18006F3A6
0x18006f37b  mov     eax, cs:dword_18039EB68
0x18006f381  cmp     ebx, 7Ah ; 'z'
0x18006f384  jnz     short loc_18006F397
0x18006f386  cmp     eax, 3
0x18006f389  jbe     short loc_18006F3D8
0x18006f38b  mov     [rbp+arg_0], ebx
0x18006f38e  lea     rdx, byte_180315C39
0x18006f395  jmp     short loc_18006F3A6
0x18006f397  cmp     eax, 2
0x18006f39a  jbe     short loc_18006F3D8
0x18006f39c  mov     [rbp+arg_0], ebx
0x18006f39f  lea     rdx, byte_180317465
0x18006f3a6  mov     dword ptr [rbp+var_10], 298h
0x18006f3ad  lea     rax, aCspsubsystemBu; "CSpSubsystem::BuildCache"
0x18006f3b4  mov     [rbp+var_8], rax
0x18006f3b8  lea     rax, [rbp+arg_0]
0x18006f3bc  mov     [rsp+50h+var_20], rax
0x18006f3c1  lea     rax, [rbp+var_10]
0x18006f3c5  mov     [rsp+50h+var_28], rax
0x18006f3ca  lea     rax, [rbp+var_8]
0x18006f3ce  mov     [rsp+50h+var_30], rax
0x18006f3d3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006f3d8  mov     ecx, ebx; unsigned int
0x18006f3da  call    ?MI_FROM_WIN32@@YA?AW4_MI_Result@@K@Z; MI_FROM_WIN32(ulong)
0x18006f3df  mov     ebx, eax
0x18006f3e1  jmp     loc_18006F4D9
0x18006f3e6  mov     rax, [rbp+arg_20]
0x18006f3ea  mov     r8d, r15d
0x18006f3ed  mov     r9d, [rbp+arg_38]
0x18006f3f1  mov     rdx, r14
0x18006f3f4  mov     rcx, rdi
0x18006f3f7  mov     [rsp+50h+var_30], rax
0x18006f3fc  call    ?_UpdateRootedDiscoverCache@CSpSubsystem@@IEAAXPEAU_SP_OBJECT_ID@@W4INDICATION_TYPE@SP_CONSTANTS@@H_K@Z; CSpSubsystem::_UpdateRootedDiscoverCache(_SP_OBJECT_ID *,SP_CONSTANTS::INDICATION_TYPE,int,unsigned __int64)
0x18006f401  test    esi, esi
0x18006f403  jz      loc_18006F4D9
0x18006f409  call    cs:__imp_RevertToSelf
0x18006f410  nop     dword ptr [rax+rax+00h]
0x18006f415  test    eax, eax
0x18006f417  jnz     loc_18006F4D9
0x18006f41d  call    cs:__imp_GetLastError
0x18006f424  nop     dword ptr [rax+rax+00h]
0x18006f429  mov     ebx, eax
0x18006f42b  test    eax, eax
0x18006f42d  jnz     short loc_18006F446
0x18006f42f  mov     ecx, cs:dword_18039EB68
0x18006f435  cmp     ecx, 4
0x18006f438  jbe     short loc_18006F3D8
0x18006f43a  mov     [rbp+arg_0], eax
0x18006f43d  lea     rdx, byte_1803171CD
0x18006f444  jmp     short loc_18006F475
0x18006f446  mov     eax, cs:dword_18039EB68
0x18006f44c  cmp     ebx, 7Ah ; 'z'
0x18006f44f  jnz     short loc_18006F462
0x18006f451  cmp     eax, 3
0x18006f454  jbe     short loc_18006F3D8
0x18006f456  mov     [rbp+arg_0], ebx
0x18006f459  lea     rdx, word_180315EAE
0x18006f460  jmp     short loc_18006F475
0x18006f462  cmp     eax, 2
0x18006f465  jbe     loc_18006F3D8
0x18006f46b  mov     [rbp+arg_0], ebx
0x18006f46e  lea     rdx, word_180316BC6
0x18006f475  mov     dword ptr [rbp+var_10], 2A7h
0x18006f47c  jmp     loc_18006F3AD
0x18006f481  movzx   edx, si; unsigned __int16
0x18006f484  mov     rcx, rdi; this
0x18006f487  call    ?_UpdateLeveledDiscoverCache@CSpSubsystem@@IEAA?AW4_MI_Result@@G@Z; CSpSubsystem::_UpdateLeveledDiscoverCache(ushort)
0x18006f48c  mov     ebx, eax
0x18006f48e  test    eax, eax
0x18006f490  jz      short loc_18006F4D9
0x18006f492  mov     eax, cs:dword_18039EB68
0x18006f498  cmp     eax, 2
0x18006f49b  jbe     short loc_18006F4D9
0x18006f49d  lea     rax, aCspsubsystemBu; "CSpSubsystem::BuildCache"
0x18006f4a4  mov     [rbp+arg_0], ebx
0x18006f4a7  mov     [rbp+var_8], rax
0x18006f4ab  lea     rdx, byte_180317BC1
0x18006f4b2  lea     rax, [rbp+arg_0]
0x18006f4b6  mov     dword ptr [rbp+var_10], 2B3h
0x18006f4bd  mov     [rsp+50h+var_20], rax
0x18006f4c2  lea     rax, [rbp+var_10]
0x18006f4c6  mov     [rsp+50h+var_28], rax
0x18006f4cb  lea     rax, [rbp+var_8]
0x18006f4cf  mov     [rsp+50h+var_30], rax
0x18006f4d4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006f4d9  test    r12d, r12d
0x18006f4dc  jz      short loc_18006F4EE
0x18006f4de  lea     rcx, [rdi+20h]; SRWLock
0x18006f4e2  call    cs:__imp_ReleaseSRWLockExclusive
0x18006f4e9  nop     dword ptr [rax+rax+00h]
0x18006f4ee  lea     r12, aCspsubsystemBu; "CSpSubsystem::BuildCache"
0x18006f4f5  mov     eax, cs:dword_18039EB68
0x18006f4fb  cmp     eax, 5
0x18006f4fe  jbe     short loc_18006F529
0x18006f500  lea     rax, [rbp+arg_0]
0x18006f504  mov     [rbp+arg_0], 2BEh
0x18006f50b  mov     [rsp+50h+var_28], rax
0x18006f510  lea     rdx, byte_180318913
0x18006f517  lea     rax, [rbp+var_8]
0x18006f51b  mov     [rbp+var_8], r12
0x18006f51f  mov     [rsp+50h+var_30], rax
0x18006f524  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006f529  lea     r11, [rsp+50h+var_s0]
0x18006f52e  mov     eax, ebx
0x18006f530  mov     rbx, [r11+38h]
0x18006f534  mov     rsi, [r11+40h]
0x18006f538  mov     rsp, r11
0x18006f53b  pop     r15
0x18006f53d  pop     r14
0x18006f53f  pop     r12
0x18006f541  pop     rdi
0x18006f542  pop     rbp
0x18006f543  retn
```
