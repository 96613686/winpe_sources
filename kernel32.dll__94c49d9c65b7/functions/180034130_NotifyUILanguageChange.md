# NotifyUILanguageChange

- ea: `0x180034130`
- end: `0x18003435a`
- name: `NotifyUILanguageChange`
- size: `554`
- prototype: `BOOL __stdcall(DWORD dwFlags, PCWSTR pcwstrNewLanguage, PCWSTR pcwstrPreviousLanguage, DWORD dwReserved, PDWORD pdwStatusRtrn)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180034130`
- `0x180034360`
- `0x180064bb8`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlGetUILanguageInfo` at `0x180034202`
- `ntdll!RtlGetUILanguageInfo` at `0x180034202`
- `ntdll!EtwEventEnabled` at `0x18003419f`
- `ntdll!EtwEventEnabled` at `0x1800342b5`
- `ntdll!EtwEventEnabled` at `0x1800342fa`
- `ntdll!EtwEventEnabled` at `0x18003419f`
- `ntdll!EtwEventEnabled` at `0x1800342b5`
- `ntdll!EtwEventEnabled` at `0x1800342fa`
- `ntdll!EtwEventUnregister` at `0x180034336`
- `ntdll!EtwEventUnregister` at `0x180034336`
- `ntdll!EtwEventWrite` at `0x1800341d1`
- `ntdll!EtwEventWrite` at `0x1800342e4`
- `ntdll!EtwEventWrite` at `0x18003432c`
- `ntdll!EtwEventWrite` at `0x1800341d1`
- `ntdll!EtwEventWrite` at `0x1800342e4`
- `ntdll!EtwEventWrite` at `0x18003432c`
- `ntdll!EtwEventRegister` at `0x180034181`
- `ntdll!EtwEventRegister` at `0x180034181`
- `ntdll!RtlNtStatusToDosError` at `0x180034285`
- `ntdll!RtlNtStatusToDosError` at `0x180034285`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003428d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003428d`

## pseudocode

```c
BOOL __stdcall NotifyUILanguageChange(
        DWORD dwFlags,
        PCWSTR pcwstrNewLanguage,
        PCWSTR pcwstrPreviousLanguage,
        DWORD dwReserved,
        PDWORD pdwStatusRtrn)
{
  BOOL v9; // r14d
  int UILanguageInfo; // eax
  NTSTATUS v11; // eax
  ULONG v12; // eax
  DWORD v14; // [rsp+30h] [rbp-30h] BYREF
  __int64 v15; // [rsp+38h] [rbp-28h] BYREF
  int v16; // [rsp+40h] [rbp-20h] BYREF
  DWORD *v17; // [rsp+48h] [rbp-18h] BYREF
  __int64 v18; // [rsp+50h] [rbp-10h]

  v14 = 0;
  v9 = 0;
  v15 = 0;
  v16 = 0;
  if ( (unsigned int)EtwEventRegister(MUI_ETW_PROVIDER, 0, 0, &v15) )
    v15 = 0;
  if ( v15 && (unsigned __int8)EtwEventEnabled(v15, MUI_ETW_EVENT_NOTIFY_START) )
  {
    v17 = (DWORD *)L"NotifyUILanguageChange API";
    v18 = 54;
    EtwEventWrite(v15, MUI_ETW_EVENT_NOTIFY_START, 1, &v17);
  }
  if ( pcwstrNewLanguage )
  {
    UILanguageInfo = RtlGetUILanguageInfo((dwFlags & 0x100) != 0 ? 132 : 136, pcwstrNewLanguage, 0, 0, &v16);
    v14 = UILanguageInfo;
    if ( (dwFlags & 4) != 0 )
    {
      if ( UILanguageInfo != -1073741772 )
      {
LABEL_9:
        v11 = -1073741811;
        v14 = -1073741811;
        goto LABEL_16;
      }
    }
    else if ( UILanguageInfo < 0 )
    {
      goto LABEL_9;
    }
    if ( (dwFlags & 8) != 0 && (v16 & 4) != 0 )
      goto LABEL_9;
  }
  v11 = Internal_NotifyUILanguageChange(
          dwFlags,
          pcwstrNewLanguage,
          (WCHAR *)pcwstrPreviousLanguage,
          dwReserved,
          v15,
          (__int64)pdwStatusRtrn);
  v14 = v11;
  if ( v11 >= 0 )
  {
    if ( (dwFlags & 8) == 0
      || (v11 = Internal_InvokeSwitchCallbacksOnINIT(
                  dwFlags,
                  (_DWORD)pcwstrNewLanguage,
                  dwReserved,
                  v15,
                  (__int64)pdwStatusRtrn),
          v14 = v11,
          v11 >= 0) )
    {
      v9 = 1;
    }
  }
LABEL_16:
  v12 = RtlNtStatusToDosError(v11);
  SetLastError(v12);
  if ( !v14 )
  {
LABEL_22:
    if ( v15 && (unsigned __int8)EtwEventEnabled(v15, MUI_ETW_EVENT_NOTIFY_END) )
    {
      v18 = 54;
      v17 = (DWORD *)L"NotifyUILanguageChange API";
      EtwEventWrite(v15, MUI_ETW_EVENT_NOTIFY_END, 1, &v17);
    }
    goto LABEL_25;
  }
  if ( pdwStatusRtrn )
    *pdwStatusRtrn = v14;
  if ( v15 )
  {
    if ( (unsigned __int8)EtwEventEnabled(v15, MUI_ETW_EVENT_NOTIFY_ERROR) )
    {
      v17 = &v14;
      v18 = 4;
      EtwEventWrite(v15, MUI_ETW_EVENT_NOTIFY_ERROR, 1, &v17);
    }
    goto LABEL_22;
  }
LABEL_25:
  EtwEventUnregister();
  return v9;
}

```

