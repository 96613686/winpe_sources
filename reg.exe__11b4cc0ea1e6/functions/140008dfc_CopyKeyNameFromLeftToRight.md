# CopyKeyNameFromLeftToRight

- ea: `0x140008dfc`
- end: `0x140008f07`
- name: `CopyKeyNameFromLeftToRight`
- size: `267`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140008fe8`

## callees

- `0x140002b70`
- `0x140008dfc`
- `0x14000c62c`
- `0x14000cd48`
- `0x14000daa4`
- `0x14000e450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008e3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140008e3e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140008e7e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140008eb4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140008e7e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140008eb4`

## string_xrefs

- `0x140008e50`: `COMPARE`

## pseudocode

```c
__int64 __fastcall CopyKeyNameFromLeftToRight(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 ResString2FromModule; // rax
  const WCHAR *v6; // rcx
  int v7; // eax
  unsigned int v8; // esi
  _WORD *Memory; // rax
  const WCHAR *v10; // rcx
  int v11; // eax
  unsigned int v12; // esi
  _WORD *v13; // rax
  __int64 v15; // rcx

  if ( !a1 || !a2 )
  {
    v15 = 87;
LABEL_17:
    SaveErrorMessage(v15);
    return 0;
  }
  if ( *(_DWORD *)(a2 + 16) != 1 || a1[1] == -2147483646 || a1[1] == -2147483645 )
  {
    *(_QWORD *)(a2 + 8) = a1[1];
    v6 = (const WCHAR *)a1[11];
    if ( v6 )
      v7 = lstrlenW(v6);
    else
      v7 = 0;
    v8 = v7 + 1;
    Memory = AllocateMemory((unsigned int)(2 * (v7 + 1)));
    *(_QWORD *)(a2 + 88) = Memory;
    if ( Memory )
    {
      StringCopyW(Memory, (_WORD *)a1[11], v8);
      v10 = (const WCHAR *)a1[10];
      v11 = v10 ? lstrlenW(v10) : 0;
      v12 = v11 + 1;
      v13 = AllocateMemory((unsigned int)(2 * (v11 + 1)));
      *(_QWORD *)(a2 + 80) = v13;
      if ( v13 )
      {
        StringCopyW(v13, (_WORD *)a1[10], v12);
        return 1;
      }
    }
    v15 = 14;
    goto LABEL_17;
  }
  SetLastError(0x800401E4);
  ResString2FromModule = GetResString2FromModule(v4, 105, 0);
  SetReason2(1, ResString2FromModule, L"COMPARE");
  return 0;
}

```

## disassembly

```asm
0x140008dfc  mov     [rsp+arg_0], rbx
0x140008e01  mov     [rsp+arg_8], rsi
0x140008e06  push    rdi
0x140008e07  sub     rsp, 20h
0x140008e0b  mov     rdi, rdx
0x140008e0e  mov     rbx, rcx
0x140008e11  test    rcx, rcx
0x140008e14  jz      loc_140008EEB
0x140008e1a  test    rdx, rdx
0x140008e1d  jz      loc_140008EEB
0x140008e23  cmp     dword ptr [rdx+10h], 1
0x140008e27  jnz     short loc_140008E69
0x140008e29  mov     rax, [rcx+8]
0x140008e2d  add     rax, 7FFFFFFEh
0x140008e33  cmp     rax, 1
0x140008e37  jbe     short loc_140008E69
0x140008e39  mov     ecx, 800401E4h; dwErrCode
0x140008e3e  call    cs:__imp_SetLastError
0x140008e44  xor     r8d, r8d
0x140008e47  lea     edx, [r8+69h]
0x140008e4b  call    GetResString2FromModule
0x140008e50  lea     r8, aCompare_0; "COMPARE"
0x140008e57  mov     rdx, rax
0x140008e5a  mov     ecx, 1
0x140008e5f  call    SetReason2
0x140008e64  jmp     loc_140008EF5
0x140008e69  mov     rax, [rcx+8]
0x140008e6d  mov     [rdx+8], rax
0x140008e71  mov     rcx, [rcx+58h]; lpString
0x140008e75  test    rcx, rcx
0x140008e78  jnz     short loc_140008E7E
0x140008e7a  xor     eax, eax
0x140008e7c  jmp     short loc_140008E84
0x140008e7e  call    cs:__imp_lstrlenW
0x140008e84  lea     esi, [rax+1]
0x140008e87  lea     ecx, [rsi+rsi]; dwBytes
0x140008e8a  call    AllocateMemory
0x140008e8f  mov     [rdi+58h], rax
0x140008e93  test    rax, rax
0x140008e96  jz      short loc_140008EE4
0x140008e98  mov     rdx, [rbx+58h]
0x140008e9c  mov     r8d, esi
0x140008e9f  mov     rcx, rax
0x140008ea2  call    StringCopyW
0x140008ea7  mov     rcx, [rbx+50h]; lpString
0x140008eab  test    rcx, rcx
0x140008eae  jnz     short loc_140008EB4
0x140008eb0  xor     eax, eax
0x140008eb2  jmp     short loc_140008EBA
0x140008eb4  call    cs:__imp_lstrlenW
0x140008eba  lea     esi, [rax+1]
0x140008ebd  lea     ecx, [rsi+rsi]; dwBytes
0x140008ec0  call    AllocateMemory
0x140008ec5  mov     [rdi+50h], rax
0x140008ec9  test    rax, rax
0x140008ecc  jz      short loc_140008EE4
0x140008ece  mov     rdx, [rbx+50h]
0x140008ed2  mov     r8d, esi
0x140008ed5  mov     rcx, rax
0x140008ed8  call    StringCopyW
0x140008edd  mov     eax, 1
0x140008ee2  jmp     short loc_140008EF7
0x140008ee4  mov     ecx, 0Eh
0x140008ee9  jmp     short loc_140008EF0
0x140008eeb  mov     ecx, 57h ; 'W'
0x140008ef0  call    SaveErrorMessage
0x140008ef5  xor     eax, eax
0x140008ef7  mov     rbx, [rsp+28h+arg_0]
0x140008efc  mov     rsi, [rsp+28h+arg_8]
0x140008f01  add     rsp, 20h
0x140008f05  pop     rdi
0x140008f06  retn
```
