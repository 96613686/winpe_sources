# MpWanSetLinkInfo

- ea: `0x140011b1c`
- end: `0x140011cd5`
- name: `MpWanSetLinkInfo`
- size: `441`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140002250`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x140002480`
- `0x140011b1c`

## pseudocode

```c
__int64 __fastcall MpWanSetLinkInfo(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // esi
  int v7; // ecx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  int v10; // eax

  v6 = -1073741823;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 154, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, a2, a3, *(unsigned int *)(a3 + 8), *(_DWORD *)(a3 + 12));
    }
  }
  if ( !a2 )
    goto LABEL_36;
  if ( *(_DWORD *)a3 > *(_DWORD *)(a2 + 124)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 156, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
  if ( *(_DWORD *)(a3 + 4) < *(_DWORD *)(a2 + 124)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 157, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
  v7 = ~*(_DWORD *)(a1 + 116);
  if ( (v7 & *(_DWORD *)(a3 + 8)) == 0 )
  {
    if ( (v7 & *(_DWORD *)(a3 + 12)) == 0 )
    {
      if ( *(_DWORD *)a3 )
        *(_DWORD *)(a2 + 132) = *(_DWORD *)a3;
      v10 = *(_DWORD *)(a3 + 4);
      if ( v10 )
        *(_DWORD *)(a2 + 136) = v10;
      v6 = 0;
      *(_OWORD *)(a2 + 132) = *(_OWORD *)a3;
      *(_OWORD *)(a2 + 148) = *(_OWORD *)(a3 + 16);
      goto LABEL_36;
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v6;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
      goto LABEL_36;
    v9 = 159;
    goto LABEL_25;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return v6;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v9 = 158;
LABEL_25:
    WPP_SF_(v8->AttachedDevice, v9, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids);
  }
LABEL_36:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 160, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x140011b1c  push    rbx
0x140011b1e  push    rbp
0x140011b1f  push    rsi
0x140011b20  push    rdi
0x140011b21  push    r12
0x140011b23  push    r15
0x140011b25  sub     rsp, 38h
0x140011b29  mov     rbx, r8
0x140011b2c  mov     rdi, rdx
0x140011b2f  mov     rbp, rcx
0x140011b32  mov     esi, 0C0000001h
0x140011b37  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b3e  lea     r15, WPP_GLOBAL_Control
0x140011b45  lea     r12, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x140011b4c  cmp     rcx, r15
0x140011b4f  jz      short loc_140011B9C
0x140011b51  mov     eax, [rcx+2Ch]
0x140011b54  test    al, 1
0x140011b56  jz      short loc_140011B6F
0x140011b58  cmp     byte ptr [rcx+29h], 3
0x140011b5c  jb      short loc_140011B6F
0x140011b5e  mov     rcx, [rcx+18h]
0x140011b62  mov     edx, 9Ah
0x140011b67  mov     r8, r12
0x140011b6a  call    WPP_SF_
0x140011b6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b76  cmp     rcx, r15
0x140011b79  jz      short loc_140011B9C
0x140011b7b  mov     eax, [rcx+2Ch]
0x140011b7e  test    al, 1
0x140011b80  jz      short loc_140011B9C
0x140011b82  cmp     byte ptr [rcx+29h], 3
0x140011b86  jb      short loc_140011B9C
0x140011b88  mov     eax, [rbx+0Ch]
0x140011b8b  mov     r9d, [rbx+8]
0x140011b8f  mov     rcx, [rcx+18h]
0x140011b93  mov     [rsp+68h+var_48], eax
0x140011b97  call    WPP_SF_dd
0x140011b9c  test    rdi, rdi
0x140011b9f  jz      loc_140011C97
0x140011ba5  mov     eax, [rdi+7Ch]
0x140011ba8  cmp     [rbx], eax
0x140011baa  jbe     short loc_140011BD6
0x140011bac  mov     rcx, cs:WPP_GLOBAL_Control
0x140011bb3  cmp     rcx, r15
0x140011bb6  jz      short loc_140011BD6
0x140011bb8  mov     eax, [rcx+2Ch]
0x140011bbb  test    al, 1
0x140011bbd  jz      short loc_140011BD6
0x140011bbf  cmp     byte ptr [rcx+29h], 1
0x140011bc3  jb      short loc_140011BD6
0x140011bc5  mov     rcx, [rcx+18h]
0x140011bc9  mov     edx, 9Ch
0x140011bce  mov     r8, r12
0x140011bd1  call    WPP_SF_
0x140011bd6  mov     eax, [rdi+7Ch]
0x140011bd9  cmp     [rbx+4], eax
0x140011bdc  jnb     short loc_140011C08
0x140011bde  mov     rcx, cs:WPP_GLOBAL_Control
0x140011be5  cmp     rcx, r15
0x140011be8  jz      short loc_140011C08
0x140011bea  mov     eax, [rcx+2Ch]
0x140011bed  test    al, 1
0x140011bef  jz      short loc_140011C08
0x140011bf1  cmp     byte ptr [rcx+29h], 1
0x140011bf5  jb      short loc_140011C08
0x140011bf7  mov     rcx, [rcx+18h]
0x140011bfb  mov     edx, 9Dh
0x140011c00  mov     r8, r12
0x140011c03  call    WPP_SF_
0x140011c08  mov     ecx, [rbp+74h]
0x140011c0b  not     ecx
0x140011c0d  test    [rbx+8], ecx
0x140011c10  jz      short loc_140011C42
0x140011c12  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c19  cmp     rcx, r15
0x140011c1c  jz      loc_140011CC5
0x140011c22  mov     eax, [rcx+2Ch]
0x140011c25  test    al, 1
0x140011c27  jz      short loc_140011C97
0x140011c29  cmp     byte ptr [rcx+29h], 1
0x140011c2d  jb      short loc_140011C97
0x140011c2f  mov     edx, 9Eh
0x140011c34  mov     rcx, [rcx+18h]
0x140011c38  mov     r8, r12
0x140011c3b  call    WPP_SF_
0x140011c40  jmp     short loc_140011C97
0x140011c42  test    [rbx+0Ch], ecx
0x140011c45  jz      short loc_140011C67
0x140011c47  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c4e  cmp     rcx, r15
0x140011c51  jz      short loc_140011CC5
0x140011c53  mov     eax, [rcx+2Ch]
0x140011c56  test    al, 1
0x140011c58  jz      short loc_140011C97
0x140011c5a  cmp     byte ptr [rcx+29h], 1
0x140011c5e  jb      short loc_140011C97
0x140011c60  mov     edx, 9Fh
0x140011c65  jmp     short loc_140011C34
0x140011c67  mov     eax, [rbx]
0x140011c69  test    eax, eax
0x140011c6b  jz      short loc_140011C73
0x140011c6d  mov     [rdi+84h], eax
0x140011c73  mov     eax, [rbx+4]
0x140011c76  test    eax, eax
0x140011c78  jz      short loc_140011C80
0x140011c7a  mov     [rdi+88h], eax
0x140011c80  movups  xmm0, xmmword ptr [rbx]
0x140011c83  xor     esi, esi
0x140011c85  movups  xmmword ptr [rdi+84h], xmm0
0x140011c8c  movups  xmm1, xmmword ptr [rbx+10h]
0x140011c90  movups  xmmword ptr [rdi+94h], xmm1
0x140011c97  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c9e  cmp     rcx, r15
0x140011ca1  jz      short loc_140011CC5
0x140011ca3  mov     edx, [rcx+2Ch]
0x140011ca6  test    dl, 1
0x140011ca9  jz      short loc_140011CC5
0x140011cab  cmp     byte ptr [rcx+29h], 3
0x140011caf  jb      short loc_140011CC5
0x140011cb1  mov     rcx, [rcx+18h]
0x140011cb5  mov     edx, 0A0h
0x140011cba  mov     r9d, esi
0x140011cbd  mov     r8, r12
0x140011cc0  call    WPP_SF_d
0x140011cc5  mov     eax, esi
0x140011cc7  add     rsp, 38h
0x140011ccb  pop     r15
0x140011ccd  pop     r12
0x140011ccf  pop     rdi
0x140011cd0  pop     rsi
0x140011cd1  pop     rbp
0x140011cd2  pop     rbx
0x140011cd3  retn
```
