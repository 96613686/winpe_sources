# CreateCallbackNode

- ea: `0x180009148`
- end: `0x1800091e4`
- name: `CreateCallbackNode`
- size: `156`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR, STRSAFE_LPCWSTR)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009588`

## callees

- `0x1800089c0`
- `0x180008b94`
- `0x180009148`
- `0x18000ab44`

## pseudocode

```c
__int64 __fastcall CreateCallbackNode(STRSAFE_LPCWSTR pszSrc, STRSAFE_LPCWSTR a2, STRSAFE_LPCWSTR a3, int a4)
{
  __int64 SizedNode; // rax
  __int64 v9; // rdi
  wchar_t **v10; // rbx
  wchar_t *v11; // rax
  wchar_t *v12; // rcx

  SizedNode = DtlCreateSizedNode(32);
  v9 = SizedNode;
  if ( SizedNode )
  {
    v10 = *(wchar_t ***)(SizedNode + 16);
    *v10 = StrDup(pszSrc);
    v10[1] = StrDup(a2);
    v11 = StrDup(a3);
    v12 = *v10;
    v10[2] = v11;
    *((_DWORD *)v10 + 6) = a4;
    if ( v12 && v10[1] && v11 )
      return v9;
    Free0(v12);
    Free0(v10[1]);
    Free0(v10[2]);
    Free0(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180009148  push    rbx
0x18000914a  push    rbp
0x18000914b  push    rsi
0x18000914c  push    rdi
0x18000914d  push    r14
0x18000914f  push    r15
0x180009151  sub     rsp, 28h
0x180009155  mov     r15, rcx
0x180009158  mov     esi, r9d
0x18000915b  mov     ecx, 20h ; ' '
0x180009160  mov     rbp, r8
0x180009163  mov     r14, rdx
0x180009166  call    DtlCreateSizedNode
0x18000916b  mov     rdi, rax
0x18000916e  test    rax, rax
0x180009171  jz      short loc_1800091D5
0x180009173  mov     rbx, [rax+10h]
0x180009177  mov     rcx, r15; pszSrc
0x18000917a  call    StrDup
0x18000917f  mov     rcx, r14; pszSrc
0x180009182  mov     [rbx], rax
0x180009185  call    StrDup
0x18000918a  mov     rcx, rbp; pszSrc
0x18000918d  mov     [rbx+8], rax
0x180009191  call    StrDup
0x180009196  mov     rcx, [rbx]
0x180009199  mov     [rbx+10h], rax
0x18000919d  mov     [rbx+18h], esi
0x1800091a0  test    rcx, rcx
0x1800091a3  jz      short loc_1800091B6
0x1800091a5  cmp     qword ptr [rbx+8], 0
0x1800091aa  jz      short loc_1800091B6
0x1800091ac  test    rax, rax
0x1800091af  jz      short loc_1800091B6
0x1800091b1  mov     rax, rdi
0x1800091b4  jmp     short loc_1800091D7
0x1800091b6  call    Free0
0x1800091bb  mov     rcx, [rbx+8]
0x1800091bf  call    Free0
0x1800091c4  mov     rcx, [rbx+10h]
0x1800091c8  call    Free0
0x1800091cd  mov     rcx, rdi
0x1800091d0  call    Free0
0x1800091d5  xor     eax, eax
0x1800091d7  add     rsp, 28h
0x1800091db  pop     r15
0x1800091dd  pop     r14
0x1800091df  pop     rdi
0x1800091e0  pop     rsi
0x1800091e1  pop     rbp
0x1800091e2  pop     rbx
0x1800091e3  retn
```
