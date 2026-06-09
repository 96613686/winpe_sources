# CTitleInformation::InitContentFont(char const *)

- ea: `0x18005d400`
- end: `0x18005d650`
- name: `?InitContentFont@CTitleInformation@@AEAAXPEBD@Z`
- size: `592`
- prototype: `void(CTitleInformation *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18005d804`

## callees

- `0x1800095c8`
- `0x18005d400`
- `0x180064990`
- `0x180065438`
- `0x1800661d0`
- `0x1800665d0`
- `0x1800675c0`
- `0x180069e70`
- `0x180075c5a`
- `0x180075c90`

## import_xrefs

- `msvcrt!free` at `0x18005d59d`
- `msvcrt!free` at `0x18005d59d`
- `KERNEL32!GetLocaleInfoA` at `0x18005d546`
- `KERNEL32!GetLocaleInfoA` at `0x18005d546`
- `USER32!SystemParametersInfoA` at `0x18005d5f6`
- `USER32!SystemParametersInfoA` at `0x18005d5f6`
- `GDI32!GetObjectA` at `0x18005d5d5`
- `GDI32!GetObjectA` at `0x18005d5d5`
- `GDI32!CreateFontIndirectA` at `0x18005d616`
- `GDI32!CreateFontIndirectA` at `0x18005d616`
- `SHLWAPI!StrChrA` at `0x18005d486`
- `SHLWAPI!StrChrA` at `0x18005d49e`
- `SHLWAPI!StrChrA` at `0x18005d4d8`
- `SHLWAPI!StrChrA` at `0x18005d486`
- `SHLWAPI!StrChrA` at `0x18005d49e`
- `SHLWAPI!StrChrA` at `0x18005d4d8`

## pseudocode

```c
void __fastcall CTitleInformation::InitContentFont(CTitleInformation *this, const char *a2)
{
  PSTR v4; // rax
  PSTR v5; // rax
  const CHAR *StringResource; // rax
  const CHAR *v7; // rbx
  int v8; // eax
  const CHAR *v9; // r11
  int v10; // r10d
  const char *v11; // r8
  unsigned int v12; // eax
  const unsigned __int16 *WideStr; // rax
  unsigned int *v14; // rdx
  HDC v15; // r8
  unsigned __int16 *v16; // rbx
  int ObjectA; // eax
  int v18; // ebx
  BOOL v19; // eax
  HFONT v20; // rax
  LOGFONTA pv; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD pvParam[40]; // [rsp+60h] [rbp-A0h] BYREF
  LONG v23; // [rsp+100h] [rbp+0h]
  CHAR LCData[16]; // [rsp+1C0h] [rbp+C0h] BYREF
  CHAR pszStart[272]; // [rsp+1D0h] [rbp+D0h] BYREF

  memset(&pv, 0, sizeof(pv));
  memset_0(pvParam, 0, 0x158u);
  if ( !a2 || !*a2 )
  {
    StringResource = GetStringResource(0x400u);
    v7 = StringResource;
    if ( g_fSysWinNT )
    {
      StrChrA(StringResource, 0x2Cu);
      if ( !v7 )
      {
LABEL_12:
        v11 = "MS Shell Dlg,8";
LABEL_14:
        StringCchCopyA(pszStart, 0x104u, v11);
        goto LABEL_15;
      }
      if ( *((_DWORD *)this + 1070) <= 1u || (v8 = Atoi(v7 + 1), v8 == v10) )
      {
LABEL_13:
        v11 = v7;
        goto LABEL_14;
      }
      v7 = v9;
    }
    if ( !v7 )
      goto LABEL_12;
    goto LABEL_13;
  }
  StringCchCopyA(pszStart, 0x104u, a2);
  v4 = StrChrA(pszStart, 0x2Cu);
  if ( v4 )
  {
    v5 = StrChrA(v4 + 1, 0x2Cu);
    if ( v5 )
      *((_DWORD *)this + 1070) = Atoi(v5 + 1);
  }
LABEL_15:
  if ( g_fSysWinNT )
  {
    if ( !GetLocaleInfoA(*((_DWORD *)this + 4), 0x1004u, LCData, 10) )
      StringCchCopyA(pszStart, 0x104u, "MS Shell Dlg,8");
    v12 = CodePageFromLCID(*((_DWORD *)this + 4));
    WideStr = MakeWideStr(pszStart, v12);
    v16 = (unsigned __int16 *)WideStr;
    if ( WideStr )
    {
      *((_QWORD *)this + 532) = CreateUserFontW(WideStr, v14, v15, *((_DWORD *)this + 1070));
      free(v16);
    }
  }
  else
  {
    *((_QWORD *)this + 532) = CreateUserFont(pszStart, 0, 0, *((_DWORD *)this + 1070));
  }
  ObjectA = GetObjectA(*((HANDLE *)this + 532), 60, &pv);
  pvParam[0] = 344;
  v18 = ObjectA;
  v19 = SystemParametersInfoA(0x29u, 0x158u, pvParam, 0);
  if ( v18 && v19 && v23 < pv.lfHeight )
  {
    pv.lfHeight = v23;
    v20 = CreateFontIndirectA(&pv);
  }
  else
  {
    v20 = (HFONT)*((_QWORD *)this + 532);
  }
  *((_QWORD *)this + 533) = v20;
}

```

