# InternalStringOut(tag_STRING_ANALYSIS *,int,int,uint,tagRECT const *)

- ea: `0x180011a70`
- end: `0x180011fb8`
- name: `?InternalStringOut@@YAJPEAUtag_STRING_ANALYSIS@@HHIPEBUtagRECT@@@Z`
- size: `1352`
- prototype: `__int64 __usercall@<rax>(struct tag_STRING_ANALYSIS *@<rcx>, int@<edx>, int@<r8d>, unsigned int@<r9d>, const struct tagRECT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180011770`
- `0x180058f1c`

## callees

- `0x180005fac`
- `0x180010e60`
- `0x180011a70`
- `0x180011fc0`
- `0x180014240`
- `0x180014710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d4b`
- `GDI32!ExtTextOutA` at `0x180011eca`
- `GDI32!ExtTextOutA` at `0x180011eca`
- `GDI32!ExtTextOutW` at `0x180011c72`
- `GDI32!ExtTextOutW` at `0x180011f63`
- `GDI32!ExtTextOutW` at `0x180011c72`
- `GDI32!ExtTextOutW` at `0x180011f63`
- `GDI32!SelectObject` at `0x180011bd4`
- `GDI32!SelectObject` at `0x180011f95`
- `GDI32!SelectObject` at `0x180011bd4`
- `GDI32!SelectObject` at `0x180011f95`
- `GDI32!SetBkMode` at `0x180011f80`
- `GDI32!SetBkMode` at `0x180011fad`
- `GDI32!SetBkMode` at `0x180011f80`
- `GDI32!SetBkMode` at `0x180011fad`
- `TextShaping!ShapingGetCombiningOptions` at `0x180011dc3`
- `TextShaping!ShapingGetCombiningOptions` at `0x180011dc3`

## pseudocode

