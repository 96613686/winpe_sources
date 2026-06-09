# ResourceStringFindAndSizeEx

- ea: `0x1800042ac`
- end: `0x180004391`
- name: `ResourceStringFindAndSizeEx`
- size: `229`
- prototype: `DWORD __fastcall(HMODULE hModule, unsigned int, __int64, unsigned __int64 *, _WORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800041cc`

## callees

- `0x1800042ac`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x1800042d3`
- `KERNEL32!FindResourceExW` at `0x1800042d3`
- `KERNEL32!LoadResource` at `0x1800042e4`
- `KERNEL32!LoadResource` at `0x1800042e4`
- `KERNEL32!GetLastError` at `0x18000435c`
- `KERNEL32!GetLastError` at `0x180004368`
- `KERNEL32!GetLastError` at `0x180004375`
- `KERNEL32!GetLastError` at `0x18000435c`
- `KERNEL32!GetLastError` at `0x180004368`
- `KERNEL32!GetLastError` at `0x180004375`
- `KERNEL32!LockResource` at `0x1800042f2`
- `KERNEL32!LockResource` at `0x1800042f2`

## pseudocode

```c
DWORD __fastcall ResourceStringFindAndSizeEx(
        HMODULE hModule,
        unsigned int a2,
        __int64 a3,
        unsigned __int64 *a4,
        _WORD *a5)
{
  char v6; // bl
  HRSRC Resource; // rax
  HGLOBAL v9; // rax
  unsigned __int16 *v10; // rdx
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int16 v13; // r8
  DWORD result; // eax
  DWORD LastError; // eax

  v6 = a2;
  Resource = FindResourceExW(hModule, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)((a2 >> 4) + 1), 0);
  if ( Resource && (v9 = LoadResource(hModule, Resource)) != 0 )
  {
    v10 = (unsigned __int16 *)LockResource(v9);
    if ( v10 )
    {
      v11 = 0;
      v12 = v6 & 0xF;
      if ( v12 )
      {
        do
        {
          ++v11;
          v10 += *v10 + 1;
        }
        while ( v11 < v12 );
      }
      if ( a4 )
      {
        v13 = *v10;
        *a4 = (unsigned __int64)(v10 + 1) & -(__int64)(*v10 != 0);
        *a5 = v13;
      }
      else if ( a5 )
      {
        *a5 = *v10;
      }
      return 0;
    }
    else
    {
      return -2147467259;
    }
  }
  else if ( (GetLastError() & 0x80000000) == 0 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LOWORD(LastError) = 1;
    return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    result = GetLastError();
    if ( !result )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800042ac  push    rbx
0x1800042ae  push    rbp
0x1800042af  push    rsi
0x1800042b0  push    rdi
0x1800042b1  sub     rsp, 28h
0x1800042b5  mov     eax, edx
0x1800042b7  mov     rdi, r9
0x1800042ba  xor     r9d, r9d; wLanguage
0x1800042bd  shr     eax, 4
0x1800042c0  mov     ebx, edx
0x1800042c2  mov     rsi, rcx
0x1800042c5  lea     ebp, [r9+1]
0x1800042c9  add     ax, bp
0x1800042cc  lea     edx, [rbp+5]; lpType
0x1800042cf  movzx   r8d, ax; lpName
0x1800042d3  call    cs:__imp_FindResourceExW
0x1800042d9  test    rax, rax
0x1800042dc  jz      short loc_18000435C
0x1800042de  mov     rdx, rax; hResInfo
0x1800042e1  mov     rcx, rsi; hModule
0x1800042e4  call    cs:__imp_LoadResource
0x1800042ea  test    rax, rax
0x1800042ed  jz      short loc_18000435C
0x1800042ef  mov     rcx, rax; hResData
0x1800042f2  call    cs:__imp_LockResource
0x1800042f8  mov     rdx, rax
0x1800042fb  test    rax, rax
0x1800042fe  jz      short loc_180004355
0x180004300  lea     eax, [rbp-1]
0x180004303  and     ebx, 0Fh
0x180004306  jbe     short loc_180004319
0x180004308  movzx   ecx, word ptr [rdx]
0x18000430b  add     eax, ebp
0x18000430d  lea     rdx, [rdx+rcx*2]
0x180004311  add     rdx, 2
0x180004315  cmp     eax, ebx
0x180004317  jb      short loc_180004308
0x180004319  test    rdi, rdi
0x18000431c  jz      short loc_180004341
0x18000431e  movzx   r8d, word ptr [rdx]
0x180004322  add     rdx, 2
0x180004326  movzx   eax, r8w
0x18000432a  neg     ax
0x18000432d  mov     rax, [rsp+48h+arg_20]
0x180004332  sbb     rcx, rcx
0x180004335  and     rcx, rdx
0x180004338  mov     [rdi], rcx
0x18000433b  mov     [rax], r8w
0x18000433f  jmp     short loc_180004351
0x180004341  mov     rcx, [rsp+48h+arg_20]
0x180004346  test    rcx, rcx
0x180004349  jz      short loc_180004351
0x18000434b  movzx   eax, word ptr [rdx]
0x18000434e  mov     [rcx], ax
0x180004351  xor     eax, eax
0x180004353  jmp     short loc_180004388
0x180004355  mov     eax, 80004005h
0x18000435a  jmp     short loc_180004388
0x18000435c  call    cs:__imp_GetLastError
0x180004362  test    eax, eax
0x180004364  jz      short loc_180004375
0x180004366  jg      short loc_180004375
0x180004368  call    cs:__imp_GetLastError
0x18000436e  test    eax, eax
0x180004370  cmovz   eax, ebp
0x180004373  jmp     short loc_180004388
0x180004375  call    cs:__imp_GetLastError
0x18000437b  test    eax, eax
0x18000437d  cmovz   eax, ebp
0x180004380  movzx   eax, ax
0x180004383  or      eax, 80070000h
0x180004388  add     rsp, 28h
0x18000438c  pop     rdi
0x18000438d  pop     rsi
0x18000438e  pop     rbp
0x18000438f  pop     rbx
0x180004390  retn
```
