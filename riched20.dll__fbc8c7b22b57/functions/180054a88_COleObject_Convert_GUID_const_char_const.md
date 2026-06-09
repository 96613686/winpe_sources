# COleObject::Convert(_GUID const &,char const *)

- ea: `0x180054a88`
- end: `0x180054d69`
- name: `?Convert@COleObject@@QEAAJAEBU_GUID@@PEBD@Z`
- size: `737`
- prototype: `__int64 __fastcall(struct IOleClientSite *this, const struct _GUID *, LPCCH lpMultiByteStr)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x180070ba0`

## callees

- `0x18000e40c`
- `0x180017230`
- `0x1800427ac`
- `0x18004c10c`
- `0x1800546e8`
- `0x180054750`
- `0x180054a88`
- `0x18008fe00`
- `0x180092870`
- `0x1800931b0`
- `0x1800939d0`
- `0x180093a3c`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180054be7`
- `KERNEL32!MultiByteToWideChar` at `0x180054be7`

## string_xrefs

- `0x180054b49`: `ReadFmtUserTypeStg`
- `0x180054b00`: `ReadClassStg`

## pseudocode

```c
__int64 __fastcall COleObject::Convert(struct IOleClientSite *this, const struct _GUID *a2, LPCCH lpMultiByteStr)
{
  struct IOleClientSiteVtbl *lpVtbl; // rsi
  struct COLE32_PROC *Ole32Procs; // rax
  __int64 (__fastcall **v9)(struct IOleClientSiteVtbl *, struct _GUID *); // rbx
  unsigned int v10; // ebx
  struct IOleClientSiteVtbl *v11; // rsi
  struct COLE32_PROC *v12; // rax
  __int64 (__fastcall **v13)(struct IOleClientSiteVtbl *, unsigned __int16 *, unsigned __int16 **); // rbx
  unsigned int v14; // ebx
  int v15; // eax
  struct IOleClientSiteVtbl *v16; // rsi
  struct COLE32_PROC *v17; // rax
  __int64 (__fastcall **v18)(struct IOleClientSiteVtbl *, __int64); // rbx
  const struct _GUID *v19; // rdx
  unsigned int v20; // esi
  unsigned __int16 v21; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v22; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v23[80]; // [rsp+50h] [rbp-B0h] BYREF
  struct _GUID v24; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR WideCharStr[264]; // [rsp+B0h] [rbp-50h] BYREF

  lpVtbl = this[10].lpVtbl;
  v21 = 0;
  v22 = 0;
  v24 = 0;
  if ( !lpVtbl )
    return 2147942487LL;
  Ole32Procs = CThreadData::GetOle32Procs();
  v9 = (__int64 (__fastcall **)(struct IOleClientSiteVtbl *, struct _GUID *))((char *)Ole32Procs + 248);
  if ( !*((_QWORD *)Ole32Procs + 31) )
    SetProcAddr((FARPROC *)Ole32Procs + 31, 1, "ReadClassStg");
  if ( !*v9 )
    return (unsigned int)-2147467259;
  v10 = (*v9)(lpVtbl, &v24);
  if ( v10 )
    return v10;
  v11 = this[10].lpVtbl;
  v12 = CThreadData::GetOle32Procs();
  v13 = (__int64 (__fastcall **)(struct IOleClientSiteVtbl *, unsigned __int16 *, unsigned __int16 **))((char *)v12 + 240);
  if ( !*((_QWORD *)v12 + 30) )
    SetProcAddr((FARPROC *)v12 + 30, 1, "ReadFmtUserTypeStg");
  if ( !*v13 )
    return (unsigned int)-2147467259;
  v10 = (*v13)(v11, &v21, &v22);
  if ( v10 )
    return v10;
  COleObject::Close((COleObject *)this, 0);
  (*((void (__fastcall **)(struct IOleClientSiteVtbl *))this[9].lpVtbl->QueryInterface + 2))(this[9].lpVtbl);
  if ( (unsigned int)CSafeRefCount::IsZombie((CSafeRefCount *)&this[3]) )
    return 2147746303LL;
  v14 = CW32System::WriteClassStg((struct IStorage *)this[10].lpVtbl, a2);
  if ( v14 )
    goto LABEL_22;
  v15 = MultiByteToWideChar(0, 1u, lpMultiByteStr, -1, WideCharStr, 260);
  v14 = CW32System::WriteFmtUserTypeStg(
          (struct IStorage *)this[10].lpVtbl,
          v21,
          (unsigned __int16 *)((unsigned __int64)WideCharStr & -(__int64)(v15 != 0)));
  if ( v14 )
    goto LABEL_22;
  v16 = this[10].lpVtbl;
  v17 = CThreadData::GetOle32Procs();
  v18 = (__int64 (__fastcall **)(struct IOleClientSiteVtbl *, __int64))((char *)v17 + 232);
  if ( !*((_QWORD *)v17 + 29) )
    SetProcAddr((FARPROC *)v17 + 29, 1, "SetConvertStg");
  if ( !*v18 )
  {
    v14 = -2147467259;
LABEL_22:
    CW32System::WriteClassStg((struct IStorage *)this[10].lpVtbl, &v24);
    CW32System::WriteFmtUserTypeStg((struct IStorage *)this[10].lpVtbl, v21, v22);
    goto LABEL_23;
  }
  v14 = (*v18)(v16, 1);
  if ( v14 )
    goto LABEL_22;
  v14 = (*((__int64 (__fastcall **)(struct IOleClientSiteVtbl *, _QWORD))this[10].lpVtbl->QueryInterface + 9))(
          this[10].lpVtbl,
          0);
  if ( v14 )
  {
    v14 = (*((__int64 (__fastcall **)(struct IOleClientSiteVtbl *, __int64))this[10].lpVtbl->QueryInterface + 9))(
            this[10].lpVtbl,
            1);
    if ( v14 )
      goto LABEL_22;
  }
LABEL_23:
  if ( (unsigned int)CSafeRefCount::IsZombie((CSafeRefCount *)&this[3]) )
    return 2147746303LL;
  v20 = CW32System::OleLoad((struct IStorage *)this[10].lpVtbl, v19, this, (void **)&this[9].lpVtbl);
  if ( v20 )
  {
    CRchTxtPtr::CRchTxtPtr((CRchTxtPtr *)v23, (struct CTxtEdit *)this[8].lpVtbl, (int)this[14].lpVtbl);
    CRchTxtPtr::ReplaceRange((CRchTxtPtr *)v23, 1, 1, L" ", 0, -1, 0, 0);
  }
  else
  {
    COleObject::ConnectObject((COleObject *)this);
  }
  CW32System::CoTaskMemFree(v22);
  if ( v14 )
    return v14;
  return v20;
}

