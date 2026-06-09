# MRxDAVPrecompleteUserModeQueryVolumeInformationRequest

- ea: `0x1400214d0`
- end: `0x140021715`
- name: `MRxDAVPrecompleteUserModeQueryVolumeInformationRequest`
- size: `581`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x14000163c`
- `0x140001680`
- `0x140001b64`
- `0x1400214d0`
- `0x140027a20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140021511`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021545`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021637`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021691`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400216d5`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021511`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021545`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021637`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140021691`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400216d5`

## pseudocode

```c
__int64 __fastcall MRxDAVPrecompleteUserModeQueryVolumeInformationRequest(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        int a5)
{
  int v8; // edi
  __int64 v9; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v11; // rbx
  HANDLE v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rbx
  HANDLE v16; // rax
  __int64 v17; // rbx
  HANDLE v18; // rax
  __int64 v19; // rdx

  v8 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v9, 109, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v12 = PsGetCurrentThreadId();
      WPP_SF_qqq(v11, 110, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v12, a1, a2);
    }
  }
  if ( a5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v16 = PsGetCurrentThreadId();
      WPP_SF_qqq(v15, 111, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v16, a1, a2);
    }
  }
  else if ( !*(_DWORD *)(a1 + 128) )
  {
    v13 = *(_QWORD *)(a2 + 456);
    if ( *(_DWORD *)(a2 + 448) == 3 )
    {
      *(_DWORD *)(v13 + 16) = 1;
      *(_DWORD *)(v13 + 20) = 512;
      *(_QWORD *)v13 = a3[289] / 512LL;
      *(_QWORD *)(v13 + 8) = a3[290] / 512LL;
    }
    else
    {
      *(_DWORD *)(v13 + 24) = 1;
      *(_DWORD *)(v13 + 28) = 512;
      *(_QWORD *)v13 = a3[289] / 512LL;
      v14 = a3[290] / 512LL;
      *(_QWORD *)(v13 + 16) = v14;
      *(_DWORD *)(v13 + 8) = v14;
      *(_DWORD *)(v13 + 12) = *(_DWORD *)(v13 + 20);
    }
  }
  if ( a3[79] && (v8 = UMRxFreeSecondaryBuffer(a1)) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v18 = PsGetCurrentThreadId();
      v19 = 112;
LABEL_25:
      WPP_SF_qD(v17, v19, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids, v18, v8);
    }
  }
  else if ( a3[80] )
  {
    v8 = UMRxFreeSecondaryBuffer(a1);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
      {
        v17 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v18 = PsGetCurrentThreadId();
        v19 = 113;
        goto LABEL_25;
      }
    }
  }
  *(_DWORD *)(a1 + 128) = v8;
  return 1;
}

```

## disassembly

