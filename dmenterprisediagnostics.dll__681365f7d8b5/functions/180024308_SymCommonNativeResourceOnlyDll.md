# SymCommonNativeResourceOnlyDll

- ea: `0x180024308`
- end: `0x180024416`
- name: `SymCommonNativeResourceOnlyDll`
- size: `270`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800239a8`

## callees

- `0x180024308`

## import_xrefs

- `ntdll!RtlImageDirectoryEntryToData` at `0x18002433d`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002435f`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002437d`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800243dc`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002433d`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002435f`
- `ntdll!RtlImageDirectoryEntryToData` at `0x18002437d`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800243dc`

## pseudocode

```c
__int64 __fastcall SymCommonNativeResourceOnlyDll(unsigned int *BaseAddress, BOOLEAN a2)
{
  unsigned int v4; // ebx
  PVOID v5; // r14
  PVOID v6; // rbp
  __int64 v7; // rcx
  _DWORD *v8; // rax
  ULONG v10[10]; // [rsp+20h] [rbp-28h] BYREF
  ULONG v11; // [rsp+60h] [rbp+18h] BYREF
  ULONG Size; // [rsp+68h] [rbp+20h] BYREF

  v10[0] = 0;
  Size = 0;
  v11 = 0;
  v4 = 1;
  v5 = RtlImageDirectoryEntryToData(BaseAddress, a2, 0, v10);
  v6 = RtlImageDirectoryEntryToData(BaseAddress, a2, 1u, &Size);
  if ( !RtlImageDirectoryEntryToData(BaseAddress, a2, 2u, &v11) )
    return 0;
  if ( !v11 )
    return 0;
  if ( v6 )
    return 0;
  if ( Size )
    return 0;
  if ( v5 )
    return 0;
  if ( v10[0] )
    return 0;
  v7 = BaseAddress[15];
  if ( ((*(_WORD *)((char *)BaseAddress + v7 + 24) - 267) & 0xFEFF) != 0
    || *(unsigned int *)((char *)BaseAddress + v7 + 40) )
  {
    return 0;
  }
  else
  {
    v8 = RtlImageDirectoryEntryToData(BaseAddress, a2, 0xEu, &v11);
    if ( v11 == 72 && v8 )
      return *v8 != 72;
  }
  return v4;
}

```

## disassembly

```asm
0x180024308  mov     rax, rsp
0x18002430b  mov     [rax+8], rbx
0x18002430f  mov     [rax+10h], rbp
0x180024313  push    rsi
0x180024314  push    rdi
0x180024315  push    r14
0x180024317  sub     rsp, 30h
0x18002431b  xor     r8d, r8d; Directory
0x18002431e  mov     dword ptr [rax-28h], 0
0x180024325  lea     r9, [rax-28h]; Size
0x180024329  mov     dword ptr [rax+20h], 0
0x180024330  mov     sil, dl
0x180024333  mov     dword ptr [rax+18h], 0
0x18002433a  mov     rdi, rcx
0x18002433d  call    cs:__imp_RtlImageDirectoryEntryToData
0x180024344  nop     dword ptr [rax+rax+00h]
0x180024349  mov     ebx, 1
0x18002434e  lea     r9, [rsp+48h+Size]; Size
0x180024353  mov     r8d, ebx; Directory
0x180024356  mov     dl, sil; MappedAsImage
0x180024359  mov     rcx, rdi; BaseAddress
0x18002435c  mov     r14, rax
0x18002435f  call    cs:__imp_RtlImageDirectoryEntryToData
0x180024366  nop     dword ptr [rax+rax+00h]
0x18002436b  lea     r8d, [rbx+1]; Directory
0x18002436f  mov     dl, sil; MappedAsImage
0x180024372  lea     r9, [rsp+48h+arg_10]; Size
0x180024377  mov     rcx, rdi; BaseAddress
0x18002437a  mov     rbp, rax
0x18002437d  call    cs:__imp_RtlImageDirectoryEntryToData
0x180024384  nop     dword ptr [rax+rax+00h]
0x180024389  test    rax, rax
0x18002438c  jz      short loc_1800243FE
0x18002438e  cmp     [rsp+48h+arg_10], 0
0x180024393  jz      short loc_1800243FE
0x180024395  test    rbp, rbp
0x180024398  jnz     short loc_1800243FE
0x18002439a  cmp     [rsp+48h+Size], ebp
0x18002439e  jnz     short loc_1800243FE
0x1800243a0  test    r14, r14
0x1800243a3  jnz     short loc_1800243FE
0x1800243a5  cmp     [rsp+48h+var_28], r14d
0x1800243aa  jnz     short loc_1800243FE
0x1800243ac  mov     ecx, [rdi+3Ch]
0x1800243af  mov     edx, 10Bh
0x1800243b4  movzx   eax, word ptr [rcx+rdi+18h]
0x1800243b9  sub     ax, dx
0x1800243bc  mov     edx, 0FEFFh
0x1800243c1  test    dx, ax
0x1800243c4  jnz     short loc_1800243FE
0x1800243c6  cmp     [rcx+rdi+28h], r14d
0x1800243cb  jnz     short loc_1800243FE
0x1800243cd  lea     r8d, [rbx+0Dh]; Directory
0x1800243d1  mov     dl, sil; MappedAsImage
0x1800243d4  lea     r9, [rsp+48h+arg_10]; Size
0x1800243d9  mov     rcx, rdi; BaseAddress
0x1800243dc  call    cs:__imp_RtlImageDirectoryEntryToData
0x1800243e3  nop     dword ptr [rax+rax+00h]
0x1800243e8  cmp     [rsp+48h+arg_10], 48h ; 'H'
0x1800243ed  jnz     short loc_180024400
0x1800243ef  test    rax, rax
0x1800243f2  jz      short loc_180024400
0x1800243f4  xor     ebx, ebx
0x1800243f6  cmp     dword ptr [rax], 48h ; 'H'
0x1800243f9  setnz   bl
0x1800243fc  jmp     short loc_180024400
0x1800243fe  xor     ebx, ebx
0x180024400  mov     rbp, [rsp+48h+arg_8]
0x180024405  mov     eax, ebx
0x180024407  mov     rbx, [rsp+48h+arg_0]
0x18002440c  add     rsp, 30h
0x180024410  pop     r14
0x180024412  pop     rdi
0x180024413  pop     rsi
0x180024414  retn
```
