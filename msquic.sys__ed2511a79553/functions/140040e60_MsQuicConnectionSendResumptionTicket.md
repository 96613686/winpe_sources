# MsQuicConnectionSendResumptionTicket

- ea: `0x140040e60`
- end: `0x1400410c9`
- name: `MsQuicConnectionSendResumptionTicket`
- size: `617`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000c440`
- `0x14000c4b8`
- `0x140029ef0`
- `0x1400337e4`
- `0x14003cb00`
- `0x14003eca4`
- `0x14003ed00`
- `0x140040c2c`
- `0x140040e60`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140041046`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041046`
- `ntoskrnl!ExAllocatePool2` at `0x140040fc1`
- `ntoskrnl!ExAllocatePool2` at `0x140040fc1`

## string_xrefs

- `0x140040fea`: `Resumption data copy`

## pseudocode

```c
__int64 __fastcall MsQuicConnectionSendResumptionTicket(__int64 a1, __int64 a2, unsigned __int16 a3, const void *a4)
{
  size_t v4; // rbp
  int v6; // r15d
  unsigned int *v7; // rbx
  void *v8; // rsi
  void *Pool2; // rax
  __int64 v10; // rdx
  unsigned int v11; // ebx
  __int64 v12; // rax

  v4 = a3;
  v6 = a2;
  v7 = (unsigned int *)a1;
  v8 = 0;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 17, a1);
  if ( (unsigned __int16)v4 > 0x3E8u || !a4 && (_WORD)v4 || v6 > 1 || !v7 )
    goto LABEL_37;
  a1 = *v7;
  if ( (unsigned int)(a1 - 3) > 1 )
  {
    if ( (_DWORD)a1 != 5 )
    {
LABEL_37:
      v11 = -1073741811;
      goto LABEL_38;
    }
    if ( (v7[23] & 8) != 0 )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 563, "!Stream->Flags.HandleClosed");
    if ( (v7[23] & 0x40) != 0 )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 564, "!Stream->Flags.Freed");
    v7 = (unsigned int *)*((_QWORD *)v7 + 9);
  }
  if ( (v7[63] & 0x40) != 0 )
  {
    if ( (*((_BYTE *)v7 + 249) & 4) != 0 )
    {
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 571, "!Connection->State.Freed");
      __int2c();
    }
    if ( (v7[63] & 0x40) != 0 && (*((_BYTE *)v7 + 249) & 2) != 0 )
    {
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 572, "!Connection->State.HandleClosed");
      __int2c();
    }
  }
  if ( (unsigned __int8)QuicConnIsClient(v7) )
    goto LABEL_37;
  if ( (*((_BYTE *)v7 + 251) & 0x10) == 0 || (v7[62] & 8) == 0 || (v7[700] & 1) == 0 )
  {
    v11 = -1073741436;
    goto LABEL_38;
  }
  if ( (_WORD)v4 )
  {
    Pool2 = (void *)ExAllocatePool2(66, v4, 859005777);
    v8 = Pool2;
    if ( !Pool2 )
    {
      v11 = -1073741801;
      if ( (Microsoft_QuicEnableBits & 2) != 0 )
        McTemplateU0sx_EtwWriteTransfer(a1, v10, "Resumption data copy", v4);
      goto LABEL_38;
    }
    memmove(Pool2, a4, v4);
  }
  v12 = QuicOperationAlloc(*((_QWORD *)v7 + 9), 0);
  if ( v12 )
  {
    **(_DWORD **)(v12 + 24) = 4;
    *(_DWORD *)(*(_QWORD *)(v12 + 24) + 24LL) = v6;
    *(_QWORD *)(*(_QWORD *)(v12 + 24) + 32LL) = v8;
    *(_WORD *)(*(_QWORD *)(v12 + 24) + 40LL) = v4;
    QuicConnQueueOper(v7, v12);
    v11 = 0;
  }
  else
  {
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(a1, 0, "CONN_SEND_RESUMPTION_TICKET operation", 0);
    v11 = -1073741801;
    if ( v8 )
      ExFreePoolWithTag(v8, 0x33336351u);
  }
