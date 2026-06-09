# KpsProcessProxyRequest(KpsIoLockedRef &)

- ea: `0x1800222f0`
- end: `0x1800223f4`
- name: `?KpsProcessProxyRequest@@YAXAEAVKpsIoLockedRef@@@Z`
- size: `260`
- prototype: `void __fastcall(struct _KPS_IO **)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180020d0c`

## callees

- `0x18001ae38`
- `0x18001e728`
- `0x18001f390`
- `0x1800202d0`
- `0x1800222f0`
- `0x180026a08`
- `0x180026d9c`
- `0x18002aae8`
- `0x18002fe08`

## string_xrefs

- `0x180022372`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsProcessProxyRequest(struct _KPS_IO **a1)
{
  unsigned int v2; // edi
  unsigned __int16 v3; // dx
  char *v4; // r8
  char *v5; // r9
  _QWORD *v6; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, *a1);
  v2 = KpsUnpackProxyRequest(*a1);
  if ( v2 == 1935 )
  {
    KpsPerfUpdate(4u);
    KpsDoHttpSendResponse((struct KpsIoLockedRef *)a1, v3, v4, v5);
LABEL_11:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_12;
  }
  if ( !v2 )
  {
    KpsForwardKerbRequest((struct KpsIoLockedRef *)a1);
    goto LABEL_11;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      141,
      (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
      v2,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
      10);
    goto LABEL_11;
  }
LABEL_12:
  if ( *a1 )
  {
    KpsDoHttpCancelRequest((struct KpsIoLockedRef *)a1);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_D(v6[2], 142, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, v2);
}

```

## disassembly

```asm
0x1800222f0  mov     [rsp+arg_0], rbx
0x1800222f5  mov     [rsp+arg_8], rsi
0x1800222fa  push    rdi
0x1800222fb  sub     rsp, 30h
0x1800222ff  mov     rbx, rcx
0x180022302  mov     rcx, cs:WPP_GLOBAL_Control
0x180022309  lea     rsi, WPP_GLOBAL_Control
0x180022310  cmp     rcx, rsi
0x180022313  jz      short loc_180022333
0x180022315  test    byte ptr [rcx+1Ch], 20h
0x180022319  jz      short loc_180022333
0x18002231b  mov     r9, [rbx]
0x18002231e  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180022325  mov     rcx, [rcx+10h]
0x180022329  mov     edx, 8Ch
0x18002232e  call    WPP_SF_q
0x180022333  mov     rcx, [rbx]; struct _KPS_IO *
0x180022336  call    ?KpsUnpackProxyRequest@@YAKPEAU_KPS_IO@@@Z; KpsUnpackProxyRequest(_KPS_IO *)
0x18002233b  mov     edi, eax
0x18002233d  cmp     eax, 78Fh
0x180022342  jnz     short loc_180022358
0x180022344  mov     ecx, 4; unsigned int
0x180022349  call    ?KpsPerfUpdate@@YAXK@Z; KpsPerfUpdate(ulong)
0x18002234e  mov     rcx, rbx; this
0x180022351  call    ?KpsDoHttpSendResponse@@YAXAEAVKpsIoLockedRef@@GPEAD1@Z; KpsDoHttpSendResponse(KpsIoLockedRef &,ushort,char *,char *)
0x180022356  jmp     short loc_1800223A4
0x180022358  test    edi, edi
0x18002235a  jz      short loc_18002239C
0x18002235c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022363  cmp     rcx, rsi
0x180022366  jz      short loc_1800223AB
0x180022368  test    byte ptr [rcx+1Ch], 1
0x18002236c  jz      short loc_1800223AB
0x18002236e  mov     rcx, [rcx+10h]
0x180022372  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x180022379  mov     edx, 8Dh
0x18002237e  mov     [rsp+38h+var_10], 0A0Ah
0x180022386  mov     r9d, edi
0x180022389  mov     [rsp+38h+var_18], rax
0x18002238e  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x180022395  call    WPP_SF_Dsd
0x18002239a  jmp     short loc_1800223A4
0x18002239c  mov     rcx, rbx; struct KpsIoLockedRef *
0x18002239f  call    ?KpsForwardKerbRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsForwardKerbRequest(KpsIoLockedRef &)
0x1800223a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223ab  cmp     qword ptr [rbx], 0
0x1800223af  jz      short loc_1800223C0
0x1800223b1  mov     rcx, rbx; this
0x1800223b4  call    ?KpsDoHttpCancelRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpCancelRequest(KpsIoLockedRef &)
0x1800223b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800223c0  cmp     rcx, rsi
0x1800223c3  jz      short loc_1800223E3
0x1800223c5  test    byte ptr [rcx+1Ch], 20h
0x1800223c9  jz      short loc_1800223E3
0x1800223cb  mov     rcx, [rcx+10h]
0x1800223cf  lea     r8, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x1800223d6  mov     edx, 8Eh
0x1800223db  mov     r9d, edi
0x1800223de  call    WPP_SF_D
0x1800223e3  mov     rbx, [rsp+38h+arg_0]
0x1800223e8  mov     rsi, [rsp+38h+arg_8]
0x1800223ed  add     rsp, 30h
0x1800223f1  pop     rdi
0x1800223f2  retn
```
