# CIssuanceLicense::ParseDescriptor(CDRMLicense *)

- ea: `0x180013630`
- end: `0x180013a01`
- name: `?ParseDescriptor@CIssuanceLicense@@AEAAJPEAVCDRMLicense@@@Z`
- size: `977`
- prototype: `__int64 __fastcall(CIssuanceLicense *__hidden this, struct CDRMLicense *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x180013d80`
- `0x18001513c`

## callees

- `0x180001284`
- `0x180001290`
- `0x180002cd8`
- `0x180013630`
- `0x180015ef8`
- `0x1800172d4`
- `0x18003b3b8`
- `0x18003b55c`
- `0x18003d994`
- `0x18003daac`
- `0x18005bd72`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800138e3`
- `msvcrt!_wtoi` at `0x1800138e3`
- `msvcrt!wcsstr` at `0x180013720`
- `msvcrt!wcsstr` at `0x18001373d`
- `msvcrt!wcsstr` at `0x1800137aa`
- `msvcrt!wcsstr` at `0x1800137c7`
- `msvcrt!wcsstr` at `0x18001383c`
- `msvcrt!wcsstr` at `0x180013720`
- `msvcrt!wcsstr` at `0x18001373d`
- `msvcrt!wcsstr` at `0x1800137aa`
- `msvcrt!wcsstr` at `0x1800137c7`
- `msvcrt!wcsstr` at `0x18001383c`

## pseudocode

```c
__int64 __fastcall CIssuanceLicense::ParseDescriptor(CIssuanceLicense *this, struct CDRMLicense *a2)
{
  void *v3; // rcx
  unsigned __int16 *v4; // r14
  unsigned __int16 *v5; // rsi
  unsigned __int16 *v6; // rdi
  void *v7; // r15
  int LicenseID; // ebx
  int LicenseName; // eax
  wchar_t **v11; // r8
  wchar_t *v12; // rdi
  wchar_t *v13; // rax
  const unsigned __int16 *v14; // rbx
  wchar_t *v15; // rax
  unsigned __int64 v16; // rsi
  unsigned __int16 *v17; // rax
  wchar_t *v18; // rax
  const unsigned __int16 *v19; // rbx
  wchar_t *v20; // rax
  unsigned __int64 v21; // r12
  unsigned __int16 *v22; // rax
  wchar_t *v23; // rax
  const unsigned __int16 *v24; // r12
  unsigned __int64 v25; // rbx
  unsigned __int16 *v26; // rax
  unsigned __int16 v27; // ax
  unsigned __int16 *v28; // r12
  wchar_t **v29; // r8
  void *Block; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v32; // [rsp+38h] [rbp-18h] BYREF
  wchar_t *String; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v34; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v36; // [rsp+A0h] [rbp+50h] BYREF
  unsigned __int16 *v37; // [rsp+A8h] [rbp+58h] BYREF

  v3 = (void *)*((_QWORD *)this + 97);
  v4 = 0;
  v32 = 0;
  v5 = 0;
  v6 = 0;
  Block = 0;
  v7 = 0;
  v37 = 0;
  String = 0;
  v34 = 0;
  operator delete(v3);
  *((_QWORD *)this + 97) = 0;
  LicenseID = CDRMLicense::GetLicenseID(a2, &v34, (unsigned __int16 **)this + 97);
  if ( (int)(LicenseID + 0x80000000) >= 0 && LicenseID != -2147168490 )
    goto LABEL_31;
  LicenseName = CDRMLicense::GetLicenseName(a2, &v32);
  LicenseID = LicenseName;
  if ( LicenseName != -2147168490 )
  {
    if ( LicenseName < 0 )
      goto LABEL_31;
    LicenseID = UnescapeXML(v32, &String, &v36);
    if ( LicenseID < 0 )
      goto LABEL_31;
    v12 = wcstok_mvcrt_legacy_two_parameter_form(String, L";", v11);
    do
    {
      if ( v12 && *v12 == 10 )
        ++v12;
      v13 = wcsstr(v12, L"LCID ");
      if ( !v13 )
        break;
      v14 = v13 + 5;
      v15 = wcsstr(v13 + 5, L":");
      if ( !v15 )
      {
        LicenseID = -2147168512;
        goto LABEL_28;
      }
      v16 = v15 - v14 + 1;
      v17 = (unsigned __int16 *)operator new[](saturated_mul(v16, 2u));
      v4 = v17;
      if ( !v17 )
      {
        LicenseID = -2147024882;
        goto LABEL_29;
      }
      memset_0(v17, 0, 2 * v16);
      LicenseID = StringCchCopyNW(v4, v16, v14, v16 - 1);
      if ( LicenseID < 0 )
        goto LABEL_29;
      v18 = wcsstr(v12, L"NAME ");
      if ( !v18 || (v19 = v18 + 5, (v20 = wcsstr(v18 + 5, L":")) == 0) )
      {
        LicenseID = -2147168512;
        goto LABEL_29;
      }
      v21 = v20 - v19 + 1;
      v22 = (unsigned __int16 *)operator new[](saturated_mul(v21, 2u));
      v5 = v22;
      if ( !v22 )
      {
        LicenseID = -2147024882;
        goto LABEL_30;
      }
      memset_0(v22, 0, 2 * v21);
      LicenseID = StringCchCopyNW(v5, v21, v19, v21 - 1);
      if ( LicenseID < 0 )
        goto LABEL_30;
      v23 = wcsstr(v12, L"DESCRIPTION ");
      if ( !v23 )
      {
        LicenseID = -2147168512;
        goto LABEL_30;
      }
      v24 = v23 + 12;
      v25 = -1;
      do
        ++v25;
      while ( v24[v25] );
      v26 = (unsigned __int16 *)operator new[](saturated_mul(v25 + 1, 2u));
      v6 = v26;
      if ( !v26 )
      {
        LicenseID = -2147024882;
        goto LABEL_31;
      }
      memset_0(v26, 0, 2 * (v25 + 1));
      LicenseID = StringCchCopyNW(v6, v25 + 1, v24, v25);
      if ( LicenseID < 0 )
        goto LABEL_31;
      LicenseID = EscapeXML(v5, (unsigned __int16 **)&Block);
      if ( LicenseID < 0 || (LicenseID = EscapeXML(v6, &v37), LicenseID < 0) )
      {
        v7 = Block;
        goto LABEL_31;
      }
      v27 = _wtoi(v4);
      v7 = Block;
      v28 = v37;
      LicenseID = CIssuanceLicense::SetNameAndDescription(this, 0, v27, (unsigned __int16 *)Block, v37);
      if ( LicenseID < 0 )
        goto LABEL_32;
      operator delete(v4);
      operator delete(v5);
      operator delete(v6);
      operator delete(v7);
      Block = 0;
      v7 = 0;
      operator delete(v28);
      v37 = 0;
      v12 = wcstok_mvcrt_legacy_two_parameter_form(0, L";", v29);
    }
    while ( v12 );
  }
  LicenseID = 0;
LABEL_28:
  v4 = 0;
LABEL_29:
  v5 = 0;
LABEL_30:
  v6 = 0;
LABEL_31:
  v28 = v37;
LABEL_32:
  operator delete(v32);
  operator delete(v4);
  operator delete(v5);
  operator delete(v6);
  operator delete(v7);
  operator delete(v28);
  operator delete(String);
  operator delete(v34);
  return (unsigned int)LicenseID;
}

