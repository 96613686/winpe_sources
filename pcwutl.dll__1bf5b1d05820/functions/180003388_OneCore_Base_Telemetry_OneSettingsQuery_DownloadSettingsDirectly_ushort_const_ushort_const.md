# OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsDirectly(ushort const *,ushort const *)

- ea: `0x180003388`
- end: `0x180003544`
- name: `?DownloadSettingsDirectly@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG0@Z`
- size: `444`
- prototype: `__int64 __fastcall(void **this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800055f4`

## callees

- `0x180003388`
- `0x180003770`
- `0x180004a2c`
- `0x180004d68`
- `0x180006c40`
- `0x1800191f0`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x1800034af`
- `ADVAPI32!RevertToSelf` at `0x1800034d2`
- `ADVAPI32!RevertToSelf` at `0x1800034af`
- `ADVAPI32!RevertToSelf` at `0x1800034d2`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180003421`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x180003421`
- `KERNEL32!GetLastError` at `0x1800034dc`
- `KERNEL32!GetLastError` at `0x1800034eb`
- `KERNEL32!GetLastError` at `0x18000350c`
- `KERNEL32!GetLastError` at `0x1800034dc`
- `KERNEL32!GetLastError` at `0x1800034eb`
- `KERNEL32!GetLastError` at `0x18000350c`
- `KERNEL32!ExitProcess` at `0x1800034e4`
- `KERNEL32!ExitProcess` at `0x180003514`
- `KERNEL32!ExitProcess` at `0x1800034e4`
- `KERNEL32!ExitProcess` at `0x180003514`
- `WINHTTP!WinHttpSetCredentials` at `0x180003490`
- `WINHTTP!WinHttpSetCredentials` at `0x180003490`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::DownloadSettingsDirectly(
        void **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v4; // rdx
  OneCore::Base::Telemetry::OneSettingsQuery *v5; // rcx
  bool v7; // si
  __int64 v8; // rdi
  signed int UserSession; // ebx
  UINT v10; // eax
  signed int v11; // eax
  UINT LastError; // eax
  LPCWSTR pwszPassword; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v14; // [rsp+30h] [rbp-D0h]
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hToken; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pwszUserName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v18[264]; // [rsp+260h] [rbp+160h] BYREF

  hToken = 0;
  v18[0] = 0;
  pwszUserName[0] = 0;
  v15 = 0;
  if ( IsWindowsVersionOrGreaterEx((unsigned __int16)this, (unsigned __int16)a2, (unsigned __int16)a3, 0x4F7Cu) )
    return 2147500037LL;
  v7 = 0;
  v8 = 0;
  while ( 1 )
  {
    if ( v8 == 1 )
    {
      UserSession = OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(v5, &hToken, &v15);
      if ( UserSession < 0 )
        goto LABEL_19;
      if ( v15 )
        break;
    }
LABEL_9:
    UserSession = OneCore::Base::Telemetry::OneSettingsQuery::OpenWebRequest(
                    this,
                    v4,
                    v7,
                    pwszUserName,
                    (unsigned __int64)pwszPassword,
                    v18,
                    v14);
    if ( UserSession >= 0 )
    {
      UserSession = OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(
                      (OneCore::Base::Telemetry::OneSettingsQuery *)this,
                      v4);
      if ( UserSession == -2147024891 && pwszUserName[0] && WinHttpSetCredentials(this[2], 1u, 1u, pwszUserName, v18, 0) )
        UserSession = OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(
                        (OneCore::Base::Telemetry::OneSettingsQuery *)this,
                        v4);
    }
    if ( v8 == 1 && v7 )
    {
      if ( !RevertToSelf() )
      {
        LastError = GetLastError();
        ExitProcess(LastError);
      }
      v7 = 0;
    }
    if ( UserSession >= 0 )
      goto LABEL_20;
LABEL_19:
    if ( (unsigned __int64)++v8 >= 2 )
      goto LABEL_20;
  }
  if ( ImpersonateLoggedOnUser(hToken) )
  {
    v7 = 1;
    goto LABEL_9;
  }
  v11 = GetLastError();
  UserSession = v11;
  if ( v11 > 0 )
    UserSession = (unsigned __int16)v11 | 0x80070000;
  if ( UserSession >= 0 )
    UserSession = -2147467259;
LABEL_20:
  if ( v7 && !RevertToSelf() )
  {
    v10 = GetLastError();
    ExitProcess(v10);
  }
  return (unsigned int)UserSession;
}

```

## disassembly

