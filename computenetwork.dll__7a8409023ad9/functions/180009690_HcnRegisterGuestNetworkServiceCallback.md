# HcnRegisterGuestNetworkServiceCallback

- ea: `0x180009690`
- end: `0x18000972a`
- name: `HcnRegisterGuestNetworkServiceCallback`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007904`
- `0x180009690`
- `0x18000a608`

## string_xrefs

- `0x1800096e0`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x1800096fa`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180009714`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
__int64 __fastcall HcnRegisterGuestNetworkServiceCallback(
        char *a1,
        void (*a2)(unsigned int, void *, int, const unsigned __int16 *),
        char *a3,
        char ***a4)
{
  unsigned int v4; // r8d
  const char *v5; // r9
  __int64 result; // rax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    if ( !a1 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x78E,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v7);
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x78F,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v7);
    if ( !a4 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x790,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80004003LL,
        v7);
    *a4 = Hns::Client::Notifications::NotificationCallbacks::RegisterCallback(
            (RTL_SRWLOCK *)qword_1800184D0,
            a1,
            a3,
            a2);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x795, v4, v5);
  }
  return result;
}

```

## disassembly

```asm
0x180009690  push    rbx; int
0x180009692  sub     rsp, 20h
0x180009696  mov     rbx, r9
0x180009699  mov     rax, [rsp+28h]
0x18000969e  test    rcx, rcx
0x1800096a1  jz      short loc_1800096DA
0x1800096a3  mov     rax, [rsp+28h]
0x1800096a8  test    rdx, rdx
0x1800096ab  jz      short loc_1800096F4
0x1800096ad  mov     rax, [rsp+28h]
0x1800096b2  test    rbx, rbx
0x1800096b5  jz      short loc_18000970E
0x1800096b7  mov     r9, rdx; void (*)(unsigned int, void *, int, const unsigned __int16 *)
0x1800096ba  mov     rdx, rcx; void *
0x1800096bd  lea     rcx, qword_1800184D0; this
0x1800096c4  call    ?RegisterCallback@NotificationCallbacks@Notifications@Client@Hns@@QEAAPEAXPEAX0P6AXK0JPEBG@Z@Z; Hns::Client::Notifications::NotificationCallbacks::RegisterCallback(void *,void *,void (*)(ulong,void *,long,ushort const *))
0x1800096c9  mov     [rbx], rax
0x1800096cc  xor     eax, eax
0x1800096ce  jmp     short loc_1800096D4
0x1800096d0  mov     eax, [rsp+28h+arg_0]
0x1800096d4  add     rsp, 20h
0x1800096d8  pop     rbx
0x1800096d9  retn
0x1800096da  mov     r9d, 80070057h; char *
0x1800096e0  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x1800096e7  mov     edx, 78Eh; void *
0x1800096ec  mov     rcx, rax; this
0x1800096ef  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800096f4  mov     r9d, 80070057h; char *
0x1800096fa  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180009701  mov     edx, 78Fh; void *
0x180009706  mov     rcx, rax; this
0x180009709  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000970e  mov     r9d, 80004003h; char *
0x180009714  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x18000971b  mov     edx, 790h; void *
0x180009720  mov     rcx, rax; this
0x180009723  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
