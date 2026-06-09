# LPA::Lpd::DownloadInstance::OnEs10bPrepareDownloadComplete(long,_GUID const &,ulong,std::vector<uchar,std::allocator<uchar>>)

- ea: `0x1800b4460`
- end: `0x1800b471d`
- name: `?OnEs10bPrepareDownloadComplete@DownloadInstance@Lpd@LPA@@UEAAXJAEBU_GUID@@KV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `701`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180005d6c`
- `0x1800709e4`
- `0x1800715d0`
- `0x180071940`
- `0x180071994`
- `0x1800ae944`
- `0x1800b1768`
- `0x1800b4460`
- `0x180101010`

## string_xrefs

- `0x1800b4493`: `LpaServiceLpd`
- `0x1800b4696`: `LpaServiceLpd`
- `0x1800b448c`: `LPA::Lpd::DownloadInstance::OnEs10bPrepareDownloadComplete`
- `0x1800b468b`: `LPA::Lpd::DownloadInstance::OnEs10bPrepareDownloadComplete`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall LPA::Lpd::DownloadInstance::OnEs10bPrepareDownloadComplete(
        _DWORD *a1,
        int a2,
        int a3,
        int a4,
        __int64 a5)
{
  int BoundProfilePackage; // ebx
  _QWORD **v7; // rdi
  _QWORD *i; // rbx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  _DWORD *v13; // rax
  int v15; // [rsp+68h] [rbp-1h] BYREF
  int v16; // [rsp+6Ch] [rbp+3h] BYREF
  const char *v17; // [rsp+70h] [rbp+7h] BYREF
  const char *v18; // [rsp+78h] [rbp+Fh] BYREF
  std::_Ref_count_base *v19; // [rsp+80h] [rbp+17h]
  const char *v20; // [rsp+88h] [rbp+1Fh] BYREF
  std::_Ref_count_base *v21; // [rsp+90h] [rbp+27h]
  int v22; // [rsp+C8h] [rbp+5Fh] BYREF
  int v23; // [rsp+D0h] [rbp+67h] BYREF

  BoundProfilePackage = a2;
  if ( a2 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v23 = a2;
      v22 = 14;
      v20 = "OnEs10bPrepareDownload";
      v16 = a1[226];
      v15 = 4;
      v18 = "LPA::Lpd::DownloadInstance::OnEs10bPrepareDownloadComplete";
      v17 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)a1,
        (unsigned int)&byte_1801305E7,
        a3,
        a4,
        (__int64)&v17,
        (__int64)&v18,
        (__int64)&v15,
        (__int64)&v16,
        (__int64)&v20,
        (__int64)&v22,
        (__int64)&v23);
    }
    goto LABEL_22;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v23 = a2;
    v22 = 14;
    v17 = "OnEs10bPrepareDownload";
    v15 = a1[226];
    v16 = 4;
    v18 = "LPA::Lpd::DownloadInstance::OnEs10bPrepareDownloadComplete";
    v20 = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)&dword_18013064C,
      a3,
      a4,
      (__int64)&v20,
      (__int64)&v18,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v17,
      (__int64)&v22,
      (__int64)&v23);
  }
  std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(a1 + 6, &v18);
  if ( v18 )
  {
    v7 = (_QWORD **)*((_QWORD *)v18 + 15);
    for ( i = *v7; i != v7; i = (_QWORD *)*i )
    {
      std::weak_ptr<LPA::LpdNotificationHandler>::lock(i + 2, &v20);
      if ( v20 )
        (*(void (__fastcall **)(const char *, _DWORD *, _DWORD *))(*(_QWORD *)v20 + 32LL))(v20, a1 + 219, a1 + 257);
      if ( v21 )
        std::_Ref_count_base::_Decref(v21);
    }
  }
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  BoundProfilePackage = LPA::Lpd::DownloadInstance::Es9GetBoundProfilePackage(a1 - 2, a5);
  if ( BoundProfilePackage < 0 )
  {
    v12 = a1[254];
    v13 = a1 + 255;
    if ( (v12 & 1) == 0 || !*v13 )
    {
      a1[254] = v12 | 1;
      *v13 = 13;
    }
LABEL_22:
    LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted((__int64)(a1 - 2), BoundProfilePackage, 2u);
    return std::vector<unsigned char>::_Tidy(a5);
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v23 = a1[228];
    v22 = 11;
    v20 = "WaitEs9GetBoundProfilePackage";
    v16 = a1[226];
    v15 = 4;
    v18 = "LPA::Lpd::DownloadInstance::OnEs10bPrepareDownloadComplete";
    v17 = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v9,
      (unsigned int)byte_180130583,
      v10,
      v11,
      (__int64)&v17,
      (__int64)&v18,
      (__int64)&v15,
      (__int64)&v16,
      (__int64)&v20,
      (__int64)&v22,
      (__int64)&v23);
  }
  return std::vector<unsigned char>::_Tidy(a5);
}

