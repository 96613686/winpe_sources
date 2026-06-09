# ATL::Checked::memmove_s(void *,unsigned __int64,void const *,unsigned __int64)

- ea: `0x180017f7c`
- end: `0x180017fd3`
- name: `?memmove_s@Checked@ATL@@YAXPEAX_KPEBX1@Z`
- size: `87`
- prototype: `void(ATL::Checked *__hidden this, void *, unsigned __int64, const void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180014cd8`
- `0x180014da0`
- `0x18001a038`

## callees

- `0x180002316`
- `0x1800029c1`
- `0x180009948`
- `0x180017f7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017f8f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017fad`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017f8f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017fad`

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
0x180017f7c  push    rbx
0x180017f7e  sub     rsp, 20h
0x180017f82  mov     rax, r8
0x180017f85  test    r9, r9
0x180017f88  jz      short loc_180017FC5
0x180017f8a  test    rcx, rcx
0x180017f8d  jnz     short loc_180017FA3
0x180017f8f  call    cs:__imp__o__errno
0x180017f95  mov     ebx, 16h
0x180017f9a  mov     [rax], ebx
0x180017f9c  call    _invalid_parameter_noinfo
0x180017fa1  jmp     short loc_180017FC7
0x180017fa3  test    rax, rax
0x180017fa6  jz      short loc_180017F8F
0x180017fa8  cmp     rdx, r9
0x180017fab  jnb     short loc_180017FBA
0x180017fad  call    cs:__imp__o__errno
0x180017fb3  mov     ebx, 22h ; '"'
0x180017fb8  jmp     short loc_180017F9A
0x180017fba  mov     r8, r9; Size
0x180017fbd  mov     rdx, rax; Src
0x180017fc0  call    memmove_0
0x180017fc5  xor     ebx, ebx
0x180017fc7  mov     ecx, ebx; int
0x180017fc9  add     rsp, 20h
0x180017fcd  pop     rbx
0x180017fce  jmp     ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
```
