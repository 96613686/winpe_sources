# MsQuicConnectionShutdown

- ea: `0x140022270`
- end: `0x14002243a`
- name: `MsQuicConnectionShutdown`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000c440`
- `0x140022270`
- `0x140022440`
- `0x1400337e4`
- `0x14003eb54`
- `0x140040c2c`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14002236e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002236e`

## string_xrefs

- `0x14002238c`: `(Connection->WorkerThreadID == ((CXPLAT_THREAD_ID)PsGetCurrentThreadId())) || !Connection->State.HandleClosed`

## pseudocode

```c
void __fastcall MsQuicConnectionShutdown(unsigned int *a1, __int64 a2, unsigned __int64 a3)
{
  int v4; // esi
  unsigned int *v5; // rbx
  char v6; // al
  __int64 v7; // rdx

  v4 = a2;
  v5 = a1;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 14, a1);
  if ( v5 )
  {
    a1 = (unsigned int *)*v5;
    if ( (unsigned int)((_DWORD)a1 - 3) > 1 )
    {
      if ( (_DWORD)a1 != 5 )
        goto LABEL_25;
      if ( (v5[23] & 8) != 0 )
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 242, "!Stream->Flags.HandleClosed");
      if ( (v5[23] & 0x40) != 0 )
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 243, "!Stream->Flags.Freed");
      v5 = (unsigned int *)*((_QWORD *)v5 + 9);
    }
    v6 = v5[63] & 0x40;
    if ( a3 <= 0x3FFFFFFFFFFFFFFFLL )
    {
      if ( v6 && (*((_BYTE *)v5 + 249) & 4) != 0 )
      {
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 254, "!Connection->State.Freed");
        __int2c();
      }
      if ( (v5[63] & 0x40) != 0 && *((HANDLE *)v5 + 32) != PsGetCurrentThreadId() && (*((_BYTE *)v5 + 249) & 2) != 0 )
      {
        CxPlatLogAssert(
          "C:\\__w\\1\\s\\msquic\\src\\core\\api.c",
          257,
          "(Connection->WorkerThreadID == ((CXPLAT_THREAD_ID)PsGetCurrentThreadId())) || !Connection->State.HandleClosed");
        __int2c();
      }
      v7 = QuicOperationAlloc(*((_QWORD *)v5 + 9), 0);
      if ( !v7 )
      {
        if ( _InterlockedCompareExchange16((volatile signed __int16 *)v5 + 792, 1, 0) )
          goto LABEL_25;
        v7 = (__int64)(v5 + 368);
        *((_BYTE *)v5 + 1492) = 0;
        v5[372] = 0;
        *((_QWORD *)v5 + 187) = v5 + 382;
      }
      **(_DWORD **)(v7 + 24) = 1;
      *(_DWORD *)(*(_QWORD *)(v7 + 24) + 24LL) = v4;
      *(_QWORD *)(*(_QWORD *)(v7 + 24) + 32LL) = a3;
      *(_BYTE *)(*(_QWORD *)(v7 + 24) + 28LL) &= ~1u;
      *(_BYTE *)(*(_QWORD *)(v7 + 24) + 28LL) &= ~2u;
      QuicConnQueueHighestPriorityOper(v5);
    }
    else if ( v6 )
    {
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 250, "ErrorCode <= ((1ULL << 62U) - 1)");
      __int2c();
    }
  }
LABEL_25:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0_EtwWriteTransfer(a1, QuicApiExit);
}

```

## disassembly

