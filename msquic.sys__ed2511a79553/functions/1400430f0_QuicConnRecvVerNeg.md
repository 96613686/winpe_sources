# QuicConnRecvVerNeg

- ea: `0x1400430f0`
- end: `0x140043360`
- name: `QuicConnRecvVerNeg`
- size: `624`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x140015b70`

## callees

- `0x140005184`
- `0x1400123b0`
- `0x14001c638`
- `0x140026a88`
- `0x140029ef0`
- `0x14002a55c`
- `0x14002a634`
- `0x14002f204`
- `0x14003c8e0`
- `0x14003ead8`
- `0x14003ec10`
- `0x140042650`
- `0x1400430f0`
- `0x140043368`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140043173`
- `ntoskrnl!_snprintf_s` at `0x1400431d3`
- `ntoskrnl!_snprintf_s` at `0x14004329b`
- `ntoskrnl!_snprintf_s` at `0x1400432fe`
- `ntoskrnl!_snprintf_s` at `0x140043173`
- `ntoskrnl!_snprintf_s` at `0x1400431d3`
- `ntoskrnl!_snprintf_s` at `0x14004329b`
- `ntoskrnl!_snprintf_s` at `0x1400432fe`

## string_xrefs

- `0x140043286`: `Failed to update crypto on ver neg`

## pseudocode

```c
__int64 __fastcall QuicConnRecvVerNeg(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebp
  unsigned __int64 v5; // r12
  unsigned __int64 v6; // r14
  __int64 v7; // rcx
  unsigned __int16 v8; // si
  unsigned int v9; // edi
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v18; // rcx
  char DstBuf[128]; // [rsp+30h] [rbp-C8h] BYREF

  v4 = 0;
  v5 = *(unsigned __int8 *)(*(_QWORD *)(a2 + 56) + 5LL)
     + (unsigned __int64)*(unsigned __int8 *)(*(unsigned __int8 *)(*(_QWORD *)(a2 + 56) + 5LL)
                                            + *(_QWORD *)(a2 + 56)
                                            + 6LL)
     + *(_QWORD *)(a2 + 56)
     + 7LL;
  v6 = (*(unsigned __int16 *)(a2 + 80) - (unsigned __int64)(unsigned __int16)(v5 - *(_WORD *)(a2 + 56))) >> 2;
  if ( byte_14005C48E < 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[C][RX][-] VN");
    McTemplateU0s_EtwWriteTransfer(v7, QuicLogVerbose, DstBuf);
  }
  v8 = 0;
  if ( (_WORD)v6 )
  {
    do
    {
      v9 = *(_DWORD *)(v5 + 4LL * v8);
      if ( byte_14005C48E < 0 )
      {
        _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[C][RX][-]   Ver[%d]: 0x%x", v8, _byteswap_ulong(v9));
        McTemplateU0s_EtwWriteTransfer(v10, QuicLogVerbose, DstBuf);
      }
      if ( v9 == *(_DWORD *)(a1 + 3636) && !(unsigned __int8)QuicIsVersionReserved(v9) )
        return QuicPacketLogDrop(a1, a2, "Version Negotation that includes the current version");
      if ( !v4
        && ((unsigned __int8)QuicConnIsClient(a1)
         && (unsigned __int8)QuicVersionNegotiationExtIsVersionClientSupported(v11, v9)
         || (unsigned __int8)QuicConnIsServer(a1)
         && (unsigned __int8)QuicVersionNegotiationExtIsVersionServerSupported(v9)) )
      {
        v4 = v9;
      }
      ++v8;
    }
    while ( v8 < (unsigned __int16)v6 );
    if ( !v4 )
      goto LABEL_22;
    *(_DWORD *)(a1 + 3880) = *(_DWORD *)(a1 + 3636);
    *(_DWORD *)(a1 + 3636) = v4;
    QuicConnOnQuicVersionSet(a1);
    v12 = QuicCryptoOnVersionChange(a1 + 2784);
    v14 = v12;
    if ( v12 >= 0 )
    {
      LOBYTE(v13) = 1;
      return QuicConnRestart(a1, v13);
    }
    if ( (byte_14005C48B & 0x20) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Failed to update crypto on ver neg");
      McTemplateU0ps_EtwWriteTransfer(v15, QuicConnLogError, a1, DstBuf);
    }
    v16 = v14;
  }
  else
  {
LABEL_22:
    if ( (byte_14005C48B & 0x20) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Version Negotation contained no supported versions");
      McTemplateU0ps_EtwWriteTransfer(v18, QuicConnLogError, a1, DstBuf);
    }
    v16 = -1071382527;
  }
  return QuicConnCloseLocally(a1, 19, v16);
}

```

