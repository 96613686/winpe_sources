# ServiceMain$catch$9

- ea: `0x1800156f5`
- end: `0x1800157c3`
- name: `ServiceMain$catch$9`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001bb4`
- `0x180005d84`
- `0x1800062c4`
- `0x1800077a0`
- `0x180007878`
- `0x1800096d0`
- `0x18000a4b8`
- `0x1800156f5`

## string_xrefs

- `0x18001570b`: `servercommon\base\securehostingservice\common\service\dll\hgclientservice.cpp`
- `0x180015731`: `ServiceMain failed`
- `0x180015758`: `Stopping the service.`

## pseudocode

```c
__int64 __fastcall ServiceMain_catch_9(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  void *v5; // rdx
  wil *v6; // rcx
  unsigned int v7; // r8d
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // edi
  __int64 v12; // rcx
  wil::details::in1diag3 **v13; // rbx

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 408),
    (void *)0x53,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\dll\\hgclientservice.cpp",
    a4);
  v8 = wil::ResultFromCaughtException(v6, v5, v7);
  v11 = v8;
  v12 = (unsigned int)Microsoft_Windows_HostGuardianClient_ServiceEnableBits;
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 8) != 0 )
  {
    McTemplateU0zq_EventWriteTransfer(
      (unsigned int)Microsoft_Windows_HostGuardianClient_ServiceEnableBits,
      ServiceDebugError,
      L"ServiceMain failed",
      v8);
    v12 = (unsigned int)Microsoft_Windows_HostGuardianClient_ServiceEnableBits;
  }
  v13 = *(wil::details::in1diag3 ***)(a2 + 56);
  if ( v13 )
  {
    if ( (v12 & 2) != 0 )
    {
      *(_QWORD *)(a2 + 352) = L"Stopping the service.";
      *(_QWORD *)(a2 + 360) = 44;
      McGenEventWrite_EventWriteTransfer(
        v12,
        (const EVENT_DESCRIPTOR *)ServiceDebugInformational,
        v10,
        2u,
        (PEVENT_DATA_DESCRIPTOR)(a2 + 336));
    }
    Microsoft::HostGuardian::Client::HgService::Stop(v13, v9, v11);
    Microsoft::HostGuardian::Client::HgService::~HgService((Microsoft::HostGuardian::Client::HgService *)v13);
    operator delete(v13);
  }
  return 0;
}

```

## disassembly

```asm
0x1800156f5  mov     [rsp+arg_8], rdx
0x1800156fa  push    rbx
0x1800156fb  push    rbp
0x1800156fc  push    rdi
0x1800156fd  sub     rsp, 30h
0x180015701  mov     rbp, rdx
0x180015704  mov     rcx, [rbp+198h]; this
0x18001570b  lea     r8, aServercommonBa; "servercommon\\base\\securehostingservic"...
0x180015712  mov     edx, 53h ; 'S'; void *
0x180015717  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18001571c  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180015721  mov     edi, eax
0x180015723  mov     ecx, cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits
0x180015729  test    cl, 8
0x18001572c  jz      short loc_18001574A
0x18001572e  mov     r9d, eax
0x180015731  lea     r8, aServicemainFai; "ServiceMain failed"
0x180015738  lea     rdx, ServiceDebugError
0x18001573f  call    McTemplateU0zq_EventWriteTransfer
0x180015744  mov     ecx, cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits
0x18001574a  mov     rbx, [rbp+38h]
0x18001574e  test    rbx, rbx
0x180015751  jz      short loc_1800157B0
0x180015753  test    cl, 2
0x180015756  jz      short loc_18001578F
0x180015758  lea     rax, aStoppingTheSer; "Stopping the service."
0x18001575f  mov     [rbp+160h], rax
0x180015766  mov     qword ptr [rbp+168h], 2Ch ; ','
0x180015771  lea     rax, [rbp+150h]
0x180015778  mov     [rsp+48h+var_28], rax
0x18001577d  mov     r9d, 2
0x180015783  lea     rdx, ServiceDebugInformational
0x18001578a  call    McGenEventWrite_EventWriteTransfer
0x18001578f  mov     r8d, edi; unsigned int
0x180015792  mov     rcx, rbx; this
0x180015795  call    ?Stop@HgService@Client@HostGuardian@Microsoft@@QEAAXEK@Z; Microsoft::HostGuardian::Client::HgService::Stop(uchar,ulong)
0x18001579a  mov     rcx, rbx; this
0x18001579d  call    ??1HgService@Client@HostGuardian@Microsoft@@QEAA@XZ; Microsoft::HostGuardian::Client::HgService::~HgService(void)
0x1800157a2  mov     edx, 0C8h
0x1800157a7  mov     rcx, rbx; Block
0x1800157aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800157af  nop
0x1800157b0  mov     rax, 0
0x1800157ba  add     rsp, 30h
0x1800157be  pop     rdi
0x1800157bf  pop     rbp
0x1800157c0  pop     rbx
0x1800157c1  retn
```
