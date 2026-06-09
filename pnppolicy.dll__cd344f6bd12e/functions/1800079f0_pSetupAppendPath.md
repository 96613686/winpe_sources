# pSetupAppendPath

- ea: `0x1800079f0`
- end: `0x180007b44`
- name: `pSetupAppendPath`
- size: `340`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180006100`
- `0x1800084ac`

## callees

- `0x1800034e8`
- `0x180006e28`
- `0x180006f1c`
- `0x1800074fc`
- `0x1800079f0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180007b1d`
- `KERNEL32!HeapFree` at `0x180007b1d`
- `KERNEL32!HeapAlloc` at `0x180007a2c`
- `KERNEL32!HeapAlloc` at `0x180007aad`
- `KERNEL32!HeapAlloc` at `0x180007a2c`
- `KERNEL32!HeapAlloc` at `0x180007aad`

## pseudocode

```c
__int64 __fastcall pSetupAppendPath(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR a2, _QWORD *a3)
{
  const wchar_t *v5; // r15
  unsigned int v6; // ebx
  _WORD *v7; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  size_t v12; // r12
  wchar_t *v13; // rdi
  unsigned int v14; // r14d

  v5 = pszSrc;
  v6 = 0;
  if ( __PAIR128__((unsigned __int64)pszSrc, (unsigned __int64)a2) == 0 )
  {
    v7 = HeapAlloc(hHeap, 0, 2u);
    *a3 = v7;
    if ( v7 )
    {
      *v7 = 0;
      return 1;
    }
    return 0;
  }
  if ( !pszSrc )
  {
    pszSrc = a2;
LABEL_6:
    v9 = pSetupDuplicateString(pszSrc);
    *a3 = v9;
    LOBYTE(v6) = v9 != 0;
    return v6;
  }
  if ( !a2 )
    goto LABEL_6;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  do
    ++v10;
  while ( v5[v10] );
  v12 = (unsigned int)(v10 + v11 + 2);
  if ( 2 * v12 > 0xFFFFFFFF )
    v13 = 0;
  else
    v13 = (wchar_t *)HeapAlloc(hHeap, 0, (unsigned int)(2 * v12));
  if ( !v13 )
  {
    *a3 = 0;
    return 0;
  }
  StringCchCopyW(v13, v12, v5);
  v14 = pSetupConcatenatePaths(v13, a2, (unsigned int)v12);
  if ( !v14 )
  {
    HeapFree(hHeap, 0, v13);
    v13 = 0;
  }
  *a3 = v13;
  return v14;
}

