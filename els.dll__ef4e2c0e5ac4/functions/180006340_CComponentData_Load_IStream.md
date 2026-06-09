# CComponentData::Load(IStream *)

- ea: `0x180006340`
- end: `0x1800065c2`
- name: `?Load@CComponentData@@UEAAJPEAUIStream@@@Z`
- size: `642`
- prototype: `__int64 __fastcall(CComponentData *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002928`
- `0x180006340`
- `0x18000726c`
- `0x180008b70`
- `0x180015f90`
- `0x180022292`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall CComponentData::Load(CComponentData *this, struct IStream *a2)
{
  __int64 v2; // rax
  int ViewsFromStream; // ebx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 result; // rax
  unsigned __int16 i; // r15
  char *v11; // rax
  CLogSet *v12; // rsi
  struct IStringTable *v13; // r12
  unsigned __int16 v14; // r13
  _WORD v15[8]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 v16; // [rsp+88h] [rbp+48h] BYREF
  unsigned __int16 v17; // [rsp+90h] [rbp+50h] BYREF
  __int16 v18; // [rsp+98h] [rbp+58h] BYREF

  v2 = *(_QWORD *)a2;
  v17 = 0;
  ViewsFromStream = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int16 *, __int64, _QWORD))(v2 + 24))(
                      a2,
                      &v17,
                      2,
                      0);
  if ( ViewsFromStream < 0 )
    return (unsigned int)ViewsFromStream;
  if ( (unsigned __int16)(v17 - 512) > 0x1FFu )
    return (unsigned int)ViewsFromStream;
  v6 = *(_QWORD *)a2;
  v18 = 0;
  ViewsFromStream = (*(__int64 (__fastcall **)(struct IStream *, __int16 *, __int64, _QWORD))(v6 + 24))(a2, &v18, 2, 0);
  if ( ViewsFromStream < 0 )
    return (unsigned int)ViewsFromStream;
  *((_WORD *)this + 28) |= v18;
  v7 = *(_QWORD *)a2;
  v16 = 0;
  ViewsFromStream = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int16 *, __int64, _QWORD))(v7 + 24))(
                      a2,
                      &v16,
                      2,
                      0);
  if ( ViewsFromStream < 0 )
    return (unsigned int)ViewsFromStream;
  if ( v16 > 0x106u )
    return (unsigned int)-2147467259;
  ViewsFromStream = (*(__int64 (__fastcall **)(struct IStream *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL))(
                      a2,
                      (char *)this + 88,
                      2 * (unsigned int)v16,
                      0);
  if ( ViewsFromStream < 0 )
    return (unsigned int)ViewsFromStream;
  ViewsFromStream = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int16 *, __int64, _QWORD))(*(_QWORD *)a2 + 24LL))(
                      a2,
                      &v16,
                      2,
                      0);
  if ( ViewsFromStream < 0 )
    return (unsigned int)ViewsFromStream;
  if ( v16 > 0x105u )
    return (unsigned int)-2147467259;
  ViewsFromStream = (*(__int64 (__fastcall **)(struct IStream *, char *, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL))(
                      a2,
                      (char *)this + 612,
                      2 * (unsigned int)v16,
                      0);
  if ( ViewsFromStream < 0 )
    return (unsigned int)ViewsFromStream;
  if ( g_fMachineNameOverride && (*((_BYTE *)this + 56) & 0x40) != 0 )
    CComponentData::_UpdateCurFocusSystemRoot(this);
  v8 = *(_QWORD *)a2;
  v15[0] = 0;
  result = (*(__int64 (__fastcall **)(struct IStream *, _WORD *, __int64, _QWORD))(v8 + 24))(a2, v15, 2, 0);
  ViewsFromStream = result;
  if ( (int)result >= 0 )
  {
    for ( i = 0; i < v15[0]; ++i )
    {
      v11 = (char *)operator new(0x90u);
      v12 = (CLogSet *)v11;
      if ( !v11 )
        return (unsigned int)-2147024882;
      *((_QWORD *)v11 + 1) = 0;
      *((_QWORD *)v11 + 2) = 0;
      *((_WORD *)v11 + 12) = 0;
      *(_QWORD *)v11 = &CLogSet::`vftable';
      *((_QWORD *)v11 + 4) = this;
      *((_QWORD *)v11 + 5) = 0;
      *((_QWORD *)v11 + 6) = 0;
      *((_QWORD *)v11 + 17) = 0;
      memset_0(v11 + 56, 0, 0x50u);
      v13 = (struct IStringTable *)*((_QWORD *)this + 147);
      v14 = v17;
      ViewsFromStream = (*(__int64 (__fastcall **)(struct IStream *, __int64, __int64))(*(_QWORD *)a2 + 24LL))(
                          a2,
                          (__int64)v12 + 56,
                          80);
      if ( ViewsFromStream >= 0 )
        ViewsFromStream = CLogSet::LoadViewsFromStream(v12, a2, v14, v13);
      if ( ViewsFromStream < 0 )
      {
        (**(void (__fastcall ***)(CLogSet *, __int64))v12)(v12, 1);
        return (unsigned int)ViewsFromStream;
      }
      CComponentData::_AddLogSetToList(this, v12);
    }
    return (unsigned int)ViewsFromStream;
  }
  return result;
}

```

## disassembly

```asm
0x180006340  mov     [rsp-38h+arg_0], rbx
0x180006345  push    rbp
0x180006346  push    rsi
0x180006347  push    rdi
0x180006348  push    r12
0x18000634a  push    r13
0x18000634c  push    r14
0x18000634e  push    r15
0x180006350  mov     rbp, rsp
0x180006353  sub     rsp, 40h
0x180006357  mov     rax, [rdx]
0x18000635a  mov     rdi, rdx
0x18000635d  xor     r12d, r12d
0x180006360  lea     rdx, [rbp+arg_10]
0x180006364  mov     r14, rcx
0x180006367  mov     [rbp+arg_10], r12w
0x18000636c  xor     r9d, r9d
0x18000636f  mov     rcx, rdi
0x180006372  mov     rax, [rax+18h]
0x180006376  lea     esi, [r12+2]
0x18000637b  mov     r8d, esi
0x18000637e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006383  mov     ebx, eax
0x180006385  test    eax, eax
0x180006387  js      loc_1800065A8
0x18000638d  movzx   ecx, [rbp+arg_10]
0x180006391  mov     eax, 200h
0x180006396  sub     cx, ax
0x180006399  mov     eax, 1FFh
0x18000639e  cmp     cx, ax
0x1800063a1  ja      loc_1800065A8
0x1800063a7  mov     rax, [rdi]
0x1800063aa  lea     rdx, [rbp+arg_18]
0x1800063ae  xor     r9d, r9d
0x1800063b1  mov     [rbp+arg_18], r12w
0x1800063b6  mov     r8d, esi
0x1800063b9  mov     rcx, rdi
0x1800063bc  mov     rax, [rax+18h]
0x1800063c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063c5  mov     ebx, eax
0x1800063c7  test    eax, eax
0x1800063c9  js      loc_1800065A8
0x1800063cf  movzx   eax, [rbp+arg_18]
0x1800063d3  lea     rdx, [rbp+arg_8]
0x1800063d7  or      [r14+38h], ax
0x1800063dc  xor     r9d, r9d
0x1800063df  mov     rax, [rdi]
0x1800063e2  mov     r8d, esi
0x1800063e5  mov     rcx, rdi
0x1800063e8  mov     [rbp+arg_8], r12w
0x1800063ed  mov     rax, [rax+18h]
0x1800063f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063f6  mov     ebx, eax
0x1800063f8  test    eax, eax
0x1800063fa  js      loc_1800065A8
0x180006400  mov     eax, 106h
0x180006405  cmp     [rbp+arg_8], ax
0x180006409  jbe     short loc_180006415
0x18000640b  mov     ebx, 80004005h
0x180006410  jmp     loc_1800065A8
0x180006415  mov     rax, [rdi]
0x180006418  lea     rdx, [r14+58h]
0x18000641c  movzx   r8d, [rbp+arg_8]
0x180006421  xor     r9d, r9d
0x180006424  add     r8d, r8d
0x180006427  mov     rcx, rdi
0x18000642a  mov     rax, [rax+18h]
0x18000642e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006433  mov     ebx, eax
0x180006435  test    eax, eax
0x180006437  js      loc_1800065A8
0x18000643d  mov     rax, [rdi]
0x180006440  lea     rdx, [rbp+arg_8]
0x180006444  xor     r9d, r9d
0x180006447  mov     r8d, esi
0x18000644a  mov     rcx, rdi
0x18000644d  mov     rax, [rax+18h]
0x180006451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006456  mov     ebx, eax
0x180006458  test    eax, eax
0x18000645a  js      loc_1800065A8
0x180006460  mov     eax, 105h
0x180006465  cmp     [rbp+arg_8], ax
0x180006469  ja      short loc_18000640B
0x18000646b  mov     rax, [rdi]
0x18000646e  lea     rdx, [r14+264h]
0x180006475  movzx   r8d, [rbp+arg_8]
0x18000647a  xor     r9d, r9d
0x18000647d  add     r8d, r8d
0x180006480  mov     rcx, rdi
0x180006483  mov     rax, [rax+18h]
0x180006487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000648c  mov     ebx, eax
0x18000648e  test    eax, eax
0x180006490  js      loc_1800065A8
0x180006496  cmp     cs:?g_fMachineNameOverride@@3HA, r12d; int g_fMachineNameOverride
0x18000649d  jz      short loc_1800064AE
0x18000649f  test    byte ptr [r14+38h], 40h
0x1800064a4  jz      short loc_1800064AE
0x1800064a6  mov     rcx, r14; this
0x1800064a9  call    ?_UpdateCurFocusSystemRoot@CComponentData@@AEAAXXZ; CComponentData::_UpdateCurFocusSystemRoot(void)
0x1800064ae  mov     rax, [rdi]
0x1800064b1  lea     rdx, [rbp+var_10]
0x1800064b5  xor     r9d, r9d
0x1800064b8  mov     [rbp+var_10], r12w
0x1800064bd  mov     r8d, esi
0x1800064c0  mov     rcx, rdi
0x1800064c3  mov     rax, [rax+18h]
0x1800064c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064cc  mov     ebx, eax
0x1800064ce  test    eax, eax
0x1800064d0  js      loc_1800065AA
0x1800064d6  mov     r15d, r12d
0x1800064d9  cmp     r15w, [rbp+var_10]
0x1800064de  jnb     loc_1800065A8
0x1800064e4  mov     ecx, 90h; Size
0x1800064e9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800064ee  mov     rsi, rax
0x1800064f1  test    rax, rax
0x1800064f4  jz      loc_1800065A3
0x1800064fa  mov     [rax+8], r12
0x1800064fe  lea     rcx, [rsi+38h]; void *
0x180006502  mov     [rax+10h], r12
0x180006506  xor     edx, edx; Val
0x180006508  mov     [rax+18h], r12w
0x18000650d  lea     rax, ??_7CLogSet@@6B@; const CLogSet::`vftable'
0x180006514  mov     [rsi], rax
0x180006517  mov     [rsi+20h], r14
0x18000651b  lea     r8d, [rdx+50h]; Size
0x18000651f  mov     [rsi+28h], r12
0x180006523  mov     [rsi+30h], r12
0x180006527  mov     [rsi+88h], r12
0x18000652e  call    memset_0
0x180006533  mov     rax, [rdi]
0x180006536  lea     rdx, [rsi+38h]
0x18000653a  mov     r12, [r14+498h]
0x180006541  xor     r9d, r9d
0x180006544  movzx   r13d, [rbp+arg_10]
0x180006549  mov     rcx, rdi
0x18000654c  mov     rax, [rax+18h]
0x180006550  lea     r8d, [r9+50h]
0x180006554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006559  mov     ebx, eax
0x18000655b  test    eax, eax
0x18000655d  js      short loc_180006573
0x18000655f  mov     r9, r12; struct IStringTable *
0x180006562  movzx   r8d, r13w; unsigned __int16
0x180006566  mov     rdx, rdi; struct IStream *
0x180006569  mov     rcx, rsi; this
0x18000656c  call    ?LoadViewsFromStream@CLogSet@@QEAAJPEAUIStream@@GPEAUIStringTable@@@Z; CLogSet::LoadViewsFromStream(IStream *,ushort,IStringTable *)
0x180006571  mov     ebx, eax
0x180006573  xor     r12d, r12d
0x180006576  test    ebx, ebx
0x180006578  js      short loc_18000658E
0x18000657a  mov     rdx, rsi; struct CLogSet *
0x18000657d  mov     rcx, r14; this
0x180006580  call    ?_AddLogSetToList@CComponentData@@AEAAXPEAVCLogSet@@@Z; CComponentData::_AddLogSetToList(CLogSet *)
0x180006585  inc     r15w
0x180006589  jmp     loc_1800064D9
0x18000658e  mov     rax, [rsi]
0x180006591  mov     edx, 1
0x180006596  mov     rcx, rsi
0x180006599  mov     rax, [rax]
0x18000659c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065a1  jmp     short loc_1800065A8
0x1800065a3  mov     ebx, 8007000Eh
0x1800065a8  mov     eax, ebx
0x1800065aa  mov     rbx, [rsp+40h+arg_0]
0x1800065b2  add     rsp, 40h
0x1800065b6  pop     r15
0x1800065b8  pop     r14
0x1800065ba  pop     r13
0x1800065bc  pop     r12
0x1800065be  pop     rdi
0x1800065bf  pop     rsi
0x1800065c0  pop     rbp
0x1800065c1  retn
```
