# CRTFConverter::ReadFontSubInfo(void)

- ea: `0x18007dc60`
- end: `0x18007df93`
- name: `?ReadFontSubInfo@CRTFConverter@@IEAAXXZ`
- size: `819`
- prototype: `void __fastcall(CRTFConverter *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18004bc28`

## callees

- `0x180022780`
- `0x180023010`
- `0x180039e64`
- `0x18004180c`
- `0x18007db38`
- `0x18007dc60`
- `0x18008e000`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18007dc7f`
- `KERNEL32!EnterCriticalSection` at `0x18007dc7f`
- `KERNEL32!LeaveCriticalSection` at `0x18007df8c`

## pseudocode

```c
void __fastcall CRTFConverter::ReadFontSubInfo(CRTFConverter *this)
{
  signed int v1; // ebx
  unsigned __int16 *v2; // rdx
  const unsigned __int16 *v3; // rcx
  signed int ProfileSection; // eax
  __int64 v5; // rdi
  WCHAR *v6; // rax
  WCHAR *v7; // rax
  _WORD *v8; // rcx
  char *v9; // rbx
  int v10; // r13d
  int v11; // eax
  WCHAR *v12; // r12
  unsigned int v13; // edi
  __int64 v14; // r14
  _WORD *v15; // r15
  __int64 i; // rsi
  wchar_t **j; // rdi
  char v18; // al
  char *v19; // rax
  __int64 v20; // rdx
  int v21; // [rsp+40h] [rbp-28h] BYREF
  LPWSTR v22; // [rsp+48h] [rbp-20h] BYREF
  __int64 v23; // [rsp+50h] [rbp-18h] BYREF
  _WORD *v24; // [rsp+58h] [rbp-10h] BYREF
  CRTFConverter *v25; // [rsp+B0h] [rbp+48h] BYREF
  char v26; // [rsp+B8h] [rbp+50h] BYREF
  int v27; // [rsp+C0h] [rbp+58h]
  int v28; // [rsp+C8h] [rbp+60h] BYREF

  v25 = this;
  EnterCriticalSection(&g_CriticalSection);
  if ( CRTFConverter::_ctfi )
    goto LABEL_47;
  v1 = 600;
  CRTFConverter::_pchFontSubInfo = (LPWSTR)CW32System::PvAlloc(0x4B0u, 0);
  if ( !CRTFConverter::_pchFontSubInfo )
    goto LABEL_42;
  while ( 1 )
  {
    ProfileSection = CW32System::GetProfileSection(v3, v2, v1);
    v5 = ProfileSection;
    if ( ProfileSection < v1 - 2 )
      break;
    if ( (v1 & 0x20000000) != 0 )
      goto LABEL_42;
    if ( 2 * v1 < v1 )
      goto LABEL_42;
    v6 = (WCHAR *)CW32System::PvReAlloc(CRTFConverter::_pchFontSubInfo, 4 * v1);
    if ( !v6 )
      goto LABEL_42;
    v1 *= 2;
    CRTFConverter::_pchFontSubInfo = v6;
  }
  if ( ProfileSection )
  {
    v7 = (WCHAR *)CW32System::PvReAlloc(CRTFConverter::_pchFontSubInfo, 2 * ProfileSection);
    if ( !v7 )
      goto LABEL_42;
    CRTFConverter::_pchFontSubInfo = v7;
  }
  else
  {
    *CRTFConverter::_pchFontSubInfo = 0;
  }
  CRTFConverter::_ctfi = 12;
  CRTFConverter::_rgtfi = CW32System::PvAlloc(0x120u, 0);
  v9 = (char *)CRTFConverter::_rgtfi;
  if ( !CRTFConverter::_rgtfi )
  {
LABEL_42:
    if ( CRTFConverter::_pchFontSubInfo )
    {
      CW32System::FreePv(CRTFConverter::_pchFontSubInfo);
      CRTFConverter::_pchFontSubInfo = 0;
    }
    if ( CRTFConverter::_rgtfi )
    {
      CW32System::FreePv(CRTFConverter::_rgtfi);
      CRTFConverter::_rgtfi = 0;
    }
    CRTFConverter::_ctfi = 0;
    goto LABEL_47;
  }
  v10 = 0;
  v22 = CRTFConverter::_pchFontSubInfo;
  v11 = 0;
  v23 = 0;
  v24 = 0;
  v12 = &CRTFConverter::_pchFontSubInfo[v5];
  LOBYTE(v25) = 0;
  v13 = CRTFConverter::_ctfi;
  v26 = 0;
  while ( v22 < v12 && v11 != 2 && v10 != 2 )
  {
    v28 = 0;
    v21 = 0;
    v11 = CRTFConverter::ParseFontName(v8, v22, v12, 61, &v23, &v25, &v28, &v22);
    v27 = v11;
    if ( !v11 )
    {
      v10 = CRTFConverter::ParseFontName(v8, v22, v12, 0, &v24, &v26, &v21, &v22);
      if ( v10 )
        goto LABEL_39;
      v14 = v23;
      v15 = v24;
      if ( v28 )
      {
        v18 = (char)v25;
      }
      else
      {
        v8 = v24;
        for ( i = v23; *v8 == *(_WORD *)i; ++v8 )
          i += 2;
        while ( *v8 )
        {
          if ( *v8 != 32 && *v8 != 9 )
            goto LABEL_39;
          ++v8;
        }
        for ( j = &off_180096490; ; j += 2 )
        {
          if ( !*((_BYTE *)j + 8) )
          {
            v13 = CRTFConverter::_ctfi;
            goto LABEL_39;
          }
          if ( !(unsigned int)CW32System::lstrcmpi((const unsigned __int16 *)(i + 2), *j) )
            break;
        }
        v18 = *((_BYTE *)j + 8);
        v13 = CRTFConverter::_ctfi;
      }
      if ( v21 && v18 != v26 )
        goto LABEL_39;
      v8 = CRTFConverter::_rgtfi;
      v9[16] = v18;
      *((_QWORD *)v9 + 1) = v14;
      *(_QWORD *)v9 = v15;
      v9 += 24;
      if ( -1431655765 * (unsigned int)((v9 - (char *)v8) >> 3) < v13 )
      {
        v11 = v27;
      }
      else
      {
        v19 = (char *)CW32System::PvReAlloc(v8, 24 * (v13 + 4));
        CRTFConverter::_rgtfi = v19;
        if ( !v19 )
          goto LABEL_42;
        v20 = 3LL * CRTFConverter::_ctfi;
        v13 = CRTFConverter::_ctfi + 4;
        CRTFConverter::_ctfi += 4;
        v9 = &v19[8 * v20];
LABEL_39:
        v11 = v27;
      }
    }
  }
  CRTFConverter::_ctfi = -1431655765 * ((v9 - (_BYTE *)CRTFConverter::_rgtfi) >> 3);
  if ( !CRTFConverter::_ctfi )
    goto LABEL_42;
LABEL_47:
  LeaveCriticalSection(&g_CriticalSection);
}

