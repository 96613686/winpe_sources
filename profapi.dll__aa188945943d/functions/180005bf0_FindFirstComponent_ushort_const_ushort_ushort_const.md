# _FindFirstComponent(ushort const *,ushort * *,ushort const * *)

- ea: `0x180005bf0`
- end: `0x180005de0`
- name: `?_FindFirstComponent@@YAJPEBGPEAPEAGPEAPEBG@Z`
- size: `496`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005160`

## callees

- `0x180005b60`
- `0x180005bf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005d20`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005d20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d0f`

## pseudocode

```c
__int64 __fastcall _FindFirstComponent(const unsigned __int16 *a1, unsigned __int16 **a2, const unsigned __int16 **a3)
{
  int v3; // r14d
  const unsigned __int16 *v6; // rbx
  unsigned __int16 *v8; // rcx
  unsigned int v9; // edi
  const unsigned __int16 *v10; // r14
  unsigned __int64 v11; // rbp
  unsigned int v12; // esi
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned __int16 *v17; // rdx
  int v18; // [rsp+20h] [rbp-28h]
  int v19; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a3 = 0;
  v6 = a1;
  if ( !a1 || !*a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"minio\\profapi\\env.cpp",
      (const char *)0x80070057LL,
      v18);
    return 2147942487LL;
  }
  v9 = 0;
  v19 = v3;
  v10 = a1;
  do
  {
    if ( !*v10 )
      break;
    if ( *v10 == 59 )
      break;
    ++v9;
    ++v10;
  }
  while ( v10 );
  v11 = v9 + 1;
  if ( !is_mul_ok(v11, 2u) )
  {
    v12 = -2147024362;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"minio\\profapi\\env.cpp",
      (const char *)v12,
      v19);
    return v12;
  }
  ProcessHeap = GetProcessHeap();
  v14 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 2LL * (v9 + 1));
  v12 = -2147024882;
  if ( !v14 )
    goto LABEL_17;
  if ( v9 != -1 )
  {
    if ( v11 > 0x7FFFFFFF )
    {
      *v14 = 0;
    }
    else if ( v9 > 0x7FFFFFFE )
    {
      *v14 = 0;
    }
    else
    {
      v15 = v9;
      v16 = v9 + 1;
      v17 = v14;
      do
      {
        if ( !v15 )
          break;
        if ( !*v6 )
          break;
        *v17++ = *v6++;
        --v15;
        --v16;
      }
      while ( v16 );
      v8 = v17 - 1;
      if ( v16 )
        v8 = v17;
      *v8 = 0;
    }
  }
  if ( v14[v11 - 1] == 92 )
    v14[v11 - 1] = 0;
  if ( v10 )
  {
    if ( !*v10 || *v10 == 59 && (*a3 = v10 + 1, v10 != (const unsigned __int16 *)-2LL) && !v10[1] )
      *a3 = 0;
  }
  *a2 = v14;
  return *a3 == 0;
}

```

## disassembly

