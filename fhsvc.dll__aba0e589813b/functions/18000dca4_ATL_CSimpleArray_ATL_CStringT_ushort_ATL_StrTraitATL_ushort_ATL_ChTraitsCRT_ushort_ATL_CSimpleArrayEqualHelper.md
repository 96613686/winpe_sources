# ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAt(int)

- ea: `0x18000dca4`
- end: `0x18000dd1f`
- name: `?RemoveAt@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAHH@Z`
- size: `123`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000df70`
- `0x18000e8b0`

## callees

- `0x18000ac14`
- `0x18000ba7c`
- `0x18000dca4`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000dcf6`
- `msvcrt!memmove_s` at `0x18000dcf6`

## pseudocode

```c
__int64 __fastcall ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAt(
        __int64 a1,
        int a2)
{
  __int64 v2; // rdi
  int v4; // edx
  errno_t v5; // eax

  v2 = a2;
  if ( a2 < 0 || a2 >= *(_DWORD *)(a1 + 8) )
    return 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(*(_QWORD *)a1 + 8LL * a2));
  v4 = *(_DWORD *)(a1 + 8);
  if ( (_DWORD)v2 != v4 - 1 )
  {
    v5 = memmove_s(
           (void *const)(*(_QWORD *)a1 + 8 * v2),
           8LL * (v4 - (int)v2),
           (const void *const)(*(_QWORD *)a1 + 8 * v2 + 8),
           8LL * (v4 - (int)v2 - 1));
    ATL::AtlCrtErrorCheck(v5);
  }
  --*(_DWORD *)(a1 + 8);
  return 1;
}

```

## disassembly

```asm
0x18000dca4  mov     [rsp+arg_0], rbx
0x18000dca9  mov     [rsp+arg_8], rsi
0x18000dcae  push    rdi
0x18000dcaf  sub     rsp, 20h
0x18000dcb3  movsxd  rdi, edx
0x18000dcb6  mov     rbx, rcx
0x18000dcb9  test    edx, edx
0x18000dcbb  js      short loc_18000DD0D
0x18000dcbd  cmp     edi, [rcx+8]
0x18000dcc0  jge     short loc_18000DD0D
0x18000dcc2  mov     rax, [rcx]
0x18000dcc5  lea     rcx, [rax+rdi*8]
0x18000dcc9  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000dcce  mov     edx, [rbx+8]
0x18000dcd1  lea     eax, [rdx-1]
0x18000dcd4  cmp     edi, eax
0x18000dcd6  jz      short loc_18000DD03
0x18000dcd8  mov     rax, [rbx]
0x18000dcdb  sub     edx, edi
0x18000dcdd  lea     rcx, [rax+rdi*8]; Destination
0x18000dce1  lea     eax, [rdx-1]
0x18000dce4  movsxd  rdx, edx
0x18000dce7  movsxd  r9, eax
0x18000dcea  lea     r8, [rcx+8]; Source
0x18000dcee  shl     r9, 3; SourceSize
0x18000dcf2  shl     rdx, 3; DestinationSize
0x18000dcf6  call    cs:__imp_memmove_s
0x18000dcfc  mov     ecx, eax; int
0x18000dcfe  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000dd03  dec     dword ptr [rbx+8]
0x18000dd06  mov     eax, 1
0x18000dd0b  jmp     short loc_18000DD0F
0x18000dd0d  xor     eax, eax
0x18000dd0f  mov     rbx, [rsp+28h+arg_0]
0x18000dd14  mov     rsi, [rsp+28h+arg_8]
0x18000dd19  add     rsp, 20h
0x18000dd1d  pop     rdi
0x18000dd1e  retn
```
