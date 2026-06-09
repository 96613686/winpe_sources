# MsQuicStreamReceiveComplete

- ea: `0x140041220`
- end: `0x1400413ea`
- name: `MsQuicStreamReceiveComplete`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x14000c4b8`
- `0x140022440`
- `0x14002974c`
- `0x1400337e4`
- `0x14003eb54`
- `0x14003ec10`
- `0x140040c2c`
- `0x140040de8`
- `0x140041220`

## string_xrefs

- `0x140041325`: `RecvCompletionLength is overflow`

## pseudocode

```c
void __fastcall MsQuicStreamReceiveComplete(__int64 a1, unsigned __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rsi
  unsigned __int64 v5; // rax
  __int64 v6; // rdx

  v3 = a1;
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 23, a1);
  if ( v3 && *(_DWORD *)v3 == 5 )
  {
    if ( (*(_BYTE *)(v3 + 92) & 8) != 0 )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1323, "!Stream->Flags.HandleClosed");
    if ( (*(_BYTE *)(v3 + 92) & 0x40) != 0 )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 1324, "!Stream->Flags.Freed");
    v4 = *(_QWORD *)(v3 + 72);
    if ( (*(_BYTE *)(v4 + 252) & 0x40) != 0 )
    {
      v5 = *(_QWORD *)(v3 + 688);
      if ( v5 )
      {
        if ( a2 > v5 && a2 > 0x3FFFFFFFFFFFFFFFLL )
        {
          CxPlatLogAssert(
            "C:\\__w\\1\\s\\msquic\\src\\core\\api.c",
            1331,
            "(Stream->RecvPendingLength == 0) || BufferLength <= Stream->RecvPendingLength || BufferLength <= (0xffffffff"
            "ffffffffui64 >> 2)");
          __int2c();
        }
      }
    }
    if ( (byte_14005C48D & 2) != 0 )
      McTemplateU0pp_EtwWriteTransfer(a1, QuicStreamAppReceiveCompleteCall, v3);
    a1 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v3 + 696), a2);
    if ( (a2 & a1 & 0x4000000000000000LL) != 0 )
    {
      if ( (byte_14005C48C & 0x10) != 0 )
        McTemplateU0ps_EtwWriteTransfer(a1, QuicStreamError, v3, "RecvCompletionLength is overflow");
      a1 = 1;
      if ( !_InterlockedCompareExchange16((volatile signed __int16 *)(v4 + 1584), 1, 0) )
      {
        *(_BYTE *)(v4 + 1492) = 0;
        *(_QWORD *)(v4 + 1496) = v4 + 1528;
        *(_DWORD *)(v4 + 1488) = 0;
        *(_DWORD *)(v4 + 1528) = 1;
        *(_DWORD *)(*(_QWORD *)(v4 + 1496) + 24LL) = 32769;
        *(_QWORD *)(*(_QWORD *)(v4 + 1496) + 32LL) = -1073741436;
        *(_BYTE *)(*(_QWORD *)(v4 + 1496) + 28LL) &= ~1u;
        *(_BYTE *)(*(_QWORD *)(v4 + 1496) + 28LL) |= 2u;
        QuicConnQueueHighestPriorityOper(v4);
      }
    }
    else if ( a1 >= 0 && _InterlockedExchange64((volatile __int64 *)(v3 + 720), 0) )
    {
      CxPlatRefIncrement(v3 + 16);
      QuicConnQueueOper(v4, v6);
    }
  }
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0_EtwWriteTransfer(a1, QuicApiExit);
}

