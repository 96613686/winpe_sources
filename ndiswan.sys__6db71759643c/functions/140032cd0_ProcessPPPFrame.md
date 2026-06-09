# ProcessPPPFrame

- ea: `0x140032cd0`
- end: `0x140033093`
- name: `ProcessPPPFrame`
- size: `963`
- prototype: `__int64 __fastcall(PVOID)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14002d7dc`
- `0x140032ba0`

## callees

- `0x140003620`
- `0x14000a290`
- `0x14000a2c0`
- `0x1400161f0`
- `0x14002cf98`
- `0x14002d570`
- `0x140032cd0`
- `0x1400330a0`

## import_xrefs

- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140032fc8`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140032fc8`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140032f67`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140032f67`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140032f9a`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140032f9a`

## pseudocode

```c
__int64 __fastcall ProcessPPPFrame(_DWORD *a1, __int64 a2)
{
  unsigned __int16 *v4; // rdx
  unsigned int v5; // esi
  int v6; // r8d
  int v7; // r8d
  unsigned __int16 v8; // cx
  unsigned __int16 *v9; // rdx
  _DWORD *v10; // r9
  __int64 v12; // rax
  struct _NET_BUFFER_LIST *v13; // rcx
  ULONG v14; // r14d
  int v15; // [rsp+30h] [rbp-30h]
  int v16; // [rsp+30h] [rbp-30h]
  unsigned __int16 *v17; // [rsp+38h] [rbp-28h]
  unsigned __int16 *v18; // [rsp+38h] [rbp-28h]
  __int64 v19; // [rsp+40h] [rbp-20h] BYREF
  int v20; // [rsp+48h] [rbp-18h] BYREF
  int v21; // [rsp+4Ch] [rbp-14h]
  int v22; // [rsp+50h] [rbp-10h]
  __int16 v23; // [rsp+54h] [rbp-Ch]

  v4 = *(unsigned __int16 **)(a2 + 64);
  v5 = 0;
  v17 = v4;
  v6 = *(_DWORD *)(a2 + 72);
  v15 = v6;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_52604c4400d53a16edd48a543f00e082_Traceguids);
    v4 = v17;
    v6 = v15;
  }
  ++a1[406];
  if ( (*(_BYTE *)v4 & 1) == 0 || *(_BYTE *)v4 == 0xCF )
  {
    v7 = v6 - 2;
    v8 = _byteswap_ushort(*v4);
    v9 = v4 + 1;
  }
  else
  {
    v7 = v6 - 1;
    v8 = *(unsigned __int8 *)v4;
    v9 = (unsigned __int16 *)((char *)v4 + 1);
  }
  v18 = v9;
  v16 = v7;
  if ( v7 <= 0 )
    goto LABEL_11;
  if ( v8 != 253 )
  {
    if ( v8 == 0x80FD && *(_BYTE *)v9 == 14 )
    {
      if ( qword_14001E2D8 || gbEnablePacketCapture && *((_BYTE *)a1 + 2436) )
      {
        *(_WORD *)(a2 + 56) = -32515;
        v12 = *(_QWORD *)(a2 + 24);
        v21 = 1377894230;
        v22 = -11123899;
        v23 = -1;
        *(_QWORD *)(a2 + 64) = v9;
        *(_DWORD *)(a2 + 72) = v7;
        v20 = 1128616480;
        v19 = 0;
        HIBYTE(v22) = *(_BYTE *)(v12 + 40);
        BYTE1(v21) = HIBYTE(v22);
        v13 = *(struct _NET_BUFFER_LIST **)(a2 + 104);
        v23 = -640;
        v14 = v7 - *(_DWORD *)(v13->Link.Region + 24) + 14;
        if ( !NdisRetreatNetBufferListDataStart(v13, v14, 0, 0, 0) )
        {
          RtlCopyKernelBufferToMdl(
            &v20,
            *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 104) + 8LL) + 8LL),
            *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(a2 + 104) + 8LL) + 16LL),
            14,
            &v19);
          IndicatePromiscuousRecv(a1, a2, *(_QWORD *)(a2 + 104), 1);
          NdisAdvanceNetBufferListDataStart(*(PNET_BUFFER_LIST *)(a2 + 104), v14, 1u, 0);
        }
      }
      if ( a1[210] )
        a1[4] |= 4u;
      goto LABEL_11;
    }
    v10 = a1 + 64;
    if ( (a1[64] & 4) != 0 && v8 < 0x8000u )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v5;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_52604c4400d53a16edd48a543f00e082_Traceguids);
      goto LABEL_11;
    }
LABEL_9:
    *(_WORD *)(a2 + 56) = v8;
    *(_DWORD *)(a2 + 72) = v7;
    *(_QWORD *)(a2 + 64) = v9;
    if ( (*v10 & 0x200) == 0
      || ((v8 - 45) & 0xFFFD) != 0
      || (*(_DWORD *)(a2 + 48) &= ~2u, DoVJDecompression((__int64)a1, a2)) )
    {
      v5 = ApplyQoSAndIndicateRecvPacket(a1, a2);
    }
    goto LABEL_11;
  }
  *(_DWORD *)(a2 + 48) &= ~2u;
  if ( (unsigned __int8)DoDecompDecryptProcessing(a1) )
  {
    if ( (*(_BYTE *)v18 & 1) != 0 && v16 > 0 )
    {
      v7 = v16 - 1;
      v9 = (unsigned __int16 *)((char *)v18 + 1);
      v10 = a1 + 64;
      v8 = *(unsigned __int8 *)v18;
      goto LABEL_9;
    }
    if ( v16 > 1 )
    {
      v7 = v16 - 2;
      v10 = a1 + 64;
      v8 = _byteswap_ushort(*v18);
      v9 = v18 + 1;
      goto LABEL_9;
    }
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v5;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        29,
        WPP_52604c4400d53a16edd48a543f00e082_Traceguids,
        (unsigned int)v16);
  }
LABEL_11:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_52604c4400d53a16edd48a543f00e082_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x140032cd0  push    rbp
0x140032cd2  push    rbx
0x140032cd3  push    rsi
0x140032cd4  push    rdi
0x140032cd5  push    r15
0x140032cd7  mov     rbp, rsp
0x140032cda  sub     rsp, 60h
0x140032cde  mov     rax, cs:__security_cookie
0x140032ce5  xor     rax, rsp
0x140032ce8  mov     [rbp+var_8], rax
0x140032cec  mov     rbx, rdx
0x140032cef  mov     rdi, rcx
0x140032cf2  mov     rdx, [rdx+40h]
0x140032cf6  xor     esi, esi
0x140032cf8  mov     [rbp+var_28], rdx
0x140032cfc  mov     r8d, [rbx+48h]
0x140032d00  mov     [rbp+var_30], r8d
0x140032d04  mov     rcx, cs:WPP_GLOBAL_Control
0x140032d0b  lea     r15, WPP_GLOBAL_Control
0x140032d12  cmp     rcx, r15
0x140032d15  jz      short loc_140032D22
0x140032d17  mov     eax, [rcx+2Ch]
0x140032d1a  test    al, 10h
0x140032d1c  jnz     loc_140032E6B
0x140032d22  inc     dword ptr [rdi+658h]
0x140032d28  movzx   eax, byte ptr [rdx]
0x140032d2b  test    al, 1
0x140032d2d  jnz     loc_140032E32
0x140032d33  movzx   ecx, ax
0x140032d36  add     r8d, 0FFFFFFFEh
0x140032d3a  movzx   eax, byte ptr [rdx+1]
0x140032d3e  shl     cx, 8
0x140032d42  or      cx, ax
0x140032d45  add     rdx, 2
0x140032d49  mov     [rbp+var_28], rdx
0x140032d4d  mov     [rbp+var_30], r8d
0x140032d51  test    r8d, r8d
0x140032d54  jle     short loc_140032DA6
0x140032d56  mov     eax, 0FDh
0x140032d5b  cmp     cx, ax
0x140032d5e  jz      short loc_140032DD7
0x140032d60  mov     eax, 80FDh
0x140032d65  cmp     cx, ax
0x140032d68  jz      loc_140032ED6
0x140032d6e  lea     r9, [rdi+100h]
0x140032d75  mov     eax, [r9]
0x140032d78  test    al, 4
0x140032d7a  jnz     loc_140032FF1
0x140032d80  mov     [rbx+38h], cx
0x140032d84  mov     [rbx+48h], r8d
0x140032d88  mov     [rbx+40h], rdx
0x140032d8c  test    dword ptr [r9], 200h
0x140032d93  jnz     loc_14003303E
0x140032d99  mov     rdx, rbx
0x140032d9c  mov     rcx, rdi
0x140032d9f  call    ApplyQoSAndIndicateRecvPacket
0x140032da4  mov     esi, eax
0x140032da6  mov     rcx, cs:WPP_GLOBAL_Control
0x140032dad  cmp     rcx, r15
0x140032db0  jz      short loc_140032DBD
0x140032db2  mov     eax, [rcx+2Ch]
0x140032db5  test    al, 10h
0x140032db7  jnz     loc_14003306C
0x140032dbd  mov     eax, esi
0x140032dbf  mov     rcx, [rbp+var_8]
0x140032dc3  xor     rcx, rsp; StackCookie
0x140032dc6  call    __security_check_cookie
0x140032dcb  add     rsp, 60h
0x140032dcf  pop     r15
0x140032dd1  pop     rdi
0x140032dd2  pop     rsi
0x140032dd3  pop     rbx
0x140032dd4  pop     rbp
0x140032dd5  retn
0x140032dd7  and     dword ptr [rbx+30h], 0FFFFFFFDh
0x140032ddb  lea     r8, [rbp+var_30]
0x140032ddf  lea     rdx, [rbp+var_28]
0x140032de3  mov     rcx, rdi; PVOID
0x140032de6  call    DoDecompDecryptProcessing
0x140032deb  test    al, al
0x140032ded  jz      short loc_140032DA6
0x140032def  mov     rdx, [rbp+var_28]
0x140032df3  mov     r9d, [rbp+var_30]
0x140032df7  movzx   eax, byte ptr [rdx]
0x140032dfa  test    al, 1
0x140032dfc  jnz     short loc_140032E48
0x140032dfe  cmp     r9d, 1
0x140032e02  jle     loc_140032E97
0x140032e08  movzx   ecx, ax
0x140032e0b  lea     r8d, [r9-2]
0x140032e0f  movzx   eax, byte ptr [rdx+1]
0x140032e13  lea     r9, [rdi+100h]
0x140032e1a  shl     cx, 8
0x140032e1e  or      cx, ax
0x140032e21  mov     [rbp+var_30], r8d
0x140032e25  add     rdx, 2
0x140032e29  mov     [rbp+var_28], rdx
0x140032e2d  jmp     loc_140032D80
0x140032e32  cmp     al, 0CFh
0x140032e34  jz      loc_140032D33
0x140032e3a  dec     r8d
0x140032e3d  movzx   ecx, ax
0x140032e40  inc     rdx
0x140032e43  jmp     loc_140032D49
0x140032e48  test    r9d, r9d
0x140032e4b  jle     short loc_140032DFE
0x140032e4d  lea     r8d, [r9-1]
0x140032e51  inc     rdx
0x140032e54  mov     [rbp+var_28], rdx
0x140032e58  lea     r9, [rdi+100h]
0x140032e5f  mov     [rbp+var_30], r8d
0x140032e63  movzx   ecx, ax
0x140032e66  jmp     loc_140032D80
0x140032e6b  cmp     byte ptr [rcx+29h], 5
0x140032e6f  jb      loc_140032D22
0x140032e75  mov     rcx, [rcx+18h]
0x140032e79  lea     r8, WPP_52604c4400d53a16edd48a543f00e082_Traceguids
0x140032e80  mov     edx, 1Ch
0x140032e85  call    WPP_SF_
0x140032e8a  mov     rdx, [rbp+var_28]
0x140032e8e  mov     r8d, [rbp+var_30]
0x140032e92  jmp     loc_140032D22
0x140032e97  mov     rcx, cs:WPP_GLOBAL_Control
0x140032e9e  cmp     rcx, r15
0x140032ea1  jz      loc_140032DBD
0x140032ea7  mov     eax, [rcx+2Ch]
0x140032eaa  test    al, 10h
0x140032eac  jz      loc_140032DA6
0x140032eb2  cmp     byte ptr [rcx+29h], 3
0x140032eb6  jb      loc_140032DA6
0x140032ebc  mov     rcx, [rcx+18h]
0x140032ec0  lea     r8, WPP_52604c4400d53a16edd48a543f00e082_Traceguids
0x140032ec7  mov     edx, 1Dh
0x140032ecc  call    WPP_SF_d
0x140032ed1  jmp     loc_140032DA6
0x140032ed6  cmp     byte ptr [rdx], 0Eh
0x140032ed9  jnz     loc_140032D6E
0x140032edf  cmp     cs:qword_14001E2D8, rsi
0x140032ee6  jnz     short loc_140032F02
0x140032ee8  cmp     cs:gbEnablePacketCapture, sil
0x140032eef  jz      loc_140032FDC
0x140032ef5  cmp     [rdi+984h], sil
0x140032efc  jz      loc_140032FDC
0x140032f02  mov     [rbx+38h], ax
0x140032f06  xor     r9d, r9d; AllocateMdlHandler
0x140032f09  mov     rax, [rbx+18h]
0x140032f0d  mov     [rbp+var_14], 5220FF56h
0x140032f14  mov     [rbp+var_10], 0FF564345h
0x140032f1b  mov     [rbp+var_C], 0FFFFh
0x140032f21  mov     [rbx+40h], rdx
0x140032f25  mov     [rbx+48h], r8d
0x140032f29  mov     [rbp+var_18], 43455220h
0x140032f30  mov     [rbp+var_20], rsi
0x140032f34  movzx   ecx, byte ptr [rax+28h]
0x140032f38  mov     byte ptr [rbp+var_10+3], cl
0x140032f3b  mov     byte ptr [rbp+var_14+1], cl
0x140032f3e  mov     rcx, [rbx+68h]; NetBufferList
0x140032f42  mov     [rbp+var_C], 0FD80h
0x140032f48  mov     [rsp+60h+arg_10], r14
0x140032f50  mov     [rsp+60h+FreeMdlHandler], rsi; FreeMdlHandler
0x140032f55  mov     rax, [rcx+8]
0x140032f59  sub     r8d, [rax+18h]
0x140032f5d  lea     r14d, [r8+0Eh]
0x140032f61  xor     r8d, r8d; DataBackFill
0x140032f64  mov     edx, r14d; DataOffsetDelta
0x140032f67  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x140032f6e  nop     dword ptr [rax+rax+00h]
0x140032f73  test    eax, eax
0x140032f75  jnz     short loc_140032FD4
0x140032f77  mov     rax, [rbx+68h]
0x140032f7b  lea     rcx, [rbp+var_18]
0x140032f7f  mov     r9d, 0Eh
0x140032f85  mov     rdx, [rax+8]
0x140032f89  lea     rax, [rbp+var_20]
0x140032f8d  mov     [rsp+60h+FreeMdlHandler], rax
0x140032f92  mov     r8d, [rdx+10h]
0x140032f96  mov     rdx, [rdx+8]
0x140032f9a  call    cs:__imp_RtlCopyKernelBufferToMdl
0x140032fa1  nop     dword ptr [rax+rax+00h]
0x140032fa6  mov     r8, [rbx+68h]
0x140032faa  mov     r9d, 1
0x140032fb0  mov     rdx, rbx
0x140032fb3  mov     rcx, rdi
0x140032fb6  call    IndicatePromiscuousRecv
0x140032fbb  mov     rcx, [rbx+68h]; NetBufferList
0x140032fbf  xor     r9d, r9d; FreeMdlMdlHandler
0x140032fc2  mov     r8b, 1; FreeMdl
0x140032fc5  mov     edx, r14d; DataOffsetDelta
0x140032fc8  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x140032fcf  nop     dword ptr [rax+rax+00h]
0x140032fd4  mov     r14, [rsp+60h+arg_10]
0x140032fdc  cmp     [rdi+348h], esi
0x140032fe2  jz      loc_140032DA6
0x140032fe8  or      dword ptr [rdi+10h], 4
0x140032fec  jmp     loc_140032DA6
0x140032ff1  mov     eax, 8000h
0x140032ff6  cmp     cx, ax
0x140032ff9  jnb     loc_140032D80
0x140032fff  mov     rcx, cs:WPP_GLOBAL_Control
0x140033006  cmp     rcx, r15
0x140033009  jz      loc_140032DBD
0x14003300f  mov     eax, [rcx+2Ch]
0x140033012  test    al, 10h
0x140033014  jz      loc_140032DA6
0x14003301a  cmp     byte ptr [rcx+29h], 3
0x14003301e  jb      loc_140032DA6
0x140033024  mov     rcx, [rcx+18h]
0x140033028  lea     r8, WPP_52604c4400d53a16edd48a543f00e082_Traceguids
0x14003302f  mov     edx, 1Eh
0x140033034  call    WPP_SF_
0x140033039  jmp     loc_140032DA6
0x14003303e  sub     cx, 2Dh ; '-'
0x140033042  mov     eax, 0FFFDh
0x140033047  test    ax, cx
0x14003304a  jnz     loc_140032D99
0x140033050  and     dword ptr [rbx+30h], 0FFFFFFFDh
0x140033054  mov     rdx, rbx
0x140033057  mov     rcx, rdi
0x14003305a  call    DoVJDecompression
0x14003305f  test    al, al
0x140033061  jz      loc_140032DA6
0x140033067  jmp     loc_140032D99
0x14003306c  cmp     byte ptr [rcx+29h], 5
0x140033070  jb      loc_140032DBD
0x140033076  mov     rcx, [rcx+18h]
0x14003307a  lea     r8, WPP_52604c4400d53a16edd48a543f00e082_Traceguids
0x140033081  mov     edx, 1Fh
0x140033086  mov     r9d, esi
0x140033089  call    WPP_SF_d
0x14003308e  jmp     loc_140032DBD
```
