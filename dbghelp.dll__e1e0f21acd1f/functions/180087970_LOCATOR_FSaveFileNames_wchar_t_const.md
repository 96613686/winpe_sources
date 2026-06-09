# LOCATOR::FSaveFileNames(wchar_t const *)

- ea: `0x180087970`
- end: `0x180087a1b`
- name: `?FSaveFileNames@LOCATOR@@AEAA_NPEB_W@Z`
- size: `171`
- prototype: `bool __fastcall(LOCATOR *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180084420`

## callees

- `0x180087970`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180087980`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x180087980`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800879e8`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800879e8`

## pseudocode

```c
bool __fastcall LOCATOR::FSaveFileNames(LOCATOR *this, const wchar_t *a2)
{
  const wchar_t *v3; // rax

  v3 = (const wchar_t *)_o__wcsdup(a2);
  *((_QWORD *)this + 284) = v3;
  if ( v3 )
  {
    _wsplitpath_s(v3, 0, 0, 0, 0, (wchar_t *)this + 1140, 0x100u, (wchar_t *)this + 1396, 0x100u);
    if ( !*((_WORD *)this + 1396) || (v3 = (const wchar_t *)((char *)this + 2794), !*((_WORD *)this + 1397)) )
      v3 = 0;
    *((_QWORD *)this + 413) = v3;
    LOBYTE(v3) = 1;
  }
  else
  {
    *(_DWORD *)this = 2;
    *((_WORD *)this + 2) = 0;
  }
  return (char)v3;
}

```

## disassembly

```asm
0x180087970  mov     [rsp+arg_8], rsi
0x180087975  push    rdi
0x180087976  sub     rsp, 50h
0x18008797a  mov     rdi, rcx
0x18008797d  mov     rcx, rdx
0x180087980  call    cs:__imp__o__wcsdup
0x180087986  xor     esi, esi
0x180087988  mov     [rdi+8E0h], rax
0x18008798f  mov     rcx, rax; FullPath
0x180087992  test    rax, rax
0x180087995  jnz     short loc_1800879AC
0x180087997  mov     dword ptr [rdi], 2
0x18008799d  mov     [rdi+4], si
0x1800879a1  mov     rsi, [rsp+58h+arg_8]
0x1800879a6  add     rsp, 50h
0x1800879aa  pop     rdi
0x1800879ab  retn
0x1800879ac  mov     [rsp+58h+ExtCount], 100h; ExtCount
0x1800879b5  lea     rax, [rdi+8E8h]
0x1800879bc  mov     [rsp+58h+arg_0], rbx
0x1800879c1  xor     r9d, r9d; Dir
0x1800879c4  lea     rbx, [rdi+0AE8h]
0x1800879cb  xor     r8d, r8d; DriveCount
0x1800879ce  mov     [rsp+58h+Ext], rbx; Ext
0x1800879d3  xor     edx, edx; Drive
0x1800879d5  mov     [rsp+58h+FilenameCount], 100h; FilenameCount
0x1800879de  mov     [rsp+58h+Filename], rax; Filename
0x1800879e3  mov     [rsp+58h+DirCount], rsi; DirCount
0x1800879e8  call    cs:__imp__wsplitpath_s
0x1800879ee  cmp     [rbx], si
0x1800879f1  mov     rbx, [rsp+58h+arg_0]
0x1800879f6  jz      short loc_180087A04
0x1800879f8  lea     rax, [rdi+0AEAh]
0x1800879ff  cmp     [rax], si
0x180087a02  jnz     short loc_180087A07
0x180087a04  mov     rax, rsi
0x180087a07  mov     [rdi+0CE8h], rax
0x180087a0e  mov     al, 1
0x180087a10  mov     rsi, [rsp+58h+arg_8]
0x180087a15  add     rsp, 50h
0x180087a19  pop     rdi
0x180087a1a  retn
```
