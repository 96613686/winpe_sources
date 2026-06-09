# CComponentData::NotifySnapinsLogChanged(unsigned __int64,__int64,int)

- ea: `0x1800066dc`
- end: `0x18000682e`
- name: `?NotifySnapinsLogChanged@CComponentData@@QEAAH_K_JH@Z`
- size: `338`
- prototype: `__int64 __fastcall(CComponentData *__hidden this, unsigned __int64, __int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007ee4`
- `0x18001e460`

## callees

- `0x1800066dc`
- `0x18001c400`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall CComponentData::NotifySnapinsLogChanged(
        CComponentData *this,
        unsigned int a2,
        __int64 a3,
        unsigned int a4)
{
  __int64 v8; // rax
  __int64 i; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v13; // rbx
  unsigned int j; // esi
  int v15; // [rsp+20h] [rbp-48h] BYREF
  __int128 v16; // [rsp+24h] [rbp-44h]
  __int64 v17; // [rsp+34h] [rbp-34h]
  int v18; // [rsp+3Ch] [rbp-2Ch]
  __int64 v19; // [rsp+40h] [rbp-28h]
  __int64 v20; // [rsp+48h] [rbp-20h]
  __int64 v21; // [rsp+50h] [rbp-18h]

  if ( a2 == 4 )
  {
    v8 = *((_QWORD *)this + 10);
LABEL_3:
    if ( v8 )
    {
      for ( i = *(_QWORD *)(v8 + 136); ; i = *(_QWORD *)(i + 8) )
      {
        if ( !i )
        {
          v8 = *(_QWORD *)(v8 + 8);
          goto LABEL_3;
        }
        if ( a3 == i )
          break;
      }
      v10 = *((_QWORD *)this + 145);
      v20 = *((_QWORD *)this + 142);
      v21 = *(_QWORD *)(a3 + 4856);
      v16 = 0;
      v17 = 0;
      v18 = 0;
      v15 = 32;
      v19 = a3;
      if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 48LL))(v10, &v15) >= 0 )
      {
        v15 = 46;
        if ( (*(_WORD *)(a3 + 24) & 0x200) != 0 )
        {
          HIDWORD(v16) = 2;
          LODWORD(v17) = 2;
        }
        else
        {
          HIDWORD(v16) = 0;
          LODWORD(v17) = 1;
        }
        v11 = *((_QWORD *)this + 145);
        *(_QWORD *)((char *)&v16 + 4) = -1;
        v19 = a3;
        (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 40LL))(v11, &v15);
      }
    }
    return 0;
  }
  else
  {
    v13 = *((_QWORD *)this + 8);
    for ( j = 0; v13; v13 = (*(_QWORD *)(v13 + 64) - 56LL) & -(__int64)(*(_QWORD *)(v13 + 64) != 0) )
    {
      if ( !a4 || j )
        CSnapin::HandleLogChange(v13, a2, a3, 0);
      else
        j = CSnapin::HandleLogChange(v13, a2, a3, a4);
    }
    return j;
  }
}

