# CIssuanceLicense::GenerateNameAndDescriptionXML(uint *,ushort * *)

- ea: `0x18000b5b4`
- end: `0x18000ba16`
- name: `?GenerateNameAndDescriptionXML@CIssuanceLicense@@AEAAJPEAIPEAPEAG@Z`
- size: `1122`
- prototype: `__int64 __fastcall(CIssuanceLicense *__hidden this, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x18000cd4c`

## callees

- `0x180001284`
- `0x180001290`
- `0x18000b5b4`
- `0x18000d5ec`
- `0x180017358`
- `0x18001ef30`
- `0x18001f2fc`
- `0x18001ff54`
- `0x18001ffd8`
- `0x180020080`
- `0x18005bd72`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b9e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b9e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b60a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b60a`

## string_xrefs

- `0x18000b61b`: `<DESCRIPTOR><OBJECT><ID type="MS-GUID">%s</ID><NAME>%s</NAME></OBJECT></DESCRIPTOR>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIssuanceLicense::GenerateNameAndDescriptionXML(
        CIssuanceLicense *this,
        unsigned int *a2,
        unsigned __int16 **a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  unsigned __int16 *v6; // r14
  int v7; // edi
  int v8; // r12d
  unsigned int i; // r13d
  CDRMCBase *v10; // rcx
  CNameValue *v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int Data; // eax
  CDRMCBase *v15; // rcx
  CDRMCBase *v16; // rcx
  __int64 v17; // r12
  __int64 v18; // rcx
  __int64 v19; // rax
  unsigned int v20; // eax
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // rsi
  unsigned int v23; // eax
  __int64 v24; // r13
  CDRMCBase *v25; // rcx
  CNameValue *v26; // r13
  __int64 v27; // rax
  __int64 v28; // rdi
  __int64 v29; // rsi
  unsigned int v30; // eax
  unsigned __int16 *v31; // rax
  unsigned __int16 *v32; // r9
  unsigned int v34; // [rsp+38h] [rbp-D0h]
  int v35; // [rsp+40h] [rbp-C8h]
  unsigned int v36; // [rsp+40h] [rbp-C8h]
  int v37; // [rsp+48h] [rbp-C0h]
  unsigned int v38; // [rsp+48h] [rbp-C0h]
  unsigned __int16 *Block; // [rsp+50h] [rbp-B8h]
  unsigned __int16 *v40; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int16 **v41; // [rsp+60h] [rbp-A8h]
  __int64 v42; // [rsp+68h] [rbp-A0h]
  unsigned int *v43; // [rsp+70h] [rbp-98h]
  __int64 v44; // [rsp+78h] [rbp-90h]
  char *v45; // [rsp+80h] [rbp-88h]
  unsigned __int16 v46[8]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v47; // [rsp+98h] [rbp-70h]
  __int128 v48; // [rsp+A8h] [rbp-60h]
  __int128 v49; // [rsp+B8h] [rbp-50h]
  wchar_t v50; // [rsp+C8h] [rbp-40h]
  unsigned __int16 v51[8]; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v52; // [rsp+E8h] [rbp-20h]
  __int128 v53; // [rsp+F8h] [rbp-10h]
  __int128 v54; // [rsp+108h] [rbp+0h]
  __int128 v55; // [rsp+118h] [rbp+10h]
  __int128 v56; // [rsp+128h] [rbp+20h]
  __int128 v57; // [rsp+138h] [rbp+30h]
  __int128 v58; // [rsp+148h] [rbp+40h]
  __int128 v59; // [rsp+158h] [rbp+50h]
  __int128 v60; // [rsp+168h] [rbp+60h]
  __int64 v61; // [rsp+178h] [rbp+70h]

  v44 = -2;
  v41 = a3;
  v43 = a2;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  v45 = (char *)this + 88;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  Block = 0;
  v6 = 0;
  *(_OWORD *)v51 = *(_OWORD *)L"<DESCRIPTOR><OBJECT><ID type=\"MS-GUID\">%s</ID><NAME>%s</NAME></OBJECT></DESCRIPTOR>";
  v52 = *(_OWORD *)L"TOR><OBJECT><ID type=\"MS-GUID\">%s</ID><NAME>%s</NAME></OBJECT></DESCRIPTOR>";
  v53 = *(_OWORD *)L"ECT><ID type=\"MS-GUID\">%s</ID><NAME>%s</NAME></OBJECT></DESCRIPTOR>";
  v54 = *(_OWORD *)L"type=\"MS-GUID\">%s</ID><NAME>%s</NAME></OBJECT></DESCRIPTOR>";
  v55 = *(_OWORD *)L"-GUID\">%s</ID><NAME>%s</NAME></OBJECT></DESCRIPTOR>";
  v56 = *(_OWORD *)L"s</ID><NAME>%s</NAME></OBJECT></DESCRIPTOR>";
  v57 = *(_OWORD *)L"AME>%s</NAME></OBJECT></DESCRIPTOR>";
  v58 = *(_OWORD *)L"NAME></OBJECT></DESCRIPTOR>";
  v59 = *(_OWORD *)L"BJECT></DESCRIPTOR>";
  v60 = *(_OWORD *)L"DESCRIPTOR>";
  v61 = *(_QWORD *)L"OR>";
  *(_OWORD *)v46 = *(_OWORD *)L"LCID %d:NAME %s:DESCRIPTION %s;\n";
  v47 = *(_OWORD *)L"NAME %s:DESCRIPTION %s;\n";
  v48 = *(_OWORD *)L"DESCRIPTION %s;\n";
  v49 = *(_OWORD *)L"ION %s;\n";
  v50 = aLcidDNameSDesc[32];
  v40 = 0;
  if ( a2 )
  {
    v7 = 0;
    v34 = *((_DWORD *)this + 46);
    *a2 = 0;
    if ( v34 )
    {
      v8 = 0;
      for ( i = 0; i < v34; ++i )
      {
        if ( i >= *((_DWORD *)this + 46) )
          goto LABEL_43;
        v10 = *(CDRMCBase **)(*((_QWORD *)this + 22) + 8LL * i);
        if ( !v10 )
          goto LABEL_44;
        CDRMCBase::AddRef(v10);
        v11 = *(CNameValue **)(*((_QWORD *)this + 22) + 8LL * i);
        if ( !v11 )
          goto LABEL_44;
        if ( !(unsigned int)CDRMCBase::IsDeleted(v11) )
        {
          v12 = -1;
          do
            ++v12;
          while ( *(_WORD *)(*((_QWORD *)v11 + 16) + 2 * v12) );
          v37 = v12;
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)(*((_QWORD *)v11 + 17) + 2 * v13) );
          v35 = v13;
          Data = CNameValue::GetData(v11);
          v8 += v35 + v37 + CDRMCBase::UINT2STRLength(v15, Data) + 26;
        }
        CDRMCBase::Release(v11);
      }
      if ( v8 )
      {
        if ( *((_QWORD *)this + 97) || (v7 = CDRMCBase::CreateGuidString(v16, &v40), v7 >= 0) )
        {
          v17 = (unsigned int)(v8 + 1);
          v18 = *((_QWORD *)this + 97);
          v19 = -1;
          if ( v18 )
          {
            do
              ++v19;
            while ( *(_WORD *)(v18 + 2 * v19) );
          }
          else
          {
            do
              ++v19;
            while ( v40[v19] );
          }
          v20 = v17 + v19 + 79;
          v38 = v20;
          if ( !v41 )
          {
LABEL_42:
            *v43 = v20;
            v6 = 0;
            goto LABEL_44;
          }
          v21 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)v17, 2u));
          v22 = v21;
          Block = v21;
          if ( !v21 )
          {
LABEL_24:
            v7 = -2147024882;
            goto LABEL_44;
          }
          memset_0(v21, 0, 2 * v17);
          v23 = 0;
          v36 = 0;
          while ( v23 < *((_DWORD *)this + 46) )
          {
            v24 = v23;
            v25 = *(CDRMCBase **)(*((_QWORD *)this + 22) + 8LL * v23);
            if ( !v25 )
              goto LABEL_44;
            CDRMCBase::AddRef(v25);
            v26 = *(CNameValue **)(*((_QWORD *)this + 22) + 8 * v24);
            if ( !v26 )
              goto LABEL_44;
            if ( !(unsigned int)CDRMCBase::IsDeleted(v26) )
            {
              v27 = -1;
              do
                ++v27;
              while ( v22[v27] );
              v42 = v27;
              v28 = *((_QWORD *)v26 + 17);
              v29 = *((_QWORD *)v26 + 16);
              v30 = CNameValue::GetData(v26);
              v7 = StringCchPrintfW(&Block[(unsigned int)v42], (unsigned int)(v17 - v42), v46, v30, v29, v28);
              if ( v7 < 0 )
              {
                CDRMCBase::Release(v26);
                goto LABEL_44;
              }
              v22 = Block;
            }
            CDRMCBase::Release(v26);
            v23 = v36 + 1;
            v36 = v23;
            if ( v23 >= v34 )
            {
              v31 = (unsigned __int16 *)operator new[](saturated_mul(v38, 2u));
              v6 = v31;
              if ( !v31 )
                goto LABEL_24;
              memset_0(v31, 0, 2LL * v38);
              v32 = v40;
              if ( *((_QWORD *)this + 97) )
                v32 = (unsigned __int16 *)*((_QWORD *)this + 97);
              v7 = StringCchPrintfW(v6, v38, v51, v32, v22);
              if ( v7 >= 0 )
              {
                *v41 = v6;
                v20 = v38;
                goto LABEL_42;
              }
              goto LABEL_44;
            }
          }
