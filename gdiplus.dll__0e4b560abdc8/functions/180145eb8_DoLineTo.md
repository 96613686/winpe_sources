# DoLineTo

- ea: `0x180145eb8`
- end: `0x180145fe6`
- name: `DoLineTo`
- size: `302`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18013fe90`
- `0x18014607c`
- `0x180146b74`

## callees

- `0x1800b0128`
- `0x1800b1ee8`
- `0x1800b2030`
- `0x180145eb8`

## import_xrefs

- `GDI32!GetCurrentPositionEx` at `0x180145f2b`
- `GDI32!GetCurrentPositionEx` at `0x180145f2b`
- `GDI32!LineTo` at `0x180145f16`
- `GDI32!LineTo` at `0x180145f16`
- `GDI32!MoveToEx` at `0x180145f7e`
- `GDI32!MoveToEx` at `0x180145f7e`

## pseudocode

```c
int __fastcall DoLineTo(__int64 a1, int a2, int a3)
{
  int v6; // edi
  int v7; // esi
  HDC v8; // rcx
  __int64 v10; // r9
  __int64 v11; // r8
  unsigned __int64 v12; // [rsp+50h] [rbp+30h] BYREF
  struct tagPOINT pt; // [rsp+68h] [rbp+48h] BYREF

  pt = 0;
  v12 = __PAIR64__(a3, a2);
  v6 = a2;
  v7 = a3;
  if ( !pfnSetVirtualResolution )
  {
    bXformWorkhorse(&v12, 1, a1 + 84);
    v7 = HIDWORD(v12);
    v6 = v12;
  }
  v8 = *(HDC *)(a1 + 40);
  if ( (*(_BYTE *)(a1 + 4) & 8) != 0 )
    return LineTo(v8, v6, v7);
  if ( !GetCurrentPositionEx(v8, &pt) || !pfnSetVirtualResolution && !(unsigned int)bXformWorkhorse(&pt, 1, a1 + 108) )
    return 0;
  if ( !(unsigned int)bValidateMetaFileCP(a1, (unsigned int)pt.x, (unsigned int)pt.y) )
    return 0;
  if ( !MoveToEx(*(HDC *)(a1 + 40), v6, v7, 0) )
    return 0;
  v12 = __PAIR64__(a3, a2);
  if ( !(unsigned int)bXformWorkhorse(&v12, 1, a1 + 228) )
    return 0;
  v10 = WORD2(v12);
  v11 = (unsigned __int16)v12;
  *(_QWORD *)(a1 + 360) = v12;
  return bW16Emit2(a1, 531, v11, v10);
}

```

## disassembly

```asm
0x180145eb8  mov     [rsp-28h+arg_8], rbx
0x180145ebd  push    rbp
0x180145ebe  push    rsi
0x180145ebf  push    rdi
0x180145ec0  push    r14
0x180145ec2  push    r15
0x180145ec4  mov     rbp, rsp
0x180145ec7  sub     rsp, 20h
0x180145ecb  and     qword ptr [rbp+pt.x], 0
0x180145ed0  mov     r14d, r8d
0x180145ed3  cmp     cs:pfnSetVirtualResolution, 0
0x180145edb  mov     r15d, edx
0x180145ede  mov     rbx, rcx
0x180145ee1  mov     dword ptr [rbp+arg_0], edx
0x180145ee4  mov     edi, edx
0x180145ee6  mov     dword ptr [rbp+arg_0+4], r8d
0x180145eea  mov     esi, r8d
0x180145eed  jnz     short loc_180145F07
0x180145eef  lea     r8, [rcx+54h]
0x180145ef3  mov     edx, 1
0x180145ef8  lea     rcx, [rbp+arg_0]
0x180145efc  call    bXformWorkhorse
0x180145f01  mov     esi, dword ptr [rbp+arg_0+4]
0x180145f04  mov     edi, dword ptr [rbp+arg_0]
0x180145f07  test    byte ptr [rbx+4], 8
0x180145f0b  mov     rcx, [rbx+28h]; hdc
0x180145f0f  jz      short loc_180145F27
0x180145f11  mov     r8d, esi; y
0x180145f14  mov     edx, edi; x
0x180145f16  call    cs:__imp_LineTo
0x180145f1d  nop     dword ptr [rax+rax+00h]
0x180145f22  jmp     loc_180145FD4
0x180145f27  lea     rdx, [rbp+pt]; lppt
0x180145f2b  call    cs:__imp_GetCurrentPositionEx
0x180145f32  nop     dword ptr [rax+rax+00h]
0x180145f37  test    eax, eax
0x180145f39  jz      loc_180145FD2
0x180145f3f  cmp     cs:pfnSetVirtualResolution, 0
0x180145f47  jnz     short loc_180145F5F
0x180145f49  lea     r8, [rbx+6Ch]
0x180145f4d  mov     edx, 1
0x180145f52  lea     rcx, [rbp+pt]
0x180145f56  call    bXformWorkhorse
0x180145f5b  test    eax, eax
0x180145f5d  jz      short loc_180145FD2
0x180145f5f  mov     r8d, [rbp+pt.y]
0x180145f63  mov     rcx, rbx
0x180145f66  mov     edx, [rbp+pt.x]
0x180145f69  call    bValidateMetaFileCP
0x180145f6e  test    eax, eax
0x180145f70  jz      short loc_180145FD2
0x180145f72  mov     rcx, [rbx+28h]; hdc
0x180145f76  xor     r9d, r9d; lppt
0x180145f79  mov     r8d, esi; y
0x180145f7c  mov     edx, edi; x
0x180145f7e  call    cs:__imp_MoveToEx
0x180145f85  nop     dword ptr [rax+rax+00h]
0x180145f8a  test    eax, eax
0x180145f8c  jz      short loc_180145FD2
0x180145f8e  lea     r8, [rbx+0E4h]
0x180145f95  mov     dword ptr [rbp+arg_0], r15d
0x180145f99  mov     edx, 1
0x180145f9e  mov     dword ptr [rbp+arg_0+4], r14d
0x180145fa2  lea     rcx, [rbp+arg_0]
0x180145fa6  call    bXformWorkhorse
0x180145fab  test    eax, eax
0x180145fad  jz      short loc_180145FD2
0x180145faf  mov     rax, [rbp+arg_0]
0x180145fb3  mov     edx, 213h
0x180145fb8  movzx   r9d, word ptr [rbp+arg_0+4]
0x180145fbd  movzx   r8d, ax
0x180145fc1  mov     rcx, rbx
0x180145fc4  mov     [rbx+168h], rax
0x180145fcb  call    bW16Emit2
0x180145fd0  jmp     short loc_180145FD4
0x180145fd2  xor     eax, eax
0x180145fd4  mov     rbx, [rsp+20h+arg_8]
0x180145fd9  add     rsp, 20h
0x180145fdd  pop     r15
0x180145fdf  pop     r14
0x180145fe1  pop     rdi
0x180145fe2  pop     rsi
0x180145fe3  pop     rbp
0x180145fe4  retn
```
