# RasSetPerConnectionProxy

- ea: `0x1800b0370`
- end: `0x1800b0583`
- name: `RasSetPerConnectionProxy`
- size: `531`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, ULONG SessionId)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800825cc`

## callees

- `0x180010d10`
- `0x18004e580`
- `0x18004e984`
- `0x18006ae64`
- `0x1800afe28`
- `0x1800b0370`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b0513`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b0513`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800b0466`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800b0466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b03e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b03e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0473`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0563`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b0563`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800b03c4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x1800b03c4`

## pseudocode

```c
__int64 __fastcall RasSetPerConnectionProxy(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        DWORD a5,
        DWORD a6,
        ULONG SessionId)
{
  BOOL v11; // r14d
  int v12; // ecx
  DWORD LastError; // eax
  DWORD v14; // eax
  unsigned int v15; // ebx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned int v19; // eax
  void *phToken; // [rsp+60h] [rbp+8h] BYREF

  phToken = 0;
  DebugInit();
  if ( a1 && *a1 )
  {
    v11 = 0;
    if ( !WTSQueryUserToken(SessionId, &phToken)
      && !(unsigned int)QueryLoggedOnUserForSingleSessionDevice(v12, &phToken) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids, LastError);
        }
      }
    }
    if ( !phToken || NtCurrentTeb()->IsImpersonating )
      goto LABEL_22;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids);
    }
    v11 = ImpersonateLoggedOnUser(phToken);
    if ( v11 )
    {
LABEL_22:
      v19 = RasSetInternetOptions(a1, a2, a3, a4, a5, a6);
      v15 = v19;
      if ( v19
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids, v19);
      }
      if ( v11 )
        RevertToSelf();
    }
    else
    {
      v14 = GetLastError();
      v15 = v14;
      if ( v14 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v17 = 15;
          v18 = v14;
LABEL_33:
          WPP_SF_d(v16[2], v17, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids, v18);
        }
      }
    }
  }
  else
  {
    v15 = 87;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = 12;
      v18 = 87;
      goto LABEL_33;
    }
  }
  if ( phToken )
    CloseHandle(phToken);
  return v15;
}

```

## disassembly

