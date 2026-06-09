# GetOffsetOfResource(int,char const *,int,_IMAGE_DOS_HEADER *,long *,long *)

- ea: `0x180058240`
- end: `0x1800586f0`
- name: `?GetOffsetOfResource@@YAJHPEBDHPEAU_IMAGE_DOS_HEADER@@PEAJ2@Z`
- size: `1200`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, const char *@<rdx>, int@<r8d>, struct _IMAGE_DOS_HEADER *@<r9>, int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180012b70`

## callees

- `0x180032130`
- `0x180032214`
- `0x180032668`
- `0x180032de0`
- `0x18004d900`
- `0x18004e530`
- `0x180058240`
- `0x1800586f8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005833b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005833b`
- `KERNELBASE!CompareStringA` at `0x1800583b9`
- `KERNELBASE!CompareStringA` at `0x1800583b9`
- `KERNELBASE!lstrcmpiA` at `0x180058641`
- `KERNELBASE!lstrcmpiA` at `0x180058641`

## pseudocode

```c
__int64 __fastcall GetOffsetOfResource(int a1, const char *a2, int a3, struct _IMAGE_DOS_HEADER *a4, int *a5, int *a6)
{
  LONG e_lfanew; // edx
  __int64 result; // rax
  int v11; // eax
  __int16 v12; // r14
  int v13; // r15d
  WCHAR *v14; // r8
  unsigned int v15; // edx
  unsigned int v16; // r9d
  int i; // r14d
  DWORD v18; // ecx
  int v19; // eax
  int v20; // r14d
  __int16 v21; // si
  char v22; // cl
  __int64 v23; // [rsp+38h] [rbp-D0h] BYREF
  _IMAGE_RESOURCE_DIRECTORY_ENTRY v24; // [rsp+40h] [rbp-C8h] BYREF
  int v25; // [rsp+48h] [rbp-C0h] BYREF
  int v26; // [rsp+4Ch] [rbp-BCh] BYREF
  int v27; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v28[4]; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v29; // [rsp+68h] [rbp-A0h] BYREF
  int v30; // [rsp+78h] [rbp-90h]
  unsigned __int16 *v31; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v32[4]; // [rsp+90h] [rbp-78h]
  int v33; // [rsp+A0h] [rbp-68h]
  int v34; // [rsp+A4h] [rbp-64h]
  const wchar_t *v35; // [rsp+A8h] [rbp-60h]
  __int64 v36; // [rsp+B0h] [rbp-58h]
  CHAR String1[16]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v38; // [rsp+D8h] [rbp-30h]
  __int64 v39; // [rsp+E8h] [rbp-20h]
  WCHAR WideCharStr[3]; // [rsp+F8h] [rbp-10h] BYREF
  char v41; // [rsp+FFh] [rbp-9h]

  e_lfanew = a4->e_lfanew;
  v26 = 0;
  result = HrSeek(a1, e_lfanew, 0);
  if ( (int)result < 0 )
    return result;
  result = HrRead(a1, &v26, 4u);
  if ( (int)result < 0 )
    return result;
  if ( v26 != 17744 )
  {
    if ( (_WORD)v26 == 17742 )
    {
      LOBYTE(v23) = 0;
      LOWORD(v25) = 0;
      memset_0(&v31, 0, 0x40u);
      v24 = 0;
      *(_QWORD *)v28 = 0;
      v28[2] = 0;
      v27 = 0;
      result = HrRead(a1, (char *)&v31 + 4, 0x3Cu);
      if ( (int)result < 0 )
        return result;
      if ( WORD2(v35) != HIWORD(v35) )
      {
        v20 = a4->e_lfanew + WORD2(v35);
        result = HrSeek(a1, v20, 0);
        if ( (int)result < 0 )
          return result;
        result = HrRead(a1, &v25, 2u);
        if ( (int)result < 0 )
          return result;
        result = HrRead(a1, &v24, 2u);
        if ( (int)result < 0 )
          return result;
        while ( v24.Id )
        {
          result = HrRead(a1, (char *)&v24.Name + 2, 2u);
          if ( (int)result < 0 )
            return result;
          result = HrRead(a1, &v24.OffsetToData, 4u);
          if ( (int)result < 0 )
            return result;
          if ( (v24.Id & 0x8000u) == 0 )
          {
            result = HrCurPos(a1, (unsigned int *)&v27);
            if ( (int)result < 0 )
              return result;
            result = HrSeek(a1, v20 + (unsigned int)v24.Id, 0);
            if ( (int)result < 0 )
              return result;
            result = HrRead(a1, &v23, 1u);
            if ( (int)result < 0 )
              return result;
            if ( (_BYTE)v23 == 7 )
            {
              result = HrRead(a1, WideCharStr, 7u);
              if ( (int)result < 0 )
                return result;
              v41 = 0;
            }
            result = HrSeek(a1, v27, 0);
            if ( (int)result < 0 )
              return result;
            if ( (_BYTE)v23 == 7 && !lstrcmpiA((LPCSTR)WideCharStr, "typelib") )
            {
              v21 = 0;
              if ( !HIWORD(v24.Name) )
                return 2147654730LL;
              while ( 1 )
              {
                result = HrRead(a1, v28, 0xCu);
                if ( (int)result < 0 )
                  break;
                if ( HIWORD(v28[1]) == (a3 | 0x8000) )
                {
                  v22 = v25;
                  *a5 = LOWORD(v28[0]) << v25;
                  v19 = HIWORD(v28[0]) << v22;
LABEL_50:
                  *a6 = v19;
                  return 0;
                }
                if ( (unsigned __int16)++v21 >= HIWORD(v24.Name) )
                  return 2147654730LL;
              }
              return result;
            }
          }
          result = HrSeek(a1, 12 * (unsigned int)HIWORD(v24.Name), 1);
          if ( (int)result >= 0 )
          {
            result = HrRead(a1, &v24, 2u);
            if ( (int)result >= 0 )
              continue;
          }
          return result;
        }
      }
    }
    return 2147654730LL;
  }
  v24 = 0;
  v30 = 0;
  v39 = 0;
  v34 = 0;
  v35 = L"*";
  v36 = 0;
  v29 = 0;
  *(_OWORD *)String1 = 0;
  v38 = 0;
  *(_OWORD *)v28 = 0;
  *(_OWORD *)v32 = 0;
  v11 = mbslen("typelib");
  MultiByteToWideChar(0, 0, "typelib", v11 + 1, WideCharStr, 128);
  v33 = a3;
  v31 = WideCharStr;
  result = HrRead(a1, &v29, 0x14u);
  if ( (int)result < 0 )
    return result;
  result = HrSeek(a1, (unsigned __int16)v30, 1);
  if ( (int)result < 0 )
    return result;
  v12 = 0;
  if ( !WORD1(v29) )
    return 2147654730LL;
  while ( 1 )
  {
    result = HrRead(a1, String1, 0x28u);
    if ( (int)result < 0 )
      return result;
    if ( CompareStringA(0x7Fu, 1u, String1, -1, ".rsrc", -1) == 2 )
    {
      v13 = DWORD1(v38);
      v14 = WideCharStr;
      v15 = DWORD1(v38);
      v16 = _mm_cvtsi128_si32((__m128i)0LL);
      for ( i = 0; ; v14 = *(WCHAR **)&v32[4 * i - 2] )
      {
        result = GetRsrcDirEntry(a1, v15, v14, v16, &v24);
        if ( (int)result < 0 )
          break;
        v18 = v24.OffsetToData & 0x80000000;
        v15 = (v24.OffsetToData & 0x7FFFFFFF) + v13;
        if ( i == 2 )
        {
          if ( v18 )
            return 2147654730LL;
          result = HrSeek(a1, v15, 0);
          if ( (int)result >= 0 )
          {
            result = HrRead(a1, v28, 0x10u);
            if ( (int)result >= 0 )
            {
              *a5 = v13 + v28[0] - *(_DWORD *)&String1[12];
              v19 = v28[1];
              goto LABEL_50;
            }
          }
          return result;
        }
        if ( !v18 )
          return 2147654730LL;
        v16 = v32[4 * ++i];
      }
      return result;
    }
    if ( ++v12 == WORD1(v29) )
      return 2147654730LL;
  }
}

