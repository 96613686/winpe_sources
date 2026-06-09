# IASLoadResourceMessage

- ea: `0x18002c5bc`
- end: `0x18002c6a1`
- name: `IASLoadResourceMessage`
- size: `229`
- prototype: `__int64 __fastcall(DWORD dwMessageId)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180028b74`
- `0x18002931c`
- `0x1800294d8`
- `0x18002962c`

## callees

- `0x18000e4e0`
- `0x18002c5bc`

## import_xrefs

- `msvcrt!free` at `0x18002c64b`
- `msvcrt!free` at `0x18002c655`
- `msvcrt!free` at `0x18002c696`
- `msvcrt!free` at `0x18002c64b`
- `msvcrt!free` at `0x18002c655`
- `msvcrt!free` at `0x18002c696`
- `KERNEL32!FormatMessageW` at `0x18002c634`
- `KERNEL32!FormatMessageW` at `0x18002c634`
- `KERNEL32!GetModuleHandleW` at `0x18002c60e`
- `KERNEL32!GetModuleHandleW` at `0x18002c60e`

## string_xrefs

- `0x18002c607`: `iassvcs.dll`

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
0x18002c5bc  push    rbx
0x18002c5be  push    rbp
0x18002c5bf  push    rsi
0x18002c5c0  push    rdi
0x18002c5c1  push    r14
0x18002c5c3  sub     rsp, 40h
0x18002c5c7  xor     esi, esi
0x18002c5c9  mov     edi, edx
0x18002c5cb  test    edx, edx
0x18002c5cd  mov     r14d, 400h
0x18002c5d3  mov     ebp, ecx
0x18002c5d5  cmovz   edi, r14d
0x18002c5d9  cmp     esi, 2
0x18002c5dc  jge     short loc_18002C65B
0x18002c5de  mov     ecx, edi
0x18002c5e0  mov     eax, 2
0x18002c5e5  mul     rcx
0x18002c5e8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002c5ef  cmovb   rax, rcx
0x18002c5f3  mov     rcx, rax; Size
0x18002c5f6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002c5fb  mov     rbx, rax
0x18002c5fe  test    rax, rax
0x18002c601  jz      loc_18002C692
0x18002c607  lea     rcx, aIassvcsDll_0; "iassvcs.dll"
0x18002c60e  call    cs:__imp_GetModuleHandleW
0x18002c614  mov     [rsp+68h+Arguments], 0; Arguments
0x18002c61d  xor     r9d, r9d; dwLanguageId
0x18002c620  mov     rdx, rax; lpSource
0x18002c623  mov     [rsp+68h+nSize], edi; nSize
0x18002c627  mov     r8d, ebp; dwMessageId
0x18002c62a  mov     [rsp+68h+lpBuffer], rbx; lpBuffer
0x18002c62f  mov     ecx, 0A00h; dwFlags
0x18002c634  call    cs:__imp_FormatMessageW
0x18002c63a  mov     ecx, eax
0x18002c63c  test    eax, eax
0x18002c63e  jnz     short loc_18002C668
0x18002c640  mov     rcx, rbx; Block
0x18002c643  cmp     edi, r14d
0x18002c646  jnb     short loc_18002C655
0x18002c648  mov     edi, r14d
0x18002c64b  call    cs:__imp_free
0x18002c651  inc     esi
0x18002c653  jmp     short loc_18002C5D9
0x18002c655  call    cs:__imp_free
0x18002c65b  xor     eax, eax
0x18002c65d  add     rsp, 40h
0x18002c661  pop     r14
0x18002c663  pop     rdi
0x18002c664  pop     rsi
0x18002c665  pop     rbp
0x18002c666  pop     rbx
0x18002c667  retn
0x18002c668  cmp     ecx, 2
0x18002c66b  jb      short loc_18002C694
0x18002c66d  dec     eax
0x18002c66f  movsxd  rdx, eax
0x18002c672  cmp     word ptr [rbx+rdx*2], 0Ah
0x18002c677  jnz     short loc_18002C694
0x18002c679  lea     eax, [rcx-2]
0x18002c67c  movsxd  rcx, eax
0x18002c67f  cmp     word ptr [rbx+rcx*2], 0Dh
0x18002c684  jnz     short loc_18002C694
0x18002c686  xor     eax, eax
0x18002c688  mov     [rbx+rcx*2], ax
0x18002c68c  mov     [rbx+rdx*2], ax
0x18002c690  jmp     short loc_18002C694
0x18002c692  xor     ebx, ebx
0x18002c694  xor     ecx, ecx; Block
0x18002c696  call    cs:__imp_free
0x18002c69c  mov     rax, rbx
0x18002c69f  jmp     short loc_18002C65D
```
