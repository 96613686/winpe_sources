# DfsRemoveDomainRootTarget(ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x140011c54`
- end: `0x14001201a`
- name: `?DfsRemoveDomainRootTarget@@YAKPEBG000KK@Z`
- size: `966`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140004d80`
- `0x140005030`

## callees

- `0x1400011c4`
- `0x140005b28`
- `0x140005c10`
- `0x140005cc4`
- `0x14000abc4`
- `0x14000ffbc`
- `0x140011c54`
- `0x140012748`
- `0x140012c20`
- `0x14001ca58`
- `0x14004a414`
- `0x1400571ac`
- `0x1400586a8`
- `0x1400591e4`
- `0x14005e010`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x140011f66`
- `ntdll!RtlCompareUnicodeString` at `0x140011f66`
- `ntdll!RtlInitUnicodeStringEx` at `0x140011dd6`
- `ntdll!RtlInitUnicodeStringEx` at `0x140011dd6`

## pseudocode

```c
__int64 __fastcall DfsRemoveDomainRootTarget(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int8 a5,
        unsigned int a6)
{
  unsigned __int16 *v6; // r15
  unsigned int *v11; // rcx
  const WCHAR *v12; // rdi
  unsigned __int8 IsScopedServerName; // r12
  const unsigned __int16 *AdDomainName; // rax
  unsigned int inited; // ebx
  unsigned int v16; // eax
  unsigned int v18; // eax
  int v19; // [rsp+28h] [rbp-58h]
  struct _UNICODE_STRING v20; // [rsp+40h] [rbp-40h] BYREF
  UNICODE_STRING String2; // [rsp+50h] [rbp-30h] BYREF
  UNICODE_STRING String1; // [rsp+60h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-10h] BYREF
  DfsGeneric *v24; // [rsp+B0h] [rbp+30h] BYREF

  v24 = 0;
  String2 = 0;
  a5 = 0;
  v6 = 0;
  v20 = 0;
  String1 = 0;
  DestinationString = 0;
  v11 = pWppControl;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x40) != 0
    && *((_BYTE *)pWppControl + 25) >= 2u )
  {
    WPP_SF_SSS(
      *((_QWORD *)pWppControl + 2),
      35,
      (unsigned int)WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids,
      (_DWORD)a1,
      (__int64)a3,
      (__int64)a4);
    v11 = pWppControl;
  }
  if ( !a1 || !*a1 || !a3 || !*a3 || !a4 || !*a4 )
    goto LABEL_36;
  v12 = DfsSkipLeadingPathSep(a1);
  IsScopedServerName = DfsIsScopedServerName(v12);
  if ( IsScopedServerName )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_S(*((_QWORD *)pWppControl + 2), 36, WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids, v12);
    }
    AdDomainName = v12;
  }
  else
  {
    AdDomainName = DfsGetAdDomainName();
  }
  inited = DfsRtlInitUnicodeStringEx(&String2, AdDomainName);
  if ( inited
    || (inited = DfsRtlInitUnicodeStringEx(&v20, a4)) != 0
    || (inited = DfsRtlInitUnicodeStringEx(&String1, a3)) != 0 )
  {
LABEL_54:
    v11 = pWppControl;
    goto LABEL_37;
  }
  RtlInitUnicodeStringEx(&DestinationString, 0);
  v16 = DfsLookupRootFolder(&String2, &v20, IsScopedServerName, &v24);
  inited = v16;
  v11 = pWppControl;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_SqD(
      *((_QWORD *)pWppControl + 2),
      37,
      (unsigned int)WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids,
      (_DWORD)a4,
      (char)v24,
      v16);
    v11 = pWppControl;
  }
  if ( !inited )
  {
    if ( *((_DWORD *)v24 + 78) != 512 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || !v11
        || (v11[7] & 0x40) == 0
        || *((_BYTE *)v11 + 25) < 2u )
      {
        goto LABEL_36;
      }
      WPP_SF_SS(
        *((_QWORD *)v11 + 2),
        38,
        (unsigned int)WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids,
        (_DWORD)v12,
        (__int64)a3);
LABEL_35:
      v11 = pWppControl;
LABEL_36:
      inited = 87;
      goto LABEL_37;
    }
    if ( a6 == 1 && *((_DWORD *)v24 + 55) != 1 )
    {
      inited = 50;
      goto LABEL_37;
    }
    if ( RtlCompareUnicodeString(&String1, (PCUNICODE_STRING)((char *)v24 + 152), 1u) )
      goto LABEL_35;
    v6 = (unsigned __int16 *)DfsNormaliseHostName(v12, &a5);
    if ( !v6 )
    {
      inited = 8;
      goto LABEL_54;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x40) != 0
      && *((_BYTE *)pWppControl + 25) >= 2u )
    {
      WPP_SF_SS(
        *((_QWORD *)pWppControl + 2),
        39,
        (unsigned int)WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids,
        (_DWORD)v12,
        (__int64)v6);
    }
    LOBYTE(v19) = IsScopedServerName;
    v18 = (*(__int64 (__fastcall **)(DfsGeneric *, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, _BYTE))(*(_QWORD *)v24 + 160LL))(
            v24,
            v6,
            a2,
            a3,
            a4,
            v19,
            0);
    v11 = pWppControl;
    inited = v18;
  }
LABEL_37:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && v11
    && (v11[7] & 0x20) != 0
    && *((_BYTE *)v11 + 25) >= 3u )
  {
    WPP_SF_qSD(
      *((_QWORD *)v11 + 2),
      40,
      (unsigned int)WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids,
      (_DWORD)v24,
      (__int64)a4,
      inited);
  }
  if ( v24 )
    DfsGeneric::ReleaseReference(v24);
  if ( a5 )
    operator delete(v6);
  return inited;
}

```

