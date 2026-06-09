# CMemPropStore::_SerializeValue(_tagpropertykey const *,ushort const *,int,tagPROPVARIANT const *)

- ea: `0x18003cce0`
- end: `0x18003d344`
- name: `?_SerializeValue@CMemPropStore@@AEAAJPEBU_tagpropertykey@@PEBGHPEBUtagPROPVARIANT@@@Z`
- size: `1636`
- prototype: `int(CMemPropStore *__hidden this, const struct _tagpropertykey *, const unsigned __int16 *, int, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003bff0`

## callees

- `0x18003cce0`
- `0x18003d500`
- `0x18003d630`
- `0x18003ef7c`
- `0x18006ed20`
- `0x18006fb80`
- `0x18006fb8c`
- `0x18006fb98`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003d116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003d1f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003d2ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003d116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003d1f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18003d2ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d0b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d331`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d0b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d331`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cf09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cf09`
- `SHCORE!__imp_ualstrcmpiW` at `0x18003cf66`
- `SHCORE!__imp_ualstrcmpiW` at `0x18003cf66`

## pseudocode

```c
__int64 __fastcall CMemPropStore::_SerializeValue(
        CMemPropStore *this,
        const struct _tagpropertykey *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        const struct tagPROPVARIANT *a5)
{
  const struct _tagpropertykey *v6; // rbx
  const struct _tagpropertykey *v8; // rsi
  unsigned int *v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned int v12; // esi
  __int64 v13; // r9
  __int64 v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // rax
  DWORD pid; // r14d
  __int64 v18; // rax
  int v19; // esi
  unsigned int *i; // rbx
  bool v21; // zf
  VARTYPE vt; // ax
  unsigned int v23; // r14d
  void *v24; // r12
  int v25; // ecx
  void *v26; // r15
  int v27; // r15d
  int v28; // eax
  unsigned int v29; // ecx
  int v30; // edx
  unsigned int v31; // r10d
  int v32; // r15d
  unsigned int v33; // ecx
  unsigned int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rsi
  __int64 v37; // rcx
  LPVOID v39; // rax
  __int64 v40; // rax
  size_t v41; // r8
  unsigned int *v42; // rax
  __int64 v43; // rax
  int (__fastcall ***QuadPart)(_QWORD, GUID *, char *); // rcx
  int v45; // r14d
  unsigned int v46; // ebx
  LPVOID v47; // rax
  int cb; // [rsp+50h] [rbp-88h]
  unsigned int cba; // [rsp+50h] [rbp-88h]
  void *v50; // [rsp+58h] [rbp-80h] BYREF
  const struct _tagpropertykey *v51; // [rsp+60h] [rbp-78h]
  const struct tagPROPVARIANT *v52; // [rsp+68h] [rbp-70h]
  __int64 v53; // [rsp+70h] [rbp-68h]
  __int128 v54; // [rsp+78h] [rbp-60h] BYREF
  __int64 v55; // [rsp+88h] [rbp-50h]
  size_t Size; // [rsp+90h] [rbp-48h] BYREF

  v51 = a2;
  v6 = a2;
  v52 = a5;
  if ( a5 && (a2 || a3) )
  {
    v8 = (const struct _tagpropertykey *)&FMTID_UserDefinedProperties;
    v9 = (unsigned int *)*((_QWORD *)this + 25);
    if ( !a3 )
      v8 = a2;
    if ( v9 )
    {
      while ( 1 )
      {
        v10 = *v9;
        if ( !(_DWORD)v10 )
          break;
        v11 = *(_QWORD *)&v8->fmtid.Data1 - *((_QWORD *)v9 + 1);
        if ( *(_QWORD *)&v8->fmtid.Data1 == *((_QWORD *)v9 + 1) )
          v11 = *(_QWORD *)v8->fmtid.Data4 - *((_QWORD *)v9 + 2);
        if ( !v11 )
          goto LABEL_11;
        v9 = (unsigned int *)((char *)v9 + v10);
      }
    }
    else
    {
      if ( *((_DWORD *)this + 53) < 0x100u )
      {
        v42 = (unsigned int *)CoTaskMemRealloc(0, 0x100u);
        v9 = v42;
        if ( !v42 )
          return (unsigned int)-2147024882;
        *((_QWORD *)this + 25) = v42;
        *((_DWORD *)this + 53) = 256;
      }
      *((_DWORD *)this + 52) = 4;
      LODWORD(v10) = 0;
      *v9 = 0;
LABEL_11:
      if ( (_DWORD)v10 )
      {
LABEL_15:
        if ( (*((_BYTE *)this + 184) & 1) != 0 )
        {
          v43 = v9[6];
          for ( i = v9 + 6; (_DWORD)v43; v43 = *i )
            i = (unsigned int *)((char *)i + v43);
LABEL_28:
          vt = a5->vt;
          v23 = 0;
          v24 = 0;
          LODWORD(Size) = 0;
          v12 = -2147024882;
          v50 = 0;
          if ( !vt )
          {
            LODWORD(Size) = 0;
            goto LABEL_42;
          }
          v55 = 0;
          v54 = 0;
          if ( vt == 13 )
          {
            QuadPart = (int (__fastcall ***)(_QWORD, GUID *, char *))a5->hVal.QuadPart;
            if ( QuadPart )
            {
              if ( (**QuadPart)(QuadPart, &GUID_0000000c_0000_0000_c000_000000000046, (char *)&v54 + 8) >= 0 )
              {
                LOWORD(v54) = 66;
                v27 = StgSerializePropVariantEx(1, &v54, &v50, &Size);
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v54 + 1) + 16LL))(*((_QWORD *)&v54 + 1));
                v23 = Size;
                v24 = v50;
                goto LABEL_38;
              }
            }
          }
          LODWORD(Size) = 0;
          StgConvertVariantToPropertyNoEH(1, a5);
          v25 = Size;
          if ( (Size & 0x80000000) != 0LL )
          {
            v26 = 0;
          }
          else
          {
            v26 = CoTaskMemAlloc(0);
            if ( !v26 )
            {
              v27 = -2147024882;
              goto LABEL_38;
            }
            v23 = 0;
            StgConvertVariantToPropertyNoEH(1, v52);
            v25 = Size;
            if ( (Size & 0x80000000) == 0LL )
            {
              v24 = v26;
              v27 = 0;
              goto LABEL_38;
            }
          }
          v28 = MapNTStatusToHResult(v25);
          cb = v28;
          if ( v28 < 0 )
          {
            cb = v28;
            if ( !v26 )
            {
              v27 = v28;
              goto LABEL_38;
            }
            CoTaskMemFree(v26);
          }
          v27 = cb;
LABEL_38:
          LODWORD(Size) = 0;
          if ( v27 < 0 )
            v23 = 0;
          if ( v23 )
          {
            v29 = v23 + 9;
            v23 += 9;
            if ( a3 )
            {
              v40 = -1;
              do
                v21 = a3[++v40] == 0;
              while ( !v21 );
              v23 = 0;
              LODWORD(Size) = 2 * v40 + 2;
              if ( v29 + (unsigned int)Size >= v29 )
                v23 = v29 + Size;
            }
          }
LABEL_42:
          LODWORD(v50) = *((_DWORD *)this + 50);
          v30 = (int)v50;
          v31 = *i + (_DWORD)i - (_DWORD)v50;
          v32 = v23 - *i;
          v53 = v31;
          if ( v32 <= 0 )
          {
LABEL_46:
            v36 = v31;
            memmove_0(
              (void *)(*((_QWORD *)this + 25) + v32 + v31),
              (const void *)(v31 + *((_QWORD *)this + 25)),
              *((_DWORD *)this + 52) - v31);
            if ( v32 > 0 )
              memset_0((void *)(v36 + *((_QWORD *)this + 25)), 0, v32);
            *((_DWORD *)this + 52) += v32;
            v12 = 0;
            if ( v23 )
            {
              *i = v23;
              *((_BYTE *)i + 8) = 0;
              if ( a3 )
              {
                v41 = (unsigned int)Size;
                i[1] = Size;
                memcpy_0((char *)i + 9, a3, v41);
              }
              else
              {
                i[1] = v51->pid;
              }
              if ( v52->vt )
              {
                if ( a3 )
                  v37 = i[1] + 9;
                else
                  v37 = 9;
                memcpy_0((char *)i + v37, v24, *i - (unsigned int)v37);
              }
            }
            *v9 += v32;
            goto LABEL_56;
          }
          v33 = v32 + *((_DWORD *)this + 52);
          if ( v33 + 256 < v33 )
          {
            v12 = -2147024362;
          }
          else
          {
            v34 = (v33 + 255) & 0xFFFFFF00;
            cba = v34;
            if ( v34 <= *((_DWORD *)this + 53) )
            {
LABEL_45:
              v35 = *((_QWORD *)this + 25);
              v9 = (unsigned int *)(v35 + (unsigned int)((_DWORD)v9 - v30));
              i = (unsigned int *)(v35 + (unsigned int)((_DWORD)i - v30));
              goto LABEL_46;
            }
            v39 = CoTaskMemRealloc(*((LPVOID *)this + 25), v34);
            if ( v39 )
            {
              v30 = (int)v50;
              v31 = v53;
              *((_QWORD *)this + 25) = v39;
              *((_DWORD *)this + 53) = cba;
              goto LABEL_45;
            }
          }
LABEL_56:
          CoTaskMemFree(v24);
          return v12;
        }
        if ( a3 )
          pid = 0;
        else
          pid = v6->pid;
        v18 = *((_QWORD *)v9 + 1) - *(_QWORD *)&FMTID_UserDefinedProperties.Data1;
        v53 = 0;
        if ( !v18 )
          v18 = *((_QWORD *)v9 + 2) - *(_QWORD *)FMTID_UserDefinedProperties.Data4;
        if ( v18 )
        {
          v19 = 0;
          if ( !a3 )
            goto LABEL_22;
        }
        else if ( a3 )
        {
          v19 = 1;
LABEL_22:
          for ( i = v9 + 6; *i; i = (unsigned int *)((char *)i + *i) )
          {
            v21 = v19 ? (unsigned int)ualstrcmpiW((char *)i + 9, a3) == 0 : pid == i[1];
            if ( v21 )
              break;
          }
          goto LABEL_28;
        }
        return (unsigned int)-2147467259;
      }
    }
    if ( *((_DWORD *)this + 52) + 284 < (unsigned int)(*((_DWORD *)this + 52) + 28) )
      return (unsigned int)-2147024362;
    v45 = *((_DWORD *)this + 50);
    v46 = (*((_DWORD *)this + 52) + 283) & 0xFFFFFF00;
    if ( v46 <= *((_DWORD *)this + 53) )
      goto LABEL_14;
    v47 = CoTaskMemRealloc(*((LPVOID *)this + 25), v46);
    if ( v47 )
    {
      *((_QWORD *)this + 25) = v47;
      *((_DWORD *)this + 53) = v46;
LABEL_14:
      v13 = *((_QWORD *)this + 25);
      v14 = (unsigned int)((_DWORD)v9 - v45);
      v15 = (unsigned int)v14;
      v9 = (unsigned int *)(v13 + v14);
      memmove_0(
        (void *)(v13 + (unsigned int)(v15 + 28)),
        (const void *)(v15 + v13),
        (unsigned int)(*((_DWORD *)this + 52) - v15));
      v16 = *((_QWORD *)this + 25);
      *(_OWORD *)(v15 + v16) = 0;
      *(_OWORD *)(v15 + v16 + 12) = 0;
      *((_DWORD *)this + 52) += 28;
      v6 = v51;
      *v9 = 28;
      v9[1] = 1397773105;
      *(GUID *)(v9 + 2) = v8->fmtid;
      goto LABEL_15;
    }
    return (unsigned int)-2147024882;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18003cce0  push    rbx
