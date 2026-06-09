# GetServerNameOrSpn

- ea: `0x18000f048`
- end: `0x18000f14e`
- name: `GetServerNameOrSpn`
- size: `262`
- prototype: `__int64 __fastcall(__int64, int, wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180007ad0`
- `0x18000b8dc`

## callees

- `0x180004300`
- `0x180007a00`
- `0x180009bb0`
- `0x180009c00`
- `0x18000f048`

## import_xrefs

- `msvcrt!wcschr` at `0x18000f06b`
- `msvcrt!wcschr` at `0x18000f082`
- `msvcrt!wcschr` at `0x18000f06b`
- `msvcrt!wcschr` at `0x18000f082`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f133`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f133`

## pseudocode

```c
__int64 __fastcall GetServerNameOrSpn(__int64 a1, int a2, wchar_t *a3)
{
  const wchar_t *v3; // rbx
  wchar_t *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx
  size_t cchToCopy; // rdi
  unsigned int v10; // r10d
  __int64 v11; // r10
  size_t pcchLength; // [rsp+50h] [rbp+8h] BYREF

  v3 = (const wchar_t *)(a1 + 4);
  v6 = wcschr((const wchar_t *)(a1 + 4), 0x40u);
  if ( !v6 )
  {
    v6 = wcschr(v3, 0x5Cu);
    if ( !v6 )
    {
      v7 = -1;
      do
        ++v7;
      while ( v3[v7] );
      v6 = (wchar_t *)&v3[v7];
    }
  }
  v8 = v6 - v3;
  if ( (unsigned int)(v8 - 1) > 0xFF )
  {
    SetLastError(0x43u);
    return 67;
  }
  else
  {
    cchToCopy = (unsigned int)v8;
    if ( a2 )
    {
      StringCchCopyW(a3, 0x101u, L"HTTP/");
      pcchLength = 0;
      if ( StringLengthWorkerW(a3, v10, &pcchLength) >= 0 && cchToCopy <= 0x7FFFFFFE )
        StringCopyWorkerW(&a3[pcchLength], v11 - pcchLength, 0, v3, cchToCopy);
    }
    else
    {
      StringCchCopyNW(a3, 0x101u, v3, (unsigned int)v8);
      a3[cchToCopy] = 0;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18000f048  mov     [rsp+arg_8], rbx
0x18000f04d  mov     [rsp+arg_10], rbp
0x18000f052  push    rsi
0x18000f053  push    rdi
0x18000f054  push    r14
0x18000f056  sub     rsp, 30h
0x18000f05a  lea     rbx, [rcx+4]
0x18000f05e  mov     ebp, edx
0x18000f060  mov     rcx, rbx; Str
0x18000f063  mov     edx, 40h ; '@'; Ch
0x18000f068  mov     rsi, r8
0x18000f06b  call    cs:__imp_wcschr
0x18000f071  xor     r14d, r14d
0x18000f074  mov     rcx, rax
0x18000f077  test    rax, rax
0x18000f07a  jnz     short loc_18000F0A2
0x18000f07c  lea     edx, [rax+5Ch]; Ch
0x18000f07f  mov     rcx, rbx; Str
0x18000f082  call    cs:__imp_wcschr
0x18000f088  mov     rcx, rax
0x18000f08b  test    rax, rax
0x18000f08e  jnz     short loc_18000F0A2
0x18000f090  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f094  inc     rax
0x18000f097  cmp     [rbx+rax*2], r14w
0x18000f09c  jnz     short loc_18000F094
0x18000f09e  lea     rcx, [rbx+rax*2]
0x18000f0a2  sub     rcx, rbx
0x18000f0a5  sar     rcx, 1
0x18000f0a8  lea     eax, [rcx-1]
0x18000f0ab  cmp     eax, 0FFh
0x18000f0b0  ja      short loc_18000F12C
0x18000f0b2  mov     edi, ecx
0x18000f0b4  mov     rcx, rsi; pszDest
0x18000f0b7  test    ebp, ebp
0x18000f0b9  jnz     short loc_18000F0D2
0x18000f0bb  mov     r9d, edi; cchToCopy
0x18000f0be  mov     r8, rbx; pszSrc
0x18000f0c1  mov     edx, 101h; cchDest
0x18000f0c6  call    StringCchCopyNW
0x18000f0cb  mov     [rsi+rdi*2], r14w
0x18000f0d0  jmp     short loc_18000F128
0x18000f0d2  mov     r10d, 101h
0x18000f0d8  lea     r8, aHttp; "HTTP/"
0x18000f0df  mov     edx, r10d; cchDest
0x18000f0e2  call    StringCchCopyW
0x18000f0e7  lea     r8, [rsp+48h+pcchLength]; pcchLength
0x18000f0ec  mov     [rsp+48h+pcchLength], r14
0x18000f0f1  mov     edx, r10d; cchMax
0x18000f0f4  mov     rcx, rsi; psz
0x18000f0f7  call    StringLengthWorkerW
0x18000f0fc  test    eax, eax
0x18000f0fe  js      short loc_18000F128
0x18000f100  cmp     rdi, 7FFFFFFEh
0x18000f107  ja      short loc_18000F128
0x18000f109  mov     rax, [rsp+48h+pcchLength]
0x18000f10e  mov     r9, rbx; pszSrc
0x18000f111  sub     r10, rax
0x18000f114  mov     [rsp+48h+cchToCopy], rdi; cchToCopy
0x18000f119  xor     r8d, r8d; pcchNewDestLength
0x18000f11c  mov     rdx, r10; cchDest
0x18000f11f  lea     rcx, [rsi+rax*2]; pszDest
0x18000f123  call    StringCopyWorkerW
0x18000f128  xor     eax, eax
0x18000f12a  jmp     short loc_18000F13B
0x18000f12c  mov     ebx, 43h ; 'C'
0x18000f131  mov     ecx, ebx; dwErrCode
0x18000f133  call    cs:__imp_SetLastError
0x18000f139  mov     eax, ebx
0x18000f13b  mov     rbx, [rsp+48h+arg_8]
0x18000f140  mov     rbp, [rsp+48h+arg_10]
0x18000f145  add     rsp, 30h
0x18000f149  pop     r14
0x18000f14b  pop     rdi
0x18000f14c  pop     rsi
0x18000f14d  retn
```
