# CDplUser::Initialize(ushort const *)

- ea: `0x1800b3f90`
- end: `0x1800b4207`
- name: `?Initialize@CDplUser@@AEAAJPEBG@Z`
- size: `631`
- prototype: `__int64 __fastcall(PVOID pv, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800895e8`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180088cf8`
- `0x1800b3f90`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b40a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b40e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4120`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b40a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b40e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4120`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b41bc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b41bc`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800b40d8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800b4112`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800b40d8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800b4112`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b4195`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b41a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b4195`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b41a5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b409c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b409c`

## pseudocode

```c
__int64 __fastcall CDplUser::Initialize(char *pv, const unsigned __int16 *a2)
{
  PSID v2; // rbp
  struct _TP_TIMER *ThreadpoolTimer; // r14
  __int64 v6; // rcx
  _QWORD *v7; // rsi
  unsigned int v8; // ebx
  int v9; // eax
  signed int v10; // eax
  int v11; // r8d
  signed int v12; // eax
  PTP_TIMER v13; // rcx
  signed int LastError; // eax
  char v16; // [rsp+20h] [rbp-48h]
  LPWSTR StringSid; // [rsp+70h] [rbp+8h] BYREF
  PSID Sid; // [rsp+80h] [rbp+18h] BYREF

  v2 = 0;
  Sid = 0;
  StringSid = 0;
  ThreadpoolTimer = 0;
  fnEfsLogTrace1Strings((_DWORD)pv, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 40, 228);
  v7 = pv + 112;
  if ( *(_OWORD *)(pv + 104) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  if ( *((_QWORD *)pv + 13) || *v7 || *((_QWORD *)pv + 34) || *((_QWORD *)pv + 41) || *((_QWORD *)pv + 40) != -1 )
  {
    v8 = -2147418113;
    v16 = -17;
    v11 = -2147418113;
LABEL_24:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v11, 40, v16);
    goto LABEL_25;
  }
  fnEfsLogTrace1Strings(v6, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 243);
  v8 = CDplServiceImpl::CheckConvertStringSidToSid(a2, &Sid);
  v9 = fnEfsLogTrace1String1Dword(
         g_hPublisher,
         (unsigned int)EFS_TRACE_COMPLETE_EVENT,
         (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
         (unsigned int)&sourceString,
         v8,
         40,
         243);
  v2 = Sid;
  if ( v9 >= 0 )
  {
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(CDplUser::_KeyDropTimerCallback, pv, 0);
      if ( ThreadpoolTimer )
      {
        v13 = CreateThreadpoolTimer(CDplUser::_RecoveryBackupCallback, pv, 0);
        if ( v13 )
        {
          *((_QWORD *)pv + 13) = StringSid;
          StringSid = 0;
          *v7 = v2;
          *((_QWORD *)pv + 34) = ThreadpoolTimer;
          *((_QWORD *)pv + 41) = v13;
          goto LABEL_31;
        }
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        v16 = 11;
      }
      else
      {
        v12 = GetLastError();
        v8 = v12;
        if ( v12 > 0 )
          v8 = (unsigned __int16)v12 | 0x80070000;
        v16 = 1;
      }
    }
    else
    {
      v10 = GetLastError();
      v8 = v10;
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      v16 = -9;
    }
    v11 = v8;
    goto LABEL_24;
  }
LABEL_25:
  if ( v2 )
    LocalFree(v2);
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( ThreadpoolTimer )
    CloseThreadpoolTimer(ThreadpoolTimer);
LABEL_31:
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v8,
    40,
    52);
  return v8;
}

