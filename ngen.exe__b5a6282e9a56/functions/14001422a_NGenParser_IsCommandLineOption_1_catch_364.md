# _NGenParser::IsCommandLineOption_::_1_::catch$364

- ea: `0x14001422a`
- end: `0x140014295`
- name: `_NGenParser::IsCommandLineOption_::_1_::catch$364`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001614`
- `0x140001fa0`
- `0x140013efe`

## pseudocode

```c
void __fastcall __noreturn NGenParser::IsCommandLineOption_::_1_::catch_364(__int64 a1, __int64 a2)
{
  __int64 v3; // rax

  *(_QWORD *)(a2 + 48) = &Exception::`vftable';
  *(_QWORD *)(a2 + 56) = 0;
  *(_QWORD *)(a2 + 48) = &DelegatingException::`vftable';
  *(_QWORD *)(a2 + 64) = -1;
  v3 = *(_QWORD *)(a2 + 80);
  *(_QWORD *)(a2 + 96) = v3;
  *(_DWORD *)(a2 + 104) = 0;
  *(_DWORD *)(a2 + 104) = v3 != 0;
  Exception::HandlerState::SetupCatch((Exception::HandlerState *)(a2 + 72), 505);
  NGenParser::PrintLogoHelper(*(NGenParser **)(a2 + 112));
  *(_DWORD *)(a2 + 104) = 0;
  throw;
}

```

## disassembly

```asm
0x14001422a  mov     [rsp+arg_8], rdx
0x14001422f  push    rbp
0x140014230  sub     rsp, 30h
0x140014234  mov     rbp, rdx
0x140014237  lea     rax, ??_7Exception@@6B@; const Exception::`vftable'
0x14001423e  mov     [rbp+30h], rax
0x140014242  and     qword ptr [rbp+38h], 0
0x140014247  lea     rax, ??_7DelegatingException@@6B@; const DelegatingException::`vftable'
0x14001424e  mov     [rbp+30h], rax
0x140014252  or      qword ptr [rbp+40h], 0FFFFFFFFFFFFFFFFh
0x140014257  mov     rax, [rbp+50h]
0x14001425b  mov     [rbp+60h], rax
0x14001425f  xor     ecx, ecx
0x140014261  mov     [rbp+68h], ecx
0x140014264  lea     edx, [rcx+1]
0x140014267  test    rax, rax
0x14001426a  cmovnz  ecx, edx
0x14001426d  mov     [rbp+68h], ecx
0x140014270  mov     edx, 1F9h; int
0x140014275  lea     rcx, [rbp+48h]; this
0x140014279  call    ?SetupCatch@HandlerState@Exception@@QEAAXH_N@Z; Exception::HandlerState::SetupCatch(int,bool)
0x14001427e  mov     rcx, [rbp+70h]; this
0x140014282  call    ?PrintLogoHelper@NGenParser@@AEAAXXZ; NGenParser::PrintLogoHelper(void)
0x140014287  and     dword ptr [rbp+68h], 0
0x14001428b  xor     edx, edx; pThrowInfo
0x14001428d  xor     ecx, ecx; pExceptionObject
0x14001428f  call    _CxxThrowException_0
```
