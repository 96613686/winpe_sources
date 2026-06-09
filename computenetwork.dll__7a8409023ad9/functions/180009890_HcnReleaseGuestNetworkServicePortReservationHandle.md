# HcnReleaseGuestNetworkServicePortReservationHandle

- ea: `0x180009890`
- end: `0x18000990e`
- name: `HcnReleaseGuestNetworkServicePortReservationHandle`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800020dc`
- `0x180006a54`
- `0x180009890`

## string_xrefs

- `0x1800098ac`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x1800098ea`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
__int64 __fastcall HcnReleaseGuestNetworkServicePortReservationHandle(__int64 a1)
{
  __int64 result; // rax
  int v2; // eax
  unsigned int v3; // r8d
  const char *v4; // r9
  unsigned int v5; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v9; // [rsp+38h] [rbp+10h] BYREF

  v8 = a1;
  if ( a1 )
  {
    v9 = &v8;
    try
    {
      v2 = Hns::Client::RpcHelper::InvokeRpcFunction<long (*)(void * *),void * *>(HnsRpc_ReleasePortRange, &v9);
      v5 = v2;
      if ( v2 >= 0 )
      {
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x707,
          (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
          (const char *)(unsigned int)v2,
          v6);
        result = v5;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x70B, v3, v4);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x701,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
      (const char *)0x80070057LL,
      v6);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180009890  mov     [rsp+arg_0], rcx
0x180009895  push    rbx; int
0x180009896  sub     rsp, 20h
0x18000989a  test    rcx, rcx
0x18000989d  jnz     short loc_1800098C1
0x18000989f  mov     rcx, [rsp+28h]; this
0x1800098a4  mov     ebx, 80070057h
0x1800098a9  mov     r9d, ebx; char *
0x1800098ac  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x1800098b3  mov     edx, 701h; void *
0x1800098b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800098bd  mov     eax, ebx
0x1800098bf  jmp     short loc_180009907
0x1800098c1  lea     rax, [rsp+28h+arg_0]
0x1800098c6  mov     [rsp+28h+arg_8], rax
0x1800098cb  lea     rdx, [rsp+28h+arg_8]
0x1800098d0  lea     rcx, HnsRpc_ReleasePortRange
0x1800098d7  call    ??$InvokeRpcFunction@P6AJPEAPEAX@ZPEAPEAX@RpcHelper@Client@Hns@@YA?A_TP6AJPEAPEAX@Z$$QEAPEAPEAX@Z
0x1800098dc  mov     ebx, eax
0x1800098de  test    eax, eax
0x1800098e0  jns     short loc_1800098FF
0x1800098e2  mov     rcx, [rsp+28h]; this
0x1800098e7  mov     r9d, eax; char *
0x1800098ea  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x1800098f1  mov     edx, 707h; void *
0x1800098f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800098fb  mov     eax, ebx
0x1800098fd  jmp     short loc_180009907
0x1800098ff  xor     eax, eax
0x180009901  jmp     short loc_180009907
0x180009903  mov     eax, dword ptr [rsp+28h+arg_0]
0x180009907  add     rsp, 20h
0x18000990b  pop     rbx
0x18000990c  retn
```
