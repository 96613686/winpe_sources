# OnReadCeremonyDataCompleteStub(ulong,uchar const *,long,void *)

- ea: `0x180031658`
- end: `0x180031b13`
- name: `?OnReadCeremonyDataCompleteStub@@YAJKPEBEJPEAX@Z`
- size: `1211`
- prototype: `__int64 __fastcall(size_t Size, const unsigned __int8 *Src, int, void *)`
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180056878`
- `0x180056ca0`
- `0x1800635d0`

## callees

- `0x1800074c0`
- `0x180008a50`
- `0x180009220`
- `0x18001eae0`
- `0x18002a948`
- `0x1800306d8`
- `0x180031658`
- `0x180031f24`
- `0x180033470`
- `0x1800335bc`
- `0x1800345f0`
- `0x18003bc80`
- `0x18003c79c`
- `0x180045df0`
- `0x180046ef0`
- `0x18007e9d8`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800318ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003190d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003199e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800318ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003190d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003199e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031714`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031714`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180031993`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180031993`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180031957`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x180031957`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800316ab`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800316ab`

## string_xrefs

- `0x1800316f0`: `onecore\base\devices\association\service\lib\associationcontext.cpp`
- `0x180031a98`: `onecore\base\devices\association\service\lib\associationcontext.cpp`

## pseudocode

```c
__int64 __fastcall OnReadCeremonyDataCompleteStub(size_t Size, const unsigned __int8 *Src, int a3, char *a4)
{
  size_t v4; // r14
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  DWORD v10; // r12d
  int v11; // r8d
  const GUID *v12; // rdx
  bool v13; // zf
  __int64 v14; // rax
  const wchar_t **v15; // rax
  const wchar_t *v16; // rax
  _QWORD *v17; // rbx
  void *v18; // rcx
  _DWORD *v19; // rax
  __int64 v20; // rcx
  int v21; // ecx
  int v22; // eax
  __int64 v23; // rcx
  char *p_Reply; // rdx
  int v25; // ebx
  int v26; // edx
  int v27; // r8d
  int ProcessName; // eax
  int v29; // ecx
  int MessageGuid; // [rsp+20h] [rbp-E0h]
  char v32[4]; // [rsp+50h] [rbp-B0h] BYREF
  int Reply; // [rsp+58h] [rbp-A8h] BYREF
  void *v34; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int NotificationsQueued; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v4 = (unsigned int)Size;
  Reply = a3;
  *(_DWORD *)v32 = 0;
  v34 = 0;
  EventActivityIdControl(2u, (LPGUID)(a4 + 348));
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
    McTemplateU0p_EventWriteTransfer(v7, ASSOC_READ_PROVIDER_STOP, a4);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v34,
    0);
  v8 = DafStringCopy(*((_QWORD *)a4 + 1), &v34);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA10,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\associationcontext.cpp",
      (const char *)(unsigned int)v8,
      MessageGuid);
    goto LABEL_56;
  }
  v10 = *((_DWORD *)a4 + 16);
  AcquireSRWLockExclusive((PSRWLOCK)a4 + 6);
  v12 = &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids;
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
        135,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *((_QWORD *)a4 + 1),
        (__int64)v16,
        (char)a4,
        v32[0]);
    }
    v13 = Reply == 0;
  }
  if ( v13 && (_DWORD)v4 && !*((_DWORD *)a4 + 9) )
  {
    **((_DWORD **)a4 + 17) = v4;
    **((_QWORD **)a4 + 18) = 0;
    v17 = (_QWORD *)*((_QWORD *)a4 + 18);
    *v17 = DAF_user_alloc(v4);
    v18 = (void *)**((_QWORD **)a4 + 18);
    if ( v18 )
    {
      memcpy_0(v18, Src, v4);
    }
    else
    {
      v19 = (_DWORD *)*((_QWORD *)a4 + 17);
      *(_DWORD *)v32 = -2147024882;
      *v19 = 0;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)v12,
          v11,
          136,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a4 + 1),
          (char)a4,
          v32[0]);
    }
  }
  if ( *((_DWORD *)a4 + 10) )
  {
    *((_DWORD *)a4 + 7) = -1;
    *(_DWORD *)v32 = -2147416294;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_SqD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)v12,
        v11,
        137,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *((_QWORD *)a4 + 1),
        (char)a4,
        26);
    ReleaseSRWLockExclusive((PSRWLOCK)a4 + 6);
    *((_DWORD *)a4 + 10) = 0;
  }
  else
  {
    if ( *((_DWORD *)a4 + 9) )
    {
      *(_DWORD *)v32 = -2147418113;
      *((_DWORD *)a4 + 7) = -1;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          (int)v12,
          v11,
          138,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a4 + 1),
          (char)a4,
          255);
      ReleaseSRWLockExclusive((PSRWLOCK)a4 + 6);
      goto LABEL_49;
    }
    v21 = *(_DWORD *)v32;
    if ( *(int *)v32 < 0 || Reply < 0 )
      v22 = -1;
    else
      v22 = 4;
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
      v21 = *(_DWORD *)v32;
    }
    *((_DWORD *)a4 + 9) = 1;
    if ( Reply < 0 || (p_Reply = v32, v21 >= 0) )
      p_Reply = (char *)&Reply;
    v25 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)a4 + 25), p_Reply);
    ReleaseSRWLockExclusive((PSRWLOCK)a4 + 6);
    if ( !v25 || v25 == 1818 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Sq(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v26,
          v27,
          140,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a4 + 1),
          (char)a4);
    }
    else
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v26,
          v27,
          139,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a4 + 1),
          (char)a4,
          v25);
      if ( v25 >= 0 )
        v25 = (unsigned __int16)v25 | 0x80010000;
      *(_DWORD *)v32 = v25;
    }
  }
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
    McTemplateU0p_EventWriteTransfer(v20, ASSOC_READ_STOP, a4);
  (*(void (__fastcall **)(char *))(*(_QWORD *)a4 + 16LL))(a4);
