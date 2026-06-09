# CEdpCredSvcUserState::GetCreateUserState(ushort const *,int,CEdpCredSvcUserState * *)

- ea: `0x18009ca50`
- end: `0x18009cd93`
- name: `?GetCreateUserState@CEdpCredSvcUserState@@SAJPEBGHPEAPEAV1@@Z`
- size: `835`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, struct CEdpCredSvcUserState **)`
- caller_count: `12`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180080960`
- `0x180081bf8`
- `0x180082224`
- `0x180082620`
- `0x180082968`
- `0x180083c44`
- `0x180086c60`
- `0x1800968bc`
- `0x18009b7bc`
- `0x18009c2a8`
- `0x18009d8a0`
- `0x1800a0da0`

## callees

- `0x180004e10`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180088cf8`
- `0x18009a9d4`
- `0x18009ac28`
- `0x18009ca50`
- `0x18009e6bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009cb57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009cb57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009cd00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009cd00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cc4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009cc4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cd15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009cd15`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009cb87`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18009cb87`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18009cc41`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18009cc41`

## pseudocode

```c
__int64 __fastcall CEdpCredSvcUserState::GetCreateUserState(
        const unsigned __int16 *a1,
        int a2,
        struct CEdpCredSvcUserState **a3)
{
  int v6; // ecx
  unsigned int v7; // ebx
  struct _LIST_ENTRY *Flink; // rsi
  PSID v9; // rdi
  CEdpCredSvcUserState *v10; // rbp
  CEdpCredSvcUserState *v11; // rax
  CEdpCredSvcUserState *v12; // rax
  CEdpCredSvcUserState *v13; // rsi
  signed int LastError; // eax
  PSID pSid1; // [rsp+70h] [rbp+8h] BYREF

  pSid1 = 0;
  fnEfsLogTrace1Strings((_DWORD)a1, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 35, 165);
  if ( a3 )
    *a3 = 0;
  if ( a1 )
  {
    if ( a3 )
    {
      if ( g_EdpSvcInitCounter <= 0 )
      {
        v7 = -2147418113;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 35, 176);
      }
      else
      {
        fnEfsLogTrace1Strings(v6, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 35, 179);
        v7 = CDplServiceImpl::CheckConvertStringSidToSid(a1, &pSid1);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    v7,
                    35,
                    179) < 0 )
        {
          v9 = pSid1;
        }
        else
        {
          EnterCriticalSection(&g_UserStateListLock);
          Flink = g_UserStateList.Flink;
          v9 = pSid1;
          if ( g_UserStateList.Flink == &g_UserStateList )
            goto LABEL_14;
          do
          {
            v10 = (CEdpCredSvcUserState *)&Flink[-5];
            if ( EqualSid(v9, Flink[1].Blink) )
              break;
            Flink = Flink->Flink;
            v10 = 0;
          }
          while ( Flink != &g_UserStateList );
          if ( !v10 )
          {
LABEL_14:
            if ( a2 )
            {
              v11 = (CEdpCredSvcUserState *)operator new(0x98u, (const struct std::nothrow_t *)&std::nothrow);
              if ( v11 && (v12 = CEdpCredSvcUserState::CEdpCredSvcUserState(v11), (v13 = v12) != 0) )
              {
                if ( ConvertSidToStringSidW(v9, (LPWSTR *)v12 + 1) )
                {
                  *((_QWORD *)v13 + 13) = v9;
                  v9 = 0;
                  fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
                    (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
                    (unsigned int)L"Returning new object",
                    0,
                    35,
                    253);
                  CEdpCredSvcUserState::AddRef(v13);
                  *a3 = v13;
                }
                else
                {
                  LastError = GetLastError();
                  v7 = LastError;
                  if ( LastError > 0 )
                    v7 = (unsigned __int16)LastError | 0x80070000;
                  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v7, 35, 243);
                  CEdpCredSvcUserState::Release(v13);
                }
              }
              else
              {
                v7 = -2147024882;
                fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024882, 35, 239);
              }
            }
            else
            {
              v7 = 1;
              fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 35, 229);
            }
          }
          else
          {
            fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
              (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
              (unsigned int)L"Returning existing object",
              0,
              35,
              214);
            CEdpCredSvcUserState::AddRef(v10);
            *a3 = v10;
          }
          LeaveCriticalSection(&g_UserStateListLock);
        }
        if ( v9 )
          LocalFree(v9);
      }
    }
    else
    {
      v7 = -2147467261;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147467261, 35, 174);
    }
  }
  else
  {
    v7 = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 35, 173);
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v7,
    35,
    15);
  return v7;
}

