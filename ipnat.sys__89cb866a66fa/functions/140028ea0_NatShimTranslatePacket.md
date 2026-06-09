# NatShimTranslatePacket

- ea: `0x140028ea0`
- end: `0x14002921c`
- name: `NatShimTranslatePacket`
- size: `892`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG DataOffsetDelta, char)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x140029850`
- `0x140029e50`
- `0x14002a440`
- `0x14002a9c0`
- `0x14002bc7c`

## callees

- `0x14000218c`
- `0x1400021bc`
- `0x140022320`
- `0x140028c0c`
- `0x140028d34`
- `0x140028ea0`
- `0x140029224`

## import_xrefs

- `NETIO!NetioAllocateMdl` at `0x140029031`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14002903d`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14002903d`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14002910c`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140029168`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400291bd`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14002910c`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140029168`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400291bd`

## pseudocode

```c
__int64 __fastcall NatShimTranslatePacket(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        ULONG DataOffsetDelta,
        char a6)
{
  char v8; // r12
  ULONG v9; // ebx
  struct _NET_BUFFER *v10; // rcx
  ULONG CurrentMdlOffset; // eax
  _QWORD *v12; // rsi
  unsigned int v13; // edi
  bool v14; // r15
  __int64 v15; // rcx
  struct _NET_BUFFER *v16; // rcx
  ULONG v17; // edx
  NDIS_STATUS v18; // eax
  struct _NET_BUFFER *v19; // rcx
  ULONG v20; // edx
  PDEVICE_OBJECT v21; // rcx
  unsigned __int16 v22; // dx
  struct _NET_BUFFER *v23; // rcx
  ULONG v24; // edx
  __int64 v26; // [rsp+40h] [rbp-10h] BYREF
  _DWORD *Buffer; // [rsp+48h] [rbp-8h] BYREF
  int v28; // [rsp+98h] [rbp+48h] BYREF
  char v29; // [rsp+A0h] [rbp+50h] BYREF

  v29 = a3;
  v28 = a2;
  v8 = a6;
  v9 = DataOffsetDelta;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_ddddc(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, a2, (unsigned __int8)a3, DataOffsetDelta, a6);
  }
  Buffer = 0;
  v26 = 0;
  if ( v9 )
  {
    v10 = *(struct _NET_BUFFER **)(a4 + 8);
    CurrentMdlOffset = v10->CurrentMdlOffset;
    if ( CurrentMdlOffset < v9 )
    {
      v18 = NdisRetreatNetBufferDataStart(v10, v9, 0, NetioAllocateMdl);
      if ( v18 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_d(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0xBu,
              (__int64)WPP_d38067f78364399e8ac7d4e5932d9d3a_Traceguids,
              v18);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
          {
            WPP_SF_(
              (__int64)WPP_GLOBAL_Control->AttachedDevice,
              0xCu,
              (__int64)WPP_d38067f78364399e8ac7d4e5932d9d3a_Traceguids);
          }
        }
        return 1;
      }
    }
    else
    {
      v10->DataOffset -= v9;
      v10->DataLength += v9;
      v10->CurrentMdlOffset = CurrentMdlOffset - v9;
    }
  }
  v12 = *(_QWORD **)(a4 + 8);
  v13 = 0;
  v14 = 0;
  if ( !v12 )
    goto LABEL_23;
  do
  {
    Buffer = NatShimAllocateBuffer((__int64)v12);
    v26 = 0;
    if ( !Buffer )
    {
      if ( v9 )
      {
        v23 = *(struct _NET_BUFFER **)(a4 + 8);
        v24 = v9 + v23->CurrentMdlOffset;
        if ( v24 >= *(_DWORD *)(v23->Link.Region + 40) )
        {
          NdisAdvanceNetBufferDataStart(v23, v9, 0, 0);
        }
        else
        {
          v23->DataOffset += v9;
          v23->DataLength -= v9;
          v23->CurrentMdlOffset = v24;
        }
      }
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v22 = 13;
        goto LABEL_55;
      }
      return 1;
    }
    v13 = NatTranslatePacket((unsigned int)&Buffer, a1, (unsigned int)&v28, (unsigned int)&v29, 0, 0, (__int64)&v26);
    if ( v13 == 1 )
    {
      if ( Buffer )
        NatShimFreeBuffer(Buffer);
      if ( v26 )
        NatShimFreeBuffer(v26);
      if ( v9 )
      {
        v19 = *(struct _NET_BUFFER **)(a4 + 8);
        v20 = v9 + v19->CurrentMdlOffset;
        if ( v20 >= *(_DWORD *)(v19->Link.Region + 40) )
        {
          NdisAdvanceNetBufferDataStart(v19, v9, 0, 0);
        }
        else
        {
          v19->DataOffset += v9;
          v19->DataLength -= v9;
          v19->CurrentMdlOffset = v20;
        }
      }
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
      {
        v22 = 14;
LABEL_55:
        WPP_SF_((__int64)v21->AttachedDevice, v22, (__int64)WPP_d38067f78364399e8ac7d4e5932d9d3a_Traceguids);
        return 1;
      }
      return 1;
    }
    v15 = v26;
    if ( !v14 )
      v14 = v26 != 0;
    if ( Buffer )
    {
      NatShimFreeBuffer(Buffer);
      v15 = v26;
    }
    if ( v15 )
      NatShimFreeBuffer(v15);
    v12 = (_QWORD *)*v12;
  }
  while ( v12 );
  if ( v14 )
  {
    if ( !v8 && a4 != -144 )
      *(_DWORD *)(a4 + 144) &= 0xFFFFFFF3;
    v13 = 3;
  }
