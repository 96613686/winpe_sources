# ReadString(IStream *,ushort *,ushort)

- ea: `0x1800209e4`
- end: `0x180020ad7`
- name: `?ReadString@@YAJPEAUIStream@@PEAGG@Z`
- size: `243`
- prototype: `__int64 __fastcall(struct IStream *, unsigned __int16 *, unsigned __int16)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011738`
- `0x180016b54`

## callees

- `0x1800209e4`
- `0x180024010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180020a84`
- `msvcrt!wcsncpy_s` at `0x180020a84`
- `msvcrt!free` at `0x180020a95`
- `msvcrt!free` at `0x180020a95`
- `msvcrt!malloc` at `0x180020a32`
- `msvcrt!malloc` at `0x180020a32`

## pseudocode

```c
__int64 __fastcall ReadString(struct IStream *a1, unsigned __int16 *a2, unsigned __int16 a3)
{
  rsize_t v3; // r15
  int v6; // edi
  wchar_t *v7; // rax
  wchar_t *v8; // rsi
  unsigned __int16 v10; // [rsp+60h] [rbp+18h] BYREF

  v3 = a3;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int16 *, __int64))(*(_QWORD *)a1 + 24LL))(a1, &v10, 2);
  if ( v10 < (unsigned __int16)v3 )
  {
    if ( v6 >= 0 )
      return (unsigned int)(*(__int64 (__fastcall **)(struct IStream *, unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)a1 + 24LL))(
                             a1,
                             a2,
                             2 * (unsigned int)v10,
                             0);
  }
  else
  {
    v7 = (wchar_t *)malloc(2LL * v10);
    v8 = v7;
    if ( v7 )
    {
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(struct IStream *, wchar_t *, _QWORD, _QWORD))(*(_QWORD *)a1 + 24LL))(
               a1,
               v7,
               2 * (unsigned int)v10,
               0);
        v8[v10 - 1] = 0;
        wcsncpy_s(a2, v3, v8, v3 - 1);
        a2[v3 - 1] = 0;
      }
      free(v8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800209e4  mov     [rsp+arg_0], rbx
0x1800209e9  mov     [rsp+arg_8], rsi
0x1800209ee  push    rdi
0x1800209ef  push    r14
0x1800209f1  push    r15
0x1800209f3  sub     rsp, 30h
0x1800209f7  xor     eax, eax
0x1800209f9  movzx   r15d, r8w
0x1800209fd  mov     [rsp+48h+arg_10], ax
0x180020a02  xor     r9d, r9d
0x180020a05  mov     rax, [rcx]
0x180020a08  mov     r14, rdx
0x180020a0b  lea     rdx, [rsp+48h+arg_10]
0x180020a10  mov     rbx, rcx
0x180020a13  lea     r8d, [r9+2]
0x180020a17  mov     rax, [rax+18h]
0x180020a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a20  mov     edi, eax
0x180020a22  cmp     [rsp+48h+arg_10], r15w
0x180020a28  jb      short loc_180020A9D
0x180020a2a  movzx   ecx, [rsp+48h+arg_10]
0x180020a2f  add     rcx, rcx; Size
0x180020a32  call    cs:__imp_malloc
0x180020a38  mov     rsi, rax
0x180020a3b  test    rax, rax
0x180020a3e  jnz     short loc_180020A47
0x180020a40  mov     edi, 8007000Eh
0x180020a45  jmp     short loc_180020AC1
0x180020a47  test    edi, edi
0x180020a49  js      short loc_180020A92
0x180020a4b  mov     rax, [rbx]
0x180020a4e  xor     r9d, r9d
0x180020a51  movzx   r8d, [rsp+48h+arg_10]
0x180020a57  mov     rdx, rsi
0x180020a5a  add     r8d, r8d
0x180020a5d  mov     rcx, rbx
0x180020a60  mov     rax, [rax+18h]
0x180020a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a69  movzx   ecx, [rsp+48h+arg_10]
0x180020a6e  lea     r9, [r15-1]; MaxCount
0x180020a72  mov     edi, eax
0x180020a74  mov     r8, rsi; Source
0x180020a77  xor     eax, eax
0x180020a79  mov     rdx, r15; SizeInWords
0x180020a7c  mov     [rsi+rcx*2-2], ax
0x180020a81  mov     rcx, r14; Destination
0x180020a84  call    cs:__imp_wcsncpy_s
0x180020a8a  xor     eax, eax
0x180020a8c  mov     [r14+r15*2-2], ax
0x180020a92  mov     rcx, rsi; Block
0x180020a95  call    cs:__imp_free
0x180020a9b  jmp     short loc_180020AC1
0x180020a9d  test    edi, edi
0x180020a9f  js      short loc_180020AC1
0x180020aa1  mov     rax, [rbx]
0x180020aa4  xor     r9d, r9d
0x180020aa7  movzx   r8d, [rsp+48h+arg_10]
0x180020aad  mov     rdx, r14
0x180020ab0  add     r8d, r8d
0x180020ab3  mov     rcx, rbx
0x180020ab6  mov     rax, [rax+18h]
0x180020aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020abf  mov     edi, eax
0x180020ac1  mov     rbx, [rsp+48h+arg_0]
0x180020ac6  mov     eax, edi
0x180020ac8  mov     rsi, [rsp+48h+arg_8]
0x180020acd  add     rsp, 30h
0x180020ad1  pop     r15
0x180020ad3  pop     r14
0x180020ad5  pop     rdi
0x180020ad6  retn
```
