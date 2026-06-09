# LPA::Lpd::DownloadInstance::OnEs10bRemoveNotificationFromListComplete(long,_GUID const &,ulong)

- ea: `0x1800b47c0`
- end: `0x1800b4927`
- name: `?OnEs10bRemoveNotificationFromListComplete@DownloadInstance@Lpd@LPA@@UEAAXJAEBU_GUID@@K@Z`
- size: `359`
- prototype: `void(LPA::Lpd::DownloadInstance *__hidden this, int, const struct _GUID *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180005d6c`
- `0x1800b1768`
- `0x1800b47c0`
- `0x1800b6a4c`

## string_xrefs

- `0x1800b481b`: `LpaServiceLpd`
- `0x1800b4892`: `LpaServiceLpd`
- `0x1800b47ee`: `OnEs10bRemoveNotificationFromListComplete`
- `0x1800b4865`: `OnEs10bRemoveNotificationFromListComplete`
- `0x1800b4810`: `LPA::Lpd::DownloadInstance::OnEs10bRemoveNotificationFromListComplete`
- `0x1800b4887`: `LPA::Lpd::DownloadInstance::OnEs10bRemoveNotificationFromListComplete`

## pseudocode

```c
void __fastcall LPA::Lpd::DownloadInstance::OnEs10bRemoveNotificationFromListComplete(
        LPA::Lpd::DownloadInstance *this,
        int a2,
        const struct _GUID *a3,
        int a4)
{
  char *v6; // rdx
  const char **v7; // rax
  int *v8; // rcx
  int *v9; // [rsp+30h] [rbp-50h]
  int *v10; // [rsp+38h] [rbp-48h]
  const char **v11; // [rsp+40h] [rbp-40h]
  int v12; // [rsp+60h] [rbp-20h] BYREF
  int v13; // [rsp+64h] [rbp-1Ch] BYREF
  const char *v14; // [rsp+68h] [rbp-18h] BYREF
  const char *v15; // [rsp+70h] [rbp-10h] BYREF
  const char *v16; // [rsp+78h] [rbp-8h] BYREF
  int v17; // [rsp+90h] [rbp+10h] BYREF
  int v18; // [rsp+98h] [rbp+18h] BYREF

  if ( a2 < 0 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_7;
    v12 = 4;
    v16 = "OnEs10bRemoveNotificationFromListComplete";
    v6 = byte_18013038B;
    v13 = *((_DWORD *)this + 226);
    v15 = "LPA::Lpd::DownloadInstance::OnEs10bRemoveNotificationFromListComplete";
    v14 = "LpaServiceLpd";
    v11 = &v16;
    v10 = &v13;
    v9 = &v12;
    v7 = &v14;
  }
  else
  {
    if ( (unsigned int)CallbackContext <= 4 )
      goto LABEL_7;
    v13 = 4;
    v14 = "OnEs10bRemoveNotificationFromListComplete";
    v6 = (char *)&unk_1801303F0;
    v12 = *((_DWORD *)this + 226);
    v15 = "LPA::Lpd::DownloadInstance::OnEs10bRemoveNotificationFromListComplete";
    v16 = "LpaServiceLpd";
    v11 = &v14;
    v10 = &v12;
    v9 = &v13;
    v7 = &v16;
  }
  v18 = a2;
  v17 = 18;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
    (_DWORD)this,
    (_DWORD)v6,
    (_DWORD)a3,
    a4,
    (__int64)v7,
    (__int64)&v15,
    (__int64)v9,
    (__int64)v10,
    (__int64)v11,
    (__int64)&v17,
    (__int64)&v18);
LABEL_7:
  v8 = (int *)((char *)this - 8);
  if ( *((_DWORD *)this + 218) == 3 )
    LPA::Lpd::DownloadInstance::OnNotificationSentToSmdp((LPA::Lpd::DownloadInstance *)v8, a2);
  else
    LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted((__int64)v8, v8[225], 2u);
}

```

## disassembly