```

## disassembly

```asm
0x18007dc60  mov     [rsp-40h+arg_0], rcx
0x18007dc65  push    rbp
0x18007dc66  push    rbx
0x18007dc67  push    rsi
0x18007dc68  push    rdi
0x18007dc69  push    r12
0x18007dc6b  push    r13
0x18007dc6d  push    r14
0x18007dc6f  push    r15
0x18007dc71  mov     rbp, rsp
0x18007dc74  sub     rsp, 68h
0x18007dc78  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18007dc7f  call    cs:__imp_EnterCriticalSection
0x18007dc85  xor     esi, esi
0x18007dc87  cmp     cs:?_ctfi@CRTFConverter@@1HA, esi; int CRTFConverter::_ctfi
0x18007dc8d  jnz     loc_18007DF75
0x18007dc93  xor     edx, edx; unsigned int
0x18007dc95  mov     ecx, 4B0h; unsigned int
0x18007dc9a  mov     ebx, 258h
0x18007dc9f  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18007dca4  mov     cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA, rax; ushort * CRTFConverter::_pchFontSubInfo
0x18007dcab  test    rax, rax
0x18007dcae  jz      loc_18007DF3F
0x18007dcb4  mov     r8d, ebx; unsigned int
0x18007dcb7  call    ?GetProfileSection@CW32System@@SAKPEBGPEAGK@Z; CW32System::GetProfileSection(ushort const *,ushort *,ulong)
0x18007dcbc  movsxd  rdi, eax
0x18007dcbf  lea     ecx, [rbx-2]
0x18007dcc2  cmp     edi, ecx
0x18007dcc4  jl      short loc_18007DCFC
0x18007dcc6  lea     edi, [rbx+rbx]
0x18007dcc9  lea     edx, [rdi+rdi]; unsigned int
0x18007dccc  test    edx, edx
0x18007dcce  js      loc_18007DF3F
0x18007dcd4  cmp     edi, ebx
0x18007dcd6  jl      loc_18007DF3F
0x18007dcdc  mov     rcx, cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA; void *
0x18007dce3  call    ?PvReAlloc@CW32System@@SAPEAXPEAXK@Z; CW32System::PvReAlloc(void *,ulong)
0x18007dce8  test    rax, rax
0x18007dceb  jz      loc_18007DF3F
0x18007dcf1  mov     ebx, edi
0x18007dcf3  mov     cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA, rax; ushort * CRTFConverter::_pchFontSubInfo
0x18007dcfa  jmp     short loc_18007DCB4
0x18007dcfc  test    eax, eax
0x18007dcfe  jnz     short loc_18007DD0C
0x18007dd00  mov     rax, cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA; ushort * CRTFConverter::_pchFontSubInfo
0x18007dd07  mov     [rax], si
0x18007dd0a  jmp     short loc_18007DD2B
0x18007dd0c  mov     rcx, cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA; void *
0x18007dd13  lea     edx, [rdi+rdi]; unsigned int
0x18007dd16  call    ?PvReAlloc@CW32System@@SAPEAXPEAXK@Z; CW32System::PvReAlloc(void *,ulong)
0x18007dd1b  test    rax, rax
0x18007dd1e  jz      loc_18007DF3F
0x18007dd24  mov     cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA, rax; ushort * CRTFConverter::_pchFontSubInfo
0x18007dd2b  xor     edx, edx; unsigned int
0x18007dd2d  mov     cs:?_ctfi@CRTFConverter@@1HA, 0Ch; int CRTFConverter::_ctfi
0x18007dd37  mov     ecx, 120h; unsigned int
0x18007dd3c  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18007dd41  mov     cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA, rax; _tfi * CRTFConverter::_rgtfi
0x18007dd48  mov     rbx, rax
0x18007dd4b  test    rax, rax
0x18007dd4e  jz      loc_18007DF3F
0x18007dd54  mov     rdx, cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA; ushort * CRTFConverter::_pchFontSubInfo
0x18007dd5b  mov     r13d, esi
0x18007dd5e  mov     [rbp+var_20], rdx
0x18007dd62  mov     eax, esi
0x18007dd64  mov     [rbp+var_18], rsi
0x18007dd68  mov     [rbp+var_10], rsi
0x18007dd6c  lea     r12, [rdx+rdi*2]
0x18007dd70  mov     byte ptr [rbp+arg_0], sil
0x18007dd74  mov     edi, cs:?_ctfi@CRTFConverter@@1HA; int CRTFConverter::_ctfi
0x18007dd7a  mov     [rbp+arg_8], sil
0x18007dd7e  mov     r8, 0AAAAAAAAAAAAAAABh
0x18007dd88  mov     rdx, [rbp+var_20]
0x18007dd8c  cmp     rdx, r12
0x18007dd8f  jnb     loc_18007DF26
0x18007dd95  cmp     eax, 2
0x18007dd98  jz      loc_18007DF26
0x18007dd9e  cmp     r13d, 2
0x18007dda2  jz      loc_18007DF26
0x18007dda8  lea     rax, [rbp+var_20]
0x18007ddac  mov     [rbp+arg_18], esi
0x18007ddaf  mov     [rsp+68h+var_30], rax
0x18007ddb4  mov     r9d, 3Dh ; '='
0x18007ddba  lea     rax, [rbp+arg_18]
0x18007ddbe  mov     [rbp+var_28], esi
0x18007ddc1  mov     [rsp+68h+var_38], rax
0x18007ddc6  mov     r8, r12
0x18007ddc9  lea     rax, [rbp+arg_0]
0x18007ddcd  mov     [rsp+68h+var_40], rax
0x18007ddd2  lea     rax, [rbp+var_18]
0x18007ddd6  mov     [rsp+68h+var_48], rax
0x18007dddb  call    ?ParseFontName@CRTFConverter@@IEBA?AW4PARSEFONTNAME@1@PEAG0GPEAPEAGAEAEAEAH1@Z; CRTFConverter::ParseFontName(ushort *,ushort *,ushort,ushort * *,uchar &,int &,ushort * *)
0x18007dde0  mov     [rbp+arg_10], eax
0x18007dde3  test    eax, eax
0x18007dde5  jnz     short loc_18007DD7E
0x18007dde7  mov     rdx, [rbp+var_20]
0x18007ddeb  lea     rax, [rbp+var_20]
0x18007ddef  mov     [rsp+68h+var_30], rax
0x18007ddf4  xor     r9d, r9d
0x18007ddf7  lea     rax, [rbp+var_28]
0x18007ddfb  mov     r8, r12
0x18007ddfe  mov     [rsp+68h+var_38], rax
0x18007de03  lea     rax, [rbp+arg_8]
0x18007de07  mov     [rsp+68h+var_40], rax
0x18007de0c  lea     rax, [rbp+var_10]
0x18007de10  mov     [rsp+68h+var_48], rax
0x18007de15  call    ?ParseFontName@CRTFConverter@@IEBA?AW4PARSEFONTNAME@1@PEAG0GPEAPEAGAEAEAEAH1@Z; CRTFConverter::ParseFontName(ushort *,ushort *,ushort,ushort * *,uchar &,int &,ushort * *)
0x18007de1a  mov     r13d, eax
0x18007de1d  test    eax, eax
0x18007de1f  jnz     loc_18007DF16
0x18007de25  mov     r14, [rbp+var_18]
0x18007de29  mov     r15, [rbp+var_10]
0x18007de2d  cmp     [rbp+arg_18], esi
0x18007de30  jnz     short loc_18007DEA6
0x18007de32  movzx   eax, word ptr [r14]
0x18007de36  mov     rcx, r15
0x18007de39  mov     rsi, r14
0x18007de3c  cmp     [r15], ax
0x18007de40  jnz     short loc_18007DE52
0x18007de42  add     rsi, 2
0x18007de46  add     rcx, 2
0x18007de4a  movzx   eax, word ptr [rsi]
0x18007de4d  cmp     [rcx], ax
0x18007de50  jz      short loc_18007DE42
0x18007de52  xor     eax, eax
0x18007de54  cmp     [rcx], ax
0x18007de57  jz      short loc_18007DE6B
0x18007de59  cmp     word ptr [rcx], 20h ; ' '
0x18007de5d  jz      short loc_18007DE65
0x18007de5f  cmp     word ptr [rcx], 9
0x18007de63  jnz     short loc_18007DE95
0x18007de65  add     rcx, 2
0x18007de69  jmp     short loc_18007DE54
0x18007de6b  lea     rdi, off_180096490; "cyr"
0x18007de72  cmp     [rdi+8], al
0x18007de75  jz      short loc_18007DE8F
0x18007de77  mov     rdx, [rdi]; unsigned __int16 *
0x18007de7a  lea     rcx, [rsi+2]; unsigned __int16 *
0x18007de7e  call    ?lstrcmpi@CW32System@@SAHPEBG0@Z; CW32System::lstrcmpi(ushort const *,ushort const *)
0x18007de83  test    eax, eax
0x18007de85  jz      short loc_18007DE99
0x18007de87  add     rdi, 10h
0x18007de8b  xor     eax, eax
0x18007de8d  jmp     short loc_18007DE72
0x18007de8f  mov     edi, cs:?_ctfi@CRTFConverter@@1HA; int CRTFConverter::_ctfi
0x18007de95  xor     esi, esi
0x18007de97  jmp     short loc_18007DF16
0x18007de99  mov     al, [rdi+8]
0x18007de9c  xor     esi, esi
0x18007de9e  mov     edi, cs:?_ctfi@CRTFConverter@@1HA; int CRTFConverter::_ctfi
0x18007dea4  jmp     short loc_18007DEA9
0x18007dea6  mov     al, byte ptr [rbp+arg_0]
0x18007dea9  cmp     [rbp+var_28], esi
0x18007deac  jz      short loc_18007DEB3
0x18007deae  cmp     al, [rbp+arg_8]
0x18007deb1  jnz     short loc_18007DF16
0x18007deb3  mov     rcx, cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA; void *
0x18007deba  mov     r8, 0AAAAAAAAAAAAAAABh
0x18007dec4  mov     [rbx+10h], al
0x18007dec7  mov     [rbx+8], r14
0x18007decb  mov     [rbx], r15
0x18007dece  add     rbx, 18h
0x18007ded2  mov     rax, rbx
0x18007ded5  sub     rax, rcx
0x18007ded8  sar     rax, 3
0x18007dedc  imul    rax, r8
0x18007dee0  cmp     eax, edi
0x18007dee2  jb      short loc_18007DF1E
0x18007dee4  lea     eax, [rdi+4]
0x18007dee7  lea     edx, [rax+rax*2]
0x18007deea  shl     edx, 3; unsigned int
0x18007deed  call    ?PvReAlloc@CW32System@@SAPEAXPEAXK@Z; CW32System::PvReAlloc(void *,ulong)
0x18007def2  mov     cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA, rax; _tfi * CRTFConverter::_rgtfi
0x18007def9  test    rax, rax
0x18007defc  jz      short loc_18007DF3F
0x18007defe  movsxd  rdi, cs:?_ctfi@CRTFConverter@@1HA; int CRTFConverter::_ctfi
0x18007df05  lea     rdx, [rdi+rdi*2]
0x18007df09  add     edi, 4
0x18007df0c  mov     cs:?_ctfi@CRTFConverter@@1HA, edi; int CRTFConverter::_ctfi
0x18007df12  lea     rbx, [rax+rdx*8]
0x18007df16  mov     eax, [rbp+arg_10]
0x18007df19  jmp     loc_18007DD7E
0x18007df1e  mov     eax, [rbp+arg_10]
0x18007df21  jmp     loc_18007DD88
0x18007df26  sub     rbx, cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA; _tfi * CRTFConverter::_rgtfi
0x18007df2d  sar     rbx, 3
0x18007df31  imul    rbx, r8
0x18007df35  mov     cs:?_ctfi@CRTFConverter@@1HA, ebx; int CRTFConverter::_ctfi
0x18007df3b  test    ebx, ebx
0x18007df3d  jnz     short loc_18007DF75
0x18007df3f  mov     rcx, cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA; lpMem
0x18007df46  test    rcx, rcx
0x18007df49  jz      short loc_18007DF57
0x18007df4b  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x18007df50  mov     cs:?_pchFontSubInfo@CRTFConverter@@1PEAGEA, rsi; ushort * CRTFConverter::_pchFontSubInfo
0x18007df57  mov     rcx, cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA; lpMem
0x18007df5e  test    rcx, rcx
0x18007df61  jz      short loc_18007DF6F
0x18007df63  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x18007df68  mov     cs:?_rgtfi@CRTFConverter@@1PEAU_tfi@@EA, rsi; _tfi * CRTFConverter::_rgtfi
0x18007df6f  mov     cs:?_ctfi@CRTFConverter@@1HA, esi; int CRTFConverter::_ctfi
0x18007df75  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CriticalSection
0x18007df7c  add     rsp, 68h
0x18007df80  pop     r15
0x18007df82  pop     r14
0x18007df84  pop     r13
0x18007df86  pop     r12
0x18007df88  pop     rdi
0x18007df89  pop     rsi
0x18007df8a  pop     rbx
0x18007df8b  pop     rbp
0x18007df8c  jmp     cs:__imp_LeaveCriticalSection
```
