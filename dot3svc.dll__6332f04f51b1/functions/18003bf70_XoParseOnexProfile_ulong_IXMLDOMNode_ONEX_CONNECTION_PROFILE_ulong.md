# XoParseOnexProfile(ulong,IXMLDOMNode *,_ONEX_CONNECTION_PROFILE * *,ulong *)

- ea: `0x18003bf70`
- end: `0x18003c2d8`
- name: `?XoParseOnexProfile@@YAKKPEAUIXMLDOMNode@@PEAPEAU_ONEX_CONNECTION_PROFILE@@PEAK@Z`
- size: `872`
- prototype: `unsigned int(unsigned int, struct IXMLDOMNode *, struct _ONEX_CONNECTION_PROFILE **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180033c08`

## callees

- `0x180030fd8`
- `0x1800326fc`
- `0x18003b4ec`
- `0x18003b5c8`
- `0x18003ba24`
- `0x18003bcb0`
- `0x18003bd10`
- `0x18003bf70`
- `0x18003c694`
- `0x18003c9a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bfe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bfe9`

## string_xrefs

- `0x18003c00e`: `OneX:cacheUserData`

## pseudocode

```c
__int64 __fastcall XoParseOnexProfile(
        __int64 a1,
        struct IXMLDOMNode *a2,
        struct _ONEX_CONNECTION_PROFILE **a3,
        unsigned int *a4)
{
  unsigned int SingleNode; // eax
  unsigned int NodeEnumValue; // edi
  struct _ONEX_CONNECTION_PROFILE *v7; // rax
  struct _ONEX_CONNECTION_PROFILE *v8; // rbx
  unsigned int v9; // r9d
  unsigned int v10; // r9d
  char v11; // al
  unsigned int v12; // r9d
  char v13; // al
  unsigned int v14; // r9d
  char v15; // al
  unsigned int v16; // r9d
  char v17; // al
  char v18; // al
  char v19; // al
  unsigned int *v20; // r8
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // rcx
  unsigned int *v24; // r9
  int v26; // [rsp+28h] [rbp-28h]
  int v27; // [rsp+28h] [rbp-28h]
  int v28; // [rsp+28h] [rbp-28h]
  int v29; // [rsp+28h] [rbp-28h]
  int v30; // [rsp+28h] [rbp-28h]
  struct IXMLDOMNode *v31; // [rsp+40h] [rbp-10h] BYREF
  struct _ONEX_CONNECTION_PROFILE *v32; // [rsp+48h] [rbp-8h] BYREF
  int v33; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v34; // [rsp+98h] [rbp+48h] BYREF
  int v35; // [rsp+9Ch] [rbp+4Ch]

  v35 = HIDWORD(a4);
  v31 = 0;
  v34 = 0;
  v33 = 0;
  SingleNode = XcGetSingleNode(a2, L"OneX:OneX", &v31);
  NodeEnumValue = SingleNode;
  if ( SingleNode == 1168 )
  {
    NodeEnumValue = 0;
    *a3 = 0;
  }
  else if ( !SingleNode )
  {
    v7 = (struct _ONEX_CONNECTION_PROFILE *)Xc_Process_user_allocate(0x68u);
    v32 = v7;
    v8 = v7;
    if ( v7 )
    {
      *(_DWORD *)v7 = 1;
      *((_DWORD *)v7 + 1) = 104;
      NodeEnumValue = XcGetNodeEnumValue(
                        v31,
                        L"OneX:cacheUserData",
                        (const struct _XC_STRING_VALUE_MAPPING *)&off_180042480,
                        4u,
                        &v34,
                        1,
                        1u,
                        &v33);
      if ( !NodeEnumValue )
      {
        if ( v33 )
        {
          *((_DWORD *)v8 + 2) |= 1u;
          if ( !v34 )
            *((_DWORD *)v8 + 3) |= 2u;
        }
        NodeEnumValue = XcGetNodeDWORDValue(
                          v31,
                          L"OneX:heldPeriod",
                          (unsigned int *)v8 + 6,
                          v9,
                          0xE10u,
                          v26,
                          0xFFFFFFFF,
                          &v33);
        if ( !NodeEnumValue )
        {
          v11 = v33;
          *((_DWORD *)v8 + 2) &= ~8u;
          *((_DWORD *)v8 + 2) |= 8 * (v11 & 1);
          NodeEnumValue = XcGetNodeDWORDValue(
                            v31,
                            L"OneX:authPeriod",
                            (unsigned int *)v8 + 7,
                            v10,
                            0xE10u,
                            v27,
                            0xFFFFFFFF,
                            &v33);
          if ( !NodeEnumValue )
          {
            v13 = v33;
            *((_DWORD *)v8 + 2) &= ~0x10u;
            *((_DWORD *)v8 + 2) |= 16 * (v13 & 1);
            NodeEnumValue = XcGetNodeDWORDValue(
                              v31,
                              L"OneX:startPeriod",
                              (unsigned int *)v8 + 8,
                              v12,
                              0xE10u,
                              v28,
                              0xFFFFFFFF,
                              &v33);
            if ( !NodeEnumValue )
            {
              v15 = v33;
              *((_DWORD *)v8 + 2) &= ~0x20u;
              *((_DWORD *)v8 + 2) |= 32 * (v15 & 1);
              NodeEnumValue = XcGetNodeDWORDValue(
                                v31,
                                L"OneX:maxStart",
                                (unsigned int *)v8 + 9,
                                v14,
                                0x64u,
                                v29,
                                0xFFFFFFFF,
                                &v33);
              if ( !NodeEnumValue )
              {
                v17 = v33;
                *((_DWORD *)v8 + 2) &= ~0x40u;
                *((_DWORD *)v8 + 2) |= (v17 & 1) << 6;
                NodeEnumValue = XcGetNodeDWORDValue(
                                  v31,
                                  L"OneX:maxAuthFailures",
                                  (unsigned int *)v8 + 10,
                                  v16,
                                  0x64u,
                                  v30,
                                  0xFFFFFFFF,
                                  &v33);
                if ( !NodeEnumValue )
                {
                  v18 = v33;
                  *((_DWORD *)v8 + 2) &= ~0x80u;
                  *((_DWORD *)v8 + 2) |= (v18 & 1) << 7;
                  NodeEnumValue = XcGetNodeEnumValue(
                                    v31,
                                    L"OneX:supplicantMode",
                                    (const struct _XC_STRING_VALUE_MAPPING *)&off_180042520,
                                    3u,
                                    (unsigned int *)v8 + 4,
                                    1,
                                    3u,
                                    &v33);
                  if ( !NodeEnumValue )
                  {
                    v19 = v33;
                    *((_DWORD *)v8 + 2) &= ~2u;
                    *((_DWORD *)v8 + 2) |= 2 * (v19 & 1);
                    NodeEnumValue = XcGetNodeEnumValue(
                                      v31,
                                      L"OneX:authMode",
                                      (const struct _XC_STRING_VALUE_MAPPING *)&off_1800424E0,
                                      4u,
                                      (unsigned int *)v8 + 5,
                                      1,
                                      5u,
                                      &v33);
                    if ( !NodeEnumValue )
                    {
                      *((_DWORD *)v8 + 2) &= ~4u;
                      *((_DWORD *)v8 + 2) |= 4 * (v33 & 1);
                      NodeEnumValue = XopParseSingleSignOn(v31, v8, v20);
                      if ( !NodeEnumValue )
                      {
                        NodeEnumValue = GetAlignedSize(32, (char *)v8 + 60, v21);
                        if ( !NodeEnumValue )
                        {
                          NodeEnumValue = GetAlignedSize(68, (char *)v8 + 64, v22);
                          if ( !NodeEnumValue )
                          {
                            NodeEnumValue = XopParseEapConfig(v23, v31, &v32, v24);
                            if ( !NodeEnumValue )
                            {
                              *a3 = v32;
                              goto LABEL_26;
                            }
                            v8 = v32;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      NodeEnumValue = GetLastError();
      if ( !NodeEnumValue )
        goto LABEL_26;
    }
    if ( v8 )
      Xc_Process_user_free(v8);
  }
LABEL_26:
  ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>((__int64 *)&v31);
  return NodeEnumValue;
}

```

