# COleObject::Convert(_GUID const &,char const *)

- ea: `0x18005361c`
- end: `0x1800538f6`
- name: `?Convert@COleObject@@QEAAJAEBU_GUID@@PEBD@Z`
- size: `730`
- prototype: `__int64 __fastcall(struct IOleClientSite *this, const struct _GUID *, LPCCH lpMultiByteStr)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x18006ed30`

## callees

- `0x18000df8c`
- `0x180018390`
- `0x180041adc`
- `0x18004af3c`
- `0x180053284`
- `0x1800532ec`
- `0x18005361c`
- `0x18008d624`
- `0x18008fef8`
- `0x1800907ac`
- `0x180090f20`
- `0x180090f8c`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18005377b`
- `KERNEL32!MultiByteToWideChar` at `0x18005377b`

## string_xrefs

- `0x1800536dd`: `ReadFmtUserTypeStg`
- `0x180053694`: `ReadClassStg`

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
0x18005361c  mov     [rsp-8+arg_18], rbx
0x180053621  push    rbp
0x180053622  push    rsi
0x180053623  push    rdi
0x180053624  push    r12
0x180053626  push    r13
0x180053628  push    r14
0x18005362a  push    r15
0x18005362c  lea     rbp, [rsp-1D0h]
0x180053634  sub     rsp, 2D0h
0x18005363b  mov     rax, cs:__security_cookie
0x180053642  xor     rax, rsp
0x180053645  mov     [rbp+200h+var_40], rax
0x18005364c  mov     rsi, [rcx+50h]
0x180053650  xor     r15d, r15d
0x180053653  mov     [rsp+300h+var_2C0], r15w
0x180053659  xorps   xmm0, xmm0
0x18005365c  mov     [rsp+300h+var_2B8], r15
0x180053661  mov     r13, r8
0x180053664  mov     r14, rdx
0x180053667  mov     rdi, rcx
0x18005366a  movups  xmmword ptr [rbp+200h+var_260.Data1], xmm0
0x18005366e  test    rsi, rsi
0x180053671  jnz     short loc_18005367D
0x180053673  mov     eax, 80070057h
0x180053678  jmp     loc_1800538CC
0x18005367d  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x180053682  mov     r12d, 1
0x180053688  lea     rbx, [rax+0F8h]
0x18005368f  cmp     [rbx], r15
0x180053692  jnz     short loc_1800536A6
0x180053694  lea     r8, aReadclassstg; "ReadClassStg"
0x18005369b  mov     edx, r12d
0x18005369e  mov     rcx, rbx
0x1800536a1  call    SetProcAddr
0x1800536a6  mov     rax, [rbx]
0x1800536a9  test    rax, rax
0x1800536ac  jz      loc_1800538C5
0x1800536b2  lea     rdx, [rbp+200h+var_260]
0x1800536b6  mov     rcx, rsi
0x1800536b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536be  mov     ebx, eax
0x1800536c0  test    eax, eax
0x1800536c2  jnz     loc_1800538CA
0x1800536c8  mov     rsi, [rdi+50h]
0x1800536cc  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x1800536d1  lea     rbx, [rax+0F0h]
0x1800536d8  cmp     [rbx], r15
0x1800536db  jnz     short loc_1800536EF
0x1800536dd  lea     r8, aReadfmtusertyp; "ReadFmtUserTypeStg"
0x1800536e4  mov     edx, r12d
0x1800536e7  mov     rcx, rbx
0x1800536ea  call    SetProcAddr
0x1800536ef  mov     rax, [rbx]
0x1800536f2  test    rax, rax
0x1800536f5  jz      loc_1800538C5
0x1800536fb  lea     r8, [rsp+300h+var_2B8]
0x180053700  mov     rcx, rsi
0x180053703  lea     rdx, [rsp+300h+var_2C0]
0x180053708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005370d  mov     ebx, eax
0x18005370f  test    eax, eax
0x180053711  jnz     loc_1800538CA
0x180053717  xor     edx, edx; unsigned int
0x180053719  mov     rcx, rdi; this
0x18005371c  call    ?Close@COleObject@@QEAAXK@Z; COleObject::Close(ulong)
0x180053721  mov     rcx, [rdi+48h]
0x180053725  mov     rax, [rcx]
0x180053728  mov     rax, [rax+10h]
0x18005372c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053731  lea     rcx, [rdi+18h]; this
0x180053735  call    ?IsZombie@CSafeRefCount@@QEAAHXZ; CSafeRefCount::IsZombie(void)
0x18005373a  test    eax, eax
0x18005373c  jnz     loc_1800538BE
0x180053742  mov     rcx, [rdi+50h]; struct IStorage *
0x180053746  mov     rdx, r14; struct _GUID *
0x180053749  call    ?WriteClassStg@CW32System@@SAJPEAUIStorage@@AEBU_GUID@@@Z; CW32System::WriteClassStg(IStorage *,_GUID const &)
0x18005374e  xor     r14d, r14d
0x180053751  mov     ebx, eax
0x180053753  test    eax, eax
0x180053755  jnz     loc_18005381B
0x18005375b  lea     rax, [rbp+200h+WideCharStr]
0x18005375f  mov     [rsp+300h+cchWideChar], 104h; cchWideChar
0x180053767  mov     r8, r13; lpMultiByteStr
0x18005376a  mov     [rsp+300h+lpWideCharStr], rax; lpWideCharStr
0x18005376f  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180053773  mov     edx, r12d; dwFlags
0x180053776  xor     ecx, ecx; CodePage
0x180053778  mov     r13d, r12d
0x18005377b  call    cs:__imp_MultiByteToWideChar
0x180053781  movzx   edx, [rsp+300h+var_2C0]; unsigned __int16
0x180053786  neg     eax
0x180053788  mov     rcx, [rdi+50h]; struct IStorage *
0x18005378c  lea     rax, [rbp+200h+WideCharStr]
0x180053790  sbb     r8, r8
0x180053793  and     r8, rax; unsigned __int16 *
0x180053796  call    ?WriteFmtUserTypeStg@CW32System@@SAJPEAUIStorage@@GPEAG@Z; CW32System::WriteFmtUserTypeStg(IStorage *,ushort,ushort *)
0x18005379b  mov     ebx, eax
0x18005379d  test    eax, eax
0x18005379f  jnz     short loc_18005381E
0x1800537a1  mov     rsi, [rdi+50h]
0x1800537a5  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x1800537aa  lea     rbx, [rax+0E8h]
0x1800537b1  cmp     [rbx], r14
0x1800537b4  jnz     short loc_1800537C8
0x1800537b6  lea     r8, aSetconvertstg; "SetConvertStg"
0x1800537bd  mov     edx, r12d
0x1800537c0  mov     rcx, rbx
0x1800537c3  call    SetProcAddr
0x1800537c8  mov     rax, [rbx]
0x1800537cb  test    rax, rax
0x1800537ce  jz      short loc_180053814
0x1800537d0  mov     edx, r13d
0x1800537d3  mov     rcx, rsi
0x1800537d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537db  mov     ebx, eax
0x1800537dd  test    eax, eax
0x1800537df  jnz     short loc_18005381E
0x1800537e1  mov     rcx, [rdi+50h]
0x1800537e5  xor     edx, edx
0x1800537e7  mov     rax, [rcx]
0x1800537ea  mov     rax, [rax+48h]
0x1800537ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537f3  mov     ebx, eax
0x1800537f5  test    eax, eax
0x1800537f7  jz      short loc_18005383E
0x1800537f9  mov     rcx, [rdi+50h]
0x1800537fd  mov     edx, r13d
0x180053800  mov     rax, [rcx]
0x180053803  mov     rax, [rax+48h]
0x180053807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005380c  mov     ebx, eax
0x18005380e  test    eax, eax
0x180053810  jz      short loc_18005383E
0x180053812  jmp     short loc_18005381E
0x180053814  mov     ebx, 80004005h
0x180053819  jmp     short loc_18005381E
0x18005381b  mov     r13d, r12d
0x18005381e  mov     rcx, [rdi+50h]; struct IStorage *
0x180053822  lea     rdx, [rbp+200h+var_260]; struct _GUID *
0x180053826  call    ?WriteClassStg@CW32System@@SAJPEAUIStorage@@AEBU_GUID@@@Z; CW32System::WriteClassStg(IStorage *,_GUID const &)
0x18005382b  mov     r8, [rsp+300h+var_2B8]; unsigned __int16 *
0x180053830  movzx   edx, [rsp+300h+var_2C0]; unsigned __int16
0x180053835  mov     rcx, [rdi+50h]; struct IStorage *
0x180053839  call    ?WriteFmtUserTypeStg@CW32System@@SAJPEAUIStorage@@GPEAG@Z; CW32System::WriteFmtUserTypeStg(IStorage *,ushort,ushort *)
0x18005383e  lea     rcx, [rdi+18h]; this
0x180053842  call    ?IsZombie@CSafeRefCount@@QEAAHXZ; CSafeRefCount::IsZombie(void)
0x180053847  test    eax, eax
0x180053849  jnz     short loc_1800538BE
0x18005384b  mov     rcx, [rdi+50h]; struct IStorage *
0x18005384f  lea     r9, [rdi+48h]; void **
0x180053853  mov     r8, rdi; struct IOleClientSite *
0x180053856  call    ?OleLoad@CW32System@@SAJPEAUIStorage@@AEBU_GUID@@PEAUIOleClientSite@@PEAPEAX@Z; CW32System::OleLoad(IStorage *,_GUID const &,IOleClientSite *,void * *)
0x18005385b  mov     esi, eax
0x18005385d  test    eax, eax
0x18005385f  jz      short loc_1800538A3
0x180053861  mov     r8d, [rdi+70h]; int
0x180053865  lea     rcx, [rsp+300h+var_2B0]; this
0x18005386a  mov     rdx, [rdi+40h]; struct CTxtEdit *
0x18005386e  call    ??0CRchTxtPtr@@QEAA@PEAVCTxtEdit@@J@Z; CRchTxtPtr::CRchTxtPtr(CTxtEdit *,long)
0x180053873  mov     [rsp+300h+var_2C8], r14d; unsigned int
0x180053878  lea     r9, asc_180098174; " "
0x18005387f  mov     [rsp+300h+var_2D0], r14; int *
0x180053884  lea     rcx, [rsp+300h+var_2B0]; this
0x180053889  mov     [rsp+300h+cchWideChar], 0FFFFFFFFh; int
0x180053891  mov     r8d, r13d; int
0x180053894  mov     edx, r13d; int
0x180053897  mov     [rsp+300h+lpWideCharStr], r14; struct IUndoBuilder *
0x18005389c  call    ?ReplaceRange@CRchTxtPtr@@QEAAJJJPEBGPEAVIUndoBuilder@@JPEAJK@Z; CRchTxtPtr::ReplaceRange(long,long,ushort const *,IUndoBuilder *,long,long *,ulong)
0x1800538a1  jmp     short loc_1800538AB
0x1800538a3  mov     rcx, rdi; this
0x1800538a6  call    ?ConnectObject@COleObject@@AEAAJXZ; COleObject::ConnectObject(void)
0x1800538ab  mov     rcx, [rsp+300h+var_2B8]; void *
0x1800538b0  call    ?CoTaskMemFree@CW32System@@SAXPEAX@Z; CW32System::CoTaskMemFree(void *)
0x1800538b5  test    ebx, ebx
0x1800538b7  cmovnz  esi, ebx
0x1800538ba  mov     eax, esi
0x1800538bc  jmp     short loc_1800538CC
0x1800538be  mov     eax, 800401FFh
0x1800538c3  jmp     short loc_1800538CC
0x1800538c5  mov     ebx, 80004005h
0x1800538ca  mov     eax, ebx
0x1800538cc  mov     rcx, [rbp+200h+var_40]
0x1800538d3  xor     rcx, rsp; StackCookie
0x1800538d6  call    __security_check_cookie
0x1800538db  mov     rbx, [rsp+300h+arg_18]
0x1800538e3  add     rsp, 2D0h
0x1800538ea  pop     r15
0x1800538ec  pop     r14
0x1800538ee  pop     r13
0x1800538f0  pop     r12
0x1800538f2  pop     rdi
0x1800538f3  pop     rsi
0x1800538f4  pop     rbp
0x1800538f5  retn
```
