# FatOpenRootDcb

- ea: `0x14002bf3c`
- end: `0x14002c078`
- name: `FatOpenRootDcb`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1400268c0`

## callees

- `0x1400201f4`
- `0x14002bf3c`
- `0x14003db44`
- `0x1400465f4`
- `0x1400475e8`
- `0x14004814c`

## import_xrefs

- `ntoskrnl!IoRemoveShareAccess` at `0x14005c9b0`
- `ntoskrnl!IoRemoveShareAccess` at `0x14005c9b0`
- `ntoskrnl!IoCheckShareAccess` at `0x14002bfe6`
- `ntoskrnl!IoCheckShareAccess` at `0x14002bfe6`
- `ntoskrnl!IoSetShareAccess` at `0x14002bffa`
- `ntoskrnl!IoSetShareAccess` at `0x14002bffa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c05c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c9c5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002c05c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c9c5`

## pseudocode

```c
__int64 __fastcall FatOpenRootDcb(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        ACCESS_MASK *a5,
        unsigned __int16 a6,
        int a7)
{
  __int64 v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // rcx
  struct _SHARE_ACCESS *v13; // r9
  ACCESS_MASK v14; // ecx
  NTSTATUS v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 Ccb; // [rsp+70h] [rbp+8h]

  *(_OWORD *)a1 = 0;
  v10 = *(_QWORD *)(a4 + 208);
  FatAcquireExclusiveFcb(a2, v10);
  if ( ((a7 - 1) & 0xFFFFFFFD) != 0
    || (LOBYTE(v11) = *(_BYTE *)(v10 + 546), !(unsigned __int8)FatCheckFileAccess(v12, v11, a5)) )
  {
    *(_DWORD *)a1 = -1073741790;
  }
  else
  {
    v13 = (struct _SHARE_ACCESS *)(v10 + 200);
    v14 = *a5;
    if ( *(_DWORD *)(v10 + 232) )
    {
      v15 = IoCheckShareAccess(v14, a6, (PFILE_OBJECT)a3, v13, 1u);
      *(_DWORD *)a1 = v15;
      if ( v15 < 0 )
        goto LABEL_11;
    }
    else
    {
      IoSetShareAccess(v14, a6, (PFILE_OBJECT)a3, v13);
    }
    Ccb = FatCreateCcb(v17, v16);
    FatSetFileObject(a3, v18, v10, Ccb);
    ++*(_DWORD *)(v10 + 228);
    ++*(_DWORD *)(v10 + 232);
    ++*(_DWORD *)(a4 + 272);
    if ( !*(_WORD *)(a3 + 75) )
      ++*(_DWORD *)(a4 + 276);
    *(_DWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 1;
  }
LABEL_11:
  ExReleaseResourceLite(*(PERESOURCE *)(v10 + 8));
  return a1;
}

```

## disassembly

```asm
0x14002bf3c  mov     [rsp+arg_18], r9
0x14002bf41  mov     [rsp+arg_10], r8
0x14002bf46  push    rbx
0x14002bf47  push    rsi
0x14002bf48  push    rdi
0x14002bf49  push    r14
0x14002bf4b  push    r15
0x14002bf4d  sub     rsp, 40h
0x14002bf51  mov     rsi, r9
0x14002bf54  mov     r14, r8
0x14002bf57  mov     rax, rdx
0x14002bf5a  mov     rbx, rcx
0x14002bf5d  xorps   xmm0, xmm0
0x14002bf60  movups  xmmword ptr [rcx], xmm0
0x14002bf63  mov     [rsp+68h+var_37], 0
0x14002bf68  mov     [rsp+68h+arg_0], 0
0x14002bf71  mov     [rsp+68h+var_38], 0
0x14002bf76  mov     rdi, [r9+0D0h]
0x14002bf7d  mov     [rsp+68h+var_30], rdi
0x14002bf82  mov     rdx, rdi
0x14002bf85  mov     rcx, rax
0x14002bf88  call    FatAcquireExclusiveFcb
0x14002bf8d  nop
0x14002bf8e  mov     eax, [rsp+68h+arg_30]
0x14002bf95  dec     eax
0x14002bf97  test    eax, 0FFFFFFFDh
0x14002bf9c  jz      short loc_14002BFA9
0x14002bf9e  mov     dword ptr [rbx], 0C0000022h
0x14002bfa4  jmp     loc_14002C058
0x14002bfa9  mov     r15, [rsp+68h+arg_20]
0x14002bfb1  mov     r8, r15
0x14002bfb4  mov     dl, [rdi+222h]
0x14002bfba  call    FatCheckFileAccess
0x14002bfbf  test    al, al
0x14002bfc1  jz      short loc_14002BF9E
0x14002bfc3  lea     r9, [rdi+0C8h]; ShareAccess
0x14002bfca  movzx   edx, [rsp+68h+arg_28]; DesiredShareAccess
0x14002bfd2  mov     ecx, [r15]; DesiredAccess
0x14002bfd5  mov     r8, r14; FileObject
0x14002bfd8  cmp     dword ptr [rdi+0E8h], 0
0x14002bfdf  jbe     short loc_14002BFFA
0x14002bfe1  mov     [rsp+68h+Update], 1; Update
0x14002bfe6  call    cs:__imp_IoCheckShareAccess
0x14002bfed  nop     dword ptr [rax+rax+00h]
0x14002bff2  mov     [rbx], eax
0x14002bff4  test    eax, eax
0x14002bff6  js      short loc_14002C058
0x14002bff8  jmp     short loc_14002C006
0x14002bffa  call    cs:__imp_IoSetShareAccess
0x14002c001  nop     dword ptr [rax+rax+00h]
0x14002c006  mov     [rsp+68h+var_37], 1
0x14002c00b  call    FatCreateCcb
0x14002c010  mov     [rsp+68h+arg_0], rax
0x14002c015  mov     r9, rax
0x14002c018  mov     r8, rdi
0x14002c01b  mov     rcx, r14
0x14002c01e  call    FatSetFileObject
0x14002c023  inc     dword ptr [rdi+0E4h]
0x14002c029  inc     dword ptr [rdi+0E8h]
0x14002c02f  inc     dword ptr [rsi+110h]
0x14002c035  mov     al, [r14+4Ch]
0x14002c039  or      al, [r14+4Bh]
0x14002c03d  jnz     short loc_14002C045
0x14002c03f  inc     dword ptr [rsi+114h]
0x14002c045  mov     [rsp+68h+var_38], 1
0x14002c04a  mov     dword ptr [rbx], 0
0x14002c050  mov     qword ptr [rbx+8], 1
0x14002c058  mov     rcx, [rdi+8]; Resource
0x14002c05c  call    cs:__imp_ExReleaseResourceLite
0x14002c063  nop     dword ptr [rax+rax+00h]
0x14002c068  mov     rax, rbx
0x14002c06b  add     rsp, 40h
0x14002c06f  pop     r15
0x14002c071  pop     r14
0x14002c073  pop     rdi
0x14002c074  pop     rsi
0x14002c075  pop     rbx
0x14002c076  retn
0x14005c935  push    rbp
0x14005c937  sub     rsp, 30h
0x14005c93b  mov     rbp, rdx
0x14005c93e  movzx   eax, cl
0x14005c941  test    cl, cl
0x14005c943  jz      short loc_14005C9BD
0x14005c945  cmp     byte ptr [rbp+30h], 0
0x14005c949  jz      short loc_14005C987
0x14005c94b  mov     rcx, [rbp+38h]
0x14005c94f  dec     dword ptr [rcx+0E4h]
0x14005c955  dec     dword ptr [rcx+0E8h]
0x14005c95b  mov     rdx, [rbp+88h]
0x14005c962  dec     dword ptr [rdx+110h]
0x14005c968  mov     rax, [rbp+80h]
0x14005c96f  mov     cl, [rax+4Bh]
0x14005c972  mov     al, [rax+4Ch]
0x14005c975  or      al, cl
0x14005c977  jnz     short loc_14005C987
0x14005c979  mov     eax, [rdx+114h]
0x14005c97f  dec     eax
0x14005c981  mov     [rdx+114h], eax
0x14005c987  cmp     qword ptr [rbp+70h], 0
0x14005c98c  jz      short loc_14005C998
0x14005c98e  lea     rdx, [rbp+70h]
0x14005c992  call    FatDeleteCcb
0x14005c997  nop
0x14005c998  cmp     byte ptr [rbp+31h], 0
0x14005c99c  jz      short loc_14005C9BD
0x14005c99e  mov     rdx, [rbp+38h]
0x14005c9a2  add     rdx, 0C8h; ShareAccess
0x14005c9a9  mov     rcx, [rbp+80h]; FileObject
0x14005c9b0  call    cs:__imp_IoRemoveShareAccess
0x14005c9b7  nop     dword ptr [rax+rax+00h]
0x14005c9bc  nop
0x14005c9bd  mov     rcx, [rbp+38h]
0x14005c9c1  mov     rcx, [rcx+8]; Resource
0x14005c9c5  call    cs:__imp_ExReleaseResourceLite
0x14005c9cc  nop     dword ptr [rax+rax+00h]
0x14005c9d1  nop
0x14005c9d2  add     rsp, 30h
0x14005c9d6  pop     rbp
0x14005c9d7  retn
```
