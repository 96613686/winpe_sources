# KpsValidateKpasswdMessage(uchar *,ulong)

- ea: `0x18002b4e0`
- end: `0x18002b7c3`
- name: `?KpsValidateKpasswdMessage@@YAKPEAEK@Z`
- size: `739`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002aae8`

## callees

- `0x18001ae0c`
- `0x18001ae38`
- `0x1800268f0`
- `0x180026a08`
- `0x1800288c4`
- `0x180028c08`
- `0x18002b4e0`
- `0x18002c930`

## import_xrefs

- `WS2_32!__imp_ntohs` at `0x18002b54f`
- `WS2_32!__imp_ntohs` at `0x18002b59e`
- `WS2_32!__imp_ntohs` at `0x18002b5e6`
- `WS2_32!__imp_ntohs` at `0x18002b54f`
- `WS2_32!__imp_ntohs` at `0x18002b59e`
- `WS2_32!__imp_ntohs` at `0x18002b5e6`

## string_xrefs

- `0x18002b677`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`
- `0x18002b6f8`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
__int64 __fastcall KpsValidateKpasswdMessage(unsigned __int8 *a1, unsigned int a2, int a3, int a4)
{
  _QWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ebx
  u_short v10; // ax
  int v11; // r8d
  int v12; // r9d
  unsigned __int8 *v13; // rdi
  u_short v14; // ax
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // r14
  unsigned int v18; // eax
  __int64 v19; // rcx
  unsigned int v20; // eax
  __int64 v21; // rcx
  int v23; // [rsp+28h] [rbp-30h]
  int v24; // [rsp+28h] [rbp-30h]
  void *v25; // [rsp+60h] [rbp+8h] BYREF
  void *v26; // [rsp+70h] [rbp+18h] BYREF

  v26 = 0;
  v25 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  if ( !a1 || a2 < 6 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
    {
      WPP_SF_sd(v6[2], 91, a3, a4, 97);
      v6 = WPP_GLOBAL_Control;
    }
    v9 = 11;
    goto LABEL_38;
  }
  if ( ntohs(*(_WORD *)a1) != a2 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_11;
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, v7, v8, 117);
LABEL_10:
    v6 = WPP_GLOBAL_Control;
LABEL_11:
    v9 = 11;
    goto LABEL_43;
  }
  v10 = ntohs(*((_WORD *)a1 + 1));
  if ( v10 != 1 && v10 != 0xFF80 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_11;
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, v11, v12, 134);
    goto LABEL_10;
  }
  v13 = a1 + 6;
  v14 = ntohs(*((_WORD *)a1 + 2));
  v17 = v14;
  if ( v14 > a2 - 6 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_11;
    WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, v15, v16, 151);
    goto LABEL_10;
  }
  v18 = KpsDerUnpack(0x35u, v13, v14, &v26);
  v9 = v18;
  if ( v18 )
  {
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 2) != 0 )
      McTemplateU0zq_EventWriteTransfer(v19, Asn1UnpackFailure, L"KERB_AP_REQUEST_PDU", v18);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_41;
    v23 = 1702;
    WPP_SF_Dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      95,
      (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
      v9,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
      v23);
    goto LABEL_40;
  }
  v20 = KpsDerUnpack(0x39u, &v13[v17], a2 - 6 - v17, &v25);
  v9 = v20;
  if ( v20 )
  {
    if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 2) != 0 )
      McTemplateU0zq_EventWriteTransfer(v21, Asn1UnpackFailure, L"KERB_PRIV_MESSAGE_PDU", v20);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_38;
    v24 = 1719;
    WPP_SF_Dsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      96,
      (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
      v9,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
      v24);
  }
  v6 = WPP_GLOBAL_Control;
LABEL_38:
  if ( !v25 )
    goto LABEL_41;
  KpsDerFree(0x39u, v25);
LABEL_40:
  v6 = WPP_GLOBAL_Control;
LABEL_41:
  if ( v26 )
  {
    KpsDerFree(0x35u, v26);
    v6 = WPP_GLOBAL_Control;
  }
