# Smb2Read_HandleRdmaDdpReceive

- ea: `0x14002da60`
- end: `0x14002ddd6`
- name: `Smb2Read_HandleRdmaDdpReceive`
- size: `886`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001c190`

## callees

- `0x1400219b0`
- `0x140027fc0`
- `0x140028950`
- `0x140029840`
- `0x14002a6a8`
- `0x14002da60`
- `0x140033708`
- `0x1400372c0`

## import_xrefs

- `rdbss!RxLowIoGetBufferAddress` at `0x14002dba2`
- `rdbss!RxLowIoGetBufferAddress` at `0x14002dba2`
- `mrxsmb!SmbCryptoDecryptRdmaPayload` at `0x14002dc36`
- `mrxsmb!SmbCryptoDecryptRdmaPayload` at `0x14002dc36`
- `mrxsmb!MRxSmbDetermineDdpSecurity` at `0x14002da95`
- `mrxsmb!MRxSmbDetermineDdpSecurity` at `0x14002da95`

## pseudocode

```c
__int64 __fastcall Smb2Read_HandleRdmaDdpReceive(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        _DWORD *a5,
        __int64 a6)
{
  _WORD *v7; // r14
  __int64 v8; // rcx
  char v12; // al
  __int64 v13; // rbp
  char v14; // r12
  unsigned int v15; // edi
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  char *v19; // rdi
  char *BufferAddress; // rax
  char *v21; // rdx
  int v22; // eax
  unsigned __int64 v24[11]; // [rsp+40h] [rbp-58h] BYREF
  int v25; // [rsp+A0h] [rbp+8h] BYREF

  v7 = 0;
  v8 = *(_QWORD *)(a1 + 88);
  v24[0] = 0;
  v25 = 0;
  v12 = MRxSmbDetermineDdpSecurity(*(_QWORD *)(v8 + 424));
  v13 = a6;
  v14 = v12;
  if ( (*(_BYTE *)(a6 + 12) & 1) != 0 )
  {
    v15 = Smb2Read_ValidateRdmaTransforms(v24, &v25, a1, a2, a3, a4, a5, a6);
    if ( (v15 & 0x80000000) != 0 )
      return v15;
    if ( !*(_QWORD *)(a1 + 1032) )
    {
      v15 = -1073741629;
      Smb2LkmdTelCollectParsingFailureReadHelper(a2, a1, 9);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v17 = 32;
LABEL_8:
        WPP_SF_qD(v16->AttachedDevice, v17, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids, a1, *(_DWORD *)(a1 + 68));
        return v15;
      }
      return v15;
    }
    v7 = (_WORD *)v24[0];
  }
  v18 = *(_QWORD *)(a1 + 1024);
  if ( v18 )
  {
    v19 = (char *)((v18 & 0xFFFFFFFFFFFFFFF8uLL) + *(unsigned int *)(a2 + 1392));
  }
  else
  {
    if ( *(_QWORD *)(a1 + 2456) )
      BufferAddress = *(char **)(a1 + 2488);
    else
      BufferAddress = (char *)RxLowIoGetBufferAddress(*(PRX_CONTEXT *)(a1 + 48));
    if ( *(_QWORD *)(a1 + 2456) )
      v21 = &BufferAddress[*(unsigned int *)(*(_QWORD *)(a1 + 2464) + 8LL)];
    else
      v21 = BufferAddress;
    v19 = &v21[*(unsigned int *)(a2 + 1392)];
  }
  if ( *(_QWORD *)(a1 + 1032) )
    memmove(v19, *(const void **)(a2 + 712), *(unsigned int *)(v13 + 8));
  if ( v7 )
  {
    if ( *v7 == 1 )
    {
      v15 = SmbCryptoDecryptRdmaPayload(
              *(_QWORD *)(*(_QWORD *)(a1 + 96) + 536LL),
              v7 + 4,
              (unsigned __int16)v7[1],
              (char *)v7 + (unsigned __int16)v7[1] + 8,
              (unsigned __int16)v7[2],
              v19,
              *(_DWORD *)(v13 + 8));
      if ( (v15 & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids, a1, v15);
        }
        return v15;
      }
    }
    else
    {
      if ( *v7 != 2 )
        return (unsigned int)-1073741595;
      if ( (*(_DWORD *)(a2 + 4) & 0x1000) == 0 )
      {
        v15 = -1073741629;
        Smb2LkmdTelCollectParsingFailureReadHelper(a2, a1, 10);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qqD(
            WPP_GLOBAL_Control->AttachedDevice,
            34,
            WPP_a0b49660c994371bf323b193efb7fcea_Traceguids,
            a1,
            a2,
            -1073741629);
        }
        return v15;
      }
      v15 = Smb2ValidateIncomingSignatureForRdmaBuffer(a2, v7, v19, *(unsigned int *)(v13 + 8));
      if ( (v15 & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            35,
            WPP_a0b49660c994371bf323b193efb7fcea_Traceguids,
            a1,
            *(_DWORD *)(a1 + 68),
            v15);
        }
        return v15;
      }
    }
    return 0;
  }
  if ( !v14 )
    return 0;
  if ( !*(_DWORD *)(v13 + 8) )
    return 0;
  v22 = *(_DWORD *)(a2 + 4);
  if ( (v22 & 0x8000) == 0 && (v22 & 0x1000) == 0 )
    return 0;
  v15 = -1073741629;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v17 = 36;
    goto LABEL_8;
  }
  return v15;
}

