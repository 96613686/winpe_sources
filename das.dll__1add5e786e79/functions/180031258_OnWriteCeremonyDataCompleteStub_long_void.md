# OnWriteCeremonyDataCompleteStub(long,void *)

- ea: `0x180031258`
- end: `0x180031651`
- name: `?OnWriteCeremonyDataCompleteStub@@YAJJPEAX@Z`
- size: `1017`
- prototype: `int(int, void *)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180056ca0`
- `0x180057aac`
- `0x1800636f0`

## callees

- `0x1800074c0`
- `0x180008a50`
- `0x18001eae0`
- `0x18002a948`
- `0x1800306d8`
- `0x180031258`
- `0x180031f24`
- `0x180033470`
- `0x1800335bc`
- `0x1800345f0`
- `0x18003bc80`
- `0x18003c79c`
- `0x180045df0`
- `0x180046ef0`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800313f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031450`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800314e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800313f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031450`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800314e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031317`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031317`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800314d7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800314d7`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18003149a`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18003149a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800312ae`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800312ae`

## string_xrefs

- `0x1800312f3`: `onecore\base\devices\association\service\lib\associationcontext.cpp`
- `0x1800315ce`: `onecore\base\devices\association\service\lib\associationcontext.cpp`

## pseudocode

```c
__int64 __fastcall OnWriteCeremonyDataCompleteStub(int a1, char *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  unsigned int v5; // edi
  DWORD v6; // r14d
  int v7; // edx
  int v8; // r8d
  int v9; // ecx
  __int64 v10; // rax
  const wchar_t **v11; // rax
  const wchar_t *v12; // rax
  __int64 v13; // rcx
  int v14; // edx
  int v15; // eax
  __int64 v16; // rcx
  bool v17; // sf
  char *p_Reply; // rdx
  int v19; // edi
  int v20; // edx
  int v21; // r8d
  int ProcessName; // eax
  int v23; // ecx
  int MessageGuid; // [rsp+20h] [rbp-E0h]
  char v26[4]; // [rsp+50h] [rbp-B0h] BYREF
  int Reply; // [rsp+58h] [rbp-A8h] BYREF
  void *v28; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int NotificationsQueued; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Filename[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  Reply = a1;
  *(_DWORD *)v26 = 0;
  v28 = 0;
  EventActivityIdControl(2u, (LPGUID)(a2 + 348));
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
    McTemplateU0p_EventWriteTransfer(v3, ASSOC_WRITE_PROVIDER_STOP, a2);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v28,
    0);
  v4 = DafStringCopy(*((_QWORD *)a2 + 1), &v28);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA70,
      (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\associationcontext.cpp",
      (const char *)(unsigned int)v4,
      MessageGuid);
    goto LABEL_48;
  }
  v6 = *((_DWORD *)a2 + 16);
  AcquireSRWLockExclusive((PSRWLOCK)a2 + 6);
  v9 = Reply;
  if ( Reply < 0 && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v10 = *((_QWORD *)a2 + 46);
    if ( !v10 || (v11 = *(const wchar_t ***)(v10 + 24)) == 0 || (v12 = *v11) == 0 )
      v12 = L"unknown";
    WPP_RECORDER_SF_SSqD(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v7,
      v8,
      141,
      &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
      *((_QWORD *)a2 + 1),
      (__int64)v12,
      (char)a2,
      v26[0]);
    v9 = Reply;
  }
  if ( *((_DWORD *)a2 + 10) )
  {
    *((_DWORD *)a2 + 7) = -1;
    *(_DWORD *)v26 = -2147416294;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_SqD(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v7,
        v8,
        142,
        &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
        *((_QWORD *)a2 + 1),
        (char)a2,
        26);
    *((_DWORD *)a2 + 10) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)a2 + 6);
  }
  else
  {
    if ( *((_DWORD *)a2 + 9) )
    {
      *(_DWORD *)v26 = -2147418113;
      *((_DWORD *)a2 + 7) = -1;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v7,
          v8,
          143,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a2 + 1),
          (char)a2,
          255);
      ReleaseSRWLockExclusive((PSRWLOCK)a2 + 6);
      goto LABEL_41;
    }
    v14 = *(_DWORD *)v26;
    if ( v9 < 0 )
      v15 = -1;
    else
      v15 = 5;
    *((_DWORD *)a2 + 7) = v15;
    if ( *((_DWORD *)a2 + 94) )
    {
      v16 = *((_QWORD *)a2 + 25);
      NotificationsQueued = 0;
      RpcServerUnsubscribeForNotification(
        *(RPC_BINDING_HANDLE *)(v16 + 32),
        RpcNotificationCallCancel,
        &NotificationsQueued);
      (*(void (__fastcall **)(char *))(*(_QWORD *)a2 + 16LL))(a2);
      v14 = *(_DWORD *)v26;
      v9 = Reply;
    }
    *((_DWORD *)a2 + 9) = 1;
    if ( v9 < 0 || (v17 = v14 < 0, p_Reply = v26, !v17) )
      p_Reply = (char *)&Reply;
    v19 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)a2 + 25), p_Reply);
    ReleaseSRWLockExclusive((PSRWLOCK)a2 + 6);
    if ( !v19 || v19 == 1818 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Sq(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v20,
          v21,
          145,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a2 + 1),
          (char)a2);
    }
    else
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_SqD(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v20,
          v21,
          144,
          &WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids,
          *((_QWORD *)a2 + 1),
          (char)a2,
          v19);
      if ( v19 >= 0 )
        v19 = (unsigned __int16)v19 | 0x80010000;
      *(_DWORD *)v26 = v19;
    }
  }
  if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 0x10) != 0 )
    McTemplateU0p_EventWriteTransfer(v13, ASSOC_WRITE_STOP, a2);
  (*(void (__fastcall **)(char *))(*(_QWORD *)a2 + 16LL))(a2);
LABEL_41:
  if ( *(int *)v26 < 0 || Reply < 0 )
  {
    memset_0(Filename, 0, 0x208u);
    ProcessName = GetProcessName(v6, Filename);
    if ( ProcessName < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAAC,
        (int)"onecore\\base\\devices\\association\\service\\lib\\associationcontext.cpp",
        (const char *)(unsigned int)ProcessName);
    if ( (Microsoft_Windows_DeviceAssociationServiceEnableBits & 2) != 0 )
      McTemplateU0zzqqq_EventWriteTransfer(
        v23,
        (unsigned int)ASSOCIATION_FAILURE_WRITE,
        (_DWORD)v28,
        (unsigned int)Filename,
        v6,
        v26[0],
        Reply);
  }
  v5 = *(_DWORD *)v26;
LABEL_48:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
  return v5;
}

```