## disassembly

```asm
0x18005d400  mov     [rsp-8+arg_10], rbx
0x18005d405  mov     [rsp-8+arg_18], rdi
0x18005d40a  push    rbp
0x18005d40b  lea     rbp, [rsp-1F0h]
0x18005d413  sub     rsp, 2F0h
0x18005d41a  mov     rax, cs:__security_cookie
0x18005d421  xor     rax, rsp
0x18005d424  mov     [rbp+1F0h+var_10], rax
0x18005d42b  xorps   xmm0, xmm0
0x18005d42e  mov     rbx, rdx
0x18005d431  mov     rdi, rcx
0x18005d434  xor     edx, edx; Val
0x18005d436  movups  [rsp+2F0h+var_2B0], xmm0
0x18005d43b  mov     r8d, 158h; Size
0x18005d441  lea     rcx, [rsp+2F0h+pvParam]; void *
0x18005d446  movups  [rsp+2F0h+var_2B0+0Ch], xmm0
0x18005d44b  movups  [rsp+2F0h+pv], xmm0
0x18005d450  movups  [rsp+2F0h+var_2C0], xmm0
0x18005d455  call    memset_0
0x18005d45a  test    rbx, rbx
0x18005d45d  jz      short loc_18005D4BA
0x18005d45f  cmp     byte ptr [rbx], 0
0x18005d462  jz      short loc_18005D4BA
0x18005d464  mov     r8, rbx; char *
0x18005d467  lea     rcx, [rbp+1F0h+pszStart]; char *
0x18005d46e  mov     ebx, 104h
0x18005d473  mov     edx, ebx; unsigned __int64
0x18005d475  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005d47a  mov     edx, 2Ch ; ','; wMatch
0x18005d47f  lea     rcx, [rbp+1F0h+pszStart]; pszStart
0x18005d486  call    cs:__imp_StrChrA
0x18005d48c  test    rax, rax
0x18005d48f  jz      loc_18005D528
0x18005d495  mov     edx, 2Ch ; ','; wMatch
0x18005d49a  lea     rcx, [rax+1]; pszStart
0x18005d49e  call    cs:__imp_StrChrA
0x18005d4a4  test    rax, rax
0x18005d4a7  jz      short loc_18005D528
0x18005d4a9  lea     rcx, [rax+1]; char *
0x18005d4ad  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x18005d4b2  mov     [rdi+10B8h], eax
0x18005d4b8  jmp     short loc_18005D528
0x18005d4ba  mov     ecx, 400h; uID
0x18005d4bf  call    ?GetStringResource@@YAPEBDH@Z; GetStringResource(int)
0x18005d4c4  cmp     cs:?g_fSysWinNT@@3HA, 0; int g_fSysWinNT
0x18005d4cb  mov     rbx, rax
0x18005d4ce  jz      short loc_18005D504
0x18005d4d0  mov     edx, 2Ch ; ','; wMatch
0x18005d4d5  mov     rcx, rax; pszStart
0x18005d4d8  call    cs:__imp_StrChrA
0x18005d4de  mov     r11, rax
0x18005d4e1  test    rbx, rbx
0x18005d4e4  jz      short loc_18005D509
0x18005d4e6  mov     r10d, [rdi+10B8h]
0x18005d4ed  cmp     r10d, 1
0x18005d4f1  jbe     short loc_18005D512
0x18005d4f3  lea     rcx, [rbx+1]; char *
0x18005d4f7  call    ?Atoi@@YAHPEBD@Z; Atoi(char const *)
0x18005d4fc  cmp     eax, r10d
0x18005d4ff  jz      short loc_18005D512
0x18005d501  mov     rbx, r11
0x18005d504  test    rbx, rbx
0x18005d507  jnz     short loc_18005D512
0x18005d509  lea     r8, aMsShellDlg8; "MS Shell Dlg,8"
0x18005d510  jmp     short loc_18005D515
0x18005d512  mov     r8, rbx; char *
0x18005d515  mov     ebx, 104h
0x18005d51a  lea     rcx, [rbp+1F0h+pszStart]; char *
0x18005d521  mov     edx, ebx; unsigned __int64
0x18005d523  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005d528  cmp     cs:?g_fSysWinNT@@3HA, 0; int g_fSysWinNT
0x18005d52f  jz      short loc_18005D5A5
0x18005d531  mov     ecx, [rdi+10h]; Locale
0x18005d534  lea     r8, [rbp+1F0h+LCData]; lpLCData
0x18005d53b  mov     r9d, 0Ah; cchData
0x18005d541  mov     edx, 1004h; LCType
0x18005d546  call    cs:__imp_GetLocaleInfoA
0x18005d54c  test    eax, eax
0x18005d54e  jnz     short loc_18005D566
0x18005d550  lea     r8, aMsShellDlg8; "MS Shell Dlg,8"
0x18005d557  mov     rdx, rbx; unsigned __int64
0x18005d55a  lea     rcx, [rbp+1F0h+pszStart]; char *
0x18005d561  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18005d566  mov     ecx, [rdi+10h]; unsigned int
0x18005d569  call    ?CodePageFromLCID@@YAIK@Z; CodePageFromLCID(ulong)
0x18005d56e  mov     edx, eax; unsigned int
0x18005d570  lea     rcx, [rbp+1F0h+pszStart]; char *
0x18005d577  call    ?MakeWideStr@@YAPEAGPEADI@Z; MakeWideStr(char *,uint)
0x18005d57c  mov     rbx, rax
0x18005d57f  test    rax, rax
0x18005d582  jz      short loc_18005D5C4
0x18005d584  mov     r9d, [rdi+10B8h]; int
0x18005d58b  mov     rcx, rax; unsigned __int16 *
0x18005d58e  call    ?CreateUserFontW@@YAPEAUHFONT__@@PEBGPEAKPEAUHDC__@@H@Z; CreateUserFontW(ushort const *,ulong *,HDC__ *,int)
0x18005d593  mov     rcx, rbx; Block
0x18005d596  mov     [rdi+10A0h], rax
0x18005d59d  call    cs:__imp_free
0x18005d5a3  jmp     short loc_18005D5C4
0x18005d5a5  mov     r9d, [rdi+10B8h]; int
0x18005d5ac  lea     rcx, [rbp+1F0h+pszStart]; char *
0x18005d5b3  xor     r8d, r8d; HDC
0x18005d5b6  xor     edx, edx; unsigned int *
0x18005d5b8  call    ?CreateUserFont@@YAPEAUHFONT__@@PEBDPEAKPEAUHDC__@@H@Z; CreateUserFont(char const *,ulong *,HDC__ *,int)
0x18005d5bd  mov     [rdi+10A0h], rax
0x18005d5c4  mov     rcx, [rdi+10A0h]; h
0x18005d5cb  lea     r8, [rsp+2F0h+pv]; pv
0x18005d5d0  mov     edx, 3Ch ; '<'; c
0x18005d5d5  call    cs:__imp_GetObjectA
0x18005d5db  xor     r9d, r9d; fWinIni
0x18005d5de  mov     [rsp+2F0h+pvParam], 158h
0x18005d5e6  lea     r8, [rsp+2F0h+pvParam]; pvParam
0x18005d5eb  mov     edx, 158h; uiParam
0x18005d5f0  mov     ebx, eax
0x18005d5f2  lea     ecx, [r9+29h]; uiAction
0x18005d5f6  call    cs:__imp_SystemParametersInfoA
0x18005d5fc  test    ebx, ebx
0x18005d5fe  jz      short loc_18005D61E
0x18005d600  test    eax, eax
0x18005d602  jz      short loc_18005D61E
0x18005d604  mov     eax, [rbp+1F0h+var_1F0]
0x18005d607  cmp     eax, dword ptr [rsp+2F0h+pv]
0x18005d60b  jge     short loc_18005D61E
0x18005d60d  lea     rcx, [rsp+2F0h+pv]; lplf
0x18005d612  mov     dword ptr [rsp+2F0h+pv], eax
0x18005d616  call    cs:__imp_CreateFontIndirectA
0x18005d61c  jmp     short loc_18005D625
0x18005d61e  mov     rax, [rdi+10A0h]
0x18005d625  mov     [rdi+10A8h], rax
0x18005d62c  mov     rcx, [rbp+1F0h+var_10]
0x18005d633  xor     rcx, rsp; StackCookie
0x18005d636  call    __security_check_cookie
0x18005d63b  lea     r11, [rsp+2F0h+var_s0]
0x18005d643  mov     rbx, [r11+20h]
0x18005d647  mov     rdi, [r11+28h]
0x18005d64b  mov     rsp, r11
0x18005d64e  pop     rbp
0x18005d64f  retn
```
