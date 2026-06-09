# StoragePool::alloc(unsigned __int64)

- ea: `0x180002e40`
- end: `0x180002f66`
- name: `?alloc@StoragePool@@QEAAPEAX_K@Z`
- size: `294`
- prototype: `char *__fastcall(StoragePool *this, __int64)`
- caller_count: `11`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800014a0`
- `0x180002c60`
- `0x180002cf0`
- `0x180002d60`
- `0x18000f9e0`
- `0x18000fce0`
- `0x180019440`
- `0x18002a630`
- `0x18002a7b0`
- `0x18002aae0`
- `0x18003c2f0`

## callees

- `0x180002e40`
- `0x180003d54`

## import_xrefs

- `msvcrt!malloc` at `0x180002eba`
- `msvcrt!malloc` at `0x180002eba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002ea5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002ea5`

## string_xrefs

- `0x180002f21`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180002f4c`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
char *__fastcall StoragePool::alloc(StoragePool *this, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rax
  char *result; // rax
  size_t v8; // rbp
  _QWORD *v9; // r14
  __int64 v10; // rdi
  void *v11; // rax
  unsigned __int64 v12; // rax
  __int64 v13; // rdi
  unsigned int v14; // edx

  v2 = a2 + 7;
  v4 = *((_QWORD *)this + 1);
  v5 = v2 & 0xFFFFFFFFFFFFFFF8uLL;
  v6 = *(_QWORD *)(v4 + 16);
  if ( v5 > v6
    || (*(_QWORD *)(v4 + 16) = v6 - v5, result = *(char **)(v4 + 8), *(_QWORD *)(v4 + 8) = &result[v5], !result) )
  {
    v8 = *(_QWORD *)this;
    if ( v5 > *(_QWORD *)this )
      v8 = 2 * v5;
    v9 = CoTaskMemAlloc(0x20u);
    if ( v9 )
    {
      v10 = *((_QWORD *)this + 1);
      v11 = malloc(v8);
      *v9 = v11;
      v9[1] = v11;
      v9[2] = v8;
      v9[3] = v10;
      if ( v11 )
        goto LABEL_7;
      v14 = 34;
    }
    else
    {
      v9 = 0;
      v14 = 94;
    }
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v14, 0xC0001204, 0x10u);
LABEL_7:
    *(_QWORD *)this = v8;
    *((_QWORD *)this + 1) = v9;
    v12 = v9[2];
    if ( v5 > v12 )
    {
      v13 = 0;
    }
    else
    {
      v13 = v9[1];
      v9[2] = v12 - v5;
      v9[1] = v13 + v5;
      if ( v13 )
        return (char *)v13;
    }
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
    return (char *)v13;
  }
  return result;
}

```

## disassembly

```asm
0x180002e40  mov     [rsp+arg_18], rbx
0x180002e45  push    rsi
0x180002e46  sub     rsp, 20h
0x180002e4a  lea     rbx, [rdx+7]
0x180002e4e  mov     rsi, rcx
0x180002e51  mov     rdx, [rcx+8]
0x180002e55  and     rbx, 0FFFFFFFFFFFFFFF8h
0x180002e59  mov     rax, [rdx+10h]
0x180002e5d  cmp     rbx, rax
0x180002e60  ja      short loc_180002E85
0x180002e62  sub     rax, rbx
0x180002e65  mov     [rdx+10h], rax
0x180002e69  mov     rax, [rdx+8]
0x180002e6d  lea     rcx, [rax+rbx]
0x180002e71  mov     [rdx+8], rcx
0x180002e75  test    rax, rax
0x180002e78  jz      short loc_180002E85
0x180002e7a  mov     rbx, [rsp+28h+arg_18]
0x180002e7f  add     rsp, 20h
0x180002e83  pop     rsi
0x180002e84  retn
0x180002e85  mov     [rsp+28h+arg_0], rbp
0x180002e8a  mov     rbp, [rsi]
0x180002e8d  mov     [rsp+28h+arg_10], r14
0x180002e92  cmp     rbx, rbp
0x180002e95  ja      loc_180002F3C
0x180002e9b  mov     ecx, 20h ; ' '; cb
0x180002ea0  mov     [rsp+28h+arg_8], rdi
0x180002ea5  call    cs:__imp_CoTaskMemAlloc
0x180002eab  mov     r14, rax
0x180002eae  test    rax, rax
0x180002eb1  jz      short loc_180002F13
0x180002eb3  mov     rdi, [rsi+8]
0x180002eb7  mov     rcx, rbp; Size
0x180002eba  call    cs:__imp_malloc
0x180002ec0  mov     [r14], rax
0x180002ec3  mov     [r14+8], rax
0x180002ec7  mov     [r14+10h], rbp
0x180002ecb  mov     [r14+18h], rdi
0x180002ecf  test    rax, rax
0x180002ed2  jz      short loc_180002F35
0x180002ed4  mov     [rsi], rbp
0x180002ed7  mov     rbp, [rsp+28h+arg_0]
0x180002edc  mov     [rsi+8], r14
0x180002ee0  mov     rax, [r14+10h]
0x180002ee4  cmp     rbx, rax
0x180002ee7  ja      short loc_180002F45
0x180002ee9  mov     rdi, [r14+8]
0x180002eed  sub     rax, rbx
0x180002ef0  mov     [r14+10h], rax
0x180002ef4  lea     rdx, [rdi+rbx]
0x180002ef8  mov     [r14+8], rdx
0x180002efc  test    rdi, rdi
0x180002eff  jz      short loc_180002F47
0x180002f01  mov     r14, [rsp+28h+arg_10]
0x180002f06  mov     rax, rdi
0x180002f09  mov     rdi, [rsp+28h+arg_8]
0x180002f0e  jmp     loc_180002E7A
0x180002f13  xor     r14d, r14d
0x180002f16  mov     edx, 5Eh ; '^'; unsigned int
0x180002f1b  mov     r9d, 10h; unsigned __int16
0x180002f21  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180002f28  mov     r8d, 0C0001204h; unsigned int
0x180002f2e  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180002f33  jmp     short loc_180002ED4
0x180002f35  mov     edx, 22h ; '"'
0x180002f3a  jmp     short loc_180002F1B
0x180002f3c  lea     rbp, [rbx+rbx]
0x180002f40  jmp     loc_180002E9B
0x180002f45  xor     edi, edi
0x180002f47  mov     edx, 64h ; 'd'; unsigned int
0x180002f4c  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180002f53  mov     r9d, 10h; unsigned __int16
0x180002f59  mov     r8d, 0C0001204h; unsigned int
0x180002f5f  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180002f64  jmp     short loc_180002F01
```
