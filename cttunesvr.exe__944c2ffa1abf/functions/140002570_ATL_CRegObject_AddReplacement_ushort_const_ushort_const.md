# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x140002570`
- end: `0x14000259e`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `46`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002308`
- `0x140002570`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  if ( a2 && a3 )
    return ATL::CExpansionVector::Add((ATL::CRegObject *)((char *)this + 8), a2, a3) == 0 ? 0x8007000E : 0;
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x140002570  sub     rsp, 28h
0x140002574  test    rdx, rdx
0x140002577  jz      short loc_140002594
0x140002579  test    r8, r8
0x14000257c  jz      short loc_140002594
0x14000257e  add     rcx, 8; this
0x140002582  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x140002587  neg     eax
0x140002589  sbb     eax, eax
0x14000258b  not     eax
0x14000258d  and     eax, 8007000Eh
0x140002592  jmp     short loc_140002599
0x140002594  mov     eax, 80070057h
0x140002599  add     rsp, 28h
0x14000259d  retn
```
