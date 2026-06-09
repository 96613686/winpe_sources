# CmsCreateProcessInContainer

- ea: `0x1800079d0`
- end: `0x180007cec`
- name: `CmsCreateProcessInContainer`
- size: `796`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x18000a430`
- `0x18000a990`

## callees

- `0x180001550`
- `0x180001574`
- `0x180001944`
- `0x1800021dc`
- `0x180002748`
- `0x180003c74`
- `0x18000639c`
- `0x1800066e4`
- `0x180007044`
- `0x1800079d0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007bb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007bcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007bdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007bb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007bcb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007bdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007c9c`

## string_xrefs

- `0x180007b14`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180007b7d`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180007b95`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180007caa`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsCreateProcessInContainer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        HANDLE *a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7)
{
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  int v12; // eax
  int v13; // eax
  int v14; // esi
  HANDLE v15; // rcx
  bool v16; // cc
  __int64 v17; // rax
  int v18; // eax
  void *v19; // rdi
  HANDLE v21; // rax
  char *v22; // rcx
  HANDLE v23; // rax
  char *v24; // rdx
  int v25; // [rsp+20h] [rbp-A1h]
  int v26; // [rsp+20h] [rbp-A1h]
  int v27; // [rsp+50h] [rbp-71h] BYREF
  HANDLE v28; // [rsp+58h] [rbp-69h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-61h] BYREF
  HANDLE v30; // [rsp+68h] [rbp-59h] BYREF
  int v31; // [rsp+70h] [rbp-51h] BYREF
  __int64 v32; // [rsp+78h] [rbp-49h] BYREF
  __int64 *v33; // [rsp+80h] [rbp-41h] BYREF
  __int64 *v34; // [rsp+88h] [rbp-39h] BYREF
  int *v35; // [rsp+90h] [rbp-31h] BYREF
  HANDLE *p_hObject; // [rsp+98h] [rbp-29h] BYREF
  HANDLE *v37; // [rsp+A0h] [rbp-21h] BYREF
  HANDLE *v38; // [rsp+A8h] [rbp-19h] BYREF
  int v39[2]; // [rsp+B0h] [rbp-11h] BYREF
  __int64 v40; // [rsp+B8h] [rbp-9h] BYREF
  _WNF_STATE_NAME v41; // [rsp+C0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  v40 = a2;
  v10 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( !v10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x304,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)0x8007000ELL,
      v25);
    return 2147942414LL;
  }
  *v10 = 0;
  *((_DWORD *)v10 + 2) = 0;
  v10[2] = 0;
  *((_DWORD *)v10 + 6) = 0;
  *((_DWORD *)v10 + 7) = 259;
  v10[4] = 0;
  v27 = 0;
  if ( a4 )
  {
    v12 = 1;
    v27 = 1;
  }
  else
  {
    v12 = 0;
  }
  if ( a5 )
  {
    v12 |= 2u;
    v27 = v12;
  }
  if ( a6 )
    v27 = v12 | 4;
  v32 = 0;
  v34 = &v32;
  v41 = 0;
  v35 = &v31;
  v31 = 0;
  p_hObject = &hObject;
  hObject = 0;
  v37 = &v28;
  v38 = &v30;
  *(_QWORD *)v39 = &v41;
  v33 = *(__int64 **)(a1 + 8);
  v28 = 0;
  v30 = 0;
  v13 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_PROCESS_PROPERTIES *,enum _CMS_PROCESS_CREATION_FLAGS,_WNF_STATE_NAME *,void * *,void * *,void * *,unsigned long *,void * *),void *,_CMS_PROCESS_PROPERTIES * &,enum _CMS_PROCESS_CREATION_FLAGS &,_WNF_STATE_NAME *,void * *,void * *,void * *,unsigned long *,void * *>(
          0,
          (unsigned int)&v33,
          (unsigned int)&v40,
          (unsigned int)&v27,
          (__int64)v39,
          (__int64)&v38,
          (__int64)&v37,
          (__int64)&p_hObject,
          (__int64)&v35,
          (__int64)&v34);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x322,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v13,
      v26);
    v15 = hObject;
    v16 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_15:
    if ( v16 )
      CloseHandle(v15);
    if ( (char *)v28 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v28);
    if ( (char *)v30 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v30);
    v19 = (void *)v11[4];
    v11[4] = 0;
    if ( v19 )
    {
      Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(v19);
      operator delete(v19, (const struct std::nothrow_t *)0x18);
    }
    operator delete(v11, (const struct std::nothrow_t *)0x28);
    return (unsigned int)v14;
  }
  v17 = v32;
  *((_DWORD *)v11 + 2) = v31;
  *v11 = v17;
  v11[2] = a3;
  v14 = Container::Manager::Client::Process::RegisterForNotifications((Container::Manager::Client::Process *)v11, &v41);
  if ( v14 < 0 )
  {
    v33 = &v32;
    v18 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(CmsRpcClt_CloseProcess, &v33);
    if ( v18 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x32C,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
        (const char *)(unsigned int)v18,
        v26);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)(unsigned int)v14,
      v26);
    v15 = hObject;
    v16 = (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_15;
  }
  if ( a4 )
  {
    *a4 = v30;
    v30 = 0;
  }
  if ( a5 )
  {
    v21 = v28;
    v22 = 0;
    v28 = 0;
    *a5 = v21;
  }
  else
  {
    v22 = (char *)v28;
  }
  if ( a6 )
  {
    v23 = hObject;
    v24 = 0;
    hObject = 0;
    *a6 = v23;
  }
  else
  {
    v24 = (char *)hObject;
  }
  *a7 = v11;
  if ( (unsigned __int64)(v24 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v24);
    v22 = (char *)v28;
  }
  if ( (unsigned __int64)(v22 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v22);
  if ( (char *)v30 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v30);
  return 0;
}

