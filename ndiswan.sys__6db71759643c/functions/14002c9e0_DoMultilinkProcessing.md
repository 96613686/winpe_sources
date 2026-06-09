# DoMultilinkProcessing

- ea: `0x14002c9e0`
- end: `0x14002cf91`
- name: `DoMultilinkProcessing`
- size: `1457`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x140032ba0`

## callees

- `0x140005750`
- `0x14000a290`
- `0x14000a648`
- `0x14000a6e0`
- `0x14000c67c`
- `0x14001043c`
- `0x1400104a4`
- `0x140010518`
- `0x140016400`
- `0x14002c9e0`
- `0x14002d170`
- `0x14002d324`
- `0x14002d7dc`
- `0x14002dc9c`

## pseudocode

```c
__int64 __fastcall DoMultilinkProcessing(__int64 a1, __int64 a2)
{
  _DWORD *v2; // rbx
  __int64 v3; // r14
  int v4; // edx
  unsigned __int8 *v7; // rcx
  __int64 v8; // r15
  int v9; // r8d
  unsigned int v10; // r9d
  unsigned int v11; // ebp
  unsigned __int8 *v12; // rax
  int v13; // ecx
  __int64 *v14; // r13
  __int64 *v15; // r10
  __int64 v16; // r9
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  _DWORD *v19; // r11
  __int64 v20; // r8
  __int64 RecvDesc; // rax
  __int64 *v22; // rax
  PDEVICE_OBJECT v23; // rcx
  __int64 v24; // rdx
  __int64 *i; // r9
  __int64 *v26; // rax
  int v27; // ecx
  int v28; // ecx
  unsigned int v29; // r8d
  unsigned int v30; // r9d
  __int64 *v31; // [rsp+40h] [rbp-58h]
  _DWORD *v32; // [rsp+48h] [rbp-50h]
  int v33; // [rsp+A0h] [rbp+8h]
  unsigned int v34; // [rsp+A8h] [rbp+10h]
  unsigned __int8 *Src; // [rsp+B0h] [rbp+18h]
  __int64 v36; // [rsp+B8h] [rbp+20h]

  v2 = *(_DWORD **)(a1 + 80);
  v3 = a2;
  v4 = *(_DWORD *)(a2 + 72);
  if ( v4 < 2 )
  {
    ++*(_DWORD *)(a1 + 612);
    ++v2[411];
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_52604c4400d53a16edd48a543f00e082_Traceguids);
    }
    return 3221225473LL;
  }
  v7 = *(unsigned __int8 **)(v3 + 64);
  v8 = 0;
  v9 = v2[18];
  v10 = *v7;
  if ( (v9 & 0x20) != 0 )
  {
    v11 = v7[1] | ((v10 & 0xF) << 8);
    if ( (v9 & 0x40) != 0 )
      v8 = (v10 >> 4) & 3;
    v12 = v7 + 2;
    v13 = v4 - 2;
  }
  else
  {
    if ( v4 < 4 )
    {
LABEL_12:
      ++*(_DWORD *)(a1 + 612);
      ++v2[411];
      return 3221225473LL;
    }
    v11 = v7[3] | ((v7[2] | (v7[1] << 8)) << 8);
    if ( (v9 & 0x40) != 0 )
      v8 = (v10 >> 2) & 0xF;
    v12 = v7 + 4;
    v13 = v4 - 4;
  }
  v33 = v13;
  Src = v12;
  if ( (_DWORD)v8 )
    goto LABEL_12;
  v14 = (__int64 *)&v2[8 * v8 + 52];
  if ( v13 <= 0 )
  {
    ++*(_DWORD *)(a1 + 612);
    ++*(_DWORD *)(a1 + 8 * v8 + 104);
    ++v2[411];
    ++*((_DWORD *)v14 + 9);
    return 3221225473LL;
  }
  v15 = (__int64 *)v14[3];
  v16 = (unsigned __int8)v10 & 0xC0;
  v34 = v16;
  v31 = v15;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_DDDq(
      WPP_GLOBAL_Control->AttachedDevice,
      2048,
      WPP_GLOBAL_Control,
      v11,
      v16,
      *((_DWORD *)v15 + 10),
      *(_QWORD *)(a1 + 40));
    v16 = v34;
    v15 = v31;
  }
  if ( v11 == *(_DWORD *)(a1 + 8 * v8 + 100) || ((v11 - *(_DWORD *)(a1 + 8 * v8 + 100)) & v2[63]) == 0 )
  {
    v19 = v15 + 5;
    v32 = v15 + 5;
    v20 = v11 - *((_DWORD *)v15 + 10);
    if ( v11 == *((_DWORD *)v15 + 10) || ((unsigned int)v20 & v2[63]) == 0 )
    {
      if ( (*(_DWORD *)(v3 + 48) & 1) == 0 )
      {
        RecvDesc = NdisWanAllocateRecvDesc(&WPP_GLOBAL_Control, 2048, v20, v16);
        v36 = RecvDesc;
        if ( !RecvDesc )
          goto LABEL_46;
        memmove(*(void **)(RecvDesc + 64), Src, v33);
        Src = *(unsigned __int8 **)(v36 + 64);
        NdisWanFreeRecvDesc(v3);
        v15 = v31;
        v19 = v32;
        v3 = v36;
      }
      *(_DWORD *)(v3 + 44) |= v34;
      *(_DWORD *)(a1 + 8 * v8 + 100) = v11;
      *(_DWORD *)(v3 + 40) = v11;
      *(_QWORD *)(v3 + 64) = Src;
      *(_DWORD *)(v3 + 72) = v33;
      if ( v11 == *v19 )
      {
        *(_QWORD *)(v3 + 8) = v15[1];
        v22 = (__int64 *)*v15;
        *(_QWORD *)v3 = *v15;
        v22[1] = v3;
        **(_QWORD **)(v3 + 8) = v3;
        FindHoleInRecvList(v2, v3, 0, v16);
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v24 = 41;
LABEL_67:
          WPP_SF_(v23->AttachedDevice, v24, WPP_52604c4400d53a16edd48a543f00e082_Traceguids);
        }
      }
      else
      {
        for ( i = (__int64 *)*v15; i != v14; i = (__int64 *)*i )
        {
          if ( (v2[62] & (v11 - *((_DWORD *)v15 + 10))) < (v2[62]
                                                         & (unsigned int)(*((_DWORD *)i + 10) - *((_DWORD *)v15 + 10))) )
          {
            *(_QWORD *)v3 = i;
            *(_QWORD *)(v3 + 8) = v15;
            i[1] = v3;
            *v15 = v3;
            v23 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              v24 = 42;
              goto LABEL_67;
            }
            goto LABEL_68;
          }
          v15 = i;
        }
        v26 = (__int64 *)v14[1];
        if ( (__int64 *)*v26 != v14 )
          __fastfail(3u);
        *(_QWORD *)v3 = v14;
        *(_QWORD *)(v3 + 8) = v26;
        *v26 = v3;
        v14[1] = v3;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v24 = 43;
          goto LABEL_67;
        }
      }
