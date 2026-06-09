# CGeneralPage::_Browse(ushort * const,unsigned __int64)

- ea: `0x1800110c4`
- end: `0x18001127d`
- name: `?_Browse@CGeneralPage@@AEAAHQEAG_K@Z`
- size: `441`
- prototype: `__int64 __fastcall(CGeneralPage *__hidden this, unsigned __int16 *const, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011c90`

## callees

- `0x1800110c4`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001114a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180011166`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001119a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001114a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180011166`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001119a`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800111b1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800111b1`
- `COMDLG32!GetOpenFileNameW` at `0x180011248`
- `COMDLG32!GetOpenFileNameW` at `0x180011248`

## pseudocode

```c
_BOOL8 __fastcall CGeneralPage::_Browse(CGeneralPage *this, unsigned __int16 *const a2)
{
  __int64 v4; // rbx
  WCHAR *v5; // rax
  __int64 v6; // rbx
  tagOFNW *v7; // rax
  tagOFNW v9; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v11; // [rsp+C8h] [rbp-38h]
  WCHAR v12[104]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR v13[264]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR v14[264]; // [rsp+3B0h] [rbp+2B0h] BYREF

  *(_QWORD *)Buffer = 0;
  v4 = 520;
  v11 = 0;
  memset_0(v14, 0, 0x208u);
  memset_0(v13, 0, 0x208u);
  memset_0(v12, 0, 0xC8u);
  LoadStringW(g_hInstance, 0x100Eu, Buffer, 5);
  LoadStringW(g_hInstance, 0x1010u, v12, 100);
  v5 = v13;
  do
  {
    *(_BYTE *)v5 = 0;
    v5 = (WCHAR *)((char *)v5 + 1);
    --v4;
  }
  while ( v4 );
  if ( !LoadStringW(g_hInstance, 0x100Fu, v13, 260) )
    return 0;
  GetCurrentDirectoryW(0x104u, v14);
  v6 = 152;
  memset_0(&v9, 0, sizeof(v9));
  v7 = &v9;
  do
  {
    LOBYTE(v7->lStructSize) = 0;
    v7 = (tagOFNW *)((char *)v7 + 1);
    --v6;
  }
  while ( v6 );
  v9.lStructSize = 136;
  *a2 = 0;
  v9.hwndOwner = (HWND)*((_QWORD *)this + 14);
  v9.hInstance = g_hInstance;
  v9.lpstrFilter = v13;
  v9.lpstrInitialDir = v14;
  v9.lpstrTitle = v12;
  v9.lpstrDefExt = Buffer;
  v9.nFilterIndex = 1;
  v9.lpstrFile = a2;
  v9.nMaxFile = 261;
  v9.Flags = 4108;
  return GetOpenFileNameW(&v9);
}

```

## disassembly

