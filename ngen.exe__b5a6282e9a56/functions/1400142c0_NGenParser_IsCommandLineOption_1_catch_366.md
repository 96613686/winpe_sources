# _NGenParser::IsCommandLineOption_::_1_::catch$366

- ea: `0x1400142c0`
- end: `0x14001432b`
- name: `_NGenParser::IsCommandLineOption_::_1_::catch$366`
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
void __fastcall __noreturn NGenParser::IsCommandLineOption_::_1_::catch_366(__int64 a1, __int64 a2)
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
  Exception::HandlerState::SetupCatch((Exception::HandlerState *)(a2 + 72), 535);
  NGenParser::PrintLogoHelper(*(NGenParser **)(a2 + 112));
  *(_DWORD *)(a2 + 104) = 0;
  throw;
}

```

## disassembly

```asm
0x1400142c0  mov     [rsp+arg_8], rdx
0x1400142c5  push    rbp
0x1400142c6  sub     rsp, 30h
0x1400142ca  mov     rbp, rdx
0x1400142cd  lea     rax, ??_7Exception@@6B@; const Exception::`vftable'
0x1400142d4  mov     [rbp+30h], rax
0x1400142d8  and     qword ptr [rbp+38h], 0
0x1400142dd  lea     rax, ??_7DelegatingException@@6B@; const DelegatingException::`vftable'
0x1400142e4  mov     [rbp+30h], rax
0x1400142e8  or      qword ptr [rbp+40h], 0FFFFFFFFFFFFFFFFh
0x1400142ed  mov     rax, [rbp+50h]
0x1400142f1  mov     [rbp+60h], rax
0x1400142f5  xor     ecx, ecx
0x1400142f7  mov     [rbp+68h], ecx
0x1400142fa  lea     edx, [rcx+1]
0x1400142fd  test    rax, rax
0x140014300  cmovnz  ecx, edx
0x140014303  mov     [rbp+68h], ecx
0x140014306  mov     edx, 217h; int
0x14001430b  lea     rcx, [rbp+48h]; this
0x14001430f  call    ?SetupCatch@HandlerState@Exception@@QEAAXH_N@Z; Exception::HandlerState::SetupCatch(int,bool)
0x140014314  mov     rcx, [rbp+70h]; this
0x140014318  call    ?PrintLogoHelper@NGenParser@@AEAAXXZ; NGenParser::PrintLogoHelper(void)
0x14001431d  and     dword ptr [rbp+68h], 0
0x140014321  xor     edx, edx; pThrowInfo
0x140014323  xor     ecx, ecx; pExceptionObject
0x140014325  call    _CxxThrowException_0
```
