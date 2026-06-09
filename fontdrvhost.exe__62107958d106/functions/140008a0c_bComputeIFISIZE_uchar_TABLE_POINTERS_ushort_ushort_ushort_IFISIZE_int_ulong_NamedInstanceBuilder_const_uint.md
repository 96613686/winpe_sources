# bComputeIFISIZE(uchar *,_TABLE_POINTERS *,ushort,ushort,ushort,_IFISIZE *,int *,ulong *,NamedInstanceBuilder const *,uint)

- ea: `0x140008a0c`
- end: `0x14000921e`
- name: `?bComputeIFISIZE@@YAHPEAEPEAU_TABLE_POINTERS@@GGGPEAU_IFISIZE@@PEAHPEAKPEBVNamedInstanceBuilder@@I@Z`
- size: `2066`
- prototype: `__int64 __fastcall(unsigned __int8 *, struct _TABLE_POINTERS *, unsigned __int16, unsigned __int16, unsigned __int16, struct _IFISIZE *, int *, unsigned int *, const struct NamedInstanceBuilder *, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400086b4`

## callees

- `0x140004148`
- `0x140004ff8`
- `0x140005348`
- `0x1400054e8`
- `0x140005560`
- `0x140006670`
- `0x140008a0c`
- `0x140055ae8`
- `0x14005e5d0`
- `0x14005eacc`
- `0x14007680c`
- `0x140076ede`
- `0x1400961d0`

## string_xrefs

- `0x1400090e7`: `Converter: Windows Type 1 Installer`

## pseudocode

