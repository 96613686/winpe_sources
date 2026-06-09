# COffscreenDC::FreeData(void)

- ea: `0x18004e418`
- end: `0x18004e48f`
- name: `?FreeData@COffscreenDC@@AEAAXXZ`
- size: `119`
- prototype: `void __fastcall(COffscreenDC *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18004e4a0`
- `0x180095890`
- `0x180100654`
- `0x18010e4f4`
- `0x18016300c`

## callees

- `0x18004e418`
- `0x1801eb774`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18004e462`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x18004e462`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18004e481`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18004e481`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18004e44b`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18004e44b`

## pseudocode

```c
void __fastcall COffscreenDC::FreeData(COffscreenDC *this, __int64 a2, int a3)
{
  HDC v4; // rcx
  HPALETTE v5; // rdx
  void *v6; // rdx
  void *v7; // rcx

  v4 = *(HDC *)this;
  if ( v4 )
  {
    v5 = (HPALETTE)*((_QWORD *)this + 3);
    if ( v5 )
      CW32System::SelectPalette(v4, v5, a3);
    v6 = (void *)*((_QWORD *)this + 1);
    if ( v6 )
      SelectObject(*(HDC *)this, v6);
    v7 = (void *)*((_QWORD *)this + 2);
    if ( v7 )
    {
      DeleteObject(v7);
      *((_QWORD *)this + 2) = 0;
    }
    DeleteDC(*(HDC *)this);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18004e418  push    rbx
0x18004e41a  sub     rsp, 20h
0x18004e41e  mov     rbx, rcx
0x18004e421  mov     rcx, [rcx]; HDC
0x18004e424  test    rcx, rcx
0x18004e427  jnz     short loc_18004E430
0x18004e429  add     rsp, 20h
0x18004e42d  pop     rbx
0x18004e42e  retn
0x18004e430  mov     rdx, [rbx+18h]; HPALETTE
0x18004e434  test    rdx, rdx
0x18004e437  jnz     short loc_18004E477
0x18004e439  mov     rdx, [rbx+8]; h
0x18004e43d  test    rdx, rdx
0x18004e440  jnz     short loc_18004E47E
0x18004e442  mov     rcx, [rbx+10h]; ho
0x18004e446  test    rcx, rcx
0x18004e449  jz      short loc_18004E45F
0x18004e44b  call    cs:__imp_DeleteObject
0x18004e452  nop     dword ptr [rax+rax+00h]
0x18004e457  mov     qword ptr [rbx+10h], 0
0x18004e45f  mov     rcx, [rbx]; hdc
0x18004e462  call    cs:__imp_DeleteDC
0x18004e469  nop     dword ptr [rax+rax+00h]
0x18004e46e  mov     qword ptr [rbx], 0
0x18004e475  jmp     short loc_18004E429
0x18004e477  call    ?SelectPalette@CW32System@@SAPEAUHPALETTE__@@PEAUHDC__@@PEAU2@H@Z; CW32System::SelectPalette(HDC__ *,HPALETTE__ *,int)
0x18004e47c  jmp     short loc_18004E439
0x18004e47e  mov     rcx, [rbx]; hdc
0x18004e481  call    cs:__imp_SelectObject
0x18004e488  nop     dword ptr [rax+rax+00h]
0x18004e48d  jmp     short loc_18004E442
```
