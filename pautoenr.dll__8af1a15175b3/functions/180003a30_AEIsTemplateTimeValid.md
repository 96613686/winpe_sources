# AEIsTemplateTimeValid

- ea: `0x180003a30`
- end: `0x180003ab1`
- name: `AEIsTemplateTimeValid`
- size: `129`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f50`

## callees

- `0x180003740`
- `0x180003a30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003a6f`
- `msvcrt!_wcsicmp` at `0x180003a6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a94`

## pseudocode

```c
__int64 __fastcall AEIsTemplateTimeValid(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  wchar_t *v4; // rdi
  unsigned int i; // ebp

  v3 = 0;
  v4 = AEGetTemplateName(a2);
  if ( v4 )
  {
    for ( i = 0; i < *(_DWORD *)(a1 + 8); ++i )
    {
      if ( !_wcsicmp(v4, *(const wchar_t **)(*(_QWORD *)a1 + 16LL * i)) )
        break;
    }
    if ( i < *(_DWORD *)(a1 + 8) )
      v3 = *(_DWORD *)(*(_QWORD *)a1 + 16LL * i + 8);
    LocalFree(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x180003a30  mov     [rsp+arg_8], rbx
0x180003a35  mov     [rsp+arg_10], rsi
0x180003a3a  push    rdi
0x180003a3b  sub     rsp, 20h
0x180003a3f  mov     rsi, rcx
0x180003a42  xor     ebx, ebx
0x180003a44  mov     rcx, rdx
0x180003a47  call    AEGetTemplateName
0x180003a4c  mov     rdi, rax
0x180003a4f  test    rax, rax
0x180003a52  jz      short loc_180003A9F
0x180003a54  mov     [rsp+28h+arg_0], rbp
0x180003a59  xor     ebp, ebp
0x180003a5b  cmp     [rsi+8], ebx
0x180003a5e  jbe     short loc_180003A80
0x180003a60  mov     rdx, [rsi]
0x180003a63  mov     rcx, rdi; String1
0x180003a66  mov     eax, ebp
0x180003a68  add     rax, rax
0x180003a6b  mov     rdx, [rdx+rax*8]; String2
0x180003a6f  call    cs:__imp__wcsicmp
0x180003a75  test    eax, eax
0x180003a77  jz      short loc_180003A80
0x180003a79  inc     ebp
0x180003a7b  cmp     ebp, [rsi+8]
0x180003a7e  jb      short loc_180003A60
0x180003a80  cmp     ebp, [rsi+8]
0x180003a83  jnb     short loc_180003A91
0x180003a85  mov     rbx, [rsi]
0x180003a88  mov     eax, ebp
0x180003a8a  add     rax, rax
0x180003a8d  mov     ebx, [rbx+rax*8+8]
0x180003a91  mov     rcx, rdi; hMem
0x180003a94  call    cs:__imp_LocalFree
0x180003a9a  mov     rbp, [rsp+28h+arg_0]
0x180003a9f  mov     rsi, [rsp+28h+arg_10]
0x180003aa4  mov     eax, ebx
0x180003aa6  mov     rbx, [rsp+28h+arg_8]
0x180003aab  add     rsp, 20h
0x180003aaf  pop     rdi
0x180003ab0  retn
```
