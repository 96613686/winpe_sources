# NatAdjustMSSOption

- ea: `0x14001f8f0`
- end: `0x14001feb7`
- name: `NatAdjustMSSOption`
- size: `1479`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x140020580`
- `0x140020970`
- `0x140021150`
- `0x140022d70`
- `0x140023160`
- `0x140023940`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140002200`
- `0x14001f8f0`

## pseudocode

```c
__int16 __fastcall NatAdjustMSSOption(__int64 a1, unsigned __int16 a2)
{
  int v2; // ebp
  __int64 v4; // rsi
  unsigned __int8 *v5; // rax
  signed __int64 v6; // rdx
  unsigned __int8 *v7; // rbx
  unsigned __int64 v8; // rdi
  __int64 v9; // rcx
  unsigned __int16 v10; // dx
  unsigned __int16 v11; // r10
  unsigned __int16 v12; // r9
  int v13; // r8d
  PDEVICE_OBJECT v14; // rcx
  unsigned __int16 v15; // dx
  __int64 v17; // [rsp+20h] [rbp-48h]

  v2 = a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x37u,
      (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids,
      a2);
  }
  v4 = *(_QWORD *)(a1 + 40);
  v5 = *(unsigned __int8 **)(a1 + 32);
  v6 = ((unsigned __int64)*(unsigned __int16 *)(v4 + 12) >> 2) & 0x3C;
  if ( *((_QWORD *)v5 + 2) + *((unsigned int *)v5 + 6) - v4 < v6 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        LOWORD(v5) = WPP_SF_(
                       (__int64)WPP_GLOBAL_Control->AttachedDevice,
                       0x38u,
                       (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
        {
          v15 = 57;
LABEL_116:
          LOWORD(v5) = WPP_SF_(
                         (__int64)v14->AttachedDevice,
                         v15,
                         (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
        }
      }
    }
  }
  else
  {
    v7 = (unsigned __int8 *)(v4 + 20);
    v8 = v6 + v4;
    while ( (unsigned __int64)v7 < v8 )
    {
      switch ( *v7 )
      {
        case 0u:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              LOWORD(v5) = WPP_SF_(
                             (__int64)WPP_GLOBAL_Control->AttachedDevice,
                             0x3Au,
                             (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
              if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
              {
                v15 = 59;
                goto LABEL_116;
              }
            }
          }
          return (__int16)v5;
        case 1u:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              LOWORD(v5) = WPP_SF_(
                             (__int64)WPP_GLOBAL_Control->AttachedDevice,
                             0x3Cu,
                             (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
          }
          v9 = 1;
          break;
        case 2u:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0x3Du,
              (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
          }
          LOWORD(v5) = v8 - (_WORD)v7;
          if ( (__int64)(v8 - (_QWORD)v7) < 4 || v7[1] != 4 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
              if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                LOWORD(v5) = WPP_SF_(
                               (__int64)WPP_GLOBAL_Control->AttachedDevice,
                               0x3Eu,
                               (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
                if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
                {
                  v15 = 63;
                  goto LABEL_116;
                }
              }
            }
            return (__int16)v5;
          }
          v10 = *((_WORD *)v7 + 1);
          v11 = __ROR2__(v10, 8);
          if ( v11 > (unsigned __int16)v2 )
          {
            v12 = __ROR2__(v2, 8);
            *((_WORD *)v7 + 1) = v12;
            if ( (((_BYTE)v7 - (_BYTE)v4) & 1) != 0 )
            {
              v13 = (unsigned __int16)~(HIBYTE(v10) | 0x400)
                  + (*v7 | (unsigned __int16)(v12 << 8))
                  + (unsigned __int16)~(*v7 | (unsigned __int16)(v10 << 8));
              LODWORD(v5) = v7[3] | 0x400;
            }
            else
            {
              LODWORD(v5) = v12;
              v13 = (unsigned __int16)~v10;
            }
            LOWORD(v5) = ~((((_DWORD)v5 + v13 + (unsigned int)(unsigned __int16)~*(_WORD *)(v4 + 16)) >> 16)
                         + ~*(_WORD *)(v4 + 16)
                         + (_WORD)v5
                         + v13
                         + (((((_DWORD)v5 + v13 + (unsigned int)(unsigned __int16)~*(_WORD *)(v4 + 16)) >> 16)
                           + (unsigned __int16)(~*(_WORD *)(v4 + 16) + (_WORD)v5 + v13)) >> 16));
            *(_WORD *)(v4 + 16) = (_WORD)v5;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
              if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                LODWORD(v17) = v2;
                LOWORD(v5) = WPP_SF_dd(
                               (__int64)WPP_GLOBAL_Control->AttachedDevice,
                               0x40u,
                               (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids,
                               v11,
                               v17);
              }
            }
          }
          v9 = 4;
          break;
        case 3u:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0x41u,
              (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
          }
          LOWORD(v5) = (_WORD)v7 - v8;
          if ( (__int64)&v7[-v8] < 3 || v7[1] != 3 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
              if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                LOWORD(v5) = WPP_SF_(
                               (__int64)WPP_GLOBAL_Control->AttachedDevice,
                               0x42u,
                               (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
                if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
                {
                  v15 = 67;
                  goto LABEL_116;
                }
              }
            }
            return (__int16)v5;
          }
          v9 = 3;
          break;
        case 4u:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0x47u,
              (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
          }
          LOWORD(v5) = (_WORD)v7 - v8;
          if ( (__int64)&v7[-v8] < 2 || v7[1] != 2 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
              if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                LOWORD(v5) = WPP_SF_(
                               (__int64)WPP_GLOBAL_Control->AttachedDevice,
                               0x48u,
                               (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
                if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
                {
                  v15 = 73;
                  goto LABEL_116;
                }
              }
            }
            return (__int16)v5;
          }
          v9 = 2;
          break;
        case 8u:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0x44u,
              (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
          }
          LOWORD(v5) = (_WORD)v7 - v8;
          if ( (__int64)&v7[-v8] < 10 || v7[1] != 10 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
              if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                LOWORD(v5) = WPP_SF_(
                               (__int64)WPP_GLOBAL_Control->AttachedDevice,
                               0x45u,
                               (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
                if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
                {
                  v15 = 70;
                  goto LABEL_116;
                }
              }
            }
            return (__int16)v5;
          }
          v9 = 10;
          break;
        default:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0x4Au,
              (__int64)WPP_876e08a63f053efae1df392b423d899c_Traceguids);
          }
          v5 = v7 + 1;
          if ( v8 <= (unsigned __int64)(v7 + 1) )
            return (__int16)v5;
          v9 = *v5;
          if ( (unsigned __int8)v9 < 2u )
            return (__int16)v5;
          LOWORD(v5) = v8 - (_WORD)v7;
          if ( v9 > (__int64)(v8 - (_QWORD)v7) )
            return (__int16)v5;
          break;
      }
      v7 += v9;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      LODWORD(v5) = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( ((unsigned __int8)v5 & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v15 = 75;
        goto LABEL_116;
      }
    }
  }
  return (__int16)v5;
}

```