```

## disassembly

```asm
0x1800066dc  push    rbp
0x1800066de  push    rbx
0x1800066df  push    rsi
0x1800066e0  push    rdi
0x1800066e1  push    r14
0x1800066e3  push    r15
0x1800066e5  mov     rbp, rsp
0x1800066e8  sub     rsp, 68h
0x1800066ec  mov     r15d, r9d
0x1800066ef  mov     rdi, r8
0x1800066f2  mov     r14, rdx
0x1800066f5  mov     rbx, rcx
0x1800066f8  cmp     edx, 4
0x1800066fb  jnz     loc_1800067D2
0x180006701  mov     rax, [rcx+50h]
0x180006705  test    rax, rax
0x180006708  jz      loc_1800067CE
0x18000670e  mov     rcx, [rax+88h]
0x180006715  test    rcx, rcx
0x180006718  jz      short loc_180006725
0x18000671a  cmp     rdi, rcx
0x18000671d  jz      short loc_18000672B
0x18000671f  mov     rcx, [rcx+8]
0x180006723  jmp     short loc_180006715
0x180006725  mov     rax, [rax+8]
0x180006729  jmp     short loc_180006705
0x18000672b  mov     rax, [rbx+470h]
0x180006732  lea     rdx, [rbp+var_48]
0x180006736  mov     rcx, [rbx+488h]
0x18000673d  xorps   xmm0, xmm0
0x180006740  mov     [rbp+var_20], rax
0x180006744  mov     rax, [r8+12F8h]
0x18000674b  mov     [rbp+var_18], rax
0x18000674f  movdqu  [rbp+var_44], xmm0
0x180006754  mov     [rbp+var_34], 0
0x18000675c  mov     [rbp+var_2C], 0
0x180006763  mov     [rbp+var_48], 20h ; ' '
0x18000676a  mov     [rbp+var_28], rdi
0x18000676e  mov     rax, [rcx]
0x180006771  mov     rax, [rax+30h]
0x180006775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000677a  test    eax, eax
0x18000677c  js      short loc_1800067CE
0x18000677e  mov     eax, 200h
0x180006783  mov     [rbp+var_48], 2Eh ; '.'
0x18000678a  test    [rdi+18h], ax
0x18000678e  jz      short loc_18000679D
0x180006790  mov     eax, 2
0x180006795  mov     dword ptr [rbp+var_44+0Ch], eax
0x180006798  mov     dword ptr [rbp+var_34], eax
0x18000679b  jmp     short loc_1800067AB
0x18000679d  mov     dword ptr [rbp+var_44+0Ch], 0
0x1800067a4  mov     dword ptr [rbp+var_34], 1
0x1800067ab  mov     rcx, [rbx+488h]
0x1800067b2  lea     rdx, [rbp+var_48]
0x1800067b6  mov     qword ptr [rbp+var_44+4], 0FFFFFFFFFFFFFFFFh
0x1800067be  mov     [rbp+var_28], rdi
0x1800067c2  mov     rax, [rcx]
0x1800067c5  mov     rax, [rax+28h]
0x1800067c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067ce  xor     eax, eax
0x1800067d0  jmp     short loc_180006821
0x1800067d2  mov     rbx, [rcx+40h]
0x1800067d6  xor     esi, esi
0x1800067d8  test    rbx, rbx
0x1800067db  jz      short loc_18000681F
0x1800067dd  test    r15d, r15d
0x1800067e0  jz      short loc_1800067FB
0x1800067e2  test    esi, esi
0x1800067e4  jnz     short loc_1800067FB
0x1800067e6  mov     r9d, r15d
0x1800067e9  mov     r8, rdi
0x1800067ec  mov     edx, r14d
0x1800067ef  mov     rcx, rbx
0x1800067f2  call    ?HandleLogChange@CSnapin@@QEAAHW4LOGDATACHANGE@@PEAVCLogInfo@@H@Z; CSnapin::HandleLogChange(LOGDATACHANGE,CLogInfo *,int)
0x1800067f7  mov     esi, eax
0x1800067f9  jmp     short loc_18000680C
0x1800067fb  xor     r9d, r9d
0x1800067fe  mov     r8, rdi
0x180006801  mov     edx, r14d
0x180006804  mov     rcx, rbx
0x180006807  call    ?HandleLogChange@CSnapin@@QEAAHW4LOGDATACHANGE@@PEAVCLogInfo@@H@Z; CSnapin::HandleLogChange(LOGDATACHANGE,CLogInfo *,int)
0x18000680c  mov     rax, [rbx+40h]
0x180006810  lea     rcx, [rax-38h]
0x180006814  neg     rax
0x180006817  sbb     rbx, rbx
0x18000681a  and     rbx, rcx
0x18000681d  jnz     short loc_1800067DD
0x18000681f  mov     eax, esi
0x180006821  add     rsp, 68h
0x180006825  pop     r15
0x180006827  pop     r14
0x180006829  pop     rdi
0x18000682a  pop     rsi
0x18000682b  pop     rbx
0x18000682c  pop     rbp
0x18000682d  retn
```
