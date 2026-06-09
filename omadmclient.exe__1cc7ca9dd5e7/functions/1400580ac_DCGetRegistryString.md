# DCGetRegistryString

- ea: `0x1400580ac`
- end: `0x140058250`
- name: `DCGetRegistryString`
- size: `420`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x140056b74`
- `0x1400585f0`
- `0x140058a5c`

## callees

- `0x1400036e4`
- `0x140003eb4`
- `0x140005864`
- `0x1400580ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140058107`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140058107`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140058153`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400581ec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140058153`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400581ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005822d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005822d`

## pseudocode

```c
__int64 __fastcall DCGetRegistryString(HKEY a1, const WCHAR *a2, const WCHAR *a3, BYTE **a4)
{
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  unsigned __int64 v10; // rbx
  unsigned __int64 v11; // rax
  BYTE *v12; // rax
  BYTE *v13; // rdi
  LSTATUS v14; // eax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  Type = 1;
  hKey = 0;
  cbData = 0;
  if ( !a1 || !a4 )
  {
    v8 = -2147024809;
    goto LABEL_24;
  }
  if ( !a2 )
  {
    hKey = a1;
LABEL_9:
    v9 = RegQueryValueExW(a1, a3, 0, &Type, 0, &cbData);
    v8 = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
    }
    else if ( Type == 1 )
    {
      v10 = ((unsigned __int64)cbData >> 1) + 1;
      v11 = 2 * v10;
      if ( !is_mul_ok(v10, 2u) )
        v11 = -1;
      v12 = (BYTE *)operator new[](v11, (const struct std::nothrow_t *)std::nothrow);
      v13 = v12;
      if ( v12 )
      {
        memset_0(v12, 0, v10);
        v14 = RegQueryValueExW(hKey, a3, 0, &Type, v13, &cbData);
        v8 = v14;
        if ( v14 )
        {
          if ( v14 > 0 )
            v8 = (unsigned __int16)v14 | 0x80070000;
          operator delete(v13);
        }
        else
        {
          v8 = 0;
          *a4 = v13;
        }
      }
      else
      {
        v8 = -2147024882;
      }
    }
    else
    {
      v8 = -2147418113;
    }
LABEL_24:
    if ( !a2 )
      return v8;
    goto LABEL_25;
  }
  v7 = RegOpenKeyExW(a1, a2, 0, 0x20119u, &hKey);
  v8 = v7;
  if ( !v7 )
  {
    a1 = hKey;
    goto LABEL_9;
  }
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x1400580ac  mov     [rsp-28h+arg_10], rbx
0x1400580b1  push    rbp
0x1400580b2  push    rsi
0x1400580b3  push    rdi
0x1400580b4  push    r14
0x1400580b6  push    r15
0x1400580b8  mov     rbp, rsp
0x1400580bb  sub     rsp, 40h
0x1400580bf  mov     [rbp+Type], 1
0x1400580c6  mov     r14, r9
0x1400580c9  mov     [rbp+hKey], 0
0x1400580d1  mov     r15, r8
0x1400580d4  mov     [rbp+cbData], 0
0x1400580db  mov     rsi, rdx
0x1400580de  test    rcx, rcx
0x1400580e1  jz      loc_14005821A
0x1400580e7  test    r9, r9
0x1400580ea  jz      loc_14005821A
0x1400580f0  test    rdx, rdx
0x1400580f3  jz      short loc_140058133
0x1400580f5  lea     rax, [rbp+hKey]
0x1400580f9  mov     r9d, 20119h; samDesired
0x1400580ff  xor     r8d, r8d; ulOptions
0x140058102  mov     [rsp+40h+phkResult], rax; phkResult
0x140058107  call    cs:__imp_RegOpenKeyExW
0x14005810e  nop     dword ptr [rax+rax+00h]
0x140058113  mov     ebx, eax
0x140058115  test    eax, eax
0x140058117  jz      short loc_14005812D
0x140058119  jle     loc_140058224
0x14005811f  movzx   ebx, ax
0x140058122  or      ebx, 80070000h
0x140058128  jmp     loc_140058224
0x14005812d  mov     rcx, [rbp+hKey]; hKey
0x140058131  jmp     short loc_140058137
0x140058133  mov     [rbp+hKey], rcx
0x140058137  lea     rax, [rbp+cbData]
0x14005813b  xor     r8d, r8d; lpReserved
0x14005813e  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140058143  lea     r9, [rbp+Type]; lpType
0x140058147  mov     rdx, r15; lpValueName
0x14005814a  mov     [rsp+40h+phkResult], 0; lpData
0x140058153  call    cs:__imp_RegQueryValueExW
0x14005815a  nop     dword ptr [rax+rax+00h]
0x14005815f  mov     ebx, eax
0x140058161  test    eax, eax
0x140058163  jz      short loc_140058179
0x140058165  jle     loc_14005821F
0x14005816b  movzx   ebx, ax
0x14005816e  or      ebx, 80070000h
0x140058174  jmp     loc_14005821F
0x140058179  cmp     [rbp+Type], 1
0x14005817d  jz      short loc_140058189
0x14005817f  mov     ebx, 8000FFFFh
0x140058184  jmp     loc_14005821F
0x140058189  mov     ebx, [rbp+cbData]
0x14005818c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140058193  shr     rbx, 1
0x140058196  mov     eax, 2
0x14005819b  inc     rbx
0x14005819e  mul     rbx
0x1400581a1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400581a8  cmovb   rax, rcx
0x1400581ac  mov     rcx, rax; unsigned __int64
0x1400581af  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400581b4  mov     rdi, rax
0x1400581b7  test    rax, rax
0x1400581ba  jnz     short loc_1400581C3
0x1400581bc  mov     ebx, 8007000Eh
0x1400581c1  jmp     short loc_14005821F
0x1400581c3  mov     r8, rbx; Size
0x1400581c6  xor     edx, edx; Val
0x1400581c8  mov     rcx, rdi; void *
0x1400581cb  call    memset_0
0x1400581d0  mov     rcx, [rbp+hKey]; hKey
0x1400581d4  lea     rax, [rbp+cbData]
0x1400581d8  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1400581dd  lea     r9, [rbp+Type]; lpType
0x1400581e1  xor     r8d, r8d; lpReserved
0x1400581e4  mov     [rsp+40h+phkResult], rdi; lpData
0x1400581e9  mov     rdx, r15; lpValueName
0x1400581ec  call    cs:__imp_RegQueryValueExW
0x1400581f3  nop     dword ptr [rax+rax+00h]
0x1400581f8  mov     ebx, eax
0x1400581fa  test    eax, eax
0x1400581fc  jz      short loc_140058213
0x1400581fe  jle     short loc_140058209
0x140058200  movzx   ebx, ax
0x140058203  or      ebx, 80070000h
0x140058209  mov     rcx, rdi; Block
0x14005820c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140058211  jmp     short loc_14005821F
0x140058213  xor     ebx, ebx
0x140058215  mov     [r14], rdi
0x140058218  jmp     short loc_14005821F
0x14005821a  mov     ebx, 80070057h
0x14005821f  test    rsi, rsi
0x140058222  jz      short loc_140058239
0x140058224  mov     rcx, [rbp+hKey]; hKey
0x140058228  test    rcx, rcx
0x14005822b  jz      short loc_140058239
0x14005822d  call    cs:__imp_RegCloseKey
0x140058234  nop     dword ptr [rax+rax+00h]
0x140058239  mov     eax, ebx
0x14005823b  mov     rbx, [rsp+40h+arg_10]
0x140058243  add     rsp, 40h
0x140058247  pop     r15
0x140058249  pop     r14
0x14005824b  pop     rdi
0x14005824c  pop     rsi
0x14005824d  pop     rbp
0x14005824e  retn
```
