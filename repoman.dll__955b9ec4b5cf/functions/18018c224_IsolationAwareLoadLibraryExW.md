# IsolationAwareLoadLibraryExW

- ea: `0x18018c224`
- end: `0x18018c2db`
- name: `IsolationAwareLoadLibraryExW`
- size: `183`
- prototype: `HMODULE()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18018cd40`

## callees

- `0x1800e3db4`
- `0x18018c224`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18018c2b1`
- `KERNEL32!GetLastError` at `0x1801a8246`
- `KERNEL32!GetLastError` at `0x18018c2b1`
- `KERNEL32!GetLastError` at `0x1801a8246`
- `KERNEL32!SetLastError` at `0x18018c2d0`
- `KERNEL32!SetLastError` at `0x1801a8264`
- `KERNEL32!SetLastError` at `0x18018c2d0`
- `KERNEL32!SetLastError` at `0x1801a8264`
- `KERNEL32!DeactivateActCtx` at `0x18018c2c4`
- `KERNEL32!DeactivateActCtx` at `0x1801a8258`
- `KERNEL32!DeactivateActCtx` at `0x18018c2c4`
- `KERNEL32!DeactivateActCtx` at `0x1801a8258`
- `KERNEL32!LoadLibraryExW` at `0x18018c285`
- `KERNEL32!LoadLibraryExW` at `0x18018c285`

## string_xrefs

- `0x18018c27e`: `wofutil.dll`

## pseudocode

```c
HMODULE IsolationAwareLoadLibraryExW()
{
  HMODULE Library; // rax
  HMODULE v2; // rdi
  BOOL v3; // ebx
  DWORD LastError; // esi
  ULONG_PTR ulCookie; // [rsp+48h] [rbp+10h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Library = LoadLibraryExW(L"wofutil.dll", 0, 0);
  v2 = Library;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    v3 = Library == 0;
    if ( Library )
      LastError = 0;
    else
      LastError = GetLastError();
    DeactivateActCtx(0, ulCookie);
    if ( v3 )
      SetLastError(LastError);
  }
  return v2;
}

```

## disassembly

```asm
0x18018c224  mov     rax, rsp
0x18018c227  mov     [rax+8], rbx
0x18018c22b  mov     [rax+18h], rsi
0x18018c22f  mov     [rax+10h], rdx
0x18018c233  push    rdi
0x18018c234  sub     rsp, 30h
0x18018c238  mov     qword ptr [rax-18h], 0
0x18018c240  mov     qword ptr [rax+10h], 0
0x18018c248  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18018c24f  jnz     short loc_18018C279
0x18018c251  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18018c258  jnz     short loc_18018C279
0x18018c25a  lea     rcx, [rax+10h]; lpCookie
0x18018c25e  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18018c263  test    eax, eax
0x18018c265  jnz     short loc_18018C279
0x18018c267  xor     eax, eax
0x18018c269  mov     rbx, [rsp+38h+arg_0]
0x18018c26e  mov     rsi, [rsp+38h+arg_10]
0x18018c273  add     rsp, 30h
0x18018c277  pop     rdi
0x18018c278  retn
0x18018c279  xor     r8d, r8d; dwFlags
0x18018c27c  xor     edx, edx; hFile
0x18018c27e  lea     rcx, aWofutilDll; "wofutil.dll"
0x18018c285  call    cs:__imp_LoadLibraryExW
0x18018c28b  mov     rdi, rax
0x18018c28e  mov     [rsp+38h+var_18], rax
0x18018c293  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18018c29a  jz      short loc_18018C2A5
0x18018c29c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18018c2a3  jnz     short loc_18018C2D6
0x18018c2a5  xor     ebx, ebx
0x18018c2a7  test    rdi, rdi
0x18018c2aa  setz    bl
0x18018c2ad  test    ebx, ebx
0x18018c2af  jz      short loc_18018C2BB
0x18018c2b1  call    cs:__imp_GetLastError
0x18018c2b7  mov     esi, eax
0x18018c2b9  jmp     short loc_18018C2BD
0x18018c2bb  xor     esi, esi
0x18018c2bd  mov     rdx, [rsp+38h+ulCookie]; ulCookie
0x18018c2c2  xor     ecx, ecx; dwFlags
0x18018c2c4  call    cs:__imp_DeactivateActCtx
0x18018c2ca  test    ebx, ebx
0x18018c2cc  jz      short loc_18018C2D6
0x18018c2ce  mov     ecx, esi; dwErrCode
0x18018c2d0  call    cs:__imp_SetLastError
0x18018c2d6  mov     rax, rdi
0x18018c2d9  jmp     short loc_18018C269
0x1801a821c  push    rbx
0x1801a821e  push    rbp
0x1801a821f  push    rdi
0x1801a8220  sub     rsp, 20h
0x1801a8224  mov     rbp, rdx
0x1801a8227  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1801a822e  jz      short loc_1801A8239
0x1801a8230  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1801a8237  jnz     short loc_1801A826B
0x1801a8239  xor     ebx, ebx
0x1801a823b  cmp     [rbp+20h], rbx
0x1801a823f  setz    bl
0x1801a8242  test    ebx, ebx
0x1801a8244  jz      short loc_1801A8250
0x1801a8246  call    cs:__imp_GetLastError
0x1801a824c  mov     edi, eax
0x1801a824e  jmp     short loc_1801A8252
0x1801a8250  xor     edi, edi
0x1801a8252  mov     rdx, [rbp+48h]; ulCookie
0x1801a8256  xor     ecx, ecx; dwFlags
0x1801a8258  call    cs:__imp_DeactivateActCtx
0x1801a825e  test    ebx, ebx
0x1801a8260  jz      short loc_1801A826B
0x1801a8262  mov     ecx, edi; dwErrCode
0x1801a8264  call    cs:__imp_SetLastError
0x1801a826a  nop
0x1801a826b  add     rsp, 20h
0x1801a826f  pop     rdi
0x1801a8270  pop     rbp
0x1801a8271  pop     rbx
0x1801a8272  retn
```
