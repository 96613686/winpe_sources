# HcnRegisterNetworkCallback(void *,void (*)(ulong,void *,long,ushort const *),void *,void * *)

- ea: `0x180005e30`
- end: `0x180005eca`
- name: `?HcnRegisterNetworkCallback@@YAJPEAXP6AXK0JPEBG@Z0PEAPEAX@Z`
- size: `154`
- prototype: `int(void *, void (*)(unsigned int, void *, int, const unsigned __int16 *), void *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180005e30`
- `0x180007904`
- `0x18000a608`

## string_xrefs

- `0x180005e80`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180005e9a`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180005eb4`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
__int64 __fastcall HcnRegisterNetworkCallback(
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
        (void *)0x7C4,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v7);
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7C5,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v7);
    if ( !a4 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x7C6,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80004003LL,
        v7);
    *a4 = Hns::Client::Notifications::NotificationCallbacks::RegisterCallback(
            (RTL_SRWLOCK *)qword_1800184A0,
            a1,
            a3,
            a2);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x7CB, v4, v5);
  }
  return result;
}

```

## disassembly

```asm
0x180005e30  push    rbx; int
0x180005e32  sub     rsp, 20h
0x180005e36  mov     rbx, r9
0x180005e39  mov     rax, [rsp+28h]
0x180005e3e  test    rcx, rcx
0x180005e41  jz      short loc_180005E7A
0x180005e43  mov     rax, [rsp+28h]
0x180005e48  test    rdx, rdx
0x180005e4b  jz      short loc_180005E94
0x180005e4d  mov     rax, [rsp+28h]
0x180005e52  test    rbx, rbx
0x180005e55  jz      short loc_180005EAE
0x180005e57  mov     r9, rdx; void (*)(unsigned int, void *, int, const unsigned __int16 *)
0x180005e5a  mov     rdx, rcx; void *
0x180005e5d  lea     rcx, qword_1800184A0; this
0x180005e64  call    ?RegisterCallback@NotificationCallbacks@Notifications@Client@Hns@@QEAAPEAXPEAX0P6AXK0JPEBG@Z@Z; Hns::Client::Notifications::NotificationCallbacks::RegisterCallback(void *,void *,void (*)(ulong,void *,long,ushort const *))
0x180005e69  mov     [rbx], rax
0x180005e6c  xor     eax, eax
0x180005e6e  jmp     short loc_180005E74
0x180005e70  mov     eax, [rsp+28h+arg_0]
0x180005e74  add     rsp, 20h
0x180005e78  pop     rbx
0x180005e79  retn
0x180005e7a  mov     r9d, 80070057h; char *
0x180005e80  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005e87  mov     edx, 7C4h; void *
0x180005e8c  mov     rcx, rax; this
0x180005e8f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005e94  mov     r9d, 80070057h; char *
0x180005e9a  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005ea1  mov     edx, 7C5h; void *
0x180005ea6  mov     rcx, rax; this
0x180005ea9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180005eae  mov     r9d, 80004003h; char *
0x180005eb4  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180005ebb  mov     edx, 7C6h; void *
0x180005ec0  mov     rcx, rax; this
0x180005ec3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
