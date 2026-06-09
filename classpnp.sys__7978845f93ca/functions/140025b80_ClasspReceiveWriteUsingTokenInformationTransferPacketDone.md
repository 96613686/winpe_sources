# ClasspReceiveWriteUsingTokenInformationTransferPacketDone

- ea: `0x140025b80`
- end: `0x140025f73`
- name: `ClasspReceiveWriteUsingTokenInformationTransferPacketDone`
- size: `1011`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400084b0`
- `0x140023bc4`
- `0x140023f24`
- `0x1400259cc`
- `0x140025b80`
- `0x140026ffc`
- `0x1400275bc`
- `0x140027870`

## string_xrefs

- `0x140025cb8`: `Target truncated write. `

## pseudocode

```c
__int64 __fastcall ClasspReceiveWriteUsingTokenInformationTransferPacketDone(_QWORD *P)
{
  struct _DEVICE_OBJECT *v1; // rsi
  __int64 v3; // r8
  unsigned __int64 v4; // r14
  char *v5; // rax
  unsigned int *DeviceExtension; // rdx
  NTSTATUS v7; // ecx
  char v8; // cl
  char v9; // di
  unsigned __int64 v10; // r12
  int v11; // r13d
  __int64 v12; // r8
  bool v13; // zf
  const wchar_t *v14; // rdx
  unsigned int *v15; // r14
  struct _SCSI_REQUEST_BLOCK *v16; // rdx
  char v17; // r11
  unsigned int v18; // r10d
  __int64 v19; // rcx
  unsigned __int64 v20; // r9
  int v21; // ecx
  int v22; // ecx
  __int64 v23; // r8
  __int64 result; // rax
  NTSTATUS v25; // r8d
  unsigned int *v26; // [rsp+40h] [rbp-18h]
  __int64 v27; // [rsp+48h] [rbp-10h]
  ULONG RetryInterval; // [rsp+A0h] [rbp+48h] BYREF
  NTSTATUS Status; // [rsp+A8h] [rbp+50h] BYREF
  int v30; // [rsp+B0h] [rbp+58h]
  unsigned __int64 v31; // [rsp+B8h] [rbp+60h]

  v1 = (struct _DEVICE_OBJECT *)*P;
  v3 = *((unsigned int *)P + 92);
  v4 = P[44];
  v27 = P[1];
  v5 = (char *)P[38];
  Status = 0;
  DeviceExtension = (unsigned int *)v1->DeviceExtension;
  v26 = DeviceExtension;
  v30 = v3;
  P[43] = 0;
  if ( !v5 )
    v5 = (char *)(P + 12);
  v7 = *((_DWORD *)v5 + 12);
  Status = v7;
  if ( v7 == -1073741764 )
  {
    Status = 0;
  }
  else if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDDI(WPP_GLOBAL_Control->AttachedDevice, 268, v3, v1, Status, v3, v4 * DeviceExtension[143]);
    }
    goto LABEL_58;
  }
  v8 = 0;
  v9 = *((_BYTE *)P + 485) & 0x7F;
  if ( v9 == 1
    || (*((_BYTE *)P + 485) & 0x7F) == 2
    || (*((_BYTE *)P + 485) & 0x7F) == 3
    || (*((_BYTE *)P + 485) & 0x7F) == 0x60 )
  {
    v8 = 1;
  }
  HIBYTE(v31) = *((_BYTE *)P + 496);
  BYTE6(v31) = *((_BYTE *)P + 497);
  BYTE5(v31) = *((_BYTE *)P + 498);
  BYTE4(v31) = *((_BYTE *)P + 499);
  BYTE3(v31) = *((_BYTE *)P + 500);
  BYTE2(v31) = *((_BYTE *)P + 501);
  BYTE1(v31) = *((_BYTE *)P + 502);
  LOBYTE(v31) = *((_BYTE *)P + 503);
  if ( !v8 )
    goto LABEL_57;
  v10 = v31;
  v11 = *((unsigned __int8 *)P + 492);
  LOBYTE(RetryInterval) = *((_BYTE *)P + 494);
  if ( v31 > v4 )
    v10 = 0;
  if ( ((v9 - 1) & 0xFD) != 0 )
    v10 = 0;
  P[45] = v10;
  ClasspAdvanceOffloadWritePosition(P, v10);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v15 = v26;
  }
  else
  {
    v13 = v10 == v4;
    v14 = &word_140043310;
    v15 = v26;
    if ( !v13 )
      v14 = L"Target truncated write. ";
    WPP_SF_qSDI(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v14,
      v12,
      (_DWORD)v1,
      (__int64)v14,
      v30,
      *((_BYTE *)P + 360) * v26[143]);
  }
  Status = 0;
  if ( (unsigned __int8)(v9 - 2) > 1u && v9 != 96 )
    goto LABEL_54;
  v16 = (struct _SCSI_REQUEST_BLOCK *)(P + 47);
  if ( *((_BYTE *)P + 378) != 40 )
  {
    *((_BYTE *)P + 380) = v11;
    goto LABEL_43;
  }
  if ( *((_DWORD *)P + 99) )
    goto LABEL_43;
  v17 = 0;
  v18 = 0;
  if ( !*((_DWORD *)P + 108) )
    goto LABEL_43;
  while ( 1 )
  {
    v19 = *((unsigned int *)&v16[1].SenseInfoBuffer + v18);
    if ( (unsigned int)v19 >= 0x80 )
    {
      v20 = *((unsigned int *)P + 98);
      if ( (unsigned int)v19 < (unsigned int)v20 )
        break;
    }
LABEL_37:
    if ( ++v18 >= *((_DWORD *)P + 108) )
      goto LABEL_43;
  }
  v12 = (unsigned int)v19;
  v21 = *(_DWORD *)((char *)&v16->Length + v19) - 64;
  if ( v21 )
  {
    v22 = v21 - 1;
    if ( !v22 )
    {
      if ( v12 + 56 <= v20 )
      {
        v17 = 1;
        *(&v16->QueueTag + v12) = v11;
      }
LABEL_36:
      if ( v17 )
        goto LABEL_43;
      goto LABEL_37;
    }
    if ( v22 != 1 )
      goto LABEL_36;
  }
  if ( v12 + 40 > v20 )
    goto LABEL_36;
  *(&v16->QueueTag + v12) = v11;
