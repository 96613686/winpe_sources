# _RtlpMuiRegValidateInstalled

- ea: `0x18014db50`
- end: `0x18014df18`
- name: `_RtlpMuiRegValidateInstalled`
- size: `968`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1801205f0`

## callees

- `0x18000908c`
- `0x18000a360`
- `0x18000c6b0`
- `0x18001861c`
- `0x1800b8d7c`
- `0x1800b8f30`
- `0x1800b9060`
- `0x1800c8c50`
- `0x18014cc38`
- `0x18014db50`
- `0x18014df20`
- `0x18014e150`
- `0x18014e26c`
- `0x180160420`
- `0x180160e40`
- `0x180162000`
- `0x18016f030`

## pseudocode

```c
__int64 __fastcall RtlpMuiRegValidateInstalled(__int64 a1)
{
  __int16 v2; // si
  int IsUILanguageComitted; // eax
  __int64 v4; // rdx
  int v5; // r13d
  __int64 result; // rax
  int v7; // r14d
  int InstalledLanguageIndexByLangId; // eax
  __int64 v9; // rcx
  __int64 v10; // r12
  __int64 v11; // rax
  __int64 v12; // r8
  int v13; // eax
  __int16 v14; // cx
  int v15; // edi
  __int64 v16; // rcx
  int v17; // esi
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int16 v20; // cx
  int v21; // edx
  __int64 v22; // r9
  __int16 v23; // cx
  unsigned int v24; // eax
  __int64 v25; // rdx
  int v26; // edi
  _WORD v27[2]; // [rsp+20h] [rbp-E0h] BYREF
  _WORD v28[2]; // [rsp+24h] [rbp-DCh] BYREF
  int v29; // [rsp+28h] [rbp-D8h] BYREF
  __int16 v30; // [rsp+2Ch] [rbp-D4h]
  __int16 v31; // [rsp+2Eh] [rbp-D2h]
  __int16 v32; // [rsp+30h] [rbp-D0h]
  __int128 v33; // [rsp+32h] [rbp-CEh]
  __int16 v34; // [rsp+42h] [rbp-BEh]
  __int64 v35; // [rsp+48h] [rbp-B8h]
  __int128 v36; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v37; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v38[176]; // [rsp+70h] [rbp-90h] BYREF

  v27[0] = 0;
  v2 = -1;
  v34 = 0;
  v28[0] = -1;
  v37 = 0;
  v33 = 0;
  v36 = 0;
  memset_thunk_772440563353939046(v38, 0, 0xAAu);
  IsUILanguageComitted = NtIsUILanguageComitted();
  v4 = *(unsigned __int16 *)(a1 + 4);
  v5 = IsUILanguageComitted;
  if ( (_WORD)v4 )
  {
    v27[0] = *(_WORD *)(a1 + 4);
  }
  else
  {
    result = NtQueryInstallUILanguage(v27);
    if ( (int)result < 0 )
      return result;
    v4 = v27[0];
  }
  v7 = -1;
  InstalledLanguageIndexByLangId = RtlpMuiRegGetInstalledLanguageIndexByLangId(a1, v4, 0, v28);
  if ( InstalledLanguageIndexByLangId == -1073741772 || InstalledLanguageIndexByLangId == -1073741637 )
  {
    v28[0] = -1;
    v11 = MuiRegAllocArray(v9, 85);
    v35 = v11;
    v10 = v11;
    if ( !v11 )
      return 3221225495LL;
    if ( (unsigned __int8)RtlpInitAndCallLcidToCultureName(&v37, v11, v27[0]) )
    {
      LOBYTE(v12) = 1;
      v13 = RtlpMuiRegGetOrAddString(a1, *((_QWORD *)&v37 + 1), v12, v28);
      v14 = -1;
      if ( v13 >= 0 )
        v14 = v28[0];
      v30 = v27[0];
      v31 = v14;
      *(_QWORD *)((char *)&v33 + 2) = 0;
      *(_DWORD *)((char *)&v33 + 10) = 0;
      HIWORD(v33) = 0;
      v34 = 0;
      v29 = 49;
      v32 = 0;
      RtlpMuiRegAddNeutralLanguage(a1, &v29, *((_QWORD *)&v37 + 1));
      if ( (int)RtlpMuiRegGetOrAddLangInfo(a1 + 24, &v29, 0) >= 0 )
        v7 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 24) + 6LL) - 1;
    }
  }
  else
  {
    v35 = 0;
    v10 = 0;
    if ( InstalledLanguageIndexByLangId >= 0 )
      v7 = v28[0];
  }
  v15 = 0;
  if ( v7 != -1 )
  {
    *((_QWORD *)&v36 + 1) = v38;
    WORD1(v36) = 170;
    if ( (int)RtlpGetNameFromLangInfoNode(a1, 28LL * v7 + *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL), &v36) >= 0 )
    {
      if ( (int)RtlpIsALicensedRegularLanguage(a1, *((_QWORD *)&v36 + 1)) >= 0 )
      {
        v15 = 1;
      }
      else
      {
        *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) + 28LL * v7) &= ~0x20u;
        *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) + 28LL * v7) |= 0x8000u;
      }
    }
  }
  if ( !v5 )
    v2 = v7;
  RtlpRemovePendingDeleteLanguages(a1, v2);
  v16 = *(_QWORD *)(a1 + 24);
  if ( *(_WORD *)(v16 + 6) )
  {
    v17 = 0;
    do
    {
      if ( (*(_BYTE *)(28LL * v17 + *(_QWORD *)(v16 + 16)) & 0x22) == 0x22 )
      {
        RtlpMuiRegValidatePartialLanguage(a1, (unsigned int)v17);
        v18 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL);
        v19 = v15 + 1;
        v20 = *(_WORD *)(v18 + 28LL * v17);
        if ( (v20 & 0x1000) != 0 )
          v19 = v15;
        v15 = v19;
        if ( !v5 && v17 != v7 && v19 > *(_DWORD *)(a1 + 120) )
        {
          *(_WORD *)(v18 + 28LL * v17) = v20 & 0xFFDF;
          *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) + 28LL * v17) |= 0x8000u;
        }
      }
      v16 = *(_QWORD *)(a1 + 24);
      ++v17;
    }
    while ( v17 < *(unsigned __int16 *)(v16 + 6) );
    v10 = v35;
  }
  if ( !v5 && *(_WORD *)(v16 + 6) )
  {
    v21 = 0;
    do
    {
      v22 = *(_QWORD *)(v16 + 16);
      v23 = *(_WORD *)(v22 + 28LL * v21);
      if ( (v23 & 0x21) == 0x21 )
      {
        v24 = v15 + 1;
        if ( (v23 & 0x1000) != 0 )
          v24 = v15;
        v15 = v24;
        if ( v21 != v7 && v24 > *(_DWORD *)(a1 + 120) )
        {
          *(_WORD *)(v22 + 28LL * v21) = v23 & 0xFFDF;
          *(_WORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 16LL) + 28LL * v21) |= 0x8000u;
        }
      }
      v16 = *(_QWORD *)(a1 + 24);
      ++v21;
    }
    while ( v21 < *(unsigned __int16 *)(v16 + 6) );
    v10 = v35;
  }
  v25 = *(_QWORD *)(a1 + 24);
  if ( *(_WORD *)(v25 + 6) )
  {
    v26 = 0;
    do
    {
      if ( (*(_BYTE *)(28LL * v26 + *(_QWORD *)(v25 + 16)) & 4) != 0 )
        RtlpMuiRegValidateLIPLanguage(a1, (unsigned int)v26);
      v25 = *(_QWORD *)(a1 + 24);
      ++v26;
    }
    while ( v26 < *(unsigned __int16 *)(v25 + 6) );
  }
  if ( v10 )
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v10);
  return 0;
}