## disassembly

```asm
0x14001f8f0  push    rbx
0x14001f8f2  push    rbp
0x14001f8f3  push    rsi
0x14001f8f4  push    rdi
0x14001f8f5  push    r12
0x14001f8f7  push    r14
0x14001f8f9  push    r15
0x14001f8fb  sub     rsp, 30h
0x14001f8ff  movzx   ebp, dx
0x14001f902  mov     rbx, rcx
0x14001f905  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f90c  lea     r15, WPP_GLOBAL_Control
0x14001f913  lea     r12, WPP_876e08a63f053efae1df392b423d899c_Traceguids
0x14001f91a  mov     r14d, 1
0x14001f920  cmp     rcx, r15
0x14001f923  jz      short loc_14001F946
0x14001f925  mov     eax, [rcx+2Ch]
0x14001f928  test    r14b, al
0x14001f92b  jz      short loc_14001F946
0x14001f92d  cmp     byte ptr [rcx+29h], 6
0x14001f931  jb      short loc_14001F946
0x14001f933  mov     rcx, [rcx+18h]
0x14001f937  lea     edx, [r14+36h]
0x14001f93b  mov     r9d, ebp
0x14001f93e  mov     r8, r12
0x14001f941  call    WPP_SF_d
0x14001f946  mov     rsi, [rbx+28h]
0x14001f94a  mov     rax, [rbx+20h]
0x14001f94e  movzx   edx, word ptr [rsi+0Ch]
0x14001f952  mov     ecx, [rax+18h]
0x14001f955  add     rcx, [rax+10h]
0x14001f959  shr     rdx, 2
0x14001f95d  sub     rcx, rsi
0x14001f960  and     edx, 3Ch
0x14001f963  cmp     rcx, rdx
0x14001f966  jl      loc_14001FE51
0x14001f96c  lea     rbx, [rsi+14h]
0x14001f970  lea     rdi, [rdx+rsi]
0x14001f974  cmp     rbx, rdi
0x14001f977  jnb     loc_14001FE30
0x14001f97d  movzx   ecx, byte ptr [rbx]
0x14001f980  mov     dl, 5
0x14001f982  test    ecx, ecx
0x14001f984  jz      loc_14001FDD9
0x14001f98a  sub     ecx, r14d
0x14001f98d  jz      loc_14001FC28
0x14001f993  sub     ecx, r14d
0x14001f996  jz      loc_14001FAF4
0x14001f99c  sub     ecx, r14d
0x14001f99f  jz      loc_14001FAA6
0x14001f9a5  sub     ecx, r14d
0x14001f9a8  jz      loc_14001FA58
0x14001f9ae  cmp     ecx, 4
0x14001f9b1  jz      short loc_14001FA0A
0x14001f9b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f9ba  cmp     rcx, r15
0x14001f9bd  jz      short loc_14001F9DD
0x14001f9bf  mov     eax, [rcx+2Ch]
0x14001f9c2  test    r14b, al
0x14001f9c5  jz      short loc_14001F9DD
0x14001f9c7  cmp     [rcx+29h], dl
0x14001f9ca  jb      short loc_14001F9DD
0x14001f9cc  mov     rcx, [rcx+18h]
0x14001f9d0  mov     edx, 4Ah ; 'J'
0x14001f9d5  mov     r8, r12
0x14001f9d8  call    WPP_SF_
0x14001f9dd  lea     rax, [rbx+1]
0x14001f9e1  cmp     rdi, rax
0x14001f9e4  jbe     loc_14001FEA7
0x14001f9ea  movzx   ecx, byte ptr [rax]
0x14001f9ed  cmp     cl, 2
0x14001f9f0  jb      loc_14001FEA7
0x14001f9f6  mov     rax, rdi
0x14001f9f9  sub     rax, rbx
0x14001f9fc  cmp     rcx, rax
0x14001f9ff  jg      loc_14001FEA7
0x14001fa05  jmp     loc_14001FC55
0x14001fa0a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fa11  cmp     rcx, r15
0x14001fa14  jz      short loc_14001FA34
0x14001fa16  mov     eax, [rcx+2Ch]
0x14001fa19  test    r14b, al
0x14001fa1c  jz      short loc_14001FA34
0x14001fa1e  cmp     [rcx+29h], dl
0x14001fa21  jb      short loc_14001FA34
0x14001fa23  mov     rcx, [rcx+18h]
0x14001fa27  mov     edx, 44h ; 'D'
0x14001fa2c  mov     r8, r12
0x14001fa2f  call    WPP_SF_
0x14001fa34  mov     rax, rbx
0x14001fa37  sub     rax, rdi
0x14001fa3a  cmp     rax, 0Ah
0x14001fa3e  jl      loc_14001FC5D
0x14001fa44  cmp     byte ptr [rbx+1], 0Ah
0x14001fa48  jnz     loc_14001FC5D
0x14001fa4e  mov     ecx, 0Ah
0x14001fa53  jmp     loc_14001FC55
0x14001fa58  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fa5f  cmp     rcx, r15
0x14001fa62  jz      short loc_14001FA82
0x14001fa64  mov     eax, [rcx+2Ch]
0x14001fa67  test    r14b, al
0x14001fa6a  jz      short loc_14001FA82
0x14001fa6c  cmp     [rcx+29h], dl
0x14001fa6f  jb      short loc_14001FA82
0x14001fa71  mov     rcx, [rcx+18h]
0x14001fa75  mov     edx, 47h ; 'G'
0x14001fa7a  mov     r8, r12
0x14001fa7d  call    WPP_SF_
0x14001fa82  mov     rax, rbx
0x14001fa85  sub     rax, rdi
0x14001fa88  cmp     rax, 2
0x14001fa8c  jl      loc_14001FCBC
0x14001fa92  cmp     byte ptr [rbx+1], 2
0x14001fa96  jnz     loc_14001FCBC
0x14001fa9c  mov     ecx, 2
0x14001faa1  jmp     loc_14001FC55
0x14001faa6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001faad  cmp     rcx, r15
0x14001fab0  jz      short loc_14001FAD0
0x14001fab2  mov     eax, [rcx+2Ch]
0x14001fab5  test    r14b, al
0x14001fab8  jz      short loc_14001FAD0
0x14001faba  cmp     [rcx+29h], dl
0x14001fabd  jb      short loc_14001FAD0
0x14001fabf  mov     rcx, [rcx+18h]
0x14001fac3  mov     edx, 41h ; 'A'
0x14001fac8  mov     r8, r12
0x14001facb  call    WPP_SF_
0x14001fad0  mov     rax, rbx
0x14001fad3  sub     rax, rdi
0x14001fad6  cmp     rax, 3
0x14001fada  jl      loc_14001FD1B
0x14001fae0  cmp     byte ptr [rbx+1], 3
0x14001fae4  jnz     loc_14001FD1B
0x14001faea  mov     ecx, 3
0x14001faef  jmp     loc_14001FC55
0x14001faf4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fafb  cmp     rcx, r15
0x14001fafe  jz      short loc_14001FB1E
0x14001fb00  mov     eax, [rcx+2Ch]
0x14001fb03  test    r14b, al
0x14001fb06  jz      short loc_14001FB1E
0x14001fb08  cmp     [rcx+29h], dl
0x14001fb0b  jb      short loc_14001FB1E
0x14001fb0d  mov     rcx, [rcx+18h]
0x14001fb11  mov     edx, 3Dh ; '='
0x14001fb16  mov     r8, r12
0x14001fb19  call    WPP_SF_
0x14001fb1e  mov     rax, rdi
0x14001fb21  sub     rax, rbx
0x14001fb24  cmp     rax, 4
0x14001fb28  jl      loc_14001FD7A
0x14001fb2e  cmp     byte ptr [rbx+1], 4
0x14001fb32  jnz     loc_14001FD7A
0x14001fb38  movzx   edx, word ptr [rbx+2]
0x14001fb3c  movzx   r10d, dx
0x14001fb40  ror     r10w, 8
0x14001fb45  cmp     r10w, bp
0x14001fb49  ja      short loc_14001FB55
0x14001fb4b  mov     ecx, 4
0x14001fb50  jmp     loc_14001FC55
0x14001fb55  movzx   r9d, bp
0x14001fb59  ror     r9w, 8
0x14001fb5e  mov     [rbx+2], r9w
0x14001fb63  movzx   eax, word ptr [rsi+10h]
0x14001fb67  not     ax
0x14001fb6a  movzx   r11d, ax
0x14001fb6e  mov     al, bl
0x14001fb70  sub     al, sil
0x14001fb73  test    r14b, al
0x14001fb76  jnz     short loc_14001FB85
0x14001fb78  not     dx
0x14001fb7b  movzx   eax, r9w
0x14001fb7f  movzx   r8d, dx
0x14001fb83  jmp     short loc_14001FBC2
0x14001fb85  movzx   ecx, byte ptr [rbx]
0x14001fb88  movzx   eax, dx
0x14001fb8b  shl     ax, 8
0x14001fb8f  or      ax, cx
0x14001fb92  shr     dx, 8
0x14001fb96  not     ax
0x14001fb99  shl     r9w, 8
0x14001fb9e  movzx   r8d, ax
0x14001fba2  movzx   eax, r9w
0x14001fba6  or      eax, ecx
0x14001fba8  mov     ecx, 400h
0x14001fbad  add     r8d, eax
0x14001fbb0  or      dx, cx
0x14001fbb3  not     dx
0x14001fbb6  movzx   eax, dx
0x14001fbb9  add     r8d, eax
0x14001fbbc  movzx   eax, byte ptr [rbx+3]
0x14001fbc0  or      eax, ecx
0x14001fbc2  add     r8d, eax
0x14001fbc5  lea     eax, [r11+r8]
0x14001fbc9  movzx   edx, ax
0x14001fbcc  lea     eax, [r8+r11]
0x14001fbd0  shr     eax, 10h
0x14001fbd3  add     edx, eax
0x14001fbd5  mov     eax, edx
0x14001fbd7  shr     eax, 10h
0x14001fbda  add     ax, dx
0x14001fbdd  not     ax
0x14001fbe0  mov     [rsi+10h], ax
0x14001fbe4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fbeb  cmp     rcx, r15
0x14001fbee  jz      loc_14001FB4B
0x14001fbf4  mov     eax, [rcx+2Ch]
0x14001fbf7  test    r14b, al
0x14001fbfa  jz      loc_14001FB4B
0x14001fc00  cmp     byte ptr [rcx+29h], 2
0x14001fc04  jb      loc_14001FB4B
0x14001fc0a  mov     rcx, [rcx+18h]
0x14001fc0e  mov     edx, 40h ; '@'
0x14001fc13  movzx   r9d, r10w
0x14001fc17  mov     r8, r12
0x14001fc1a  mov     dword ptr [rsp+68h+var_48], ebp
0x14001fc1e  call    WPP_SF_dd
0x14001fc23  jmp     loc_14001FB4B
0x14001fc28  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fc2f  cmp     rcx, r15
0x14001fc32  jz      short loc_14001FC52
0x14001fc34  mov     eax, [rcx+2Ch]
0x14001fc37  test    r14b, al
0x14001fc3a  jz      short loc_14001FC52
0x14001fc3c  cmp     [rcx+29h], dl
0x14001fc3f  jb      short loc_14001FC52
0x14001fc41  mov     rcx, [rcx+18h]
0x14001fc45  mov     edx, 3Ch ; '<'
0x14001fc4a  mov     r8, r12
0x14001fc4d  call    WPP_SF_
0x14001fc52  mov     rcx, r14
0x14001fc55  add     rbx, rcx
0x14001fc58  jmp     loc_14001F974
0x14001fc5d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fc64  cmp     rcx, r15
0x14001fc67  jz      loc_14001FEA7
0x14001fc6d  mov     eax, [rcx+2Ch]
0x14001fc70  test    r14b, al
0x14001fc73  jz      short loc_14001FC8C
0x14001fc75  cmp     byte ptr [rcx+29h], 2
0x14001fc79  jb      short loc_14001FC8C
0x14001fc7b  mov     rcx, [rcx+18h]
0x14001fc7f  mov     edx, 45h ; 'E'
0x14001fc84  mov     r8, r12
0x14001fc87  call    WPP_SF_
0x14001fc8c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fc93  cmp     rcx, r15
0x14001fc96  jz      loc_14001FEA7
0x14001fc9c  mov     eax, [rcx+2Ch]
0x14001fc9f  test    r14b, al
0x14001fca2  jz      loc_14001FEA7
0x14001fca8  cmp     byte ptr [rcx+29h], 6
0x14001fcac  jb      loc_14001FEA7
0x14001fcb2  mov     edx, 46h ; 'F'
0x14001fcb7  jmp     loc_14001FE9B
0x14001fcbc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fcc3  cmp     rcx, r15
0x14001fcc6  jz      loc_14001FEA7
0x14001fccc  mov     eax, [rcx+2Ch]
0x14001fccf  test    r14b, al
0x14001fcd2  jz      short loc_14001FCEB
0x14001fcd4  cmp     byte ptr [rcx+29h], 2
0x14001fcd8  jb      short loc_14001FCEB
0x14001fcda  mov     rcx, [rcx+18h]
0x14001fcde  mov     edx, 48h ; 'H'
0x14001fce3  mov     r8, r12
0x14001fce6  call    WPP_SF_
0x14001fceb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fcf2  cmp     rcx, r15
0x14001fcf5  jz      loc_14001FEA7
0x14001fcfb  mov     eax, [rcx+2Ch]
0x14001fcfe  test    r14b, al
0x14001fd01  jz      loc_14001FEA7
0x14001fd07  cmp     byte ptr [rcx+29h], 6
0x14001fd0b  jb      loc_14001FEA7
0x14001fd11  mov     edx, 49h ; 'I'
0x14001fd16  jmp     loc_14001FE9B
0x14001fd1b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fd22  cmp     rcx, r15
0x14001fd25  jz      loc_14001FEA7
0x14001fd2b  mov     eax, [rcx+2Ch]
0x14001fd2e  test    r14b, al
0x14001fd31  jz      short loc_14001FD4A
0x14001fd33  cmp     byte ptr [rcx+29h], 2
0x14001fd37  jb      short loc_14001FD4A
0x14001fd39  mov     rcx, [rcx+18h]
0x14001fd3d  mov     edx, 42h ; 'B'
0x14001fd42  mov     r8, r12
0x14001fd45  call    WPP_SF_
0x14001fd4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fd51  cmp     rcx, r15
0x14001fd54  jz      loc_14001FEA7
0x14001fd5a  mov     eax, [rcx+2Ch]
0x14001fd5d  test    r14b, al
0x14001fd60  jz      loc_14001FEA7
0x14001fd66  cmp     byte ptr [rcx+29h], 6
0x14001fd6a  jb      loc_14001FEA7
0x14001fd70  mov     edx, 43h ; 'C'
  ... truncated ...
```