```asm
0x1400214d0  push    rbx
0x1400214d2  push    rbp
0x1400214d3  push    rsi
0x1400214d4  push    rdi
0x1400214d5  push    r12
0x1400214d7  push    r13
0x1400214d9  push    r14
0x1400214db  push    r15
0x1400214dd  sub     rsp, 38h
0x1400214e1  mov     r14, r8
0x1400214e4  mov     rbp, rdx
0x1400214e7  mov     rsi, rcx
0x1400214ea  xor     edi, edi
0x1400214ec  mov     rbx, cs:WPP_GLOBAL_Control
0x1400214f3  lea     r12, WPP_GLOBAL_Control
0x1400214fa  lea     r13, WPP_46ebb9c74c923a3c1b1165bf6cfc7066_Traceguids
0x140021501  cmp     rbx, r12
0x140021504  jz      short loc_14002156E
0x140021506  bt      dword ptr [rbx+2Ch], 0Dh
0x14002150b  jnb     short loc_14002152E
0x14002150d  mov     rbx, [rbx+18h]
0x140021511  call    cs:__imp_PsGetCurrentThreadId
0x140021518  nop     dword ptr [rax+rax+00h]
0x14002151d  lea     edx, [rdi+6Dh]
0x140021520  mov     r8, r13
0x140021523  mov     r9, rax
0x140021526  mov     rcx, rbx
0x140021529  call    WPP_SF_q
0x14002152e  mov     rbx, cs:WPP_GLOBAL_Control
0x140021535  cmp     rbx, r12
0x140021538  jz      short loc_14002156E
0x14002153a  bt      dword ptr [rbx+2Ch], 0Dh
0x14002153f  jnb     short loc_14002156E
0x140021541  mov     rbx, [rbx+18h]
0x140021545  call    cs:__imp_PsGetCurrentThreadId
0x14002154c  nop     dword ptr [rax+rax+00h]
0x140021551  mov     edx, 6Eh ; 'n'
0x140021556  mov     [rsp+78h+var_50], rbp
0x14002155b  mov     r9, rax
0x14002155e  mov     [rsp+78h+var_58], rsi
0x140021563  mov     r8, r13
0x140021566  mov     rcx, rbx
0x140021569  call    WPP_SF_qqq
0x14002156e  mov     eax, 1
0x140021573  cmp     [rsp+78h+arg_20], edi
0x14002157a  jnz     loc_140021620
0x140021580  cmp     [rsi+80h], edi
0x140021586  jnz     loc_140021660
0x14002158c  cmp     dword ptr [rbp+1C0h], 3
0x140021593  mov     r8d, 1FFh
0x140021599  mov     rcx, [rbp+1C8h]
0x1400215a0  jnz     short loc_1400215DE
0x1400215a2  mov     [rcx+10h], eax
0x1400215a5  mov     dword ptr [rcx+14h], 200h
0x1400215ac  mov     rax, [r14+908h]
0x1400215b3  cqo
0x1400215b5  and     rdx, r8
0x1400215b8  add     rax, rdx
0x1400215bb  sar     rax, 9
0x1400215bf  mov     [rcx], rax
0x1400215c2  mov     rax, [r14+910h]
0x1400215c9  cqo
0x1400215cb  and     rdx, r8
0x1400215ce  add     rax, rdx
0x1400215d1  sar     rax, 9
0x1400215d5  mov     [rcx+8], rax
0x1400215d9  jmp     loc_140021660
0x1400215de  mov     [rcx+18h], eax
0x1400215e1  mov     dword ptr [rcx+1Ch], 200h
0x1400215e8  mov     rax, [r14+908h]
0x1400215ef  cqo
0x1400215f1  and     rdx, r8
0x1400215f4  add     rax, rdx
0x1400215f7  sar     rax, 9
0x1400215fb  mov     [rcx], rax
0x1400215fe  mov     rax, [r14+910h]
0x140021605  cqo
0x140021607  and     rdx, r8
0x14002160a  add     rax, rdx
0x14002160d  sar     rax, 9
0x140021611  mov     [rcx+10h], rax
0x140021615  mov     [rcx+8], eax
0x140021618  mov     eax, [rcx+14h]
0x14002161b  mov     [rcx+0Ch], eax
0x14002161e  jmp     short loc_140021660
0x140021620  mov     rbx, cs:WPP_GLOBAL_Control
0x140021627  cmp     rbx, r12
0x14002162a  jz      short loc_140021660
0x14002162c  bt      dword ptr [rbx+2Ch], 0Dh
0x140021631  jnb     short loc_140021660
0x140021633  mov     rbx, [rbx+18h]
0x140021637  call    cs:__imp_PsGetCurrentThreadId
0x14002163e  nop     dword ptr [rax+rax+00h]
0x140021643  mov     edx, 6Fh ; 'o'
0x140021648  mov     [rsp+78h+var_50], rbp
0x14002164d  mov     r9, rax
0x140021650  mov     [rsp+78h+var_58], rsi
0x140021655  mov     r8, r13
0x140021658  mov     rcx, rbx
0x14002165b  call    WPP_SF_qqq
0x140021660  mov     rdx, [r14+278h]
0x140021667  test    rdx, rdx
0x14002166a  jz      short loc_1400216A4
0x14002166c  mov     rcx, rsi
0x14002166f  call    UMRxFreeSecondaryBuffer
0x140021674  mov     edi, eax
0x140021676  test    eax, eax
0x140021678  jz      short loc_1400216A4
0x14002167a  mov     rbx, cs:WPP_GLOBAL_Control
0x140021681  cmp     rbx, r12
0x140021684  jz      short loc_1400216F8
0x140021686  bt      dword ptr [rbx+2Ch], 0Dh
0x14002168b  jnb     short loc_1400216F8
0x14002168d  mov     rbx, [rbx+18h]
0x140021691  call    cs:__imp_PsGetCurrentThreadId
0x140021698  nop     dword ptr [rax+rax+00h]
0x14002169d  mov     edx, 70h ; 'p'
0x1400216a2  jmp     short loc_1400216E6
0x1400216a4  mov     rdx, [r14+280h]
0x1400216ab  test    rdx, rdx
0x1400216ae  jz      short loc_1400216F8
0x1400216b0  mov     rcx, rsi
0x1400216b3  call    UMRxFreeSecondaryBuffer
0x1400216b8  mov     edi, eax
0x1400216ba  test    eax, eax
0x1400216bc  jz      short loc_1400216F8
0x1400216be  mov     rbx, cs:WPP_GLOBAL_Control
0x1400216c5  cmp     rbx, r12
0x1400216c8  jz      short loc_1400216F8
0x1400216ca  bt      dword ptr [rbx+2Ch], 0Dh
0x1400216cf  jnb     short loc_1400216F8
0x1400216d1  mov     rbx, [rbx+18h]
0x1400216d5  call    cs:__imp_PsGetCurrentThreadId
0x1400216dc  nop     dword ptr [rax+rax+00h]
0x1400216e1  mov     edx, 71h ; 'q'
0x1400216e6  mov     r9, rax
0x1400216e9  mov     dword ptr [rsp+78h+var_58], edi
0x1400216ed  mov     r8, r13
0x1400216f0  mov     rcx, rbx
0x1400216f3  call    WPP_SF_qD
0x1400216f8  mov     [rsi+80h], edi
0x1400216fe  mov     eax, 1
0x140021703  add     rsp, 38h
0x140021707  pop     r15
0x140021709  pop     r14
0x14002170b  pop     r13
0x14002170d  pop     r12
0x14002170f  pop     rdi
0x140021710  pop     rsi
0x140021711  pop     rbp
0x140021712  pop     rbx
0x140021713  retn
```
