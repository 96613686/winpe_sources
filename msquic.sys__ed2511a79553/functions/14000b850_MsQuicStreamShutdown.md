# MsQuicStreamShutdown

- ea: `0x14000b850`
- end: `0x14000babb`
- name: `MsQuicStreamShutdown`
- size: `619`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x14000b60c`
- `0x14000b850`
- `0x14000c500`
- `0x14000c5b0`
- `0x1400290b4`
- `0x140029104`
- `0x14002974c`
- `0x1400337e4`
- `0x14003eca4`
- `0x14003ed00`
- `0x140040c2c`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14000b967`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000b967`

## pseudocode

```c
__int64 __fastcall MsQuicStreamShutdown(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  unsigned int v3; // ebp
  __int64 v4; // rsi
  __int64 v6; // rdi
  char v7; // al
  unsigned int v8; // ebx
  __int64 v9; // r13
  PSLIST_ENTRY v10; // rax
  __int64 v11; // rdx
  PSLIST_ENTRY v12; // r14
  PSLIST_ENTRY v13; // rax

  v3 = a2;
  v4 = a1;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 21, a1);
  if ( !v4
    || *(_DWORD *)v4 != 5
    || (v3 & 0xFFFF7FFF) == 0
    || a3 > 0x3FFFFFFFFFFFFFFFLL
    || (LOBYTE(a1) = (v3 & 0xE) != 0, ((unsigned __int8)a1 & ((v3 & 1) != 0)) != 0)
    || (v3 & 8) != 0 && v3 != 14 )
  {
    v8 = -1073741811;
    goto LABEL_33;
  }
  if ( (*(_BYTE *)(v4 + 92) & 8) != 0 )
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 954, "!Stream->Flags.HandleClosed");
  if ( (*(_BYTE *)(v4 + 92) & 0x40) != 0 )
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 955, "!Stream->Flags.Freed");
  v6 = *(_QWORD *)(v4 + 72);
  if ( (*(_BYTE *)(v6 + 252) & 0x40) != 0 && (*(_BYTE *)(v6 + 249) & 4) != 0 )
  {
    CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 959, "!Connection->State.Freed");
    __int2c();
  }
  if ( (v3 & 0x10) != 0 && ((MsQuicLib & 4) != 0 || *(HANDLE *)(v6 + 256) == PsGetCurrentThreadId()) )
  {
    v7 = *(_BYTE *)(v6 + 251);
    if ( (v7 & 0x20) != 0 )
    {
      QuicStreamShutdown(v4, v3);
    }
    else
    {
      *(_BYTE *)(v6 + 251) = v7 | 0x20;
      QuicStreamShutdown(v4, v3);
      *(_BYTE *)(v6 + 251) &= ~0x20u;
    }
    v8 = 0;
    goto LABEL_33;
  }
  v9 = *(_QWORD *)(v6 + 72);
  v10 = CxPlatPoolAlloc(v9 + 2016);
  v12 = v10;
  if ( !v10 )
    goto LABEL_27;
  BYTE4(v10[1].Next) = 1;
  LODWORD(v10[1].Next) = 0;
  v13 = CxPlatPoolAlloc(v9 + 1824);
  *((_QWORD *)&v12[1].Next + 1) = v13;
  if ( !v13 )
  {
    CxPlatPoolFree(v12);
LABEL_27:
    v8 = -1073741801;
    if ( (Microsoft_QuicEnableBits & 2) != 0 )
      McTemplateU0sx_EtwWriteTransfer(a1, v11, "STRM_SHUTDOWN operation", 0);
    goto LABEL_33;
  }
  *((_QWORD *)&v13->Next + 1) = 0;
  *(_QWORD *)(*((_QWORD *)&v12[1].Next + 1) + 16LL) = 0;
  **((_DWORD **)&v12[1].Next + 1) = 6;
  *(_QWORD *)(*((_QWORD *)&v12[1].Next + 1) + 24LL) = v4;
  *(_DWORD *)(*((_QWORD *)&v12[1].Next + 1) + 32LL) = v3;
  *(_QWORD *)(*((_QWORD *)&v12[1].Next + 1) + 40LL) = a3;
  CxPlatRefIncrement(v4 + 16);
  if ( (unsigned __int8)QuicOperationEnqueue(v6 + 1424, *(_QWORD *)(v6 + 72), v12) )
    QuicWorkerQueueConnection(*(_QWORD *)(v6 + 64), v6);
  v8 = 259;
