# GetUserStorageArea

- ea: `0x18000dab0`
- end: `0x18000dedb`
- name: `GetUserStorageArea`
- size: `1067`
- prototype: `__int64 __fastcall(__int64, __int64, int, _WORD *, char **)`
- caller_count: `14`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009b60`
- `0x180027778`
- `0x18002b460`
- `0x18002c7b0`
- `0x1800351c8`
- `0x180036940`
- `0x1800489c8`
- `0x180049dec`
- `0x18004eec0`
- `0x180053190`
- `0x180059bd4`
- `0x18005b338`
- `0x18005bbcc`
- `0x18005e958`

## callees

- `0x1800062cc`
- `0x18000af80`
- `0x18000b250`
- `0x18000dab0`
- `0x18000def0`
- `0x18002095c`
- `0x1800398b0`
- `0x180039bf0`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ddfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ddfa`
- `USERENV!GetProfileType` at `0x18000dd5a`
- `USERENV!GetProfileType` at `0x18000dd5a`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000db0e`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000dda1`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000ddd9`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000db0e`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000dda1`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000ddd9`

## string_xrefs

- `0x18000db9e`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18000dc80`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18000dcd2`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18000de42`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18000de80`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x18000dec1`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c
__int64 __fastcall GetUserStorageArea(__int64 a1, __int64 a2, int a3, _WORD *a4, char **a5)
{
  int BasicProfileFolderPath; // eax
  size_t v8; // rdx
  size_t *v9; // r8
  unsigned int v10; // edi
  __int64 v11; // rbx
  __int64 v12; // rbx
  int v13; // eax
  size_t v14; // rbx
  char *v15; // rax
  int v16; // edx
  int v17; // r8d
  _QWORD *v18; // rcx
  __int64 v19; // rsi
  wchar_t *v20; // rcx
  __int64 v21; // rbx
  __int64 v23; // rdi
  char *v24; // rax
  char *v25; // rbx
  _QWORD *v26; // rcx
  int v27; // eax
  size_t v28; // r8
  __int64 v29; // rax
  __int64 v30; // r9
  signed int LastError; // eax
  size_t v32; // [rsp+20h] [rbp-268h]
  char v33; // [rsp+30h] [rbp-258h]
  char v34; // [rsp+30h] [rbp-258h]
  int v35; // [rsp+40h] [rbp-248h] BYREF
  DWORD dwFlags[3]; // [rsp+44h] [rbp-244h] BYREF
  wchar_t Src[264]; // [rsp+50h] [rbp-238h] BYREF

  v35 = 0;
  dwFlags[0] = 0;
  if ( !a4 )
  {
    if ( (_DWORD)a1 )
      goto LABEL_3;
    v27 = IsThreadWellKnownSid(a1, &v35);
    v10 = v27;
    if ( v27 )
    {
      if ( v27 > 0 )
        v10 = (unsigned __int16)v27 | 0x80070000;
      DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 3732);
      return v10;
    }
    if ( v35 )
    {
LABEL_3:
      BasicProfileFolderPath = GetBasicProfileFolderPath(4, 0, Src, 261);
      v10 = BasicProfileFolderPath;
      if ( BasicProfileFolderPath >= 0 )
      {
        v11 = -1;
        goto LABEL_16;
      }
      v30 = 3763;
    }
    else
    {
      if ( !GetProfileType(dwFlags) )
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v10;
        v34 = -61;
        goto LABEL_28;
      }
      if ( (dwFlags[0] & 4) != 0 || (dwFlags[0] & 1) != 0 && (dwFlags[0] & 2) == 0 )
      {
        v10 = -2146893788;
        DebugTraceError(2148073508LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 3787);
        return v10;
      }
      v11 = -1;
      if ( a3 )
      {
        BasicProfileFolderPath = GetBasicProfileFolderPath(6, 0, Src, 261);
        v10 = BasicProfileFolderPath;
        if ( !BasicProfileFolderPath )
        {
          do
LABEL_16:
            ++v11;
          while ( Src[v11] );
          v21 = (unsigned int)(2 * v11);
          if ( !(_DWORD)v21 )
          {
            v10 = -2146893792;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v8,
                (_DWORD)v9,
                (unsigned int)"Status",
                32,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
                6);
            return v10;
          }
          v23 = (unsigned int)v21;
          v24 = (char *)SafeAllocaAllocateFromHeap(v21 + 2);
          *a5 = v24;
          v25 = v24;
          if ( v24 )
          {
            memcpy_0(v24, Src, (unsigned int)v23);
            *(_WORD *)&v25[v23] = 0;
            return 0;
          }
          v10 = -2146893810;
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v33 = 19;
            goto LABEL_13;
          }
          return v10;
        }
        v30 = 3807;
      }
      else
      {
        BasicProfileFolderPath = GetBasicProfileFolderPath(5, 0, Src, 261);
        v10 = BasicProfileFolderPath;
        if ( !BasicProfileFolderPath )
        {
          v29 = -1;
          do
            ++v29;
          while ( Src[v29] );
          v19 = 261 - v29;
          v10 = StringValidateDestW(&Src[v29], 261 - v29, v28);
          if ( (v10 & 0x80000000) != 0 )
          {
            if ( v19 )
              *v20 = 0;
          }
          else
          {
            v10 = StringCopyWorkerW_0(v20, v8, v9, L"\\AppData\\Roaming", v32);
            if ( !v10 )
              goto LABEL_16;
          }
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            return v10;
          v34 = -6;
LABEL_28:
          WPP_SF_sDsd(
            v26[2],
            v8,
            (_DWORD)v9,
            (unsigned int)"Status",
            v10,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
            v34);
          return v10;
        }
        v30 = 3821;
      }
    }
    DebugTraceError(
      (unsigned int)BasicProfileFolderPath,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
      v30);
    return v10;
  }
  v12 = -1;
  do
    ++v12;
  while ( a4[v12] );
  v13 = v12 + 1;
  if ( a4[(unsigned int)(v12 - 1)] == 92 )
    v13 = v12;
  v14 = (unsigned int)(2 * v13);
  v15 = (char *)SafeAllocaAllocateFromHeap(v14);
  *a5 = v15;
  if ( v15 )
  {
    memcpy_0(v15, a4, v14);
    v10 = 0;
    *(_WORD *)&(*a5)[2 * (v14 >> 1) - 2] = 0;
    return v10;
  }
  v10 = -2146893810;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v33 = 127;
LABEL_13:
    WPP_SF_sDsd(
      v18[2],
      v16,
      v17,
      (unsigned int)"Status",
      14,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c",
      v33);
  }
  return v10;
}

```