LABEL_43:
  if ( (_BYTE)RetryInterval )
  {
    *((_BYTE *)P + 387) = RetryInterval;
    P[51] = P + 64;
    RetryInterval = 0;
    *((_WORD *)P + 189) = -31744;
    ClassInterpretSenseInfo(v1, v16, 0xFu, 0, 0, &Status, &RetryInterval);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_qDDI(WPP_GLOBAL_Control->AttachedDevice, 270, v23, v1, Status, v30, v10 * v15[143]);
    }
    if ( Status == -1073740699 )
      *((_BYTE *)P + 372) = 1;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_qDDI(WPP_GLOBAL_Control->AttachedDevice, 271, v12, v1, v11, v30, v10 * v15[143]);
  }
LABEL_54:
  if ( !v10 )
  {
    if ( Status < 0 )
    {
LABEL_58:
      result = ClasspCompleteOffloadWrite(P);
      v25 = Status;
      goto LABEL_59;
    }
LABEL_57:
    Status = -1073741823;
    goto LABEL_58;
  }
  Status = 0;
  result = ClasspReceiveWriteUsingTokenInformationDone(P);
  v25 = 259;
  Status = 259;
LABEL_59:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      return WPP_SF_qqD(
               WPP_GLOBAL_Control->AttachedDevice,
               272,
               WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
               v1,
               v27,
               v25);
  }
  return result;
}

