# KpsCheckAsReq(_KPS_IO *)

- ea: `0x180027af8`
- end: `0x180027dda`
- name: `?KpsCheckAsReq@@YAKPEAU_KPS_IO@@@Z`
- size: `738`
- prototype: `__int64 __fastcall(struct _KPS_IO *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800284ec`

## callees

- `0x180019d2c`
- `0x18001ae38`
- `0x180026a08`
- `0x180026d9c`
- `0x180027af8`
- `0x180027de0`
- `0x18002a5a8`
- `0x18002b24c`
- `0x18002b894`
- `0x18002be28`
- `0x18002fe08`
- `0x18003012c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180027c51`
- `ntdll!RtlInitUnicodeString` at `0x180027cf9`
- `ntdll!RtlInitUnicodeString` at `0x180027c51`
- `ntdll!RtlInitUnicodeString` at `0x180027cf9`

## string_xrefs

- `0x180027be1`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`
- `0x180027cb8`: `ds\security\protocols\kerberos\kps\kpskerb.cxx`

## pseudocode

```c
__int64 __fastcall KpsCheckAsReq(struct _KPS_IO *a1)
{
  void *v1; // rdi
  const WCHAR *v3; // rsi
  WCHAR *v4; // r14
  __int64 v5; // r15
  __int64 *i; // rcx
  int v7; // eax
  unsigned int v8; // esi
  _WORD *v9; // r12
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  void *lpMem; // [rsp+60h] [rbp+8h] BYREF
  PCWSTR SourceString; // [rsp+68h] [rbp+10h] BYREF

  v1 = 0;
  v3 = 0;
  lpMem = 0;
  v4 = 0;
  SourceString = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, a1);
  v5 = *((_QWORD *)a1 + 17);
  *((_DWORD *)a1 + 36) = 0;
  if ( *(char *)v5 < 0 )
  {
    for ( i = *(__int64 **)(v5 + 16); i; i = (__int64 *)*i )
    {
      v7 = *((_DWORD *)i + 2);
      if ( v7 == 136 )
      {
        *((_DWORD *)a1 + 37) |= 1u;
        KpsPerfUpdate(2u);
        goto LABEL_12;
      }
      if ( v7 == 2 )
      {
        *((_DWORD *)a1 + 36) = 2;
        goto LABEL_12;
      }
      if ( (unsigned int)(v7 - 15) <= 1 )
      {
        *((_DWORD *)a1 + 36) = 3;
        goto LABEL_12;
      }
    }
  }
  *((_DWORD *)a1 + 36) = 1;
LABEL_12:
  if ( *(char *)(v5 + 24) < 0 )
  {
    v8 = KpsPrincipalName2UnicodeString((struct KERB_PRINCIPAL_NAME *)(v5 + 48), (unsigned __int16 **)&lpMem);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          104,
          (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
          v8,
          (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
          1900);
      v1 = lpMem;
      goto LABEL_39;
    }
    v3 = (const WCHAR *)lpMem;
  }
  v9 = (_WORD *)((char *)a1 + 152);
  RtlInitUnicodeString((PUNICODE_STRING)((char *)a1 + 152), v3);
  v10 = *((_QWORD *)a1 + 20);
  if ( v10 && *v9 > 2u && *(_WORD *)(v10 + 2 * ((unsigned __int64)(unsigned __int16)*v9 >> 1) - 2) == 36 )
    *((_DWORD *)a1 + 37) |= 2u;
  v8 = KpsUtf8String2UnicodeString(*(LPCCH *)(v5 + 64), (unsigned __int16 **)&SourceString);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        105,
        (unsigned int)&WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids,
        v8,
        (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpskerb.cxx",
        1924);
    v4 = (WCHAR *)SourceString;
  }
  else
  {
    RtlInitUnicodeString((PUNICODE_STRING)((char *)a1 + 168), SourceString);
    if ( *((_DWORD *)a1 + 36) == 2 )
    {
      if ( KpsGPCheckDisallowUnprotectedPasswordAuth((*((_DWORD *)a1 + 37) & 2) != 0) )
      {
        v8 = KpsCheckAsReqForBadPassword(a1);
      }
      else
      {
        v8 = 1935;
        if ( (Microsoft_Windows_Kerberos_KdcProxyEnableBits & 0x10) != 0 )
          McTemplateU0zz_EventWriteTransfer(v12, v11, *((_QWORD *)a1 + 22), *((_QWORD *)a1 + 20));
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_ZZD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v9);
      }
    }
  }
