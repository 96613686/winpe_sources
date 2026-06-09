# QuicVersionNegotiationExtEncodeVersionInfo

- ea: `0x14002a180`
- end: `0x14002a472`
- name: `QuicVersionNegotiationExtEncodeVersionInfo`
- size: `754`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000577c`

## callees

- `0x14002a180`
- `0x14002a478`
- `0x14003c8e0`
- `0x14003cb00`
- `0x14003ec10`
- `0x14003ed00`
- `0x14003fea4`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14002a277`
- `ntoskrnl!_snprintf_s` at `0x14002a3ea`
- `ntoskrnl!_snprintf_s` at `0x14002a277`
- `ntoskrnl!_snprintf_s` at `0x14002a3ea`
- `ntoskrnl!ExAllocatePool2` at `0x14002a1fc`
- `ntoskrnl!ExAllocatePool2` at `0x14002a316`
- `ntoskrnl!ExAllocatePool2` at `0x14002a1fc`
- `ntoskrnl!ExAllocatePool2` at `0x14002a316`

## string_xrefs

- `0x14002a3c4`: `Client VI Encoded: Current Ver:%x Prev Ver:%x Compat Ver Count:%u`

## pseudocode

```c
_DWORD *__fastcall QuicVersionNegotiationExtEncodeVersionInfo(__int64 a1, unsigned int *a2)
{
  unsigned int v2; // edi
  __int64 *v4; // rbp
  unsigned int v5; // r15d
  __int64 v6; // rdx
  __int64 v7; // rcx
  _DWORD *Pool2; // rsi
  int v9; // ecx
  int v10; // r9d
  __int64 v11; // rcx
  int v12; // eax
  _DWORD *v13; // r14
  unsigned int v14; // edi
  _DWORD *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v19; // rdx
  int v20; // ecx
  int v21; // ecx
  int v22; // eax
  __int64 v23; // rcx
  int v24; // r9d
  unsigned int v25; // [rsp+40h] [rbp-D8h] BYREF
  unsigned int *v26; // [rsp+48h] [rbp-D0h]
  char DstBuf[128]; // [rsp+50h] [rbp-C8h] BYREF

  *a2 = 0;
  v2 = 4;
  v26 = a2;
  if ( *(_DWORD *)a1 == 4 )
  {
    if ( _bittest64(&qword_14005C4B0, 0x1Eu) )
    {
      v4 = *(__int64 **)(qword_14005C4B8 + 16);
      v2 = *(_DWORD *)(qword_14005C4B8 + 32);
    }
    else
    {
      v4 = DefaultSupportedVersionsList;
    }
    v5 = 4 * v2 + 4;
    Pool2 = (_DWORD *)ExAllocatePool2(66, v5, 842294097);
    if ( !Pool2 )
    {
      if ( (Microsoft_QuicEnableBits & 2) != 0 )
        McTemplateU0sx_EtwWriteTransfer(v7, v6, "Server Version Info", 4 * v2 + 4);
      return 0;
    }
    *Pool2 = *(_DWORD *)(a1 + 3636);
    memmove(Pool2 + 1, v4, 4LL * v2);
    if ( byte_14005C48B < 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Server VI Encoded: Chosen Ver:%x Other Ver Count:%u",
        *(_DWORD *)(a1 + 3636),
        v2);
      McTemplateU0ps_EtwWriteTransfer(v11, (const EVENT_DESCRIPTOR *)QuicConnLogInfo, a1, DstBuf);
    }
    if ( (byte_14005C489 & 0x40) != 0 )
    {
      LOBYTE(v10) = 4 * v2;
      McTemplateU0pubr1_EtwWriteTransfer(v9, (unsigned int)QuicConnVNEOtherVersionList, a1, v10, (__int64)(Pool2 + 1));
    }
  }
  else
  {
    v12 = *(_DWORD *)(a1 + 96);
    v13 = (_DWORD *)(a1 + 3636);
    v14 = 0;
    v25 = 0;
    if ( (v12 & 0x40000000) != 0 )
    {
      QuicVersionNegotiationExtGenerateCompatibleVersionsList(
        *v13,
        *(_QWORD *)(*(_QWORD *)(a1 + 104) + 16LL),
        *(_DWORD *)(*(_QWORD *)(a1 + 104) + 32LL),
        0,
        (__int64)&v25);
      v14 = v25;
      v5 = v25 + 4;
    }
    else
    {
      v5 = 4 * dword_14005D930 + 4;
    }
    v15 = (_DWORD *)ExAllocatePool2(66, v5, 842294097);
    Pool2 = v15;
    if ( !v15 )
    {
      if ( (Microsoft_QuicEnableBits & 2) != 0 )
        McTemplateU0sx_EtwWriteTransfer(v17, v16, "Client Version Info", v5);
      return 0;
    }
    *v15 = *v13;
    if ( (*(_DWORD *)(a1 + 96) & 0x40000000) != 0 )
    {
      v19 = *(_QWORD *)(a1 + 104);
      v20 = *v13;
      v25 = v5 - 4;
      QuicVersionNegotiationExtGenerateCompatibleVersionsList(
        v20,
        *(_QWORD *)(v19 + 16),
        *(_DWORD *)(v19 + 32),
        (_DWORD)v15 + 4,
        (__int64)&v25);
    }
    else
    {
      memmove(v15 + 1, Src, 4LL * (unsigned int)dword_14005D930);
    }
    if ( byte_14005C48B < 0 )
    {
      if ( v14 )
        v22 = v14 >> 2;
      else
        v22 = dword_14005D930;
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Client VI Encoded: Current Ver:%x Prev Ver:%x Compat Ver Count:%u",
        *v13,
        *(_DWORD *)(a1 + 3880),
        v22);
      McTemplateU0ps_EtwWriteTransfer(v23, (const EVENT_DESCRIPTOR *)QuicConnLogInfo, a1, DstBuf);
    }
    if ( (byte_14005C489 & 0x40) != 0 )
    {
      if ( v14 )
        v24 = v14;
      else
        v24 = 4 * dword_14005D930;
      McTemplateU0pubr1_EtwWriteTransfer(v21, (unsigned int)QuicConnVNEOtherVersionList, a1, v24, (__int64)(Pool2 + 1));
    }
  }
  *v26 = v5;
  return Pool2;
}

```

