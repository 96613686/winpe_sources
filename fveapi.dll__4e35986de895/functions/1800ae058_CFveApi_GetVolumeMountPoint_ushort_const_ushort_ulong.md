# CFveApi::GetVolumeMountPoint(ushort const *,ushort *,ulong)

- ea: `0x1800ae058`
- end: `0x1800ae361`
- name: `?GetVolumeMountPoint@CFveApi@@SAJPEBGPEAGK@Z`
- size: `777`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x1800caa7c`

## callees

- `0x1800050c0`
- `0x1800090c0`
- `0x18000ba30`
- `0x18000ca50`
- `0x180023800`
- `0x180046e44`
- `0x18004fddc`
- `0x1800ae058`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae0e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae0e3`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1800ae0cf`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1800ae0cf`

## pseudocode

```c
__int64 __fastcall CFveApi::GetVolumeMountPoint(LPCWSTR lpszVolumeName, unsigned __int16 *a2)
{
  ULONG v3; // r12d
  WCHAR *v4; // rsi
  DWORD v5; // edi
  unsigned int i; // ebx
  int v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned int KnownLastErrorHR; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned __int64 v15; // r15
  unsigned __int64 j; // r14
  unsigned int v17; // eax
  ULONGLONG v18; // rbp
  unsigned int v19; // eax
  __int64 v20; // r10
  unsigned __int64 v21; // r8
  ULONG pulResult; // [rsp+20h] [rbp-68h] BYREF
  ULONGLONG ullOperand; // [rsp+28h] [rbp-60h] BYREF
  unsigned __int16 *v25; // [rsp+30h] [rbp-58h]
  DWORD cchReturnLength; // [rsp+38h] [rbp-50h] BYREF

  v25 = a2;
  ullOperand = 0;
  v3 = 260;
  cchReturnLength = 0;
  pulResult = 260;
  v4 = 0;
  v5 = 0;
  memset_0(a2, 0, 0x208u);
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      if ( i == 3 )
      {
        v14 = 2147549183LL;
        v7 = -2147418113;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_48;
        v13 = 33;
LABEL_47:
        WPP_SF_d(v12[2], v13, &WPP_d49a419601d63bf81c65cb8f20c8a9f6_Traceguids, v14);
        goto LABEL_48;
      }
LABEL_24:
      v15 = 0;
      for ( j = 0; j < v5; j += v18 )
      {
        v17 = StringCchLengthW(&v4[j], v5 - j, &ullOperand);
        v7 = v17;
        if ( v17 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_d49a419601d63bf81c65cb8f20c8a9f6_Traceguids, v17);
          if ( v7 < 0 )
            goto LABEL_48;
        }
        v18 = ullOperand;
        if ( !ullOperand )
          break;
        if ( ullOperand < v3 )
        {
          v19 = ULongLongToULong(ullOperand, &pulResult);
          v7 = v19;
          if ( v19 )
          {
            if ( (PVOID *)v20 != &WPP_GLOBAL_Control && (*(_BYTE *)(v20 + 28) & 0x40) != 0 )
              WPP_SF_d(*(_QWORD *)(v20 + 16), 35, &WPP_d49a419601d63bf81c65cb8f20c8a9f6_Traceguids, v19);
            if ( v7 < 0 )
              goto LABEL_48;
          }
          v3 = pulResult;
          v15 = j;
        }
      }
      v21 = v15 + v3;
      if ( v4[v21 - 1] == 92 )
        v4[v21 - 1] = 0;
      KnownLastErrorHR = StringCchCopyW(v25, 0x104u, &v4[v15]);
      v7 = KnownLastErrorHR;
      if ( !KnownLastErrorHR )
        goto LABEL_48;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_48;
      v13 = 36;
LABEL_46:
      v14 = KnownLastErrorHR;
      goto LABEL_47;
    }
    if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, v4, v5, &cchReturnLength) )
      break;
    if ( GetLastError() != 234 )
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      v7 = KnownLastErrorHR;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v13 = 31;
        goto LABEL_46;
      }
LABEL_48:
      if ( v4 )
        CFveApiBase::FastFree(v4);
      return (unsigned int)v7;
    }
    if ( cchReturnLength <= 1 )
    {
      v7 = 0;
      goto LABEL_48;
    }
    v4 = (WCHAR *)CFveApiBase::FastAlloc(2LL * cchReturnLength);
    if ( !v4 )
    {
      v7 = -2147024882;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v9 = 32;
        v10 = 2147942414LL;
LABEL_19:
        WPP_SF_d(v8[2], v9, &WPP_d49a419601d63bf81c65cb8f20c8a9f6_Traceguids, v10);
        return (unsigned int)v7;
      }
      return (unsigned int)v7;
    }
    v5 = cchReturnLength;
  }
  if ( v4 )
    goto LABEL_24;
  v10 = 2147549183LL;
  v7 = -2147418113;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v9 = 30;
    goto LABEL_19;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800ae058  mov     [rsp+arg_10], rbx
0x1800ae05d  push    rbp
0x1800ae05e  push    rsi
0x1800ae05f  push    rdi
0x1800ae060  push    r12
0x1800ae062  push    r13
0x1800ae064  push    r14
0x1800ae066  push    r15
0x1800ae068  sub     rsp, 50h
0x1800ae06c  mov     rax, cs:__security_cookie
0x1800ae073  xor     rax, rsp
0x1800ae076  mov     [rsp+88h+var_48], rax
0x1800ae07b  mov     rax, rdx
0x1800ae07e  mov     [rsp+88h+var_58], rdx
0x1800ae083  mov     rbp, rcx
0x1800ae086  mov     [rsp+88h+ullOperand], 0
0x1800ae08f  mov     r12d, 104h
0x1800ae095  mov     [rsp+88h+cchReturnLength], 0
0x1800ae09d  mov     rcx, rax; void *
0x1800ae0a0  mov     [rsp+88h+pulResult], r12d
0x1800ae0a5  xor     edx, edx; Val
0x1800ae0a7  mov     r8d, 208h; Size
0x1800ae0ad  xor     esi, esi
0x1800ae0af  xor     edi, edi
0x1800ae0b1  call    memset_0
0x1800ae0b6  xor     ebx, ebx
0x1800ae0b8  cmp     ebx, 3
0x1800ae0bb  jnb     loc_1800AE1C9
0x1800ae0c1  lea     r9, [rsp+88h+cchReturnLength]; lpcchReturnLength
0x1800ae0c6  mov     r8d, edi; cchBufferLength
0x1800ae0c9  mov     rdx, rsi; lpszVolumePathNames
0x1800ae0cc  mov     rcx, rbp; lpszVolumeName
0x1800ae0cf  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1800ae0d6  nop     dword ptr [rax+rax+00h]
0x1800ae0db  test    eax, eax
0x1800ae0dd  jnz     loc_1800AE182
0x1800ae0e3  call    cs:__imp_GetLastError
0x1800ae0ea  nop     dword ptr [rax+rax+00h]
0x1800ae0ef  cmp     eax, 0EAh
0x1800ae0f4  jnz     short loc_1800AE150
0x1800ae0f6  cmp     [rsp+88h+cchReturnLength], 1
0x1800ae0fb  jbe     short loc_1800AE149
0x1800ae0fd  mov     ecx, [rsp+88h+cchReturnLength]
0x1800ae101  add     rcx, rcx; unsigned __int64
0x1800ae104  call    ?FastAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::FastAlloc(unsigned __int64)
0x1800ae109  mov     rsi, rax
0x1800ae10c  test    rax, rax
0x1800ae10f  jz      short loc_1800AE119
0x1800ae111  mov     edi, [rsp+88h+cchReturnLength]
0x1800ae115  inc     ebx
0x1800ae117  jmp     short loc_1800AE0B8
0x1800ae119  mov     ebx, 8007000Eh
0x1800ae11e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae125  lea     rdi, WPP_GLOBAL_Control
0x1800ae12c  cmp     rcx, rdi
0x1800ae12f  jz      loc_1800AE339
0x1800ae135  test    byte ptr [rcx+1Ch], 40h
0x1800ae139  jz      loc_1800AE339
0x1800ae13f  mov     edx, 20h ; ' '
0x1800ae144  mov     r9d, ebx
0x1800ae147  jmp     short loc_1800AE1B4
0x1800ae149  xor     ebx, ebx
0x1800ae14b  jmp     loc_1800AE32C
0x1800ae150  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1800ae155  mov     ebx, eax
0x1800ae157  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae15e  lea     rdi, WPP_GLOBAL_Control
0x1800ae165  cmp     rcx, rdi
0x1800ae168  jz      loc_1800AE32C
0x1800ae16e  test    byte ptr [rcx+1Ch], 40h
0x1800ae172  jz      loc_1800AE32C
0x1800ae178  mov     edx, 1Fh
0x1800ae17d  jmp     loc_1800AE319
0x1800ae182  test    rsi, rsi
0x1800ae185  jnz     short loc_1800AE1FF
0x1800ae187  mov     r9d, 8000FFFFh
0x1800ae18d  mov     ebx, r9d
0x1800ae190  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae197  lea     rdi, WPP_GLOBAL_Control
0x1800ae19e  cmp     rcx, rdi
0x1800ae1a1  jz      loc_1800AE339
0x1800ae1a7  test    byte ptr [rcx+1Ch], 40h
0x1800ae1ab  jz      loc_1800AE339
0x1800ae1b1  lea     edx, [rsi+1Eh]
0x1800ae1b4  mov     rcx, [rcx+10h]
0x1800ae1b8  lea     r8, WPP_d49a419601d63bf81c65cb8f20c8a9f6_Traceguids
0x1800ae1bf  call    WPP_SF_d
0x1800ae1c4  jmp     loc_1800AE339
0x1800ae1c9  jnz     short loc_1800AE1FF
0x1800ae1cb  mov     r9d, 8000FFFFh
0x1800ae1d1  mov     ebx, r9d
0x1800ae1d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae1db  lea     rdi, WPP_GLOBAL_Control
0x1800ae1e2  cmp     rcx, rdi
0x1800ae1e5  jz      loc_1800AE32C
0x1800ae1eb  test    byte ptr [rcx+1Ch], 40h
0x1800ae1ef  jz      loc_1800AE32C
0x1800ae1f5  mov     edx, 21h ; '!'
0x1800ae1fa  jmp     loc_1800AE31C
0x1800ae1ff  xor     r15d, r15d
0x1800ae202  mov     r13d, edi
0x1800ae205  xor     r14d, r14d
0x1800ae208  lea     rdi, WPP_GLOBAL_Control
0x1800ae20f  cmp     r14, r13
0x1800ae212  jnb     loc_1800AE2D2
0x1800ae218  mov     rdx, r13
0x1800ae21b  lea     rcx, [rsi+r14*2]; unsigned __int16 *
0x1800ae21f  sub     rdx, r14; unsigned __int64
0x1800ae222  lea     r8, [rsp+88h+ullOperand]; unsigned __int64 *
0x1800ae227  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800ae22c  mov     ebx, eax
0x1800ae22e  test    eax, eax
0x1800ae230  jz      short loc_1800AE26E
0x1800ae232  mov     r10, cs:WPP_GLOBAL_Control
0x1800ae239  cmp     r10, rdi
0x1800ae23c  jz      short loc_1800AE264
0x1800ae23e  test    byte ptr [r10+1Ch], 40h
0x1800ae243  jz      short loc_1800AE264
0x1800ae245  mov     rcx, [r10+10h]
0x1800ae249  lea     r8, WPP_d49a419601d63bf81c65cb8f20c8a9f6_Traceguids
0x1800ae250  mov     edx, 22h ; '"'
0x1800ae255  mov     r9d, eax
0x1800ae258  call    WPP_SF_d
0x1800ae25d  mov     r10, cs:WPP_GLOBAL_Control
0x1800ae264  test    ebx, ebx
0x1800ae266  js      loc_1800AE32C
0x1800ae26c  jmp     short loc_1800AE275
0x1800ae26e  mov     r10, cs:WPP_GLOBAL_Control
0x1800ae275  mov     rbp, [rsp+88h+ullOperand]
0x1800ae27a  test    rbp, rbp
0x1800ae27d  jz      short loc_1800AE2D2
0x1800ae27f  mov     eax, r12d
0x1800ae282  cmp     rbp, rax
0x1800ae285  jnb     short loc_1800AE2CA
0x1800ae287  lea     rdx, [rsp+88h+pulResult]; pulResult
0x1800ae28c  mov     rcx, rbp; ullOperand
0x1800ae28f  call    ULongLongToULong
0x1800ae294  mov     ebx, eax
0x1800ae296  test    eax, eax
0x1800ae298  jz      short loc_1800AE2C2
0x1800ae29a  cmp     r10, rdi
0x1800ae29d  jz      short loc_1800AE2BE
0x1800ae29f  test    byte ptr [r10+1Ch], 40h
0x1800ae2a4  jz      short loc_1800AE2BE
0x1800ae2a6  mov     rcx, [r10+10h]
0x1800ae2aa  lea     r8, WPP_d49a419601d63bf81c65cb8f20c8a9f6_Traceguids
0x1800ae2b1  mov     edx, 23h ; '#'
0x1800ae2b6  mov     r9d, eax
0x1800ae2b9  call    WPP_SF_d
0x1800ae2be  test    ebx, ebx
0x1800ae2c0  js      short loc_1800AE32C
0x1800ae2c2  mov     r12d, [rsp+88h+pulResult]
0x1800ae2c7  mov     r15, r14
0x1800ae2ca  add     r14, rbp
0x1800ae2cd  jmp     loc_1800AE20F
0x1800ae2d2  mov     r8d, r12d
0x1800ae2d5  add     r8, r15
0x1800ae2d8  cmp     word ptr [rsi+r8*2-2], 5Ch ; '\'
0x1800ae2df  jnz     short loc_1800AE2E9
0x1800ae2e1  xor     eax, eax
0x1800ae2e3  mov     [rsi+r8*2-2], ax
0x1800ae2e9  mov     rcx, [rsp+88h+var_58]; unsigned __int16 *
0x1800ae2ee  lea     r8, [rsi+r15*2]; unsigned __int16 *
0x1800ae2f2  mov     edx, 104h; unsigned __int64
0x1800ae2f7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ae2fc  mov     ebx, eax
0x1800ae2fe  test    eax, eax
0x1800ae300  jz      short loc_1800AE32C
0x1800ae302  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae309  cmp     rcx, rdi
0x1800ae30c  jz      short loc_1800AE32C
0x1800ae30e  test    byte ptr [rcx+1Ch], 40h
0x1800ae312  jz      short loc_1800AE32C
0x1800ae314  mov     edx, 24h ; '$'
0x1800ae319  mov     r9d, eax
0x1800ae31c  mov     rcx, [rcx+10h]
0x1800ae320  lea     r8, WPP_d49a419601d63bf81c65cb8f20c8a9f6_Traceguids
0x1800ae327  call    WPP_SF_d
0x1800ae32c  test    rsi, rsi
0x1800ae32f  jz      short loc_1800AE339
0x1800ae331  mov     rcx, rsi; lpMem
0x1800ae334  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x1800ae339  mov     eax, ebx
0x1800ae33b  mov     rcx, [rsp+88h+var_48]
0x1800ae340  xor     rcx, rsp; StackCookie
0x1800ae343  call    __security_check_cookie
0x1800ae348  mov     rbx, [rsp+88h+arg_10]
0x1800ae350  add     rsp, 50h
0x1800ae354  pop     r15
0x1800ae356  pop     r14
0x1800ae358  pop     r13
0x1800ae35a  pop     r12
0x1800ae35c  pop     rdi
0x1800ae35d  pop     rsi
0x1800ae35e  pop     rbp
0x1800ae35f  retn
```
