# _GetCursorLowerLeft

- ea: `0x18005029c`
- end: `0x180050443`
- name: `_GetCursorLowerLeft`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18004d908`

## callees

- `0x1800115f0`
- `0x18005029c`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800503ff`
- `GDI32!DeleteObject` at `0x18005040f`
- `GDI32!DeleteObject` at `0x1800503ff`
- `GDI32!DeleteObject` at `0x18005040f`
- `GDI32!GetObjectW` at `0x180050327`
- `GDI32!GetObjectW` at `0x180050327`
- `GDI32!GetBitmapBits` at `0x180050344`
- `GDI32!GetBitmapBits` at `0x180050344`
- `USER32!GetMessagePos` at `0x1800502cd`
- `USER32!GetMessagePos` at `0x1800502cd`
- `USER32!GetIconInfo` at `0x180050307`
- `USER32!GetIconInfo` at `0x180050307`
- `USER32!GetCursor` at `0x1800502ef`
- `USER32!GetCursor` at `0x1800502ef`

## pseudocode

```c
__int64 __fastcall GetCursorLowerLeft(_DWORD *a1, _DWORD *a2, _DWORD *a3, _DWORD *a4)
{
  DWORD MessagePos; // ebx
  HCURSOR Cursor; // rax
  HBITMAP hbmColor; // r9
  unsigned __int64 v11; // rcx
  unsigned int v12; // r8d
  int v13; // ecx
  int v14; // edx
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rcx
  __int64 result; // rax
  ICONINFO piconinfo; // [rsp+20h] [rbp-E0h] BYREF
  _OWORD pv[2]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD vBits[128]; // [rsp+70h] [rbp-90h] BYREF

  memset(&piconinfo, 0, sizeof(piconinfo));
  MessagePos = GetMessagePos();
  memset(pv, 0, sizeof(pv));
  Cursor = GetCursor();
  *a4 = 16;
  *a3 = 16;
  if ( !GetIconInfo(Cursor, &piconinfo) )
    goto LABEL_22;
  if ( !GetObjectW(piconinfo.hbmMask, 32, pv) || !GetBitmapBits(piconinfo.hbmMask, 256, vBits) )
  {
    hbmColor = piconinfo.hbmColor;
    goto LABEL_18;
  }
  hbmColor = piconinfo.hbmColor;
  v11 = (unsigned __int64)(DWORD1(pv[0]) * DWORD2(pv[0])) >> 4;
  if ( piconinfo.hbmColor )
  {
    v12 = 0;
  }
  else
  {
    v12 = v11 - 1;
    LODWORD(v11) = (int)v11 / 2;
  }
  if ( (unsigned int)v11 >= 0x80 )
  {
    v13 = 126;
    goto LABEL_10;
  }
  v13 = v11 - 1;
  if ( v13 >= 0 )
  {
LABEL_10:
    v14 = v12 < 0x80 ? v12 : 0;
    do
    {
      if ( vBits[v13] != 0xFFFF )
        break;
      if ( v14 > 0 )
      {
        if ( vBits[v14] )
          break;
        --v14;
      }
      --v13;
    }
    while ( v13 >= 0 );
  }
  v15 = 16LL * (v13 + 1);
  v16 = SDWORD2(pv[0]);
  *a4 = v15 / SDWORD1(pv[0]) - piconinfo.yHotspot;
  *a3 = v15 / v16 - piconinfo.xHotspot;
LABEL_18:
  if ( hbmColor )
    DeleteObject(hbmColor);
  if ( piconinfo.hbmMask )
    DeleteObject(piconinfo.hbmMask);
LABEL_22:
  *a1 = (__int16)MessagePos;
  result = (unsigned int)(*a4 + SHIWORD(MessagePos));
  *a2 = result;
  return result;
}

```

## disassembly

