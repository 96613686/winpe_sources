# MsQuicConnectionResumptionTicketValidationComplete

- ea: `0x140029a60`
- end: `0x140029ba2`
- name: `MsQuicConnectionResumptionTicketValidationComplete`
- size: `322`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14000c440`
- `0x14000c4b8`
- `0x140029a60`
- `0x1400337e4`
- `0x14003eca4`
- `0x14003ed00`
- `0x140040c2c`

## string_xrefs

- `0x140029b41`: `CONN_COMPLETE_RESUMPTION_TICKET_VALIDATION operation`

## pseudocode

```c
__int64 __fastcall MsQuicConnectionResumptionTicketValidationComplete(unsigned int *a1, __int64 a2)
{
  char v2; // di
  unsigned int *v3; // rbx
  __int64 v4; // rax
  unsigned int v5; // ebx

  v2 = a2;
  v3 = a1;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 26, a1);
  if ( !v3 )
    goto LABEL_21;
  a1 = (unsigned int *)*v3;
  if ( (unsigned int)((_DWORD)a1 - 3) > 1 )
  {
    if ( (_DWORD)a1 != 5 )
    {
LABEL_21:
      v5 = -1073741811;
      goto LABEL_22;
    }
    if ( (v3[23] & 8) != 0 )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1901, "!Stream->Flags.HandleClosed");
    if ( (v3[23] & 0x40) != 0 )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1902, "!Stream->Flags.Freed");
    v3 = (unsigned int *)*((_QWORD *)v3 + 9);
  }
  if ( (v3[63] & 0x40) != 0 && (*((_BYTE *)v3 + 249) & 4) != 0 )
  {
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1909, "!Connection->State.Freed");
    __int2c();
  }
  if ( *v3 == 3 )
    goto LABEL_21;
  if ( (v3[700] & 3) != 0 )
  {
    v5 = -1073741436;
  }
  else
  {
    v4 = QuicOperationAlloc(*((_QWORD *)v3 + 9), 0);
    if ( v4 )
    {
      **(_DWORD **)(v4 + 24) = 14;
      *(_BYTE *)(*(_QWORD *)(v4 + 24) + 24LL) = v2;
      QuicConnQueueOper(v3, v4);
      v5 = 259;
    }
    else
    {
      v5 = -1073741801;
      if ( (Microsoft_QuicEnableBits & 2) != 0 )
        McTemplateU0sx_EtwWriteTransfer(a1, 0, "CONN_COMPLETE_RESUMPTION_TICKET_VALIDATION operation", 0);
    }
  }
LABEL_22:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(a1, QuicApiExitStatus, v5);
  return v5;
}

```

## disassembly

```asm
0x140029a60  mov     [rsp+arg_0], rbx
0x140029a65  push    rdi
0x140029a66  sub     rsp, 20h
0x140029a6a  test    cs:Microsoft_QuicEnableBits, 8
0x140029a71  mov     dil, dl
0x140029a74  mov     rbx, rcx
0x140029a77  jz      short loc_140029A87
0x140029a79  mov     r9, rcx
0x140029a7c  mov     r8d, 1Ah
0x140029a82  call    McTemplateU0qp_EtwWriteTransfer
0x140029a87  test    rbx, rbx
0x140029a8a  jz      loc_140029B77
0x140029a90  mov     ecx, [rbx]
0x140029a92  lea     eax, [rcx-3]
0x140029a95  cmp     eax, 1
0x140029a98  jbe     short loc_140029AE3
0x140029a9a  cmp     ecx, 5
0x140029a9d  jnz     loc_140029B77
0x140029aa3  test    byte ptr [rbx+5Ch], 8
0x140029aa7  jz      short loc_140029AC1
0x140029aa9  lea     r8, aStreamFlagsHan; "!Stream->Flags.HandleClosed"
0x140029ab0  mov     edx, 76Dh
0x140029ab5  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x140029abc  call    CxPlatLogAssert
0x140029ac1  test    byte ptr [rbx+5Ch], 40h
0x140029ac5  jz      short loc_140029ADF
0x140029ac7  lea     r8, aStreamFlagsFre; "!Stream->Flags.Freed"
0x140029ace  mov     edx, 76Eh
0x140029ad3  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x140029ada  call    CxPlatLogAssert
0x140029adf  mov     rbx, [rbx+48h]
0x140029ae3  test    byte ptr [rbx+0FCh], 40h
0x140029aea  jz      short loc_140029B0F
0x140029aec  test    byte ptr [rbx+0F9h], 4
0x140029af3  jz      short loc_140029B0F
0x140029af5  lea     r8, aConnectionStat_2; "!Connection->State.Freed"
0x140029afc  mov     edx, 775h
0x140029b01  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x140029b08  call    CxPlatLogAssert
0x140029b0d  int     2Ch; Windows NT - assertion failure
0x140029b0f  cmp     dword ptr [rbx], 3
0x140029b12  jz      short loc_140029B77
0x140029b14  test    byte ptr [rbx+0AF0h], 3
0x140029b1b  jnz     short loc_140029B70
0x140029b1d  mov     rcx, [rbx+48h]
0x140029b21  xor     edx, edx
0x140029b23  call    QuicOperationAlloc
0x140029b28  mov     rdx, rax
0x140029b2b  test    rax, rax
0x140029b2e  jnz     short loc_140029B4F
0x140029b30  test    cs:Microsoft_QuicEnableBits, 2
0x140029b37  mov     ebx, 0C0000017h
0x140029b3c  jz      short loc_140029B7C
0x140029b3e  xor     r9d, r9d
0x140029b41  lea     r8, aConnCompleteRe; "CONN_COMPLETE_RESUMPTION_TICKET_VALIDAT"...
0x140029b48  call    McTemplateU0sx_EtwWriteTransfer
0x140029b4d  jmp     short loc_140029B7C
0x140029b4f  mov     rax, [rax+18h]
0x140029b53  mov     rcx, rbx
0x140029b56  mov     dword ptr [rax], 0Eh
0x140029b5c  mov     rax, [rdx+18h]
0x140029b60  mov     [rax+18h], dil
0x140029b64  call    QuicConnQueueOper
0x140029b69  mov     ebx, 103h
0x140029b6e  jmp     short loc_140029B7C
0x140029b70  mov     ebx, 0C0000184h
0x140029b75  jmp     short loc_140029B7C
0x140029b77  mov     ebx, 0C000000Dh
0x140029b7c  test    cs:Microsoft_QuicEnableBits, 8
0x140029b83  jz      short loc_140029B94
0x140029b85  mov     r8d, ebx
0x140029b88  lea     rdx, QuicApiExitStatus
0x140029b8f  call    McTemplateU0q_EtwWriteTransfer
0x140029b94  mov     eax, ebx
0x140029b96  mov     rbx, [rsp+28h+arg_0]
0x140029b9b  add     rsp, 20h
0x140029b9f  pop     rdi
0x140029ba0  retn
```
