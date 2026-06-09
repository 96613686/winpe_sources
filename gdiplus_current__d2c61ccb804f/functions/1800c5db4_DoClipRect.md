# DoClipRect

- ea: `0x1800c5db4`
- end: `0x1800c6040`
- name: `DoClipRect`
- size: `652`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1800c5d60`
- `0x1800c6ed0`
- `0x1801479b0`
- `0x1801497ec`

## callees

- `0x1800c5768`
- `0x1800c5db4`
- `0x1800c6048`
- `0x1800c60cc`
- `0x1800c790c`
- `0x18014a9e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c5e97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c5e97`
- `GDI32!ExcludeClipRect` at `0x1800c6002`
- `GDI32!ExcludeClipRect` at `0x1800c6002`
- `GDI32!ExtSelectClipRgn` at `0x1800c5f5d`
- `GDI32!ExtSelectClipRgn` at `0x1800c5f5d`
- `GDI32!IntersectClipRect` at `0x1800c5fe8`
- `GDI32!IntersectClipRect` at `0x1800c5fe8`
- `GDI32!DeleteObject` at `0x1800c5f6e`
- `GDI32!DeleteObject` at `0x1800c5f6e`
- `GDI32!CreateRectRgn` at `0x1800c5f3c`
- `GDI32!CreateRectRgn` at `0x1800c5f3c`

## pseudocode

```c
__int64 __fastcall DoClipRect(__int64 a1, int a2, int a3, int a4, int a5, int a6)
{
  int v10; // edx
  int v11; // ecx
  int v12; // esi
  int v13; // ecx
  int bottom; // r8d
  int v15; // r9d
  int i; // edx
  unsigned __int16 v17; // r10
  __int16 v18; // cx
  int v19; // r9d
  __int16 v20; // r8
  int v21; // edx
  HRGN RectRgn; // rax
  HRGN v24; // r12
  int v25; // ebx
  int v26; // eax
  int v27; // [rsp+30h] [rbp-20h] BYREF
  int v28; // [rsp+34h] [rbp-1Ch] BYREF
  int v29; // [rsp+38h] [rbp-18h] BYREF
  int v30; // [rsp+3Ch] [rbp-14h] BYREF
  int v31; // [rsp+40h] [rbp-10h] BYREF
  int v32; // [rsp+44h] [rbp-Ch]
  int v33; // [rsp+48h] [rbp-8h]
  int v34; // [rsp+4Ch] [rbp-4h]

  if ( (unsigned int)bNoDCRgn(a1, 1) )
  {
    RectRgn = CreateRectRgn(-32768, -32768, 0x7FFF, 0x7FFF);
    v24 = RectRgn;
    if ( !RectRgn )
      return 0;
    v25 = ExtSelectClipRgn(*(HDC *)(a1 + 40), RectRgn, 5);
    DeleteObject(v24);
    if ( !v25 )
      return 0;
  }
  v10 = a2;
  v27 = a2;
  v11 = a5;
  v28 = a3;
  if ( a2 > a4 )
  {
    v10 = a4;
    a4 = a2;
    v27 = v10;
  }
  if ( a3 > a5 )
  {
    v11 = a3;
    v28 = a5;
    a3 = a5;
  }
  v12 = a4 - 1;
  v31 = v10;
  v13 = v11 - 1;
  v29 = v12;
  v30 = v13;
  v32 = a3;
  v33 = v12;
  v34 = v13;
  if ( !pfnSetVirtualResolution )
  {
    if ( !(unsigned int)bXformWorkhorse(&v31, 2, a1 + 84) )
      return 0;
    v10 = v31;
    v12 = v33;
    if ( v31 > v33 )
    {
      v10 = v33;
      v12 = v31;
    }
    a3 = v32;
    v13 = v34;
    if ( v32 > v34 )
    {
      a3 = v34;
      v13 = v32;
    }
  }
  bottom = v13 + 1;
  v15 = v12 + 1;
  if ( a6 == 29 )
  {
    v26 = ExcludeClipRect(*(HDC *)(a1 + 40), v10, a3, v15, bottom);
  }
  else
  {
    if ( a6 != 30 )
      goto LABEL_9;
    v26 = IntersectClipRect(*(HDC *)(a1 + 40), v10, a3, v15, bottom);
  }
  if ( !v26 )
    return 0;
LABEL_9:
  if ( (*(_BYTE *)(a1 + 4) & 4) != 0 )
    return bDumpDCClipping(a1);
  if ( !(unsigned int)bXformWorkhorse(&v27, 2, a1 + 228) )
    return 0;
  for ( i = 0; i < 4; ++i )
  {
    if ( (unsigned int)(*(&v27 + i) + 0x8000) > 0xFFFF )
    {
      SetLastError(0x216u);
      FixOverflow(&v27);
      FixOverflow(&v28);
      FixOverflow(&v29);
      FixOverflow(&v30);
      break;
    }
  }
  v17 = v27;
  v18 = v29;
  if ( v27 > v29 )
  {
    v17 = v29;
    v18 = v27;
  }
  v19 = v28;
  v20 = v30;
  if ( v28 > v30 )
  {
    v19 = v30;
    v20 = v28;
  }
  if ( a6 == 30 )
    v21 = 1046;
  else
    v21 = 1045;
  return bW16Emit4(a1, v21, v17, v19, v18 + 1, v20 + 1);
}

