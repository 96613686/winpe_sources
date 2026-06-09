# CFtpObj::_RenderFileContents(tagFORMATETC const *,tagSTGMEDIUM *)

- ea: `0x18001b1b8`
- end: `0x18001b2d7`
- name: `?_RenderFileContents@CFtpObj@@IEAAJPEBUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `287`
- prototype: `__int64 __fastcall(CFtpObj *__hidden this, const struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180019e80`

## callees

- `0x18001b1b8`
- `0x18001ce78`
- `0x180020efc`
- `0x1800269f4`
- `0x180028010`

## import_xrefs

- `SHELL32!__imp_ILCombine` at `0x18001b238`
- `SHELL32!__imp_ILCombine` at `0x18001b238`
- `SHELL32!__imp_ILFree` at `0x18001b298`
- `SHELL32!__imp_ILFree` at `0x18001b298`
- `SHLWAPI!__imp_IUnknown_Set` at `0x18001b2c4`
- `SHLWAPI!__imp_IUnknown_Set` at `0x18001b2c4`

## pseudocode

```c
__int64 __fastcall CFtpObj::_RenderFileContents(CFtpObj *this, const struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rcx
  const ITEMIDLIST *Ptr; // rsi
  LPITEMIDLIST v9; // rsi
  __int64 v10; // rcx

  v6 = -2147024809;
  if ( a2->lindex == -1 )
    return v6;
  v7 = *(_QWORD *)(*((_QWORD *)this + 7) + 16LL);
  if ( v7 )
    Ptr = (const ITEMIDLIST *)DPA_GetPtr(*(HDPA *)(v7 + 16), a2->lindex);
  else
    Ptr = 0;
  a3->pUnkForRelease = 0;
  a3->tymed = 4;
  if ( !Ptr )
    goto LABEL_11;
  if ( (unsigned int)FtpPidl_IsDirectory(Ptr, 0) )
  {
    v6 = -2147221400;
LABEL_11:
    v10 = *((_QWORD *)this + 11);
    *((_DWORD *)this + 28) = -1;
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10);
      IUnknown_Set((IUnknown **)this + 11, 0);
    }
    return v6;
  }
  v9 = ILCombine(
         (LPCITEMIDLIST)(*(_QWORD *)(*((_QWORD *)this + 5) + 48LL) + *(int *)(*((_QWORD *)this + 5) + 64LL)),
         Ptr);
  v6 = v9 == 0 ? 0x8007000E : 0;
  if ( v9 )
  {
    v6 = CFtpStm_Create(
           *((const struct _ITEMIDLIST ***)this + 6),
           v9,
           0x80000000,
           &a3->pstm,
           *(union _ULARGE_INTEGER *)((char *)this + 96),
           *(union _ULARGE_INTEGER *)((char *)this + 104),
           *((IUnknown **)this + 11),
           a2->lindex == *((_DWORD *)this + 29));
    ILFree(v9);
  }
  if ( (v6 & 0x80000000) != 0 )
    goto LABEL_11;
  return v6;
}

