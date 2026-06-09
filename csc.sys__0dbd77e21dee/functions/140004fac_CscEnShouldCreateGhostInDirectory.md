# CscEnShouldCreateGhostInDirectory

- ea: `0x140004fac`
- end: `0x1400052ac`
- name: `CscEnShouldCreateGhostInDirectory`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140004f94`

## callees

- `0x140004fac`
- `0x140005328`
- `0x140005390`
- `0x140016a04`
- `0x14001878c`
- `0x14001aae0`
- `0x14001ac1c`
- `0x14001b568`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140005071`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140005071`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400050c4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400050c4`

## pseudocode

```c
__int64 __fastcall CscEnShouldCreateGhostInDirectory(__int64 a1, char *a2)
{
  char *v2; // r13
  unsigned int v4; // edi
  char v5; // r14
  int v6; // r12d
  __int64 v7; // rbp
  __int64 v8; // rbx
  int v9; // r15d
  __int64 v10; // r9
  void *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v13; // [rsp+70h] [rbp+8h]

  v2 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_c7a60c7e3f883d3ed947201bd17678e0_Traceguids, a1);
  CscEnpMainAcquireShared(a1);
  v4 = 0;
  if ( (*(_DWORD *)(a1 + 336) & 0x10) != 0 )
  {
    v5 = 1;
    v13 = *(_QWORD *)(a1 + 196);
    if ( (*(_DWORD *)(a1 + 192) & 0x4840) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, a1);
      }
      if ( *(_DWORD *)(a1 + 16) < 2u )
      {
        v7 = 0;
        v6 = 10176;
      }
      else
      {
        v6 = 0;
        v7 = a1;
        do
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
          {
            WPP_SF_qq(
              WPP_GLOBAL_Control->AttachedDevice,
              11,
              WPP_2d57263f6f6237979220aa59cf47311d_Traceguids,
              v7,
              retaddr);
          }
          ExAcquireResourceSharedLite(*(PERESOURCE *)(v7 + 120), 1u);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
          {
            WPP_SF_qZD(
              WPP_GLOBAL_Control->AttachedDevice,
              88,
              (unsigned int)WPP_2d57263f6f6237979220aa59cf47311d_Traceguids,
              v7,
              v7 + 48,
              *(_DWORD *)(v7 + 192));
          }
          v8 = *(_QWORD *)(v7 + 196);
          v9 = *(_DWORD *)(v7 + 192) & 0x4000;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
          {
            WPP_SF_qq(
              WPP_GLOBAL_Control->AttachedDevice,
              12,
              WPP_2d57263f6f6237979220aa59cf47311d_Traceguids,
              v7,
              retaddr);
          }
          ExReleaseResourceLite(*(PERESOURCE *)(v7 + 120));
          if ( v9 )
            break;
          v7 = *(_QWORD *)(v7 + 24);
        }
        while ( v7 );
        v2 = a2;
        if ( v7 )
          HIDWORD(v13) = HIDWORD(v8);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, v7, v6);
      }
    }
    if ( (unsigned int)(HIDWORD(v13) - 2) > 1 && !*(_WORD *)(a1 + 264) && !*(_DWORD *)(a1 + 376) )
      v5 = 0;
  }
  else
  {
    v5 = 0;
    v4 = -1073740768;
  }
  CscEnpMainRelease(a1);
  *v2 = v5;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    LOBYTE(v10) = v5 != 0 ? 89 : 78;
    WPP_SF_cD(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_c7a60c7e3f883d3ed947201bd17678e0_Traceguids, v10, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x140004fac  mov     [rsp+arg_10], rbx
0x140004fb1  mov     [rsp+arg_8], rdx
0x140004fb6  push    rbp
0x140004fb7  push    rsi
0x140004fb8  push    rdi
0x140004fb9  push    r12
0x140004fbb  push    r13
0x140004fbd  push    r14
0x140004fbf  push    r15
0x140004fc1  sub     rsp, 30h
0x140004fc5  mov     r13, rdx
0x140004fc8  mov     rsi, rcx
0x140004fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140004fd2  lea     r15, WPP_GLOBAL_Control
0x140004fd9  mov     ebx, 40000h
0x140004fde  cmp     rcx, r15
0x140004fe1  jnz     loc_140005185
0x140004fe7  mov     rcx, rsi
0x140004fea  call    CscEnpMainAcquireShared
0x140004fef  mov     eax, [rsi+150h]
0x140004ff5  xor     edi, edi
0x140004ff7  test    al, 10h
0x140004ff9  jz      loc_140005141
0x140004fff  test    dword ptr [rsi+0C0h], 4840h
0x140005009  lea     r14d, [rdi+1]
0x14000500d  mov     rax, [rsi+0C4h]
0x140005014  mov     [rsp+68h+arg_0], rax
0x140005019  jnz     loc_140005112
0x14000501f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005026  cmp     rcx, r15
0x140005029  jz      short loc_140005034
0x14000502b  test    [rcx+2Ch], ebx
0x14000502e  jnz     loc_1400051DB
0x140005034  mov     ecx, [rsi+10h]
0x140005037  test    ecx, ecx
0x140005039  jz      loc_140005250
0x14000503f  cmp     ecx, r14d
0x140005042  jz      loc_140005250
0x140005048  mov     r12d, edi
0x14000504b  lea     r13, WPP_GLOBAL_Control
0x140005052  mov     rbp, rsi
0x140005055  mov     rcx, cs:WPP_GLOBAL_Control
0x14000505c  cmp     rcx, r13
0x14000505f  jz      short loc_14000506A
0x140005061  test    [rcx+2Ch], ebx
0x140005064  jnz     loc_140005202
0x14000506a  mov     rcx, [rbp+78h]; Resource
0x14000506e  mov     dl, r14b; Wait
0x140005071  call    cs:__imp_ExAcquireResourceSharedLite
0x140005078  nop     dword ptr [rax+rax+00h]
0x14000507d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005084  cmp     rcx, r13
0x140005087  jz      short loc_140005092
0x140005089  test    [rcx+2Ch], ebx
0x14000508c  jnz     loc_1400051AB
0x140005092  mov     r15d, [rbp+0C0h]
0x140005099  mov     rbx, [rbp+0C4h]
0x1400050a0  and     r15d, 4000h
0x1400050a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400050ae  cmp     rcx, r13
0x1400050b1  jz      short loc_1400050C0
0x1400050b3  test    dword ptr [rcx+2Ch], 40000h
0x1400050ba  jnz     loc_140005229
0x1400050c0  mov     rcx, [rbp+78h]; Resource
0x1400050c4  call    cs:__imp_ExReleaseResourceLite
0x1400050cb  nop     dword ptr [rax+rax+00h]
0x1400050d0  test    r15d, r15d
0x1400050d3  jnz     short loc_1400050E2
0x1400050d5  mov     rbp, [rbp+18h]
0x1400050d9  test    rbp, rbp
0x1400050dc  jnz     loc_1400051F8
0x1400050e2  mov     r13, [rsp+68h+arg_8]
0x1400050e7  lea     r15, WPP_GLOBAL_Control
0x1400050ee  test    rbp, rbp
0x1400050f1  jz      short loc_1400050F8
0x1400050f3  mov     [rsp+68h+arg_0], rbx
0x1400050f8  mov     ebx, 40000h
0x1400050fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140005104  cmp     rcx, r15
0x140005107  jz      short loc_140005112
0x140005109  test    [rcx+2Ch], ebx
0x14000510c  jnz     loc_14000525E
0x140005112  mov     eax, dword ptr [rsp+68h+arg_0+4]
0x140005116  add     eax, 0FFFFFFFEh
0x140005119  cmp     eax, r14d
0x14000511c  jbe     short loc_140005149
0x14000511e  movzx   eax, word ptr [rsi+108h]
0x140005125  movzx   ecx, ax
0x140005128  shr     cx, 8
0x14000512c  test    cl, cl
0x14000512e  jnz     short loc_140005149
0x140005130  test    al, al
0x140005132  jnz     short loc_140005149
0x140005134  cmp     [rsi+178h], edi
0x14000513a  jnz     short loc_140005149
0x14000513c  mov     r14b, dil
0x14000513f  jmp     short loc_140005149
0x140005141  mov     r14b, dil
0x140005144  mov     edi, 0C0000420h
0x140005149  mov     rcx, rsi
0x14000514c  call    CscEnpMainRelease
0x140005151  mov     [r13+0], r14b
0x140005155  mov     rcx, cs:WPP_GLOBAL_Control
0x14000515c  cmp     rcx, r15
0x14000515f  jz      short loc_14000516A
0x140005161  test    [rcx+2Ch], ebx
0x140005164  jnz     loc_140005280
0x14000516a  mov     rbx, [rsp+68h+arg_10]
0x140005172  mov     eax, edi
0x140005174  add     rsp, 30h
0x140005178  pop     r15
0x14000517a  pop     r14
0x14000517c  pop     r13
0x14000517e  pop     r12
0x140005180  pop     rdi
0x140005181  pop     rsi
0x140005182  pop     rbp
0x140005183  retn
0x140005185  test    [rcx+2Ch], ebx
0x140005188  jz      loc_140004FE7
0x14000518e  mov     rcx, [rcx+18h]
0x140005192  lea     r8, WPP_c7a60c7e3f883d3ed947201bd17678e0_Traceguids
0x140005199  mov     edx, 1Ah
0x14000519e  mov     r9, rsi
0x1400051a1  call    WPP_SF_q
0x1400051a6  jmp     loc_140004FE7
0x1400051ab  mov     eax, [rbp+0C0h]
0x1400051b1  lea     r8, [rbp+30h]
0x1400051b5  mov     rcx, [rcx+18h]
0x1400051b9  mov     edx, 58h ; 'X'
0x1400051be  mov     [rsp+68h+var_40], eax
0x1400051c2  mov     r9, rbp
0x1400051c5  mov     [rsp+68h+var_48], r8
0x1400051ca  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x1400051d1  call    WPP_SF_qZD
0x1400051d6  jmp     loc_140005092
0x1400051db  mov     rcx, [rcx+18h]
0x1400051df  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x1400051e6  mov     edx, 57h ; 'W'
0x1400051eb  mov     r9, rsi
0x1400051ee  call    WPP_SF_q
0x1400051f3  jmp     loc_140005034
0x1400051f8  mov     ebx, 40000h
0x1400051fd  jmp     loc_140005055
0x140005202  mov     rax, [rsp+68h]
0x140005207  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x14000520e  mov     rcx, [rcx+18h]
0x140005212  mov     edx, 0Bh
0x140005217  mov     r9, rbp
0x14000521a  mov     [rsp+68h+var_48], rax
0x14000521f  call    WPP_SF_qq
0x140005224  jmp     loc_14000506A
0x140005229  mov     rax, [rsp+68h]
0x14000522e  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x140005235  mov     rcx, [rcx+18h]
0x140005239  mov     edx, 0Ch
0x14000523e  mov     r9, rbp
0x140005241  mov     [rsp+68h+var_48], rax
0x140005246  call    WPP_SF_qq
0x14000524b  jmp     loc_1400050C0
0x140005250  mov     rbp, rdi
0x140005253  mov     r12d, 27C0h
0x140005259  jmp     loc_1400050FD
0x14000525e  mov     rcx, [rcx+18h]
0x140005262  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x140005269  mov     edx, 59h ; 'Y'
0x14000526e  mov     dword ptr [rsp+68h+var_48], r12d
0x140005273  mov     r9, rbp
0x140005276  call    WPP_SF_qD
0x14000527b  jmp     loc_140005112
0x140005280  mov     rcx, [rcx+18h]
0x140005284  lea     r8, WPP_c7a60c7e3f883d3ed947201bd17678e0_Traceguids
0x14000528b  neg     r14b
0x14000528e  mov     dword ptr [rsp+68h+var_48], edi
0x140005292  mov     edx, 1Bh
0x140005297  sbb     r9b, r9b
0x14000529a  and     r9b, 0Bh
0x14000529e  add     r9b, 4Eh ; 'N'
0x1400052a2  call    WPP_SF_cD
0x1400052a7  jmp     loc_14000516A
```