LABEL_43:
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_D(v6[2], 97, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18002b4e0  mov     [rsp+arg_8], rbx
0x18002b4e5  push    rbp
0x18002b4e6  push    rsi
0x18002b4e7  push    rdi
0x18002b4e8  push    r14
0x18002b4ea  push    r15
0x18002b4ec  sub     rsp, 30h
0x18002b4f0  and     [rsp+58h+arg_10], 0
0x18002b4f6  mov     esi, edx
0x18002b4f8  and     [rsp+58h+arg_0], 0
0x18002b4fe  mov     rbx, rcx
0x18002b501  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b508  lea     r15, WPP_GLOBAL_Control
0x18002b50f  cmp     rcx, r15
0x18002b512  jz      short loc_18002B536
0x18002b514  test    byte ptr [rcx+1Ch], 20h
0x18002b518  jz      short loc_18002B536
0x18002b51a  mov     rcx, [rcx+10h]
0x18002b51e  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002b525  mov     edx, 5Ah ; 'Z'
0x18002b52a  call    WPP_SF_
0x18002b52f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b536  test    rbx, rbx
0x18002b539  jz      loc_18002B729
0x18002b53f  cmp     esi, 6
0x18002b542  jb      loc_18002B729
0x18002b548  movzx   ecx, word ptr [rbx]; netshort
0x18002b54b  lea     rdi, [rbx+2]
0x18002b54f  call    cs:__imp_ntohs
0x18002b556  nop     dword ptr [rax+rax+00h]
0x18002b55b  movzx   eax, ax
0x18002b55e  cmp     eax, esi
0x18002b560  jz      short loc_18002B59B
0x18002b562  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b569  cmp     rcx, r15
0x18002b56c  jz      short loc_18002B591
0x18002b56e  test    byte ptr [rcx+1Ch], 1
0x18002b572  jz      short loc_18002B591
0x18002b574  mov     edx, 5Ch ; '\'
0x18002b579  mov     dword ptr [rsp+58h+var_38], 675h
0x18002b581  mov     rcx, [rcx+10h]
0x18002b585  call    WPP_SF_sd
0x18002b58a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b591  mov     ebx, 0Bh
0x18002b596  jmp     loc_18002B78C
0x18002b59b  movzx   ecx, word ptr [rdi]; netshort
0x18002b59e  call    cs:__imp_ntohs
0x18002b5a5  nop     dword ptr [rax+rax+00h]
0x18002b5aa  cmp     ax, 1
0x18002b5ae  jz      short loc_18002B5DB
0x18002b5b0  mov     ecx, 0FF80h
0x18002b5b5  cmp     ax, cx
0x18002b5b8  jz      short loc_18002B5DB
0x18002b5ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5c1  cmp     rcx, r15
0x18002b5c4  jz      short loc_18002B591
0x18002b5c6  test    byte ptr [rcx+1Ch], 1
0x18002b5ca  jz      short loc_18002B591
0x18002b5cc  mov     edx, 5Dh ; ']'
0x18002b5d1  mov     dword ptr [rsp+58h+var_38], 686h
0x18002b5d9  jmp     short loc_18002B581
0x18002b5db  movzx   ecx, word ptr [rdi+2]; netshort
0x18002b5df  lea     ebp, [rsi-6]
0x18002b5e2  add     rdi, 4
0x18002b5e6  call    cs:__imp_ntohs
0x18002b5ed  nop     dword ptr [rax+rax+00h]
0x18002b5f2  movzx   r14d, ax
0x18002b5f6  cmp     r14d, ebp
0x18002b5f9  jbe     short loc_18002B61F
0x18002b5fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b602  cmp     rcx, r15
0x18002b605  jz      short loc_18002B591
0x18002b607  test    byte ptr [rcx+1Ch], 1
0x18002b60b  jz      short loc_18002B591
0x18002b60d  mov     edx, 5Eh ; '^'
0x18002b612  mov     dword ptr [rsp+58h+var_38], 697h
0x18002b61a  jmp     loc_18002B581
0x18002b61f  lea     r9, [rsp+58h+arg_10]; void **
0x18002b624  mov     r8d, r14d; unsigned int
0x18002b627  mov     rdx, rdi; void *
0x18002b62a  mov     ecx, 35h ; '5'; unsigned int
0x18002b62f  call    ?KpsDerUnpack@@YAKKPEAXKPEAPEAX@Z; KpsDerUnpack(ulong,void *,ulong,void * *)
0x18002b634  mov     ebx, eax
0x18002b636  test    eax, eax
0x18002b638  jz      short loc_18002B6A4
0x18002b63a  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 2
0x18002b641  jz      short loc_18002B659
0x18002b643  mov     r9d, eax
0x18002b646  lea     r8, aKerbApRequestP; "KERB_AP_REQUEST_PDU"
0x18002b64d  lea     rdx, Asn1UnpackFailure
0x18002b654  call    McTemplateU0zq_EventWriteTransfer
0x18002b659  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b660  cmp     rcx, r15
0x18002b663  jz      loc_18002B771
0x18002b669  test    byte ptr [rcx+1Ch], 1
0x18002b66d  jz      loc_18002B771
0x18002b673  mov     rcx, [rcx+10h]
0x18002b677  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002b67e  mov     edx, 5Fh ; '_'
0x18002b683  mov     [rsp+58h+var_30], 6A6h
0x18002b68b  mov     r9d, ebx
0x18002b68e  mov     [rsp+58h+var_38], rax
0x18002b693  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002b69a  call    WPP_SF_Dsd
0x18002b69f  jmp     loc_18002B76A
0x18002b6a4  sub     ebp, r14d
0x18002b6a7  lea     rdx, [rdi+r14]; void *
0x18002b6ab  mov     r8d, ebp; unsigned int
0x18002b6ae  lea     r9, [rsp+58h+arg_0]; void **
0x18002b6b3  mov     ecx, 39h ; '9'; unsigned int
0x18002b6b8  call    ?KpsDerUnpack@@YAKKPEAXKPEAPEAX@Z; KpsDerUnpack(ulong,void *,ulong,void * *)
0x18002b6bd  mov     ebx, eax
0x18002b6bf  test    eax, eax
0x18002b6c1  jz      short loc_18002B720
0x18002b6c3  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 2
0x18002b6ca  jz      short loc_18002B6E2
0x18002b6cc  mov     r9d, eax
0x18002b6cf  lea     r8, aKerbPrivMessag; "KERB_PRIV_MESSAGE_PDU"
0x18002b6d6  lea     rdx, Asn1UnpackFailure
0x18002b6dd  call    McTemplateU0zq_EventWriteTransfer
0x18002b6e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b6e9  cmp     rcx, r15
0x18002b6ec  jz      short loc_18002B756
0x18002b6ee  test    byte ptr [rcx+1Ch], 1
0x18002b6f2  jz      short loc_18002B756
0x18002b6f4  mov     rcx, [rcx+10h]
0x18002b6f8  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x18002b6ff  mov     edx, 60h ; '`'
0x18002b704  mov     [rsp+58h+var_30], 6B7h
0x18002b70c  mov     r9d, ebx
0x18002b70f  mov     [rsp+58h+var_38], rax
0x18002b714  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002b71b  call    WPP_SF_Dsd
0x18002b720  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b727  jmp     short loc_18002B756
0x18002b729  cmp     rcx, r15
0x18002b72c  jz      short loc_18002B751
0x18002b72e  test    byte ptr [rcx+1Ch], 1
0x18002b732  jz      short loc_18002B751
0x18002b734  mov     rcx, [rcx+10h]
0x18002b738  mov     edx, 5Bh ; '['
0x18002b73d  mov     dword ptr [rsp+58h+var_38], 661h
0x18002b745  call    WPP_SF_sd
0x18002b74a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b751  mov     ebx, 0Bh
0x18002b756  mov     rdx, [rsp+58h+arg_0]; void *
0x18002b75b  test    rdx, rdx
0x18002b75e  jz      short loc_18002B771
0x18002b760  mov     ecx, 39h ; '9'; unsigned int
0x18002b765  call    ?KpsDerFree@@YAXKPEAX@Z; KpsDerFree(ulong,void *)
0x18002b76a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b771  mov     rdx, [rsp+58h+arg_10]; void *
0x18002b776  test    rdx, rdx
0x18002b779  jz      short loc_18002B78C
0x18002b77b  mov     ecx, 35h ; '5'; unsigned int
0x18002b780  call    ?KpsDerFree@@YAXKPEAX@Z; KpsDerFree(ulong,void *)
0x18002b785  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b78c  cmp     rcx, r15
0x18002b78f  jz      short loc_18002B7AF
0x18002b791  test    byte ptr [rcx+1Ch], 20h
0x18002b795  jz      short loc_18002B7AF
0x18002b797  mov     rcx, [rcx+10h]
0x18002b79b  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x18002b7a2  mov     edx, 61h ; 'a'
0x18002b7a7  mov     r9d, ebx
0x18002b7aa  call    WPP_SF_D
0x18002b7af  mov     eax, ebx
0x18002b7b1  mov     rbx, [rsp+58h+arg_8]
0x18002b7b6  add     rsp, 30h
0x18002b7ba  pop     r15
0x18002b7bc  pop     r14
0x18002b7be  pop     rdi
0x18002b7bf  pop     rsi
0x18002b7c0  pop     rbp
0x18002b7c1  retn
```
