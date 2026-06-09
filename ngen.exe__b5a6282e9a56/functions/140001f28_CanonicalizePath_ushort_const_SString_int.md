# CanonicalizePath(ushort const *,SString &,int)

- ea: `0x140001f28`
- end: `0x140001f9e`
- name: `?CanonicalizePath@@YAXPEBGAEAVSString@@H@Z`
- size: `118`
- prototype: `void __fastcall(const unsigned __int16 *, struct SString *this, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x140002168`
- `0x140004694`
- `0x140008548`

## callees

- `0x1400016f4`
- `0x140001950`
- `0x140001bac`
- `0x140001e08`
- `0x140001f28`
- `0x14000ad80`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x140001f40`
- `KERNEL32!GetFileAttributesW` at `0x140001f40`

## pseudocode

```c
void __fastcall CanonicalizePath(const unsigned __int16 *a1, struct SString *this, int a3)
{
  DWORD FileAttributesW; // eax

  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0
    || (unsigned int)IsExe(a1)
    || (unsigned int)IsDll(a1)
    || (unsigned int)IsWinMD(a1) )
  {
    CanonicalizePathAux(a1, this, a3);
  }
  else
  {
    SString::Set(this, a1);
  }
}

```

## disassembly

```asm
0x140001f28  mov     [rsp+arg_0], rbx
0x140001f2d  mov     [rsp+arg_8], rsi
0x140001f32  push    rdi
0x140001f33  sub     rsp, 20h
0x140001f37  mov     esi, r8d
0x140001f3a  mov     rdi, rdx
0x140001f3d  mov     rbx, rcx
0x140001f40  call    cs:__imp_GetFileAttributesW
0x140001f46  cmp     eax, 0FFFFFFFFh
0x140001f49  jz      short loc_140001F4F
0x140001f4b  test    al, 10h
0x140001f4d  jz      short loc_140001F80
0x140001f4f  mov     rcx, rbx; unsigned __int16 *
0x140001f52  call    ?IsExe@@YAHPEBG@Z; IsExe(ushort const *)
0x140001f57  test    eax, eax
0x140001f59  jnz     short loc_140001F80
0x140001f5b  mov     rcx, rbx; unsigned __int16 *
0x140001f5e  call    ?IsDll@@YAHPEBG@Z; IsDll(ushort const *)
0x140001f63  test    eax, eax
0x140001f65  jnz     short loc_140001F80
0x140001f67  mov     rcx, rbx; unsigned __int16 *
0x140001f6a  call    ?IsWinMD@@YAHPEBG@Z; IsWinMD(ushort const *)
0x140001f6f  test    eax, eax
0x140001f71  jnz     short loc_140001F80
0x140001f73  mov     rdx, rbx; unsigned __int16 *
0x140001f76  mov     rcx, rdi; this
0x140001f79  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x140001f7e  jmp     short loc_140001F8E
0x140001f80  mov     r8d, esi; int
0x140001f83  mov     rdx, rdi; this
0x140001f86  mov     rcx, rbx; unsigned __int16 *
0x140001f89  call    ?CanonicalizePathAux@@YAXPEBGAEAVSString@@H@Z; CanonicalizePathAux(ushort const *,SString &,int)
0x140001f8e  mov     rbx, [rsp+28h+arg_0]
0x140001f93  mov     rsi, [rsp+28h+arg_8]
0x140001f98  add     rsp, 20h
0x140001f9c  pop     rdi
0x140001f9d  retn
```