```asm
0x1800110c4  mov     [rsp-8+arg_10], rbx
0x1800110c9  push    rbp
0x1800110ca  push    rsi
0x1800110cb  push    rdi
0x1800110cc  lea     rbp, [rsp-4D0h]
0x1800110d4  sub     rsp, 5D0h
0x1800110db  mov     rax, cs:__security_cookie
0x1800110e2  xor     rax, rsp
0x1800110e5  mov     [rbp+4E0h+var_20], rax
0x1800110ec  xor     eax, eax
0x1800110ee  mov     rdi, rdx
0x1800110f1  mov     rsi, rcx
0x1800110f4  mov     qword ptr [rbp+4E0h+Buffer], rax
0x1800110f8  mov     ebx, 208h
0x1800110fd  mov     [rbp+4E0h+var_518], ax
0x180011101  mov     r8d, ebx; Size
0x180011104  lea     rcx, [rbp+4E0h+var_230]; void *
0x18001110b  xor     edx, edx; Val
0x18001110d  call    memset_0
0x180011112  mov     r8d, ebx; Size
0x180011115  lea     rcx, [rbp+4E0h+var_440]; void *
0x18001111c  xor     edx, edx; Val
0x18001111e  call    memset_0
0x180011123  xor     edx, edx; Val
0x180011125  lea     rcx, [rbp+4E0h+var_510]; void *
0x180011129  mov     r8d, 0C8h; Size
0x18001112f  call    memset_0
0x180011134  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18001113b  lea     r8, [rbp+4E0h+Buffer]; lpBuffer
0x18001113f  mov     r9d, 5; cchBufferMax
0x180011145  mov     edx, 100Eh; uID
0x18001114a  call    cs:__imp_LoadStringW
0x180011150  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180011157  lea     r8, [rbp+4E0h+var_510]; lpBuffer
0x18001115b  mov     r9d, 64h ; 'd'; cchBufferMax
0x180011161  mov     edx, 1010h; uID
0x180011166  call    cs:__imp_LoadStringW
0x18001116c  lea     rax, [rbp+4E0h+var_440]
0x180011173  mov     byte ptr [rax], 0
0x180011176  inc     rax
0x180011179  sub     rbx, 1
0x18001117d  jnz     short loc_180011173
0x18001117f  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180011186  lea     r8, [rbp+4E0h+var_440]; lpBuffer
0x18001118d  mov     ebx, 104h
0x180011192  mov     edx, 100Fh; uID
0x180011197  mov     r9d, ebx; cchBufferMax
0x18001119a  call    cs:__imp_LoadStringW
0x1800111a0  test    eax, eax
0x1800111a2  jz      loc_180011259
0x1800111a8  lea     rdx, [rbp+4E0h+var_230]; lpBuffer
0x1800111af  mov     ecx, ebx; nBufferLength
0x1800111b1  call    cs:__imp_GetCurrentDirectoryW
0x1800111b7  mov     ebx, 98h
0x1800111bc  lea     rcx, [rsp+5E0h+var_5C0]; void *
0x1800111c1  mov     r8d, ebx; Size
0x1800111c4  xor     edx, edx; Val
0x1800111c6  call    memset_0
0x1800111cb  lea     rax, [rsp+5E0h+var_5C0]
0x1800111d0  mov     byte ptr [rax], 0
0x1800111d3  inc     rax
0x1800111d6  sub     rbx, 1
0x1800111da  jnz     short loc_1800111D0
0x1800111dc  xor     eax, eax
0x1800111de  mov     [rsp+5E0h+var_5C0.lStructSize], 88h
0x1800111e6  mov     [rdi], ax
0x1800111e9  lea     rcx, [rsp+5E0h+var_5C0]; LPOPENFILENAMEW
0x1800111ee  mov     rax, [rsi+70h]
0x1800111f2  mov     [rsp+5E0h+var_5C0.hwndOwner], rax
0x1800111f7  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800111fe  mov     [rsp+5E0h+var_5C0.hInstance], rax
0x180011203  lea     rax, [rbp+4E0h+var_440]
0x18001120a  mov     [rsp+5E0h+var_5C0.lpstrFilter], rax
0x18001120f  lea     rax, [rbp+4E0h+var_230]
0x180011216  mov     [rsp+5E0h+var_5C0.lpstrInitialDir], rax
0x18001121b  lea     rax, [rbp+4E0h+var_510]
0x18001121f  mov     [rsp+5E0h+var_5C0.lpstrTitle], rax
0x180011224  lea     rax, [rbp+4E0h+Buffer]
0x180011228  mov     [rbp+4E0h+var_5C0.lpstrDefExt], rax
0x18001122c  mov     [rsp+5E0h+var_5C0.nFilterIndex], 1
0x180011234  mov     [rsp+5E0h+var_5C0.lpstrFile], rdi
0x180011239  mov     [rsp+5E0h+var_5C0.nMaxFile], 105h
0x180011241  mov     [rbp+4E0h+var_5C0.Flags], 100Ch
0x180011248  call    cs:__imp_GetOpenFileNameW
0x18001124e  xor     ecx, ecx
0x180011250  test    eax, eax
0x180011252  setnz   cl
0x180011255  mov     eax, ecx
0x180011257  jmp     short loc_18001125B
0x180011259  xor     eax, eax
0x18001125b  mov     rcx, [rbp+4E0h+var_20]
0x180011262  xor     rcx, rsp; StackCookie
0x180011265  call    __security_check_cookie
0x18001126a  mov     rbx, [rsp+5E0h+arg_10]
0x180011272  add     rsp, 5D0h
0x180011279  pop     rdi
0x18001127a  pop     rsi
0x18001127b  pop     rbp
0x18001127c  retn
```