```

## disassembly

```asm
0x1800c5db4  push    rbp
0x1800c5db6  push    rbx
0x1800c5db7  push    rsi
0x1800c5db8  push    rdi
0x1800c5db9  push    r12
0x1800c5dbb  push    r14
0x1800c5dbd  push    r15
0x1800c5dbf  mov     rbp, rsp
0x1800c5dc2  sub     rsp, 50h
0x1800c5dc6  mov     r15d, edx
0x1800c5dc9  mov     esi, r9d
0x1800c5dcc  mov     edx, 1
0x1800c5dd1  mov     edi, r8d
0x1800c5dd4  mov     r14, rcx
0x1800c5dd7  call    bNoDCRgn
0x1800c5ddc  test    eax, eax
0x1800c5dde  jnz     loc_1800C5F2C
0x1800c5de4  mov     eax, [rbp+arg_20]
0x1800c5de7  mov     edx, r15d; left
0x1800c5dea  mov     [rbp+var_20], edx
0x1800c5ded  mov     ecx, eax
0x1800c5def  mov     [rbp+var_1C], edi
0x1800c5df2  cmp     r15d, esi
0x1800c5df5  jg      loc_1800C5F86
0x1800c5dfb  cmp     edi, eax
0x1800c5dfd  jg      loc_1800C5F93
0x1800c5e03  dec     esi
0x1800c5e05  mov     [rbp+var_10], edx
0x1800c5e08  dec     ecx
0x1800c5e0a  mov     [rbp+var_18], esi
0x1800c5e0d  cmp     cs:pfnSetVirtualResolution, 0
0x1800c5e15  mov     r15d, 2
0x1800c5e1b  mov     [rbp+var_14], ecx
0x1800c5e1e  mov     [rbp+var_C], edi
0x1800c5e21  mov     [rbp+var_8], esi
0x1800c5e24  mov     [rbp+var_4], ecx
0x1800c5e27  jz      loc_1800C5F9F
0x1800c5e2d  mov     ebx, [rbp+arg_28]
0x1800c5e30  lea     r8d, [rcx+1]
0x1800c5e34  mov     ecx, ebx
0x1800c5e36  lea     r9d, [rsi+1]; right
0x1800c5e3a  sub     ecx, 1Dh
0x1800c5e3d  jz      loc_1800C5FF6
0x1800c5e43  cmp     ecx, 1
0x1800c5e46  jz      loc_1800C5FDC
0x1800c5e4c  test    byte ptr [r14+4], 4
0x1800c5e51  jnz     loc_1800C5F22
0x1800c5e57  lea     r8, [r14+0E4h]
0x1800c5e5e  mov     edx, r15d
0x1800c5e61  lea     rcx, [rbp+var_20]
0x1800c5e65  call    bXformWorkhorse
0x1800c5e6a  test    eax, eax
0x1800c5e6c  jz      loc_1800C5F82
0x1800c5e72  xor     edx, edx
0x1800c5e74  cmp     edx, 4
0x1800c5e77  jge     short loc_1800C5EC7
0x1800c5e79  movsxd  rax, edx
0x1800c5e7c  mov     ecx, [rbp+rax*4+var_20]
0x1800c5e80  add     ecx, 8000h
0x1800c5e86  cmp     ecx, 0FFFFh
0x1800c5e8c  ja      short loc_1800C5E92
0x1800c5e8e  inc     edx
0x1800c5e90  jmp     short loc_1800C5E74
0x1800c5e92  mov     ecx, 216h; dwErrCode
0x1800c5e97  call    cs:__imp_SetLastError
0x1800c5e9e  nop     dword ptr [rax+rax+00h]
0x1800c5ea3  lea     rcx, [rbp+var_20]
0x1800c5ea7  call    FixOverflow
0x1800c5eac  lea     rcx, [rbp+var_1C]
0x1800c5eb0  call    FixOverflow
0x1800c5eb5  lea     rcx, [rbp+var_18]
0x1800c5eb9  call    FixOverflow
0x1800c5ebe  lea     rcx, [rbp+var_14]
0x1800c5ec2  call    FixOverflow
0x1800c5ec7  mov     r10d, [rbp+var_20]
0x1800c5ecb  mov     ecx, [rbp+var_18]
0x1800c5ece  cmp     r10d, ecx
0x1800c5ed1  jg      loc_1800C601B
0x1800c5ed7  mov     r9d, [rbp+var_1C]
0x1800c5edb  mov     r8d, [rbp+var_14]
0x1800c5edf  cmp     r9d, r8d
0x1800c5ee2  jg      loc_1800C6028
0x1800c5ee8  inc     r8d
0x1800c5eeb  inc     ecx
0x1800c5eed  mov     [rsp+50h+var_28], r8w
0x1800c5ef3  movzx   r8d, r10w
0x1800c5ef7  mov     word ptr [rsp+50h+bottom], cx
0x1800c5efc  mov     rcx, r14
0x1800c5eff  cmp     ebx, 1Eh
0x1800c5f02  jnz     loc_1800C6036
0x1800c5f08  mov     edx, 416h
0x1800c5f0d  call    bW16Emit4
0x1800c5f12  add     rsp, 50h
0x1800c5f16  pop     r15
0x1800c5f18  pop     r14
0x1800c5f1a  pop     r12
0x1800c5f1c  pop     rdi
0x1800c5f1d  pop     rsi
0x1800c5f1e  pop     rbx
0x1800c5f1f  pop     rbp
0x1800c5f20  retn
0x1800c5f22  mov     rcx, r14
0x1800c5f25  call    bDumpDCClipping
0x1800c5f2a  jmp     short loc_1800C5F12
0x1800c5f2c  mov     r8d, 7FFFh; x2
0x1800c5f32  mov     ecx, 0FFFF8000h; x1
0x1800c5f37  mov     r9d, r8d; y2
0x1800c5f3a  mov     edx, ecx; y1
0x1800c5f3c  call    cs:__imp_CreateRectRgn
0x1800c5f43  nop     dword ptr [rax+rax+00h]
0x1800c5f48  mov     r12, rax
0x1800c5f4b  test    rax, rax
0x1800c5f4e  jz      short loc_1800C5F82
0x1800c5f50  mov     rcx, [r14+28h]; hdc
0x1800c5f54  mov     r8d, 5; mode
0x1800c5f5a  mov     rdx, rax; hrgn
0x1800c5f5d  call    cs:__imp_ExtSelectClipRgn
0x1800c5f64  nop     dword ptr [rax+rax+00h]
0x1800c5f69  mov     rcx, r12; ho
0x1800c5f6c  mov     ebx, eax
0x1800c5f6e  call    cs:__imp_DeleteObject
0x1800c5f75  nop     dword ptr [rax+rax+00h]
0x1800c5f7a  test    ebx, ebx
0x1800c5f7c  jnz     loc_1800C5DE4
0x1800c5f82  xor     eax, eax
0x1800c5f84  jmp     short loc_1800C5F12
0x1800c5f86  mov     edx, esi
0x1800c5f88  mov     esi, r15d
0x1800c5f8b  mov     [rbp+var_20], edx
0x1800c5f8e  jmp     loc_1800C5DFB
0x1800c5f93  mov     ecx, edi
0x1800c5f95  mov     [rbp+var_1C], eax
0x1800c5f98  mov     edi, eax
0x1800c5f9a  jmp     loc_1800C5E03
0x1800c5f9f  lea     r8, [r14+54h]
0x1800c5fa3  mov     edx, r15d
0x1800c5fa6  lea     rcx, [rbp+var_10]
0x1800c5faa  call    bXformWorkhorse
0x1800c5faf  test    eax, eax
0x1800c5fb1  jz      short loc_1800C5F82
0x1800c5fb3  mov     edx, [rbp+var_10]
0x1800c5fb6  mov     esi, [rbp+var_8]
0x1800c5fb9  cmp     edx, esi
0x1800c5fbb  jle     short loc_1800C5FC3
0x1800c5fbd  mov     eax, edx
0x1800c5fbf  mov     edx, esi
0x1800c5fc1  mov     esi, eax
0x1800c5fc3  mov     edi, [rbp+var_C]
0x1800c5fc6  mov     ecx, [rbp+var_4]
0x1800c5fc9  cmp     edi, ecx
0x1800c5fcb  jle     loc_1800C5E2D
0x1800c5fd1  mov     eax, edi
0x1800c5fd3  mov     edi, ecx
0x1800c5fd5  mov     ecx, eax
0x1800c5fd7  jmp     loc_1800C5E2D
0x1800c5fdc  mov     rcx, [r14+28h]; hdc
0x1800c5fe0  mov     [rsp+50h+bottom], r8d; bottom
0x1800c5fe5  mov     r8d, edi; top
0x1800c5fe8  call    cs:__imp_IntersectClipRect
0x1800c5fef  nop     dword ptr [rax+rax+00h]
0x1800c5ff4  jmp     short loc_1800C600E
0x1800c5ff6  mov     rcx, [r14+28h]; hdc
0x1800c5ffa  mov     [rsp+50h+bottom], r8d; bottom
0x1800c5fff  mov     r8d, edi; top
0x1800c6002  call    cs:__imp_ExcludeClipRect
0x1800c6009  nop     dword ptr [rax+rax+00h]
0x1800c600e  test    eax, eax
0x1800c6010  jz      loc_1800C5F82
0x1800c6016  jmp     loc_1800C5E4C
0x1800c601b  mov     eax, r10d
0x1800c601e  mov     r10d, ecx
0x1800c6021  mov     ecx, eax
0x1800c6023  jmp     loc_1800C5ED7
0x1800c6028  mov     eax, r9d
0x1800c602b  mov     r9d, r8d
0x1800c602e  mov     r8d, eax
0x1800c6031  jmp     loc_1800C5EE8
0x1800c6036  mov     edx, 415h
0x1800c603b  jmp     loc_1800C5F0D
```
