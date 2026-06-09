# NotifyUILanguageChange

- ea: `0x1800366d0`
- end: `0x18003693d`
- name: `NotifyUILanguageChange`
- size: `621`
- prototype: `BOOL __stdcall(DWORD dwFlags, PCWSTR pcwstrNewLanguage, PCWSTR pcwstrPreviousLanguage, DWORD dwReserved, PDWORD pdwStatusRtrn)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800366d0`
- `0x180036944`
- `0x18006b8d0`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlGetUILanguageInfo` at `0x1800367b4`
- `ntdll!RtlGetUILanguageInfo` at `0x1800367b4`
- `ntdll!EtwEventEnabled` at `0x180036745`
- `ntdll!EtwEventEnabled` at `0x180036879`
- `ntdll!EtwEventEnabled` at `0x1800368ca`
- `ntdll!EtwEventEnabled` at `0x180036745`
- `ntdll!EtwEventEnabled` at `0x180036879`
- `ntdll!EtwEventEnabled` at `0x1800368ca`
- `ntdll!EtwEventUnregister` at `0x180036912`
- `ntdll!EtwEventUnregister` at `0x180036912`
- `ntdll!EtwEventWrite` at `0x18003677d`
- `ntdll!EtwEventWrite` at `0x1800368ae`
- `ntdll!EtwEventWrite` at `0x180036902`
- `ntdll!EtwEventWrite` at `0x18003677d`
- `ntdll!EtwEventWrite` at `0x1800368ae`
- `ntdll!EtwEventWrite` at `0x180036902`
- `ntdll!EtwEventRegister` at `0x180036721`
- `ntdll!EtwEventRegister` at `0x180036721`
- `ntdll!RtlNtStatusToDosError` at `0x18003683d`
- `ntdll!RtlNtStatusToDosError` at `0x18003683d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003684b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003684b`

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
0x1800366d0  push    rbp
0x1800366d2  push    rbx
0x1800366d3  push    rsi
0x1800366d4  push    rdi
0x1800366d5  push    r12
0x1800366d7  push    r14
0x1800366d9  push    r15
0x1800366db  mov     rbp, rsp
0x1800366de  sub     rsp, 60h
0x1800366e2  mov     rax, cs:__security_cookie
0x1800366e9  xor     rax, rsp
0x1800366ec  mov     [rbp+var_8], rax
0x1800366f0  mov     rdi, [rbp+pdwStatusRtrn]
0x1800366f4  mov     r15d, r9d
0x1800366f7  mov     r12, r8
0x1800366fa  mov     [rbp+var_30], 0
0x180036701  mov     rsi, rdx
0x180036704  lea     r9, [rbp+var_28]
0x180036708  mov     ebx, ecx
0x18003670a  xor     r14d, r14d
0x18003670d  xor     r8d, r8d
0x180036710  mov     [rbp+var_28], r14
0x180036714  xor     edx, edx
0x180036716  mov     [rbp+var_20], r14d
0x18003671a  lea     rcx, MUI_ETW_PROVIDER
0x180036721  call    cs:__imp_EtwEventRegister
0x180036728  nop     dword ptr [rax+rax+00h]
0x18003672d  test    eax, eax
0x18003672f  jz      short loc_180036735
0x180036731  mov     [rbp+var_28], r14
0x180036735  mov     rcx, [rbp+var_28]
0x180036739  test    rcx, rcx
0x18003673c  jz      short loc_180036789
0x18003673e  lea     rdx, MUI_ETW_EVENT_NOTIFY_START
0x180036745  call    cs:__imp_EtwEventEnabled
0x18003674c  nop     dword ptr [rax+rax+00h]
0x180036751  test    al, al
0x180036753  jz      short loc_180036789
0x180036755  mov     rcx, [rbp+var_28]
0x180036759  lea     rax, aNotifyuilangua_0; "NotifyUILanguageChange API"
0x180036760  lea     r9, [rbp+var_18]
0x180036764  mov     [rbp+var_18], rax
0x180036768  mov     r8d, 1
0x18003676e  mov     [rbp+var_10], 36h ; '6'
0x180036776  lea     rdx, MUI_ETW_EVENT_NOTIFY_START
0x18003677d  call    cs:__imp_EtwEventWrite
0x180036784  nop     dword ptr [rax+rax+00h]
0x180036789  test    rsi, rsi
0x18003678c  jz      short loc_1800367EE
0x18003678e  mov     eax, ebx
0x180036790  mov     rdx, rsi
0x180036793  and     eax, 100h
0x180036798  neg     eax
0x18003679a  lea     rax, [rbp+var_20]
0x18003679e  sbb     ecx, ecx
0x1800367a0  mov     [rsp+60h+var_40], rax
0x1800367a5  and     ecx, 0FFFFFFFCh
0x1800367a8  xor     r9d, r9d
0x1800367ab  add     ecx, 88h
0x1800367b1  xor     r8d, r8d
0x1800367b4  call    cs:__imp_RtlGetUILanguageInfo
0x1800367bb  nop     dword ptr [rax+rax+00h]
0x1800367c0  mov     [rbp+var_30], eax
0x1800367c3  test    bl, 4
0x1800367c6  jz      short loc_1800367D9
0x1800367c8  cmp     eax, 0C0000034h
0x1800367cd  jz      short loc_1800367DD
0x1800367cf  mov     eax, 0C000000Dh
0x1800367d4  mov     [rbp+var_30], eax
0x1800367d7  jmp     short loc_18003683B
0x1800367d9  test    eax, eax
0x1800367db  js      short loc_1800367CF
0x1800367dd  test    bl, 8
0x1800367e0  setnz   cl
0x1800367e3  test    byte ptr [rbp+var_20], 4
0x1800367e7  setnz   al
0x1800367ea  test    al, cl
0x1800367ec  jnz     short loc_1800367CF
0x1800367ee  mov     rax, [rbp+var_28]
0x1800367f2  mov     r9d, r15d
0x1800367f5  mov     [rsp+60h+var_38], rdi
0x1800367fa  mov     r8, r12
0x1800367fd  mov     rdx, rsi
0x180036800  mov     [rsp+60h+var_40], rax
0x180036805  mov     ecx, ebx
0x180036807  call    Internal_NotifyUILanguageChange
0x18003680c  mov     [rbp+var_30], eax
0x18003680f  test    eax, eax
0x180036811  js      short loc_18003683B
0x180036813  test    bl, 8
0x180036816  jz      short loc_180036835
0x180036818  mov     r9, [rbp+var_28]
0x18003681c  mov     r8d, r15d
0x18003681f  mov     rdx, rsi
0x180036822  mov     [rsp+60h+var_40], rdi
0x180036827  mov     ecx, ebx
0x180036829  call    Internal_InvokeSwitchCallbacksOnINIT
0x18003682e  mov     [rbp+var_30], eax
0x180036831  test    eax, eax
0x180036833  js      short loc_18003683B
0x180036835  mov     r14d, 1
0x18003683b  mov     ecx, eax; Status
0x18003683d  call    cs:__imp_RtlNtStatusToDosError
0x180036844  nop     dword ptr [rax+rax+00h]
0x180036849  mov     ecx, eax; dwErrCode
0x18003684b  call    cs:__imp_SetLastError
0x180036852  nop     dword ptr [rax+rax+00h]
0x180036857  mov     eax, [rbp+var_30]
0x18003685a  test    eax, eax
0x18003685c  jz      short loc_1800368BA
0x18003685e  test    rdi, rdi
0x180036861  jz      short loc_180036865
0x180036863  mov     [rdi], eax
0x180036865  mov     rcx, [rbp+var_28]
0x180036869  test    rcx, rcx
0x18003686c  jz      loc_180036912
0x180036872  lea     rdx, MUI_ETW_EVENT_NOTIFY_ERROR
0x180036879  call    cs:__imp_EtwEventEnabled
0x180036880  nop     dword ptr [rax+rax+00h]
0x180036885  test    al, al
0x180036887  jz      short loc_1800368BA
0x180036889  mov     rcx, [rbp+var_28]
0x18003688d  lea     rax, [rbp+var_30]
0x180036891  lea     r9, [rbp+var_18]
0x180036895  mov     [rbp+var_18], rax
0x180036899  mov     r8d, 1
0x18003689f  mov     [rbp+var_10], 4
0x1800368a7  lea     rdx, MUI_ETW_EVENT_NOTIFY_ERROR
0x1800368ae  call    cs:__imp_EtwEventWrite
0x1800368b5  nop     dword ptr [rax+rax+00h]
0x1800368ba  mov     rcx, [rbp+var_28]
0x1800368be  test    rcx, rcx
0x1800368c1  jz      short loc_180036912
0x1800368c3  lea     rdx, MUI_ETW_EVENT_NOTIFY_END
0x1800368ca  call    cs:__imp_EtwEventEnabled
0x1800368d1  nop     dword ptr [rax+rax+00h]
0x1800368d6  mov     rcx, [rbp+var_28]
0x1800368da  test    al, al
0x1800368dc  jz      short loc_180036912
0x1800368de  lea     rax, aNotifyuilangua_0; "NotifyUILanguageChange API"
0x1800368e5  mov     [rbp+var_10], 36h ; '6'
0x1800368ed  lea     r9, [rbp+var_18]
0x1800368f1  mov     [rbp+var_18], rax
0x1800368f5  mov     r8d, 1
0x1800368fb  lea     rdx, MUI_ETW_EVENT_NOTIFY_END
0x180036902  call    cs:__imp_EtwEventWrite
0x180036909  nop     dword ptr [rax+rax+00h]
0x18003690e  mov     rcx, [rbp+var_28]
0x180036912  call    cs:__imp_EtwEventUnregister
0x180036919  nop     dword ptr [rax+rax+00h]
0x18003691e  mov     eax, r14d
0x180036921  mov     rcx, [rbp+var_8]
0x180036925  xor     rcx, rsp; StackCookie
0x180036928  call    __security_check_cookie
0x18003692d  add     rsp, 60h
0x180036931  pop     r15
0x180036933  pop     r14
0x180036935  pop     r12
0x180036937  pop     rdi
0x180036938  pop     rsi
0x180036939  pop     rbx
0x18003693a  pop     rbp
0x18003693b  retn
```
