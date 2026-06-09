# OnEnumCeremoniesCompleteStub(ulong,_CEREMONY const *,long,void *)

- ea: `0x180030dac`
- end: `0x180031250`
- name: `?OnEnumCeremoniesCompleteStub@@YAJKPEBU_CEREMONY@@JPEAX@Z`
- size: `1188`
- prototype: `__int64 __fastcall(unsigned int, const struct _CEREMONY *, int, void *)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180054cc4`
- `0x180056ca0`
- `0x180063a80`

## callees

- `0x1800074c0`
- `0x180008a50`
- `0x18001eae0`
- `0x18002a948`
- `0x1800306d8`
- `0x180030dac`
- `0x180031f24`
- `0x180033470`
- `0x1800335bc`
- `0x1800345f0`
- `0x18003bc80`
- `0x18003c79c`
- `0x180045df0`
- `0x180046ef0`
- `0x1800548a8`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030ff0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031013`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800310dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030ff0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031013`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800310dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030e6b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030e6b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800310d2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800310d2`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180031095`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180031095`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180030e02`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180030e02`

## string_xrefs

- `0x180030e47`: `onecore\base\devices\association\service\lib\associationcontext.cpp`
- `0x1800311d7`: `onecore\base\devices\association\service\lib\associationcontext.cpp`

## pseudocode

```c
__int64 __fastcall OnEnumCeremoniesCompleteStub(unsigned int a1, const struct _CEREMONY *a2, int a3, char *a4)
{
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // edi
  DWORD v10; // r12d
  int v11; // r8d
  int v12; // ecx
  bool v13; // zf
  __int64 v14; // rax
  const wchar_t **v15; // rax
  const wchar_t *v16; // rax
  int v17; // eax
  int v18; // edx
  __int64 v19; // rcx
  int v20; // edx
  int v21; // r8d
  int v22; // eax
  __int64 v23; // rcx
  bool v24; // sf
  char *p_Reply; // rdx
  int v26; // edi
  int v27; // edx
  int v28; // r8d
  int ProcessName; // eax
  int v30; // ecx
  int MessageGuid; // [rsp+20h] [rbp-E0h]
  char v33[4]; // [rsp+50h] [rbp-B0h] BYREF
  int Reply; // [rsp+58h] [rbp-A8h] BYREF
  void *v35; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int NotificationsQueued; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  Reply = a3;
  *(_DWORD *)v33 = 0;
  v35 = 0;
  EventActivityIdControl(2u, (LPGUID)(a4 + 348));
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
    McTemplateU0p_EventWriteTransfer(v7, ASSOC_ENUM_PROVIDER_STOP, a4);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v35,
    0);
  v8 = DafStringCopy(*((_QWORD *)a4 + 1), &v35);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B0,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\associationcontext.cpp",
      (const char *)(unsigned int)v8,
      MessageGuid);
    goto LABEL_56;
  }
  v10 = *((_DWORD *)a4 + 16);
  AcquireSRWLockExclusive((PSRWLOCK)a4 + 6);
  v12 = Reply;
  v13 = Reply == 0;
  if ( Reply < 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v14 = *((_QWORD *)a4 + 46);
      if ( !v14 || (v15 = *(const wchar_t ***)(v14 + 24)) == 0 || (v16 = *v15) == 0 )
        v16 = L"unknown";
      WPP_RECORDER_SF_SSqD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)&WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        v11,
        129,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *((_QWORD *)a4 + 1),
        (__int64)v16,
        (char)a4,
        Reply);
      v12 = Reply;
    }
    v13 = v12 == 0;
  }
  if ( v13 && a1 && !*((_DWORD *)a4 + 9) )
  {
    v17 = CopyCermonies(
            *((_DWORD *)a4 + 95),
            *((const struct _CEREMONY **)a4 + 48),
            a1,
            a2,
            *((unsigned int **)a4 + 15),
            *((struct _CEREMONY ***)a4 + 16));
    *(_DWORD *)v33 = v17;
    v18 = v17;
    if ( v17 >= 0 || *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    {
      v12 = Reply;
      goto LABEL_21;
    }
    WPP_RECORDER_SF_SqD(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v17,
      v11,
      130,
      &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      *((_QWORD *)a4 + 1),
      (char)a4,
      v17);
    v12 = Reply;
  }
  v18 = *(_DWORD *)v33;
LABEL_21:
  if ( *((_DWORD *)a4 + 10) )
  {
    *((_DWORD *)a4 + 7) = -1;
    *(_DWORD *)v33 = -2147416294;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_SqD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v18,
        v11,
        131,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *((_QWORD *)a4 + 1),
        (char)a4,
        26);
    *((_DWORD *)a4 + 10) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)a4 + 6);
  }
  else
  {
    if ( *((_DWORD *)a4 + 9) )
    {
      *(_DWORD *)v33 = -2147418113;
      *((_DWORD *)a4 + 7) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)a4 + 6);
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v20,
          v21,
          132,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a4 + 1),
          (char)a4,
          v33[0]);
      goto LABEL_49;
    }
    if ( v18 || v12 )
      v22 = -1;
    else
      v22 = 2;
    *((_DWORD *)a4 + 7) = v22;
    if ( *((_DWORD *)a4 + 94) )
    {
      v23 = *((_QWORD *)a4 + 25);
      NotificationsQueued = 0;
      RpcServerUnsubscribeForNotification(
        *(RPC_BINDING_HANDLE *)(v23 + 32),
        RpcNotificationCallCancel,
        &NotificationsQueued);
      (*(void (__fastcall **)(char *))(*(_QWORD *)a4 + 16LL))(a4);
      v18 = *(_DWORD *)v33;
      v12 = Reply;
    }
    *((_DWORD *)a4 + 9) = 1;
    if ( v12 < 0 || (v24 = v18 < 0, p_Reply = v33, !v24) )
      p_Reply = (char *)&Reply;
    v26 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)a4 + 25), p_Reply);
    ReleaseSRWLockExclusive((PSRWLOCK)a4 + 6);
    if ( !v26 || v26 == 1818 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Sq(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v27,
          v28,
          134,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a4 + 1),
          (char)a4);
    }
    else
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v27,
          v28,
          133,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a4 + 1),
          (char)a4,
          v26);
      if ( v26 >= 0 )
        v26 = (unsigned __int16)v26 | 0x80010000;
      *(_DWORD *)v33 = v26;
    }
  }
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
    McTemplateU0p_EventWriteTransfer(v19, ASSOC_ENUM_STOP, a4);
  (*(void (__fastcall **)(char *))(*(_QWORD *)a4 + 16LL))(a4);
