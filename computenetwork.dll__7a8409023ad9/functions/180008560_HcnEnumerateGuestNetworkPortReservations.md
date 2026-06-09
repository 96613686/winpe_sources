# HcnEnumerateGuestNetworkPortReservations

- ea: `0x180008560`
- end: `0x18000866a`
- name: `HcnEnumerateGuestNetworkPortReservations`
- size: `266`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002cd0`
- `0x180006a54`
- `0x180008560`
- `0x18000b8c4`
- `0x18000f010`

## string_xrefs

- `0x180008581`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x1800085ab`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`
- `0x180008641`: `onecore\vm\dv\net\hns\computenetwork\src\hnsclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HcnEnumerateGuestNetworkPortReservations(_DWORD *a1, _QWORD *a2)
{
  __int64 result; // rax
  Rpc::RpcClient *v3; // rcx
  int v4; // edi
  unsigned int v5; // r8d
  const char *v6; // r9
  volatile signed __int32 *v7; // rbx
  __int64 v8; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v9; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( a1 )
  {
    if ( a2 )
    {
      *a1 = 0;
      *a2 = 0;
      try
      {
        v3 = (Rpc::RpcClient *)*Hns::Client::RpcHelper::GetRpcClient(&v8);
        v4 = Rpc::RpcClient::InvokeRpcFunctionWithBinding<long (*)(void *,unsigned long *,_HNS_PORT_RANGE_ENTRY * *),unsigned long * &,_HNS_PORT_RANGE_ENTRY * *>(v3);
        v7 = v9;
        if ( v9 )
        {
          if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
            if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
          }
        }
        if ( v4 >= 0 )
        {
          result = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x721,
            (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
            (const char *)(unsigned int)v4,
            v8);
          result = (unsigned int)v4;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x725, v5, v6);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x715,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
        (const char *)0x80070057LL,
        v8);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x714,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\computenetwork\\src\\hnsclient.cpp",
      (const char *)0x80070057LL,
      v8);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180008560  mov     [rsp+arg_8], rbx
0x180008565  mov     [rsp+arg_0], rcx
0x18000856a  push    rdi
0x18000856b  sub     rsp, 30h
0x18000856f  test    rcx, rcx
0x180008572  jnz     short loc_180008599
0x180008574  mov     rcx, [rsp+38h]; this
0x180008579  mov     ebx, 80070057h
0x18000857e  mov     r9d, ebx; char *
0x180008581  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008588  mov     edx, 714h; void *
0x18000858d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008592  mov     eax, ebx
0x180008594  jmp     loc_18000865E
0x180008599  test    rdx, rdx
0x18000859c  jnz     short loc_1800085C3
0x18000859e  mov     rcx, [rsp+38h]; this
0x1800085a3  mov     ebx, 80070057h
0x1800085a8  mov     r9d, ebx; char *
0x1800085ab  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x1800085b2  mov     edx, 715h; void *
0x1800085b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800085bc  mov     eax, ebx
0x1800085be  jmp     loc_18000865E
0x1800085c3  mov     dword ptr [rcx], 0
0x1800085c9  mov     qword ptr [rdx], 0
0x1800085d0  mov     [rsp+38h+arg_10], rdx
0x1800085d5  lea     rcx, [rsp+38h+var_18]
0x1800085da  call    ?GetRpcClient@RpcHelper@Client@Hns@@YA?AV?$shared_ptr@VRpcClient@Rpc@@@std@@XZ; Hns::Client::RpcHelper::GetRpcClient(void)
0x1800085df  nop
0x1800085e0  lea     r9, [rsp+38h+arg_10]
0x1800085e5  lea     r8, [rsp+38h+arg_0]
0x1800085ea  mov     rcx, [rax]; this
0x1800085ed  call    ??$InvokeRpcFunctionWithBinding@P6AJPEAXPEAKPEAPEAU_HNS_PORT_RANGE_ENTRY@@@ZAEAPEAKPEAPEAU1@@RpcClient@Rpc@@QEAA?A_TP6AJPEAXPEAKPEAPEAU_HNS_PORT_RANGE_ENTRY@@@ZAEAPEAK$$QEAPEAPEAU2@@Z
0x1800085f2  mov     edi, eax
0x1800085f4  mov     rbx, [rsp+38h+var_10]
0x1800085f9  test    rbx, rbx
0x1800085fc  jz      short loc_180008635
0x1800085fe  or      ecx, 0FFFFFFFFh
0x180008601  lock xadd [rbx+8], ecx
0x180008606  cmp     ecx, 1
0x180008609  jnz     short loc_180008635
0x18000860b  mov     rax, [rbx]
0x18000860e  mov     rcx, rbx
0x180008611  mov     rax, [rax]
0x180008614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008619  or      eax, 0FFFFFFFFh
0x18000861c  lock xadd [rbx+0Ch], eax
0x180008621  cmp     eax, 1
0x180008624  jnz     short loc_180008635
0x180008626  mov     rax, [rbx]
0x180008629  mov     rcx, rbx
0x18000862c  mov     rax, [rax+8]
0x180008630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008635  test    edi, edi
0x180008637  jns     short loc_180008656
0x180008639  mov     rcx, [rsp+38h]; this
0x18000863e  mov     r9d, edi; char *
0x180008641  lea     r8, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\computenetwo"...
0x180008648  mov     edx, 721h; void *
0x18000864d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008652  mov     eax, edi
0x180008654  jmp     short loc_18000865E
0x180008656  xor     eax, eax
0x180008658  jmp     short loc_18000865E
0x18000865a  mov     eax, dword ptr [rsp+38h+arg_0]
0x18000865e  mov     rbx, [rsp+38h+arg_8]
0x180008663  add     rsp, 30h
0x180008667  pop     rdi
0x180008668  retn
```
