# CDpUrlAccessor::GetDisplayUrl(ushort * const,ulong,ulong *)

- ea: `0x180006c10`
- end: `0x180006c7a`
- name: `?GetDisplayUrl@CDpUrlAccessor@@UEAAJQEAGKPEAK@Z`
- size: `106`
- prototype: `__int64 __fastcall(CDpUrlAccessor *this, unsigned __int16 *const, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006c10`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180006c57`
- `msvcrt!wcsncpy_s` at `0x180006c57`

## pseudocode

```c
__int64 __fastcall CDpUrlAccessor::GetDisplayUrl(
        CDpUrlAccessor *this,
        unsigned __int16 *const a2,
        unsigned int a3,
        unsigned int *a4)
{
  rsize_t v8; // r9
  rsize_t v9; // rdx
  const wchar_t *v10; // r8

  if ( !a4 )
    return 2147500035LL;
  v8 = *((_QWORD *)this + 15);
  v9 = a3;
  if ( a3 < v8 + 2 )
    return 2147614739LL;
  v10 = (const wchar_t *)((char *)this + 104);
  if ( *((_QWORD *)this + 16) >= 8u )
    v10 = *(const wchar_t **)v10;
  if ( wcsncpy_s(a2, v9, v10, v8) )
    return 2147500037LL;
  *a4 = *((_DWORD *)this + 30);
  return 0;
}

```

## disassembly

```asm
0x180006c10  mov     [rsp+arg_0], rbx
0x180006c15  push    rdi
0x180006c16  sub     rsp, 20h
0x180006c1a  mov     rdi, r9
0x180006c1d  mov     r10, rdx
0x180006c20  mov     rbx, rcx
0x180006c23  test    r9, r9
0x180006c26  jnz     short loc_180006C2F
0x180006c28  mov     eax, 80004003h
0x180006c2d  jmp     short loc_180006C6F
0x180006c2f  mov     r9, [rcx+78h]; MaxCount
0x180006c33  mov     edx, r8d; SizeInWords
0x180006c36  lea     rax, [r9+2]
0x180006c3a  cmp     rdx, rax
0x180006c3d  jnb     short loc_180006C46
0x180006c3f  mov     eax, 80020013h
0x180006c44  jmp     short loc_180006C6F
0x180006c46  lea     r8, [rcx+68h]
0x180006c4a  cmp     qword ptr [r8+18h], 8
0x180006c4f  jb      short loc_180006C54
0x180006c51  mov     r8, [r8]; Source
0x180006c54  mov     rcx, r10; Destination
0x180006c57  call    cs:__imp_wcsncpy_s
0x180006c5d  test    eax, eax
0x180006c5f  jz      short loc_180006C68
0x180006c61  mov     eax, 80004005h
0x180006c66  jmp     short loc_180006C6F
0x180006c68  mov     eax, [rbx+78h]
0x180006c6b  mov     [rdi], eax
0x180006c6d  xor     eax, eax
0x180006c6f  mov     rbx, [rsp+28h+arg_0]
0x180006c74  add     rsp, 20h
0x180006c78  pop     rdi
0x180006c79  retn
```
