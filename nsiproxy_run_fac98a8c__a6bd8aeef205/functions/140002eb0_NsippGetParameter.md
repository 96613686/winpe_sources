# NsippGetParameter

- ea: `0x140002eb0`
- end: `0x1400032c4`
- name: `NsippGetParameter`
- size: `1044`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140001dd0`
- `0x140002090`

## callees

- `0x140002eb0`
- `0x1400043d0`
- `0x1400056e8`
- `0x140006560`
- `0x140006980`
- `0x14000d08c`
- `0x14000d138`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x140002f20`
- `ntoskrnl!IoIs32bitProcess` at `0x140002f20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003076`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003076`
- `NETIO!NsiGetParameterEx` at `0x1400030df`
- `NETIO!NsiGetParameterEx` at `0x1400030df`

## pseudocode

```c
__int64 __fastcall NsippGetParameter(_DWORD *Src, unsigned int a2, unsigned __int8 a3, _QWORD *a4)
{
  BOOLEAN v7; // al
  _DWORD *v8; // r13
  char v9; // r15
  int Parameter; // ebx
  _DWORD *v11; // rdi
  unsigned int v13; // r12d
  void *v14; // rdx
  unsigned int v15; // eax
  void *v16; // rdx
  int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // [rsp+D0h] [rbp-E8h] BYREF
  PVOID P; // [rsp+D8h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-D8h] BYREF
  char *v22; // [rsp+E8h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-C8h] BYREF
  void *v24; // [rsp+F8h] [rbp-C0h] BYREF
  __int128 v25; // [rsp+100h] [rbp-B8h] BYREF
  __int128 v26; // [rsp+110h] [rbp-A8h]
  __int128 v27; // [rsp+120h] [rbp-98h]
  __m128i v28; // [rsp+130h] [rbp-88h] BYREF
  _QWORD v29[10]; // [rsp+140h] [rbp-78h] BYREF

  P = 0;
  v28 = 0;
  v24 = 0;
  v19 = 0;
  v21 = 0;
  v23 = 0;
  v22 = 0;
  memset(v29, 0, sizeof(v29));
  v7 = IoIs32bitProcess(0);
  if ( !Src )
    return 3221225485LL;
  if ( v7 )
  {
    if ( a2 >= 0x30 )
    {
      v25 = 0;
      v26 = 0;
      v27 = 0;
      v9 = 1;
      v8 = Src;
      if ( a3 )
        RtlCopyFromUser(&v25, Src, 0x30u);
      else
        RtlCopyVolatileMemory(&v25, Src, 0x30u);
      v29[5] = DWORD2(v26);
      LODWORD(v29[6]) = HIDWORD(v26);
      v29[2] = DWORD2(v25);
      LODWORD(v29[1]) = DWORD1(v25);
      LODWORD(v29[3]) = HIDWORD(v25);
      v29[8] = DWORD1(v27);
      v29[9] = *((_QWORD *)&v27 + 1);
      LODWORD(v29[7]) = v27;
      v29[4] = v26;
      v29[0] = (int)v25;
      goto LABEL_7;
    }
    return 3221225485LL;
  }
  v8 = 0;
  v9 = 0;
  if ( a2 < 0x50 )
    return 3221225485LL;
  if ( a3 )
    RtlCopyFromUser(v29, Src, 0x50u);
  else
    RtlCopyVolatileMemory(v29, Src, 0x50u);
LABEL_7:
  Parameter = NsippProbeAndAllocateParameters(
                v29,
                0x50u,
                (__int64)&v29[1],
                (__m128i *)&v29[5],
                (__int64)&v29[7],
                0,
                0,
                0,
                a3,
                1u,
                0,
                &v28,
                &v21,
                &v24,
                &v19,
                &v23,
                0,
                0,
                0,
                0,
                0,
                0,
                0,
                &v22,
                &P);
  v11 = P;
  if ( Parameter >= 0 )
  {
    *((_QWORD *)P + 5) = v21;
    v11[12] = v28.m128i_i32[2];
    *((_QWORD *)v11 + 2) = v22;
    *((_QWORD *)v11 + 8) = v23;
    v13 = v19;
    v11[18] = v19;
    Parameter = NsiGetParameterEx(v11);
    if ( Parameter >= 0 )
    {
      *a4 = 80;
      v14 = (void *)*((_QWORD *)v11 + 5);
      if ( v14 )
      {
        v15 = v11[12];
        if ( v15 )
        {
          if ( a3 )
            RtlCopyToUser((void *)v28.m128i_i64[0], v14, v15);
          else
            RtlCopyVolatileMemory((void *)v28.m128i_i64[0], v14, v15);
        }
      }
      v16 = (void *)*((_QWORD *)v11 + 8);
      if ( v16 )
      {
        v18 = v11[18];
        if ( v18 )
        {
          if ( a3 )
            RtlCopyToUser(v24, v16, v18);
          else
            RtlCopyVolatileMemory(v24, v16, v18);
        }
      }
      v17 = v11[18];
      if ( v9 == 1 )
      {
        if ( v13 != v17 )
        {
          if ( a3 )
            RtlWriteULongToUser(v8 + 10, v17);
          else
            v8[10] = v17;
        }
      }
      else if ( v13 != v17 )
      {
        if ( a3 )
          RtlWriteULongToUser(Src + 18, v17);
        else
          Src[18] = v17;
      }
    }
  }
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x140002eb0  mov     rax, rsp
0x140002eb3  mov     [rax+8], rbx
0x140002eb7  mov     [rax+10h], rsi
0x140002ebb  mov     [rax+20h], r9
0x140002ebf  push    rdi
0x140002ec0  push    r12
0x140002ec2  push    r13
0x140002ec4  push    r14
0x140002ec6  push    r15
0x140002ec8  sub     rsp, 190h
0x140002ecf  movzx   esi, r8b
0x140002ed3  mov     ebx, edx
0x140002ed5  mov     r14, rcx
0x140002ed8  xor     edi, edi
0x140002eda  mov     [rax-0E0h], rdi
0x140002ee1  xorps   xmm0, xmm0
0x140002ee4  movups  xmmword ptr [rax-88h], xmm0
0x140002eeb  mov     [rax-0C0h], rdi
0x140002ef2  mov     [rax-0E8h], edi
0x140002ef8  mov     [rax-0D8h], rdi
0x140002eff  mov     [rax-0C8h], rdi
0x140002f06  mov     [rax-0D0h], rdi
0x140002f0d  xor     edx, edx; Val
0x140002f0f  mov     r8d, 50h ; 'P'; Size
0x140002f15  lea     rcx, [rax-78h]; void *
0x140002f19  call    memset
0x140002f1e  xor     ecx, ecx; Irp
0x140002f20  call    cs:__imp_IoIs32bitProcess
0x140002f27  nop     dword ptr [rax+rax+00h]
0x140002f2c  test    r14, r14
0x140002f2f  jz      loc_1400032BA
0x140002f35  test    al, al
0x140002f37  jnz     loc_1400031B5
0x140002f3d  mov     r13d, edi
0x140002f40  xor     r15b, r15b
0x140002f43  cmp     ebx, 50h ; 'P'
0x140002f46  jb      loc_1400032BA
0x140002f4c  mov     r8d, 50h ; 'P'; Size
0x140002f52  mov     rdx, r14; Src
0x140002f55  lea     rcx, [rsp+1B8h+var_78]; void *
0x140002f5d  test    sil, sil
0x140002f60  jz      short loc_140002F69
0x140002f62  call    RtlCopyFromUser
0x140002f67  jmp     short loc_140002F6E
0x140002f69  call    RtlCopyVolatileMemory
0x140002f6e  jmp     short loc_140002F75
0x140002f70  jmp     loc_140003084
0x140002f75  lea     rax, [rsp+1B8h+P]
0x140002f7d  mov     [rsp+1B8h+var_F8], rax
0x140002f85  lea     rax, [rsp+1B8h+var_D0]
0x140002f8d  mov     [rsp+1B8h+var_100], rax
0x140002f95  mov     [rsp+1B8h+var_108], rdi
0x140002f9d  mov     [rsp+1B8h+var_110], rdi
0x140002fa5  mov     [rsp+1B8h+var_118], rdi
0x140002fad  mov     [rsp+1B8h+var_120], rdi
0x140002fb5  mov     [rsp+1B8h+var_128], rdi
0x140002fbd  mov     [rsp+1B8h+var_130], rdi
0x140002fc5  mov     [rsp+1B8h+var_138], rdi
0x140002fcd  lea     rax, [rsp+1B8h+var_C8]
0x140002fd5  mov     [rsp+1B8h+var_140], rax
0x140002fda  lea     rax, [rsp+1B8h+var_E8]
0x140002fe2  mov     [rsp+1B8h+var_148], rax
0x140002fe7  lea     rax, [rsp+1B8h+var_C0]
0x140002fef  mov     [rsp+1B8h+var_150], rax
0x140002ff4  lea     rax, [rsp+1B8h+var_D8]
0x140002ffc  mov     [rsp+1B8h+var_158], rax
0x140003001  lea     rax, [rsp+1B8h+var_88]
0x140003009  mov     [rsp+1B8h+var_160], rax
0x14000300e  mov     [rsp+1B8h+var_168], 0
0x140003013  mov     [rsp+1B8h+var_170], 1
0x14000301b  mov     [rsp+1B8h+var_178], sil
0x140003020  mov     [rsp+1B8h+var_180], rdi
0x140003025  mov     [rsp+1B8h+var_188], rdi
0x14000302a  mov     [rsp+1B8h+var_190], rdi
0x14000302f  lea     rax, [rsp+1B8h+var_40]
0x140003037  mov     [rsp+1B8h+var_198], rax
0x14000303c  lea     r9, [rsp+1B8h+var_50]
0x140003044  lea     r8, [rsp+1B8h+var_70]
0x14000304c  mov     edx, 50h ; 'P'
0x140003051  lea     rcx, [rsp+1B8h+var_78]
0x140003059  call    NsippProbeAndAllocateParameters
0x14000305e  mov     ebx, eax
0x140003060  mov     rdi, [rsp+1B8h+P]
0x140003068  test    eax, eax
0x14000306a  jns     short loc_1400030A2
0x14000306c  test    rdi, rdi
0x14000306f  jz      short loc_140003082
0x140003071  xor     edx, edx; Tag
0x140003073  mov     rcx, rdi; P
0x140003076  call    cs:__imp_ExFreePoolWithTag
0x14000307d  nop     dword ptr [rax+rax+00h]
0x140003082  mov     eax, ebx
0x140003084  lea     r11, [rsp+1B8h+var_28]
0x14000308c  mov     rbx, [r11+30h]
0x140003090  mov     rsi, [r11+38h]
0x140003094  mov     rsp, r11
0x140003097  pop     r15
0x140003099  pop     r14
0x14000309b  pop     r13
0x14000309d  pop     r12
0x14000309f  pop     rdi
0x1400030a0  retn
0x1400030a2  mov     rax, [rsp+1B8h+var_D8]
0x1400030aa  mov     [rdi+28h], rax
0x1400030ae  mov     eax, [rsp+1B8h+var_80]
0x1400030b5  mov     [rdi+30h], eax
0x1400030b8  mov     rax, [rsp+1B8h+var_D0]
0x1400030c0  mov     [rdi+10h], rax
0x1400030c4  mov     rax, [rsp+1B8h+var_C8]
0x1400030cc  mov     [rdi+40h], rax
0x1400030d0  mov     r12d, [rsp+1B8h+var_E8]
0x1400030d8  mov     [rdi+48h], r12d
0x1400030dc  mov     rcx, rdi
0x1400030df  call    cs:__imp_NsiGetParameterEx
0x1400030e6  nop     dword ptr [rax+rax+00h]
0x1400030eb  mov     ebx, eax
0x1400030ed  test    eax, eax
0x1400030ef  js      loc_14000306C
0x1400030f5  mov     rax, [rsp+1B8h+arg_18]
0x1400030fd  mov     qword ptr [rax], 50h ; 'P'
0x140003104  mov     rdx, [rdi+28h]; Src
0x140003108  test    rdx, rdx
0x14000310b  jz      short loc_140003129
0x14000310d  mov     eax, [rdi+30h]
0x140003110  test    eax, eax
0x140003112  jz      short loc_140003129
0x140003114  mov     rcx, [rsp+1B8h+var_88]; void *
0x14000311c  mov     r8d, eax; Size
0x14000311f  test    sil, sil
0x140003122  jz      short loc_14000318E
0x140003124  call    RtlCopyToUser
0x140003129  mov     rdx, [rdi+40h]; Src
0x14000312d  test    rdx, rdx
0x140003130  jnz     short loc_140003152
0x140003132  mov     eax, [rdi+48h]
0x140003135  cmp     r15b, 1
0x140003139  jz      short loc_14000319C
0x14000313b  cmp     r12d, eax
0x14000313e  jz      short loc_1400031A1
0x140003140  test    sil, sil
0x140003143  jz      short loc_140003188
0x140003145  mov     edx, eax
0x140003147  lea     rcx, [r14+48h]
0x14000314b  call    RtlWriteULongToUser
0x140003150  jmp     short loc_1400031A1
0x140003152  mov     eax, [rdi+48h]
0x140003155  test    eax, eax
0x140003157  jz      short loc_140003132
0x140003159  mov     rcx, [rsp+1B8h+var_C0]; void *
0x140003161  mov     r8d, eax; Size
0x140003164  test    sil, sil
0x140003167  jz      short loc_140003195
0x140003169  call    RtlCopyToUser
0x14000316e  jmp     short loc_140003132
0x140003170  test    sil, sil
0x140003173  jz      short loc_140003182
0x140003175  mov     edx, eax
0x140003177  lea     rcx, [r13+28h]
0x14000317b  call    RtlWriteULongToUser
0x140003180  jmp     short loc_1400031A1
0x140003182  mov     [r13+28h], eax
0x140003186  jmp     short loc_1400031A1
0x140003188  mov     [r14+48h], eax
0x14000318c  jmp     short loc_1400031A1
0x14000318e  call    RtlCopyVolatileMemory
0x140003193  jmp     short loc_140003129
0x140003195  call    RtlCopyVolatileMemory
0x14000319a  jmp     short loc_140003132
0x14000319c  cmp     r12d, eax
0x14000319f  jnz     short loc_140003170
0x1400031a1  jmp     loc_14000306C
0x1400031a6  mov     ebx, eax
0x1400031a8  mov     rdi, [rsp+1B8h+P]
0x1400031b0  jmp     loc_14000306C
0x1400031b5  cmp     ebx, 30h ; '0'
0x1400031b8  jb      loc_1400032BA
0x1400031be  xorps   xmm0, xmm0
0x1400031c1  movups  [rsp+1B8h+var_B8], xmm0
0x1400031c9  movups  [rsp+1B8h+var_A8], xmm0
0x1400031d1  movups  [rsp+1B8h+var_98], xmm0
0x1400031d9  mov     r15b, 1
0x1400031dc  mov     r13, r14
0x1400031df  mov     r8d, 30h ; '0'; Size
0x1400031e5  mov     rdx, r14; Src
0x1400031e8  lea     rcx, [rsp+1B8h+var_B8]; void *
0x1400031f0  test    sil, sil
0x1400031f3  jz      short loc_1400031FC
0x1400031f5  call    RtlCopyFromUser
0x1400031fa  jmp     short loc_140003201
0x1400031fc  call    RtlCopyVolatileMemory
0x140003201  jmp     short loc_140003208
0x140003203  jmp     loc_140003084
0x140003208  mov     eax, dword ptr [rsp+1B8h+var_A8+4]
0x14000320f  mov     dword ptr [rsp+1B8h+var_58+4], eax
0x140003216  mov     eax, dword ptr [rsp+1B8h+var_A8+8]
0x14000321d  mov     [rsp+1B8h+var_50], rax
0x140003225  mov     eax, dword ptr [rsp+1B8h+var_A8+0Ch]
0x14000322c  mov     [rsp+1B8h+var_48], eax
0x140003233  mov     eax, dword ptr [rsp+1B8h+var_B8+8]
0x14000323a  mov     [rsp+1B8h+var_68], rax
0x140003242  mov     eax, dword ptr [rsp+1B8h+var_B8+4]
0x140003249  mov     [rsp+1B8h+var_70], eax
0x140003250  mov     eax, dword ptr [rsp+1B8h+var_B8+0Ch]
0x140003257  mov     [rsp+1B8h+var_60], eax
0x14000325e  mov     eax, dword ptr [rsp+1B8h+var_98+4]
0x140003265  mov     [rsp+1B8h+var_38], rax
0x14000326d  mov     eax, dword ptr [rsp+1B8h+var_98+8]
0x140003274  mov     dword ptr [rsp+1B8h+var_30], eax
0x14000327b  mov     eax, dword ptr [rsp+1B8h+var_98+0Ch]
0x140003282  mov     dword ptr [rsp+1B8h+var_30+4], eax
0x140003289  mov     eax, dword ptr [rsp+1B8h+var_98]
0x140003290  mov     [rsp+1B8h+var_40], eax
0x140003297  mov     eax, dword ptr [rsp+1B8h+var_A8]
0x14000329e  mov     dword ptr [rsp+1B8h+var_58], eax
0x1400032a5  movsxd  rax, dword ptr [rsp+1B8h+var_B8]
0x1400032ad  mov     [rsp+1B8h+var_78], rax
0x1400032b5  jmp     loc_140002F75
0x1400032ba  mov     eax, 0C000000Dh
0x1400032bf  jmp     loc_140003084
```