LABEL_68:
      ++*((_DWORD *)v14 + 4);
      UpdateMinRecvSeqNumber(v2, 0);
      TryToAssembleFrame(v2);
      v27 = *((_DWORD *)v14 + 8) - *v32;
      if ( v27 && (v27 & v2[63]) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_DDq(WPP_GLOBAL_Control->AttachedDevice);
        }
        do
        {
          FlushRecvDescWindow(v2);
          v28 = *((_DWORD *)v14 + 8) - *v32;
        }
        while ( v28 && (v28 & v2[63]) == 0 );
      }
      v29 = gMaxRecvDescCount + v2[16];
      v30 = *((_DWORD *)v14 + 4);
      if ( v30 > v29 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_qdd(
            WPP_GLOBAL_Control->AttachedDevice,
            45,
            WPP_52604c4400d53a16edd48a543f00e082_Traceguids,
            v2,
            v30,
            v29);
        }
        FlushRecvDescWindow(v2);
      }
      return 259;
    }
    ++*(_DWORD *)(a1 + 612);
    ++*(_DWORD *)(a1 + 8 * v8 + 104);
    ++v2[411];
    ++*((_DWORD *)v14 + 9);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_46;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_DDD(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_GLOBAL_Control, v11, v16, *v19);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    {
      goto LABEL_46;
    }
    v18 = 40;
  }
  else
  {
    ++*(_DWORD *)(a1 + 612);
    ++*(_DWORD *)(a1 + 8 * v8 + 104);
    ++v2[411];
    ++*((_DWORD *)v14 + 9);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_46;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_DDD(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_GLOBAL_Control, v11, v16, *(_DWORD *)(a1 + 8 * v8 + 100));
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    {
      goto LABEL_46;
    }
    v18 = 38;
  }
  WPP_SF_q(v17->AttachedDevice, v18, WPP_52604c4400d53a16edd48a543f00e082_Traceguids, v3);