```

## disassembly

```asm
0x1800079d0  mov     [rsp-8+arg_10], rbx
0x1800079d5  push    rbp
0x1800079d6  push    rsi
0x1800079d7  push    rdi
0x1800079d8  push    r12
0x1800079da  push    r13
0x1800079dc  push    r14
0x1800079de  push    r15
0x1800079e0  lea     rbp, [rsp-0Fh]
0x1800079e5  sub     rsp, 0D0h
0x1800079ec  mov     rax, cs:__security_cookie
0x1800079f3  xor     rax, rsp
0x1800079f6  mov     [rbp+3Fh+var_38], rax
0x1800079fa  mov     r14, [rbp+3Fh+arg_20]
0x1800079fe  mov     rsi, rcx
0x180007a01  mov     r15, [rbp+3Fh+arg_28]
0x180007a05  mov     ecx, 28h ; '('; unsigned __int64
0x180007a0a  mov     r13, [rbp+3Fh+arg_30]
0x180007a0e  mov     rdi, r9
0x180007a11  mov     [rbp+3Fh+var_48], rdx
0x180007a15  mov     r12, r8
0x180007a18  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007a1f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007a24  xor     ecx, ecx
0x180007a26  mov     rbx, rax
0x180007a29  test    rax, rax
0x180007a2c  jz      loc_180007CA6
0x180007a32  mov     [rax], rcx
0x180007a35  mov     [rax+8], ecx
0x180007a38  mov     [rax+10h], rcx
0x180007a3c  mov     [rax+18h], ecx
0x180007a3f  mov     dword ptr [rax+1Ch], 103h
0x180007a46  mov     [rax+20h], rcx
0x180007a4a  mov     [rbp+3Fh+var_B0], ecx
0x180007a4d  test    rdi, rdi
0x180007a50  jnz     short loc_180007A56
0x180007a52  mov     eax, ecx
0x180007a54  jmp     short loc_180007A5E
0x180007a56  mov     eax, 1
0x180007a5b  mov     [rbp+3Fh+var_B0], eax
0x180007a5e  test    r14, r14
0x180007a61  jz      short loc_180007A69
0x180007a63  or      eax, 2
0x180007a66  mov     [rbp+3Fh+var_B0], eax
0x180007a69  test    r15, r15
0x180007a6c  jz      short loc_180007A74
0x180007a6e  or      eax, 4
0x180007a71  mov     [rbp+3Fh+var_B0], eax
0x180007a74  lea     rax, [rbp+3Fh+var_88]
0x180007a78  mov     [rbp+3Fh+var_88], rcx
0x180007a7c  mov     [rbp+3Fh+var_78], rax
0x180007a80  lea     r9, [rbp+3Fh+var_B0]
0x180007a84  lea     rax, [rbp+3Fh+var_90]
0x180007a88  mov     qword ptr [rbp+3Fh+var_40.Data], rcx
0x180007a8c  mov     [rbp+3Fh+var_70], rax
0x180007a90  lea     r8, [rbp+3Fh+var_48]
0x180007a94  lea     rax, [rbp+3Fh+hObject]
0x180007a98  mov     [rbp+3Fh+var_90], ecx
0x180007a9b  mov     [rbp+3Fh+var_68], rax
0x180007a9f  lea     rdx, [rbp+3Fh+var_80]
0x180007aa3  lea     rax, [rbp+3Fh+var_A8]
0x180007aa7  mov     [rbp+3Fh+hObject], rcx
0x180007aab  mov     [rbp+3Fh+var_60], rax
0x180007aaf  lea     rax, [rbp+3Fh+var_98]
0x180007ab3  mov     [rbp+3Fh+var_58], rax
0x180007ab7  lea     rax, [rbp+3Fh+var_40]
0x180007abb  mov     qword ptr [rbp+3Fh+var_50], rax
0x180007abf  mov     rax, [rsi+8]
0x180007ac3  mov     [rbp+3Fh+var_80], rax
0x180007ac7  lea     rax, [rbp+3Fh+var_78]
0x180007acb  mov     [rsp+100h+var_B8], rax
0x180007ad0  lea     rax, [rbp+3Fh+var_70]
0x180007ad4  mov     [rsp+100h+var_C0], rax
0x180007ad9  lea     rax, [rbp+3Fh+var_68]
0x180007add  mov     [rsp+100h+var_C8], rax
0x180007ae2  lea     rax, [rbp+3Fh+var_60]
0x180007ae6  mov     [rsp+100h+var_D0], rax
0x180007aeb  lea     rax, [rbp+3Fh+var_58]
0x180007aef  mov     [rsp+100h+var_D8], rax
0x180007af4  lea     rax, [rbp+3Fh+var_50]
0x180007af8  mov     qword ptr [rsp+100h+var_E0], rax; int
0x180007afd  mov     [rbp+3Fh+var_A8], rcx
0x180007b01  mov     [rbp+3Fh+var_98], rcx
0x180007b05  call    ??$InvokeStubFunction@P6AJPEAXPEAU_CMS_PROCESS_PROPERTIES@@W4_CMS_PROCESS_CREATION_FLAGS@@PEAU_WNF_STATE_NAME@@PEAPEAX44PEAK4@ZPEAXAEAPEAU1@AEAW42@PEAU3@PEAPEAXPEAPEAXPEAPEAXPEAKPEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_CMS_PROCESS_PROPERTIES@@W4_CMS_PROCESS_CREATION_FLAGS@@PEAU_WNF_STATE_NAME@@PEAPEAX44PEAK4@Z$$QEAPEAXAEAPEAU3@AEAW44@$$QEAPEAU5@$$QEAPEAPEAX$$QEAPEAPEAX$$QEAPEAPEAX$$QEAPEAK$$QEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_PROCESS_PROPERTIES *,_CMS_PROCESS_CREATION_FLAGS,_WNF_STATE_NAME *,void * *,void * *,void * *,ulong *,void * *),void *,_CMS_PROCESS_PROPERTIES * &,_CMS_PROCESS_CREATION_FLAGS &,_WNF_STATE_NAME *,void * *,void * *,void * *,ulong *,void * *>(long (*)(void *,_CMS_PROCESS_PROPERTIES *,_CMS_PROCESS_CREATION_FLAGS,_WNF_STATE_NAME *,void * *,void * *,void * *,ulong *,void * *),void * &&,_CMS_PROCESS_PROPERTIES * &,_CMS_PROCESS_CREATION_FLAGS &,_WNF_STATE_NAME * &&,void * * &&,void * * &&,void * * &&,ulong * &&,void * * &&)
0x180007b0a  mov     esi, eax
0x180007b0c  test    eax, eax
0x180007b0e  jns     short loc_180007B36
0x180007b10  mov     rcx, [rbp+47h]; this
0x180007b14  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007b1b  mov     r9d, eax; char *
0x180007b1e  mov     edx, 322h; void *
0x180007b23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b28  mov     rcx, [rbp+3Fh+hObject]
0x180007b2c  lea     rdx, [rcx-1]
0x180007b30  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180007b34  jmp     short loc_180007BB5
0x180007b36  mov     ecx, [rbp+3Fh+var_90]
0x180007b39  lea     rdx, [rbp+3Fh+var_40]; struct _WNF_STATE_NAME *
0x180007b3d  mov     rax, [rbp+3Fh+var_88]
0x180007b41  mov     [rbx+8], ecx
0x180007b44  mov     rcx, rbx; this
0x180007b47  mov     [rbx], rax
0x180007b4a  mov     [rbx+10h], r12
0x180007b4e  call    ?RegisterForNotifications@Process@Client@Manager@Container@@QEAAJAEBU_WNF_STATE_NAME@@@Z; Container::Manager::Client::Process::RegisterForNotifications(_WNF_STATE_NAME const &)
0x180007b53  mov     esi, eax
0x180007b55  test    eax, eax
0x180007b57  jns     loc_180007C1F
0x180007b5d  lea     rax, [rbp+3Fh+var_88]
0x180007b61  lea     rdx, [rbp+3Fh+var_80]
0x180007b65  mov     [rbp+3Fh+var_80], rax
0x180007b69  lea     rcx, CmsRpcClt_CloseProcess
0x180007b70  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x180007b75  test    eax, eax
0x180007b77  jns     short loc_180007B91
0x180007b79  mov     rcx, [rbp+47h]; this
0x180007b7d  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007b84  mov     r9d, eax; char *
0x180007b87  mov     edx, 32Ch; void *
0x180007b8c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007b91  mov     rcx, [rbp+47h]; this
0x180007b95  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007b9c  mov     r9d, esi; char *
0x180007b9f  mov     edx, 32Eh; void *
0x180007ba4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ba9  mov     rcx, [rbp+3Fh+hObject]; hObject
0x180007bad  lea     rax, [rcx-1]
0x180007bb1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007bb5  ja      short loc_180007BBD
0x180007bb7  call    cs:__imp_CloseHandle
0x180007bbd  mov     rcx, [rbp+3Fh+var_A8]; hObject
0x180007bc1  lea     rax, [rcx-1]
0x180007bc5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007bc9  ja      short loc_180007BD1
0x180007bcb  call    cs:__imp_CloseHandle
0x180007bd1  mov     rcx, [rbp+3Fh+var_98]; hObject
0x180007bd5  lea     rax, [rcx-1]
0x180007bd9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007bdd  ja      short loc_180007BE5
0x180007bdf  call    cs:__imp_CloseHandle
0x180007be5  mov     rdi, [rbx+20h]
0x180007be9  mov     qword ptr [rbx+20h], 0
0x180007bf1  test    rdi, rdi
0x180007bf4  jz      short loc_180007C0B
0x180007bf6  mov     rcx, rdi
0x180007bf9  call    ??1?$OutOfProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAA@XZ; Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(void)
0x180007bfe  mov     edx, 18h; struct std::nothrow_t *
0x180007c03  mov     rcx, rdi; void *
0x180007c06  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007c0b  mov     edx, 28h ; '('; struct std::nothrow_t *
0x180007c10  mov     rcx, rbx; void *
0x180007c13  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007c18  mov     eax, esi
0x180007c1a  jmp     loc_180007CC5
0x180007c1f  test    rdi, rdi
0x180007c22  jz      short loc_180007C33
0x180007c24  mov     rax, [rbp+3Fh+var_98]
0x180007c28  mov     [rdi], rax
0x180007c2b  mov     [rbp+3Fh+var_98], 0
0x180007c33  test    r14, r14
0x180007c36  jz      short loc_180007C47
0x180007c38  mov     rax, [rbp+3Fh+var_A8]
0x180007c3c  xor     ecx, ecx
0x180007c3e  mov     [rbp+3Fh+var_A8], rcx
0x180007c42  mov     [r14], rax
0x180007c45  jmp     short loc_180007C4B
0x180007c47  mov     rcx, [rbp+3Fh+var_A8]
0x180007c4b  test    r15, r15
0x180007c4e  jz      short loc_180007C5F
0x180007c50  mov     rax, [rbp+3Fh+hObject]
0x180007c54  xor     edx, edx
0x180007c56  mov     [rbp+3Fh+hObject], rdx
0x180007c5a  mov     [r15], rax
0x180007c5d  jmp     short loc_180007C63
0x180007c5f  mov     rdx, [rbp+3Fh+hObject]
0x180007c63  lea     rax, [rdx-1]
0x180007c67  mov     [r13+0], rbx
0x180007c6b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007c6f  ja      short loc_180007C7E
0x180007c71  mov     rcx, rdx; hObject
0x180007c74  call    cs:__imp_CloseHandle
0x180007c7a  mov     rcx, [rbp+3Fh+var_A8]; hObject
0x180007c7e  lea     rax, [rcx-1]
0x180007c82  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007c86  ja      short loc_180007C8E
0x180007c88  call    cs:__imp_CloseHandle
0x180007c8e  mov     rcx, [rbp+3Fh+var_98]; hObject
0x180007c92  lea     rax, [rcx-1]
0x180007c96  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007c9a  ja      short loc_180007CA2
0x180007c9c  call    cs:__imp_CloseHandle
0x180007ca2  xor     eax, eax
0x180007ca4  jmp     short loc_180007CC5
0x180007ca6  mov     rcx, [rbp+47h]; this
0x180007caa  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180007cb1  mov     ebx, 8007000Eh
0x180007cb6  mov     edx, 304h; void *
0x180007cbb  mov     r9d, ebx; char *
0x180007cbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007cc3  mov     eax, ebx
0x180007cc5  mov     rcx, [rbp+3Fh+var_38]
0x180007cc9  xor     rcx, rsp; StackCookie
0x180007ccc  call    __security_check_cookie
0x180007cd1  mov     rbx, [rsp+100h+arg_10]
0x180007cd9  add     rsp, 0D0h
0x180007ce0  pop     r15
0x180007ce2  pop     r14
0x180007ce4  pop     r13
0x180007ce6  pop     r12
0x180007ce8  pop     rdi
0x180007ce9  pop     rsi
0x180007cea  pop     rbp
0x180007ceb  retn
```