```

## disassembly

```asm
0x1800b4460  mov     r11, rsp
0x1800b4463  mov     [r11+18h], rbx
0x1800b4467  push    rbp
0x1800b4468  push    rsi
0x1800b4469  push    rdi
0x1800b446a  push    r12
0x1800b446c  push    r15
0x1800b446e  lea     rbp, [r11-57h]
0x1800b4472  sub     rsp, 90h
0x1800b4479  mov     ebx, edx
0x1800b447b  mov     rsi, rcx
0x1800b447e  mov     eax, cs:CallbackContext
0x1800b4484  test    edx, edx
0x1800b4486  js      loc_1800B465D
0x1800b448c  lea     r15, aLpaLpdDownload_0; "LPA::Lpd::DownloadInstance::OnEs10bPrep"...
0x1800b4493  lea     r12, aLpaservicelpd; "LpaServiceLpd"
0x1800b449a  cmp     eax, 4
0x1800b449d  jbe     short loc_1800B4513
0x1800b449f  mov     [rbp+4Fh+arg_8], edx
0x1800b44a2  mov     [rbp+4Fh+arg_0], 0Eh
0x1800b44a9  lea     rax, aOnes10bprepare; "OnEs10bPrepareDownload"
0x1800b44b0  mov     [rbp+4Fh+var_48], rax
0x1800b44b4  mov     eax, [rcx+388h]
0x1800b44ba  mov     [rbp+4Fh+var_50], eax
0x1800b44bd  mov     [rbp+4Fh+var_4C], 4
0x1800b44c4  mov     [rbp+4Fh+var_40], r15
0x1800b44c8  mov     [rbp+4Fh+var_30], r12
0x1800b44cc  lea     rax, [rbp+4Fh+arg_8]
0x1800b44d0  mov     [r11-68h], rax
0x1800b44d4  lea     rax, [rbp+4Fh+arg_0]
0x1800b44d8  mov     [r11-70h], rax
0x1800b44dc  lea     rax, [rbp+4Fh+var_48]
0x1800b44e0  mov     [r11-78h], rax
0x1800b44e4  lea     rax, [rbp+4Fh+var_50]
0x1800b44e8  mov     [r11-80h], rax
0x1800b44ec  lea     rax, [rbp+4Fh+var_4C]
0x1800b44f0  mov     [rsp+0B0h+var_80], rax
0x1800b44f5  lea     rax, [rbp+4Fh+var_40]
0x1800b44f9  mov     [rsp+0B0h+var_88], rax
0x1800b44fe  lea     rax, [rbp+4Fh+var_30]
0x1800b4502  mov     [rsp+0B0h+var_90], rax
0x1800b4507  lea     rdx, dword_18013064C
0x1800b450e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b4513  lea     rcx, [rsi+18h]
0x1800b4517  lea     rdx, [rbp+4Fh+var_40]
0x1800b451b  call    ?lock@?$weak_ptr@VDownloadInstance@Lpd@LPA@@@std@@QEBA?AV?$shared_ptr@VDownloadInstance@Lpd@LPA@@@2@XZ; std::weak_ptr<LPA::Lpd::DownloadInstance>::lock(void)
0x1800b4520  nop
0x1800b4521  mov     rdi, [rbp+4Fh+var_40]
0x1800b4525  test    rdi, rdi
0x1800b4528  jz      short loc_1800B457B
0x1800b452a  mov     rdi, [rdi+78h]
0x1800b452e  mov     rbx, [rdi]
0x1800b4531  cmp     rbx, rdi
0x1800b4534  jz      short loc_1800B457B
0x1800b4536  lea     rcx, [rbx+10h]
0x1800b453a  lea     rdx, [rbp+4Fh+var_30]
0x1800b453e  call    ?lock@?$weak_ptr@ULpdNotificationHandler@LPA@@@std@@QEBA?AV?$shared_ptr@ULpdNotificationHandler@LPA@@@2@XZ; std::weak_ptr<LPA::LpdNotificationHandler>::lock(void)
0x1800b4543  nop
0x1800b4544  mov     rcx, [rbp+4Fh+var_30]
0x1800b4548  test    rcx, rcx
0x1800b454b  jz      short loc_1800B4568
0x1800b454d  mov     rax, [rcx]
0x1800b4550  lea     r8, [rsi+404h]
0x1800b4557  lea     rdx, [rsi+36Ch]
0x1800b455e  mov     rax, [rax+20h]
0x1800b4562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4567  nop
0x1800b4568  mov     rcx, [rbp+4Fh+var_28]; this
0x1800b456c  test    rcx, rcx
0x1800b456f  jz      short loc_1800B4576
0x1800b4571  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b4576  mov     rbx, [rbx]
0x1800b4579  jmp     short loc_1800B4531
0x1800b457b  mov     rcx, [rbp+4Fh+var_38]; this
0x1800b457f  test    rcx, rcx
0x1800b4582  jz      short loc_1800B4589
0x1800b4584  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b4589  lea     rcx, [rsi-8]
0x1800b458d  mov     rdx, [rbp+4Fh+arg_20]
0x1800b4591  call    ?Es9GetBoundProfilePackage@DownloadInstance@Lpd@LPA@@AEAAJAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; LPA::Lpd::DownloadInstance::Es9GetBoundProfilePackage(std::vector<uchar> const &)
0x1800b4596  mov     ebx, eax
0x1800b4598  test    eax, eax
0x1800b459a  jns     short loc_1800B45CB
0x1800b459c  mov     ecx, [rsi+3F8h]
0x1800b45a2  lea     rax, [rsi+3FCh]
0x1800b45a9  test    cl, 1
0x1800b45ac  jz      short loc_1800B45B7
0x1800b45ae  cmp     dword ptr [rax], 0
0x1800b45b1  jnz     loc_1800B46EC
0x1800b45b7  or      ecx, 1
0x1800b45ba  mov     [rsi+3F8h], ecx
0x1800b45c0  mov     dword ptr [rax], 0Dh
0x1800b45c6  jmp     loc_1800B46EC
0x1800b45cb  mov     eax, cs:CallbackContext
0x1800b45d1  cmp     eax, 4
0x1800b45d4  jbe     loc_1800B46FE
0x1800b45da  mov     eax, [rsi+390h]
0x1800b45e0  mov     [rbp+4Fh+arg_8], eax
0x1800b45e3  mov     [rbp+4Fh+arg_0], 0Bh
0x1800b45ea  lea     rax, aWaites9getboun; "WaitEs9GetBoundProfilePackage"
0x1800b45f1  mov     [rbp+4Fh+var_30], rax
0x1800b45f5  mov     eax, [rsi+388h]
0x1800b45fb  mov     [rbp+4Fh+var_4C], eax
0x1800b45fe  mov     [rbp+4Fh+var_50], 4
0x1800b4605  mov     [rbp+4Fh+var_40], r15
0x1800b4609  mov     [rbp+4Fh+var_48], r12
0x1800b460d  lea     rax, [rbp+4Fh+arg_8]
0x1800b4611  mov     [rsp+50h], rax
0x1800b4616  lea     rax, [rbp+4Fh+arg_0]
0x1800b461a  mov     [rsp+0B0h+var_68], rax
0x1800b461f  lea     rax, [rbp+4Fh+var_30]
0x1800b4623  mov     [rsp+0B0h+var_70], rax
0x1800b4628  lea     rax, [rbp+4Fh+var_4C]
0x1800b462c  mov     [rsp+0B0h+var_78], rax
0x1800b4631  lea     rax, [rbp+4Fh+var_50]
0x1800b4635  mov     [rsp+0B0h+var_80], rax
0x1800b463a  lea     rax, [rbp+4Fh+var_40]
0x1800b463e  mov     [rsp+0B0h+var_88], rax
0x1800b4643  lea     rax, [rbp+4Fh+var_48]
0x1800b4647  mov     [rsp+0B0h+var_90], rax
0x1800b464c  lea     rdx, byte_180130583
0x1800b4653  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b4658  jmp     loc_1800B46FE
0x1800b465d  cmp     eax, 2
0x1800b4660  jbe     loc_1800B46EC
0x1800b4666  mov     [rbp+4Fh+arg_8], edx
0x1800b4669  mov     [rbp+4Fh+arg_0], 0Eh
0x1800b4670  lea     rax, aOnes10bprepare; "OnEs10bPrepareDownload"
0x1800b4677  mov     [rbp+4Fh+var_30], rax
0x1800b467b  mov     eax, [rcx+388h]
0x1800b4681  mov     [rbp+4Fh+var_4C], eax
0x1800b4684  mov     [rbp+4Fh+var_50], 4
0x1800b468b  lea     r15, aLpaLpdDownload_0; "LPA::Lpd::DownloadInstance::OnEs10bPrep"...
0x1800b4692  mov     [rbp+4Fh+var_40], r15
0x1800b4696  lea     r12, aLpaservicelpd; "LpaServiceLpd"
0x1800b469d  mov     [rbp+4Fh+var_48], r12
0x1800b46a1  lea     rax, [rbp+4Fh+arg_8]
0x1800b46a5  mov     [rsp+50h], rax
0x1800b46aa  lea     rax, [rbp+4Fh+arg_0]
0x1800b46ae  mov     [rsp+0B0h+var_68], rax
0x1800b46b3  lea     rax, [rbp+4Fh+var_30]
0x1800b46b7  mov     [rsp+0B0h+var_70], rax
0x1800b46bc  lea     rax, [rbp+4Fh+var_4C]
0x1800b46c0  mov     [rsp+0B0h+var_78], rax
0x1800b46c5  lea     rax, [rbp+4Fh+var_50]
0x1800b46c9  mov     [rsp+0B0h+var_80], rax
0x1800b46ce  lea     rax, [rbp+4Fh+var_40]
0x1800b46d2  mov     [rsp+0B0h+var_88], rax
0x1800b46d7  lea     rax, [rbp+4Fh+var_48]
0x1800b46db  mov     [rsp+0B0h+var_90], rax
0x1800b46e0  lea     rdx, byte_1801305E7
0x1800b46e7  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b46ec  lea     rcx, [rsi-8]
0x1800b46f0  mov     r8d, 2
0x1800b46f6  mov     edx, ebx
0x1800b46f8  call    ?OnCmaOrInstallCompleted@DownloadInstance@Lpd@LPA@@AEAAXJW4CmaOrInstallCompletion@123@@Z; LPA::Lpd::DownloadInstance::OnCmaOrInstallCompleted(long,LPA::Lpd::DownloadInstance::CmaOrInstallCompletion)
0x1800b46fd  nop
0x1800b46fe  mov     rcx, [rbp+4Fh+arg_20]
0x1800b4702  mov     rbx, [rsp+0B0h+arg_10]
0x1800b470a  add     rsp, 90h
0x1800b4711  pop     r15
0x1800b4713  pop     r12
0x1800b4715  pop     rdi
0x1800b4716  pop     rsi
0x1800b4717  pop     rbp
0x1800b4718  jmp     ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
```
