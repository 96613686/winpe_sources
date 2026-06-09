# NatLookupReverseMapping

- ea: `0x14000ef60`
- end: `0x14000f12d`
- name: `NatLookupReverseMapping`
- size: `461`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140009488`
- `0x14000d8b0`
- `0x14000e988`
- `0x14001169c`
- `0x140022320`

## callees

- `0x14000218c`
- `0x14000ef60`
- `0x14000fe48`

## pseudocode

```c
__int64 __fastcall NatLookupReverseMapping(unsigned __int64 a1, unsigned __int64 a2, __int64 *a3)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  PDEVICE_OBJECT v8; // rcx
  unsigned __int16 v9; // dx
  _QWORD *v11; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_ii(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x3Cu,
      (__int64)WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids,
      a1,
      a2);
  }
  v6 = a1 & 0x3FF;
  if ( (_DWORD)a1 == LODWORD(qword_1400382A0[3 * v6]) )
  {
    ++LODWORD(qword_1400382A0[3 * v6 + 2]);
    v7 = qword_1400382A0[3 * v6 + 1];
    if ( v7 && *(_QWORD *)(v7 + 72) == a1 && *(_QWORD *)(v7 + 88) == a2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_(
            (__int64)WPP_GLOBAL_Control->AttachedDevice,
            0x3Du,
            (__int64)WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          v9 = 62;
          goto LABEL_17;
        }
      }
      return v7;
    }
  }
  else
  {
    ++HIDWORD(qword_1400382A0[3 * v6 + 2]);
  }
  v7 = 0;
  v11 = (_QWORD *)((*((_QWORD *)&MappingTree + 1) + 40LL)
                 & ((unsigned __int128)-(__int128)*((unsigned __int64 *)&MappingTree + 1) >> 64));
  if ( !v11 )
  {
LABEL_28:
    if ( a3 )
      *a3 = v7;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x40u,
        (__int64)WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
    }
    return 0;
  }
  while ( 1 )
  {
    v7 = (__int64)(v11 - 5);
    if ( a1 >= v11[4] )
    {
      if ( a1 > *(_QWORD *)(v7 + 72) )
        goto LABEL_26;
      if ( a2 >= *(_QWORD *)(v7 + 88) )
        break;
    }
    v11 = (_QWORD *)v11[1];
LABEL_27:
    if ( !v11 )
      goto LABEL_28;
  }
  if ( a2 > *(_QWORD *)(v7 + 88) )
  {
LABEL_26:
    v11 = (_QWORD *)v11[2];
    goto LABEL_27;
  }
  if ( (_DWORD)a1 != LODWORD(qword_1400382A0[3 * v6])
    && SLODWORD(qword_1400382A0[3 * v6 + 2]) < HIDWORD(qword_1400382A0[3 * v6 + 2])
                                             - (SHIDWORD(qword_1400382A0[3 * v6 + 2]) >> 2) )
  {
    LODWORD(qword_1400382A0[3 * v6]) = a1;
    qword_1400382A0[3 * v6 + 1] = v7;
    qword_1400382A0[3 * v6 + 2] = 0;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    v9 = 63;
LABEL_17:
    WPP_SF_((__int64)v8->AttachedDevice, v9, (__int64)WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids);
  }
  return v7;
}

