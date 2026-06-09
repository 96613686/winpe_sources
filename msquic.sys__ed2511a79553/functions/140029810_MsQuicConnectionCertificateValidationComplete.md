# MsQuicConnectionCertificateValidationComplete

- ea: `0x140029810`
- end: `0x14002995e`
- name: `MsQuicConnectionCertificateValidationComplete`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14000c440`
- `0x14000c4b8`
- `0x140029810`
- `0x1400337e4`
- `0x14003eca4`
- `0x14003ed00`
- `0x140040c2c`

## string_xrefs

- `0x1400298f8`: `CONN_COMPLETE_CERTIFICATE_VALIDATION operation`

## pseudocode

```c
__int64 __fastcall MsQuicConnectionCertificateValidationComplete(unsigned int *a1, __int64 a2, int a3)
{
  char v4; // si
  unsigned int *v5; // rbx
  __int64 v6; // rax
  unsigned int v7; // ebx

  v4 = a2;
  v5 = a1;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 27, a1);
  if ( !v5 )
    goto LABEL_20;
  a1 = (unsigned int *)*v5;
  if ( (unsigned int)((_DWORD)a1 - 3) > 1 )
  {
    if ( (_DWORD)a1 != 5 )
    {
LABEL_20:
      v7 = -1073741811;
      goto LABEL_21;
    }
    if ( (v5[23] & 8) != 0 )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1977, "!Stream->Flags.HandleClosed");
    if ( (v5[23] & 0x40) != 0 )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1978, "!Stream->Flags.Freed");
    v5 = (unsigned int *)*((_QWORD *)v5 + 9);
  }
  if ( (v5[63] & 0x40) != 0 && (*((_BYTE *)v5 + 249) & 4) != 0 )
  {
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1985, "!Connection->State.Freed");
    __int2c();
  }
  if ( !v4 && a3 > 255 )
    goto LABEL_20;
  v6 = QuicOperationAlloc(*((_QWORD *)v5 + 9), 0);
  if ( v6 )
  {
    **(_DWORD **)(v6 + 24) = 15;
    *(_DWORD *)(*(_QWORD *)(v6 + 24) + 24LL) = a3;
    *(_BYTE *)(*(_QWORD *)(v6 + 24) + 28LL) = v4;
    QuicConnQueueOper(v5, v6);
    v7 = 259;
  }
  else
  {
    v7 = -1073741801;
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(a1, 0, "CONN_COMPLETE_CERTIFICATE_VALIDATION operation", 0);
  }
LABEL_21:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(a1, QuicApiExitStatus, v7);
  return v7;
}

```

## disassembly

```asm
0x140029810  mov     [rsp+arg_0], rbx
0x140029815  mov     [rsp+arg_8], rsi
0x14002981a  push    rdi
0x14002981b  sub     rsp, 20h
0x14002981f  test    cs:Microsoft_QuicEnableBits, 8
0x140029826  mov     edi, r8d
0x140029829  mov     sil, dl
0x14002982c  mov     rbx, rcx
0x14002982f  jz      short loc_14002983F
0x140029831  mov     r9, rcx
0x140029834  mov     r8d, 1Bh
0x14002983a  call    McTemplateU0qp_EtwWriteTransfer
0x14002983f  test    rbx, rbx
0x140029842  jz      loc_14002992E
0x140029848  mov     ecx, [rbx]
0x14002984a  lea     eax, [rcx-3]
0x14002984d  cmp     eax, 1
0x140029850  jbe     short loc_14002989B
0x140029852  cmp     ecx, 5
0x140029855  jnz     loc_14002992E
0x14002985b  test    byte ptr [rbx+5Ch], 8
0x14002985f  jz      short loc_140029879
0x140029861  lea     r8, aStreamFlagsHan; "!Stream->Flags.HandleClosed"
0x140029868  mov     edx, 7B9h
0x14002986d  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x140029874  call    CxPlatLogAssert
0x140029879  test    byte ptr [rbx+5Ch], 40h
0x14002987d  jz      short loc_140029897
0x14002987f  lea     r8, aStreamFlagsFre; "!Stream->Flags.Freed"
0x140029886  mov     edx, 7BAh
0x14002988b  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x140029892  call    CxPlatLogAssert
0x140029897  mov     rbx, [rbx+48h]
0x14002989b  test    byte ptr [rbx+0FCh], 40h
0x1400298a2  jz      short loc_1400298C7
0x1400298a4  test    byte ptr [rbx+0F9h], 4
0x1400298ab  jz      short loc_1400298C7
0x1400298ad  lea     r8, aConnectionStat_2; "!Connection->State.Freed"
0x1400298b4  mov     edx, 7C1h
0x1400298b9  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x1400298c0  call    CxPlatLogAssert
0x1400298c5  int     2Ch; Windows NT - assertion failure
0x1400298c7  test    sil, sil
0x1400298ca  jnz     short loc_1400298D4
0x1400298cc  cmp     edi, 0FFh
0x1400298d2  jg      short loc_14002992E
0x1400298d4  mov     rcx, [rbx+48h]
0x1400298d8  xor     edx, edx
0x1400298da  call    QuicOperationAlloc
0x1400298df  mov     rdx, rax
0x1400298e2  test    rax, rax
0x1400298e5  jnz     short loc_140029906
0x1400298e7  test    cs:Microsoft_QuicEnableBits, 2
0x1400298ee  mov     ebx, 0C0000017h
0x1400298f3  jz      short loc_140029933
0x1400298f5  xor     r9d, r9d
0x1400298f8  lea     r8, aConnCompleteCe; "CONN_COMPLETE_CERTIFICATE_VALIDATION op"...
0x1400298ff  call    McTemplateU0sx_EtwWriteTransfer
0x140029904  jmp     short loc_140029933
0x140029906  mov     rax, [rax+18h]
0x14002990a  mov     rcx, rbx
0x14002990d  mov     dword ptr [rax], 0Fh
0x140029913  mov     rax, [rdx+18h]
0x140029917  mov     [rax+18h], edi
0x14002991a  mov     rax, [rdx+18h]
0x14002991e  mov     [rax+1Ch], sil
0x140029922  call    QuicConnQueueOper
0x140029927  mov     ebx, 103h
0x14002992c  jmp     short loc_140029933
0x14002992e  mov     ebx, 0C000000Dh
0x140029933  test    cs:Microsoft_QuicEnableBits, 8
0x14002993a  jz      short loc_14002994B
0x14002993c  mov     r8d, ebx
0x14002993f  lea     rdx, QuicApiExitStatus
0x140029946  call    McTemplateU0q_EtwWriteTransfer
0x14002994b  mov     rsi, [rsp+28h+arg_8]
0x140029950  mov     eax, ebx
0x140029952  mov     rbx, [rsp+28h+arg_0]
0x140029957  add     rsp, 20h
0x14002995b  pop     rdi
0x14002995c  retn
```
