# Microsoft::HostGuardian::Client::HgService::ServiceStopCallback(void *,uchar)

- ea: `0x180009f30`
- end: `0x180009fc0`
- name: `?ServiceStopCallback@HgService@Client@HostGuardian@Microsoft@@KAXPEAXE@Z`
- size: `144`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::HgService *this, unsigned __int8)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001770`
- `0x180001bb4`
- `0x1800077a0`
- `0x1800096d0`
- `0x180009cb4`
- `0x180009f30`
- `0x18000a4b8`

## string_xrefs

- `0x180009f52`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgService::ServiceStopCallback(
        Microsoft::HostGuardian::Client::HgService *this,
        unsigned __int8 a2)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  int v5; // [rsp+20h] [rbp-38h]
  _BYTE v6[16]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( this )
  {
    Microsoft::HostGuardian::Client::HgService::Stop(this, a2, 0);
    Microsoft::HostGuardian::Client::HgService::~HgService(this);
    operator delete(this);
    if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v3, ServiceShutdown, v4, 1, v6);
  }
  else
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
      (const char *)0x80070057LL,
      v5);
  }
}

```

## disassembly

```asm
0x180009f30  push    rbx
0x180009f32  sub     rsp, 50h
0x180009f36  mov     rax, cs:__security_cookie
0x180009f3d  xor     rax, rsp
0x180009f40  mov     [rsp+58h+var_18], rax
0x180009f45  mov     rbx, rcx
0x180009f48  test    rcx, rcx
0x180009f4b  jnz     short loc_180009F6B
0x180009f4d  mov     rcx, [rsp+58h]; this
0x180009f52  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x180009f59  mov     r9d, 80070057h; char *
0x180009f5f  mov     edx, 0AEh; void *
0x180009f64  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180009f69  jmp     short loc_180009FAD
0x180009f6b  xor     r8d, r8d; unsigned int
0x180009f6e  call    ?Stop@HgService@Client@HostGuardian@Microsoft@@QEAAXEK@Z; Microsoft::HostGuardian::Client::HgService::Stop(uchar,ulong)
0x180009f73  mov     rcx, rbx; this
0x180009f76  call    ??1HgService@Client@HostGuardian@Microsoft@@QEAA@XZ; Microsoft::HostGuardian::Client::HgService::~HgService(void)
0x180009f7b  mov     edx, 0C8h
0x180009f80  mov     rcx, rbx; Block
0x180009f83  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009f88  mov     r9d, 1
0x180009f8e  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, r9b
0x180009f95  jz      short loc_180009FAD
0x180009f97  lea     rax, [rsp+58h+var_28]
0x180009f9c  lea     rdx, ServiceShutdown
0x180009fa3  mov     qword ptr [rsp+58h+var_38], rax
0x180009fa8  call    McGenEventWrite_EventWriteTransfer
0x180009fad  mov     rcx, [rsp+58h+var_18]
0x180009fb2  xor     rcx, rsp; StackCookie
0x180009fb5  call    __security_check_cookie
0x180009fba  add     rsp, 50h
0x180009fbe  pop     rbx
0x180009fbf  retn
```