```

## disassembly

```asm
0x14000ef60  push    rbx
0x14000ef62  push    rsi
0x14000ef63  push    rdi
0x14000ef64  push    r12
0x14000ef66  push    r14
0x14000ef68  push    r15
0x14000ef6a  sub     rsp, 38h
0x14000ef6e  mov     r14, r8
0x14000ef71  mov     rsi, rdx
0x14000ef74  mov     rdi, rcx
0x14000ef77  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ef7e  lea     r15, WPP_GLOBAL_Control
0x14000ef85  lea     r12, WPP_fd522692ea5834be15ec9d943cb9e317_Traceguids
0x14000ef8c  cmp     rcx, r15
0x14000ef8f  jz      short loc_14000EFB7
0x14000ef91  mov     eax, [rcx+2Ch]
0x14000ef94  test    al, 1
0x14000ef96  jz      short loc_14000EFB7
0x14000ef98  cmp     byte ptr [rcx+29h], 6
0x14000ef9c  jb      short loc_14000EFB7
0x14000ef9e  mov     rcx, [rcx+18h]
0x14000efa2  mov     edx, 3Ch ; '<'
0x14000efa7  mov     r9, rdi
0x14000efaa  mov     [rsp+68h+var_48], rsi
0x14000efaf  mov     r8, r12
0x14000efb2  call    WPP_SF_ii
0x14000efb7  mov     rcx, cs:off_14002F088
0x14000efbe  mov     eax, edi
0x14000efc0  and     eax, 3FFh
0x14000efc5  lea     r8, [rax+rax*2]
0x14000efc9  cmp     edi, [rcx+r8*8]
0x14000efcd  jnz     short loc_14000F044
0x14000efcf  inc     dword ptr [rcx+r8*8+10h]
0x14000efd4  mov     rbx, [rcx+r8*8+8]
0x14000efd9  test    rbx, rbx
0x14000efdc  jz      short loc_14000F049
0x14000efde  cmp     [rbx+48h], rdi
0x14000efe2  jnz     short loc_14000F049
0x14000efe4  cmp     [rbx+58h], rsi
0x14000efe8  jnz     short loc_14000F049
0x14000efea  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eff1  cmp     rcx, r15
0x14000eff4  jz      short loc_14000F03F
0x14000eff6  mov     eax, [rcx+2Ch]
0x14000eff9  test    al, 1
0x14000effb  jz      short loc_14000F014
0x14000effd  cmp     byte ptr [rcx+29h], 5
0x14000f001  jb      short loc_14000F014
0x14000f003  mov     rcx, [rcx+18h]
0x14000f007  mov     edx, 3Dh ; '='
0x14000f00c  mov     r8, r12
0x14000f00f  call    WPP_SF_
0x14000f014  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f01b  cmp     rcx, r15
0x14000f01e  jz      short loc_14000F03F
0x14000f020  mov     edx, [rcx+2Ch]
0x14000f023  test    dl, 1
0x14000f026  jz      short loc_14000F03F
0x14000f028  cmp     byte ptr [rcx+29h], 6
0x14000f02c  jb      short loc_14000F03F
0x14000f02e  mov     edx, 3Eh ; '>'
0x14000f033  mov     rcx, [rcx+18h]
0x14000f037  mov     r8, r12
0x14000f03a  call    WPP_SF_
0x14000f03f  mov     rax, rbx
0x14000f042  jmp     short loc_14000F0BC
0x14000f044  inc     dword ptr [rcx+r8*8+14h]
0x14000f049  mov     rax, qword ptr cs:MappingTree+8
0x14000f050  xor     ebx, ebx
0x14000f052  lea     rcx, [rax+28h]
0x14000f056  neg     rax
0x14000f059  sbb     rdx, rdx
0x14000f05c  and     rdx, rcx
0x14000f05f  jz      short loc_14000F088
0x14000f061  lea     rbx, [rdx-28h]
0x14000f065  cmp     rdi, [rdx+20h]
0x14000f069  jnb     short loc_14000F071
0x14000f06b  mov     rdx, [rdx+8]
0x14000f06f  jmp     short loc_14000F083
0x14000f071  cmp     rdi, [rbx+48h]
0x14000f075  ja      short loc_14000F07F
0x14000f077  cmp     rsi, [rbx+58h]
0x14000f07b  jb      short loc_14000F06B
0x14000f07d  jbe     short loc_14000F0CB
0x14000f07f  mov     rdx, [rdx+10h]
0x14000f083  test    rdx, rdx
0x14000f086  jnz     short loc_14000F061
0x14000f088  test    r14, r14
0x14000f08b  jz      short loc_14000F090
0x14000f08d  mov     [r14], rbx
0x14000f090  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f097  cmp     rcx, r15
0x14000f09a  jz      short loc_14000F0BA
0x14000f09c  mov     eax, [rcx+2Ch]
0x14000f09f  test    al, 1
0x14000f0a1  jz      short loc_14000F0BA
0x14000f0a3  cmp     byte ptr [rcx+29h], 6
0x14000f0a7  jb      short loc_14000F0BA
0x14000f0a9  mov     rcx, [rcx+18h]
0x14000f0ad  mov     edx, 40h ; '@'
0x14000f0b2  mov     r8, r12
0x14000f0b5  call    WPP_SF_
0x14000f0ba  xor     eax, eax
0x14000f0bc  add     rsp, 38h
0x14000f0c0  pop     r15
0x14000f0c2  pop     r14
0x14000f0c4  pop     r12
0x14000f0c6  pop     rdi
0x14000f0c7  pop     rsi
0x14000f0c8  pop     rbx
0x14000f0c9  retn
0x14000f0cb  mov     rdx, cs:off_14002F088
0x14000f0d2  cmp     edi, [rdx+r8*8]
0x14000f0d6  jz      short loc_14000F0FD
0x14000f0d8  mov     ecx, [rdx+r8*8+14h]
0x14000f0dd  mov     eax, ecx
0x14000f0df  sar     eax, 2
0x14000f0e2  sub     ecx, eax
0x14000f0e4  cmp     [rdx+r8*8+10h], ecx
0x14000f0e9  jge     short loc_14000F0FD
0x14000f0eb  mov     [rdx+r8*8], edi
0x14000f0ef  mov     [rdx+r8*8+8], rbx
0x14000f0f4  mov     qword ptr [rdx+r8*8+10h], 0
0x14000f0fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f104  cmp     rcx, r15
0x14000f107  jz      loc_14000F03F
0x14000f10d  mov     edx, [rcx+2Ch]
0x14000f110  test    dl, 1
0x14000f113  jz      loc_14000F03F
0x14000f119  cmp     byte ptr [rcx+29h], 6
0x14000f11d  jb      loc_14000F03F
0x14000f123  mov     edx, 3Fh ; '?'
0x14000f128  jmp     loc_14000F033
```
