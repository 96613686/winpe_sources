# DoClipRect

- ea: `0x1800b0ff0`
- end: `0x1800b12a2`
- name: `DoClipRect`
- size: `690`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1800b01b0`
- `0x1800b0428`
- `0x18013fa80`
- `0x1801432b0`

## callees

- `0x1800b0ff0`
- `0x1800b12a8`
- `0x1800b1574`
- `0x1800b1ee8`
- `0x1800b2b34`
- `0x1801449c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b10e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b10e9`
- `GDI32!ExcludeClipRect` at `0x1800b1264`
- `GDI32!ExcludeClipRect` at `0x1800b1264`
- `GDI32!ExtSelectClipRgn` at `0x1800b11be`
- `GDI32!ExtSelectClipRgn` at `0x1800b11be`
- `GDI32!IntersectClipRect` at `0x1800b124e`
- `GDI32!IntersectClipRect` at `0x1800b124e`
- `GDI32!DeleteObject` at `0x1800b11cf`
- `GDI32!DeleteObject` at `0x1800b11cf`
- `GDI32!CreateRectRgn` at `0x1800b119d`
- `GDI32!CreateRectRgn` at `0x1800b119d`

## pseudocode

```c
__int64 __fastcall DoClipRect(__int64 a1, signed int a2, signed int a3, int a4, int a5, int a6)
{
  __int64 v10; // rdi
  int v11; // eax
  int v12; // ecx
  int v13; // ecx
  int v14; // r9d
  int v15; // r8d
  int v16; // edx
  int v17; // r9d
  int bottom; // ecx
  unsigned __int16 v19; // r10
  __int16 v20; // cx
  int v21; // r9d
  __int16 v22; // r8
  int v23; // edx
  HRGN RectRgn; // rax
  HRGN v26; // r13
  int v27; // ebx
  int v28; // eax
  __int128 v29; // [rsp+30h] [rbp-20h] BYREF
  int left[4]; // [rsp+40h] [rbp-10h] BYREF

  v10 = 0;
  if ( (unsigned int)bNoDCRgn(a1, 1) )
  {
    RectRgn = CreateRectRgn(-32768, -32768, 0x7FFF, 0x7FFF);
    v26 = RectRgn;
    if ( !RectRgn )
      return 0;
    v27 = ExtSelectClipRgn(*(HDC *)(a1 + 40), RectRgn, 5);
    DeleteObject(v26);
    if ( !v27 )
      return 0;
  }
  v11 = a5;
  *(_QWORD *)&v29 = __PAIR64__(a3, a2);
  v12 = a4;
  if ( a2 > a4 )
  {
    v12 = a2;
    LODWORD(v29) = a4;
  }
  if ( a3 > a5 )
  {
    v11 = a3;
    DWORD1(v29) = a5;
  }
  DWORD2(v29) = v12 - 1;
  HIDWORD(v29) = v11 - 1;
  *(_OWORD *)left = v29;
  if ( pfnSetVirtualResolution )
  {
    v13 = left[3];
    v14 = left[2];
    v15 = left[1];
    v16 = left[0];
  }
  else
  {
    if ( !(unsigned int)bXformWorkhorse(left, 2, a1 + 84) )
      return 0;
    v16 = left[0];
    v14 = left[2];
    if ( left[0] > left[2] )
    {
      v16 = left[2];
      v14 = left[0];
    }
    v15 = left[1];
    v13 = left[3];
    if ( left[1] > left[3] )
    {
      v15 = left[3];
      v13 = left[1];
    }
  }
  v17 = v14 + 1;
  bottom = v13 + 1;
  if ( a6 == 29 )
  {
    v28 = ExcludeClipRect(*(HDC *)(a1 + 40), v16, v15, v17, bottom);
  }
  else
  {
    if ( a6 != 30 )
      goto LABEL_10;
    v28 = IntersectClipRect(*(HDC *)(a1 + 40), v16, v15, v17, bottom);
  }
  if ( !v28 )
    return 0;
LABEL_10:
  if ( (*(_BYTE *)(a1 + 4) & 4) != 0 )
    return bDumpDCClipping(a1);
  if ( !(unsigned int)bXformWorkhorse(&v29, 2, a1 + 228) )
    return 0;
  while ( v10 < 4 )
  {
    if ( (unsigned int)(left[v10 - 4] + 0x8000) > 0xFFFF )
    {
      SetLastError(0x216u);
      FixOverflow(&v29);
      FixOverflow((char *)&v29 + 4);
      FixOverflow((char *)&v29 + 8);
      FixOverflow((char *)&v29 + 12);
      break;
    }
    ++v10;
  }
  v19 = v29;
  v20 = WORD4(v29);
  if ( (int)v29 > SDWORD2(v29) )
  {
    v19 = WORD4(v29);
    v20 = v29;
  }
  v21 = DWORD1(v29);
  v22 = WORD6(v29);
  if ( SDWORD1(v29) > SHIDWORD(v29) )
  {
    v21 = HIDWORD(v29);
    v22 = WORD2(v29);
  }
  if ( a6 == 30 )
    v23 = 1046;
  else
    v23 = 1045;
  return bW16Emit4(a1, v23, v19, v21, v20 + 1, v22 + 1);
}