## disassembly

```asm
0x140011c54  mov     r11, rsp
0x140011c57  mov     [r11+10h], rbx
0x140011c5b  mov     [r11+18h], rsi
0x140011c5f  mov     [r11+20h], rdi
0x140011c63  push    rbp
0x140011c64  push    r12
0x140011c66  push    r13
0x140011c68  push    r14
0x140011c6a  push    r15
0x140011c6c  mov     rbp, rsp
0x140011c6f  sub     rsp, 80h
0x140011c76  xor     edi, edi
0x140011c78  xorps   xmm0, xmm0
0x140011c7b  xorps   xmm1, xmm1
0x140011c7e  mov     [rbp+arg_0], rdi
0x140011c82  movups  xmmword ptr [rbp+String2.Length], xmm0
0x140011c86  mov     [rbp+arg_20], dil
0x140011c8a  mov     r15d, edi
0x140011c8d  movups  xmmword ptr [rbp+var_40.Length], xmm1
0x140011c91  mov     r14, r9
0x140011c94  mov     rsi, r8
0x140011c97  movups  xmmword ptr [rbp+String1.Length], xmm0
0x140011c9b  mov     r13, rdx
0x140011c9e  mov     rbx, rcx
0x140011ca1  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140011ca5  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140011cac  lea     rax, WPP_GLOBAL_Control
0x140011cb3  cmp     cs:WPP_GLOBAL_Control, rax
0x140011cba  jz      short loc_140011CF3
0x140011cbc  test    rcx, rcx
0x140011cbf  jz      short loc_140011CF3
0x140011cc1  test    byte ptr [rcx+1Ch], 40h
0x140011cc5  jz      short loc_140011CF3
0x140011cc7  cmp     byte ptr [rcx+19h], 2
0x140011ccb  jb      short loc_140011CF3
0x140011ccd  mov     rcx, [rcx+10h]
0x140011cd1  lea     edx, [rdi+23h]
0x140011cd4  mov     [r11-80h], r9
0x140011cd8  mov     r9, rbx
0x140011cdb  mov     [rsp+80h+var_60], r8
0x140011ce0  lea     r8, WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids
0x140011ce7  call    WPP_SF_SSS
0x140011cec  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140011cf3  test    rbx, rbx
0x140011cf6  jz      loc_140011EAD
0x140011cfc  cmp     [rbx], di
0x140011cff  jz      loc_140011EAD
0x140011d05  test    rsi, rsi
0x140011d08  jz      loc_140011EAD
0x140011d0e  cmp     [rsi], di
0x140011d11  jz      loc_140011EAD
0x140011d17  test    r14, r14
0x140011d1a  jz      loc_140011EAD
0x140011d20  cmp     [r14], di
0x140011d24  jz      loc_140011EAD
0x140011d2a  mov     rcx, rbx; unsigned __int16 *
0x140011d2d  call    ?DfsSkipLeadingPathSep@@YAPEBGPEBG@Z; DfsSkipLeadingPathSep(ushort const *)
0x140011d32  mov     rcx, rax; SourceString
0x140011d35  mov     rdi, rax
0x140011d38  call    ?DfsIsScopedServerName@@YAEPEBG@Z; DfsIsScopedServerName(ushort const *)
0x140011d3d  mov     r12b, al
0x140011d40  test    al, al
0x140011d42  jz      short loc_140011D89
0x140011d44  lea     rax, WPP_GLOBAL_Control
0x140011d4b  cmp     cs:WPP_GLOBAL_Control, rax
0x140011d52  jz      short loc_140011D84
0x140011d54  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140011d5b  test    rcx, rcx
0x140011d5e  jz      short loc_140011D84
0x140011d60  test    byte ptr [rcx+1Ch], 20h
0x140011d64  jz      short loc_140011D84
0x140011d66  cmp     byte ptr [rcx+19h], 3
0x140011d6a  jb      short loc_140011D84
0x140011d6c  mov     rcx, [rcx+10h]
0x140011d70  lea     r8, WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids
0x140011d77  mov     edx, 24h ; '$'
0x140011d7c  mov     r9, rdi
0x140011d7f  call    WPP_SF_S
0x140011d84  mov     rax, rdi
0x140011d87  jmp     short loc_140011D8E
0x140011d89  call    ?DfsGetAdDomainName@@YAPEBGXZ; DfsGetAdDomainName(void)
0x140011d8e  mov     rdx, rax
0x140011d91  lea     rcx, [rbp+String2]
0x140011d95  call    DfsRtlInitUnicodeStringEx
0x140011d9a  mov     ebx, eax
0x140011d9c  test    eax, eax
0x140011d9e  jnz     loc_140011F91
0x140011da4  mov     rdx, r14
0x140011da7  lea     rcx, [rbp+var_40]
0x140011dab  call    DfsRtlInitUnicodeStringEx
0x140011db0  mov     ebx, eax
0x140011db2  test    eax, eax
0x140011db4  jnz     loc_140011F91
0x140011dba  mov     rdx, rsi
0x140011dbd  lea     rcx, [rbp+String1]
0x140011dc1  call    DfsRtlInitUnicodeStringEx
0x140011dc6  mov     ebx, eax
0x140011dc8  test    eax, eax
0x140011dca  jnz     loc_140011F91
0x140011dd0  xor     edx, edx; SourceString
0x140011dd2  lea     rcx, [rbp+DestinationString]; DestinationString
0x140011dd6  call    cs:__imp_RtlInitUnicodeStringEx
0x140011ddd  nop     dword ptr [rax+rax+00h]
0x140011de2  lea     r9, [rbp+arg_0]; struct DfsRootFolder **
0x140011de6  mov     r8b, r12b; unsigned __int8
0x140011de9  lea     rdx, [rbp+var_40]; struct _UNICODE_STRING *
0x140011ded  lea     rcx, [rbp+String2]; String2
0x140011df1  call    ?DfsLookupRootFolder@@YAKPEAU_UNICODE_STRING@@0EPEAPEAVDfsRootFolder@@@Z; DfsLookupRootFolder(_UNICODE_STRING *,_UNICODE_STRING *,uchar,DfsRootFolder * *)
0x140011df6  mov     ebx, eax
0x140011df8  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140011dff  lea     rdx, WPP_GLOBAL_Control
0x140011e06  cmp     cs:WPP_GLOBAL_Control, rdx
0x140011e0d  jz      short loc_140011E53
0x140011e0f  test    rcx, rcx
0x140011e12  jz      short loc_140011E53
0x140011e14  test    byte ptr [rcx+1Ch], 20h
0x140011e18  jz      short loc_140011E53
0x140011e1a  cmp     byte ptr [rcx+19h], 3
0x140011e1e  jb      short loc_140011E53
0x140011e20  mov     rcx, [rcx+10h]
0x140011e24  lea     r8, WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids
0x140011e2b  mov     [rsp+80h+var_58], eax
0x140011e2f  mov     edx, 25h ; '%'
0x140011e34  mov     rax, [rbp+arg_0]
0x140011e38  mov     r9, r14
0x140011e3b  mov     [rsp+80h+var_60], rax
0x140011e40  call    WPP_SF_SqD
0x140011e45  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140011e4c  lea     rdx, WPP_GLOBAL_Control
0x140011e53  test    ebx, ebx
0x140011e55  jnz     loc_140011F4D
0x140011e5b  mov     rax, [rbp+arg_0]
0x140011e5f  cmp     dword ptr [rax+138h], 200h
0x140011e69  jz      loc_140011F35
0x140011e6f  cmp     cs:WPP_GLOBAL_Control, rdx
0x140011e76  jz      short loc_140011EAB
0x140011e78  test    rcx, rcx
0x140011e7b  jz      short loc_140011EAB
0x140011e7d  test    byte ptr [rcx+1Ch], 40h
0x140011e81  jz      short loc_140011EAB
0x140011e83  cmp     byte ptr [rcx+19h], 2
0x140011e87  jb      short loc_140011EAB
0x140011e89  mov     rcx, [rcx+10h]
0x140011e8d  lea     edx, [rbx+26h]
0x140011e90  mov     r9, rdi
0x140011e93  mov     [rsp+80h+var_60], rsi
0x140011e98  lea     r8, WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids
0x140011e9f  call    WPP_SF_SS
0x140011ea4  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140011eab  xor     edi, edi
0x140011ead  mov     ebx, 57h ; 'W'
0x140011eb2  lea     rax, WPP_GLOBAL_Control
0x140011eb9  cmp     cs:WPP_GLOBAL_Control, rax
0x140011ec0  jz      short loc_140011EF5
0x140011ec2  test    rcx, rcx
0x140011ec5  jz      short loc_140011EF5
0x140011ec7  test    byte ptr [rcx+1Ch], 20h
0x140011ecb  jz      short loc_140011EF5
0x140011ecd  cmp     byte ptr [rcx+19h], 3
0x140011ed1  jb      short loc_140011EF5
0x140011ed3  mov     r9, [rbp+arg_0]
0x140011ed7  lea     r8, WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids
0x140011ede  mov     rcx, [rcx+10h]
0x140011ee2  mov     edx, 28h ; '('
0x140011ee7  mov     [rsp+80h+var_58], ebx
0x140011eeb  mov     [rsp+80h+var_60], r14
0x140011ef0  call    WPP_SF_qSD
0x140011ef5  mov     rcx, [rbp+arg_0]; this
0x140011ef9  test    rcx, rcx
0x140011efc  jz      short loc_140011F03
0x140011efe  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x140011f03  cmp     [rbp+arg_20], dil
0x140011f07  jz      short loc_140011F11
0x140011f09  mov     rcx, r15; Block
0x140011f0c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140011f11  lea     r11, [rsp+80h+var_s0]
0x140011f19  mov     eax, ebx
0x140011f1b  mov     rbx, [r11+38h]
0x140011f1f  mov     rsi, [r11+40h]
0x140011f23  mov     rdi, [r11+48h]
0x140011f27  mov     rsp, r11
0x140011f2a  pop     r15
0x140011f2c  pop     r14
0x140011f2e  pop     r13
0x140011f30  pop     r12
0x140011f32  pop     rbp
0x140011f33  retn
0x140011f35  cmp     [rbp+arg_28], 1
0x140011f39  jnz     short loc_140011F54
0x140011f3b  mov     rax, [rbp+arg_0]
0x140011f3f  cmp     dword ptr [rax+0DCh], 1
0x140011f46  jz      short loc_140011F54
0x140011f48  mov     ebx, 32h ; '2'
0x140011f4d  xor     edi, edi
0x140011f4f  jmp     loc_140011EB2
0x140011f54  mov     rdx, [rbp+arg_0]
0x140011f58  lea     rcx, [rbp+String1]; String1
0x140011f5c  add     rdx, 98h; String2
0x140011f63  mov     r8b, 1; CaseInsensitive
0x140011f66  call    cs:__imp_RtlCompareUnicodeString
0x140011f6d  nop     dword ptr [rax+rax+00h]
0x140011f72  test    eax, eax
0x140011f74  jnz     loc_140011EA4
0x140011f7a  lea     rdx, [rbp+arg_20]; unsigned __int8 *
0x140011f7e  mov     rcx, rdi; unsigned __int16 *
0x140011f81  call    ?DfsNormaliseHostName@@YAPEBGPEBGPEAE@Z; DfsNormaliseHostName(ushort const *,uchar *)
0x140011f86  mov     r15, rax
0x140011f89  test    rax, rax
0x140011f8c  jnz     short loc_140011F9A
0x140011f8e  lea     ebx, [rax+8]
0x140011f91  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140011f98  jmp     short loc_140011F4D
0x140011f9a  lea     rax, WPP_GLOBAL_Control
0x140011fa1  cmp     cs:WPP_GLOBAL_Control, rax
0x140011fa8  jz      short loc_140011FDF
0x140011faa  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140011fb1  test    rcx, rcx
0x140011fb4  jz      short loc_140011FDF
0x140011fb6  test    byte ptr [rcx+1Ch], 40h
0x140011fba  jz      short loc_140011FDF
0x140011fbc  cmp     byte ptr [rcx+19h], 2
0x140011fc0  jb      short loc_140011FDF
0x140011fc2  mov     rcx, [rcx+10h]
0x140011fc6  lea     r8, WPP_b559db2e15fe3b9d2aa49457f6fd7b63_Traceguids
0x140011fcd  mov     edx, 27h ; '''
0x140011fd2  mov     [rsp+80h+var_60], r15
0x140011fd7  mov     r9, rdi
0x140011fda  call    WPP_SF_SS
0x140011fdf  mov     rcx, [rbp+arg_0]
0x140011fe3  xor     edi, edi
0x140011fe5  mov     [rsp+80h+var_50], dil
0x140011fea  mov     r9, rsi
0x140011fed  mov     byte ptr [rsp+80h+var_58], r12b
0x140011ff2  mov     r8, r13
0x140011ff5  mov     rdx, r15
0x140011ff8  mov     [rsp+80h+var_60], r14
0x140011ffd  mov     rax, [rcx]
0x140012000  mov     rax, [rax+0A0h]
0x140012007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001200c  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140012013  mov     ebx, eax
0x140012015  jmp     loc_140011EB2
```