LABEL_46:
  NdisWanFreeRecvDesc(v3);
  return 259;
}

```

## disassembly

```asm
0x14002c9e0  push    rbx
0x14002c9e2  push    rbp
0x14002c9e3  push    rsi
0x14002c9e4  push    rdi
0x14002c9e5  push    r12
0x14002c9e7  push    r13
0x14002c9e9  push    r14
0x14002c9eb  push    r15
0x14002c9ed  sub     rsp, 58h
0x14002c9f1  mov     rbx, [rcx+50h]
0x14002c9f5  mov     r14, rdx
0x14002c9f8  mov     edx, [rdx+48h]
0x14002c9fb  mov     rdi, rcx
0x14002c9fe  cmp     edx, 2
0x14002ca01  jge     short loc_14002CA53
0x14002ca03  mov     esi, 1
0x14002ca08  add     [rcx+264h], esi
0x14002ca0e  add     [rbx+66Ch], esi
0x14002ca14  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ca1b  lea     rdi, WPP_GLOBAL_Control
0x14002ca22  cmp     rcx, rdi
0x14002ca25  jz      short loc_14002CA49
0x14002ca27  test    dword ptr [rcx+2Ch], 800h
0x14002ca2e  jz      short loc_14002CA49
0x14002ca30  cmp     byte ptr [rcx+29h], 3
0x14002ca34  jb      short loc_14002CA49
0x14002ca36  mov     rcx, [rcx+18h]
0x14002ca3a  lea     edx, [rsi+22h]
0x14002ca3d  lea     r8, WPP_52604c4400d53a16edd48a543f00e082_Traceguids
0x14002ca44  call    WPP_SF_
0x14002ca49  mov     eax, 0C0000001h
0x14002ca4e  jmp     loc_14002CF7F
0x14002ca53  mov     rcx, [r14+40h]
0x14002ca57  xor     r15d, r15d
0x14002ca5a  mov     r8d, [rbx+48h]
0x14002ca5e  movzx   r9d, byte ptr [rcx]
0x14002ca62  test    r8b, 20h
0x14002ca66  jz      short loc_14002CA91
0x14002ca68  movzx   eax, byte ptr [rcx+1]
0x14002ca6c  mov     ebp, r9d
0x14002ca6f  and     ebp, 0Fh
0x14002ca72  shl     ebp, 8
0x14002ca75  or      ebp, eax
0x14002ca77  test    r8b, 40h
0x14002ca7b  jz      short loc_14002CA88
0x14002ca7d  mov     r15d, r9d
0x14002ca80  shr     r15d, 4
0x14002ca84  and     r15d, 3
0x14002ca88  lea     rax, [rcx+2]
0x14002ca8c  lea     ecx, [rdx-2]
0x14002ca8f  jmp     short loc_14002CAD7
0x14002ca91  cmp     edx, 4
0x14002ca94  jge     short loc_14002CAA9
0x14002ca96  mov     esi, 1
0x14002ca9b  add     [rdi+264h], esi
0x14002caa1  add     [rbx+66Ch], esi
0x14002caa7  jmp     short loc_14002CA49
0x14002caa9  movzx   eax, byte ptr [rcx+2]
0x14002caad  movzx   ebp, byte ptr [rcx+1]
0x14002cab1  shl     ebp, 8
0x14002cab4  or      ebp, eax
0x14002cab6  movzx   eax, byte ptr [rcx+3]
0x14002caba  shl     ebp, 8
0x14002cabd  or      ebp, eax
0x14002cabf  test    r8b, 40h
0x14002cac3  jz      short loc_14002CAD0
0x14002cac5  mov     r15d, r9d
0x14002cac8  shr     r15d, 2
0x14002cacc  and     r15d, 0Fh
0x14002cad0  lea     rax, [rcx+4]
0x14002cad4  lea     ecx, [rdx-4]
0x14002cad7  mov     esi, 1
0x14002cadc  mov     [rsp+98h+arg_0], ecx
0x14002cae3  mov     [rsp+98h+Src], rax
0x14002caeb  cmp     r15d, esi
0x14002caee  jnb     short loc_14002CA9B
0x14002caf0  mov     r12d, r15d
0x14002caf3  lea     r13, ds:1Ah[r15*4]
0x14002cafb  add     r13, r12
0x14002cafe  lea     r13, [rbx+r13*8]
0x14002cb02  test    ecx, ecx
0x14002cb04  jg      short loc_14002CB20
0x14002cb06  add     [rdi+264h], esi
0x14002cb0c  add     [rdi+r15*8+68h], esi
0x14002cb11  add     [rbx+66Ch], esi
0x14002cb17  add     [r13+24h], esi
0x14002cb1b  jmp     loc_14002CA49
0x14002cb20  mov     r10, [r13+18h]
0x14002cb24  and     r9d, 0C0h
0x14002cb2b  mov     [rsp+98h+arg_8], r9d
0x14002cb33  mov     [rsp+98h+var_58], r10
0x14002cb38  mov     r8, cs:WPP_GLOBAL_Control
0x14002cb3f  lea     rcx, WPP_GLOBAL_Control
0x14002cb46  mov     edx, 800h
0x14002cb4b  cmp     r8, rcx
0x14002cb4e  jz      short loc_14002CB98
0x14002cb50  test    [r8+2Ch], edx
0x14002cb54  jz      short loc_14002CB98
0x14002cb56  cmp     byte ptr [r8+29h], 4
0x14002cb5b  jb      short loc_14002CB98
0x14002cb5d  mov     rax, [rdi+28h]
0x14002cb61  mov     rcx, [r8+18h]
0x14002cb65  mov     [rsp+98h+var_68], rax
0x14002cb6a  mov     eax, [r10+28h]
0x14002cb6e  mov     dword ptr [rsp+98h+var_70], eax
0x14002cb72  mov     [rsp+98h+var_78], r9d
0x14002cb77  mov     r9d, ebp
0x14002cb7a  call    WPP_SF_DDDq
0x14002cb7f  mov     r9d, [rsp+98h+arg_8]
0x14002cb87  lea     rcx, WPP_GLOBAL_Control
0x14002cb8e  mov     r10, [rsp+98h+var_58]
0x14002cb93  mov     edx, 800h
0x14002cb98  mov     r8d, ebp
0x14002cb9b  sub     r8d, [rdi+r15*8+64h]
0x14002cba0  jz      loc_14002CC3C
0x14002cba6  test    [rbx+0FCh], r8d
0x14002cbad  jz      loc_14002CC3C
0x14002cbb3  add     [rdi+264h], esi
0x14002cbb9  add     [rdi+r15*8+68h], esi
0x14002cbbe  add     [rbx+66Ch], esi
0x14002cbc4  add     [r13+24h], esi
0x14002cbc8  mov     r8, cs:WPP_GLOBAL_Control
0x14002cbcf  cmp     r8, rcx
0x14002cbd2  jz      loc_14002CD04
0x14002cbd8  test    [r8+2Ch], edx
0x14002cbdc  jz      short loc_14002CC04
0x14002cbde  cmp     byte ptr [r8+29h], 3
0x14002cbe3  jb      short loc_14002CC04
0x14002cbe5  mov     eax, [rdi+r15*8+64h]
0x14002cbea  mov     edx, 25h ; '%'
0x14002cbef  mov     rcx, [r8+18h]
0x14002cbf3  mov     dword ptr [rsp+98h+var_70], eax
0x14002cbf7  mov     [rsp+98h+var_78], r9d
0x14002cbfc  mov     r9d, ebp
0x14002cbff  call    WPP_SF_DDD
0x14002cc04  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cc0b  lea     rdi, WPP_GLOBAL_Control
0x14002cc12  cmp     rcx, rdi
0x14002cc15  jz      loc_14002CD04
0x14002cc1b  test    dword ptr [rcx+2Ch], 8000h
0x14002cc22  jz      loc_14002CD04
0x14002cc28  cmp     byte ptr [rcx+29h], 5
0x14002cc2c  jb      loc_14002CD04
0x14002cc32  mov     edx, 26h ; '&'
0x14002cc37  jmp     loc_14002CCD4
0x14002cc3c  lea     r11, [r10+28h]
0x14002cc40  mov     r8d, ebp
0x14002cc43  mov     [rsp+98h+var_50], r11
0x14002cc48  sub     r8d, [r11]
0x14002cc4b  jz      loc_14002CCE9
0x14002cc51  test    [rbx+0FCh], r8d
0x14002cc58  jz      loc_14002CCE9
0x14002cc5e  add     [rdi+264h], esi
0x14002cc64  add     [rdi+r15*8+68h], esi
0x14002cc69  add     [rbx+66Ch], esi
0x14002cc6f  add     [r13+24h], esi
0x14002cc73  mov     r8, cs:WPP_GLOBAL_Control
0x14002cc7a  cmp     r8, rcx
0x14002cc7d  jz      loc_14002CD04
0x14002cc83  test    [r8+2Ch], edx
0x14002cc87  jz      short loc_14002CCAD
0x14002cc89  cmp     byte ptr [r8+29h], 3
0x14002cc8e  jb      short loc_14002CCAD
0x14002cc90  mov     eax, [r11]
0x14002cc93  mov     edx, 27h ; '''
0x14002cc98  mov     rcx, [r8+18h]
0x14002cc9c  mov     dword ptr [rsp+98h+var_70], eax
0x14002cca0  mov     [rsp+98h+var_78], r9d
0x14002cca5  mov     r9d, ebp
0x14002cca8  call    WPP_SF_DDD
0x14002ccad  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ccb4  lea     rdi, WPP_GLOBAL_Control
0x14002ccbb  cmp     rcx, rdi
0x14002ccbe  jz      short loc_14002CD04
0x14002ccc0  test    dword ptr [rcx+2Ch], 8000h
0x14002ccc7  jz      short loc_14002CD04
0x14002ccc9  cmp     byte ptr [rcx+29h], 5
0x14002cccd  jb      short loc_14002CD04
0x14002cccf  mov     edx, 28h ; '('
0x14002ccd4  mov     rcx, [rcx+18h]
0x14002ccd8  lea     r8, WPP_52604c4400d53a16edd48a543f00e082_Traceguids
0x14002ccdf  mov     r9, r14
0x14002cce2  call    WPP_SF_q
0x14002cce7  jmp     short loc_14002CD04
0x14002cce9  mov     eax, [r14+30h]
0x14002cced  test    sil, al
0x14002ccf0  jnz     short loc_14002CD58
0x14002ccf2  call    NdisWanAllocateRecvDesc
0x14002ccf7  mov     [rsp+98h+arg_18], rax
0x14002ccff  test    rax, rax
0x14002cd02  jnz     short loc_14002CD11
0x14002cd04  mov     rcx, r14
0x14002cd07  call    NdisWanFreeRecvDesc
0x14002cd0c  jmp     loc_14002CF7A
0x14002cd11  movsxd  r8, [rsp+98h+arg_0]; Size
0x14002cd19  mov     rdx, [rsp+98h+Src]; Src
0x14002cd21  mov     rcx, [rax+40h]; void *
0x14002cd25  call    memmove
0x14002cd2a  mov     rax, [rsp+98h+arg_18]
0x14002cd32  mov     rcx, r14
0x14002cd35  mov     rax, [rax+40h]
0x14002cd39  mov     [rsp+98h+Src], rax
0x14002cd41  call    NdisWanFreeRecvDesc
0x14002cd46  mov     r10, [rsp+98h+var_58]
0x14002cd4b  mov     r11, [rsp+98h+var_50]
0x14002cd50  mov     r14, [rsp+98h+arg_18]
0x14002cd58  mov     eax, [rsp+98h+arg_8]
0x14002cd5f  or      [r14+2Ch], eax
0x14002cd63  mov     rcx, [rsp+98h+Src]
0x14002cd6b  mov     eax, [rsp+98h+arg_0]
0x14002cd72  mov     [rdi+r15*8+64h], ebp
0x14002cd77  mov     [r14+28h], ebp
0x14002cd7b  mov     [r14+40h], rcx
0x14002cd7f  mov     [r14+48h], eax
0x14002cd83  cmp     ebp, [r11]
0x14002cd86  jnz     short loc_14002CDE7
0x14002cd88  mov     rax, [r10+8]
0x14002cd8c  mov     r8d, r15d
0x14002cd8f  mov     [r14+8], rax
0x14002cd93  mov     rdx, r14
0x14002cd96  mov     rax, [r10]
0x14002cd99  mov     rcx, rbx
0x14002cd9c  mov     [r14], rax
0x14002cd9f  mov     [rax+8], r14
0x14002cda3  mov     rax, [r14+8]
0x14002cda7  mov     [rax], r14
0x14002cdaa  call    FindHoleInRecvList
0x14002cdaf  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cdb6  lea     rdi, WPP_GLOBAL_Control
0x14002cdbd  cmp     rcx, rdi
0x14002cdc0  jz      loc_14002CEA2
0x14002cdc6  test    dword ptr [rcx+2Ch], 800h
0x14002cdcd  jz      loc_14002CEA2
0x14002cdd3  cmp     byte ptr [rcx+29h], 4
0x14002cdd7  jb      loc_14002CEA2
0x14002cddd  mov     edx, 29h ; ')'
0x14002cde2  jmp     loc_14002CE92
0x14002cde7  mov     r9, [r10]
0x14002cdea  cmp     r9, r13
0x14002cded  jz      short loc_14002CE4D
0x14002cdef  mov     ecx, [r10+28h]
0x14002cdf3  mov     eax, ebp
0x14002cdf5  mov     r8d, [rbx+0F8h]
0x14002cdfc  sub     eax, ecx
0x14002cdfe  mov     edx, [r9+28h]
0x14002ce02  and     eax, r8d
0x14002ce05  sub     edx, ecx
0x14002ce07  and     edx, r8d
0x14002ce0a  cmp     eax, edx
0x14002ce0c  jb      short loc_14002CE16
0x14002ce0e  mov     r10, r9
0x14002ce11  mov     r9, [r9]
0x14002ce14  jmp     short loc_14002CDEA
0x14002ce16  mov     [r14], r9
0x14002ce19  mov     [r14+8], r10
0x14002ce1d  mov     [r9+8], r14
0x14002ce21  mov     [r10], r14
0x14002ce24  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ce2b  lea     rdi, WPP_GLOBAL_Control
0x14002ce32  cmp     rcx, rdi
0x14002ce35  jz      short loc_14002CEA2
0x14002ce37  test    dword ptr [rcx+2Ch], 800h
0x14002ce3e  jz      short loc_14002CEA2
0x14002ce40  cmp     byte ptr [rcx+29h], 4
0x14002ce44  jb      short loc_14002CEA2
0x14002ce46  mov     edx, 2Ah ; '*'
0x14002ce4b  jmp     short loc_14002CE92
0x14002ce4d  mov     rax, [r13+8]
0x14002ce51  cmp     [rax], r13
0x14002ce54  jz      short loc_14002CE5D
0x14002ce56  mov     ecx, 3
0x14002ce5b  int     29h; Win8: RtlFailFast(ecx)
0x14002ce5d  mov     [r14], r13
0x14002ce60  mov     [r14+8], rax
0x14002ce64  mov     [rax], r14
0x14002ce67  mov     [r13+8], r14
0x14002ce6b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ce72  lea     rdi, WPP_GLOBAL_Control
0x14002ce79  cmp     rcx, rdi
0x14002ce7c  jz      short loc_14002CEA2
0x14002ce7e  test    dword ptr [rcx+2Ch], 800h
0x14002ce85  jz      short loc_14002CEA2
0x14002ce87  cmp     byte ptr [rcx+29h], 4
0x14002ce8b  jb      short loc_14002CEA2
0x14002ce8d  mov     edx, 2Bh ; '+'
0x14002ce92  mov     rcx, [rcx+18h]
0x14002ce96  lea     r8, WPP_52604c4400d53a16edd48a543f00e082_Traceguids
0x14002ce9d  call    WPP_SF_
0x14002cea2  add     [r13+10h], esi
0x14002cea6  mov     edx, r15d
0x14002cea9  mov     rcx, rbx
0x14002ceac  call    UpdateMinRecvSeqNumber
0x14002ceb1  mov     edx, r15d
0x14002ceb4  mov     rcx, rbx; PVOID
0x14002ceb7  call    TryToAssembleFrame
0x14002cebc  mov     rsi, [rsp+98h+var_50]
0x14002cec1  mov     r9d, [r13+20h]
0x14002cec5  mov     ecx, r9d
0x14002cec8  mov     edx, [rsi]
0x14002ceca  sub     ecx, edx
  ... truncated ...
```
