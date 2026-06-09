# DoHeader

- ea: `0x18013e144`
- end: `0x18013e2e0`
- name: `DoHeader`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18013fdf0`

## callees

- `0x1800b2030`
- `0x1800b2190`
- `0x1800b21dc`
- `0x1800e0fa8`
- `0x18013dee8`
- `0x18013e144`
- `0x180141928`

## import_xrefs

- `GDI32!CreateCompatibleBitmap` at `0x18013e1cf`
- `GDI32!CreateCompatibleBitmap` at `0x18013e1cf`
- `GDI32!SelectObject` at `0x18013e1ef`
- `GDI32!SelectObject` at `0x18013e1ef`
- `GDI32!CreateCompatibleDC` at `0x18013e1a2`
- `GDI32!CreateCompatibleDC` at `0x18013e1a2`

## pseudocode

```c
__int64 __fastcall DoHeader(__int64 a1, __int64 a2)
{
  unsigned int inited; // ecx
  HDC CompatibleDC; // rax
  int v6; // edi
  unsigned int v7; // esi
  HBITMAP CompatibleBitmap; // rax
  __int16 v9; // di
  __int64 v10; // rdx
  __int128 v12; // [rsp+20h] [rbp-10h] BYREF

  v12 = 0;
  inited = bInitHandleTableManager();
  if ( inited )
  {
    inited = bInitXformMatrices(a1, a2, &v12);
    if ( inited )
    {
      if ( !pfnSetVirtualResolution )
      {
        CompatibleDC = CreateCompatibleDC(0);
        *(_QWORD *)(a1 + 40) = CompatibleDC;
        if ( !CompatibleDC )
          return 0;
        v6 = HIDWORD(v12) - DWORD1(v12);
        v7 = DWORD2(v12) - v12;
        CompatibleBitmap = CreateCompatibleBitmap(CompatibleDC, DWORD2(v12) - (int)v12, HIDWORD(v12) - DWORD1(v12));
        *(_QWORD *)(a1 + 56) = CompatibleBitmap;
        if ( !CompatibleBitmap )
          return 0;
        SelectObject(*(HDC *)(a1 + 40), CompatibleBitmap);
        *((_QWORD *)&v12 + 1) = __PAIR64__(v6, v7);
        *(_QWORD *)&v12 = 0;
      }
      *(_QWORD *)(a1 + 378) = 50331657;
      *(_WORD *)(a1 + 376) = 1;
      *(_WORD *)(a1 + 386) = 0;
      *(_DWORD *)(a1 + 388) = 0;
      *(_WORD *)(a1 + 392) = 0;
      inited = bEmit(a1, a1 + 376, 18);
      if ( inited )
      {
        if ( (*(_BYTE *)(a1 + 4) & 2) == 0 || (inited = bHandleWin32Comment(a1)) != 0 )
        {
          inited = bW16Emit1(a1, 259, *(unsigned __int16 *)(a1 + 64));
          if ( inited )
          {
            v9 = v12;
            if ( (unsigned int)bW16Emit2(a1, 523, (unsigned __int16)v12, DWORD1(v12)) )
            {
              LOWORD(v10) = 524;
              return (unsigned int)bW16Emit2(
                                     a1,
                                     v10,
                                     (unsigned __int16)(WORD4(v12) - v9),
                                     (unsigned __int16)(WORD6(v12) - WORD2(v12))) != 0;
            }
            else
            {
              return 0;
            }
          }
        }
      }
    }
  }
  return inited;
}