LABEL_33:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0q_EtwWriteTransfer(a1, QuicApiExitStatus, v8);
  return v8;
}

```

## disassembly

```asm
0x14000b850  sub     rsp, 38h
0x14000b854  test    cs:Microsoft_QuicEnableBits, 8
0x14000b85b  mov     [rsp+38h+arg_8], rbp
0x14000b860  mov     ebp, edx
0x14000b862  mov     [rsp+38h+arg_10], rsi
0x14000b867  mov     rsi, rcx
0x14000b86a  mov     [rsp+38h+var_18], r15
0x14000b86f  mov     r15, r8
0x14000b872  jz      short loc_14000B882
0x14000b874  mov     r9, rcx
0x14000b877  mov     r8d, 15h
0x14000b87d  call    McTemplateU0qp_EtwWriteTransfer
0x14000b882  mov     [rsp+38h+arg_0], rbx
0x14000b887  mov     [rsp+38h+arg_18], rdi
0x14000b88c  mov     [rsp+38h+var_8], r13
0x14000b891  mov     [rsp+38h+var_10], r14
0x14000b896  test    rsi, rsi
0x14000b899  jz      loc_14000BA73
0x14000b89f  cmp     dword ptr [rsi], 5
0x14000b8a2  jnz     loc_14000BA73
0x14000b8a8  test    ebp, 0FFFF7FFFh
0x14000b8ae  jz      loc_14000BA73
0x14000b8b4  mov     rax, 3FFFFFFFFFFFFFFFh
0x14000b8be  cmp     r15, rax
0x14000b8c1  ja      loc_14000BA73
0x14000b8c7  test    bpl, 0Eh
0x14000b8cb  setnz   cl
0x14000b8ce  test    bpl, 1
0x14000b8d2  setnz   al
0x14000b8d5  test    al, cl
0x14000b8d7  jnz     loc_14000BA73
0x14000b8dd  test    bpl, 8
0x14000b8e1  jz      short loc_14000B8EC
0x14000b8e3  cmp     ebp, 0Eh
0x14000b8e6  jnz     loc_14000BA73
0x14000b8ec  test    byte ptr [rsi+5Ch], 8
0x14000b8f0  jz      short loc_14000B90A
0x14000b8f2  lea     r8, aStreamFlagsHan; "!Stream->Flags.HandleClosed"
0x14000b8f9  mov     edx, 3BAh
0x14000b8fe  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14000b905  call    CxPlatLogAssert
0x14000b90a  test    byte ptr [rsi+5Ch], 40h
0x14000b90e  jz      short loc_14000B928
0x14000b910  lea     r8, aStreamFlagsFre; "!Stream->Flags.Freed"
0x14000b917  mov     edx, 3BBh
0x14000b91c  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14000b923  call    CxPlatLogAssert
0x14000b928  mov     rdi, [rsi+48h]
0x14000b92c  test    byte ptr [rdi+0FCh], 40h
0x14000b933  jz      short loc_14000B958
0x14000b935  test    byte ptr [rdi+0F9h], 4
0x14000b93c  jz      short loc_14000B958
0x14000b93e  lea     r8, aConnectionStat_2; "!Connection->State.Freed"
0x14000b945  mov     edx, 3BFh
0x14000b94a  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14000b951  call    CxPlatLogAssert
0x14000b956  int     2Ch; Windows NT - assertion failure
0x14000b958  test    bpl, 10h
0x14000b95c  jz      short loc_14000B9B6
0x14000b95e  test    cs:MsQuicLib, 4
0x14000b965  jnz     short loc_14000B97C
0x14000b967  call    cs:__imp_PsGetCurrentThreadId
0x14000b96e  nop     dword ptr [rax+rax+00h]
0x14000b973  cmp     [rdi+100h], rax
0x14000b97a  jnz     short loc_14000B9B6
0x14000b97c  movzx   eax, byte ptr [rdi+0FBh]
0x14000b983  mov     r8, r15
0x14000b986  mov     edx, ebp
0x14000b988  mov     rcx, rsi
0x14000b98b  test    al, 20h
0x14000b98d  jnz     short loc_14000B9AA
0x14000b98f  or      al, 20h
0x14000b991  mov     [rdi+0FBh], al
0x14000b997  call    QuicStreamShutdown
0x14000b99c  and     byte ptr [rdi+0FBh], 0DFh
0x14000b9a3  xor     ebx, ebx
0x14000b9a5  jmp     loc_14000BA78
0x14000b9aa  call    QuicStreamShutdown
0x14000b9af  xor     ebx, ebx
0x14000b9b1  jmp     loc_14000BA78
0x14000b9b6  mov     r13, [rdi+48h]
0x14000b9ba  lea     rcx, [r13+7E0h]
0x14000b9c1  call    CxPlatPoolAlloc
0x14000b9c6  mov     r14, rax
0x14000b9c9  test    rax, rax
0x14000b9cc  jz      short loc_14000B9F4
0x14000b9ce  xor     ebx, ebx
0x14000b9d0  mov     byte ptr [rax+14h], 1
0x14000b9d4  lea     rcx, [r13+720h]
0x14000b9db  mov     [rax+10h], ebx
0x14000b9de  call    CxPlatPoolAlloc
0x14000b9e3  mov     [r14+18h], rax
0x14000b9e7  test    rax, rax
0x14000b9ea  jnz     short loc_14000BA13
0x14000b9ec  mov     rcx, r14
0x14000b9ef  call    CxPlatPoolFree
0x14000b9f4  test    cs:Microsoft_QuicEnableBits, 2
0x14000b9fb  mov     ebx, 0C0000017h
0x14000ba00  jz      short loc_14000BA78
0x14000ba02  xor     r9d, r9d
0x14000ba05  lea     r8, aStrmShutdownOp; "STRM_SHUTDOWN operation"
0x14000ba0c  call    McTemplateU0sx_EtwWriteTransfer
0x14000ba11  jmp     short loc_14000BA78
0x14000ba13  mov     [rax+8], rbx
0x14000ba17  lea     rcx, [rsi+10h]
0x14000ba1b  mov     rax, [r14+18h]
0x14000ba1f  mov     [rax+10h], rbx
0x14000ba23  mov     rax, [r14+18h]
0x14000ba27  mov     dword ptr [rax], 6
0x14000ba2d  mov     rax, [r14+18h]
0x14000ba31  mov     [rax+18h], rsi
0x14000ba35  mov     rax, [r14+18h]
0x14000ba39  mov     [rax+20h], ebp
0x14000ba3c  mov     rax, [r14+18h]
0x14000ba40  mov     [rax+28h], r15
0x14000ba44  call    CxPlatRefIncrement
0x14000ba49  mov     rdx, [rdi+48h]
0x14000ba4d  lea     rcx, [rdi+590h]
0x14000ba54  mov     r8, r14
0x14000ba57  call    QuicOperationEnqueue
0x14000ba5c  test    al, al
0x14000ba5e  jz      short loc_14000BA6C
0x14000ba60  mov     rcx, [rdi+40h]
0x14000ba64  mov     rdx, rdi
0x14000ba67  call    QuicWorkerQueueConnection
0x14000ba6c  mov     ebx, 103h
0x14000ba71  jmp     short loc_14000BA78
0x14000ba73  mov     ebx, 0C000000Dh
0x14000ba78  test    cs:Microsoft_QuicEnableBits, 8
0x14000ba7f  mov     r15, [rsp+38h+var_18]
0x14000ba84  mov     r14, [rsp+38h+var_10]
0x14000ba89  mov     r13, [rsp+38h+var_8]
0x14000ba8e  mov     rdi, [rsp+38h+arg_18]
0x14000ba93  mov     rsi, [rsp+38h+arg_10]
0x14000ba98  mov     rbp, [rsp+38h+arg_8]
0x14000ba9d  jz      short loc_14000BAAE
0x14000ba9f  mov     r8d, ebx
0x14000baa2  lea     rdx, QuicApiExitStatus
0x14000baa9  call    McTemplateU0q_EtwWriteTransfer
0x14000baae  mov     eax, ebx
0x14000bab0  mov     rbx, [rsp+38h+arg_0]
0x14000bab5  add     rsp, 38h
0x14000bab9  retn
```
