# InternalStringOut(tag_STRING_ANALYSIS *,int,int,uint,tagRECT const *)

- ea: `0x180024610`
- end: `0x180024b9b`
- name: `?InternalStringOut@@YAJPEAUtag_STRING_ANALYSIS@@HHIPEBUtagRECT@@@Z`
- size: `1419`
- prototype: `__int64 __usercall@<rax>(struct tag_STRING_ANALYSIS *@<rcx>, int@<edx>, int@<r8d>, unsigned int@<r9d>, const struct tagRECT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800242f0`
- `0x18005d9e8`

## callees

- `0x180009760`
- `0x180019630`
- `0x1800209d0`
- `0x180020a90`
- `0x180024610`
- `0x180024c40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002491b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002491b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800248f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800248f9`
- `GDI32!ExtTextOutA` at `0x180024a8b`
- `GDI32!ExtTextOutA` at `0x180024a8b`
- `GDI32!ExtTextOutW` at `0x180024819`
- `GDI32!ExtTextOutW` at `0x180024b2e`
- `GDI32!ExtTextOutW` at `0x180024819`
- `GDI32!ExtTextOutW` at `0x180024b2e`
- `GDI32!SelectObject` at `0x180024774`
- `GDI32!SelectObject` at `0x180024b6c`
- `GDI32!SelectObject` at `0x180024774`
- `GDI32!SelectObject` at `0x180024b6c`
- `GDI32!SetBkMode` at `0x180024b51`
- `GDI32!SetBkMode` at `0x180024b8a`
- `GDI32!SetBkMode` at `0x180024b51`
- `GDI32!SetBkMode` at `0x180024b8a`
- `TextShaping!ShapingGetCombiningOptions` at `0x18002497d`
- `TextShaping!ShapingGetCombiningOptions` at `0x18002497d`

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
          if ( (char *)funcs_180021072[3 * v21] != (char *)ShlTextOut )
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
0x180024610  mov     r11, rsp
0x180024613  mov     [r11+18h], r8d
0x180024617  mov     [rsp+x], edx
0x18002461b  push    rbx
0x18002461c  push    rbp
0x18002461d  push    r12
0x18002461f  sub     rsp, 0A0h
0x180024626  mov     rbx, rcx
0x180024629  mov     r12d, r9d
0x18002462c  mov     ecx, [rcx+8]
0x18002462f  mov     eax, 40h ; '@'
0x180024634  test    cl, 8
0x180024637  mov     r9d, 1A8h
0x18002463d  mov     r10d, [rbx+190h]
0x180024644  cmovz   eax, r9d
0x180024648  mov     eax, [rax+rbx]
0x18002464b  mov     [r11+8], eax
0x18002464f  test    r10d, r10d
0x180024652  jle     loc_1800247E9
0x180024658  bt      ecx, 1Eh
0x18002465c  jb      loc_180024A48
0x180024662  test    ecx, 0C00h
0x180024668  jnz     loc_1800249E5
0x18002466e  mov     rax, [rbx+0D8h]
0x180024675  xor     ebp, ebp
0x180024677  mov     [r11-30h], r14
0x18002467b  mov     [r11-38h], r15
0x18002467f  test    rax, rax
0x180024682  jz      loc_180024AA6
0x180024688  movzx   r14d, byte ptr [rax]
0x18002468c  mov     rdx, [rbx+1B8h]
0x180024693  mov     [rsp+0B8h+arg_18], rsi
0x18002469b  mov     r15d, r14d
0x18002469e  mov     [rsp+0B8h+var_20], rdi
0x1800246a6  mov     eax, [rdx+30h]
0x1800246a9  mov     [rsp+0B8h+var_28], r13
0x1800246b1  mov     rcx, [rbx+r15*8+1B8h]
0x1800246b9  cmp     [rcx+30h], eax
0x1800246bc  jnz     loc_1800247C0
0x1800246c2  cmp     r10d, 1
0x1800246c6  jg      loc_180024834
0x1800246cc  mov     rsi, [rsp+0B8h+lprect]
0x1800246d4  mov     edi, 1
0x1800246d9  test    r14d, r14d
0x1800246dc  jnz     loc_180024AAE
0x1800246e2  mov     ebp, [rsp+0B8h+x]
0x1800246e9  mov     rax, [rbx+0C8h]
0x1800246f0  lea     rdx, [rbx+1B8h]
0x1800246f7  mov     rcx, [rbx+68h]
0x1800246fb  lea     rdx, [rdx+r15*8]; psc
0x1800246ff  mov     [rsp+0B8h+pGoffset], rax; pGoffset
0x180024704  add     rcx, 4
0x180024708  mov     rax, [rbx+0C0h]
0x18002470f  mov     r9d, r8d; y
0x180024712  mov     [rsp+0B8h+piJustify], rax; piJustify
0x180024717  mov     r8d, ebp; x
0x18002471a  mov     rax, [rbx+0B8h]
0x180024721  mov     [rsp+0B8h+piAdvance], rax; piAdvance
0x180024726  mov     eax, [rbx+194h]
0x18002472c  mov     [rsp+0B8h+cGlyphs], eax; cGlyphs
0x180024730  mov     rax, [rbx+0A0h]
0x180024737  mov     [rsp+0B8h+pwGlyphs], rax; pwGlyphs
0x18002473c  mov     eax, [rbx+38h]
0x18002473f  mov     [rsp+0B8h+iReserved], eax; iReserved
0x180024743  mov     rax, [rbx+30h]
0x180024747  mov     [rsp+0B8h+pwcReserved], rax; pwcReserved
0x18002474c  mov     [rsp+0B8h+psa], rcx; psa
0x180024751  mov     rcx, [rbx]; hdc
0x180024754  mov     [rsp+0B8h+lprc], rsi; lprc
0x180024759  mov     [rsp+0B8h+fuOptions], r12d; fuOptions
0x18002475e  call    ScriptTextOut
0x180024763  mov     esi, eax
0x180024765  test    r14d, r14d
0x180024768  jz      short loc_180024780
0x18002476a  mov     rdx, [rbx+390h]; h
0x180024771  mov     rcx, [rbx]; hdc
0x180024774  call    cs:__imp_SelectObject
0x18002477b  nop     dword ptr [rax+rax+00h]
0x180024780  cmp     edi, 1
0x180024783  jnz     loc_180024B85
0x180024789  mov     eax, esi
0x18002478b  mov     rdi, [rsp+0B8h+var_20]
0x180024793  mov     r13, [rsp+0B8h+var_28]
0x18002479b  mov     rsi, [rsp+0B8h+arg_18]
0x1800247a3  mov     r14, [rsp+0B8h+var_30]
0x1800247ab  mov     r15, [rsp+0B8h+var_38]
0x1800247b3  add     rsp, 0A0h
0x1800247ba  pop     r12
0x1800247bc  pop     rbp
0x1800247bd  pop     rbx
0x1800247be  retn
0x1800247c0  mov     rax, [rsp+0B8h+lprect]
0x1800247c8  mov     r9d, r12d; unsigned int
0x1800247cb  mov     r8d, [rsp+0B8h+y]; y
0x1800247d3  mov     rcx, rbx; struct tag_STRING_ANALYSIS *
0x1800247d6  mov     edx, [rsp+0B8h+x]; x
0x1800247dd  mov     qword ptr [rsp+0B8h+fuOptions], rax; struct tagRECT *
0x1800247e2  call    ?MultiPartStringOut@@YAJPEAUtag_STRING_ANALYSIS@@HHIPEBUtagRECT@@@Z; MultiPartStringOut(tag_STRING_ANALYSIS *,int,int,uint,tagRECT const *)
0x1800247e7  jmp     short loc_18002478B
0x1800247e9  mov     rax, [rbx+30h]
0x1800247ed  xor     ebp, ebp
0x1800247ef  mov     rcx, [rbx]; hdc
0x1800247f2  and     r12d, 0FFFFFFEFh
0x1800247f6  mov     [rsp+0B8h+pwcReserved], rbp; lpDx
0x1800247fb  bts     r12d, 0Ch
0x180024800  mov     dword ptr [rsp+0B8h+psa], ebp; c
0x180024804  mov     r9d, r12d; options
0x180024807  mov     [rsp+0B8h+lprc], rax; lpString
0x18002480c  mov     rax, [rsp+0B8h+lprect]
0x180024814  mov     qword ptr [rsp+0B8h+fuOptions], rax; lprect
0x180024819  call    cs:__imp_ExtTextOutW
0x180024820  nop     dword ptr [rax+rax+00h]
0x180024825  xor     eax, eax
0x180024827  add     rsp, 0A0h
0x18002482e  pop     r12
0x180024830  pop     rbp
0x180024831  pop     rbx
0x180024832  retn
0x180024834  mov     rax, [rdx+50h]
0x180024838  cmp     [rax+13Ch], ebp
0x18002483e  jle     loc_1800246CC
0x180024844  mov     rax, [rbx+68h]
0x180024848  movzx   eax, word ptr [rax+4]
0x18002484c  shr     eax, 0Bh
0x18002484f  and     eax, 1
0x180024852  mov     [rsp+0B8h+var_48], eax
0x180024856  lea     r10, __ImageBase
0x18002485d  cmp     ebp, [rbx+190h]
0x180024863  jge     loc_180024A0A
0x180024869  mov     rax, [rbx+68h]
0x18002486d  movsxd  r13, ebp
0x180024870  movzx   esi, word ptr [rax+r13*8+4]
0x180024876  test    si, si
0x180024879  js      loc_1800247C0
0x18002487f  mov     rax, [rbx+0D8h]
0x180024886  test    rax, rax
0x180024889  jz      loc_1800247C0
0x18002488f  movzx   eax, byte ptr [rax+r13]
0x180024894  cmp     eax, r14d
0x180024897  jnz     loc_1800247C0
0x18002489d  movsxd  r15, dword ptr [rbx+150h]
0x1800248a4  and     esi, 3FFh
0x1800248aa  add     r15, 37h ; '7'
0x1800248ae  lea     r15, [rbx+r15*8]
0x1800248b2  test    r15, r15
0x1800248b5  jz      loc_1800249C8
0x1800248bb  mov     rax, [r15]
0x1800248be  test    rax, rax
0x1800248c1  jz      short loc_1800248EF
0x1800248c3  mov     rcx, [rax+50h]
0x1800248c7  test    rcx, rcx
0x1800248ca  jz      short loc_1800248EF
0x1800248cc  cmp     esi, 0E1h
0x1800248d2  jnb     loc_1800249C8
0x1800248d8  mov     rcx, [rcx+rsi*8+158h]
0x1800248e0  test    rcx, rcx
0x1800248e3  jz      loc_1800249C8
0x1800248e9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800248ed  jnz     short loc_180024936
0x1800248ef  mov     rdi, [rbx]
0x1800248f2  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800248f9  call    cs:__imp_EnterCriticalSection
0x180024900  nop     dword ptr [rax+rax+00h]
0x180024905  mov     r8, rdi; HDC
0x180024908  mov     edx, esi; int
0x18002490a  mov     rcx, r15; void **
0x18002490d  call    ?UpdateCache@@YAJPEAPEAXHPEAUHDC__@@@Z; UpdateCache(void * *,int,HDC__ *)
0x180024912  lea     rcx, ?csCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180024919  mov     edi, eax
0x18002491b  call    cs:__imp_LeaveCriticalSection
0x180024922  nop     dword ptr [rax+rax+00h]
0x180024927  lea     r10, __ImageBase
0x18002492e  test    edi, edi
0x180024930  js      loc_1800249C8
0x180024936  mov     rax, [r15]
0x180024939  mov     edx, esi
0x18002493b  shr     rdx, 5
0x18002493f  mov     r9d, esi
0x180024942  mov     r8, [rax+50h]
0x180024946  mov     eax, esi
0x180024948  and     eax, 8000001Fh
0x18002494d  jge     short loc_180024956
0x18002494f  dec     eax
0x180024951  or      eax, 0FFFFFFE0h
0x180024954  inc     eax
0x180024956  movzx   ecx, al
0x180024959  mov     eax, [r8+rdx*4+0F8h]
0x180024961  bt      eax, ecx
0x180024964  jnb     short loc_1800249C8
0x180024966  cmp     esi, 13h
0x180024969  jz      loc_1800247C0
0x18002496f  movzx   ecx, ds:rva ?ShlScriptSupport@@3QBUSHAPING_LIBRARY_XREF@@B[r10+r9*8]; SHAPING_LIBRARY_XREF const near * const ShlScriptSupport ...
0x180024978  mov     edx, 1
0x18002497d  call    cs:__imp_ShapingGetCombiningOptions
0x180024984  nop     dword ptr [rax+rax+00h]
0x180024989  test    al, 2
0x18002498b  jz      loc_1800247C0
0x180024991  cmp     [rsp+0B8h+var_48], 0
0x180024996  mov     rax, [rbx+88h]
0x18002499d  jnz     short loc_180024A1A
0x18002499f  movzx   ecx, word ptr [rax+r13*2-2]
0x1800249a5  mov     rdx, [rbx+80h]; x
0x1800249ac  movzx   eax, word ptr [rdx+r13*2-2]
0x1800249b2  add     ecx, eax
0x1800249b4  movzx   eax, word ptr [rdx+r13*2]
0x1800249b9  cmp     eax, ecx
0x1800249bb  jnz     loc_1800247C0
0x1800249c1  inc     ebp
0x1800249c3  jmp     loc_180024856
0x1800249c8  lea     rax, [rsi+rsi*2]
0x1800249cc  mov     r9d, esi
0x1800249cf  lea     rcx, ?ShlTextOut@@YAJPEAUHDC__@@PEAPEAXHHIPEBUtagRECT@@PEBUtag_SCRIPT_ANALYSIS@@PEBGHPEBH5PEBUtagGOFFSET@@@Z; ShlTextOut(HDC__ *,void * *,int,int,uint,tagRECT const *,tag_SCRIPT_ANALYSIS const *,ushort const *,int,int const *,int const *,tagGOFFSET const *)
0x1800249d6  cmp     ds:rva funcs_180021072[r10+rax*8], rcx
0x1800249de  jz      short loc_180024966
0x1800249e0  jmp     loc_1800247C0
0x1800249e5  mov     rax, [rsp+0B8h+lprect]
0x1800249ed  mov     r9d, r12d; unsigned int
0x1800249f0  mov     rcx, rbx; struct tag_STRING_ANALYSIS *
0x1800249f3  mov     qword ptr [rsp+0B8h+fuOptions], rax; struct tagRECT *
0x1800249f8  call    ?MultiPartStringOut@@YAJPEAUtag_STRING_ANALYSIS@@HHIPEBUtagRECT@@@Z; MultiPartStringOut(tag_STRING_ANALYSIS *,int,int,uint,tagRECT const *)
0x1800249fd  add     rsp, 0A0h
0x180024a04  pop     r12
0x180024a06  pop     rbp
0x180024a07  pop     rbx
0x180024a08  retn
0x180024a0a  mov     r8d, [rsp+0B8h+y]; y
0x180024a12  mov     r15d, r14d
0x180024a15  jmp     loc_1800246CC
0x180024a1a  movzx   edx, word ptr [rax+r13*2]
0x180024a1f  mov     rcx, [rbx+80h]
0x180024a26  movzx   eax, word ptr [rcx+r13*2]
0x180024a2b  add     edx, eax; x
0x180024a2d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180024a34  add     rax, r13
0x180024a37  movzx   ecx, word ptr [rcx+rax*2]
0x180024a3b  cmp     edx, ecx
0x180024a3d  jnz     loc_1800247C0
0x180024a43  jmp     loc_1800249C1
0x180024a48  mov     rax, [rbx+1B8h]
0x180024a4f  or      r12d, 10h
0x180024a53  mov     r9d, r12d; options
0x180024a56  mov     rcx, [rax+50h]
0x180024a5a  lea     rax, [rsp+0B8h+arg_0]
0x180024a62  mov     [rsp+0B8h+pwcReserved], rax; lpDx
0x180024a67  add     rcx, 118h
0x180024a6e  mov     rax, [rsp+0B8h+lprect]
0x180024a76  mov     dword ptr [rsp+0B8h+psa], 1; c
0x180024a7e  mov     [rsp+0B8h+lprc], rcx; lpString
0x180024a83  mov     rcx, [rbx]; hdc
0x180024a86  mov     qword ptr [rsp+0B8h+fuOptions], rax; lprect
0x180024a8b  call    cs:__imp_ExtTextOutA
0x180024a92  nop     dword ptr [rax+rax+00h]
0x180024a97  xor     eax, eax
0x180024a99  add     rsp, 0A0h
0x180024aa0  pop     r12
0x180024aa2  pop     rbp
0x180024aa3  pop     rbx
0x180024aa4  retn
0x180024aa6  mov     r14d, ebp
0x180024aa9  jmp     loc_18002468C
0x180024aae  cmp     qword ptr [rbx+568h], 0
0x180024ab6  jz      short loc_180024ACA
0x180024ab8  cmp     byte ptr [rbx+169h], 0
0x180024abf  jnz     short loc_180024AD6
0x180024ac1  cmp     byte ptr [rbx+16Ah], 0
0x180024ac8  jnz     short loc_180024AD6
0x180024aca  mov     ebp, [rsp+0B8h+x]
0x180024ad1  jmp     loc_180024B61
0x180024ad6  mov     rcx, [rbx]; h
0x180024ad9  call    GetObjectType
0x180024ade  mov     ebp, [rsp+0B8h+x]
0x180024ae5  add     eax, 0FFFFFFFCh
0x180024ae8  mov     r8d, [rsp+0B8h+y]; y
0x180024af0  and     eax, 0FFFFFFF7h
0x180024af3  neg     eax
0x180024af5  mov     r9d, r12d
0x180024af8  lea     rax, [rsp+0B8h+arg_0]
0x180024b00  mov     edx, ebp; x
0x180024b02  sbb     ecx, ecx
0x180024b04  mov     [rsp+0B8h+pwcReserved], rax; lpDx
0x180024b09  and     ecx, 1000h
0x180024b0f  mov     dword ptr [rsp+0B8h+psa], edi; c
0x180024b13  and     r9d, 0FFFFFFEFh
0x180024b17  lea     rax, String; " "
0x180024b1e  or      r9d, ecx; options
0x180024b21  mov     [rsp+0B8h+lprc], rax; lpString
0x180024b26  mov     rcx, [rbx]; hdc
0x180024b29  mov     qword ptr [rsp+0B8h+fuOptions], rsi; lprect
0x180024b2e  call    cs:__imp_ExtTextOutW
0x180024b35  nop     dword ptr [rax+rax+00h]
0x180024b3a  mov     rcx, [rbx]; hdc
0x180024b3d  call    GetBkMode
0x180024b42  mov     edi, eax
0x180024b44  cmp     eax, 2
0x180024b47  jnz     short loc_180024B5D
0x180024b49  mov     rcx, [rbx]; hdc
0x180024b4c  mov     edx, 1; mode
0x180024b51  call    cs:__imp_SetBkMode
0x180024b58  nop     dword ptr [rax+rax+00h]
0x180024b5d  and     r12d, 0FFFFFFFDh
  ... truncated ...
```
