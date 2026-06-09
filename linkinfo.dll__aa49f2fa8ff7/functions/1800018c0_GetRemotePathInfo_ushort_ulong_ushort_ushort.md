# GetRemotePathInfo(ushort *,ulong *,ushort *,ushort * *)

- ea: `0x1800018c0`
- end: `0x1800019cf`
- name: `?GetRemotePathInfo@@YAHPEAGPEAK0PEAPEAG@Z`
- size: `271`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001ce0`

## callees

- `0x1800018c0`
- `0x1800023d0`
- `0x180003570`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800018d7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800018d7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180001913`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180001931`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180001954`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180001913`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180001931`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180001954`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x18000198d`
- `api-ms-win-core-string-l2-1-0!CharUpperW` at `0x18000198d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800019bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800019bf`

## pseudocode

```c
__int64 __fastcall GetRemotePathInfo(
        unsigned __int16 *a1,
        unsigned int *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  const WCHAR *v8; // r10
  __int16 *v9; // rax
  unsigned __int64 v10; // rdx
  LPWSTR v11; // r9
  __int16 i; // cx
  unsigned __int16 *v13; // rcx

  if ( PathIsUNCW(a1) )
  {
    *a2 = 0;
    if ( !CharIsSlash(a1[2]) )
    {
      do
        v9 = (__int16 *)CharNextW(v8);
      while ( !CharIsSlash(*v9) );
    }
    v11 = CharNextW(v8);
    for ( i = *v11; *v11; i = *v11 )
    {
      if ( CharIsSlash(i) )
        break;
      v11 = CharNextW(v11);
    }
    v13 = v11 + 1;
    if ( !*v11 )
    {
      *v11 = 92;
      *v13 = 0;
    }
    *a4 = v13;
    StringCchCopyNW(a3, v10, a1, v11 - a1);
    CharUpperW(a3);
    *a2 |= 1u;
    return 1;
  }
  else
  {
    SetLastError(0xA1u);
    return 0;
  }
}

```

## disassembly

```asm
0x1800018c0  push    rbx
0x1800018c2  push    rbp
0x1800018c3  push    rsi
0x1800018c4  push    rdi
0x1800018c5  push    r14
0x1800018c7  sub     rsp, 20h
0x1800018cb  mov     r14, r9
0x1800018ce  mov     rbp, r8
0x1800018d1  mov     rsi, rdx
0x1800018d4  mov     rdi, rcx
0x1800018d7  call    cs:__imp_PathIsUNCW
0x1800018de  nop     dword ptr [rax+rax+00h]
0x1800018e3  mov     ebx, eax
0x1800018e5  test    eax, eax
0x1800018e7  jz      loc_1800019BA
0x1800018ed  lea     r10, [rdi+4]
0x1800018f1  mov     dword ptr [rsi], 0
0x1800018f7  movzx   ecx, word ptr [r10]; unsigned __int16
0x1800018fb  call    ?CharIsSlash@@YAHG@Z; CharIsSlash(ushort)
0x180001900  test    eax, eax
0x180001902  jnz     short loc_18000192E
0x180001904  nop     dword ptr [rax+00h]
0x180001908  nop     dword ptr [rax+rax+00000000h]
0x180001910  mov     rcx, r10; lpsz
0x180001913  call    cs:__imp_CharNextW
0x18000191a  nop     dword ptr [rax+rax+00h]
0x18000191f  mov     r10, rax
0x180001922  movzx   ecx, word ptr [rax]; unsigned __int16
0x180001925  call    ?CharIsSlash@@YAHG@Z; CharIsSlash(ushort)
0x18000192a  test    eax, eax
0x18000192c  jz      short loc_180001910
0x18000192e  mov     rcx, r10; lpsz
0x180001931  call    cs:__imp_CharNextW
0x180001938  nop     dword ptr [rax+rax+00h]
0x18000193d  mov     r9, rax
0x180001940  movzx   ecx, word ptr [rax]; unsigned __int16
0x180001943  test    cx, cx
0x180001946  jz      short loc_18000196B
0x180001948  call    ?CharIsSlash@@YAHG@Z; CharIsSlash(ushort)
0x18000194d  test    eax, eax
0x18000194f  jnz     short loc_18000196B
0x180001951  mov     rcx, r9; lpsz
0x180001954  call    cs:__imp_CharNextW
0x18000195b  nop     dword ptr [rax+rax+00h]
0x180001960  mov     r9, rax
0x180001963  movzx   ecx, word ptr [rax]
0x180001966  test    cx, cx
0x180001969  jnz     short loc_180001948
0x18000196b  cmp     word ptr [r9], 0
0x180001970  lea     rcx, [r9+2]
0x180001974  jz      short loc_1800019AD
0x180001976  sub     r9, rdi
0x180001979  mov     [r14], rcx
0x18000197c  sar     r9, 1; unsigned __int64
0x18000197f  mov     r8, rdi; unsigned __int16 *
0x180001982  mov     rcx, rbp; unsigned __int16 *
0x180001985  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000198a  mov     rcx, rbp; lpsz
0x18000198d  call    cs:__imp_CharUpperW
0x180001994  nop     dword ptr [rax+rax+00h]
0x180001999  or      dword ptr [rsi], 1
0x18000199c  mov     eax, 1
0x1800019a1  add     rsp, 20h
0x1800019a5  pop     r14
0x1800019a7  pop     rdi
0x1800019a8  pop     rsi
0x1800019a9  pop     rbp
0x1800019aa  pop     rbx
0x1800019ab  retn
0x1800019ad  xor     eax, eax
0x1800019af  mov     word ptr [r9], 5Ch ; '\'
0x1800019b5  mov     [rcx], ax
0x1800019b8  jmp     short loc_180001976
0x1800019ba  mov     ecx, 0A1h; dwErrCode
0x1800019bf  call    cs:__imp_SetLastError
0x1800019c6  nop     dword ptr [rax+rax+00h]
0x1800019cb  mov     eax, ebx
0x1800019cd  jmp     short loc_1800019A1
```