LABEL_49:
  if ( *(int *)v32 < 0 || Reply < 0 )
  {
    memset_0(Filename, 0, 0x208u);
    ProcessName = GetProcessName(v10, Filename);
    if ( ProcessName < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA5C,
        (int)"onecore\\base\\devices\\association\\service\\lib\\associationcontext.cpp",
        (const char *)(unsigned int)ProcessName);
    if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 2) != 0 )
      McTemplateU0zzqqq_EventWriteTransfer(
        v29,
        (unsigned int)ASSOCIATION_FAILURE_READ,
        (_DWORD)v34,
        (unsigned int)Filename,
        v10,
        v32[0],
        Reply);
  }
  v9 = *(_DWORD *)v32;
LABEL_56:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
  return v9;
}

```

## disassembly

```asm
0x180031658  push    rbp
0x18003165a  push    rbx
0x18003165b  push    rsi
0x18003165c  push    rdi
0x18003165d  push    r12
0x18003165f  push    r13
0x180031661  push    r14
0x180031663  push    r15
0x180031665  lea     rbp, [rsp-198h]
0x18003166d  sub     rsp, 298h
0x180031674  mov     rax, cs:__security_cookie
0x18003167b  xor     rax, rsp
0x18003167e  mov     [rbp+1D0h+var_50], rax
0x180031685  xor     r13d, r13d
0x180031688  mov     r14d, ecx
0x18003168b  mov     r15, rdx
0x18003168e  mov     [rsp+2D0h+Reply], r8d
0x180031693  lea     rdx, [r9+15Ch]; ActivityId
0x18003169a  mov     dword ptr [rsp+2D0h+var_280], r13d
0x18003169f  mov     rdi, r9
0x1800316a2  mov     [rsp+2D0h+var_270], r13
0x1800316a7  lea     ecx, [r13+2]; ControlCode
0x1800316ab  call    cs:__imp_EventActivityIdControl
0x1800316b1  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 10h
0x1800316b8  jz      short loc_1800316C9
0x1800316ba  mov     r8, rdi
0x1800316bd  lea     rdx, ASSOC_READ_PROVIDER_STOP
0x1800316c4  call    McTemplateU0p_EventWriteTransfer
0x1800316c9  xor     edx, edx
0x1800316cb  lea     rcx, [rsp+2D0h+var_270]
0x1800316d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800316d5  mov     rcx, [rdi+8]
0x1800316d9  lea     rdx, [rsp+2D0h+var_270]
0x1800316de  call    DafStringCopy
0x1800316e3  mov     ebx, eax
0x1800316e5  test    eax, eax
0x1800316e7  jns     short loc_180031709
0x1800316e9  mov     rcx, [rbp+1D8h]; this
0x1800316f0  lea     r8, aOnecoreBaseDev_14; "onecore\\base\\devices\\association\\se"...
0x1800316f7  mov     r9d, eax; char *
0x1800316fa  mov     edx, 0A10h; void *
0x1800316ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031704  jmp     loc_180031AE4
0x180031709  mov     r12d, [rdi+40h]
0x18003170d  lea     rsi, [rdi+30h]
0x180031711  mov     rcx, rsi; SRWLock
0x180031714  call    cs:__imp_AcquireSRWLockExclusive
0x18003171a  lea     rdx, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids; int
0x180031721  lea     rbx, WPP_RECORDER_INITIALIZED
0x180031728  cmp     [rsp+2D0h+Reply], r13d
0x18003172d  jge     short loc_180031797
0x18003172f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x180031736  jz      short loc_180031792
0x180031738  mov     rax, [rdi+170h]
0x18003173f  mov     ecx, dword ptr [rsp+2D0h+var_280]
0x180031743  test    rax, rax
0x180031746  jz      short loc_180031759
0x180031748  mov     rax, [rax+18h]
0x18003174c  test    rax, rax
0x18003174f  jz      short loc_180031759
0x180031751  mov     rax, [rax]
0x180031754  test    rax, rax
0x180031757  jnz     short loc_180031760
0x180031759  lea     rax, aUnknown_0; "unknown"
0x180031760  mov     dword ptr [rsp+2D0h+var_290], ecx; char
0x180031764  mov     r9d, 87h; int
0x18003176a  mov     rcx, cs:WPP_GLOBAL_Control
0x180031771  mov     qword ptr [rsp+2D0h+var_298], rdi; char
0x180031776  mov     qword ptr [rsp+2D0h+var_2A0], rax; __int64
0x18003177b  mov     rax, [rdi+8]
0x18003177f  mov     rcx, [rcx+28h]; int
0x180031783  mov     [rsp+2D0h+var_2A8], rax; __int64
0x180031788  mov     [rsp+2D0h+MessageGuid], rdx; MessageGuid
0x18003178d  call    WPP_RECORDER_SF_SSqD
0x180031792  cmp     [rsp+2D0h+Reply], r13d
0x180031797  jnz     loc_180031853
0x18003179d  test    r14d, r14d
0x1800317a0  jz      loc_180031853
0x1800317a6  cmp     [rdi+24h], r13d
0x1800317aa  jnz     loc_180031853
0x1800317b0  mov     rax, [rdi+88h]
0x1800317b7  mov     rcx, r14
0x1800317ba  mov     [rax], r14d
0x1800317bd  mov     rax, [rdi+90h]
0x1800317c4  mov     [rax], r13
0x1800317c7  mov     rbx, [rdi+90h]
0x1800317ce  call    DAF_user_alloc
0x1800317d3  mov     [rbx], rax
0x1800317d6  mov     rax, [rdi+90h]
0x1800317dd  mov     rcx, [rax]; void *
0x1800317e0  test    rcx, rcx
0x1800317e3  jnz     short loc_180031841
0x1800317e5  mov     rax, [rdi+88h]
0x1800317ec  mov     dword ptr [rsp+2D0h+var_280], 8007000Eh
0x1800317f4  mov     [rax], r13d
0x1800317f7  lea     rbx, WPP_RECORDER_INITIALIZED
0x1800317fe  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x180031805  lea     r14, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x18003180c  jz      short loc_18003185A
0x18003180e  mov     eax, dword ptr [rsp+2D0h+var_280]
0x180031812  mov     r9d, 88h; int
0x180031818  mov     rcx, cs:WPP_GLOBAL_Control
0x18003181f  mov     dword ptr [rsp+2D0h+var_298], eax; char
0x180031823  mov     rax, [rdi+8]
0x180031827  mov     qword ptr [rsp+2D0h+var_2A0], rdi; char
0x18003182c  mov     rcx, [rcx+28h]; int
0x180031830  mov     [rsp+2D0h+var_2A8], rax; __int64
0x180031835  mov     [rsp+2D0h+MessageGuid], r14; MessageGuid
0x18003183a  call    WPP_RECORDER_SF_SqD
0x18003183f  jmp     short loc_18003185A
0x180031841  mov     r8, r14; Size
0x180031844  mov     rdx, r15; Src
0x180031847  call    memcpy_0
0x18003184c  lea     rbx, WPP_RECORDER_INITIALIZED
0x180031853  lea     r14, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x18003185a  cmp     [rdi+28h], r13d
0x18003185e  jz      short loc_1800318BB
0x180031860  mov     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x180031867  mov     dword ptr [rsp+2D0h+var_280], 8001071Ah
0x18003186f  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x180031876  jz      short loc_1800318A9
0x180031878  mov     rcx, cs:WPP_GLOBAL_Control
0x18003187f  mov     r9d, 89h; int
0x180031885  mov     rax, [rdi+8]
0x180031889  mov     dword ptr [rsp+2D0h+var_298], 8001071Ah; char
0x180031891  mov     qword ptr [rsp+2D0h+var_2A0], rdi; char
0x180031896  mov     rcx, [rcx+28h]; int
0x18003189a  mov     [rsp+2D0h+var_2A8], rax; __int64
0x18003189f  mov     [rsp+2D0h+MessageGuid], r14; MessageGuid
0x1800318a4  call    WPP_RECORDER_SF_SqD
0x1800318a9  mov     rcx, rsi; SRWLock
0x1800318ac  call    cs:__imp_ReleaseSRWLockExclusive
0x1800318b2  mov     [rdi+28h], r13d
0x1800318b6  jmp     loc_180031A39
0x1800318bb  cmp     [rdi+24h], r13d
0x1800318bf  jz      short loc_180031918
0x1800318c1  mov     dword ptr [rsp+2D0h+var_280], 8000FFFFh
0x1800318c9  mov     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x1800318d0  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1800318d7  jz      short loc_18003190A
0x1800318d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800318e0  mov     r9d, 8Ah; int
0x1800318e6  mov     rax, [rdi+8]
0x1800318ea  mov     dword ptr [rsp+2D0h+var_298], 8000FFFFh; char
0x1800318f2  mov     qword ptr [rsp+2D0h+var_2A0], rdi; char
0x1800318f7  mov     rcx, [rcx+28h]; int
0x1800318fb  mov     [rsp+2D0h+var_2A8], rax; __int64
0x180031900  mov     [rsp+2D0h+MessageGuid], r14; MessageGuid
0x180031905  call    WPP_RECORDER_SF_SqD
0x18003190a  mov     rcx, rsi; SRWLock
0x18003190d  call    cs:__imp_ReleaseSRWLockExclusive
0x180031913  jmp     loc_180031A60
0x180031918  mov     ecx, dword ptr [rsp+2D0h+var_280]
0x18003191c  test    ecx, ecx
0x18003191e  js      short loc_18003192E
0x180031920  cmp     [rsp+2D0h+Reply], r13d
0x180031925  jl      short loc_18003192E
0x180031927  mov     eax, 4
0x18003192c  jmp     short loc_180031931
0x18003192e  or      eax, 0FFFFFFFFh
0x180031931  mov     [rdi+1Ch], eax
0x180031934  cmp     [rdi+178h], r13d
0x18003193b  jz      short loc_180031970
0x18003193d  mov     rcx, [rdi+0C8h]
0x180031944  lea     r8, [rsp+2D0h+NotificationsQueued]; NotificationsQueued
0x180031949  mov     edx, 2; Notification
0x18003194e  mov     [rsp+2D0h+NotificationsQueued], r13d
0x180031953  mov     rcx, [rcx+20h]; Binding
0x180031957  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18003195d  mov     rax, [rdi]
0x180031960  mov     rcx, rdi
0x180031963  mov     rax, [rax+10h]
0x180031967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003196c  mov     ecx, dword ptr [rsp+2D0h+var_280]
0x180031970  mov     dword ptr [rdi+24h], 1
0x180031977  cmp     [rsp+2D0h+Reply], r13d
0x18003197c  jl      short loc_180031987
0x18003197e  lea     rdx, [rsp+2D0h+var_280]
0x180031983  test    ecx, ecx
0x180031985  js      short loc_18003198C
0x180031987  lea     rdx, [rsp+2D0h+Reply]; Reply
0x18003198c  mov     rcx, [rdi+0C8h]; pAsync
0x180031993  call    cs:__imp_RpcAsyncCompleteCall
0x180031999  mov     rcx, rsi; SRWLock
0x18003199c  mov     ebx, eax
0x18003199e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800319a4  test    ebx, ebx
0x1800319a6  jz      short loc_180031A00
0x1800319a8  cmp     ebx, 71Ah
0x1800319ae  jz      short loc_180031A00
0x1800319b0  lea     rax, WPP_RECORDER_INITIALIZED
0x1800319b7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800319be  jz      short loc_1800319ED
0x1800319c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319c7  mov     r9d, 8Bh; int
0x1800319cd  mov     rax, [rdi+8]
0x1800319d1  mov     dword ptr [rsp+2D0h+var_298], ebx; char
0x1800319d5  mov     qword ptr [rsp+2D0h+var_2A0], rdi; char
0x1800319da  mov     rcx, [rcx+28h]; int
0x1800319de  mov     [rsp+2D0h+var_2A8], rax; __int64
0x1800319e3  mov     [rsp+2D0h+MessageGuid], r14; MessageGuid
0x1800319e8  call    WPP_RECORDER_SF_SqD
0x1800319ed  test    ebx, ebx
0x1800319ef  js      short loc_1800319FA
0x1800319f1  movzx   ebx, bx
0x1800319f4  or      ebx, 80010000h
0x1800319fa  mov     dword ptr [rsp+2D0h+var_280], ebx
0x1800319fe  jmp     short loc_180031A39
0x180031a00  lea     rax, WPP_RECORDER_INITIALIZED
0x180031a07  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180031a0e  jz      short loc_180031A39
0x180031a10  mov     rcx, cs:WPP_GLOBAL_Control
0x180031a17  mov     r9d, 8Ch; int
0x180031a1d  mov     rax, [rdi+8]
0x180031a21  mov     qword ptr [rsp+2D0h+var_2A0], rdi; char
0x180031a26  mov     [rsp+2D0h+var_2A8], rax; __int64
0x180031a2b  mov     rcx, [rcx+28h]; int
0x180031a2f  mov     [rsp+2D0h+MessageGuid], r14; int
0x180031a34  call    WPP_RECORDER_SF_Sq
0x180031a39  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 10h
0x180031a40  jz      short loc_180031A51
0x180031a42  mov     r8, rdi
0x180031a45  lea     rdx, ASSOC_READ_STOP
0x180031a4c  call    McTemplateU0p_EventWriteTransfer
0x180031a51  mov     rax, [rdi]
0x180031a54  mov     rcx, rdi
0x180031a57  mov     rax, [rax+10h]
0x180031a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a60  cmp     dword ptr [rsp+2D0h+var_280], r13d
0x180031a65  jl      short loc_180031A6E
0x180031a67  cmp     [rsp+2D0h+Reply], r13d
0x180031a6c  jge     short loc_180031AE0
0x180031a6e  xor     edx, edx; Val
0x180031a70  lea     rcx, [rsp+2D0h+Filename]; void *
0x180031a75  mov     r8d, 208h; Size
0x180031a7b  call    memset_0
0x180031a80  lea     rdx, [rsp+2D0h+Filename]; lpFilename
0x180031a85  mov     ecx, r12d; dwProcessId
0x180031a88  call    ?GetProcessName@@YAJKQEAG@Z; GetProcessName(ulong,ushort * const)
0x180031a8d  test    eax, eax
0x180031a8f  jns     short loc_180031AAC
0x180031a91  mov     rcx, [rbp+1D8h]; this
0x180031a98  lea     r8, aOnecoreBaseDev_14; "onecore\\base\\devices\\association\\se"...
0x180031a9f  mov     r9d, eax; char *
0x180031aa2  mov     edx, 0A5Ch; void *
0x180031aa7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031aac  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 2
0x180031ab3  jz      short loc_180031AE0
0x180031ab5  mov     eax, [rsp+2D0h+Reply]
0x180031ab9  lea     r9, [rsp+2D0h+Filename]
0x180031abe  mov     r8, [rsp+2D0h+var_270]
0x180031ac3  lea     rdx, ASSOCIATION_FAILURE_READ
0x180031aca  mov     dword ptr [rsp+2D0h+var_2A0], eax
0x180031ace  mov     eax, dword ptr [rsp+2D0h+var_280]
0x180031ad2  mov     dword ptr [rsp+2D0h+var_2A8], eax
0x180031ad6  mov     dword ptr [rsp+2D0h+MessageGuid], r12d
0x180031adb  call    McTemplateU0zzqqq_EventWriteTransfer
0x180031ae0  mov     ebx, dword ptr [rsp+2D0h+var_280]
0x180031ae4  lea     rcx, [rsp+2D0h+var_270]
0x180031ae9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180031aee  mov     eax, ebx
0x180031af0  mov     rcx, [rbp+1D0h+var_50]
0x180031af7  xor     rcx, rsp; StackCookie
0x180031afa  call    __security_check_cookie
0x180031aff  add     rsp, 298h
0x180031b06  pop     r15
0x180031b08  pop     r14
0x180031b0a  pop     r13
0x180031b0c  pop     r12
0x180031b0e  pop     rdi
0x180031b0f  pop     rsi
0x180031b10  pop     rbx
0x180031b11  pop     rbp
0x180031b12  retn
```
