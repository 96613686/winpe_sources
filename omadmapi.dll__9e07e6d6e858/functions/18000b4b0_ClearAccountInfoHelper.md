# ClearAccountInfoHelper

- ea: `0x18000b4b0`
- end: `0x18000b522`
- name: `ClearAccountInfoHelper`
- size: `114`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000e5d4`

## callees

- `0x18000b4b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000b4e6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000b4e6`

## pseudocode

```c
__int64 __fastcall ClearAccountInfoHelper(HKEY hKey, int a2, unsigned int a3, __int64 a4)
{
  unsigned int v4; // ebx
  unsigned int v5; // edi
  __int64 v10; // rdx
  LSTATUS v11; // eax

  v4 = 0;
  v5 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      v10 = 32LL * v5;
      if ( (a2 & *(_DWORD *)(v10 + a4 + 8)) != 0 )
      {
        v11 = RegDeleteValueW(hKey, *(LPCWSTR *)(v10 + a4));
        if ( (v11 & 0xFFFFFFFD) != 0 )
          break;
      }
      if ( ++v5 >= a3 )
        return v4;
    }
    if ( v11 > 0 )
      return (unsigned __int16)v11 | 0x80070000;
    else
      return (unsigned int)v11;
  }
  return v4;
}

```

## disassembly

```asm
0x18000b4b0  push    rbx
0x18000b4b2  push    rbp
0x18000b4b3  push    rsi
0x18000b4b4  push    rdi
0x18000b4b5  push    r14
0x18000b4b7  push    r15
0x18000b4b9  sub     rsp, 28h
0x18000b4bd  xor     ebx, ebx
0x18000b4bf  xor     edi, edi
0x18000b4c1  mov     rbp, r9
0x18000b4c4  mov     esi, r8d
0x18000b4c7  mov     r14d, edx
0x18000b4ca  mov     r15, rcx
0x18000b4cd  test    r8d, r8d
0x18000b4d0  jz      short loc_18000B512
0x18000b4d2  mov     edx, edi
0x18000b4d4  shl     rdx, 5
0x18000b4d8  test    [rdx+rbp+8], r14d
0x18000b4dd  jz      short loc_18000B4F9
0x18000b4df  mov     rdx, [rdx+rbp]; lpValueName
0x18000b4e3  mov     rcx, r15; hKey
0x18000b4e6  call    cs:__imp_RegDeleteValueW
0x18000b4ed  nop     dword ptr [rax+rax+00h]
0x18000b4f2  test    eax, 0FFFFFFFDh
0x18000b4f7  jnz     short loc_18000B501
0x18000b4f9  inc     edi
0x18000b4fb  cmp     edi, esi
0x18000b4fd  jb      short loc_18000B4D2
0x18000b4ff  jmp     short loc_18000B512
0x18000b501  test    eax, eax
0x18000b503  jg      short loc_18000B509
0x18000b505  mov     ebx, eax
0x18000b507  jmp     short loc_18000B512
0x18000b509  movzx   ebx, ax
0x18000b50c  or      ebx, 80070000h
0x18000b512  mov     eax, ebx
0x18000b514  add     rsp, 28h
0x18000b518  pop     r15
0x18000b51a  pop     r14
0x18000b51c  pop     rdi
0x18000b51d  pop     rsi
0x18000b51e  pop     rbp
0x18000b51f  pop     rbx
0x18000b520  retn
```