```

## disassembly

```asm
0x180058240  mov     rax, rsp
0x180058243  mov     [rax+10h], rbx
0x180058247  push    rbp
0x180058248  push    rsi
0x180058249  push    rdi
0x18005824a  push    r12
0x18005824c  push    r13
0x18005824e  push    r14
0x180058250  push    r15
0x180058252  lea     rbp, [rax-148h]
0x180058259  sub     rsp, 210h
0x180058260  movaps  xmmword ptr [rax-48h], xmm6
0x180058264  mov     rax, cs:__security_cookie
0x18005826b  xor     rax, rsp
0x18005826e  mov     [rbp+140h+var_50], rax
0x180058275  mov     edx, [r9+3Ch]; int
0x180058279  mov     r15d, r8d
0x18005827c  mov     r12, [rbp+140h+arg_20]
0x180058283  xor     esi, esi
0x180058285  mov     r13, [rbp+140h+arg_28]
0x18005828c  xor     r8d, r8d; int
0x18005828f  mov     [rsp+240h+var_1FC], esi
0x180058293  mov     rdi, r9
0x180058296  mov     ebx, ecx
0x180058298  call    ?HrSeek@@YAJHJH@Z; HrSeek(int,long,int)
0x18005829d  test    eax, eax
0x18005829f  js      loc_1800583D4
0x1800582a5  lea     r8d, [rsi+4]; unsigned int
0x1800582a9  mov     ecx, ebx; int
0x1800582ab  lea     rdx, [rsp+240h+var_1FC]; void *
0x1800582b0  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x1800582b5  test    eax, eax
0x1800582b7  js      loc_1800583D4
0x1800582bd  cmp     [rsp+240h+var_1FC], 4550h
0x1800582c5  jnz     loc_1800584AD
0x1800582cb  xor     eax, eax
0x1800582cd  mov     qword ptr [rsp+240h+var_208], rsi
0x1800582d2  xorps   xmm0, xmm0
0x1800582d5  mov     [rsp+240h+var_1D0], eax
0x1800582d9  xorps   xmm1, xmm1
0x1800582dc  mov     [rbp+140h+var_160], rax
0x1800582e0  lea     rax, asc_1800B131C; "*"
0x1800582e7  mov     [rbp+140h+var_1A4], esi
0x1800582ea  xorps   xmm6, xmm6
0x1800582ed  mov     [rbp+140h+var_1A0], rax
0x1800582f1  lea     rcx, MultiByteStr; "typelib"
0x1800582f8  mov     [rbp+140h+var_198], rsi
0x1800582fc  movups  xmmword ptr [rsp+240h+var_1E8+8], xmm0
0x180058301  movups  xmmword ptr [rbp+140h+String1], xmm1
0x180058305  movups  [rbp+140h+var_170], xmm1
0x180058309  movups  xmmword ptr [rsp+240h+var_1F8+8], xmm0
0x18005830e  movdqu  xmmword ptr [rbp+140h+var_1B8], xmm6
0x180058313  call    _mbslen
0x180058318  lea     rcx, [rbp+140h+WideCharStr]
0x18005831c  mov     [rsp+240h+cchWideChar], 80h; cchWideChar
0x180058324  mov     [rsp+240h+lpWideCharStr], rcx; lpWideCharStr
0x180058329  lea     edi, [rsi+1]
0x18005832c  xor     ecx, ecx; CodePage
0x18005832e  lea     r8, MultiByteStr; "typelib"
0x180058335  lea     r9d, [rdi+rax]; cbMultiByte
0x180058339  xor     edx, edx; dwFlags
0x18005833b  call    cs:__imp_MultiByteToWideChar
0x180058341  lea     rax, [rbp+140h+WideCharStr]
0x180058345  mov     [rbp+140h+var_1A8], r15d
0x180058349  lea     r8d, [rsi+14h]; unsigned int
0x18005834d  mov     [rbp+140h+var_1C0], rax
0x180058351  lea     rdx, [rsp+240h+var_1E8+8]; void *
0x180058356  mov     ecx, ebx; int
0x180058358  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x18005835d  test    eax, eax
0x18005835f  js      short loc_1800583D4
0x180058361  movzx   edx, word ptr [rsp+240h+var_1D0]; int
0x180058366  mov     r8d, edi; int
0x180058369  mov     ecx, ebx; int
0x18005836b  call    ?HrSeek@@YAJHJH@Z; HrSeek(int,long,int)
0x180058370  test    eax, eax
0x180058372  js      short loc_1800583D4
0x180058374  mov     r14d, esi
0x180058377  cmp     si, word ptr [rsp+240h+var_1E8+0Ah]
0x18005837c  jz      short loc_1800583CF
0x18005837e  or      r15d, 0FFFFFFFFh
0x180058382  lea     esi, [rdi+1]
0x180058385  mov     r8d, 28h ; '('; unsigned int
0x18005838b  lea     rdx, [rbp+140h+String1]; void *
0x18005838f  mov     ecx, ebx; int
0x180058391  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x180058396  test    eax, eax
0x180058398  js      short loc_1800583D4
0x18005839a  lea     rax, aRsrc; ".rsrc"
0x1800583a1  mov     [rsp+240h+cchWideChar], r15d; cchCount2
0x1800583a6  mov     r9d, r15d; cchCount1
0x1800583a9  mov     [rsp+240h+lpWideCharStr], rax; lpString2
0x1800583ae  lea     r8, [rbp+140h+String1]; lpString1
0x1800583b2  mov     edx, edi; dwCmpFlags
0x1800583b4  mov     ecx, 7Fh; Locale
0x1800583b9  call    cs:__imp_CompareStringA
0x1800583bf  cmp     eax, esi
0x1800583c1  jz      short loc_180058403
0x1800583c3  add     r14w, di
0x1800583c7  cmp     r14w, word ptr [rsp+240h+var_1E8+0Ah]
0x1800583cd  jnz     short loc_180058385
0x1800583cf  mov     eax, 80029C4Ah
0x1800583d4  mov     rcx, [rbp+140h+var_50]
0x1800583db  xor     rcx, rsp; StackCookie
0x1800583de  call    __security_check_cookie
0x1800583e3  lea     r11, [rsp+240h+var_30]
0x1800583eb  mov     rbx, [r11+48h]
0x1800583ef  movaps  xmm6, xmmword ptr [r11-10h]
0x1800583f4  mov     rsp, r11
0x1800583f7  pop     r15
0x1800583f9  pop     r14
0x1800583fb  pop     r13
0x1800583fd  pop     r12
0x1800583ff  pop     rdi
0x180058400  pop     rsi
0x180058401  pop     rbp
0x180058402  retn
0x180058403  mov     r15d, dword ptr [rbp+140h+var_170+4]
0x180058407  lea     r8, [rbp+140h+WideCharStr]
0x18005840b  mov     edx, r15d
0x18005840e  movd    r9d, xmm6
0x180058413  xor     r14d, r14d
0x180058416  jmp     short loc_180058448
0x180058418  mov     eax, dword ptr [rsp+240h+var_208.4]
0x18005841c  mov     ecx, eax
0x18005841e  btr     eax, 1Fh
0x180058422  and     ecx, 80000000h
0x180058428  lea     edx, [rax+r15]; int
0x18005842c  cmp     r14d, esi
0x18005842f  jz      short loc_180058462
0x180058431  test    ecx, ecx
0x180058433  jz      short loc_1800583CF
0x180058435  add     r14d, edi
0x180058438  movsxd  r8, r14d
0x18005843b  add     r8, r8
0x18005843e  mov     r9d, [rbp+r8*8+140h+var_1B8]; unsigned int
0x180058443  mov     r8, [rbp+r8*8+140h+var_1C0]; unsigned __int16 *
0x180058448  lea     rax, [rsp+240h+var_208]
0x18005844d  mov     ecx, ebx; int
0x18005844f  mov     [rsp+240h+lpWideCharStr], rax; struct _IMAGE_RESOURCE_DIRECTORY_ENTRY *
0x180058454  call    ?GetRsrcDirEntry@@YAJHKPEBGKPEAU_IMAGE_RESOURCE_DIRECTORY_ENTRY@@@Z; GetRsrcDirEntry(int,ulong,ushort const *,ulong,_IMAGE_RESOURCE_DIRECTORY_ENTRY *)
0x180058459  test    eax, eax
0x18005845b  jns     short loc_180058418
0x18005845d  jmp     loc_1800583D4
0x180058462  test    ecx, ecx
0x180058464  jnz     loc_1800583CF
0x18005846a  xor     r8d, r8d; int
0x18005846d  mov     ecx, ebx; int
0x18005846f  call    ?HrSeek@@YAJHJH@Z; HrSeek(int,long,int)
0x180058474  test    eax, eax
0x180058476  js      loc_1800583D4
0x18005847c  mov     r8d, 10h; unsigned int
0x180058482  lea     rdx, [rsp+240h+var_1F8+8]; void *
0x180058487  mov     ecx, ebx; int
0x180058489  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x18005848e  test    eax, eax
0x180058490  js      loc_1800583D4
0x180058496  mov     eax, [rsp+240h+var_1F8+8]
0x18005849a  sub     eax, dword ptr [rbp+140h+String1+0Ch]
0x18005849d  add     eax, r15d
0x1800584a0  mov     [r12], eax
0x1800584a4  mov     eax, [rsp+240h+var_1F8+0Ch]
0x1800584a8  jmp     loc_1800586E5
0x1800584ad  mov     eax, 454Eh
0x1800584b2  cmp     word ptr [rsp+240h+var_1FC], ax
0x1800584b7  jnz     loc_1800583CF
0x1800584bd  xor     edx, edx; Val
0x1800584bf  mov     byte ptr [rsp+240h+var_210], sil
0x1800584c4  lea     rcx, [rbp+140h+var_1C0]; void *
0x1800584c8  mov     word ptr [rsp+240h+var_200], si
0x1800584cd  lea     r8d, [rdx+40h]; Size
0x1800584d1  call    memset_0
0x1800584d6  xor     eax, eax
0x1800584d8  mov     qword ptr [rsp+240h+var_208], rsi
0x1800584dd  lea     rdx, [rbp+140h+var_1C0+4]; void *
0x1800584e1  mov     qword ptr [rsp+240h+var_1F8+8], rax
0x1800584e6  mov     ecx, ebx; int
0x1800584e8  mov     dword ptr [rsp+240h+var_1E8], eax
0x1800584ec  mov     [rsp+240h+var_1F8], esi
0x1800584f0  lea     r8d, [rax+3Ch]; unsigned int
0x1800584f4  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x1800584f9  test    eax, eax
0x1800584fb  js      loc_1800583D4
0x180058501  movzx   eax, word ptr [rbp+140h+var_1A0+4]
0x180058505  cmp     ax, word ptr [rbp+140h+var_1A0+6]
0x180058509  jz      loc_1800583CF
0x18005850f  mov     r14d, eax
0x180058512  xor     r8d, r8d; int
0x180058515  add     r14d, [rdi+3Ch]
0x180058519  mov     ecx, ebx; int
0x18005851b  mov     edx, r14d; int
0x18005851e  call    ?HrSeek@@YAJHJH@Z; HrSeek(int,long,int)
0x180058523  test    eax, eax
0x180058525  js      loc_1800583D4
0x18005852b  mov     esi, 2
0x180058530  lea     rdx, [rsp+240h+var_200]; void *
0x180058535  mov     r8d, esi; unsigned int
0x180058538  mov     ecx, ebx; int
0x18005853a  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x18005853f  test    eax, eax
0x180058541  js      loc_1800583D4
0x180058547  mov     r8d, esi; unsigned int
0x18005854a  lea     rdx, [rsp+240h+var_208]; void *
0x18005854f  mov     ecx, ebx; int
0x180058551  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x180058556  xor     ecx, ecx
0x180058558  test    eax, eax
0x18005855a  js      loc_1800583D4
0x180058560  lea     edi, [rsi-1]
0x180058563  cmp     word ptr [rsp+240h+var_208], cx
0x180058568  jz      loc_1800583CF
0x18005856e  mov     r8d, esi; unsigned int
0x180058571  lea     rdx, [rsp+240h+var_208+2]; void *
0x180058576  mov     ecx, ebx; int
0x180058578  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x18005857d  test    eax, eax
0x18005857f  js      loc_1800583D4
0x180058585  mov     r8d, 4; unsigned int
0x18005858b  lea     rdx, [rsp+240h+var_208.4]; void *
0x180058590  mov     ecx, ebx; int
0x180058592  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x180058597  test    eax, eax
0x180058599  js      loc_1800583D4
0x18005859f  mov     eax, 8000h
0x1800585a4  test    word ptr [rsp+240h+var_208], ax
0x1800585a9  jnz     loc_18005864D
0x1800585af  lea     rdx, [rsp+240h+var_1F8]; unsigned int *
0x1800585b4  mov     ecx, ebx; int
0x1800585b6  call    ?HrCurPos@@YAJHPEAK@Z; HrCurPos(int,ulong *)
0x1800585bb  test    eax, eax
0x1800585bd  js      loc_1800583D4
0x1800585c3  movzx   edx, word ptr [rsp+240h+var_208]
0x1800585c8  xor     r8d, r8d; int
0x1800585cb  add     edx, r14d; int
0x1800585ce  mov     ecx, ebx; int
0x1800585d0  call    ?HrSeek@@YAJHJH@Z; HrSeek(int,long,int)
0x1800585d5  test    eax, eax
0x1800585d7  js      loc_1800583D4
0x1800585dd  mov     r8d, edi; unsigned int
0x1800585e0  lea     rdx, [rsp+240h+var_210]; void *
0x1800585e5  mov     ecx, ebx; int
0x1800585e7  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x1800585ec  test    eax, eax
0x1800585ee  js      loc_1800583D4
0x1800585f4  cmp     byte ptr [rsp+240h+var_210], 7
0x1800585f9  jnz     short loc_180058619
0x1800585fb  mov     r8d, 7; unsigned int
0x180058601  lea     rdx, [rbp+140h+WideCharStr]; void *
0x180058605  mov     ecx, ebx; int
0x180058607  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x18005860c  xor     ecx, ecx
0x18005860e  test    eax, eax
0x180058610  js      loc_1800583D4
0x180058616  mov     [rbp+140h+var_149], cl
0x180058619  mov     edx, [rsp+240h+var_1F8]; int
0x18005861d  xor     r8d, r8d; int
0x180058620  mov     ecx, ebx; int
0x180058622  call    ?HrSeek@@YAJHJH@Z; HrSeek(int,long,int)
0x180058627  test    eax, eax
0x180058629  js      loc_1800583D4
0x18005862f  cmp     byte ptr [rsp+240h+var_210], 7
0x180058634  jnz     short loc_18005864D
0x180058636  lea     rdx, MultiByteStr; "typelib"
0x18005863d  lea     rcx, [rbp+140h+WideCharStr]; lpString1
0x180058641  call    cs:__imp_lstrcmpiA
0x180058647  xor     ecx, ecx
0x180058649  test    eax, eax
0x18005864b  jz      short loc_180058688
0x18005864d  movzx   eax, word ptr [rsp+240h+var_208+2]
0x180058652  mov     r8d, edi; int
0x180058655  mov     ecx, ebx; int
0x180058657  lea     edx, [rax+rax*2]
0x18005865a  shl     edx, 2; int
0x18005865d  call    ?HrSeek@@YAJHJH@Z; HrSeek(int,long,int)
0x180058662  test    eax, eax
0x180058664  js      loc_1800583D4
0x18005866a  mov     r8d, esi; unsigned int
0x18005866d  lea     rdx, [rsp+240h+var_208]; void *
0x180058672  mov     ecx, ebx; int
0x180058674  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x180058679  xor     ecx, ecx
0x18005867b  test    eax, eax
0x18005867d  jns     loc_180058563
0x180058683  jmp     loc_1800583D4
0x180058688  mov     esi, ecx
0x18005868a  cmp     cx, word ptr [rsp+240h+var_208+2]
0x18005868f  jnb     loc_1800583CF
0x180058695  mov     r8d, 0Ch; unsigned int
0x18005869b  lea     rdx, [rsp+240h+var_1F8+8]; void *
0x1800586a0  mov     ecx, ebx; int
0x1800586a2  call    ?HrRead@@YAJHPEAXI@Z; HrRead(int,void *,uint)
0x1800586a7  test    eax, eax
0x1800586a9  js      loc_1800583D4
0x1800586af  movzx   eax, word ptr [rsp+240h+var_1F8+0Eh]
0x1800586b4  mov     ecx, r15d
0x1800586b7  bts     ecx, 0Fh
0x1800586bb  cmp     eax, ecx
0x1800586bd  jz      short loc_1800586CE
0x1800586bf  add     si, di
0x1800586c2  cmp     si, word ptr [rsp+240h+var_208+2]
  ... truncated ...
```
