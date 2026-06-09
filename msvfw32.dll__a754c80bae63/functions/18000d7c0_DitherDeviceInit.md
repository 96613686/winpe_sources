# DitherDeviceInit

- ea: `0x18000d7c0`
- end: `0x18000d9f5`
- name: `DitherDeviceInit`
- size: `565`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d9fc`

## callees

- `0x18000d7c0`
- `0x18000dae0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000d828`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000d828`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000d81f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000d81f`
- `GDI32!DeleteObject` at `0x18000d90f`
- `GDI32!DeleteObject` at `0x18000d9a8`
- `GDI32!DeleteObject` at `0x18000d90f`
- `GDI32!DeleteObject` at `0x18000d9a8`
- `GDI32!DeleteDC` at `0x18000d93c`
- `GDI32!DeleteDC` at `0x18000d93c`
- `GDI32!CreateCompatibleDC` at `0x18000d84d`
- `GDI32!CreateCompatibleDC` at `0x18000d84d`
- `GDI32!SelectObject` at `0x18000d87b`
- `GDI32!SelectObject` at `0x18000d8cf`
- `GDI32!SelectObject` at `0x18000d906`
- `GDI32!SelectObject` at `0x18000d933`
- `GDI32!SelectObject` at `0x18000d87b`
- `GDI32!SelectObject` at `0x18000d8cf`
- `GDI32!SelectObject` at `0x18000d906`
- `GDI32!SelectObject` at `0x18000d933`
- `GDI32!CreateCompatibleBitmap` at `0x18000d864`
- `GDI32!CreateCompatibleBitmap` at `0x18000d864`
- `GDI32!PatBlt` at `0x18000d8fa`
- `GDI32!PatBlt` at `0x18000d8fa`
- `GDI32!CreateSolidBrush` at `0x18000d8c3`
- `GDI32!CreateSolidBrush` at `0x18000d8c3`
- `GDI32!GetDIBits` at `0x18000d98c`
- `GDI32!GetDIBits` at `0x18000d98c`
- `USER32!GetDC` at `0x18000d841`
- `USER32!GetDC` at `0x18000d841`
- `USER32!ReleaseDC` at `0x18000d9b3`
- `USER32!ReleaseDC` at `0x18000d9b3`

## pseudocode

```c
__int64 __fastcall DitherDeviceInit(__int64 a1, __int128 *a2, _QWORD *a3, LPCVOID a4)
{
  void *v4; // rsi
  __int128 v6; // xmm6
  __int128 v8; // xmm7
  __int64 v9; // xmm8_8
  HGLOBAL v10; // rax
  HDC DC; // r12
  HDC CompatibleDC; // r15
  HBITMAP v14; // rbx
  HGDIOBJ v15; // rax
  int v16; // ebp
  __int64 v17; // r13
  HBRUSH SolidBrush; // rax
  HGDIOBJ v19; // rbx
  HGDIOBJ v20; // rax
  int v21; // eax
  HBITMAP CompatibleBitmap; // [rsp+B8h] [rbp+10h]
  HGDIOBJ v24; // [rsp+C8h] [rbp+20h]

  v4 = (void *)a4;
  v6 = *a2;
  v8 = a2[1];
  v9 = *((_QWORD *)a2 + 4);
  if ( a4 == glpDitherTable )
  {
    DitherTerm(a4);
  }
  else if ( a4 )
  {
    goto LABEL_6;
  }
  v10 = GlobalAlloc(0x42u, 0x4000u);
  v4 = GlobalLock(v10);
  if ( !v4 )
    return -1;
LABEL_6:
  DC = GetDC(0);
  CompatibleDC = CreateCompatibleDC(DC);
  CompatibleBitmap = CreateCompatibleBitmap(DC, 2048, 8);
  v14 = CompatibleBitmap;
  v15 = SelectObject(CompatibleDC, CompatibleBitmap);
  v16 = *(_DWORD *)(a1 + 32);
  v24 = v15;
  if ( !v16 )
    v16 = 1 << *(_BYTE *)(a1 + 14);
  v17 = 0;
  if ( v16 > 0 )
  {
    do
    {
      SolidBrush = CreateSolidBrush(
                     *(unsigned __int8 *)(a1 + 4 * v17 + 42)
                   | (*(unsigned __int8 *)(a1 + 4 * v17 + 40) << 16)
                   | (*(unsigned __int8 *)(a1 + 4 * v17 + 41) << 8));
      v19 = SelectObject(CompatibleDC, SolidBrush);
      PatBlt(CompatibleDC, 8 * v17, 0, 8, 8, 0xF00021u);
      v20 = SelectObject(CompatibleDC, v19);
      DeleteObject(v20);
      v17 = (unsigned int)(v17 + 1);
    }
    while ( (int)v17 < v16 );
    v14 = CompatibleBitmap;
    v15 = v24;
  }
  SelectObject(CompatibleDC, v15);
  DeleteDC(CompatibleDC);
  *(_DWORD *)a2 = 40;
  *((_DWORD *)a2 + 2) = 8;
  *((_DWORD *)a2 + 3) = 524289;
  *((_DWORD *)a2 + 1) = 2048;
  *((_DWORD *)a2 + 4) = 0;
  *(_QWORD *)((char *)a2 + 20) = 0x4000;
  *(_QWORD *)((char *)a2 + 28) = 0;
  *((_DWORD *)a2 + 9) = 0;
  GetDIBits(DC, v14, 0, 8u, v4, (LPBITMAPINFO)a2, 0);
  v21 = *((_DWORD *)a2 + 8);
  *a2 = v6;
  a2[1] = v8;
  *((_QWORD *)a2 + 4) = v9;
  *((_DWORD *)a2 + 8) = v21;
  DeleteObject(v14);
  ReleaseDC(0, DC);
  *a3 = Dither8;
  return (__int64)v4;
}