```

## disassembly

```asm
0x180013630  mov     [rsp-38h+arg_8], rbx
0x180013635  mov     [rsp-38h+arg_0], rcx
0x18001363a  push    rbp
0x18001363b  push    rsi
0x18001363c  push    rdi
0x18001363d  push    r12
0x18001363f  push    r13
0x180013641  push    r14
0x180013643  push    r15
0x180013645  mov     rbp, rsp
0x180013648  sub     rsp, 50h
0x18001364c  xor     r13d, r13d
0x18001364f  mov     rbx, rcx
0x180013652  mov     rcx, [rcx+308h]; Block
0x180013659  mov     r14d, r13d
0x18001365c  mov     [rbp+var_18], r13
0x180013660  mov     esi, r13d
0x180013663  mov     edi, r13d
0x180013666  mov     [rbp+Block], r13
0x18001366a  mov     r15d, r13d
0x18001366d  mov     [rbp+arg_18], r13
0x180013671  mov     [rbp+String], r13
0x180013675  mov     r12, rdx
0x180013678  mov     [rbp+var_8], r13
0x18001367c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013681  lea     r8, [rbx+308h]; unsigned __int16 **
0x180013688  mov     [rbx+308h], r13
0x18001368f  lea     rdx, [rbp+var_8]; unsigned __int16 **
0x180013693  mov     rcx, r12; this
0x180013696  call    ?GetLicenseID@CDRMLicense@@QEAAJPEAPEAG0@Z; CDRMLicense::GetLicenseID(ushort * *,ushort * *)
0x18001369b  mov     ecx, 80000000h
0x1800136a0  mov     ebx, eax
0x1800136a2  add     eax, ecx
0x1800136a4  test    ecx, eax
0x1800136a6  jnz     short loc_1800136B4
0x1800136a8  cmp     ebx, 8004CF16h
0x1800136ae  jnz     loc_180013967
0x1800136b4  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x1800136b8  mov     rcx, r12; this
0x1800136bb  call    ?GetLicenseName@CDRMLicense@@QEAAJPEAPEAG@Z; CDRMLicense::GetLicenseName(ushort * *)
0x1800136c0  mov     ebx, eax
0x1800136c2  cmp     eax, 8004CF16h
0x1800136c7  jz      loc_18001395B
0x1800136cd  test    eax, eax
0x1800136cf  js      loc_180013967
0x1800136d5  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x1800136d9  lea     r8, [rbp+arg_10]; unsigned int *
0x1800136dd  lea     rdx, [rbp+String]; unsigned __int16 **
0x1800136e1  call    ?UnescapeXML@@YAJPEAGPEAPEAGPEAI@Z; UnescapeXML(ushort *,ushort * *,uint *)
0x1800136e6  mov     ebx, eax
0x1800136e8  test    eax, eax
0x1800136ea  js      loc_180013967
0x1800136f0  mov     rcx, [rbp+String]; String
0x1800136f4  lea     rdx, Delimiter; ";"
0x1800136fb  call    wcstok_mvcrt_legacy_two_parameter_form
0x180013700  mov     rdi, rax
0x180013703  or      r14, 0FFFFFFFFFFFFFFFFh
0x180013707  test    rdi, rdi
0x18001370a  jz      short loc_180013716
0x18001370c  cmp     word ptr [rdi], 0Ah
0x180013710  jnz     short loc_180013716
0x180013712  add     rdi, 2
0x180013716  lea     rdx, aLcid; "LCID "
0x18001371d  mov     rcx, rdi; Str
0x180013720  call    cs:__imp_wcsstr
0x180013726  test    rax, rax
0x180013729  jz      loc_18001395B
0x18001372f  lea     rbx, [rax+0Ah]
0x180013733  mov     rcx, rbx; Str
0x180013736  lea     rdx, asc_18006543C; ":"
0x18001373d  call    cs:__imp_wcsstr
0x180013743  test    rax, rax
0x180013746  jz      loc_1800139F7
0x18001374c  sub     rax, rbx
0x18001374f  sar     rax, 1
0x180013752  lea     rsi, [rax+1]
0x180013756  mov     eax, 2
0x18001375b  mul     rsi
0x18001375e  cmovb   rax, r14
0x180013762  mov     rcx, rax; unsigned __int64
0x180013765  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001376a  mov     r14, rax
0x18001376d  test    rax, rax
0x180013770  jz      loc_1800139ED
0x180013776  lea     r8, [rsi+rsi]; Size
0x18001377a  xor     edx, edx; Val
0x18001377c  mov     rcx, rax; void *
0x18001377f  call    memset_0
0x180013784  lea     r9, [rsi-1]; unsigned __int64
0x180013788  mov     r8, rbx; unsigned __int16 *
0x18001378b  mov     rdx, rsi; unsigned __int64
0x18001378e  mov     rcx, r14; unsigned __int16 *
0x180013791  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180013796  mov     ebx, eax
0x180013798  test    eax, eax
0x18001379a  js      loc_180013961
0x1800137a0  lea     rdx, aName; "NAME "
0x1800137a7  mov     rcx, rdi; Str
0x1800137aa  call    cs:__imp_wcsstr
0x1800137b0  test    rax, rax
0x1800137b3  jz      loc_1800139E3
0x1800137b9  lea     rbx, [rax+0Ah]
0x1800137bd  mov     rcx, rbx; Str
0x1800137c0  lea     rdx, asc_18006543C; ":"
0x1800137c7  call    cs:__imp_wcsstr
0x1800137cd  test    rax, rax
0x1800137d0  jz      loc_1800139E3
0x1800137d6  sub     rax, rbx
0x1800137d9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800137e0  sar     rax, 1
0x1800137e3  lea     r12, [rax+1]
0x1800137e7  mov     eax, 2
0x1800137ec  mul     r12
0x1800137ef  cmovb   rax, rcx
0x1800137f3  mov     rcx, rax; unsigned __int64
0x1800137f6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800137fb  mov     rsi, rax
0x1800137fe  test    rax, rax
0x180013801  jz      loc_1800139DC
0x180013807  lea     r8, [r12+r12]; Size
0x18001380b  xor     edx, edx; Val
0x18001380d  mov     rcx, rax; void *
0x180013810  call    memset_0
0x180013815  lea     r9, [r12-1]; unsigned __int64
0x18001381a  mov     r8, rbx; unsigned __int16 *
0x18001381d  mov     rdx, r12; unsigned __int64
0x180013820  mov     rcx, rsi; unsigned __int16 *
0x180013823  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180013828  mov     ebx, eax
0x18001382a  test    eax, eax
0x18001382c  js      loc_180013964
0x180013832  lea     rdx, aDescription; "DESCRIPTION "
0x180013839  mov     rcx, rdi; Str
0x18001383c  call    cs:__imp_wcsstr
0x180013842  test    rax, rax
0x180013845  jz      loc_1800139D5
0x18001384b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001384f  lea     r12, [rax+18h]
0x180013853  mov     rbx, rcx
0x180013856  inc     rbx
0x180013859  cmp     [r12+rbx*2], r13w
0x18001385e  jnz     short loc_180013856
0x180013860  lea     r13, [rbx+1]
0x180013864  mov     eax, 2
0x180013869  mul     r13
0x18001386c  cmovb   rax, rcx
0x180013870  mov     rcx, rax; unsigned __int64
0x180013873  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180013878  mov     rdi, rax
0x18001387b  test    rax, rax
0x18001387e  jz      loc_1800139CE
0x180013884  lea     r8, ds:0[r13*2]; Size
0x18001388c  xor     edx, edx; Val
0x18001388e  mov     rcx, rax; void *
0x180013891  call    memset_0
0x180013896  mov     r9, rbx; unsigned __int64
0x180013899  mov     r8, r12; unsigned __int16 *
0x18001389c  mov     rdx, r13; unsigned __int64
0x18001389f  mov     rcx, rdi; unsigned __int16 *
0x1800138a2  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800138a7  xor     r13d, r13d
0x1800138aa  mov     ebx, eax
0x1800138ac  test    eax, eax
0x1800138ae  js      loc_180013967
0x1800138b4  lea     rdx, [rbp+Block]; unsigned __int16 **
0x1800138b8  mov     rcx, rsi; unsigned __int16 *
0x1800138bb  call    ?EscapeXML@@YAJPEAGPEAPEAG@Z; EscapeXML(ushort *,ushort * *)
0x1800138c0  mov     ebx, eax
0x1800138c2  test    eax, eax
0x1800138c4  js      loc_1800139C8
0x1800138ca  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x1800138ce  mov     rcx, rdi; unsigned __int16 *
0x1800138d1  call    ?EscapeXML@@YAJPEAGPEAPEAG@Z; EscapeXML(ushort *,ushort * *)
0x1800138d6  mov     ebx, eax
0x1800138d8  test    eax, eax
0x1800138da  js      loc_1800139C8
0x1800138e0  mov     rcx, r14; String
0x1800138e3  call    cs:__imp__wtoi
0x1800138e9  mov     r15, [rbp+Block]
0x1800138ed  xor     edx, edx; int
0x1800138ef  mov     r12, [rbp+arg_18]
0x1800138f3  mov     r9, r15; unsigned __int16 *
0x1800138f6  mov     rcx, [rbp+arg_0]; this
0x1800138fa  movzx   r8d, ax; unsigned int
0x1800138fe  mov     [rsp+50h+var_30], r12; unsigned __int16 *
0x180013903  call    ?SetNameAndDescription@CIssuanceLicense@@QEAAJHIPEAG0@Z; CIssuanceLicense::SetNameAndDescription(int,uint,ushort *,ushort *)
0x180013908  mov     ebx, eax
0x18001390a  test    eax, eax
0x18001390c  js      short loc_18001396B
0x18001390e  mov     rcx, r14; Block
0x180013911  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013916  mov     rcx, rsi; Block
0x180013919  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001391e  mov     rcx, rdi; Block
0x180013921  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013926  mov     rcx, r15; Block
0x180013929  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001392e  mov     rcx, r12; Block
0x180013931  mov     [rbp+Block], r13
0x180013935  mov     r15d, r13d
0x180013938  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001393d  lea     rdx, Delimiter; ";"
0x180013944  mov     [rbp+arg_18], r13
0x180013948  xor     ecx, ecx; String
0x18001394a  call    wcstok_mvcrt_legacy_two_parameter_form
0x18001394f  mov     rdi, rax
0x180013952  test    rax, rax
0x180013955  jnz     loc_180013703
0x18001395b  mov     ebx, r13d
0x18001395e  mov     r14, r13
0x180013961  mov     rsi, r13
0x180013964  mov     rdi, r13
0x180013967  mov     r12, [rbp+arg_18]
0x18001396b  mov     rcx, [rbp+var_18]; Block
0x18001396f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013974  mov     rcx, r14; Block
0x180013977  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001397c  mov     rcx, rsi; Block
0x18001397f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013984  mov     rcx, rdi; Block
0x180013987  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001398c  mov     rcx, r15; Block
0x18001398f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180013994  mov     rcx, r12; Block
0x180013997  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001399c  mov     rcx, [rbp+String]; Block
0x1800139a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800139a5  mov     rcx, [rbp+var_8]; Block
0x1800139a9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800139ae  mov     eax, ebx
0x1800139b0  mov     rbx, [rsp+50h+arg_8]
0x1800139b8  add     rsp, 50h
0x1800139bc  pop     r15
0x1800139be  pop     r14
0x1800139c0  pop     r13
0x1800139c2  pop     r12
0x1800139c4  pop     rdi
0x1800139c5  pop     rsi
0x1800139c6  pop     rbp
0x1800139c7  retn
0x1800139c8  mov     r15, [rbp+Block]
0x1800139cc  jmp     short loc_180013967
0x1800139ce  mov     ebx, 8007000Eh
0x1800139d3  jmp     short loc_180013967
0x1800139d5  mov     ebx, 8004CF00h
0x1800139da  jmp     short loc_180013964
0x1800139dc  mov     ebx, 8007000Eh
0x1800139e1  jmp     short loc_180013964
0x1800139e3  mov     ebx, 8004CF00h
0x1800139e8  jmp     loc_180013961
0x1800139ed  mov     ebx, 8007000Eh
0x1800139f2  jmp     loc_180013961
0x1800139f7  mov     ebx, 8004CF00h
0x1800139fc  jmp     loc_18001395E
```
