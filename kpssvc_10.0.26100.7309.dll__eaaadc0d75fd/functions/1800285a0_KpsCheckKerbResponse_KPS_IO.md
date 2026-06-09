# KpsCheckKerbResponse(_KPS_IO *)

- ea: `0x1800285a0`
- end: `0x1800287f8`
- name: `?KpsCheckKerbResponse@@YAKPEAU_KPS_IO@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(struct _KPS_IO *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002a42c`

## callees

- `0x18001ae38`
- `0x1800268f0`
- `0x180026a08`
- `0x180026d9c`
- `0x1800279f8`
- `0x180028030`
- `0x1800285a0`
- `0x1800288c4`
- `0x180028c08`
- `0x18002bb28`

## import_xrefs

- `WS2_32!__imp_ntohl` at `0x18002861b`
- `WS2_32!__imp_ntohl` at `0x18002861b`

## string_xrefs

- `0x1800286e4`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`
- `0x180028775`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
__int64 __fastcall KpsCheckKerbResponse(struct _KPS_IO *a1)
{
  unsigned int v1; // ebx
  unsigned int v2; // r14d
  void *v3; // rsi
  _BYTE *v5; // rcx
  u_long *v6; // rax
  u_long v7; // eax
  __int64 v8; // r9
  _BYTE *v9; // rdx
  int v10; // ebp
  unsigned int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // eax
  void *v15; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  v2 = 0;
  v3 = 0;
  v15 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, a1);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = (u_long *)*((_QWORD *)a1 + 32);
  if ( !v6 || *((_DWORD *)a1 + 66) < 5u )
  {
    v1 = 11;
    if ( v5 == (_BYTE *)&WPP_GLOBAL_Control )
      return v1;
    if ( (v5[28] & 1) == 0 )
      goto LABEL_32;
    WPP_SF_Dsd(
      *((_QWORD *)v5 + 2),
      128,
      (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
      11,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
      2248);
    goto LABEL_28;
  }
  v7 = ntohl(*v6);
  v8 = *((unsigned int *)a1 + 66);
  if ( v7 + 4LL == v8 )
  {
    v9 = (_BYTE *)(*((_QWORD *)a1 + 32) + 4LL);
    if ( *v9 == 126 )
    {
      v10 = 1;
      v2 = 6;
      v11 = KpsDerUnpack(6u, v9, v7, &v15);
      v1 = v11;
      if ( v11 )
      {
        if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 2) != 0 )
          McTemplateU0zq_EventWriteTransfer(v12, Asn1UnpackFailure, L"KERB_ERROR_PDU", v11);
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          v3 = v15;
          goto LABEL_29;
        }
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          130,
          (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
          v1,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
          2303);
        v3 = v15;
LABEL_28:
        v5 = WPP_GLOBAL_Control;
LABEL_29:
        if ( v3 )
        {
          KpsDerFree(v2, v3);
          goto LABEL_31;
        }
        goto LABEL_32;
      }
      v3 = v15;
    }
    else
    {
      if ( *v9 != 107 )
        goto LABEL_31;
      v10 = 2;
    }
    *((_DWORD *)a1 + 61) = v10;
    *((_QWORD *)a1 + 31) = v3;
    if ( v10 == 1 )
      v13 = KpsCheckKerbError(a1);
    else
      v13 = KpsCheckAsRep(a1);
    v1 = v13;
    goto LABEL_31;
  }
  v1 = 11;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_DDDsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, v7, v8, v7, v8);
LABEL_31:
    v5 = WPP_GLOBAL_Control;
  }
LABEL_32:
  if ( v5 != (_BYTE *)&WPP_GLOBAL_Control && (v5[28] & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)v5 + 2), 131, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x1800285a0  mov     rax, rsp
0x1800285a3  mov     [rax+10h], rbx
0x1800285a7  mov     [rax+18h], rbp
0x1800285ab  mov     [rax+20h], rsi
0x1800285af  push    rdi
0x1800285b0  push    r14
0x1800285b2  push    r15
0x1800285b4  sub     rsp, 40h
0x1800285b8  xor     ebx, ebx
0x1800285ba  xor     r14d, r14d
0x1800285bd  xor     esi, esi
0x1800285bf  mov     rdi, rcx
0x1800285c2  mov     [rax+8], rsi
0x1800285c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285cd  lea     r15, WPP_GLOBAL_Control
0x1800285d4  cmp     rcx, r15
0x1800285d7  jz      short loc_1800285FC
0x1800285d9  test    byte ptr [rcx+1Ch], 20h
0x1800285dd  jz      short loc_1800285FC
0x1800285df  mov     rcx, [rcx+10h]
0x1800285e3  lea     edx, [rbx+7Fh]
0x1800285e6  mov     r9, rdi
0x1800285e9  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x1800285f0  call    WPP_SF_q
0x1800285f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800285fc  mov     rax, [rdi+100h]
0x180028603  test    rax, rax
0x180028606  jz      loc_180028761
0x18002860c  cmp     dword ptr [rdi+108h], 5
0x180028613  jb      loc_180028761
0x180028619  mov     ecx, [rax]; netlong
0x18002861b  call    cs:__imp_ntohl
0x180028622  nop     dword ptr [rax+rax+00h]
0x180028627  mov     r9d, [rdi+108h]
0x18002862e  mov     r8d, eax; unsigned int
0x180028631  mov     eax, eax
0x180028633  add     rax, 4
0x180028637  cmp     rax, r9
0x18002863a  jz      short loc_18002867E
0x18002863c  mov     ebx, 0Bh
0x180028641  mov     rcx, cs:WPP_GLOBAL_Control
0x180028648  cmp     rcx, r15
0x18002864b  jz      loc_1800287DC
0x180028651  test    byte ptr [rcx+1Ch], 1
0x180028655  jz      loc_1800287B9
0x18002865b  mov     rcx, [rcx+10h]
0x18002865f  lea     edx, [rbx+76h]
0x180028662  mov     [rsp+58h+var_20], 8D7h
0x18002866a  mov     [rsp+58h+var_30], r9d
0x18002866f  mov     dword ptr [rsp+58h+var_38], r8d
0x180028674  call    WPP_SF_DDDsd
0x180028679  jmp     loc_1800287B2
0x18002867e  mov     rdx, [rdi+100h]
0x180028685  add     rdx, 4; void *
0x180028689  mov     al, [rdx]
0x18002868b  cmp     al, 7Eh ; '~'
0x18002868d  jnz     loc_180028727
0x180028693  mov     ebp, 1
0x180028698  lea     r9, [rsp+58h+arg_0]; void **
0x18002869d  lea     r14d, [rbp+5]
0x1800286a1  mov     ecx, r14d; unsigned int
0x1800286a4  call    ?KpsDerUnpack@@YAKKPEAXKPEAPEAX@Z; KpsDerUnpack(ulong,void *,ulong,void * *)
0x1800286a9  mov     ebx, eax
0x1800286ab  test    eax, eax
0x1800286ad  jz      short loc_180028720
0x1800286af  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 2
0x1800286b6  jz      short loc_1800286CE
0x1800286b8  mov     r9d, eax
0x1800286bb  lea     r8, aKerbErrorPdu; "KERB_ERROR_PDU"
0x1800286c2  lea     rdx, Asn1UnpackFailure
0x1800286c9  call    McTemplateU0zq_EventWriteTransfer
0x1800286ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286d5  cmp     rcx, r15
0x1800286d8  jz      short loc_180028716
0x1800286da  test    [rcx+1Ch], bpl
0x1800286de  jz      short loc_180028716
0x1800286e0  mov     rcx, [rcx+10h]
0x1800286e4  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x1800286eb  mov     edx, 82h
0x1800286f0  mov     [rsp+58h+var_30], 8FFh
0x1800286f8  mov     r9d, ebx
0x1800286fb  mov     [rsp+58h+var_38], rax
0x180028700  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180028707  call    WPP_SF_Dsd
0x18002870c  mov     rsi, [rsp+58h+arg_0]
0x180028711  jmp     loc_18002879B
0x180028716  mov     rsi, [rsp+58h+arg_0]
0x18002871b  jmp     loc_1800287A2
0x180028720  mov     rsi, [rsp+58h+arg_0]
0x180028725  jmp     short loc_180028734
0x180028727  cmp     al, 6Bh ; 'k'
0x180028729  jnz     loc_1800287B2
0x18002872f  mov     ebp, 2
0x180028734  mov     [rdi+0F4h], ebp
0x18002873a  mov     [rdi+0F8h], rsi
0x180028741  cmp     ebp, 1
0x180028744  jnz     short loc_180028752
0x180028746  mov     rcx, rdi; struct _KPS_IO *
0x180028749  call    ?KpsCheckKerbError@@YAKPEAU_KPS_IO@@@Z; KpsCheckKerbError(_KPS_IO *)
0x18002874e  mov     ebx, eax
0x180028750  jmp     short loc_1800287B2
0x180028752  cmp     ebp, 2
0x180028755  jnz     short loc_1800287B2
0x180028757  mov     rcx, rdi; struct _KPS_IO *
0x18002875a  call    ?KpsCheckAsRep@@YAKPEAU_KPS_IO@@@Z; KpsCheckAsRep(_KPS_IO *)
0x18002875f  jmp     short loc_18002874E
0x180028761  mov     ebx, 0Bh
0x180028766  cmp     rcx, r15
0x180028769  jz      short loc_1800287DC
0x18002876b  test    byte ptr [rcx+1Ch], 1
0x18002876f  jz      short loc_1800287B9
0x180028771  mov     rcx, [rcx+10h]
0x180028775  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002877c  lea     edx, [rbx+75h]
0x18002877f  mov     [rsp+58h+var_30], 8C8h
0x180028787  mov     r9d, ebx
0x18002878a  mov     [rsp+58h+var_38], rax
0x18002878f  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180028796  call    WPP_SF_Dsd
0x18002879b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287a2  test    rsi, rsi
0x1800287a5  jz      short loc_1800287B9
0x1800287a7  mov     rdx, rsi; void *
0x1800287aa  mov     ecx, r14d; unsigned int
0x1800287ad  call    ?KpsDerFree@@YAXKPEAX@Z; KpsDerFree(ulong,void *)
0x1800287b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287b9  cmp     rcx, r15
0x1800287bc  jz      short loc_1800287DC
0x1800287be  test    byte ptr [rcx+1Ch], 20h
0x1800287c2  jz      short loc_1800287DC
0x1800287c4  mov     rcx, [rcx+10h]
0x1800287c8  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x1800287cf  mov     edx, 83h
0x1800287d4  mov     r9d, ebx
0x1800287d7  call    WPP_SF_D
0x1800287dc  mov     rbp, [rsp+58h+arg_10]
0x1800287e1  mov     eax, ebx
0x1800287e3  mov     rbx, [rsp+58h+arg_8]
0x1800287e8  mov     rsi, [rsp+58h+arg_18]
0x1800287ed  add     rsp, 40h
0x1800287f1  pop     r15
0x1800287f3  pop     r14
0x1800287f5  pop     rdi
0x1800287f6  retn
```