```

## disassembly

```asm
0x18014db50  push    rbp
0x18014db52  push    rbx
0x18014db53  push    rsi
0x18014db54  push    rdi
0x18014db55  push    r12
0x18014db57  push    r13
0x18014db59  push    r14
0x18014db5b  push    r15
0x18014db5d  lea     rbp, [rsp-38h]
0x18014db62  sub     rsp, 138h
0x18014db69  mov     rax, cs:__security_cookie
0x18014db70  xor     rax, rsp
0x18014db73  mov     [rbp+70h+var_50], rax
0x18014db77  xorps   xmm0, xmm0
0x18014db7a  mov     rbx, rcx
0x18014db7d  xor     r15d, r15d
0x18014db80  lea     rcx, [rsp+170h+var_100]; void *
0x18014db85  xorps   xmm1, xmm1
0x18014db88  mov     [rsp+170h+var_150], r15w
0x18014db8e  or      esi, 0FFFFFFFFh
0x18014db91  mov     [rsp+170h+var_12E], r15w
0x18014db97  xor     edx, edx; Val
0x18014db99  mov     [rsp+170h+var_14C], si
0x18014db9e  mov     r8d, 0AAh; Size
0x18014dba4  movups  [rsp+170h+var_110], xmm0
0x18014dba9  movdqu  [rsp+170h+var_13E], xmm1
0x18014dbaf  movups  [rsp+170h+var_120], xmm0
0x18014dbb4  call    memset$thunk$772440563353939046
0x18014dbb9  call    NtIsUILanguageComitted
0x18014dbbe  movzx   edx, word ptr [rbx+4]
0x18014dbc2  mov     r13d, eax
0x18014dbc5  test    dx, dx
0x18014dbc8  jz      short loc_18014DBD1
0x18014dbca  mov     [rsp+170h+var_150], dx
0x18014dbcf  jmp     short loc_18014DBE8
0x18014dbd1  lea     rcx, [rsp+170h+var_150]
0x18014dbd6  call    NtQueryInstallUILanguage
0x18014dbdb  test    eax, eax
0x18014dbdd  js      loc_18014DEF7
0x18014dbe3  movzx   edx, [rsp+170h+var_150]
0x18014dbe8  lea     r9, [rsp+170h+var_14C]
0x18014dbed  xor     r8d, r8d
0x18014dbf0  mov     rcx, rbx
0x18014dbf3  mov     r14d, esi
0x18014dbf6  call    RtlpMuiRegGetInstalledLanguageIndexByLangId
0x18014dbfb  cmp     eax, 0C0000034h
0x18014dc00  jz      short loc_18014DC24
0x18014dc02  cmp     eax, 0C00000BBh
0x18014dc07  jz      short loc_18014DC24
0x18014dc09  mov     [rsp+170h+var_128], r15
0x18014dc0e  mov     r12, r15
0x18014dc11  test    eax, eax
0x18014dc13  js      loc_18014DD01
0x18014dc19  movsx   r14d, [rsp+170h+var_14C]
0x18014dc1f  jmp     loc_18014DD01
0x18014dc24  mov     edx, 55h ; 'U'
0x18014dc29  mov     [rsp+170h+var_14C], si
0x18014dc2e  call    _MuiRegAllocArray
0x18014dc33  mov     [rsp+170h+var_128], rax
0x18014dc38  mov     r12, rax
0x18014dc3b  test    rax, rax
0x18014dc3e  jnz     short loc_18014DC4A
0x18014dc40  mov     eax, 0C0000017h
0x18014dc45  jmp     loc_18014DEF7
0x18014dc4a  movzx   r8d, [rsp+170h+var_150]
0x18014dc50  lea     rcx, [rsp+170h+var_110]
0x18014dc55  mov     rdx, rax
0x18014dc58  call    RtlpInitAndCallLcidToCultureName
0x18014dc5d  test    al, al
0x18014dc5f  jz      loc_18014DD01
0x18014dc65  mov     rdx, qword ptr [rsp+170h+var_110+8]
0x18014dc6a  lea     r9, [rsp+170h+var_14C]
0x18014dc6f  mov     r8b, 1
0x18014dc72  mov     rcx, rbx
0x18014dc75  call    RtlpMuiRegGetOrAddString
0x18014dc7a  movzx   ecx, si
0x18014dc7d  test    eax, eax
0x18014dc7f  js      short loc_18014DC86
0x18014dc81  movzx   ecx, [rsp+170h+var_14C]
0x18014dc86  movzx   eax, [rsp+170h+var_150]
0x18014dc8b  lea     rdx, [rsp+170h+var_148]
0x18014dc90  mov     r8, qword ptr [rsp+170h+var_110+8]
0x18014dc95  mov     [rsp+170h+var_144], ax
0x18014dc9a  mov     eax, r15d
0x18014dc9d  mov     [rsp+170h+var_142], cx
0x18014dca2  mov     rcx, rbx
0x18014dca5  mov     word ptr [rsp+170h+var_13E+2], ax
0x18014dcaa  mov     word ptr [rsp+170h+var_13E+4], ax
0x18014dcaf  mov     word ptr [rsp+170h+var_13E+6], ax
0x18014dcb4  mov     word ptr [rsp+170h+var_13E+8], ax
0x18014dcb9  mov     word ptr [rsp+170h+var_13E+0Ah], ax
0x18014dcbe  mov     word ptr [rsp+170h+var_13E+0Ch], ax
0x18014dcc3  mov     word ptr [rsp+170h+var_13E+0Eh], ax
0x18014dcc8  mov     [rsp+170h+var_12E], ax
0x18014dccd  mov     [rsp+170h+var_148], 31h ; '1'
0x18014dcd5  mov     [rsp+170h+var_140], r15w
0x18014dcdb  call    _RtlpMuiRegAddNeutralLanguage
0x18014dce0  xor     r8d, r8d
0x18014dce3  lea     rdx, [rsp+170h+var_148]
0x18014dce8  lea     rcx, [rbx+18h]
0x18014dcec  call    RtlpMuiRegGetOrAddLangInfo
0x18014dcf1  test    eax, eax
0x18014dcf3  js      short loc_18014DD01
0x18014dcf5  mov     rax, [rbx+18h]
0x18014dcf9  movzx   r14d, word ptr [rax+6]
0x18014dcfe  dec     r14d
0x18014dd01  mov     edi, r15d
0x18014dd04  cmp     r14d, esi
0x18014dd07  jz      short loc_18014DD7F
0x18014dd09  lea     rax, [rsp+170h+var_100]
0x18014dd0e  mov     rcx, rbx
0x18014dd11  mov     qword ptr [rsp+170h+var_120+8], rax
0x18014dd16  lea     r8, [rsp+170h+var_120]
0x18014dd1b  mov     eax, 0AAh
0x18014dd20  mov     word ptr [rsp+170h+var_120+2], ax
0x18014dd25  movsxd  rax, r14d
0x18014dd28  imul    r15, rax, 1Ch
0x18014dd2c  mov     rax, [rbx+18h]
0x18014dd30  mov     rdx, [rax+10h]
0x18014dd34  add     rdx, r15
0x18014dd37  call    RtlpGetNameFromLangInfoNode
0x18014dd3c  test    eax, eax
0x18014dd3e  js      short loc_18014DD7C
0x18014dd40  mov     rdx, qword ptr [rsp+170h+var_120+8]
0x18014dd45  mov     rcx, rbx
0x18014dd48  call    RtlpIsALicensedRegularLanguage
0x18014dd4d  test    eax, eax
0x18014dd4f  jns     short loc_18014DD77
0x18014dd51  mov     rax, [rbx+18h]
0x18014dd55  mov     rcx, [rax+10h]
0x18014dd59  mov     eax, 0FFDFh
0x18014dd5e  and     [rcx+r15], ax
0x18014dd63  mov     rax, [rbx+18h]
0x18014dd67  mov     rcx, [rax+10h]
0x18014dd6b  mov     eax, 8000h
0x18014dd70  or      [rcx+r15], ax
0x18014dd75  jmp     short loc_18014DD7C
0x18014dd77  mov     edi, 1
0x18014dd7c  xor     r15d, r15d
0x18014dd7f  test    r13d, r13d
0x18014dd82  jnz     short loc_18014DD88
0x18014dd84  movzx   esi, r14w
0x18014dd88  movzx   edx, si
0x18014dd8b  mov     rcx, rbx
0x18014dd8e  call    _RtlpRemovePendingDeleteLanguages
0x18014dd93  mov     rcx, [rbx+18h]
0x18014dd97  mov     r10d, 1000h
0x18014dd9d  cmp     r15w, [rcx+6]
0x18014dda2  jnb     loc_18014DE31
0x18014dda8  mov     esi, r15d
0x18014ddab  mov     r12d, 0FFDFh
0x18014ddb1  movsxd  rax, esi
0x18014ddb4  imul    r15, rax, 1Ch
0x18014ddb8  mov     rax, [rcx+10h]
0x18014ddbc  mov     cl, [r15+rax]
0x18014ddc0  and     cl, 22h
0x18014ddc3  cmp     cl, 22h ; '"'
0x18014ddc6  jnz     short loc_18014DE1B
0x18014ddc8  mov     edx, esi
0x18014ddca  mov     rcx, rbx
0x18014ddcd  call    _RtlpMuiRegValidatePartialLanguage
0x18014ddd2  mov     rax, [rbx+18h]
0x18014ddd6  mov     r10d, 1000h
0x18014dddc  mov     rdx, [rax+10h]
0x18014dde0  lea     eax, [rdi+1]
0x18014dde3  movzx   ecx, word ptr [rdx+r15]
0x18014dde8  test    r10w, cx
0x18014ddec  cmovnz  eax, edi
0x18014ddef  mov     edi, eax
0x18014ddf1  test    r13d, r13d
0x18014ddf4  jnz     short loc_18014DE1B
0x18014ddf6  cmp     esi, r14d
0x18014ddf9  jz      short loc_18014DE1B
0x18014ddfb  cmp     eax, [rbx+78h]
0x18014ddfe  jbe     short loc_18014DE1B
0x18014de00  and     cx, r12w
0x18014de04  mov     [rdx+r15], cx
0x18014de09  mov     rax, [rbx+18h]
0x18014de0d  mov     rcx, [rax+10h]
0x18014de11  mov     eax, 8000h
0x18014de16  or      [rcx+r15], ax
0x18014de1b  mov     rcx, [rbx+18h]
0x18014de1f  inc     esi
0x18014de21  movzx   eax, word ptr [rcx+6]
0x18014de25  cmp     esi, eax
0x18014de27  jl      short loc_18014DDB1
0x18014de29  mov     r12, [rsp+170h+var_128]
0x18014de2e  xor     r15d, r15d
0x18014de31  test    r13d, r13d
0x18014de34  jnz     short loc_18014DEA2
0x18014de36  cmp     r15w, [rcx+6]
0x18014de3b  jnb     short loc_18014DEA2
0x18014de3d  mov     edx, r15d
0x18014de40  mov     r12d, 0FFDFh
0x18014de46  mov     r9, [rcx+10h]
0x18014de4a  movsxd  rax, edx
0x18014de4d  imul    r8, rax, 1Ch
0x18014de51  movzx   ecx, word ptr [r9+r8]
0x18014de56  mov     al, cl
0x18014de58  and     al, 21h
0x18014de5a  cmp     al, 21h ; '!'
0x18014de5c  jnz     short loc_18014DE8F
0x18014de5e  test    r10w, cx
0x18014de62  lea     eax, [rdi+1]
0x18014de65  cmovnz  eax, edi
0x18014de68  mov     edi, eax
0x18014de6a  cmp     edx, r14d
0x18014de6d  jz      short loc_18014DE8F
0x18014de6f  cmp     eax, [rbx+78h]
0x18014de72  jbe     short loc_18014DE8F
0x18014de74  and     cx, r12w
0x18014de78  mov     [r9+r8], cx
0x18014de7d  mov     rax, [rbx+18h]
0x18014de81  mov     rcx, [rax+10h]
0x18014de85  mov     eax, 8000h
0x18014de8a  or      [rcx+r8], ax
0x18014de8f  mov     rcx, [rbx+18h]
0x18014de93  inc     edx
0x18014de95  movzx   eax, word ptr [rcx+6]
0x18014de99  cmp     edx, eax
0x18014de9b  jl      short loc_18014DE46
0x18014de9d  mov     r12, [rsp+170h+var_128]
0x18014dea2  mov     rdx, [rbx+18h]
0x18014dea6  cmp     r15w, [rdx+6]
0x18014deab  jnb     short loc_18014DED9
0x18014dead  mov     edi, r15d
0x18014deb0  movsxd  rax, edi
0x18014deb3  imul    rcx, rax, 1Ch
0x18014deb7  mov     rax, [rdx+10h]
0x18014debb  test    byte ptr [rcx+rax], 4
0x18014debf  jz      short loc_18014DECB
0x18014dec1  mov     edx, edi
0x18014dec3  mov     rcx, rbx
0x18014dec6  call    _RtlpMuiRegValidateLIPLanguage
0x18014decb  mov     rdx, [rbx+18h]
0x18014decf  inc     edi
0x18014ded1  movzx   eax, word ptr [rdx+6]
0x18014ded5  cmp     edi, eax
0x18014ded7  jl      short loc_18014DEB0
0x18014ded9  test    r12, r12
0x18014dedc  jz      short loc_18014DEF5
0x18014dede  mov     rcx, gs:60h
0x18014dee7  mov     r8, r12
0x18014deea  xor     edx, edx
0x18014deec  mov     rcx, [rcx+30h]
0x18014def0  call    RtlFreeHeap_0
0x18014def5  xor     eax, eax
0x18014def7  mov     rcx, [rbp+70h+var_50]
0x18014defb  xor     rcx, rsp; StackCookie
0x18014defe  call    __security_check_cookie
0x18014df03  add     rsp, 138h
0x18014df0a  pop     r15
0x18014df0c  pop     r14
0x18014df0e  pop     r13
0x18014df10  pop     r12
0x18014df12  pop     rdi
0x18014df13  pop     rsi
0x18014df14  pop     rbx
0x18014df15  pop     rbp
0x18014df16  retn
```
