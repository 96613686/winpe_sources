# EapLm::Peer::ThirdPartyEapMethodRuntime::GetUIContext(EapHost::Session &,TempBuffer<0> &)

- ea: `0x1800190d0`
- end: `0x1800191d3`
- name: `?GetUIContext@ThirdPartyEapMethodRuntime@Peer@EapLm@@UEAAXAEAVSession@EapHost@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002af0`
- `0x1800054c4`
- `0x18000a4d4`
- `0x1800155c8`
- `0x180018498`
- `0x1800190d0`
- `0x18001e4ac`
- `0x180030f54`
- `0x180039010`

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
0x1800190d0  mov     [rsp-8+arg_0], rbx
0x1800190d5  mov     [rsp-8+arg_18], rdi
0x1800190da  push    rbp
0x1800190db  lea     rbp, [rsp-57h]
0x1800190e0  sub     rsp, 0C0h
0x1800190e7  mov     rax, cs:__security_cookie
0x1800190ee  xor     rax, rsp
0x1800190f1  mov     [rbp+57h+var_10], rax
0x1800190f5  mov     rdi, r8
0x1800190f8  mov     rbx, rdx
0x1800190fb  mov     [rbp+57h+var_80], 0
0x180019103  mov     [rbp+57h+var_90], 0
0x18001910a  mov     [rbp+57h+var_88], 0
0x180019112  mov     rcx, [rdx+50h]
0x180019116  mov     rax, [rcx]
0x180019119  lea     rdx, [rbp+57h+var_80]
0x18001911d  mov     [rsp+0C0h+var_A0], rdx
0x180019122  lea     r9, [rbp+57h+var_88]
0x180019126  lea     r8, [rbp+57h+var_90]
0x18001912a  mov     edx, [rbx+40h]
0x18001912d  mov     rax, [rax+48h]
0x180019131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019136  test    eax, eax
0x180019138  jns     short loc_180019155
0x18001913a  mov     r8d, eax; unsigned int
0x18001913d  mov     rdx, [rbp+57h+var_80]; struct _EAP_ERROR *
0x180019141  lea     rcx, [rbp+57h+var_70]; this
0x180019145  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001914a  nop
0x18001914b  lea     rcx, [rbp+57h+var_70]; struct EapHost::EapError *
0x18001914f  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x180019155  mov     edx, [rbp+57h+var_90]
0x180019158  mov     r8, [rbp+57h+var_88]
0x18001915c  mov     rcx, rdi
0x18001915f  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180019164  lea     rax, WPP_GLOBAL_Control
0x18001916b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019172  cmp     rcx, rax
0x180019175  jz      short loc_18001919E
0x180019177  test    byte ptr [rcx+1Ch], 4
0x18001917b  jz      short loc_18001919E
0x18001917d  mov     edx, 16h
0x180019182  mov     eax, [rbp+57h+var_90]
0x180019185  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180019189  mov     r9d, [rbx+38h]
0x18001918d  lea     r8, WPP_0e79d599408d37b150a6010943369b1e_Traceguids
0x180019194  mov     rcx, [rcx+10h]
0x180019198  call    WPP_SF_dd
0x18001919d  nop
0x18001919e  lea     rcx, [rbp+57h+var_88]
0x1800191a2  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x1800191a7  nop
0x1800191a8  lea     rcx, [rbp+57h+var_80]
0x1800191ac  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x1800191b1  mov     rcx, [rbp+57h+var_10]
0x1800191b5  xor     rcx, rsp; StackCookie
0x1800191b8  call    __security_check_cookie
0x1800191bd  lea     r11, [rsp+0C0h+var_s0]
0x1800191c5  mov     rbx, [r11+10h]
0x1800191c9  mov     rdi, [r11+28h]
0x1800191cd  mov     rsp, r11
0x1800191d0  pop     rbp
0x1800191d1  retn
```
