# EapLm::Peer::ThirdPartyEapMethodRuntime::GetUIContext(EapHost::Session &,TempBuffer<0> &)

- ea: `0x180018740`
- end: `0x180018842`
- name: `?GetUIContext@ThirdPartyEapMethodRuntime@Peer@EapLm@@UEAAXAEAVSession@EapHost@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002a90`
- `0x180005370`
- `0x18000a050`
- `0x180014d8c`
- `0x180017b78`
- `0x180018740`
- `0x18001d9bc`
- `0x18002fd44`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EapLm::Peer::ThirdPartyEapMethodRuntime::GetUIContext(__int64 a1, __int64 a2, __int64 a3)
{
  signed int v5; // eax
  unsigned int v6; // [rsp+30h] [rbp-39h] BYREF
  void *v7; // [rsp+38h] [rbp-31h] BYREF
  struct _EAP_ERROR *v8[2]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v9[96]; // [rsp+50h] [rbp-19h] BYREF

  v8[0] = 0;
  v6 = 0;
  v7 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *, void **, struct _EAP_ERROR **))(**(_QWORD **)(a2 + 80)
                                                                                                + 72LL))(
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
      22,
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
0x180018740  mov     [rsp-8+arg_0], rbx
0x180018745  mov     [rsp-8+arg_18], rdi
0x18001874a  push    rbp
0x18001874b  lea     rbp, [rsp-57h]
0x180018750  sub     rsp, 0C0h
0x180018757  mov     rax, cs:__security_cookie
0x18001875e  xor     rax, rsp
0x180018761  mov     [rbp+57h+var_10], rax
0x180018765  mov     rdi, r8
0x180018768  mov     rbx, rdx
0x18001876b  mov     [rbp+57h+var_80], 0
0x180018773  mov     [rbp+57h+var_90], 0
0x18001877a  mov     [rbp+57h+var_88], 0
0x180018782  mov     rcx, [rdx+50h]
0x180018786  mov     rax, [rcx]
0x180018789  lea     rdx, [rbp+57h+var_80]
0x18001878d  mov     [rsp+0C0h+var_A0], rdx
0x180018792  lea     r9, [rbp+57h+var_88]
0x180018796  lea     r8, [rbp+57h+var_90]
0x18001879a  mov     edx, [rbx+40h]
0x18001879d  mov     rax, [rax+48h]
0x1800187a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187a6  test    eax, eax
0x1800187a8  jns     short loc_1800187C5
0x1800187aa  mov     r8d, eax; unsigned int
0x1800187ad  mov     rdx, [rbp+57h+var_80]; struct _EAP_ERROR *
0x1800187b1  lea     rcx, [rbp+57h+var_70]; this
0x1800187b5  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x1800187ba  nop
0x1800187bb  lea     rcx, [rbp+57h+var_70]; struct EapHost::EapError *
0x1800187bf  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x1800187c5  mov     edx, [rbp+57h+var_90]
0x1800187c8  mov     r8, [rbp+57h+var_88]
0x1800187cc  mov     rcx, rdi
0x1800187cf  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x1800187d4  lea     rax, WPP_GLOBAL_Control
0x1800187db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187e2  cmp     rcx, rax
0x1800187e5  jz      short loc_18001880E
0x1800187e7  test    byte ptr [rcx+1Ch], 4
0x1800187eb  jz      short loc_18001880E
0x1800187ed  mov     edx, 16h
0x1800187f2  mov     eax, [rbp+57h+var_90]
0x1800187f5  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800187f9  mov     r9d, [rbx+38h]
0x1800187fd  lea     r8, WPP_0e79d599408d37b150a6010943369b1e_Traceguids
0x180018804  mov     rcx, [rcx+10h]
0x180018808  call    WPP_SF_dd
0x18001880d  nop
0x18001880e  lea     rcx, [rbp+57h+var_88]
0x180018812  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x180018817  nop
0x180018818  lea     rcx, [rbp+57h+var_80]
0x18001881c  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x180018821  mov     rcx, [rbp+57h+var_10]
0x180018825  xor     rcx, rsp; StackCookie
0x180018828  call    __security_check_cookie
0x18001882d  lea     r11, [rsp+0C0h+var_s0]
0x180018835  mov     rbx, [r11+10h]
0x180018839  mov     rdi, [r11+28h]
0x18001883d  mov     rsp, r11
0x180018840  pop     rbp
0x180018841  retn
```
