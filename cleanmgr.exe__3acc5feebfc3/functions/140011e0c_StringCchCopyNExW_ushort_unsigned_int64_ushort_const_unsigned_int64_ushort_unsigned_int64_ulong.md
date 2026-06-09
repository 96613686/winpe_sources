# StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)

- ea: `0x140011e0c`
- end: `0x140011ee8`
- name: `?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z`
- size: `220`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **, const unsigned __int16 *, unsigned __int64, size_t pcchNewDestLength)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012a7c`

## callees

- `0x140003390`
- `0x140011e0c`
- `0x140011f54`

## pseudocode

```c
__int64 __fastcall StringCchCopyNExW(
        unsigned __int16 *a1,
        unsigned __int16 **a2,
        const unsigned __int16 *a3,
        unsigned __int64 a4,
        size_t pcchNewDestLength)
{
  HRESULT v8; // ebx
  const wchar_t *v9; // r9
  size_t cchToCopy; // rax
  char *v11; // rdi
  bool v12; // cf

  if ( !a1 && a2 || (unsigned __int64)a2 > 0x7FFFFFFF )
  {
    v8 = -2147024809;
LABEL_7:
    *a1 = 0;
    return (unsigned int)v8;
  }
  if ( a4 < 0x7FFFFFFF )
  {
    v9 = &String;
    if ( a3 )
      v9 = a3;
    cchToCopy = a4 & -(__int64)(a3 != 0);
    if ( a2 )
    {
      pcchNewDestLength = 0;
      v8 = StringCopyWorkerW_0(a1, (size_t)a2, &pcchNewDestLength, v9, cchToCopy);
      if ( v8 >= 0 )
      {
        v12 = a2 == (unsigned __int16 **)pcchNewDestLength;
        v11 = (char *)a2 - pcchNewDestLength;
        if ( !v12 && v11 != (char *)1 && (unsigned __int64)(2LL * (_QWORD)v11) > 2 )
          memset_0(&a1[pcchNewDestLength + 1], 0, 2LL * (_QWORD)v11 - 2);
      }
    }
    else
    {
      v8 = 0;
      if ( cchToCopy && *v9 )
        return (unsigned int)(a1 != 0 ? -2147024774 : -2147024809);
    }
  }
  else
  {
    v8 = -2147024809;
    if ( a2 )
      goto LABEL_7;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140011e0c  push    rbx
0x140011e0e  push    rbp
0x140011e0f  push    rsi
0x140011e10  push    rdi
0x140011e11  sub     rsp, 38h
0x140011e15  xor     ebp, ebp
0x140011e17  mov     r10, r9
0x140011e1a  mov     rdi, rdx
0x140011e1d  mov     rsi, rcx
0x140011e20  test    rcx, rcx
0x140011e23  jnz     short loc_140011E2A
0x140011e25  test    rdx, rdx
0x140011e28  jnz     short loc_140011E34
0x140011e2a  mov     eax, 7FFFFFFFh
0x140011e2f  cmp     rdi, rax
0x140011e32  jbe     short loc_140011E3B
0x140011e34  mov     ebx, 80070057h
0x140011e39  jmp     short loc_140011E4E
0x140011e3b  cmp     r10, rax
0x140011e3e  jb      short loc_140011E56
0x140011e40  mov     ebx, 80070057h
0x140011e45  test    rdi, rdi
0x140011e48  jz      loc_140011EDD
0x140011e4e  mov     [rcx], bp
0x140011e51  jmp     loc_140011EDD
0x140011e56  test    r8, r8
0x140011e59  lea     r9, String
0x140011e60  cmovnz  r9, r8; pszSrc
0x140011e64  neg     r8
0x140011e67  sbb     rax, rax
0x140011e6a  and     rax, r10
0x140011e6d  test    rdi, rdi
0x140011e70  jnz     short loc_140011E90
0x140011e72  mov     ebx, ebp
0x140011e74  test    rax, rax
0x140011e77  jz      short loc_140011EDD
0x140011e79  cmp     [r9], bp
0x140011e7d  jz      short loc_140011EDD
0x140011e7f  neg     rsi
0x140011e82  mov     ebx, 80070057h
0x140011e87  sbb     eax, eax
0x140011e89  and     eax, 23h
0x140011e8c  add     ebx, eax
0x140011e8e  jmp     short loc_140011EDD
0x140011e90  lea     r8, [rsp+58h+pcchNewDestLength]; pcchNewDestLength
0x140011e98  mov     [rsp+58h+pcchNewDestLength], rbp
0x140011ea0  mov     [rsp+58h+cchToCopy], rax; cchToCopy
0x140011ea5  call    StringCopyWorkerW_0
0x140011eaa  mov     ebx, eax
0x140011eac  test    eax, eax
0x140011eae  js      short loc_140011EDD
0x140011eb0  mov     rax, [rsp+58h+pcchNewDestLength]
0x140011eb8  sub     rdi, rax
0x140011ebb  cmp     rdi, 1
0x140011ebf  jbe     short loc_140011EDD
0x140011ec1  lea     r8, [rdi+rdi]
0x140011ec5  cmp     r8, 2
0x140011ec9  jbe     short loc_140011EDD
0x140011ecb  inc     rax
0x140011ece  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x140011ed2  xor     edx, edx; Val
0x140011ed4  lea     rcx, [rsi+rax*2]; void *
0x140011ed8  call    memset_0
0x140011edd  mov     eax, ebx
0x140011edf  add     rsp, 38h
0x140011ee3  pop     rdi
0x140011ee4  pop     rsi
0x140011ee5  pop     rbp
0x140011ee6  pop     rbx
0x140011ee7  retn
```
