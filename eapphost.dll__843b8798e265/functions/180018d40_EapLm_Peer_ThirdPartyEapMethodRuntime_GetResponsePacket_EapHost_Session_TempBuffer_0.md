# EapLm::Peer::ThirdPartyEapMethodRuntime::GetResponsePacket(EapHost::Session &,TempBuffer<0> &)

- ea: `0x180018d40`
- end: `0x180018e6b`
- name: `?GetResponsePacket@ThirdPartyEapMethodRuntime@Peer@EapLm@@UEAAXAEAVSession@EapHost@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180002af0`
- `0x1800054c4`
- `0x18000a24c`
- `0x18000a4d4`
- `0x1800155c8`
- `0x180018498`
- `0x180018d40`
- `0x18001e4ac`
- `0x180030f54`
- `0x180039010`

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
0x180018d40  mov     [rsp-8+arg_0], rbx
0x180018d45  push    rbp
0x180018d46  push    rdi
0x180018d47  push    r14
0x180018d49  lea     rbp, [rsp-47h]
0x180018d4e  sub     rsp, 0C0h
0x180018d55  mov     rax, cs:__security_cookie
0x180018d5c  xor     rax, rsp
0x180018d5f  mov     [rbp+57h+var_20], rax
0x180018d63  mov     rdi, r8
0x180018d66  mov     rbx, rdx
0x180018d69  lea     r14, WPP_GLOBAL_Control
0x180018d70  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d77  cmp     rcx, r14
0x180018d7a  jz      short loc_180018D9B
0x180018d7c  test    byte ptr [rcx+1Ch], 4
0x180018d80  jz      short loc_180018D9B
0x180018d82  mov     edx, 13h
0x180018d87  mov     r9d, [rbx+38h]
0x180018d8b  lea     r8, WPP_0e79d599408d37b150a6010943369b1e_Traceguids
0x180018d92  mov     rcx, [rcx+10h]
0x180018d96  call    WPP_SF_d
0x180018d9b  mov     [rbp+57h+var_90], 0
0x180018da3  mov     [rbp+57h+var_A0], 0
0x180018daa  mov     [rbp+57h+var_98], 0
0x180018db2  mov     rcx, [rbx+50h]
0x180018db6  mov     rax, [rcx]
0x180018db9  lea     rdx, [rbp+57h+var_90]
0x180018dbd  mov     [rsp+0D0h+var_B0], rdx
0x180018dc2  lea     r9, [rbp+57h+var_98]
0x180018dc6  lea     r8, [rbp+57h+var_A0]
0x180018dca  mov     edx, [rbx+40h]
0x180018dcd  mov     rax, [rax+38h]
0x180018dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018dd6  test    eax, eax
0x180018dd8  jns     short loc_180018DF5
0x180018dda  mov     r8d, eax; unsigned int
0x180018ddd  mov     rdx, [rbp+57h+var_90]; struct _EAP_ERROR *
0x180018de1  lea     rcx, [rbp+57h+var_80]; this
0x180018de5  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180018dea  nop
0x180018deb  lea     rcx, [rbp+57h+var_80]; struct EapHost::EapError *
0x180018def  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x180018df5  mov     edx, [rbp+57h+var_A0]
0x180018df8  mov     r8, [rbp+57h+var_98]
0x180018dfc  mov     rcx, rdi
0x180018dff  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180018e04  mov     rcx, cs:WPP_GLOBAL_Control
0x180018e0b  cmp     rcx, r14
0x180018e0e  jz      short loc_180018E37
0x180018e10  test    byte ptr [rcx+1Ch], 4
0x180018e14  jz      short loc_180018E37
0x180018e16  mov     edx, 14h
0x180018e1b  mov     eax, [rbp+57h+var_A0]
0x180018e1e  mov     dword ptr [rsp+0D0h+var_B0], eax
0x180018e22  mov     r9d, [rbx+38h]
0x180018e26  lea     r8, WPP_0e79d599408d37b150a6010943369b1e_Traceguids
0x180018e2d  mov     rcx, [rcx+10h]
0x180018e31  call    WPP_SF_dd
0x180018e36  nop
0x180018e37  lea     rcx, [rbp+57h+var_98]
0x180018e3b  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x180018e40  nop
0x180018e41  lea     rcx, [rbp+57h+var_90]
0x180018e45  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x180018e4a  mov     rcx, [rbp+57h+var_20]
0x180018e4e  xor     rcx, rsp; StackCookie
0x180018e51  call    __security_check_cookie
0x180018e56  mov     rbx, [rsp+0D0h+arg_0]
0x180018e5e  add     rsp, 0C0h
0x180018e65  pop     r14
0x180018e67  pop     rdi
0x180018e68  pop     rbp
0x180018e69  retn
```
