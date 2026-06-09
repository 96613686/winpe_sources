# CCertTypeInfo::_FindInDS(ldap *,ushort const * *,ulong,ulong,ulong,CCertTypeInfo * *)

- ea: `0x18003211c`
- end: `0x180032379`
- name: `?_FindInDS@CCertTypeInfo@@KAJPEAUldap@@PEAPEBGKKKPEAPEAV1@@Z`
- size: `605`
- prototype: `__int64 __fastcall(struct ldap *, const unsigned __int16 **, __int16, unsigned int, unsigned int, struct CCertTypeInfo **)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18002ff3c`

## callees

- `0x1800019a0`
- `0x180008400`
- `0x180008610`
- `0x18000a630`
- `0x18000d520`
- `0x18000e500`
- `0x180011130`
- `0x1800113e0`
- `0x180012260`
- `0x180014fac`
- `0x18002fa14`
- `0x18003211c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180032217`
- `msvcrt!_wcsicmp` at `0x180032217`

## string_xrefs

- `0x1800321da`: `msPKI-Cert-Template-OID`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_FindInDS(
        struct ldap *a1,
        const unsigned __int16 **a2,
        __int16 a3,
        unsigned int a4,
        unsigned int a5,
        struct CCertTypeInfo **a6)
{
  unsigned int v8; // ebx
  unsigned int v9; // edx
  int v10; // eax
  CCertTypeInfo *v11; // rsi
  CCertTypeInfo *v12; // rbx
  CCertTypeInfo *v13; // r13
  int v14; // edi
  int v15; // eax
  struct CCertTypeInfo *v16; // rdx
  CCertTypeInfo *v17; // rax
  CCertTypeInfo *v18; // rdi
  unsigned int v19; // edx
  const wchar_t **v21; // [rsp+30h] [rbp-28h] BYREF
  struct CCertTypeInfo *v22[4]; // [rsp+38h] [rbp-20h] BYREF

