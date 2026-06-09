# MakeTypeInfo(int,int,ushort * *,ITypeInfo * *)

- ea: `0x180085330`
- end: `0x1800855df`
- name: `?MakeTypeInfo@@YAJHHPEAPEAGPEAPEAUITypeInfo@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(int, int, unsigned __int16 **, struct ITypeInfo **)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180084cd0`
- `0x180084e58`
- `0x18008e128`

## callees

- `0x180084210`
- `0x180085330`
- `0x18009429a`
- `0x1800942d0`
- `0x180094360`
- `0x180096010`

## import_xrefs

- `OLEAUT32!__imp_CreateTypeLib2` at `0x1800853b0`
- `OLEAUT32!__imp_CreateTypeLib2` at `0x1800853b0`

## pseudocode

```c
__int64 __fastcall MakeTypeInfo(int a1, int a2, unsigned __int16 **a3, struct ITypeInfo **a4)
{
  unsigned __int64 v4; // rdi
  HRESULT v8; // ebx
  size_t v9; // r8
  __int64 v10; // rax
  void *v11; // rsp
  struct ITypeInfo *v12; // rcx
  __int64 result; // rax
  int i; // ecx
  __int64 v15; // rax
  __int64 v16; // [rsp+30h] [rbp+0h] BYREF
  struct ITypeInfo *v17; // [rsp+38h] [rbp+8h] BYREF
  ICreateTypeLib2 *ppctlib; // [rsp+40h] [rbp+10h] BYREF
  _BYTE v19[16]; // [rsp+50h] [rbp+20h] BYREF
  __int64 *v20; // [rsp+60h] [rbp+30h]
  int v21; // [rsp+68h] [rbp+38h]
  int v22; // [rsp+6Ch] [rbp+3Ch]
  int v23; // [rsp+70h] [rbp+40h]
  __int16 v24; // [rsp+74h] [rbp+44h]
  __int16 v25; // [rsp+7Ah] [rbp+4Ah]
  __int128 v26; // [rsp+80h] [rbp+50h]
  __int128 v27; // [rsp+90h] [rbp+60h]
  _BYTE v28[32]; // [rsp+B0h] [rbp+80h] BYREF
  __int16 v29; // [rsp+D0h] [rbp+A0h]
  int v30; // [rsp+ECh] [rbp+BCh]

  v4 = a2;
  memset_0(v28, 0, 0x40u);
  memset_0(v19, 0, 0x58u);
  v17 = 0;
  ppctlib = 0;
  v16 = 0;
  v8 = CreateTypeLib2(SYS_WIN32, L"JSSig.tlb", &ppctlib);
  if ( v8 < 0 )
    goto LABEL_10;
  v8 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, _QWORD, __int64, __int64 *))ppctlib->lpVtbl->CreateTypeInfo)(
         ppctlib,
         *a3,
         4,
         &v16);
  if ( v8 < 0 )
    goto LABEL_10;
  if ( a1 == 1 )
  {
    if ( (v4 & 0x80000000) != 0LL || v4 > 0x3FFFFFF )
      goto LABEL_9;
    v9 = 32 * v4;
    v10 = 32 * v4 + 15;
    if ( v9 + 15 < v9 )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
    if ( !&v16 )
    {
LABEL_9:
      v8 = -2147024882;
LABEL_10:
      v12 = v17;
      goto LABEL_11;
    }
    memset_0(&v16, 0, v9);
    for ( i = 0; i < (int)v4; *((_WORD *)&v16 + 16 * v15 + 4) = 12 )
      v15 = (unsigned int)i++;
    memset_0(v19, 0, 0x58u);
    v20 = &v16;
    v21 = 4;
    v23 = 4;
    v22 = 1;
    v24 = v4 - 1;
    v26 = 0;
    v25 = -1;
    v27 = 0;
    WORD4(v26) = 12;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v16 + 72LL))(v16, 0, v19);
    if ( v8 < 0 )
      goto LABEL_10;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 **, _QWORD))(*(_QWORD *)v16 + 120LL))(
           v16,
           0,
           a3,
           (unsigned int)v4);
    if ( v8 < 0 )
      goto LABEL_10;
  }
  else
  {
    memset_0(v28, 0, 0x40u);
    v30 = 3;
    v29 = 12;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v16 + 112LL))(v16, 0, v28);
    if ( (int)result < 0 )
      return result;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v16 + 128LL))(v16, 0, *a3);
    if ( (int)result < 0 )
      return result;
  }
  v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ITypeInfo **))v16)(v16, &IID_ITypeInfo, &v17);
  if ( v8 < 0 )
    goto LABEL_10;
  v12 = v17;
  v8 = 0;
  *a4 = v17;
LABEL_11:
  if ( v12 && v8 < 0 )
    ((void (__fastcall *)(struct ITypeInfo *))v12->lpVtbl->Release)(v12);
  if ( ppctlib )
    ((void (__fastcall *)(ICreateTypeLib2 *))ppctlib->lpVtbl->Release)(ppctlib);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  FreeNames(a3, (unsigned int)v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180085330  push    rbp
0x180085332  push    rbx
0x180085333  push    rsi
0x180085334  push    rdi
0x180085335  push    r13
0x180085337  push    r14
0x180085339  push    r15
0x18008533b  sub     rsp, 100h
0x180085342  lea     rbp, [rsp+30h]
0x180085347  mov     rax, cs:__security_cookie
0x18008534e  xor     rax, rbp
0x180085351  mov     [rbp+100h+var_40], rax
0x180085358  movsxd  rdi, edx
0x18008535b  mov     r14, r8
0x18008535e  xor     edx, edx; Val
0x180085360  mov     esi, ecx
0x180085362  lea     rcx, [rbp+100h+var_80]; void *
0x180085369  mov     r15, r9
0x18008536c  lea     r8d, [rdx+40h]; Size
0x180085370  call    memset_0
0x180085375  xor     edx, edx; Val
0x180085377  lea     rcx, [rbp+100h+var_E0]; void *
0x18008537b  lea     r8d, [rdx+58h]; Size
0x18008537f  call    memset_0
0x180085384  mov     r13d, 1
0x18008538a  mov     [rbp+100h+var_F8], 0
0x180085392  mov     ecx, r13d; syskind
0x180085395  mov     [rbp+100h+ppctlib], 0
0x18008539d  lea     r8, [rbp+100h+ppctlib]; ppctlib
0x1800853a1  mov     [rbp+100h+var_100], 0
0x1800853a9  lea     rdx, szFile; "JSSig.tlb"
0x1800853b0  call    cs:__imp_CreateTypeLib2
0x1800853b6  mov     ebx, eax
0x1800853b8  test    eax, eax
0x1800853ba  js      short loc_180085428
0x1800853bc  mov     rcx, [rbp+100h+ppctlib]
0x1800853c0  lea     r9, [rbp+100h+var_100]
0x1800853c4  mov     rdx, [r14]
0x1800853c7  lea     r8d, [r13+3]
0x1800853cb  mov     rax, [rcx]
0x1800853ce  mov     rax, [rax+18h]
0x1800853d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800853d7  mov     ebx, eax
0x1800853d9  test    eax, eax
0x1800853db  js      short loc_180085428
0x1800853dd  cmp     esi, r13d
0x1800853e0  jnz     loc_180085544
0x1800853e6  test    edi, edi
0x1800853e8  js      short loc_180085423
0x1800853ea  mov     r8, rdi
0x1800853ed  cmp     rdi, 3FFFFFFh
0x1800853f4  ja      short loc_180085423
0x1800853f6  shl     r8, 5
0x1800853fa  lea     rax, [r8+0Fh]
0x1800853fe  cmp     rax, r8
0x180085401  ja      short loc_18008540D
0x180085403  mov     rax, 0FFFFFFFFFFFFFF0h
0x18008540d  and     rax, 0FFFFFFFFFFFFFFF0h
0x180085411  call    _alloca_probe
0x180085416  sub     rsp, rax
0x180085419  lea     rbx, [rsp+130h+var_100]
0x18008541e  test    rbx, rbx
0x180085421  jnz     short loc_180085498
0x180085423  mov     ebx, 8007000Eh
0x180085428  mov     rcx, [rbp+100h+var_F8]
0x18008542c  test    rcx, rcx
0x18008542f  jz      short loc_180085441
0x180085431  test    ebx, ebx
0x180085433  jns     short loc_180085441
0x180085435  mov     rax, [rcx]
0x180085438  mov     rax, [rax+10h]
0x18008543c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085441  mov     rcx, [rbp+100h+ppctlib]
0x180085445  test    rcx, rcx
0x180085448  jz      short loc_180085456
0x18008544a  mov     rax, [rcx]
0x18008544d  mov     rax, [rax+10h]
0x180085451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085456  mov     rcx, [rbp+100h+var_100]
0x18008545a  test    rcx, rcx
0x18008545d  jz      short loc_18008546B
0x18008545f  mov     rax, [rcx]
0x180085462  mov     rax, [rax+10h]
0x180085466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008546b  mov     edx, edi
0x18008546d  mov     rcx, r14
0x180085470  call    FreeNames
0x180085475  mov     eax, ebx
0x180085477  mov     rcx, [rbp+100h+var_40]
0x18008547e  xor     rcx, rbp; StackCookie
0x180085481  call    __security_check_cookie
0x180085486  lea     rsp, [rbp+0D0h]
0x18008548d  pop     r15
0x18008548f  pop     r14
0x180085491  pop     r13
0x180085493  pop     rdi
0x180085494  pop     rsi
0x180085495  pop     rbx
0x180085496  pop     rbp
0x180085497  retn
0x180085498  xor     edx, edx; Val
0x18008549a  mov     rcx, rbx; void *
0x18008549d  call    memset_0
0x1800854a2  xor     ecx, ecx
0x1800854a4  lea     esi, [rcx+0Ch]
0x1800854a7  test    edi, edi
0x1800854a9  jle     short loc_1800854BD
0x1800854ab  mov     eax, ecx
0x1800854ad  add     ecx, r13d
0x1800854b0  shl     rax, 5
0x1800854b4  mov     [rax+rbx+8], si
0x1800854b9  cmp     ecx, edi
0x1800854bb  jl      short loc_1800854AB
0x1800854bd  xor     edx, edx; Val
0x1800854bf  lea     rcx, [rbp+100h+var_E0]; void *
0x1800854c3  lea     r8d, [rdx+58h]; Size
0x1800854c7  call    memset_0
0x1800854cc  mov     rcx, [rbp+100h+var_100]
0x1800854d0  lea     r8, [rbp+100h+var_E0]
0x1800854d4  mov     eax, 4
0x1800854d9  mov     [rbp+100h+var_D0], rbx
0x1800854dd  mov     [rbp+100h+var_C8], eax
0x1800854e0  xorps   xmm0, xmm0
0x1800854e3  mov     [rbp+100h+var_C0], eax
0x1800854e6  xor     edx, edx
0x1800854e8  movzx   eax, di
0x1800854eb  mov     [rbp+100h+var_C4], r13d
0x1800854ef  sub     ax, r13w
0x1800854f3  mov     [rbp+100h+var_BC], ax
0x1800854f7  or      eax, 0FFFFFFFFh
0x1800854fa  movups  [rbp+100h+var_B0], xmm0
0x1800854fe  mov     [rbp+100h+var_B6], ax
0x180085502  movups  [rbp+100h+var_A0], xmm0
0x180085506  mov     word ptr [rbp+100h+var_B0+8], si
0x18008550a  mov     rax, [rcx]
0x18008550d  mov     rax, [rax+48h]
0x180085511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085516  mov     ebx, eax
0x180085518  test    eax, eax
0x18008551a  js      loc_180085428
0x180085520  mov     rcx, [rbp+100h+var_100]
0x180085524  mov     r9d, edi
0x180085527  mov     r8, r14
0x18008552a  xor     edx, edx
0x18008552c  mov     rax, [rcx]
0x18008552f  mov     rax, [rax+78h]
0x180085533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085538  mov     ebx, eax
0x18008553a  test    eax, eax
0x18008553c  js      loc_180085428
0x180085542  jmp     short loc_1800855AD
0x180085544  xor     edx, edx; Val
0x180085546  lea     rcx, [rbp+100h+var_80]; void *
0x18008554d  lea     r8d, [rdx+40h]; Size
0x180085551  call    memset_0
0x180085556  mov     rcx, [rbp+100h+var_100]
0x18008555a  lea     r8, [rbp+100h+var_80]
0x180085561  mov     [rbp+100h+var_44], 3
0x18008556b  mov     esi, 0Ch
0x180085570  mov     [rbp+100h+var_60], si
0x180085577  xor     edx, edx
0x180085579  mov     rax, [rcx]
0x18008557c  mov     rax, [rax+70h]
0x180085580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085585  test    eax, eax
0x180085587  js      loc_180085477
0x18008558d  mov     rcx, [rbp+100h+var_100]
0x180085591  xor     edx, edx
0x180085593  mov     r8, [r14]
0x180085596  mov     rax, [rcx]
0x180085599  mov     rax, [rax+80h]
0x1800855a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800855a5  test    eax, eax
0x1800855a7  js      loc_180085477
0x1800855ad  mov     rcx, [rbp+100h+var_100]
0x1800855b1  lea     r8, [rbp+100h+var_F8]
0x1800855b5  lea     rdx, IID_ITypeInfo
0x1800855bc  mov     rax, [rcx]
0x1800855bf  mov     rax, [rax]
0x1800855c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800855c7  mov     ebx, eax
0x1800855c9  test    eax, eax
0x1800855cb  js      loc_180085428
0x1800855d1  mov     rcx, [rbp+100h+var_F8]
0x1800855d5  xor     ebx, ebx
0x1800855d7  mov     [r15], rcx
0x1800855da  jmp     loc_18008542C
```
