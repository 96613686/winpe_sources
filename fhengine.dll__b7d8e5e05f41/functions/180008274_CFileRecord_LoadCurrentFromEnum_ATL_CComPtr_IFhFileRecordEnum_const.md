# CFileRecord::LoadCurrentFromEnum(ATL::CComPtr<IFhFileRecordEnum> const &)

- ea: `0x180008274`
- end: `0x180008356`
- name: `?LoadCurrentFromEnum@CFileRecord@@QEAAJAEBV?$CComPtr@UIFhFileRecordEnum@@@ATL@@@Z`
- size: `226`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008484`
- `0x180010de8`
- `0x180016da0`
- `0x180017290`

## callees

- `0x180007818`
- `0x180008274`
- `0x180034010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180008292`
- `OLEAUT32!__imp_SysFreeString` at `0x180008292`

## pseudocode

```c
__int64 __fastcall CFileRecord::LoadCurrentFromEnum(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // r14
  int v5; // ebx

  v4 = (_QWORD *)(a1 + 24);
  SysFreeString(*(BSTR *)(a1 + 24));
  *v4 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64))(*(_QWORD *)*a2 + 48LL))(
         *a2,
         a1 + 16,
         v4,
         a1 + 32,
         a1 + 36,
         a1 + 40,
         a1 + 42,
         a1 + 48,
         a1 + 56,
         a1 + 60,
         a1 + 64);
  if ( v5 >= 0 )
  {
    *(_WORD *)(a1 + 72) = *(_WORD *)(a1 + 40);
    *(_DWORD *)(a1 + 76) = 0;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids, (unsigned int)v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008274  push    rbx
0x180008276  push    rbp
0x180008277  push    rsi
0x180008278  push    rdi
0x180008279  push    r12
0x18000827b  push    r13
0x18000827d  push    r14
0x18000827f  push    r15
0x180008281  sub     rsp, 68h
0x180008285  mov     rbx, rdx
0x180008288  mov     r13, rcx
0x18000828b  lea     r14, [rcx+18h]
0x18000828f  mov     rcx, [r14]; bstrString
0x180008292  call    cs:__imp_SysFreeString
0x180008298  mov     qword ptr [r14], 0
0x18000829f  mov     rcx, [rbx]
0x1800082a2  lea     r12, [r13+28h]
0x1800082a6  mov     rax, [rcx]
0x1800082a9  lea     r10, [r13+40h]
0x1800082ad  lea     r11, [r13+3Ch]
0x1800082b1  lea     rbx, [r13+38h]
0x1800082b5  lea     rdi, [r13+30h]
0x1800082b9  lea     rsi, [r13+2Ah]
0x1800082bd  lea     rbp, [r13+24h]
0x1800082c1  lea     r9, [r13+20h]
0x1800082c5  mov     [rsp+0A8h+var_58], r10
0x1800082ca  mov     [rsp+0A8h+var_60], r11
0x1800082cf  mov     [rsp+0A8h+var_68], rbx
0x1800082d4  mov     [rsp+0A8h+var_70], rdi
0x1800082d9  mov     [rsp+0A8h+var_78], rsi
0x1800082de  mov     [rsp+0A8h+var_80], r12
0x1800082e3  mov     [rsp+0A8h+var_88], rbp
0x1800082e8  mov     r8, r14
0x1800082eb  lea     rdx, [r13+10h]
0x1800082ef  mov     rax, [rax+30h]
0x1800082f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082f8  mov     ebx, eax
0x1800082fa  test    eax, eax
0x1800082fc  jns     short loc_180008331
0x1800082fe  lea     rax, WPP_GLOBAL_Control
0x180008305  mov     rcx, cs:WPP_GLOBAL_Control
0x18000830c  cmp     rcx, rax
0x18000830f  jz      short loc_180008343
0x180008311  test    byte ptr [rcx+1Ch], 1
0x180008315  jz      short loc_180008343
0x180008317  mov     edx, 0Bh
0x18000831c  mov     r9d, ebx
0x18000831f  lea     r8, WPP_d0c10813b8dd33525641bcb4dab89869_Traceguids
0x180008326  mov     rcx, [rcx+10h]
0x18000832a  call    WPP_SF_d
0x18000832f  jmp     short loc_180008343
0x180008331  movzx   eax, word ptr [r12]
0x180008336  mov     [r13+48h], ax
0x18000833b  mov     dword ptr [r13+4Ch], 0
0x180008343  mov     eax, ebx
0x180008345  add     rsp, 68h
0x180008349  pop     r15
0x18000834b  pop     r14
0x18000834d  pop     r13
0x18000834f  pop     r12
0x180008351  pop     rdi
0x180008352  pop     rsi
0x180008353  pop     rbp
0x180008354  pop     rbx
0x180008355  retn
```
