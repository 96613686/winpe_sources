# Np::WriteSyncPost(SNI_Packet *)

- ea: `0x1004243d0`
- end: `0x1004245cd`
- name: `?WriteSyncPost@Np@@UEAAKPEAVSNI_Packet@@@Z`
- size: `509`
- prototype: `unsigned int __fastcall(Np *__hidden this, struct SNI_Packet *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1004243d0`
- `0x10043a7c4`
- `0x10043a930`
- `0x10043b2b4`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100546b88`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10042446f`
- `KERNEL32!GetLastError` at `0x10042446f`
- `KERNEL32!WriteFile` at `0x100424461`
- `KERNEL32!WriteFile` at `0x100424461`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::WriteSyncPost(HANDLE *this, struct _OVERLAPPED *a2)
{
  char *v4; // rbp
  DWORD hEvent; // r14d
  DWORD LastError; // edi
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+8h] BYREF
  __int64 v9; // [rsp+68h] [rbp+10h] BYREF

  v9 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7A08[0] )
    bidScopeEnterW(&v9, off_1005E7A08[0], *((unsigned int *)this + 11));
  NumberOfBytesWritten = 0;
  v4 = (char *)a2[2].Pointer + LODWORD(a2[3].Internal);
  hEvent = (DWORD)a2[2].hEvent;
  SNI::detail::Transport::PrepareForSyncCall((SNI::detail::Transport *)this, (struct SNI_Packet *)a2);
  a2->Offset = 0;
  a2->OffsetHigh = 0;
  if ( WriteFile(this[8], v4, hEvent, &NumberOfBytesWritten, a2) )
  {
    LastError = 0;
    if ( (bidGblFlags & 0x24002) == 0x24002 && off_1005E4DD8[0] )
      bidTraceW(0, 723968, off_1005E4DD8[0], NumberOfBytesWritten);
    if ( (bidGblFlags & 0x24002) == 0x24002 )
      bidWriteBin(bidID, 16, v4, NumberOfBytesWritten, 0);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E4DC8[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(0, 712704, off_1005E4DC8[0], *((unsigned int *)this + 18));
      }
      SNISetLastError(*((unsigned int *)this + 18), LastError, 50100);
      if ( (bidGblFlags & 0x24002) == 0x24002 && off_1005E4DD0[0] )
        bidTraceW(0, 715776, off_1005E4DD0[0], hEvent);
      if ( (bidGblFlags & 0x24002) == 0x24002 )
        bidWriteBin(bidID, 16, v4, hEvent, 0);
    }
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4DE0[0] )
    bidTraceW(0, 728064, off_1005E4DE0[0], LastError);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v9);
  return LastError;
}