```

## disassembly

```asm
0x18000d7c0  mov     rax, rsp
0x18000d7c3  mov     [rax+8], rbx
0x18000d7c7  mov     [rax+18h], r8
0x18000d7cb  push    rbp
0x18000d7cc  push    rsi
0x18000d7cd  push    rdi
0x18000d7ce  push    r12
0x18000d7d0  push    r13
0x18000d7d2  push    r14
0x18000d7d4  push    r15
0x18000d7d6  sub     rsp, 70h
0x18000d7da  cmp     r9, cs:glpDitherTable
0x18000d7e1  mov     rsi, r9
0x18000d7e4  movaps  xmmword ptr [rax-48h], xmm6
0x18000d7e8  mov     rdi, rdx
0x18000d7eb  movups  xmm6, xmmword ptr [rdx]
0x18000d7ee  mov     r14, rcx
0x18000d7f1  movaps  xmmword ptr [rax-58h], xmm7
0x18000d7f5  movups  xmm7, xmmword ptr [rdx+10h]
0x18000d7f9  movaps  xmmword ptr [rax-68h], xmm8
0x18000d7fe  movsd   xmm8, qword ptr [rdx+20h]
0x18000d804  jnz     short loc_18000D810
0x18000d806  mov     rcx, r9; pMem
0x18000d809  call    DitherTerm
0x18000d80e  jmp     short loc_18000D815
0x18000d810  test    r9, r9
0x18000d813  jnz     short loc_18000D83F
0x18000d815  mov     edx, 4000h; dwBytes
0x18000d81a  mov     ecx, 42h ; 'B'; uFlags
0x18000d81f  call    cs:__imp_GlobalAlloc
0x18000d825  mov     rcx, rax; hMem
0x18000d828  call    cs:__imp_GlobalLock
0x18000d82e  mov     rsi, rax
0x18000d831  test    rax, rax
0x18000d834  jnz     short loc_18000D83F
0x18000d836  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d83a  jmp     loc_18000D9CE
0x18000d83f  xor     ecx, ecx; hWnd
0x18000d841  call    cs:__imp_GetDC
0x18000d847  mov     rcx, rax; hdc
0x18000d84a  mov     r12, rax
0x18000d84d  call    cs:__imp_CreateCompatibleDC
0x18000d853  mov     edx, 800h; cx
0x18000d858  mov     r8d, 8; cy
0x18000d85e  mov     rcx, r12; hdc
0x18000d861  mov     r15, rax
0x18000d864  call    cs:__imp_CreateCompatibleBitmap
0x18000d86a  mov     rdx, rax; h
0x18000d86d  mov     [rsp+0A8h+arg_8], rax
0x18000d875  mov     rcx, r15; hdc
0x18000d878  mov     rbx, rax
0x18000d87b  call    cs:__imp_SelectObject
0x18000d881  mov     ebp, [r14+20h]
0x18000d885  mov     [rsp+0A8h+arg_18], rax
0x18000d88d  test    ebp, ebp
0x18000d88f  jnz     short loc_18000D89C
0x18000d891  mov     cl, [r14+0Eh]
0x18000d895  mov     ebp, 1
0x18000d89a  shl     ebp, cl
0x18000d89c  xor     r13d, r13d
0x18000d89f  test    ebp, ebp
0x18000d8a1  jle     loc_18000D92D
0x18000d8a7  movzx   ecx, byte ptr [r14+r13*4+29h]
0x18000d8ad  movzx   eax, byte ptr [r14+r13*4+28h]
0x18000d8b3  shl     ecx, 8
0x18000d8b6  shl     eax, 10h
0x18000d8b9  or      ecx, eax
0x18000d8bb  movzx   eax, byte ptr [r14+r13*4+2Ah]
0x18000d8c1  or      ecx, eax; color
0x18000d8c3  call    cs:__imp_CreateSolidBrush
0x18000d8c9  mov     rdx, rax; h
0x18000d8cc  mov     rcx, r15; hdc
0x18000d8cf  call    cs:__imp_SelectObject
0x18000d8d5  lea     edx, ds:0[r13*8]; x
0x18000d8dd  mov     [rsp+0A8h+rop], 0F00021h; rop
0x18000d8e5  mov     rbx, rax
0x18000d8e8  xor     r8d, r8d; y
0x18000d8eb  mov     eax, 8
0x18000d8f0  mov     rcx, r15; hdc
0x18000d8f3  mov     r9d, eax; w
0x18000d8f6  mov     [rsp+0A8h+h], eax; h
0x18000d8fa  call    cs:__imp_PatBlt
0x18000d900  mov     rdx, rbx; h
0x18000d903  mov     rcx, r15; hdc
0x18000d906  call    cs:__imp_SelectObject
0x18000d90c  mov     rcx, rax; ho
0x18000d90f  call    cs:__imp_DeleteObject
0x18000d915  inc     r13d
0x18000d918  cmp     r13d, ebp
0x18000d91b  jl      short loc_18000D8A7
0x18000d91d  mov     rbx, [rsp+0A8h+arg_8]
0x18000d925  mov     rax, [rsp+0A8h+arg_18]
0x18000d92d  mov     rdx, rax; h
0x18000d930  mov     rcx, r15; hdc
0x18000d933  call    cs:__imp_SelectObject
0x18000d939  mov     rcx, r15; hdc
0x18000d93c  call    cs:__imp_DeleteDC
0x18000d942  xor     eax, eax
0x18000d944  mov     dword ptr [rdi], 28h ; '('
0x18000d94a  mov     ecx, 8
0x18000d94f  mov     [rsp+0A8h+usage], eax; usage
0x18000d953  mov     [rdi+8], ecx
0x18000d956  mov     r9d, ecx; cLines
0x18000d959  mov     qword ptr [rsp+0A8h+rop], rdi; lpbmi
0x18000d95e  mov     rcx, r12; hdc
0x18000d961  xor     r8d, r8d; start
0x18000d964  mov     qword ptr [rsp+0A8h+h], rsi; lpvBits
0x18000d969  mov     rdx, rbx; hbm
0x18000d96c  mov     dword ptr [rdi+0Ch], 80001h
0x18000d973  mov     dword ptr [rdi+4], 800h
0x18000d97a  mov     [rdi+10h], eax
0x18000d97d  mov     qword ptr [rdi+14h], 4000h
0x18000d985  mov     [rdi+1Ch], rax
0x18000d989  mov     [rdi+24h], eax
0x18000d98c  call    cs:__imp_GetDIBits
0x18000d992  mov     eax, [rdi+20h]
0x18000d995  mov     rcx, rbx; ho
0x18000d998  movups  xmmword ptr [rdi], xmm6
0x18000d99b  movups  xmmword ptr [rdi+10h], xmm7
0x18000d99f  movsd   qword ptr [rdi+20h], xmm8
0x18000d9a5  mov     [rdi+20h], eax
0x18000d9a8  call    cs:__imp_DeleteObject
0x18000d9ae  mov     rdx, r12; hDC
0x18000d9b1  xor     ecx, ecx; hWnd
0x18000d9b3  call    cs:__imp_ReleaseDC
0x18000d9b9  mov     rax, [rsp+0A8h+arg_10]
0x18000d9c1  lea     rcx, Dither8
0x18000d9c8  mov     [rax], rcx
0x18000d9cb  mov     rax, rsi
0x18000d9ce  movaps  xmm6, [rsp+0A8h+var_48]
0x18000d9d3  lea     r11, [rsp+0A8h+var_38]
0x18000d9d8  mov     rbx, [r11+40h]
0x18000d9dc  movaps  xmm8, xmmword ptr [r11-30h]
0x18000d9e1  movaps  xmm7, [rsp+0A8h+var_58]
0x18000d9e6  mov     rsp, r11
0x18000d9e9  pop     r15
0x18000d9eb  pop     r14
0x18000d9ed  pop     r13
0x18000d9ef  pop     r12
0x18000d9f1  pop     rdi
0x18000d9f2  pop     rsi
0x18000d9f3  pop     rbp
0x18000d9f4  retn
```
