# CComponentData::Initialize(IUnknown *)

- ea: `0x1800061b0`
- end: `0x18000630c`
- name: `?Initialize@CComponentData@@UEAAJPEAUIUnknown@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(CComponentData *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800061b0`
- `0x18001e264`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800062a6`
- `KERNEL32!GetLastError` at `0x1800062a6`
- `USER32!LoadBitmapW` at `0x180006298`
- `USER32!LoadBitmapW` at `0x180006298`
- `GDI32!DeleteObject` at `0x1800062e4`
- `GDI32!DeleteObject` at `0x1800062e4`

## pseudocode

```c
__int64 __fastcall CComponentData::Initialize(CComponentData *this, struct IUnknown *a2)
{
  signed int v4; // ebx
  _QWORD *v5; // r14
  HBITMAP BitmapW; // rax
  HBITMAP v7; // rdi
  signed int LastError; // eax
  __int64 v10; // [rsp+60h] [rbp+8h] BYREF

  v10 = 0;
  if ( (int)CSynchWindow::Register(this, (CComponentData *)((char *)this - 8)) >= 0 )
    *((_WORD *)this + 24) |= 8u;
  v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IConsoleNameSpace,
         (char *)this + 1152);
  if ( v4 >= 0 )
  {
    v5 = (_QWORD *)((char *)this + 1144);
    v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IConsole2,
           (char *)this + 1144);
    if ( v4 >= 0 )
    {
      v4 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v5)(
             *v5,
             &IID_IPropertySheetProvider,
             (char *)this + 1160);
      if ( v4 >= 0 )
      {
        v4 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v5)(*v5, &IID_IStringTable, (char *)this + 1168);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v5 + 48LL))(*v5, &v10);
          if ( v4 >= 0 )
          {
            BitmapW = LoadBitmapW(g_hinst, (LPCWSTR)0x66);
            v7 = BitmapW;
            if ( BitmapW )
            {
              v4 = (*(__int64 (__fastcall **)(__int64, HBITMAP, HBITMAP, _QWORD, int))(*(_QWORD *)v10 + 32LL))(
                     v10,
                     BitmapW,
                     BitmapW,
                     0,
                     65280);
              DeleteObject(v7);
            }
            else
            {
              LastError = GetLastError();
              v4 = LastError;
              if ( LastError > 0 )
                v4 = (unsigned __int16)LastError | 0x80070000;
            }
          }
        }
      }
    }
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800061b0  push    rbx
0x1800061b2  push    rsi
0x1800061b3  push    rdi
0x1800061b4  push    r14
0x1800061b6  sub     rsp, 38h
0x1800061ba  mov     rsi, rdx
0x1800061bd  mov     [rsp+58h+arg_0], 0
0x1800061c6  lea     rdx, [rcx-8]; struct CComponentData *
0x1800061ca  mov     rdi, rcx
0x1800061cd  call    ?Register@CSynchWindow@@QEAAJPEAVCComponentData@@@Z; CSynchWindow::Register(CComponentData *)
0x1800061d2  test    eax, eax
0x1800061d4  js      short loc_1800061DB
0x1800061d6  or      word ptr [rdi+30h], 8
0x1800061db  mov     rax, [rsi]
0x1800061de  lea     r8, [rdi+480h]
0x1800061e5  lea     rdx, IID_IConsoleNameSpace
0x1800061ec  mov     rcx, rsi
0x1800061ef  mov     rax, [rax]
0x1800061f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061f7  mov     ebx, eax
0x1800061f9  test    eax, eax
0x1800061fb  js      loc_1800062EA
0x180006201  mov     rax, [rsi]
0x180006204  lea     r14, [rdi+478h]
0x18000620b  mov     r8, r14
0x18000620e  lea     rdx, IID_IConsole2
0x180006215  mov     rcx, rsi
0x180006218  mov     rax, [rax]
0x18000621b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006220  mov     ebx, eax
0x180006222  test    eax, eax
0x180006224  js      loc_1800062EA
0x18000622a  mov     rcx, [r14]
0x18000622d  lea     r8, [rdi+488h]
0x180006234  lea     rdx, IID_IPropertySheetProvider
0x18000623b  mov     rax, [rcx]
0x18000623e  mov     rax, [rax]
0x180006241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006246  mov     ebx, eax
0x180006248  test    eax, eax
0x18000624a  js      loc_1800062EA
0x180006250  mov     rcx, [r14]
0x180006253  lea     r8, [rdi+490h]
0x18000625a  lea     rdx, IID_IStringTable
0x180006261  mov     rax, [rcx]
0x180006264  mov     rax, [rax]
0x180006267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000626c  mov     ebx, eax
0x18000626e  test    eax, eax
0x180006270  js      short loc_1800062EA
0x180006272  mov     rcx, [r14]
0x180006275  lea     rdx, [rsp+58h+arg_0]
0x18000627a  mov     rax, [rcx]
0x18000627d  mov     rax, [rax+30h]
0x180006281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006286  mov     ebx, eax
0x180006288  test    eax, eax
0x18000628a  js      short loc_1800062EA
0x18000628c  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180006293  mov     edx, 66h ; 'f'; lpBitmapName
0x180006298  call    cs:__imp_LoadBitmapW
0x18000629e  mov     rdi, rax
0x1800062a1  test    rax, rax
0x1800062a4  jnz     short loc_1800062BD
0x1800062a6  call    cs:__imp_GetLastError
0x1800062ac  mov     ebx, eax
0x1800062ae  test    eax, eax
0x1800062b0  jle     short loc_1800062EA
0x1800062b2  movzx   ebx, ax
0x1800062b5  or      ebx, 80070000h
0x1800062bb  jmp     short loc_1800062EA
0x1800062bd  mov     rcx, [rsp+58h+arg_0]
0x1800062c2  xor     r9d, r9d
0x1800062c5  mov     r8, rdi
0x1800062c8  mov     [rsp+58h+var_38], 0FF00h
0x1800062d0  mov     rdx, rdi
0x1800062d3  mov     rax, [rcx]
0x1800062d6  mov     rax, [rax+20h]
0x1800062da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062df  mov     rcx, rdi; ho
0x1800062e2  mov     ebx, eax
0x1800062e4  call    cs:__imp_DeleteObject
0x1800062ea  mov     rcx, [rsp+58h+arg_0]
0x1800062ef  test    rcx, rcx
0x1800062f2  jz      short loc_180006300
0x1800062f4  mov     rax, [rcx]
0x1800062f7  mov     rax, [rax+10h]
0x1800062fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006300  mov     eax, ebx
0x180006302  add     rsp, 38h
0x180006306  pop     r14
0x180006308  pop     rdi
0x180006309  pop     rsi
0x18000630a  pop     rbx
0x18000630b  retn
```