0x18003cce2  push    rbp
0x18003cce3  push    r13
0x18003cce5  push    r15
0x18003cce7  sub     rsp, 0B8h
0x18003ccee  mov     rax, cs:__security_cookie
0x18003ccf5  xor     rax, rsp
0x18003ccf8  mov     [rsp+0D8h+var_40], rax
0x18003cd00  mov     r15, [rsp+0D8h+arg_20]
0x18003cd08  mov     rbp, r8
0x18003cd0b  mov     [rsp+0D8h+var_78], rdx
0x18003cd10  mov     rbx, rdx
0x18003cd13  mov     [rsp+0D8h+var_70], r15
0x18003cd18  mov     r13, rcx
0x18003cd1b  test    r15, r15
0x18003cd1e  jz      loc_18003D1E7
0x18003cd24  test    rdx, rdx
0x18003cd27  jz      loc_18003D1DE
0x18003cd2d  mov     [rsp+0D8h+arg_8], rsi
0x18003cd35  test    rbp, rbp
0x18003cd38  mov     [rsp+0D8h+var_28], rdi
0x18003cd40  lea     rsi, FMTID_UserDefinedProperties
0x18003cd47  mov     rdi, [rcx+0C8h]
0x18003cd4e  cmovz   rsi, rdx
0x18003cd52  xor     r8d, r8d
0x18003cd55  mov     [rsp+0D8h+var_38], r14
0x18003cd5d  test    rdi, rdi
0x18003cd60  jz      loc_18003D194
0x18003cd66  mov     ecx, [rdi]
0x18003cd68  test    ecx, ecx
0x18003cd6a  jz      short loc_18003CD8F
0x18003cd6c  mov     rax, [rsi]
0x18003cd6f  sub     rax, [rdi+8]
0x18003cd73  jnz     short loc_18003CD7D
0x18003cd75  mov     rax, [rsi+8]
0x18003cd79  sub     rax, [rdi+10h]
0x18003cd7d  test    rax, rax
0x18003cd80  jz      short loc_18003CD87
0x18003cd82  add     rdi, rcx
0x18003cd85  jmp     short loc_18003CD66
0x18003cd87  test    ecx, ecx
0x18003cd89  jnz     loc_18003CE10
0x18003cd8f  mov     ebx, [r13+0D0h]
0x18003cd96  add     ebx, 1Ch
0x18003cd99  lea     eax, [rbx+100h]
0x18003cd9f  cmp     eax, ebx
0x18003cda1  jnb     loc_18003D2C3
0x18003cda7  mov     esi, 80070216h
0x18003cdac  jmp     loc_18003D0C1
0x18003cdb1  mov     r9, [r13+0C8h]
0x18003cdb8  sub     edi, r14d
0x18003cdbb  mov     r8d, [r13+0D0h]
0x18003cdc2  mov     ebx, edi
0x18003cdc4  add     rdi, r9
0x18003cdc7  sub     r8d, ebx; Size
0x18003cdca  lea     ecx, [rbx+1Ch]
0x18003cdcd  add     rcx, r9; void *
0x18003cdd0  lea     rdx, [rbx+r9]; Src
0x18003cdd4  call    memmove_0
0x18003cdd9  mov     rax, [r13+0C8h]
0x18003cde0  xorps   xmm0, xmm0
0x18003cde3  movups  xmmword ptr [rbx+rax], xmm0
0x18003cde7  movups  xmmword ptr [rbx+rax+0Ch], xmm0
0x18003cdec  add     dword ptr [r13+0D0h], 1Ch
0x18003cdf4  mov     rbx, [rsp+0D8h+var_78]
0x18003cdf9  xor     r8d, r8d
0x18003cdfc  mov     dword ptr [rdi], 1Ch
0x18003ce02  mov     dword ptr [rdi+4], 53505331h
0x18003ce09  movups  xmm0, xmmword ptr [rsi]
0x18003ce0c  movups  xmmword ptr [rdi+8], xmm0
0x18003ce10  test    byte ptr [r13+0B8h], 1
0x18003ce18  jnz     loc_18003D224
0x18003ce1e  test    rbp, rbp
0x18003ce21  jz      loc_18003D314
0x18003ce27  mov     r14d, r8d
0x18003ce2a  mov     rax, [rdi+8]
0x18003ce2e  sub     rax, qword ptr cs:FMTID_UserDefinedProperties.Data1
0x18003ce35  mov     [rsp+0D8h+var_68], r8
0x18003ce3a  jnz     short loc_18003CE47
0x18003ce3c  mov     rax, [rdi+10h]
0x18003ce40  sub     rax, qword ptr cs:FMTID_UserDefinedProperties.Data4
0x18003ce47  test    rax, rax
0x18003ce4a  jz      loc_18003D17A
0x18003ce50  mov     esi, r8d
0x18003ce53  test    rbp, rbp
0x18003ce56  jnz     loc_18003D17F
0x18003ce5c  lea     rbx, [rdi+18h]
0x18003ce60  cmp     dword ptr [rbx], 0
0x18003ce63  jz      short loc_18003CE7A
0x18003ce65  test    esi, esi
0x18003ce67  jnz     loc_18003CF5F
0x18003ce6d  cmp     r14d, [rbx+4]
0x18003ce71  jz      short loc_18003CE7A
0x18003ce73  mov     eax, [rbx]
0x18003ce75  add     rbx, rax
0x18003ce78  jmp     short loc_18003CE60
0x18003ce7a  xor     r8d, r8d
0x18003ce7d  movzx   eax, word ptr [r15]
0x18003ce81  mov     r14d, r8d
0x18003ce84  mov     [rsp+0D8h+var_30], r12
0x18003ce8c  mov     r12, r8
0x18003ce8f  mov     dword ptr [rsp+0D8h+Size], r8d
0x18003ce97  mov     esi, 8007000Eh
0x18003ce9c  mov     [rsp+0D8h+var_80], r8
0x18003cea1  test    ax, ax
0x18003cea4  jz      loc_18003D100
0x18003ceaa  xor     ecx, ecx
0x18003ceac  xorps   xmm0, xmm0
0x18003ceaf  mov     [rsp+0D8h+var_50], rcx
0x18003ceb7  movups  [rsp+0D8h+var_60], xmm0
0x18003cebc  cmp     ax, 0Dh
0x18003cec0  jz      loc_18003D241
0x18003cec6  lea     rax, [rsp+0D8h+Size]
0x18003cece  mov     dword ptr [rsp+0D8h+cb], r8d
0x18003ced3  mov     [rsp+0D8h+var_98], rax
0x18003ced8  xor     r9d, r9d
0x18003cedb  lea     rax, [rsp+0D8h+cb]
0x18003cee0  mov     dword ptr [rsp+0D8h+Size], r8d
0x18003cee8  mov     rdx, r15
0x18003ceeb  mov     [rsp+0D8h+var_B8], rax
0x18003cef0  mov     ecx, 1
0x18003cef5  call    StgConvertVariantToPropertyNoEH
0x18003cefa  mov     ecx, dword ptr [rsp+0D8h+Size]; int
0x18003cf01  test    ecx, ecx
0x18003cf03  js      short loc_18003CF73
0x18003cf05  mov     ecx, dword ptr [rsp+0D8h+cb]; cb
0x18003cf09  call    cs:__imp_CoTaskMemAlloc
0x18003cf0f  mov     r15, rax
0x18003cf12  test    rax, rax
0x18003cf15  jz      loc_18003D31D
0x18003cf1b  mov     rdx, [rsp+0D8h+var_70]
0x18003cf20  lea     rax, [rsp+0D8h+Size]
0x18003cf28  mov     r14d, dword ptr [rsp+0D8h+cb]
0x18003cf2d  mov     r9, r15
0x18003cf30  mov     [rsp+0D8h+var_98], rax
0x18003cf35  mov     ecx, 1
0x18003cf3a  lea     rax, [rsp+0D8h+cb]
0x18003cf3f  mov     [rsp+0D8h+var_B8], rax
0x18003cf44  call    StgConvertVariantToPropertyNoEH
0x18003cf49  mov     ecx, dword ptr [rsp+0D8h+Size]
0x18003cf50  test    ecx, ecx
0x18003cf52  js      short loc_18003CF76
0x18003cf54  xor     r8d, r8d
0x18003cf57  mov     r12, r15
0x18003cf5a  mov     r15d, r8d
0x18003cf5d  jmp     short loc_18003CF8F
0x18003cf5f  lea     rcx, [rbx+9]
0x18003cf63  mov     rdx, rbp
0x18003cf66  call    cs:__imp_ualstrcmpiW
0x18003cf6c  test    eax, eax
0x18003cf6e  jmp     loc_18003CE71
0x18003cf73  xor     r15d, r15d
0x18003cf76  call    ?MapNTStatusToHResult@@YAJJ@Z; MapNTStatusToHResult(long)
0x18003cf7b  mov     dword ptr [rsp+0D8h+cb], eax
0x18003cf7f  test    eax, eax
0x18003cf81  js      loc_18003D325
0x18003cf87  mov     r15d, dword ptr [rsp+0D8h+cb]
0x18003cf8c  xor     r8d, r8d
0x18003cf8f  test    r15d, r15d
0x18003cf92  mov     dword ptr [rsp+0D8h+Size], r8d
0x18003cf9a  cmovs   r14d, r8d
0x18003cf9e  test    r14d, r14d
0x18003cfa1  jz      short loc_18003CFB3
0x18003cfa3  lea     ecx, [r14+9]
0x18003cfa7  mov     r14d, ecx
0x18003cfaa  test    rbp, rbp
0x18003cfad  jnz     loc_18003D141
0x18003cfb3  mov     edx, [r13+0C8h]
0x18003cfba  mov     r10d, ebx
0x18003cfbd  sub     r10d, edx
0x18003cfc0  mov     dword ptr [rsp+0D8h+var_80], edx
0x18003cfc4  add     r10d, [rbx]
0x18003cfc7  mov     r15d, r14d
0x18003cfca  sub     r15d, [rbx]
0x18003cfcd  mov     [rsp+0D8h+var_68], r10
0x18003cfd2  test    r15d, r15d
0x18003cfd5  jle     short loc_18003D01C
0x18003cfd7  mov     ecx, [r13+0D0h]
0x18003cfde  add     ecx, r15d
0x18003cfe1  lea     eax, [rcx+100h]
0x18003cfe7  cmp     eax, ecx
0x18003cfe9  jb      loc_18003D0F9
0x18003cfef  lea     eax, [rcx+0FFh]
0x18003cff5  and     eax, 0FFFFFF00h
0x18003cffa  mov     dword ptr [rsp+0D8h+cb], eax
0x18003cffe  cmp     eax, [r13+0D4h]
0x18003d005  ja      loc_18003D10D
0x18003d00b  mov     rax, [r13+0C8h]
0x18003d012  sub     edi, edx
0x18003d014  add     rdi, rax
0x18003d017  sub     ebx, edx
0x18003d019  add     rbx, rax
0x18003d01c  mov     r9, [r13+0C8h]
0x18003d023  lea     ecx, [r15+r10]
0x18003d027  mov     r8d, [r13+0D0h]
0x18003d02e  add     rcx, r9; void *
0x18003d031  mov     esi, r10d
0x18003d034  sub     r8d, r10d; Size
0x18003d037  lea     rdx, [rsi+r9]; Src
0x18003d03b  call    memmove_0
0x18003d040  test    r15d, r15d
0x18003d043  jle     short loc_18003D059
0x18003d045  mov     rcx, [r13+0C8h]
0x18003d04c  xor     edx, edx; Val
0x18003d04e  add     rcx, rsi; void *
0x18003d051  movsxd  r8, r15d; Size
0x18003d054  call    memset_0
0x18003d059  add     [r13+0D0h], r15d
0x18003d060  xor     eax, eax
0x18003d062  mov     esi, eax
0x18003d064  test    r14d, r14d
0x18003d067  jz      short loc_18003D0AD
0x18003d069  mov     [rbx], r14d
0x18003d06c  mov     [rbx+8], al
0x18003d06f  test    rbp, rbp
0x18003d072  jnz     loc_18003D1C0
0x18003d078  mov     rax, [rsp+0D8h+var_78]
0x18003d07d  mov     eax, [rax+10h]
0x18003d080  mov     [rbx+4], eax
0x18003d083  mov     rax, [rsp+0D8h+var_70]
0x18003d088  cmp     [rax], si
0x18003d08b  jz      short loc_18003D0AD
0x18003d08d  mov     eax, [rbx]
0x18003d08f  test    rbp, rbp
0x18003d092  jnz     loc_18003D189
0x18003d098  mov     ecx, 9
0x18003d09d  sub     eax, ecx
0x18003d09f  mov     rdx, r12; Src
0x18003d0a2  mov     r8d, eax; Size
0x18003d0a5  add     rcx, rbx; void *
0x18003d0a8  call    memcpy_0
0x18003d0ad  add     [rdi], r15d
0x18003d0b0  mov     rcx, r12; pv
0x18003d0b3  call    cs:__imp_CoTaskMemFree
0x18003d0b9  mov     r12, [rsp+0D8h+var_30]
0x18003d0c1  mov     r14, [rsp+0D8h+var_38]
0x18003d0c9  mov     eax, esi
0x18003d0cb  mov     rsi, [rsp+0D8h+arg_8]
0x18003d0d3  mov     rdi, [rsp+0D8h+var_28]
0x18003d0db  mov     rcx, [rsp+0D8h+var_40]
0x18003d0e3  xor     rcx, rsp; StackCookie
0x18003d0e6  call    __security_check_cookie
0x18003d0eb  add     rsp, 0B8h
0x18003d0f2  pop     r15
0x18003d0f4  pop     r13
0x18003d0f6  pop     rbp
0x18003d0f7  pop     rbx
0x18003d0f8  retn
0x18003d0f9  mov     esi, 80070216h
0x18003d0fe  jmp     short loc_18003D0B0
0x18003d100  mov     dword ptr [rsp+0D8h+Size], r8d
0x18003d108  jmp     loc_18003CFB3
0x18003d10d  mov     rcx, [r13+0C8h]; pv
0x18003d114  mov     edx, eax; cb
0x18003d116  call    cs:__imp_CoTaskMemRealloc
0x18003d11c  test    rax, rax
0x18003d11f  jz      short loc_18003D0B0
0x18003d121  mov     edx, dword ptr [rsp+0D8h+var_80]
0x18003d125  mov     r10, [rsp+0D8h+var_68]
0x18003d12a  mov     [r13+0C8h], rax
0x18003d131  mov     eax, dword ptr [rsp+0D8h+cb]
0x18003d135  mov     [r13+0D4h], eax
0x18003d13c  jmp     loc_18003D00B
0x18003d141  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18003d148  nop     dword ptr [rax+rax+00000000h]
0x18003d150  cmp     word ptr [rbp+rax*2+2], 0
0x18003d156  lea     rax, [rax+1]
0x18003d15a  jnz     short loc_18003D150
0x18003d15c  lea     eax, ds:2[rax*2]
0x18003d163  mov     r14d, r8d
0x18003d166  mov     dword ptr [rsp+0D8h+Size], eax
0x18003d16d  add     eax, ecx
0x18003d16f  cmp     eax, ecx
0x18003d171  cmovnb  r14d, eax
0x18003d175  jmp     loc_18003CFB3
0x18003d17a  test    rbp, rbp
0x18003d17d  jnz     short loc_18003D1B6
0x18003d17f  mov     esi, 80004005h
0x18003d184  jmp     loc_18003D0C1
0x18003d189  mov     ecx, [rbx+4]
0x18003d18c  add     ecx, 9
0x18003d18f  jmp     loc_18003D09D
0x18003d194  cmp     dword ptr [rcx+0D4h], 100h
0x18003d19e  jb      short loc_18003D1F1
0x18003d1a0  mov     dword ptr [r13+0D0h], 4
0x18003d1ab  mov     ecx, r8d
0x18003d1ae  mov     [rdi], r8d
0x18003d1b1  jmp     loc_18003CD87
0x18003d1b6  mov     esi, 1
0x18003d1bb  jmp     loc_18003CE5C
0x18003d1c0  mov     eax, dword ptr [rsp+0D8h+Size]
0x18003d1c7  lea     rcx, [rbx+9]; void *
0x18003d1cb  mov     r8d, eax; Size
0x18003d1ce  mov     [rbx+4], eax
0x18003d1d1  mov     rdx, rbp; Src
0x18003d1d4  call    memcpy_0
0x18003d1d9  jmp     loc_18003D083
0x18003d1de  test    rbp, rbp
0x18003d1e1  jnz     loc_18003CD2D
0x18003d1e7  mov     eax, 80070057h
  ... truncated ...
```