```

## disassembly

```asm
0x140041220  mov     [rsp+arg_0], rbx
0x140041225  mov     [rsp+arg_8], rbp
0x14004122a  mov     [rsp+arg_10], rsi
0x14004122f  push    rdi
0x140041230  sub     rsp, 20h
0x140041234  test    cs:Microsoft_QuicEnableBits, 8
0x14004123b  mov     rdi, rdx
0x14004123e  mov     rbx, rcx
0x140041241  jz      short loc_140041251
0x140041243  mov     r9, rcx
0x140041246  mov     r8d, 17h
0x14004124c  call    McTemplateU0qp_EtwWriteTransfer
0x140041251  xor     ebp, ebp
0x140041253  test    rbx, rbx
0x140041256  jz      loc_1400413BF
0x14004125c  cmp     dword ptr [rbx], 5
0x14004125f  jnz     loc_1400413BF
0x140041265  test    byte ptr [rbx+5Ch], 8
0x140041269  jz      short loc_140041283
0x14004126b  lea     r8, aStreamFlagsHan; "!Stream->Flags.HandleClosed"
0x140041272  mov     edx, 52Bh
0x140041277  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14004127e  call    CxPlatLogAssert
0x140041283  test    byte ptr [rbx+5Ch], 40h
0x140041287  jz      short loc_1400412A1
0x140041289  lea     r8, aStreamFlagsFre; "!Stream->Flags.Freed"
0x140041290  mov     edx, 52Ch
0x140041295  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14004129c  call    CxPlatLogAssert
0x1400412a1  mov     rsi, [rbx+48h]
0x1400412a5  test    byte ptr [rsi+0FCh], 40h
0x1400412ac  jz      short loc_1400412E8
0x1400412ae  mov     rax, [rbx+2B0h]
0x1400412b5  test    rax, rax
0x1400412b8  jz      short loc_1400412E8
0x1400412ba  cmp     rdi, rax
0x1400412bd  jbe     short loc_1400412E8
0x1400412bf  mov     rax, 3FFFFFFFFFFFFFFFh
0x1400412c9  cmp     rdi, rax
0x1400412cc  jbe     short loc_1400412E8
0x1400412ce  lea     r8, aStreamRecvpend; "(Stream->RecvPendingLength == 0) || Buf"...
0x1400412d5  mov     edx, 533h
0x1400412da  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x1400412e1  call    CxPlatLogAssert
0x1400412e6  int     2Ch; Windows NT - assertion failure
0x1400412e8  test    cs:byte_14005C48D, 2
0x1400412ef  jz      short loc_140041303
0x1400412f1  mov     r9, rdi
0x1400412f4  lea     rdx, QuicStreamAppReceiveCompleteCall
0x1400412fb  mov     r8, rbx
0x1400412fe  call    McTemplateU0pp_EtwWriteTransfer
0x140041303  mov     rcx, rdi
0x140041306  lock xadd [rbx+2B8h], rcx
0x14004130f  mov     rax, rcx
0x140041312  and     rax, rdi
0x140041315  bt      rax, 3Eh ; '>'
0x14004131a  jnb     short loc_14004139A
0x14004131c  test    cs:byte_14005C48C, 10h
0x140041323  jz      short loc_14004133B
0x140041325  lea     r9, aRecvcompletion; "RecvCompletionLength is overflow"
0x14004132c  mov     r8, rbx
0x14004132f  lea     rdx, QuicStreamError
0x140041336  call    McTemplateU0ps_EtwWriteTransfer
0x14004133b  xor     eax, eax
0x14004133d  lea     ecx, [rax+1]
0x140041340  lock cmpxchg [rsi+630h], cx
0x140041349  test    ax, ax
0x14004134c  jnz     short loc_1400413BF
0x14004134e  lea     rdx, [rsi+5C0h]
0x140041355  mov     [rdx+14h], bpl
0x140041359  lea     rax, [rsi+5F8h]
0x140041360  mov     [rdx+18h], rax
0x140041364  mov     [rdx+10h], ebp
0x140041367  mov     [rax], ecx
0x140041369  mov     rcx, rsi
0x14004136c  mov     rax, [rdx+18h]
0x140041370  mov     dword ptr [rax+18h], 8001h
0x140041377  mov     rax, [rdx+18h]
0x14004137b  mov     qword ptr [rax+20h], 0FFFFFFFFC0000184h
0x140041383  mov     rax, [rdx+18h]
0x140041387  and     byte ptr [rax+1Ch], 0FEh
0x14004138b  mov     rax, [rdx+18h]
0x14004138f  or      byte ptr [rax+1Ch], 2
0x140041393  call    QuicConnQueueHighestPriorityOper
0x140041398  jmp     short loc_1400413BF
0x14004139a  test    rcx, rcx
0x14004139d  js      short loc_1400413BF
0x14004139f  mov     rdx, rbp
0x1400413a2  xchg    rdx, [rbx+2D0h]
0x1400413a9  test    rdx, rdx
0x1400413ac  jz      short loc_1400413BF
0x1400413ae  lea     rcx, [rbx+10h]
0x1400413b2  call    CxPlatRefIncrement
0x1400413b7  mov     rcx, rsi
0x1400413ba  call    QuicConnQueueOper
0x1400413bf  test    cs:Microsoft_QuicEnableBits, 8
0x1400413c6  jz      short loc_1400413D4
0x1400413c8  lea     rdx, QuicApiExit
0x1400413cf  call    McTemplateU0_EtwWriteTransfer
0x1400413d4  mov     rbx, [rsp+28h+arg_0]
0x1400413d9  mov     rbp, [rsp+28h+arg_8]
0x1400413de  mov     rsi, [rsp+28h+arg_10]
0x1400413e3  add     rsp, 20h
0x1400413e7  pop     rdi
0x1400413e8  retn
```