LABEL_49:
  if ( *(int *)v33 < 0 || Reply < 0 )
  {
    memset_0(Filename, 0, 0x208u);
    ProcessName = GetProcessName(v10, Filename);
    if ( ProcessName < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9FA,
        (int)"onecore\\base\\devices\\association\\service\\lib\\associationcontext.cpp",
        (const char *)(unsigned int)ProcessName);
    if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 2) != 0 )
      McTemplateU0zzqqq_EventWriteTransfer(
        v30,
        (unsigned int)ASSOCIATION_FAILURE_ENUM_CEREMONIES,
        (_DWORD)v35,
        (unsigned int)Filename,
        v10,
        v33[0],
        Reply);
  }
  v9 = *(_DWORD *)v33;
LABEL_56:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
  return v9;
}

```

## disassembly

```asm
0x180030dac  push    rbp
0x180030dae  push    rbx
0x180030daf  push    rsi
0x180030db0  push    rdi
0x180030db1  push    r12
0x180030db3  push    r14
0x180030db5  push    r15
0x180030db7  lea     rbp, [rsp-190h]
0x180030dbf  sub     rsp, 290h
0x180030dc6  mov     rax, cs:__security_cookie
0x180030dcd  xor     rax, rsp
0x180030dd0  mov     [rbp+1C0h+var_40], rax
0x180030dd7  mov     r15, rdx
0x180030dda  mov     [rsp+2C0h+Reply], r8d
0x180030ddf  mov     r14d, ecx
0x180030de2  mov     dword ptr [rsp+2C0h+var_270], 0
0x180030dea  lea     rdx, [r9+15Ch]; ActivityId
0x180030df1  mov     [rsp+2C0h+var_260], 0
0x180030dfa  mov     ecx, 2; ControlCode
0x180030dff  mov     rbx, r9
0x180030e02  call    cs:__imp_EventActivityIdControl
0x180030e08  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 10h
0x180030e0f  jz      short loc_180030E20
0x180030e11  mov     r8, rbx
0x180030e14  lea     rdx, ASSOC_ENUM_PROVIDER_STOP
0x180030e1b  call    McTemplateU0p_EventWriteTransfer
0x180030e20  xor     edx, edx
0x180030e22  lea     rcx, [rsp+2C0h+var_260]
0x180030e27  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180030e2c  mov     rcx, [rbx+8]
0x180030e30  lea     rdx, [rsp+2C0h+var_260]
0x180030e35  call    DafStringCopy
0x180030e3a  mov     edi, eax
0x180030e3c  test    eax, eax
0x180030e3e  jns     short loc_180030E60
0x180030e40  mov     rcx, [rbp+1C8h]; this
0x180030e47  lea     r8, aOnecoreBaseDev_14; "onecore\\base\\devices\\association\\se"...
0x180030e4e  mov     r9d, eax; char *
0x180030e51  mov     edx, 9B0h; void *
0x180030e56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030e5b  jmp     loc_180031223
0x180030e60  mov     r12d, [rbx+40h]
0x180030e64  lea     rsi, [rbx+30h]
0x180030e68  mov     rcx, rsi; SRWLock
0x180030e6b  call    cs:__imp_AcquireSRWLockExclusive
0x180030e71  mov     ecx, [rsp+2C0h+Reply]
0x180030e75  lea     rdx, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids; int
0x180030e7c  lea     rdi, WPP_RECORDER_INITIALIZED
0x180030e83  test    ecx, ecx
0x180030e85  jns     short loc_180030EEC
0x180030e87  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180030e8e  jz      short loc_180030EEA
0x180030e90  mov     rax, [rbx+170h]
0x180030e97  test    rax, rax
0x180030e9a  jz      short loc_180030EAD
0x180030e9c  mov     rax, [rax+18h]
0x180030ea0  test    rax, rax
0x180030ea3  jz      short loc_180030EAD
0x180030ea5  mov     rax, [rax]
0x180030ea8  test    rax, rax
0x180030eab  jnz     short loc_180030EB4
0x180030ead  lea     rax, aUnknown_0; "unknown"
0x180030eb4  mov     dword ptr [rsp+2C0h+var_280], ecx; char
0x180030eb8  mov     r9d, 81h; int
0x180030ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ec5  mov     qword ptr [rsp+2C0h+var_288], rbx; char
0x180030eca  mov     qword ptr [rsp+2C0h+var_290], rax; __int64
0x180030ecf  mov     rax, [rbx+8]
0x180030ed3  mov     rcx, [rcx+28h]; int
0x180030ed7  mov     [rsp+2C0h+var_298], rax; __int64
0x180030edc  mov     [rsp+2C0h+MessageGuid], rdx; MessageGuid
0x180030ee1  call    WPP_RECORDER_SF_SSqD
0x180030ee6  mov     ecx, [rsp+2C0h+Reply]
0x180030eea  test    ecx, ecx
0x180030eec  jnz     loc_180030F8C
0x180030ef2  test    r14d, r14d
0x180030ef5  jz      loc_180030F8C
0x180030efb  cmp     dword ptr [rbx+24h], 0
0x180030eff  jnz     loc_180030F8C
0x180030f05  mov     rax, [rbx+80h]
0x180030f0c  mov     r9, r15; struct _CEREMONY *
0x180030f0f  mov     rdx, [rbx+180h]; struct _CEREMONY *
0x180030f16  mov     r8d, r14d; unsigned int
0x180030f19  mov     ecx, [rbx+17Ch]; unsigned int
0x180030f1f  mov     [rsp+2C0h+var_298], rax; struct _CEREMONY **
0x180030f24  mov     rax, [rbx+78h]
0x180030f28  mov     [rsp+2C0h+MessageGuid], rax; unsigned int *
0x180030f2d  call    ?CopyCermonies@@YAJKPEBU_CEREMONY@@K0PEAKPEAPEAU1@@Z; CopyCermonies(ulong,_CEREMONY const *,ulong,_CEREMONY const *,ulong *,_CEREMONY * *)
0x180030f32  mov     dword ptr [rsp+2C0h+var_270], eax
0x180030f36  mov     edx, eax; int
0x180030f38  test    eax, eax
0x180030f3a  jns     short loc_180030F7F
0x180030f3c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180030f43  jz      short loc_180030F7F
0x180030f45  mov     rcx, cs:WPP_GLOBAL_Control
0x180030f4c  lea     r14, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x180030f53  mov     dword ptr [rsp+2C0h+var_288], eax; char
0x180030f57  mov     r9d, 82h; int
0x180030f5d  mov     rax, [rbx+8]
0x180030f61  mov     qword ptr [rsp+2C0h+var_290], rbx; char
0x180030f66  mov     rcx, [rcx+28h]; int
0x180030f6a  mov     [rsp+2C0h+var_298], rax; __int64
0x180030f6f  mov     [rsp+2C0h+MessageGuid], r14; MessageGuid
0x180030f74  call    WPP_RECORDER_SF_SqD
0x180030f79  mov     ecx, [rsp+2C0h+Reply]
0x180030f7d  jmp     short loc_180030F93
0x180030f7f  mov     ecx, [rsp+2C0h+Reply]
0x180030f83  lea     r14, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x180030f8a  jmp     short loc_180030F97
0x180030f8c  lea     r14, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x180030f93  mov     edx, dword ptr [rsp+2C0h+var_270]; int
0x180030f97  cmp     dword ptr [rbx+28h], 0
0x180030f9b  jz      short loc_180030FFB
0x180030f9d  mov     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x180030fa4  mov     dword ptr [rsp+2C0h+var_270], 8001071Ah
0x180030fac  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180030fb3  jz      short loc_180030FE6
0x180030fb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180030fbc  mov     r9d, 83h; int
0x180030fc2  mov     rax, [rbx+8]
0x180030fc6  mov     dword ptr [rsp+2C0h+var_288], 8001071Ah; char
0x180030fce  mov     qword ptr [rsp+2C0h+var_290], rbx; char
0x180030fd3  mov     rcx, [rcx+28h]; int
0x180030fd7  mov     [rsp+2C0h+var_298], rax; __int64
0x180030fdc  mov     [rsp+2C0h+MessageGuid], r14; MessageGuid
0x180030fe1  call    WPP_RECORDER_SF_SqD
0x180030fe6  mov     rcx, rsi; SRWLock
0x180030fe9  mov     dword ptr [rbx+28h], 0
0x180030ff0  call    cs:__imp_ReleaseSRWLockExclusive
0x180030ff6  jmp     loc_180031178
0x180030ffb  cmp     dword ptr [rbx+24h], 0
0x180030fff  jz      short loc_18003105C
0x180031001  mov     rcx, rsi; SRWLock
0x180031004  mov     dword ptr [rsp+2C0h+var_270], 8000FFFFh
0x18003100c  mov     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x180031013  call    cs:__imp_ReleaseSRWLockExclusive
0x180031019  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x180031020  jz      loc_18003119F
0x180031026  mov     eax, dword ptr [rsp+2C0h+var_270]
0x18003102a  mov     r9d, 84h; int
0x180031030  mov     rcx, cs:WPP_GLOBAL_Control
0x180031037  mov     dword ptr [rsp+2C0h+var_288], eax; char
0x18003103b  mov     rax, [rbx+8]
0x18003103f  mov     qword ptr [rsp+2C0h+var_290], rbx; char
0x180031044  mov     rcx, [rcx+28h]; int
0x180031048  mov     [rsp+2C0h+var_298], rax; __int64
0x18003104d  mov     [rsp+2C0h+MessageGuid], r14; MessageGuid
0x180031052  call    WPP_RECORDER_SF_SqD
0x180031057  jmp     loc_18003119F
0x18003105c  test    edx, edx
0x18003105e  jnz     short loc_180031069
0x180031060  test    ecx, ecx
0x180031062  jnz     short loc_180031069
0x180031064  lea     eax, [rdx+2]
0x180031067  jmp     short loc_18003106C
0x180031069  or      eax, 0FFFFFFFFh
0x18003106c  mov     [rbx+1Ch], eax
0x18003106f  cmp     dword ptr [rbx+178h], 0
0x180031076  jz      short loc_1800310B2
0x180031078  mov     rcx, [rbx+0C8h]
0x18003107f  lea     r8, [rsp+2C0h+NotificationsQueued]; NotificationsQueued
0x180031084  mov     edx, 2; Notification
0x180031089  mov     [rsp+2C0h+NotificationsQueued], 0
0x180031091  mov     rcx, [rcx+20h]; Binding
0x180031095  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18003109b  mov     rax, [rbx]
0x18003109e  mov     rcx, rbx
0x1800310a1  mov     rax, [rax+10h]
0x1800310a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310aa  mov     edx, dword ptr [rsp+2C0h+var_270]
0x1800310ae  mov     ecx, [rsp+2C0h+Reply]
0x1800310b2  mov     dword ptr [rbx+24h], 1
0x1800310b9  test    ecx, ecx
0x1800310bb  js      short loc_1800310C6
0x1800310bd  test    edx, edx
0x1800310bf  lea     rdx, [rsp+2C0h+var_270]
0x1800310c4  js      short loc_1800310CB
0x1800310c6  lea     rdx, [rsp+2C0h+Reply]; Reply
0x1800310cb  mov     rcx, [rbx+0C8h]; pAsync
0x1800310d2  call    cs:__imp_RpcAsyncCompleteCall
0x1800310d8  mov     rcx, rsi; SRWLock
0x1800310db  mov     edi, eax
0x1800310dd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800310e3  test    edi, edi
0x1800310e5  jz      short loc_18003113F
0x1800310e7  cmp     edi, 71Ah
0x1800310ed  jz      short loc_18003113F
0x1800310ef  lea     rax, WPP_RECORDER_INITIALIZED
0x1800310f6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800310fd  jz      short loc_18003112C
0x1800310ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180031106  mov     r9d, 85h; int
0x18003110c  mov     rax, [rbx+8]
0x180031110  mov     dword ptr [rsp+2C0h+var_288], edi; char
0x180031114  mov     qword ptr [rsp+2C0h+var_290], rbx; char
0x180031119  mov     rcx, [rcx+28h]; int
0x18003111d  mov     [rsp+2C0h+var_298], rax; __int64
0x180031122  mov     [rsp+2C0h+MessageGuid], r14; MessageGuid
0x180031127  call    WPP_RECORDER_SF_SqD
0x18003112c  test    edi, edi
0x18003112e  js      short loc_180031139
0x180031130  movzx   edi, di
0x180031133  or      edi, 80010000h
0x180031139  mov     dword ptr [rsp+2C0h+var_270], edi
0x18003113d  jmp     short loc_180031178
0x18003113f  lea     rax, WPP_RECORDER_INITIALIZED
0x180031146  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003114d  jz      short loc_180031178
0x18003114f  mov     rcx, cs:WPP_GLOBAL_Control
0x180031156  mov     r9d, 86h; int
0x18003115c  mov     rax, [rbx+8]
0x180031160  mov     qword ptr [rsp+2C0h+var_290], rbx; char
0x180031165  mov     [rsp+2C0h+var_298], rax; __int64
0x18003116a  mov     rcx, [rcx+28h]; int
0x18003116e  mov     [rsp+2C0h+MessageGuid], r14; int
0x180031173  call    WPP_RECORDER_SF_Sq
0x180031178  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 10h
0x18003117f  jz      short loc_180031190
0x180031181  mov     r8, rbx
0x180031184  lea     rdx, ASSOC_ENUM_STOP
0x18003118b  call    McTemplateU0p_EventWriteTransfer
0x180031190  mov     rax, [rbx]
0x180031193  mov     rcx, rbx
0x180031196  mov     rax, [rax+10h]
0x18003119a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003119f  cmp     dword ptr [rsp+2C0h+var_270], 0
0x1800311a4  jl      short loc_1800311AD
0x1800311a6  cmp     [rsp+2C0h+Reply], 0
0x1800311ab  jge     short loc_18003121F
0x1800311ad  xor     edx, edx; Val
0x1800311af  lea     rcx, [rsp+2C0h+Filename]; void *
0x1800311b4  mov     r8d, 208h; Size
0x1800311ba  call    memset_0
0x1800311bf  lea     rdx, [rsp+2C0h+Filename]; lpFilename
0x1800311c4  mov     ecx, r12d; dwProcessId
0x1800311c7  call    ?GetProcessName@@YAJKQEAG@Z; GetProcessName(ulong,ushort * const)
0x1800311cc  test    eax, eax
0x1800311ce  jns     short loc_1800311EB
0x1800311d0  mov     rcx, [rbp+1C8h]; this
0x1800311d7  lea     r8, aOnecoreBaseDev_14; "onecore\\base\\devices\\association\\se"...
0x1800311de  mov     r9d, eax; char *
0x1800311e1  mov     edx, 9FAh; void *
0x1800311e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800311eb  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 2
0x1800311f2  jz      short loc_18003121F
0x1800311f4  mov     eax, [rsp+2C0h+Reply]
0x1800311f8  lea     r9, [rsp+2C0h+Filename]
0x1800311fd  mov     r8, [rsp+2C0h+var_260]
0x180031202  lea     rdx, ASSOCIATION_FAILURE_ENUM_CEREMONIES
0x180031209  mov     dword ptr [rsp+2C0h+var_290], eax
0x18003120d  mov     eax, dword ptr [rsp+2C0h+var_270]
0x180031211  mov     dword ptr [rsp+2C0h+var_298], eax
0x180031215  mov     dword ptr [rsp+2C0h+MessageGuid], r12d
0x18003121a  call    McTemplateU0zzqqq_EventWriteTransfer
0x18003121f  mov     edi, dword ptr [rsp+2C0h+var_270]
0x180031223  lea     rcx, [rsp+2C0h+var_260]
0x180031228  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003122d  mov     eax, edi
0x18003122f  mov     rcx, [rbp+1C0h+var_40]
0x180031236  xor     rcx, rsp; StackCookie
0x180031239  call    __security_check_cookie
0x18003123e  add     rsp, 290h
0x180031245  pop     r15
0x180031247  pop     r14
0x180031249  pop     r12
0x18003124b  pop     rdi
0x18003124c  pop     rsi
0x18003124d  pop     rbx
0x18003124e  pop     rbp
0x18003124f  retn
```
