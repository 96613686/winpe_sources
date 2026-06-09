# Microsoft::HostGuardian::Client::HgService::ControlHandlerCallback(ulong,ulong,void *,void *)

- ea: `0x1800099d0`
- end: `0x180009a43`
- name: `?ControlHandlerCallback@HgService@Client@HostGuardian@Microsoft@@KAKKKPEAX0@Z`
- size: `115`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, HANDLE *lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000734c`
- `0x1800099d0`
- `0x180009cb4`
- `0x180009fc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009a1a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009a1a`

## string_xrefs

- `0x1800099e9`: `servercommon\base\securehostingservice\common\service\lib\hgservice.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::HgService::ControlHandlerCallback(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        HANDLE *lpContext)
{
  DWORD v6; // ecx
  __int64 v7; // r8
  const char *v8; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( lpContext )
  {
    v6 = dwControl - 1;
    if ( !v6 || v6 == 4 )
    {
      try
      {
        Microsoft::HostGuardian::Client::HgService::SetStatus(
          (Microsoft::HostGuardian::Client::HgService *)lpContext,
          3u);
        if ( !SetEvent(lpContext[11]) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v7, v8);
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x8D,
                               (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
                               v8);
      }
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgservice.cpp",
      (const char *)0x80070057LL,
      v9);
    return 87;
  }
}

```

## disassembly

```asm
0x1800099d0  push    rbx; int
0x1800099d2  sub     rsp, 20h
0x1800099d6  mov     rbx, r9
0x1800099d9  test    r9, r9
0x1800099dc  jnz     short loc_1800099FF
0x1800099de  mov     rcx, [rsp+28h]; this
0x1800099e3  mov     r9d, 80070057h; char *
0x1800099e9  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x1800099f0  mov     edx, 82h; void *
0x1800099f5  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800099fa  lea     eax, [rbx+57h]
0x1800099fd  jmp     short loc_180009A31
0x1800099ff  sub     ecx, 1
0x180009a02  jz      short loc_180009A09
0x180009a04  cmp     ecx, 4
0x180009a07  jnz     short loc_180009A29
0x180009a09  mov     edx, 3; unsigned int
0x180009a0e  mov     rcx, rbx; this
0x180009a11  call    ?SetStatus@HgService@Client@HostGuardian@Microsoft@@IEAAXK@Z; Microsoft::HostGuardian::Client::HgService::SetStatus(ulong)
0x180009a16  mov     rcx, [rbx+58h]; hEvent
0x180009a1a  call    cs:__imp_SetEvent
0x180009a20  mov     rcx, [rsp+28h]; this
0x180009a25  test    eax, eax
0x180009a27  jz      short loc_180009A37
0x180009a29  xor     eax, eax
0x180009a2b  jmp     short loc_180009A31
0x180009a2d  mov     eax, [rsp+28h+arg_18]
0x180009a31  add     rsp, 20h
0x180009a35  pop     rbx
0x180009a36  retn
0x180009a37  mov     edx, 0A01h; void *
0x180009a3c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
