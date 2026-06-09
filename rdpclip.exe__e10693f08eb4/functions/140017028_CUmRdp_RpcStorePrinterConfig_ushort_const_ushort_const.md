# CUmRdp::RpcStorePrinterConfig(ushort const *,ushort const *)

- ea: `0x140017028`
- end: `0x140017165`
- name: `?RpcStorePrinterConfig@CUmRdp@@QEAAIPEBG0@Z`
- size: `317`
- prototype: `unsigned int __fastcall(CUmRdp *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140017840`

## callees

- `0x140008ce0`
- `0x140017028`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140017094`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140017094`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001712e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001712e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001707f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001707f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140017071`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140017071`

## string_xrefs

- `0x14001706a`: `printui.dll`

## pseudocode

```c
DWORD __fastcall CUmRdp::RpcStorePrinterConfig(CUmRdp *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v4; // rbx
  HMODULE LibraryW; // rax
  HMODULE v6; // rdi
  FARPROC ProcAddress; // rbp
  char *v9; // rdx
  unsigned __int16 v10; // ax
  int v11; // ebx
  _BYTE v12[1056]; // [rsp+30h] [rbp-AA8h] BYREF
  unsigned __int16 v13[816]; // [rsp+450h] [rbp-688h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 87;
  LibraryW = LoadLibraryW(L"printui.dll");
  v6 = LibraryW;
  if ( !LibraryW )
    return GetLastError();
  ProcAddress = GetProcAddress(LibraryW, "PrintUIEntryW");
  v9 = v12;
  while ( 1 )
  {
    v10 = *v4;
    if ( !*v4 )
      break;
    if ( v10 == 34 || v10 == 64 )
    {
      *(_WORD *)v9 = 92;
      v9 += 2;
    }
    *(_WORD *)v9 = v10;
    v9 += 2;
    ++v4;
    if ( (unsigned __int64)((v9 - v12) >> 1) >= 0x209 )
      return 234;
  }
  *(_WORD *)v9 = 0;
  StringCchPrintfW(v13, 0x32Bu, L"/q /Sr /n \"%ws\" /a \"%ws\" u r", v12, a3);
  v11 = ((__int64 (__fastcall *)(_QWORD, HMODULE, unsigned __int16 *, __int64))ProcAddress)(0, v6, v13, 1);
  FreeLibrary(v6);
  return v11;
}

```

## disassembly

```asm
0x140017028  mov     [rsp+arg_0], rbx
0x14001702d  mov     [rsp+arg_8], rbp
0x140017032  push    rsi
0x140017033  push    rdi
0x140017034  push    r14
0x140017036  sub     rsp, 0AC0h
0x14001703d  mov     rax, cs:__security_cookie
0x140017044  xor     rax, rsp
0x140017047  mov     [rsp+0AD8h+var_28], rax
0x14001704f  xor     r14d, r14d
0x140017052  mov     rsi, r8
0x140017055  mov     rbx, rdx
0x140017058  test    rdx, rdx
0x14001705b  jz      loc_140017138
0x140017061  test    r8, r8
0x140017064  jz      loc_140017138
0x14001706a  lea     rcx, LibFileName; "printui.dll"
0x140017071  call    cs:__imp_LoadLibraryW
0x140017077  mov     rdi, rax
0x14001707a  test    rax, rax
0x14001707d  jnz     short loc_14001708A
0x14001707f  call    cs:__imp_GetLastError
0x140017085  jmp     loc_14001713D
0x14001708a  lea     rdx, aPrintuientryw; "PrintUIEntryW"
0x140017091  mov     rcx, rdi; hModule
0x140017094  call    cs:__imp_GetProcAddress
0x14001709a  mov     rbp, rax
0x14001709d  lea     rdx, [rsp+0AD8h+var_AA8]
0x1400170a2  movzx   eax, word ptr [rbx]
0x1400170a5  test    ax, ax
0x1400170a8  jz      short loc_1400170E7
0x1400170aa  cmp     ax, 22h ; '"'
0x1400170ae  jz      short loc_1400170B6
0x1400170b0  cmp     ax, 40h ; '@'
0x1400170b4  jnz     short loc_1400170BF
0x1400170b6  mov     word ptr [rdx], 5Ch ; '\'
0x1400170bb  add     rdx, 2
0x1400170bf  mov     [rdx], ax
0x1400170c2  lea     rcx, [rsp+0AD8h+var_AA8]
0x1400170c7  add     rdx, 2
0x1400170cb  add     rbx, 2
0x1400170cf  mov     rax, rdx
0x1400170d2  sub     rax, rcx
0x1400170d5  sar     rax, 1
0x1400170d8  cmp     rax, 209h
0x1400170de  jb      short loc_1400170A2
0x1400170e0  mov     eax, 0EAh
0x1400170e5  jmp     short loc_14001713D
0x1400170e7  mov     [rdx], r14w
0x1400170eb  lea     r9, [rsp+0AD8h+var_AA8]
0x1400170f0  mov     edx, 32Bh; unsigned __int64
0x1400170f5  mov     [rsp+0AD8h+var_AB8], rsi
0x1400170fa  lea     r8, aQSrNWsAWsUR; "/q /Sr /n \"%ws\" /a \"%ws\" u r"
0x140017101  lea     rcx, [rsp+0AD8h+var_688]; unsigned __int16 *
0x140017109  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001710e  mov     r9d, 1
0x140017114  lea     r8, [rsp+0AD8h+var_688]
0x14001711c  mov     rdx, rdi
0x14001711f  xor     ecx, ecx
0x140017121  mov     rax, rbp
0x140017124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017129  mov     rcx, rdi; hLibModule
0x14001712c  mov     ebx, eax
0x14001712e  call    cs:__imp_FreeLibrary
0x140017134  mov     eax, ebx
0x140017136  jmp     short loc_14001713D
0x140017138  mov     eax, 57h ; 'W'
0x14001713d  mov     rcx, [rsp+0AD8h+var_28]
0x140017145  xor     rcx, rsp; StackCookie
0x140017148  call    __security_check_cookie
0x14001714d  lea     r11, [rsp+0AD8h+var_18]
0x140017155  mov     rbx, [r11+20h]
0x140017159  mov     rbp, [r11+28h]
0x14001715d  mov     rsp, r11
0x140017160  pop     r14
0x140017162  pop     rdi
0x140017163  pop     rsi
0x140017164  retn
```