## disassembly

```asm
0x18000dab0  mov     [rsp+arg_0], rbx
0x18000dab5  mov     [rsp+arg_8], rbp
0x18000daba  push    rsi
0x18000dabb  push    rdi
0x18000dabc  push    r14
0x18000dabe  sub     rsp, 270h
0x18000dac5  mov     rax, cs:__security_cookie
0x18000dacc  xor     rax, rsp
0x18000dacf  mov     [rsp+288h+var_28], rax
0x18000dad7  mov     r14, [rsp+288h+arg_20]
0x18000dadf  xor     ebp, ebp
0x18000dae1  mov     [rsp+288h+var_248], ebp
0x18000dae5  mov     rdi, r9
0x18000dae8  mov     [rsp+288h+dwFlags], ebp
0x18000daec  mov     esi, r8d
0x18000daef  test    r9, r9
0x18000daf2  jnz     short loc_18000DB30
0x18000daf4  test    ecx, ecx
0x18000daf6  jz      loc_18000DD37
0x18000dafc  mov     r9d, 105h
0x18000db02  lea     r8, [rsp+288h+Src]
0x18000db07  xor     edx, edx
0x18000db09  mov     ecx, 4
0x18000db0e  call    cs:__imp_GetBasicProfileFolderPath
0x18000db15  nop     dword ptr [rax+rax+00h]
0x18000db1a  mov     edi, eax
0x18000db1c  test    eax, eax
0x18000db1e  js      loc_18000DEBB
0x18000db24  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000db2b  jmp     loc_18000DBEB
0x18000db30  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000db37  nop     word ptr [rax+rax+00000000h]
0x18000db40  inc     rbx
0x18000db43  cmp     [r9+rbx*2], bp
0x18000db48  jnz     short loc_18000DB40
0x18000db4a  lea     ecx, [rbx-1]
0x18000db4d  cmp     word ptr [r9+rcx*2], 5Ch ; '\'
0x18000db53  lea     eax, [rbx+1]
0x18000db56  cmovz   eax, ebx
0x18000db59  add     eax, eax
0x18000db5b  mov     ecx, eax
0x18000db5d  mov     ebx, eax
0x18000db5f  call    SafeAllocaAllocateFromHeap
0x18000db64  mov     [r14], rax
0x18000db67  test    rax, rax
0x18000db6a  jnz     loc_18000DD17
0x18000db70  mov     edi, 8009000Eh
0x18000db75  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db7c  lea     rax, WPP_GLOBAL_Control
0x18000db83  cmp     rcx, rax
0x18000db86  jz      loc_18000DC1B
0x18000db8c  test    byte ptr [rcx+1Ch], 1
0x18000db90  jz      loc_18000DC1B
0x18000db96  mov     dword ptr [rsp+288h+var_258], 0E7Fh
0x18000db9e  lea     rax, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dba5  mov     [rsp+288h+var_260], rax
0x18000dbaa  mov     dword ptr [rsp+288h+var_268], 8009000Eh
0x18000dbb2  jmp     loc_18000DC94
0x18000dbb7  sub     rsi, rax
0x18000dbba  lea     rcx, [rsp+288h+Src]
0x18000dbbf  mov     rdx, rsi; cchDest
0x18000dbc2  lea     rcx, [rcx+rax*2]; pszDest
0x18000dbc6  call    StringValidateDestW
0x18000dbcb  mov     edi, eax
0x18000dbcd  test    eax, eax
0x18000dbcf  js      loc_18000DEAA
0x18000dbd5  lea     r9, aAppdataRoaming; "\\AppData\\Roaming"
0x18000dbdc  call    StringCopyWorkerW_0
0x18000dbe1  mov     edi, eax
0x18000dbe3  test    eax, eax
0x18000dbe5  jnz     loc_18000DCA9
0x18000dbeb  lea     rax, [rsp+288h+Src]
0x18000dbf0  inc     rbx
0x18000dbf3  cmp     [rax+rbx*2], bp
0x18000dbf7  jnz     short loc_18000DBF0
0x18000dbf9  add     ebx, ebx
0x18000dbfb  jnz     short loc_18000DC46
0x18000dbfd  mov     edi, 80090020h
0x18000dc02  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc09  lea     rax, WPP_GLOBAL_Control
0x18000dc10  cmp     rcx, rax
0x18000dc13  jz      short loc_18000DC1B
0x18000dc15  test    byte ptr [rcx+1Ch], 1
0x18000dc19  jnz     short loc_18000DC78
0x18000dc1b  mov     eax, edi
0x18000dc1d  mov     rcx, [rsp+288h+var_28]
0x18000dc25  xor     rcx, rsp; StackCookie
0x18000dc28  call    __security_check_cookie
0x18000dc2d  lea     r11, [rsp+288h+var_18]
0x18000dc35  mov     rbx, [r11+20h]
0x18000dc39  mov     rbp, [r11+28h]
0x18000dc3d  mov     rsp, r11
0x18000dc40  pop     r14
0x18000dc42  pop     rdi
0x18000dc43  pop     rsi
0x18000dc44  retn
0x18000dc46  lea     rcx, [rbx+2]
0x18000dc4a  mov     edi, ebx
0x18000dc4c  call    SafeAllocaAllocateFromHeap
0x18000dc51  mov     [r14], rax
0x18000dc54  mov     rbx, rax
0x18000dc57  test    rax, rax
0x18000dc5a  jz      loc_18000DCE4
0x18000dc60  mov     r8d, edi; Size
0x18000dc63  lea     rdx, [rsp+288h+Src]; Src
0x18000dc68  mov     rcx, rax; void *
0x18000dc6b  call    memcpy_0
0x18000dc70  mov     [rdi+rbx], bp
0x18000dc74  mov     edi, ebp
0x18000dc76  jmp     short loc_18000DC1B
0x18000dc78  mov     dword ptr [rsp+288h+var_258], 0F06h
0x18000dc80  lea     rax, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dc87  mov     [rsp+288h+var_260], rax
0x18000dc8c  mov     dword ptr [rsp+288h+var_268], 80090020h
0x18000dc94  mov     rcx, [rcx+10h]
0x18000dc98  lea     r9, aStatus; "Status"
0x18000dc9f  call    WPP_SF_sDsd
0x18000dca4  jmp     loc_18000DC1B
0x18000dca9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcb0  lea     rax, WPP_GLOBAL_Control
0x18000dcb7  cmp     rcx, rax
0x18000dcba  jz      loc_18000DC1B
0x18000dcc0  test    byte ptr [rcx+1Ch], 1
0x18000dcc4  jz      loc_18000DC1B
0x18000dcca  mov     dword ptr [rsp+288h+var_258], 0EFAh
0x18000dcd2  lea     rax, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dcd9  mov     [rsp+288h+var_260], rax
0x18000dcde  mov     dword ptr [rsp+288h+var_268], edi
0x18000dce2  jmp     short loc_18000DC94
0x18000dce4  mov     edi, 8009000Eh
0x18000dce9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dcf0  lea     rax, WPP_GLOBAL_Control
0x18000dcf7  cmp     rcx, rax
0x18000dcfa  jz      loc_18000DC1B
0x18000dd00  test    byte ptr [rcx+1Ch], 1
0x18000dd04  jz      loc_18000DC1B
0x18000dd0a  mov     dword ptr [rsp+288h+var_258], 0F13h
0x18000dd12  jmp     loc_18000DB9E
0x18000dd17  mov     r8, rbx; Size
0x18000dd1a  mov     rdx, rdi; Src
0x18000dd1d  mov     rcx, rax; void *
0x18000dd20  call    memcpy_0
0x18000dd25  mov     rcx, [r14]
0x18000dd28  mov     edi, ebp
0x18000dd2a  shr     rbx, 1
0x18000dd2d  mov     [rcx+rbx*2-2], bp
0x18000dd32  jmp     loc_18000DC1B
0x18000dd37  lea     rdx, [rsp+288h+var_248]
0x18000dd3c  call    IsThreadWellKnownSid
0x18000dd41  mov     edi, eax
0x18000dd43  test    eax, eax
0x18000dd45  jnz     loc_18000DE3A
0x18000dd4b  cmp     [rsp+288h+var_248], ebp
0x18000dd4f  jnz     loc_18000DAFC
0x18000dd55  lea     rcx, [rsp+288h+dwFlags]; dwFlags
0x18000dd5a  call    cs:__imp_GetProfileType
0x18000dd61  nop     dword ptr [rax+rax+00h]
0x18000dd66  test    eax, eax
0x18000dd68  jz      loc_18000DDFA
0x18000dd6e  mov     eax, [rsp+288h+dwFlags]
0x18000dd72  test    al, 4
0x18000dd74  jnz     loc_18000DE7A
0x18000dd7a  test    al, 1
0x18000dd7c  jnz     loc_18000DE72
0x18000dd82  xor     edx, edx
0x18000dd84  lea     r8, [rsp+288h+Src]
0x18000dd89  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000dd90  test    esi, esi
0x18000dd92  jnz     short loc_18000DDCE
0x18000dd94  mov     esi, 105h
0x18000dd99  mov     ecx, 5
0x18000dd9e  mov     r9d, esi
0x18000dda1  call    cs:__imp_GetBasicProfileFolderPath
0x18000dda8  nop     dword ptr [rax+rax+00h]
0x18000ddad  mov     edi, eax
0x18000ddaf  test    eax, eax
0x18000ddb1  jnz     loc_18000DEA2
0x18000ddb7  lea     rcx, [rsp+288h+Src]
0x18000ddbc  mov     rax, rbx
0x18000ddbf  nop
0x18000ddc0  inc     rax
0x18000ddc3  cmp     [rcx+rax*2], bp
0x18000ddc7  jnz     short loc_18000DDC0
0x18000ddc9  jmp     loc_18000DBB7
0x18000ddce  mov     r9d, 105h
0x18000ddd4  mov     ecx, 6
0x18000ddd9  call    cs:__imp_GetBasicProfileFolderPath
0x18000dde0  nop     dword ptr [rax+rax+00h]
0x18000dde5  mov     edi, eax
0x18000dde7  test    eax, eax
0x18000dde9  jz      loc_18000DBEB
0x18000ddef  mov     r9d, 0EDFh
0x18000ddf5  jmp     loc_18000DEC1
0x18000ddfa  call    cs:__imp_GetLastError
0x18000de01  nop     dword ptr [rax+rax+00h]
0x18000de06  mov     edi, eax
0x18000de08  test    eax, eax
0x18000de0a  jg      short loc_18000DE67
0x18000de0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de13  lea     rax, WPP_GLOBAL_Control
0x18000de1a  cmp     rcx, rax
0x18000de1d  jz      loc_18000DC1B
0x18000de23  test    byte ptr [rcx+1Ch], 1
0x18000de27  jz      loc_18000DC1B
0x18000de2d  mov     dword ptr [rsp+288h+var_258], 0EC3h
0x18000de35  jmp     loc_18000DCD2
0x18000de3a  jg      short loc_18000DE5C
0x18000de3c  mov     r9d, 0E94h
0x18000de42  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000de49  lea     rdx, aStatus; "Status"
0x18000de50  mov     ecx, edi
0x18000de52  call    DebugTraceError
0x18000de57  jmp     loc_18000DC1B
0x18000de5c  movzx   edi, ax
0x18000de5f  or      edi, 80070000h
0x18000de65  jmp     short loc_18000DE3C
0x18000de67  movzx   edi, ax
0x18000de6a  or      edi, 80070000h
0x18000de70  jmp     short loc_18000DE0C
0x18000de72  test    al, 2
0x18000de74  jnz     loc_18000DD82
0x18000de7a  mov     r9d, 0ECBh
0x18000de80  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000de87  lea     rdx, aStatus; "Status"
0x18000de8e  mov     ecx, 80090024h
0x18000de93  mov     edi, 80090024h
0x18000de98  call    DebugTraceError
0x18000de9d  jmp     loc_18000DC1B
0x18000dea2  mov     r9d, 0EEDh
0x18000dea8  jmp     short loc_18000DEC1
0x18000deaa  test    rsi, rsi
0x18000dead  jz      loc_18000DCA9
0x18000deb3  mov     [rcx], bp
0x18000deb6  jmp     loc_18000DCA9
0x18000debb  mov     r9d, 0EB3h
0x18000dec1  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dec8  mov     ecx, eax
0x18000deca  lea     rdx, aStatus; "Status"
0x18000ded1  call    DebugTraceError
0x18000ded6  jmp     loc_18000DC1B
```
