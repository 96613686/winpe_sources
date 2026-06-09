# RdpBoundsAccumulator::AlignRectsInBA(int,int,int)

- ea: `0x18001ae30`
- end: `0x18001b062`
- name: `?AlignRectsInBA@RdpBoundsAccumulator@@UEAAJHHH@Z`
- size: `562`
- prototype: `__int64 __fastcall(RdpBoundsAccumulator *__hidden this, int, int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18001ad10`
- `0x18001ae30`
- `0x18001b3e0`
- `0x18001cac0`
- `0x18001d114`
- `0x18002a1c4`
- `0x18002c010`

## string_xrefs

- `0x18001aea0`: `CreateIterator failed!`

## pseudocode

```c
__int64 __fastcall RdpBoundsAccumulator::AlignRectsInBA(RdpBoundsAccumulator *this, int a2, int a3, int a4)
{
  int Iterator; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  struct IRdpBAIterator *v12; // rsi
  int v13; // ebx
  int ActivityIdPrefix; // eax
  int v15; // edx
  const char *v16; // rcx
  int v17; // edi
  int v18; // r14d
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned int v23; // r10d
  int v24; // r8d
  int v25; // r9d
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  struct IRdpBAIterator *v34[2]; // [rsp+30h] [rbp-18h] BYREF

  v34[0] = 0;
  Iterator = RdpBoundsAccumulator::CreateIterator(this, v34);
  v12 = v34[0];
  v13 = Iterator;
  if ( Iterator >= 0 )
  {
    v17 = a4 - 1;
    v18 = 0;
    while ( 1 )
    {
      *(_OWORD *)v34 = 0;
      v19 = (*(__int64 (__fastcall **)(struct IRdpBAIterator *, struct IRdpBAIterator **))(*(_QWORD *)v12 + 32LL))(
              v12,
              v34);
      if ( v19 < 0 )
        break;
      v23 = (unsigned int)v34[0];
      if ( ((__int64)v34[0] & v17) != 0
        || (HIDWORD(v34[0]) & v17) != 0
        || LODWORD(v34[1]) != a2 && ((__int64)v34[1] & v17) != 0
        || HIDWORD(v34[1]) != a3 && (HIDWORD(v34[1]) & v17) != 0 )
      {
        v24 = ~v17 & HIDWORD(v34[0]);
        v25 = ~v17 & (LODWORD(v34[1]) + v17);
        LODWORD(v34[0]) &= ~v17;
        HIDWORD(v34[0]) = v24;
        if ( a2 < v25 )
          v25 = a2;
        v26 = ~v17 & (v17 + HIDWORD(v34[1]));
        LODWORD(v34[1]) = v25;
        if ( a3 < v26 )
          v26 = a3;
        HIDWORD(v34[1]) = v26;
        v13 = RdpBoundsAccumulator::AddRect(this, ~v17 & v23, v24, v25, v26);
        if ( v13 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v27, v28, v29);
            v15 = 48;
            v16 = "Failed to add rect";
            goto LABEL_37;
          }
          goto LABEL_38;
        }
        v18 = 1;
      }
    }
    v13 = 0;
    if ( v19 != -2147024637 )
      v13 = v19;
    if ( v13 >= 0 )
    {
      if ( v18 )
      {
        v13 = RdpBoundsAccumulator::SimplifyRects(this);
        if ( v13 < 0
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v30, v31, v32);
          v15 = 50;
          v16 = "Failed to simplify rects";
          goto LABEL_37;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v20, v21, v22);
      v15 = 49;
      v16 = "Failed to iterate rects";
      goto LABEL_37;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v9, v10, v11);
    v15 = 47;
    v16 = "CreateIterator failed!";
LABEL_37:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      (unsigned int)WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids,
      ActivityIdPrefix,
      (__int64)v16,
      v13,
      v34[0],
      v34[1]);
  }
LABEL_38:
  if ( v12 )
    (*(void (__fastcall **)(struct IRdpBAIterator *))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001ae30  push    rbp
0x18001ae32  push    rbx
0x18001ae33  push    rsi
0x18001ae34  push    rdi
0x18001ae35  push    r12
0x18001ae37  push    r13
0x18001ae39  push    r14
0x18001ae3b  push    r15
0x18001ae3d  mov     rbp, rsp
0x18001ae40  sub     rsp, 48h
0x18001ae44  mov     r13d, edx
0x18001ae47  mov     [rbp+var_18], 0
0x18001ae4f  lea     rdx, [rbp+var_18]; struct IRdpBAIterator **
0x18001ae53  mov     edi, r9d
0x18001ae56  mov     r12d, r8d
0x18001ae59  mov     r15, rcx
0x18001ae5c  call    ?CreateIterator@RdpBoundsAccumulator@@UEBAJPEAPEAVIRdpBAIterator@@@Z; RdpBoundsAccumulator::CreateIterator(IRdpBAIterator * *)
0x18001ae61  mov     rsi, [rbp+var_18]
0x18001ae65  mov     ebx, eax
0x18001ae67  test    eax, eax
0x18001ae69  jns     short loc_18001AEAC
0x18001ae6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae72  lea     rax, WPP_GLOBAL_Control
0x18001ae79  cmp     rcx, rax
0x18001ae7c  jz      loc_18001B03B
0x18001ae82  test    byte ptr [rcx+1Ch], 8
0x18001ae86  jz      loc_18001B03B
0x18001ae8c  cmp     byte ptr [rcx+19h], 2
0x18001ae90  jb      loc_18001B03B
0x18001ae96  call    RdpX_GetActivityIdPrefix
0x18001ae9b  mov     edx, 2Fh ; '/'
0x18001aea0  lea     rcx, aCreateiterator; "CreateIterator failed!"
0x18001aea7  jmp     loc_18001B018
0x18001aeac  dec     edi
0x18001aeae  xor     r14d, r14d
0x18001aeb1  xorps   xmm0, xmm0
0x18001aeb4  lea     rdx, [rbp+var_18]
0x18001aeb8  movdqu  xmmword ptr [rbp+var_18], xmm0
0x18001aebd  mov     rax, [rsi]
0x18001aec0  mov     rcx, rsi
0x18001aec3  mov     rax, [rax+20h]
0x18001aec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aecc  test    eax, eax
0x18001aece  js      loc_18001AF91
0x18001aed4  mov     r10d, dword ptr [rbp+var_18]
0x18001aed8  mov     eax, dword ptr [rbp+var_18+0Ch]
0x18001aedb  mov     edx, dword ptr [rbp+var_18+8]
0x18001aede  mov     r8d, dword ptr [rbp+var_18+4]
0x18001aee2  test    edi, r10d
0x18001aee5  jnz     short loc_18001AEFE
0x18001aee7  test    edi, r8d
0x18001aeea  jnz     short loc_18001AEFE
0x18001aeec  cmp     edx, r13d
0x18001aeef  jz      short loc_18001AEF5
0x18001aef1  test    edi, edx
0x18001aef3  jnz     short loc_18001AEFE
0x18001aef5  cmp     eax, r12d
0x18001aef8  jz      short loc_18001AEB1
0x18001aefa  test    edi, eax
0x18001aefc  jz      short loc_18001AEB1
0x18001aefe  lea     r9d, [rdx+rdi]
0x18001af02  mov     ecx, edi
0x18001af04  not     ecx
0x18001af06  and     r10d, ecx
0x18001af09  and     r8d, ecx; int
0x18001af0c  and     r9d, ecx
0x18001af0f  mov     dword ptr [rbp+var_18], r10d
0x18001af13  cmp     r13d, r9d
0x18001af16  mov     dword ptr [rbp+var_18+4], r8d
0x18001af1a  mov     edx, r10d; int
0x18001af1d  cmovl   r9d, r13d; int
0x18001af21  add     eax, edi
0x18001af23  and     eax, ecx
0x18001af25  mov     dword ptr [rbp+var_18+8], r9d
0x18001af29  cmp     r12d, eax
0x18001af2c  mov     rcx, r15; this
0x18001af2f  cmovl   eax, r12d
0x18001af33  mov     dword ptr [rbp+var_18+0Ch], eax
0x18001af36  mov     [rsp+48h+var_28], eax; int
0x18001af3a  call    ?AddRect@RdpBoundsAccumulator@@UEAAJHHHH@Z; RdpBoundsAccumulator::AddRect(int,int,int,int)
0x18001af3f  mov     ebx, eax
0x18001af41  test    eax, eax
0x18001af43  js      short loc_18001AF50
0x18001af45  mov     r14d, 1
0x18001af4b  jmp     loc_18001AEB1
0x18001af50  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af57  lea     rax, WPP_GLOBAL_Control
0x18001af5e  cmp     rcx, rax
0x18001af61  jz      loc_18001B03B
0x18001af67  test    byte ptr [rcx+1Ch], 8
0x18001af6b  jz      loc_18001B03B
0x18001af71  cmp     byte ptr [rcx+19h], 2
0x18001af75  jb      loc_18001B03B
0x18001af7b  call    RdpX_GetActivityIdPrefix
0x18001af80  mov     edx, 30h ; '0'
0x18001af85  lea     rcx, aFailedToAddRec; "Failed to add rect"
0x18001af8c  jmp     loc_18001B018
0x18001af91  xor     ebx, ebx
0x18001af93  cmp     eax, 80070103h
0x18001af98  cmovnz  ebx, eax
0x18001af9b  test    ebx, ebx
0x18001af9d  jns     short loc_18001AFD5
0x18001af9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afa6  lea     rax, WPP_GLOBAL_Control
0x18001afad  cmp     rcx, rax
0x18001afb0  jz      loc_18001B03B
0x18001afb6  test    byte ptr [rcx+1Ch], 8
0x18001afba  jz      short loc_18001B03B
0x18001afbc  cmp     byte ptr [rcx+19h], 2
0x18001afc0  jb      short loc_18001B03B
0x18001afc2  call    RdpX_GetActivityIdPrefix
0x18001afc7  mov     edx, 31h ; '1'
0x18001afcc  lea     rcx, aFailedToIterat; "Failed to iterate rects"
0x18001afd3  jmp     short loc_18001B018
0x18001afd5  test    r14d, r14d
0x18001afd8  jz      short loc_18001B03B
0x18001afda  mov     rcx, r15; this
0x18001afdd  call    ?SimplifyRects@RdpBoundsAccumulator@@UEBAJXZ; RdpBoundsAccumulator::SimplifyRects(void)
0x18001afe2  mov     ebx, eax
0x18001afe4  test    eax, eax
0x18001afe6  jns     short loc_18001B03B
0x18001afe8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afef  lea     rax, WPP_GLOBAL_Control
0x18001aff6  cmp     rcx, rax
0x18001aff9  jz      short loc_18001B03B
0x18001affb  test    byte ptr [rcx+1Ch], 8
0x18001afff  jz      short loc_18001B03B
0x18001b001  cmp     byte ptr [rcx+19h], 2
0x18001b005  jb      short loc_18001B03B
0x18001b007  call    RdpX_GetActivityIdPrefix
0x18001b00c  mov     edx, 32h ; '2'
0x18001b011  lea     rcx, aFailedToSimpli; "Failed to simplify rects"
0x18001b018  mov     [rsp+48h+var_20], ebx
0x18001b01c  lea     r8, WPP_e0b1a13c79f6309489df2e34f92a6dee_Traceguids
0x18001b023  mov     qword ptr [rsp+48h+var_28], rcx
0x18001b028  mov     r9d, eax
0x18001b02b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b032  mov     rcx, [rcx+10h]
0x18001b036  call    WPP_SF_DsD
0x18001b03b  test    rsi, rsi
0x18001b03e  jz      short loc_18001B04F
0x18001b040  mov     rax, [rsi]
0x18001b043  mov     rcx, rsi
0x18001b046  mov     rax, [rax+10h]
0x18001b04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b04f  mov     eax, ebx
0x18001b051  add     rsp, 48h
0x18001b055  pop     r15
0x18001b057  pop     r14
0x18001b059  pop     r13
0x18001b05b  pop     r12
0x18001b05d  pop     rdi
0x18001b05e  pop     rsi
0x18001b05f  pop     rbx
0x18001b060  pop     rbp
0x18001b061  retn
```
