# CscEnpWriteAttributesInternal

- ea: `0x140082ccc`
- end: `0x14008305b`
- name: `CscEnpWriteAttributesInternal`
- size: `911`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `11`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000bd4c`
- `0x140013f10`
- `0x14001463c`
- `0x1400176c4`
- `0x140018344`
- `0x14002a61c`
- `0x140046aac`
- `0x140048450`
- `0x1400593dc`
- `0x14005db10`
- `0x1400829e0`

## callees

- `0x14000f6a8`
- `0x14000fc60`
- `0x14000fcd0`
- `0x1400134d4`
- `0x140014de0`
- `0x1400190ec`
- `0x14002cad0`
- `0x14002f010`
- `0x14002f440`
- `0x14005c44c`
- `0x1400829e0`
- `0x140082ccc`
- `0x140083064`
- `0x140083298`

## import_xrefs

- `ntoskrnl!RtlInitializeBitMap` at `0x140082e99`
- `ntoskrnl!RtlInitializeBitMap` at `0x140082e99`
- `ntoskrnl!RtlSetBit` at `0x140082ed0`
- `ntoskrnl!RtlSetBit` at `0x140082ed0`

## pseudocode

```c
__int64 __fastcall CscEnpWriteAttributesInternal(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  int updated; // esi
  __int64 v15; // r12
  int v16; // edi
  int v17; // ecx
  __int16 v18; // di
  unsigned __int16 i; // si
  __int16 v20; // dx
  bool v21; // zf
  _DWORD *v22; // rdx
  int v23; // ecx
  int v24; // r9d
  __int64 v25; // r8
  int v26; // edx
  int v27; // eax
  _BYTE v29[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  struct _RTL_BITMAP BitMapHeader; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+78h] [rbp-88h]
  ULONG v34[44]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v35[16]; // [rsp+130h] [rbp+30h] BYREF

  v30 = a6;
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = a7;
  v33 = a8;
  updated = 0;
  v32 = a9;
  memset(v34, 0, 0xA8u);
  v29[0] = 0;
  if ( a2 )
  {
    v15 = v30;
    updated = CscEnpWriteAttributesInternal_UpdateEa(
                a1,
                a2,
                a4,
                a5,
                v30,
                *(__int64 *)&BitMapHeader.SizeOfBitMap,
                v33,
                v32,
                a10);
    if ( updated < 0 )
    {
      v16 = 5974;
      goto LABEL_39;
    }
    if ( a4 )
    {
      if ( (((unsigned __int8)(*(_DWORD *)a4 >> 4) ^ (unsigned __int8)(*(_DWORD *)(a1 + 192) >> 4)) & 1) != 0 )
      {
        updated = CscEnpChangeChildCountEx(*(_QWORD *)(a1 + 24), a4, 16);
        if ( updated < 0 )
        {
          v16 = 5994;
          goto LABEL_39;
        }
      }
      v17 = *(_DWORD *)(a1 + 196);
      if ( (v17 & 0x10) == 0 && (*(_DWORD *)(a4 + 4) & 1) != 0 && (v17 & 1) == 0 )
      {
        updated = CscEnpUpdateAncestorDfsLinkStatus(*(_QWORD *)(a1 + 24));
        if ( updated < 0 )
        {
          v16 = 6006;
          goto LABEL_39;
        }
      }
    }
  }
  else
  {
    v15 = v30;
  }
  if ( a3 )
  {
    v30 = *(_QWORD *)(a1 + 196);
    CscEnpOverrideShareInformationIfNeeded(a1, &v30);
    CscEnpFieldUpdateAcquireShared(a1);
    CscEnpFillPqInfo((unsigned int)v34, a1, a4, a5, v15, *(__int64 *)&BitMapHeader.SizeOfBitMap, v33, v32);
    LODWORD(BitMapHeader.Buffer) = 0;
    *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
    v18 = 8;
    RtlInitializeBitMap(&BitMapHeader, &v34[40], 8u);
    for ( i = 0; i < 8u; ++i )
    {
      v20 = *(_WORD *)(a1 + 8LL * i + 446);
      if ( !v20 )
        break;
      v21 = (*(_BYTE *)(a1 + 8LL * i + 453) & 1) == 0;
      *((_WORD *)&v34[36] + i) = v20;
      if ( !v21 )
        RtlSetBit(&BitMapHeader, i);
    }
    if ( *(_WORD *)(a1 + 264) )
      v18 = 12;
    v22 = (_DWORD *)(a1 + 192);
    if ( a4 )
    {
      if ( (*v22 & 0x10000) != 0 && !_bittest((const signed __int32 *)a4, 0x10u) )
        v18 |= 1u;
      v23 = HIDWORD(v30);
      if ( HIDWORD(v30) != *(_DWORD *)(a4 + 8) && (*v22 & 0x4000) != 0 )
      {
        v18 |= 2u;
        v23 = *(_DWORD *)(a4 + 8);
      }
    }
    else
    {
      v23 = HIDWORD(v30);
    }
    updated = CscEnpComputePqQueueCommand(v23, *v22, LOWORD(v34[18]), 2, v18, (__int64)v35, (__int64)v29);
    if ( updated >= 0 )
    {
      v25 = *(_QWORD *)(a1 + 136);
      v26 = *(_DWORD *)(a1 + 128);
      if ( a3 == v25 )
      {
        LOBYTE(v24) = *(_BYTE *)(a1 + 442);
        v27 = CscPqUpdateEntryEx(
                *(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL),
                v26,
                v25,
                v24,
                (__int64)v34,
                (unsigned __int64)v35 & -(__int64)(v29[0] != 0));
      }
      else
      {
        v27 = CscPqChangeFileIdEntry(
                *(_QWORD *)(*(_QWORD *)(a1 + 8) + 48LL),
                v26,
                v25,
                a3,
                (__int64)v34,
                (unsigned __int64)v35 & -(__int64)(v29[0] != 0));
      }
      updated = v27;
      v16 = 0;
      if ( v27 < 0 )
        v16 = 6104;
    }
    else
    {
      v16 = 6071;
    }
    CscEnpFieldUpdateRelease(a1);
  }
  else
  {
    v16 = 0;
  }
LABEL_39:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      49,
      WPP_2d57263f6f6237979220aa59cf47311d_Traceguids,
      (unsigned int)updated,
      v16);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140082ccc  push    rbp