```

## disassembly

```asm
0x1800b3f90  mov     rax, rsp
0x1800b3f93  mov     [rax+10h], rbx
0x1800b3f97  push    rbp
0x1800b3f98  push    rsi
0x1800b3f99  push    rdi
0x1800b3f9a  push    r12
0x1800b3f9c  push    r14
0x1800b3f9e  sub     rsp, 40h
0x1800b3fa2  xor     ebp, ebp
0x1800b3fa4  mov     dword ptr [rax-48h], 0E4h
0x1800b3fab  mov     rbx, rdx
0x1800b3fae  mov     [rax+18h], rbp
0x1800b3fb2  lea     r8, sourceString
0x1800b3fb9  mov     [rax+8], rbp
0x1800b3fbd  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800b3fc4  mov     rdi, rcx
0x1800b3fc7  lea     r12d, [rbp+28h]
0x1800b3fcb  xor     r14d, r14d
0x1800b3fce  mov     r9d, r12d
0x1800b3fd1  call    fnEfsLogTrace1Strings
0x1800b3fd6  lea     rsi, [rdi+70h]
0x1800b3fda  cmp     [rdi+68h], rbp
0x1800b3fde  jnz     short loc_1800B3FE5
0x1800b3fe0  cmp     [rsi], rbp
0x1800b3fe3  jz      short loc_1800B3FEA
0x1800b3fe5  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "m_pwszUserSid == NULL && m_pUserSid == NULL")
0x1800b3fea  cmp     [rdi+68h], rbp
0x1800b3fee  jnz     loc_1800B4164
0x1800b3ff4  cmp     [rsi], rbp
0x1800b3ff7  jnz     loc_1800B4164
0x1800b3ffd  cmp     [rdi+110h], rbp
0x1800b4004  jnz     loc_1800B4164
0x1800b400a  cmp     [rdi+148h], rbp
0x1800b4011  jnz     loc_1800B4164
0x1800b4017  cmp     qword ptr [rdi+140h], 0FFFFFFFFFFFFFFFFh
0x1800b401f  jnz     loc_1800B4164
0x1800b4025  mov     ebp, 0F3h
0x1800b402a  lea     r8, sourceString
0x1800b4031  mov     r9d, r12d
0x1800b4034  mov     dword ptr [rsp+68h+var_48], ebp
0x1800b4038  lea     rdx, EFS_TRACE_START_EVENT
0x1800b403f  call    fnEfsLogTrace1Strings
0x1800b4044  lea     rdx, [rsp+68h+Sid]; void **
0x1800b404c  mov     rcx, rbx; unsigned __int16 *
0x1800b404f  call    ?CheckConvertStringSidToSid@CDplServiceImpl@@CAJPEBGPEAPEAX@Z; CDplServiceImpl::CheckConvertStringSidToSid(ushort const *,void * *)
0x1800b4054  mov     rcx, cs:g_hPublisher
0x1800b405b  lea     r9, sourceString
0x1800b4062  mov     [rsp+68h+var_38], ebp
0x1800b4066  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800b406d  mov     [rsp+68h+var_40], r12d
0x1800b4072  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800b4079  mov     dword ptr [rsp+68h+var_48], eax
0x1800b407d  mov     ebx, eax
0x1800b407f  call    fnEfsLogTrace1String1Dword
0x1800b4084  mov     rbp, [rsp+68h+Sid]
0x1800b408c  test    eax, eax
0x1800b408e  js      loc_1800B418D
0x1800b4094  lea     rdx, [rsp+68h+StringSid]; StringSid
0x1800b4099  mov     rcx, rbp; Sid
0x1800b409c  call    cs:__imp_ConvertSidToStringSidW
0x1800b40a2  test    eax, eax
0x1800b40a4  jnz     short loc_1800B40CB
0x1800b40a6  call    cs:__imp_GetLastError
0x1800b40ac  mov     ebx, eax
0x1800b40ae  test    eax, eax
0x1800b40b0  jle     short loc_1800B40BB
0x1800b40b2  movzx   ebx, ax
0x1800b40b5  or      ebx, 80070000h
0x1800b40bb  mov     dword ptr [rsp+68h+var_48], 0F7h
0x1800b40c3  mov     r8d, ebx
0x1800b40c6  jmp     loc_1800B4177
0x1800b40cb  xor     r8d, r8d; pcbe
0x1800b40ce  lea     rcx, ?_KeyDropTimerCallback@CDplUser@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800b40d5  mov     rdx, rdi; pv
0x1800b40d8  call    cs:__imp_CreateThreadpoolTimer
0x1800b40de  mov     r14, rax
0x1800b40e1  test    rax, rax
0x1800b40e4  jnz     short loc_1800B4105
0x1800b40e6  call    cs:__imp_GetLastError
0x1800b40ec  mov     ebx, eax
0x1800b40ee  test    eax, eax
0x1800b40f0  jle     short loc_1800B40FB
0x1800b40f2  movzx   ebx, ax
0x1800b40f5  or      ebx, 80070000h
0x1800b40fb  mov     dword ptr [rsp+68h+var_48], 101h
0x1800b4103  jmp     short loc_1800B40C3
0x1800b4105  xor     r8d, r8d; pcbe
0x1800b4108  lea     rcx, ?_RecoveryBackupCallback@CDplUser@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800b410f  mov     rdx, rdi; pv
0x1800b4112  call    cs:__imp_CreateThreadpoolTimer
0x1800b4118  mov     rcx, rax
0x1800b411b  test    rax, rax
0x1800b411e  jnz     short loc_1800B413F
0x1800b4120  call    cs:__imp_GetLastError
0x1800b4126  mov     ebx, eax
0x1800b4128  test    eax, eax
0x1800b412a  jle     short loc_1800B4135
0x1800b412c  movzx   ebx, ax
0x1800b412f  or      ebx, 80070000h
0x1800b4135  mov     dword ptr [rsp+68h+var_48], 10Bh
0x1800b413d  jmp     short loc_1800B40C3
0x1800b413f  mov     rax, [rsp+68h+StringSid]
0x1800b4144  mov     [rdi+68h], rax
0x1800b4148  mov     [rsp+68h+StringSid], 0
0x1800b4151  mov     [rsi], rbp
0x1800b4154  mov     [rdi+110h], r14
0x1800b415b  mov     [rdi+148h], rcx
0x1800b4162  jmp     short loc_1800B41C2
0x1800b4164  mov     ebx, 8000FFFFh
0x1800b4169  mov     dword ptr [rsp+68h+var_48], 0EFh
0x1800b4171  mov     r8d, 8000FFFFh
0x1800b4177  mov     rcx, cs:g_hPublisher
0x1800b417e  lea     rdx, EFS_TRACE_ERROR
0x1800b4185  mov     r9d, r12d
0x1800b4188  call    fnEfsLogTrace1
0x1800b418d  test    rbp, rbp
0x1800b4190  jz      short loc_1800B419B
0x1800b4192  mov     rcx, rbp; hMem
0x1800b4195  call    cs:__imp_LocalFree
0x1800b419b  mov     rcx, [rsp+68h+StringSid]; hMem
0x1800b41a0  test    rcx, rcx
0x1800b41a3  jz      short loc_1800B41B4
0x1800b41a5  call    cs:__imp_LocalFree
0x1800b41ab  mov     [rsp+68h+StringSid], 0
0x1800b41b4  test    r14, r14
0x1800b41b7  jz      short loc_1800B41C2
0x1800b41b9  mov     rcx, r14; pti
0x1800b41bc  call    cs:__imp_CloseThreadpoolTimer
0x1800b41c2  mov     rcx, cs:g_hPublisher
0x1800b41c9  lea     r9, sourceString
0x1800b41d0  mov     [rsp+68h+var_38], 134h
0x1800b41d8  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x1800b41df  mov     [rsp+68h+var_40], r12d
0x1800b41e4  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x1800b41eb  mov     dword ptr [rsp+68h+var_48], ebx
0x1800b41ef  call    fnEfsLogTrace1String1Dword
0x1800b41f4  mov     eax, ebx
0x1800b41f6  mov     rbx, [rsp+68h+arg_8]
0x1800b41fb  add     rsp, 40h
0x1800b41ff  pop     r14
0x1800b4201  pop     r12
0x1800b4203  pop     rdi
0x1800b4204  pop     rsi
0x1800b4205  pop     rbp
0x1800b4206  retn
```
