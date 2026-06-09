# Microsoft::HostGuardian::Client::HgService::SetStatus(ulong)

- ea: `0x180009fc8`
- end: `0x18000a062`
- name: `?SetStatus@HgService@Client@HostGuardian@Microsoft@@IEAAXK@Z`
- size: `154`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::HgService *this, int)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009300`
- `0x1800097f8`
- `0x1800099d0`
- `0x18000a068`
- `0x18000a4b8`

## callees

- `0x180009cec`
- `0x180009fc8`
- `0x18000a7bc`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000a036`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000a036`

## string_xrefs

- `0x180009ffd`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`
- `0x18000a050`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::HgService::SetStatus(
        Microsoft::HostGuardian::Client::HgService *this,
        int a2)
{
  SERVICE_STATUS_HANDLE v4; // rcx
  const char *v5; // r9
  char *v6; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a2 == 1 || a2 == 2 || a2 == 3 )
  {
    *((_DWORD *)this + 12) = 0;
  }
  else if ( a2 == 4 )
  {
    *((_DWORD *)this + 12) = 1;
  }
  else
  {
    LODWORD(v6) = a2;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xDD,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
      (const char *)0x80070057LL,
      (int)"Unsupported set status request: 0x%08x.",
      v6);
  }
  v4 = (SERVICE_STATUS_HANDLE)*((_QWORD *)this + 4);
  *((_DWORD *)this + 11) = a2;
  if ( !SetServiceStatus(v4, (LPSERVICE_STATUS)((char *)this + 40)) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xE1,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
      v5);
}

```

## disassembly

```asm
0x180009fc8  mov     [rsp+arg_0], rbx
0x180009fcd  push    rdi
0x180009fce  sub     rsp, 30h
0x180009fd2  mov     eax, edx
0x180009fd4  mov     edi, edx
0x180009fd6  mov     rbx, rcx
0x180009fd9  sub     eax, 1
0x180009fdc  jz      short loc_18000A024
0x180009fde  sub     eax, 1
0x180009fe1  jz      short loc_18000A024
0x180009fe3  sub     eax, 1
0x180009fe6  jz      short loc_18000A024
0x180009fe8  cmp     eax, 1
0x180009feb  jz      short loc_18000A01B
0x180009fed  mov     rcx, [rsp+38h]; this
0x180009ff2  lea     rax, aUnsupportedSet; "Unsupported set status request: 0x%08x."
0x180009ff9  mov     dword ptr [rsp+38h+var_10], edx; char *
0x180009ffd  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x18000a004  mov     edx, 0DDh; void *
0x18000a009  mov     qword ptr [rsp+38h+var_18], rax; int
0x18000a00e  mov     r9d, 80070057h; char *
0x18000a014  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000a019  jmp     short loc_18000A02B
0x18000a01b  mov     dword ptr [rcx+30h], 1
0x18000a022  jmp     short loc_18000A02B
0x18000a024  mov     dword ptr [rcx+30h], 0
0x18000a02b  mov     rcx, [rbx+20h]; hServiceStatus
0x18000a02f  lea     rdx, [rbx+28h]; lpServiceStatus
0x18000a033  mov     [rdx+4], edi
0x18000a036  call    cs:__imp_SetServiceStatus
0x18000a03c  test    eax, eax
0x18000a03e  jz      short loc_18000A04B
0x18000a040  mov     rbx, [rsp+38h+arg_0]
0x18000a045  add     rsp, 30h
0x18000a049  pop     rdi
0x18000a04a  retn
0x18000a04b  mov     rcx, [rsp+38h]; this
0x18000a050  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x18000a057  mov     edx, 0E1h; void *
0x18000a05c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
