# CscEnCloseEntryOpenHandle

- ea: `0x14007d610`
- end: `0x14007d92b`
- name: `CscEnCloseEntryOpenHandle`
- size: `795`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x140011634`
- `0x14001362c`
- `0x14006c560`

## callees

- `0x140005390`
- `0x140007420`
- `0x14000a64c`
- `0x140010f6c`
- `0x140016a04`
- `0x140017908`
- `0x140018fd0`
- `0x14001a494`
- `0x14007d610`
- `0x14007d934`
- `0x14007dc34`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007d6c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d727`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d6c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d727`

## pseudocode

```c
__int64 __fastcall CscEnCloseEntryOpenHandle(_DWORD *P, __int64 a2, unsigned int *a3)
{
  unsigned int v3; // ebp
  unsigned __int8 v6; // r13
  __int64 v7; // rdi
  unsigned int v8; // r15d
  char v9; // r14
  __int64 v10; // rcx
  char v11; // r12
  void *v12; // rcx
  int v13; // r12d
  int v15; // r8d
  int v16; // r12d
  int v17; // r12d
  unsigned int v19; // eax
  __int64 v20; // rcx
  unsigned int v21; // [rsp+70h] [rbp+8h] BYREF
  __int64 v22; // [rsp+80h] [rbp+18h] BYREF

  v3 = 0;
  v6 = a2;
  v21 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    if ( P )
      v15 = P[4];
    else
      v15 = 0;
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      102,
      WPP_2d57263f6f6237979220aa59cf47311d_Traceguids,
      P,
      v15,
      (unsigned __int8)a2);
  }
  if ( !P )
  {
    v8 = -1073741811;
    v13 = 10833;
    goto LABEL_23;
  }
  v7 = *((_QWORD *)P + 1);
  if ( !v7 && (P[4] & 0x800) == 0 )
  {
    v8 = -1073741811;
    v13 = 10847;
    goto LABEL_23;
  }
  v8 = 0;
  v9 = 0;
  v22 = *((_QWORD *)P + 1);
  if ( v7 )
  {
    CscEnpMainAcquireExclusive(v7);
    v9 = 1;
  }
  if ( (P[4] & 0x100) != 0 )
  {
    v10 = *((_QWORD *)P + 3);
    v11 = 1;
    if ( v10 )
    {
      v8 = CscStorepLowIoClosePoster(v10);
      *((_QWORD *)P + 3) = 0;
    }
    v12 = (void *)*((_QWORD *)P + 4);
    if ( v12 )
    {
      ExFreePoolWithTag(v12, 0x21407343u);
      *((_QWORD *)P + 4) = 0;
    }
  }
  else
  {
    v11 = 0;
  }
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, v7);
    }
    if ( v11 )
    {
      --*(_DWORD *)(v7 + 160);
    }
    else
    {
      v16 = P[4];
      if ( (v16 & 0x1000) != 0 )
      {
        v20 = *(_QWORD *)(v7 + 152);
        if ( v20 )
        {
          LOBYTE(a2) = 1;
          v8 = CscStorepLowIoSetDeleteDisposition(v20, a2);
          CscStorepLowIoClosePoster(*(_QWORD *)(v7 + 152));
          *(_QWORD *)(v7 + 152) = 0;
        }
        P[4] &= ~0x1000u;
        v16 = P[4];
      }
      if ( !*(_DWORD *)(v7 + 160) )
      {
        v8 = -1073740768;
        v13 = 10906;
        goto LABEL_19;
      }
      v17 = v16 & 0x400;
      if ( v6 )
      {
        CscEnpImplicitTimeUpdate(P, v6, &v21);
        v3 = v21;
      }
      --*(_DWORD *)(v7 + 160);
      if ( v17 )
      {
        if ( (*(_DWORD *)(v7 + 164))-- == 1 )
        {
          v19 = CscStorepLowIoClosePoster(*(_QWORD *)(v7 + 168));
          *(_QWORD *)(v7 + 168) = 0;
          v8 = v19;
          *(_QWORD *)(v7 + 176) = 0;
        }
      }
    }
    CscEnpNotifyItemChangedEx(v7, 0, 0);
  }
  v13 = 0;
  P[4] = 0;
  ExFreePoolWithTag(P, 0x21407343u);
LABEL_19:
  if ( v9 )
    CscEnpMainRelease(v7);
  if ( v7 )
    CscEnDereferenceEntry(&v22);
LABEL_23:
  if ( a3 )
    *a3 = v3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_DDd(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, v3, v8, v13);
  return v8;
}

