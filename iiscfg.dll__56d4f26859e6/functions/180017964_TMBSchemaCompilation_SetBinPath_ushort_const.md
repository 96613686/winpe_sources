# TMBSchemaCompilation::SetBinPath(ushort const *)

- ea: `0x180017964`
- end: `0x180017a8e`
- name: `?SetBinPath@TMBSchemaCompilation@@QEAAJPEBG@Z`
- size: `298`
- prototype: `signed int __fastcall(TMBSchemaCompilation *this, wchar_t *Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180004600`

## callees

- `0x180017964`
- `0x180017b70`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180017a28`
- `msvcrt!wcscpy_s` at `0x180017a28`
- `KERNEL32!GetFileAttributesW` at `0x18001798d`
- `KERNEL32!GetFileAttributesW` at `0x18001798d`
- `KERNEL32!GetLastError` at `0x180017998`
- `KERNEL32!GetLastError` at `0x180017998`
- `ole32!CoTaskMemAlloc` at `0x1800179fe`
- `ole32!CoTaskMemAlloc` at `0x1800179fe`

## pseudocode

```c
signed int __fastcall TMBSchemaCompilation::SetBinPath(TMBSchemaCompilation *this, wchar_t *Source)
{
  signed int result; // eax
  DWORD FileAttributesW; // eax
  __int64 v6; // rcx
  wchar_t *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rcx

  if ( !Source )
    return -2147024809;
  FileAttributesW = GetFileAttributesW(Source);
  if ( FileAttributesW == -1 )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else if ( (FileAttributesW & 0x10) != 0 )
  {
    if ( *((_QWORD *)this + 321) )
    {
      return 1;
    }
    else
    {
      v6 = -1;
      do
        ++v6;
      while ( Source[v6] );
      *((_QWORD *)this + 320) = v6;
      v7 = (wchar_t *)CoTaskMemAlloc(saturated_mul(v6 + 2, 2u));
      *((_QWORD *)this + 321) = v7;
      if ( v7 )
      {
        wcscpy_s(v7, *((_QWORD *)this + 320) + 2LL, Source);
        v8 = *((_QWORD *)this + 320);
        v9 = *((_QWORD *)this + 321);
        if ( *(_WORD *)(v9 + 2 * v8 - 2) != 92 )
        {
          *(_WORD *)(v9 + 2 * v8) = 92;
          *(_WORD *)(*((_QWORD *)this + 321) + 2LL * *((_QWORD *)this + 320) + 2) = 0;
          v8 = *((_QWORD *)this + 320) + 1LL;
        }
        *((_QWORD *)this + 320) = v8 + 23;
        TMBSchemaCompilation::WalkTheFileSystemToFindTheLatestBinFileName(this);
        return 0;
      }
      else
      {
        return -2147024882;
      }
    }
  }
  else
  {
    return -2147024893;
  }
  return result;
}

```

## disassembly

```asm
0x180017964  mov     [rsp+arg_0], rbx
0x180017969  mov     [rsp+arg_8], rsi
0x18001796e  push    rdi
0x18001796f  sub     rsp, 20h
0x180017973  xor     esi, esi
0x180017975  mov     rdi, rdx
0x180017978  mov     rbx, rcx
0x18001797b  test    rdx, rdx
0x18001797e  jnz     short loc_18001798A
0x180017980  mov     eax, 80070057h
0x180017985  jmp     loc_180017A7E
0x18001798a  mov     rcx, rdi; lpFileName
0x18001798d  call    cs:__imp_GetFileAttributesW
0x180017993  cmp     eax, 0FFFFFFFFh
0x180017996  jnz     short loc_1800179B3
0x180017998  call    cs:__imp_GetLastError
0x18001799e  test    eax, eax
0x1800179a0  jle     loc_180017A7E
0x1800179a6  movzx   eax, ax
0x1800179a9  or      eax, 80070000h
0x1800179ae  jmp     loc_180017A7E
0x1800179b3  test    al, 10h
0x1800179b5  jnz     short loc_1800179C1
0x1800179b7  mov     eax, 80070003h
0x1800179bc  jmp     loc_180017A7E
0x1800179c1  cmp     [rbx+0A08h], rsi
0x1800179c8  jz      short loc_1800179D4
0x1800179ca  mov     eax, 1
0x1800179cf  jmp     loc_180017A7E
0x1800179d4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800179d8  mov     rcx, r8
0x1800179db  inc     rcx
0x1800179de  cmp     [rdi+rcx*2], si
0x1800179e2  jnz     short loc_1800179DB
0x1800179e4  mov     [rbx+0A00h], rcx
0x1800179eb  mov     eax, 2
0x1800179f0  add     rcx, 2
0x1800179f4  mul     rcx
0x1800179f7  cmovb   rax, r8
0x1800179fb  mov     rcx, rax; cb
0x1800179fe  call    cs:__imp_CoTaskMemAlloc
0x180017a04  mov     [rbx+0A08h], rax
0x180017a0b  test    rax, rax
0x180017a0e  jnz     short loc_180017A17
0x180017a10  mov     eax, 8007000Eh
0x180017a15  jmp     short loc_180017A7E
0x180017a17  mov     rdx, [rbx+0A00h]
0x180017a1e  mov     r8, rdi; Source
0x180017a21  add     rdx, 2; SizeInWords
0x180017a25  mov     rcx, rax; Destination
0x180017a28  call    cs:__imp_wcscpy_s
0x180017a2e  mov     rax, [rbx+0A00h]
0x180017a35  mov     edx, 5Ch ; '\'
0x180017a3a  mov     rcx, [rbx+0A08h]
0x180017a41  cmp     [rcx+rax*2-2], dx
0x180017a46  jz      short loc_180017A69
0x180017a48  mov     [rcx+rax*2], dx
0x180017a4c  mov     rdx, [rbx+0A00h]
0x180017a53  mov     rcx, [rbx+0A08h]
0x180017a5a  mov     [rcx+rdx*2+2], si
0x180017a5f  mov     rax, [rbx+0A00h]
0x180017a66  inc     rax
0x180017a69  add     rax, 17h
0x180017a6d  mov     rcx, rbx; this
0x180017a70  mov     [rbx+0A00h], rax
0x180017a77  call    ?WalkTheFileSystemToFindTheLatestBinFileName@TMBSchemaCompilation@@AEAAJXZ; TMBSchemaCompilation::WalkTheFileSystemToFindTheLatestBinFileName(void)
0x180017a7c  xor     eax, eax
0x180017a7e  mov     rbx, [rsp+28h+arg_0]
0x180017a83  mov     rsi, [rsp+28h+arg_8]
0x180017a88  add     rsp, 20h
0x180017a8c  pop     rdi
0x180017a8d  retn
```