## disassembly

```asm
0x180034130  push    rbp
0x180034132  push    rbx
0x180034133  push    rsi
0x180034134  push    rdi
0x180034135  push    r12
0x180034137  push    r14
0x180034139  push    r15
0x18003413b  mov     rbp, rsp
0x18003413e  sub     rsp, 60h
0x180034142  mov     rax, cs:__security_cookie
0x180034149  xor     rax, rsp
0x18003414c  mov     [rbp+var_8], rax
0x180034150  mov     rdi, [rbp+pdwStatusRtrn]
0x180034154  mov     r15d, r9d
0x180034157  mov     r12, r8
0x18003415a  mov     [rbp+var_30], 0
0x180034161  mov     rsi, rdx
0x180034164  lea     r9, [rbp+var_28]
0x180034168  mov     ebx, ecx
0x18003416a  xor     r14d, r14d
0x18003416d  xor     r8d, r8d
0x180034170  mov     [rbp+var_28], r14
0x180034174  xor     edx, edx
0x180034176  mov     [rbp+var_20], r14d
0x18003417a  lea     rcx, MUI_ETW_PROVIDER
0x180034181  call    cs:__imp_EtwEventRegister
0x180034187  test    eax, eax
0x180034189  jz      short loc_18003418F
0x18003418b  mov     [rbp+var_28], r14
0x18003418f  mov     rcx, [rbp+var_28]
0x180034193  test    rcx, rcx
0x180034196  jz      short loc_1800341D7
0x180034198  lea     rdx, MUI_ETW_EVENT_NOTIFY_START
0x18003419f  call    cs:__imp_EtwEventEnabled
0x1800341a5  test    al, al
0x1800341a7  jz      short loc_1800341D7
0x1800341a9  mov     rcx, [rbp+var_28]
0x1800341ad  lea     rax, aNotifyuilangua_0; "NotifyUILanguageChange API"
0x1800341b4  lea     r9, [rbp+var_18]
0x1800341b8  mov     [rbp+var_18], rax
0x1800341bc  mov     r8d, 1
0x1800341c2  mov     [rbp+var_10], 36h ; '6'
0x1800341ca  lea     rdx, MUI_ETW_EVENT_NOTIFY_START
0x1800341d1  call    cs:__imp_EtwEventWrite
0x1800341d7  test    rsi, rsi
0x1800341da  jz      short loc_180034236
0x1800341dc  mov     eax, ebx
0x1800341de  mov     rdx, rsi
0x1800341e1  and     eax, 100h
0x1800341e6  neg     eax
0x1800341e8  lea     rax, [rbp+var_20]
0x1800341ec  sbb     ecx, ecx
0x1800341ee  mov     [rsp+60h+var_40], rax
0x1800341f3  and     ecx, 0FFFFFFFCh
0x1800341f6  xor     r9d, r9d
0x1800341f9  add     ecx, 88h
0x1800341ff  xor     r8d, r8d
0x180034202  call    cs:__imp_RtlGetUILanguageInfo
0x180034208  mov     [rbp+var_30], eax
0x18003420b  test    bl, 4
0x18003420e  jz      short loc_180034221
0x180034210  cmp     eax, 0C0000034h
0x180034215  jz      short loc_180034225
0x180034217  mov     eax, 0C000000Dh
0x18003421c  mov     [rbp+var_30], eax
0x18003421f  jmp     short loc_180034283
0x180034221  test    eax, eax
0x180034223  js      short loc_180034217
0x180034225  test    bl, 8
0x180034228  setnz   cl
0x18003422b  test    byte ptr [rbp+var_20], 4
0x18003422f  setnz   al
0x180034232  test    al, cl
0x180034234  jnz     short loc_180034217
0x180034236  mov     rax, [rbp+var_28]
0x18003423a  mov     r9d, r15d
0x18003423d  mov     [rsp+60h+var_38], rdi
0x180034242  mov     r8, r12
0x180034245  mov     rdx, rsi
0x180034248  mov     [rsp+60h+var_40], rax
0x18003424d  mov     ecx, ebx
0x18003424f  call    Internal_NotifyUILanguageChange
0x180034254  mov     [rbp+var_30], eax
0x180034257  test    eax, eax
0x180034259  js      short loc_180034283
0x18003425b  test    bl, 8
0x18003425e  jz      short loc_18003427D
0x180034260  mov     r9, [rbp+var_28]
0x180034264  mov     r8d, r15d
0x180034267  mov     rdx, rsi
0x18003426a  mov     [rsp+60h+var_40], rdi
0x18003426f  mov     ecx, ebx
0x180034271  call    Internal_InvokeSwitchCallbacksOnINIT
0x180034276  mov     [rbp+var_30], eax
0x180034279  test    eax, eax
0x18003427b  js      short loc_180034283
0x18003427d  mov     r14d, 1
0x180034283  mov     ecx, eax; Status
0x180034285  call    cs:__imp_RtlNtStatusToDosError
0x18003428b  mov     ecx, eax; dwErrCode
0x18003428d  call    cs:__imp_SetLastError
0x180034293  mov     eax, [rbp+var_30]
0x180034296  test    eax, eax
0x180034298  jz      short loc_1800342EA
0x18003429a  test    rdi, rdi
0x18003429d  jz      short loc_1800342A1
0x18003429f  mov     [rdi], eax
0x1800342a1  mov     rcx, [rbp+var_28]
0x1800342a5  test    rcx, rcx
0x1800342a8  jz      loc_180034336
0x1800342ae  lea     rdx, MUI_ETW_EVENT_NOTIFY_ERROR
0x1800342b5  call    cs:__imp_EtwEventEnabled
0x1800342bb  test    al, al
0x1800342bd  jz      short loc_1800342EA
0x1800342bf  mov     rcx, [rbp+var_28]
0x1800342c3  lea     rax, [rbp+var_30]
0x1800342c7  lea     r9, [rbp+var_18]
0x1800342cb  mov     [rbp+var_18], rax
0x1800342cf  mov     r8d, 1
0x1800342d5  mov     [rbp+var_10], 4
0x1800342dd  lea     rdx, MUI_ETW_EVENT_NOTIFY_ERROR
0x1800342e4  call    cs:__imp_EtwEventWrite
0x1800342ea  mov     rcx, [rbp+var_28]
0x1800342ee  test    rcx, rcx
0x1800342f1  jz      short loc_180034336
0x1800342f3  lea     rdx, MUI_ETW_EVENT_NOTIFY_END
0x1800342fa  call    cs:__imp_EtwEventEnabled
0x180034300  mov     rcx, [rbp+var_28]
0x180034304  test    al, al
0x180034306  jz      short loc_180034336
0x180034308  lea     rax, aNotifyuilangua_0; "NotifyUILanguageChange API"
0x18003430f  mov     [rbp+var_10], 36h ; '6'
0x180034317  lea     r9, [rbp+var_18]
0x18003431b  mov     [rbp+var_18], rax
0x18003431f  mov     r8d, 1
0x180034325  lea     rdx, MUI_ETW_EVENT_NOTIFY_END
0x18003432c  call    cs:__imp_EtwEventWrite
0x180034332  mov     rcx, [rbp+var_28]
0x180034336  call    cs:__imp_EtwEventUnregister
0x18003433c  mov     eax, r14d
0x18003433f  mov     rcx, [rbp+var_8]
0x180034343  xor     rcx, rsp; StackCookie
0x180034346  call    __security_check_cookie
0x18003434b  add     rsp, 60h
0x18003434f  pop     r15
0x180034351  pop     r14
0x180034353  pop     r12
0x180034355  pop     rdi
0x180034356  pop     rsi
0x180034357  pop     rbx
0x180034358  pop     rbp
0x180034359  retn
```
