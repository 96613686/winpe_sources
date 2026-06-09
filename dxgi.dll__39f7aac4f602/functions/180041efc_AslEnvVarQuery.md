# AslEnvVarQuery

- ea: `0x180041efc`
- end: `0x180042127`
- name: `AslEnvVarQuery`
- size: `555`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180041d58`
- `0x1800bd32c`

## callees

- `0x180041efc`
- `0x180076e9c`
- `0x180076f08`
- `0x1800cb010`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x18004202b`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180042037`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18004202b`
- `ntdll!RtlUpcaseUnicodeChar` at `0x180042037`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041f78`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180041f78`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041f60`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041f60`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180041f8e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180041f8e`

## string_xrefs

- `0x180041f4e`: `ntdll.dll`

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
0x180041efc  push    rbx
0x180041efe  push    rbp
0x180041eff  push    rsi
0x180041f00  push    rdi
0x180041f01  push    r12
0x180041f03  push    r13
0x180041f05  push    r14
0x180041f07  push    r15
0x180041f09  sub     rsp, 28h
0x180041f0d  xor     r15d, r15d
0x180041f10  mov     rbx, r8
0x180041f13  mov     r14, r9
0x180041f16  mov     r12, rdx
0x180041f19  mov     rsi, rcx
0x180041f1c  lea     r8d, [r15+0Ah]; MaxCount
0x180041f20  cmp     rbx, r8
0x180041f23  jb      loc_180041FFB
0x180041f29  lea     rdx, aSystemroot_3; "systemroot"
0x180041f30  mov     rcx, r12; String1
0x180041f33  call    _wcsnicmp
0x180041f38  test    eax, eax
0x180041f3a  jnz     loc_180041FFB
0x180041f40  mov     rsi, cs:Src
0x180041f47  test    rsi, rsi
0x180041f4a  jnz     short loc_180041F9B
0x180041f4c  xor     edx, edx; hFile
0x180041f4e  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180041f55  mov     r8d, 800h; dwFlags
0x180041f5b  mov     esi, 7FFE0030h
0x180041f60  call    cs:__imp_LoadLibraryExW
0x180041f66  mov     rbx, rax
0x180041f69  test    rax, rax
0x180041f6c  jz      short loc_180041F94
0x180041f6e  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x180041f75  mov     rcx, rax; hModule
0x180041f78  call    cs:__imp_GetProcAddress
0x180041f7e  test    rax, rax
0x180041f81  jz      short loc_180041F8B
0x180041f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f88  mov     rsi, rax
0x180041f8b  mov     rcx, rbx; hLibModule
0x180041f8e  call    cs:__imp_FreeLibrary
0x180041f94  mov     cs:Src, rsi
0x180041f9b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180041f9f  inc     rdi
0x180041fa2  cmp     [rsi+rdi*2], r15w
0x180041fa7  jnz     short loc_180041F9F
0x180041fa9  cmp     rdi, [rsp+68h+arg_20]
0x180041fb1  jb      short loc_180041FD1
0x180041fb3  test    r14, r14
0x180041fb6  jz      short loc_180041FC7
0x180041fb8  cmp     [rsp+68h+arg_20], 1
0x180041fc1  jb      short loc_180041FC7
0x180041fc3  mov     [r14], r15w
0x180041fc7  mov     eax, 0C0000023h
0x180041fcc  inc     rdi
0x180041fcf  jmp     short loc_180041FEB
0x180041fd1  lea     rbx, [rdi+rdi]
0x180041fd5  mov     rdx, rsi; Src
0x180041fd8  mov     r8, rbx; Size
0x180041fdb  mov     rcx, r14; void *
0x180041fde  call    memcpy_0
0x180041fe3  mov     [rbx+r14], r15w
0x180041fe8  mov     eax, r15d
0x180041feb  mov     rcx, [rsp+68h+arg_28]
0x180041ff3  mov     [rcx], rdi
0x180041ff6  jmp     loc_180042116
0x180041ffb  test    rsi, rsi
0x180041ffe  jz      loc_180042111
0x180042004  lea     rbp, [r12+rbx*2]
0x180042008  cmp     [rsi], r15w
0x18004200c  jz      loc_180042111
0x180042012  mov     r13, rsi
0x180042015  mov     r15, r12
0x180042018  cmp     r12, rbp
0x18004201b  jnb     short loc_18004204F
0x18004201d  xor     eax, eax
0x18004201f  cmp     [rsi], ax
0x180042022  jz      short loc_180042064
0x180042024  movzx   ecx, word ptr [r15]; Source
0x180042028  movzx   ebx, word ptr [rsi]
0x18004202b  call    cs:__imp_RtlUpcaseUnicodeChar
0x180042031  movzx   ecx, bx; Source
0x180042034  movzx   edi, ax
0x180042037  call    cs:__imp_RtlUpcaseUnicodeChar
0x18004203d  cmp     ax, di
0x180042040  jnz     short loc_18004204F
0x180042042  add     rsi, 2
0x180042046  add     r15, 2
0x18004204a  cmp     r15, rbp
0x18004204d  jb      short loc_18004201D
0x18004204f  cmp     r15, rbp
0x180042052  jnz     short loc_180042064
0x180042054  cmp     word ptr [rsi], 3Dh ; '='
0x180042058  jnz     short loc_180042064
0x18004205a  mov     edx, 1
0x18004205f  xor     r15d, r15d
0x180042062  jmp     short loc_18004208F
0x180042064  movzx   eax, word ptr [rsi]
0x180042067  xor     r15d, r15d
0x18004206a  test    ax, ax
0x18004206d  jz      short loc_1800420B2
0x18004206f  cmp     ax, 3Dh ; '='
0x180042073  jnz     short loc_18004207A
0x180042075  cmp     rsi, r13
0x180042078  jnz     short loc_180042086
0x18004207a  add     rsi, 2
0x18004207e  movzx   eax, word ptr [rsi]
0x180042081  test    ax, ax
0x180042084  jnz     short loc_18004206F
0x180042086  cmp     [rsi], r15w
0x18004208a  jz      short loc_1800420B2
0x18004208c  mov     edx, r15d
0x18004208f  mov     rcx, rsi
0x180042092  mov     rax, rsi
0x180042095  sub     rax, rcx
0x180042098  and     rax, 0FFFFFFFFFFFFFFFEh
0x18004209c  cmp     rax, 0FFFEh
0x1800420a2  jge     short loc_1800420AE
0x1800420a4  add     rsi, 2
0x1800420a8  cmp     [rsi], r15w
0x1800420ac  jnz     short loc_180042092
0x1800420ae  test    edx, edx
0x1800420b0  jnz     short loc_1800420BB
0x1800420b2  add     rsi, 2
0x1800420b6  jmp     loc_180042008
0x1800420bb  mov     rdi, [rsp+68h+arg_28]
0x1800420c3  lea     rdx, [rcx+2]; Src
0x1800420c7  sub     rsi, rdx
0x1800420ca  sar     rsi, 1
0x1800420cd  cmp     rsi, [rsp+68h+arg_20]
0x1800420d5  jb      short loc_1800420F5
0x1800420d7  test    r14, r14
0x1800420da  jz      short loc_1800420EB
0x1800420dc  cmp     [rsp+68h+arg_20], 1
0x1800420e5  jb      short loc_1800420EB
0x1800420e7  mov     [r14], r15w
0x1800420eb  mov     eax, 0C0000023h
0x1800420f0  inc     rsi
0x1800420f3  jmp     short loc_18004210C
0x1800420f5  lea     rbx, [rsi+rsi]
0x1800420f9  mov     rcx, r14; void *
0x1800420fc  mov     r8, rbx; Size
0x1800420ff  call    memcpy_0
0x180042104  mov     [rbx+r14], r15w
0x180042109  mov     eax, r15d
0x18004210c  mov     [rdi], rsi
0x18004210f  jmp     short loc_180042116
0x180042111  mov     eax, 0C0000100h
0x180042116  add     rsp, 28h
0x18004211a  pop     r15
0x18004211c  pop     r14
0x18004211e  pop     r13
0x180042120  pop     r12
0x180042122  pop     rdi
0x180042123  pop     rsi
0x180042124  pop     rbp
0x180042125  pop     rbx
0x180042126  retn
```
