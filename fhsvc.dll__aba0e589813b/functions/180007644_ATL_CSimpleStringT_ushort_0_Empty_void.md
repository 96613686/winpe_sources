# ATL::CSimpleStringT<ushort,0>::Empty(void)

- ea: `0x180007644`
- end: `0x180007699`
- name: `?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ`
- size: `85`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180007720`
- `0x180007800`
- `0x180008b30`
- `0x18000ee2c`
- `0x180010894`

## callees

- `0x180007644`
- `0x1800076a0`
- `0x18000ba44`
- `0x180013010`

## pseudocode

```c
void __fastcall ATL::CSimpleStringT<unsigned short,0>::Empty(_QWORD *a1)
{
  ATL::CStringData *v2; // rcx
  __int64 v3; // rbx

  v2 = (ATL::CStringData *)(*a1 - 24LL);
  if ( *((_DWORD *)v2 + 2) )
  {
    if ( *((int *)v2 + 4) >= 0 )
    {
      v3 = *(_QWORD *)v2;
      ATL::CStringData::Release(v2);
      *a1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3) + 24;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, 0);
    }
  }
}

```

## disassembly

```asm
0x180007644  mov     [rsp+arg_0], rbx
0x180007649  push    rdi
0x18000764a  sub     rsp, 20h
0x18000764e  mov     rdi, rcx
0x180007651  mov     rcx, [rcx]
0x180007654  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180007658  cmp     dword ptr [rcx+8], 0
0x18000765c  jz      short loc_18000768E
0x18000765e  cmp     dword ptr [rcx+10h], 0
0x180007662  jge     short loc_180007670
0x180007664  xor     edx, edx
0x180007666  mov     rcx, rdi
0x180007669  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18000766e  jmp     short loc_18000768E
0x180007670  mov     rbx, [rcx]
0x180007673  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007678  mov     rax, [rbx]
0x18000767b  mov     rcx, rbx
0x18000767e  mov     rax, [rax+18h]
0x180007682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007687  add     rax, 18h
0x18000768b  mov     [rdi], rax
0x18000768e  mov     rbx, [rsp+28h+arg_0]
0x180007693  add     rsp, 20h
0x180007697  pop     rdi
0x180007698  retn
```
