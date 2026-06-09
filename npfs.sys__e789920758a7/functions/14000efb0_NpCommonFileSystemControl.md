# NpCommonFileSystemControl

- ea: `0x14000efb0`
- end: `0x14000f3f7`
- name: `NpCommonFileSystemControl`
- size: `1095`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14000ef40`

## callees

- `0x14000172c`
- `0x140002240`
- `0x14000b15c`
- `0x14000b354`
- `0x14000b54c`
- `0x14000b84c`
- `0x14000bacc`
- `0x14000c800`
- `0x14000ca2c`
- `0x14000d728`
- `0x14000e490`
- `0x14000efb0`
- `0x14000f400`
- `0x14000f610`
- `0x14000f8c0`
- `0x14000fb00`
- `0x14000fb40`
- `0x1400100bc`
- `0x1400104c0`
- `0x140010890`
- `0x140015610`
- `0x1400156e8`
- `0x14001612c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000f0a5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000f0b7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000f0a5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000f0b7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f0e8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f105`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f179`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f18f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f0e8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f105`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f179`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f18f`
- `ntoskrnl!IofCompleteRequest` at `0x14000f03a`
- `ntoskrnl!IofCompleteRequest` at `0x14000f03a`

## pseudocode

```c
__int64 __fastcall NpCommonFileSystemControl(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  unsigned int v5; // eax
  unsigned int ClientProcessImpl; // ebp
  _QWORD *v7; // rbx
  IRP *v8; // rcx
  __int64 v10; // rbx
  unsigned __int64 v11; // rdi
  __int64 v12; // r8
  __int64 v13; // r9
  void *v14; // rbx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // ebp
  __int64 v20; // r14
  __int64 v21; // rbx
  __int64 v22; // rdi
  __int64 v23; // r10
  __int64 v24; // r8
  __int64 v25; // [rsp+28h] [rbp-40h]
  __int64 v26; // [rsp+30h] [rbp-38h]
  _QWORD v27[5]; // [rsp+40h] [rbp-28h] BYREF

  v4 = *(_QWORD *)(a2 + 184);
  v27[1] = v27;
  v27[0] = v27;
  v5 = *(_DWORD *)(v4 + 24);
  switch ( v5 )
  {
    case 0x110024u:
      v19 = *(_DWORD *)(v4 + 8);
      v20 = *(_QWORD *)(v4 + 48);
      if ( v19 < 0x10 )
      {
        ClientProcessImpl = -1073741811;
      }
      else
      {
        v21 = *(_QWORD *)(a2 + 24);
        v22 = 56;
        if ( v19 < 0x38 )
          v22 = 16;
        memset(*(void **)(a2 + 24), 0, (unsigned int)v22);
        v23 = v21 + 16;
        v24 = v21 + 18;
        if ( v19 < 0x38 )
        {
          v23 = 0;
          v24 = 0;
        }
        v26 = v23;
        v25 = v24;
        ClientProcessImpl = NpQueryClientProcessImpl(v20, v21, v24, v21 + 8);
        *(_QWORD *)(a2 + 56) = v22;
      }
      goto LABEL_7;
    case 0x11400Cu:
      ClientProcessImpl = NpPeek(a1, a2, v27, a1);
      goto LABEL_7;
    case 0x110004u:
      v10 = *(_QWORD *)(v4 + 48);
      if ( **(_WORD **)(v10 + 24) == 514 && (*(_QWORD *)(v10 + 32) & 1) != 0 )
      {
        if ( (*(_QWORD *)(v10 + 32) & 2) == 0 )
        {
          ClientProcessImpl = -1073741649;
          goto LABEL_7;
        }
        v11 = *(_QWORD *)(v10 + 32) & 0xFFFFFFFFFFFFFFFCuLL;
        ExAcquirePushLockExclusiveEx(*(_QWORD *)(v11 + 40) + 128LL, 0, a3, a1);
        ExAcquirePushLockExclusiveEx(v11 + 64, 0, v12, v13);
        if ( (*(_QWORD *)(v10 + 32) & 1) != 0 )
        {
          ClientProcessImpl = NpSetDisconnectedPipeState(v11, v27);
          ExReleasePushLockExclusiveEx(*(_QWORD *)(v11 + 40) + 128LL, 0);
          v14 = (void *)NpClearSecurity(v11);
          ExReleasePushLockExclusiveEx(v11 + 64, 0);
          NpFreeClientSecurityContext(v14);
          goto LABEL_7;
        }
        ExReleasePushLockExclusiveEx(v11 + 64, 0);
        ExReleasePushLockExclusiveEx(*(_QWORD *)(v11 + 40) + 128LL, 0);
      }
      ClientProcessImpl = -1073741648;
      goto LABEL_7;
  }
  if ( v5 != 1114136 )
  {
    if ( v5 <= 0x112FFC )
    {
      if ( v5 != 1126396 )
      {
        switch ( v5 )
        {
          case 0x110008u:
            ClientProcessImpl = NpListen(a1, a2, v27);
            goto LABEL_7;
          case 0x11001Cu:
            ClientProcessImpl = NpImpersonate(a1, a2, 0, a1);
            goto LABEL_7;
          case 0x110028u:
            ClientProcessImpl = NpGetAttribute(a2, 0, a3, a1);
            goto LABEL_7;
          case 0x11002Cu:
            ClientProcessImpl = NpSetAttribute(a2, 0, a3, a1);
            goto LABEL_7;
          case 0x110030u:
            ClientProcessImpl = NpGetAttribute(a2, 1, a3, a1);
            goto LABEL_7;
          case 0x110034u:
            ClientProcessImpl = NpSetAttribute(a2, 1, a3, a1);
            goto LABEL_7;
          case 0x110038u:
            ClientProcessImpl = NpGetAttribute(a2, 2, a3, a1);
            goto LABEL_7;
          case 0x11003Cu:
            ClientProcessImpl = NpSetAttribute(a2, 2, a3, a1);
            goto LABEL_7;
          case 0x110044u:
            ClientProcessImpl = NpImpersonate(a1, a2, 1, a1);
            goto LABEL_7;
          case 0x11004Cu:
            ClientProcessImpl = NpCreateSymlinkFsCtl(a1, a2);
            goto LABEL_7;
          case 0x110050u:
            ClientProcessImpl = NpDeleteSymlinkFsCtl(a1, a2);
            goto LABEL_7;
          case 0x110054u:
            ClientProcessImpl = NpQueryClientProcess(a1, a2, a3, a1);
            goto LABEL_7;
          default:
            return 3221225659LL;
        }
      }
      goto LABEL_41;
    }
    if ( v5 > 0x118048 )
    {
      switch ( v5 )
      {
        case 0x11C017u:
          ClientProcessImpl = NpTransceive(a1, a2, v27, a1);
          goto LABEL_7;
        case 0x11AFFCu:
LABEL_41:
          ClientProcessImpl = NpSelectEvents(a2, v4, a3, a1);
          goto LABEL_7;
        case 0x11DFFFu:
          ClientProcessImpl = NpInternalTransceive(a1, a2, v27, a1);
          goto LABEL_7;
        case 0x119FF8u:
          ClientProcessImpl = NpInternalWrite(a1, a2, v27, a1);
          goto LABEL_7;
      }
      return 3221225659LL;
    }
    if ( v5 == 1146952 )
    {
      ClientProcessImpl = NpSiloArrivalFsCtl(a2, v4, a3, a1);
      goto LABEL_7;
    }
    LOBYTE(a3) = 0;
    v15 = v5 - 1126400;
    if ( v15 )
    {
      v16 = v15 - 12276;
      if ( v16 )
      {
        v17 = v16 - 12;
        if ( v17 )
        {
          v18 = v17 - 4096;
          if ( v18 )
          {
            if ( v18 == 4160 )
            {
              ClientProcessImpl = NpCommonFlushBuffers(a1, a2, a3, a1);
              goto LABEL_7;
            }
            return 3221225659LL;
          }
          goto LABEL_39;
        }
        LOBYTE(a3) = 1;
      }
      ClientProcessImpl = NpInternalRead(a1, a2, a3, v27);
      goto LABEL_7;
    }
LABEL_39:
    ClientProcessImpl = NpEnumEvents(a2, v4, a3, a1);
    goto LABEL_7;
  }
  ClientProcessImpl = NpWaitForNamedPipe(a1, a2, a3, a1);
LABEL_7:
  v7 = (_QWORD *)v27[0];
  while ( v7 != v27 )
  {
    v8 = (IRP *)(v7 - 21);
    v7 = (_QWORD *)*v7;
    IofCompleteRequest(v8, 2);
  }
  return ClientProcessImpl;
}

