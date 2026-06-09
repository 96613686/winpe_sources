# IsSlotInUse(int)

- ea: `0x180012d00`
- end: `0x180012f92`
- name: `?IsSlotInUse@@YAHH@Z`
- size: `658`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800127b0`

## callees

- `0x180012d00`
- `0x18001e4c0`
- `0x180047fec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012f33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012f33`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180012d5f`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180012d5f`

## pseudocode

```c
_BOOL8 __fastcall IsSlotInUse(int a1)
{
  __int64 v1; // rdi
  int v2; // ecx
  int v3; // eax
  char *v4; // rdx
  int v5; // r11d
  int v6; // r8d
  int v7; // r11d
  int v8; // r11d
  int v9; // r10d
  char *v10; // rdx
  int v11; // ecx
  int v12; // r8d
  int v13; // r10d
  int v14; // r10d
  int v15; // r9d
  char *v16; // rdx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // r9d
  int v21; // ebx
  char *v22; // r8
  int v23; // ecx
  int v24; // edx
  int v25; // ebx
  int v26; // ebx
  WCHAR Buffer[5]; // [rsp+20h] [rbp-78h] BYREF
  char v29; // [rsp+2Ah] [rbp-6Eh] BYREF
  __int16 v30; // [rsp+3Ah] [rbp-5Eh]
  char v31; // [rsp+3Ch] [rbp-5Ch] BYREF
  __int16 v32; // [rsp+4Ch] [rbp-4Ch]
  char v33; // [rsp+4Eh] [rbp-4Ah] BYREF
  __int16 v34; // [rsp+5Eh] [rbp-3Ah]
  char v35; // [rsp+60h] [rbp-38h] BYREF
  __int16 v36; // [rsp+70h] [rbp-28h]
  __int16 v37; // [rsp+72h] [rbp-26h]

  v1 = 2LL * a1;
  v2 = *((_DWORD *)&g_OutstandingObjectTable + 4 * a1 + 3);
  if ( !v2 )
    return 0;
  if ( HIWORD(v2) )
    return 0;
  if ( !(_WORD)v2 )
    return 0;
  if ( GlobalGetAtomNameW(v2, Buffer, 42) != 41 )
    return 0;
  v3 = memcmp_0(Buffer, L"MSAA:", 0xAu);
  if ( v3 || v30 != 58 || v32 != 58 || v34 != 58 || v36 != 58 || v37 )
    return 0;
  v4 = &v29;
  v5 = 0;
  while ( v3 < 8 )
  {
    v6 = *(unsigned __int16 *)v4;
    v7 = 16 * v5;
    if ( (unsigned __int16)(v6 - 48) <= 9u )
    {
      v8 = v7 - 48;
      goto LABEL_15;
    }
    if ( (unsigned __int16)(v6 - 65) > 5u )
    {
      if ( (unsigned __int16)(v6 - 97) > 5u )
        return 0;
      v8 = v7 - 87;
LABEL_15:
      v5 = v6 + v8;
      ++v3;
      v4 += 2;
    }
    else
    {
      ++v3;
      v5 = v6 + v7 - 55;
      v4 += 2;
    }
  }
  v9 = 0;
  v10 = &v31;
  v11 = 0;
  while ( v11 < 8 )
  {
    v12 = *(unsigned __int16 *)v10;
    v13 = 16 * v9;
    if ( (unsigned __int16)(v12 - 48) <= 9u )
    {
      v14 = v13 - 48;
      goto LABEL_22;
    }
    if ( (unsigned __int16)(v12 - 65) > 5u )
    {
      if ( (unsigned __int16)(v12 - 97) > 5u )
        return 0;
      v14 = v13 - 87;
LABEL_22:
      v9 = v12 + v14;
      ++v11;
      v10 += 2;
    }
    else
    {
      ++v11;
      v9 = v12 + v13 - 55;
      v10 += 2;
    }
  }
  v15 = 0;
  v16 = &v33;
  v17 = 0;
  while ( v17 < 8 )
  {
    v18 = *(unsigned __int16 *)v16;
    v19 = 16 * v15;
    if ( (unsigned __int16)(v18 - 48) <= 9u )
    {
      v20 = v19 - 48;
      goto LABEL_29;
    }
    if ( (unsigned __int16)(v18 - 65) > 5u )
    {
      if ( (unsigned __int16)(v18 - 97) > 5u )
        return 0;
      v20 = v19 - 87;
LABEL_29:
      v15 = v18 + v20;
      ++v17;
      v16 += 2;
    }
    else
    {
      ++v17;
      v15 = v18 + v19 - 55;
      v16 += 2;
    }
  }
  v21 = 0;
  v22 = &v35;
  v23 = 0;
  while ( v23 < 8 )
  {
    v24 = *(unsigned __int16 *)v22;
    v25 = 16 * v21;
    if ( (unsigned __int16)(v24 - 48) <= 9u )
    {
      v26 = v25 - 48;
      goto LABEL_36;
    }
    if ( (unsigned __int16)(v24 - 65) > 5u )
    {
      if ( (unsigned __int16)(v24 - 97) > 5u )
        return 0;
      v26 = v25 - 87;
LABEL_36:
      v21 = v24 + v26;
      ++v23;
      v22 += 2;
    }
    else
    {
      ++v23;
      v21 = v24 + v25 - 55;
      v22 += 2;
    }
  }
  return v5 == *((_DWORD *)&g_OutstandingObjectTable + 2 * v1)
      && v9 == *((_DWORD *)&g_OutstandingObjectTable + 2 * v1 + 1)
      && v15 == *((_DWORD *)&g_OutstandingObjectTable + 2 * v1 + 2)
      && v21 == GetCurrentProcessId();
}