```

## disassembly

```asm
0x1004243d0  mov     r11, rsp
0x1004243d3  push    rsi
0x1004243d4  push    rdi
0x1004243d5  push    r14
0x1004243d7  sub     rsp, 40h
0x1004243db  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x1004243e3  mov     [r11+18h], rbx
0x1004243e7  mov     [r11+20h], rbp
0x1004243eb  mov     rbx, rdx
0x1004243ee  mov     rsi, rcx
0x1004243f1  or      qword ptr [r11+10h], 0FFFFFFFFFFFFFFFFh
0x1004243f6  mov     eax, cs:_bidGblFlags
0x1004243fc  mov     ecx, 20004h
0x100424401  and     eax, ecx
0x100424403  cmp     eax, ecx
0x100424405  jnz     short loc_10042442A
0x100424407  mov     rax, cs:off_1005E7A08; "<Np::WriteSyncPost|API|SNI> %u#, pPacke"...
0x10042440e  test    rax, rax
0x100424411  jz      short loc_10042442A
0x100424413  mov     r9, rdx
0x100424416  mov     r8d, [rsi+2Ch]
0x10042441a  mov     rdx, cs:off_1005E7A08; "<Np::WriteSyncPost|API|SNI> %u#, pPacke"...
0x100424421  lea     rcx, [r11+10h]
0x100424425  call    _bidScopeEnterW
0x10042442a  and     [rsp+58h+NumberOfBytesWritten], 0
0x10042442f  mov     ebp, [rbx+60h]
0x100424432  add     rbp, [rbx+50h]
0x100424436  mov     r14d, [rbx+58h]
0x10042443a  mov     rdx, rbx; struct SNI_Packet *
0x10042443d  mov     rcx, rsi; this
0x100424440  call    ?PrepareForSyncCall@Transport@detail@SNI@@IEAAXPEAVSNI_Packet@@@Z; SNI::detail::Transport::PrepareForSyncCall(SNI_Packet *)
0x100424445  and     dword ptr [rbx+10h], 0
0x100424449  and     dword ptr [rbx+14h], 0
0x10042444d  mov     [rsp+58h+lpOverlapped], rbx; lpOverlapped
0x100424452  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x100424457  mov     r8d, r14d; nNumberOfBytesToWrite
0x10042445a  mov     rdx, rbp; lpBuffer
0x10042445d  mov     rcx, [rsi+40h]; hFile
0x100424461  call    cs:__imp_WriteFile
0x100424467  test    eax, eax
0x100424469  jnz     loc_100424519
0x10042446f  call    cs:__imp_GetLastError
0x100424475  mov     edi, eax
0x100424477  cmp     eax, 3E5h
0x10042447c  jz      loc_10042457A
0x100424482  mov     ebx, 0C3B4h
0x100424487  test    byte ptr cs:_bidGblFlags, 2
0x10042448e  jz      short loc_1004244C2
0x100424490  mov     rcx, cs:off_1005E4DC8; "<Np::WriteSyncPost|ERR|SNI> ProviderNum"...
0x100424497  test    rcx, rcx
0x10042449a  jz      short loc_1004244C2
0x10042449c  mov     ecx, ebx; unsigned int
0x10042449e  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1004244a3  mov     [rsp+58h+var_30], edi
0x1004244a7  mov     dword ptr [rsp+58h+lpOverlapped], eax
0x1004244ab  mov     r9d, [rsi+48h]
0x1004244af  mov     r8, cs:off_1005E4DC8; "<Np::WriteSyncPost|ERR|SNI> ProviderNum"...
0x1004244b6  mov     edx, 0AE000h
0x1004244bb  xor     ecx, ecx
0x1004244bd  call    _bidTraceW
0x1004244c2  mov     r8d, ebx
0x1004244c5  mov     edx, edi
0x1004244c7  mov     ecx, [rsi+48h]
0x1004244ca  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004244cf  mov     eax, cs:_bidGblFlags
0x1004244d5  mov     ebx, 24002h
0x1004244da  and     eax, ebx
0x1004244dc  cmp     eax, ebx
0x1004244de  jnz     short loc_100424502
0x1004244e0  mov     rax, cs:off_1005E4DD0; "<Np::WriteSyncPost|ERR|SNI> Send Packet"...
0x1004244e7  test    rax, rax
0x1004244ea  jz      short loc_100424502
0x1004244ec  mov     r9d, r14d
0x1004244ef  mov     r8, cs:off_1005E4DD0; "<Np::WriteSyncPost|ERR|SNI> Send Packet"...
0x1004244f6  mov     edx, 0AEC00h
0x1004244fb  xor     ecx, ecx
0x1004244fd  call    _bidTraceW
0x100424502  mov     eax, cs:_bidGblFlags
0x100424508  and     eax, ebx
0x10042450a  cmp     eax, ebx
0x10042450c  jnz     short loc_10042457A
0x10042450e  and     [rsp+58h+lpOverlapped], 0
0x100424514  mov     r9d, r14d
0x100424517  jmp     short loc_100424566
0x100424519  xor     edi, edi
0x10042451b  mov     eax, cs:_bidGblFlags
0x100424521  mov     ebx, 24002h
0x100424526  and     eax, ebx
0x100424528  cmp     eax, ebx
0x10042452a  jnz     short loc_100424550
0x10042452c  mov     rax, cs:off_1005E4DD8; "<Np::WriteSyncPost|SNI> Send Packet, By"...
0x100424533  test    rax, rax
0x100424536  jz      short loc_100424550
0x100424538  mov     r9d, [rsp+58h+NumberOfBytesWritten]
0x10042453d  mov     r8, cs:off_1005E4DD8; "<Np::WriteSyncPost|SNI> Send Packet, By"...
0x100424544  mov     edx, 0B0C00h
0x100424549  xor     ecx, ecx
0x10042454b  call    _bidTraceW
0x100424550  mov     eax, cs:_bidGblFlags
0x100424556  and     eax, ebx
0x100424558  cmp     eax, ebx
0x10042455a  jnz     short loc_10042457A
0x10042455c  and     [rsp+58h+lpOverlapped], rdi
0x100424561  mov     r9d, [rsp+58h+NumberOfBytesWritten]
0x100424566  mov     r8, rbp
0x100424569  mov     edx, 10h
0x10042456e  mov     rcx, cs:_bidID
0x100424575  call    _bidWriteBin
0x10042457a  mov     eax, cs:_bidGblFlags
0x100424580  mov     ecx, 20002h
0x100424585  and     eax, ecx
0x100424587  cmp     eax, ecx
0x100424589  jnz     short loc_1004245AE
0x10042458b  mov     rax, cs:off_1005E4DE0; "<Np::WriteSyncPost|RET|SNI> %d{WINERR}"...
0x100424592  test    rax, rax
0x100424595  jz      short loc_1004245AE
0x100424597  mov     r9d, edi
0x10042459a  mov     r8, cs:off_1005E4DE0; "<Np::WriteSyncPost|RET|SNI> %d{WINERR}"...
0x1004245a1  mov     edx, 0B1C00h
0x1004245a6  xor     ecx, ecx
0x1004245a8  call    _bidTraceW
0x1004245ad  nop
0x1004245ae  lea     rcx, [rsp+58h+arg_8]; this
0x1004245b3  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1004245b8  mov     eax, edi
0x1004245ba  mov     rbx, [rsp+58h+arg_10]
0x1004245bf  mov     rbp, [rsp+58h+arg_18]
0x1004245c4  add     rsp, 40h
0x1004245c8  pop     r14
0x1004245ca  pop     rdi
0x1004245cb  pop     rsi
0x1004245cc  retn
```