```

## disassembly

```asm
0x1800079f0  mov     [rsp+arg_8], rbx
0x1800079f5  mov     [rsp+arg_18], rsi
0x1800079fa  mov     [rsp+arg_10], r8
0x1800079ff  push    rdi
0x180007a00  push    r12
0x180007a02  push    r13
0x180007a04  push    r14
0x180007a06  push    r15
0x180007a08  sub     rsp, 30h
0x180007a0c  mov     rsi, r8
0x180007a0f  mov     r14, rdx
0x180007a12  mov     r15, rcx
0x180007a15  xor     ebx, ebx
0x180007a17  test    rcx, rcx
0x180007a1a  jnz     short loc_180007A49
0x180007a1c  test    rdx, rdx
0x180007a1f  jnz     short loc_180007A49
0x180007a21  lea     r8d, [rcx+2]; dwBytes
0x180007a25  mov     rcx, cs:hHeap; hHeap
0x180007a2c  call    cs:__imp_HeapAlloc
0x180007a32  mov     [rsi], rax
0x180007a35  test    rax, rax
0x180007a38  jz      loc_180007AC8
0x180007a3e  mov     [rax], bx
0x180007a41  lea     eax, [rbx+1]
0x180007a44  jmp     loc_180007B2C
0x180007a49  test    r15, r15
0x180007a4c  jnz     short loc_180007A66
0x180007a4e  mov     rcx, r14; pszSrc
0x180007a51  call    pSetupDuplicateString
0x180007a56  mov     [rsi], rax
0x180007a59  test    rax, rax
0x180007a5c  setnz   bl
0x180007a5f  mov     eax, ebx
0x180007a61  jmp     loc_180007B2C
0x180007a66  test    r14, r14
0x180007a69  jz      short loc_180007A51
0x180007a6b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007a6f  mov     rcx, rax
0x180007a72  inc     rcx
0x180007a75  cmp     [rdx+rcx*2], bx
0x180007a79  jnz     short loc_180007A72
0x180007a7b  inc     rax
0x180007a7e  cmp     [r15+rax*2], bx
0x180007a83  jnz     short loc_180007A7B
0x180007a85  lea     r12d, [rcx+2]
0x180007a89  add     r12d, eax
0x180007a8c  mov     r13d, r12d
0x180007a8f  lea     rax, ds:0[r12*2]
0x180007a97  mov     ecx, 0FFFFFFFFh
0x180007a9c  cmp     rax, rcx
0x180007a9f  ja      short loc_180007AB8
0x180007aa1  mov     r8d, eax; dwBytes
0x180007aa4  xor     edx, edx; dwFlags
0x180007aa6  mov     rcx, cs:hHeap; hHeap
0x180007aad  call    cs:__imp_HeapAlloc
0x180007ab3  mov     rdi, rax
0x180007ab6  jmp     short loc_180007ABB
0x180007ab8  mov     rdi, rbx
0x180007abb  mov     [rsp+58h+arg_0], rdi
0x180007ac0  test    rdi, rdi
0x180007ac3  jnz     short loc_180007ACC
0x180007ac5  mov     [rsi], rbx
0x180007ac8  xor     eax, eax
0x180007aca  jmp     short loc_180007B2C
0x180007acc  mov     r8, r15; pszSrc
0x180007acf  mov     rdx, r13; cchDest
0x180007ad2  mov     rcx, rdi; pszDest
0x180007ad5  call    StringCchCopyW
0x180007ada  mov     r8d, r12d
0x180007add  mov     rdx, r14
0x180007ae0  mov     rcx, rdi
0x180007ae3  call    pSetupConcatenatePaths
0x180007ae8  mov     r14d, eax
0x180007aeb  mov     [rsp+58h+var_2C], eax
0x180007aef  jmp     short loc_180007B0C
0x180007af1  mov     ecx, eax
0x180007af3  call    pSetupExceptionHandler
0x180007af8  xor     r14d, r14d
0x180007afb  mov     [rsp+58h+var_2C], r14d
0x180007b00  xor     ebx, ebx
0x180007b02  mov     rsi, [rsp+58h+arg_10]
0x180007b07  mov     rdi, [rsp+58h+arg_0]
0x180007b0c  test    r14d, r14d
0x180007b0f  jnz     short loc_180007B26
0x180007b11  mov     r8, rdi; lpMem
0x180007b14  xor     edx, edx; dwFlags
0x180007b16  mov     rcx, cs:hHeap; hHeap
0x180007b1d  call    cs:__imp_HeapFree
0x180007b23  mov     rdi, rbx
0x180007b26  mov     [rsi], rdi
0x180007b29  mov     eax, r14d
0x180007b2c  mov     rbx, [rsp+58h+arg_8]
0x180007b31  mov     rsi, [rsp+58h+arg_18]
0x180007b36  add     rsp, 30h
0x180007b3a  pop     r15
0x180007b3c  pop     r14
0x180007b3e  pop     r13
0x180007b40  pop     r12
0x180007b42  pop     rdi
0x180007b43  retn
0x18000a5b5  push    rbp
0x18000a5b7  sub     rsp, 20h
0x18000a5bb  mov     rbp, rdx
0x18000a5be  mov     rax, [rcx]
0x18000a5c1  mov     ecx, [rax]
0x18000a5c3  mov     [rbp+20h], ecx
0x18000a5c6  mov     eax, [rbp+20h]
0x18000a5c9  cmp     eax, 0E0000300h
0x18000a5ce  jz      short loc_18000A5E3
0x18000a5d0  mov     eax, [rbp+20h]
0x18000a5d3  cmp     eax, 0C0000194h
0x18000a5d8  jz      short loc_18000A5E3
0x18000a5da  mov     dword ptr [rbp+28h], 1
0x18000a5e1  jmp     short loc_18000A5EA
0x18000a5e3  mov     dword ptr [rbp+28h], 0
0x18000a5ea  mov     eax, [rbp+28h]
0x18000a5ed  add     rsp, 20h
0x18000a5f1  pop     rbp
0x18000a5f2  retn
```