```

## disassembly

```asm
0x14007d610  push    rbp
0x14007d612  sub     rsp, 60h
0x14007d616  mov     [rsp+68h+arg_8], rbx
0x14007d61b  xor     ebp, ebp
0x14007d61d  mov     [rsp+68h+var_10], rsi
0x14007d622  mov     rbx, rcx
0x14007d625  mov     [rsp+68h+var_18], rdi
0x14007d62a  mov     rsi, r8
0x14007d62d  mov     [rsp+68h+var_28], r13
0x14007d632  movzx   r13d, dl
0x14007d636  mov     [rsp+68h+arg_0], ebp
0x14007d63a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d641  lea     rdi, WPP_GLOBAL_Control
0x14007d648  cmp     rcx, rdi
0x14007d64b  jnz     loc_14007D7AF
0x14007d651  mov     [rsp+68h+var_20], r12
0x14007d656  mov     [rsp+68h+var_38], r15
0x14007d65b  test    rbx, rbx
0x14007d65e  jz      loc_14007D799
0x14007d664  mov     rdi, [rbx+8]
0x14007d668  test    rdi, rdi
0x14007d66b  jz      loc_14007D820
0x14007d671  mov     [rsp+68h+var_30], r14
0x14007d676  xor     r15d, r15d
0x14007d679  xor     r14b, r14b
0x14007d67c  mov     [rsp+68h+arg_10], rdi
0x14007d684  test    rdi, rdi
0x14007d687  jz      short loc_14007D694
0x14007d689  mov     rcx, rdi
0x14007d68c  call    CscEnpMainAcquireExclusive
0x14007d691  mov     r14b, 1
0x14007d694  test    dword ptr [rbx+10h], 100h
0x14007d69b  jz      loc_14007D7A7
0x14007d6a1  mov     rcx, [rbx+18h]
0x14007d6a5  mov     r12b, 1
0x14007d6a8  test    rcx, rcx
0x14007d6ab  jz      short loc_14007D6B9
0x14007d6ad  call    CscStorepLowIoClosePoster
0x14007d6b2  mov     r15d, eax
0x14007d6b5  mov     [rbx+18h], rbp
0x14007d6b9  mov     rcx, [rbx+20h]; P
0x14007d6bd  test    rcx, rcx
0x14007d6c0  jz      short loc_14007D6D7
0x14007d6c2  mov     edx, 21407343h; Tag
0x14007d6c7  call    cs:__imp_ExFreePoolWithTag
0x14007d6ce  nop     dword ptr [rax+rax+00h]
0x14007d6d3  mov     [rbx+20h], rbp
0x14007d6d7  test    rdi, rdi
0x14007d6da  jz      short loc_14007D718
0x14007d6dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d6e3  lea     rax, WPP_GLOBAL_Control
0x14007d6ea  cmp     rcx, rax
0x14007d6ed  jz      short loc_14007D6FC
0x14007d6ef  test    dword ptr [rcx+2Ch], 40000h
0x14007d6f6  jnz     loc_14007D8D5
0x14007d6fc  test    r12b, r12b
0x14007d6ff  jz      loc_14007D83E
0x14007d705  dec     dword ptr [rdi+0A0h]
0x14007d70b  xor     r8d, r8d
0x14007d70e  xor     edx, edx
0x14007d710  mov     rcx, rdi
0x14007d713  call    CscEnpNotifyItemChangedEx
0x14007d718  xor     r12d, r12d
0x14007d71b  mov     edx, 21407343h; Tag
0x14007d720  mov     rcx, rbx; P
0x14007d723  mov     [rbx+10h], r12d
0x14007d727  call    cs:__imp_ExFreePoolWithTag
0x14007d72e  nop     dword ptr [rax+rax+00h]
0x14007d733  test    r14b, r14b
0x14007d736  mov     r14, [rsp+68h+var_30]
0x14007d73b  jz      short loc_14007D745
0x14007d73d  mov     rcx, rdi
0x14007d740  call    CscEnpMainRelease
0x14007d745  test    rdi, rdi
0x14007d748  jz      short loc_14007D757
0x14007d74a  lea     rcx, [rsp+68h+arg_10]
0x14007d752  call    CscEnDereferenceEntry
0x14007d757  lea     rdi, WPP_GLOBAL_Control
0x14007d75e  mov     r13, [rsp+68h+var_28]
0x14007d763  mov     rbx, [rsp+68h+arg_8]
0x14007d768  test    rsi, rsi
0x14007d76b  jz      short loc_14007D76F
0x14007d76d  mov     [rsi], ebp
0x14007d76f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d776  mov     rsi, [rsp+68h+var_10]
0x14007d77b  cmp     rcx, rdi
0x14007d77e  mov     rdi, [rsp+68h+var_18]
0x14007d783  jnz     short loc_14007D7F0
0x14007d785  mov     r12, [rsp+68h+var_20]
0x14007d78a  mov     eax, r15d
0x14007d78d  mov     r15, [rsp+68h+var_38]
0x14007d792  add     rsp, 60h
0x14007d796  pop     rbp
0x14007d797  retn
0x14007d799  mov     r15d, 0C000000Dh
0x14007d79f  mov     r12d, 2A51h
0x14007d7a5  jmp     short loc_14007D75E
0x14007d7a7  xor     r12b, r12b
0x14007d7aa  jmp     loc_14007D6D7
0x14007d7af  test    dword ptr [rcx+2Ch], 40000h
0x14007d7b6  jz      loc_14007D651
0x14007d7bc  test    rbx, rbx
0x14007d7bf  jz      loc_14007D8CD
0x14007d7c5  mov     r8d, [rbx+10h]
0x14007d7c9  mov     rcx, [rcx+18h]
0x14007d7cd  mov     edx, 66h ; 'f'
0x14007d7d2  mov     [rsp+68h+var_40], r13d
0x14007d7d7  mov     r9, rbx
0x14007d7da  mov     [rsp+68h+var_48], r8d
0x14007d7df  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14007d7e6  call    WPP_SF_qDD
0x14007d7eb  jmp     loc_14007D651
0x14007d7f0  test    dword ptr [rcx+2Ch], 40000h
0x14007d7f7  jz      short loc_14007D785
0x14007d7f9  mov     rcx, [rcx+18h]
0x14007d7fd  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14007d804  mov     edx, 68h ; 'h'
0x14007d809  mov     [rsp+68h+var_40], r12d
0x14007d80e  mov     r9d, ebp
0x14007d811  mov     [rsp+68h+var_48], r15d
0x14007d816  call    WPP_SF_DDd
0x14007d81b  jmp     loc_14007D785
0x14007d820  test    dword ptr [rbx+10h], 800h
0x14007d827  jnz     loc_14007D671
0x14007d82d  mov     r15d, 0C000000Dh
0x14007d833  mov     r12d, 2A5Fh
0x14007d839  jmp     loc_14007D757
0x14007d83e  mov     r12d, [rbx+10h]
0x14007d842  bt      r12d, 0Ch
0x14007d847  jb      loc_14007D8F2
0x14007d84d  cmp     [rdi+0A0h], ebp
0x14007d853  jz      short loc_14007D8BC
0x14007d855  and     r12d, 400h
0x14007d85c  test    r13b, r13b
0x14007d85f  jz      short loc_14007D876
0x14007d861  lea     r8, [rsp+68h+arg_0]
0x14007d866  movzx   edx, r13b
0x14007d86a  mov     rcx, rbx
0x14007d86d  call    CscEnpImplicitTimeUpdate
0x14007d872  mov     ebp, [rsp+68h+arg_0]
0x14007d876  dec     dword ptr [rdi+0A0h]
0x14007d87c  test    r12d, r12d
0x14007d87f  jz      loc_14007D70B
0x14007d885  sub     dword ptr [rdi+0A4h], 1
0x14007d88c  jnz     loc_14007D70B
0x14007d892  mov     rcx, [rdi+0A8h]
0x14007d899  call    CscStorepLowIoClosePoster
0x14007d89e  mov     qword ptr [rdi+0A8h], 0
0x14007d8a9  mov     r15d, eax
0x14007d8ac  mov     qword ptr [rdi+0B0h], 0
0x14007d8b7  jmp     loc_14007D70B
0x14007d8bc  mov     r15d, 0C0000420h
0x14007d8c2  mov     r12d, 2A9Ah
0x14007d8c8  jmp     loc_14007D733
0x14007d8cd  xor     r8d, r8d
0x14007d8d0  jmp     loc_14007D7C9
0x14007d8d5  mov     rcx, [rcx+18h]
0x14007d8d9  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14007d8e0  mov     edx, 67h ; 'g'
0x14007d8e5  mov     r9, rdi
0x14007d8e8  call    WPP_SF_q
0x14007d8ed  jmp     loc_14007D6FC
0x14007d8f2  mov     rcx, [rdi+98h]
0x14007d8f9  test    rcx, rcx
0x14007d8fc  jz      short loc_14007D91B
0x14007d8fe  mov     dl, 1
0x14007d900  call    CscStorepLowIoSetDeleteDisposition
0x14007d905  mov     rcx, [rdi+98h]
0x14007d90c  mov     r15d, eax
0x14007d90f  call    CscStorepLowIoClosePoster
0x14007d914  mov     [rdi+98h], rbp
0x14007d91b  and     dword ptr [rbx+10h], 0FFFFEFFFh
0x14007d922  mov     r12d, [rbx+10h]
0x14007d926  jmp     loc_14007D84D
```
