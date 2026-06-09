# BthServRadioInterfaceWatcher::Start(void)

- ea: `0x180014464`
- end: `0x180014662`
- name: `?Start@BthServRadioInterfaceWatcher@@QEAAXXZ`
- size: `510`
- prototype: `void __fastcall(BthServRadioInterfaceWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010f60`

## callees

- `0x180001d20`
- `0x180001d88`
- `0x180005044`
- `0x180011b9c`
- `0x180014464`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001454a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001454a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800144c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800144c4`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18001453a`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x18001453a`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18001450a`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18001450a`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800144b6`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800144b6`

## string_xrefs

- `0x18001464d`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\radios.cpp`

## pseudocode

```c
void __fastcall BthServRadioInterfaceWatcher::Start(BthServRadioInterfaceWatcher *this)
{
  __int64 v2; // rsi
  DWORD LastError; // ebx
  int ObjectQuery; // eax
  unsigned int v5; // r8d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int CompareAddress; // [rsp+60h] [rbp+8h] BYREF

  if ( dword_180047328 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180047328);
    if ( dword_180047328 == -1 )
    {
      dword_18004638C = 0;
      qword_180046390 = 0;
      dword_1800463C4 = 0;
      qword_1800463C8 = 0;
      *(DEVPROPKEY *)byte_180046378 = DEVPKEY_DeviceInterface_ClassGuid;
      qword_1800463A0 = (__int64)&GUID_BTHPORT_DEVICE_INTERFACE;
      *(DEVPROPKEY *)byte_1800463B0 = DEVPKEY_DeviceInterface_Enabled;
      qword_1800463D8 = (__int64)byte_18003DBB1;
      dword_180046398 = 13;
      dword_18004639C = 16;
      dword_1800463A8 = 2;
      dword_1800463D0 = 17;
      dword_1800463D4 = 1;
      Init_thread_footer(&dword_180047328);
    }
  }
  v2 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    DevCloseObjectQuery(v2);
    SetLastError(LastError);
  }
  *(_QWORD *)this = 0;
  ObjectQuery = DevCreateObjectQuery(1, 1, 0);
  if ( ObjectQuery < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\radios.cpp",
      (const char *)(unsigned int)ObjectQuery,
      2);
  while ( !*((_DWORD *)this + 2) )
  {
    CompareAddress = 0;
    if ( !WaitOnAddress((char *)this + 8, &CompareAddress, 4u, 0xFFFFFFFF) )
    {
      if ( GetLastError() != 1460 )
        wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xBF6, v5, v6);
      return;
    }
  }
}

```

## disassembly

