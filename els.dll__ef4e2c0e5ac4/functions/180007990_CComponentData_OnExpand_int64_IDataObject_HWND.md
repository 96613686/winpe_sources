# CComponentData::_OnExpand(__int64,IDataObject *,HWND__ *)

- ea: `0x180007990`
- end: `0x180007a02`
- name: `?_OnExpand@CComponentData@@AEAAJ_JPEAUIDataObject@@PEAUHWND__@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(CComponentData *__hidden this, __int64, struct IDataObject *, HWND hWnd)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800065d0`
- `0x180021820`

## callees

- `0x180007488`
- `0x180007990`
- `0x180008890`
- `0x180008958`
- `0x18001f638`

## pseudocode

```c
int __fastcall CComponentData::_OnExpand(CComponentData *this, __int64 a2, struct IDataObject *a3, HWND hWnd)
{
  struct CDataObject *OwnDataObject; // rax
  int result; // eax

  OwnDataObject = ExtractOwnDataObject(a3);
  if ( !OwnDataObject )
    return CComponentData::_ScopePaneAddExtensionRoot(this, a2, a3);
  if ( *((_DWORD *)OwnDataObject + 7) )
    return 0;
  *((_QWORD *)this + 142) = a2;
  if ( (*((_BYTE *)this + 56) & 0x10) != 0 )
    return CComponentData::_ScopePaneAddLogSet(this, hWnd);
  result = CComponentData::_CreateLogSet(this, a3, a2, 0);
  if ( result >= 0 )
    return CComponentData::_ScopePaneAddLogSet(this, hWnd);
  return result;
}

```

## disassembly

```asm
0x180007990  push    rbx
0x180007992  push    rbp
0x180007993  push    rsi
0x180007994  push    rdi
0x180007995  sub     rsp, 28h
0x180007999  mov     rbx, rcx
0x18000799c  mov     rbp, r9
0x18000799f  mov     rcx, r8; struct IDataObject *
0x1800079a2  mov     rsi, r8
0x1800079a5  mov     rdi, rdx
0x1800079a8  call    ?ExtractOwnDataObject@@YAPEAVCDataObject@@PEAUIDataObject@@@Z; ExtractOwnDataObject(IDataObject *)
0x1800079ad  test    rax, rax
0x1800079b0  jnz     short loc_1800079C2
0x1800079b2  mov     r8, rsi; struct IDataObject *
0x1800079b5  mov     rdx, rdi; __int64
0x1800079b8  mov     rcx, rbx; this
0x1800079bb  call    ?_ScopePaneAddExtensionRoot@CComponentData@@AEAAJ_JPEAUIDataObject@@@Z; CComponentData::_ScopePaneAddExtensionRoot(__int64,IDataObject *)
0x1800079c0  jmp     short loc_1800079F9
0x1800079c2  cmp     dword ptr [rax+1Ch], 0
0x1800079c6  jz      short loc_1800079CC
0x1800079c8  xor     eax, eax
0x1800079ca  jmp     short loc_1800079F9
0x1800079cc  mov     [rbx+470h], rdi
0x1800079d3  test    byte ptr [rbx+38h], 10h
0x1800079d7  jnz     short loc_1800079EE
0x1800079d9  xor     r9d, r9d; __int64
0x1800079dc  mov     r8, rdi; __int64
0x1800079df  mov     rdx, rsi; struct IDataObject *
0x1800079e2  mov     rcx, rbx; this
0x1800079e5  call    ?_CreateLogSet@CComponentData@@AEAAJPEAUIDataObject@@_J1@Z; CComponentData::_CreateLogSet(IDataObject *,__int64,__int64)
0x1800079ea  test    eax, eax
0x1800079ec  js      short loc_1800079F9
0x1800079ee  mov     rdx, rbp; hWnd
0x1800079f1  mov     rcx, rbx; this
0x1800079f4  call    ?_ScopePaneAddLogSet@CComponentData@@AEAAJPEAUHWND__@@@Z; CComponentData::_ScopePaneAddLogSet(HWND__ *)
0x1800079f9  add     rsp, 28h
0x1800079fd  pop     rdi
0x1800079fe  pop     rsi
0x1800079ff  pop     rbp
0x180007a00  pop     rbx
0x180007a01  retn
```
