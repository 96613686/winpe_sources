# CMCreateTransformExtW

- ea: `0x18001d930`
- end: `0x18001da23`
- name: `CMCreateTransformExtW`
- size: `243`
- prototype: `HCMTRANSFORM __stdcall(LPLOGCOLORSPACEW lpColorSpace, LPDEVCHARACTER lpDevCharacter, LPDEVCHARACTER lpTargetDevCharacter, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001d7a0`
- `0x18001d930`
- `0x18001da5c`

## import_xrefs

- `mscms!OpenColorProfileW` at `0x18001d98b`
- `mscms!OpenColorProfileW` at `0x18001d98b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d972`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d999`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001d9fe`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001d9fe`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001d9ea`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18001d9ea`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001d9e1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001d9f5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001d9e1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18001d9f5`

## pseudocode

```c
HCMTRANSFORM __stdcall CMCreateTransformExtW(
        LPLOGCOLORSPACEW lpColorSpace,
        LPDEVCHARACTER lpDevCharacter,
        LPDEVCHARACTER lpTargetDevCharacter,
        DWORD dwFlags)
{
  void *v4; // rsi
  DWORD v7; // eax
  DWORD v8; // ebx
  HPROFILE v9; // r9
  DWORD LastError; // eax
  HGLOBAL v11; // rax
  HGLOBAL v12; // rax
  HCMTRANSFORM result; // rax
  PROFILE pProfile; // [rsp+30h] [rbp-38h] BYREF
  void *v15; // [rsp+70h] [rbp+8h] BYREF

  v15 = 0;
  v4 = 0;
  memset(&pProfile, 0, 20);
  v7 = FillProfileFromLogW(lpColorSpace, &pProfile, lpTargetDevCharacter);
  v8 = v7;
  if ( v7 )
  {
    SetLastError(v7);
  }
  else
  {
    v9 = OpenColorProfileW(&pProfile, 1u, 1u, 3u);
    if ( v9 )
    {
      LastError = CMCreateTransformExtInternal(
                    &v15,
                    dwFlags,
                    (unsigned int)lpColorSpace->lcsIntent,
                    v9,
                    *(_QWORD *)&lpColorSpace[1].lcsSize,
                    *(_QWORD *)&lpColorSpace[1].lcsSignature);
      v4 = v15;
    }
    else
    {
      LastError = GetLastError();
    }
    v8 = LastError;
  }
  if ( !lpColorSpace->lcsFilename[0] && pProfile.pProfileData )
  {
    v11 = GlobalHandle(pProfile.pProfileData);
    GlobalUnlock(v11);
    v12 = GlobalHandle(pProfile.pProfileData);
    GlobalFree(v12);
  }
  result = (HCMTRANSFORM)(unsigned __int8)v8;
  if ( !v8 )
    return v4;
  return result;
}

```

## disassembly

```asm
0x18001d930  mov     r11, rsp
0x18001d933  mov     [r11+10h], rbx
0x18001d937  mov     [r11+18h], rbp
0x18001d93b  push    rsi
0x18001d93c  push    rdi
0x18001d93d  push    r14
0x18001d93f  sub     rsp, 50h
0x18001d943  xor     r14d, r14d
0x18001d946  lea     rdx, [r11-38h]
0x18001d94a  xor     eax, eax
0x18001d94c  mov     [r11+8], r14
0x18001d950  xorps   xmm0, xmm0
0x18001d953  mov     [rsp+68h+pProfile.cbDataSize], eax
0x18001d957  mov     esi, r14d
0x18001d95a  mov     ebp, r9d
0x18001d95d  movups  xmmword ptr [rsp+68h+pProfile.dwType], xmm0
0x18001d962  mov     rdi, rcx
0x18001d965  call    FillProfileFromLogW
0x18001d96a  mov     ebx, eax
0x18001d96c  test    eax, eax
0x18001d96e  jz      short loc_18001D97A
0x18001d970  mov     ecx, eax; dwErrCode
0x18001d972  call    cs:__imp_SetLastError
0x18001d978  jmp     short loc_18001D9D0
0x18001d97a  mov     edx, 1; dwDesiredAccess
0x18001d97f  lea     rcx, [rsp+68h+pProfile]; pProfile
0x18001d984  mov     r8d, edx; dwShareMode
0x18001d987  lea     r9d, [rdx+2]; dwCreationMode
0x18001d98b  call    cs:__imp_OpenColorProfileW
0x18001d991  mov     r9, rax
0x18001d994  test    rax, rax
0x18001d997  jnz     short loc_18001D9A1
0x18001d999  call    cs:__imp_GetLastError
0x18001d99f  jmp     short loc_18001D9CE
0x18001d9a1  mov     rax, [rdi+24Ch]
0x18001d9a8  lea     rcx, [rsp+68h+arg_0]
0x18001d9ad  mov     r8d, [rdi+10h]
0x18001d9b1  mov     edx, ebp
0x18001d9b3  mov     [rsp+68h+var_40], rax
0x18001d9b8  mov     rax, [rdi+254h]
0x18001d9bf  mov     [rsp+68h+var_48], rax
0x18001d9c4  call    CMCreateTransformExtInternal
0x18001d9c9  mov     rsi, [rsp+68h+arg_0]
0x18001d9ce  mov     ebx, eax
0x18001d9d0  cmp     [rdi+44h], r14w
0x18001d9d5  jnz     short loc_18001DA04
0x18001d9d7  mov     rcx, [rsp+68h+pProfile.pProfileData]; pMem
0x18001d9dc  test    rcx, rcx
0x18001d9df  jz      short loc_18001DA04
0x18001d9e1  call    cs:__imp_GlobalHandle
0x18001d9e7  mov     rcx, rax; hMem
0x18001d9ea  call    cs:__imp_GlobalUnlock
0x18001d9f0  mov     rcx, [rsp+68h+pProfile.pProfileData]; pMem
0x18001d9f5  call    cs:__imp_GlobalHandle
0x18001d9fb  mov     rcx, rax; hMem
0x18001d9fe  call    cs:__imp_GlobalFree
0x18001da04  movzx   eax, bl
0x18001da07  test    ebx, ebx
0x18001da09  jnz     short loc_18001DA0E
0x18001da0b  mov     rax, rsi
0x18001da0e  lea     r11, [rsp+68h+var_18]
0x18001da13  mov     rbx, [r11+28h]
0x18001da17  mov     rbp, [r11+30h]
0x18001da1b  mov     rsp, r11
0x18001da1e  pop     r14
0x18001da20  pop     rdi
0x18001da21  pop     rsi
0x18001da22  retn
```