  v22[0] = 0;
  v21 = 0;
  if ( !a6 )
  {
    v8 = -2147467261;
    CSPrintErrorLineFile(0xB740328u, -2147467261);
    goto LABEL_42;
  }
  *a6 = 0;
  v10 = CCertTypeInfo::_EnumFromDS(a1, a3, a4, a5, v22);
  v8 = v10;
  if ( v10 )
  {
    CSPrintErrorLineFile(0xB7F0328u, v10);
    v11 = v22[0];
    goto LABEL_39;
  }
  v11 = v22[0];
LABEL_6:
  if ( !a2 || !*a2 )
  {
    v8 = 0;
    goto LABEL_39;
  }
  v12 = v11;
  v13 = 0;
  v14 = 0;
  while ( v12 )
  {
    if ( (a3 & 0x200) != 0 )
    {
      v15 = CAGetCertTypePropertyEx(v12, L"msPKI-Cert-Template-OID", (unsigned __int16 ***)&v21);
      if ( v15 )
      {
        CSPrintErrorLineFileData2(*((const unsigned __int16 **)v12 + 1), 0xB910328u, v15, 0);
      }
      else
      {
        v9 = (unsigned int)v21;
        if ( !v21 )
          goto LABEL_21;
        if ( *v21 && !_wcsicmp(*v21, *a2) )
          v14 = 1;
      }
    }
    else if ( !(unsigned int)mylstrcmpNLSub(*((PCNZWCH *)v12 + 1), *a2, -1, 1) )
    {
      v14 = 1;
    }
    v9 = (unsigned int)v21;
    if ( v21 )
    {
      CAFreeCertTypeProperty(v12);
      v21 = 0;
    }
LABEL_21:
    if ( v14 )
    {
      if ( v13 )
        *((_QWORD *)v13 + 19) = *((_QWORD *)v12 + 19);
      else
        v11 = (CCertTypeInfo *)*((_QWORD *)v12 + 19);
      *((_QWORD *)v12 + 19) = 0;
      v16 = v12;
LABEL_34:
      CCertTypeInfo::_Append(a6, v16);
LABEL_35:
      ++a2;
      goto LABEL_6;
    }
    v13 = v12;
    v12 = (CCertTypeInfo *)*((_QWORD *)v12 + 19);
  }
  if ( (a3 & 0x4000) == 0 )
    goto LABEL_35;
  v17 = (CCertTypeInfo *)operator new(0xC0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v17 )
    v18 = CCertTypeInfo::CCertTypeInfo(v17, 0);
  else
    v18 = 0;
  v22[0] = (struct CCertTypeInfo *)*a2;
  v22[1] = 0;
  if ( v18 )
  {
    v8 = CCertTypeInfo::SetProperty(v18, L"cn", (unsigned __int16 **)v22);
    if ( !v8 )
    {
      v16 = v18;
      goto LABEL_34;
    }
    CCertTypeInfo::`scalar deleting destructor'(v18, v19);
    CSPrintErrorLineFileData2((const unsigned __int16 *)v22[0], 0xBD10328u, v8, 0);
  }
  else
  {
    v8 = -2147024882;
    CSPrintErrorLineFile(0xBC60328u, -2147024882);
  }
LABEL_39:
  if ( v11 )
    CCertTypeInfo::`scalar deleting destructor'(v11, v9);
  if ( v8 )
  {
LABEL_42:
    if ( *a6 )
    {
      CCertTypeInfo::`scalar deleting destructor'(*a6, v9);
      *a6 = 0;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18003211c  push    rbp
0x18003211e  push    rbx
0x18003211f  push    rsi
0x180032120  push    rdi
0x180032121  push    r12
0x180032123  push    r13
0x180032125  push    r14
0x180032127  push    r15
0x180032129  mov     rbp, rsp
0x18003212c  sub     rsp, 58h
0x180032130  mov     eax, r9d
0x180032133  mov     r12d, r8d
0x180032136  mov     r14, rdx
0x180032139  mov     [rbp+var_20], 0
0x180032141  mov     [rbp+var_28], 0
0x180032149  mov     r15, [rbp+arg_28]
0x18003214d  test    r15, r15
0x180032150  jnz     short loc_180032168
0x180032152  mov     ebx, 80004003h
0x180032157  mov     edx, ebx; int
0x180032159  mov     ecx, 0B740328h; unsigned int
0x18003215e  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180032163  jmp     loc_180032352
0x180032168  mov     qword ptr [r15], 0
0x18003216f  lea     rdx, [rbp+var_20]
0x180032173  mov     [rsp+58h+var_38], rdx; struct CCertTypeInfo **
0x180032178  mov     r9d, [rbp+arg_20]; unsigned int
0x18003217c  mov     r8d, eax; unsigned int
0x18003217f  mov     edx, r12d; unsigned int
0x180032182  call    ?_EnumFromDS@CCertTypeInfo@@KAJPEAUldap@@KKKPEAPEAV1@@Z; CCertTypeInfo::_EnumFromDS(ldap *,ulong,ulong,ulong,CCertTypeInfo * *)
0x180032187  mov     ebx, eax
0x180032189  test    eax, eax
0x18003218b  jz      short loc_1800321A2
0x18003218d  mov     edx, eax; int
0x18003218f  mov     ecx, 0B7F0328h; unsigned int
0x180032194  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180032199  mov     rsi, [rbp+var_20]
0x18003219d  jmp     loc_180032341
0x1800321a2  mov     eax, 1
0x1800321a7  mov     rsi, [rbp+var_20]
0x1800321ab  test    r14, r14
0x1800321ae  jz      loc_18003233F
0x1800321b4  cmp     qword ptr [r14], 0
0x1800321b8  jz      loc_18003233F
0x1800321be  mov     rbx, rsi
0x1800321c1  xor     r13d, r13d
0x1800321c4  xor     edi, edi
0x1800321c6  test    rbx, rbx
0x1800321c9  jz      loc_180032296
0x1800321cf  bt      r12d, 9
0x1800321d4  jnb     short loc_180032226
0x1800321d6  lea     r8, [rbp+var_28]
0x1800321da  lea     rdx, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x1800321e1  mov     rcx, rbx
0x1800321e4  call    CAGetCertTypePropertyEx
0x1800321e9  test    eax, eax
0x1800321eb  jz      short loc_180032203
0x1800321ed  xor     r9d, r9d; int
0x1800321f0  mov     r8d, eax; int
0x1800321f3  mov     edx, 0B910328h; unsigned int
0x1800321f8  mov     rcx, [rbx+8]; unsigned __int16 *
0x1800321fc  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x180032201  jmp     short loc_180032243
0x180032203  mov     rdx, [rbp+var_28]
0x180032207  test    rdx, rdx
0x18003220a  jz      short loc_18003225C
0x18003220c  mov     rcx, [rdx]; String1
0x18003220f  test    rcx, rcx
0x180032212  jz      short loc_180032243
0x180032214  mov     rdx, [r14]; String2
0x180032217  call    cs:__imp__wcsicmp
0x18003221d  test    eax, eax
0x18003221f  jnz     short loc_180032243
0x180032221  lea     edi, [rax+1]
0x180032224  jmp     short loc_180032243
0x180032226  mov     r9b, al; bool
0x180032229  or      r8d, 0FFFFFFFFh; int
0x18003222d  mov     rdx, [r14]; unsigned __int16 *
0x180032230  mov     rcx, [rbx+8]; lpString1
0x180032234  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180032239  test    eax, eax
0x18003223b  mov     eax, 1
0x180032240  cmovz   edi, eax
0x180032243  mov     rdx, [rbp+var_28]
0x180032247  test    rdx, rdx
0x18003224a  jz      short loc_18003225C
0x18003224c  mov     rcx, rbx
0x18003224f  call    CAFreeCertTypeProperty
0x180032254  mov     [rbp+var_28], 0
0x18003225c  mov     rax, [rbx+98h]
0x180032263  test    edi, edi
0x180032265  jnz     short loc_180032275
0x180032267  mov     r13, rbx
0x18003226a  mov     rbx, rax
0x18003226d  lea     eax, [rdi+1]
0x180032270  jmp     loc_1800321C6
0x180032275  test    r13, r13
0x180032278  jz      short loc_180032283
0x18003227a  mov     [r13+98h], rax
0x180032281  jmp     short loc_180032286
0x180032283  mov     rsi, rax
0x180032286  mov     qword ptr [rbx+98h], 0
0x180032291  mov     rdx, rbx
0x180032294  jmp     short loc_1800322F8
0x180032296  bt      r12d, 0Eh
0x18003229b  jnb     short loc_180032305
0x18003229d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800322a4  mov     ecx, 0C0h; unsigned __int64
0x1800322a9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800322ae  mov     [rbp+arg_28], rax
0x1800322b2  test    rax, rax
0x1800322b5  jz      short loc_1800322C6
0x1800322b7  xor     edx, edx; int
0x1800322b9  mov     rcx, rax; this
0x1800322bc  call    ??0CCertTypeInfo@@QEAA@H@Z; CCertTypeInfo::CCertTypeInfo(int)
0x1800322c1  mov     rdi, rax
0x1800322c4  jmp     short loc_1800322C8
0x1800322c6  xor     edi, edi
0x1800322c8  mov     rax, [r14]
0x1800322cb  mov     [rbp+var_20], rax
0x1800322cf  mov     [rbp+var_18], 0
0x1800322d7  test    rdi, rdi
0x1800322da  jz      short loc_18003232C
0x1800322dc  lea     r8, [rbp+var_20]; unsigned __int16 **
0x1800322e0  lea     rdx, aCn_1; "cn"
0x1800322e7  mov     rcx, rdi; this
0x1800322ea  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x1800322ef  mov     ebx, eax
0x1800322f1  test    eax, eax
0x1800322f3  jnz     short loc_18003230E
0x1800322f5  mov     rdx, rdi; struct CCertTypeInfo *
0x1800322f8  mov     rcx, r15; struct CCertTypeInfo **
0x1800322fb  call    ?_Append@CCertTypeInfo@@SAPEAV1@PEAPEAV1@PEAV1@@Z; CCertTypeInfo::_Append(CCertTypeInfo * *,CCertTypeInfo *)
0x180032300  mov     eax, 1
0x180032305  add     r14, 8
0x180032309  jmp     loc_1800321AB
0x18003230e  mov     rcx, rdi; this
0x180032311  call    ??_GCCertTypeInfo@@QEAAPEAXI@Z; CCertTypeInfo::`scalar deleting destructor'(uint)
0x180032316  xor     r9d, r9d; int
0x180032319  mov     r8d, ebx; int
0x18003231c  mov     edx, 0BD10328h; unsigned int
0x180032321  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x180032325  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18003232a  jmp     short loc_180032341
0x18003232c  mov     ebx, 8007000Eh
0x180032331  mov     edx, ebx; int
0x180032333  mov     ecx, 0BC60328h; unsigned int
0x180032338  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18003233d  jmp     short loc_180032341
0x18003233f  xor     ebx, ebx
0x180032341  test    rsi, rsi
0x180032344  jz      short loc_18003234E
0x180032346  mov     rcx, rsi; this
0x180032349  call    ??_GCCertTypeInfo@@QEAAPEAXI@Z; CCertTypeInfo::`scalar deleting destructor'(uint)
0x18003234e  test    ebx, ebx
0x180032350  jz      short loc_180032366
0x180032352  mov     rcx, [r15]; this
0x180032355  test    rcx, rcx
0x180032358  jz      short loc_180032366
0x18003235a  call    ??_GCCertTypeInfo@@QEAAPEAXI@Z; CCertTypeInfo::`scalar deleting destructor'(uint)
0x18003235f  mov     qword ptr [r15], 0
0x180032366  mov     eax, ebx
0x180032368  add     rsp, 58h
0x18003236c  pop     r15
0x18003236e  pop     r14
0x180032370  pop     r13
0x180032372  pop     r12
0x180032374  pop     rdi
0x180032375  pop     rsi
0x180032376  pop     rbx
0x180032377  pop     rbp
0x180032378  retn
```