## disassembly

```asm
0x1400430f0  mov     [rsp+arg_10], rbx
0x1400430f5  push    rbp
0x1400430f6  push    rsi
0x1400430f7  push    rdi
0x1400430f8  push    r12
0x1400430fa  push    r13
0x1400430fc  push    r14
0x1400430fe  push    r15
0x140043100  sub     rsp, 0C0h
0x140043107  mov     rax, cs:__security_cookie
0x14004310e  xor     rax, rsp
0x140043111  mov     [rsp+0F8h+var_48], rax
0x140043119  mov     r15, rdx
0x14004311c  mov     rbx, rcx
0x14004311f  mov     rdx, [rdx+38h]
0x140043123  xor     r13d, r13d
0x140043126  mov     ebp, r13d
0x140043129  movzx   r14d, word ptr [r15+50h]
0x14004312e  movzx   eax, byte ptr [rdx+5]
0x140043132  lea     r12, [rdx+7]
0x140043136  movzx   ecx, byte ptr [rax+rdx+6]
0x14004313b  add     rcx, rax
0x14004313e  add     r12, rcx
0x140043141  movzx   eax, r12w
0x140043145  sub     ax, [r15+38h]
0x14004314a  movzx   ecx, ax
0x14004314d  mov     al, cs:byte_14005C48E
0x140043153  sub     r14, rcx
0x140043156  shr     r14, 2
0x14004315a  test    al, al
0x14004315c  jns     short loc_140043190
0x14004315e  lea     r9, aCRxVn; "[C][RX][-] VN"
0x140043165  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140043169  mov     edx, 80h; SizeInBytes
0x14004316e  lea     rcx, [rsp+0F8h+DstBuf]; DstBuf
0x140043173  call    cs:__imp__snprintf_s
0x14004317a  nop     dword ptr [rax+rax+00h]
0x14004317f  lea     r8, [rsp+0F8h+DstBuf]
0x140043184  lea     rdx, QuicLogVerbose
0x14004318b  call    McTemplateU0s_EtwWriteTransfer
0x140043190  movzx   esi, r13w
0x140043194  cmp     r13w, r14w
0x140043198  jnb     loc_1400432E0
0x14004319e  movzx   eax, si
0x1400431a1  mov     edi, [r12+rax*4]
0x1400431a5  mov     al, cs:byte_14005C48E
0x1400431ab  test    al, al
0x1400431ad  jns     short loc_1400431F0
0x1400431af  mov     ecx, edi
0x1400431b1  movzx   eax, si
0x1400431b4  bswap   ecx
0x1400431b6  mov     [rsp+0F8h+var_D0], ecx
0x1400431ba  lea     r9, aCRxVerD0xX; "[C][RX][-]   Ver[%d]: 0x%x"
0x1400431c1  lea     rcx, [rsp+0F8h+DstBuf]; DstBuf
0x1400431c6  mov     [rsp+0F8h+var_D8], eax
0x1400431ca  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400431ce  mov     edx, 80h; SizeInBytes
0x1400431d3  call    cs:__imp__snprintf_s
0x1400431da  nop     dword ptr [rax+rax+00h]
0x1400431df  lea     r8, [rsp+0F8h+DstBuf]
0x1400431e4  lea     rdx, QuicLogVerbose
0x1400431eb  call    McTemplateU0s_EtwWriteTransfer
0x1400431f0  cmp     edi, [rbx+0E34h]
0x1400431f6  jnz     short loc_140043207
0x1400431f8  mov     ecx, edi
0x1400431fa  call    QuicIsVersionReserved
0x1400431ff  test    al, al
0x140043201  jz      loc_1400432C0
0x140043207  test    ebp, ebp
0x140043209  jnz     short loc_14004323B
0x14004320b  mov     rcx, rbx
0x14004320e  call    QuicConnIsClient
0x140043213  test    al, al
0x140043215  jz      short loc_140043222
0x140043217  mov     edx, edi
0x140043219  call    QuicVersionNegotiationExtIsVersionClientSupported
0x14004321e  test    al, al
0x140043220  jnz     short loc_140043239
0x140043222  mov     rcx, rbx
0x140043225  call    QuicConnIsServer
0x14004322a  test    al, al
0x14004322c  jz      short loc_14004323B
0x14004322e  mov     ecx, edi
0x140043230  call    QuicVersionNegotiationExtIsVersionServerSupported
0x140043235  test    al, al
0x140043237  jz      short loc_14004323B
0x140043239  mov     ebp, edi
0x14004323b  inc     si
0x14004323e  cmp     si, r14w
0x140043242  jb      loc_14004319E
0x140043248  test    ebp, ebp
0x14004324a  jz      loc_1400432E0
0x140043250  mov     eax, [rbx+0E34h]
0x140043256  mov     rcx, rbx
0x140043259  mov     [rbx+0F28h], eax
0x14004325f  mov     [rbx+0E34h], ebp
0x140043265  call    QuicConnOnQuicVersionSet
0x14004326a  lea     rcx, [rbx+0AE0h]
0x140043271  call    QuicCryptoOnVersionChange
0x140043276  movsxd  rdi, eax
0x140043279  test    eax, eax
0x14004327b  jns     short loc_1400432D4
0x14004327d  test    cs:byte_14005C48B, 20h
0x140043284  jz      short loc_1400432BB
0x140043286  lea     r9, aFailedToUpdate_0; "Failed to update crypto on ver neg"
0x14004328d  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140043291  mov     edx, 80h; SizeInBytes
0x140043296  lea     rcx, [rsp+0F8h+DstBuf]; DstBuf
0x14004329b  call    cs:__imp__snprintf_s
0x1400432a2  nop     dword ptr [rax+rax+00h]
0x1400432a7  lea     r9, [rsp+0F8h+DstBuf]
0x1400432ac  mov     r8, rbx
0x1400432af  lea     rdx, QuicConnLogError
0x1400432b6  call    McTemplateU0ps_EtwWriteTransfer
0x1400432bb  mov     r8, rdi
0x1400432be  jmp     short loc_140043325
0x1400432c0  lea     r8, aVersionNegotat; "Version Negotation that includes the cu"...
0x1400432c7  mov     rdx, r15
0x1400432ca  mov     rcx, rbx
0x1400432cd  call    QuicPacketLogDrop
0x1400432d2  jmp     short loc_140043334
0x1400432d4  mov     dl, 1
0x1400432d6  mov     rcx, rbx
0x1400432d9  call    QuicConnRestart
0x1400432de  jmp     short loc_140043334
0x1400432e0  test    cs:byte_14005C48B, 20h
0x1400432e7  jz      short loc_14004331E
0x1400432e9  lea     r9, aVersionNegotat_0; "Version Negotation contained no support"...
0x1400432f0  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400432f4  mov     edx, 80h; SizeInBytes
0x1400432f9  lea     rcx, [rsp+0F8h+DstBuf]; DstBuf
0x1400432fe  call    cs:__imp__snprintf_s
0x140043305  nop     dword ptr [rax+rax+00h]
0x14004330a  lea     r9, [rsp+0F8h+DstBuf]
0x14004330f  mov     r8, rbx
0x140043312  lea     rdx, QuicConnLogError
0x140043319  call    McTemplateU0ps_EtwWriteTransfer
0x14004331e  mov     r8, 0FFFFFFFFC0240001h
0x140043325  xor     r9d, r9d
0x140043328  mov     rcx, rbx
0x14004332b  lea     edx, [r9+13h]
0x14004332f  call    QuicConnCloseLocally
0x140043334  mov     rcx, [rsp+0F8h+var_48]
0x14004333c  xor     rcx, rsp; StackCookie
0x14004333f  call    __security_check_cookie
0x140043344  mov     rbx, [rsp+0F8h+arg_10]
0x14004334c  add     rsp, 0C0h
0x140043353  pop     r15
0x140043355  pop     r14
0x140043357  pop     r13
0x140043359  pop     r12
0x14004335b  pop     rdi
0x14004335c  pop     rsi
0x14004335d  pop     rbp
0x14004335e  retn
```