```c
__int64 __fastcall bComputeIFISIZE(
        unsigned __int8 *a1,
        struct _TABLE_POINTERS *a2,
        unsigned __int16 a3,
        unsigned __int16 a4,
        unsigned __int16 a5,
        struct _IFISIZE *a6,
        int *a7,
        unsigned int *a8,
        const struct NamedInstanceBuilder *a9,
        unsigned int a10)
{
  __int64 v10; // rbp
  int v13; // r15d
  unsigned __int8 *v14; // rdi
  unsigned __int8 *v15; // rsi
  unsigned __int8 *v16; // rdx
  unsigned __int64 v17; // r14
  unsigned __int8 *v18; // rcx
  unsigned __int8 *v19; // rbp
  const struct NamedInstanceBuilder *v20; // r13
  unsigned __int8 *v21; // r12
  int v22; // r14d
  unsigned int v23; // eax
  unsigned __int64 v24; // r9
  int v25; // r8d
  int i; // edi
  unsigned __int8 *v27; // rdx
  int v28; // r10d
  unsigned int v29; // r11d
  unsigned int v30; // eax
  char v31; // r9
  bool v32; // zf
  unsigned int v33; // eax
  unsigned __int16 v34; // r8
  unsigned __int8 *v35; // rdx
  int v36; // r10d
  int v37; // r8d
  unsigned int v38; // r9d
  unsigned __int8 v39; // al
  int v40; // ecx
  int v41; // ecx
  int v42; // eax
  int v43; // ecx
  int v44; // edx
  int v45; // edi
  int v46; // ecx
  int v47; // ecx
  unsigned int v48; // edi
  unsigned int v49; // ecx
  size_t v50; // r8
  char v51; // al
  unsigned int v52; // ecx
  unsigned int v53; // eax
  size_t v54; // r8
  int v55; // eax
  unsigned int v56; // ecx
  _BYTE *v57; // rdx
  const char *v58; // r9
  int v59; // r10d
  _BYTE *v60; // rdx
  _BYTE *v61; // rdx
  const char *v62; // r9
  int v63; // r10d
  _BYTE *v64; // rdx
  _BYTE *v65; // rdx
  const char *v66; // r9
  int v67; // r10d
  _BYTE *v68; // rdx
  __int64 result; // rax
  USHORT AnsiCodePage[2]; // [rsp+30h] [rbp-78h] BYREF
  USHORT OemCodePage[2]; // [rsp+34h] [rbp-74h] BYREF
  unsigned __int64 v72; // [rsp+38h] [rbp-70h]
  unsigned __int64 v73; // [rsp+40h] [rbp-68h]
  unsigned __int8 *v74; // [rsp+48h] [rbp-60h]
  unsigned __int8 *v75; // [rsp+50h] [rbp-58h]

  v10 = *((unsigned int *)a2 + 15);
  AnsiCodePage[0] = 0;
  if ( (unsigned int)v10 < 6 )
    return 0;
  v13 = 1;
  if ( ((a3 - 1) & 0xFFFD) != 0 )
    return 0;
  v14 = &a1[*((unsigned int *)a2 + 14)];
  memset_0(a6, 0, 0x8Cu);
  *((_WORD *)a6 + 70) = a3;
  v15 = v14 + 6;
  *((_WORD *)a6 + 71) = a4;
  v75 = v14 + 6;
  if ( v14 >= v14 + 6 )
    return 0;
  v16 = &v14[v10];
  v17 = (unsigned int)v10;
  v73 = (unsigned __int64)&v14[v10];
  if ( v15 > &v14[v10] )
    return 0;
  v18 = &v15[12 * (v14[3] | ((unsigned __int64)v14[2] << 8))];
  v72 = (unsigned __int64)v18;
  if ( v15 > v18 )
    return 0;
  v19 = &v14[((unsigned __int64)v14[4] << 8) | v14[5]];
  if ( v18 > v19 )
    return 0;
  if ( v19 > v16 )
    return 0;
  EngGetCurrentCodePage(OemCodePage, AnsiCodePage);
  if ( v17 < 12 * (v14[3] | ((unsigned __int64)v14[2] << 8)) + 6 )
    return 0;
  v20 = a9;
  v21 = 0;
  v22 = 0;
  *(_DWORD *)OemCodePage = 0;
  if ( a9 )
  {
    *((_DWORD *)a6 + 30) = 2 * NamedInstanceBuilder::GetInstanceFamilyName(a9, a10, 0, 0);
    *((_DWORD *)a6 + 32) = 2 * NamedInstanceBuilder::GetInstanceSubFamilyName(a9, a10, 0, 0);
    *((_DWORD *)a6 + 34) = 2 * NamedInstanceBuilder::GetInstanceFullName(a9, a10, 0, 0);
    *((_DWORD *)a6 + 33) = 2 * NamedInstanceBuilder::GetInstanceFullName(a9, a10, 0, 0);
    if ( !*((_DWORD *)a6 + 30) )
      return 0;
    v23 = NameTable::Match((const struct NamedInstanceBuilder *)((char *)a9 + 128), 5u, a3, a4, a5);
    if ( v23 != -1 )
    {
      v21 = (unsigned __int8 *)(*((_QWORD *)a9 + 17)
                              + (((unsigned __int64)*(unsigned __int8 *)(*((_QWORD *)a9 + 16) + 12LL * v23 + 10) << 8)
                               | *(unsigned __int8 *)(*((_QWORD *)a9 + 16) + 12LL * v23 + 11)));
      *(_DWORD *)OemCodePage = NameTable::GetStringByteCount(
                                 (const struct NamedInstanceBuilder *)((char *)a9 + 128),
                                 v23);
      v22 = 1;
    }
  }
  else
  {
    v13 = 0;
  }
  v73 -= (unsigned __int64)v19;
  v24 = v72;
  v25 = 0;
  v74 = 0;
  for ( i = 0; i < 4; ++i )
  {
    if ( v22 || v20 )
      break;
    v27 = v15;
    if ( (unsigned __int64)v15 >= v24 )
      continue;
    while ( !v22 )
    {
      v28 = v27[9] | (v27[8] << 8);
      if ( !v28 )
        goto LABEL_63;
      v29 = (v27[10] << 8) | v27[11];
      if ( v28 + v29 > v73 )
        goto LABEL_63;
      v22 = 0;
      switch ( i )
      {
        case 0:
          v32 = _byteswap_ushort(*((_WORD *)v27 + 2)) == a5;
LABEL_36:
          v25 = 0;
LABEL_37:
          LOBYTE(v25) = v32;
          break;
        case 1:
          if ( (unsigned __int8)a5 != 4 )
          {
            v32 = (unsigned __int16)v27[5] == (unsigned __int16)(unsigned __int8)a5;
            goto LABEL_36;
          }
          v33 = ConvertLangIDtoCodePage(_byteswap_ushort(*((_WORD *)v27 + 2)));
          v25 = 0;
          if ( v33 != AnsiCodePage[0] )
          {
LABEL_33:
            v32 = v31 == 9;
            goto LABEL_29;
          }
LABEL_28:
          v32 = v31 == 4;
LABEL_29:
          v24 = v72;
          goto LABEL_37;
        case 2:
          if ( (_BYTE)a5 != 4 )
          {
            v32 = v27[5] == 9;
            goto LABEL_36;
          }
          v30 = ConvertLangIDtoCodePage(_byteswap_ushort(*((_WORD *)v27 + 2)));
          v25 = 0;
          if ( v30 == AnsiCodePage[0] )
            goto LABEL_33;
          goto LABEL_28;
        case 3:
          v25 = 1;
          break;
      }
      if ( _byteswap_ushort(*(_WORD *)v27) == a3 && _byteswap_ushort(*((_WORD *)v27 + 1)) == a4 && v25 )
      {
        switch ( (v27[6] << 8) | v27[7] )
        {
          case 1:
            if ( *((_QWORD *)a6 + 1) )
              goto LABEL_57;
            *((_DWORD *)a6 + 4) = v28;
            *((_QWORD *)a6 + 1) = &v19[v29];
            v74 = v27;
            break;
          case 2:
            if ( !*((_QWORD *)a6 + 5) )
            {
              *((_DWORD *)a6 + 12) = v28;
              *((_QWORD *)a6 + 5) = &v19[v29];
            }
            break;
          case 3:
            if ( !*((_QWORD *)a6 + 7) )
            {
              *((_DWORD *)a6 + 16) = v28;
              *((_QWORD *)a6 + 7) = &v19[v29];
            }
            break;
          case 4:
            if ( !*((_QWORD *)a6 + 9) )
            {
              *((_DWORD *)a6 + 20) = v28;
              *((_QWORD *)a6 + 9) = &v19[v29];
            }
            break;
          default:
            if ( ((v27[6] << 8) | v27[7]) == 5 && !v21 )
            {
              v21 = &v19[v29];
              *(_DWORD *)OemCodePage = v28;
            }
            break;
        }
      }
      if ( *((_QWORD *)a6 + 1) )
      {
LABEL_57:
        if ( *((_QWORD *)a6 + 5) && *((_QWORD *)a6 + 7) && *((_QWORD *)a6 + 9) )
        {
          v13 = 1;
          if ( v21 )
            v22 = 1;
          goto LABEL_63;
        }
      }
      v13 = 0;
LABEL_63:
      v27 += 12;
      if ( (unsigned __int64)v27 >= v24 )
        break;
    }
    v15 = v75;
    v20 = a9;
  }
  if ( !v13 )
    return 0;
  v34 = a3;
  if ( a3 != 3 )
  {
    if ( !v20 )
      goto LABEL_87;
    goto LABEL_89;
  }
  if ( v20 )
  {
LABEL_89:
    *((_DWORD *)a6 + 23) = 212;
    *((_DWORD *)a6 + 24) = 352;
    v40 = 40 * (*((_DWORD *)v20 + 10) + 9);
LABEL_90:
    *((_DWORD *)a6 + 25) = v40;
    v41 = *((_DWORD *)a6 + 30) + v40;
    if ( *((_QWORD *)a6 + 3) )
    {
      v42 = *((_DWORD *)a6 + 31) + 4;
      *((_DWORD *)a6 + 26) = v41;
      v41 += v42;
    }
    v43 = v41 + 2;
    v44 = v43 + *((_DWORD *)a6 + 33);
    v45 = *((_DWORD *)a6 + 32) + 3;
    *((_DWORD *)a6 + 28) = v43;
    v46 = *((_DWORD *)a6 + 34) + 2;
    *((_DWORD *)a6 + 29) = v44;
    v47 = v44 + v46;
    *a7 = 0;
    *((_DWORD *)a6 + 27) = v47;
    v48 = (v47 + v45) & 0xFFFFFFFC;
    if ( v21 )
    {
      if ( v34 == 3 )
      {
        v49 = *(_DWORD *)OemCodePage;
        if ( *(_DWORD *)OemCodePage > 0x48u )
          v49 = 72;
        v50 = v49 - 2;
        if ( v49 <= 2 )
          v50 = v49;
        *a7 = memcmp_0(v21, qword_1400A4BF0, v50) == 0;
      }
      else
      {
        v53 = *(_DWORD *)OemCodePage;
        if ( *(_DWORD *)OemCodePage > 0x24u )
          v53 = 36;
        v54 = v53 - 1;
        if ( v53 <= 1 )
          v54 = v53;
        *a7 = strncmp_0((const char *)v21, "Converter: Windows Type 1 Installer", v54) == 0;
      }
    }
    v51 = fsSelectionTTFD(a1, a2, v20, a10);
    if ( (v51 & 0x21) != 0 )
    {
      if ( (v51 & 0x21) != 1 && (v51 & 0x21) != 0x20 )
      {
        v52 = v48;
        v48 = 0;
LABEL_111:
        *((_DWORD *)a6 + 1) = v48;
        *((_DWORD *)a6 + 21) = v52;
        v56 = v52 + 16;
        if ( *((_DWORD *)a2 + 16) )
        {
          if ( &a1[*((unsigned int *)a2 + 16)] )
          {
            *((_DWORD *)a6 + 22) = v56;
            v56 += 24;
          }
        }
        *a8 = 0;
        if ( !v20 )
        {
          switch ( *((_DWORD *)a6 + 16) )
          {
            case '8':
              v57 = (_BYTE *)*((_QWORD *)a6 + 7);
              v58 = "Microsoft Sans Serif Regular";
              v59 = 0;
              while ( 1 )
              {
                v60 = v57 + 1;
                if ( *v60 != *v58 )
                  break;
                ++v58;
                v57 = v60 + 1;
                if ( (unsigned int)++v59 >= 0x1C )
                {
                  *a8 = 1;
                  goto LABEL_130;
                }
              }
              break;
            case '0':
              v61 = (_BYTE *)*((_QWORD *)a6 + 7);
              v62 = "Microsoft Tahoma Regular";
              v63 = 0;
              while ( 1 )
              {
                v64 = v61 + 1;
                if ( *v64 != *v62 )
                  break;
                ++v62;
                v61 = v64 + 1;
                if ( (unsigned int)++v63 >= 0x18 )
                {
                  *a8 = 2;
                  goto LABEL_130;
                }
              }
              break;
            case '*':
              v65 = (_BYTE *)*((_QWORD *)a6 + 7);
              v66 = "Microsoft Tahoma Bold";
              v67 = 0;
              while ( 1 )
              {
                v68 = v65 + 1;
                if ( *v68 != *v66 )
                  break;
                ++v66;
                v65 = v68 + 1;
                if ( (unsigned int)++v67 >= 0x15 )
                {
                  *a8 = 3;
                  goto LABEL_130;
                }
              }
              break;
          }
        }
LABEL_130:
        result = 1;
        *(_DWORD *)a6 = (v56 + 7) & 0xFFFFFFF8;
        return result;
      }
      v55 = 1;
    }
    else
    {
      v55 = 3;
    }
    v52 = v48 + 4 * (v55 + 4 * v55 + 3);
    goto LABEL_111;
  }
  v35 = 0;
  v36 = 0;
  if ( (unsigned __int64)v15 >= v72 )
    goto LABEL_87;
  while ( 2 )
  {
    v37 = v15[9] | (v15[8] << 8);
    if ( !v37 )
      goto LABEL_84;
    v38 = (v15[10] << 8) | v15[11];
    if ( v37 + v38 > v73
      || _byteswap_ushort(*(_WORD *)v15) != 3
      || _byteswap_ushort(*((_WORD *)v15 + 1)) != a4
      || _byteswap_ushort(*((_WORD *)v15 + 3)) != 1
      || v74 == v15 )
    {
      goto LABEL_84;
    }
    v39 = v15[5];
    if ( v74[5] == 9 )
    {
      if ( v39 != 9 )
        goto LABEL_78;
LABEL_82:
      if ( !v35 )
      {
        v36 = v15[9] | (v15[8] << 8);
        v35 = &v19[v38];
      }
LABEL_84:
      v15 += 12;
      if ( (unsigned __int64)v15 >= v72 )
        goto LABEL_79;
      continue;
    }
    break;
  }
  if ( v39 != 9 )
    goto LABEL_82;
LABEL_78:
  v36 = v15[9] | (v15[8] << 8);
  v35 = &v19[v38];
LABEL_79:
  if ( v35 )
  {
    *((_QWORD *)a6 + 3) = v35;
    *((_DWORD *)a6 + 8) = v36;
  }
LABEL_87:
  if ( (unsigned int)bConvertExtras(0, a6) )
  {
    v34 = a3;
    *((_DWORD *)a6 + 23) = 208;
    v40 = 216;
    goto LABEL_90;
  }
  return 0;
}

```

