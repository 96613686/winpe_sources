# DriverGdi::GetBrush(ulong)

- ea: `0x18003b578`
- end: `0x18003b62b`
- name: `?GetBrush@DriverGdi@@AEAAPEAUHBRUSH__@@K@Z`
- size: `179`
- prototype: `HBRUSH __fastcall(DriverGdi *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18003a9e0`
- `0x18004d5e8`
- `0x1800839b0`

## callees

- `0x18003b578`
- `0x1800c1c50`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x18003b5cd`
- `GDI32!CreateSolidBrush` at `0x18003b5cd`
- `GDI32!GetStockObject` at `0x18003b602`
- `GDI32!GetStockObject` at `0x18003b602`
- `GDI32!DeleteObject` at `0x18003b5b5`
- `GDI32!DeleteObject` at `0x18003b618`
- `GDI32!DeleteObject` at `0x18003b5b5`
- `GDI32!DeleteObject` at `0x18003b618`

## pseudocode

```c
HBRUSH __fastcall DriverGdi::GetBrush(DriverGdi *this, int a2)
{
  HGDIOBJ *v2; // rbx
  COLORREF v3; // edi
  HBRUSH SolidBrush; // rax

  v2 = (HGDIOBJ *)((char *)this + 40);
  v3 = a2 | 0x2000000;
  if ( *((_DWORD *)this + 10) == 1198932785 )
  {
    if ( !*((_DWORD *)this + 11) && v3 == *((_DWORD *)this + 15) )
      return ConvertBrushToGdi::GetGdiBrush((ConvertBrushToGdi *)v2);
    DeleteObject(*((HGDIOBJ *)this + 6));
    if ( *((_DWORD *)v2 + 1) == 2 )
    {
      DeleteObject(v2[3]);
      v2[3] = 0;
    }
  }
  *((_DWORD *)v2 + 1) = 0;
  SolidBrush = CreateSolidBrush(v3);
  v2[1] = SolidBrush;
  *((_DWORD *)v2 + 5) = v3;
  *(_DWORD *)v2 = SolidBrush != 0 ? 1198932785 : 1279869254;
  if ( !SolidBrush )
    v2[1] = GetStockObject(2);
  return ConvertBrushToGdi::GetGdiBrush((ConvertBrushToGdi *)v2);
}

```

## disassembly

```asm
0x18003b578  mov     [rsp+arg_0], rbx
0x18003b57d  push    rdi
0x18003b57e  sub     rsp, 20h
0x18003b582  mov     edi, edx
0x18003b584  lea     rbx, [rcx+28h]
0x18003b588  bts     edi, 19h
0x18003b58c  cmp     dword ptr [rbx], 47764331h
0x18003b592  jnz     short loc_18003B5C7
0x18003b594  cmp     dword ptr [rbx+4], 0
0x18003b598  jnz     short loc_18003B5B1
0x18003b59a  cmp     edi, [rbx+14h]
0x18003b59d  jnz     short loc_18003B5B1
0x18003b59f  mov     rcx, rbx; this
0x18003b5a2  mov     rbx, [rsp+28h+arg_0]
0x18003b5a7  add     rsp, 20h
0x18003b5ab  pop     rdi
0x18003b5ac  jmp     ?GetGdiBrush@ConvertBrushToGdi@@QEAAPEAUHBRUSH__@@XZ; ConvertBrushToGdi::GetGdiBrush(void)
0x18003b5b1  mov     rcx, [rbx+8]; ho
0x18003b5b5  call    cs:__imp_DeleteObject
0x18003b5bc  nop     dword ptr [rax+rax+00h]
0x18003b5c1  cmp     dword ptr [rbx+4], 2
0x18003b5c5  jz      short loc_18003B614
0x18003b5c7  and     dword ptr [rbx+4], 0
0x18003b5cb  mov     ecx, edi; color
0x18003b5cd  call    cs:__imp_CreateSolidBrush
0x18003b5d4  nop     dword ptr [rax+rax+00h]
0x18003b5d9  mov     [rbx+8], rax
0x18003b5dd  mov     rdx, rax
0x18003b5e0  neg     rdx
0x18003b5e3  mov     [rbx+14h], edi
0x18003b5e6  sbb     r8d, r8d
0x18003b5e9  and     r8d, 0FB2D01EBh
0x18003b5f0  add     r8d, 4C494146h
0x18003b5f7  mov     [rbx], r8d
0x18003b5fa  test    rax, rax
0x18003b5fd  jnz     short loc_18003B59F
0x18003b5ff  lea     ecx, [rax+2]; i
0x18003b602  call    cs:__imp_GetStockObject
0x18003b609  nop     dword ptr [rax+rax+00h]
0x18003b60e  mov     [rbx+8], rax
0x18003b612  jmp     short loc_18003B59F
0x18003b614  mov     rcx, [rbx+18h]; ho
0x18003b618  call    cs:__imp_DeleteObject
0x18003b61f  nop     dword ptr [rax+rax+00h]
0x18003b624  and     qword ptr [rbx+18h], 0
0x18003b629  jmp     short loc_18003B5C7
```