## disassembly

```asm
0x14002a180  mov     [rsp+arg_10], rbx
0x14002a185  push    rbp
0x14002a186  push    rsi
0x14002a187  push    rdi
0x14002a188  push    r12
0x14002a18a  push    r13
0x14002a18c  push    r14
0x14002a18e  push    r15
0x14002a190  sub     rsp, 0E0h
0x14002a197  mov     rax, cs:__security_cookie
0x14002a19e  xor     rax, rsp
0x14002a1a1  mov     [rsp+118h+var_48], rax
0x14002a1a9  and     dword ptr [rdx], 0
0x14002a1ac  mov     edi, 4
0x14002a1b1  mov     rbx, rcx
0x14002a1b4  mov     [rsp+118h+var_D0], rdx
0x14002a1b9  cmp     [rcx], edi
0x14002a1bb  jnz     loc_14002A2B5
0x14002a1c1  bt      cs:qword_14005C4B0, 1Eh
0x14002a1ca  jnb     short loc_14002A1DC
0x14002a1cc  mov     rax, cs:qword_14005C4B8
0x14002a1d3  mov     rbp, [rax+10h]
0x14002a1d7  mov     edi, [rax+20h]
0x14002a1da  jmp     short loc_14002A1E3
0x14002a1dc  lea     rbp, DefaultSupportedVersionsList
0x14002a1e3  lea     r15d, ds:4[rdi*4]
0x14002a1eb  mov     r8d, 32346351h
0x14002a1f1  mov     edx, r15d
0x14002a1f4  mov     ecx, 42h ; 'B'
0x14002a1f9  mov     r14d, r15d
0x14002a1fc  call    cs:__imp_ExAllocatePool2
0x14002a203  nop     dword ptr [rax+rax+00h]
0x14002a208  mov     rsi, rax
0x14002a20b  test    rax, rax
0x14002a20e  jnz     short loc_14002A22C
0x14002a210  test    cs:Microsoft_QuicEnableBits, 2
0x14002a217  jz      loc_14002A342
0x14002a21d  mov     r9d, r14d
0x14002a220  lea     r8, aServerVersionI; "Server Version Info"
0x14002a227  jmp     loc_14002A33D
0x14002a22c  mov     eax, [rbx+0E34h]
0x14002a232  lea     r14, [rsi+4]
0x14002a236  mov     r8d, edi
0x14002a239  mov     rcx, r14; void *
0x14002a23c  shl     r8, 2; Size
0x14002a240  mov     rdx, rbp; Src
0x14002a243  mov     [rsi], eax
0x14002a245  call    memmove
0x14002a24a  mov     al, cs:byte_14005C48B
0x14002a250  test    al, al
0x14002a252  jns     short loc_14002A297
0x14002a254  mov     eax, [rbx+0E34h]
0x14002a25a  lea     r9, aServerViEncode; "Server VI Encoded: Chosen Ver:%x Other "...
0x14002a261  mov     [rsp+118h+var_F0], edi
0x14002a265  lea     rcx, [rsp+118h+DstBuf]; DstBuf
0x14002a26a  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002a26e  mov     dword ptr [rsp+118h+var_F8], eax
0x14002a272  mov     edx, 80h; SizeInBytes
0x14002a277  call    cs:__imp__snprintf_s
0x14002a27e  nop     dword ptr [rax+rax+00h]
0x14002a283  lea     r9, [rsp+118h+DstBuf]
0x14002a288  mov     r8, rbx
0x14002a28b  lea     rdx, QuicConnLogInfo
0x14002a292  call    McTemplateU0ps_EtwWriteTransfer
0x14002a297  test    cs:byte_14005C489, 40h
0x14002a29e  jz      loc_14002A43B
0x14002a2a4  shl     dil, 2
0x14002a2a8  mov     r9b, dil
0x14002a2ab  mov     [rsp+118h+var_F8], r14
0x14002a2b0  jmp     loc_14002A42C
0x14002a2b5  mov     eax, [rcx+60h]
0x14002a2b8  lea     r14, [rcx+0E34h]
0x14002a2bf  xor     edi, edi
0x14002a2c1  bt      rax, 1Eh
0x14002a2c6  mov     [rsp+118h+var_D8], edi
0x14002a2ca  jnb     short loc_14002A2F7
0x14002a2cc  mov     rdx, [rcx+68h]
0x14002a2d0  lea     rax, [rsp+118h+var_D8]
0x14002a2d5  mov     ecx, [r14]
0x14002a2d8  xor     r9d, r9d
0x14002a2db  mov     [rsp+118h+var_F8], rax
0x14002a2e0  mov     r8d, [rdx+20h]
0x14002a2e4  mov     rdx, [rdx+10h]
0x14002a2e8  call    QuicVersionNegotiationExtGenerateCompatibleVersionsList
0x14002a2ed  mov     edi, [rsp+118h+var_D8]
0x14002a2f1  lea     r15d, [rdi+4]
0x14002a2f5  jmp     short loc_14002A305
0x14002a2f7  mov     eax, cs:dword_14005D930
0x14002a2fd  lea     r15d, ds:4[rax*4]
0x14002a305  mov     r8d, 32346351h
0x14002a30b  mov     edx, r15d
0x14002a30e  mov     ecx, 42h ; 'B'
0x14002a313  mov     r13d, r15d
0x14002a316  call    cs:__imp_ExAllocatePool2
0x14002a31d  nop     dword ptr [rax+rax+00h]
0x14002a322  mov     rsi, rax
0x14002a325  test    rax, rax
0x14002a328  jnz     short loc_14002A349
0x14002a32a  test    cs:Microsoft_QuicEnableBits, 2
0x14002a331  jz      short loc_14002A342
0x14002a333  mov     r9d, r13d
0x14002a336  lea     r8, aClientVersionI; "Client Version Info"
0x14002a33d  call    McTemplateU0sx_EtwWriteTransfer
0x14002a342  xor     eax, eax
0x14002a344  jmp     loc_14002A446
0x14002a349  mov     eax, [r14]
0x14002a34c  lea     r13, [rsi+4]
0x14002a350  mov     [rsi], eax
0x14002a352  mov     eax, [rbx+60h]
0x14002a355  bt      rax, 1Eh
0x14002a35a  jnb     short loc_14002A38B
0x14002a35c  mov     rdx, [rbx+68h]
0x14002a360  mov     eax, esi
0x14002a362  mov     ecx, [r14]
0x14002a365  sub     eax, r13d
0x14002a368  add     eax, r15d
0x14002a36b  mov     r9, r13
0x14002a36e  mov     [rsp+118h+var_D8], eax
0x14002a372  lea     rax, [rsp+118h+var_D8]
0x14002a377  mov     r8d, [rdx+20h]
0x14002a37b  mov     rdx, [rdx+10h]
0x14002a37f  mov     [rsp+118h+var_F8], rax
0x14002a384  call    QuicVersionNegotiationExtGenerateCompatibleVersionsList
0x14002a389  jmp     short loc_14002A3A5
0x14002a38b  mov     r8d, cs:dword_14005D930
0x14002a392  mov     rcx, r13; void *
0x14002a395  mov     rdx, cs:Src; Src
0x14002a39c  shl     r8, 2; Size
0x14002a3a0  call    memmove
0x14002a3a5  mov     al, cs:byte_14005C48B
0x14002a3ab  test    al, al
0x14002a3ad  jns     short loc_14002A40A
0x14002a3af  test    edi, edi
0x14002a3b1  jnz     short loc_14002A3BB
0x14002a3b3  mov     eax, cs:dword_14005D930
0x14002a3b9  jmp     short loc_14002A3C0
0x14002a3bb  mov     eax, edi
0x14002a3bd  shr     eax, 2
0x14002a3c0  mov     [rsp+118h+var_E8], eax
0x14002a3c4  lea     r9, aClientViEncode; "Client VI Encoded: Current Ver:%x Prev "...
0x14002a3cb  mov     eax, [rbx+0F28h]
0x14002a3d1  lea     rcx, [rsp+118h+DstBuf]; DstBuf
0x14002a3d6  mov     [rsp+118h+var_F0], eax
0x14002a3da  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14002a3de  mov     eax, [r14]
0x14002a3e1  mov     edx, 80h; SizeInBytes
0x14002a3e6  mov     dword ptr [rsp+118h+var_F8], eax
0x14002a3ea  call    cs:__imp__snprintf_s
0x14002a3f1  nop     dword ptr [rax+rax+00h]
0x14002a3f6  lea     r9, [rsp+118h+DstBuf]
0x14002a3fb  mov     r8, rbx
0x14002a3fe  lea     rdx, QuicConnLogInfo
0x14002a405  call    McTemplateU0ps_EtwWriteTransfer
0x14002a40a  test    cs:byte_14005C489, 40h
0x14002a411  jz      short loc_14002A43B
0x14002a413  test    edi, edi
0x14002a415  jnz     short loc_14002A424
0x14002a417  mov     r9d, cs:dword_14005D930
0x14002a41e  shl     r9, 2
0x14002a422  jmp     short loc_14002A427
0x14002a424  mov     r9d, edi
0x14002a427  mov     [rsp+118h+var_F8], r13
0x14002a42c  mov     r8, rbx
0x14002a42f  lea     rdx, QuicConnVNEOtherVersionList
0x14002a436  call    McTemplateU0pubr1_EtwWriteTransfer
0x14002a43b  mov     rax, [rsp+118h+var_D0]
0x14002a440  mov     [rax], r15d
0x14002a443  mov     rax, rsi
0x14002a446  mov     rcx, [rsp+118h+var_48]
0x14002a44e  xor     rcx, rsp; StackCookie
0x14002a451  call    __security_check_cookie
0x14002a456  mov     rbx, [rsp+118h+arg_10]
0x14002a45e  add     rsp, 0E0h
0x14002a465  pop     r15
0x14002a467  pop     r14
0x14002a469  pop     r13
0x14002a46b  pop     r12
0x14002a46d  pop     rdi
0x14002a46e  pop     rsi
0x14002a46f  pop     rbp
0x14002a470  retn
```
