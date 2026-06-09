# PacketInsertTag

- ea: `0x1400138d0`
- end: `0x140013a45`
- name: `PacketInsertTag`
- size: `373`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1400112e8`
- `0x140011560`
- `0x140013c90`

## callees

- `0x14000110c`
- `0x140006d40`
- `0x1400138d0`

## pseudocode

```c
__int64 __fastcall PacketInsertTag(__int64 a1, __int16 a2, unsigned __int16 a3, const void *a4, _QWORD *a5)
{
  size_t v6; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // eax
  __int64 v13; // rcx
  void *v14; // rdi

  v6 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x2Bu,
      (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
  }
  v9 = *(_QWORD *)(a1 + 112);
  v10 = (unsigned __int16)__ROR2__(*(_WORD *)(v9 + 18), 8);
  v11 = 1478;
  if ( *(_BYTE *)(v9 + 15) != 9 )
    v11 = 1494;
  if ( (int)v10 + (int)v6 + 4 <= v11 )
  {
    v13 = *(_QWORD *)(a1 + 120);
    *(_WORD *)(v13 + v10) = __ROR2__(a2, 8);
    v14 = (void *)(v10 + v13 + 4);
    *(_WORD *)(v13 + v10 + 2) = __ROR2__(v6, 8);
    if ( (_WORD)v6 )
      memmove(v14, a4, v6);
    if ( a5 )
      *a5 = v14;
    *(_WORD *)(*(_QWORD *)(a1 + 112) + 18LL) = __ROR2__(
                                                 v6 + __ROR2__(*(_WORD *)(*(_QWORD *)(a1 + 112) + 18LL), 8) + 4,
                                                 8);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x2Eu,
        (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x2Cu,
          (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x2Du,
          (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
      }
    }
    return 3221291023LL;
  }
}

```

## disassembly

```asm
0x1400138d0  push    rbx
0x1400138d2  push    rbp
0x1400138d3  push    rsi
0x1400138d4  push    rdi
0x1400138d5  push    r13
0x1400138d7  sub     rsp, 20h
0x1400138db  mov     rbp, r9
0x1400138de  movzx   ebx, r8w
0x1400138e2  mov     edi, edx
0x1400138e4  mov     rsi, rcx
0x1400138e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400138ee  lea     r13, WPP_GLOBAL_Control
0x1400138f5  cmp     rcx, r13
0x1400138f8  jz      short loc_14001391C
0x1400138fa  mov     eax, [rcx+2Ch]
0x1400138fd  test    al, 20h
0x1400138ff  jz      short loc_14001391C
0x140013901  cmp     byte ptr [rcx+29h], 4
0x140013905  jb      short loc_14001391C
0x140013907  mov     rcx, [rcx+18h]
0x14001390b  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x140013912  mov     edx, 2Bh ; '+'
0x140013917  call    WPP_SF_
0x14001391c  mov     rdx, [rsi+70h]
0x140013920  lea     ecx, [rbx+4]
0x140013923  movzx   eax, word ptr [rdx+12h]
0x140013927  ror     ax, 8
0x14001392b  movzx   r8d, ax
0x14001392f  mov     eax, 5C6h
0x140013934  add     ecx, r8d
0x140013937  cmp     byte ptr [rdx+0Fh], 9
0x14001393b  lea     r9d, [rax+10h]
0x14001393f  cmovnz  eax, r9d
0x140013943  cmp     ecx, eax
0x140013945  jbe     short loc_1400139AD
0x140013947  mov     rcx, cs:WPP_GLOBAL_Control
0x14001394e  cmp     rcx, r13
0x140013951  jz      short loc_1400139A3
0x140013953  mov     eax, [rcx+2Ch]
0x140013956  test    al, 20h
0x140013958  jz      short loc_140013975
0x14001395a  cmp     byte ptr [rcx+29h], 1
0x14001395e  jb      short loc_140013975
0x140013960  mov     rcx, [rcx+18h]
0x140013964  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x14001396b  mov     edx, 2Ch ; ','
0x140013970  call    WPP_SF_
0x140013975  mov     rcx, cs:WPP_GLOBAL_Control
0x14001397c  cmp     rcx, r13
0x14001397f  jz      short loc_1400139A3
0x140013981  mov     eax, [rcx+2Ch]
0x140013984  test    al, 20h
0x140013986  jz      short loc_1400139A3
0x140013988  cmp     byte ptr [rcx+29h], 4
0x14001398c  jb      short loc_1400139A3
0x14001398e  mov     rcx, [rcx+18h]
0x140013992  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x140013999  mov     edx, 2Dh ; '-'
0x14001399e  call    WPP_SF_
0x1400139a3  mov     eax, 0C001000Fh
0x1400139a8  jmp     loc_140013A39
0x1400139ad  mov     rcx, [rsi+78h]
0x1400139b1  movzx   eax, bx
0x1400139b4  ror     di, 8
0x1400139b8  ror     ax, 8
0x1400139bc  mov     [rcx+r8], di
0x1400139c1  lea     rdi, [rcx+4]
0x1400139c5  add     rdi, r8
0x1400139c8  mov     [rcx+r8+2], ax
0x1400139ce  test    bx, bx
0x1400139d1  jz      short loc_1400139E1
0x1400139d3  mov     r8, rbx; Size
0x1400139d6  mov     rdx, rbp; Src
0x1400139d9  mov     rcx, rdi; void *
0x1400139dc  call    memmove
0x1400139e1  mov     rax, [rsp+48h+arg_20]
0x1400139e6  test    rax, rax
0x1400139e9  jz      short loc_1400139EE
0x1400139eb  mov     [rax], rdi
0x1400139ee  mov     rcx, [rsi+70h]
0x1400139f2  movzx   eax, word ptr [rcx+12h]
0x1400139f6  ror     ax, 8
0x1400139fa  add     ax, 4
0x1400139fe  add     ax, bx
0x140013a01  ror     ax, 8
0x140013a05  mov     [rcx+12h], ax
0x140013a09  mov     rcx, cs:WPP_GLOBAL_Control
0x140013a10  cmp     rcx, r13
0x140013a13  jz      short loc_140013A37
0x140013a15  mov     eax, [rcx+2Ch]
0x140013a18  test    al, 20h
0x140013a1a  jz      short loc_140013A37
0x140013a1c  cmp     byte ptr [rcx+29h], 4
0x140013a20  jb      short loc_140013A37
0x140013a22  mov     rcx, [rcx+18h]
0x140013a26  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x140013a2d  mov     edx, 2Eh ; '.'
0x140013a32  call    WPP_SF_
0x140013a37  xor     eax, eax
0x140013a39  add     rsp, 20h
0x140013a3d  pop     r13
0x140013a3f  pop     rdi
0x140013a40  pop     rsi
0x140013a41  pop     rbp
0x140013a42  pop     rbx
0x140013a43  retn
```
