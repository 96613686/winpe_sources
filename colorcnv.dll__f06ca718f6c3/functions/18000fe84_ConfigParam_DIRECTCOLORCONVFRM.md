# ConfigParam(DIRECTCOLORCONVFRM *)

- ea: `0x18000fe84`
- end: `0x18000ff0d`
- name: `?ConfigParam@@YA?AW4tagColorConvertStatus@@PEAUDIRECTCOLORCONVFRM@@@Z`
- size: `137`
- prototype: `__int64 __fastcall(struct DIRECTCOLORCONVFRM *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180028b6c`

## callees

- `0x180008f30`
- `0x18000fe84`
- `0x180010db8`
- `0x1800132e4`
- `0x180013490`
- `0x180013778`
- `0x180013978`

## pseudocode

```c
__int64 __fastcall ConfigParam(struct DIRECTCOLORCONVFRM *a1)
{
  int v2; // edi
  int v3; // r11d
  __int64 result; // rax

  v2 = *(_DWORD *)(*(_QWORD *)a1 + 16LL);
  v3 = *(_DWORD *)(*((_QWORD *)a1 + 1) + 16LL);
  if ( !v2 || v2 == 3 )
    SetSrcRGBtoYVUTable(a1);
  if ( !v3 || v3 == 3 )
    SetSrcYVUtoRGBTable(a1);
  if ( !v2 && *(_WORD *)(*(_QWORD *)a1 + 14LL) == 8 || !v3 && *(_WORD *)(*((_QWORD *)a1 + 1) + 14LL) == 8 )
    SetDstDitherMap(a1);
  result = InitRGBInfo(a1);
  if ( !(_DWORD)result )
  {
    result = CheckSize((__int64 *)a1);
    if ( !(_DWORD)result )
    {
      SetSequencePointers(a1);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000fe84  mov     [rsp+arg_0], rbx
0x18000fe89  push    rdi
0x18000fe8a  sub     rsp, 20h
0x18000fe8e  mov     rax, [rcx]
0x18000fe91  mov     rbx, rcx
0x18000fe94  mov     edi, [rax+10h]
0x18000fe97  mov     rax, [rcx+8]
0x18000fe9b  mov     r11d, [rax+10h]
0x18000fe9f  test    edi, edi
0x18000fea1  jz      short loc_18000FEA8
0x18000fea3  cmp     edi, 3
0x18000fea6  jnz     short loc_18000FEAD
0x18000fea8  call    ?SetSrcRGBtoYVUTable@@YAXPEAUDIRECTCOLORCONVFRM@@@Z; SetSrcRGBtoYVUTable(DIRECTCOLORCONVFRM *)
0x18000fead  test    r11d, r11d
0x18000feb0  jz      short loc_18000FEB8
0x18000feb2  cmp     r11d, 3
0x18000feb6  jnz     short loc_18000FEBD
0x18000feb8  call    ?SetSrcYVUtoRGBTable@@YAXPEAUDIRECTCOLORCONVFRM@@@Z; SetSrcYVUtoRGBTable(DIRECTCOLORCONVFRM *)
0x18000febd  test    edi, edi
0x18000febf  jnz     short loc_18000FECB
0x18000fec1  mov     rax, [rbx]
0x18000fec4  cmp     word ptr [rax+0Eh], 8
0x18000fec9  jz      short loc_18000FEDB
0x18000fecb  test    r11d, r11d
0x18000fece  jnz     short loc_18000FEE0
0x18000fed0  mov     rax, [rbx+8]
0x18000fed4  cmp     word ptr [rax+0Eh], 8
0x18000fed9  jnz     short loc_18000FEE0
0x18000fedb  call    ?SetDstDitherMap@@YAXPEAUDIRECTCOLORCONVFRM@@@Z; SetDstDitherMap(DIRECTCOLORCONVFRM *)
0x18000fee0  mov     rcx, rbx
0x18000fee3  call    ?InitRGBInfo@@YA?AW4tagColorConvertStatus@@PEAUDIRECTCOLORCONVFRM@@@Z; InitRGBInfo(DIRECTCOLORCONVFRM *)
0x18000fee8  test    eax, eax
0x18000feea  jnz     short loc_18000FF02
0x18000feec  mov     rcx, rbx
0x18000feef  call    ?CheckSize@@YA?AW4tagColorConvertStatus@@PEAUDIRECTCOLORCONVFRM@@@Z; CheckSize(DIRECTCOLORCONVFRM *)
0x18000fef4  test    eax, eax
0x18000fef6  jnz     short loc_18000FF02
0x18000fef8  mov     rcx, rbx; struct DIRECTCOLORCONVFRM *
0x18000fefb  call    ?SetSequencePointers@@YAXPEAUDIRECTCOLORCONVFRM@@@Z; SetSequencePointers(DIRECTCOLORCONVFRM *)
0x18000ff00  xor     eax, eax
0x18000ff02  mov     rbx, [rsp+28h+arg_0]
0x18000ff07  add     rsp, 20h
0x18000ff0b  pop     rdi
0x18000ff0c  retn
```
