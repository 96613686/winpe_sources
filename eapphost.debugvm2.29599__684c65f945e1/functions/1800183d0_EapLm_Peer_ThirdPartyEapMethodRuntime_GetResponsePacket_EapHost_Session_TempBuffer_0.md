# EapLm::Peer::ThirdPartyEapMethodRuntime::GetResponsePacket(EapHost::Session &,TempBuffer<0> &)

- ea: `0x1800183d0`
- end: `0x1800184fa`
- name: `?GetResponsePacket@ThirdPartyEapMethodRuntime@Peer@EapLm@@UEAAXAEAVSession@EapHost@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002a90`
- `0x180005370`
- `0x180009dec`
- `0x18000a050`
- `0x180014d8c`
- `0x180017b78`
- `0x1800183d0`
- `0x18001d9bc`
- `0x18002fd44`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EapLm::Peer::ThirdPartyEapMethodRuntime::GetResponsePacket(__int64 a1, __int64 a2, __int64 a3)
{
  signed int v5; // eax
  unsigned int v6; // [rsp+30h] [rbp-49h] BYREF
  void *v7; // [rsp+38h] [rbp-41h] BYREF
  struct _EAP_ERROR *v8[2]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v9[96]; // [rsp+50h] [rbp-29h] BYREF

  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_0e79d599408d37b150a6010943369b1e_Traceguids,
      *(unsigned int *)(a2 + 56));
  }
  v8[0] = 0;
  v6 = 0;
  v7 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *, void **, struct _EAP_ERROR **))(**(_QWORD **)(a2 + 80)
                                                                                                + 56LL))(
         *(_QWORD *)(a2 + 80),
         *(unsigned int *)(a2 + 64),
         &v6,
         &v7,
         v8);
  if ( v5 < 0 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v9, v8[0], v5);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v9);
  }
  TempBuffer<0>::Assign(a3, v6, v7);
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_0e79d599408d37b150a6010943369b1e_Traceguids,
      *(unsigned int *)(a2 + 56),
      v6);
  }
  com_ptr<unsigned char>::Clear(&v7);
  com_ptr<_EAP_ERROR>::Clear((LPVOID *)v8);
}

```

## disassembly

```asm
0x1800183d0  mov     [rsp-8+arg_0], rbx
0x1800183d5  push    rbp
0x1800183d6  push    rdi
0x1800183d7  push    r14
0x1800183d9  lea     rbp, [rsp-47h]
0x1800183de  sub     rsp, 0C0h
0x1800183e5  mov     rax, cs:__security_cookie
0x1800183ec  xor     rax, rsp
0x1800183ef  mov     [rbp+57h+var_20], rax
0x1800183f3  mov     rdi, r8
0x1800183f6  mov     rbx, rdx
0x1800183f9  lea     r14, WPP_GLOBAL_Control
0x180018400  mov     rcx, cs:WPP_GLOBAL_Control
0x180018407  cmp     rcx, r14
0x18001840a  jz      short loc_18001842B
0x18001840c  test    byte ptr [rcx+1Ch], 4
0x180018410  jz      short loc_18001842B
0x180018412  mov     edx, 13h
0x180018417  mov     r9d, [rbx+38h]
0x18001841b  lea     r8, WPP_0e79d599408d37b150a6010943369b1e_Traceguids
0x180018422  mov     rcx, [rcx+10h]
0x180018426  call    WPP_SF_d
0x18001842b  mov     [rbp+57h+var_90], 0
0x180018433  mov     [rbp+57h+var_A0], 0
0x18001843a  mov     [rbp+57h+var_98], 0
0x180018442  mov     rcx, [rbx+50h]
0x180018446  mov     rax, [rcx]
0x180018449  lea     rdx, [rbp+57h+var_90]
0x18001844d  mov     [rsp+0D0h+var_B0], rdx
0x180018452  lea     r9, [rbp+57h+var_98]
0x180018456  lea     r8, [rbp+57h+var_A0]
0x18001845a  mov     edx, [rbx+40h]
0x18001845d  mov     rax, [rax+38h]
0x180018461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018466  test    eax, eax
0x180018468  jns     short loc_180018485
0x18001846a  mov     r8d, eax; unsigned int
0x18001846d  mov     rdx, [rbp+57h+var_90]; struct _EAP_ERROR *
0x180018471  lea     rcx, [rbp+57h+var_80]; this
0x180018475  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001847a  nop
0x18001847b  lea     rcx, [rbp+57h+var_80]; struct EapHost::EapError *
0x18001847f  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x180018485  mov     edx, [rbp+57h+var_A0]
0x180018488  mov     r8, [rbp+57h+var_98]
0x18001848c  mov     rcx, rdi
0x18001848f  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180018494  mov     rcx, cs:WPP_GLOBAL_Control
0x18001849b  cmp     rcx, r14
0x18001849e  jz      short loc_1800184C7
0x1800184a0  test    byte ptr [rcx+1Ch], 4
0x1800184a4  jz      short loc_1800184C7
0x1800184a6  mov     edx, 14h
0x1800184ab  mov     eax, [rbp+57h+var_A0]
0x1800184ae  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800184b2  mov     r9d, [rbx+38h]
0x1800184b6  lea     r8, WPP_0e79d599408d37b150a6010943369b1e_Traceguids
0x1800184bd  mov     rcx, [rcx+10h]
0x1800184c1  call    WPP_SF_dd
0x1800184c6  nop
0x1800184c7  lea     rcx, [rbp+57h+var_98]
0x1800184cb  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x1800184d0  nop
0x1800184d1  lea     rcx, [rbp+57h+var_90]
0x1800184d5  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x1800184da  mov     rcx, [rbp+57h+var_20]
0x1800184de  xor     rcx, rsp; StackCookie
0x1800184e1  call    __security_check_cookie
0x1800184e6  mov     rbx, [rsp+0D0h+arg_0]
0x1800184ee  add     rsp, 0C0h
0x1800184f5  pop     r14
0x1800184f7  pop     rdi
0x1800184f8  pop     rbp
0x1800184f9  retn
```
