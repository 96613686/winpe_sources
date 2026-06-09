# LANG_STRING::Initialize(HINSTANCE__ *,ulong)

- ea: `0x18002a610`
- end: `0x18002a8db`
- name: `?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z`
- size: `715`
- prototype: `__int64 __fastcall(LANG_STRING *__hidden this, HINSTANCE, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18002b7f8`

## callees

- `0x180002b60`
- `0x1800183f8`
- `0x180018438`
- `0x180019980`
- `0x18002a610`
- `0x18002c48e`
- `0x18002c4c0`

## import_xrefs

- `msvcrt!_stricmp` at `0x18002a7de`
- `msvcrt!_stricmp` at `0x18002a800`
- `msvcrt!_stricmp` at `0x18002a7de`
- `msvcrt!_stricmp` at `0x18002a800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6b9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002a6af`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002a6af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a8a9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a8a9`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18002a7b0`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18002a7b0`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x18002a79c`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x18002a79c`
- `api-ms-win-core-localization-obsolete-l1-2-0!EnumUILanguagesW` at `0x18002a76d`
- `api-ms-win-core-localization-obsolete-l1-2-0!EnumUILanguagesW` at `0x18002a76d`

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
0x18002a610  push    rbp
0x18002a612  push    rbx
0x18002a613  push    rsi
0x18002a614  push    rdi
0x18002a615  push    r12
0x18002a617  push    r13
0x18002a619  push    r14
0x18002a61b  push    r15
0x18002a61d  lea     rbp, [rsp-78h]
0x18002a622  sub     rsp, 178h
0x18002a629  mov     rax, cs:__security_cookie
0x18002a630  xor     rax, rsp
0x18002a633  mov     [rbp+0B0h+var_50], rax
0x18002a637  mov     ebx, r8d
0x18002a63a  mov     rdi, rdx
0x18002a63d  mov     rsi, rcx
0x18002a640  xorps   xmm0, xmm0
0x18002a643  xor     eax, eax
0x18002a645  lea     rcx, [rbp+0B0h+Name]; void *
0x18002a649  xor     edx, edx; Val
0x18002a64b  mov     [rsp+1B0h+Block], rax
0x18002a650  mov     r8d, 0C8h; Size
0x18002a656  movups  xmmword ptr [rsp+1B0h+lParam], xmm0
0x18002a65b  call    memset_0
0x18002a660  xor     r12d, r12d
0x18002a663  mov     [rsp+1B0h+var_150], 20h ; ' '
0x18002a66b  mov     [rsp+1B0h+var_14C], 100h
0x18002a672  lea     rax, [rsp+1B0h+var_140]
0x18002a677  mov     [rsp+1B0h+String1], rax
0x18002a67c  mov     r13d, r12d
0x18002a67f  mov     [rsp+1B0h+var_148], r12d
0x18002a684  mov     [rsp+1B0h+var_140], r12b
0x18002a689  lea     r15d, [r12+1]
0x18002a68e  test    rdi, rdi
0x18002a691  jz      loc_18002A82A
0x18002a697  test    ebx, ebx
0x18002a699  jz      loc_18002A82A
0x18002a69f  lea     rcx, [rsi+30h]; lpCriticalSection
0x18002a6a3  mov     [rsi+8], rdi
0x18002a6a7  mov     edx, 3E8h; dwSpinCount
0x18002a6ac  mov     [rsi+10h], ebx
0x18002a6af  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002a6b5  test    eax, eax
0x18002a6b7  jnz     short loc_18002A6D7
0x18002a6b9  call    cs:__imp_GetLastError
0x18002a6bf  mov     ebx, eax
0x18002a6c1  test    eax, eax
0x18002a6c3  jle     loc_18002A82F
0x18002a6c9  movzx   ebx, ax
0x18002a6cc  or      ebx, 80070000h
0x18002a6d2  jmp     loc_18002A82F
0x18002a6d7  mov     ecx, [rsi+10h]
0x18002a6da  mov     eax, 10h
0x18002a6df  mul     rcx
0x18002a6e2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002a6e9  mov     r13d, r15d
0x18002a6ec  cmovb   rax, rcx
0x18002a6f0  mov     rcx, rax; Size
0x18002a6f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a6f8  mov     [rsi+18h], rax
0x18002a6fc  test    rax, rax
0x18002a6ff  jnz     short loc_18002A70B
0x18002a701  mov     ebx, 80070008h
0x18002a706  jmp     loc_18002A82F
0x18002a70b  mov     r8d, [rsi+10h]
0x18002a70f  xor     edx, edx; Val
0x18002a711  shl     r8, 3; Size
0x18002a715  mov     rcx, rax; void *
0x18002a718  call    memset_0
0x18002a71d  mov     edx, r12d
0x18002a720  cmp     [rsi+10h], r12d
0x18002a724  jbe     short loc_18002A73F
0x18002a726  mov     ecx, edx
0x18002a728  add     edx, r15d
0x18002a72b  shl     rcx, 4
0x18002a72f  add     rcx, [rsi+18h]
0x18002a733  mov     [rcx+8], rcx
0x18002a737  mov     [rcx], rcx
0x18002a73a  cmp     edx, [rsi+10h]
0x18002a73d  jb      short loc_18002A726
0x18002a73f  mov     ebx, 8
0x18002a744  mov     [rsp+1B0h+lParam], r13
0x18002a749  mov     ecx, ebx; Size
0x18002a74b  mov     dword ptr [rsp+1B0h+lParam+8], r12d
0x18002a750  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a755  mov     [rsp+1B0h+Block], rax
0x18002a75a  test    rax, rax
0x18002a75d  jz      short loc_18002A701
0x18002a75f  lea     r8, [rsp+1B0h+lParam]; lParam
0x18002a764  mov     edx, ebx; dwFlags
0x18002a766  lea     rcx, ?EnumUILanguagesProc@LANG_STRING@@CAHPEAG_J@Z; lpUILanguageEnumProc
0x18002a76d  call    cs:__imp_EnumUILanguagesW
0x18002a773  test    eax, eax
0x18002a775  jz      loc_18002A6B9
0x18002a77b  mov     ebx, dword ptr [rsp+1B0h+lParam+8]
0x18002a77f  test    ebx, ebx
0x18002a781  js      loc_18002A82F
0x18002a787  mov     eax, dword ptr [rsp+1B0h+lParam+4]
0x18002a78b  mov     [rsi+28h], eax
0x18002a78e  mov     rax, [rsp+1B0h+Block]
0x18002a793  mov     [rsi+20h], rax
0x18002a797  mov     [rsp+1B0h+Block], r12
0x18002a79c  call    cs:__imp_GetSystemDefaultUILanguage
0x18002a7a2  xor     r9d, r9d; dwFlags
0x18002a7a5  movzx   ecx, ax; Locale
0x18002a7a8  lea     rdx, [rbp+0B0h+Name]; lpName
0x18002a7ac  lea     r8d, [r9+64h]; cchName
0x18002a7b0  call    cs:__imp_LCIDToLocaleName
0x18002a7b6  test    eax, eax
0x18002a7b8  jz      loc_18002A6B9
0x18002a7be  lea     rdx, [rbp+0B0h+Name]; unsigned __int16 *
0x18002a7c2  lea     rcx, [rsp+1B0h+var_178]; this
0x18002a7c7  call    ?CopyWTruncate@STRA@@QEAAJPEBG@Z; STRA::CopyWTruncate(ushort const *)
0x18002a7cc  mov     ebx, eax
0x18002a7ce  test    eax, eax
0x18002a7d0  js      short loc_18002A82F
0x18002a7d2  mov     rdx, [rsi+20h]
0x18002a7d6  mov     rcx, [rsp+1B0h+String1]; String1
0x18002a7db  mov     rdx, [rdx]; String2
0x18002a7de  call    cs:__imp__stricmp
0x18002a7e4  test    eax, eax
0x18002a7e6  jz      short loc_18002A825
0x18002a7e8  mov     edi, r15d
0x18002a7eb  cmp     edi, [rsi+28h]
0x18002a7ee  jnb     short loc_18002A82A
0x18002a7f0  mov     rdx, [rsi+20h]
0x18002a7f4  mov     rcx, [rsp+1B0h+String1]; String1
0x18002a7f9  mov     r14d, edi
0x18002a7fc  mov     rdx, [rdx+r14*8]; String2
0x18002a800  call    cs:__imp__stricmp
0x18002a806  test    eax, eax
0x18002a808  jz      short loc_18002A80F
0x18002a80a  add     edi, r15d
0x18002a80d  jmp     short loc_18002A7EB
0x18002a80f  mov     rcx, [rsi+20h]
0x18002a813  mov     rax, [rcx]
0x18002a816  mov     rdx, [rcx+r14*8]
0x18002a81a  mov     [rcx+r14*8], rax
0x18002a81e  mov     rax, [rsi+20h]
0x18002a822  mov     [rax], rdx
0x18002a825  mov     [rsi], r15d
0x18002a828  jmp     short loc_18002A82F
0x18002a82a  mov     ebx, 80070057h
0x18002a82f  mov     edi, 30h ; '0'
0x18002a834  mov     r14, rsi
0x18002a837  cmp     [rsp+1B0h+Block], r12
0x18002a83c  jz      short loc_18002A88A
0x18002a83e  mov     edx, dword ptr [rsp+1B0h+lParam+4]
0x18002a842  mov     r15d, r12d
0x18002a845  test    edx, edx
0x18002a847  jz      short loc_18002A87B
0x18002a849  mov     rax, [rsp+1B0h+Block]
0x18002a84e  mov     r12d, r15d
0x18002a851  mov     rcx, [rax+r12*8]; Block
0x18002a855  test    rcx, rcx
0x18002a858  jz      short loc_18002A870
0x18002a85a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a85f  mov     rax, [rsp+1B0h+Block]
0x18002a864  mov     qword ptr [rax+r12*8], 0
0x18002a86c  mov     edx, dword ptr [rsp+1B0h+lParam+4]
0x18002a870  inc     r15d
0x18002a873  cmp     r15d, edx
0x18002a876  jb      short loc_18002A849
0x18002a878  xor     r12d, r12d
0x18002a87b  mov     rcx, [rsp+1B0h+Block]; Block
0x18002a880  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a885  mov     [rsp+1B0h+Block], r12
0x18002a88a  test    ebx, ebx
0x18002a88c  jns     short loc_18002A8AF
0x18002a88e  mov     rcx, [rsi+18h]; Block
0x18002a892  test    rcx, rcx
0x18002a895  jz      short loc_18002A8A0
0x18002a897  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002a89c  mov     [rsi+18h], r12
0x18002a8a0  test    r13d, r13d
0x18002a8a3  jz      short loc_18002A8AF
0x18002a8a5  lea     rcx, [rdi+r14]; lpCriticalSection
0x18002a8a9  call    cs:__imp_DeleteCriticalSection
0x18002a8af  lea     rcx, [rsp+1B0h+var_178]; this
0x18002a8b4  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18002a8b9  mov     eax, ebx
0x18002a8bb  mov     rcx, [rbp+0B0h+var_50]
0x18002a8bf  xor     rcx, rsp; StackCookie
0x18002a8c2  call    __security_check_cookie
0x18002a8c7  add     rsp, 178h
0x18002a8ce  pop     r15
0x18002a8d0  pop     r14
0x18002a8d2  pop     r13
0x18002a8d4  pop     r12
0x18002a8d6  pop     rdi
0x18002a8d7  pop     rsi
0x18002a8d8  pop     rbx
0x18002a8d9  pop     rbp
0x18002a8da  retn
```