```c
__int64 __fastcall InternalStringOut(struct tag_STRING_ANALYSIS *a1, int a2, int a3, int a4, struct tagRECT *lprect)
{
  UINT fuOptions; // r12d
  int v7; // ecx
  __int64 v8; // rax
  int v9; // r10d
  unsigned __int8 *v10; // rax
  int v11; // ebp
  unsigned int v12; // r14d
  __int64 v13; // rdx
  __int64 v14; // r15
  const RECT *lprc; // rsi
  int BkMode; // edi
  int v17; // ebp
  unsigned int v18; // esi
  __int64 v20; // rax
  __int64 v21; // rsi
  void **v22; // r15
  __int64 v23; // rcx
  __int64 v24; // rcx
  HDC v25; // rdi
  __int64 v26; // r9
  int v27; // eax
  __int64 v28; // rax
  DWORD ObjectType; // eax
  int v30; // [rsp+70h] [rbp-48h]
  INT v31; // [rsp+C0h] [rbp+8h] BYREF
  int x; // [rsp+C8h] [rbp+10h]
  int y; // [rsp+D0h] [rbp+18h]

  y = a3;
  x = a2;
  fuOptions = a4;
  v7 = *((_DWORD *)a1 + 2);
  v8 = 64;
  v9 = *((_DWORD *)a1 + 100);
  if ( (v7 & 8) == 0 )
    v8 = 424;
  v31 = *(_DWORD *)((char *)a1 + v8);
  if ( v9 <= 0 )
  {
    ExtTextOutW(*(HDC *)a1, a2, a3, a4 & 0xFFFFEFEF | 0x1000, lprect, *((LPCWSTR *)a1 + 6), 0, 0);
    return 0;
  }
  else if ( (v7 & 0x40000000) != 0 )
  {
    ExtTextOutA(
      *(HDC *)a1,
      a2,
      a3,
      a4 | 0x10,
      lprect,
      (LPCSTR)(*(_QWORD *)(*((_QWORD *)a1 + 55) + 80LL) + 280LL),
      1u,
      &v31);
    return 0;
  }
  else if ( (v7 & 0xC00) != 0 )
  {
    return MultiPartStringOut(a1, a2, a3, a4, lprect);
  }
  else
  {
    v10 = (unsigned __int8 *)*((_QWORD *)a1 + 27);
    v11 = 0;
    if ( v10 )
      v12 = *v10;
    else
      v12 = 0;
    v13 = *((_QWORD *)a1 + 55);
    v14 = v12;
    if ( *(_DWORD *)(*((_QWORD *)a1 + v12 + 55) + 48LL) == *(_DWORD *)(v13 + 48) )
    {
      if ( v9 > 1 && *(int *)(*(_QWORD *)(v13 + 80) + 316LL) > 0 )
      {
        v30 = (*(unsigned __int16 *)(*((_QWORD *)a1 + 13) + 4LL) >> 11) & 1;
        while ( 1 )
        {
          if ( v11 >= *((_DWORD *)a1 + 100) )
          {
            a3 = y;
            v14 = v12;
            break;
          }
          if ( *(__int16 *)(*((_QWORD *)a1 + 13) + 8LL * v11 + 4) < 0 )
            return MultiPartStringOut(a1, x, y, fuOptions, lprect);
          v20 = *((_QWORD *)a1 + 27);
          if ( !v20 || *(unsigned __int8 *)(v20 + v11) != v12 )
            return MultiPartStringOut(a1, x, y, fuOptions, lprect);
          v21 = *(_WORD *)(*((_QWORD *)a1 + 13) + 8LL * v11 + 4) & 0x3FF;
          v22 = (void **)((char *)a1 + 8 * *((int *)a1 + 84) + 440);
          if ( !v22 )
            goto LABEL_38;
          if ( *v22 )
          {
            v23 = *((_QWORD *)*v22 + 10);
            if ( v23 )
            {
              if ( (unsigned int)v21 >= 0xE1 )
                goto LABEL_38;
              v24 = *(_QWORD *)(v23 + 8 * v21 + 344);
              if ( !v24 )
                goto LABEL_38;
              if ( v24 != -1 )
                goto LABEL_32;
            }
          }
          v25 = *(HDC *)a1;
          EnterCriticalSection(&csCache);
          LODWORD(v25) = UpdateCache(v22, v21, v25);
          LeaveCriticalSection(&csCache);
          if ( (int)v25 >= 0 )
          {
LABEL_32:
            v26 = (unsigned int)v21;
            v27 = *(_DWORD *)(*((_QWORD *)*v22 + 10) + 4 * ((unsigned __int64)(unsigned int)v21 >> 5) + 248);
            if ( _bittest(&v27, (unsigned __int8)((int)v21 % 32)) )
              goto LABEL_33;
          }
LABEL_38:
          v26 = (unsigned int)v21;
          if ( (char *)funcs_180014CAF[3 * v21] != (char *)ShlTextOut )
            return MultiPartStringOut(a1, x, y, fuOptions, lprect);
LABEL_33:
          if ( (_DWORD)v21 == 19
            || (ShapingGetCombiningOptions(*((unsigned __int16 *)&ShlScriptSupport + 4 * v26), 1) & 2) == 0 )
          {
            return MultiPartStringOut(a1, x, y, fuOptions, lprect);
          }
          v28 = *((_QWORD *)a1 + 17);
          if ( v30 )
          {
            if ( *(unsigned __int16 *)(*((_QWORD *)a1 + 16) + 2LL * v11) + *(unsigned __int16 *)(v28 + 2LL * v11) != *(unsigned __int16 *)(*((_QWORD *)a1 + 16) + 2 * (v11 - 1LL)) )
              return MultiPartStringOut(a1, x, y, fuOptions, lprect);
          }
          else if ( *(unsigned __int16 *)(*((_QWORD *)a1 + 16) + 2LL * v11) != *(unsigned __int16 *)(*((_QWORD *)a1 + 16) + 2LL * v11 - 2)
                                                                             + *(unsigned __int16 *)(v28 + 2LL * v11 - 2) )
          {
            return MultiPartStringOut(a1, x, y, fuOptions, lprect);
          }
          ++v11;
        }
      }
      lprc = lprect;
      BkMode = 1;
      if ( v12 )
      {
        if ( *((_QWORD *)a1 + 173) && (*((_BYTE *)a1 + 361) || *((_BYTE *)a1 + 362)) )
        {
          ObjectType = GetObjectType(*(HGDIOBJ *)a1);
          v17 = x;
          ExtTextOutW(
            *(HDC *)a1,
            x,
            y,
            (((ObjectType - 4) & 0xFFFFFFF7) != 0 ? 0x1000 : 0) | fuOptions & 0xFFFFFFEF,
            lprc,
            L" ",
            1u,
            &v31);
          BkMode = GetBkMode(*(HDC *)a1);
          if ( BkMode == 2 )
            SetBkMode(*(HDC *)a1, 1);
          fuOptions &= ~2u;
        }
        else
        {
          v17 = x;
        }
        SelectObject(*(HDC *)a1, *((HGDIOBJ *)a1 + v14 + 114));
        a3 = y;
      }
      else
      {
        v17 = x;
      }
      v18 = ScriptTextOut(
              *(const HDC *)a1,
              (SCRIPT_CACHE *)a1 + v14 + 55,
              v17,
              a3,
              fuOptions,
              lprc,
              (const SCRIPT_ANALYSIS *)(*((_QWORD *)a1 + 13) + 4LL),
              *((const WCHAR **)a1 + 6),
              *((_DWORD *)a1 + 14),
              *((const WORD **)a1 + 20),
              *((_DWORD *)a1 + 101),
              *((const int **)a1 + 23),
              *((const int **)a1 + 24),
              *((const GOFFSET **)a1 + 25));
      if ( v12 )
        SelectObject(*(HDC *)a1, *((HGDIOBJ *)a1 + 114));
      if ( BkMode != 1 )
        SetBkMode(*(HDC *)a1, BkMode);
      return v18;
    }
    else
    {
      return MultiPartStringOut(a1, x, y, fuOptions, lprect);
    }
  }
}

```

