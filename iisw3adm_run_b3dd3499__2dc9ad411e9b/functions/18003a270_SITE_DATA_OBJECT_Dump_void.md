# SITE_DATA_OBJECT::Dump(void)

- ea: `0x18003a270`
- end: `0x18003a520`
- name: `?Dump@SITE_DATA_OBJECT@@UEAAXXZ`
- size: `688`
- prototype: `void __fastcall(SITE_DATA_OBJECT *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800157c4`
- `0x18003a270`
- `0x18006101a`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18003a4f6`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18003a4f6`
- `iisutil!PuDbgPrint` at `0x18003a352`
- `iisutil!PuDbgPrint` at `0x18003a4e8`
- `iisutil!PuDbgPrint` at `0x18003a352`
- `iisutil!PuDbgPrint` at `0x18003a4e8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003a30c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003a30c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003a2c6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003a2c6`

## string_xrefs

- `0x18003a4d7`: `Site data %p:\n     Self Valid =%d; \n     Cross Valid =%d; \n     InWAS = %S; \n     DeleteWhenDone = %S \n     Does WAS Care About = %S\n     Should WAS Insert = %S\n     Should WAS Update = %S\n     Should WAS Delete = %S\n     Will WAS Know about = %S\n     Have properties Changed = %S \n`
- `0x18003a33f`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore.hxx`
- `0x18003a4a7`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\sitestore.hxx`

## pseudocode

```c
void __fastcall SITE_DATA_OBJECT::Dump(SITE_DATA_OBJECT *this)
{
  int v2; // eax
  int v3; // ecx
  const wchar_t *v4; // rsi
  const wchar_t *v5; // r12
  const wchar_t *v6; // r13
  int v7; // ebp
  int v8; // eax
  const wchar_t *v9; // r15
  bool v10; // zf
  int v11; // eax
  const wchar_t *v12; // r14
  const wchar_t *v13; // rdi
  const wchar_t *v14; // rcx
  const wchar_t *v15; // rax
  _BYTE v16[32]; // [rsp+80h] [rbp-498h] BYREF
  __int64 v17; // [rsp+A0h] [rbp-478h]
  unsigned __int16 v18[256]; // [rsp+C0h] [rbp-458h] BYREF
  unsigned __int16 v19[256]; // [rsp+2C0h] [rbp-258h] BYREF

  memset_0(v18, 0, sizeof(v18));
  STRU::STRU((STRU *)v16, v18, 0x100u);
  if ( (g_dwDebugFlags & 0x50000) == 0 )
    goto LABEL_46;
  StringCchPrintfW(v19, 0x100u, L"SITE_DATA_OBJECT %p \n     SiteId = %d \n     ", this, *((_DWORD *)this + 12));
  STRU::Copy((STRU *)v16, v19);
  if ( (g_dwDebugFlags & 3) == 0 )
    goto LABEL_46;
  PuDbgPrint(
    g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore.hxx",
    226,
    "SITE_DATA_OBJECT::Dump",
    "%ws",
    v17);
  if ( (g_dwDebugFlags & 3) == 0 )
    goto LABEL_46;
  v2 = (*(__int64 (__fastcall **)(SITE_DATA_OBJECT *))(*(_QWORD *)this + 32LL))(this);
  v3 = *((_DWORD *)this + 6);
  v4 = L"TRUE";
  v5 = L"FALSE";
  v6 = L"TRUE";
  if ( !v2 )
    v6 = L"FALSE";
  v7 = 1;
  if ( !v3 || !*((_DWORD *)this + 7) || (v8 = 1, *((_DWORD *)this + 5)) )
    v8 = 0;
  v9 = L"TRUE";
  if ( !v8 )
    v9 = L"FALSE";
  if ( !*((_DWORD *)this + 4) )
    goto LABEL_21;
  if ( !v3 || !*((_DWORD *)this + 7) || *((_DWORD *)this + 5) )
    v5 = L"TRUE";
  if ( !v3
    || !*((_DWORD *)this + 7)
    || *((_DWORD *)this + 5)
    || (v10 = (*(unsigned int (__fastcall **)(SITE_DATA_OBJECT *, _QWORD))(*(_QWORD *)this + 32LL))(this, 0) == 0,
        v11 = 1,
        v10) )
  {
LABEL_21:
    v11 = 0;
  }
  v12 = L"TRUE";
  if ( !v11 )
    v12 = L"FALSE";
  if ( !*((_DWORD *)this + 4) )
  {
    if ( *((_DWORD *)this + 6) && *((_DWORD *)this + 7) && !*((_DWORD *)this + 5) )
    {
      v13 = L"TRUE";
      goto LABEL_39;
    }
    v13 = L"FALSE";
    if ( *((_DWORD *)this + 6) && *((_DWORD *)this + 7) && !*((_DWORD *)this + 5) )
      goto LABEL_39;
LABEL_37:
    v7 = 0;
    goto LABEL_39;
  }
  if ( !*((_DWORD *)this + 6) || !*((_DWORD *)this + 7) || *((_DWORD *)this + 5) )
  {
    v13 = L"FALSE";
    goto LABEL_39;
  }
  v13 = L"FALSE";
  if ( !(*(unsigned int (__fastcall **)(SITE_DATA_OBJECT *, _QWORD))(*(_QWORD *)this + 32LL))(this, 0) )
    goto LABEL_37;
LABEL_39:
  v14 = L"TRUE";
  if ( !v7 )
    v14 = L"FALSE";
  v15 = L"TRUE";
  if ( !*((_DWORD *)this + 5) )
    v15 = L"FALSE";
  if ( !*((_DWORD *)this + 4) )
    v4 = L"FALSE";
  PuDbgPrint(
    g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\sitestore.hxx",
    250,
    "SITE_DATA_OBJECT::Dump",
    "Site data %p:\n"
    "     Self Valid =%d; \n"
    "     Cross Valid =%d; \n"
    "     InWAS = %S; \n"
    "     DeleteWhenDone = %S \n"
    "     Does WAS Care About = %S\n"
    "     Should WAS Insert = %S\n"
    "     Should WAS Update = %S\n"
    "     Should WAS Delete = %S\n"
    "     Will WAS Know about = %S\n"
    "     Have properties Changed = %S \n",
    this,
    *((_DWORD *)this + 7),
    *((_DWORD *)this + 6),
    v4,
    v15,
    v14,
    v13,
    v12,
    v5,
    v9,
    v6);
LABEL_46:
  STRU::~STRU((STRU *)v16);
}

```