0x140082cce  push    rbx
0x140082ccf  push    rsi
0x140082cd0  push    rdi
0x140082cd1  push    r12
0x140082cd3  push    r13
0x140082cd5  push    r14
0x140082cd7  push    r15
0x140082cd9  lea     rbp, [rsp-58h]
0x140082cde  sub     rsp, 158h
0x140082ce5  mov     rax, cs:__security_cookie
0x140082cec  xor     rax, rsp
0x140082cef  mov     [rbp+90h+var_50], rax
0x140082cf3  mov     rax, [rbp+90h+arg_28]
0x140082cfa  mov     r15, r8
0x140082cfd  mov     r13, [rbp+90h+arg_20]
0x140082d04  mov     rdi, rdx
0x140082d07  mov     r12, [rbp+90h+arg_48]
0x140082d0e  mov     rbx, rcx
0x140082d11  mov     [rsp+190h+var_138], rax
0x140082d16  lea     rcx, [rbp+90h+var_110]; void *
0x140082d1a  mov     rax, [rbp+90h+arg_30]
0x140082d21  xor     edx, edx; Val
0x140082d23  mov     qword ptr [rsp+190h+BitMapHeader.SizeOfBitMap], rax
0x140082d28  mov     r8d, 0A8h; Size
0x140082d2e  mov     rax, [rbp+90h+arg_38]
0x140082d35  mov     r14, r9
0x140082d38  mov     [rsp+190h+var_118], rax
0x140082d3d  xor     esi, esi
0x140082d3f  mov     rax, [rbp+90h+arg_40]
0x140082d46  mov     [rsp+190h+var_120], rax
0x140082d4b  call    memset
0x140082d50  mov     [rsp+190h+var_140], sil
0x140082d55  test    rdi, rdi
0x140082d58  jz      loc_140082E1A
0x140082d5e  mov     rax, [rsp+190h+var_120]
0x140082d63  mov     r9, r13
0x140082d66  mov     [rsp+190h+var_150], r12
0x140082d6b  mov     r8, r14
0x140082d6e  mov     r12, [rsp+190h+var_138]
0x140082d73  mov     rdx, rdi
0x140082d76  mov     [rsp+190h+var_158], rax
0x140082d7b  mov     rcx, rbx
0x140082d7e  mov     rax, [rsp+190h+var_118]
0x140082d83  mov     [rsp+190h+var_160], rax
0x140082d88  mov     rax, qword ptr [rsp+190h+BitMapHeader.SizeOfBitMap]
0x140082d8d  mov     [rsp+190h+var_168], rax
0x140082d92  mov     [rsp+190h+var_170], r12
0x140082d97  call    CscEnpWriteAttributesInternal_UpdateEa
0x140082d9c  mov     esi, eax
0x140082d9e  test    eax, eax
0x140082da0  jns     short loc_140082DAC
0x140082da2  mov     edi, 1756h
0x140082da7  jmp     loc_140083000
0x140082dac  test    r14, r14
0x140082daf  jz      short loc_140082E1F
0x140082db1  mov     ecx, [rbx+0C0h]
0x140082db7  mov     eax, [r14]
0x140082dba  shr     ecx, 4
0x140082dbd  shr     eax, 4
0x140082dc0  xor     cl, al
0x140082dc2  test    cl, 1
0x140082dc5  jz      short loc_140082DE9
0x140082dc7  mov     rcx, [rbx+18h]
0x140082dcb  mov     r8d, 10h
0x140082dd1  mov     rdx, r14
0x140082dd4  call    CscEnpChangeChildCountEx
0x140082dd9  mov     esi, eax
0x140082ddb  test    eax, eax
0x140082ddd  jns     short loc_140082DE9
0x140082ddf  mov     edi, 176Ah
0x140082de4  jmp     loc_140083000
0x140082de9  mov     ecx, [rbx+0C4h]
0x140082def  test    cl, 10h
0x140082df2  jnz     short loc_140082E1F
0x140082df4  mov     eax, [r14+4]
0x140082df8  test    al, 1
0x140082dfa  jz      short loc_140082E1F
0x140082dfc  test    cl, 1
0x140082dff  jnz     short loc_140082E1F
0x140082e01  mov     rcx, [rbx+18h]
0x140082e05  call    CscEnpUpdateAncestorDfsLinkStatus
0x140082e0a  mov     esi, eax
0x140082e0c  test    eax, eax
0x140082e0e  jns     short loc_140082E1F
0x140082e10  mov     edi, 1776h
0x140082e15  jmp     loc_140083000
0x140082e1a  mov     r12, [rsp+190h+var_138]
0x140082e1f  test    r15, r15
0x140082e22  jz      loc_140082FFE
0x140082e28  mov     rax, [rbx+0C4h]
0x140082e2f  lea     rdx, [rsp+190h+var_138]
0x140082e34  mov     rcx, rbx
0x140082e37  mov     [rsp+190h+var_138], rax
0x140082e3c  call    CscEnpOverrideShareInformationIfNeeded
0x140082e41  mov     rcx, rbx
0x140082e44  call    CscEnpFieldUpdateAcquireShared
0x140082e49  mov     rax, [rsp+190h+var_120]
0x140082e4e  lea     rcx, [rbp+90h+var_110]
0x140082e52  mov     [rsp+190h+var_158], rax
0x140082e57  mov     r9, r13
0x140082e5a  mov     rax, [rsp+190h+var_118]
0x140082e5f  mov     r8, r14
0x140082e62  mov     [rsp+190h+var_160], rax
0x140082e67  mov     rdx, rbx
0x140082e6a  mov     rax, qword ptr [rsp+190h+BitMapHeader.SizeOfBitMap]
0x140082e6f  mov     [rsp+190h+var_168], rax
0x140082e74  mov     [rsp+190h+var_170], r12
0x140082e79  call    CscEnpFillPqInfo
0x140082e7e  xor     eax, eax
0x140082e80  lea     rdx, [rbp+90h+BitMapBuffer]; BitMapBuffer
0x140082e84  mov     qword ptr [rsp+190h+BitMapHeader+4], rax
0x140082e89  lea     rcx, [rsp+190h+BitMapHeader]; BitMapHeader
0x140082e8e  mov     qword ptr [rsp+190h+BitMapHeader.SizeOfBitMap], rax
0x140082e93  lea     edi, [rax+8]
0x140082e96  mov     r8d, edi; SizeOfBitMap
0x140082e99  call    cs:__imp_RtlInitializeBitMap
0x140082ea0  nop     dword ptr [rax+rax+00h]
0x140082ea5  xor     esi, esi
0x140082ea7  movzx   ecx, si
0x140082eaa  xor     eax, eax
0x140082eac  movzx   edx, word ptr [rbx+rcx*8+1BEh]
0x140082eb4  cmp     ax, dx
0x140082eb7  jz      short loc_140082EE4
0x140082eb9  test    byte ptr [rbx+rcx*8+1C5h], 1
0x140082ec1  mov     [rbp+rcx*2+90h+var_80], dx
0x140082ec6  jz      short loc_140082EDC
0x140082ec8  movzx   edx, si; BitNumber
0x140082ecb  lea     rcx, [rsp+190h+BitMapHeader]; BitMapHeader
0x140082ed0  call    cs:__imp_RtlSetBit
0x140082ed7  nop     dword ptr [rax+rax+00h]
0x140082edc  inc     si
0x140082edf  cmp     si, di
0x140082ee2  jb      short loc_140082EA7
0x140082ee4  movzx   eax, word ptr [rbx+108h]
0x140082eeb  movzx   ecx, ax
0x140082eee  shr     cx, 8
0x140082ef2  test    cl, cl
0x140082ef4  jnz     short loc_140082EFA
0x140082ef6  test    al, al
0x140082ef8  jz      short loc_140082EFF
0x140082efa  mov     edi, 0Ch
0x140082eff  lea     rdx, [rbx+0C0h]
0x140082f06  mov     r9d, 2
0x140082f0c  test    r14, r14
0x140082f0f  jz      short loc_140082F41
0x140082f11  mov     r8d, [rdx]
0x140082f14  bt      r8d, 10h
0x140082f19  jnb     short loc_140082F26
0x140082f1b  bt      dword ptr [r14], 10h
0x140082f20  jb      short loc_140082F26
0x140082f22  or      di, 1
0x140082f26  mov     eax, [r14+8]
0x140082f2a  mov     ecx, dword ptr [rsp+190h+var_138+4]
0x140082f2e  cmp     ecx, eax
0x140082f30  jz      short loc_140082F45
0x140082f32  bt      r8d, 0Eh
0x140082f37  jnb     short loc_140082F45
0x140082f39  or      di, r9w
0x140082f3d  mov     ecx, eax
0x140082f3f  jmp     short loc_140082F45
0x140082f41  mov     ecx, dword ptr [rsp+190h+var_138+4]
0x140082f45  movzx   r8d, [rbp+90h+var_C8]
0x140082f4a  lea     rax, [rsp+190h+var_140]
0x140082f4f  mov     edx, [rdx]
0x140082f51  mov     [rsp+190h+var_160], rax
0x140082f56  lea     rax, [rbp+90h+var_60]
0x140082f5a  mov     [rsp+190h+var_168], rax
0x140082f5f  mov     word ptr [rsp+190h+var_170], di
0x140082f64  call    CscEnpComputePqQueueCommand
0x140082f69  mov     esi, eax
0x140082f6b  test    eax, eax
0x140082f6d  jns     short loc_140082F76
0x140082f6f  mov     edi, 17B7h
0x140082f74  jmp     short loc_140082FF4
0x140082f76  mov     r8, [rbx+88h]
0x140082f7d  mov     al, [rsp+190h+var_140]
0x140082f81  mov     edx, [rbx+80h]
0x140082f87  cmp     r15, r8
0x140082f8a  jz      short loc_140082FB8
0x140082f8c  neg     al
0x140082f8e  mov     r9, r15
0x140082f91  lea     rax, [rbp+90h+var_60]
0x140082f95  sbb     rcx, rcx
0x140082f98  and     rcx, rax
0x140082f9b  mov     rax, [rbx+8]
0x140082f9f  mov     [rsp+190h+var_168], rcx
0x140082fa4  lea     rcx, [rbp+90h+var_110]
0x140082fa8  mov     [rsp+190h+var_170], rcx
0x140082fad  mov     rcx, [rax+30h]
0x140082fb1  call    CscPqChangeFileIdEntry
0x140082fb6  jmp     short loc_140082FE6
0x140082fb8  mov     r9b, [rbx+1BAh]
0x140082fbf  neg     al
0x140082fc1  lea     rax, [rbp+90h+var_60]
0x140082fc5  sbb     rcx, rcx
0x140082fc8  and     rcx, rax
0x140082fcb  mov     rax, [rbx+8]
0x140082fcf  mov     [rsp+190h+var_168], rcx
0x140082fd4  lea     rcx, [rbp+90h+var_110]
0x140082fd8  mov     [rsp+190h+var_170], rcx
0x140082fdd  mov     rcx, [rax+30h]
0x140082fe1  call    CscPqUpdateEntryEx
0x140082fe6  mov     esi, eax
0x140082fe8  xor     edi, edi
0x140082fea  test    esi, esi
0x140082fec  mov     eax, 17D8h
0x140082ff1  cmovs   edi, eax
0x140082ff4  mov     rcx, rbx
0x140082ff7  call    CscEnpFieldUpdateRelease
0x140082ffc  jmp     short loc_140083000
0x140082ffe  xor     edi, edi
0x140083000  mov     rcx, cs:WPP_GLOBAL_Control
0x140083007  lea     rax, WPP_GLOBAL_Control
0x14008300e  cmp     rcx, rax
0x140083011  jz      short loc_140083038
0x140083013  test    dword ptr [rcx+2Ch], 40000h
0x14008301a  jz      short loc_140083038
0x14008301c  mov     rcx, [rcx+18h]
0x140083020  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x140083027  mov     edx, 31h ; '1'
0x14008302c  mov     dword ptr [rsp+190h+var_170], edi
0x140083030  mov     r9d, esi
0x140083033  call    WPP_SF_Dd
0x140083038  mov     eax, esi
0x14008303a  mov     rcx, [rbp+90h+var_50]
0x14008303e  xor     rcx, rsp; StackCookie
0x140083041  call    __security_check_cookie
0x140083046  add     rsp, 158h
0x14008304d  pop     r15
0x14008304f  pop     r14
0x140083051  pop     r13
0x140083053  pop     r12
0x140083055  pop     rdi
0x140083056  pop     rsi
0x140083057  pop     rbx
0x140083058  pop     rbp
0x140083059  retn
```
