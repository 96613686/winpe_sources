# COffscreenDC::Realloc(long,long)

- ea: `0x180177cb4`
- end: `0x180177d0f`
- name: `?Realloc@COffscreenDC@@QEAAHJJ@Z`
- size: `91`
- prototype: `__int64 __fastcall(COffscreenDC *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800ff310`

## callees

- `0x180177cb4`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180177cde`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180177cde`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x180177cc4`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x180177cc4`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180177cee`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180177cee`

## pseudocode

```c
__int64 __fastcall COffscreenDC::Realloc(COffscreenDC *this, int a2, int a3)
{
  __int64 result; // rax
  __int64 v5; // rdi

  result = (__int64)CreateCompatibleBitmap(*(HDC *)this, a2, a3);
  v5 = result;
  if ( result )
  {
    SelectObject(*(HDC *)this, (HGDIOBJ)result);
    DeleteObject(*((HGDIOBJ *)this + 2));
    result = 1;
    *((_QWORD *)this + 2) = v5;
  }
  return result;
}

```

## disassembly

```asm
0x180177cb4  mov     [rsp+arg_0], rbx
0x180177cb9  push    rdi
0x180177cba  sub     rsp, 20h
0x180177cbe  mov     rbx, rcx
0x180177cc1  mov     rcx, [rcx]; hdc
0x180177cc4  call    cs:__imp_CreateCompatibleBitmap
0x180177ccb  nop     dword ptr [rax+rax+00h]
0x180177cd0  mov     rdi, rax
0x180177cd3  test    rax, rax
0x180177cd6  jz      short loc_180177D03
0x180177cd8  mov     rcx, [rbx]; hdc
0x180177cdb  mov     rdx, rdi; h
0x180177cde  call    cs:__imp_SelectObject
0x180177ce5  nop     dword ptr [rax+rax+00h]
0x180177cea  mov     rcx, [rbx+10h]; ho
0x180177cee  call    cs:__imp_DeleteObject
0x180177cf5  nop     dword ptr [rax+rax+00h]
0x180177cfa  mov     eax, 1
0x180177cff  mov     [rbx+10h], rdi
0x180177d03  mov     rbx, [rsp+28h+arg_0]
0x180177d08  add     rsp, 20h
0x180177d0c  pop     rdi
0x180177d0d  retn
```
