# MsQuicStreamOpen

- ea: `0x14000af30`
- end: `0x14000b08f`
- name: `MsQuicStreamOpen`
- size: `351`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000af30`
- `0x14000bad0`
- `0x1400337e4`
- `0x14003eca4`
- `0x140040c2c`

## pseudocode

```c
__int64 __fastcall MsQuicStreamOpen(KSPIN_LOCK *a1, __int64 a2, KSPIN_LOCK a3, KSPIN_LOCK a4, KSPIN_LOCK **a5)
{
  char v7; // r14
  unsigned int *v8; // rbx
  int v9; // ebx

  v7 = a2;
  v8 = (unsigned int *)a1;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer((__int64)a1, a2, 18, a1);
  if ( !a5 || !a3 || !v8 )
    goto LABEL_21;
  a1 = (KSPIN_LOCK *)*v8;
  if ( (unsigned int)((_DWORD)a1 - 3) > 1 )
  {
    if ( (_DWORD)a1 == 5 )
    {
      if ( (v8[23] & 8) != 0 )
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 669, "!Stream->Flags.HandleClosed");
      if ( (v8[23] & 0x40) != 0 )
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 670, "!Stream->Flags.Freed");
      v8 = (unsigned int *)*((_QWORD *)v8 + 9);
      goto LABEL_13;
    }
LABEL_21:
    v9 = -1073741811;
    goto LABEL_22;
  }
LABEL_13:
  if ( (v8[63] & 0x40) != 0 && (*((_BYTE *)v8 + 249) & 4) != 0 )
  {
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 677, "!Connection->State.Freed");
    __int2c();
  }
  LOBYTE(a1) = *((_BYTE *)v8 + 248);
  if ( ((unsigned __int8)a1 & 0x10) != 0 || ((unsigned __int8)a1 & 0x20) != 0 )
  {
    v9 = (v8[62] & 0x10) != 0 ? -1073741436 : -1073741536;
  }
  else
  {
    v9 = QuicStreamInitialize((KSPIN_LOCK)v8, 0, v7, a5);
    if ( v9 >= 0 )
    {
      (*a5)[89] = a3;
      a1 = *a5;
      (*a5)[1] = a4;
    }
  }
LABEL_22:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer((__int64)a1, (const EVENT_DESCRIPTOR *)QuicApiExitStatus, (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000af30  mov     rax, rsp
0x14000af33  mov     [rax+8], rbx
0x14000af37  mov     [rax+10h], rbp
0x14000af3b  mov     [rax+18h], rsi
0x14000af3f  mov     [rax+20h], rdi
0x14000af43  push    r14
0x14000af45  sub     rsp, 20h
0x14000af49  test    cs:Microsoft_QuicEnableBits, 8
0x14000af50  mov     rbp, r9
0x14000af53  mov     rsi, r8
0x14000af56  mov     r14d, edx
0x14000af59  mov     rbx, rcx
0x14000af5c  jz      short loc_14000AF6C
0x14000af5e  mov     r9, rcx
0x14000af61  mov     r8d, 12h
0x14000af67  call    McTemplateU0qp_EtwWriteTransfer
0x14000af6c  mov     rdi, [rsp+28h+arg_20]
0x14000af71  test    rdi, rdi
0x14000af74  jz      loc_14000B054
0x14000af7a  test    rsi, rsi
0x14000af7d  jz      loc_14000B054
0x14000af83  test    rbx, rbx
0x14000af86  jz      loc_14000B054
0x14000af8c  mov     ecx, [rbx]
0x14000af8e  lea     eax, [rcx-3]
0x14000af91  cmp     eax, 1
0x14000af94  jbe     short loc_14000AFDF
0x14000af96  cmp     ecx, 5
0x14000af99  jnz     loc_14000B054
0x14000af9f  test    byte ptr [rbx+5Ch], 8
0x14000afa3  jz      short loc_14000AFBD
0x14000afa5  lea     r8, aStreamFlagsHan; "!Stream->Flags.HandleClosed"
0x14000afac  mov     edx, 29Dh
0x14000afb1  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14000afb8  call    CxPlatLogAssert
0x14000afbd  test    byte ptr [rbx+5Ch], 40h
0x14000afc1  jz      short loc_14000AFDB
0x14000afc3  lea     r8, aStreamFlagsFre; "!Stream->Flags.Freed"
0x14000afca  mov     edx, 29Eh
0x14000afcf  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14000afd6  call    CxPlatLogAssert
0x14000afdb  mov     rbx, [rbx+48h]
0x14000afdf  test    byte ptr [rbx+0FCh], 40h
0x14000afe6  jz      short loc_14000B00B
0x14000afe8  test    byte ptr [rbx+0F9h], 4
0x14000afef  jz      short loc_14000B00B
0x14000aff1  lea     r8, aConnectionStat_2; "!Connection->State.Freed"
0x14000aff8  mov     edx, 2A5h
0x14000affd  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14000b004  call    CxPlatLogAssert
0x14000b009  int     2Ch; Windows NT - assertion failure
0x14000b00b  mov     cl, [rbx+0F8h]
0x14000b011  mov     al, cl
0x14000b013  and     al, 10h
0x14000b015  jnz     short loc_14000B045
0x14000b017  test    cl, 20h
0x14000b01a  jnz     short loc_14000B045
0x14000b01c  mov     r9, rdi
0x14000b01f  mov     r8d, r14d
0x14000b022  xor     edx, edx
0x14000b024  mov     rcx, rbx
0x14000b027  call    QuicStreamInitialize
0x14000b02c  mov     ebx, eax
0x14000b02e  test    eax, eax
0x14000b030  js      short loc_14000B059
0x14000b032  mov     rcx, [rdi]
0x14000b035  mov     [rcx+2C8h], rsi
0x14000b03c  mov     rcx, [rdi]
0x14000b03f  mov     [rcx+8], rbp
0x14000b043  jmp     short loc_14000B059
0x14000b045  neg     al
0x14000b047  sbb     ebx, ebx
0x14000b049  and     ebx, 64h
0x14000b04c  add     ebx, 0C0000120h
0x14000b052  jmp     short loc_14000B059
0x14000b054  mov     ebx, 0C000000Dh
0x14000b059  test    cs:Microsoft_QuicEnableBits, 8
0x14000b060  jz      short loc_14000B071
0x14000b062  mov     r8d, ebx
0x14000b065  lea     rdx, QuicApiExitStatus
0x14000b06c  call    McTemplateU0q_EtwWriteTransfer
0x14000b071  mov     rbp, [rsp+28h+arg_8]
0x14000b076  mov     eax, ebx
0x14000b078  mov     rbx, [rsp+28h+arg_0]
0x14000b07d  mov     rsi, [rsp+28h+arg_10]
0x14000b082  mov     rdi, [rsp+28h+arg_18]
0x14000b087  add     rsp, 20h
0x14000b08b  pop     r14
0x14000b08d  retn
```
