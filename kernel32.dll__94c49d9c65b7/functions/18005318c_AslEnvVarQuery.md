# AslEnvVarQuery

- ea: `0x18005318c`
- end: `0x1800533b7`
- name: `AslEnvVarQuery`
- size: `555`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180045cf8`
- `0x180052ff8`

## callees

- `0x18005318c`
- `0x18005c414`
- `0x18007a7d1`
- `0x18007c010`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x1800532bb`
- `ntdll!RtlUpcaseUnicodeChar` at `0x1800532c7`
- `ntdll!RtlUpcaseUnicodeChar` at `0x1800532bb`
- `ntdll!RtlUpcaseUnicodeChar` at `0x1800532c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053208`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053208`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005321e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005321e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800531f0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800531f0`

## string_xrefs

- `0x1800531de`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall AslEnvVarQuery(
        WCHAR *a1,
        const wchar_t *a2,
        unsigned __int64 a3,
        _WORD *a4,
        unsigned __int64 a5,
        unsigned __int64 *a6)
{
  __int64 v10; // rsi
  HMODULE Library; // rax
  HMODULE v12; // rbx
  __int64 (*ProcAddress)(void); // rax
  unsigned __int64 v14; // rdi
  __int64 result; // rax
  WCHAR *v16; // rbp
  WCHAR *v17; // r13
  WCHAR *v18; // r15
  WCHAR v19; // bx
  WCHAR v20; // di
  int v21; // edx
  WCHAR v22; // ax
  WCHAR *v23; // rcx
  unsigned __int64 v24; // rsi

  if ( a3 < 0xA || wcsnicmp_0(a2, L"systemroot", 0xAu) )
  {
    if ( !a1 )
      return 3221225728LL;
    v16 = (WCHAR *)&a2[a3];
    while ( 1 )
    {
      if ( !*a1 )
        return 3221225728LL;
      v17 = a1;
      v18 = (WCHAR *)a2;
      if ( a2 >= v16 )
      {
LABEL_25:
        if ( v18 == v16 && *a1 == 61 )
        {
          v21 = 1;
          goto LABEL_34;
        }
      }
      else
      {
        while ( *a1 )
        {
          v19 = *a1;
          v20 = RtlUpcaseUnicodeChar(*v18);
          if ( RtlUpcaseUnicodeChar(v19) == v20 )
          {
            ++a1;
            if ( ++v18 < v16 )
              continue;
          }
          goto LABEL_25;
        }
      }
      v22 = *a1;
      if ( !*a1 )
        goto LABEL_38;
      do
      {
        if ( v22 == 61 && a1 != v17 )
          break;
        v22 = *++a1;
      }
      while ( *a1 );
      if ( !*a1 )
        goto LABEL_38;
      v21 = 0;
LABEL_34:
      v23 = a1;
      do
      {
        if ( (__int64)(((char *)a1 - (char *)v23) & 0xFFFFFFFFFFFFFFFEuLL) >= 65534 )
          break;
        ++a1;
      }
      while ( *a1 );
      if ( v21 )
      {
        v24 = a1 - (v23 + 1);
        if ( v24 < a5 )
        {
          memcpy_0(a4, v23 + 1, 2 * v24);
          a4[v24] = 0;
          result = 0;
        }
        else
        {
          if ( a4 && a5 )
            *a4 = 0;
          result = 3221225507LL;
          ++v24;
        }
        *a6 = v24;
        return result;
      }
LABEL_38:
      ++a1;
    }
  }
  v10 = (__int64)Src;
  if ( !Src )
  {
    v10 = 2147352624;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v12 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
      if ( ProcAddress )
        v10 = ProcAddress();
      FreeLibrary(v12);
    }
    Src = (wchar_t *)v10;
  }
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(v10 + 2 * v14) );
  if ( v14 < a5 )
  {
    memcpy_0(a4, (const void *)v10, 2 * v14);
    a4[v14] = 0;
    result = 0;
  }
  else
  {
    if ( a4 )
    {
      if ( a5 )
        *a4 = 0;
    }
    result = 3221225507LL;
    ++v14;
  }
  *a6 = v14;
  return result;
}