## disassembly

```asm
0x180031258  mov     [rsp-8+arg_10], rbx
0x18003125d  mov     [rsp-8+arg_18], rsi
0x180031262  push    rbp
0x180031263  push    rdi
0x180031264  push    r12
0x180031266  push    r13
0x180031268  push    r14
0x18003126a  lea     rbp, [rsp-190h]
0x180031272  sub     rsp, 290h
0x180031279  mov     rax, cs:__security_cookie
0x180031280  xor     rax, rsp
0x180031283  mov     [rbp+1B0h+var_30], rax
0x18003128a  mov     rbx, rdx
0x18003128d  mov     [rsp+2B0h+Reply], ecx
0x180031291  add     rdx, 15Ch; ActivityId
0x180031298  mov     dword ptr [rsp+2B0h+var_260], 0
0x1800312a0  mov     ecx, 2; ControlCode
0x1800312a5  mov     [rsp+2B0h+var_250], 0
0x1800312ae  call    cs:__imp_EventActivityIdControl
0x1800312b4  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 10h
0x1800312bb  jz      short loc_1800312CC
0x1800312bd  mov     r8, rbx
0x1800312c0  lea     rdx, ASSOC_WRITE_PROVIDER_STOP
0x1800312c7  call    McTemplateU0p_EventWriteTransfer
0x1800312cc  xor     edx, edx
0x1800312ce  lea     rcx, [rsp+2B0h+var_250]
0x1800312d3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800312d8  mov     rcx, [rbx+8]
0x1800312dc  lea     rdx, [rsp+2B0h+var_250]
0x1800312e1  call    DafStringCopy
0x1800312e6  mov     edi, eax
0x1800312e8  test    eax, eax
0x1800312ea  jns     short loc_18003130C
0x1800312ec  mov     rcx, [rbp+1B8h]; this
0x1800312f3  lea     r8, aOnecoreBaseDev_14; "onecore\\base\\devices\\association\\se"...
0x1800312fa  mov     r9d, eax; char *
0x1800312fd  mov     edx, 0A70h; void *
0x180031302  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031307  jmp     loc_18003161A
0x18003130c  mov     r14d, [rbx+40h]
0x180031310  lea     rsi, [rbx+30h]
0x180031314  mov     rcx, rsi; SRWLock
0x180031317  call    cs:__imp_AcquireSRWLockExclusive
0x18003131d  mov     ecx, [rsp+2B0h+Reply]
0x180031321  lea     r13, WPP_874f92a0c6e73621df2f99b11e224c1f_Traceguids
0x180031328  lea     r12, WPP_RECORDER_INITIALIZED
0x18003132f  test    ecx, ecx
0x180031331  jns     short loc_18003139A
0x180031333  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003133a  jz      short loc_18003139A
0x18003133c  mov     rax, [rbx+170h]
0x180031343  mov     ecx, dword ptr [rsp+2B0h+var_260]
0x180031347  test    rax, rax
0x18003134a  jz      short loc_18003135D
0x18003134c  mov     rax, [rax+18h]
0x180031350  test    rax, rax
0x180031353  jz      short loc_18003135D
0x180031355  mov     rax, [rax]
0x180031358  test    rax, rax
0x18003135b  jnz     short loc_180031364
0x18003135d  lea     rax, aUnknown_0; "unknown"
0x180031364  mov     dword ptr [rsp+2B0h+var_270], ecx; char
0x180031368  mov     r9d, 8Dh; int
0x18003136e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031375  mov     qword ptr [rsp+2B0h+var_278], rbx; char
0x18003137a  mov     qword ptr [rsp+2B0h+var_280], rax; __int64
0x18003137f  mov     rax, [rbx+8]
0x180031383  mov     rcx, [rcx+28h]; int
0x180031387  mov     [rsp+2B0h+var_288], rax; __int64
0x18003138c  mov     [rsp+2B0h+MessageGuid], r13; MessageGuid
0x180031391  call    WPP_RECORDER_SF_SSqD
0x180031396  mov     ecx, [rsp+2B0h+Reply]
0x18003139a  cmp     dword ptr [rbx+28h], 0
0x18003139e  jz      short loc_1800313FE
0x1800313a0  mov     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x1800313a7  mov     dword ptr [rsp+2B0h+var_260], 8001071Ah
0x1800313af  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800313b6  jz      short loc_1800313E9
0x1800313b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800313bf  mov     r9d, 8Eh; int
0x1800313c5  mov     rax, [rbx+8]
0x1800313c9  mov     dword ptr [rsp+2B0h+var_278], 8001071Ah; char
0x1800313d1  mov     qword ptr [rsp+2B0h+var_280], rbx; char
0x1800313d6  mov     rcx, [rcx+28h]; int
0x1800313da  mov     [rsp+2B0h+var_288], rax; __int64
0x1800313df  mov     [rsp+2B0h+MessageGuid], r13; MessageGuid
0x1800313e4  call    WPP_RECORDER_SF_SqD
0x1800313e9  mov     rcx, rsi; SRWLock
0x1800313ec  mov     dword ptr [rbx+28h], 0
0x1800313f3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800313f9  jmp     loc_18003156F
0x1800313fe  cmp     dword ptr [rbx+24h], 0
0x180031402  jz      short loc_18003145B
0x180031404  mov     dword ptr [rsp+2B0h+var_260], 8000FFFFh
0x18003140c  mov     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x180031413  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003141a  jz      short loc_18003144D
0x18003141c  mov     rcx, cs:WPP_GLOBAL_Control
0x180031423  mov     r9d, 8Fh; int
0x180031429  mov     rax, [rbx+8]
0x18003142d  mov     dword ptr [rsp+2B0h+var_278], 8000FFFFh; char
0x180031435  mov     qword ptr [rsp+2B0h+var_280], rbx; char
0x18003143a  mov     rcx, [rcx+28h]; int
0x18003143e  mov     [rsp+2B0h+var_288], rax; __int64
0x180031443  mov     [rsp+2B0h+MessageGuid], r13; MessageGuid
0x180031448  call    WPP_RECORDER_SF_SqD
0x18003144d  mov     rcx, rsi; SRWLock
0x180031450  call    cs:__imp_ReleaseSRWLockExclusive
0x180031456  jmp     loc_180031596
0x18003145b  mov     edx, dword ptr [rsp+2B0h+var_260]
0x18003145f  test    edx, edx
0x180031461  js      short loc_18003146E
0x180031463  test    ecx, ecx
0x180031465  js      short loc_18003146E
0x180031467  mov     eax, 5
0x18003146c  jmp     short loc_180031471
0x18003146e  or      eax, 0FFFFFFFFh
0x180031471  mov     [rbx+1Ch], eax
0x180031474  cmp     dword ptr [rbx+178h], 0
0x18003147b  jz      short loc_1800314B7
0x18003147d  mov     rcx, [rbx+0C8h]
0x180031484  lea     r8, [rsp+2B0h+NotificationsQueued]; NotificationsQueued
0x180031489  mov     edx, 2; Notification
0x18003148e  mov     [rsp+2B0h+NotificationsQueued], 0
0x180031496  mov     rcx, [rcx+20h]; Binding
0x18003149a  call    cs:__imp_RpcServerUnsubscribeForNotification
0x1800314a0  mov     rax, [rbx]
0x1800314a3  mov     rcx, rbx
0x1800314a6  mov     rax, [rax+10h]
0x1800314aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314af  mov     edx, dword ptr [rsp+2B0h+var_260]
0x1800314b3  mov     ecx, [rsp+2B0h+Reply]
0x1800314b7  mov     dword ptr [rbx+24h], 1
0x1800314be  test    ecx, ecx
0x1800314c0  js      short loc_1800314CB
0x1800314c2  test    edx, edx
0x1800314c4  lea     rdx, [rsp+2B0h+var_260]
0x1800314c9  js      short loc_1800314D0
0x1800314cb  lea     rdx, [rsp+2B0h+Reply]; Reply
0x1800314d0  mov     rcx, [rbx+0C8h]; pAsync
0x1800314d7  call    cs:__imp_RpcAsyncCompleteCall
0x1800314dd  mov     rcx, rsi; SRWLock
0x1800314e0  mov     edi, eax
0x1800314e2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800314e8  test    edi, edi
0x1800314ea  jz      short loc_18003153D
0x1800314ec  cmp     edi, 71Ah
0x1800314f2  jz      short loc_18003153D
0x1800314f4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800314fb  jz      short loc_18003152A
0x1800314fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180031504  mov     r9d, 90h; int
0x18003150a  mov     rax, [rbx+8]
0x18003150e  mov     dword ptr [rsp+2B0h+var_278], edi; char
0x180031512  mov     qword ptr [rsp+2B0h+var_280], rbx; char
0x180031517  mov     rcx, [rcx+28h]; int
0x18003151b  mov     [rsp+2B0h+var_288], rax; __int64
0x180031520  mov     [rsp+2B0h+MessageGuid], r13; MessageGuid
0x180031525  call    WPP_RECORDER_SF_SqD
0x18003152a  test    edi, edi
0x18003152c  js      short loc_180031537
0x18003152e  movzx   edi, di
0x180031531  or      edi, 80010000h
0x180031537  mov     dword ptr [rsp+2B0h+var_260], edi
0x18003153b  jmp     short loc_18003156F
0x18003153d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180031544  jz      short loc_18003156F
0x180031546  mov     rcx, cs:WPP_GLOBAL_Control
0x18003154d  mov     r9d, 91h; int
0x180031553  mov     rax, [rbx+8]
0x180031557  mov     qword ptr [rsp+2B0h+var_280], rbx; char
0x18003155c  mov     [rsp+2B0h+var_288], rax; __int64
0x180031561  mov     rcx, [rcx+28h]; int
0x180031565  mov     [rsp+2B0h+MessageGuid], r13; int
0x18003156a  call    WPP_RECORDER_SF_Sq
0x18003156f  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 10h
0x180031576  jz      short loc_180031587
0x180031578  mov     r8, rbx
0x18003157b  lea     rdx, ASSOC_WRITE_STOP
0x180031582  call    McTemplateU0p_EventWriteTransfer
0x180031587  mov     rax, [rbx]
0x18003158a  mov     rcx, rbx
0x18003158d  mov     rax, [rax+10h]
0x180031591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031596  cmp     dword ptr [rsp+2B0h+var_260], 0
0x18003159b  jl      short loc_1800315A4
0x18003159d  cmp     [rsp+2B0h+Reply], 0
0x1800315a2  jge     short loc_180031616
0x1800315a4  xor     edx, edx; Val
0x1800315a6  lea     rcx, [rsp+2B0h+Filename]; void *
0x1800315ab  mov     r8d, 208h; Size
0x1800315b1  call    memset_0
0x1800315b6  lea     rdx, [rsp+2B0h+Filename]; lpFilename
0x1800315bb  mov     ecx, r14d; dwProcessId
0x1800315be  call    ?GetProcessName@@YAJKQEAG@Z; GetProcessName(ulong,ushort * const)
0x1800315c3  test    eax, eax
0x1800315c5  jns     short loc_1800315E2
0x1800315c7  mov     rcx, [rbp+1B8h]; this
0x1800315ce  lea     r8, aOnecoreBaseDev_14; "onecore\\base\\devices\\association\\se"...
0x1800315d5  mov     r9d, eax; char *
0x1800315d8  mov     edx, 0AACh; void *
0x1800315dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800315e2  test    byte ptr cs:Microsoft_Windows_DeviceAssociationServiceEnableBits, 2
0x1800315e9  jz      short loc_180031616
0x1800315eb  mov     eax, [rsp+2B0h+Reply]
0x1800315ef  lea     r9, [rsp+2B0h+Filename]
0x1800315f4  mov     r8, [rsp+2B0h+var_250]
0x1800315f9  lea     rdx, ASSOCIATION_FAILURE_WRITE
0x180031600  mov     dword ptr [rsp+2B0h+var_280], eax
0x180031604  mov     eax, dword ptr [rsp+2B0h+var_260]
0x180031608  mov     dword ptr [rsp+2B0h+var_288], eax
0x18003160c  mov     dword ptr [rsp+2B0h+MessageGuid], r14d
0x180031611  call    McTemplateU0zzqqq_EventWriteTransfer
0x180031616  mov     edi, dword ptr [rsp+2B0h+var_260]
0x18003161a  lea     rcx, [rsp+2B0h+var_250]
0x18003161f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180031624  mov     eax, edi
0x180031626  mov     rcx, [rbp+1B0h+var_30]
0x18003162d  xor     rcx, rsp; StackCookie
0x180031630  call    __security_check_cookie
0x180031635  lea     r11, [rsp+2B0h+var_20]
0x18003163d  mov     rbx, [r11+40h]
0x180031641  mov     rsi, [r11+48h]
0x180031645  mov     rsp, r11
0x180031648  pop     r14
0x18003164a  pop     r13
0x18003164c  pop     r12
0x18003164e  pop     rdi
0x18003164f  pop     rbp
0x180031650  retn
```
