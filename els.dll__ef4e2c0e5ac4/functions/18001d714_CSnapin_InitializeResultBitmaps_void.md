# CSnapin::_InitializeResultBitmaps(void)

- ea: `0x18001d714`
- end: `0x18001d7d2`
- name: `?_InitializeResultBitmaps@CSnapin@@AEAAJXZ`
- size: `190`
- prototype: `__int64 __fastcall(CSnapin *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c770`

## callees

- `0x18001d714`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d740`
- `KERNEL32!GetLastError` at `0x18001d76e`
- `KERNEL32!GetLastError` at `0x18001d740`
- `KERNEL32!GetLastError` at `0x18001d76e`
- `USER32!LoadBitmapW` at `0x18001d732`
- `USER32!LoadBitmapW` at `0x18001d760`
- `USER32!LoadBitmapW` at `0x18001d732`
- `USER32!LoadBitmapW` at `0x18001d760`
- `GDI32!DeleteObject` at `0x18001d7b1`
- `GDI32!DeleteObject` at `0x18001d7ba`
- `GDI32!DeleteObject` at `0x18001d7b1`
- `GDI32!DeleteObject` at `0x18001d7ba`

## pseudocode

```c
signed int __fastcall CSnapin::_InitializeResultBitmaps(CSnapin *this)
{
  HBITMAP BitmapW; // rdi
  signed int result; // eax
  HBITMAP v4; // rax
  HBITMAP v5; // rsi
  signed int LastError; // eax
  unsigned int v7; // ebx
  HBITMAP v8; // rcx

  BitmapW = LoadBitmapW(g_hinst, (LPCWSTR)0x64);
  if ( BitmapW )
  {
    v4 = LoadBitmapW(g_hinst, (LPCWSTR)0x65);
    v5 = v4;
    if ( v4 )
    {
      v7 = (*(__int64 (__fastcall **)(_QWORD, HBITMAP, HBITMAP, _QWORD, int))(**((_QWORD **)this + 205) + 32LL))(
             *((_QWORD *)this + 205),
             BitmapW,
             v4,
             0,
             65280);
      DeleteObject(BitmapW);
      v8 = v5;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v8 = BitmapW;
    }
    DeleteObject(v8);
    return v7;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18001d714  mov     [rsp+arg_0], rbx
0x18001d719  mov     [rsp+arg_8], rsi
0x18001d71e  push    rdi
0x18001d71f  sub     rsp, 30h
0x18001d723  mov     rbx, rcx
0x18001d726  mov     edx, 64h ; 'd'; lpBitmapName
0x18001d72b  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18001d732  call    cs:__imp_LoadBitmapW
0x18001d738  mov     rdi, rax
0x18001d73b  test    rax, rax
0x18001d73e  jnz     short loc_18001D754
0x18001d740  call    cs:__imp_GetLastError
0x18001d746  test    eax, eax
0x18001d748  jle     short loc_18001D7C2
0x18001d74a  movzx   eax, ax
0x18001d74d  or      eax, 80070000h
0x18001d752  jmp     short loc_18001D7C2
0x18001d754  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18001d75b  mov     edx, 65h ; 'e'; lpBitmapName
0x18001d760  call    cs:__imp_LoadBitmapW
0x18001d766  mov     rsi, rax
0x18001d769  test    rax, rax
0x18001d76c  jnz     short loc_18001D788
0x18001d76e  call    cs:__imp_GetLastError
0x18001d774  mov     ebx, eax
0x18001d776  test    eax, eax
0x18001d778  jle     short loc_18001D783
0x18001d77a  movzx   ebx, ax
0x18001d77d  or      ebx, 80070000h
0x18001d783  mov     rcx, rdi
0x18001d786  jmp     short loc_18001D7BA
0x18001d788  mov     rcx, [rbx+668h]
0x18001d78f  xor     r9d, r9d
0x18001d792  mov     r8, rsi
0x18001d795  mov     [rsp+38h+var_18], 0FF00h
0x18001d79d  mov     rdx, rdi
0x18001d7a0  mov     rax, [rcx]
0x18001d7a3  mov     rax, [rax+20h]
0x18001d7a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d7ac  mov     rcx, rdi; ho
0x18001d7af  mov     ebx, eax
0x18001d7b1  call    cs:__imp_DeleteObject
0x18001d7b7  mov     rcx, rsi; ho
0x18001d7ba  call    cs:__imp_DeleteObject
0x18001d7c0  mov     eax, ebx
0x18001d7c2  mov     rbx, [rsp+38h+arg_0]
0x18001d7c7  mov     rsi, [rsp+38h+arg_8]
0x18001d7cc  add     rsp, 30h
0x18001d7d0  pop     rdi
0x18001d7d1  retn
```