LABEL_23:
  if ( v9 )
  {
    v16 = *(struct _NET_BUFFER **)(a4 + 8);
    v17 = v9 + v16->CurrentMdlOffset;
    if ( v17 >= *(_DWORD *)(v16->Link.Region + 40) )
    {
      NdisAdvanceNetBufferDataStart(v16, v9, 0, 0);
    }
    else
    {
      v16->DataOffset += v9;
      v16->DataLength -= v9;
      v16->CurrentMdlOffset = v17;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xFu,
      (__int64)WPP_d38067f78364399e8ac7d4e5932d9d3a_Traceguids,
      v13);
  }
  return v13;
}

```

## disassembly

```asm
0x140028ea0  mov     [rsp-38h+arg_0], rbx
0x140028ea5  mov     [rsp-38h+arg_10], r8b
0x140028eaa  mov     [rsp-38h+arg_8], edx
0x140028eae  push    rbp
0x140028eaf  push    rsi
0x140028eb0  push    rdi
0x140028eb1  push    r12
0x140028eb3  push    r13
0x140028eb5  push    r14
0x140028eb7  push    r15
0x140028eb9  mov     rbp, rsp
0x140028ebc  sub     rsp, 50h
0x140028ec0  mov     r14, r9
0x140028ec3  mov     r13d, ecx
0x140028ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x140028ecd  lea     rsi, WPP_GLOBAL_Control
0x140028ed4  mov     r12b, [rbp+arg_28]
0x140028ed8  mov     dil, 2
0x140028edb  mov     ebx, [rbp+DataOffsetDelta]
0x140028ede  cmp     rcx, rsi
0x140028ee1  jz      short loc_140028F12
0x140028ee3  mov     eax, [rcx+2Ch]
0x140028ee6  test    dil, al
0x140028ee9  jz      short loc_140028F12
0x140028eeb  cmp     byte ptr [rcx+29h], 6
0x140028eef  jb      short loc_140028F12
0x140028ef1  mov     rcx, [rcx+18h]
0x140028ef5  mov     r9d, r13d
0x140028ef8  mov     [rsp+50h+var_18], r12b
0x140028efd  movzx   eax, r8b
0x140028f01  mov     dword ptr [rsp+50h+var_20], ebx
0x140028f05  mov     [rsp+50h+var_28], eax
0x140028f09  mov     dword ptr [rsp+50h+var_30], edx
0x140028f0d  call    WPP_SF_ddddc
0x140028f12  mov     [rbp+var_8], 0
0x140028f1a  mov     r15d, 1
0x140028f20  mov     [rbp+var_10], 0
0x140028f28  test    ebx, ebx
0x140028f2a  jz      short loc_140028F46
0x140028f2c  mov     rcx, [r14+8]; NetBuffer
0x140028f30  mov     eax, [rcx+10h]
0x140028f33  cmp     eax, ebx
0x140028f35  jb      loc_140029031
0x140028f3b  sub     [rcx+28h], ebx
0x140028f3e  sub     eax, ebx
0x140028f40  add     [rcx+18h], ebx
0x140028f43  mov     [rcx+10h], eax
0x140028f46  mov     rsi, [r14+8]
0x140028f4a  xor     edi, edi
0x140028f4c  xor     r15b, r15b
0x140028f4f  test    rsi, rsi
0x140028f52  jz      loc_140029005
0x140028f58  mov     rcx, rsi
0x140028f5b  call    NatShimAllocateBuffer
0x140028f60  xor     ecx, ecx
0x140028f62  mov     [rbp+var_8], rax
0x140028f66  mov     [rbp+var_10], rcx
0x140028f6a  test    rax, rax
0x140028f6d  jz      loc_14002913F
0x140028f73  lea     rax, [rbp+var_10]
0x140028f77  mov     edx, r13d
0x140028f7a  mov     [rsp+50h+var_20], rax
0x140028f7f  lea     r9, [rbp+arg_10]
0x140028f83  mov     [rsp+50h+var_28], ecx
0x140028f87  lea     r8, [rbp+arg_8]
0x140028f8b  mov     [rsp+50h+var_30], rcx
0x140028f90  lea     rcx, [rbp+var_8]
0x140028f94  call    NatTranslatePacket
0x140028f99  mov     edi, eax
0x140028f9b  mov     eax, 1
0x140028fa0  cmp     edi, eax
0x140028fa2  jz      loc_1400290C7
0x140028fa8  mov     rcx, [rbp+var_10]
0x140028fac  test    r15b, r15b
0x140028faf  jnz     short loc_140028FBC
0x140028fb1  test    rcx, rcx
0x140028fb4  movzx   r15d, r15b
0x140028fb8  cmovnz  r15d, eax
0x140028fbc  mov     rax, [rbp+var_8]
0x140028fc0  test    rax, rax
0x140028fc3  jz      short loc_140028FD1
0x140028fc5  mov     rcx, rax
0x140028fc8  call    NatShimFreeBuffer
0x140028fcd  mov     rcx, [rbp+var_10]
0x140028fd1  test    rcx, rcx
0x140028fd4  jz      short loc_140028FDB
0x140028fd6  call    NatShimFreeBuffer
0x140028fdb  mov     rsi, [rsi]
0x140028fde  test    rsi, rsi
0x140028fe1  jnz     loc_140028F58
0x140028fe7  test    r15b, r15b
0x140028fea  jz      short loc_140029005
0x140028fec  test    r12b, r12b
0x140028fef  jnz     short loc_140029000
0x140028ff1  lea     rax, [r14+90h]
0x140028ff8  test    rax, rax
0x140028ffb  jz      short loc_140029000
0x140028ffd  and     dword ptr [rax], 0FFFFFFF3h
0x140029000  mov     edi, 3
0x140029005  test    ebx, ebx
0x140029007  jz      loc_1400291C9
0x14002900d  mov     rcx, [r14+8]; NetBuffer
0x140029011  mov     rax, [rcx+8]
0x140029015  mov     edx, [rcx+10h]
0x140029018  add     edx, ebx
0x14002901a  cmp     edx, [rax+28h]
0x14002901d  jnb     loc_1400291B5
0x140029023  add     [rcx+28h], ebx
0x140029026  sub     [rcx+18h], ebx
0x140029029  mov     [rcx+10h], edx
0x14002902c  jmp     loc_1400291C9
0x140029031  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x140029038  xor     r8d, r8d; DataBackFill
0x14002903b  mov     edx, ebx; DataOffsetDelta
0x14002903d  call    cs:__imp_NdisRetreatNetBufferDataStart
0x140029044  nop     dword ptr [rax+rax+00h]
0x140029049  test    eax, eax
0x14002904b  jns     loc_140028F46
0x140029051  mov     rcx, cs:WPP_GLOBAL_Control
0x140029058  cmp     rcx, rsi
0x14002905b  jz      loc_1400291B0
0x140029061  mov     edx, [rcx+2Ch]
0x140029064  test    dil, dl
0x140029067  jz      short loc_140029087
0x140029069  cmp     [rcx+29h], dil
0x14002906d  jb      short loc_140029087
0x14002906f  mov     rcx, [rcx+18h]
0x140029073  lea     r8, WPP_d38067f78364399e8ac7d4e5932d9d3a_Traceguids
0x14002907a  mov     edx, 0Bh
0x14002907f  mov     r9d, eax
0x140029082  call    WPP_SF_d
0x140029087  mov     rcx, cs:WPP_GLOBAL_Control
0x14002908e  cmp     rcx, rsi
0x140029091  jz      loc_1400291B0
0x140029097  mov     eax, [rcx+2Ch]
0x14002909a  test    dil, al
0x14002909d  jz      loc_1400291B0
0x1400290a3  cmp     byte ptr [rcx+29h], 6
0x1400290a7  jb      loc_1400291B0
0x1400290ad  mov     rcx, [rcx+18h]
0x1400290b1  lea     r8, WPP_d38067f78364399e8ac7d4e5932d9d3a_Traceguids
0x1400290b8  mov     edx, 0Ch
0x1400290bd  call    WPP_SF_
0x1400290c2  jmp     loc_1400291B0
0x1400290c7  mov     rcx, [rbp+var_8]
0x1400290cb  test    rcx, rcx
0x1400290ce  jz      short loc_1400290D5
0x1400290d0  call    NatShimFreeBuffer
0x1400290d5  mov     rcx, [rbp+var_10]
0x1400290d9  test    rcx, rcx
0x1400290dc  jz      short loc_1400290E3
0x1400290de  call    NatShimFreeBuffer
0x1400290e3  test    ebx, ebx
0x1400290e5  jz      short loc_140029118
0x1400290e7  mov     rcx, [r14+8]; NetBuffer
0x1400290eb  mov     rax, [rcx+8]
0x1400290ef  mov     edx, [rcx+10h]
0x1400290f2  add     edx, ebx
0x1400290f4  cmp     edx, [rax+28h]
0x1400290f7  jnb     short loc_140029104
0x1400290f9  add     [rcx+28h], ebx
0x1400290fc  sub     [rcx+18h], ebx
0x1400290ff  mov     [rcx+10h], edx
0x140029102  jmp     short loc_140029118
0x140029104  xor     r9d, r9d; FreeMdlHandler
0x140029107  xor     r8d, r8d; FreeMdl
0x14002910a  mov     edx, ebx; DataOffsetDelta
0x14002910c  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140029113  nop     dword ptr [rax+rax+00h]
0x140029118  mov     rcx, cs:WPP_GLOBAL_Control
0x14002911f  lea     rax, WPP_GLOBAL_Control
0x140029126  cmp     rcx, rax
0x140029129  jz      short loc_1400291AA
0x14002912b  mov     eax, [rcx+2Ch]
0x14002912e  test    al, 2
0x140029130  jz      short loc_1400291AA
0x140029132  cmp     byte ptr [rcx+29h], 6
0x140029136  jb      short loc_1400291AA
0x140029138  mov     edx, 0Eh
0x14002913d  jmp     short loc_14002919A
0x14002913f  test    ebx, ebx
0x140029141  jz      short loc_140029174
0x140029143  mov     rcx, [r14+8]; NetBuffer
0x140029147  mov     rax, [rcx+8]
0x14002914b  mov     edx, [rcx+10h]
0x14002914e  add     edx, ebx
0x140029150  cmp     edx, [rax+28h]
0x140029153  jnb     short loc_140029160
0x140029155  add     [rcx+28h], ebx
0x140029158  sub     [rcx+18h], ebx
0x14002915b  mov     [rcx+10h], edx
0x14002915e  jmp     short loc_140029174
0x140029160  xor     r9d, r9d; FreeMdlHandler
0x140029163  xor     r8d, r8d; FreeMdl
0x140029166  mov     edx, ebx; DataOffsetDelta
0x140029168  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14002916f  nop     dword ptr [rax+rax+00h]
0x140029174  mov     rcx, cs:WPP_GLOBAL_Control
0x14002917b  lea     rax, WPP_GLOBAL_Control
0x140029182  cmp     rcx, rax
0x140029185  jz      short loc_1400291AA
0x140029187  mov     edx, [rcx+2Ch]
0x14002918a  test    dl, 2
0x14002918d  jz      short loc_1400291AA
0x14002918f  cmp     byte ptr [rcx+29h], 6
0x140029193  jb      short loc_1400291AA
0x140029195  mov     edx, 0Dh
0x14002919a  mov     rcx, [rcx+18h]
0x14002919e  lea     r8, WPP_d38067f78364399e8ac7d4e5932d9d3a_Traceguids
0x1400291a5  call    WPP_SF_
0x1400291aa  mov     r15d, 1
0x1400291b0  mov     eax, r15d
0x1400291b3  jmp     short loc_140029203
0x1400291b5  xor     r9d, r9d; FreeMdlHandler
0x1400291b8  xor     r8d, r8d; FreeMdl
0x1400291bb  mov     edx, ebx; DataOffsetDelta
0x1400291bd  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x1400291c4  nop     dword ptr [rax+rax+00h]
0x1400291c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400291d0  lea     rax, WPP_GLOBAL_Control
0x1400291d7  cmp     rcx, rax
0x1400291da  jz      short loc_140029201
0x1400291dc  mov     eax, [rcx+2Ch]
0x1400291df  test    al, 2
0x1400291e1  jz      short loc_140029201
0x1400291e3  cmp     byte ptr [rcx+29h], 6
0x1400291e7  jb      short loc_140029201
0x1400291e9  mov     rcx, [rcx+18h]
0x1400291ed  lea     r8, WPP_d38067f78364399e8ac7d4e5932d9d3a_Traceguids
0x1400291f4  mov     edx, 0Fh
0x1400291f9  mov     r9d, edi
0x1400291fc  call    WPP_SF_d
0x140029201  mov     eax, edi
0x140029203  mov     rbx, [rsp+50h+arg_0]
0x14002920b  add     rsp, 50h
0x14002920f  pop     r15
0x140029211  pop     r14
0x140029213  pop     r13
0x140029215  pop     r12
0x140029217  pop     rdi
0x140029218  pop     rsi
0x140029219  pop     rbp
0x14002921a  retn
```