```

## disassembly

```asm
0x14002da60  mov     rax, rsp
0x14002da63  push    rbx
0x14002da64  push    rbp
0x14002da65  push    rsi
0x14002da66  push    rdi
0x14002da67  push    r12
0x14002da69  push    r13
0x14002da6b  push    r14
0x14002da6d  push    r15
0x14002da6f  sub     rsp, 58h
0x14002da73  mov     rbx, rcx
0x14002da76  xor     r14d, r14d
0x14002da79  mov     rcx, [rcx+58h]
0x14002da7d  mov     rdi, r9
0x14002da80  mov     r15d, r8d
0x14002da83  mov     [rax-58h], r14
0x14002da87  mov     rsi, rdx
0x14002da8a  mov     [rax+8], r14d
0x14002da8e  mov     rcx, [rcx+1A8h]
0x14002da95  call    cs:__imp_MRxSmbDetermineDdpSecurity
0x14002da9c  nop     dword ptr [rax+rax+00h]
0x14002daa1  mov     rbp, [rsp+98h+arg_28]
0x14002daa9  lea     r13d, [r14+1]
0x14002daad  mov     r12b, al
0x14002dab0  test    [rbp+0Ch], r13b
0x14002dab4  jnz     short loc_14002DABE
0x14002dab6  xor     r15d, r15d
0x14002dab9  jmp     loc_14002DB71
0x14002dabe  mov     rax, [rsp+98h+arg_20]
0x14002dac6  lea     rdx, [rsp+98h+arg_0]
0x14002dace  mov     [rsp+98h+var_60], rbp
0x14002dad3  lea     rcx, [rsp+98h+var_58]
0x14002dad8  mov     [rsp+98h+var_68], rax
0x14002dadd  mov     r9, rsi
0x14002dae0  mov     [rsp+98h+var_70], rdi
0x14002dae5  mov     r8, rbx
0x14002dae8  mov     dword ptr [rsp+98h+var_78], r15d
0x14002daed  call    Smb2Read_ValidateRdmaTransforms
0x14002daf2  xor     r15d, r15d
0x14002daf5  mov     edi, eax
0x14002daf7  test    eax, eax
0x14002daf9  js      loc_14002DDC2
0x14002daff  cmp     [rbx+408h], r15
0x14002db06  jnz     short loc_14002DB6C
0x14002db08  lea     r8d, [r15+9]
0x14002db0c  mov     rdx, rbx
0x14002db0f  mov     rcx, rsi
0x14002db12  mov     edi, 0C00000C3h
0x14002db17  call    Smb2LkmdTelCollectParsingFailureReadHelper
0x14002db1c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002db23  lea     rax, WPP_GLOBAL_Control
0x14002db2a  cmp     rcx, rax
0x14002db2d  jz      loc_14002DDC2
0x14002db33  mov     eax, [rcx+2Ch]
0x14002db36  test    r13b, al
0x14002db39  jz      loc_14002DDC2
0x14002db3f  cmp     [rcx+29h], r13b
0x14002db43  jb      loc_14002DDC2
0x14002db49  lea     edx, [r15+20h]
0x14002db4d  mov     eax, [rbx+44h]
0x14002db50  mov     dword ptr [rsp+98h+var_78], eax
0x14002db54  mov     rcx, [rcx+18h]
0x14002db58  lea     r8, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids
0x14002db5f  mov     r9, rbx
0x14002db62  call    WPP_SF_qD
0x14002db67  jmp     loc_14002DDC2
0x14002db6c  mov     r14, [rsp+98h+var_58]
0x14002db71  mov     rax, [rbx+400h]
0x14002db78  test    rax, rax
0x14002db7b  jz      short loc_14002DB8C
0x14002db7d  mov     edi, [rsi+570h]
0x14002db83  and     rax, 0FFFFFFFFFFFFFFF8h
0x14002db87  add     rdi, rax
0x14002db8a  jmp     short loc_14002DBD2
0x14002db8c  cmp     [rbx+998h], r15
0x14002db93  jz      short loc_14002DB9E
0x14002db95  mov     rax, [rbx+9B8h]
0x14002db9c  jmp     short loc_14002DBAE
0x14002db9e  mov     rcx, [rbx+30h]; RxContext
0x14002dba2  call    cs:__imp_RxLowIoGetBufferAddress
0x14002dba9  nop     dword ptr [rax+rax+00h]
0x14002dbae  cmp     [rbx+998h], r15
0x14002dbb5  jz      short loc_14002DBC6
0x14002dbb7  mov     rcx, [rbx+9A0h]
0x14002dbbe  mov     edx, [rcx+8]
0x14002dbc1  add     rdx, rax
0x14002dbc4  jmp     short loc_14002DBC9
0x14002dbc6  mov     rdx, rax
0x14002dbc9  mov     edi, [rsi+570h]
0x14002dbcf  add     rdi, rdx
0x14002dbd2  cmp     [rbx+408h], r15
0x14002dbd9  jz      short loc_14002DBEE
0x14002dbdb  mov     r8d, [rbp+8]; Size
0x14002dbdf  mov     rcx, rdi; void *
0x14002dbe2  mov     rdx, [rsi+2C8h]; Src
0x14002dbe9  call    memmove
0x14002dbee  test    r14, r14
0x14002dbf1  jz      loc_14002DD75
0x14002dbf7  movzx   eax, word ptr [r14]
0x14002dbfb  cmp     r13w, ax
0x14002dbff  jnz     loc_14002DC87
0x14002dc05  movzx   r8d, word ptr [r14+2]
0x14002dc0a  lea     rdx, [r14+8]
0x14002dc0e  mov     rcx, [rbx+60h]
0x14002dc12  mov     eax, [rbp+8]
0x14002dc15  movzx   r10d, word ptr [r14+4]
0x14002dc1a  mov     dword ptr [rsp+98h+var_68], eax
0x14002dc1e  lea     r9, [r8+8]
0x14002dc22  mov     rcx, [rcx+218h]
0x14002dc29  add     r9, r14
0x14002dc2c  mov     [rsp+98h+var_70], rdi
0x14002dc31  mov     dword ptr [rsp+98h+var_78], r10d
0x14002dc36  call    cs:__imp_SmbCryptoDecryptRdmaPayload
0x14002dc3d  nop     dword ptr [rax+rax+00h]
0x14002dc42  mov     edi, eax
0x14002dc44  test    eax, eax
0x14002dc46  jns     loc_14002DDBF
0x14002dc4c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dc53  lea     rax, WPP_GLOBAL_Control
0x14002dc5a  cmp     rcx, rax
0x14002dc5d  jz      loc_14002DDC2
0x14002dc63  mov     eax, [rcx+2Ch]
0x14002dc66  test    r13b, al
0x14002dc69  jz      loc_14002DDC2
0x14002dc6f  cmp     [rcx+29h], r13b
0x14002dc73  jb      loc_14002DDC2
0x14002dc79  mov     edx, 21h ; '!'
0x14002dc7e  mov     dword ptr [rsp+98h+var_78], edi
0x14002dc82  jmp     loc_14002DB54
0x14002dc87  mov     ecx, 2
0x14002dc8c  cmp     cx, ax
0x14002dc8f  jnz     loc_14002DD6E
0x14002dc95  test    dword ptr [rsi+4], 1000h
0x14002dc9c  mov     rcx, rsi
0x14002dc9f  jnz     short loc_14002DD0B
0x14002dca1  mov     r8d, 0Ah
0x14002dca7  mov     rdx, rbx
0x14002dcaa  mov     edi, 0C00000C3h
0x14002dcaf  call    Smb2LkmdTelCollectParsingFailureReadHelper
0x14002dcb4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dcbb  lea     rax, WPP_GLOBAL_Control
0x14002dcc2  cmp     rcx, rax
0x14002dcc5  jz      loc_14002DDC2
0x14002dccb  mov     eax, [rcx+2Ch]
0x14002dcce  test    r13b, al
0x14002dcd1  jz      loc_14002DDC2
0x14002dcd7  cmp     [rcx+29h], r13b
0x14002dcdb  jb      loc_14002DDC2
0x14002dce1  mov     rcx, [rcx+18h]
0x14002dce5  lea     r8, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids
0x14002dcec  mov     edx, 22h ; '"'
0x14002dcf1  mov     dword ptr [rsp+98h+var_70], 0C00000C3h
0x14002dcf9  mov     r9, rbx
0x14002dcfc  mov     [rsp+98h+var_78], rsi
0x14002dd01  call    WPP_SF_qqD
0x14002dd06  jmp     loc_14002DDC2
0x14002dd0b  mov     r9d, [rbp+8]
0x14002dd0f  mov     r8, rdi
0x14002dd12  mov     rdx, r14
0x14002dd15  call    Smb2ValidateIncomingSignatureForRdmaBuffer
0x14002dd1a  mov     edi, eax
0x14002dd1c  test    eax, eax
0x14002dd1e  jns     loc_14002DDBF
0x14002dd24  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dd2b  lea     rax, WPP_GLOBAL_Control
0x14002dd32  cmp     rcx, rax
0x14002dd35  jz      loc_14002DDC2
0x14002dd3b  mov     eax, [rcx+2Ch]
0x14002dd3e  test    r13b, al
0x14002dd41  jz      short loc_14002DDC2
0x14002dd43  cmp     [rcx+29h], r13b
0x14002dd47  jb      short loc_14002DDC2
0x14002dd49  mov     eax, [rbx+44h]
0x14002dd4c  lea     r8, WPP_a0b49660c994371bf323b193efb7fcea_Traceguids
0x14002dd53  mov     rcx, [rcx+18h]
0x14002dd57  mov     edx, 23h ; '#'
0x14002dd5c  mov     dword ptr [rsp+98h+var_70], edi
0x14002dd60  mov     r9, rbx
0x14002dd63  mov     dword ptr [rsp+98h+var_78], eax
0x14002dd67  call    WPP_SF_qDD
0x14002dd6c  jmp     short loc_14002DDC2
0x14002dd6e  mov     edi, 0C00000E5h
0x14002dd73  jmp     short loc_14002DDC2
0x14002dd75  test    r12b, r12b
0x14002dd78  jz      short loc_14002DDBF
0x14002dd7a  cmp     [rbp+8], r15d
0x14002dd7e  jbe     short loc_14002DDBF
0x14002dd80  mov     eax, [rsi+4]
0x14002dd83  bt      eax, 0Fh
0x14002dd87  jb      short loc_14002DD8F
0x14002dd89  bt      eax, 0Ch
0x14002dd8d  jnb     short loc_14002DDBF
0x14002dd8f  mov     edi, 0C00000C3h
0x14002dd94  mov     rcx, cs:WPP_GLOBAL_Control
0x14002dd9b  lea     rax, WPP_GLOBAL_Control
0x14002dda2  cmp     rcx, rax
0x14002dda5  jz      short loc_14002DDC2
0x14002dda7  mov     eax, [rcx+2Ch]
0x14002ddaa  test    r13b, al
0x14002ddad  jz      short loc_14002DDC2
0x14002ddaf  cmp     [rcx+29h], r13b
0x14002ddb3  jb      short loc_14002DDC2
0x14002ddb5  mov     edx, 24h ; '$'
0x14002ddba  jmp     loc_14002DB4D
0x14002ddbf  mov     edi, r15d
0x14002ddc2  mov     eax, edi
0x14002ddc4  add     rsp, 58h
0x14002ddc8  pop     r15
0x14002ddca  pop     r14
0x14002ddcc  pop     r13
0x14002ddce  pop     r12
0x14002ddd0  pop     rdi
0x14002ddd1  pop     rsi
0x14002ddd2  pop     rbp
0x14002ddd3  pop     rbx
0x14002ddd4  retn
```
