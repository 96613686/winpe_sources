# BaseRegDeleteKeyExInternal

- ea: `0x18001c648`
- end: `0x18001c72e`
- name: `BaseRegDeleteKeyExInternal`
- size: `230`
- prototype: `ULONG __fastcall(__int64, unsigned __int16 *, __int16, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800194e0`
- `0x1800195b0`

## callees

- `0x18001c648`
- `0x18001d698`

## import_xrefs

- `ntdll!NtDeleteKey` at `0x18001c6fb`
- `ntdll!NtDeleteKey` at `0x18001c6fb`
- `ntdll!RtlNtStatusToDosError` at `0x18001c70f`
- `ntdll!RtlNtStatusToDosError` at `0x18001c70f`
- `ntdll!NtClose` at `0x18001c707`
- `ntdll!NtClose` at `0x18001c707`

## pseudocode

```c
ULONG __fastcall BaseRegDeleteKeyExInternal(__int64 a1, unsigned __int16 *a2, __int16 a3, int a4)
{
  unsigned int v7; // r9d
  __int64 v8; // rcx
  int v9; // ebx
  int v11; // [rsp+20h] [rbp-40h]
  int v12[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+38h] [rbp-28h]
  unsigned __int16 *v14; // [rsp+40h] [rbp-20h]
  int v15; // [rsp+48h] [rbp-18h]
  int v16; // [rsp+4Ch] [rbp-14h]
  __int128 v17; // [rsp+50h] [rbp-10h]
  HANDLE KeyHandle; // [rsp+78h] [rbp+18h] BYREF

  v12[1] = 0;
  v16 = 0;
  KeyHandle = 0;
  if ( !a2 )
    return 87;
  v7 = *a2;
  if ( v7 < 2 )
    return 87;
  v8 = *((_QWORD *)a2 + 1);
  if ( !v8 || (v7 & 1) != 0 || *(_WORD *)(v8 + 2 * ((unsigned __int64)*a2 >> 1) - 2) || a4 )
    return 87;
  v13 = a1;
  *a2 = v7 - 2;
  v14 = a2;
  v12[0] = 48;
  v15 = 64;
  v17 = 0;
  v9 = Wow64NtOpenKey((int)&KeyHandle, a3 & 0x300 | 0x10000u, (int)v12, 0, v11);
  if ( v9 >= 0 )
  {
    v9 = NtDeleteKey(KeyHandle);
    NtClose(KeyHandle);
  }
  return RtlNtStatusToDosError(v9);
}

```

## disassembly

```asm
0x18001c648  mov     [rsp-8+arg_0], rbx
0x18001c64d  mov     [rsp-8+arg_10], rdi
0x18001c652  push    rbp
0x18001c653  mov     rbp, rsp
0x18001c656  sub     rsp, 60h
0x18001c65a  xor     edi, edi
0x18001c65c  mov     r10d, r8d
0x18001c65f  mov     [rbp+var_2C], edi
0x18001c662  mov     r11d, r9d
0x18001c665  mov     [rbp+var_14], edi
0x18001c668  mov     r8, rcx
0x18001c66b  mov     [rbp+KeyHandle], rdi
0x18001c66f  test    rdx, rdx
0x18001c672  jz      loc_18001C717
0x18001c678  movzx   r9d, word ptr [rdx]
0x18001c67c  cmp     r9d, 2
0x18001c680  jb      loc_18001C717
0x18001c686  mov     rcx, [rdx+8]
0x18001c68a  test    rcx, rcx
0x18001c68d  jz      loc_18001C717
0x18001c693  test    r9b, 1
0x18001c697  jnz     short loc_18001C717
0x18001c699  mov     eax, r9d
0x18001c69c  shr     rax, 1
0x18001c69f  cmp     [rcx+rax*2-2], di
0x18001c6a4  jnz     short loc_18001C717
0x18001c6a6  test    r11d, r11d
0x18001c6a9  jnz     short loc_18001C717
0x18001c6ab  sub     r9w, 2
0x18001c6b0  mov     [rbp+var_28], r8
0x18001c6b4  mov     [rdx], r9w
0x18001c6b8  lea     r8, [rbp+var_30]; int
0x18001c6bc  and     r10d, 300h
0x18001c6c3  mov     [rbp+var_20], rdx
0x18001c6c7  bts     r10d, 10h
0x18001c6cc  mov     [rbp+var_30], 30h ; '0'
0x18001c6d3  xorps   xmm0, xmm0
0x18001c6d6  mov     [rbp+var_18], 40h ; '@'
0x18001c6dd  mov     edx, r10d; int
0x18001c6e0  lea     rcx, [rbp+KeyHandle]; int
0x18001c6e4  xor     r9d, r9d; int
0x18001c6e7  movdqu  [rbp+var_10], xmm0
0x18001c6ec  call    Wow64NtOpenKey
0x18001c6f1  mov     ebx, eax
0x18001c6f3  test    eax, eax
0x18001c6f5  js      short loc_18001C70D
0x18001c6f7  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18001c6fb  call    cs:__imp_NtDeleteKey
0x18001c701  mov     rcx, [rbp+KeyHandle]; Handle
0x18001c705  mov     ebx, eax
0x18001c707  call    cs:__imp_NtClose
0x18001c70d  mov     ecx, ebx; Status
0x18001c70f  call    cs:__imp_RtlNtStatusToDosError
0x18001c715  jmp     short loc_18001C71C
0x18001c717  mov     eax, 57h ; 'W'
0x18001c71c  lea     r11, [rsp+60h+var_s0]
0x18001c721  mov     rbx, [r11+10h]
0x18001c725  mov     rdi, [r11+20h]
0x18001c729  mov     rsp, r11
0x18001c72c  pop     rbp
0x18001c72d  retn
```
