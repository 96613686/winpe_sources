# ATL::IDispatchImpl<ICtTuner,&_GUID const IID_ICtTuner,&_GUID const LIBID_cttunesvrLib,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(_GUID const &,ushort * *,uint,ulong,long *)

- ea: `0x140003100`
- end: `0x1400031ec`
- name: `?GetIDsOfNames@?$IDispatchImpl@UICtTuner@@$1?IID_ICtTuner@@3U_GUID@@B$1?LIBID_cttunesvrLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJAEBU_GUID@@PEAPEAGIKPEAJ@Z`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003100`
- `0x1400031f4`
- `0x1400065c6`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ICtTuner,&_GUID const IID_ICtTuner,&_GUID const LIBID_cttunesvrLib,1,0,ATL::CComTypeInfoHolder>::GetIDsOfNames(
        ATL::CComTypeInfoHolder *a1,
        __int64 a2,
        const void **a3,
        unsigned int a4,
        LCID a5,
        _DWORD *a6)
{
  struct ITypeInfo *v6; // r14
  __int64 v9; // rbx
  __int64 result; // rax
  _WORD *v11; // r15
  __int64 v12; // rsi
  unsigned int v13; // ebp

  v6 = qword_14000B068;
  if ( !qword_14000B068 || (v9 = qword_14000B078, result = 0, !qword_14000B078) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(a1, a5);
    v9 = qword_14000B078;
    v6 = qword_14000B068;
  }
  if ( v6 )
  {
    if ( v9 && a4 == 1 )
    {
      v11 = *a3;
      if ( *a3 )
      {
        v12 = -1;
        do
          ++v12;
        while ( v11[v12] );
      }
      else
      {
        LODWORD(v12) = 0;
      }
      v13 = dword_14000B080;
      while ( (--v13 & 0x80000000) == 0 )
      {
        if ( (_DWORD)v12 == *(_DWORD *)(v9 + 16LL * v13 + 8)
          && !memcmp_0(*(const void **)(v9 + 16LL * v13), v11, 2LL * *(int *)(v9 + 16LL * v13 + 8)) )
        {
          *a6 = *(_DWORD *)(v9 + 16LL * v13 + 12);
          return 0;
        }
      }
    }
    return ((__int64 (__fastcall *)(struct ITypeInfo *, const void **, _QWORD, _DWORD *))v6->lpVtbl->GetIDsOfNames)(
             v6,
             a3,
             a4,
             a6);
  }
  return result;
}

```

## disassembly

```asm
0x140003100  push    rbx
0x140003102  push    rbp
0x140003103  push    rsi
0x140003104  push    rdi
0x140003105  push    r12
0x140003107  push    r13
0x140003109  push    r14
0x14000310b  push    r15
0x14000310d  sub     rsp, 38h
0x140003111  mov     r14, cs:qword_14000B068
0x140003118  xor     edx, edx
0x14000311a  mov     r12d, r9d
0x14000311d  mov     r13, r8
0x140003120  test    r14, r14
0x140003123  jz      short loc_140003133
0x140003125  mov     rbx, cs:qword_14000B078
0x14000312c  mov     eax, edx
0x14000312e  test    rbx, rbx
0x140003131  jnz     short loc_14000314F
0x140003133  mov     edx, [rsp+78h+arg_20]; unsigned int
0x14000313a  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x14000313f  mov     rbx, cs:qword_14000B078
0x140003146  xor     edx, edx
0x140003148  mov     r14, cs:qword_14000B068
0x14000314f  test    r14, r14
0x140003152  jz      short loc_1400031C9
0x140003154  test    rbx, rbx
0x140003157  jz      short loc_1400031AC
0x140003159  cmp     r12d, 1
0x14000315d  jnz     short loc_1400031AC
0x14000315f  mov     r15, [r13+0]
0x140003163  test    r15, r15
0x140003166  jnz     short loc_14000316C
0x140003168  mov     esi, edx
0x14000316a  jmp     short loc_14000317A
0x14000316c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140003170  inc     rsi
0x140003173  cmp     [r15+rsi*2], dx
0x140003178  jnz     short loc_140003170
0x14000317a  mov     ebp, cs:dword_14000B080
0x140003180  jmp     short loc_1400031A7
0x140003182  mov     edi, ebp
0x140003184  add     rdi, rdi
0x140003187  cmp     esi, [rbx+rdi*8+8]
0x14000318b  jnz     short loc_1400031A7
0x14000318d  movsxd  r8, dword ptr [rbx+rdi*8+8]
0x140003192  mov     rdx, r15; Buf2
0x140003195  mov     rcx, [rbx+rdi*8]; Buf1
0x140003199  add     r8, r8; Size
0x14000319c  call    memcmp_0
0x1400031a1  xor     edx, edx
0x1400031a3  test    eax, eax
0x1400031a5  jz      short loc_1400031DA
0x1400031a7  sub     ebp, 1
0x1400031aa  jns     short loc_140003182
0x1400031ac  mov     rax, [r14]
0x1400031af  mov     r8d, r12d
0x1400031b2  mov     r9, [rsp+78h+arg_28]
0x1400031ba  mov     rdx, r13
0x1400031bd  mov     rcx, r14
0x1400031c0  mov     rax, [rax+50h]
0x1400031c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031c9  add     rsp, 38h
0x1400031cd  pop     r15
0x1400031cf  pop     r14
0x1400031d1  pop     r13
0x1400031d3  pop     r12
0x1400031d5  pop     rdi
0x1400031d6  pop     rsi
0x1400031d7  pop     rbp
0x1400031d8  pop     rbx
0x1400031d9  retn
0x1400031da  mov     rax, [rsp+78h+arg_28]
0x1400031e2  mov     ecx, [rbx+rdi*8+0Ch]
0x1400031e6  mov     [rax], ecx
0x1400031e8  mov     eax, edx
0x1400031ea  jmp     short loc_1400031C9
```
