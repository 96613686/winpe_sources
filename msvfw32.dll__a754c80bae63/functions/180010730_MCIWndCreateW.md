# MCIWndCreateW

- ea: `0x180010730`
- end: `0x18001081e`
- name: `MCIWndCreateW`
- size: `238`
- prototype: `HWND __cdecl(HWND hwndParent, HINSTANCE hInstance, DWORD dwStyle, LPCWSTR szFile)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f25c`
- `0x180010690`

## callees

- `0x180010730`
- `0x180012860`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010751`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010751`
- `USER32!CreateWindowExW` at `0x180010806`
- `USER32!CreateWindowExW` at `0x180010806`

## pseudocode

```c
HWND __cdecl MCIWndCreateW(HWND hwndParent, HINSTANCE hInstance, DWORD dwStyle, LPCWSTR szFile)
{
  HINSTANCE ModuleHandleW; // rsi
  HWND result; // rax
  int Y; // edx
  int X; // r8d
  int v11; // ebx

  ModuleHandleW = hInstance;
  if ( !hInstance )
    ModuleHandleW = GetModuleHandleW(0);
  if ( !MCIWndRegisterClass() )
    return 0;
  Y = 0;
  X = 0;
  if ( HIWORD(dwStyle) )
  {
    v11 = dwStyle | 0x6000000;
    if ( hwndParent )
      goto LABEL_13;
LABEL_10:
    if ( v11 >= 0 )
    {
      X = 0x80000000;
      if ( (v11 & 0x10000000) != 0 )
        Y = 5;
    }
    goto LABEL_13;
  }
  if ( !hwndParent )
  {
    v11 = dwStyle | 0x16CF0000;
    goto LABEL_10;
  }
  v11 = dwStyle | 0x56800000;
LABEL_13:
  fFileNameIsUnicode = 1;
  result = CreateWindowExW(
             0,
             aszMCIWndClassName,
             &szNULL,
             v11,
             X,
             Y,
             300,
             0,
             hwndParent,
             (v11 & 0x40000000) != 0 ? (HMENU)0x42 : 0,
             ModuleHandleW,
             (LPVOID)szFile);
  fFileNameIsUnicode = 0;
  return result;
}

```

## disassembly

```asm
0x180010730  push    rbx
0x180010732  push    rbp
0x180010733  push    rsi
0x180010734  push    rdi
0x180010735  push    r14
0x180010737  sub     rsp, 60h
0x18001073b  xor     r14d, r14d
0x18001073e  mov     rbp, r9
0x180010741  mov     ebx, r8d
0x180010744  mov     rsi, rdx
0x180010747  mov     rdi, rcx
0x18001074a  test    rdx, rdx
0x18001074d  jnz     short loc_18001075A
0x18001074f  xor     ecx, ecx; lpModuleName
0x180010751  call    cs:__imp_GetModuleHandleW
0x180010757  mov     rsi, rax
0x18001075a  call    MCIWndRegisterClass
0x18001075f  test    eax, eax
0x180010761  jnz     short loc_18001076A
0x180010763  xor     eax, eax
0x180010765  jmp     loc_180010813
0x18001076a  mov     eax, ebx
0x18001076c  mov     edx, r14d
0x18001076f  shr     eax, 10h
0x180010772  mov     r8d, r14d
0x180010775  test    ax, ax
0x180010778  jnz     short loc_18001078F
0x18001077a  test    rdi, rdi
0x18001077d  jz      short loc_180010787
0x18001077f  or      ebx, 56800000h
0x180010785  jmp     short loc_1800107B0
0x180010787  or      ebx, 16CF0000h
0x18001078d  jmp     short loc_18001079A
0x18001078f  or      ebx, 6000000h
0x180010795  test    rdi, rdi
0x180010798  jnz     short loc_1800107B0
0x18001079a  test    ebx, ebx
0x18001079c  js      short loc_1800107B0
0x18001079e  bt      ebx, 1Ch
0x1800107a2  mov     eax, 5
0x1800107a7  mov     r8d, 80000000h
0x1800107ad  cmovb   edx, eax
0x1800107b0  mov     [rsp+88h+lpParam], rbp; lpParam
0x1800107b5  mov     eax, ebx
0x1800107b7  mov     [rsp+88h+hInstance], rsi; hInstance
0x1800107bc  and     eax, 40000000h
0x1800107c1  neg     eax
0x1800107c3  mov     cs:fFileNameIsUnicode, 1
0x1800107cd  mov     r9d, ebx; dwStyle
0x1800107d0  sbb     rcx, rcx
0x1800107d3  and     ecx, 42h
0x1800107d6  mov     [rsp+88h+hMenu], rcx; hMenu
0x1800107db  xor     ecx, ecx; dwExStyle
0x1800107dd  mov     [rsp+88h+hWndParent], rdi; hWndParent
0x1800107e2  mov     [rsp+88h+nHeight], r14d; nHeight
0x1800107e7  mov     [rsp+88h+nWidth], 12Ch; nWidth
0x1800107ef  mov     [rsp+88h+Y], edx; Y
0x1800107f3  lea     rdx, aszMCIWndClassName; "MCIWndClass"
0x1800107fa  mov     [rsp+88h+X], r8d; X
0x1800107ff  lea     r8, szNULL; lpWindowName
0x180010806  call    cs:__imp_CreateWindowExW
0x18001080c  mov     cs:fFileNameIsUnicode, r14d
0x180010813  add     rsp, 60h
0x180010817  pop     r14
0x180010819  pop     rdi
0x18001081a  pop     rsi
0x18001081b  pop     rbp
0x18001081c  pop     rbx
0x18001081d  retn
```
