# CSnapinAbout::GetStaticFolderImage(HBITMAP__ * *,HBITMAP__ * *,HBITMAP__ * *,ulong *)

- ea: `0x180004160`
- end: `0x18000428c`
- name: `?GetStaticFolderImage@CSnapinAbout@@UEAAJPEAPEAUHBITMAP__@@00PEAK@Z`
- size: `300`
- prototype: `__int64 __fastcall(CSnapinAbout *__hidden this, HBITMAP *, HBITMAP *, HBITMAP *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004160`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800041b2`
- `KERNEL32!GetLastError` at `0x180004200`
- `KERNEL32!GetLastError` at `0x180004241`
- `KERNEL32!GetLastError` at `0x1800041b2`
- `KERNEL32!GetLastError` at `0x180004200`
- `KERNEL32!GetLastError` at `0x180004241`
- `USER32!LoadBitmapW` at `0x1800041a4`
- `USER32!LoadBitmapW` at `0x180004233`
- `USER32!LoadBitmapW` at `0x1800041a4`
- `USER32!LoadBitmapW` at `0x180004233`
- `USER32!LoadImageW` at `0x1800041f2`
- `USER32!LoadImageW` at `0x1800041f2`
- `GDI32!DeleteObject` at `0x180004218`
- `GDI32!DeleteObject` at `0x180004259`
- `GDI32!DeleteObject` at `0x180004269`
- `GDI32!DeleteObject` at `0x180004218`
- `GDI32!DeleteObject` at `0x180004259`
- `GDI32!DeleteObject` at `0x180004269`

## pseudocode

```c
__int64 __fastcall CSnapinAbout::GetStaticFolderImage(
        CSnapinAbout *this,
        HBITMAP *a2,
        HBITMAP *a3,
        HBITMAP *a4,
        unsigned int *a5)
{
  HINSTANCE v6; // rcx
  HBITMAP BitmapW; // rax
  signed int v10; // eax
  unsigned int v11; // ebx
  HBITMAP ImageW; // rax
  signed int v13; // eax
  HBITMAP v14; // rax
  signed int LastError; // eax

  v6 = g_hinst;
  *a5 = 65280;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  BitmapW = LoadBitmapW(v6, (LPCWSTR)0x135);
  *a2 = BitmapW;
  if ( BitmapW )
  {
    ImageW = (HBITMAP)LoadImageW(g_hinst, (LPCWSTR)0x136, 0, 0, 0, 0);
    *a3 = ImageW;
    if ( ImageW )
    {
      v14 = LoadBitmapW(g_hinst, (LPCWSTR)0x65);
      *a4 = v14;
      if ( v14 )
      {
        return 0;
      }
      else
      {
        LastError = GetLastError();
        v11 = LastError;
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        DeleteObject(*a2);
        *a2 = 0;
        DeleteObject(*a3);
        *a3 = 0;
      }
    }
    else
    {
      v13 = GetLastError();
      v11 = v13;
      if ( v13 > 0 )
        v11 = (unsigned __int16)v13 | 0x80070000;
      DeleteObject(*a2);
      *a2 = 0;
    }
  }
  else
  {
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      return (unsigned __int16)v10 | 0x80070000;
  }
  return v11;
}

```

## disassembly

```asm
0x180004160  mov     [rsp+arg_0], rbx
0x180004165  mov     [rsp+arg_8], rsi
0x18000416a  push    rdi
0x18000416b  sub     rsp, 30h
0x18000416f  mov     rax, [rsp+38h+arg_20]
0x180004174  mov     rdi, rdx
0x180004177  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000417e  mov     rbx, r9
0x180004181  mov     rsi, r8
0x180004184  mov     dword ptr [rax], 0FF00h
0x18000418a  mov     qword ptr [rdx], 0
0x180004191  mov     edx, 135h; lpBitmapName
0x180004196  mov     qword ptr [r8], 0
0x18000419d  mov     qword ptr [r9], 0
0x1800041a4  call    cs:__imp_LoadBitmapW
0x1800041aa  mov     [rdi], rax
0x1800041ad  test    rax, rax
0x1800041b0  jnz     short loc_1800041D0
0x1800041b2  call    cs:__imp_GetLastError
0x1800041b8  mov     ebx, eax
0x1800041ba  test    eax, eax
0x1800041bc  jle     loc_18000427A
0x1800041c2  movzx   ebx, ax
0x1800041c5  or      ebx, 80070000h
0x1800041cb  jmp     loc_18000427A
0x1800041d0  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInst
0x1800041d7  xor     r9d, r9d; cx
0x1800041da  mov     [rsp+38h+fuLoad], 0; fuLoad
0x1800041e2  xor     r8d, r8d; type
0x1800041e5  mov     edx, 136h; name
0x1800041ea  mov     [rsp+38h+cy], 0; cy
0x1800041f2  call    cs:__imp_LoadImageW
0x1800041f8  mov     [rsi], rax
0x1800041fb  test    rax, rax
0x1800041fe  jnz     short loc_180004227
0x180004200  call    cs:__imp_GetLastError
0x180004206  mov     ebx, eax
0x180004208  test    eax, eax
0x18000420a  jle     short loc_180004215
0x18000420c  movzx   ebx, ax
0x18000420f  or      ebx, 80070000h
0x180004215  mov     rcx, [rdi]; ho
0x180004218  call    cs:__imp_DeleteObject
0x18000421e  mov     qword ptr [rdi], 0
0x180004225  jmp     short loc_18000427A
0x180004227  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000422e  mov     edx, 65h ; 'e'; lpBitmapName
0x180004233  call    cs:__imp_LoadBitmapW
0x180004239  mov     [rbx], rax
0x18000423c  test    rax, rax
0x18000423f  jnz     short loc_180004278
0x180004241  call    cs:__imp_GetLastError
0x180004247  mov     ebx, eax
0x180004249  test    eax, eax
0x18000424b  jle     short loc_180004256
0x18000424d  movzx   ebx, ax
0x180004250  or      ebx, 80070000h
0x180004256  mov     rcx, [rdi]; ho
0x180004259  call    cs:__imp_DeleteObject
0x18000425f  mov     qword ptr [rdi], 0
0x180004266  mov     rcx, [rsi]; ho
0x180004269  call    cs:__imp_DeleteObject
0x18000426f  mov     qword ptr [rsi], 0
0x180004276  jmp     short loc_18000427A
0x180004278  xor     ebx, ebx
0x18000427a  mov     rsi, [rsp+38h+arg_8]
0x18000427f  mov     eax, ebx
0x180004281  mov     rbx, [rsp+38h+arg_0]
0x180004286  add     rsp, 30h
0x18000428a  pop     rdi
0x18000428b  retn
```
