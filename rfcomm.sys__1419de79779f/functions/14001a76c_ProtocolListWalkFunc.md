# ProtocolListWalkFunc

- ea: `0x14001a76c`
- end: `0x14001aa0f`
- name: `ProtocolListWalkFunc`
- size: `675`
- prototype: `__int64 __fastcall(void *Buf1)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140034e38`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x14001a76c`
- `0x140020260`
- `0x1400345b0`
- `0x1400345c0`
- `0x1400345cc`
- `0x140034a40`
- `0x140034a50`
- `0x140034a5c`

## pseudocode

```c
__int64 __fastcall ProtocolListWalkFunc(_BYTE *Buf1, unsigned __int8 a2, unsigned int a3, unsigned __int8 *a4)
{
  size_t v5; // rbp
  _DWORD *v8; // rdx
  int v10; // eax
  int v11; // edx
  int v12; // r9d
  int v13; // edx
  int v14; // ebp
  int v15; // ebp
  unsigned int *v16; // rdx
  int v17; // eax
  int v18; // r9d
  unsigned __int16 *v19; // rdx
  int v20; // r8d
  int v21; // [rsp+28h] [rbp-50h]
  _QWORD Buf2[9]; // [rsp+30h] [rbp-48h] BYREF

  v5 = a3;
  LODWORD(v8) = a2 - 1;
  if ( !(_DWORD)v8 || (LODWORD(v8) = (_DWORD)v8 - 1, !(_DWORD)v8) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        4,
        26,
        (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
    if ( !Buf1[16] )
      return 0;
    Buf1[17] = 1;
    v14 = v5 - 1;
    if ( v14 )
    {
      v15 = v14 - 1;
      if ( !v15 )
      {
        SdpRetrieveUint16(a4, Buf1 + 20);
        v20 = (unsigned __int16)SdpByteSwapUint16(*v19);
        *v8 = v20;
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return 3221225473LL;
        v18 = 28;
        v21 = v20;
LABEL_37:
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v8,
          4,
          v18,
          (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids,
          v21);
        return 3221225473LL;
      }
      if ( v15 != 2 )
      {
        Buf1[17] = 0;
        return 3221225473LL;
      }
      SdpRetrieveUint32(a4, Buf1 + 20);
      v17 = SdpByteSwapUint32(*v16);
      *v8 = v17;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 3221225473LL;
      v18 = 29;
    }
    else
    {
      v17 = *a4;
      *((_DWORD *)Buf1 + 5) = v17;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return 3221225473LL;
      v18 = 27;
    }
    v21 = v17;
    goto LABEL_37;
  }
  if ( (_DWORD)v8 != 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v8,
        4,
        30,
        (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids,
        a2);
    return 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      1,
      4,
      22,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
  if ( !Buf1[16] )
  {
    if ( (_DWORD)v5 == 2 )
    {
      SdpRetrieveUint16(a4, Buf2);
      LOWORD(v10) = SdpByteSwapUint16(LOWORD(Buf2[0]));
      LOWORD(Buf2[0]) = v10;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_19;
      v10 = (unsigned __int16)v10;
      v12 = 23;
    }
    else
    {
      if ( (_DWORD)v5 != 4 )
      {
        if ( (_DWORD)v5 == 16 )
        {
          SdpRetrieveUuid128(a4, Buf2);
          SdpByteSwapUuid128(Buf2, Buf2);
        }
        goto LABEL_19;
      }
      SdpRetrieveUint32(a4, Buf2);
      v10 = SdpByteSwapUint32(LODWORD(Buf2[0]));
      LODWORD(Buf2[0]) = v10;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_19:
        if ( !memcmp(Buf1, Buf2, v5) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v13,
              4,
              25,
              (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids);
          Buf1[16] = 1;
        }
        return 0;
      }
      v10 = (unsigned __int16)v10;
      v12 = 24;
    }
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      4,
      v12,
      (__int64)&WPP_3313475e708830025d331cff5c1f0c33_Traceguids,
      v10,
      Buf2[0]);
    goto LABEL_19;
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x14001a76c  push    rbx
0x14001a76e  push    rbp
0x14001a76f  push    rsi
0x14001a770  push    rdi
0x14001a771  push    r14
0x14001a773  push    r15
0x14001a775  sub     rsp, 48h
0x14001a779  mov     r14, rcx
0x14001a77c  mov     ebp, r8d
0x14001a77f  movzx   ecx, dl
0x14001a782  mov     r15, r9
0x14001a785  mov     edx, ecx
0x14001a787  sub     edx, 1
0x14001a78a  jz      loc_14001A91A
0x14001a790  sub     edx, 1
0x14001a793  jz      loc_14001A91A
0x14001a799  cmp     edx, 1
0x14001a79c  jz      short loc_14001A7E8
0x14001a79e  lea     rbx, WPP_RECORDER_INITIALIZED
0x14001a7a5  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001a7ac  jz      short loc_14001A7D8
0x14001a7ae  mov     [rsp+78h+var_50], ecx
0x14001a7b2  lea     rsi, WPP_3313475e708830025d331cff5c1f0c33_Traceguids
0x14001a7b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a7c0  mov     r9d, 1Eh
0x14001a7c6  mov     [rsp+78h+var_58], rsi
0x14001a7cb  mov     rcx, [rcx+40h]
0x14001a7cf  lea     r8d, [r9-1Ah]
0x14001a7d3  call    WPP_RECORDER_SF_d
0x14001a7d8  xor     eax, eax
0x14001a7da  add     rsp, 48h
0x14001a7de  pop     r15
0x14001a7e0  pop     r14
0x14001a7e2  pop     rdi
0x14001a7e3  pop     rsi
0x14001a7e4  pop     rbp
0x14001a7e5  pop     rbx
0x14001a7e6  retn
0x14001a7e8  lea     rbx, WPP_RECORDER_INITIALIZED
0x14001a7ef  mov     edi, 4
0x14001a7f4  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001a7fb  lea     rsi, WPP_3313475e708830025d331cff5c1f0c33_Traceguids
0x14001a802  jz      short loc_14001A820
0x14001a804  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a80b  lea     r9d, [rdi+12h]
0x14001a80f  mov     r8d, edi
0x14001a812  mov     [rsp+78h+var_58], rsi
0x14001a817  mov     rcx, [rcx+40h]
0x14001a81b  call    WPP_RECORDER_SF_
0x14001a820  cmp     byte ptr [r14+10h], 0
0x14001a825  jnz     loc_14001AA05
0x14001a82b  cmp     ebp, 2
0x14001a82e  jz      short loc_14001A889
0x14001a830  cmp     ebp, edi
0x14001a832  jz      short loc_14001A85B
0x14001a834  cmp     ebp, 10h
0x14001a837  jnz     loc_14001A8D3
0x14001a83d  lea     rdx, [rsp+78h+Buf2]
0x14001a842  mov     rcx, r15
0x14001a845  call    SdpRetrieveUuid128
0x14001a84a  lea     rdx, [rsp+78h+Buf2]
0x14001a84f  lea     rcx, [rsp+78h+Buf2]
0x14001a854  call    SdpByteSwapUuid128
0x14001a859  jmp     short loc_14001A8D3
0x14001a85b  lea     rdx, [rsp+78h+Buf2]
0x14001a860  mov     rcx, r15
0x14001a863  call    SdpRetrieveUint32
0x14001a868  mov     ecx, [rsp+78h+Buf2]
0x14001a86c  call    SdpByteSwapUint32
0x14001a871  mov     [rsp+78h+Buf2], eax
0x14001a875  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001a87c  jz      short loc_14001A8D3
0x14001a87e  movzx   eax, ax
0x14001a881  mov     r9d, 18h
0x14001a887  jmp     short loc_14001A8B7
0x14001a889  lea     rdx, [rsp+78h+Buf2]
0x14001a88e  mov     rcx, r15
0x14001a891  call    SdpRetrieveUint16
0x14001a896  movzx   ecx, word ptr [rsp+78h+Buf2]
0x14001a89b  call    SdpByteSwapUint16
0x14001a8a0  mov     word ptr [rsp+78h+Buf2], ax
0x14001a8a5  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001a8ac  jz      short loc_14001A8D3
0x14001a8ae  movzx   eax, ax
0x14001a8b1  mov     r9d, 17h
0x14001a8b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a8be  mov     r8d, edi
0x14001a8c1  mov     [rsp+78h+var_50], eax
0x14001a8c5  mov     [rsp+78h+var_58], rsi
0x14001a8ca  mov     rcx, [rcx+40h]
0x14001a8ce  call    WPP_RECORDER_SF_d
0x14001a8d3  mov     r8, rbp; Size
0x14001a8d6  lea     rdx, [rsp+78h+Buf2]; Buf2
0x14001a8db  mov     rcx, r14; Buf1
0x14001a8de  call    memcmp
0x14001a8e3  test    eax, eax
0x14001a8e5  jnz     loc_14001A7D8
0x14001a8eb  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001a8f2  jz      short loc_14001A910
0x14001a8f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a8fb  lea     r9d, [rax+19h]
0x14001a8ff  mov     r8d, edi
0x14001a902  mov     [rsp+78h+var_58], rsi
0x14001a907  mov     rcx, [rcx+40h]
0x14001a90b  call    WPP_RECORDER_SF_
0x14001a910  mov     byte ptr [r14+10h], 1
0x14001a915  jmp     loc_14001A7D8
0x14001a91a  lea     rbx, WPP_RECORDER_INITIALIZED
0x14001a921  mov     edi, 4
0x14001a926  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001a92d  lea     rsi, WPP_3313475e708830025d331cff5c1f0c33_Traceguids
0x14001a934  jz      short loc_14001A952
0x14001a936  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a93d  lea     r9d, [rdi+16h]
0x14001a941  mov     r8d, edi
0x14001a944  mov     [rsp+78h+var_58], rsi
0x14001a949  mov     rcx, [rcx+40h]
0x14001a94d  call    WPP_RECORDER_SF_
0x14001a952  cmp     byte ptr [r14+10h], 0
0x14001a957  jz      loc_14001A7D8
0x14001a95d  mov     byte ptr [r14+11h], 1
0x14001a962  sub     ebp, 1
0x14001a965  jz      short loc_14001A9D2
0x14001a967  sub     ebp, 1
0x14001a96a  jz      short loc_14001A9A1
0x14001a96c  cmp     ebp, 2
0x14001a96f  jz      short loc_14001A97B
0x14001a971  mov     byte ptr [r14+11h], 0
0x14001a976  jmp     loc_14001AA05
0x14001a97b  lea     rdx, [r14+14h]
0x14001a97f  mov     rcx, r15
0x14001a982  call    SdpRetrieveUint32
0x14001a987  mov     ecx, [rdx]
0x14001a989  call    SdpByteSwapUint32
0x14001a98e  mov     [rdx], eax
0x14001a990  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001a997  jz      short loc_14001AA05
0x14001a999  mov     r9d, 1Dh
0x14001a99f  jmp     short loc_14001A9E9
0x14001a9a1  lea     rdx, [r14+14h]
0x14001a9a5  mov     rcx, r15
0x14001a9a8  call    SdpRetrieveUint16
0x14001a9ad  movzx   ecx, word ptr [rdx]
0x14001a9b0  call    SdpByteSwapUint16
0x14001a9b5  movzx   r8d, ax
0x14001a9b9  mov     [rdx], r8d
0x14001a9bc  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001a9c3  jz      short loc_14001AA05
0x14001a9c5  mov     r9d, 1Ch
0x14001a9cb  mov     [rsp+78h+var_50], r8d
0x14001a9d0  jmp     short loc_14001A9ED
0x14001a9d2  movzx   eax, byte ptr [r15]
0x14001a9d6  mov     [r14+14h], eax
0x14001a9da  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14001a9e1  jz      short loc_14001AA05
0x14001a9e3  mov     r9d, 1Bh
0x14001a9e9  mov     [rsp+78h+var_50], eax
0x14001a9ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a9f4  mov     r8d, edi
0x14001a9f7  mov     [rsp+78h+var_58], rsi
0x14001a9fc  mov     rcx, [rcx+40h]
0x14001aa00  call    WPP_RECORDER_SF_d
0x14001aa05  mov     eax, 0C0000001h
0x14001aa0a  jmp     loc_14001A7DA
```