LABEL_39:
  KpsFreeMem(v4);
  KpsFreeMem(v1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180027af8  mov     rax, rsp
0x180027afb  mov     [rax+18h], rbx
0x180027aff  mov     [rax+20h], rsi
0x180027b03  push    rdi
0x180027b04  push    r12
0x180027b06  push    r13
0x180027b08  push    r14
0x180027b0a  push    r15
0x180027b0c  sub     rsp, 30h
0x180027b10  xor     edi, edi
0x180027b12  mov     rbx, rcx
0x180027b15  mov     esi, edi
0x180027b17  mov     [rax+8], rdi
0x180027b1b  mov     r14d, edi
0x180027b1e  mov     [rax+10h], rdi
0x180027b22  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b29  lea     rax, WPP_GLOBAL_Control
0x180027b30  cmp     rcx, rax
0x180027b33  jz      short loc_180027B51
0x180027b35  test    byte ptr [rcx+1Ch], 20h
0x180027b39  jz      short loc_180027B51
0x180027b3b  mov     rcx, [rcx+10h]
0x180027b3f  lea     edx, [rdi+67h]
0x180027b42  mov     r9, rbx
0x180027b45  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180027b4c  call    WPP_SF_q
0x180027b51  mov     r15, [rbx+88h]
0x180027b58  mov     r13d, 2
0x180027b5e  mov     [rbx+90h], edi
0x180027b64  test    byte ptr [r15], 80h
0x180027b68  jz      short loc_180027B9B
0x180027b6a  mov     rcx, [r15+10h]
0x180027b6e  jmp     short loc_180027B96
0x180027b70  mov     eax, [rcx+8]
0x180027b73  cmp     eax, 88h
0x180027b78  jz      loc_180027C2B
0x180027b7e  cmp     eax, r13d
0x180027b81  jz      loc_180027C1F
0x180027b87  add     eax, 0FFFFFFF1h
0x180027b8a  cmp     eax, 1
0x180027b8d  jbe     loc_180027C13
0x180027b93  mov     rcx, [rcx]
0x180027b96  test    rcx, rcx
0x180027b99  jnz     short loc_180027B70
0x180027b9b  mov     dword ptr [rbx+90h], 1
0x180027ba5  test    byte ptr [r15+18h], 80h
0x180027baa  jz      loc_180027C44
0x180027bb0  lea     rcx, [r15+30h]; struct KERB_PRINCIPAL_NAME *
0x180027bb4  lea     rdx, [rsp+58h+lpMem]; unsigned __int16 **
0x180027bb9  call    ?KpsPrincipalName2UnicodeString@@YAKPEAUKERB_PRINCIPAL_NAME@@PEAPEAG@Z; KpsPrincipalName2UnicodeString(KERB_PRINCIPAL_NAME *,ushort * *)
0x180027bbe  mov     esi, eax
0x180027bc0  test    eax, eax
0x180027bc2  jz      short loc_180027C3F
0x180027bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180027bcb  lea     rbx, WPP_GLOBAL_Control
0x180027bd2  cmp     rcx, rbx
0x180027bd5  jz      short loc_180027C09
0x180027bd7  test    byte ptr [rcx+1Ch], 1
0x180027bdb  jz      short loc_180027C09
0x180027bdd  mov     rcx, [rcx+10h]
0x180027be1  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x180027be8  mov     edx, 68h ; 'h'
0x180027bed  mov     [rsp+58h+var_30], 76Ch
0x180027bf5  mov     r9d, esi
0x180027bf8  mov     [rsp+58h+var_38], rax
0x180027bfd  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180027c04  call    WPP_SF_Dsd
0x180027c09  mov     rdi, [rsp+58h+lpMem]
0x180027c0e  jmp     loc_180027D85
0x180027c13  mov     dword ptr [rbx+90h], 3
0x180027c1d  jmp     short loc_180027BA5
0x180027c1f  mov     [rbx+90h], r13d
0x180027c26  jmp     loc_180027BA5
0x180027c2b  or      dword ptr [rbx+94h], 1
0x180027c32  mov     ecx, r13d; unsigned int
0x180027c35  call    ?KpsPerfUpdate@@YAXK@Z; KpsPerfUpdate(ulong)
0x180027c3a  jmp     loc_180027BA5
0x180027c3f  mov     rsi, [rsp+58h+lpMem]
0x180027c44  lea     r12, [rbx+98h]
0x180027c4b  mov     rdx, rsi; SourceString
0x180027c4e  mov     rcx, r12; DestinationString
0x180027c51  call    cs:__imp_RtlInitUnicodeString
0x180027c58  nop     dword ptr [rax+rax+00h]
0x180027c5d  mov     rcx, [rbx+0A0h]
0x180027c64  test    rcx, rcx
0x180027c67  jz      short loc_180027C87
0x180027c69  cmp     [r12], r13w
0x180027c6e  jbe     short loc_180027C87
0x180027c70  movzx   eax, word ptr [r12]
0x180027c75  shr     rax, 1
0x180027c78  cmp     word ptr [rcx+rax*2-2], 24h ; '$'
0x180027c7e  jnz     short loc_180027C87
0x180027c80  or      [rbx+94h], r13d
0x180027c87  mov     rcx, [r15+40h]; lpMultiByteStr
0x180027c8b  lea     rdx, [rsp+58h+SourceString]; unsigned __int16 **
0x180027c90  call    ?KpsUtf8String2UnicodeString@@YAKPEADPEAPEAG@Z; KpsUtf8String2UnicodeString(char *,ushort * *)
0x180027c95  mov     esi, eax
0x180027c97  test    eax, eax
0x180027c99  jz      short loc_180027CEA
0x180027c9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ca2  lea     rbx, WPP_GLOBAL_Control
0x180027ca9  cmp     rcx, rbx
0x180027cac  jz      short loc_180027CE0
0x180027cae  test    byte ptr [rcx+1Ch], 1
0x180027cb2  jz      short loc_180027CE0
0x180027cb4  mov     rcx, [rcx+10h]
0x180027cb8  lea     rax, aDsSecurityProt; "ds\\security\\protocols\\kerberos\\kps"...
0x180027cbf  mov     edx, 69h ; 'i'
0x180027cc4  mov     [rsp+58h+var_30], 784h
0x180027ccc  mov     r9d, esi
0x180027ccf  mov     [rsp+58h+var_38], rax
0x180027cd4  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180027cdb  call    WPP_SF_Dsd
0x180027ce0  mov     r14, [rsp+58h+SourceString]
0x180027ce5  jmp     loc_180027D85
0x180027cea  mov     rdx, [rsp+58h+SourceString]; SourceString
0x180027cef  lea     r15, [rbx+0A8h]
0x180027cf6  mov     rcx, r15; DestinationString
0x180027cf9  call    cs:__imp_RtlInitUnicodeString
0x180027d00  nop     dword ptr [rax+rax+00h]
0x180027d05  cmp     [rbx+90h], r13d
0x180027d0c  jnz     short loc_180027D7E
0x180027d0e  mov     ecx, [rbx+94h]
0x180027d14  shr     ecx, 1
0x180027d16  and     cl, 1; unsigned __int8
0x180027d19  call    ?KpsGPCheckDisallowUnprotectedPasswordAuth@@YAEE@Z; KpsGPCheckDisallowUnprotectedPasswordAuth(uchar)
0x180027d1e  test    al, al
0x180027d20  jnz     short loc_180027D74
0x180027d22  test    cs:Microsoft_Windows_Kerberos_KdcProxyEnableBits, 10h
0x180027d29  mov     esi, 78Fh
0x180027d2e  jz      short loc_180027D43
0x180027d30  mov     r9, [rbx+0A0h]
0x180027d37  mov     r8, [rbx+0B0h]
0x180027d3e  call    McTemplateU0zz_EventWriteTransfer
0x180027d43  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d4a  lea     rbx, WPP_GLOBAL_Control
0x180027d51  cmp     rcx, rbx
0x180027d54  jz      short loc_180027D85
0x180027d56  test    byte ptr [rcx+1Ch], 10h
0x180027d5a  jz      short loc_180027D85
0x180027d5c  mov     rcx, [rcx+10h]; LoggerHandle
0x180027d60  mov     edx, 6Ah ; 'j'
0x180027d65  mov     r9, r15
0x180027d68  mov     [rsp+58h+var_38], r12; __int64
0x180027d6d  call    WPP_SF_ZZD
0x180027d72  jmp     short loc_180027D85
0x180027d74  mov     rcx, rbx; struct _KPS_IO *
0x180027d77  call    ?KpsCheckAsReqForBadPassword@@YAKPEAU_KPS_IO@@@Z; KpsCheckAsReqForBadPassword(_KPS_IO *)
0x180027d7c  mov     esi, eax
0x180027d7e  lea     rbx, WPP_GLOBAL_Control
0x180027d85  mov     rcx, r14; lpMem
0x180027d88  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x180027d8d  mov     rcx, rdi; lpMem
0x180027d90  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x180027d95  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d9c  cmp     rcx, rbx
0x180027d9f  jz      short loc_180027DBF
0x180027da1  test    byte ptr [rcx+1Ch], 20h
0x180027da5  jz      short loc_180027DBF
0x180027da7  mov     rcx, [rcx+10h]
0x180027dab  lea     r8, WPP_3e5ccd314c8a37fe62ed78d8f3344d0a_Traceguids
0x180027db2  mov     edx, 6Bh ; 'k'
0x180027db7  mov     r9d, esi
0x180027dba  call    WPP_SF_D
0x180027dbf  mov     rbx, [rsp+58h+arg_10]
0x180027dc4  mov     eax, esi
0x180027dc6  mov     rsi, [rsp+58h+arg_18]
0x180027dcb  add     rsp, 30h
0x180027dcf  pop     r15
0x180027dd1  pop     r14
0x180027dd3  pop     r13
0x180027dd5  pop     r12
0x180027dd7  pop     rdi
0x180027dd8  retn
```