LABEL_38:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(a1, QuicApiExitStatus, v11);
  return v11;
}

```

## disassembly

```asm
0x140040e60  mov     rax, rsp
0x140040e63  mov     [rax+8], rbx
0x140040e67  mov     [rax+10h], rbp
0x140040e6b  mov     [rax+18h], rsi
0x140040e6f  mov     [rax+20h], rdi
0x140040e73  push    r12
0x140040e75  push    r14
0x140040e77  push    r15
0x140040e79  sub     rsp, 20h
0x140040e7d  xor     r12d, r12d
0x140040e80  movzx   ebp, r8w
0x140040e84  test    cs:Microsoft_QuicEnableBits, 8
0x140040e8b  mov     r14, r9
0x140040e8e  mov     r15d, edx
0x140040e91  mov     rbx, rcx
0x140040e94  mov     esi, r12d
0x140040e97  jz      short loc_140040EA6
0x140040e99  mov     r9, rcx
0x140040e9c  lea     r8d, [r12+11h]
0x140040ea1  call    McTemplateU0qp_EtwWriteTransfer
0x140040ea6  mov     eax, 3E8h
0x140040eab  cmp     bp, ax
0x140040eae  ja      loc_14004108A
0x140040eb4  test    r14, r14
0x140040eb7  jnz     short loc_140040EC2
0x140040eb9  test    bp, bp
0x140040ebc  jnz     loc_14004108A
0x140040ec2  cmp     r15d, 1
0x140040ec6  jg      loc_14004108A
0x140040ecc  test    rbx, rbx
0x140040ecf  jz      loc_14004108A
0x140040ed5  mov     ecx, [rbx]
0x140040ed7  lea     rdi, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x140040ede  lea     eax, [rcx-3]
0x140040ee1  cmp     eax, 1
0x140040ee4  jbe     short loc_140040F27
0x140040ee6  cmp     ecx, 5
0x140040ee9  jnz     loc_14004108A
0x140040eef  test    byte ptr [rbx+5Ch], 8
0x140040ef3  jz      short loc_140040F09
0x140040ef5  lea     r8, aStreamFlagsHan; "!Stream->Flags.HandleClosed"
0x140040efc  mov     edx, 233h
0x140040f01  mov     rcx, rdi
0x140040f04  call    CxPlatLogAssert
0x140040f09  test    byte ptr [rbx+5Ch], 40h
0x140040f0d  jz      short loc_140040F23
0x140040f0f  lea     r8, aStreamFlagsFre; "!Stream->Flags.Freed"
0x140040f16  mov     edx, 234h
0x140040f1b  mov     rcx, rdi
0x140040f1e  call    CxPlatLogAssert
0x140040f23  mov     rbx, [rbx+48h]
0x140040f27  test    byte ptr [rbx+0FCh], 40h
0x140040f2e  jz      short loc_140040F77
0x140040f30  test    byte ptr [rbx+0F9h], 4
0x140040f37  jz      short loc_140040F4F
0x140040f39  lea     r8, aConnectionStat_2; "!Connection->State.Freed"
0x140040f40  mov     edx, 23Bh
0x140040f45  mov     rcx, rdi
0x140040f48  call    CxPlatLogAssert
0x140040f4d  int     2Ch; Windows NT - assertion failure
0x140040f4f  test    byte ptr [rbx+0FCh], 40h
0x140040f56  jz      short loc_140040F77
0x140040f58  test    byte ptr [rbx+0F9h], 2
0x140040f5f  jz      short loc_140040F77
0x140040f61  lea     r8, aConnectionStat_0; "!Connection->State.HandleClosed"
0x140040f68  mov     edx, 23Ch
0x140040f6d  mov     rcx, rdi
0x140040f70  call    CxPlatLogAssert
0x140040f75  int     2Ch; Windows NT - assertion failure
0x140040f77  mov     rcx, rbx
0x140040f7a  call    QuicConnIsClient
0x140040f7f  test    al, al
0x140040f81  jnz     loc_14004108A
0x140040f87  test    byte ptr [rbx+0FBh], 10h
0x140040f8e  jz      loc_140041083
0x140040f94  test    byte ptr [rbx+0F8h], 8
0x140040f9b  jz      loc_140041083
0x140040fa1  test    byte ptr [rbx+0AF0h], 1
0x140040fa8  jz      loc_140041083
0x140040fae  test    bp, bp
0x140040fb1  jz      short loc_140041009
0x140040fb3  mov     r8d, 33336351h
0x140040fb9  mov     rdx, rbp
0x140040fbc  mov     ecx, 42h ; 'B'
0x140040fc1  call    cs:__imp_ExAllocatePool2
0x140040fc8  nop     dword ptr [rax+rax+00h]
0x140040fcd  mov     rsi, rax
0x140040fd0  test    rax, rax
0x140040fd3  jnz     short loc_140040FFB
0x140040fd5  test    cs:Microsoft_QuicEnableBits, 2
0x140040fdc  mov     ebx, 0C0000017h
0x140040fe1  jz      loc_14004108F
0x140040fe7  mov     r9, rbp
0x140040fea  lea     r8, aResumptionData; "Resumption data copy"
0x140040ff1  call    McTemplateU0sx_EtwWriteTransfer
0x140040ff6  jmp     loc_14004108F
0x140040ffb  mov     r8, rbp; Size
0x140040ffe  mov     rdx, r14; Src
0x140041001  mov     rcx, rax; void *
0x140041004  call    memmove
0x140041009  mov     rcx, [rbx+48h]
0x14004100d  xor     edx, edx
0x14004100f  call    QuicOperationAlloc
0x140041014  mov     rdx, rax
0x140041017  test    rax, rax
0x14004101a  jnz     short loc_140041054
0x14004101c  test    cs:Microsoft_QuicEnableBits, 2
0x140041023  jz      short loc_140041034
0x140041025  xor     r9d, r9d
0x140041028  lea     r8, aConnSendResump; "CONN_SEND_RESUMPTION_TICKET operation"
0x14004102f  call    McTemplateU0sx_EtwWriteTransfer
0x140041034  mov     ebx, 0C0000017h
0x140041039  test    rsi, rsi
0x14004103c  jz      short loc_14004108F
0x14004103e  mov     edx, 33336351h; Tag
0x140041043  mov     rcx, rsi; P
0x140041046  call    cs:__imp_ExFreePoolWithTag
0x14004104d  nop     dword ptr [rax+rax+00h]
0x140041052  jmp     short loc_14004108F
0x140041054  mov     rax, [rax+18h]
0x140041058  mov     rcx, rbx
0x14004105b  mov     dword ptr [rax], 4
0x140041061  mov     rax, [rdx+18h]
0x140041065  mov     [rax+18h], r15d
0x140041069  mov     rax, [rdx+18h]
0x14004106d  mov     [rax+20h], rsi
0x140041071  mov     rax, [rdx+18h]
0x140041075  mov     [rax+28h], bp
0x140041079  call    QuicConnQueueOper
0x14004107e  mov     ebx, r12d
0x140041081  jmp     short loc_14004108F
0x140041083  mov     ebx, 0C0000184h
0x140041088  jmp     short loc_14004108F
0x14004108a  mov     ebx, 0C000000Dh
0x14004108f  test    cs:Microsoft_QuicEnableBits, 8
0x140041096  jz      short loc_1400410A7
0x140041098  mov     r8d, ebx
0x14004109b  lea     rdx, QuicApiExitStatus
0x1400410a2  call    McTemplateU0q_EtwWriteTransfer
0x1400410a7  mov     rbp, [rsp+38h+arg_8]
0x1400410ac  mov     eax, ebx
0x1400410ae  mov     rbx, [rsp+38h+arg_0]
0x1400410b3  mov     rsi, [rsp+38h+arg_10]
0x1400410b8  mov     rdi, [rsp+38h+arg_18]
0x1400410bd  add     rsp, 20h
0x1400410c1  pop     r15
0x1400410c3  pop     r14
0x1400410c5  pop     r12
0x1400410c7  retn
```