## disassembly

```asm
0x18003a270  push    rbx
0x18003a272  push    rbp
0x18003a273  push    rsi
0x18003a274  push    rdi
0x18003a275  push    r12
0x18003a277  push    r13
0x18003a279  push    r14
0x18003a27b  push    r15
0x18003a27d  sub     rsp, 4D8h
0x18003a284  mov     rax, cs:__security_cookie
0x18003a28b  xor     rax, rsp
0x18003a28e  mov     [rsp+518h+var_58], rax
0x18003a296  mov     rbx, rcx
0x18003a299  xor     edx, edx; Val
0x18003a29b  lea     rcx, [rsp+518h+var_458]; void *
0x18003a2a3  mov     r8d, 200h; Size
0x18003a2a9  call    memset_0
0x18003a2ae  mov     edi, 100h
0x18003a2b3  lea     rdx, [rsp+518h+var_458]
0x18003a2bb  mov     r8d, edi
0x18003a2be  lea     rcx, [rsp+518h+var_498]
0x18003a2c6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18003a2cc  test    cs:g_dwDebugFlags, 50000h
0x18003a2d6  jz      loc_18003A4EE
0x18003a2dc  mov     eax, [rbx+30h]
0x18003a2df  lea     r8, aSiteDataObject_11; "SITE_DATA_OBJECT %p \n     SiteId = %d "...
0x18003a2e6  mov     r9, rbx
0x18003a2e9  mov     dword ptr [rsp+518h+var_4F8], eax
0x18003a2ed  mov     edx, edi; unsigned __int64
0x18003a2ef  lea     rcx, [rsp+518h+var_258]; unsigned __int16 *
0x18003a2f7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a2fc  lea     rdx, [rsp+518h+var_258]
0x18003a304  lea     rcx, [rsp+518h+var_498]
0x18003a30c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003a312  mov     eax, cs:g_dwDebugFlags
0x18003a318  test    al, 3
0x18003a31a  jz      loc_18003A4EE
0x18003a320  mov     rax, [rsp+518h+var_478]
0x18003a328  lea     r9, aSiteDataObject_7; "SITE_DATA_OBJECT::Dump"
0x18003a32f  mov     rcx, cs:g_pDebug
0x18003a336  lea     r8d, [rdi-1Eh]
0x18003a33a  mov     [rsp+518h+var_4F0], rax
0x18003a33f  lea     rdx, aServercommonIn_17; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18003a346  lea     rax, aWs; "%ws"
0x18003a34d  mov     [rsp+518h+var_4F8], rax
0x18003a352  call    cs:__imp_PuDbgPrint
0x18003a358  mov     eax, cs:g_dwDebugFlags
0x18003a35e  test    al, 3
0x18003a360  jz      loc_18003A4EE
0x18003a366  mov     rax, [rbx]
0x18003a369  mov     rcx, rbx
0x18003a36c  mov     rax, [rax+20h]
0x18003a370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a375  mov     ecx, [rbx+18h]
0x18003a378  lea     rsi, aTrue_1; "TRUE"
0x18003a37f  xor     edx, edx
0x18003a381  lea     r12, aFalse_1; "FALSE"
0x18003a388  test    eax, eax
0x18003a38a  mov     r13, rsi
0x18003a38d  cmovz   r13, r12
0x18003a391  lea     ebp, [rdx+1]
0x18003a394  test    ecx, ecx
0x18003a396  jz      short loc_18003A3A4
0x18003a398  cmp     [rbx+1Ch], edx
0x18003a39b  jz      short loc_18003A3A4
0x18003a39d  mov     eax, ebp
0x18003a39f  cmp     [rbx+14h], edx
0x18003a3a2  jz      short loc_18003A3A6
0x18003a3a4  mov     eax, edx
0x18003a3a6  test    eax, eax
0x18003a3a8  mov     r15, rsi
0x18003a3ab  mov     eax, [rbx+10h]
0x18003a3ae  cmovz   r15, r12
0x18003a3b2  test    eax, eax
0x18003a3b4  jz      short loc_18003A3F2
0x18003a3b6  test    ecx, ecx
0x18003a3b8  jz      short loc_18003A3C4
0x18003a3ba  cmp     [rbx+1Ch], edx
0x18003a3bd  jz      short loc_18003A3C4
0x18003a3bf  cmp     [rbx+14h], edx
0x18003a3c2  jz      short loc_18003A3C9
0x18003a3c4  mov     r12, rsi
0x18003a3c7  jmp     short loc_18003A3CD
0x18003a3c9  test    eax, eax
0x18003a3cb  jz      short loc_18003A3F2
0x18003a3cd  test    ecx, ecx
0x18003a3cf  jz      short loc_18003A3F2
0x18003a3d1  cmp     [rbx+1Ch], edx
0x18003a3d4  jz      short loc_18003A3F2
0x18003a3d6  cmp     [rbx+14h], edx
0x18003a3d9  jnz     short loc_18003A3F2
0x18003a3db  mov     rax, [rbx]
0x18003a3de  mov     rcx, rbx
0x18003a3e1  mov     rax, [rax+20h]
0x18003a3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3ea  xor     edx, edx
0x18003a3ec  test    eax, eax
0x18003a3ee  mov     eax, ebp
0x18003a3f0  jnz     short loc_18003A3F4
0x18003a3f2  mov     eax, edx
0x18003a3f4  test    eax, eax
0x18003a3f6  lea     r8, aFalse_1; "FALSE"
0x18003a3fd  mov     eax, [rbx+10h]
0x18003a400  mov     r14, rsi
0x18003a403  cmovz   r14, r8
0x18003a407  test    eax, eax
0x18003a409  jnz     short loc_18003A437
0x18003a40b  cmp     [rbx+18h], edx
0x18003a40e  jz      short loc_18003A41F
0x18003a410  cmp     [rbx+1Ch], edx
0x18003a413  jz      short loc_18003A41F
0x18003a415  cmp     [rbx+14h], edx
0x18003a418  jnz     short loc_18003A41F
0x18003a41a  mov     rdi, rsi
0x18003a41d  jmp     short loc_18003A46C
0x18003a41f  test    eax, eax
0x18003a421  jnz     short loc_18003A437
0x18003a423  mov     rdi, r8
0x18003a426  cmp     [rbx+18h], edx
0x18003a429  jz      short loc_18003A465
0x18003a42b  cmp     [rbx+1Ch], edx
0x18003a42e  jz      short loc_18003A465
0x18003a430  cmp     [rbx+14h], edx
0x18003a433  jnz     short loc_18003A465
0x18003a435  jmp     short loc_18003A46C
0x18003a437  cmp     [rbx+18h], edx
0x18003a43a  jz      short loc_18003A469
0x18003a43c  cmp     [rbx+1Ch], edx
0x18003a43f  jz      short loc_18003A469
0x18003a441  cmp     [rbx+14h], edx
0x18003a444  jnz     short loc_18003A469
0x18003a446  mov     rax, [rbx]
0x18003a449  mov     rcx, rbx
0x18003a44c  mov     rdi, r8
0x18003a44f  mov     rax, [rax+20h]
0x18003a453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a458  xor     edx, edx
0x18003a45a  lea     r8, aFalse_1; "FALSE"
0x18003a461  test    eax, eax
0x18003a463  jnz     short loc_18003A46C
0x18003a465  mov     ebp, edx
0x18003a467  jmp     short loc_18003A46C
0x18003a469  mov     rdi, r8
0x18003a46c  mov     [rsp+518h+var_4A0], r13
0x18003a471  lea     r9, aSiteDataObject_7; "SITE_DATA_OBJECT::Dump"
0x18003a478  mov     [rsp+518h+var_4A8], r15
0x18003a47d  test    ebp, ebp
0x18003a47f  mov     [rsp+518h+var_4B0], r12
0x18003a484  mov     rcx, rsi
0x18003a487  mov     [rsp+518h+var_4B8], r14
0x18003a48c  cmovz   rcx, r8
0x18003a490  cmp     [rbx+14h], edx
0x18003a493  mov     rax, rsi
0x18003a496  mov     [rsp+518h+var_4C0], rdi
0x18003a49b  mov     [rsp+518h+var_4C8], rcx
0x18003a4a0  cmovz   rax, r8
0x18003a4a4  cmp     [rbx+10h], edx
0x18003a4a7  lea     rdx, aServercommonIn_17; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18003a4ae  mov     rcx, cs:g_pDebug
0x18003a4b5  mov     [rsp+518h+var_4D0], rax
0x18003a4ba  cmovz   rsi, r8
0x18003a4be  mov     eax, [rbx+18h]
0x18003a4c1  mov     r8d, 0FAh
0x18003a4c7  mov     [rsp+518h+var_4D8], rsi
0x18003a4cc  mov     [rsp+518h+var_4E0], eax
0x18003a4d0  mov     eax, [rbx+1Ch]
0x18003a4d3  mov     [rsp+518h+var_4E8], eax
0x18003a4d7  lea     rax, aSiteDataPSelfV; "Site data %p:\n     Self Valid =%d; \n "...
0x18003a4de  mov     [rsp+518h+var_4F0], rbx
0x18003a4e3  mov     [rsp+518h+var_4F8], rax
0x18003a4e8  call    cs:__imp_PuDbgPrint
0x18003a4ee  lea     rcx, [rsp+518h+var_498]
0x18003a4f6  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18003a4fc  mov     rcx, [rsp+518h+var_58]
0x18003a504  xor     rcx, rsp; StackCookie
0x18003a507  call    __security_check_cookie
0x18003a50c  add     rsp, 4D8h
0x18003a513  pop     r15
0x18003a515  pop     r14
0x18003a517  pop     r13
0x18003a519  pop     r12
0x18003a51b  pop     rdi
0x18003a51c  pop     rsi
0x18003a51d  pop     rbp
0x18003a51e  pop     rbx
0x18003a51f  retn
```