```asm
0x180005bf0  push    rbx
0x180005bf2  push    r12
0x180005bf4  push    r13
0x180005bf6  push    r15
0x180005bf8  sub     rsp, 28h
0x180005bfc  xor     r13d, r13d
0x180005bff  mov     r15, r8
0x180005c02  mov     [r8], r13
0x180005c05  mov     r12, rdx
0x180005c08  mov     rbx, rcx
0x180005c0b  test    rcx, rcx
0x180005c0e  jnz     loc_180005C97
0x180005c14  mov     rcx, [rsp+48h]; this
0x180005c19  lea     r8, aMinioProfapiEn; "minio\\profapi\\env.cpp"
0x180005c20  mov     r9d, 80070057h; char *
0x180005c26  mov     edx, 10h; void *
0x180005c2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c30  mov     eax, 80070057h
0x180005c35  add     rsp, 28h
0x180005c39  pop     r15
0x180005c3b  pop     r13
0x180005c3d  pop     r12
0x180005c3f  pop     rbx
0x180005c40  retn
0x180005c41  test    r8, r8
0x180005c44  lea     rcx, [rdx-2]
0x180005c48  cmovnz  rcx, rdx
0x180005c4c  mov     [rcx], r13w
0x180005c50  mov     eax, 5Ch ; '\'
0x180005c55  cmp     ax, [r9+rbp*2-2]
0x180005c5b  jz      loc_180005DD5
0x180005c61  test    r14, r14
0x180005c64  jnz     loc_180005D8E
0x180005c6a  mov     eax, r13d
0x180005c6d  mov     [r12], r9
0x180005c71  cmp     [r15], rax
0x180005c74  setz    al
0x180005c77  mov     rdi, [rsp+48h+arg_18]
0x180005c7c  mov     rsi, [rsp+48h+arg_10]
0x180005c81  mov     rbp, [rsp+48h+arg_8]
0x180005c86  mov     r14, qword ptr [rsp+48h+var_28]
0x180005c8b  add     rsp, 28h
0x180005c8f  pop     r15
0x180005c91  pop     r13
0x180005c93  pop     r12
0x180005c95  pop     rbx
0x180005c96  retn
0x180005c97  cmp     r13w, [rcx]
0x180005c9b  jz      loc_180005C14
0x180005ca1  mov     [rsp+48h+arg_8], rbp
0x180005ca6  mov     [rsp+48h+arg_10], rsi
0x180005cab  mov     [rsp+48h+arg_18], rdi
0x180005cb0  mov     edi, r13d
0x180005cb3  mov     qword ptr [rsp+48h+var_28], r14; int
0x180005cb8  mov     r14, rcx
0x180005cbb  nop     dword ptr [rax+rax+00h]
0x180005cc0  movzx   eax, word ptr [r14]
0x180005cc4  test    ax, ax
0x180005cc7  jz      short loc_180005CD7
0x180005cc9  cmp     ax, 3Bh ; ';'
0x180005ccd  jz      short loc_180005CD7
0x180005ccf  inc     edi
0x180005cd1  add     r14, 2
0x180005cd5  jnz     short loc_180005CC0
0x180005cd7  lea     ebp, [rdi+1]
0x180005cda  mov     eax, 2
0x180005cdf  mul     rbp
0x180005ce2  mov     rsi, rax
0x180005ce5  test    rdx, rdx
0x180005ce8  jz      short loc_180005D0F
0x180005cea  mov     esi, 80070216h
0x180005cef  mov     rcx, [rsp+48h]; this
0x180005cf4  lea     r8, aMinioProfapiEn; "minio\\profapi\\env.cpp"
0x180005cfb  mov     r9d, esi; char *
0x180005cfe  mov     edx, 1Eh; void *
0x180005d03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005d08  mov     eax, esi
0x180005d0a  jmp     loc_180005C77
0x180005d0f  call    cs:__imp_GetProcessHeap
0x180005d15  mov     r8, rsi; dwBytes
0x180005d18  mov     edx, 8; dwFlags
0x180005d1d  mov     rcx, rax; hHeap
0x180005d20  call    cs:__imp_HeapAlloc
0x180005d26  test    rax, rax
0x180005d29  mov     esi, 8007000Eh
0x180005d2e  mov     r9, rax
0x180005d31  cmovnz  esi, r13d
0x180005d35  jz      short loc_180005CEF
0x180005d37  test    rbp, rbp
0x180005d3a  jz      loc_180005C50
0x180005d40  cmp     rbp, 7FFFFFFFh
0x180005d47  ja      loc_180005DCC
0x180005d4d  cmp     edi, 7FFFFFFEh
0x180005d53  ja      short loc_180005DC3
0x180005d55  mov     ecx, edi
0x180005d57  mov     r8, rbp
0x180005d5a  mov     rdx, rax
0x180005d5d  nop     dword ptr [rax]
0x180005d60  test    rcx, rcx
0x180005d63  jz      loc_180005C41
0x180005d69  movzx   eax, word ptr [rbx]
0x180005d6c  test    ax, ax
0x180005d6f  jz      loc_180005C41
0x180005d75  mov     [rdx], ax
0x180005d78  add     rbx, 2
0x180005d7c  add     rdx, 2
0x180005d80  dec     rcx
0x180005d83  sub     r8, 1
0x180005d87  jnz     short loc_180005D60
0x180005d89  jmp     loc_180005C41
0x180005d8e  movzx   eax, word ptr [r14]
0x180005d92  test    ax, ax
0x180005d95  jz      short loc_180005DBB
0x180005d97  cmp     ax, 3Bh ; ';'
0x180005d9b  jnz     loc_180005C6A
0x180005da1  lea     rcx, [r14+2]
0x180005da5  mov     [r15], rcx
0x180005da8  test    rcx, rcx
0x180005dab  jz      loc_180005C6A
0x180005db1  cmp     r13w, [rcx]
0x180005db5  jnz     loc_180005C6A
0x180005dbb  mov     [r15], r13
0x180005dbe  jmp     loc_180005C6A
0x180005dc3  mov     [rax], r13w
0x180005dc7  jmp     loc_180005C50
0x180005dcc  mov     [rax], r13w
0x180005dd0  jmp     loc_180005C50
0x180005dd5  mov     [r9+rbp*2-2], r13w
0x180005ddb  jmp     loc_180005C61
```