## disassembly

```asm
0x18003bf70  mov     [rsp-28h+arg_8], rbx
0x18003bf75  mov     qword ptr [rsp-28h+arg_18], r9
0x18003bf7a  mov     [rsp-28h+arg_0], ecx
0x18003bf7e  push    rbp
0x18003bf7f  push    rsi
0x18003bf80  push    rdi
0x18003bf81  push    r12
0x18003bf83  push    r15
0x18003bf85  mov     rbp, rsp
0x18003bf88  sub     rsp, 50h
0x18003bf8c  mov     rsi, r8
0x18003bf8f  mov     [rbp+var_10], 0
0x18003bf97  mov     rcx, rdx; struct IXMLDOMNode *
0x18003bf9a  mov     [rbp+arg_18], 0
0x18003bfa1  lea     r8, [rbp+var_10]; struct IXMLDOMNode **
0x18003bfa5  mov     [rbp+arg_0], 0
0x18003bfac  lea     rdx, aOnexOnex; "OneX:OneX"
0x18003bfb3  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18003bfb8  mov     edi, eax
0x18003bfba  cmp     eax, 490h
0x18003bfbf  jnz     short loc_18003BFCB
0x18003bfc1  xor     edi, edi
0x18003bfc3  mov     [rsi], rdi
0x18003bfc6  jmp     loc_18003C2B9
0x18003bfcb  test    eax, eax
0x18003bfcd  jnz     loc_18003C2B9
0x18003bfd3  lea     edi, [rax+68h]
0x18003bfd6  mov     ecx, edi; dwBytes
0x18003bfd8  call    ?Xc_Process_user_allocate@@YAPEAX_K@Z; Xc_Process_user_allocate(unsigned __int64)
0x18003bfdd  mov     [rbp+var_8], rax
0x18003bfe1  mov     rbx, rax
0x18003bfe4  test    rax, rax
0x18003bfe7  jnz     short loc_18003BFFE
0x18003bfe9  call    cs:__imp_GetLastError
0x18003bfef  mov     edi, eax
0x18003bff1  test    eax, eax
0x18003bff3  jz      loc_18003C2B9
0x18003bff9  jmp     loc_18003C2AC
0x18003bffe  mov     r15d, 1
0x18003c004  lea     r8, off_180042480; struct _XC_STRING_VALUE_MAPPING *
0x18003c00b  mov     [rax], r15d
0x18003c00e  lea     rdx, aOnexCacheuserd; "OneX:cacheUserData"
0x18003c015  mov     [rax+4], edi
0x18003c018  lea     rax, [rbp+arg_0]
0x18003c01c  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x18003c020  mov     [rsp+50h+var_18], rax; int *
0x18003c025  lea     r9d, [r15+3]; unsigned int
0x18003c029  mov     [rsp+50h+var_20], r15d; unsigned int
0x18003c02e  lea     rax, [rbp+arg_18]
0x18003c032  mov     [rsp+50h+var_28], r15d; int
0x18003c037  mov     [rsp+50h+var_30], rax; unsigned int *
0x18003c03c  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18003c041  mov     edi, eax
0x18003c043  test    eax, eax
0x18003c045  jnz     loc_18003C2AC
0x18003c04b  cmp     [rbp+arg_0], eax
0x18003c04e  jz      short loc_18003C05D
0x18003c050  or      [rbx+8], r15d
0x18003c054  cmp     [rbp+arg_18], eax
0x18003c057  jnz     short loc_18003C05D
0x18003c059  or      dword ptr [rbx+0Ch], 2
0x18003c05d  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x18003c061  lea     rax, [rbp+arg_0]
0x18003c065  mov     [rsp+50h+var_18], rax; int *
0x18003c06a  lea     r8, [rbx+18h]; unsigned int *
0x18003c06e  or      r12d, 0FFFFFFFFh
0x18003c072  lea     rdx, aOnexHeldperiod; "OneX:heldPeriod"
0x18003c079  mov     [rsp+50h+var_20], r12d; unsigned int
0x18003c07e  mov     dword ptr [rsp+50h+var_30], 0E10h; unsigned int
0x18003c086  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x18003c08b  mov     edi, eax
0x18003c08d  test    eax, eax
0x18003c08f  jnz     loc_18003C2AC
0x18003c095  mov     eax, [rbp+arg_0]
0x18003c098  lea     r8, [rbx+1Ch]; unsigned int *
0x18003c09c  and     dword ptr [rbx+8], 0FFFFFFF7h
0x18003c0a0  lea     rdx, aOnexAuthperiod; "OneX:authPeriod"
0x18003c0a7  and     eax, r15d
0x18003c0aa  shl     eax, 3
0x18003c0ad  or      [rbx+8], eax
0x18003c0b0  lea     rax, [rbp+arg_0]
0x18003c0b4  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x18003c0b8  mov     [rsp+50h+var_18], rax; int *
0x18003c0bd  mov     [rsp+50h+var_20], r12d; unsigned int
0x18003c0c2  mov     dword ptr [rsp+50h+var_30], 0E10h; unsigned int
0x18003c0ca  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x18003c0cf  mov     edi, eax
0x18003c0d1  test    eax, eax
0x18003c0d3  jnz     loc_18003C2AC
0x18003c0d9  mov     eax, [rbp+arg_0]
0x18003c0dc  lea     r8, [rbx+20h]; unsigned int *
0x18003c0e0  and     dword ptr [rbx+8], 0FFFFFFEFh
0x18003c0e4  lea     rdx, aOnexStartperio; "OneX:startPeriod"
0x18003c0eb  and     eax, r15d
0x18003c0ee  shl     eax, 4
0x18003c0f1  or      [rbx+8], eax
0x18003c0f4  lea     rax, [rbp+arg_0]
0x18003c0f8  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x18003c0fc  mov     [rsp+50h+var_18], rax; int *
0x18003c101  mov     [rsp+50h+var_20], r12d; unsigned int
0x18003c106  mov     dword ptr [rsp+50h+var_30], 0E10h; unsigned int
0x18003c10e  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x18003c113  mov     edi, eax
0x18003c115  test    eax, eax
0x18003c117  jnz     loc_18003C2AC
0x18003c11d  mov     eax, [rbp+arg_0]
0x18003c120  lea     r8, [rbx+24h]; unsigned int *
0x18003c124  and     dword ptr [rbx+8], 0FFFFFFDFh
0x18003c128  lea     rdx, aOnexMaxstart; "OneX:maxStart"
0x18003c12f  and     eax, r15d
0x18003c132  shl     eax, 5
0x18003c135  or      [rbx+8], eax
0x18003c138  lea     rax, [rbp+arg_0]
0x18003c13c  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x18003c140  mov     [rsp+50h+var_18], rax; int *
0x18003c145  mov     [rsp+50h+var_20], r12d; unsigned int
0x18003c14a  mov     dword ptr [rsp+50h+var_30], 64h ; 'd'; unsigned int
0x18003c152  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x18003c157  mov     edi, eax
0x18003c159  test    eax, eax
0x18003c15b  jnz     loc_18003C2AC
0x18003c161  mov     eax, [rbp+arg_0]
0x18003c164  lea     r8, [rbx+28h]; unsigned int *
0x18003c168  and     dword ptr [rbx+8], 0FFFFFFBFh
0x18003c16c  lea     rdx, aOnexMaxauthfai; "OneX:maxAuthFailures"
0x18003c173  and     eax, r15d
0x18003c176  shl     eax, 6
0x18003c179  or      [rbx+8], eax
0x18003c17c  lea     rax, [rbp+arg_0]
0x18003c180  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x18003c184  mov     [rsp+50h+var_18], rax; int *
0x18003c189  mov     [rsp+50h+var_20], r12d; unsigned int
0x18003c18e  mov     dword ptr [rsp+50h+var_30], 64h ; 'd'; unsigned int
0x18003c196  call    ?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z; XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)
0x18003c19b  mov     edi, eax
0x18003c19d  test    eax, eax
0x18003c19f  jnz     loc_18003C2AC
0x18003c1a5  mov     eax, [rbp+arg_0]
0x18003c1a8  lea     rcx, [rbp+arg_0]
0x18003c1ac  btr     dword ptr [rbx+8], 7
0x18003c1b1  lea     r9d, [rdi+3]; unsigned int
0x18003c1b5  mov     [rsp+50h+var_18], rcx; int *
0x18003c1ba  lea     r8, off_180042520; struct _XC_STRING_VALUE_MAPPING *
0x18003c1c1  and     eax, r15d
0x18003c1c4  mov     [rsp+50h+var_20], r9d; unsigned int
0x18003c1c9  shl     eax, 7
0x18003c1cc  lea     rdx, aOnexSupplicant; "OneX:supplicantMode"
0x18003c1d3  or      [rbx+8], eax
0x18003c1d6  lea     rax, [rbx+10h]
0x18003c1da  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x18003c1de  mov     [rsp+50h+var_28], r15d; int
0x18003c1e3  mov     [rsp+50h+var_30], rax; unsigned int *
0x18003c1e8  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18003c1ed  mov     edi, eax
0x18003c1ef  test    eax, eax
0x18003c1f1  jnz     loc_18003C2AC
0x18003c1f7  mov     eax, [rbp+arg_0]
0x18003c1fa  lea     rcx, [rbp+arg_0]
0x18003c1fe  and     dword ptr [rbx+8], 0FFFFFFFDh
0x18003c202  lea     r9d, [rdi+4]; unsigned int
0x18003c206  mov     [rsp+50h+var_18], rcx; int *
0x18003c20b  lea     r8, off_1800424E0; struct _XC_STRING_VALUE_MAPPING *
0x18003c212  and     eax, r15d
0x18003c215  mov     [rsp+50h+var_20], 5; unsigned int
0x18003c21d  add     eax, eax
0x18003c21f  mov     [rsp+50h+var_28], r15d; int
0x18003c224  or      [rbx+8], eax
0x18003c227  lea     rdx, aOnexAuthmode; "OneX:authMode"
0x18003c22e  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x18003c232  lea     rax, [rbx+14h]
0x18003c236  mov     [rsp+50h+var_30], rax; unsigned int *
0x18003c23b  call    ?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z; XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)
0x18003c240  mov     edi, eax
0x18003c242  test    eax, eax
0x18003c244  jnz     short loc_18003C2AC
0x18003c246  and     dword ptr [rbx+8], 0FFFFFFFBh
0x18003c24a  mov     rdx, rbx; struct _ONEX_CONNECTION_PROFILE *
0x18003c24d  mov     eax, [rbp+arg_0]
0x18003c250  and     eax, r15d
0x18003c253  shl     eax, 2
0x18003c256  or      [rbx+8], eax
0x18003c259  mov     rcx, [rbp+var_10]; struct IXMLDOMNode *
0x18003c25d  call    ?XopParseSingleSignOn@@YAKPEAUIXMLDOMNode@@PEAU_ONEX_CONNECTION_PROFILE@@PEAK@Z; XopParseSingleSignOn(IXMLDOMNode *,_ONEX_CONNECTION_PROFILE *,ulong *)
0x18003c262  mov     edi, eax
0x18003c264  test    eax, eax
0x18003c266  jnz     short loc_18003C2AC
0x18003c268  lea     rdx, [rbx+3Ch]
0x18003c26c  lea     ecx, [rax+20h]
0x18003c26f  call    GetAlignedSize
0x18003c274  mov     edi, eax
0x18003c276  test    eax, eax
0x18003c278  jnz     short loc_18003C2AC
0x18003c27a  lea     rdx, [rbx+40h]
0x18003c27e  lea     ecx, [rax+44h]
0x18003c281  call    GetAlignedSize
0x18003c286  mov     edi, eax
0x18003c288  test    eax, eax
0x18003c28a  jnz     short loc_18003C2AC
0x18003c28c  mov     rdx, [rbp+var_10]; struct IXMLDOMNode *
0x18003c290  lea     r8, [rbp+var_8]; struct _ONEX_CONNECTION_PROFILE **
0x18003c294  call    ?XopParseEapConfig@@YAKKPEAUIXMLDOMNode@@PEAPEAU_ONEX_CONNECTION_PROFILE@@PEAK@Z; XopParseEapConfig(ulong,IXMLDOMNode *,_ONEX_CONNECTION_PROFILE * *,ulong *)
0x18003c299  mov     edi, eax
0x18003c29b  test    eax, eax
0x18003c29d  jnz     short loc_18003C2A8
0x18003c29f  mov     rax, [rbp+var_8]
0x18003c2a3  mov     [rsi], rax
0x18003c2a6  jmp     short loc_18003C2B9
0x18003c2a8  mov     rbx, [rbp+var_8]
0x18003c2ac  test    rbx, rbx
0x18003c2af  jz      short loc_18003C2B9
0x18003c2b1  mov     rcx, rbx; lpMem
0x18003c2b4  call    ?Xc_Process_user_free@@YAXPEAX@Z; Xc_Process_user_free(void *)
0x18003c2b9  lea     rcx, [rbp+var_10]
0x18003c2bd  call    ??1?$CComPtrBase@UIXMLDOMParseError@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMParseError>::~CComPtrBase<IXMLDOMParseError>(void)
0x18003c2c2  mov     rbx, [rsp+50h+arg_8]
0x18003c2ca  mov     eax, edi
0x18003c2cc  add     rsp, 50h
0x18003c2d0  pop     r15
0x18003c2d2  pop     r12
0x18003c2d4  pop     rdi
0x18003c2d5  pop     rsi
0x18003c2d6  pop     rbp
0x18003c2d7  retn
```
