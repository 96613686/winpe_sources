# DetourFindFunction

- ea: `0x180077540`
- end: `0x180077709`
- name: `DetourFindFunction`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800734e8`

## callees

- `0x180075fa0`
- `0x180076f20`
- `0x180077060`
- `0x1800773e0`
- `0x180077540`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077584`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180077584`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18007756c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18007756c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800775ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800775ca`

## pseudocode

```c
FARPROC __fastcall DetourFindFunction(const CHAR *a1, const CHAR *a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rdi
  FARPROC result; // rax
  struct _DETOUR_SYM_INFO *ImageHlp; // rax
  struct _DETOUR_SYM_INFO *v8; // rbx
  __int64 v9; // rax
  char *v10; // r8
  __int64 v11; // rcx
  char *v12; // rdx
  char *v13; // rax
  _DWORD v14[14]; // [rsp+40h] [rbp-B18h] BYREF
  __int64 v15; // [rsp+78h] [rbp-AE0h]
  int v16; // [rsp+90h] [rbp-AC8h]
  int v17; // [rsp+2A0h] [rbp-8B8h] BYREF
  char v18[32]; // [rsp+2A4h] [rbp-8B4h] BYREF
  char v19; // [rsp+2C4h] [rbp-894h] BYREF
  char v20[512]; // [rsp+930h] [rbp-228h] BYREF

  Library = LoadLibraryExA(a1, 0, 0);
  v5 = Library;
  if ( !Library )
    return 0;
  result = GetProcAddress(Library, a2);
  if ( result )
    return result;
  ImageHlp = DetourLoadImageHlp();
  v8 = ImageHlp;
  if ( !ImageHlp
    || !(*((__int64 (__fastcall **)(_QWORD, _QWORD, const CHAR *, _QWORD, HMODULE, _DWORD))ImageHlp + 6))(
          *(_QWORD *)ImageHlp,
          0,
          a1,
          0,
          v5,
          0)
    && GetLastError() )
  {
    return 0;
  }
  memset_0(v18, 0, 0x68Cu);
  v17 = 1680;
  if ( !(*((unsigned int (__fastcall **)(_QWORD, HMODULE, int *))v8 + 7))(*(_QWORD *)v8, v5, &v17) )
    return 0;
  v9 = 2147483646;
  v10 = &v19;
  v11 = 512;
  v12 = v20;
  do
  {
    if ( !v9 )
      break;
    if ( !*v10 )
      break;
    *v12++ = *v10++;
    --v9;
    --v11;
  }
  while ( v11 );
  v13 = v12 - 1;
  if ( v11 )
    v13 = v12;
  *v13 = 0;
  if ( v11
    && (int)StringCchCatA(v20, 0x200u, "!") >= 0
    && (int)StringCchCatA(v20, 0x200u, a2) >= 0
    && (memset_0(v14, 0, 0x258u),
        v14[0] = 88,
        v16 = 512,
        (*((unsigned int (__fastcall **)(_QWORD, char *, _DWORD *))v8 + 8))(*(_QWORD *)v8, v20, v14)) )
  {
    return (FARPROC)v15;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180077540  mov     [rsp+arg_10], rbx
0x180077545  push    rbp
0x180077546  push    rsi
0x180077547  push    rdi
0x180077548  sub     rsp, 0B40h
0x18007754f  mov     rax, cs:__security_cookie
0x180077556  xor     rax, rsp
0x180077559  mov     [rsp+0B58h+var_28], rax
0x180077561  mov     rbp, rdx
0x180077564  xor     r8d, r8d; dwFlags
0x180077567  xor     edx, edx; hFile
0x180077569  mov     rsi, rcx
0x18007756c  call    cs:__imp_LoadLibraryExA
0x180077572  mov     rdi, rax
0x180077575  test    rax, rax
0x180077578  jz      loc_1800776E4
0x18007757e  mov     rdx, rbp; lpProcName
0x180077581  mov     rcx, rax; hModule
0x180077584  call    cs:__imp_GetProcAddress
0x18007758a  test    rax, rax
0x18007758d  jnz     loc_1800776E6
0x180077593  call    ?DetourLoadImageHlp@@YAPEAU_DETOUR_SYM_INFO@@XZ; DetourLoadImageHlp(void)
0x180077598  mov     rbx, rax
0x18007759b  test    rax, rax
0x18007759e  jz      loc_1800776E4
0x1800775a4  mov     rcx, [rax]
0x1800775a7  xor     r9d, r9d
0x1800775aa  mov     rax, [rax+30h]
0x1800775ae  mov     r8, rsi
0x1800775b1  mov     [rsp+0B58h+var_B30], 0
0x1800775b9  xor     edx, edx
0x1800775bb  mov     [rsp+0B58h+var_B38], rdi
0x1800775c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775c5  test    rax, rax
0x1800775c8  jnz     short loc_1800775D8
0x1800775ca  call    cs:__imp_GetLastError
0x1800775d0  test    eax, eax
0x1800775d2  jnz     loc_1800776E4
0x1800775d8  xor     edx, edx; Val
0x1800775da  lea     rcx, [rsp+0B58h+var_8B4]; void *
0x1800775e2  mov     r8d, 68Ch; Size
0x1800775e8  call    memset_0
0x1800775ed  mov     [rsp+0B58h+var_8B8], 690h
0x1800775f8  lea     r8, [rsp+0B58h+var_8B8]
0x180077600  mov     rcx, [rbx]
0x180077603  mov     rdx, rdi
0x180077606  mov     rax, [rbx+38h]
0x18007760a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007760f  test    eax, eax
0x180077611  jz      loc_1800776E4
0x180077617  mov     eax, 7FFFFFFEh
0x18007761c  lea     r8, [rsp+0B58h+var_894]
0x180077624  mov     ecx, 200h
0x180077629  lea     rdx, [rsp+0B58h+var_228]
0x180077631  test    rax, rax
0x180077634  jz      short loc_180077651
0x180077636  movzx   r9d, byte ptr [r8]
0x18007763a  test    r9b, r9b
0x18007763d  jz      short loc_180077651
0x18007763f  mov     [rdx], r9b
0x180077642  inc     r8
0x180077645  inc     rdx
0x180077648  dec     rax
0x18007764b  sub     rcx, 1
0x18007764f  jnz     short loc_180077631
0x180077651  test    rcx, rcx
0x180077654  lea     rax, [rdx-1]
0x180077658  cmovnz  rax, rdx
0x18007765c  mov     byte ptr [rax], 0
0x18007765f  jz      loc_1800776E4
0x180077665  lea     r8, asc_1800DA7EC; "!"
0x18007766c  mov     edx, 200h; unsigned __int64
0x180077671  lea     rcx, [rsp+0B58h+var_228]; char *
0x180077679  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18007767e  test    eax, eax
0x180077680  js      short loc_1800776E4
0x180077682  mov     r8, rbp; char *
0x180077685  lea     rcx, [rsp+0B58h+var_228]; char *
0x18007768d  mov     edx, 200h; unsigned __int64
0x180077692  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180077697  test    eax, eax
0x180077699  js      short loc_1800776E4
0x18007769b  xor     edx, edx; Val
0x18007769d  lea     rcx, [rsp+0B58h+var_B18]; void *
0x1800776a2  mov     r8d, 258h; Size
0x1800776a8  call    memset_0
0x1800776ad  mov     [rsp+0B58h+var_B18], 58h ; 'X'
0x1800776b5  lea     r8, [rsp+0B58h+var_B18]
0x1800776ba  mov     [rsp+0B58h+var_AC8], 200h
0x1800776c5  lea     rdx, [rsp+0B58h+var_228]
0x1800776cd  mov     rcx, [rbx]
0x1800776d0  mov     rax, [rbx+40h]
0x1800776d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800776d9  test    eax, eax
0x1800776db  jz      short loc_1800776E4
0x1800776dd  mov     rax, [rsp+0B58h+var_AE0]
0x1800776e2  jmp     short loc_1800776E6
0x1800776e4  xor     eax, eax
0x1800776e6  mov     rcx, [rsp+0B58h+var_28]
0x1800776ee  xor     rcx, rsp; StackCookie
0x1800776f1  call    __security_check_cookie
0x1800776f6  mov     rbx, [rsp+0B58h+arg_10]
0x1800776fe  add     rsp, 0B40h
0x180077705  pop     rdi
0x180077706  pop     rsi
0x180077707  pop     rbp
0x180077708  retn
```