LABEL_43:
          v6 = 0;
        }
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
LABEL_44:
  operator delete(Block);
  operator delete(v6);
  operator delete(v40);
  LeaveCriticalSection(v5);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b5b4  mov     rax, rsp
0x18000b5b7  push    rbp
0x18000b5b8  push    rsi
0x18000b5b9  push    rdi
0x18000b5ba  push    r12
0x18000b5bc  push    r13
0x18000b5be  push    r14
0x18000b5c0  push    r15
0x18000b5c2  lea     rbp, [rax-0C8h]
0x18000b5c9  sub     rsp, 190h
0x18000b5d0  mov     [rsp+1C0h+var_150], 0FFFFFFFFFFFFFFFEh
0x18000b5d9  mov     [rax+20h], rbx
0x18000b5dd  mov     rax, cs:__security_cookie
0x18000b5e4  xor     rax, rsp
0x18000b5e7  mov     [rbp+0C0h+var_40], rax
0x18000b5ee  mov     [rsp+1C0h+var_168], r8
0x18000b5f3  mov     rsi, rdx
0x18000b5f6  mov     [rsp+1C0h+var_158], rdx
0x18000b5fb  mov     r15, rcx
0x18000b5fe  lea     rbx, [rcx+58h]
0x18000b602  mov     [rsp+1C0h+var_148], rbx
0x18000b607  mov     rcx, rbx; lpCriticalSection
0x18000b60a  call    cs:__imp_EnterCriticalSection
0x18000b610  nop
0x18000b611  xor     edx, edx
0x18000b613  mov     [rsp+1C0h+Block], rdx
0x18000b618  mov     r14d, edx
0x18000b61b  movaps  xmm0, xmmword ptr cs:aDescriptorObje; "<DESCRIPTOR><OBJECT><ID type=\"MS-GUID"...
0x18000b622  movups  xmmword ptr [rbp+0C0h+var_F0], xmm0
0x18000b626  movaps  xmm1, xmmword ptr cs:aDescriptorObje+10h; "TOR><OBJECT><ID type=\"MS-GUID\">%s</ID"...
0x18000b62d  movups  [rbp+0C0h+var_E0], xmm1
0x18000b631  movaps  xmm0, xmmword ptr cs:aDescriptorObje+20h; "ECT><ID type=\"MS-GUID\">%s</ID><NAME>%"...
0x18000b638  movups  [rbp+0C0h+var_D0], xmm0
0x18000b63c  movaps  xmm1, xmmword ptr cs:aDescriptorObje+30h; "type=\"MS-GUID\">%s</ID><NAME>%s</NAME>"...
0x18000b643  movups  [rbp+0C0h+var_C0], xmm1
0x18000b647  movaps  xmm0, xmmword ptr cs:aDescriptorObje+40h; "-GUID\">%s</ID><NAME>%s</NAME></OBJECT>"...
0x18000b64e  movups  [rbp+0C0h+var_B0], xmm0
0x18000b652  movaps  xmm1, xmmword ptr cs:aDescriptorObje+50h; "s</ID><NAME>%s</NAME></OBJECT></DESCRIP"...
0x18000b659  movups  [rbp+0C0h+var_A0], xmm1
0x18000b65d  movaps  xmm0, xmmword ptr cs:aDescriptorObje+60h; "AME>%s</NAME></OBJECT></DESCRIPTOR>"
0x18000b664  movups  [rbp+0C0h+var_90], xmm0
0x18000b668  movaps  xmm1, xmmword ptr cs:aDescriptorObje+70h; "NAME></OBJECT></DESCRIPTOR>"
0x18000b66f  movups  [rbp+0C0h+var_80], xmm1
0x18000b673  movaps  xmm0, xmmword ptr cs:aDescriptorObje+80h; "BJECT></DESCRIPTOR>"
0x18000b67a  movups  [rbp+0C0h+var_70], xmm0
0x18000b67e  movaps  xmm1, xmmword ptr cs:aDescriptorObje+90h; "DESCRIPTOR>"
0x18000b685  movups  [rbp+0C0h+var_60], xmm1
0x18000b689  mov     rax, qword ptr cs:aDescriptorObje+0A0h; "OR>"
0x18000b690  mov     [rbp+0C0h+var_50], rax
0x18000b694  movaps  xmm0, xmmword ptr cs:aLcidDNameSDesc; "LCID %d:NAME %s:DESCRIPTION %s;\n"
0x18000b69b  movaps  xmmword ptr [rbp+0C0h+var_140], xmm0
0x18000b69f  movaps  xmm1, xmmword ptr cs:aLcidDNameSDesc+10h; "NAME %s:DESCRIPTION %s;\n"
0x18000b6a6  movaps  [rbp+0C0h+var_130], xmm1
0x18000b6aa  movaps  xmm0, xmmword ptr cs:aLcidDNameSDesc+20h; "DESCRIPTION %s;\n"
0x18000b6b1  movaps  [rbp+0C0h+var_120], xmm0
0x18000b6b5  movaps  xmm1, xmmword ptr cs:aLcidDNameSDesc+30h; "ION %s;\n"
0x18000b6bc  movaps  [rbp+0C0h+var_110], xmm1
0x18000b6c0  movzx   eax, word ptr cs:aLcidDNameSDesc+40h; ""
0x18000b6c7  mov     [rbp+0C0h+var_100], ax
0x18000b6cb  mov     [rsp+1C0h+var_170], rdx
0x18000b6d0  test    rsi, rsi
0x18000b6d3  jnz     short loc_18000B6DF
0x18000b6d5  mov     edi, 80070057h
0x18000b6da  jmp     loc_18000B9C4
0x18000b6df  mov     edi, edx
0x18000b6e1  mov     eax, [r15+0B8h]
0x18000b6e8  mov     dword ptr [rsp+1C0h+var_190], eax
0x18000b6ec  mov     [rsi], edx
0x18000b6ee  test    eax, eax
0x18000b6f0  jz      loc_18000B9C4
0x18000b6f6  mov     r12d, edx
0x18000b6f9  mov     r13d, edx
0x18000b6fc  jmp     short loc_18000B700
0x18000b6fe  xor     edx, edx
0x18000b700  cmp     r13d, [r15+0B8h]
0x18000b707  jnb     loc_18000B9C1
0x18000b70d  mov     esi, r13d
0x18000b710  mov     rax, [r15+0B0h]
0x18000b717  mov     rcx, [rax+rsi*8]; this
0x18000b71b  test    rcx, rcx
0x18000b71e  jz      loc_18000B9C4
0x18000b724  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x18000b729  mov     rax, [r15+0B0h]
0x18000b730  mov     rsi, [rax+rsi*8]
0x18000b734  test    rsi, rsi
0x18000b737  jz      loc_18000B9C4
0x18000b73d  mov     rcx, rsi; this
0x18000b740  call    ?IsDeleted@CDRMCBase@@QEAAHXZ; CDRMCBase::IsDeleted(void)
0x18000b745  xor     edx, edx
0x18000b747  test    eax, eax
0x18000b749  jnz     short loc_18000B79C
0x18000b74b  mov     rcx, [rsi+80h]
0x18000b752  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b756  mov     rax, r8
0x18000b759  inc     rax
0x18000b75c  cmp     [rcx+rax*2], dx
0x18000b760  jnz     short loc_18000B759
0x18000b762  mov     [rsp+1C0h+var_180], rax
0x18000b767  mov     rcx, [rsi+88h]
0x18000b76e  mov     rax, r8
0x18000b771  inc     rax
0x18000b774  cmp     [rcx+rax*2], dx
0x18000b778  jnz     short loc_18000B771
0x18000b77a  mov     [rsp+1C0h+var_188], rax
0x18000b77f  mov     rcx, rsi; this
0x18000b782  call    ?GetData@CNameValue@@QEAAIXZ; CNameValue::GetData(void)
0x18000b787  mov     edx, eax; unsigned int
0x18000b789  call    ?UINT2STRLength@CDRMCBase@@QEAAII@Z; CDRMCBase::UINT2STRLength(uint)
0x18000b78e  add     eax, 1Ah
0x18000b791  add     eax, dword ptr [rsp+1C0h+var_180]
0x18000b795  add     eax, dword ptr [rsp+1C0h+var_188]
0x18000b799  add     r12d, eax
0x18000b79c  mov     rcx, rsi; this
0x18000b79f  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000b7a4  inc     r13d
0x18000b7a7  cmp     r13d, dword ptr [rsp+1C0h+var_190]
0x18000b7ac  jb      loc_18000B6FE
0x18000b7b2  xor     r13d, r13d
0x18000b7b5  test    r12d, r12d
0x18000b7b8  jz      loc_18000B9C4
0x18000b7be  cmp     [r15+308h], r13
0x18000b7c5  jnz     short loc_18000B7DB
0x18000b7c7  lea     rdx, [rsp+1C0h+var_170]; unsigned __int16 **
0x18000b7cc  call    ?CreateGuidString@CDRMCBase@@QEAAJPEAPEAG@Z; CDRMCBase::CreateGuidString(ushort * *)
0x18000b7d1  mov     edi, eax
0x18000b7d3  test    eax, eax
0x18000b7d5  js      loc_18000B9C4
0x18000b7db  inc     r12d
0x18000b7de  mov     rcx, [r15+308h]
0x18000b7e5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000b7e9  mov     rax, r8
0x18000b7ec  test    rcx, rcx
0x18000b7ef  jz      short loc_18000B7FD
0x18000b7f1  inc     rax
0x18000b7f4  cmp     [rcx+rax*2], r13w
0x18000b7f9  jnz     short loc_18000B7F1
0x18000b7fb  jmp     short loc_18000B80C
0x18000b7fd  mov     rcx, [rsp+1C0h+var_170]
0x18000b802  inc     rax
0x18000b805  cmp     [rcx+rax*2], r13w
0x18000b80a  jnz     short loc_18000B802
0x18000b80c  add     eax, 4Fh ; 'O'
0x18000b80f  add     eax, r12d
0x18000b812  mov     dword ptr [rsp+1C0h+var_180], eax
0x18000b816  cmp     [rsp+1C0h+var_168], r13
0x18000b81b  jz      loc_18000B9B5
0x18000b821  mov     r13d, r12d
0x18000b824  mov     eax, 2
0x18000b829  mul     r13
0x18000b82c  cmovb   rax, r8
0x18000b830  mov     rcx, rax; unsigned __int64
0x18000b833  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b838  mov     rsi, rax
0x18000b83b  mov     [rsp+1C0h+Block], rax
0x18000b840  test    rax, rax
0x18000b843  jnz     short loc_18000B84F
0x18000b845  mov     edi, 8007000Eh
0x18000b84a  jmp     loc_18000B9C4
0x18000b84f  lea     r8, ds:0[r12*2]; Size
0x18000b857  xor     edx, edx; Val
0x18000b859  mov     rcx, rax; void *
0x18000b85c  call    memset_0
0x18000b861  xor     edx, edx
0x18000b863  mov     eax, edx
0x18000b865  mov     dword ptr [rsp+1C0h+var_188], edx
0x18000b869  cmp     eax, [r15+0B8h]
0x18000b870  jnb     loc_18000B9C1
0x18000b876  mov     r13d, eax
0x18000b879  mov     rax, [r15+0B0h]
0x18000b880  mov     rcx, [rax+r13*8]; this
0x18000b884  test    rcx, rcx
0x18000b887  jz      loc_18000B9C4
0x18000b88d  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x18000b892  mov     rax, [r15+0B0h]
0x18000b899  mov     r13, [rax+r13*8]
0x18000b89d  test    r13, r13
0x18000b8a0  jz      loc_18000B9C4
0x18000b8a6  mov     rcx, r13; this
0x18000b8a9  call    ?IsDeleted@CDRMCBase@@QEAAHXZ; CDRMCBase::IsDeleted(void)
0x18000b8ae  xor     ecx, ecx
0x18000b8b0  test    eax, eax
0x18000b8b2  jnz     short loc_18000B915
0x18000b8b4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b8b8  inc     rax
0x18000b8bb  cmp     [rsi+rax*2], cx
0x18000b8bf  jnz     short loc_18000B8B8
0x18000b8c1  mov     [rsp+1C0h+var_160], rax
0x18000b8c6  mov     rdi, [r13+88h]
0x18000b8cd  mov     rsi, [r13+80h]
0x18000b8d4  mov     rcx, r13; this
0x18000b8d7  call    ?GetData@CNameValue@@QEAAIXZ; CNameValue::GetData(void)
0x18000b8dc  mov     edx, r12d
0x18000b8df  mov     rcx, [rsp+1C0h+var_160]
0x18000b8e4  sub     edx, ecx; unsigned __int64
0x18000b8e6  mov     r8d, ecx
0x18000b8e9  mov     rcx, [rsp+1C0h+Block]
0x18000b8ee  lea     rcx, [rcx+r8*2]; unsigned __int16 *
0x18000b8f2  mov     qword ptr [rsp+1C0h+var_198], rdi
0x18000b8f7  mov     [rsp+1C0h+var_1A0], rsi
0x18000b8fc  mov     r9d, eax
0x18000b8ff  lea     r8, [rbp+0C0h+var_140]; unsigned __int16 *
0x18000b903  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b908  mov     edi, eax
0x18000b90a  xor     esi, esi
0x18000b90c  test    eax, eax
0x18000b90e  js      short loc_18000B934
0x18000b910  mov     rsi, [rsp+1C0h+Block]
0x18000b915  mov     rcx, r13; this
0x18000b918  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000b91d  mov     eax, dword ptr [rsp+1C0h+var_188]
0x18000b921  inc     eax
0x18000b923  mov     dword ptr [rsp+1C0h+var_188], eax
0x18000b927  cmp     eax, dword ptr [rsp+1C0h+var_190]
0x18000b92b  jnb     short loc_18000B941
0x18000b92d  xor     edx, edx
0x18000b92f  jmp     loc_18000B869
0x18000b934  mov     rcx, r13; this
0x18000b937  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000b93c  jmp     loc_18000B9C4
0x18000b941  mov     edi, dword ptr [rsp+1C0h+var_180]
0x18000b945  mov     eax, 2
0x18000b94a  mul     rdi
0x18000b94d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000b954  cmovb   rax, rcx
0x18000b958  mov     rcx, rax; unsigned __int64
0x18000b95b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000b960  mov     r14, rax
0x18000b963  xor     r13d, r13d
0x18000b966  test    rax, rax
0x18000b969  jz      loc_18000B845
0x18000b96f  lea     r8, [rdi+rdi]; Size
0x18000b973  xor     edx, edx; Val
0x18000b975  mov     rcx, rax; void *
0x18000b978  call    memset_0
0x18000b97d  mov     rax, [r15+308h]
0x18000b984  mov     r9, [rsp+1C0h+var_170]
0x18000b989  test    rax, rax
0x18000b98c  cmovnz  r9, rax
0x18000b990  mov     [rsp+1C0h+var_1A0], rsi
0x18000b995  lea     r8, [rbp+0C0h+var_F0]; unsigned __int16 *
0x18000b999  mov     edx, edi; unsigned __int64
0x18000b99b  mov     rcx, r14; unsigned __int16 *
0x18000b99e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b9a3  mov     edi, eax
0x18000b9a5  test    eax, eax
0x18000b9a7  js      short loc_18000B9C4
0x18000b9a9  mov     rax, [rsp+1C0h+var_168]
0x18000b9ae  mov     [rax], r14
0x18000b9b1  mov     eax, dword ptr [rsp+1C0h+var_180]
0x18000b9b5  mov     rcx, [rsp+1C0h+var_158]
0x18000b9ba  mov     [rcx], eax
0x18000b9bc  mov     r14, r13
0x18000b9bf  jmp     short loc_18000B9C4
0x18000b9c1  mov     r14, rdx
0x18000b9c4  mov     rcx, [rsp+1C0h+Block]; Block
0x18000b9c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b9ce  mov     rcx, r14; Block
0x18000b9d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b9d6  mov     rcx, [rsp+1C0h+var_170]; Block
0x18000b9db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b9e0  nop
0x18000b9e1  mov     rcx, rbx; lpCriticalSection
0x18000b9e4  call    cs:__imp_LeaveCriticalSection
0x18000b9ea  mov     eax, edi
0x18000b9ec  mov     rcx, [rbp+0C0h+var_40]
0x18000b9f3  xor     rcx, rsp; StackCookie
0x18000b9f6  call    __security_check_cookie
0x18000b9fb  mov     rbx, [rsp+1C0h+arg_18]
0x18000ba03  add     rsp, 190h
0x18000ba0a  pop     r15
0x18000ba0c  pop     r14
0x18000ba0e  pop     r13
0x18000ba10  pop     r12
0x18000ba12  pop     rdi
0x18000ba13  pop     rsi
0x18000ba14  pop     rbp
0x18000ba15  retn
```