```asm
0x1800b47c0  mov     r11, rsp
0x1800b47c3  mov     [r11+18h], rbx
0x1800b47c7  mov     [r11+20h], rdi
0x1800b47cb  push    rbp
0x1800b47cc  mov     rbp, rsp
0x1800b47cf  sub     rsp, 80h
0x1800b47d6  mov     eax, cs:CallbackContext
0x1800b47dc  mov     ebx, edx
0x1800b47de  mov     rdi, rcx
0x1800b47e1  test    edx, edx
0x1800b47e3  js      short loc_1800B485C
0x1800b47e5  cmp     eax, 4
0x1800b47e8  jbe     loc_1800B48EB
0x1800b47ee  lea     rax, aOnes10bremoven; "OnEs10bRemoveNotificationFromListComple"...
0x1800b47f5  mov     [rbp+var_1C], 4
0x1800b47fc  mov     [rbp+var_18], rax
0x1800b4800  lea     rdx, unk_1801303F0
0x1800b4807  mov     eax, [rcx+388h]
0x1800b480d  mov     [rbp+var_20], eax
0x1800b4810  lea     rax, aLpaLpdDownload_27; "LPA::Lpd::DownloadInstance::OnEs10bRemo"...
0x1800b4817  mov     [rbp+var_10], rax
0x1800b481b  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b4822  mov     [rbp+var_8], rax
0x1800b4826  lea     rax, [rbp+arg_8]
0x1800b482a  mov     [r11-38h], rax
0x1800b482e  lea     rax, [rbp+arg_0]
0x1800b4832  mov     [r11-40h], rax
0x1800b4836  lea     rax, [rbp+var_18]
0x1800b483a  mov     [r11-48h], rax
0x1800b483e  lea     rax, [rbp+var_20]
0x1800b4842  mov     [r11-50h], rax
0x1800b4846  lea     rax, [rbp+var_1C]
0x1800b484a  mov     [r11-58h], rax
0x1800b484e  lea     rax, [rbp+var_10]
0x1800b4852  mov     [r11-60h], rax
0x1800b4856  lea     rax, [rbp+var_8]
0x1800b485a  jmp     short loc_1800B48D7
0x1800b485c  cmp     eax, 2
0x1800b485f  jbe     loc_1800B48EB
0x1800b4865  lea     rax, aOnes10bremoven; "OnEs10bRemoveNotificationFromListComple"...
0x1800b486c  mov     [rbp+var_20], 4
0x1800b4873  mov     [rbp+var_8], rax
0x1800b4877  lea     rdx, byte_18013038B
0x1800b487e  mov     eax, [rcx+388h]
0x1800b4884  mov     [rbp+var_1C], eax
0x1800b4887  lea     rax, aLpaLpdDownload_27; "LPA::Lpd::DownloadInstance::OnEs10bRemo"...
0x1800b488e  mov     [rbp+var_10], rax
0x1800b4892  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b4899  mov     [rbp+var_18], rax
0x1800b489d  lea     rax, [rbp+arg_8]
0x1800b48a1  mov     [rsp+80h+var_30], rax
0x1800b48a6  lea     rax, [rbp+arg_0]
0x1800b48aa  mov     [rsp+80h+var_38], rax
0x1800b48af  lea     rax, [rbp+var_8]
0x1800b48b3  mov     [rsp+80h+var_40], rax
0x1800b48b8  lea     rax, [rbp+var_1C]
0x1800b48bc  mov     [rsp+80h+var_48], rax
0x1800b48c1  lea     rax, [rbp+var_20]
0x1800b48c5  mov     [rsp+80h+var_50], rax
0x1800b48ca  lea     rax, [rbp+var_10]
0x1800b48ce  mov     [rsp+80h+var_58], rax
0x1800b48d3  lea     rax, [rbp+var_18]
0x1800b48d7  mov     [rsp+80h+var_60], rax
0x1800b48dc  mov     [rbp+arg_8], ebx
0x1800b48df  mov     [rbp+arg_0], 12h
0x1800b48e6  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b48eb  lea     rcx, [rdi-8]; this
0x1800b48ef  cmp     dword ptr [rcx+370h], 3
0x1800b48f6  jnz     short loc_1800B4901
0x1800b48f8  mov     edx, ebx; int
0x1800b48fa  call    ?OnNotificationSentToSmdp@DownloadInstance@Lpd@LPA@@AEAAXJ@Z; LPA::Lpd::DownloadInstance::OnNotificationSentToSmdp(long)
0x1800b48ff  jmp     short loc_1800B4912
0x1800b4901  mov     edx, [rcx+384h]
0x1800b4907  mov     r8d, 2
0x1800b490d  call    ?OnCmaOrInstallCompleted@DownloadInstance@Lpd@LPA@@AEAAXJW4CmaOrInstallCompletion@123@@Z; LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted(long,LPA::Lpd::DownloadInstance::CmaOrInstallCompletion)
0x1800b4912  lea     r11, [rsp+80h+var_s0]
0x1800b491a  mov     rbx, [r11+20h]
0x1800b491e  mov     rdi, [r11+28h]
0x1800b4922  mov     rsp, r11
0x1800b4925  pop     rbp
0x1800b4926  retn
```