```asm
0x18005029c  push    rbp
0x18005029e  push    rbx
0x18005029f  push    rsi
0x1800502a0  push    rdi
0x1800502a1  push    r12
0x1800502a3  push    r14
0x1800502a5  push    r15
0x1800502a7  lea     rbp, [rsp-80h]
0x1800502ac  sub     rsp, 180h
0x1800502b3  mov     rax, cs:__security_cookie
0x1800502ba  xor     rax, rsp
0x1800502bd  mov     [rbp+0B0h+var_40], rax
0x1800502c1  mov     rdi, r9
0x1800502c4  mov     r15, r8
0x1800502c7  mov     r14, rdx
0x1800502ca  mov     rsi, rcx
0x1800502cd  call    cs:__imp_GetMessagePos
0x1800502d3  xorps   xmm0, xmm0
0x1800502d6  xorps   xmm1, xmm1
0x1800502d9  movups  xmmword ptr [rsp+1B0h+piconinfo.fIcon], xmm0
0x1800502de  mov     ebx, eax
0x1800502e0  movups  xmmword ptr [rsp+1B0h+piconinfo.hbmMask], xmm0
0x1800502e5  movups  [rsp+1B0h+pv], xmm1
0x1800502ea  movups  [rsp+1B0h+var_158], xmm1
0x1800502ef  call    cs:__imp_GetCursor
0x1800502f5  mov     ecx, 10h
0x1800502fa  lea     rdx, [rsp+1B0h+piconinfo]; piconinfo
0x1800502ff  mov     [rdi], ecx
0x180050301  mov     [r15], ecx
0x180050304  mov     rcx, rax; hIcon
0x180050307  call    cs:__imp_GetIconInfo
0x18005030d  xor     r12d, r12d
0x180050310  test    eax, eax
0x180050312  jz      loc_180050415
0x180050318  mov     rcx, [rsp+1B0h+piconinfo.hbmMask]; h
0x18005031d  lea     r8, [rsp+1B0h+pv]; pv
0x180050322  lea     edx, [r12+20h]; c
0x180050327  call    cs:__imp_GetObjectW
0x18005032d  test    eax, eax
0x18005032f  jz      loc_1800503F2
0x180050335  mov     rcx, [rsp+1B0h+piconinfo.hbmMask]; hbit
0x18005033a  lea     r8, [rsp+1B0h+vBits]; lpvBits
0x18005033f  mov     edx, 100h; cb
0x180050344  call    cs:__imp_GetBitmapBits
0x18005034a  test    eax, eax
0x18005034c  jz      loc_1800503F2
0x180050352  mov     eax, dword ptr [rsp+1B0h+pv+8]
0x180050356  imul    eax, dword ptr [rsp+1B0h+pv+4]
0x18005035b  mov     r9, [rsp+1B0h+piconinfo.hbmColor]
0x180050360  movsxd  rcx, eax
0x180050363  shr     rcx, 4
0x180050367  test    r9, r9
0x18005036a  jnz     short loc_18005037B
0x18005036c  mov     eax, ecx
0x18005036e  lea     r8d, [rcx-1]
0x180050372  cdq
0x180050373  sub     eax, edx
0x180050375  sar     eax, 1
0x180050377  mov     ecx, eax
0x180050379  jmp     short loc_18005037E
0x18005037b  mov     r8d, r12d
0x18005037e  mov     eax, 80h
0x180050383  cmp     ecx, eax
0x180050385  jb      short loc_18005038C
0x180050387  lea     ecx, [rax-2]
0x18005038a  jmp     short loc_180050391
0x18005038c  sub     ecx, 1
0x18005038f  js      short loc_1800503BF
0x180050391  cmp     r8d, eax
0x180050394  sbb     edx, edx
0x180050396  and     edx, r8d
0x180050399  mov     eax, ecx
0x18005039b  mov     r8d, 0FFFFh
0x1800503a1  cmp     [rsp+rax*2+1B0h+vBits], r8w
0x1800503a7  jnz     short loc_1800503BF
0x1800503a9  test    edx, edx
0x1800503ab  jle     short loc_1800503BA
0x1800503ad  movsxd  rax, edx
0x1800503b0  cmp     [rsp+rax*2+1B0h+vBits], r12w
0x1800503b6  jnz     short loc_1800503BF
0x1800503b8  dec     edx
0x1800503ba  sub     ecx, 1
0x1800503bd  jns     short loc_180050399
0x1800503bf  lea     eax, [rcx+1]
0x1800503c2  xor     edx, edx
0x1800503c4  movsxd  rcx, dword ptr [rsp+1B0h+pv+4]
0x1800503c9  movsxd  r8, eax
0x1800503cc  shl     r8, 4
0x1800503d0  mov     rax, r8
0x1800503d3  div     rcx
0x1800503d6  movsxd  rcx, dword ptr [rsp+1B0h+pv+8]
0x1800503db  xor     edx, edx
0x1800503dd  sub     eax, [rsp+1B0h+piconinfo.yHotspot]
0x1800503e1  mov     [rdi], eax
0x1800503e3  mov     rax, r8
0x1800503e6  div     rcx
0x1800503e9  sub     eax, [rsp+1B0h+piconinfo.xHotspot]
0x1800503ed  mov     [r15], eax
0x1800503f0  jmp     short loc_1800503F7
0x1800503f2  mov     r9, [rsp+1B0h+piconinfo.hbmColor]
0x1800503f7  test    r9, r9
0x1800503fa  jz      short loc_180050405
0x1800503fc  mov     rcx, r9; ho
0x1800503ff  call    cs:__imp_DeleteObject
0x180050405  mov     rcx, [rsp+1B0h+piconinfo.hbmMask]; ho
0x18005040a  test    rcx, rcx
0x18005040d  jz      short loc_180050415
0x18005040f  call    cs:__imp_DeleteObject
0x180050415  movsx   eax, bx
0x180050418  mov     [rsi], eax
0x18005041a  shr     ebx, 10h
0x18005041d  movsx   eax, bx
0x180050420  add     eax, [rdi]
0x180050422  mov     [r14], eax
0x180050425  mov     rcx, [rbp+0B0h+var_40]
0x180050429  xor     rcx, rsp; StackCookie
0x18005042c  call    __security_check_cookie
0x180050431  add     rsp, 180h
0x180050438  pop     r15
0x18005043a  pop     r14
0x18005043c  pop     r12
0x18005043e  pop     rdi
0x18005043f  pop     rsi
0x180050440  pop     rbx
0x180050441  pop     rbp
0x180050442  retn
```