## disassembly

```asm
0x180011a70  mov     r11, rsp
0x180011a73  mov     [r11+18h], r8d
0x180011a77  mov     [rsp+x], edx
0x180011a7b  push    rbx
0x180011a7c  push    rbp
0x180011a7d  push    r12
0x180011a7f  sub     rsp, 0A0h
0x180011a86  mov     rbx, rcx
0x180011a89  mov     r12d, r9d
0x180011a8c  mov     ecx, [rcx+8]
0x180011a8f  mov     eax, 40h ; '@'
0x180011a94  test    cl, 8
0x180011a97  mov     r9d, 1A8h
0x180011a9d  mov     r10d, [rbx+190h]
0x180011aa4  cmovz   eax, r9d
0x180011aa8  mov     eax, [rax+rbx]
0x180011aab  mov     [r11+8], eax
0x180011aaf  test    r10d, r10d
0x180011ab2  jle     loc_180011C42
0x180011ab8  bt      ecx, 1Eh
0x180011abc  jb      loc_180011E87
0x180011ac2  test    ecx, 0C00h
0x180011ac8  jnz     loc_180011E25
0x180011ace  mov     rax, [rbx+0D8h]
0x180011ad5  xor     ebp, ebp
0x180011ad7  mov     [r11-30h], r14
0x180011adb  mov     [r11-38h], r15
0x180011adf  test    rax, rax
0x180011ae2  jz      loc_180011EDE
0x180011ae8  movzx   r14d, byte ptr [rax]
0x180011aec  mov     rdx, [rbx+1B8h]
0x180011af3  mov     [rsp+0B8h+arg_18], rsi
0x180011afb  mov     r15d, r14d
0x180011afe  mov     [rsp+0B8h+var_20], rdi
0x180011b06  mov     eax, [rdx+30h]
0x180011b09  mov     [rsp+0B8h+var_28], r13
0x180011b11  mov     rcx, [rbx+r15*8+1B8h]
0x180011b19  cmp     [rcx+30h], eax
0x180011b1c  jnz     loc_180011C19
0x180011b22  cmp     r10d, 1
0x180011b26  jg      loc_180011C86
0x180011b2c  mov     rsi, [rsp+0B8h+lprect]
0x180011b34  mov     edi, 1
0x180011b39  test    r14d, r14d
0x180011b3c  jnz     loc_180011EE6
0x180011b42  mov     ebp, [rsp+0B8h+x]
0x180011b49  mov     rax, [rbx+0C8h]
0x180011b50  lea     rdx, [rbx+1B8h]
0x180011b57  mov     rcx, [rbx+68h]
0x180011b5b  lea     rdx, [rdx+r15*8]; psc
0x180011b5f  mov     [rsp+0B8h+pGoffset], rax; pGoffset
0x180011b64  add     rcx, 4
0x180011b68  mov     rax, [rbx+0C0h]
0x180011b6f  mov     r9d, r8d; y
0x180011b72  mov     [rsp+0B8h+piJustify], rax; piJustify
0x180011b77  mov     r8d, ebp; x
0x180011b7a  mov     rax, [rbx+0B8h]
0x180011b81  mov     [rsp+0B8h+piAdvance], rax; piAdvance
0x180011b86  mov     eax, [rbx+194h]
0x180011b8c  mov     [rsp+0B8h+cGlyphs], eax; cGlyphs
0x180011b90  mov     rax, [rbx+0A0h]
0x180011b97  mov     [rsp+0B8h+pwGlyphs], rax; pwGlyphs
0x180011b9c  mov     eax, [rbx+38h]
0x180011b9f  mov     [rsp+0B8h+iReserved], eax; iReserved
0x180011ba3  mov     rax, [rbx+30h]
0x180011ba7  mov     [rsp+0B8h+pwcReserved], rax; pwcReserved
0x180011bac  mov     [rsp+0B8h+psa], rcx; psa
0x180011bb1  mov     rcx, [rbx]; hdc
0x180011bb4  mov     [rsp+0B8h+lprc], rsi; lprc
0x180011bb9  mov     [rsp+0B8h+fuOptions], r12d; fuOptions
0x180011bbe  call    ScriptTextOut
0x180011bc3  mov     esi, eax
0x180011bc5  test    r14d, r14d
0x180011bc8  jz      short loc_180011BDA
0x180011bca  mov     rdx, [rbx+390h]; h
0x180011bd1  mov     rcx, [rbx]; hdc
0x180011bd4  call    cs:__imp_SelectObject
0x180011bda  cmp     edi, 1
0x180011bdd  jnz     loc_180011FA8
0x180011be3  mov     eax, esi
0x180011be5  mov     rdi, [rsp+0B8h+var_20]
0x180011bed  mov     r13, [rsp+0B8h+var_28]
0x180011bf5  mov     rsi, [rsp+0B8h+arg_18]
0x180011bfd  mov     r14, [rsp+0B8h+var_30]
0x180011c05  mov     r15, [rsp+0B8h+var_38]
0x180011c0d  add     rsp, 0A0h
0x180011c14  pop     r12
0x180011c16  pop     rbp
0x180011c17  pop     rbx
0x180011c18  retn
0x180011c19  mov     rax, [rsp+0B8h+lprect]
0x180011c21  mov     r9d, r12d; unsigned int
0x180011c24  mov     r8d, [rsp+0B8h+y]; y
0x180011c2c  mov     rcx, rbx; struct tag_STRING_ANALYSIS *
0x180011c2f  mov     edx, [rsp+0B8h+x]; x
0x180011c36  mov     qword ptr [rsp+0B8h+fuOptions], rax; struct tagRECT *
0x180011c3b  call    ?MultiPartStringOut@@YAJPEAUtag_STRING_ANALYSIS@@HHIPEBUtagRECT@@@Z; MultiPartStringOut(tag_STRING_ANALYSIS *,int,int,uint,tagRECT const *)
0x180011c40  jmp     short loc_180011BE5
0x180011c42  mov     rax, [rbx+30h]
0x180011c46  xor     ebp, ebp
0x180011c48  mov     rcx, [rbx]; hdc
0x180011c4b  and     r12d, 0FFFFFFEFh
0x180011c4f  mov     [rsp+0B8h+pwcReserved], rbp; lpDx
0x180011c54  bts     r12d, 0Ch
0x180011c59  mov     dword ptr [rsp+0B8h+psa], ebp; c
0x180011c5d  mov     r9d, r12d; options
0x180011c60  mov     [rsp+0B8h+lprc], rax; lpString
0x180011c65  mov     rax, [rsp+0B8h+lprect]
0x180011c6d  mov     qword ptr [rsp+0B8h+fuOptions], rax; lprect
0x180011c72  call    cs:__imp_ExtTextOutW
0x180011c78  xor     eax, eax
0x180011c7a  add     rsp, 0A0h
0x180011c81  pop     r12
0x180011c83  pop     rbp
0x180011c84  pop     rbx
0x180011c85  retn
0x180011c86  mov     rax, [rdx+50h]
0x180011c8a  cmp     [rax+13Ch], ebp
0x180011c90  jle     loc_180011B2C
0x180011c96  mov     rax, [rbx+68h]
0x180011c9a  movzx   eax, word ptr [rax+4]
0x180011c9e  shr     eax, 0Bh
0x180011ca1  and     eax, 1
0x180011ca4  mov     [rsp+0B8h+var_48], eax
0x180011ca8  lea     r10, __ImageBase
0x180011caf  cmp     ebp, [rbx+190h]
0x180011cb5  jge     loc_180011E49
0x180011cbb  mov     rax, [rbx+68h]
0x180011cbf  movsxd  r13, ebp
0x180011cc2  movzx   esi, word ptr [rax+r13*8+4]
0x180011cc8  test    si, si
0x180011ccb  js      loc_180011C19
0x180011cd1  mov     rax, [rbx+0D8h]
0x180011cd8  test    rax, rax
0x180011cdb  jz      loc_180011C19
0x180011ce1  movzx   eax, byte ptr [rax+r13]
0x180011ce6  cmp     eax, r14d
0x180011ce9  jnz     loc_180011C19
0x180011cef  movsxd  r15, dword ptr [rbx+150h]
0x180011cf6  and     esi, 3FFh
0x180011cfc  add     r15, 37h ; '7'
0x180011d00  lea     r15, [rbx+r15*8]
0x180011d04  test    r15, r15
0x180011d07  jz      loc_180011E08
0x180011d0d  mov     rax, [r15]
0x180011d10  test    rax, rax
0x180011d13  jz      short loc_180011D41
0x180011d15  mov     rcx, [rax+50h]
0x180011d19  test    rcx, rcx
0x180011d1c  jz      short loc_180011D41
0x180011d1e  cmp     esi, 0E1h
0x180011d24  jnb     loc_180011E08
0x180011d2a  mov     rcx, [rcx+rsi*8+158h]
0x180011d32  test    rcx, rcx
0x180011d35  jz      loc_180011E08
0x180011d3b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011d3f  jnz     short loc_180011D7C
0x180011d41  mov     rdi, [rbx]
0x180011d44  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180011d4b  call    cs:__imp_EnterCriticalSection
0x180011d51  mov     r8, rdi; HDC
0x180011d54  mov     edx, esi; int
0x180011d56  mov     rcx, r15; void **
0x180011d59  call    ?UpdateCache@@YAJPEAPEAXHPEAUHDC__@@@Z; UpdateCache(void * *,int,HDC__ *)
0x180011d5e  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180011d65  mov     edi, eax
0x180011d67  call    cs:__imp_LeaveCriticalSection
0x180011d6d  lea     r10, __ImageBase
0x180011d74  test    edi, edi
0x180011d76  js      loc_180011E08
0x180011d7c  mov     rax, [r15]
0x180011d7f  mov     edx, esi
0x180011d81  shr     rdx, 5
0x180011d85  mov     r9d, esi
0x180011d88  mov     r8, [rax+50h]
0x180011d8c  mov     eax, esi
0x180011d8e  and     eax, 8000001Fh
0x180011d93  jge     short loc_180011D9C
0x180011d95  dec     eax
0x180011d97  or      eax, 0FFFFFFE0h
0x180011d9a  inc     eax
0x180011d9c  movzx   ecx, al
0x180011d9f  mov     eax, [r8+rdx*4+0F8h]
0x180011da7  bt      eax, ecx
0x180011daa  jnb     short loc_180011E08
0x180011dac  cmp     esi, 13h
0x180011daf  jz      loc_180011C19
0x180011db5  movzx   ecx, ds:rva ?ShlScriptSupport@@3QBUSHAPING_LIBRARY_XREF@@B[r10+r9*8]; SHAPING_LIBRARY_XREF const near * const ShlScriptSupport ...
0x180011dbe  mov     edx, 1
0x180011dc3  call    cs:__imp_ShapingGetCombiningOptions
0x180011dc9  test    al, 2
0x180011dcb  jz      loc_180011C19
0x180011dd1  cmp     [rsp+0B8h+var_48], 0
0x180011dd6  mov     rax, [rbx+88h]
0x180011ddd  jnz     short loc_180011E59
0x180011ddf  movzx   ecx, word ptr [rax+r13*2-2]
0x180011de5  mov     rdx, [rbx+80h]; x
0x180011dec  movzx   eax, word ptr [rdx+r13*2-2]
0x180011df2  add     ecx, eax
0x180011df4  movzx   eax, word ptr [rdx+r13*2]
0x180011df9  cmp     eax, ecx
0x180011dfb  jnz     loc_180011C19
0x180011e01  inc     ebp
0x180011e03  jmp     loc_180011CA8
0x180011e08  lea     rax, [rsi+rsi*2]
0x180011e0c  mov     r9d, esi
0x180011e0f  lea     rcx, ?ShlTextOut@@YAJPEAUHDC__@@PEAPEAXHHIPEBUtagRECT@@PEBUtag_SCRIPT_ANALYSIS@@PEBGHPEBH5PEBUtagGOFFSET@@@Z; ShlTextOut(HDC__ *,void * *,int,int,uint,tagRECT const *,tag_SCRIPT_ANALYSIS const *,ushort const *,int,int const *,int const *,tagGOFFSET const *)
0x180011e16  cmp     ds:rva funcs_180014CAF[r10+rax*8], rcx
0x180011e1e  jz      short loc_180011DAC
0x180011e20  jmp     loc_180011C19
0x180011e25  mov     rax, [rsp+0B8h+lprect]
0x180011e2d  mov     r9d, r12d; unsigned int
0x180011e30  mov     rcx, rbx; struct tag_STRING_ANALYSIS *
0x180011e33  mov     qword ptr [rsp+0B8h+fuOptions], rax; struct tagRECT *
0x180011e38  call    ?MultiPartStringOut@@YAJPEAUtag_STRING_ANALYSIS@@HHIPEBUtagRECT@@@Z; MultiPartStringOut(tag_STRING_ANALYSIS *,int,int,uint,tagRECT const *)
0x180011e3d  add     rsp, 0A0h
0x180011e44  pop     r12
0x180011e46  pop     rbp
0x180011e47  pop     rbx
0x180011e48  retn
0x180011e49  mov     r8d, [rsp+0B8h+y]; y
0x180011e51  mov     r15d, r14d
0x180011e54  jmp     loc_180011B2C
0x180011e59  movzx   edx, word ptr [rax+r13*2]
0x180011e5e  mov     rcx, [rbx+80h]
0x180011e65  movzx   eax, word ptr [rcx+r13*2]
0x180011e6a  add     edx, eax; x
0x180011e6c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180011e73  add     rax, r13
0x180011e76  movzx   ecx, word ptr [rcx+rax*2]
0x180011e7a  cmp     edx, ecx
0x180011e7c  jnz     loc_180011C19
0x180011e82  jmp     loc_180011E01
0x180011e87  mov     rax, [rbx+1B8h]
0x180011e8e  or      r12d, 10h
0x180011e92  mov     r9d, r12d; options
0x180011e95  mov     rcx, [rax+50h]
0x180011e99  lea     rax, [rsp+0B8h+arg_0]
0x180011ea1  mov     [rsp+0B8h+pwcReserved], rax; lpDx
0x180011ea6  add     rcx, 118h
0x180011ead  mov     rax, [rsp+0B8h+lprect]
0x180011eb5  mov     dword ptr [rsp+0B8h+psa], 1; c
0x180011ebd  mov     [rsp+0B8h+lprc], rcx; lpString
0x180011ec2  mov     rcx, [rbx]; hdc
0x180011ec5  mov     qword ptr [rsp+0B8h+fuOptions], rax; lprect
0x180011eca  call    cs:__imp_ExtTextOutA
0x180011ed0  xor     eax, eax
0x180011ed2  add     rsp, 0A0h
0x180011ed9  pop     r12
0x180011edb  pop     rbp
0x180011edc  pop     rbx
0x180011edd  retn
0x180011ede  mov     r14d, ebp
0x180011ee1  jmp     loc_180011AEC
0x180011ee6  cmp     qword ptr [rbx+568h], 0
0x180011eee  jz      short loc_180011F02
0x180011ef0  cmp     byte ptr [rbx+169h], 0
0x180011ef7  jnz     short loc_180011F0B
0x180011ef9  cmp     byte ptr [rbx+16Ah], 0
0x180011f00  jnz     short loc_180011F0B
0x180011f02  mov     ebp, [rsp+0B8h+x]
0x180011f09  jmp     short loc_180011F8A
0x180011f0b  mov     rcx, [rbx]; h
0x180011f0e  call    GetObjectType
0x180011f13  mov     ebp, [rsp+0B8h+x]
0x180011f1a  add     eax, 0FFFFFFFCh
0x180011f1d  mov     r8d, [rsp+0B8h+y]; y
0x180011f25  and     eax, 0FFFFFFF7h
0x180011f28  neg     eax
0x180011f2a  mov     r9d, r12d
0x180011f2d  lea     rax, [rsp+0B8h+arg_0]
0x180011f35  mov     edx, ebp; x
0x180011f37  sbb     ecx, ecx
0x180011f39  mov     [rsp+0B8h+pwcReserved], rax; lpDx
0x180011f3e  and     ecx, 1000h
0x180011f44  mov     dword ptr [rsp+0B8h+psa], edi; c
0x180011f48  and     r9d, 0FFFFFFEFh
0x180011f4c  lea     rax, String; " "
0x180011f53  or      r9d, ecx; options
0x180011f56  mov     [rsp+0B8h+lprc], rax; lpString
0x180011f5b  mov     rcx, [rbx]; hdc
0x180011f5e  mov     qword ptr [rsp+0B8h+fuOptions], rsi; lprect
0x180011f63  call    cs:__imp_ExtTextOutW
0x180011f69  mov     rcx, [rbx]; hdc
0x180011f6c  call    GetBkMode
0x180011f71  mov     edi, eax
0x180011f73  cmp     eax, 2
0x180011f76  jnz     short loc_180011F86
0x180011f78  mov     rcx, [rbx]; hdc
0x180011f7b  mov     edx, 1; mode
0x180011f80  call    cs:__imp_SetBkMode
0x180011f86  and     r12d, 0FFFFFFFDh
0x180011f8a  mov     rdx, [rbx+r15*8+390h]; h
0x180011f92  mov     rcx, [rbx]; hdc
0x180011f95  call    cs:__imp_SelectObject
0x180011f9b  mov     r8d, [rsp+0B8h+y]
0x180011fa3  jmp     loc_180011B49
0x180011fa8  mov     rcx, [rbx]; hdc
0x180011fab  mov     edx, edi; mode
0x180011fad  call    cs:__imp_SetBkMode
  ... truncated ...
```