```

## disassembly

```asm
0x18009ca50  mov     rax, rsp
0x18009ca53  mov     [rax+10h], rbx
0x18009ca57  mov     [rax+18h], rbp
0x18009ca5b  push    rsi
0x18009ca5c  push    rdi
0x18009ca5d  push    r13
0x18009ca5f  push    r14
0x18009ca61  push    r15
0x18009ca63  sub     rsp, 40h
0x18009ca67  mov     r14, r8
0x18009ca6a  mov     qword ptr [rax+8], 0
0x18009ca72  mov     r15d, edx
0x18009ca75  mov     dword ptr [rax-48h], 0FA5h
0x18009ca7c  mov     r13d, 23h ; '#'
0x18009ca82  lea     r8, sourceString
0x18009ca89  mov     r9d, r13d
0x18009ca8c  lea     rdx, EFS_TRACE_ENTER_EVENT
0x18009ca93  mov     rbx, rcx
0x18009ca96  call    fnEfsLogTrace1Strings
0x18009ca9b  test    r14, r14
0x18009ca9e  jz      short loc_18009CAA5
0x18009caa0  xor     eax, eax
0x18009caa2  mov     [r14], rax
0x18009caa5  test    rbx, rbx
0x18009caa8  jnz     short loc_18009CAC2
0x18009caaa  mov     ebx, 80070057h
0x18009caaf  mov     [rsp+68h+var_48], 0FADh
0x18009cab7  mov     r8d, 80070057h
0x18009cabd  jmp     loc_18009CD30
0x18009cac2  test    r14, r14
0x18009cac5  jnz     short loc_18009CADF
0x18009cac7  mov     ebx, 80004003h
0x18009cacc  mov     [rsp+68h+var_48], 0FAEh
0x18009cad4  mov     r8d, 80004003h
0x18009cada  jmp     loc_18009CD30
0x18009cadf  cmp     cs:?g_EdpSvcInitCounter@@3JA, 0; long g_EdpSvcInitCounter
0x18009cae6  jle     loc_18009CD1D
0x18009caec  mov     edi, 0FB3h
0x18009caf1  lea     r8, sourceString
0x18009caf8  mov     r9d, r13d
0x18009cafb  mov     [rsp+68h+var_48], edi
0x18009caff  lea     rdx, EFS_TRACE_START_EVENT
0x18009cb06  call    fnEfsLogTrace1Strings
0x18009cb0b  lea     rdx, [rsp+68h+pSid1]; void **
0x18009cb10  mov     rcx, rbx; unsigned __int16 *
0x18009cb13  call    ?CheckConvertStringSidToSid@CDplServiceImpl@@CAJPEBGPEAPEAX@Z; CDplServiceImpl::CheckConvertStringSidToSid(ushort const *,void * *)
0x18009cb18  mov     rcx, cs:g_hPublisher
0x18009cb1f  lea     r9, sourceString
0x18009cb26  mov     [rsp+68h+var_38], edi
0x18009cb2a  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18009cb31  mov     [rsp+68h+var_40], r13d
0x18009cb36  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18009cb3d  mov     [rsp+68h+var_48], eax
0x18009cb41  mov     ebx, eax
0x18009cb43  call    fnEfsLogTrace1String1Dword
0x18009cb48  test    eax, eax
0x18009cb4a  js      loc_18009CD08
0x18009cb50  lea     rcx, ?g_UserStateListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009cb57  call    cs:__imp_EnterCriticalSection
0x18009cb5d  mov     rsi, cs:?g_UserStateList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_UserStateList
0x18009cb64  lea     rax, ?g_UserStateList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_UserStateList
0x18009cb6b  mov     rdi, [rsp+68h+pSid1]
0x18009cb70  cmp     rsi, rax
0x18009cb73  jz      short loc_18009CBEC
0x18009cb75  lea     r13, ?g_UserStateList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_UserStateList
0x18009cb7c  lea     rbp, [rsi-50h]
0x18009cb80  mov     rcx, rdi; pSid1
0x18009cb83  mov     rdx, [rbp+68h]; pSid2
0x18009cb87  call    cs:__imp_EqualSid
0x18009cb8d  test    eax, eax
0x18009cb8f  jnz     short loc_18009CB9B
0x18009cb91  mov     rsi, [rsi]
0x18009cb94  xor     ebp, ebp
0x18009cb96  cmp     rsi, r13
0x18009cb99  jnz     short loc_18009CB7C
0x18009cb9b  mov     r13d, 23h ; '#'
0x18009cba1  test    rbp, rbp
0x18009cba4  jz      short loc_18009CBEC
0x18009cba6  mov     rcx, cs:g_hPublisher
0x18009cbad  lea     r9, aReturningExist; "Returning existing object"
0x18009cbb4  mov     [rsp+68h+var_38], 0FD6h
0x18009cbbc  lea     r8, EFS_TRACE_MSG_DWORD_EVENT
0x18009cbc3  mov     [rsp+68h+var_40], r13d
0x18009cbc8  lea     rdx, EFS_TRACE_MSG_DWORD_EVENT
0x18009cbcf  mov     [rsp+68h+var_48], 0
0x18009cbd7  call    fnEfsLogTrace1String1Dword
0x18009cbdc  mov     rcx, rbp; this
0x18009cbdf  call    ?AddRef@CEdpCredSvcUserState@@QEAAJXZ; CEdpCredSvcUserState::AddRef(void)
0x18009cbe4  mov     [r14], rbp
0x18009cbe7  jmp     loc_18009CCF9
0x18009cbec  test    r15d, r15d
0x18009cbef  jnz     short loc_18009CC0C
0x18009cbf1  lea     ebx, [r15+1]
0x18009cbf5  mov     [rsp+68h+var_48], 0FE5h
0x18009cbfd  mov     r8d, ebx
0x18009cc00  lea     rdx, EFS_TRACE_STATUS
0x18009cc07  jmp     loc_18009CCEA
0x18009cc0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009cc13  mov     ecx, 98h; unsigned __int64
0x18009cc18  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18009cc1d  test    rax, rax
0x18009cc20  jz      loc_18009CCD0
0x18009cc26  mov     rcx, rax; this
0x18009cc29  call    ??0CEdpCredSvcUserState@@QEAA@XZ; CEdpCredSvcUserState::CEdpCredSvcUserState(void)
0x18009cc2e  mov     rsi, rax
0x18009cc31  test    rax, rax
0x18009cc34  jz      loc_18009CCD0
0x18009cc3a  lea     rdx, [rax+8]; StringSid
0x18009cc3e  mov     rcx, rdi; Sid
0x18009cc41  call    cs:__imp_ConvertSidToStringSidW
0x18009cc47  test    eax, eax
0x18009cc49  jnz     short loc_18009CC8B
0x18009cc4b  call    cs:__imp_GetLastError
0x18009cc51  mov     ebx, eax
0x18009cc53  test    eax, eax
0x18009cc55  jle     short loc_18009CC60
0x18009cc57  movzx   ebx, ax
0x18009cc5a  or      ebx, 80070000h
0x18009cc60  mov     rcx, cs:g_hPublisher
0x18009cc67  lea     rdx, EFS_TRACE_ERROR
0x18009cc6e  mov     r9d, r13d
0x18009cc71  mov     [rsp+68h+var_48], 0FF3h
0x18009cc79  mov     r8d, ebx
0x18009cc7c  call    fnEfsLogTrace1
0x18009cc81  mov     rcx, rsi; this
0x18009cc84  call    ?Release@CEdpCredSvcUserState@@QEAAJXZ; CEdpCredSvcUserState::Release(void)
0x18009cc89  jmp     short loc_18009CCF9
0x18009cc8b  mov     [rsi+68h], rdi
0x18009cc8f  lea     r9, aReturningNewOb; "Returning new object"
0x18009cc96  mov     rcx, cs:g_hPublisher
0x18009cc9d  lea     r8, EFS_TRACE_MSG_DWORD_EVENT
0x18009cca4  mov     [rsp+68h+var_38], 0FFDh
0x18009ccac  lea     rdx, EFS_TRACE_MSG_DWORD_EVENT
0x18009ccb3  xor     edi, edi
0x18009ccb5  mov     [rsp+68h+var_40], r13d
0x18009ccba  mov     [rsp+68h+var_48], edi
0x18009ccbe  call    fnEfsLogTrace1String1Dword
0x18009ccc3  mov     rcx, rsi; this
0x18009ccc6  call    ?AddRef@CEdpCredSvcUserState@@QEAAJXZ; CEdpCredSvcUserState::AddRef(void)
0x18009cccb  mov     [r14], rsi
0x18009ccce  jmp     short loc_18009CCF9
0x18009ccd0  mov     ebx, 8007000Eh
0x18009ccd5  mov     [rsp+68h+var_48], 0FEFh
0x18009ccdd  mov     r8d, 8007000Eh
0x18009cce3  lea     rdx, EFS_TRACE_ERROR
0x18009ccea  mov     rcx, cs:g_hPublisher
0x18009ccf1  mov     r9d, r13d
0x18009ccf4  call    fnEfsLogTrace1
0x18009ccf9  lea     rcx, ?g_UserStateListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009cd00  call    cs:__imp_LeaveCriticalSection
0x18009cd06  jmp     short loc_18009CD0D
0x18009cd08  mov     rdi, [rsp+68h+pSid1]
0x18009cd0d  test    rdi, rdi
0x18009cd10  jz      short loc_18009CD46
0x18009cd12  mov     rcx, rdi; hMem
0x18009cd15  call    cs:__imp_LocalFree
0x18009cd1b  jmp     short loc_18009CD46
0x18009cd1d  mov     ebx, 8000FFFFh
0x18009cd22  mov     [rsp+68h+var_48], 0FB0h
0x18009cd2a  mov     r8d, 8000FFFFh
0x18009cd30  mov     rcx, cs:g_hPublisher
0x18009cd37  lea     rdx, EFS_TRACE_ERROR
0x18009cd3e  mov     r9d, r13d
0x18009cd41  call    fnEfsLogTrace1
0x18009cd46  mov     rcx, cs:g_hPublisher
0x18009cd4d  lea     r9, sourceString
0x18009cd54  mov     [rsp+68h+var_38], 100Fh
0x18009cd5c  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x18009cd63  mov     [rsp+68h+var_40], r13d
0x18009cd68  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x18009cd6f  mov     [rsp+68h+var_48], ebx
0x18009cd73  call    fnEfsLogTrace1String1Dword
0x18009cd78  lea     r11, [rsp+68h+var_28]
0x18009cd7d  mov     eax, ebx
0x18009cd7f  mov     rbx, [r11+38h]
0x18009cd83  mov     rbp, [r11+40h]
0x18009cd87  mov     rsp, r11
0x18009cd8a  pop     r15
0x18009cd8c  pop     r14
0x18009cd8e  pop     r13
0x18009cd90  pop     rdi
0x18009cd91  pop     rsi
0x18009cd92  retn
```
