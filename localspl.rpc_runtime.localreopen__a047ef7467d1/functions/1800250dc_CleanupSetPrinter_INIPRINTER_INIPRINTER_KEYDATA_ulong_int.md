# CleanupSetPrinter(_INIPRINTER *,_INIPRINTER *,_KEYDATA *,ulong,int)

- ea: `0x1800250dc`
- end: `0x1800251d6`
- name: `?CleanupSetPrinter@@YAXPEAU_INIPRINTER@@0PEAU_KEYDATA@@KH@Z`
- size: `250`
- prototype: `void __fastcall(struct _INIPRINTER *, struct _INIPRINTER *, struct _KEYDATA *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180057b58`

## callees

- `0x180008730`
- `0x1800250dc`
- `0x180025270`

## import_xrefs

- `SPOOLSS!DllFreeSplStr` at `0x180025123`
- `SPOOLSS!DllFreeSplStr` at `0x180025133`
- `SPOOLSS!DllFreeSplStr` at `0x180025149`
- `SPOOLSS!DllFreeSplStr` at `0x18002515f`
- `SPOOLSS!DllFreeSplStr` at `0x18002516f`
- `SPOOLSS!DllFreeSplStr` at `0x18002517f`
- `SPOOLSS!DllFreeSplStr` at `0x180025123`
- `SPOOLSS!DllFreeSplStr` at `0x180025133`
- `SPOOLSS!DllFreeSplStr` at `0x180025149`
- `SPOOLSS!DllFreeSplStr` at `0x18002515f`
- `SPOOLSS!DllFreeSplStr` at `0x18002516f`
- `SPOOLSS!DllFreeSplStr` at `0x18002517f`
- `SPOOLSS!DllFreeSplMem` at `0x1800251b7`
- `SPOOLSS!DllFreeSplMem` at `0x1800251b7`
- `SPOOLSS!DllFreeSplMem` at `0x1800251cf`

## pseudocode

```c
void __fastcall CleanupSetPrinter(struct _INIPRINTER *a1, struct _INIPRINTER *a2, struct _KEYDATA *a3, int a4, int a5)
{
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax

  FreePortTokenList(a3);
  if ( a2 && !a5 && a4 == 2 )
  {
    v8 = *((_QWORD *)a2 + 5);
    if ( v8 != *((_QWORD *)a1 + 5) )
      DllFreeSplStr(v8);
    v9 = *((_QWORD *)a2 + 10);
    if ( v9 != *((_QWORD *)a1 + 10) )
      DllFreeSplStr(v9);
    v10 = *((_QWORD *)a2 + 18);
    if ( v10 != *((_QWORD *)a1 + 18) )
      DllFreeSplStr(v10);
    v11 = *((_QWORD *)a2 + 16);
    if ( v11 != *((_QWORD *)a1 + 16) )
      DllFreeSplStr(v11);
    v12 = *((_QWORD *)a2 + 8);
    if ( v12 != *((_QWORD *)a1 + 8) )
      DllFreeSplStr(v12);
    v13 = *((_QWORD *)a2 + 9);
    if ( v13 != *((_QWORD *)a1 + 9) )
      DllFreeSplStr(v13);
    v14 = *((_QWORD *)a2 + 11);
    if ( v14 && v14 != *((_QWORD *)a1 + 11) && *(_DWORD *)(v14 + 16) )
      SafeDecrementReference((unsigned int *)(v14 + 16));
    v15 = *((_QWORD *)a2 + 7);
    if ( v15 && v15 != *((_QWORD *)a1 + 7) )
      --*(_DWORD *)(v15 + 16);
  }
  DllFreeSplMem(a2);
  DllFreeSplMem(a1);
}

```

## disassembly

```asm
0x1800250dc  mov     [rsp+arg_0], rbx
0x1800250e1  mov     [rsp+arg_8], rsi
0x1800250e6  push    rdi
0x1800250e7  sub     rsp, 20h
0x1800250eb  mov     rdi, rcx
0x1800250ee  mov     esi, r9d
0x1800250f1  mov     rcx, r8
0x1800250f4  mov     rbx, rdx
0x1800250f7  call    FreePortTokenList
0x1800250fc  test    rbx, rbx
0x1800250ff  jz      loc_1800251B4
0x180025105  cmp     [rsp+28h+arg_20], 0
0x18002510a  jnz     loc_1800251B4
0x180025110  cmp     esi, 2
0x180025113  jnz     loc_1800251B4
0x180025119  mov     rcx, [rbx+28h]
0x18002511d  cmp     rcx, [rdi+28h]
0x180025121  jz      short loc_180025129
0x180025123  call    cs:__imp_DllFreeSplStr
0x180025129  mov     rcx, [rbx+50h]
0x18002512d  cmp     rcx, [rdi+50h]
0x180025131  jz      short loc_180025139
0x180025133  call    cs:__imp_DllFreeSplStr
0x180025139  mov     rcx, [rbx+90h]
0x180025140  cmp     rcx, [rdi+90h]
0x180025147  jz      short loc_18002514F
0x180025149  call    cs:__imp_DllFreeSplStr
0x18002514f  mov     rcx, [rbx+80h]
0x180025156  cmp     rcx, [rdi+80h]
0x18002515d  jz      short loc_180025165
0x18002515f  call    cs:__imp_DllFreeSplStr
0x180025165  mov     rcx, [rbx+40h]
0x180025169  cmp     rcx, [rdi+40h]
0x18002516d  jz      short loc_180025175
0x18002516f  call    cs:__imp_DllFreeSplStr
0x180025175  mov     rcx, [rbx+48h]
0x180025179  cmp     rcx, [rdi+48h]
0x18002517d  jz      short loc_180025185
0x18002517f  call    cs:__imp_DllFreeSplStr
0x180025185  mov     rax, [rbx+58h]
0x180025189  test    rax, rax
0x18002518c  jz      short loc_1800251A2
0x18002518e  cmp     rax, [rdi+58h]
0x180025192  jz      short loc_1800251A2
0x180025194  lea     rcx, [rax+10h]; unsigned int *
0x180025198  cmp     dword ptr [rcx], 0
0x18002519b  jz      short loc_1800251A2
0x18002519d  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x1800251a2  mov     rax, [rbx+38h]
0x1800251a6  test    rax, rax
0x1800251a9  jz      short loc_1800251B4
0x1800251ab  cmp     rax, [rdi+38h]
0x1800251af  jz      short loc_1800251B4
0x1800251b1  dec     dword ptr [rax+10h]
0x1800251b4  mov     rcx, rbx
0x1800251b7  call    cs:__imp_DllFreeSplMem
0x1800251bd  mov     rcx, rdi
0x1800251c0  mov     rbx, [rsp+28h+arg_0]
0x1800251c5  mov     rsi, [rsp+28h+arg_8]
0x1800251ca  add     rsp, 20h
0x1800251ce  pop     rdi
0x1800251cf  jmp     cs:__imp_DllFreeSplMem
```