```

## disassembly

```asm
0x180054a88  mov     [rsp-8+arg_18], rbx
0x180054a8d  push    rbp
0x180054a8e  push    rsi
0x180054a8f  push    rdi
0x180054a90  push    r12
0x180054a92  push    r13
0x180054a94  push    r14
0x180054a96  push    r15
0x180054a98  lea     rbp, [rsp-1D0h]
0x180054aa0  sub     rsp, 2D0h
0x180054aa7  mov     rax, cs:__security_cookie
0x180054aae  xor     rax, rsp
0x180054ab1  mov     [rbp+200h+var_40], rax
0x180054ab8  mov     rsi, [rcx+50h]
0x180054abc  xor     r15d, r15d
0x180054abf  mov     [rsp+300h+var_2C0], r15w
0x180054ac5  xorps   xmm0, xmm0
0x180054ac8  mov     [rsp+300h+var_2B8], r15
0x180054acd  mov     r13, r8
0x180054ad0  mov     r14, rdx
0x180054ad3  mov     rdi, rcx
0x180054ad6  movups  xmmword ptr [rbp+200h+var_260.Data1], xmm0
0x180054ada  test    rsi, rsi
0x180054add  jnz     short loc_180054AE9
0x180054adf  mov     eax, 80070057h
0x180054ae4  jmp     loc_180054D3E
0x180054ae9  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x180054aee  mov     r12d, 1
0x180054af4  lea     rbx, [rax+0F8h]
0x180054afb  cmp     [rbx], r15
0x180054afe  jnz     short loc_180054B12
0x180054b00  lea     r8, aReadclassstg; "ReadClassStg"
0x180054b07  mov     edx, r12d
0x180054b0a  mov     rcx, rbx
0x180054b0d  call    SetProcAddr
0x180054b12  mov     rax, [rbx]
0x180054b15  test    rax, rax
0x180054b18  jz      loc_180054D37
0x180054b1e  lea     rdx, [rbp+200h+var_260]
0x180054b22  mov     rcx, rsi
0x180054b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b2a  mov     ebx, eax
0x180054b2c  test    eax, eax
0x180054b2e  jnz     loc_180054D3C
0x180054b34  mov     rsi, [rdi+50h]
0x180054b38  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x180054b3d  lea     rbx, [rax+0F0h]
0x180054b44  cmp     [rbx], r15
0x180054b47  jnz     short loc_180054B5B
0x180054b49  lea     r8, aReadfmtusertyp; "ReadFmtUserTypeStg"
0x180054b50  mov     edx, r12d
0x180054b53  mov     rcx, rbx
0x180054b56  call    SetProcAddr
0x180054b5b  mov     rax, [rbx]
0x180054b5e  test    rax, rax
0x180054b61  jz      loc_180054D37
0x180054b67  lea     r8, [rsp+300h+var_2B8]
0x180054b6c  mov     rcx, rsi
0x180054b6f  lea     rdx, [rsp+300h+var_2C0]
0x180054b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b79  mov     ebx, eax
0x180054b7b  test    eax, eax
0x180054b7d  jnz     loc_180054D3C
0x180054b83  xor     edx, edx; unsigned int
0x180054b85  mov     rcx, rdi; this
0x180054b88  call    ?Close@COleObject@@QEAAXK@Z; COleObject::Close(ulong)
0x180054b8d  mov     rcx, [rdi+48h]
0x180054b91  mov     rax, [rcx]
0x180054b94  mov     rax, [rax+10h]
0x180054b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054b9d  lea     rcx, [rdi+18h]; this
0x180054ba1  call    ?IsZombie@CSafeRefCount@@QEAAHXZ; CSafeRefCount::IsZombie(void)
0x180054ba6  test    eax, eax
0x180054ba8  jnz     loc_180054D30
0x180054bae  mov     rcx, [rdi+50h]; struct IStorage *
0x180054bb2  mov     rdx, r14; struct _GUID *
0x180054bb5  call    ?WriteClassStg@CW32System@@SAJPEAUIStorage@@AEBU_GUID@@@Z; CW32System::WriteClassStg(IStorage *,_GUID const &)
0x180054bba  xor     r14d, r14d
0x180054bbd  mov     ebx, eax
0x180054bbf  test    eax, eax
0x180054bc1  jnz     loc_180054C8D
0x180054bc7  lea     rax, [rbp+200h+WideCharStr]
0x180054bcb  mov     [rsp+300h+cchWideChar], 104h; cchWideChar
0x180054bd3  mov     r8, r13; lpMultiByteStr
0x180054bd6  mov     [rsp+300h+lpWideCharStr], rax; lpWideCharStr
0x180054bdb  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180054bdf  mov     edx, r12d; dwFlags
0x180054be2  xor     ecx, ecx; CodePage
0x180054be4  mov     r13d, r12d
0x180054be7  call    cs:__imp_MultiByteToWideChar
0x180054bee  nop     dword ptr [rax+rax+00h]
0x180054bf3  movzx   edx, [rsp+300h+var_2C0]; unsigned __int16
0x180054bf8  neg     eax
0x180054bfa  mov     rcx, [rdi+50h]; struct IStorage *
0x180054bfe  lea     rax, [rbp+200h+WideCharStr]
0x180054c02  sbb     r8, r8
0x180054c05  and     r8, rax; unsigned __int16 *
0x180054c08  call    ?WriteFmtUserTypeStg@CW32System@@SAJPEAUIStorage@@GPEAG@Z; CW32System::WriteFmtUserTypeStg(IStorage *,ushort,ushort *)
0x180054c0d  mov     ebx, eax
0x180054c0f  test    eax, eax
0x180054c11  jnz     short loc_180054C90
0x180054c13  mov     rsi, [rdi+50h]
0x180054c17  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x180054c1c  lea     rbx, [rax+0E8h]
0x180054c23  cmp     [rbx], r14
0x180054c26  jnz     short loc_180054C3A
0x180054c28  lea     r8, aSetconvertstg; "SetConvertStg"
0x180054c2f  mov     edx, r12d
0x180054c32  mov     rcx, rbx
0x180054c35  call    SetProcAddr
0x180054c3a  mov     rax, [rbx]
0x180054c3d  test    rax, rax
0x180054c40  jz      short loc_180054C86
0x180054c42  mov     edx, r13d
0x180054c45  mov     rcx, rsi
0x180054c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c4d  mov     ebx, eax
0x180054c4f  test    eax, eax
0x180054c51  jnz     short loc_180054C90
0x180054c53  mov     rcx, [rdi+50h]
0x180054c57  xor     edx, edx
0x180054c59  mov     rax, [rcx]
0x180054c5c  mov     rax, [rax+48h]
0x180054c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c65  mov     ebx, eax
0x180054c67  test    eax, eax
0x180054c69  jz      short loc_180054CB0
0x180054c6b  mov     rcx, [rdi+50h]
0x180054c6f  mov     edx, r13d
0x180054c72  mov     rax, [rcx]
0x180054c75  mov     rax, [rax+48h]
0x180054c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054c7e  mov     ebx, eax
0x180054c80  test    eax, eax
0x180054c82  jz      short loc_180054CB0
0x180054c84  jmp     short loc_180054C90
0x180054c86  mov     ebx, 80004005h
0x180054c8b  jmp     short loc_180054C90
0x180054c8d  mov     r13d, r12d
0x180054c90  mov     rcx, [rdi+50h]; struct IStorage *
0x180054c94  lea     rdx, [rbp+200h+var_260]; struct _GUID *
0x180054c98  call    ?WriteClassStg@CW32System@@SAJPEAUIStorage@@AEBU_GUID@@@Z; CW32System::WriteClassStg(IStorage *,_GUID const &)
0x180054c9d  mov     r8, [rsp+300h+var_2B8]; unsigned __int16 *
0x180054ca2  movzx   edx, [rsp+300h+var_2C0]; unsigned __int16
0x180054ca7  mov     rcx, [rdi+50h]; struct IStorage *
0x180054cab  call    ?WriteFmtUserTypeStg@CW32System@@SAJPEAUIStorage@@GPEAG@Z; CW32System::WriteFmtUserTypeStg(IStorage *,ushort,ushort *)
0x180054cb0  lea     rcx, [rdi+18h]; this
0x180054cb4  call    ?IsZombie@CSafeRefCount@@QEAAHXZ; CSafeRefCount::IsZombie(void)
0x180054cb9  test    eax, eax
0x180054cbb  jnz     short loc_180054D30
0x180054cbd  mov     rcx, [rdi+50h]; struct IStorage *
0x180054cc1  lea     r9, [rdi+48h]; void **
0x180054cc5  mov     r8, rdi; struct IOleClientSite *
0x180054cc8  call    ?OleLoad@CW32System@@SAJPEAUIStorage@@AEBU_GUID@@PEAUIOleClientSite@@PEAPEAX@Z; CW32System::OleLoad(IStorage *,_GUID const &,IOleClientSite *,void * *)
0x180054ccd  mov     esi, eax
0x180054ccf  test    eax, eax
0x180054cd1  jz      short loc_180054D15
0x180054cd3  mov     r8d, [rdi+70h]; int
0x180054cd7  lea     rcx, [rsp+300h+var_2B0]; this
0x180054cdc  mov     rdx, [rdi+40h]; struct CTxtEdit *
0x180054ce0  call    ??0CRchTxtPtr@@QEAA@PEAVCTxtEdit@@J@Z; CRchTxtPtr::CRchTxtPtr(CTxtEdit *,long)
0x180054ce5  mov     [rsp+300h+var_2C8], r14d; unsigned int
0x180054cea  lea     r9, asc_18009B174; " "
0x180054cf1  mov     [rsp+300h+var_2D0], r14; int *
0x180054cf6  lea     rcx, [rsp+300h+var_2B0]; this
0x180054cfb  mov     [rsp+300h+cchWideChar], 0FFFFFFFFh; int
0x180054d03  mov     r8d, r13d; int
0x180054d06  mov     edx, r13d; int
0x180054d09  mov     [rsp+300h+lpWideCharStr], r14; struct IUndoBuilder *
0x180054d0e  call    ?ReplaceRange@CRchTxtPtr@@QEAAJJJPEBGPEAVIUndoBuilder@@JPEAJK@Z; CRchTxtPtr::ReplaceRange(long,long,ushort const *,IUndoBuilder *,long,long *,ulong)
0x180054d13  jmp     short loc_180054D1D
0x180054d15  mov     rcx, rdi; this
0x180054d18  call    ?ConnectObject@COleObject@@AEAAJXZ; COleObject::ConnectObject(void)
0x180054d1d  mov     rcx, [rsp+300h+var_2B8]; void *
0x180054d22  call    ?CoTaskMemFree@CW32System@@SAXPEAX@Z; CW32System::CoTaskMemFree(void *)
0x180054d27  test    ebx, ebx
0x180054d29  cmovnz  esi, ebx
0x180054d2c  mov     eax, esi
0x180054d2e  jmp     short loc_180054D3E
0x180054d30  mov     eax, 800401FFh
0x180054d35  jmp     short loc_180054D3E
0x180054d37  mov     ebx, 80004005h
0x180054d3c  mov     eax, ebx
0x180054d3e  mov     rcx, [rbp+200h+var_40]
0x180054d45  xor     rcx, rsp; StackCookie
0x180054d48  call    __security_check_cookie
0x180054d4d  mov     rbx, [rsp+300h+arg_18]
0x180054d55  add     rsp, 2D0h
0x180054d5c  pop     r15
0x180054d5e  pop     r14
0x180054d60  pop     r13
0x180054d62  pop     r12
0x180054d64  pop     rdi
0x180054d65  pop     rsi
0x180054d66  pop     rbp
0x180054d67  retn
```
