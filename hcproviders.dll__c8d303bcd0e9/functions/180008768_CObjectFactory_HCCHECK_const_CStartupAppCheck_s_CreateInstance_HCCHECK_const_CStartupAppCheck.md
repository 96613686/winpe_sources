# CObjectFactory<HCCHECK const *,CStartupAppCheck>::s_CreateInstance(HCCHECK const *,CStartupAppCheck * *)

- ea: `0x180008768`
- end: `0x18000880e`
- name: `?s_CreateInstance@?$CObjectFactory@PEBUHCCHECK@@VCStartupAppCheck@@@@SAJPEBUHCCHECK@@PEAPEAVCStartupAppCheck@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(struct HCCHECK *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180008410`

## callees

- `0x180002770`
- `0x180002e30`
- `0x180004fc8`
- `0x180008768`
- `0x180009e16`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall CObjectFactory<HCCHECK const *,CStartupAppCheck>::s_CreateInstance(const IID *a1, CCheckBase **a2)
{
  CCheckBase *v4; // rax
  CCheckBase *v5; // rbx
  CCheckBase *v6; // rcx
  int v7; // edi

  v4 = (CCheckBase *)operator new(0xF8u);
  v5 = v4;
  if ( v4 )
  {
    memset_0(v4, 0, 0xF8u);
    CCheckBase::CCheckBase(v5);
    *((_QWORD *)v5 + 28) = 0;
    *(_QWORD *)v5 = &CStartupAppCheck::`vftable';
    *((_QWORD *)v5 + 29) = 0;
    *((_QWORD *)v5 + 30) = 0;
    v7 = CCheckBase::_Initialize(v6, a1);
    if ( v7 < 0 )
      (*(void (__fastcall **)(CCheckBase *))(*(_QWORD *)v5 + 16LL))(v5);
    else
      *a2 = v5;
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008768  mov     [rsp+arg_0], rbx
0x18000876d  mov     [rsp+arg_8], rsi
0x180008772  push    rdi
0x180008773  sub     rsp, 20h
0x180008777  mov     rdi, rcx
0x18000877a  mov     rsi, rdx
0x18000877d  mov     ecx, 0F8h; Size
0x180008782  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008787  mov     rbx, rax
0x18000878a  test    rax, rax
0x18000878d  jz      short loc_1800087F6
0x18000878f  xor     edx, edx; Val
0x180008791  mov     r8d, 0F8h; Size
0x180008797  mov     rcx, rax; void *
0x18000879a  call    memset_0
0x18000879f  mov     rcx, rbx; this
0x1800087a2  call    ??0CCheckBase@@IEAA@XZ; CCheckBase::CCheckBase(void)
0x1800087a7  lea     rax, ??_7CStartupAppCheck@@6B@; const CStartupAppCheck::`vftable'
0x1800087ae  mov     qword ptr [rbx+0E0h], 0
0x1800087b9  mov     rdx, rdi; struct HCCHECK *
0x1800087bc  mov     [rbx], rax
0x1800087bf  mov     qword ptr [rbx+0E8h], 0
0x1800087ca  mov     qword ptr [rbx+0F0h], 0
0x1800087d5  call    ?_Initialize@CCheckBase@@IEAAJPEBUHCCHECK@@@Z; CCheckBase::_Initialize(HCCHECK const *)
0x1800087da  mov     edi, eax
0x1800087dc  test    eax, eax
0x1800087de  js      short loc_1800087E5
0x1800087e0  mov     [rsi], rbx
0x1800087e3  jmp     short loc_1800087FB
0x1800087e5  mov     rax, [rbx]
0x1800087e8  mov     rcx, rbx
0x1800087eb  mov     rax, [rax+10h]
0x1800087ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087f4  jmp     short loc_1800087FB
0x1800087f6  mov     edi, 8007000Eh
0x1800087fb  mov     rbx, [rsp+28h+arg_0]
0x180008800  mov     eax, edi
0x180008802  mov     rsi, [rsp+28h+arg_8]
0x180008807  add     rsp, 20h
0x18000880b  pop     rdi
0x18000880c  retn
```
