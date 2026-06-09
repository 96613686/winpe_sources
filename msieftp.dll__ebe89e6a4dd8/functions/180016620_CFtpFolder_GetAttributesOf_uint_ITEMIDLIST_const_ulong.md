# CFtpFolder::GetAttributesOf(uint,_ITEMIDLIST const * *,ulong *)

- ea: `0x180016620`
- end: `0x18001677d`
- name: `?GetAttributesOf@CFtpFolder@@UEAAJIPEAPEFBU_ITEMIDLIST@@PEAK@Z`
- size: `349`
- prototype: `__int64 __fastcall(CFtpFolder *__hidden this, unsigned int, const struct _ITEMIDLIST **, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180016620`
- `0x180016b4c`
- `0x18001c4fc`
- `0x180024ac8`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x1800166c4`
- `SHELL32!__imp_ILCombine` at `0x1800166c4`
- `SHELL32!__imp_ILFree` at `0x180016704`
- `SHELL32!__imp_ILFree` at `0x180016704`

## pseudocode

```c
__int64 __fastcall CFtpFolder::GetAttributesOf(
        CFtpFolder *this,
        unsigned int a2,
        const struct _ITEMIDLIST **a3,
        unsigned int *a4)
{
  int v8; // ebp
  _WORD *v9; // rdx
  char Attributes; // al
  const struct _ITEMIDLIST *v11; // rax
  ITEMIDLIST *v12; // r15
  char v13; // al
  _WORD *v15; // rdx
  int v16; // eax
  struct CFtpDir *FtpDir; // rax
  struct CFtpDir *v18; // rbx

  if ( a2 && a3 && *a3 && (*a3)->mkid.cb )
  {
    if ( a2 > 1 )
      *a4 &= 0xFFFFFEEF;
    v8 = 0;
    while ( 1 )
    {
      v9 = (USHORT *)((char *)&a3[v8]->mkid.cb + a3[v8]->mkid.cb);
      if ( v9 && *v9 )
      {
        Attributes = FtpPidl_GetAttributes(*a3);
        *a4 &= ((Attributes & 1) != 0 ? 16453 : 16503) | ((Attributes & 0x10) != 0 ? -1602223872 : 138412032);
      }
      else
      {
        v11 = ILCombine((LPCITEMIDLIST)(*((_QWORD *)this + 6) + *((int *)this + 16)), *a3);
        v12 = (ITEMIDLIST *)v11;
        if ( !v11 )
          return 2147942414LL;
        v13 = FtpPidl_GetAttributes(v11);
        *a4 &= ((v13 & 1) != 0 ? 16453 : 16503) | ((v13 & 0x10) != 0 ? -1602223872 : 138412032);
        ILFree(v12);
      }
      if ( ++v8 >= a2 )
        return 0;
    }
  }
  v15 = (_WORD *)(*((_QWORD *)this + 6) + *((int *)this + 16));
  if ( !v15 || (v16 = -1593818761, !*v15) )
    v16 = -1593819017;
  *a4 &= v16;
  if ( (*a4 & 0x1000000) != 0 )
  {
    FtpDir = CFtpFolder::GetFtpDir(this);
    v18 = FtpDir;
    if ( FtpDir )
    {
      IUnknown_Set((struct CFtpDir **)FtpDir + 3, 0);
      (*(void (__fastcall **)(struct CFtpDir *))(*(_QWORD *)v18 + 16LL))(v18);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016620  push    rbx
0x180016622  push    rbp
0x180016623  push    rsi
0x180016624  push    rdi
0x180016625  push    r12
0x180016627  push    r14
0x180016629  push    r15
0x18001662b  sub     rsp, 20h
0x18001662f  xor     r12d, r12d
0x180016632  mov     rbx, r9
0x180016635  mov     rsi, r8
0x180016638  mov     r14d, edx
0x18001663b  mov     rdi, rcx
0x18001663e  test    edx, edx
0x180016640  jz      loc_18001671E
0x180016646  test    r8, r8
0x180016649  jz      loc_18001671E
0x18001664f  mov     rax, [r8]
0x180016652  test    rax, rax
0x180016655  jz      loc_18001671E
0x18001665b  cmp     [rax], r12w
0x18001665f  jz      loc_18001671E
0x180016665  cmp     edx, 1
0x180016668  jbe     short loc_180016671
0x18001666a  and     dword ptr [r9], 0FFFFFEEFh
0x180016671  mov     ebp, r12d
0x180016674  mov     eax, ebp
0x180016676  mov     rcx, [rsi+rax*8]
0x18001667a  movzx   edx, word ptr [rcx]
0x18001667d  add     rdx, rcx
0x180016680  jz      short loc_1800166B9
0x180016682  cmp     [rdx], r12w
0x180016686  jz      short loc_1800166B9
0x180016688  mov     rcx, [rsi]; struct _ITEMIDLIST *
0x18001668b  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x180016690  mov     ecx, eax
0x180016692  and     cl, 10h
0x180016695  neg     cl
0x180016697  sbb     edx, edx
0x180016699  and     al, 1
0x18001669b  and     edx, 98400100h
0x1800166a1  add     edx, 8400000h
0x1800166a7  neg     al
0x1800166a9  sbb     eax, eax
0x1800166ab  and     eax, 0FFFFFFCEh
0x1800166ae  add     eax, 4077h
0x1800166b3  or      edx, eax
0x1800166b5  and     [rbx], edx
0x1800166b7  jmp     short loc_18001670A
0x1800166b9  movsxd  rcx, dword ptr [rdi+40h]
0x1800166bd  add     rcx, [rdi+30h]; pidl1
0x1800166c1  mov     rdx, [rsi]; pidl2
0x1800166c4  call    cs:__imp_ILCombine
0x1800166ca  mov     r15, rax
0x1800166cd  test    rax, rax
0x1800166d0  jz      short loc_180016717
0x1800166d2  mov     rcx, rax; struct _ITEMIDLIST *
0x1800166d5  call    ?FtpPidl_GetAttributes@@YAKPEFBU_ITEMIDLIST@@@Z; FtpPidl_GetAttributes(_ITEMIDLIST const *)
0x1800166da  mov     ecx, eax
0x1800166dc  and     cl, 10h
0x1800166df  neg     cl
0x1800166e1  mov     rcx, r15; pidl
0x1800166e4  sbb     edx, edx
0x1800166e6  and     al, 1
0x1800166e8  and     edx, 98400100h
0x1800166ee  add     edx, 8400000h
0x1800166f4  neg     al
0x1800166f6  sbb     eax, eax
0x1800166f8  and     eax, 0FFFFFFCEh
0x1800166fb  add     eax, 4077h
0x180016700  or      edx, eax
0x180016702  and     [rbx], edx
0x180016704  call    cs:__imp_ILFree
0x18001670a  inc     ebp
0x18001670c  cmp     ebp, r14d
0x18001670f  jb      loc_180016674
0x180016715  jmp     short loc_18001676B
0x180016717  mov     eax, 8007000Eh
0x18001671c  jmp     short loc_18001676E
0x18001671e  movsxd  rdx, dword ptr [rcx+40h]
0x180016722  add     rdx, [rcx+30h]
0x180016726  jz      short loc_180016733
0x180016728  mov     eax, 0A1004177h
0x18001672d  cmp     [rdx], r12w
0x180016731  jnz     short loc_180016738
0x180016733  mov     eax, 0A1004077h
0x180016738  and     [r9], eax
0x18001673b  test    dword ptr [r9], 1000000h
0x180016742  jz      short loc_18001676B
0x180016744  call    ?GetFtpDir@CFtpFolder@@QEAAPEAVCFtpDir@@XZ; CFtpFolder::GetFtpDir(void)
0x180016749  mov     rbx, rax
0x18001674c  test    rax, rax
0x18001674f  jz      short loc_18001676B
0x180016751  lea     rcx, [rax+18h]; struct CFtpDir **
0x180016755  xor     edx, edx; struct CFtpDir *
0x180016757  call    ?IUnknown_Set@@YAXPEAPEAVCFtpDir@@PEAV1@@Z; IUnknown_Set(CFtpDir * *,CFtpDir *)
0x18001675c  mov     rcx, [rbx]
0x18001675f  mov     rax, [rcx+10h]
0x180016763  mov     rcx, rbx
0x180016766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001676b  mov     eax, r12d
0x18001676e  add     rsp, 20h
0x180016772  pop     r15
0x180016774  pop     r14
0x180016776  pop     r12
0x180016778  pop     rdi
0x180016779  pop     rsi
0x18001677a  pop     rbp
0x18001677b  pop     rbx
0x18001677c  retn
```
