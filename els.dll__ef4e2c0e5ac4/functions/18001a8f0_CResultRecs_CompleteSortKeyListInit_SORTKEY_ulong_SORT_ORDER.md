# CResultRecs::_CompleteSortKeyListInit(SORTKEY *,ulong *,SORT_ORDER)

- ea: `0x18001a8f0`
- end: `0x18001abd1`
- name: `?_CompleteSortKeyListInit@CResultRecs@@AEAAJPEAUSORTKEY@@PEAKW4SORT_ORDER@@@Z`
- size: `737`
- prototype: `int __high(struct SORTKEY *, unsigned int *, enum SORT_ORDER)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001a67c`

## callees

- `0x180004710`
- `0x180004774`
- `0x180014dd8`
- `0x180014eb8`
- `0x180019708`
- `0x18001a8f0`
- `0x18001b164`
- `0x18001b2b4`
- `0x180020f74`
- `0x1800212e0`
- `0x1800222d0`

## import_xrefs

- `msvcrt!qsort` at `0x18001a94e`
- `msvcrt!qsort` at `0x18001a94e`

## pseudocode

```c
__int64 __fastcall CResultRecs::_CompleteSortKeyListInit(__int64 a1, _DWORD *a2, unsigned int *a3, int a4)
{
  _QWORD *v6; // rbx
  unsigned int v7; // r13d
  CLightRecCache *v8; // rsi
  CRecList *v9; // rcx
  __int64 v10; // r15
  int v11; // ebp
  unsigned int *v12; // rsi
  unsigned int v13; // eax
  CSharedStringArray *v14; // rcx
  unsigned int v15; // edx
  unsigned int v16; // eax
  unsigned int v17; // edx
  const unsigned __int16 *Name; // rdx
  __int64 v19; // rbx
  const unsigned __int16 *SourceStr; // rax
  CCategories *Categories; // rax
  unsigned int v22; // edx
  unsigned int Handle; // eax
  __int64 v24; // rcx
  int v26; // edx
  unsigned int i; // edi
  __int64 v28; // rcx
  unsigned int v29; // [rsp+20h] [rbp-68h] BYREF
  int v30; // [rsp+24h] [rbp-64h]
  _QWORD *v31; // [rsp+28h] [rbp-60h]
  CLightRecCache *v32; // [rsp+30h] [rbp-58h]
  struct _SYSTEMTIME v33; // [rsp+38h] [rbp-50h] BYREF

  v31 = (_QWORD *)a1;
  v30 = a4;
  v6 = (_QWORD *)a1;
  if ( (unsigned int)(a4 - 8) <= 1 )
  {
    v26 = *(_DWORD *)(a1 + 724);
    for ( i = 0; i < *a3; a2[4 * v28 + 2] = a2[4 * v28] - v26 )
      v28 = i++;
    return 0;
  }
  qsort(a2, *a3, 0x10u, CompareRecNoDescending);
  v7 = 0;
  if ( !*a3 )
    return 0;
  v8 = (CLightRecCache *)(v6 + 4);
  v32 = (CLightRecCache *)(v6 + 4);
  while ( 1 )
  {
    v9 = (CRecList *)*((_QWORD *)v8 + 8);
    v10 = 4LL * v7;
    v29 = 0;
    v11 = CRecList::RecNoToIndex(v9, a2[v10], &v29);
    if ( v11 >= 0 )
      v11 = CLightRecCache::SeekToIndex(v8, v29);
    if ( v11 < 0 )
      break;
    v12 = (unsigned int *)v6[8];
    switch ( v30 )
    {
      case 0:
        LOBYTE(a2[v10 + 2]) = *((_BYTE *)v12 + 18);
        goto LABEL_40;
      case 1:
        a2[v10 + 2] = *v12;
        goto LABEL_40;
      case 2:
        v24 = *v12;
        v33 = 0;
        SecondsSince1970ToSystemTime(v24, &v33);
        *(_DWORD *)&v33.wYear = 67506;
        v33.wDay = 2;
        SystemTimeToSecondsSince1970(&v33, &a2[v10 + 2]);
        goto LABEL_40;
    }
    if ( v30 != 3 )
    {
      switch ( v30 )
      {
        case 4:
          if ( v12[6] != 1 || (v17 = v12[5], v17 == -1) )
          {
            if ( *((_WORD *)v12 + 6) )
            {
              v19 = v6[164];
              SourceStr = CLightRecCache::GetSourceStr(v32);
              Categories = CSources::GetCategories((CSources *)(v19 + 4784), SourceStr);
              if ( Categories && (v22 = *((unsigned __int16 *)v12 + 6), v22 <= *(_DWORD *)Categories) )
                Name = CCategories::GetName(Categories, v22);
              else
                Name = (const unsigned __int16 *)*((unsigned __int16 *)v12 + 6);
              v6 = v31;
            }
            else
            {
              Name = &g_wszNone;
            }
          }
          else
          {
            Name = CSharedStringArray::GetStringFromHandle((CSharedStringArray *)(v6 + 170), v17);
          }
          if ( WORD1(Name) )
          {
            Handle = CSharedStringArray::GetHandle((CSharedStringArray *)(v6 + 170), Name);
            Name = CSharedStringArray::GetStringFromHandle((CSharedStringArray *)(v6 + 170), Handle);
          }
          v6 = v31;
          v8 = v32;
          *(_QWORD *)&a2[v10 + 2] = Name;
          goto LABEL_41;
        case 5:
          LOWORD(a2[v10 + 2]) = *((_WORD *)v12 + 8);
          break;
        case 6:
          v16 = v12[1];
          v14 = (CSharedStringArray *)(v6 + 168);
          if ( v16 )
            ++*(_DWORD *)(16LL * (v16 - 1) + *(_QWORD *)v14);
          v15 = v12[1];
LABEL_18:
          *(_QWORD *)&a2[v10 + 2] = CSharedStringArray::GetStringFromHandle(v14, v15);
          break;
        case 7:
          v13 = v12[2];
          v14 = (CSharedStringArray *)(v6 + 166);
          if ( v13 )
            ++*(_DWORD *)(16LL * (v13 - 1) + *(_QWORD *)v14);
          v15 = v12[2];
          goto LABEL_18;
      }
LABEL_40:
      v8 = (CLightRecCache *)(v6 + 4);
      goto LABEL_41;
    }
    v8 = (CLightRecCache *)(v6 + 4);
    *(_QWORD *)&a2[v10 + 2] = CLightRecCache::GetSourceStr((CLightRecCache *)(v6 + 4));
LABEL_41:
    if ( ++v7 >= *a3 )
      return (unsigned int)v11;
  }
  if ( v7 > 2 )
  {
    *a3 = v7;
    return 0;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001a8f0  mov     [rsp+arg_18], rbx
0x18001a8f5  push    rbp
0x18001a8f6  push    rsi
0x18001a8f7  push    rdi
0x18001a8f8  push    r12
0x18001a8fa  push    r13
0x18001a8fc  push    r14
0x18001a8fe  push    r15
0x18001a900  sub     rsp, 50h
0x18001a904  mov     rax, cs:__security_cookie
0x18001a90b  xor     rax, rsp
0x18001a90e  mov     [rsp+88h+var_40], rax
0x18001a913  mov     eax, r9d
0x18001a916  mov     [rsp+88h+var_60], rcx
0x18001a91b  mov     [rsp+88h+var_64], eax
0x18001a91f  mov     r12, r8
0x18001a922  add     eax, 0FFFFFFF8h
0x18001a925  mov     r8d, 1
0x18001a92b  mov     r14, rdx
0x18001a92e  mov     rbx, rcx
0x18001a931  cmp     eax, r8d
0x18001a934  jbe     loc_18001AB83
0x18001a93a  mov     edx, [r12]; NumOfElements
0x18001a93e  lea     r9, ?CompareRecNoDescending@@YAHPEBX0@Z; CompareFunction
0x18001a945  mov     r8d, 10h; SizeOfElements
0x18001a94b  mov     rcx, r14; Base
0x18001a94e  call    cs:__imp_qsort
0x18001a954  xor     edi, edi
0x18001a956  mov     r13d, edi
0x18001a959  cmp     [r12], edi
0x18001a95d  jbe     loc_18001AB7D
0x18001a963  lea     rsi, [rbx+20h]
0x18001a967  mov     [rsp+88h+var_58], rsi
0x18001a96c  mov     rcx, [rsi+40h]; this
0x18001a970  lea     r8, [rsp+88h+var_68]; unsigned int *
0x18001a975  mov     r15d, r13d
0x18001a978  shl     r15, 4
0x18001a97c  mov     [rsp+88h+var_68], edi
0x18001a980  mov     edx, [r15+r14]; unsigned int
0x18001a984  call    ?RecNoToIndex@CRecList@@QEAAJKPEAK@Z; CRecList::RecNoToIndex(ulong,ulong *)
0x18001a989  mov     ebp, eax
0x18001a98b  test    eax, eax
0x18001a98d  js      short loc_18001A99D
0x18001a98f  mov     edx, [rsp+88h+var_68]; unsigned int
0x18001a993  mov     rcx, rsi; this
0x18001a996  call    ?SeekToIndex@CLightRecCache@@QEAAJK@Z; CLightRecCache::SeekToIndex(ulong)
0x18001a99b  mov     ebp, eax
0x18001a99d  test    ebp, ebp
0x18001a99f  js      loc_18001AB73
0x18001a9a5  mov     ecx, [rsp+88h+var_64]
0x18001a9a9  mov     rsi, [rbx+40h]
0x18001a9ad  test    ecx, ecx
0x18001a9af  jz      loc_18001AB58
0x18001a9b5  sub     ecx, 1
0x18001a9b8  jz      loc_18001AB4F
0x18001a9be  sub     ecx, 1
0x18001a9c1  jz      loc_18001AB16
0x18001a9c7  sub     ecx, 1
0x18001a9ca  jz      loc_18001AB03
0x18001a9d0  sub     ecx, 1
0x18001a9d3  jz      short loc_18001AA52
0x18001a9d5  sub     ecx, 1
0x18001a9d8  jz      short loc_18001AA43
0x18001a9da  sub     ecx, 1
0x18001a9dd  jz      short loc_18001AA1C
0x18001a9df  cmp     ecx, 1
0x18001a9e2  jnz     loc_18001AB60
0x18001a9e8  mov     eax, [rsi+8]
0x18001a9eb  lea     rcx, [rbx+530h]; this
0x18001a9f2  test    eax, eax
0x18001a9f4  jz      short loc_18001AA0A
0x18001a9f6  lea     edx, [rax-1]
0x18001a9f9  mov     r8d, 1
0x18001a9ff  mov     rax, [rcx]
0x18001aa02  shl     rdx, 4
0x18001aa06  add     [rdx+rax], r8d
0x18001aa0a  mov     edx, [rsi+8]; unsigned int
0x18001aa0d  call    ?GetStringFromHandle@CSharedStringArray@@QEAAPEAGK@Z; CSharedStringArray::GetStringFromHandle(ulong)
0x18001aa12  mov     [r15+r14+8], rax
0x18001aa17  jmp     loc_18001AB60
0x18001aa1c  mov     eax, [rsi+4]
0x18001aa1f  lea     rcx, [rbx+540h]
0x18001aa26  test    eax, eax
0x18001aa28  jz      short loc_18001AA3E
0x18001aa2a  lea     edx, [rax-1]
0x18001aa2d  mov     r8d, 1
0x18001aa33  mov     rax, [rcx]
0x18001aa36  shl     rdx, 4
0x18001aa3a  add     [rdx+rax], r8d
0x18001aa3e  mov     edx, [rsi+4]
0x18001aa41  jmp     short loc_18001AA0D
0x18001aa43  movzx   eax, word ptr [rsi+10h]
0x18001aa47  mov     [r15+r14+8], ax
0x18001aa4d  jmp     loc_18001AB60
0x18001aa52  mov     r8d, 1
0x18001aa58  cmp     [rsi+18h], r8d
0x18001aa5c  jnz     short loc_18001AA77
0x18001aa5e  mov     edx, [rsi+14h]; unsigned int
0x18001aa61  cmp     edx, 0FFFFFFFFh
0x18001aa64  jz      short loc_18001AA77
0x18001aa66  lea     rcx, [rbx+550h]; this
0x18001aa6d  call    ?GetStringFromHandle@CSharedStringArray@@QEAAPEAGK@Z; CSharedStringArray::GetStringFromHandle(ulong)
0x18001aa72  mov     rdx, rax
0x18001aa75  jmp     short loc_18001AAC9
0x18001aa77  cmp     [rsi+0Ch], di
0x18001aa7b  jz      short loc_18001AAC2
0x18001aa7d  mov     rcx, [rsp+88h+var_58]; this
0x18001aa82  mov     rbx, [rbx+520h]
0x18001aa89  call    ?GetSourceStr@CLightRecCache@@QEAAPEBGXZ; CLightRecCache::GetSourceStr(void)
0x18001aa8e  mov     rdx, rax; unsigned __int16 *
0x18001aa91  lea     rcx, [rbx+12B0h]; this
0x18001aa98  call    ?GetCategories@CSources@@QEAAPEAVCCategories@@PEBG@Z; CSources::GetCategories(ushort const *)
0x18001aa9d  test    rax, rax
0x18001aaa0  jz      short loc_18001AAB7
0x18001aaa2  movzx   edx, word ptr [rsi+0Ch]; unsigned int
0x18001aaa6  cmp     edx, [rax]
0x18001aaa8  ja      short loc_18001AAB7
0x18001aaaa  mov     rcx, rax; this
0x18001aaad  call    ?GetName@CCategories@@QEAAPEBGK@Z; CCategories::GetName(ulong)
0x18001aab2  mov     rdx, rax
0x18001aab5  jmp     short loc_18001AABB
0x18001aab7  movzx   edx, word ptr [rsi+0Ch]
0x18001aabb  mov     rbx, [rsp+88h+var_60]
0x18001aac0  jmp     short loc_18001AAC9
0x18001aac2  lea     rdx, ?g_wszNone@@3PAGA; unsigned __int16 *
0x18001aac9  mov     rax, rdx
0x18001aacc  shr     rax, 10h
0x18001aad0  test    ax, ax
0x18001aad3  jz      short loc_18001AAF2
0x18001aad5  lea     rcx, [rbx+550h]; this
0x18001aadc  call    ?GetHandle@CSharedStringArray@@QEAAKPEBG@Z; CSharedStringArray::GetHandle(ushort const *)
0x18001aae1  mov     edx, eax; unsigned int
0x18001aae3  lea     rcx, [rbx+550h]; this
0x18001aaea  call    ?GetStringFromHandle@CSharedStringArray@@QEAAPEAGK@Z; CSharedStringArray::GetStringFromHandle(ulong)
0x18001aaef  mov     rdx, rax
0x18001aaf2  mov     rbx, [rsp+88h+var_60]
0x18001aaf7  mov     rsi, [rsp+88h+var_58]
0x18001aafc  mov     [r15+r14+8], rdx
0x18001ab01  jmp     short loc_18001AB64
0x18001ab03  lea     rsi, [rbx+20h]
0x18001ab07  mov     rcx, rsi; this
0x18001ab0a  call    ?GetSourceStr@CLightRecCache@@QEAAPEBGXZ; CLightRecCache::GetSourceStr(void)
0x18001ab0f  mov     [r15+r14+8], rax
0x18001ab14  jmp     short loc_18001AB64
0x18001ab16  mov     ecx, [rsi]
0x18001ab18  lea     rdx, [rsp+88h+var_50]
0x18001ab1d  xorps   xmm0, xmm0
0x18001ab20  movups  xmmword ptr [rsp+88h+var_50.wYear], xmm0
0x18001ab25  call    SecondsSince1970ToSystemTime
0x18001ab2a  mov     eax, 2
0x18001ab2f  mov     dword ptr [rsp+88h+var_50.wYear], 107B2h
0x18001ab37  lea     rdx, [r14+8]
0x18001ab3b  mov     [rsp+88h+var_50.wDay], ax
0x18001ab40  add     rdx, r15; unsigned int *
0x18001ab43  lea     rcx, [rsp+88h+var_50]; struct _SYSTEMTIME *
0x18001ab48  call    ?SystemTimeToSecondsSince1970@@YAHPEAU_SYSTEMTIME@@PEAK@Z; SystemTimeToSecondsSince1970(_SYSTEMTIME *,ulong *)
0x18001ab4d  jmp     short loc_18001AB60
0x18001ab4f  mov     eax, [rsi]
0x18001ab51  mov     [r15+r14+8], eax
0x18001ab56  jmp     short loc_18001AB60
0x18001ab58  mov     al, [rsi+12h]
0x18001ab5b  mov     [r15+r14+8], al
0x18001ab60  lea     rsi, [rbx+20h]
0x18001ab64  inc     r13d
0x18001ab67  cmp     r13d, [r12]
0x18001ab6b  jb      loc_18001A96C
0x18001ab71  jmp     short loc_18001AB7F
0x18001ab73  cmp     r13d, 2
0x18001ab77  jbe     short loc_18001AB7F
0x18001ab79  mov     [r12], r13d
0x18001ab7d  mov     ebp, edi
0x18001ab7f  mov     eax, ebp
0x18001ab81  jmp     short loc_18001ABAC
0x18001ab83  mov     edx, [rcx+2D4h]
0x18001ab89  xor     edi, edi
0x18001ab8b  cmp     [r12], edi
0x18001ab8f  jbe     short loc_18001ABAA
0x18001ab91  mov     ecx, edi
0x18001ab93  add     edi, r8d
0x18001ab96  add     rcx, rcx
0x18001ab99  mov     eax, [r14+rcx*8]
0x18001ab9d  sub     eax, edx
0x18001ab9f  mov     [r14+rcx*8+8], eax
0x18001aba4  cmp     edi, [r12]
0x18001aba8  jb      short loc_18001AB91
0x18001abaa  xor     eax, eax
0x18001abac  mov     rcx, [rsp+88h+var_40]
0x18001abb1  xor     rcx, rsp; StackCookie
0x18001abb4  call    __security_check_cookie
0x18001abb9  mov     rbx, [rsp+88h+arg_18]
0x18001abc1  add     rsp, 50h
0x18001abc5  pop     r15
0x18001abc7  pop     r14
0x18001abc9  pop     r13
0x18001abcb  pop     r12
0x18001abcd  pop     rdi
0x18001abce  pop     rsi
0x18001abcf  pop     rbp
0x18001abd0  retn
```
