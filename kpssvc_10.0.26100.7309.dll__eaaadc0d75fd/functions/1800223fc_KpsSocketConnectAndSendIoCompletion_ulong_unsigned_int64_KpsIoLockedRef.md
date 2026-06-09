# KpsSocketConnectAndSendIoCompletion(ulong,unsigned __int64,KpsIoLockedRef &)

- ea: `0x1800223fc`
- end: `0x1800225c7`
- name: `?KpsSocketConnectAndSendIoCompletion@@YAXK_KAEAVKpsIoLockedRef@@@Z`
- size: `459`
- prototype: `void __fastcall(unsigned int, __int64, struct _KPS_IO **)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800225d0`

## callees

- `0x18001ae38`
- `0x18001e728`
- `0x18001f5ec`
- `0x180020038`
- `0x1800223fc`
- `0x180026a08`
- `0x180026bc0`
- `0x180026de0`
- `0x18002b03c`

## import_xrefs

- `WS2_32!__imp_closesocket` at `0x180022473`
- `WS2_32!__imp_closesocket` at `0x180022473`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180022499`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x180022499`

## string_xrefs

- `0x1800224e0`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x180022536`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsSocketConnectAndSendIoCompletion(unsigned int a1, __int64 a2, struct _KPS_IO **a3)
{
  unsigned int updated; // edi
  _QWORD *v6; // rcx
  struct _KPS_IO *v7; // rax
  SOCKET v8; // rcx
  struct _TP_IO *v9; // rcx
  __int64 v10; // [rsp+28h] [rbp-20h]

  updated = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_qDI(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, a3, *a3, a1, a2);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = *a3;
  if ( !a1 )
  {
    updated = KpsUpdateDomainRediscovery(*a3);
    if ( updated )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_21;
      WPP_SF_ZDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        updated,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
        206);
    }
    else
    {
      KpsDoSocketRecvDataLength(a3);
    }
LABEL_20:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_21;
  }
  if ( *((_QWORD *)v7 + 26) )
  {
    v8 = *((_QWORD *)v7 + 27);
    if ( v8 != -1 )
    {
      closesocket(v8);
      *((_QWORD *)*a3 + 27) = -1;
    }
    v9 = (struct _TP_IO *)*((_QWORD *)*a3 + 28);
    if ( v9 )
    {
      CloseThreadpoolIo(v9);
      *((_QWORD *)*a3 + 28) = 0;
    }
    *((_QWORD *)*a3 + 26) = *(_QWORD *)(*((_QWORD *)*a3 + 26) + 40LL);
    KpsDoSocketConnectAndSend(a3);
    goto LABEL_20;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
  {
    LODWORD(v10) = 2244;
    WPP_SF_Dsd(
      v6[2],
      121,
      (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
      a1,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
      v10);
    v6 = WPP_GLOBAL_Control;
  }
  updated = a1;
LABEL_21:
  if ( *a3 )
  {
    KpsDoHttpCancelRequest((struct KpsIoLockedRef *)a3);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_D(v6[2], 123, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, updated);
}

```

## disassembly

