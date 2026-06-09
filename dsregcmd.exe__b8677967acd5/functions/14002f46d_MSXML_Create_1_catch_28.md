# _MSXML::Create_::_1_::catch$28

- ea: `0x14002f46d`
- end: `0x14002f51b`
- name: `_MSXML::Create_::_1_::catch$28`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x14000813c`
- `0x1400081d8`
- `0x14001413c`
- `0x14002f46d`
- `0x140030010`

## string_xrefs

- `0x14002f4a0`: `Msxml2.FreeThreadedDOMDocument.6.0`

## pseudocode

```c
__int64 __fastcall MSXML::Create_::_1_::catch_28(__int64 a1, _QWORD *a2)
{
  _DWORD *v3; // rcx
  const wchar_t **v4; // rax
  __int64 *v5; // rax
  __int64 v6; // rcx

  v3 = (_DWORD *)a2[10];
  if ( v3[2] == -2147221164 )
  {
    v4 = (const wchar_t **)ResourceMsg::ResourceMsg((ResourceMsg *)(a2 + 27), 0x4AAE0014u);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      a2 + 4,
      *v4,
      L"Msxml2.FreeThreadedDOMDocument.6.0",
      L"88d96a06-f192-11d4-a65f-0040963251e5");
  }
  else
  {
    v5 = (__int64 *)(*(__int64 (__fastcall **)(_DWORD *, _QWORD *))(*(_QWORD *)v3 + 8LL))(v3, a2 + 27);
    ATL::CSimpleStringT<unsigned short,0>::Append(a2 + 4, *v5, *(unsigned int *)(*v5 - 16));
  }
  v6 = a2[27];
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 - 8), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v6 - 24) + 8LL))(*(_QWORD *)(v6 - 24), v6 - 24);
  return 0;
}

```

## disassembly

```asm
0x14002f46d  mov     [rsp+arg_8], rdx
0x14002f472  push    rbp
0x14002f473  sub     rsp, 20h
0x14002f477  mov     rbp, rdx
0x14002f47a  mov     rcx, [rbp+50h]
0x14002f47e  cmp     dword ptr [rcx+8], 80040154h
0x14002f485  jnz     short loc_14002F4B6
0x14002f487  mov     edx, 4AAE0014h; unsigned int
0x14002f48c  lea     rcx, [rbp+0D8h]; this
0x14002f493  call    ??0ResourceMsg@@QEAA@K@Z; ResourceMsg::ResourceMsg(ulong)
0x14002f498  nop
0x14002f499  lea     r9, a88d96a06F19211; "88d96a06-f192-11d4-a65f-0040963251e5"
0x14002f4a0  lea     r8, aMsxml2Freethre; "Msxml2.FreeThreadedDOMDocument.6.0"
0x14002f4a7  mov     rdx, [rax]
0x14002f4aa  lea     rcx, [rbp+20h]
0x14002f4ae  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14002f4b3  nop
0x14002f4b4  jmp     short loc_14002F4DE
0x14002f4b6  mov     rax, [rcx]
0x14002f4b9  lea     rdx, [rbp+0D8h]
0x14002f4c0  mov     rax, [rax+8]
0x14002f4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f4c9  nop
0x14002f4ca  mov     r8, [rax]
0x14002f4cd  mov     r8d, [r8-10h]
0x14002f4d1  mov     rdx, [rax]
0x14002f4d4  lea     rcx, [rbp+20h]
0x14002f4d8  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14002f4dd  nop
0x14002f4de  mov     rcx, [rbp+0D8h]
0x14002f4e5  or      eax, 0FFFFFFFFh
0x14002f4e8  lock xadd [rcx-8], eax
0x14002f4ed  sub     eax, 1
0x14002f4f0  jg      short loc_14002F50A
0x14002f4f2  lea     rdx, [rcx-18h]
0x14002f4f6  mov     rax, [rcx-18h]
0x14002f4fa  mov     rcx, rax
0x14002f4fd  mov     r8, [rax]
0x14002f500  mov     rax, [r8+8]
0x14002f504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f509  nop
0x14002f50a  mov     rax, 0
0x14002f514  add     rsp, 20h
0x14002f518  pop     rbp
0x14002f519  retn
```
