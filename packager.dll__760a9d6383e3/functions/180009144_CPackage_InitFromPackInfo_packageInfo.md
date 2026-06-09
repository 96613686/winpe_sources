# CPackage::InitFromPackInfo(_packageInfo *)

- ea: `0x180009144`
- end: `0x1800092c7`
- name: `?InitFromPackInfo@CPackage@@IEAAJPEAU_packageInfo@@@Z`
- size: `387`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct _packageInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800050b0`

## callees

- `0x1800073b8`
- `0x180007b28`
- `0x180009144`
- `0x18000a624`
- `0x18000e010`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x1800091e5`
- `SHLWAPI!PathFileExistsW` at `0x1800091e5`

## pseudocode

```c
__int64 __fastcall CPackage::InitFromPackInfo(CPackage *this, struct _packageInfo *a2)
{
  const WCHAR *v2; // r14
  struct _packageInfo *v3; // rbx
  bool v4; // zf
  const unsigned __int16 *v6; // rdx
  __int64 v7; // rbp
  __int64 v8; // rsi
  int v9; // r15d
  __int64 v10; // rcx
  const WCHAR *v11; // rdx
  _WORD *v12; // rax
  __int64 v13; // r8
  _WORD *v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  _WORD *v17; // rcx
  _WORD *v18; // rax
  _WORD *v19; // rcx
  _WORD *v20; // rax
  _WORD *v21; // rcx
  __int64 v22; // rcx

  v2 = (const WCHAR *)((char *)a2 + 520);
  v3 = a2;
  v4 = *((_DWORD *)a2 + 391) == 0;
  v6 = (const unsigned __int16 *)((char *)a2 + 520);
  v7 = 2147483646;
  v8 = 260;
  if ( v4 )
  {
    v9 = CPackage::EmbedInitFromFile(this, v6, 0);
    v10 = 2147483646;
    v11 = v2;
    v12 = (_WORD *)(*((_QWORD *)this + 14) + 72LL);
    v13 = 260;
    do
    {
      if ( !v10 )
        break;
      if ( !*v11 )
        break;
      *v12++ = *v11++;
      --v10;
      --v13;
    }
    while ( v13 );
    v14 = v12 - 1;
    if ( v13 )
      v14 = v12;
    *v14 = 0;
    *((_DWORD *)this + 26) = 3;
  }
  else
  {
    v9 = CPackage::CmlInitFromFile((__int64)this, v6, 0);
  }
  if ( v9 >= 0 )
  {
    if ( PathFileExistsW(v2) )
    {
      v15 = 2147483646;
      v16 = 260;
      v17 = (_WORD *)((char *)v3 + (-(__int64)(*((_WORD *)v3 + 520) != 0) & 0x208) + 520);
      v18 = (_WORD *)(*((_QWORD *)this + 12) + 8LL);
      do
      {
        if ( !v15 )
          break;
        if ( !*v17 )
          break;
        *v18++ = *v17++;
        --v15;
        --v16;
      }
      while ( v16 );
      v19 = v18 - 1;
      if ( v16 )
        v19 = v18;
      *v19 = 0;
    }
    *(_DWORD *)(*((_QWORD *)this + 12) + 1048LL) = *((_DWORD *)v3 + 390);
    v20 = (_WORD *)(*((_QWORD *)this + 12) + 528LL);
    do
    {
      if ( !v7 )
        break;
      if ( !*(_WORD *)v3 )
        break;
      *v20 = *(_WORD *)v3;
      v3 = (struct _packageInfo *)((char *)v3 + 2);
      ++v20;
      --v7;
      --v8;
    }
    while ( v8 );
    v21 = v20 - 1;
    if ( v8 )
      v21 = v20;
    *v21 = 0;
    CPackage::_IconRefresh((HICON **)this);
    v22 = *((_QWORD *)this + 22);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 24LL))(v22);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009144  push    rbx
0x180009146  push    rbp
0x180009147  push    rsi
0x180009148  push    rdi
0x180009149  push    r12
0x18000914b  push    r14
0x18000914d  push    r15
0x18000914f  sub     rsp, 20h
0x180009153  xor     r12d, r12d
0x180009156  lea     r14, [rdx+208h]
0x18000915d  xor     r8d, r8d; int
0x180009160  mov     rbx, rdx
0x180009163  cmp     [rdx+61Ch], r12d
0x18000916a  mov     rdi, rcx
0x18000916d  mov     rdx, r14; unsigned __int16 *
0x180009170  mov     ebp, 7FFFFFFEh
0x180009175  mov     esi, 104h
0x18000917a  jz      short loc_180009186
0x18000917c  call    ?CmlInitFromFile@CPackage@@IEAAJPEBGHW4PANETYPE@@@Z; CPackage::CmlInitFromFile(ushort const *,int,PANETYPE)
0x180009181  mov     r15d, eax
0x180009184  jmp     short loc_1800091D9
0x180009186  call    ?EmbedInitFromFile@CPackage@@IEAAJPEBGH@Z; CPackage::EmbedInitFromFile(ushort const *,int)
0x18000918b  mov     r15d, eax
0x18000918e  mov     rcx, rbp
0x180009191  mov     rax, [rdi+70h]
0x180009195  mov     rdx, r14
0x180009198  add     rax, 48h ; 'H'
0x18000919c  mov     r8, rsi
0x18000919f  test    rcx, rcx
0x1800091a2  jz      short loc_1800091C3
0x1800091a4  movzx   r9d, word ptr [rdx]
0x1800091a8  test    r9w, r9w
0x1800091ac  jz      short loc_1800091C3
0x1800091ae  mov     [rax], r9w
0x1800091b2  add     rdx, 2
0x1800091b6  add     rax, 2
0x1800091ba  dec     rcx
0x1800091bd  sub     r8, 1
0x1800091c1  jnz     short loc_18000919F
0x1800091c3  test    r8, r8
0x1800091c6  lea     rdx, [rax-2]
0x1800091ca  cmovnz  rdx, rax
0x1800091ce  mov     [rdx], r12w
0x1800091d2  mov     dword ptr [rdi+68h], 3
0x1800091d9  test    r15d, r15d
0x1800091dc  js      loc_1800092B5
0x1800091e2  mov     rcx, r14; pszPath
0x1800091e5  call    cs:__imp_PathFileExistsW
0x1800091eb  test    eax, eax
0x1800091ed  jz      short loc_18000924B
0x1800091ef  movzx   eax, word ptr [rbx+410h]
0x1800091f6  mov     r8, rbp
0x1800091f9  neg     ax
0x1800091fc  mov     rdx, rsi
0x1800091ff  mov     eax, 208h
0x180009204  sbb     rcx, rcx
0x180009207  and     rcx, rax
0x18000920a  add     rcx, rax
0x18000920d  mov     rax, [rdi+60h]
0x180009211  add     rcx, rbx
0x180009214  add     rax, 8
0x180009218  test    r8, r8
0x18000921b  jz      short loc_18000923C
0x18000921d  movzx   r9d, word ptr [rcx]
0x180009221  test    r9w, r9w
0x180009225  jz      short loc_18000923C
0x180009227  mov     [rax], r9w
0x18000922b  add     rcx, 2
0x18000922f  add     rax, 2
0x180009233  dec     r8
0x180009236  sub     rdx, 1
0x18000923a  jnz     short loc_180009218
0x18000923c  test    rdx, rdx
0x18000923f  lea     rcx, [rax-2]
0x180009243  cmovnz  rcx, rax
0x180009247  mov     [rcx], r12w
0x18000924b  mov     eax, [rbx+618h]
0x180009251  mov     rcx, [rdi+60h]
0x180009255  mov     [rcx+418h], eax
0x18000925b  mov     rax, [rdi+60h]
0x18000925f  add     rax, 210h
0x180009265  test    rbp, rbp
0x180009268  jz      short loc_180009286
0x18000926a  movzx   ecx, word ptr [rbx]
0x18000926d  test    cx, cx
0x180009270  jz      short loc_180009286
0x180009272  mov     [rax], cx
0x180009275  add     rbx, 2
0x180009279  add     rax, 2
0x18000927d  dec     rbp
0x180009280  sub     rsi, 1
0x180009284  jnz     short loc_180009265
0x180009286  lea     rcx, [rax-2]
0x18000928a  test    rsi, rsi
0x18000928d  cmovnz  rcx, rax
0x180009291  mov     [rcx], r12w
0x180009295  mov     rcx, rdi; this
0x180009298  call    ?_IconRefresh@CPackage@@IEAAJXZ; CPackage::_IconRefresh(void)
0x18000929d  mov     rcx, [rdi+0B0h]
0x1800092a4  test    rcx, rcx
0x1800092a7  jz      short loc_1800092B5
0x1800092a9  mov     rax, [rcx]
0x1800092ac  mov     rax, [rax+18h]
0x1800092b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092b5  mov     eax, r15d
0x1800092b8  add     rsp, 20h
0x1800092bc  pop     r15
0x1800092be  pop     r14
0x1800092c0  pop     r12
0x1800092c2  pop     rdi
0x1800092c3  pop     rsi
0x1800092c4  pop     rbp
0x1800092c5  pop     rbx
0x1800092c6  retn
```
