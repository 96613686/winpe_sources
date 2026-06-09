# HcnUnregisterNetworkCallback(void *)

- ea: `0x180005ed0`
- end: `0x180005f24`
- name: `?HcnUnregisterNetworkCallback@@YAJPEAX@Z`
- size: `84`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005ed0`
- `0x180007904`
- `0x18000ad58`

## string_xrefs

- `0x180005f0e`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
__int64 __fastcall HcnUnregisterNetworkCallback(void **a1)
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
        (void *)0x7DC,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80004003LL,
        v4);
    v6 = 0;
    Hns::Client::Notifications::NotificationCallbacks::UnregisterCallback((RTL_SRWLOCK *)qword_1800184A0, a1, &v6);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x7E3, v1, v2);
  }
  return result;
}

```

## disassembly

```asm
0x180005ed0  sub     rsp, 28h
0x180005ed4  mov     rax, [rsp+28h]
0x180005ed9  test    rcx, rcx
0x180005edc  jz      short loc_180005F08
0x180005ede  mov     [rsp+28h+arg_0], 0
0x180005ee7  lea     r8, [rsp+28h+arg_0]; void **
0x180005eec  mov     rdx, rcx; void *
0x180005eef  lea     rcx, qword_1800184A0; this
0x180005ef6  call    ?UnregisterCallback@NotificationCallbacks@Notifications@Client@Hns@@QEAAXPEAXPEAPEAX@Z; Hns::Client::Notifications::NotificationCallbacks::UnregisterCallback(void *,void * *)
0x180005efb  xor     eax, eax
0x180005efd  jmp     short loc_180005F03
0x180005eff  mov     eax, dword ptr [rsp+28h+arg_0]
0x180005f03  add     rsp, 28h
0x180005f07  retn
0x180005f08  mov     r9d, 80004003h; char *
0x180005f0e  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005f15  mov     edx, 7DCh; void *
0x180005f1a  mov     rcx, rax; this
0x180005f1d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
