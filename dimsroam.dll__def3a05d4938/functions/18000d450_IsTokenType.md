# IsTokenType

- ea: `0x18000d450`
- end: `0x18000d501`
- name: `IsTokenType`
- size: `177`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006230`

## callees

- `0x18000d450`
- `0x18000d508`
- `0x18000d678`
- `0x18000d8d0`

## pseudocode

```c
__int64 __fastcall IsTokenType(__int64 a1, int a2)
{
  int v3; // r10d
  DWORD v4; // edx
  int v6; // eax
  unsigned __int64 i; // rcx
  WCHAR v9; // ax
  WCHAR szContainer[264]; // [rsp+20h] [rbp-228h] BYREF

  v3 = *(unsigned __int8 *)(a1 + 1) - 48;
  v4 = 1;
  v6 = 1 << (*(_BYTE *)(a1 + 1) - 48);
  if ( (v6 & a2) != 0 )
    return 1;
  if ( a2 >= 0 )
    return 0;
  if ( (v6 & 6) == 0 )
  {
    if ( (v6 & 0x18) != 0 )
      return drr_IsEncryptionCert((BYTE *)(a1 + 132), *(_DWORD *)(a1 + 128));
    return 0;
  }
  for ( i = 0; i < 0x5D; ++i )
  {
    v9 = *(unsigned __int8 *)(a1 + i + 3);
    if ( !(_BYTE)v9 )
      break;
    szContainer[i] = v9;
  }
  szContainer[i] = 0;
  if ( v3 != 1 )
    v4 = 3;
  return drr_IsEncryptionKey(szContainer, v4);
}

```

## disassembly

```asm
0x18000d450  sub     rsp, 248h
0x18000d457  mov     rax, cs:__security_cookie
0x18000d45e  xor     rax, rsp
0x18000d461  mov     [rsp+248h+var_18], rax
0x18000d469  movzx   r10d, byte ptr [rcx+1]
0x18000d46e  mov     r9d, edx
0x18000d471  add     r10d, 0FFFFFFD0h
0x18000d475  mov     edx, 1
0x18000d47a  mov     r8, rcx
0x18000d47d  mov     eax, edx
0x18000d47f  mov     ecx, r10d
0x18000d482  shl     eax, cl
0x18000d484  test    r9d, eax
0x18000d487  jz      short loc_18000D48D
0x18000d489  mov     eax, edx
0x18000d48b  jmp     short loc_18000D4E9
0x18000d48d  test    r9d, r9d
0x18000d490  jns     short loc_18000D4E7
0x18000d492  test    al, 6
0x18000d494  jz      short loc_18000D4CE
0x18000d496  xor     ecx, ecx
0x18000d498  movzx   eax, byte ptr [r8+rcx+3]
0x18000d49e  test    al, al
0x18000d4a0  jz      short loc_18000D4B0
0x18000d4a2  mov     [rsp+rcx*2+248h+szContainer], ax
0x18000d4a7  add     rcx, rdx
0x18000d4aa  cmp     rcx, 5Dh ; ']'
0x18000d4ae  jb      short loc_18000D498
0x18000d4b0  xor     eax, eax
0x18000d4b2  mov     [rsp+rcx*2+248h+szContainer], ax
0x18000d4b7  cmp     r10d, edx
0x18000d4ba  mov     eax, 3
0x18000d4bf  lea     rcx, [rsp+248h+szContainer]; szContainer
0x18000d4c4  cmovnz  edx, eax; dwProvType
0x18000d4c7  call    _drr_IsEncryptionKey
0x18000d4cc  jmp     short loc_18000D4E9
0x18000d4ce  test    al, 18h
0x18000d4d0  jz      short loc_18000D4E7
0x18000d4d2  mov     edx, [r8+80h]; cbElement
0x18000d4d9  lea     rcx, [r8+84h]; pbElement
0x18000d4e0  call    _drr_IsEncryptionCert
0x18000d4e5  jmp     short loc_18000D4E9
0x18000d4e7  xor     eax, eax
0x18000d4e9  mov     rcx, [rsp+248h+var_18]
0x18000d4f1  xor     rcx, rsp; StackCookie
0x18000d4f4  call    __security_check_cookie
0x18000d4f9  add     rsp, 248h
0x18000d500  retn
```
