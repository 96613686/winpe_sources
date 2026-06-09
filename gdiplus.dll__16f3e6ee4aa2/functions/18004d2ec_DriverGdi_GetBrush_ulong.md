# DriverGdi::GetBrush(ulong)

- ea: `0x18004d2ec`
- end: `0x18004d390`
- name: `?GetBrush@DriverGdi@@AEAAPEAUHBRUSH__@@K@Z`
- size: `164`
- prototype: `HBRUSH __fastcall(DriverGdi *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180018e78`
- `0x18004c9e0`
- `0x18004cc00`

## callees

- `0x18004d2ec`
- `0x18004d398`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x18004d331`
- `GDI32!CreateSolidBrush` at `0x18004d331`
- `GDI32!GetStockObject` at `0x18004d35f`
- `GDI32!GetStockObject` at `0x18004d35f`
- `GDI32!DeleteObject` at `0x18004d371`
- `GDI32!DeleteObject` at `0x18004d380`
- `GDI32!DeleteObject` at `0x18004d371`
- `GDI32!DeleteObject` at `0x18004d380`

## pseudocode

```c
HBRUSH __fastcall DriverGdi::GetBrush(DriverGdi *this, int a2)
{
  HGDIOBJ *v2; // rbx
  COLORREF v3; // ebp
  _DWORD *v4; // rdi
  _QWORD *v6; // rsi
  HBRUSH SolidBrush; // rax

  v2 = (HGDIOBJ *)((char *)this + 40);
  v3 = a2 | 0x2000000;
  v4 = (_DWORD *)((char *)this + 44);
  if ( *((_DWORD *)this + 10) == 1198932785 )
  {
    if ( !*v4 && v3 == *((_DWORD *)this + 15) )
      return ConvertBrushToGdi::GetGdiBrush((ConvertBrushToGdi *)v2);
    v6 = (_QWORD *)((char *)this + 48);
    DeleteObject(*((HGDIOBJ *)this + 6));
    if ( *v4 == 2 )
    {
      DeleteObject(v2[3]);
      v2[3] = 0;
    }
  }
  else
  {
    v6 = (_QWORD *)((char *)this + 48);
  }
  *v4 = 0;
  SolidBrush = CreateSolidBrush(v3);
  *v6 = SolidBrush;
  *((_DWORD *)v2 + 5) = v3;
  *(_DWORD *)v2 = SolidBrush != 0 ? 1198932785 : 1279869254;
  if ( !SolidBrush )
    *v6 = GetStockObject(2);
  return ConvertBrushToGdi::GetGdiBrush((ConvertBrushToGdi *)v2);
}

```

## disassembly

```asm
0x18004d2ec  push    rbx
0x18004d2ee  push    rbp
0x18004d2ef  push    rsi
0x18004d2f0  push    rdi
0x18004d2f1  sub     rsp, 28h
0x18004d2f5  lea     rbx, [rcx+28h]
0x18004d2f9  mov     ebp, edx
0x18004d2fb  bts     ebp, 19h
0x18004d2ff  lea     rdi, [rbx+4]
0x18004d303  cmp     dword ptr [rbx], 47764331h
0x18004d309  jnz     short loc_18004D325
0x18004d30b  cmp     dword ptr [rdi], 0
0x18004d30e  jnz     short loc_18004D36A
0x18004d310  cmp     ebp, [rbx+14h]
0x18004d313  jnz     short loc_18004D36A
0x18004d315  mov     rcx, rbx; this
0x18004d318  add     rsp, 28h
0x18004d31c  pop     rdi
0x18004d31d  pop     rsi
0x18004d31e  pop     rbp
0x18004d31f  pop     rbx
0x18004d320  jmp     ?GetGdiBrush@ConvertBrushToGdi@@QEAAPEAUHBRUSH__@@XZ; ConvertBrushToGdi::GetGdiBrush(void)
0x18004d325  lea     rsi, [rbx+8]
0x18004d329  mov     ecx, ebp; color
0x18004d32b  mov     dword ptr [rdi], 0
0x18004d331  call    cs:__imp_CreateSolidBrush
0x18004d337  mov     [rsi], rax
0x18004d33a  mov     rdx, rax
0x18004d33d  neg     rdx
0x18004d340  mov     [rbx+14h], ebp
0x18004d343  sbb     r8d, r8d
0x18004d346  and     r8d, 0FB2D01EBh
0x18004d34d  add     r8d, 4C494146h
0x18004d354  mov     [rbx], r8d
0x18004d357  test    rax, rax
0x18004d35a  jnz     short loc_18004D315
0x18004d35c  lea     ecx, [rax+2]; i
0x18004d35f  call    cs:__imp_GetStockObject
0x18004d365  mov     [rsi], rax
0x18004d368  jmp     short loc_18004D315
0x18004d36a  lea     rsi, [rbx+8]
0x18004d36e  mov     rcx, [rsi]; ho
0x18004d371  call    cs:__imp_DeleteObject
0x18004d377  cmp     dword ptr [rdi], 2
0x18004d37a  jnz     short loc_18004D329
0x18004d37c  mov     rcx, [rbx+18h]; ho
0x18004d380  call    cs:__imp_DeleteObject
0x18004d386  mov     qword ptr [rbx+18h], 0
0x18004d38e  jmp     short loc_18004D329
```