```asm
0x180003388  mov     [rsp-8+arg_8], rbx
0x18000338d  mov     [rsp-8+arg_10], rsi
0x180003392  push    rbp
0x180003393  push    rdi
0x180003394  push    r14
0x180003396  lea     rbp, [rsp-380h]
0x18000339e  sub     rsp, 480h
0x1800033a5  mov     rax, cs:__security_cookie
0x1800033ac  xor     rax, rsp
0x1800033af  mov     [rbp+390h+var_20], rax
0x1800033b6  xor     eax, eax
0x1800033b8  mov     [rsp+490h+hToken], 0
0x1800033c1  mov     r9d, 4F7Ch; unsigned __int16
0x1800033c7  mov     [rbp+390h+var_230], ax
0x1800033ce  mov     [rsp+490h+pwszUserName], ax
0x1800033d3  mov     r14, rcx
0x1800033d6  mov     [rsp+490h+var_450], 0
0x1800033de  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x1800033e3  test    al, al
0x1800033e5  jz      short loc_1800033F1
0x1800033e7  mov     eax, 80004005h
0x1800033ec  jmp     loc_18000351D
0x1800033f1  xor     sil, sil
0x1800033f4  xor     edi, edi
0x1800033f6  cmp     rdi, 1
0x1800033fa  jnz     short loc_180003432
0x1800033fc  lea     r8, [rsp+490h+var_450]; int *
0x180003401  lea     rdx, [rsp+490h+hToken]; void **
0x180003406  call    ?FindUserSession@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEAPEAXPEAH@Z; OneCore::Base::Telemetry::OneSettingsQuery::FindUserSession(void * *,int *)
0x18000340b  mov     ebx, eax
0x18000340d  test    eax, eax
0x18000340f  js      loc_1800034C0
0x180003415  cmp     [rsp+490h+var_450], 0
0x18000341a  jz      short loc_180003432
0x18000341c  mov     rcx, [rsp+490h+hToken]; hToken
0x180003421  call    cs:__imp_ImpersonateLoggedOnUser
0x180003427  test    eax, eax
0x180003429  jz      loc_1800034EB
0x18000342f  mov     sil, dil
0x180003432  lea     rax, [rbp+390h+var_230]
0x180003439  mov     r8b, sil; bool
0x18000343c  lea     r9, [rsp+490h+pwszUserName]; unsigned __int16 *
0x180003441  mov     [rsp+490h+pAuthParams], rax; unsigned __int16 *
0x180003446  mov     rcx, r14; this
0x180003449  call    ?OpenWebRequest@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG_NPEAG_K23@Z; OneCore::Base::Telemetry::OneSettingsQuery::OpenWebRequest(ushort const *,bool,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x18000344e  mov     ebx, eax
0x180003450  test    eax, eax
0x180003452  js      short loc_1800034A4
0x180003454  mov     rcx, r14; this
0x180003457  call    ?RetrieveOneSettingsFromWeb@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG@Z; OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(ushort const *)
0x18000345c  mov     ebx, eax
0x18000345e  cmp     eax, 80070005h
0x180003463  jnz     short loc_1800034A4
0x180003465  xor     eax, eax
0x180003467  cmp     ax, [rsp+490h+pwszUserName]
0x18000346c  jz      short loc_1800034A4
0x18000346e  mov     rcx, [r14+10h]; hRequest
0x180003472  lea     r9, [rsp+490h+pwszUserName]; pwszUserName
0x180003477  mov     [rsp+490h+pAuthParams], rax; pAuthParams
0x18000347c  mov     edx, 1; AuthTargets
0x180003481  lea     rax, [rbp+390h+var_230]
0x180003488  mov     r8d, edx; AuthScheme
0x18000348b  mov     [rsp+490h+pwszPassword], rax; pwszPassword
0x180003490  call    cs:__imp_WinHttpSetCredentials
0x180003496  test    eax, eax
0x180003498  jz      short loc_1800034A4
0x18000349a  mov     rcx, r14; this
0x18000349d  call    ?RetrieveOneSettingsFromWeb@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJPEBG@Z; OneCore::Base::Telemetry::OneSettingsQuery::RetrieveOneSettingsFromWeb(ushort const *)
0x1800034a2  mov     ebx, eax
0x1800034a4  cmp     rdi, 1
0x1800034a8  jnz     short loc_1800034BC
0x1800034aa  test    sil, sil
0x1800034ad  jz      short loc_1800034BC
0x1800034af  call    cs:__imp_RevertToSelf
0x1800034b5  test    eax, eax
0x1800034b7  jz      short loc_18000350C
0x1800034b9  xor     sil, sil
0x1800034bc  test    ebx, ebx
0x1800034be  jns     short loc_1800034CD
0x1800034c0  inc     rdi
0x1800034c3  cmp     rdi, 2
0x1800034c7  jb      loc_1800033F6
0x1800034cd  test    sil, sil
0x1800034d0  jz      short loc_18000351B
0x1800034d2  call    cs:__imp_RevertToSelf
0x1800034d8  test    eax, eax
0x1800034da  jnz     short loc_18000351B
0x1800034dc  call    cs:__imp_GetLastError
0x1800034e2  mov     ecx, eax; uExitCode
0x1800034e4  call    cs:__imp_ExitProcess
0x1800034eb  call    cs:__imp_GetLastError
0x1800034f1  mov     ebx, eax
0x1800034f3  test    eax, eax
0x1800034f5  jle     short loc_180003500
0x1800034f7  movzx   ebx, ax
0x1800034fa  or      ebx, 80070000h
0x180003500  test    ebx, ebx
0x180003502  mov     eax, 80004005h
0x180003507  cmovns  ebx, eax
0x18000350a  jmp     short loc_1800034CD
0x18000350c  call    cs:__imp_GetLastError
0x180003512  mov     ecx, eax; uExitCode
0x180003514  call    cs:__imp_ExitProcess
0x18000351b  mov     eax, ebx
0x18000351d  mov     rcx, [rbp+390h+var_20]
0x180003524  xor     rcx, rsp; StackCookie
0x180003527  call    __security_check_cookie
0x18000352c  lea     r11, [rsp+490h+var_10]
0x180003534  mov     rbx, [r11+28h]
0x180003538  mov     rsi, [r11+30h]
0x18000353c  mov     rsp, r11
0x18000353f  pop     r14
0x180003541  pop     rdi
0x180003542  pop     rbp
0x180003543  retn
```