```

## disassembly

```asm
0x140025b80  push    rbp
0x140025b82  push    rbx
0x140025b83  push    rsi
0x140025b84  push    rdi
0x140025b85  push    r12
0x140025b87  push    r13
0x140025b89  push    r14
0x140025b8b  push    r15
0x140025b8d  mov     rbp, rsp
0x140025b90  sub     rsp, 58h
0x140025b94  mov     rax, [rcx+8]
0x140025b98  xor     r9d, r9d
0x140025b9b  mov     rsi, [rcx]
0x140025b9e  mov     rbx, rcx
0x140025ba1  mov     r8d, [rcx+170h]
0x140025ba8  mov     r14, [rcx+160h]
0x140025baf  mov     [rbp+var_10], rax
0x140025bb3  mov     rax, [rcx+130h]
0x140025bba  mov     [rbp+arg_8], r9d
0x140025bbe  mov     rdx, [rsi+40h]
0x140025bc2  mov     [rbp+var_18], rdx
0x140025bc6  mov     [rbp+arg_10], r8d
0x140025bca  mov     [rcx+158h], r9
0x140025bd1  test    rax, rax
0x140025bd4  jnz     short loc_140025BDA
0x140025bd6  lea     rax, [rcx+60h]
0x140025bda  mov     ecx, [rax+30h]
0x140025bdd  mov     [rbp+arg_8], ecx
0x140025be0  cmp     ecx, 0C000003Ch
0x140025be6  jnz     loc_140025CFB
0x140025bec  mov     [rbp+arg_8], r9d
0x140025bf0  mov     al, [rbx+1E5h]
0x140025bf6  mov     cl, r9b
0x140025bf9  and     al, 7Fh
0x140025bfb  movzx   edi, al
0x140025bfe  mov     eax, edi
0x140025c00  sub     eax, 1
0x140025c03  jz      short loc_140025C14
0x140025c05  sub     eax, 1
0x140025c08  jz      short loc_140025C14
0x140025c0a  sub     eax, 1
0x140025c0d  jz      short loc_140025C14
0x140025c0f  cmp     eax, 5Dh ; ']'
0x140025c12  jnz     short loc_140025C16
0x140025c14  mov     cl, 1
0x140025c16  mov     al, [rbx+1F0h]
0x140025c1c  lea     r15, WPP_GLOBAL_Control
0x140025c23  mov     byte ptr [rbp+arg_18+7], al
0x140025c26  mov     al, [rbx+1F1h]
0x140025c2c  mov     byte ptr [rbp+arg_18+6], al
0x140025c2f  mov     al, [rbx+1F2h]
0x140025c35  mov     byte ptr [rbp+arg_18+5], al
0x140025c38  mov     al, [rbx+1F3h]
0x140025c3e  mov     byte ptr [rbp+arg_18+4], al
0x140025c41  mov     al, [rbx+1F4h]
0x140025c47  mov     byte ptr [rbp+arg_18+3], al
0x140025c4a  mov     al, [rbx+1F5h]
0x140025c50  mov     byte ptr [rbp+arg_18+2], al
0x140025c53  mov     al, [rbx+1F6h]
0x140025c59  mov     byte ptr [rbp+arg_18+1], al
0x140025c5c  mov     al, [rbx+1F7h]
0x140025c62  mov     byte ptr [rbp+arg_18], al
0x140025c65  test    cl, cl
0x140025c67  jz      loc_140025F0C
0x140025c6d  mov     al, [rbx+1EEh]
0x140025c73  mov     rcx, rbx
0x140025c76  mov     r12, [rbp+arg_18]
0x140025c7a  movzx   r13d, byte ptr [rbx+1ECh]
0x140025c82  cmp     r12, r14
0x140025c85  mov     byte ptr [rbp+arg_0], al
0x140025c88  lea     eax, [rdi-1]
0x140025c8b  cmova   r12, r9
0x140025c8f  test    al, 0FDh
0x140025c91  cmovnz  r12, r9
0x140025c95  mov     rdx, r12
0x140025c98  mov     [rbx+168h], r12
0x140025c9f  call    ClasspAdvanceOffloadWritePosition
0x140025ca4  mov     rcx, cs:WPP_GLOBAL_Control
0x140025cab  cmp     rcx, r15
0x140025cae  jz      loc_140025D60
0x140025cb4  mov     rcx, [rcx+18h]
0x140025cb8  lea     rax, aTargetTruncate; "Target truncated write. "
0x140025cbf  cmp     r12, r14
0x140025cc2  lea     rdx, word_140043310
0x140025cc9  mov     r14, [rbp+var_18]
0x140025ccd  mov     r9, rsi
0x140025cd0  cmovnz  rdx, rax
0x140025cd4  mov     eax, [r14+23Ch]
0x140025cdb  imul    rax, [rbx+168h]
0x140025ce3  mov     [rsp+58h+RetryInterval], rax
0x140025ce8  mov     eax, [rbp+arg_10]
0x140025ceb  mov     dword ptr [rsp+58h+Status], eax
0x140025cef  mov     qword ptr [rsp+58h+RetryCount], rdx
0x140025cf4  call    WPP_SF_qSDI
0x140025cf9  jmp     short loc_140025D64
0x140025cfb  test    ecx, ecx
0x140025cfd  jns     loc_140025BF0
0x140025d03  mov     rcx, cs:WPP_GLOBAL_Control
0x140025d0a  lea     r15, WPP_GLOBAL_Control
0x140025d11  cmp     rcx, r15
0x140025d14  jz      loc_140025F13
0x140025d1a  mov     eax, [rcx+2Ch]
0x140025d1d  test    al, 10h
0x140025d1f  jz      loc_140025F13
0x140025d25  cmp     byte ptr [rcx+29h], 2
0x140025d29  jb      loc_140025F13
0x140025d2f  mov     eax, [rdx+23Ch]
0x140025d35  mov     r9, rsi
0x140025d38  mov     rcx, [rcx+18h]
0x140025d3c  mov     edx, 10Ch
0x140025d41  imul    rax, r14
0x140025d45  mov     [rsp+58h+RetryInterval], rax
0x140025d4a  mov     eax, [rbp+arg_8]
0x140025d4d  mov     dword ptr [rsp+58h+Status], r8d
0x140025d52  mov     [rsp+58h+RetryCount], eax
0x140025d56  call    WPP_SF_qDDI
0x140025d5b  jmp     loc_140025F13
0x140025d60  mov     r14, [rbp+var_18]
0x140025d64  lea     eax, [rdi-2]
0x140025d67  mov     [rbp+arg_8], 0
0x140025d6e  cmp     al, 1
0x140025d70  jbe     short loc_140025D7C
0x140025d72  cmp     dil, 60h ; '`'
0x140025d76  jnz     loc_140025EE7
0x140025d7c  lea     rdx, [rbx+178h]; Srb
0x140025d83  xor     edi, edi
0x140025d85  cmp     byte ptr [rdx+2], 28h ; '('
0x140025d89  jnz     short loc_140025DFB
0x140025d8b  cmp     [rdx+14h], edi
0x140025d8e  jnz     short loc_140025DFF
0x140025d90  mov     r11b, dil
0x140025d93  mov     r10d, edi
0x140025d96  cmp     [rdx+38h], edi
0x140025d99  jbe     short loc_140025DFF
0x140025d9b  mov     eax, r10d
0x140025d9e  mov     ecx, [rdx+rax*4+78h]
0x140025da2  cmp     ecx, 80h
0x140025da8  jb      short loc_140025DD6
0x140025daa  mov     r9d, [rdx+10h]
0x140025dae  cmp     ecx, r9d
0x140025db1  jnb     short loc_140025DD6
0x140025db3  mov     r8d, ecx
0x140025db6  mov     ecx, [rcx+rdx]
0x140025db9  sub     ecx, 40h ; '@'
0x140025dbc  jz      short loc_140025DC8
0x140025dbe  sub     ecx, 1
0x140025dc1  jz      short loc_140025DE1
0x140025dc3  cmp     ecx, 1
0x140025dc6  jnz     short loc_140025DD1
0x140025dc8  lea     rcx, [r8+28h]
0x140025dcc  cmp     rcx, r9
0x140025dcf  jbe     short loc_140025DF4
0x140025dd1  test    r11b, r11b
0x140025dd4  jnz     short loc_140025DFF
0x140025dd6  inc     r10d
0x140025dd9  cmp     r10d, [rdx+38h]
0x140025ddd  jb      short loc_140025D9B
0x140025ddf  jmp     short loc_140025DFF
0x140025de1  lea     rcx, [r8+38h]
0x140025de5  cmp     rcx, r9
0x140025de8  ja      short loc_140025DD1
0x140025dea  mov     r11b, 1
0x140025ded  mov     [r8+rdx+8], r13b
0x140025df2  jmp     short loc_140025DD1
0x140025df4  mov     [r8+rdx+8], r13b
0x140025df9  jmp     short loc_140025DFF
0x140025dfb  mov     [rdx+4], r13b
0x140025dff  mov     cl, byte ptr [rbp+arg_0]
0x140025e02  test    cl, cl
0x140025e04  jz      loc_140025E9F
0x140025e0a  lea     rax, [rbx+200h]
0x140025e11  mov     [rdx+0Bh], cl
0x140025e14  mov     [rdx+20h], rax
0x140025e18  xor     r9d, r9d; IoDeviceCode
0x140025e1b  lea     rax, [rbp+arg_0]
0x140025e1f  mov     [rbp+arg_0], edi
0x140025e22  mov     [rsp+58h+RetryInterval], rax; RetryInterval
0x140025e27  mov     r8b, 0Fh; MajorFunctionCode
0x140025e2a  lea     rax, [rbp+arg_8]
0x140025e2e  mov     word ptr [rdx+2], 8400h
0x140025e34  mov     [rsp+58h+Status], rax; Status
0x140025e39  mov     rcx, rsi; DeviceObject
0x140025e3c  mov     [rsp+58h+RetryCount], edi; RetryCount
0x140025e40  call    ClassInterpretSenseInfo
0x140025e45  mov     rcx, cs:WPP_GLOBAL_Control
0x140025e4c  cmp     rcx, r15
0x140025e4f  jz      short loc_140025E8D
0x140025e51  mov     eax, [rcx+2Ch]
0x140025e54  test    al, 10h
0x140025e56  jz      short loc_140025E8D
0x140025e58  cmp     byte ptr [rcx+29h], 3
0x140025e5c  jb      short loc_140025E8D
0x140025e5e  mov     eax, [r14+23Ch]
0x140025e65  mov     edx, 10Eh
0x140025e6a  mov     rcx, [rcx+18h]
0x140025e6e  mov     r9, rsi
0x140025e71  imul    rax, r12
0x140025e75  mov     [rsp+58h+RetryInterval], rax
0x140025e7a  mov     eax, [rbp+arg_10]
0x140025e7d  mov     dword ptr [rsp+58h+Status], eax
0x140025e81  mov     eax, [rbp+arg_8]
0x140025e84  mov     [rsp+58h+RetryCount], eax
0x140025e88  call    WPP_SF_qDDI
0x140025e8d  cmp     [rbp+arg_8], 0C0000465h
0x140025e94  jnz     short loc_140025EE9
0x140025e96  mov     byte ptr [rbx+174h], 1
0x140025e9d  jmp     short loc_140025EE9
0x140025e9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140025ea6  cmp     rcx, r15
0x140025ea9  jz      short loc_140025EE9
0x140025eab  mov     eax, [rcx+2Ch]
0x140025eae  test    al, 10h
0x140025eb0  jz      short loc_140025EE9
0x140025eb2  cmp     byte ptr [rcx+29h], 3
0x140025eb6  jb      short loc_140025EE9
0x140025eb8  mov     eax, [r14+23Ch]
0x140025ebf  mov     edx, 10Fh
0x140025ec4  mov     rcx, [rcx+18h]
0x140025ec8  mov     r9, rsi
0x140025ecb  imul    rax, r12
0x140025ecf  mov     [rsp+58h+RetryInterval], rax
0x140025ed4  mov     eax, [rbp+arg_10]
0x140025ed7  mov     dword ptr [rsp+58h+Status], eax
0x140025edb  mov     [rsp+58h+RetryCount], r13d
0x140025ee0  call    WPP_SF_qDDI
0x140025ee5  jmp     short loc_140025EE9
0x140025ee7  xor     edi, edi
0x140025ee9  test    r12, r12
0x140025eec  jz      short loc_140025F07
0x140025eee  xor     edx, edx
0x140025ef0  mov     [rbp+arg_8], edi
0x140025ef3  mov     rcx, rbx; P
0x140025ef6  call    ClasspReceiveWriteUsingTokenInformationDone
0x140025efb  mov     r8d, 103h
0x140025f01  mov     [rbp+arg_8], r8d
0x140025f05  jmp     short loc_140025F22
0x140025f07  cmp     [rbp+arg_8], edi
0x140025f0a  jl      short loc_140025F13
0x140025f0c  mov     [rbp+arg_8], 0C0000001h
0x140025f13  mov     edx, [rbp+arg_8]
0x140025f16  mov     rcx, rbx; P
0x140025f19  call    ClasspCompleteOffloadWrite
0x140025f1e  mov     r8d, [rbp+arg_8]
0x140025f22  mov     rcx, cs:WPP_GLOBAL_Control
0x140025f29  cmp     rcx, r15
0x140025f2c  jz      short loc_140025F61
0x140025f2e  mov     eax, [rcx+2Ch]
0x140025f31  test    al, 10h
0x140025f33  jz      short loc_140025F61
0x140025f35  cmp     byte ptr [rcx+29h], 5
0x140025f39  jb      short loc_140025F61
0x140025f3b  mov     rax, [rbp+var_10]
0x140025f3f  mov     edx, 110h
0x140025f44  mov     rcx, [rcx+18h]
0x140025f48  mov     r9, rsi
0x140025f4b  mov     dword ptr [rsp+58h+Status], r8d
0x140025f50  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140025f57  mov     qword ptr [rsp+58h+RetryCount], rax
0x140025f5c  call    WPP_SF_qqD
0x140025f61  add     rsp, 58h
0x140025f65  pop     r15
0x140025f67  pop     r14
0x140025f69  pop     r13
0x140025f6b  pop     r12
0x140025f6d  pop     rdi
0x140025f6e  pop     rsi
0x140025f6f  pop     rbx
0x140025f70  pop     rbp
0x140025f71  retn
```
