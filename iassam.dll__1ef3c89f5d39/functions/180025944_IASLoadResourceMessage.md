# IASLoadResourceMessage

- ea: `0x180025944`
- end: `0x180025a29`
- name: `IASLoadResourceMessage`
- size: `229`
- prototype: `__int64 __fastcall(DWORD dwMessageId)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180025fb8`
- `0x180026764`
- `0x180026920`
- `0x180026a70`

## callees

- `0x18000342c`
- `0x180025944`

## import_xrefs

- `msvcrt!free` at `0x1800259d3`
- `msvcrt!free` at `0x1800259dd`
- `msvcrt!free` at `0x180025a1e`
- `msvcrt!free` at `0x1800259d3`
- `msvcrt!free` at `0x1800259dd`
- `msvcrt!free` at `0x180025a1e`
- `KERNEL32!FormatMessageW` at `0x1800259bc`
- `KERNEL32!FormatMessageW` at `0x1800259bc`
- `KERNEL32!GetModuleHandleW` at `0x180025996`
- `KERNEL32!GetModuleHandleW` at `0x180025996`

## string_xrefs

- `0x18002598f`: `iassvcs.dll`

## pseudocode

```c
WCHAR *__fastcall IASLoadResourceMessage(DWORD dwMessageId, DWORD a2)
{
  int v2; // esi
  DWORD nSize; // edi
  unsigned __int128 v5; // rax
  WCHAR *lpBuffer; // rbx
  HMODULE ModuleHandleW; // rax
  DWORD v8; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx

  v2 = 0;
  nSize = a2;
  if ( !a2 )
    nSize = 1024;
  while ( 1 )
  {
    if ( v2 >= 2 )
      return 0;
    v5 = nSize * (unsigned __int128)2uLL;
    if ( !is_mul_ok(nSize, 2u) )
      *(_QWORD *)&v5 = -1;
    lpBuffer = (WCHAR *)operator new[](v5, *((const struct std::nothrow_t **)&v5 + 1));
    if ( !lpBuffer )
    {
      lpBuffer = 0;
      goto LABEL_17;
    }
    ModuleHandleW = GetModuleHandleW(L"iassvcs.dll");
    v8 = FormatMessageW(0xA00u, ModuleHandleW, dwMessageId, 0, lpBuffer, nSize, 0);
    if ( v8 )
      break;
    if ( nSize >= 0x400 )
    {
      free(lpBuffer);
      return 0;
    }
    nSize = 1024;
    free(lpBuffer);
    ++v2;
  }
  if ( v8 >= 2 )
  {
    v10 = (int)(v8 - 1);
    if ( lpBuffer[v10] == 10 )
    {
      v11 = (int)(v8 - 2);
      if ( lpBuffer[v11] == 13 )
      {
        lpBuffer[v11] = 0;
        lpBuffer[v10] = 0;
      }
    }
  }
LABEL_17:
  free(0);
  return lpBuffer;
}

```

## disassembly

```asm
0x180025944  push    rbx
0x180025946  push    rbp
0x180025947  push    rsi
0x180025948  push    rdi
0x180025949  push    r14
0x18002594b  sub     rsp, 40h
0x18002594f  xor     esi, esi
0x180025951  mov     edi, edx
0x180025953  test    edx, edx
0x180025955  mov     r14d, 400h
0x18002595b  mov     ebp, ecx
0x18002595d  cmovz   edi, r14d
0x180025961  cmp     esi, 2
0x180025964  jge     short loc_1800259E3
0x180025966  mov     ecx, edi
0x180025968  mov     eax, 2
0x18002596d  mul     rcx
0x180025970  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180025977  cmovb   rax, rcx
0x18002597b  mov     rcx, rax; Size
0x18002597e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180025983  mov     rbx, rax
0x180025986  test    rax, rax
0x180025989  jz      loc_180025A1A
0x18002598f  lea     rcx, aIassvcsDll_0; "iassvcs.dll"
0x180025996  call    cs:__imp_GetModuleHandleW
0x18002599c  mov     [rsp+68h+Arguments], 0; Arguments
0x1800259a5  xor     r9d, r9d; dwLanguageId
0x1800259a8  mov     rdx, rax; lpSource
0x1800259ab  mov     [rsp+68h+nSize], edi; nSize
0x1800259af  mov     r8d, ebp; dwMessageId
0x1800259b2  mov     [rsp+68h+lpBuffer], rbx; lpBuffer
0x1800259b7  mov     ecx, 0A00h; dwFlags
0x1800259bc  call    cs:__imp_FormatMessageW
0x1800259c2  mov     ecx, eax
0x1800259c4  test    eax, eax
0x1800259c6  jnz     short loc_1800259F0
0x1800259c8  mov     rcx, rbx; Block
0x1800259cb  cmp     edi, r14d
0x1800259ce  jnb     short loc_1800259DD
0x1800259d0  mov     edi, r14d
0x1800259d3  call    cs:__imp_free
0x1800259d9  inc     esi
0x1800259db  jmp     short loc_180025961
0x1800259dd  call    cs:__imp_free
0x1800259e3  xor     eax, eax
0x1800259e5  add     rsp, 40h
0x1800259e9  pop     r14
0x1800259eb  pop     rdi
0x1800259ec  pop     rsi
0x1800259ed  pop     rbp
0x1800259ee  pop     rbx
0x1800259ef  retn
0x1800259f0  cmp     ecx, 2
0x1800259f3  jb      short loc_180025A1C
0x1800259f5  dec     eax
0x1800259f7  movsxd  rdx, eax
0x1800259fa  cmp     word ptr [rbx+rdx*2], 0Ah
0x1800259ff  jnz     short loc_180025A1C
0x180025a01  lea     eax, [rcx-2]
0x180025a04  movsxd  rcx, eax
0x180025a07  cmp     word ptr [rbx+rcx*2], 0Dh
0x180025a0c  jnz     short loc_180025A1C
0x180025a0e  xor     eax, eax
0x180025a10  mov     [rbx+rcx*2], ax
0x180025a14  mov     [rbx+rdx*2], ax
0x180025a18  jmp     short loc_180025A1C
0x180025a1a  xor     ebx, ebx
0x180025a1c  xor     ecx, ecx; Block
0x180025a1e  call    cs:__imp_free
0x180025a24  mov     rax, rbx
0x180025a27  jmp     short loc_1800259E5
```