```asm
0x1800b0370  mov     [rsp+arg_8], rbx
0x1800b0375  mov     [rsp+arg_10], rsi
0x1800b037a  push    rdi
0x1800b037b  push    r12
0x1800b037d  push    r13
0x1800b037f  push    r14
0x1800b0381  push    r15
0x1800b0383  sub     rsp, 30h
0x1800b0387  mov     r15, r9
0x1800b038a  mov     [rsp+58h+phToken], 0
0x1800b0393  mov     r12, r8
0x1800b0396  mov     r13, rdx
0x1800b0399  mov     rbx, rcx
0x1800b039c  call    DebugInit
0x1800b03a1  test    rbx, rbx
0x1800b03a4  jz      loc_1800B051B
0x1800b03aa  xor     eax, eax
0x1800b03ac  cmp     ax, [rbx]
0x1800b03af  jz      loc_1800B051B
0x1800b03b5  mov     ecx, [rsp+58h+SessionId]; SessionId
0x1800b03bc  lea     rdx, [rsp+58h+phToken]; phToken
0x1800b03c1  xor     r14d, r14d
0x1800b03c4  call    cs:__imp_WTSQueryUserToken
0x1800b03ca  mov     esi, 800h
0x1800b03cf  lea     rdi, WPP_GLOBAL_Control
0x1800b03d6  test    eax, eax
0x1800b03d8  jnz     short loc_1800B0420
0x1800b03da  lea     rdx, [rsp+58h+phToken]; void **
0x1800b03df  call    ?QueryLoggedOnUserForSingleSessionDevice@@YAHKPEAPEAX@Z; QueryLoggedOnUserForSingleSessionDevice(ulong,void * *)
0x1800b03e4  test    eax, eax
0x1800b03e6  jnz     short loc_1800B0420
0x1800b03e8  call    cs:__imp_GetLastError
0x1800b03ee  test    eax, eax
0x1800b03f0  jz      short loc_1800B0420
0x1800b03f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b03f9  cmp     rcx, rdi
0x1800b03fc  jz      short loc_1800B0420
0x1800b03fe  test    [rcx+1Ch], esi
0x1800b0401  jz      short loc_1800B0420
0x1800b0403  cmp     byte ptr [rcx+19h], 2
0x1800b0407  jb      short loc_1800B0420
0x1800b0409  mov     rcx, [rcx+10h]
0x1800b040d  lea     edx, [r14+0Dh]
0x1800b0411  mov     r9d, eax
0x1800b0414  lea     r8, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids
0x1800b041b  call    WPP_SF_d
0x1800b0420  cmp     [rsp+58h+phToken], r14
0x1800b0425  jz      loc_1800B04B2
0x1800b042b  mov     eax, gs:179Ch
0x1800b0433  test    eax, eax
0x1800b0435  jnz     short loc_1800B04B2
0x1800b0437  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b043e  cmp     rcx, rdi
0x1800b0441  jz      short loc_1800B0461
0x1800b0443  test    [rcx+1Ch], esi
0x1800b0446  jz      short loc_1800B0461
0x1800b0448  cmp     byte ptr [rcx+19h], 4
0x1800b044c  jb      short loc_1800B0461
0x1800b044e  mov     rcx, [rcx+10h]
0x1800b0452  lea     edx, [rax+0Eh]
0x1800b0455  lea     r8, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids
0x1800b045c  call    WPP_SF_
0x1800b0461  mov     rcx, [rsp+58h+phToken]; hToken
0x1800b0466  call    cs:__imp_ImpersonateLoggedOnUser
0x1800b046c  mov     r14d, eax
0x1800b046f  test    eax, eax
0x1800b0471  jnz     short loc_1800B04B2
0x1800b0473  call    cs:__imp_GetLastError
0x1800b0479  mov     ebx, eax
0x1800b047b  test    eax, eax
0x1800b047d  jz      loc_1800B0559
0x1800b0483  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b048a  cmp     rcx, rdi
0x1800b048d  jz      loc_1800B0559
0x1800b0493  test    [rcx+1Ch], esi
0x1800b0496  jz      loc_1800B0559
0x1800b049c  cmp     byte ptr [rcx+19h], 2
0x1800b04a0  jb      loc_1800B0559
0x1800b04a6  lea     edx, [r14+0Fh]
0x1800b04aa  mov     r9d, eax
0x1800b04ad  jmp     loc_1800B0549
0x1800b04b2  mov     eax, [rsp+58h+arg_28]
0x1800b04b9  mov     r9, r15; unsigned __int16 *
0x1800b04bc  mov     [rsp+58h+var_30], eax; unsigned int
0x1800b04c0  mov     r8, r12; unsigned __int16 *
0x1800b04c3  mov     eax, [rsp+58h+arg_20]
0x1800b04ca  mov     rdx, r13; unsigned __int16 *
0x1800b04cd  mov     rcx, rbx; unsigned __int16 *
0x1800b04d0  mov     [rsp+58h+var_38], eax; unsigned int
0x1800b04d4  call    ?RasSetInternetOptions@@YAKPEAG000KK@Z; RasSetInternetOptions(ushort *,ushort *,ushort *,ushort *,ulong,ulong)
0x1800b04d9  mov     ebx, eax
0x1800b04db  test    eax, eax
0x1800b04dd  jz      short loc_1800B050E
0x1800b04df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b04e6  cmp     rcx, rdi
0x1800b04e9  jz      short loc_1800B050E
0x1800b04eb  test    [rcx+1Ch], esi
0x1800b04ee  jz      short loc_1800B050E
0x1800b04f0  cmp     byte ptr [rcx+19h], 2
0x1800b04f4  jb      short loc_1800B050E
0x1800b04f6  mov     rcx, [rcx+10h]
0x1800b04fa  lea     r8, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids
0x1800b0501  mov     edx, 10h
0x1800b0506  mov     r9d, eax
0x1800b0509  call    WPP_SF_d
0x1800b050e  test    r14d, r14d
0x1800b0511  jz      short loc_1800B0559
0x1800b0513  call    cs:__imp_RevertToSelf
0x1800b0519  jmp     short loc_1800B0559
0x1800b051b  mov     ebx, 57h ; 'W'
0x1800b0520  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0527  lea     rdi, WPP_GLOBAL_Control
0x1800b052e  cmp     rcx, rdi
0x1800b0531  jz      short loc_1800B0559
0x1800b0533  mov     esi, 800h
0x1800b0538  test    [rcx+1Ch], esi
0x1800b053b  jz      short loc_1800B0559
0x1800b053d  cmp     byte ptr [rcx+19h], 2
0x1800b0541  jb      short loc_1800B0559
0x1800b0543  lea     edx, [rbx-4Bh]
0x1800b0546  mov     r9d, ebx
0x1800b0549  mov     rcx, [rcx+10h]
0x1800b054d  lea     r8, WPP_9388769838ad322ee42cf89a8fb551ff_Traceguids
0x1800b0554  call    WPP_SF_d
0x1800b0559  mov     rcx, [rsp+58h+phToken]; hObject
0x1800b055e  test    rcx, rcx
0x1800b0561  jz      short loc_1800B0569
0x1800b0563  call    cs:__imp_CloseHandle
0x1800b0569  mov     rsi, [rsp+58h+arg_10]
0x1800b056e  mov     eax, ebx
0x1800b0570  mov     rbx, [rsp+58h+arg_8]
0x1800b0575  add     rsp, 30h
0x1800b0579  pop     r15
0x1800b057b  pop     r14
0x1800b057d  pop     r13
0x1800b057f  pop     r12
0x1800b0581  pop     rdi
0x1800b0582  retn
```