```asm
0x140022270  mov     [rsp+arg_0], rbx
0x140022275  mov     [rsp+arg_8], rbp
0x14002227a  mov     [rsp+arg_10], rsi
0x14002227f  push    rdi
0x140022280  push    r13
0x140022282  push    r14
0x140022284  sub     rsp, 20h
0x140022288  test    cs:Microsoft_QuicEnableBits, 8
0x14002228f  mov     rdi, r8
0x140022292  mov     esi, edx
0x140022294  mov     rbx, rcx
0x140022297  jz      short loc_1400222A7
0x140022299  mov     r9, rcx
0x14002229c  mov     r8d, 0Eh
0x1400222a2  call    McTemplateU0qp_EtwWriteTransfer
0x1400222a7  xor     ebp, ebp
0x1400222a9  test    rbx, rbx
0x1400222ac  jz      loc_14002240B
0x1400222b2  mov     ecx, [rbx]
0x1400222b4  lea     r13d, [rbp+1]
0x1400222b8  lea     r14, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x1400222bf  lea     eax, [rcx-3]
0x1400222c2  cmp     eax, r13d
0x1400222c5  jbe     short loc_140022308
0x1400222c7  cmp     ecx, 5
0x1400222ca  jnz     loc_14002240B
0x1400222d0  test    byte ptr [rbx+5Ch], 8
0x1400222d4  jz      short loc_1400222EA
0x1400222d6  lea     r8, aStreamFlagsHan; "!Stream->Flags.HandleClosed"
0x1400222dd  mov     edx, 0F2h
0x1400222e2  mov     rcx, r14
0x1400222e5  call    CxPlatLogAssert
0x1400222ea  test    byte ptr [rbx+5Ch], 40h
0x1400222ee  jz      short loc_140022304
0x1400222f0  lea     r8, aStreamFlagsFre; "!Stream->Flags.Freed"
0x1400222f7  mov     edx, 0F3h
0x1400222fc  mov     rcx, r14
0x1400222ff  call    CxPlatLogAssert
0x140022304  mov     rbx, [rbx+48h]
0x140022308  mov     al, [rbx+0FCh]
0x14002230e  mov     rdx, 3FFFFFFFFFFFFFFFh
0x140022318  and     al, 40h
0x14002231a  cmp     rdi, rdx
0x14002231d  jbe     short loc_140022342
0x14002231f  test    al, al
0x140022321  jz      loc_14002240B
0x140022327  lea     r8, aErrorcode1ull6; "ErrorCode <= ((1ULL << 62U) - 1)"
0x14002232e  mov     edx, 0FAh
0x140022333  mov     rcx, r14
0x140022336  call    CxPlatLogAssert
0x14002233b  int     2Ch; Windows NT - assertion failure
0x14002233d  jmp     loc_14002240B
0x140022342  test    al, al
0x140022344  jz      short loc_140022365
0x140022346  test    byte ptr [rbx+0F9h], 4
0x14002234d  jz      short loc_140022365
0x14002234f  lea     r8, aConnectionStat_2; "!Connection->State.Freed"
0x140022356  mov     edx, 0FEh
0x14002235b  mov     rcx, r14
0x14002235e  call    CxPlatLogAssert
0x140022363  int     2Ch; Windows NT - assertion failure
0x140022365  test    byte ptr [rbx+0FCh], 40h
0x14002236c  jz      short loc_1400223A2
0x14002236e  call    cs:__imp_PsGetCurrentThreadId
0x140022375  nop     dword ptr [rax+rax+00h]
0x14002237a  cmp     [rbx+100h], rax
0x140022381  jz      short loc_1400223A2
0x140022383  test    byte ptr [rbx+0F9h], 2
0x14002238a  jz      short loc_1400223A2
0x14002238c  lea     r8, aConnectionWork; "(Connection->WorkerThreadID == ((CXPLAT"...
0x140022393  mov     edx, 101h
0x140022398  mov     rcx, r14
0x14002239b  call    CxPlatLogAssert
0x1400223a0  int     2Ch; Windows NT - assertion failure
0x1400223a2  mov     rcx, [rbx+48h]
0x1400223a6  xor     edx, edx
0x1400223a8  call    QuicOperationAlloc
0x1400223ad  mov     rdx, rax
0x1400223b0  test    rax, rax
0x1400223b3  jnz     short loc_1400223DD
0x1400223b5  lock cmpxchg [rbx+630h], r13w
0x1400223bf  test    ax, ax
0x1400223c2  jnz     short loc_14002240B
0x1400223c4  lea     rdx, [rbx+5C0h]
0x1400223cb  lea     rax, [rbx+5F8h]
0x1400223d2  mov     [rdx+14h], bpl
0x1400223d6  mov     [rdx+10h], ebp
0x1400223d9  mov     [rdx+18h], rax
0x1400223dd  mov     rax, [rdx+18h]
0x1400223e1  mov     rcx, rbx
0x1400223e4  mov     [rax], r13d
0x1400223e7  mov     rax, [rdx+18h]
0x1400223eb  mov     [rax+18h], esi
0x1400223ee  mov     rax, [rdx+18h]
0x1400223f2  mov     [rax+20h], rdi
0x1400223f6  mov     rax, [rdx+18h]
0x1400223fa  and     byte ptr [rax+1Ch], 0FEh
0x1400223fe  mov     rax, [rdx+18h]
0x140022402  and     byte ptr [rax+1Ch], 0FDh
0x140022406  call    QuicConnQueueHighestPriorityOper
0x14002240b  test    cs:Microsoft_QuicEnableBits, 8
0x140022412  jz      short loc_140022420
0x140022414  lea     rdx, QuicApiExit
0x14002241b  call    McTemplateU0_EtwWriteTransfer
0x140022420  mov     rbx, [rsp+38h+arg_0]
0x140022425  mov     rbp, [rsp+38h+arg_8]
0x14002242a  mov     rsi, [rsp+38h+arg_10]
0x14002242f  add     rsp, 20h
0x140022433  pop     r14
0x140022435  pop     r13
0x140022437  pop     rdi
0x140022438  retn
```
