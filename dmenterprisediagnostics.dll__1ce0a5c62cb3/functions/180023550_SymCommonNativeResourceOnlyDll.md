# SymCommonNativeResourceOnlyDll

- ea: `0x180023550`
- end: `0x180023645`
- name: `SymCommonNativeResourceOnlyDll`
- size: `245`
- prototype: `__int64 __fastcall(PVOID BaseAddress)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022c08`

## callees

- `0x180023550`

## import_xrefs

- `ntdll!RtlImageDirectoryEntryToData` at `0x180023585`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800235a1`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800235b9`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180023612`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180023585`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800235a1`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800235b9`
- `ntdll!RtlImageDirectoryEntryToData` at `0x180023612`

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
0x180023550  mov     rax, rsp
0x180023553  mov     [rax+8], rbx
0x180023557  mov     [rax+10h], rbp
0x18002355b  push    rsi
0x18002355c  push    rdi
0x18002355d  push    r14
0x18002355f  sub     rsp, 30h
0x180023563  xor     r8d, r8d; Directory
0x180023566  mov     dword ptr [rax-28h], 0
0x18002356d  lea     r9, [rax-28h]; Size
0x180023571  mov     dword ptr [rax+20h], 0
0x180023578  mov     sil, dl
0x18002357b  mov     dword ptr [rax+18h], 0
0x180023582  mov     rdi, rcx
0x180023585  call    cs:__imp_RtlImageDirectoryEntryToData
0x18002358b  mov     ebx, 1
0x180023590  lea     r9, [rsp+48h+Size]; Size
0x180023595  mov     r8d, ebx; Directory
0x180023598  mov     dl, sil; MappedAsImage
0x18002359b  mov     rcx, rdi; BaseAddress
0x18002359e  mov     r14, rax
0x1800235a1  call    cs:__imp_RtlImageDirectoryEntryToData
0x1800235a7  lea     r8d, [rbx+1]; Directory
0x1800235ab  mov     dl, sil; MappedAsImage
0x1800235ae  lea     r9, [rsp+48h+arg_10]; Size
0x1800235b3  mov     rcx, rdi; BaseAddress
0x1800235b6  mov     rbp, rax
0x1800235b9  call    cs:__imp_RtlImageDirectoryEntryToData
0x1800235bf  test    rax, rax
0x1800235c2  jz      short loc_18002362E
0x1800235c4  cmp     [rsp+48h+arg_10], 0
0x1800235c9  jz      short loc_18002362E
0x1800235cb  test    rbp, rbp
0x1800235ce  jnz     short loc_18002362E
0x1800235d0  cmp     [rsp+48h+Size], ebp
0x1800235d4  jnz     short loc_18002362E
0x1800235d6  test    r14, r14
0x1800235d9  jnz     short loc_18002362E
0x1800235db  cmp     [rsp+48h+var_28], r14d
0x1800235e0  jnz     short loc_18002362E
0x1800235e2  mov     ecx, [rdi+3Ch]
0x1800235e5  mov     edx, 10Bh
0x1800235ea  movzx   eax, word ptr [rcx+rdi+18h]
0x1800235ef  sub     ax, dx
0x1800235f2  mov     edx, 0FEFFh
0x1800235f7  test    dx, ax
0x1800235fa  jnz     short loc_18002362E
0x1800235fc  cmp     [rcx+rdi+28h], r14d
0x180023601  jnz     short loc_18002362E
0x180023603  lea     r8d, [rbx+0Dh]; Directory
0x180023607  mov     dl, sil; MappedAsImage
0x18002360a  lea     r9, [rsp+48h+arg_10]; Size
0x18002360f  mov     rcx, rdi; BaseAddress
0x180023612  call    cs:__imp_RtlImageDirectoryEntryToData
0x180023618  cmp     [rsp+48h+arg_10], 48h ; 'H'
0x18002361d  jnz     short loc_180023630
0x18002361f  test    rax, rax
0x180023622  jz      short loc_180023630
0x180023624  xor     ebx, ebx
0x180023626  cmp     dword ptr [rax], 48h ; 'H'
0x180023629  setnz   bl
0x18002362c  jmp     short loc_180023630
0x18002362e  xor     ebx, ebx
0x180023630  mov     rbp, [rsp+48h+arg_8]
0x180023635  mov     eax, ebx
0x180023637  mov     rbx, [rsp+48h+arg_0]
0x18002363c  add     rsp, 30h
0x180023640  pop     r14
0x180023642  pop     rdi
0x180023643  pop     rsi
0x180023644  retn
```
