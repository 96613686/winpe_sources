# DriverGdi::GetBrush(ulong)

- ea: `0x18002ac64`
- end: `0x18002ad20`
- name: `?GetBrush@DriverGdi@@AEAAPEAUHBRUSH__@@K@Z`
- size: `188`
- prototype: `HBRUSH __fastcall(DriverGdi *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000acac`
- `0x18002a130`
- `0x18002ad50`

## callees

- `0x18002ac64`
- `0x18002ad28`

## import_xrefs

- `GDI32!CreateSolidBrush` at `0x18002aca9`
- `GDI32!CreateSolidBrush` at `0x18002aca9`
- `GDI32!GetStockObject` at `0x18002acdd`
- `GDI32!GetStockObject` at `0x18002acdd`
- `GDI32!DeleteObject` at `0x18002acf5`
- `GDI32!DeleteObject` at `0x18002ad0a`
- `GDI32!DeleteObject` at `0x18002acf5`
- `GDI32!DeleteObject` at `0x18002ad0a`

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
0x18002ac64  push    rbx
0x18002ac66  push    rbp
0x18002ac67  push    rsi
0x18002ac68  push    rdi
0x18002ac69  sub     rsp, 28h
0x18002ac6d  lea     rbx, [rcx+28h]
0x18002ac71  mov     ebp, edx
0x18002ac73  bts     ebp, 19h
0x18002ac77  lea     rdi, [rbx+4]
0x18002ac7b  cmp     dword ptr [rbx], 47764331h
0x18002ac81  jnz     short loc_18002AC9D
0x18002ac83  cmp     dword ptr [rdi], 0
0x18002ac86  jnz     short loc_18002ACEE
0x18002ac88  cmp     ebp, [rbx+14h]
0x18002ac8b  jnz     short loc_18002ACEE
0x18002ac8d  mov     rcx, rbx; this
0x18002ac90  add     rsp, 28h
0x18002ac94  pop     rdi
0x18002ac95  pop     rsi
0x18002ac96  pop     rbp
0x18002ac97  pop     rbx
0x18002ac98  jmp     ?GetGdiBrush@ConvertBrushToGdi@@QEAAPEAUHBRUSH__@@XZ; ConvertBrushToGdi::GetGdiBrush(void)
0x18002ac9d  lea     rsi, [rbx+8]
0x18002aca1  mov     ecx, ebp; color
0x18002aca3  mov     dword ptr [rdi], 0
0x18002aca9  call    cs:__imp_CreateSolidBrush
0x18002acb0  nop     dword ptr [rax+rax+00h]
0x18002acb5  mov     [rsi], rax
0x18002acb8  mov     rdx, rax
0x18002acbb  neg     rdx
0x18002acbe  mov     [rbx+14h], ebp
0x18002acc1  sbb     r8d, r8d
0x18002acc4  and     r8d, 0FB2D01EBh
0x18002accb  add     r8d, 4C494146h
0x18002acd2  mov     [rbx], r8d
0x18002acd5  test    rax, rax
0x18002acd8  jnz     short loc_18002AC8D
0x18002acda  lea     ecx, [rax+2]; i
0x18002acdd  call    cs:__imp_GetStockObject
0x18002ace4  nop     dword ptr [rax+rax+00h]
0x18002ace9  mov     [rsi], rax
0x18002acec  jmp     short loc_18002AC8D
0x18002acee  lea     rsi, [rbx+8]
0x18002acf2  mov     rcx, [rsi]; ho
0x18002acf5  call    cs:__imp_DeleteObject
0x18002acfc  nop     dword ptr [rax+rax+00h]
0x18002ad01  cmp     dword ptr [rdi], 2
0x18002ad04  jnz     short loc_18002ACA1
0x18002ad06  mov     rcx, [rbx+18h]; ho
0x18002ad0a  call    cs:__imp_DeleteObject
0x18002ad11  nop     dword ptr [rax+rax+00h]
0x18002ad16  mov     qword ptr [rbx+18h], 0
0x18002ad1e  jmp     short loc_18002ACA1
```