```

## disassembly

```asm
0x1800b0ff0  mov     [rsp-28h+arg_0], rbx
0x1800b0ff5  mov     [rsp-28h+arg_8], rsi
0x1800b0ffa  mov     [rsp-28h+arg_10], rdi
0x1800b0fff  push    rbp
0x1800b1000  push    r12
0x1800b1002  push    r13
0x1800b1004  push    r14
0x1800b1006  push    r15
0x1800b1008  mov     rbp, rsp
0x1800b100b  sub     rsp, 50h
0x1800b100f  mov     r12d, edx
0x1800b1012  mov     r15d, r9d
0x1800b1015  mov     edx, 1
0x1800b101a  mov     r14d, r8d
0x1800b101d  mov     rsi, rcx
0x1800b1020  call    bNoDCRgn
0x1800b1025  xor     edi, edi
0x1800b1027  test    eax, eax
0x1800b1029  jnz     loc_1800B118D
0x1800b102f  mov     edx, [rbp+arg_20]
0x1800b1032  mov     eax, edx
0x1800b1034  mov     dword ptr [rbp+var_20], r12d
0x1800b1038  mov     ecx, r15d
0x1800b103b  mov     dword ptr [rbp+var_20+4], r14d
0x1800b103f  cmp     r12d, r15d
0x1800b1042  jg      loc_1800B11EA
0x1800b1048  cmp     r14d, edx
0x1800b104b  jg      loc_1800B11F6
0x1800b1051  dec     ecx
0x1800b1053  dec     eax
0x1800b1055  cmp     cs:pfnSetVirtualResolution, rdi
0x1800b105c  mov     r14d, 2
0x1800b1062  mov     dword ptr [rbp+var_20+8], ecx
0x1800b1065  mov     dword ptr [rbp+var_20+0Ch], eax
0x1800b1068  movaps  xmm0, [rbp+var_20]
0x1800b106c  movdqa  xmmword ptr [rbp+left], xmm0
0x1800b1071  jz      loc_1800B1201
0x1800b1077  mov     ecx, [rbp+left+0Ch]
0x1800b107a  mov     r9d, [rbp+left+8]
0x1800b107e  mov     r8d, [rbp+left+4]; top
0x1800b1082  mov     edx, [rbp+left]; left
0x1800b1085  mov     ebx, [rbp+arg_28]
0x1800b1088  inc     r9d; right
0x1800b108b  mov     r10d, ebx
0x1800b108e  inc     ecx
0x1800b1090  sub     r10d, 1Dh
0x1800b1094  jz      loc_1800B125C
0x1800b109a  cmp     r10d, 1
0x1800b109e  jz      loc_1800B1246
0x1800b10a4  test    byte ptr [rsi+4], 4
0x1800b10a8  jnz     loc_1800B1183
0x1800b10ae  lea     r8, [rsi+0E4h]
0x1800b10b5  mov     edx, r14d
0x1800b10b8  lea     rcx, [rbp+var_20]
0x1800b10bc  call    bXformWorkhorse
0x1800b10c1  test    eax, eax
0x1800b10c3  jz      loc_1800B11E3
0x1800b10c9  cmp     rdi, 4
0x1800b10cd  jge     short loc_1800B1119
0x1800b10cf  mov     eax, dword ptr [rbp+rdi*4+var_20]
0x1800b10d3  add     eax, 8000h
0x1800b10d8  cmp     eax, 0FFFFh
0x1800b10dd  ja      short loc_1800B10E4
0x1800b10df  inc     rdi
0x1800b10e2  jmp     short loc_1800B10C9
0x1800b10e4  mov     ecx, 216h; dwErrCode
0x1800b10e9  call    cs:__imp_SetLastError
0x1800b10f0  nop     dword ptr [rax+rax+00h]
0x1800b10f5  lea     rcx, [rbp+var_20]
0x1800b10f9  call    FixOverflow
0x1800b10fe  lea     rcx, [rbp+var_20+4]
0x1800b1102  call    FixOverflow
0x1800b1107  lea     rcx, [rbp+var_20+8]
0x1800b110b  call    FixOverflow
0x1800b1110  lea     rcx, [rbp+var_20+0Ch]
0x1800b1114  call    FixOverflow
0x1800b1119  mov     r10d, dword ptr [rbp+var_20]
0x1800b111d  mov     ecx, dword ptr [rbp+var_20+8]
0x1800b1120  cmp     r10d, ecx
0x1800b1123  jg      loc_1800B127D
0x1800b1129  mov     r9d, dword ptr [rbp+var_20+4]
0x1800b112d  mov     r8d, dword ptr [rbp+var_20+0Ch]
0x1800b1131  cmp     r9d, r8d
0x1800b1134  jg      loc_1800B128A
0x1800b113a  inc     r8d
0x1800b113d  inc     ecx
0x1800b113f  mov     [rsp+50h+var_28], r8w
0x1800b1145  movzx   r8d, r10w
0x1800b1149  mov     word ptr [rsp+50h+bottom], cx
0x1800b114e  mov     rcx, rsi
0x1800b1151  cmp     ebx, 1Eh
0x1800b1154  jnz     loc_1800B1298
0x1800b115a  mov     edx, 416h
0x1800b115f  call    bW16Emit4
0x1800b1164  lea     r11, [rsp+50h+var_s0]
0x1800b1169  mov     rbx, [r11+30h]
0x1800b116d  mov     rsi, [r11+38h]
0x1800b1171  mov     rdi, [r11+40h]
0x1800b1175  mov     rsp, r11
0x1800b1178  pop     r15
0x1800b117a  pop     r14
0x1800b117c  pop     r13
0x1800b117e  pop     r12
0x1800b1180  pop     rbp
0x1800b1181  retn
0x1800b1183  mov     rcx, rsi
0x1800b1186  call    bDumpDCClipping
0x1800b118b  jmp     short loc_1800B1164
0x1800b118d  mov     r8d, 7FFFh; x2
0x1800b1193  mov     ecx, 0FFFF8000h; x1
0x1800b1198  mov     r9d, r8d; y2
0x1800b119b  mov     edx, ecx; y1
0x1800b119d  call    cs:__imp_CreateRectRgn
0x1800b11a4  nop     dword ptr [rax+rax+00h]
0x1800b11a9  mov     r13, rax
0x1800b11ac  test    rax, rax
0x1800b11af  jz      short loc_1800B11E3
0x1800b11b1  mov     rcx, [rsi+28h]; hdc
0x1800b11b5  mov     r8d, 5; mode
0x1800b11bb  mov     rdx, rax; hrgn
0x1800b11be  call    cs:__imp_ExtSelectClipRgn
0x1800b11c5  nop     dword ptr [rax+rax+00h]
0x1800b11ca  mov     rcx, r13; ho
0x1800b11cd  mov     ebx, eax
0x1800b11cf  call    cs:__imp_DeleteObject
0x1800b11d6  nop     dword ptr [rax+rax+00h]
0x1800b11db  test    ebx, ebx
0x1800b11dd  jnz     loc_1800B102F
0x1800b11e3  xor     eax, eax
0x1800b11e5  jmp     loc_1800B1164
0x1800b11ea  mov     ecx, r12d
0x1800b11ed  mov     dword ptr [rbp+var_20], r15d
0x1800b11f1  jmp     loc_1800B1048
0x1800b11f6  mov     eax, r14d
0x1800b11f9  mov     dword ptr [rbp+var_20+4], edx
0x1800b11fc  jmp     loc_1800B1051
0x1800b1201  lea     r8, [rsi+54h]
0x1800b1205  mov     edx, r14d
0x1800b1208  lea     rcx, [rbp+left]
0x1800b120c  call    bXformWorkhorse
0x1800b1211  test    eax, eax
0x1800b1213  jz      short loc_1800B11E3
0x1800b1215  mov     edx, [rbp+left]
0x1800b1218  mov     r9d, [rbp+left+8]
0x1800b121c  cmp     edx, r9d
0x1800b121f  jle     short loc_1800B1229
0x1800b1221  mov     eax, edx
0x1800b1223  mov     edx, r9d
0x1800b1226  mov     r9d, eax
0x1800b1229  mov     r8d, [rbp+left+4]
0x1800b122d  mov     ecx, [rbp+left+0Ch]
0x1800b1230  cmp     r8d, ecx
0x1800b1233  jle     loc_1800B1085
0x1800b1239  mov     eax, r8d
0x1800b123c  mov     r8d, ecx
0x1800b123f  mov     ecx, eax
0x1800b1241  jmp     loc_1800B1085
0x1800b1246  mov     [rsp+50h+bottom], ecx; bottom
0x1800b124a  mov     rcx, [rsi+28h]; hdc
0x1800b124e  call    cs:__imp_IntersectClipRect
0x1800b1255  nop     dword ptr [rax+rax+00h]
0x1800b125a  jmp     short loc_1800B1270
0x1800b125c  mov     [rsp+50h+bottom], ecx; bottom
0x1800b1260  mov     rcx, [rsi+28h]; hdc
0x1800b1264  call    cs:__imp_ExcludeClipRect
0x1800b126b  nop     dword ptr [rax+rax+00h]
0x1800b1270  test    eax, eax
0x1800b1272  jz      loc_1800B11E3
0x1800b1278  jmp     loc_1800B10A4
0x1800b127d  mov     eax, r10d
0x1800b1280  mov     r10d, ecx
0x1800b1283  mov     ecx, eax
0x1800b1285  jmp     loc_1800B1129
0x1800b128a  mov     eax, r9d
0x1800b128d  mov     r9d, r8d
0x1800b1290  mov     r8d, eax
0x1800b1293  jmp     loc_1800B113A
0x1800b1298  mov     edx, 415h
0x1800b129d  jmp     loc_1800B115F
```
