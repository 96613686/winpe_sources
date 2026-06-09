# std::_Uninit_move<GUIDVarInfo *,GUIDVarInfo *,std::allocator<GUIDVarInfo>,GUIDVarInfo>(GUIDVarInfo *,GUIDVarInfo *,GUIDVarInfo *,std::_Wrap_alloc<std::allocator<GUIDVarInfo>> &,GUIDVarInfo *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x18000c2b4`
- end: `0x18000c326`
- name: `??$_Uninit_move@PEAUGUIDVarInfo@@PEAU1@V?$allocator@UGUIDVarInfo@@@std@@U1@@std@@YAPEAUGUIDVarInfo@@PEAU1@00AEAU?$_Wrap_alloc@V?$allocator@UGUIDVarInfo@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010b18`

## callees

- `0x180005460`
- `0x18000c2b4`

## pseudocode

```c
_OWORD *__fastcall std::_Uninit_move<GUIDVarInfo *,GUIDVarInfo *,std::allocator<GUIDVarInfo>,GUIDVarInfo>(
        _OWORD *a1,
        _OWORD *a2,
        _OWORD *a3)
{
  _OWORD *i; // rdi

  for ( i = a1; i != a2; i += 5 )
  {
    *a3 = *i;
    std::wstring::wstring(a3 + 1, i + 1);
    std::wstring::wstring(a3 + 3, i + 3);
    a3 += 5;
  }
  return a3;
}

```

## disassembly

```asm
0x18000c2b4  mov     rax, rsp
0x18000c2b7  mov     [rax+8], rbx
0x18000c2bb  mov     [rax+10h], rsi
0x18000c2bf  mov     [rax+20h], r9
0x18000c2c3  mov     [rax+18h], r8
0x18000c2c7  push    rdi
0x18000c2c8  sub     rsp, 20h
0x18000c2cc  mov     rbx, r8
0x18000c2cf  mov     rsi, rdx
0x18000c2d2  mov     rdi, rcx
0x18000c2d5  mov     [rsp+28h+arg_18], rbx
0x18000c2da  cmp     rcx, rdx
0x18000c2dd  jz      short loc_18000C312
0x18000c2df  movups  xmm0, xmmword ptr [rdi]
0x18000c2e2  movdqu  xmmword ptr [rbx], xmm0
0x18000c2e6  lea     rdx, [rdi+10h]
0x18000c2ea  lea     rcx, [rbx+10h]
0x18000c2ee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000c2f3  lea     rdx, [rdi+30h]
0x18000c2f7  lea     rcx, [rbx+30h]
0x18000c2fb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000c300  add     rbx, 50h ; 'P'
0x18000c304  mov     [rsp+28h+arg_10], rbx
0x18000c309  add     rdi, 50h ; 'P'
0x18000c30d  cmp     rdi, rsi
0x18000c310  jnz     short loc_18000C2DF
0x18000c312  mov     rax, rbx
0x18000c315  mov     rbx, [rsp+28h+arg_0]
0x18000c31a  mov     rsi, [rsp+28h+arg_8]
0x18000c31f  add     rsp, 20h
0x18000c323  pop     rdi
0x18000c324  retn
```
