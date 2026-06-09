# ATL::Checked::memmove_s(void *,unsigned __int64,void const *,unsigned __int64)

- ea: `0x1800189c4`
- end: `0x180018a27`
- name: `?memmove_s@Checked@ATL@@YAXPEAX_KPEBX1@Z`
- size: `99`
- prototype: `void(ATL::Checked *__hidden this, void *, unsigned __int64, const void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800155ac`
- `0x180015688`
- `0x18001aab8`

## callees

- `0x180002336`
- `0x1800029e1`
- `0x180009e24`
- `0x1800189c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800189d7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800189fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800189d7`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800189fb`

## pseudocode

```c
void __fastcall ATL::Checked::memmove_s(ATL::Checked *this, void *a2, const void *a3, void *a4)
{
  int *v4; // rax
  int v5; // ebx

  if ( !a4 )
    goto LABEL_9;
  if ( this && a3 )
  {
    if ( a2 < a4 )
    {
      v4 = (int *)((__int64 (*)(void))_o__errno)();
      v5 = 34;
      goto LABEL_4;
    }
    memmove_0(this, a3, (size_t)a4);
LABEL_9:
    v5 = 0;
    goto LABEL_10;
  }
  v4 = (int *)_o__errno(this, a2);
  v5 = 22;
LABEL_4:
  *v4 = v5;
  invalid_parameter_noinfo();
LABEL_10:
  ATL::AtlCrtErrorCheck(v5);
}

```

## disassembly

```asm
0x1800189c4  push    rbx
0x1800189c6  sub     rsp, 20h
0x1800189ca  mov     rax, r8
0x1800189cd  test    r9, r9
0x1800189d0  jz      short loc_180018A19
0x1800189d2  test    rcx, rcx
0x1800189d5  jnz     short loc_1800189F1
0x1800189d7  call    cs:__imp__o__errno
0x1800189de  nop     dword ptr [rax+rax+00h]
0x1800189e3  mov     ebx, 16h
0x1800189e8  mov     [rax], ebx
0x1800189ea  call    _invalid_parameter_noinfo
0x1800189ef  jmp     short loc_180018A1B
0x1800189f1  test    rax, rax
0x1800189f4  jz      short loc_1800189D7
0x1800189f6  cmp     rdx, r9
0x1800189f9  jnb     short loc_180018A0E
0x1800189fb  call    cs:__imp__o__errno
0x180018a02  nop     dword ptr [rax+rax+00h]
0x180018a07  mov     ebx, 22h ; '"'
0x180018a0c  jmp     short loc_1800189E8
0x180018a0e  mov     r8, r9; Size
0x180018a11  mov     rdx, rax; Src
0x180018a14  call    memmove_0
0x180018a19  xor     ebx, ebx
0x180018a1b  mov     ecx, ebx; int
0x180018a1d  add     rsp, 20h
0x180018a21  pop     rbx
0x180018a22  jmp     ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
```
