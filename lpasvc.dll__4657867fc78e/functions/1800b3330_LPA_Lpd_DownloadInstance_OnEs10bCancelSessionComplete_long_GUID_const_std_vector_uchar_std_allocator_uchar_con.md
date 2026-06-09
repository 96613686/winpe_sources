# LPA::Lpd::DownloadInstance::OnEs10bCancelSessionComplete(long,_GUID const &,std::vector<uchar,std::allocator<uchar>> const &,ulong)

- ea: `0x1800b3330`
- end: `0x1800b35ed`
- name: `?OnEs10bCancelSessionComplete@DownloadInstance@Lpd@LPA@@UEAAXJAEBU_GUID@@AEBV?$vector@EV?$allocator@E@std@@@std@@K@Z`
- size: `701`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005d6c`
- `0x1800709e4`
- `0x180071940`
- `0x180071994`
- `0x1800ae530`
- `0x1800b1768`
- `0x1800b3330`
- `0x180101010`

## string_xrefs

- `0x1800b3366`: `LpaServiceLpd`
- `0x1800b3574`: `LpaServiceLpd`
- `0x1800b335f`: `LPA::Lpd::DownloadInstance::OnEs10bCancelSessionComplete`
- `0x1800b3569`: `LPA::Lpd::DownloadInstance::OnEs10bCancelSessionComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall LPA::Lpd::DownloadInstance::OnEs10bCancelSessionComplete(__int64 a1, int a2, int a3, __int64 a4)
{
  int v4; // ebx
  _QWORD **v6; // rdi
  _QWORD *i; // rbx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int v11; // ecx
  _DWORD *v12; // rax
  int v13; // [rsp+68h] [rbp-11h] BYREF
  int v14; // [rsp+6Ch] [rbp-Dh] BYREF
  const char *v15; // [rsp+70h] [rbp-9h] BYREF
  const char *v16; // [rsp+78h] [rbp-1h] BYREF
  std::_Ref_count_base *v17; // [rsp+80h] [rbp+7h]
  const char *v18; // [rsp+88h] [rbp+Fh] BYREF
  std::_Ref_count_base *v19; // [rsp+90h] [rbp+17h]
  int v20; // [rsp+D8h] [rbp+5Fh] BYREF
  int v21; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v22; // [rsp+F0h] [rbp+77h]

  v22 = a4;
  v4 = a2;
  if ( a2 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v21 = a2;
      v20 = 12;
      v18 = "OnEs10bCancelSession";
      v14 = *(_DWORD *)(a1 + 904);
      v13 = 4;
      v16 = "LPA::Lpd::DownloadInstance::OnEs10bCancelSessionComplete";
      v15 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        a1,
        (unsigned int)byte_180130715,
        a3,
        a4,
        (__int64)&v15,
        (__int64)&v16,
        (__int64)&v13,
        (__int64)&v14,
        (__int64)&v18,
        (__int64)&v20,
        (__int64)&v21);
    }
    goto LABEL_23;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v21 = a2;
    v20 = 12;
    v15 = "OnEs10bCancelSession";
    v13 = *(_DWORD *)(a1 + 904);
    v14 = 4;
    v16 = "LPA::Lpd::DownloadInstance::OnEs10bCancelSessionComplete";
    v18 = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned int)word_18013077A,
      a3,
      a4,
      (__int64)&v18,
      (__int64)&v16,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v15,
      (__int64)&v20,
      (__int64)&v21);
  }
  if ( !*(_BYTE *)(a1 + 868) )
  {
    std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(a1 + 24, &v16);
    if ( v16 )
    {
      v6 = (_QWORD **)*((_QWORD *)v16 + 15);
      for ( i = *v6; i != v6; i = (_QWORD *)*i )
      {
        std::weak_ptr<LPA::LpdNotificationHandler>::lock(i + 2, &v18);
        if ( v18 )
          (*(void (__fastcall **)(const char *, __int64, __int64))(*(_QWORD *)v18 + 16LL))(v18, a1 + 876, a1 + 1028);
        if ( v19 )
          std::_Ref_count_base::_Decref(v19);
      }
    }
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
  }
  v4 = LPA::Lpd::DownloadInstance::Es9CancelSession(a1 - 8, v22);
  if ( v4 < 0 )
  {
    v11 = *(_DWORD *)(a1 + 1016);
    v12 = (_DWORD *)(a1 + 1020);
    if ( (v11 & 1) == 0 || !*v12 )
    {
      *(_DWORD *)(a1 + 1016) = v11 | 1;
      *v12 = 13;
    }
LABEL_23:
    LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted(a1 - 8, v4, 2u);
    return;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v21 = *(_DWORD *)(a1 + 912);
    v20 = 10;
    v18 = "WaitEs9CancelSession";
    v14 = *(_DWORD *)(a1 + 904);
    v13 = 4;
    v16 = "LPA::Lpd::DownloadInstance::OnEs10bCancelSessionComplete";
    v15 = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)byte_1801306B1,
      v9,
      v10,
      (__int64)&v15,
      (__int64)&v16,
      (__int64)&v13,
      (__int64)&v14,
      (__int64)&v18,
      (__int64)&v20,
      (__int64)&v21);
  }
}