```

## disassembly

```asm
0x18005318c  push    rbx
0x18005318e  push    rbp
0x18005318f  push    rsi
0x180053190  push    rdi
0x180053191  push    r12
0x180053193  push    r13
0x180053195  push    r14
0x180053197  push    r15
0x180053199  sub     rsp, 28h
0x18005319d  xor     r15d, r15d
0x1800531a0  mov     rbx, r8
0x1800531a3  mov     r14, r9
0x1800531a6  mov     r12, rdx
0x1800531a9  mov     rsi, rcx
0x1800531ac  lea     r8d, [r15+0Ah]; MaxCount
0x1800531b0  cmp     rbx, r8
0x1800531b3  jb      loc_18005328B
0x1800531b9  lea     rdx, aSystemroot_2; "systemroot"
0x1800531c0  mov     rcx, r12; String1
0x1800531c3  call    _wcsnicmp_0
0x1800531c8  test    eax, eax
0x1800531ca  jnz     loc_18005328B
0x1800531d0  mov     rsi, cs:Src
0x1800531d7  test    rsi, rsi
0x1800531da  jnz     short loc_18005322B
0x1800531dc  xor     edx, edx; hFile
0x1800531de  lea     rcx, ModuleName; "ntdll.dll"
0x1800531e5  mov     r8d, 800h; dwFlags
0x1800531eb  mov     esi, 7FFE0030h
0x1800531f0  call    cs:__imp_LoadLibraryExW
0x1800531f6  mov     rbx, rax
0x1800531f9  test    rax, rax
0x1800531fc  jz      short loc_180053224
0x1800531fe  lea     rdx, ProcName; "RtlGetNtSystemRoot"
0x180053205  mov     rcx, rax; hModule
0x180053208  call    cs:__imp_GetProcAddress
0x18005320e  test    rax, rax
0x180053211  jz      short loc_18005321B
0x180053213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053218  mov     rsi, rax
0x18005321b  mov     rcx, rbx; hLibModule
0x18005321e  call    cs:__imp_FreeLibrary
0x180053224  mov     cs:Src, rsi
0x18005322b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005322f  inc     rdi
0x180053232  cmp     [rsi+rdi*2], r15w
0x180053237  jnz     short loc_18005322F
0x180053239  cmp     rdi, [rsp+68h+arg_20]
0x180053241  jb      short loc_180053261
0x180053243  test    r14, r14
0x180053246  jz      short loc_180053257
0x180053248  cmp     [rsp+68h+arg_20], 1
0x180053251  jb      short loc_180053257
0x180053253  mov     [r14], r15w
0x180053257  mov     eax, 0C0000023h
0x18005325c  inc     rdi
0x18005325f  jmp     short loc_18005327B
0x180053261  lea     rbx, [rdi+rdi]
0x180053265  mov     rdx, rsi; Src
0x180053268  mov     r8, rbx; Size
0x18005326b  mov     rcx, r14; void *
0x18005326e  call    memcpy_0
0x180053273  mov     [rbx+r14], r15w
0x180053278  mov     eax, r15d
0x18005327b  mov     rcx, [rsp+68h+arg_28]
0x180053283  mov     [rcx], rdi
0x180053286  jmp     loc_1800533A6
0x18005328b  test    rsi, rsi
0x18005328e  jz      loc_1800533A1
0x180053294  lea     rbp, [r12+rbx*2]
0x180053298  cmp     [rsi], r15w
0x18005329c  jz      loc_1800533A1
0x1800532a2  mov     r13, rsi
0x1800532a5  mov     r15, r12
0x1800532a8  cmp     r12, rbp
0x1800532ab  jnb     short loc_1800532DF
0x1800532ad  xor     eax, eax
0x1800532af  cmp     [rsi], ax
0x1800532b2  jz      short loc_1800532F4
0x1800532b4  movzx   ecx, word ptr [r15]; Source
0x1800532b8  movzx   ebx, word ptr [rsi]
0x1800532bb  call    cs:__imp_RtlUpcaseUnicodeChar
0x1800532c1  movzx   ecx, bx; Source
0x1800532c4  movzx   edi, ax
0x1800532c7  call    cs:__imp_RtlUpcaseUnicodeChar
0x1800532cd  cmp     ax, di
0x1800532d0  jnz     short loc_1800532DF
0x1800532d2  add     rsi, 2
0x1800532d6  add     r15, 2
0x1800532da  cmp     r15, rbp
0x1800532dd  jb      short loc_1800532AD
0x1800532df  cmp     r15, rbp
0x1800532e2  jnz     short loc_1800532F4
0x1800532e4  cmp     word ptr [rsi], 3Dh ; '='
0x1800532e8  jnz     short loc_1800532F4
0x1800532ea  mov     edx, 1
0x1800532ef  xor     r15d, r15d
0x1800532f2  jmp     short loc_18005331F
0x1800532f4  movzx   eax, word ptr [rsi]
0x1800532f7  xor     r15d, r15d
0x1800532fa  test    ax, ax
0x1800532fd  jz      short loc_180053342
0x1800532ff  cmp     ax, 3Dh ; '='
0x180053303  jnz     short loc_18005330A
0x180053305  cmp     rsi, r13
0x180053308  jnz     short loc_180053316
0x18005330a  add     rsi, 2
0x18005330e  movzx   eax, word ptr [rsi]
0x180053311  test    ax, ax
0x180053314  jnz     short loc_1800532FF
0x180053316  cmp     [rsi], r15w
0x18005331a  jz      short loc_180053342
0x18005331c  mov     edx, r15d
0x18005331f  mov     rcx, rsi
0x180053322  mov     rax, rsi
0x180053325  sub     rax, rcx
0x180053328  and     rax, 0FFFFFFFFFFFFFFFEh
0x18005332c  cmp     rax, 0FFFEh
0x180053332  jge     short loc_18005333E
0x180053334  add     rsi, 2
0x180053338  cmp     [rsi], r15w
0x18005333c  jnz     short loc_180053322
0x18005333e  test    edx, edx
0x180053340  jnz     short loc_18005334B
0x180053342  add     rsi, 2
0x180053346  jmp     loc_180053298
0x18005334b  mov     rdi, [rsp+68h+arg_28]
0x180053353  lea     rdx, [rcx+2]; Src
0x180053357  sub     rsi, rdx
0x18005335a  sar     rsi, 1
0x18005335d  cmp     rsi, [rsp+68h+arg_20]
0x180053365  jb      short loc_180053385
0x180053367  test    r14, r14
0x18005336a  jz      short loc_18005337B
0x18005336c  cmp     [rsp+68h+arg_20], 1
0x180053375  jb      short loc_18005337B
0x180053377  mov     [r14], r15w
0x18005337b  mov     eax, 0C0000023h
0x180053380  inc     rsi
0x180053383  jmp     short loc_18005339C
0x180053385  lea     rbx, [rsi+rsi]
0x180053389  mov     rcx, r14; void *
0x18005338c  mov     r8, rbx; Size
0x18005338f  call    memcpy_0
0x180053394  mov     [rbx+r14], r15w
0x180053399  mov     eax, r15d
0x18005339c  mov     [rdi], rsi
0x18005339f  jmp     short loc_1800533A6
0x1800533a1  mov     eax, 0C0000100h
0x1800533a6  add     rsp, 28h
0x1800533aa  pop     r15
0x1800533ac  pop     r14
0x1800533ae  pop     r13
0x1800533b0  pop     r12
0x1800533b2  pop     rdi
0x1800533b3  pop     rsi
0x1800533b4  pop     rbp
0x1800533b5  pop     rbx
0x1800533b6  retn
```
