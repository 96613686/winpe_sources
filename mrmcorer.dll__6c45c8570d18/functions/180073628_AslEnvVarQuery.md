# AslEnvVarQuery

- ea: `0x180073628`
- end: `0x180073850`
- name: `AslEnvVarQuery`
- size: `552`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180073454`

## callees

- `0x180073628`
- `0x180086e68`
- `0x180088d45`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800736a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800736a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800736cd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800736cd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800736bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800736bb`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18007374b`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180073757`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18007374b`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180073757`

## string_xrefs

- `0x180073691`: `ntdll.dll`

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
  __int64 result; // rax
  __int64 v11; // rsi
  HMODULE Library; // rax
  HMODULE v13; // rbx
  __int64 (*ProcAddress)(void); // rax
  unsigned __int64 v15; // rdi
  WCHAR *v16; // rbp
  WCHAR *v17; // r13
  WCHAR *v18; // r15
  WCHAR v19; // bx
  WCHAR v20; // di
  int v21; // edx
  WCHAR *v22; // rcx
  unsigned __int64 v23; // rsi
  WCHAR v24; // ax

  if ( a3 < 0xA || wcsnicmp(a2, L"systemroot", 0xAu) )
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
LABEL_22:
        if ( v18 == v16 && *a1 == 61 )
        {
          v21 = 1;
          goto LABEL_25;
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
          goto LABEL_22;
        }
      }
      v24 = *a1;
      if ( !*a1 )
        goto LABEL_32;
      do
      {
        if ( v24 == 61 && a1 != v17 )
          break;
        v24 = *++a1;
      }
      while ( *a1 );
      if ( !*a1 )
        goto LABEL_32;
      v21 = 0;
LABEL_25:
      v22 = a1;
      do
      {
        if ( (__int64)(((char *)a1 - (char *)v22) & 0xFFFFFFFFFFFFFFFEuLL) >= 65534 )
          break;
        ++a1;
      }
      while ( *a1 );
      if ( v21 )
      {
        v23 = a1 - (v22 + 1);
        if ( v23 >= a5 )
        {
          if ( a4 )
          {
            if ( a5 )
              *a4 = 0;
          }
          result = 3221225507LL;
          ++v23;
        }
        else
        {
          memcpy_0(a4, v22 + 1, 2 * v23);
          a4[v23] = 0;
          result = 0;
        }
        *a6 = v23;
        return result;
      }
LABEL_32:
      ++a1;
    }
  }
  v11 = (__int64)Src;
  if ( !Src )
  {
    v11 = 2147352624;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v13 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
      if ( ProcAddress )
        v11 = ProcAddress();
      FreeLibrary(v13);
    }
    Src = (void *)v11;
  }
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(v11 + 2 * v15) );
  if ( v15 >= a5 )
  {
    if ( a4 && a5 )
      *a4 = 0;
    result = 3221225507LL;
    ++v15;
  }
  else
  {
    memcpy_0(a4, (const void *)v11, 2 * v15);
    a4[v15] = 0;
    result = 0;
  }
  *a6 = v15;
  return result;
}