```

## disassembly

```asm
0x180012d00  mov     [rsp+arg_8], rbx
0x180012d05  mov     [rsp+arg_10], rsi
0x180012d0a  push    rdi
0x180012d0b  sub     rsp, 90h
0x180012d12  mov     rax, cs:__security_cookie
0x180012d19  xor     rax, rsp
0x180012d1c  mov     [rsp+98h+var_18], rax
0x180012d24  movsxd  rdi, ecx
0x180012d27  lea     rsi, ?g_OutstandingObjectTable@@3PAUOutstandingObjectEntry@@A; OutstandingObjectEntry near * g_OutstandingObjectTable
0x180012d2e  add     rdi, rdi
0x180012d31  mov     ecx, [rsi+rdi*8+0Ch]; nAtom
0x180012d35  test    ecx, ecx
0x180012d37  jz      loc_180012EF6
0x180012d3d  mov     eax, ecx
0x180012d3f  shr     eax, 10h
0x180012d42  test    ax, ax
0x180012d45  jnz     loc_180012EF6
0x180012d4b  test    cx, cx
0x180012d4e  jz      loc_180012EF6
0x180012d54  mov     r8d, 2Ah ; '*'; nSize
0x180012d5a  lea     rdx, [rsp+98h+Buffer]; lpBuffer
0x180012d5f  call    cs:__imp_GlobalGetAtomNameW
0x180012d65  cmp     eax, 29h ; ')'
0x180012d68  jnz     loc_180012EF6
0x180012d6e  mov     r8d, 0Ah; Size
0x180012d74  lea     rdx, aMsaa_0; "MSAA:"
0x180012d7b  lea     rcx, [rsp+98h+Buffer]; Buf1
0x180012d80  call    memcmp_0
0x180012d85  test    eax, eax
0x180012d87  jnz     loc_180012EF6
0x180012d8d  cmp     [rsp+98h+var_5E], 3Ah ; ':'
0x180012d93  jnz     loc_180012EF6
0x180012d99  cmp     [rsp+98h+var_4C], 3Ah ; ':'
0x180012d9f  jnz     loc_180012EF6
0x180012da5  cmp     [rsp+98h+var_3A], 3Ah ; ':'
0x180012dab  jnz     loc_180012EF6
0x180012db1  cmp     [rsp+98h+var_28], 3Ah ; ':'
0x180012db7  jnz     loc_180012EF6
0x180012dbd  cmp     [rsp+98h+var_26], ax
0x180012dc2  jnz     loc_180012EF6
0x180012dc8  lea     rdx, [rsp+98h+var_6E]
0x180012dcd  xor     r11d, r11d
0x180012dd0  cmp     eax, 8
0x180012dd3  jge     short loc_180012E13
0x180012dd5  movzx   r8d, word ptr [rdx]
0x180012dd9  shl     r11d, 4
0x180012ddd  lea     ecx, [r8-30h]
0x180012de1  cmp     cx, 9
0x180012de5  ja      short loc_180012DF6
0x180012de7  add     r11d, 0FFFFFFD0h
0x180012deb  add     r11d, r8d
0x180012dee  inc     eax
0x180012df0  add     rdx, 2
0x180012df4  jmp     short loc_180012DD0
0x180012df6  lea     ecx, [r8-41h]
0x180012dfa  cmp     cx, 5
0x180012dfe  ja      loc_180012F44
0x180012e04  add     r11d, 0FFFFFFC9h
0x180012e08  inc     eax
0x180012e0a  add     r11d, r8d
0x180012e0d  add     rdx, 2
0x180012e11  jmp     short loc_180012DD0
0x180012e13  xor     r10d, r10d
0x180012e16  lea     rdx, [rsp+98h+var_5C]
0x180012e1b  xor     ecx, ecx
0x180012e1d  nop     dword ptr [rax]
0x180012e20  cmp     ecx, 8
0x180012e23  jge     short loc_180012E63
0x180012e25  movzx   r8d, word ptr [rdx]
0x180012e29  shl     r10d, 4
0x180012e2d  lea     eax, [r8-30h]
0x180012e31  cmp     ax, 9
0x180012e35  ja      short loc_180012E46
0x180012e37  add     r10d, 0FFFFFFD0h
0x180012e3b  add     r10d, r8d
0x180012e3e  inc     ecx
0x180012e40  add     rdx, 2
0x180012e44  jmp     short loc_180012E20
0x180012e46  lea     eax, [r8-41h]
0x180012e4a  cmp     ax, 5
0x180012e4e  ja      loc_180012F57
0x180012e54  add     r10d, 0FFFFFFC9h
0x180012e58  inc     ecx
0x180012e5a  add     r10d, r8d
0x180012e5d  add     rdx, 2
0x180012e61  jmp     short loc_180012E20
0x180012e63  xor     r9d, r9d
0x180012e66  lea     rdx, [rsp+98h+var_4A]
0x180012e6b  xor     ecx, ecx
0x180012e6d  nop     dword ptr [rax]
0x180012e70  cmp     ecx, 8
0x180012e73  jge     short loc_180012EB3
0x180012e75  movzx   r8d, word ptr [rdx]
0x180012e79  shl     r9d, 4
0x180012e7d  lea     eax, [r8-30h]
0x180012e81  cmp     ax, 9
0x180012e85  ja      short loc_180012E96
0x180012e87  add     r9d, 0FFFFFFD0h
0x180012e8b  add     r9d, r8d
0x180012e8e  inc     ecx
0x180012e90  add     rdx, 2
0x180012e94  jmp     short loc_180012E70
0x180012e96  lea     eax, [r8-41h]
0x180012e9a  cmp     ax, 5
0x180012e9e  ja      loc_180012F6A
0x180012ea4  add     r9d, 0FFFFFFC9h
0x180012ea8  inc     ecx
0x180012eaa  add     r9d, r8d
0x180012ead  add     rdx, 2
0x180012eb1  jmp     short loc_180012E70
0x180012eb3  xor     ebx, ebx
0x180012eb5  lea     r8, [rsp+98h+var_38]
0x180012eba  xor     ecx, ecx
0x180012ebc  nop     dword ptr [rax+00h]
0x180012ec0  cmp     ecx, 8
0x180012ec3  jge     short loc_180012EE2
0x180012ec5  movzx   edx, word ptr [r8]
0x180012ec9  shl     ebx, 4
0x180012ecc  lea     eax, [rdx-30h]
0x180012ecf  cmp     ax, 9
0x180012ed3  ja      short loc_180012F1D
0x180012ed5  add     ebx, 0FFFFFFD0h
0x180012ed8  add     ebx, edx
0x180012eda  inc     ecx
0x180012edc  add     r8, 2
0x180012ee0  jmp     short loc_180012EC0
0x180012ee2  cmp     r11d, [rsi+rdi*8]
0x180012ee6  jnz     short loc_180012EF6
0x180012ee8  cmp     r10d, [rsi+rdi*8+4]
0x180012eed  jnz     short loc_180012EF6
0x180012eef  cmp     r9d, [rsi+rdi*8+8]
0x180012ef4  jz      short loc_180012F33
0x180012ef6  xor     eax, eax
0x180012ef8  mov     rcx, [rsp+98h+var_18]
0x180012f00  xor     rcx, rsp; StackCookie
0x180012f03  call    __security_check_cookie
0x180012f08  lea     r11, [rsp+98h+var_8]
0x180012f10  mov     rbx, [r11+18h]
0x180012f14  mov     rsi, [r11+20h]
0x180012f18  mov     rsp, r11
0x180012f1b  pop     rdi
0x180012f1c  retn
0x180012f1d  lea     eax, [rdx-41h]
0x180012f20  cmp     ax, 5
0x180012f24  ja      short loc_180012F7D
0x180012f26  add     ebx, 0FFFFFFC9h
0x180012f29  inc     ecx
0x180012f2b  add     ebx, edx
0x180012f2d  add     r8, 2
0x180012f31  jmp     short loc_180012EC0
0x180012f33  call    cs:__imp_GetCurrentProcessId
0x180012f39  cmp     ebx, eax
0x180012f3b  jnz     short loc_180012EF6
0x180012f3d  mov     eax, 1
0x180012f42  jmp     short loc_180012EF8
0x180012f44  lea     ecx, [r8-61h]
0x180012f48  cmp     cx, 5
0x180012f4c  ja      short loc_180012EF6
0x180012f4e  add     r11d, 0FFFFFFA9h
0x180012f52  jmp     loc_180012DEB
0x180012f57  lea     eax, [r8-61h]
0x180012f5b  cmp     ax, 5
0x180012f5f  ja      short loc_180012EF6
0x180012f61  add     r10d, 0FFFFFFA9h
0x180012f65  jmp     loc_180012E3B
0x180012f6a  lea     eax, [r8-61h]
0x180012f6e  cmp     ax, 5
0x180012f72  ja      short loc_180012EF6
0x180012f74  add     r9d, 0FFFFFFA9h
0x180012f78  jmp     loc_180012E8B
0x180012f7d  lea     eax, [rdx-61h]
0x180012f80  cmp     ax, 5
0x180012f84  ja      loc_180012EF6
0x180012f8a  add     ebx, 0FFFFFFA9h
0x180012f8d  jmp     loc_180012ED8
```