```

## disassembly

```asm
0x14000efb0  mov     [rsp+arg_10], rbx
0x14000efb5  push    rbp
0x14000efb6  push    rsi
0x14000efb7  push    rdi
0x14000efb8  sub     rsp, 50h
0x14000efbc  lea     rax, [rsp+68h+var_28]
0x14000efc1  mov     rsi, rdx
0x14000efc4  mov     rdx, [rdx+0B8h]
0x14000efcb  mov     r9, rcx
0x14000efce  mov     [rsp+68h+var_20], rax
0x14000efd3  lea     rax, [rsp+68h+var_28]
0x14000efd8  mov     [rsp+68h+var_28], rax
0x14000efdd  mov     eax, [rdx+18h]
0x14000efe0  cmp     eax, 110024h
0x14000efe5  jz      loc_14000F381
0x14000efeb  cmp     eax, 11400Ch
0x14000eff0  jz      short loc_14000F010
0x14000eff2  cmp     eax, 110004h
0x14000eff7  jz      short loc_14000F063
0x14000eff9  cmp     eax, 110018h
0x14000effe  jnz     loc_14000F11E
0x14000f004  mov     rdx, rsi
0x14000f007  call    NpWaitForNamedPipe
0x14000f00c  mov     ebp, eax
0x14000f00e  jmp     short loc_14000F01F
0x14000f010  lea     r8, [rsp+68h+var_28]
0x14000f015  mov     rdx, rsi
0x14000f018  call    NpPeek
0x14000f01d  mov     ebp, eax
0x14000f01f  mov     rbx, [rsp+68h+var_28]
0x14000f024  lea     rax, [rsp+68h+var_28]
0x14000f029  cmp     rbx, rax
0x14000f02c  jz      short loc_14000F050
0x14000f02e  lea     rcx, [rbx-0A8h]; Irp
0x14000f035  mov     dl, 2; PriorityBoost
0x14000f037  mov     rbx, [rbx]
0x14000f03a  call    cs:__imp_IofCompleteRequest
0x14000f041  nop     dword ptr [rax+rax+00h]
0x14000f046  lea     rax, [rsp+68h+var_28]
0x14000f04b  cmp     rbx, rax
0x14000f04e  jnz     short loc_14000F02E
0x14000f050  mov     eax, ebp
0x14000f052  mov     rbx, [rsp+68h+arg_10]
0x14000f05a  add     rsp, 50h
0x14000f05e  pop     rdi
0x14000f05f  pop     rsi
0x14000f060  pop     rbp
0x14000f061  retn
0x14000f063  mov     rbx, [rdx+30h]
0x14000f067  mov     ecx, 202h
0x14000f06c  mov     rax, [rbx+18h]
0x14000f070  cmp     [rax], cx
0x14000f073  jnz     loc_14000F19B
0x14000f079  mov     rax, [rbx+20h]
0x14000f07d  test    al, 1
0x14000f07f  jz      loc_14000F19B
0x14000f085  mov     rax, [rbx+20h]
0x14000f089  shr     al, 1
0x14000f08b  test    al, 1
0x14000f08d  jz      loc_14000F224
0x14000f093  mov     rdi, [rbx+20h]
0x14000f097  xor     edx, edx
0x14000f099  and     rdi, 0FFFFFFFFFFFFFFFCh
0x14000f09d  mov     rcx, [rdi+28h]
0x14000f0a1  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14000f0a5  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000f0ac  nop     dword ptr [rax+rax+00h]
0x14000f0b1  xor     edx, edx
0x14000f0b3  lea     rcx, [rdi+40h]
0x14000f0b7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000f0be  nop     dword ptr [rax+rax+00h]
0x14000f0c3  mov     rax, [rbx+20h]
0x14000f0c7  test    al, 1
0x14000f0c9  jz      loc_14000F173
0x14000f0cf  lea     rdx, [rsp+68h+var_28]
0x14000f0d4  mov     rcx, rdi
0x14000f0d7  call    NpSetDisconnectedPipeState
0x14000f0dc  mov     rcx, [rdi+28h]
0x14000f0e0  xor     edx, edx
0x14000f0e2  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14000f0e6  mov     ebp, eax
0x14000f0e8  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000f0ef  nop     dword ptr [rax+rax+00h]
0x14000f0f4  mov     rcx, rdi
0x14000f0f7  call    NpClearSecurity
0x14000f0fc  xor     edx, edx
0x14000f0fe  lea     rcx, [rdi+40h]
0x14000f102  mov     rbx, rax
0x14000f105  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000f10c  nop     dword ptr [rax+rax+00h]
0x14000f111  mov     rcx, rbx; P
0x14000f114  call    NpFreeClientSecurityContext
0x14000f119  jmp     loc_14000F01F
0x14000f11e  cmp     eax, 112FFCh
0x14000f123  ja      loc_14000F1B7
0x14000f129  jz      loc_14000F2A4
0x14000f12f  add     eax, 0FFEEFFF8h; switch 77 cases
0x14000f134  cmp     eax, 4Ch
0x14000f137  ja      def_14000F156; jumptable 000000014000F156 default case, cases 1114121-1114139,1114141-1114151,1114153-1114155,1114157-1114159,1114161-1114163,1114165-1114167,1114169-1114171,1114173-1114179,1114181-1114187,1114189-1114191,1114193-1114195
0x14000f13d  lea     rdx, cs:140000000h
0x14000f144  movzx   eax, ds:(byte_140004520 - 140000000h)[rdx+rax]
0x14000f14c  mov     ecx, ds:(jpt_14000F156 - 140000000h)[rdx+rax*4]
0x14000f153  add     rcx, rdx
0x14000f156  jmp     rcx; switch jump
0x14000f15c  lea     r8, [rsp+68h+var_28]; jumptable 000000014000F156 case 1114120
0x14000f161  mov     rdx, rsi
0x14000f164  mov     rcx, r9
0x14000f167  call    NpListen
0x14000f16c  mov     ebp, eax
0x14000f16e  jmp     loc_14000F01F
0x14000f173  xor     edx, edx
0x14000f175  lea     rcx, [rdi+40h]
0x14000f179  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000f180  nop     dword ptr [rax+rax+00h]
0x14000f185  mov     rcx, [rdi+28h]
0x14000f189  xor     edx, edx
0x14000f18b  sub     rcx, 0FFFFFFFFFFFFFF80h
0x14000f18f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000f196  nop     dword ptr [rax+rax+00h]
0x14000f19b  mov     ebp, 0C00000B0h
0x14000f1a0  jmp     loc_14000F01F
0x14000f1a5  xor     r8d, r8d; jumptable 000000014000F156 case 1114140
0x14000f1a8  mov     rdx, rsi
0x14000f1ab  call    NpImpersonate
0x14000f1b0  mov     ebp, eax
0x14000f1b2  jmp     loc_14000F01F
0x14000f1b7  cmp     eax, 118048h
0x14000f1bc  jbe     short loc_14000F22E
0x14000f1be  cmp     eax, 11C017h
0x14000f1c3  jnz     short loc_14000F1D9
0x14000f1c5  lea     r8, [rsp+68h+var_28]
0x14000f1ca  mov     rdx, rsi
0x14000f1cd  call    NpTransceive
0x14000f1d2  mov     ebp, eax
0x14000f1d4  jmp     loc_14000F01F
0x14000f1d9  cmp     eax, 11AFFCh
0x14000f1de  jz      loc_14000F2A4
0x14000f1e4  cmp     eax, 11DFFFh
0x14000f1e9  jz      loc_14000F2B3
0x14000f1ef  cmp     eax, 119FF8h
0x14000f1f4  jz      loc_14000F36D
0x14000f1fa  mov     rbx, [rsp+68h+arg_10]; jumptable 000000014000F156 default case, cases 1114121-1114139,1114141-1114151,1114153-1114155,1114157-1114159,1114161-1114163,1114165-1114167,1114169-1114171,1114173-1114179,1114181-1114187,1114189-1114191,1114193-1114195
0x14000f202  mov     eax, 0C00000BBh
0x14000f207  add     rsp, 50h
0x14000f20b  pop     rdi
0x14000f20c  pop     rsi
0x14000f20d  pop     rbp
0x14000f20e  retn
0x14000f210  mov     edx, 1; jumptable 000000014000F156 case 1114160
0x14000f215  mov     rcx, rsi
0x14000f218  call    NpGetAttribute
0x14000f21d  mov     ebp, eax
0x14000f21f  jmp     loc_14000F01F
0x14000f224  mov     ebp, 0C00000AFh
0x14000f229  jmp     loc_14000F01F
0x14000f22e  jz      loc_14000F35E
0x14000f234  xor     r8b, r8b
0x14000f237  sub     eax, 113000h
0x14000f23c  jz      short loc_14000F280
0x14000f23e  sub     eax, 2FF4h
0x14000f243  jz      loc_14000F34A
0x14000f249  sub     eax, 0Ch
0x14000f24c  jz      loc_14000F347
0x14000f252  sub     eax, 1000h
0x14000f257  jz      short loc_14000F280
0x14000f259  cmp     eax, 1040h
0x14000f25e  jnz     short def_14000F156; jumptable 000000014000F156 default case, cases 1114121-1114139,1114141-1114151,1114153-1114155,1114157-1114159,1114161-1114163,1114165-1114167,1114169-1114171,1114173-1114179,1114181-1114187,1114189-1114191,1114193-1114195
0x14000f260  mov     rdx, rsi
0x14000f263  call    NpCommonFlushBuffers
0x14000f268  mov     ebp, eax
0x14000f26a  jmp     loc_14000F01F
0x14000f26f  xor     edx, edx; jumptable 000000014000F156 case 1114152
0x14000f271  mov     rcx, rsi
0x14000f274  call    NpGetAttribute
0x14000f279  mov     ebp, eax
0x14000f27b  jmp     loc_14000F01F
0x14000f280  mov     rcx, rsi
0x14000f283  call    NpEnumEvents
0x14000f288  mov     ebp, eax
0x14000f28a  jmp     loc_14000F01F
0x14000f28f  mov     r8d, 1; jumptable 000000014000F156 case 1114180
0x14000f295  mov     rdx, rsi
0x14000f298  call    NpImpersonate
0x14000f29d  mov     ebp, eax
0x14000f29f  jmp     loc_14000F01F
0x14000f2a4  mov     rcx, rsi
0x14000f2a7  call    NpSelectEvents
0x14000f2ac  mov     ebp, eax
0x14000f2ae  jmp     loc_14000F01F
0x14000f2b3  lea     r8, [rsp+68h+var_28]
0x14000f2b8  mov     rdx, rsi
0x14000f2bb  call    NpInternalTransceive
0x14000f2c0  mov     ebp, eax
0x14000f2c2  jmp     loc_14000F01F
0x14000f2c7  mov     rdx, rsi; jumptable 000000014000F156 case 1114196
0x14000f2ca  call    NpQueryClientProcess
0x14000f2cf  mov     ebp, eax
0x14000f2d1  jmp     loc_14000F01F
0x14000f2d6  xor     edx, edx; jumptable 000000014000F156 case 1114156
0x14000f2d8  mov     rcx, rsi
0x14000f2db  call    NpSetAttribute
0x14000f2e0  mov     ebp, eax
0x14000f2e2  jmp     loc_14000F01F
0x14000f2e7  mov     edx, 1; jumptable 000000014000F156 case 1114164
0x14000f2ec  mov     rcx, rsi
0x14000f2ef  call    NpSetAttribute
0x14000f2f4  mov     ebp, eax
0x14000f2f6  jmp     loc_14000F01F
0x14000f2fb  mov     edx, 2; jumptable 000000014000F156 case 1114168
0x14000f300  mov     rcx, rsi
0x14000f303  call    NpGetAttribute
0x14000f308  mov     ebp, eax
0x14000f30a  jmp     loc_14000F01F
0x14000f30f  mov     edx, 2; jumptable 000000014000F156 case 1114172
0x14000f314  mov     rcx, rsi
0x14000f317  call    NpSetAttribute
0x14000f31c  mov     ebp, eax
0x14000f31e  jmp     loc_14000F01F
0x14000f323  mov     rdx, rsi; jumptable 000000014000F156 case 1114188
0x14000f326  mov     rcx, r9
0x14000f329  call    NpCreateSymlinkFsCtl
0x14000f32e  mov     ebp, eax
0x14000f330  jmp     loc_14000F01F
0x14000f335  mov     rdx, rsi; jumptable 000000014000F156 case 1114192
0x14000f338  mov     rcx, r9
0x14000f33b  call    NpDeleteSymlinkFsCtl
0x14000f340  mov     ebp, eax
0x14000f342  jmp     loc_14000F01F
0x14000f347  mov     r8b, 1
0x14000f34a  lea     r9, [rsp+68h+var_28]
0x14000f34f  mov     rdx, rsi
0x14000f352  call    NpInternalRead
0x14000f357  mov     ebp, eax
0x14000f359  jmp     loc_14000F01F
0x14000f35e  mov     rcx, rsi
0x14000f361  call    NpSiloArrivalFsCtl
0x14000f366  mov     ebp, eax
0x14000f368  jmp     loc_14000F01F
0x14000f36d  lea     r8, [rsp+68h+var_28]
0x14000f372  mov     rdx, rsi
0x14000f375  call    NpInternalWrite
0x14000f37a  mov     ebp, eax
0x14000f37c  jmp     loc_14000F01F
0x14000f381  mov     ebp, [rdx+8]
0x14000f384  mov     [rsp+68h+arg_0], r14
0x14000f389  mov     r14, [rdx+30h]
0x14000f38d  cmp     ebp, 10h
0x14000f390  jb      short loc_14000F3E8
0x14000f392  mov     rbx, [rsi+18h]
0x14000f396  mov     edi, 38h ; '8'
0x14000f39b  mov     eax, 10h
0x14000f3a0  cmp     ebp, edi
0x14000f3a2  mov     rcx, rbx; void *
0x14000f3a5  cmovb   edi, eax
0x14000f3a8  xor     edx, edx; Val
0x14000f3aa  mov     r8d, edi; Size
0x14000f3ad  call    memset
0x14000f3b2  xor     eax, eax
0x14000f3b4  lea     r10, [rbx+10h]
0x14000f3b8  cmp     ebp, 38h ; '8'
0x14000f3bb  lea     r8, [rbx+12h]
0x14000f3bf  lea     r9, [rbx+8]
0x14000f3c3  mov     rdx, rbx
0x14000f3c6  cmovb   r10, rax
0x14000f3ca  cmovb   r8, rax
0x14000f3ce  mov     [rsp+68h+var_38], r10
0x14000f3d3  mov     rcx, r14
0x14000f3d6  mov     [rsp+68h+var_40], r8
0x14000f3db  call    NpQueryClientProcessImpl
0x14000f3e0  mov     ebp, eax
0x14000f3e2  mov     [rsi+38h], rdi
0x14000f3e6  jmp     short loc_14000F3ED
0x14000f3e8  mov     ebp, 0C000000Dh
0x14000f3ed  mov     r14, [rsp+68h+arg_0]
0x14000f3f2  jmp     loc_14000F01F
```
