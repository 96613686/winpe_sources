# CFtpMenu::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x18000e710`
- end: `0x18000e920`
- name: `?QueryContextMenu@CFtpMenu@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `528`
- prototype: `__int64 __fastcall(CFtpMenu *__hidden this, HMENU, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000e710`
- `0x18000fd24`
- `0x18000fed0`
- `0x18001ce78`
- `0x180023be0`
- `0x1800269f4`

## import_xrefs

- `USER32!DeleteMenu` at `0x18000e8fc`
- `USER32!DeleteMenu` at `0x18000e8fc`
- `USER32!GetCursorPos` at `0x18000e731`
- `USER32!GetCursorPos` at `0x18000e731`
- `USER32!SetMenuDefaultItem` at `0x18000e86b`
- `USER32!SetMenuDefaultItem` at `0x18000e8bd`
- `USER32!SetMenuDefaultItem` at `0x18000e86b`
- `USER32!SetMenuDefaultItem` at `0x18000e8bd`

## pseudocode

```c
__int64 __fastcall CFtpMenu::QueryContextMenu(
        struct tagPOINT *this,
        HMENU a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        LONG a6)
{
  unsigned int v10; // edx
  bool v11; // zf
  struct tagPOINT v13; // rdx
  int v14; // ebx
  int IsDirectory; // r12d
  int v16; // r14d
  __int64 v17; // rcx
  const struct _ITEMIDLIST *Ptr; // rax
  BOOL v19; // r14d
  unsigned int v20; // r9d
  unsigned int v21; // r13d
  unsigned int v22; // r14d
  unsigned int v23; // edx
  unsigned int v24; // eax
  struct tagPOINT v26; // [rsp+90h] [rbp+8h]
  unsigned int x; // [rsp+B8h] [rbp+30h]

  GetCursorPos(this + 8);
  v11 = this[9].y == 0;
  this[9].x = a6;
  if ( v11 )
  {
    v13 = this[4];
    v14 = 1;
    IsDirectory = 1;
    v26 = v13;
    v16 = **(_DWORD **)(*(_QWORD *)(*(_QWORD *)&v13 + 16LL) + 16LL) - 1;
    do
    {
      if ( v16 < 0 )
        break;
      v17 = *(_QWORD *)(*(_QWORD *)&v13 + 16LL);
      if ( v17 )
      {
        Ptr = (const struct _ITEMIDLIST *)DPA_GetPtr(*(HDPA *)(v17 + 16), v16);
        if ( Ptr )
          IsDirectory = FtpPidl_IsDirectory(Ptr, 1);
        v13 = v26;
      }
      --v16;
    }
    while ( IsDirectory );
    if ( (a6 & 0x10002) == 0 )
    {
      x = this[3].x;
      v19 = !a6 && a3 == 1;
      AddToPopupMenu(a2, v13.x, 3u, a3, a4, a5, 1u);
      v20 = x & 0xFFFFFFCF;
      if ( !v19 )
        v20 = x;
      CFtpMenu::_RemoveContextMenuItems((CFtpMenu *)this, a2, a4, v20);
    }
    if ( a6 || a3 != 1 )
    {
      v21 = a5;
      AddToPopupMenu(a2, v13.x, 2u, a3, a4, a5, 1u);
      v22 = a6 & 0x20;
      if ( (a6 & 0x20) != 0 )
      {
LABEL_22:
        v24 = a6 || a3 != 1;
        AddToPopupMenu(a2, v23, IsDirectory == 0, a3, a4, v21, v24);
        if ( !v22 )
        {
          if ( (a6 & 4) == 0 || !IsDirectory )
            v14 = 0;
          SetMenuDefaultItem(a2, v14 + a4, 0);
        }
        goto LABEL_33;
      }
    }
    else
    {
      v21 = a5;
      v22 = 0;
    }
    SetMenuDefaultItem(a2, a4 + 2, 1u);
    goto LABEL_22;
  }
  AddToPopupMenu(a2, v10, 4u, a3, a4, a5, 1u);
  if ( (a6 & 0x10000) != 0 )
    DeleteMenu(a2, a4 + 3, 0);
LABEL_33:
  _SHPrettyMenu(a2);
  return 15;
}

```

## disassembly

```asm
0x18000e710  push    rbx
0x18000e712  push    rbp
0x18000e713  push    rsi
0x18000e714  push    rdi
0x18000e715  push    r12
0x18000e717  push    r13
0x18000e719  push    r14
0x18000e71b  push    r15
0x18000e71d  sub     rsp, 48h
0x18000e721  mov     r13, rcx
0x18000e724  mov     ebp, r9d
0x18000e727  add     rcx, 40h ; '@'; lpPoint
0x18000e72b  mov     r15d, r8d
0x18000e72e  mov     rsi, rdx
0x18000e731  call    cs:__imp_GetCursorPos
0x18000e737  cmp     dword ptr [r13+4Ch], 0
0x18000e73c  mov     edi, [rsp+88h+arg_28]
0x18000e743  mov     [r13+48h], edi
0x18000e747  jnz     loc_18000E8C5
0x18000e74d  mov     rdx, [r13+20h]
0x18000e751  mov     ebx, 1
0x18000e756  mov     r12d, ebx
0x18000e759  mov     qword ptr [rsp+88h+arg_0], rdx
0x18000e761  mov     rax, [rdx+10h]
0x18000e765  mov     rcx, [rax+10h]
0x18000e769  mov     r14d, [rcx]
0x18000e76c  sub     r14d, ebx
0x18000e76f  test    r14d, r14d
0x18000e772  js      short loc_18000E7AB
0x18000e774  mov     rcx, [rdx+10h]
0x18000e778  test    rcx, rcx
0x18000e77b  jz      short loc_18000E7A3
0x18000e77d  mov     rcx, [rcx+10h]; hdpa
0x18000e781  movsxd  rdx, r14d; i
0x18000e784  call    DPA_GetPtr
0x18000e789  test    rax, rax
0x18000e78c  jz      short loc_18000E79B
0x18000e78e  mov     edx, ebx; int
0x18000e790  mov     rcx, rax; struct _ITEMIDLIST *
0x18000e793  call    ?FtpPidl_IsDirectory@@YAHPEFBU_ITEMIDLIST@@H@Z; FtpPidl_IsDirectory(_ITEMIDLIST const *,int)
0x18000e798  mov     r12d, eax
0x18000e79b  mov     rdx, qword ptr [rsp+88h+arg_0]; unsigned int
0x18000e7a3  sub     r14d, ebx
0x18000e7a6  test    r12d, r12d
0x18000e7a9  jnz     short loc_18000E76F
0x18000e7ab  test    edi, 10002h
0x18000e7b1  jnz     short loc_18000E819
0x18000e7b3  mov     eax, [r13+18h]
0x18000e7b7  mov     [rsp+88h+arg_28], eax
0x18000e7be  test    edi, edi
0x18000e7c0  jnz     short loc_18000E7CC
0x18000e7c2  cmp     r15d, ebx
0x18000e7c5  jnz     short loc_18000E7CC
0x18000e7c7  mov     r14d, ebx
0x18000e7ca  jmp     short loc_18000E7CF
0x18000e7cc  xor     r14d, r14d
0x18000e7cf  mov     eax, [rsp+88h+arg_20]
0x18000e7d6  mov     r9d, r15d; unsigned int
0x18000e7d9  mov     [rsp+88h+var_58], ebx; unsigned int
0x18000e7dd  mov     r8d, 3; unsigned int
0x18000e7e3  mov     [rsp+88h+var_60], eax; unsigned int
0x18000e7e7  mov     rcx, rsi; hmDst
0x18000e7ea  mov     [rsp+88h+var_68], ebp; unsigned int
0x18000e7ee  call    ?AddToPopupMenu@@YAIPEAUHMENU__@@IIIIII@Z; AddToPopupMenu(HMENU__ *,uint,uint,uint,uint,uint,uint)
0x18000e7f3  mov     r9d, [rsp+88h+arg_28]
0x18000e7fb  mov     r8d, ebp; unsigned int
0x18000e7fe  and     r9d, 0FFFFFFCFh
0x18000e802  mov     rdx, rsi; HMENU
0x18000e805  test    r14d, r14d
0x18000e808  mov     rcx, r13; this
0x18000e80b  cmovz   r9d, [rsp+88h+arg_28]; unsigned int
0x18000e814  call    ?_RemoveContextMenuItems@CFtpMenu@@IEAAHPEAUHMENU__@@IK@Z; CFtpMenu::_RemoveContextMenuItems(HMENU__ *,uint,ulong)
0x18000e819  test    edi, edi
0x18000e81b  jnz     short loc_18000E833
0x18000e81d  cmp     r15d, ebx
0x18000e820  jnz     short loc_18000E833
0x18000e822  mov     r13d, [rsp+88h+arg_20]
0x18000e82a  mov     r14d, edi
0x18000e82d  and     r14d, 20h
0x18000e831  jmp     short loc_18000E862
0x18000e833  mov     r13d, [rsp+88h+arg_20]
0x18000e83b  mov     r9d, r15d; unsigned int
0x18000e83e  mov     [rsp+88h+var_58], ebx; unsigned int
0x18000e842  mov     r8d, 2; unsigned int
0x18000e848  mov     [rsp+88h+var_60], r13d; unsigned int
0x18000e84d  mov     rcx, rsi; hmDst
0x18000e850  mov     [rsp+88h+var_68], ebp; unsigned int
0x18000e854  call    ?AddToPopupMenu@@YAIPEAUHMENU__@@IIIIII@Z; AddToPopupMenu(HMENU__ *,uint,uint,uint,uint,uint,uint)
0x18000e859  mov     r14d, edi
0x18000e85c  and     r14d, 20h
0x18000e860  jnz     short loc_18000E871
0x18000e862  lea     edx, [rbp+2]; uItem
0x18000e865  mov     r8d, ebx; fByPos
0x18000e868  mov     rcx, rsi; hMenu
0x18000e86b  call    cs:__imp_SetMenuDefaultItem
0x18000e871  test    edi, edi
0x18000e873  jnz     short loc_18000E87E
0x18000e875  cmp     r15d, ebx
0x18000e878  jnz     short loc_18000E87E
0x18000e87a  xor     eax, eax
0x18000e87c  jmp     short loc_18000E880
0x18000e87e  mov     eax, ebx
0x18000e880  xor     r8d, r8d
0x18000e883  mov     [rsp+88h+var_58], eax; unsigned int
0x18000e887  test    r12d, r12d
0x18000e88a  mov     [rsp+88h+var_60], r13d; unsigned int
0x18000e88f  mov     r9d, r15d; unsigned int
0x18000e892  mov     [rsp+88h+var_68], ebp; unsigned int
0x18000e896  setz    r8b; unsigned int
0x18000e89a  mov     rcx, rsi; hmDst
0x18000e89d  call    ?AddToPopupMenu@@YAIPEAUHMENU__@@IIIIII@Z; AddToPopupMenu(HMENU__ *,uint,uint,uint,uint,uint,uint)
0x18000e8a2  test    r14d, r14d
0x18000e8a5  jnz     short loc_18000E902
0x18000e8a7  test    dil, 4
0x18000e8ab  jz      short loc_18000E8B2
0x18000e8ad  test    r12d, r12d
0x18000e8b0  jnz     short loc_18000E8B4
0x18000e8b2  xor     ebx, ebx
0x18000e8b4  lea     edx, [rbx+rbp]; uItem
0x18000e8b7  xor     r8d, r8d; fByPos
0x18000e8ba  mov     rcx, rsi; hMenu
0x18000e8bd  call    cs:__imp_SetMenuDefaultItem
0x18000e8c3  jmp     short loc_18000E902
0x18000e8c5  mov     eax, [rsp+88h+arg_20]
0x18000e8cc  mov     r9d, r15d; unsigned int
0x18000e8cf  mov     [rsp+88h+var_58], 1; unsigned int
0x18000e8d7  mov     r8d, 4; unsigned int
0x18000e8dd  mov     [rsp+88h+var_60], eax; unsigned int
0x18000e8e1  mov     rcx, rsi; hmDst
0x18000e8e4  mov     [rsp+88h+var_68], ebp; unsigned int
0x18000e8e8  call    ?AddToPopupMenu@@YAIPEAUHMENU__@@IIIIII@Z; AddToPopupMenu(HMENU__ *,uint,uint,uint,uint,uint,uint)
0x18000e8ed  bt      edi, 10h
0x18000e8f1  jnb     short loc_18000E902
0x18000e8f3  lea     edx, [rbp+3]; uPosition
0x18000e8f6  xor     r8d, r8d; uFlags
0x18000e8f9  mov     rcx, rsi; hMenu
0x18000e8fc  call    cs:__imp_DeleteMenu
0x18000e902  mov     rcx, rsi; hmenu
0x18000e905  call    ?_SHPrettyMenu@@YAXPEAUHMENU__@@@Z; _SHPrettyMenu(HMENU__ *)
0x18000e90a  mov     eax, 0Fh
0x18000e90f  add     rsp, 48h
0x18000e913  pop     r15
0x18000e915  pop     r14
0x18000e917  pop     r13
0x18000e919  pop     r12
0x18000e91b  pop     rdi
0x18000e91c  pop     rsi
0x18000e91d  pop     rbp
0x18000e91e  pop     rbx
0x18000e91f  retn
```