```

## disassembly

```asm
0x18001b1b8  push    rbx
0x18001b1ba  push    rbp
0x18001b1bb  push    rsi
0x18001b1bc  push    rdi
0x18001b1bd  push    r14
0x18001b1bf  sub     rsp, 40h
0x18001b1c3  cmp     dword ptr [rdx+14h], 0FFFFFFFFh
0x18001b1c7  mov     r14, r8
0x18001b1ca  mov     rbp, rdx
0x18001b1cd  mov     rdi, rcx
0x18001b1d0  mov     ebx, 80070057h
0x18001b1d5  jz      loc_18001B2CA
0x18001b1db  mov     rax, [rcx+38h]
0x18001b1df  mov     rcx, [rax+10h]
0x18001b1e3  test    rcx, rcx
0x18001b1e6  jz      short loc_18001B1FA
0x18001b1e8  movsxd  rdx, dword ptr [rdx+14h]; i
0x18001b1ec  mov     rcx, [rcx+10h]; hdpa
0x18001b1f0  call    DPA_GetPtr
0x18001b1f5  mov     rsi, rax
0x18001b1f8  jmp     short loc_18001B1FC
0x18001b1fa  xor     esi, esi
0x18001b1fc  mov     qword ptr [r14+10h], 0
0x18001b204  mov     dword ptr [r14], 4
0x18001b20b  test    rsi, rsi
0x18001b20e  jz      loc_18001B2A2
0x18001b214  xor     edx, edx; int
0x18001b216  mov     rcx, rsi; struct _ITEMIDLIST *
0x18001b219  call    ?FtpPidl_IsDirectory@@YAHPEFBU_ITEMIDLIST@@H@Z; FtpPidl_IsDirectory(_ITEMIDLIST const *,int)
0x18001b21e  test    eax, eax
0x18001b220  jz      short loc_18001B229
0x18001b222  mov     ebx, 80040068h
0x18001b227  jmp     short loc_18001B2A2
0x18001b229  mov     rax, [rdi+28h]
0x18001b22d  mov     rdx, rsi; pidl2
0x18001b230  movsxd  rcx, dword ptr [rax+40h]
0x18001b234  add     rcx, [rax+30h]; pidl1
0x18001b238  call    cs:__imp_ILCombine
0x18001b23e  mov     rsi, rax
0x18001b241  neg     rax
0x18001b244  sbb     ebx, ebx
0x18001b246  not     ebx
0x18001b248  and     ebx, 8007000Eh
0x18001b24e  test    rsi, rsi
0x18001b251  jz      short loc_18001B29E
0x18001b253  mov     eax, [rdi+74h]
0x18001b256  lea     r9, [r14+8]; struct IStream **
0x18001b25a  xor     ecx, ecx
0x18001b25c  mov     r8d, 80000000h; unsigned int
0x18001b262  cmp     [rbp+14h], eax
0x18001b265  mov     rdx, rsi; struct _ITEMIDLIST *
0x18001b268  mov     rax, [rdi+58h]
0x18001b26c  setz    cl
0x18001b26f  mov     [rsp+68h+var_30], ecx; int
0x18001b273  mov     rcx, [rdi+30h]; struct CFtpDir *
0x18001b277  mov     [rsp+68h+var_38], rax; struct IProgressDialog *
0x18001b27c  mov     rax, [rdi+68h]
0x18001b280  mov     qword ptr [rsp+68h+var_40], rax; union _ULARGE_INTEGER
0x18001b285  mov     rax, [rdi+60h]
0x18001b289  mov     qword ptr [rsp+68h+var_48], rax; union _ULARGE_INTEGER
0x18001b28e  call    ?CFtpStm_Create@@YAJPEAVCFtpDir@@PEFBU_ITEMIDLIST@@KPEAPEAUIStream@@T_ULARGE_INTEGER@@3PEAUIProgressDialog@@H@Z; CFtpStm_Create(CFtpDir *,_ITEMIDLIST const *,ulong,IStream * *,_ULARGE_INTEGER,_ULARGE_INTEGER,IProgressDialog *,int)
0x18001b293  mov     rcx, rsi; pidl
0x18001b296  mov     ebx, eax
0x18001b298  call    cs:__imp_ILFree
0x18001b29e  test    ebx, ebx
0x18001b2a0  jns     short loc_18001B2CA
0x18001b2a2  mov     rcx, [rdi+58h]
0x18001b2a6  mov     dword ptr [rdi+70h], 0FFFFFFFFh
0x18001b2ad  test    rcx, rcx
0x18001b2b0  jz      short loc_18001B2CA
0x18001b2b2  mov     rax, [rcx]
0x18001b2b5  mov     rax, [rax+20h]
0x18001b2b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2be  xor     edx, edx; punk
0x18001b2c0  lea     rcx, [rdi+58h]; ppunk
0x18001b2c4  call    cs:__imp_IUnknown_Set
0x18001b2ca  mov     eax, ebx
0x18001b2cc  add     rsp, 40h
0x18001b2d0  pop     r14
0x18001b2d2  pop     rdi
0x18001b2d3  pop     rsi
0x18001b2d4  pop     rbp
0x18001b2d5  pop     rbx
0x18001b2d6  retn
```