## disassembly

```asm
0x140008a0c  mov     rax, rsp
0x140008a0f  mov     [rax+20h], r9w
0x140008a14  mov     [rax+18h], r8w
0x140008a19  mov     [rax+10h], rdx
0x140008a1d  mov     [rax+8], rcx
0x140008a21  push    rbx
0x140008a22  push    rbp
0x140008a23  push    rsi
0x140008a24  push    rdi
0x140008a25  push    r12
0x140008a27  push    r13
0x140008a29  push    r14
0x140008a2b  push    r15
0x140008a2d  sub     rsp, 68h
0x140008a31  mov     ebp, [rdx+3Ch]
0x140008a34  xor     eax, eax
0x140008a36  mov     [rsp+0A8h+AnsiCodePage], ax
0x140008a3b  movzx   r14d, r9w
0x140008a3f  movzx   esi, r8w
0x140008a43  cmp     ebp, 6
0x140008a46  jb      loc_14000920B
0x140008a4c  movzx   eax, r8w
0x140008a50  mov     r15d, 1
0x140008a56  sub     ax, r15w
0x140008a5a  mov     r8d, 0FFFDh
0x140008a60  test    r8w, ax
0x140008a64  jnz     loc_14000920B
0x140008a6a  mov     edi, [rdx+38h]
0x140008a6d  mov     r8d, 8Ch; Size
0x140008a73  mov     rbx, [rsp+0A8h+arg_28]
0x140008a7b  add     rdi, rcx
0x140008a7e  mov     rcx, rbx; void *
0x140008a81  xor     edx, edx; Val
0x140008a83  call    memset_0
0x140008a88  mov     [rbx+8Ch], si
0x140008a8f  lea     rsi, [rdi+6]
0x140008a93  mov     [rbx+8Eh], r14w
0x140008a9b  mov     [rsp+0A8h+var_58], rsi
0x140008aa0  cmp     rdi, rsi
0x140008aa3  ja      loc_14000920B
0x140008aa9  lea     rdx, [rdi+rbp]
0x140008aad  mov     r14d, ebp
0x140008ab0  mov     [rsp+0A8h+var_68], rdx
0x140008ab5  cmp     rsi, rdx
0x140008ab8  ja      loc_14000920B
0x140008abe  movzx   eax, byte ptr [rdi+3]
0x140008ac2  movzx   ecx, byte ptr [rdi+2]
0x140008ac6  shl     rcx, 8
0x140008aca  or      rcx, rax
0x140008acd  lea     rax, [rcx+rcx*2]
0x140008ad1  lea     rcx, [rsi+rax*4]
0x140008ad5  mov     [rsp+0A8h+var_70], rcx
0x140008ada  cmp     rsi, rcx
0x140008add  ja      loc_14000920B
0x140008ae3  movzx   eax, byte ptr [rdi+4]
0x140008ae7  movzx   ebp, byte ptr [rdi+5]
0x140008aeb  shl     rax, 8
0x140008aef  or      rbp, rax
0x140008af2  add     rbp, rdi
0x140008af5  cmp     rcx, rbp
0x140008af8  ja      loc_14000920B
0x140008afe  cmp     rbp, rdx
0x140008b01  ja      loc_14000920B
0x140008b07  lea     rdx, [rsp+0A8h+AnsiCodePage]; AnsiCodePage
0x140008b0c  lea     rcx, [rsp+0A8h+OemCodePage]; OemCodePage
0x140008b11  call    EngGetCurrentCodePage
0x140008b16  movzx   eax, byte ptr [rdi+3]
0x140008b1a  movzx   ecx, byte ptr [rdi+2]
0x140008b1e  shl     rcx, 8
0x140008b22  or      rcx, rax
0x140008b25  lea     rax, [rcx+rcx*2]
0x140008b29  lea     rax, ds:6[rax*4]
0x140008b31  cmp     r14, rax
0x140008b34  jb      loc_14000920B
0x140008b3a  mov     r13, [rsp+0A8h+arg_40]
0x140008b42  xor     r10d, r10d
0x140008b45  mov     edi, [rsp+0A8h+arg_48]
0x140008b4c  xor     r12d, r12d
0x140008b4f  xor     r14d, r14d
0x140008b52  mov     dword ptr [rsp+0A8h+OemCodePage], r10d
0x140008b57  test    r13, r13
0x140008b5a  jz      loc_140008C31
0x140008b60  xor     r9d, r9d; unsigned int
0x140008b63  xor     r8d, r8d; wchar_t *
0x140008b66  mov     edx, edi; unsigned int
0x140008b68  mov     rcx, r13; this
0x140008b6b  call    ?GetInstanceFamilyName@NamedInstanceBuilder@@QEBAIIPEA_WI@Z; NamedInstanceBuilder::GetInstanceFamilyName(uint,wchar_t *,uint)
0x140008b70  add     eax, eax
0x140008b72  xor     r9d, r9d; unsigned int
0x140008b75  xor     r8d, r8d; wchar_t *
0x140008b78  mov     [rbx+78h], eax
0x140008b7b  mov     edx, edi; unsigned int
0x140008b7d  mov     rcx, r13; this
0x140008b80  call    ?GetInstanceSubFamilyName@NamedInstanceBuilder@@QEBAIIPEA_WI@Z; NamedInstanceBuilder::GetInstanceSubFamilyName(uint,wchar_t *,uint)
0x140008b85  add     eax, eax
0x140008b87  xor     r9d, r9d; unsigned int
0x140008b8a  xor     r8d, r8d; wchar_t *
0x140008b8d  mov     [rbx+80h], eax
0x140008b93  mov     edx, edi; unsigned int
0x140008b95  mov     rcx, r13; this
0x140008b98  call    ?GetInstanceFullName@NamedInstanceBuilder@@QEBAIIPEA_WI@Z; NamedInstanceBuilder::GetInstanceFullName(uint,wchar_t *,uint)
0x140008b9d  add     eax, eax
0x140008b9f  xor     r9d, r9d; unsigned int
0x140008ba2  xor     r8d, r8d; wchar_t *
0x140008ba5  mov     [rbx+88h], eax
0x140008bab  mov     edx, edi; unsigned int
0x140008bad  mov     rcx, r13; this
0x140008bb0  call    ?GetInstanceFullName@NamedInstanceBuilder@@QEBAIIPEA_WI@Z; NamedInstanceBuilder::GetInstanceFullName(uint,wchar_t *,uint)
0x140008bb5  add     eax, eax
0x140008bb7  mov     [rbx+84h], eax
0x140008bbd  cmp     [rbx+78h], r12d
0x140008bc1  jz      loc_14000920B
0x140008bc7  movzx   eax, [rsp+0A8h+arg_20]
0x140008bcf  lea     rdi, [r13+80h]
0x140008bd6  movzx   r9d, [rsp+0A8h+arg_18]; unsigned __int16
0x140008bdf  lea     edx, [r15+4]; unsigned __int16
0x140008be3  movzx   r8d, [rsp+0A8h+arg_10]; unsigned __int16
0x140008bec  mov     rcx, rdi; this
0x140008bef  mov     [rsp+0A8h+var_88], ax; unsigned __int16
0x140008bf4  call    ?Match@NameTable@@QEBAIGGGG@Z; NameTable::Match(ushort,ushort,ushort,ushort)
0x140008bf9  mov     ecx, eax
0x140008bfb  cmp     eax, 0FFFFFFFFh
0x140008bfe  jz      short loc_140008C34
0x140008c00  mov     rdx, [rdi]
0x140008c03  lea     r8, [rcx+rcx*2]
0x140008c07  movzx   r12d, byte ptr [rdx+r8*4+0Bh]
0x140008c0d  movzx   edx, byte ptr [rdx+r8*4+0Ah]
0x140008c13  shl     rdx, 8
0x140008c17  or      r12, rdx
0x140008c1a  mov     edx, ecx; unsigned int
0x140008c1c  add     r12, [rdi+8]
0x140008c20  mov     rcx, rdi; this
0x140008c23  call    ?GetStringByteCount@NameTable@@QEBAII@Z; NameTable::GetStringByteCount(uint)
0x140008c28  mov     dword ptr [rsp+0A8h+OemCodePage], eax
0x140008c2c  mov     r14d, r15d
0x140008c2f  jmp     short loc_140008C34
0x140008c31  xor     r15d, r15d
0x140008c34  sub     [rsp+0A8h+var_68], rbp
0x140008c39  xor     ecx, ecx
0x140008c3b  mov     r9, [rsp+0A8h+var_70]
0x140008c40  xor     r8d, r8d
0x140008c43  mov     [rsp+0A8h+var_60], rcx
0x140008c48  xor     edi, edi
0x140008c4a  lea     eax, [rcx+4]
0x140008c4d  test    r14d, r14d
0x140008c50  jnz     loc_140008EB3
0x140008c56  test    r13, r13
0x140008c59  jnz     loc_140008EB3
0x140008c5f  mov     rdx, rsi
0x140008c62  cmp     rsi, r9
0x140008c65  jnb     loc_140008EA9
0x140008c6b  movzx   r13d, [rsp+0A8h+arg_20]
0x140008c74  movzx   esi, [rsp+0A8h+arg_10]
0x140008c7c  test    r14d, r14d
0x140008c7f  jnz     loc_140008E97
0x140008c85  movzx   r10d, byte ptr [rdx+8]
0x140008c8a  movzx   eax, byte ptr [rdx+9]
0x140008c8e  shl     r10d, 8
0x140008c92  or      r10d, eax
0x140008c95  jz      loc_140008E8A
0x140008c9b  movzx   eax, byte ptr [rdx+0Ah]
0x140008c9f  movzx   r11d, byte ptr [rdx+0Bh]
0x140008ca4  shl     eax, 8
0x140008ca7  or      r11d, eax
0x140008caa  lea     ecx, [r10+r11]
0x140008cae  cmp     rcx, [rsp+0A8h+var_68]
0x140008cb3  ja      loc_140008E8A
0x140008cb9  xor     r14d, r14d
0x140008cbc  mov     ecx, edi
0x140008cbe  test    edi, edi
0x140008cc0  jz      loc_140008D73
0x140008cc6  sub     ecx, 1
0x140008cc9  jz      short loc_140008D24
0x140008ccb  sub     ecx, 1
0x140008cce  jz      short loc_140008CE1
0x140008cd0  cmp     ecx, 1
0x140008cd3  jnz     loc_140008D8D
0x140008cd9  mov     r8d, ecx
0x140008cdc  jmp     loc_140008D8D
0x140008ce1  mov     r15d, 4
0x140008ce7  cmp     r13b, r15b
0x140008cea  jnz     short loc_140008D1E
0x140008cec  movzx   eax, byte ptr [rdx+4]
0x140008cf0  movzx   r9d, byte ptr [rdx+5]
0x140008cf5  shl     ax, 8
0x140008cf9  or      r9w, ax
0x140008cfd  movzx   ecx, r9w; unsigned __int16
0x140008d01  call    ?ConvertLangIDtoCodePage@@YAKG@Z; ConvertLangIDtoCodePage(ushort)
0x140008d06  mov     ecx, eax
0x140008d08  mov     r8d, r14d
0x140008d0b  movzx   eax, [rsp+0A8h+AnsiCodePage]
0x140008d10  cmp     ecx, eax
0x140008d12  jz      short loc_140008D64
0x140008d14  cmp     r9b, r15b
0x140008d17  mov     r9, [rsp+0A8h+var_70]
0x140008d1c  jmp     short loc_140008D89
0x140008d1e  cmp     byte ptr [rdx+5], 9
0x140008d22  jmp     short loc_140008D86
0x140008d24  mov     eax, 0FFh
0x140008d29  movzx   ecx, r13w
0x140008d2d  and     cx, ax
0x140008d30  mov     r15d, 4
0x140008d36  cmp     cx, r15w
0x140008d3a  jnz     short loc_140008D6A
0x140008d3c  movzx   eax, byte ptr [rdx+4]
0x140008d40  movzx   r9d, byte ptr [rdx+5]
0x140008d45  shl     ax, 8
0x140008d49  or      r9w, ax
0x140008d4d  movzx   ecx, r9w; unsigned __int16
0x140008d51  call    ?ConvertLangIDtoCodePage@@YAKG@Z; ConvertLangIDtoCodePage(ushort)
0x140008d56  mov     ecx, eax
0x140008d58  mov     r8d, r14d
0x140008d5b  movzx   eax, [rsp+0A8h+AnsiCodePage]
0x140008d60  cmp     ecx, eax
0x140008d62  jz      short loc_140008D14
0x140008d64  cmp     r9b, 9
0x140008d68  jmp     short loc_140008D17
0x140008d6a  movzx   eax, byte ptr [rdx+5]
0x140008d6e  cmp     ax, cx
0x140008d71  jmp     short loc_140008D86
0x140008d73  movzx   ecx, byte ptr [rdx+4]
0x140008d77  movzx   eax, byte ptr [rdx+5]
0x140008d7b  shl     cx, 8
0x140008d7f  or      cx, ax
0x140008d82  cmp     cx, r13w
0x140008d86  mov     r8d, r14d
0x140008d89  setz    r8b
0x140008d8d  movzx   ecx, byte ptr [rdx]
0x140008d90  movzx   eax, byte ptr [rdx+1]
0x140008d94  shl     cx, 8
0x140008d98  or      cx, ax
0x140008d9b  cmp     cx, si
0x140008d9e  jnz     loc_140008E5D
0x140008da4  movzx   eax, byte ptr [rdx+2]
0x140008da8  movzx   ecx, byte ptr [rdx+3]
0x140008dac  shl     ax, 8
0x140008db0  or      cx, ax
0x140008db3  cmp     cx, [rsp+0A8h+arg_18]
0x140008dbb  jnz     loc_140008E5D
0x140008dc1  test    r8d, r8d
0x140008dc4  jz      loc_140008E5D
0x140008dca  movzx   eax, byte ptr [rdx+6]
0x140008dce  movzx   ecx, byte ptr [rdx+7]
0x140008dd2  shl     eax, 8
0x140008dd5  or      ecx, eax
0x140008dd7  sub     ecx, 1
0x140008dda  jz      short loc_140008E44
0x140008ddc  sub     ecx, 1
0x140008ddf  jz      short loc_140008E2E
0x140008de1  sub     ecx, 1
0x140008de4  jz      short loc_140008E18
0x140008de6  sub     ecx, 1
0x140008de9  jz      short loc_140008E02
0x140008deb  cmp     ecx, 1
0x140008dee  jnz     short loc_140008E5D
0x140008df0  test    r12, r12
0x140008df3  jnz     short loc_140008E5D
0x140008df5  mov     r12d, r11d
0x140008df8  add     r12, rbp
0x140008dfb  mov     dword ptr [rsp+0A8h+OemCodePage], r10d
0x140008e00  jmp     short loc_140008E5D
0x140008e02  cmp     [rbx+48h], r14
0x140008e06  jnz     short loc_140008E5D
0x140008e08  mov     eax, r11d
0x140008e0b  add     rax, rbp
0x140008e0e  mov     [rbx+50h], r10d
0x140008e12  mov     [rbx+48h], rax
0x140008e16  jmp     short loc_140008E5D
0x140008e18  cmp     [rbx+38h], r14
0x140008e1c  jnz     short loc_140008E5D
0x140008e1e  mov     eax, r11d
0x140008e21  add     rax, rbp
0x140008e24  mov     [rbx+40h], r10d
0x140008e28  mov     [rbx+38h], rax
0x140008e2c  jmp     short loc_140008E5D
0x140008e2e  cmp     [rbx+28h], r14
0x140008e32  jnz     short loc_140008E5D
0x140008e34  mov     eax, r11d
0x140008e37  add     rax, rbp
0x140008e3a  mov     [rbx+30h], r10d
0x140008e3e  mov     [rbx+28h], rax
0x140008e42  jmp     short loc_140008E5D
0x140008e44  cmp     [rbx+8], r14
0x140008e48  jnz     short loc_140008E63
0x140008e4a  mov     eax, r11d
0x140008e4d  add     rax, rbp
0x140008e50  mov     [rbx+10h], r10d
0x140008e54  mov     [rbx+8], rax
0x140008e58  mov     [rsp+0A8h+var_60], rdx
0x140008e5d  cmp     [rbx+8], r14
0x140008e61  jz      short loc_140008E87
0x140008e63  cmp     [rbx+28h], r14
0x140008e67  jz      short loc_140008E87
0x140008e69  cmp     [rbx+38h], r14
0x140008e6d  jz      short loc_140008E87
0x140008e6f  cmp     [rbx+48h], r14
0x140008e73  jz      short loc_140008E87
0x140008e75  mov     eax, 1
0x140008e7a  mov     r15d, eax
0x140008e7d  test    r12, r12
  ... truncated ...
```