```

## disassembly

```asm
0x1800b3330  mov     r11, rsp
0x1800b3333  mov     [r11+20h], r9
0x1800b3337  push    rbp
0x1800b3338  push    rbx
0x1800b3339  push    rsi
0x1800b333a  push    rdi
0x1800b333b  push    r12
0x1800b333d  push    r13
0x1800b333f  push    r15
0x1800b3341  lea     rbp, [r11-57h]
0x1800b3345  sub     rsp, 90h
0x1800b334c  mov     ebx, edx
0x1800b334e  mov     rsi, rcx
0x1800b3351  mov     eax, cs:CallbackContext
0x1800b3357  test    edx, edx
0x1800b3359  js      loc_1800B353B
0x1800b335f  lea     r12, aLpaLpdDownload_23; "LPA::Lpd::DownloadInstance::OnEs10bCanc"...
0x1800b3366  lea     r13, aLpaservicelpd; "LpaServiceLpd"
0x1800b336d  cmp     eax, 4
0x1800b3370  jbe     short loc_1800B33E8
0x1800b3372  mov     [rbp+4Fh+arg_8], edx
0x1800b3375  mov     [rbp+4Fh+arg_0], 0Ch
0x1800b337c  lea     rax, aOnes10bcancels; "OnEs10bCancelSession"
0x1800b3383  mov     [rbp+4Fh+var_58], rax
0x1800b3387  mov     eax, [rcx+388h]
0x1800b338d  mov     [rbp+4Fh+var_60], eax
0x1800b3390  mov     [rbp+4Fh+var_5C], 4
0x1800b3397  mov     [rbp+4Fh+var_50], r12
0x1800b339b  mov     [rbp+4Fh+var_40], r13
0x1800b339f  lea     rax, [rbp+4Fh+arg_8]
0x1800b33a3  mov     [r11-78h], rax
0x1800b33a7  lea     rax, [rbp+4Fh+arg_0]
0x1800b33ab  mov     [r11-80h], rax
0x1800b33af  lea     rax, [rbp+4Fh+var_58]
0x1800b33b3  mov     [rsp+0C0h+var_80], rax
0x1800b33b8  lea     rax, [rbp+4Fh+var_60]
0x1800b33bc  mov     [rsp+0C0h+var_88], rax
0x1800b33c1  lea     rax, [rbp+4Fh+var_5C]
0x1800b33c5  mov     [rsp+0C0h+var_90], rax
0x1800b33ca  lea     rax, [rbp+4Fh+var_50]
0x1800b33ce  mov     [rsp+0C0h+var_98], rax
0x1800b33d3  lea     rax, [rbp+4Fh+var_40]
0x1800b33d7  mov     [rsp+0C0h+var_A0], rax
0x1800b33dc  lea     rdx, word_18013077A
0x1800b33e3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b33e8  cmp     byte ptr [rsi+364h], 0
0x1800b33ef  jnz     short loc_1800B3467
0x1800b33f1  lea     rcx, [rsi+18h]
0x1800b33f5  lea     rdx, [rbp+4Fh+var_50]
0x1800b33f9  call    ?lock@?$weak_ptr@VDownloadInstance@Lpd@LPA@@@std@@QEBA?AV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@2@XZ; std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(void)
0x1800b33fe  nop
0x1800b33ff  mov     rdi, [rbp+4Fh+var_50]
0x1800b3403  test    rdi, rdi
0x1800b3406  jz      short loc_1800B3459
0x1800b3408  mov     rdi, [rdi+78h]
0x1800b340c  mov     rbx, [rdi]
0x1800b340f  cmp     rbx, rdi
0x1800b3412  jz      short loc_1800B3459
0x1800b3414  lea     rcx, [rbx+10h]
0x1800b3418  lea     rdx, [rbp+4Fh+var_40]
0x1800b341c  call    ?lock@?$weak_ptr@ULpdNotificationHandler@LPA@@@std@@QEBA?AV?$shared_ptr@ULpdNotificationHandler@LPA@@@2@XZ; std::weak_ptr<LPA::LpdNotificationHandler>::lock(void)
0x1800b3421  nop
0x1800b3422  mov     rcx, [rbp+4Fh+var_40]
0x1800b3426  test    rcx, rcx
0x1800b3429  jz      short loc_1800B3446
0x1800b342b  mov     rax, [rcx]
0x1800b342e  lea     r8, [rsi+404h]
0x1800b3435  lea     rdx, [rsi+36Ch]
0x1800b343c  mov     rax, [rax+10h]
0x1800b3440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3445  nop
0x1800b3446  mov     rcx, [rbp+4Fh+var_38]; this
0x1800b344a  test    rcx, rcx
0x1800b344d  jz      short loc_1800B3454
0x1800b344f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b3454  mov     rbx, [rbx]
0x1800b3457  jmp     short loc_1800B340F
0x1800b3459  mov     rcx, [rbp+4Fh+var_48]; this
0x1800b345d  test    rcx, rcx
0x1800b3460  jz      short loc_1800B3467
0x1800b3462  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b3467  mov     rdx, [rbp+4Fh+arg_18]
0x1800b346b  lea     rcx, [rsi-8]
0x1800b346f  call    ?Es9CancelSession@DownloadInstance@Lpd@LPA@@AEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; LPA::Lpd::DownloadInstance::Es9CancelSession(std::vector<uchar> const &)
0x1800b3474  mov     ebx, eax
0x1800b3476  test    eax, eax
0x1800b3478  jns     short loc_1800B34A9
0x1800b347a  mov     ecx, [rsi+3F8h]
0x1800b3480  lea     rax, [rsi+3FCh]
0x1800b3487  test    cl, 1
0x1800b348a  jz      short loc_1800B3495
0x1800b348c  cmp     dword ptr [rax], 0
0x1800b348f  jnz     loc_1800B35CA
0x1800b3495  or      ecx, 1
0x1800b3498  mov     [rsi+3F8h], ecx
0x1800b349e  mov     dword ptr [rax], 0Dh
0x1800b34a4  jmp     loc_1800B35CA
0x1800b34a9  mov     eax, cs:CallbackContext
0x1800b34af  cmp     eax, 4
0x1800b34b2  jbe     loc_1800B35DB
0x1800b34b8  mov     eax, [rsi+390h]
0x1800b34be  mov     [rbp+4Fh+arg_8], eax
0x1800b34c1  mov     [rbp+4Fh+arg_0], 0Ah
0x1800b34c8  lea     rax, aWaites9cancels; "WaitEs9CancelSession"
0x1800b34cf  mov     [rbp+4Fh+var_40], rax
0x1800b34d3  mov     eax, [rsi+388h]
0x1800b34d9  mov     [rbp+4Fh+var_5C], eax
0x1800b34dc  mov     [rbp+4Fh+var_60], 4
0x1800b34e3  mov     [rbp+4Fh+var_50], r12
0x1800b34e7  mov     [rbp+4Fh+var_58], r13
0x1800b34eb  lea     rax, [rbp+4Fh+arg_8]
0x1800b34ef  mov     [rsp+50h], rax
0x1800b34f4  lea     rax, [rbp+4Fh+arg_0]
0x1800b34f8  mov     [rsp+0C0h+var_78], rax
0x1800b34fd  lea     rax, [rbp+4Fh+var_40]
0x1800b3501  mov     [rsp+0C0h+var_80], rax
0x1800b3506  lea     rax, [rbp+4Fh+var_5C]
0x1800b350a  mov     [rsp+0C0h+var_88], rax
0x1800b350f  lea     rax, [rbp+4Fh+var_60]
0x1800b3513  mov     [rsp+0C0h+var_90], rax
0x1800b3518  lea     rax, [rbp+4Fh+var_50]
0x1800b351c  mov     [rsp+0C0h+var_98], rax
0x1800b3521  lea     rax, [rbp+4Fh+var_58]
0x1800b3525  mov     [rsp+0C0h+var_A0], rax
0x1800b352a  lea     rdx, byte_1801306B1
0x1800b3531  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b3536  jmp     loc_1800B35DB
0x1800b353b  cmp     eax, 2
0x1800b353e  jbe     loc_1800B35CA
0x1800b3544  mov     [rbp+4Fh+arg_8], edx
0x1800b3547  mov     [rbp+4Fh+arg_0], 0Ch
0x1800b354e  lea     rax, aOnes10bcancels; "OnEs10bCancelSession"
0x1800b3555  mov     [rbp+4Fh+var_40], rax
0x1800b3559  mov     eax, [rcx+388h]
0x1800b355f  mov     [rbp+4Fh+var_5C], eax
0x1800b3562  mov     [rbp+4Fh+var_60], 4
0x1800b3569  lea     r12, aLpaLpdDownload_23; "LPA::Lpd::DownloadInstance::OnEs10bCanc"...
0x1800b3570  mov     [rbp+4Fh+var_50], r12
0x1800b3574  lea     r13, aLpaservicelpd; "LpaServiceLpd"
0x1800b357b  mov     [rbp+4Fh+var_58], r13
0x1800b357f  lea     rax, [rbp+4Fh+arg_8]
0x1800b3583  mov     [rsp+50h], rax
0x1800b3588  lea     rax, [rbp+4Fh+arg_0]
0x1800b358c  mov     [rsp+0C0h+var_78], rax
0x1800b3591  lea     rax, [rbp+4Fh+var_40]
0x1800b3595  mov     [rsp+0C0h+var_80], rax
0x1800b359a  lea     rax, [rbp+4Fh+var_5C]
0x1800b359e  mov     [rsp+0C0h+var_88], rax
0x1800b35a3  lea     rax, [rbp+4Fh+var_60]
0x1800b35a7  mov     [rsp+0C0h+var_90], rax
0x1800b35ac  lea     rax, [rbp+4Fh+var_50]
0x1800b35b0  mov     [rsp+0C0h+var_98], rax
0x1800b35b5  lea     rax, [rbp+4Fh+var_58]
0x1800b35b9  mov     [rsp+0C0h+var_A0], rax
0x1800b35be  lea     rdx, byte_180130715
0x1800b35c5  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b35ca  lea     rcx, [rsi-8]
0x1800b35ce  mov     r8d, 2
0x1800b35d4  mov     edx, ebx
0x1800b35d6  call    ?OnCmaOrInstallCompleted@DownloadInstance@Lpd@LPA@@AEAAXJW4CmaOrInstallCompletion@123@@Z; LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted(long,LPA::Lpd::DownloadInstance::CmaOrInstallCompletion)
0x1800b35db  add     rsp, 90h
0x1800b35e2  pop     r15
0x1800b35e4  pop     r13
0x1800b35e6  pop     r12
0x1800b35e8  pop     rdi
0x1800b35e9  pop     rsi
0x1800b35ea  pop     rbx
0x1800b35eb  pop     rbp
0x1800b35ec  retn
```