```

## disassembly

```asm
0x180073628  push    rbx
0x18007362a  push    rbp
0x18007362b  push    rsi
0x18007362c  push    rdi
0x18007362d  push    r12
0x18007362f  push    r13
0x180073631  push    r14
0x180073633  push    r15
0x180073635  sub     rsp, 28h
0x180073639  xor     r15d, r15d
0x18007363c  mov     rbx, r8
0x18007363f  mov     r14, r9
0x180073642  mov     r12, rdx
0x180073645  mov     rsi, rcx
0x180073648  lea     r8d, [r15+0Ah]; MaxCount
0x18007364c  cmp     rbx, r8
0x18007364f  jnb     short loc_180073670
0x180073651  test    rsi, rsi
0x180073654  jnz     loc_180073720
0x18007365a  mov     eax, 0C0000100h
0x18007365f  add     rsp, 28h
0x180073663  pop     r15
0x180073665  pop     r14
0x180073667  pop     r13
0x180073669  pop     r12
0x18007366b  pop     rdi
0x18007366c  pop     rsi
0x18007366d  pop     rbp
0x18007366e  pop     rbx
0x18007366f  retn
0x180073670  lea     rdx, aSystemroot_1; "systemroot"
0x180073677  mov     rcx, r12; String1
0x18007367a  call    _wcsnicmp
0x18007367f  test    eax, eax
0x180073681  jnz     short loc_180073651
0x180073683  mov     rsi, cs:Src
0x18007368a  test    rsi, rsi
0x18007368d  jnz     short loc_1800736DA
0x18007368f  xor     edx, edx; hFile
0x180073691  lea     rcx, ModuleName; "ntdll.dll"
0x180073698  mov     r8d, 800h; dwFlags
0x18007369e  mov     esi, 7FFE0030h
0x1800736a3  call    cs:__imp_LoadLibraryExW
0x1800736a9  mov     rbx, rax
0x1800736ac  test    rax, rax
0x1800736af  jz      short loc_1800736D3
0x1800736b1  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x1800736b8  mov     rcx, rax; hModule
0x1800736bb  call    cs:__imp_GetProcAddress
0x1800736c1  test    rax, rax
0x1800736c4  jnz     loc_1800737F1
0x1800736ca  mov     rcx, rbx; hLibModule
0x1800736cd  call    cs:__imp_FreeLibrary
0x1800736d3  mov     cs:Src, rsi
0x1800736da  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800736de  inc     rdi
0x1800736e1  cmp     [rsi+rdi*2], r15w
0x1800736e6  jnz     short loc_1800736DE
0x1800736e8  cmp     rdi, [rsp+68h+arg_20]
0x1800736f0  jnb     loc_1800737FE
0x1800736f6  lea     rbx, [rdi+rdi]
0x1800736fa  mov     rdx, rsi; Src
0x1800736fd  mov     r8, rbx; Size
0x180073700  mov     rcx, r14; void *
0x180073703  call    memcpy_0
0x180073708  mov     [rbx+r14], r15w
0x18007370d  mov     eax, r15d
0x180073710  mov     rcx, [rsp+68h+arg_28]
0x180073718  mov     [rcx], rdi
0x18007371b  jmp     loc_18007365F
0x180073720  lea     rbp, [r12+rbx*2]
0x180073724  cmp     [rsi], r15w
0x180073728  jz      loc_18007365A
0x18007372e  mov     r13, rsi
0x180073731  mov     r15, r12
0x180073734  cmp     r12, rbp
0x180073737  jnb     short loc_18007376F
0x180073739  xor     eax, eax
0x18007373b  cmp     [rsi], ax
0x18007373e  jz      loc_18007381F
0x180073744  movzx   ecx, word ptr [r15]; Source
0x180073748  movzx   ebx, word ptr [rsi]
0x18007374b  call    cs:__imp_RtlUpcaseUnicodeChar
0x180073751  movzx   ecx, bx; Source
0x180073754  movzx   edi, ax
0x180073757  call    cs:__imp_RtlUpcaseUnicodeChar
0x18007375d  cmp     ax, di
0x180073760  jnz     short loc_18007376F
0x180073762  add     rsi, 2
0x180073766  add     r15, 2
0x18007376a  cmp     r15, rbp
0x18007376d  jb      short loc_180073739
0x18007376f  cmp     r15, rbp
0x180073772  jnz     loc_18007381F
0x180073778  cmp     word ptr [rsi], 3Dh ; '='
0x18007377c  jnz     loc_18007381F
0x180073782  mov     edx, 1
0x180073787  xor     r15d, r15d
0x18007378a  mov     rcx, rsi
0x18007378d  mov     rax, rsi
0x180073790  sub     rax, rcx
0x180073793  and     rax, 0FFFFFFFFFFFFFFFEh
0x180073797  cmp     rax, 0FFFEh
0x18007379d  jge     short loc_1800737A9
0x18007379f  add     rsi, 2
0x1800737a3  cmp     [rsi], r15w
0x1800737a7  jnz     short loc_18007378D
0x1800737a9  test    edx, edx
0x1800737ab  jz      short loc_1800737E8
0x1800737ad  mov     rdi, [rsp+68h+arg_28]
0x1800737b5  lea     rdx, [rcx+2]; Src
0x1800737b9  sub     rsi, rdx
0x1800737bc  sar     rsi, 1
0x1800737bf  cmp     rsi, [rsp+68h+arg_20]
0x1800737c7  jnb     short loc_18007382F
0x1800737c9  lea     rbx, [rsi+rsi]
0x1800737cd  mov     rcx, r14; void *
0x1800737d0  mov     r8, rbx; Size
0x1800737d3  call    memcpy_0
0x1800737d8  mov     [rbx+r14], r15w
0x1800737dd  mov     eax, r15d
0x1800737e0  mov     [rdi], rsi
0x1800737e3  jmp     loc_18007365F
0x1800737e8  add     rsi, 2
0x1800737ec  jmp     loc_180073724
0x1800737f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800737f6  mov     rsi, rax
0x1800737f9  jmp     loc_1800736CA
0x1800737fe  test    r14, r14
0x180073801  jz      loc_1800C47A8
0x180073807  cmp     [rsp+68h+arg_20], 1
0x180073810  jb      loc_1800C47A8
0x180073816  mov     [r14], r15w
0x18007381a  jmp     loc_1800C47A8
0x18007381f  movzx   eax, word ptr [rsi]
0x180073822  xor     r15d, r15d
0x180073825  test    ax, ax
0x180073828  jz      short loc_1800737E8
0x18007382a  jmp     loc_1800C47B5
0x18007382f  test    r14, r14
0x180073832  jz      loc_1800C47DE
0x180073838  cmp     [rsp+68h+arg_20], 1
0x180073841  jb      loc_1800C47DE
0x180073847  mov     [r14], r15w
0x18007384b  jmp     loc_1800C47DE
0x1800c47a8  mov     eax, 0C0000023h
0x1800c47ad  inc     rdi
0x1800c47b0  jmp     loc_180073710
0x1800c47b5  cmp     ax, 3Dh ; '='
0x1800c47b9  jnz     short loc_1800C47C0
0x1800c47bb  cmp     rsi, r13
0x1800c47be  jnz     short loc_1800C47CC
0x1800c47c0  add     rsi, 2
0x1800c47c4  movzx   eax, word ptr [rsi]
0x1800c47c7  test    ax, ax
0x1800c47ca  jnz     short loc_1800C47B5
0x1800c47cc  cmp     [rsi], r15w
0x1800c47d0  jz      loc_1800737E8
0x1800c47d6  mov     edx, r15d
0x1800c47d9  jmp     loc_18007378A
0x1800c47de  mov     eax, 0C0000023h
0x1800c47e3  inc     rsi
0x1800c47e6  jmp     loc_1800737E0
```
