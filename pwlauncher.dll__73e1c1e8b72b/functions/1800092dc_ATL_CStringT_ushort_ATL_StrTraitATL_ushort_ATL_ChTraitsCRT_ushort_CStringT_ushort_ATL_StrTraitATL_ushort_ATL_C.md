# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)

- ea: `0x1800092dc`
- end: `0x180009359`
- name: `??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z`
- size: `125`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64)`
- caller_count: `17`
- callee_count: `4`
- tags: ``

## callers

- `0x180001290`
- `0x1800012c0`
- `0x1800012f0`
- `0x180001320`
- `0x180001350`
- `0x180001380`
- `0x1800013b0`
- `0x180001500`
- `0x180001530`
- `0x180001560`
- `0x180001590`
- `0x1800015c0`
- `0x1800015f0`
- `0x180001620`
- `0x18000a710`
- `0x18000a85c`
- `0x18000ee48`

## callees

- `0x1800092dc`
- `0x18000a280`
- `0x18000ad08`
- `0x180011010`

## pseudocode

```c
_QWORD *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        _QWORD *a1,
        unsigned __int64 a2)
{
  __int64 v4; // r8

  *a1 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  if ( !a2 )
  {
    v4 = 0;
LABEL_8:
    ATL::CSimpleStringT<unsigned short,0>::SetString(a1, a2, v4);
    return a1;
  }
  if ( a2 >= 0x10000 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(a2 + 2 * v4) );
    goto LABEL_8;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
    a1,
    (unsigned __int16)a2);
  return a1;
}

```

## disassembly

```asm
0x1800092dc  mov     [rsp+arg_8], rbx
0x1800092e1  mov     [rsp+arg_0], rcx
0x1800092e6  push    rdi
0x1800092e7  sub     rsp, 20h
0x1800092eb  mov     rbx, rdx
0x1800092ee  mov     rdi, rcx
0x1800092f1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800092f8  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800092ff  mov     rax, [rax+18h]
0x180009303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009308  add     rax, 18h
0x18000930c  mov     [rdi], rax
0x18000930f  xor     eax, eax
0x180009311  test    rbx, rbx
0x180009314  jz      short loc_18000933C
0x180009316  cmp     rbx, 10000h
0x18000931d  jnb     short loc_18000932C
0x18000931f  movzx   edx, bx
0x180009322  mov     rcx, rdi
0x180009325  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x18000932a  jmp     short loc_18000934B
0x18000932c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009330  inc     r8
0x180009333  cmp     [rbx+r8*2], ax
0x180009338  jnz     short loc_180009330
0x18000933a  jmp     short loc_18000933F
0x18000933c  mov     r8d, eax
0x18000933f  mov     rdx, rbx
0x180009342  mov     rcx, rdi
0x180009345  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000934a  nop
0x18000934b  mov     rax, rdi
0x18000934e  mov     rbx, [rsp+28h+arg_8]
0x180009353  add     rsp, 20h
0x180009357  pop     rdi
0x180009358  retn
```
