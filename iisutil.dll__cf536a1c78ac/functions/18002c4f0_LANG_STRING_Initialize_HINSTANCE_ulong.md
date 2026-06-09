# LANG_STRING::Initialize(HINSTANCE__ *,ulong)

- ea: `0x18002c4f0`
- end: `0x18002c7ec`
- name: `?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z`
- size: `764`
- prototype: `__int64 __fastcall(LANG_STRING *__hidden this, HINSTANCE, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18002d7a0`

## callees

- `0x1800034f0`
- `0x180019230`
- `0x180019270`
- `0x18001a7f0`
- `0x18002c4f0`
- `0x18002e52e`
- `0x18002e560`

## import_xrefs

- `msvcrt!_stricmp` at `0x18002c6dc`
- `msvcrt!_stricmp` at `0x18002c704`
- `msvcrt!_stricmp` at `0x18002c6dc`
- `msvcrt!_stricmp` at `0x18002c704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c59f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c59f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002c58f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002c58f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c7b3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c7b3`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18002c6a8`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18002c6a8`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x18002c68e`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x18002c68e`
- `api-ms-win-core-localization-obsolete-l1-2-0!EnumUILanguagesW` at `0x18002c659`
- `api-ms-win-core-localization-obsolete-l1-2-0!EnumUILanguagesW` at `0x18002c659`

## pseudocode