```asm
0x180014464  mov     [rsp+arg_8], rbx
0x180014469  mov     [rsp+arg_10], rsi
0x18001446e  push    rdi
0x18001446f  sub     rsp, 50h
0x180014473  mov     edx, cs:_tls_index
0x180014479  mov     rdi, rcx
0x18001447c  mov     rax, gs:58h
0x180014485  mov     ecx, 4
0x18001448a  mov     rax, [rax+rdx*8]
0x18001448e  mov     eax, [rcx+rax]
0x180014491  cmp     cs:dword_180047328, eax
0x180014497  jg      loc_18001457E
0x18001449d  mov     rsi, [rdi]
0x1800144a0  test    rsi, rsi
0x1800144a3  jz      short loc_1800144D0
0x1800144a5  call    cs:__imp_GetLastError
0x1800144ac  nop     dword ptr [rax+rax+00h]
0x1800144b1  mov     rcx, rsi
0x1800144b4  mov     ebx, eax
0x1800144b6  call    cs:__imp_DevCloseObjectQuery
0x1800144bd  nop     dword ptr [rax+rax+00h]
0x1800144c2  mov     ecx, ebx; dwErrCode
0x1800144c4  call    cs:__imp_SetLastError
0x1800144cb  nop     dword ptr [rax+rax+00h]
0x1800144d0  and     qword ptr [rdi], 0
0x1800144d4  lea     rax, ?DevQueryResultCallbackThunk@BthServRadioInterfaceWatcher@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; BthServRadioInterfaceWatcher::DevQueryResultCallbackThunk(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x1800144db  mov     [rsp+58h+var_18], rdi
0x1800144e0  xor     r9d, r9d
0x1800144e3  mov     [rsp+58h+var_20], rdi
0x1800144e8  xor     r8d, r8d
0x1800144eb  mov     [rsp+58h+var_28], rax
0x1800144f0  lea     rax, qword_180046370
0x1800144f7  mov     [rsp+58h+var_30], rax
0x1800144fc  lea     edx, [r9+1]
0x180014500  mov     [rsp+58h+var_38], 2; int
0x180014508  mov     ecx, edx
0x18001450a  call    cs:__imp_DevCreateObjectQuery
0x180014511  nop     dword ptr [rax+rax+00h]
0x180014516  test    eax, eax
0x180014518  js      loc_180014648
0x18001451e  mov     eax, [rdi+8]
0x180014521  test    eax, eax
0x180014523  jnz     short loc_18001455D
0x180014525  and     [rsp+58h+CompareAddress], eax
0x180014529  lea     r8d, [rax+4]; AddressSize
0x18001452d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180014531  lea     rdx, [rsp+58h+CompareAddress]; CompareAddress
0x180014536  lea     rcx, [rdi+8]; Address
0x18001453a  call    cs:__imp_WaitOnAddress
0x180014541  nop     dword ptr [rax+rax+00h]
0x180014546  test    eax, eax
0x180014548  jnz     short loc_18001451E
0x18001454a  call    cs:__imp_GetLastError
0x180014551  nop     dword ptr [rax+rax+00h]
0x180014556  cmp     eax, 5B4h
0x18001455b  jnz     short loc_18001456E
0x18001455d  mov     rbx, [rsp+58h+arg_8]
0x180014562  mov     rsi, [rsp+58h+arg_10]
0x180014567  add     rsp, 50h
0x18001456b  pop     rdi
0x18001456c  retn
0x18001456e  mov     rcx, [rsp+58h]; this
0x180014573  mov     edx, 0BF6h; void *
0x180014578  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001457e  lea     rcx, dword_180047328
0x180014585  call    _Init_thread_header
0x18001458a  cmp     cs:dword_180047328, 0FFFFFFFFh
0x180014591  jnz     loc_18001449D
0x180014597  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x18001459e  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x1800145a4  lea     rcx, dword_180047328
0x1800145ab  and     cs:dword_18004638C, 0
0x1800145b2  and     cs:qword_180046390, 0
0x1800145ba  and     cs:dword_1800463C4, 0
0x1800145c1  and     cs:qword_1800463C8, 0
0x1800145c9  mov     dword ptr cs:byte_180046378+10h, eax
0x1800145cf  lea     rax, GUID_BTHPORT_DEVICE_INTERFACE
0x1800145d6  mov     cs:qword_1800463A0, rax
0x1800145dd  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x1800145e3  movups  xmmword ptr cs:byte_180046378, xmm0
0x1800145ea  mov     dword ptr cs:byte_1800463B0+10h, eax
0x1800145f0  lea     rax, byte_18003DBB1
0x1800145f7  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x1800145fe  mov     cs:qword_1800463D8, rax
0x180014605  mov     cs:dword_180046398, 0Dh
0x18001460f  movaps  xmmword ptr cs:byte_1800463B0, xmm0
0x180014616  mov     cs:dword_18004639C, 10h
0x180014620  mov     cs:dword_1800463A8, 2
0x18001462a  mov     cs:dword_1800463D0, 11h
0x180014634  mov     cs:dword_1800463D4, 1
0x18001463e  call    _Init_thread_footer
0x180014643  jmp     loc_18001449D
0x180014648  mov     rcx, [rsp+58h]; this
0x18001464d  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x180014654  mov     r9d, eax; char *
0x180014657  mov     edx, 53h ; 'S'; void *
0x18001465c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
