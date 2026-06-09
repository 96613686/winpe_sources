# HcnUnregisterGuestNetworkServiceCallback

- ea: `0x180009bc0`
- end: `0x180009c14`
- name: `HcnUnregisterGuestNetworkServiceCallback`
- size: `84`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007904`
- `0x180009bc0`
- `0x18000ad58`

## string_xrefs

- `0x180009bfe`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
__int64 __fastcall HcnUnregisterGuestNetworkServiceCallback(void **a1)
{
  unsigned int v1; // r8d
  const char *v2; // r9
  __int64 result; // rax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v6; // [rsp+30h] [rbp+8h] BYREF

  try
  {
    if ( !a1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7A6,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80004003LL,
        v4);
    v6 = 0;
    Hns::Client::Notifications::NotificationCallbacks::UnregisterCallback((RTL_SRWLOCK *)qword_1800184D0, a1, &v6);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x7AD, v1, v2);
  }
  return result;
}

```

## disassembly

```asm
0x180009bc0  sub     rsp, 28h
0x180009bc4  mov     rax, [rsp+28h]
0x180009bc9  test    rcx, rcx
0x180009bcc  jz      short loc_180009BF8
0x180009bce  mov     [rsp+28h+arg_0], 0
0x180009bd7  lea     r8, [rsp+28h+arg_0]; void **
0x180009bdc  mov     rdx, rcx; void *
0x180009bdf  lea     rcx, qword_1800184D0; this
0x180009be6  call    ?UnregisterCallback@NotificationCallbacks@Notifications@Client@Hns@@QEAAXPEAXPEAPEAX@Z; Hns::Client::Notifications::NotificationCallbacks::UnregisterCallback(void *,void * *)
0x180009beb  xor     eax, eax
0x180009bed  jmp     short loc_180009BF3
0x180009bef  mov     eax, dword ptr [rsp+28h+arg_0]
0x180009bf3  add     rsp, 28h
0x180009bf7  retn
0x180009bf8  mov     r9d, 80004003h; char *
0x180009bfe  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009c05  mov     edx, 7A6h; void *
0x180009c0a  mov     rcx, rax; this
0x180009c0d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