```

## disassembly

```asm
0x18013e144  mov     rax, rsp
0x18013e147  mov     [rax+8], rbx
0x18013e14b  mov     [rax+10h], rsi
0x18013e14f  mov     [rax+18h], rdi
0x18013e153  mov     [rax+20h], r14
0x18013e157  push    rbp
0x18013e158  mov     rbp, rsp
0x18013e15b  sub     rsp, 30h
0x18013e15f  xorps   xmm0, xmm0
0x18013e162  mov     rdi, rdx
0x18013e165  movups  [rbp+var_10], xmm0
0x18013e169  mov     rbx, rcx
0x18013e16c  call    bInitHandleTableManager
0x18013e171  xor     r14d, r14d
0x18013e174  mov     ecx, eax
0x18013e176  test    eax, eax
0x18013e178  jz      loc_18013E2C3
0x18013e17e  lea     r8, [rbp+var_10]
0x18013e182  mov     rdx, rdi
0x18013e185  mov     rcx, rbx
0x18013e188  call    bInitXformMatrices
0x18013e18d  mov     ecx, eax
0x18013e18f  test    eax, eax
0x18013e191  jz      loc_18013E2C3
0x18013e197  cmp     cs:pfnSetVirtualResolution, r14
0x18013e19e  jnz     short loc_18013E205
0x18013e1a0  xor     ecx, ecx; hdc
0x18013e1a2  call    cs:__imp_CreateCompatibleDC
0x18013e1a9  nop     dword ptr [rax+rax+00h]
0x18013e1ae  mov     [rbx+28h], rax
0x18013e1b2  test    rax, rax
0x18013e1b5  jz      loc_18013E298
0x18013e1bb  mov     edi, dword ptr [rbp+var_10+0Ch]
0x18013e1be  mov     rcx, rax; hdc
0x18013e1c1  mov     esi, dword ptr [rbp+var_10+8]
0x18013e1c4  sub     edi, dword ptr [rbp+var_10+4]
0x18013e1c7  sub     esi, dword ptr [rbp+var_10]
0x18013e1ca  mov     r8d, edi; cy
0x18013e1cd  mov     edx, esi; cx
0x18013e1cf  call    cs:__imp_CreateCompatibleBitmap
0x18013e1d6  nop     dword ptr [rax+rax+00h]
0x18013e1db  mov     [rbx+38h], rax
0x18013e1df  test    rax, rax
0x18013e1e2  jz      loc_18013E298
0x18013e1e8  mov     rcx, [rbx+28h]; hdc
0x18013e1ec  mov     rdx, rax; h
0x18013e1ef  call    cs:__imp_SelectObject
0x18013e1f6  nop     dword ptr [rax+rax+00h]
0x18013e1fb  mov     dword ptr [rbp+var_10+8], esi
0x18013e1fe  mov     dword ptr [rbp+var_10+0Ch], edi
0x18013e201  mov     qword ptr [rbp+var_10], r14
0x18013e205  lea     rdx, [rbx+178h]
0x18013e20c  mov     qword ptr [rbx+17Ah], 3000009h
0x18013e217  mov     r8d, 12h
0x18013e21d  mov     word ptr [rdx], 1
0x18013e222  mov     rcx, rbx
0x18013e225  mov     [rbx+182h], r14w
0x18013e22d  mov     [rbx+184h], r14d
0x18013e234  mov     [rbx+188h], r14w
0x18013e23c  call    bEmit
0x18013e241  mov     ecx, eax
0x18013e243  test    eax, eax
0x18013e245  jz      short loc_18013E2C3
0x18013e247  test    byte ptr [rbx+4], 2
0x18013e24b  jz      short loc_18013E25B
0x18013e24d  mov     rcx, rbx
0x18013e250  call    bHandleWin32Comment
0x18013e255  mov     ecx, eax
0x18013e257  test    eax, eax
0x18013e259  jz      short loc_18013E2C3
0x18013e25b  movzx   r8d, word ptr [rbx+40h]
0x18013e260  mov     edx, 103h
0x18013e265  mov     rcx, rbx
0x18013e268  call    bW16Emit1
0x18013e26d  mov     ecx, eax
0x18013e26f  test    eax, eax
0x18013e271  jz      short loc_18013E2C3
0x18013e273  mov     rdi, qword ptr [rbp+var_10]
0x18013e277  mov     edx, 20Bh
0x18013e27c  mov     r9, rdi
0x18013e27f  movzx   r8d, di
0x18013e283  shr     r9, 20h
0x18013e287  mov     rcx, rbx
0x18013e28a  call    bW16Emit2
0x18013e28f  test    eax, eax
0x18013e291  jnz     short loc_18013E29C
0x18013e293  mov     ecx, r14d
0x18013e296  jmp     short loc_18013E2C3
0x18013e298  xor     eax, eax
0x18013e29a  jmp     short loc_18013E2C5
0x18013e29c  movzx   r9d, word ptr [rbp+var_10+0Ch]
0x18013e2a1  mov     dx, 20Ch
0x18013e2a5  movzx   r8d, word ptr [rbp+var_10+8]
0x18013e2aa  mov     rcx, rbx
0x18013e2ad  sub     r9w, word ptr [rbp+var_10+4]
0x18013e2b2  sub     r8w, di
0x18013e2b6  call    bW16Emit2
0x18013e2bb  test    eax, eax
0x18013e2bd  mov     ecx, r14d
0x18013e2c0  setnz   cl
0x18013e2c3  mov     eax, ecx
0x18013e2c5  mov     rbx, [rsp+30h+arg_0]
0x18013e2ca  mov     rsi, [rsp+30h+arg_8]
0x18013e2cf  mov     rdi, [rsp+30h+arg_10]
0x18013e2d4  mov     r14, [rsp+30h+arg_18]
0x18013e2d9  add     rsp, 30h
0x18013e2dd  pop     rbp
0x18013e2de  retn
```