```asm
0x1800223fc  mov     r11, rsp
0x1800223ff  mov     [r11+8], rbx
0x180022403  mov     [r11+10h], rsi
0x180022407  mov     [r11+18h], rdi
0x18002240b  push    r14
0x18002240d  sub     rsp, 40h
0x180022411  mov     rbx, r8
0x180022414  mov     rax, rdx
0x180022417  mov     esi, ecx
0x180022419  xor     edi, edi
0x18002241b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022422  lea     r14, WPP_GLOBAL_Control
0x180022429  cmp     rcx, r14
0x18002242c  jz      short loc_180022452
0x18002242e  test    byte ptr [rcx+1Ch], 20h
0x180022432  jz      short loc_180022452
0x180022434  mov     r9, [r8]
0x180022437  lea     edx, [rdi+78h]
0x18002243a  mov     rcx, [rcx+10h]
0x18002243e  mov     [r11-20h], rax
0x180022442  mov     dword ptr [rsp+48h+var_28], esi
0x180022446  call    WPP_SF_qDI
0x18002244b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022452  mov     rax, [rbx]
0x180022455  test    esi, esi
0x180022457  jz      loc_180022513
0x18002245d  cmp     [rax+0D0h], rdi
0x180022464  jz      short loc_1800224D1
0x180022466  mov     rcx, [rax+0D8h]; s
0x18002246d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180022471  jz      short loc_18002248A
0x180022473  call    cs:__imp_closesocket
0x18002247a  nop     dword ptr [rax+rax+00h]
0x18002247f  mov     rax, [rbx]
0x180022482  or      qword ptr [rax+0D8h], 0FFFFFFFFFFFFFFFFh
0x18002248a  mov     rax, [rbx]
0x18002248d  mov     rcx, [rax+0E0h]; pio
0x180022494  test    rcx, rcx
0x180022497  jz      short loc_1800224AF
0x180022499  call    cs:__imp_CloseThreadpoolIo
0x1800224a0  nop     dword ptr [rax+rax+00h]
0x1800224a5  mov     rax, [rbx]
0x1800224a8  and     [rax+0E0h], rdi
0x1800224af  mov     rdx, [rbx]
0x1800224b2  mov     rax, [rdx+0D0h]
0x1800224b9  mov     rcx, [rax+28h]
0x1800224bd  mov     [rdx+0D0h], rcx
0x1800224c4  mov     rcx, rbx; struct KpsIoLockedRef *
0x1800224c7  call    ?KpsDoSocketConnectAndSend@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoSocketConnectAndSend(KpsIoLockedRef &)
0x1800224cc  jmp     loc_180022571
0x1800224d1  cmp     rcx, r14
0x1800224d4  jz      short loc_18002250F
0x1800224d6  test    byte ptr [rcx+1Ch], 1
0x1800224da  jz      short loc_18002250F
0x1800224dc  mov     rcx, [rcx+10h]
0x1800224e0  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x1800224e7  mov     edx, 79h ; 'y'
0x1800224ec  mov     dword ptr [rsp+48h+var_20], 8C4h
0x1800224f4  mov     r9d, esi
0x1800224f7  mov     qword ptr [rsp+48h+var_28], rax
0x1800224fc  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180022503  call    WPP_SF_Dsd
0x180022508  mov     rcx, cs:WPP_GLOBAL_Control
0x18002250f  mov     edi, esi
0x180022511  jmp     short loc_180022578
0x180022513  mov     rcx, rax; struct _KPS_IO *
0x180022516  call    ?KpsUpdateDomainRediscovery@@YAKPEAU_KPS_IO@@@Z; KpsUpdateDomainRediscovery(_KPS_IO *)
0x18002251b  mov     edi, eax
0x18002251d  test    eax, eax
0x18002251f  jz      short loc_180022569
0x180022521  mov     rcx, cs:WPP_GLOBAL_Control
0x180022528  cmp     rcx, r14
0x18002252b  jz      short loc_180022578
0x18002252d  test    byte ptr [rcx+1Ch], 1
0x180022531  jz      short loc_180022578
0x180022533  mov     r9, [rbx]
0x180022536  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18002253d  mov     rcx, [rcx+10h]; LoggerHandle
0x180022541  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180022548  mov     dword ptr [rsp+48h+var_18], 8CEh; char
0x180022550  add     r9, 70h ; 'p'
0x180022554  mov     [rsp+48h+var_20], rax; __int64
0x180022559  mov     edx, 7Ah ; 'z'
0x18002255e  mov     dword ptr [rsp+48h+var_28], edi; char
0x180022562  call    WPP_SF_ZDsd
0x180022567  jmp     short loc_180022571
0x180022569  mov     rcx, rbx; this
0x18002256c  call    ?KpsDoSocketRecvDataLength@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoSocketRecvDataLength(KpsIoLockedRef &)
0x180022571  mov     rcx, cs:WPP_GLOBAL_Control
0x180022578  cmp     qword ptr [rbx], 0
0x18002257c  jz      short loc_18002258D
0x18002257e  mov     rcx, rbx; this
0x180022581  call    ?KpsDoHttpCancelRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpCancelRequest(KpsIoLockedRef &)
0x180022586  mov     rcx, cs:WPP_GLOBAL_Control
0x18002258d  cmp     rcx, r14
0x180022590  jz      short loc_1800225B0
0x180022592  test    byte ptr [rcx+1Ch], 20h
0x180022596  jz      short loc_1800225B0
0x180022598  mov     rcx, [rcx+10h]
0x18002259c  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x1800225a3  mov     edx, 7Bh ; '{'
0x1800225a8  mov     r9d, edi
0x1800225ab  call    WPP_SF_D
0x1800225b0  mov     rbx, [rsp+48h+arg_0]
0x1800225b5  mov     rsi, [rsp+48h+arg_8]
0x1800225ba  mov     rdi, [rsp+48h+arg_10]
0x1800225bf  add     rsp, 40h
0x1800225c3  pop     r14
0x1800225c5  retn
```
