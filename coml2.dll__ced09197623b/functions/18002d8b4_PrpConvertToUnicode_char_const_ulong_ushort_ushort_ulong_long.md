# PrpConvertToUnicode(char const *,ulong,ushort,ushort * *,ulong *,long *)

- ea: `0x18002d8b4`
- end: `0x18002d95e`
- name: `?PrpConvertToUnicode@@YAXPEBDKGPEAPEAGPEAKPEAJ@Z`
- size: `170`
- prototype: `void __usercall(LPCCH lpMultiByteStr@<rcx>, unsigned int cbMultiByte@<edx>, unsigned __int16@<r8w>, unsigned __int16 **@<r9>, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027ff4`
- `0x18002c284`

## callees

- `0x18002d8b4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002d905`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002d905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d91e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d91e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d93a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d93a`

## pseudocode

```c
void __fastcall PrpConvertToUnicode(
        LPCCH lpMultiByteStr,
        int cbMultiByte,
        unsigned __int16 a3,
        unsigned __int16 **a4,
        unsigned int *a5,
        int *a6)
{
  UINT v9; // r13d
  WCHAR *lpWideCharStr; // rbx
  int cchWideChar; // r14d
  int v12; // eax
  unsigned int v13; // eax
  unsigned __int16 *v14; // rax

  *a4 = 0;
  v9 = a3;
  *a6 = 0;
  lpWideCharStr = 0;
  *a5 = 0;
  cchWideChar = 0;
  while ( 1 )
  {
    v12 = MultiByteToWideChar(v9, 0, lpMultiByteStr, cbMultiByte, lpWideCharStr, cchWideChar);
    cchWideChar = v12;
    if ( !v12 )
      break;
    if ( lpWideCharStr )
      return;
    v13 = 2 * v12;
    *a5 = v13;
    v14 = (unsigned __int16 *)CoTaskMemAlloc(v13);
    *a4 = v14;
    lpWideCharStr = v14;
    if ( !v14 )
    {
      *a6 = -1073741670;
      return;
    }
  }
  CoTaskMemFree(lpWideCharStr);
  *a4 = 0;
  *a6 = -1073741470;
}

```

## disassembly

```asm
0x18002d8b4  push    rbx
0x18002d8b6  push    rbp
0x18002d8b7  push    rsi
0x18002d8b8  push    rdi
0x18002d8b9  push    r12
0x18002d8bb  push    r13
0x18002d8bd  push    r14
0x18002d8bf  push    r15
0x18002d8c1  sub     rsp, 38h
0x18002d8c5  mov     rdi, [rsp+78h+arg_28]
0x18002d8cd  xor     eax, eax
0x18002d8cf  mov     r15, [rsp+78h+arg_20]
0x18002d8d7  mov     rsi, r9
0x18002d8da  mov     ebp, edx
0x18002d8dc  mov     [r9], rax
0x18002d8df  mov     r12, rcx
0x18002d8e2  movzx   r13d, r8w
0x18002d8e6  mov     [rdi], eax
0x18002d8e8  mov     ebx, eax
0x18002d8ea  mov     [r15], eax
0x18002d8ed  mov     r14d, eax
0x18002d8f0  mov     [rsp+78h+cchWideChar], r14d; cchWideChar
0x18002d8f5  mov     r9d, ebp; cbMultiByte
0x18002d8f8  mov     r8, r12; lpMultiByteStr
0x18002d8fb  mov     [rsp+78h+lpWideCharStr], rbx; lpWideCharStr
0x18002d900  xor     edx, edx; dwFlags
0x18002d902  mov     ecx, r13d; CodePage
0x18002d905  call    cs:__imp_MultiByteToWideChar
0x18002d90b  mov     r14d, eax
0x18002d90e  test    eax, eax
0x18002d910  jz      short loc_18002D937
0x18002d912  test    rbx, rbx
0x18002d915  jnz     short loc_18002D94D
0x18002d917  add     eax, eax
0x18002d919  mov     ecx, eax; cb
0x18002d91b  mov     [r15], eax
0x18002d91e  call    cs:__imp_CoTaskMemAlloc
0x18002d924  mov     [rsi], rax
0x18002d927  mov     rbx, rax
0x18002d92a  test    rax, rax
0x18002d92d  jnz     short loc_18002D8F0
0x18002d92f  mov     dword ptr [rdi], 0C000009Ah
0x18002d935  jmp     short loc_18002D94D
0x18002d937  mov     rcx, rbx; pv
0x18002d93a  call    cs:__imp_CoTaskMemFree
0x18002d940  mov     qword ptr [rsi], 0
0x18002d947  mov     dword ptr [rdi], 0C0000162h
0x18002d94d  add     rsp, 38h
0x18002d951  pop     r15
0x18002d953  pop     r14
0x18002d955  pop     r13
0x18002d957  pop     r12
0x18002d959  pop     rdi
0x18002d95a  pop     rsi
0x18002d95b  pop     rbp
0x18002d95c  pop     rbx
0x18002d95d  retn
```
