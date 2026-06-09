# NetpOpenConfigDataWithPathEx

- ea: `0x18000c210`
- end: `0x18000c383`
- name: `NetpOpenConfigDataWithPathEx`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180052484`

## callees

- `0x180003320`
- `0x18000c210`
- `0x18000f3b4`
- `0x18000f3c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c298`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c333`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c342`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c356`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c298`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c333`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c342`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c356`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c312`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c312`

## pseudocode

```c
__int64 __fastcall NetpOpenConfigDataWithPathEx(HKEY **a1, const wchar_t *a2, HKEY a3)
{
  HKEY *v5; // r14
  __int64 v7; // rax
  unsigned __int64 v9; // rdi
  wchar_t *v10; // rax
  wchar_t *v11; // rbp
  rsize_t v12; // rdi
  LSTATUS v13; // eax
  unsigned int v14; // ebx
  HKEY phkResult; // [rsp+60h] [rbp+18h] BYREF

  phkResult = a3;
  *a1 = 0;
  if ( !a2 || !*a2 )
    return 87;
  v5 = (HKEY *)NetpMemoryAllocate(16);
  if ( !v5 )
    return 8;
  v7 = -1;
  phkResult = 0;
  while ( a2[++v7] != 0 )
    ;
  v9 = (unsigned int)(2 * v7 + 24);
  v10 = (wchar_t *)NetpMemoryAllocate(v9);
  v11 = v10;
  if ( v10 )
  {
    v12 = v9 >> 1;
    wcscpy_s(v10, v12, a2);
    wcscat_s(v11, v12, L"\\");
    wcscat_s(v11, v12, L"Parameters");
    v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, &phkResult);
    v14 = v13;
    if ( v13 == 2 )
    {
      v14 = 2146;
    }
    else if ( !v13 )
    {
      LocalFree(v11);
      v14 = 0;
      *v5 = phkResult;
      goto LABEL_15;
    }
    LocalFree(v11);
    LocalFree(v5);
    v5 = 0;
LABEL_15:
    *a1 = v5;
    return v14;
  }
  LocalFree(v5);
  return 8;
}

```

## disassembly

```asm
0x18000c210  mov     [rsp+arg_10], r8
0x18000c215  push    rbx
0x18000c216  push    rsi
0x18000c217  sub     rsp, 38h
0x18000c21b  mov     qword ptr [rcx], 0
0x18000c222  mov     rbx, rdx
0x18000c225  mov     rsi, rcx
0x18000c228  test    rdx, rdx
0x18000c22b  jz      loc_18000C376
0x18000c231  cmp     word ptr [rdx], 0
0x18000c235  jz      loc_18000C376
0x18000c23b  mov     ecx, 10h
0x18000c240  mov     [rsp+48h+var_18], r14
0x18000c245  call    NetpMemoryAllocate
0x18000c24a  mov     r14, rax
0x18000c24d  test    rax, rax
0x18000c250  jnz     short loc_18000C259
0x18000c252  mov     eax, 8
0x18000c257  jmp     short loc_18000C2B3
0x18000c259  mov     [rsp+48h+arg_0], rbp
0x18000c25e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c265  mov     [rsp+48h+arg_8], rdi
0x18000c26a  mov     [rsp+48h+arg_10], 0
0x18000c273  cmp     word ptr [rbx+rax*2+2], 0
0x18000c279  lea     rax, [rax+1]
0x18000c27d  jnz     short loc_18000C273
0x18000c27f  lea     edi, ds:18h[rax*2]
0x18000c286  mov     ecx, edi
0x18000c288  call    NetpMemoryAllocate
0x18000c28d  mov     rbp, rax
0x18000c290  test    rax, rax
0x18000c293  jnz     short loc_18000C2C0
0x18000c295  mov     rcx, r14; hMem
0x18000c298  call    cs:__imp_LocalFree
0x18000c29f  nop     dword ptr [rax+rax+00h]
0x18000c2a4  mov     eax, 8
0x18000c2a9  mov     rdi, [rsp+48h+arg_8]
0x18000c2ae  mov     rbp, [rsp+48h+arg_0]
0x18000c2b3  mov     r14, [rsp+48h+var_18]
0x18000c2b8  add     rsp, 38h
0x18000c2bc  pop     rsi
0x18000c2bd  pop     rbx
0x18000c2be  retn
0x18000c2c0  shr     rdi, 1
0x18000c2c3  mov     r8, rbx; Source
0x18000c2c6  mov     rdx, rdi; SizeInWords
0x18000c2c9  mov     rcx, rbp; Destination
0x18000c2cc  call    wcscpy_s
0x18000c2d1  lea     r8, SubStr; "\\"
0x18000c2d8  mov     rdx, rdi; SizeInWords
0x18000c2db  mov     rcx, rbp; Destination
0x18000c2de  call    wcscat_s
0x18000c2e3  lea     r8, aParameters; "Parameters"
0x18000c2ea  mov     rdx, rdi; SizeInWords
0x18000c2ed  mov     rcx, rbp; Destination
0x18000c2f0  call    wcscat_s
0x18000c2f5  lea     rax, [rsp+48h+arg_10]
0x18000c2fa  mov     r9d, 20019h; samDesired
0x18000c300  xor     r8d, r8d; ulOptions
0x18000c303  mov     [rsp+48h+phkResult], rax; phkResult
0x18000c308  mov     rdx, rbp; lpSubKey
0x18000c30b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c312  call    cs:__imp_RegOpenKeyExW
0x18000c319  nop     dword ptr [rax+rax+00h]
0x18000c31e  mov     ebx, eax
0x18000c320  cmp     eax, 2
0x18000c323  jnz     short loc_18000C32C
0x18000c325  mov     ebx, 862h
0x18000c32a  jmp     short loc_18000C330
0x18000c32c  test    eax, eax
0x18000c32e  jz      short loc_18000C353
0x18000c330  mov     rcx, rbp; hMem
0x18000c333  call    cs:__imp_LocalFree
0x18000c33a  nop     dword ptr [rax+rax+00h]
0x18000c33f  mov     rcx, r14; hMem
0x18000c342  call    cs:__imp_LocalFree
0x18000c349  nop     dword ptr [rax+rax+00h]
0x18000c34e  xor     r14d, r14d
0x18000c351  jmp     short loc_18000C36C
0x18000c353  mov     rcx, rbp; hMem
0x18000c356  call    cs:__imp_LocalFree
0x18000c35d  nop     dword ptr [rax+rax+00h]
0x18000c362  mov     rax, [rsp+48h+arg_10]
0x18000c367  xor     ebx, ebx
0x18000c369  mov     [r14], rax
0x18000c36c  mov     [rsi], r14
0x18000c36f  mov     eax, ebx
0x18000c371  jmp     loc_18000C2A9
0x18000c376  mov     eax, 57h ; 'W'
0x18000c37b  add     rsp, 38h
0x18000c37f  pop     rsi
0x18000c380  pop     rbx
0x18000c381  retn
```
