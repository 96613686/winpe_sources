# PptpCmOpenAf

- ea: `0x140002520`
- end: `0x1400026b5`
- name: `PptpCmOpenAf`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002520`
- `0x140003e08`
- `0x140003e38`

## import_xrefs

- `NDIS!NdisResetEvent` at `0x1400025f1`
- `NDIS!NdisResetEvent` at `0x1400025f1`

## pseudocode

```c
__int64 __fastcall PptpCmOpenAf(__int64 a1, _DWORD *a2, signed __int64 a3, _QWORD *a4)
{
  signed __int32 v9; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
  }
  if ( *a2 == 2049 && a2[1] == 6 && a2[2] == 30 )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 152), a3, 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
      }
      return 3221225473LL;
    }
    else
    {
      if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 24)) == 1 )
        NdisResetEvent((PNDIS_EVENT)(a1 + 168));
      v9 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 160), 1u);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids,
          (unsigned int)(v9 + 1));
      }
      *a4 = a1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
      }
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
    }
    return 3221291012LL;
  }
}

```

## disassembly

```asm
0x140002520  mov     [rsp+arg_8], rbx
0x140002525  mov     [rsp+arg_10], rbp
0x14000252a  push    rsi
0x14000252b  push    rdi
0x14000252c  push    r14
0x14000252e  sub     rsp, 20h
0x140002532  mov     r14, r9
0x140002535  mov     rsi, r8
0x140002538  mov     rbx, rdx
0x14000253b  mov     rdi, rcx
0x14000253e  mov     rcx, cs:WPP_GLOBAL_Control
0x140002545  lea     rbp, WPP_GLOBAL_Control
0x14000254c  cmp     rcx, rbp
0x14000254f  jz      short loc_140002573
0x140002551  mov     eax, [rcx+2Ch]
0x140002554  test    al, 4
0x140002556  jz      short loc_140002573
0x140002558  cmp     byte ptr [rcx+29h], 2
0x14000255c  jb      short loc_140002573
0x14000255e  mov     rcx, [rcx+18h]
0x140002562  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140002569  mov     edx, 0Fh
0x14000256e  call    WPP_SF_
0x140002573  cmp     dword ptr [rbx], 801h
0x140002579  jnz     loc_14000266E
0x14000257f  cmp     dword ptr [rbx+4], 6
0x140002583  jnz     loc_14000266E
0x140002589  cmp     dword ptr [rbx+8], 1Eh
0x14000258d  jnz     loc_14000266E
0x140002593  xor     eax, eax
0x140002595  lock cmpxchg [rdi+98h], rsi
0x14000259e  jz      short loc_1400025D8
0x1400025a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400025a7  cmp     rcx, rbp
0x1400025aa  jz      short loc_1400025CE
0x1400025ac  mov     eax, [rcx+2Ch]
0x1400025af  test    al, 4
0x1400025b1  jz      short loc_1400025CE
0x1400025b3  cmp     byte ptr [rcx+29h], 1
0x1400025b7  jb      short loc_1400025CE
0x1400025b9  mov     rcx, [rcx+18h]
0x1400025bd  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x1400025c4  mov     edx, 11h
0x1400025c9  call    WPP_SF_
0x1400025ce  mov     eax, 0C0000001h
0x1400025d3  jmp     loc_1400026A1
0x1400025d8  mov     ebx, 1
0x1400025dd  mov     eax, ebx
0x1400025df  lock xadd [rdi+18h], eax
0x1400025e4  inc     eax
0x1400025e6  cmp     eax, ebx
0x1400025e8  jnz     short loc_1400025FD
0x1400025ea  lea     rcx, [rdi+0A8h]; Event
0x1400025f1  call    cs:__imp_NdisResetEvent
0x1400025f8  nop     dword ptr [rax+rax+00h]
0x1400025fd  lock xadd [rdi+0A0h], ebx
0x140002605  mov     rcx, cs:WPP_GLOBAL_Control
0x14000260c  cmp     rcx, rbp
0x14000260f  jz      short loc_140002639
0x140002611  test    dword ptr [rcx+2Ch], 400h
0x140002618  jz      short loc_140002639
0x14000261a  cmp     byte ptr [rcx+29h], 2
0x14000261e  jb      short loc_140002639
0x140002620  mov     rcx, [rcx+18h]
0x140002624  lea     r9d, [rbx+1]
0x140002628  mov     edx, 0Ah
0x14000262d  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140002634  call    WPP_SF_d
0x140002639  mov     [r14], rdi
0x14000263c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002643  cmp     rcx, rbp
0x140002646  jz      short loc_14000266A
0x140002648  mov     eax, [rcx+2Ch]
0x14000264b  test    al, 4
0x14000264d  jz      short loc_14000266A
0x14000264f  cmp     byte ptr [rcx+29h], 2
0x140002653  jb      short loc_14000266A
0x140002655  mov     rcx, [rcx+18h]
0x140002659  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140002660  mov     edx, 12h
0x140002665  call    WPP_SF_
0x14000266a  xor     eax, eax
0x14000266c  jmp     short loc_1400026A1
0x14000266e  mov     rcx, cs:WPP_GLOBAL_Control
0x140002675  cmp     rcx, rbp
0x140002678  jz      short loc_14000269C
0x14000267a  mov     eax, [rcx+2Ch]
0x14000267d  test    al, 4
0x14000267f  jz      short loc_14000269C
0x140002681  cmp     byte ptr [rcx+29h], 1
0x140002685  jb      short loc_14000269C
0x140002687  mov     rcx, [rcx+18h]
0x14000268b  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140002692  mov     edx, 10h
0x140002697  call    WPP_SF_
0x14000269c  mov     eax, 0C0010004h
0x1400026a1  mov     rbx, [rsp+38h+arg_8]
0x1400026a6  mov     rbp, [rsp+38h+arg_10]
0x1400026ab  add     rsp, 20h
0x1400026af  pop     r14
0x1400026b1  pop     rdi
0x1400026b2  pop     rsi
0x1400026b3  retn
```