```c
__int64 __fastcall LANG_STRING::Initialize(LANG_STRING *this, HINSTANCE a2, int a3)
{
  int v6; // r13d
  signed int LastError; // eax
  signed int v8; // ebx
  void *v9; // rax
  unsigned int i; // edx
  __int64 v11; // rcx
  _QWORD *v12; // rcx
  LANGID SystemDefaultUILanguage; // ax
  unsigned int j; // edi
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // edx
  unsigned int k; // r15d
  void *v19; // rcx
  void *v20; // rcx
  LONG_PTR lParam[2]; // [rsp+20h] [rbp-E0h] BYREF
  void *Block; // [rsp+30h] [rbp-D0h]
  _BYTE v24[32]; // [rsp+38h] [rbp-C8h] BYREF
  char *String1; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  __int16 v27; // [rsp+64h] [rbp-9Ch]
  int v28; // [rsp+68h] [rbp-98h]
  char v29; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[104]; // [rsp+90h] [rbp-70h] BYREF

  Block = 0;
  *(_OWORD *)lParam = 0;
  memset_0(Name, 0, 0xC8u);
  v26 = 32;
  v27 = 256;
  String1 = &v29;
  v6 = 0;
  v28 = 0;
  v29 = 0;
  if ( !a2 || !a3 )
  {
LABEL_22:
    v8 = -2147024809;
    goto LABEL_23;
  }
  *((_QWORD *)this + 1) = a2;
  *((_DWORD *)this + 4) = a3;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 48), 0x3E8u) )
  {
    v6 = 1;
    v9 = operator new(saturated_mul(*((unsigned int *)this + 4), 0x10u));
    *((_QWORD *)this + 3) = v9;
    if ( !v9 )
      goto LABEL_7;
    memset_0(v9, 0, 8LL * *((unsigned int *)this + 4));
    for ( i = 0; i < *((_DWORD *)this + 4); *v12 = v12 )
    {
      v11 = i++;
      v12 = (_QWORD *)(*((_QWORD *)this + 3) + 16 * v11);
      v12[1] = v12;
    }
    lParam[0] = 1;
    LODWORD(lParam[1]) = 0;
    Block = operator new(8u);
    if ( !Block )
    {
LABEL_7:
      v8 = -2147024888;
      goto LABEL_23;
    }
    if ( EnumUILanguagesW(LANG_STRING::EnumUILanguagesProc, 8u, (LONG_PTR)lParam) )
    {
      v8 = lParam[1];
      if ( SLODWORD(lParam[1]) < 0 )
        goto LABEL_23;
      *((_DWORD *)this + 10) = HIDWORD(lParam[0]);
      *((_QWORD *)this + 4) = Block;
      Block = 0;
      SystemDefaultUILanguage = GetSystemDefaultUILanguage();
      if ( LCIDToLocaleName(SystemDefaultUILanguage, Name, 100, 0) )
      {
        v8 = STRA::CopyWTruncate((STRA *)v24, Name);
        if ( v8 < 0 )
          goto LABEL_23;
        if ( !_stricmp(String1, **((const char ***)this + 4)) )
        {
LABEL_21:
          *(_DWORD *)this = 1;
          goto LABEL_23;
        }
        for ( j = 1; j < *((_DWORD *)this + 10); ++j )
        {
          if ( !_stricmp(String1, *(const char **)(*((_QWORD *)this + 4) + 8LL * j)) )
          {
            v15 = (_QWORD *)*((_QWORD *)this + 4);
            v16 = v15[j];
            v15[j] = *v15;
            **((_QWORD **)this + 4) = v16;
            goto LABEL_21;
          }
        }
        goto LABEL_22;
      }
    }
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_23:
  if ( Block )
  {
    v17 = HIDWORD(lParam[0]);
    for ( k = 0; k < v17; ++k )
    {
      v19 = (void *)*((_QWORD *)Block + k);
      if ( v19 )
      {
        operator delete(v19);
        *((_QWORD *)Block + k) = 0;
        v17 = HIDWORD(lParam[0]);
      }
    }
    operator delete(Block);
    Block = 0;
  }
  if ( v8 < 0 )
  {
    v20 = (void *)*((_QWORD *)this + 3);
    if ( v20 )
    {
      operator delete(v20);
      *((_QWORD *)this + 3) = 0;
    }
    if ( v6 )
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  }
  BUFFER::~BUFFER((BUFFER *)v24);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002c4f0  push    rbp
0x18002c4f2  push    rbx
0x18002c4f3  push    rsi
0x18002c4f4  push    rdi
0x18002c4f5  push    r12
0x18002c4f7  push    r13
0x18002c4f9  push    r14
0x18002c4fb  push    r15
0x18002c4fd  lea     rbp, [rsp-78h]
0x18002c502  sub     rsp, 178h
0x18002c509  mov     rax, cs:__security_cookie
0x18002c510  xor     rax, rsp
0x18002c513  mov     [rbp+0B0h+var_50], rax
0x18002c517  mov     ebx, r8d
0x18002c51a  mov     rdi, rdx
0x18002c51d  mov     rsi, rcx
0x18002c520  xorps   xmm0, xmm0
0x18002c523  xor     eax, eax
0x18002c525  lea     rcx, [rbp+0B0h+Name]; void *
0x18002c529  xor     edx, edx; Val
0x18002c52b  mov     [rsp+1B0h+Block], rax
0x18002c530  mov     r8d, 0C8h; Size
0x18002c536  movups  xmmword ptr [rsp+1B0h+lParam], xmm0
0x18002c53b  call    memset_0
0x18002c540  xor     r12d, r12d
0x18002c543  mov     [rsp+1B0h+var_150], 20h ; ' '
0x18002c54b  mov     [rsp+1B0h+var_14C], 100h
0x18002c552  lea     rax, [rsp+1B0h+var_140]
0x18002c557  mov     [rsp+1B0h+String1], rax
0x18002c55c  mov     r13d, r12d
0x18002c55f  mov     [rsp+1B0h+var_148], r12d
0x18002c564  mov     [rsp+1B0h+var_140], r12b
0x18002c569  lea     r15d, [r12+1]
0x18002c56e  test    rdi, rdi
0x18002c571  jz      loc_18002C734
0x18002c577  test    ebx, ebx
0x18002c579  jz      loc_18002C734
0x18002c57f  lea     rcx, [rsi+30h]; lpCriticalSection
0x18002c583  mov     [rsi+8], rdi
0x18002c587  mov     edx, 3E8h; dwSpinCount
0x18002c58c  mov     [rsi+10h], ebx
0x18002c58f  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002c596  nop     dword ptr [rax+rax+00h]
0x18002c59b  test    eax, eax
0x18002c59d  jnz     short loc_18002C5C3
0x18002c59f  call    cs:__imp_GetLastError
0x18002c5a6  nop     dword ptr [rax+rax+00h]
0x18002c5ab  mov     ebx, eax
0x18002c5ad  test    eax, eax
0x18002c5af  jle     loc_18002C739
0x18002c5b5  movzx   ebx, ax
0x18002c5b8  or      ebx, 80070000h
0x18002c5be  jmp     loc_18002C739
0x18002c5c3  mov     ecx, [rsi+10h]
0x18002c5c6  mov     eax, 10h
0x18002c5cb  mul     rcx
0x18002c5ce  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002c5d5  mov     r13d, r15d
0x18002c5d8  cmovb   rax, rcx
0x18002c5dc  mov     rcx, rax; Size
0x18002c5df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c5e4  mov     [rsi+18h], rax
0x18002c5e8  test    rax, rax
0x18002c5eb  jnz     short loc_18002C5F7
0x18002c5ed  mov     ebx, 80070008h
0x18002c5f2  jmp     loc_18002C739
0x18002c5f7  mov     r8d, [rsi+10h]
0x18002c5fb  xor     edx, edx; Val
0x18002c5fd  shl     r8, 3; Size
0x18002c601  mov     rcx, rax; void *
0x18002c604  call    memset_0
0x18002c609  mov     edx, r12d
0x18002c60c  cmp     [rsi+10h], r12d
0x18002c610  jbe     short loc_18002C62B
0x18002c612  mov     ecx, edx
0x18002c614  add     edx, r15d
0x18002c617  shl     rcx, 4
0x18002c61b  add     rcx, [rsi+18h]
0x18002c61f  mov     [rcx+8], rcx
0x18002c623  mov     [rcx], rcx
0x18002c626  cmp     edx, [rsi+10h]
0x18002c629  jb      short loc_18002C612
0x18002c62b  mov     ebx, 8
0x18002c630  mov     [rsp+1B0h+lParam], r13
0x18002c635  mov     ecx, ebx; Size
0x18002c637  mov     dword ptr [rsp+1B0h+lParam+8], r12d
0x18002c63c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c641  mov     [rsp+1B0h+Block], rax
0x18002c646  test    rax, rax
0x18002c649  jz      short loc_18002C5ED
0x18002c64b  lea     r8, [rsp+1B0h+lParam]; lParam
0x18002c650  mov     edx, ebx; dwFlags
0x18002c652  lea     rcx, ?EnumUILanguagesProc@LANG_STRING@@CAHPEAG_J@Z; lpUILanguageEnumProc
0x18002c659  call    cs:__imp_EnumUILanguagesW
0x18002c660  nop     dword ptr [rax+rax+00h]
0x18002c665  test    eax, eax
0x18002c667  jz      loc_18002C59F
0x18002c66d  mov     ebx, dword ptr [rsp+1B0h+lParam+8]
0x18002c671  test    ebx, ebx
0x18002c673  js      loc_18002C739
0x18002c679  mov     eax, dword ptr [rsp+1B0h+lParam+4]
0x18002c67d  mov     [rsi+28h], eax
0x18002c680  mov     rax, [rsp+1B0h+Block]
0x18002c685  mov     [rsi+20h], rax
0x18002c689  mov     [rsp+1B0h+Block], r12
0x18002c68e  call    cs:__imp_GetSystemDefaultUILanguage
0x18002c695  nop     dword ptr [rax+rax+00h]
0x18002c69a  xor     r9d, r9d; dwFlags
0x18002c69d  movzx   ecx, ax; Locale
0x18002c6a0  lea     rdx, [rbp+0B0h+Name]; lpName
0x18002c6a4  lea     r8d, [r9+64h]; cchName
0x18002c6a8  call    cs:__imp_LCIDToLocaleName
0x18002c6af  nop     dword ptr [rax+rax+00h]
0x18002c6b4  test    eax, eax
0x18002c6b6  jz      loc_18002C59F
0x18002c6bc  lea     rdx, [rbp+0B0h+Name]; unsigned __int16 *
0x18002c6c0  lea     rcx, [rsp+1B0h+var_178]; this
0x18002c6c5  call    ?CopyWTruncate@STRA@@QEAAJPEBG@Z; STRA::CopyWTruncate(ushort const *)
0x18002c6ca  mov     ebx, eax
0x18002c6cc  test    eax, eax
0x18002c6ce  js      short loc_18002C739
0x18002c6d0  mov     rdx, [rsi+20h]
0x18002c6d4  mov     rcx, [rsp+1B0h+String1]; String1
0x18002c6d9  mov     rdx, [rdx]; String2
0x18002c6dc  call    cs:__imp__stricmp
0x18002c6e3  nop     dword ptr [rax+rax+00h]
0x18002c6e8  test    eax, eax
0x18002c6ea  jz      short loc_18002C72F
0x18002c6ec  mov     edi, r15d
0x18002c6ef  cmp     edi, [rsi+28h]
0x18002c6f2  jnb     short loc_18002C734
0x18002c6f4  mov     rdx, [rsi+20h]
0x18002c6f8  mov     rcx, [rsp+1B0h+String1]; String1
0x18002c6fd  mov     r14d, edi
0x18002c700  mov     rdx, [rdx+r14*8]; String2
0x18002c704  call    cs:__imp__stricmp
0x18002c70b  nop     dword ptr [rax+rax+00h]
0x18002c710  test    eax, eax
0x18002c712  jz      short loc_18002C719
0x18002c714  add     edi, r15d
0x18002c717  jmp     short loc_18002C6EF
0x18002c719  mov     rcx, [rsi+20h]
0x18002c71d  mov     rax, [rcx]
0x18002c720  mov     rdx, [rcx+r14*8]
0x18002c724  mov     [rcx+r14*8], rax
0x18002c728  mov     rax, [rsi+20h]
0x18002c72c  mov     [rax], rdx
0x18002c72f  mov     [rsi], r15d
0x18002c732  jmp     short loc_18002C739
0x18002c734  mov     ebx, 80070057h
0x18002c739  mov     edi, 30h ; '0'
0x18002c73e  mov     r14, rsi
0x18002c741  cmp     [rsp+1B0h+Block], r12
0x18002c746  jz      short loc_18002C794
0x18002c748  mov     edx, dword ptr [rsp+1B0h+lParam+4]
0x18002c74c  mov     r15d, r12d
0x18002c74f  test    edx, edx
0x18002c751  jz      short loc_18002C785
0x18002c753  mov     rax, [rsp+1B0h+Block]
0x18002c758  mov     r12d, r15d
0x18002c75b  mov     rcx, [rax+r12*8]; Block
0x18002c75f  test    rcx, rcx
0x18002c762  jz      short loc_18002C77A
0x18002c764  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c769  mov     rax, [rsp+1B0h+Block]
0x18002c76e  mov     qword ptr [rax+r12*8], 0
0x18002c776  mov     edx, dword ptr [rsp+1B0h+lParam+4]
0x18002c77a  inc     r15d
0x18002c77d  cmp     r15d, edx
0x18002c780  jb      short loc_18002C753
0x18002c782  xor     r12d, r12d
0x18002c785  mov     rcx, [rsp+1B0h+Block]; Block
0x18002c78a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c78f  mov     [rsp+1B0h+Block], r12
0x18002c794  test    ebx, ebx
0x18002c796  jns     short loc_18002C7BF
0x18002c798  mov     rcx, [rsi+18h]; Block
0x18002c79c  test    rcx, rcx
0x18002c79f  jz      short loc_18002C7AA
0x18002c7a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002c7a6  mov     [rsi+18h], r12
0x18002c7aa  test    r13d, r13d
0x18002c7ad  jz      short loc_18002C7BF
0x18002c7af  lea     rcx, [rdi+r14]; lpCriticalSection
0x18002c7b3  call    cs:__imp_DeleteCriticalSection
0x18002c7ba  nop     dword ptr [rax+rax+00h]
0x18002c7bf  lea     rcx, [rsp+1B0h+var_178]; this
0x18002c7c4  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002c7c9  mov     eax, ebx
0x18002c7cb  mov     rcx, [rbp+0B0h+var_50]
0x18002c7cf  xor     rcx, rsp; StackCookie
0x18002c7d2  call    __security_check_cookie
0x18002c7d7  add     rsp, 178h
0x18002c7de  pop     r15
0x18002c7e0  pop     r14
0x18002c7e2  pop     r13
0x18002c7e4  pop     r12
0x18002c7e6  pop     rdi
0x18002c7e7  pop     rsi
0x18002c7e8  pop     rbx
0x18002c7e9  pop     rbp
0x18002c7ea  retn
```
