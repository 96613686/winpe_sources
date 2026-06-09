# PeapCreateMethodConfiguration(ulong,_CONFIG_ATTRIBUTES const * const,ulong *,uchar * *)

- ea: `0x18005f230`
- end: `0x18005f61f`
- name: `?PeapCreateMethodConfiguration@@YAKKQEBU_CONFIG_ATTRIBUTES@@PEAKPEAPEAE@Z`
- size: `1007`
- prototype: `unsigned int __fastcall(unsigned int, const struct _CONFIG_ATTRIBUTES *const, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060c10`

## callees

- `0x180004bd0`
- `0x1800060f0`
- `0x1800075b0`
- `0x18001f020`
- `0x1800200b4`
- `0x18002ac1c`
- `0x18003623c`
- `0x18005f230`
- `0x18005fb70`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f4c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005f4c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f5e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f5f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f5e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f5f2`

## string_xrefs

- `0x18005f3b2`: `xmlns:EapHostConfig='http://www.microsoft.com/provisioning/EapHostConfig' xmlns:baseeapconnectionpropertiesv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1' `

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PeapCreateMethodConfiguration(
        unsigned int a1,
        const struct _CONFIG_ATTRIBUTES *a2,
        unsigned int *a3,
        struct _PEAP_CONN_PROPERTIES **a4)
{
  const struct _CONFIG_ATTRIBUTES *v4; // r15
  unsigned int v5; // r12d
  struct IXMLDOMDocument2 *v6; // rbx
  unsigned __int8 *v7; // r14
  unsigned int v8; // r13d
  unsigned int ConnectionData; // esi
  struct _PEAP_CONN_PROPERTIES *v10; // rdi
  char v11; // al
  __int64 v12; // rdx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  struct IXMLDOMDocument2 *v17; // r15
  struct _EAPTLS_CONTROL_BLOCK *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  unsigned int v21; // eax
  __int64 v22; // r9
  struct _EAPTLS_CONTROL_BLOCK *v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned int v26; // r15d
  struct _PEAP_CONN_PROPERTIES *v27; // rax
  struct _PEAP_CONN_PROPERTIES *v28; // rbx
  struct _PEAP_ENTRY_CONN_PROPERTIES *v29; // rcx
  unsigned int v30; // r15d
  char v32; // [rsp+30h] [rbp-48h]
  char v33; // [rsp+31h] [rbp-47h]
  char v34; // [rsp+32h] [rbp-46h]
  unsigned int v35; // [rsp+34h] [rbp-44h] BYREF
  unsigned int v36; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int8 *v37; // [rsp+40h] [rbp-38h] BYREF
  void *Src; // [rsp+48h] [rbp-30h] BYREF
  struct IXMLDOMNode *v39; // [rsp+50h] [rbp-28h] BYREF
  struct _PEAP_ENTRY_CONN_PROPERTIES *v40; // [rsp+58h] [rbp-20h] BYREF
  struct IXMLDOMDocument2 *v41; // [rsp+60h] [rbp-18h] BYREF
  unsigned __int16 *v42; // [rsp+68h] [rbp-10h] BYREF

  v4 = a2;
  v5 = 0;
  Src = 0;
  v6 = 0;
  v41 = 0;
  v39 = 0;
  v40 = 0;
  v7 = 0;
  v37 = 0;
  v8 = 0;
  v35 = 0;
  v36 = 0;
  *a4 = 0;
  *a3 = 0;
  ConnectionData = PeapReadConnectionData(a1, 0, 0, (struct _PEAP_CONN_PROPERTIES **)&Src);
  v10 = (struct _PEAP_CONN_PROPERTIES *)Src;
  if ( !ConnectionData )
  {
    v11 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    while ( v5 < *(_DWORD *)v4 )
    {
      v12 = *((_QWORD *)a2 + 1);
      v13 = *(_DWORD *)(v12 + 16LL * v5);
      if ( (unsigned int)(v13 - 1) > 9 )
      {
        ConnectionData = 13;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_59;
        v19 = 141;
        v20 = v5;
LABEL_58:
        WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v20);
        goto LABEL_59;
      }
      v14 = v13 - 2;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            if ( v16 == 1 )
            {
              v17 = *(struct IXMLDOMDocument2 **)(v12 + 16LL * v5 + 8);
              if ( v6 != v17 )
              {
                if ( v17 )
                  ((void (__fastcall *)(struct IXMLDOMDocument2 *))v17->lpVtbl->AddRef)(v17);
                if ( v6 )
                  ((void (__fastcall *)(struct IXMLDOMDocument2 *))v6->lpVtbl->Release)(v6);
                v6 = v17;
                v41 = v17;
              }
            }
          }
          else
          {
            v34 = 1;
          }
        }
        else
        {
          v33 = 1;
        }
        v11 = v32;
      }
      else
      {
        v11 = 1;
        v32 = 1;
      }
      ++v5;
      v4 = a2;
    }
    if ( v33 )
      *((_DWORD *)v10 + 3) |= 8u;
    else
      *((_DWORD *)v10 + 3) &= ~8u;
    if ( v34 )
      *((_DWORD *)v10 + 3) |= 1u;
    else
      *((_DWORD *)v10 + 3) &= ~1u;
    if ( v11 )
      *((_DWORD *)v10 + 6) &= 0xFFFFFFF9;
    else
      *((_DWORD *)v10 + 6) |= 6u;
    if ( v6 )
    {
      v42 = 0;
      Src = 0;
      v21 = SetNsAndSchema(
              v6,
              L"xmlns:EapHostConfig='http://www.microsoft.com/provisioning/EapHostConfig' xmlns:baseeapconnectionpropertie"
               "sv1='http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1' ",
              (const unsigned __int16 **)&v42,
              (const unsigned __int16 **)&Src);
      v22 = v21;
      if ( v21 )
      {
        ConnectionData = (unsigned __int16)v21;
        if ( (v21 & 0x1FFF0000) != 0x70000 )
          ConnectionData = v21;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_59;
        v24 = 143;
LABEL_37:
        WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v22);
        goto LABEL_59;
      }
      v25 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, GUID *, struct IXMLDOMNode **, _QWORD))v6->lpVtbl->QueryInterface)(
              v6,
              &IID_IXMLDOMNode,
              &v39,
              0);
      v22 = v25;
      if ( v25 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_59;
        v24 = 144;
        goto LABEL_37;
      }
      ConnectionData = getInnerConnectionPropertiesFromDOMNode(v39, a1, &v36, v10, &v37, &v35);
      if ( ConnectionData )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            145,
            WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
            ConnectionData);
        v7 = v37;
        goto LABEL_59;
      }
      v7 = v37;
      v8 = v35;
    }
    v26 = v8 + *((_DWORD *)v10 + 1);
    v27 = (struct _PEAP_CONN_PROPERTIES *)LocalAlloc(0x40u, v26);
    v28 = v27;
    if ( v27 )
    {
      memcpy_0(v27, v10, *((unsigned int *)v10 + 1));
      *((_DWORD *)v28 + 1) = v26;
      if ( v7 && v8 )
      {
        PeapGetFirstEntryConnProp(v28, &v40);
        v29 = v40;
        *(_DWORD *)v40 = 1;
        v30 = v36;
        *((_DWORD *)v29 + 2) = v36;
        *((_DWORD *)v29 + 1) = v8 + 15;
        memcpy_0((char *)v29 + 12, v7, v8);
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, v30);
      }
      else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
      }
      *a3 = *((_DWORD *)v28 + 1);
      *a4 = v28;
    }
    else
    {
      v20 = 8;
      ConnectionData = 8;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v19 = 146;
        goto LABEL_58;
      }
    }
    goto LABEL_59;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v19 = 142;
    v20 = ConnectionData;
    goto LABEL_58;
  }
LABEL_59:
  if ( v10 )
    LocalFree(v10);
  if ( v7 )
    LocalFree(v7);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v39);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v41);
  return ConnectionData;
}

```

## disassembly

```asm
0x18005f230  mov     rax, rsp
0x18005f233  mov     [rax+20h], r9
0x18005f237  mov     [rax+18h], r8
0x18005f23b  mov     [rax+10h], rdx
0x18005f23f  mov     [rax+8], ecx
0x18005f242  push    rbp
0x18005f243  push    rbx
0x18005f244  push    rsi
0x18005f245  push    rdi
0x18005f246  push    r12
0x18005f248  push    r13
0x18005f24a  push    r14
0x18005f24c  push    r15
0x18005f24e  mov     rbp, rsp
0x18005f251  sub     rsp, 78h
0x18005f255  mov     r15, rdx
0x18005f258  xor     r12d, r12d
0x18005f25b  mov     [rbp+Src], r12
0x18005f25f  mov     ebx, r12d
0x18005f262  mov     [rbp+var_18], rbx
0x18005f266  mov     [rbp+var_28], r12
0x18005f26a  mov     [rbp+var_20], r12
0x18005f26e  mov     r14d, r12d
0x18005f271  mov     [rbp+var_38], r12
0x18005f275  mov     r13d, r12d
0x18005f278  mov     [rbp+var_44], r12d
0x18005f27c  mov     [rbp+var_40], r12d
0x18005f280  mov     [r9], r12
0x18005f283  mov     [r8], r12d
0x18005f286  lea     r9, [rbp+Src]; struct _PEAP_CONN_PROPERTIES **
0x18005f28a  xor     r8d, r8d; unsigned int
0x18005f28d  xor     edx, edx; unsigned __int8 *
0x18005f28f  call    ?PeapReadConnectionData@@YAKKPEAEKPEAPEAU_PEAP_CONN_PROPERTIES@@@Z; PeapReadConnectionData(ulong,uchar *,ulong,_PEAP_CONN_PROPERTIES * *)
0x18005f294  mov     esi, eax
0x18005f296  mov     rdi, [rbp+Src]
0x18005f29a  test    eax, eax
0x18005f29c  jnz     loc_18005F5B1
0x18005f2a2  mov     al, r12b
0x18005f2a5  mov     [rbp+var_48], al
0x18005f2a8  mov     [rbp+var_47], r12b
0x18005f2ac  mov     [rbp+var_46], r12b
0x18005f2b0  cmp     r12d, [r15]
0x18005f2b3  jnb     loc_18005F368
0x18005f2b9  mov     r15d, r12d
0x18005f2bc  add     r15, r15
0x18005f2bf  mov     rdx, [rbp+arg_8]
0x18005f2c3  mov     rdx, [rdx+8]
0x18005f2c7  mov     ecx, [rdx+r15*8]
0x18005f2cb  lea     eax, [rcx-1]
0x18005f2ce  cmp     eax, 9
0x18005f2d1  ja      short loc_18005F33F
0x18005f2d3  sub     ecx, 2
0x18005f2d6  jz      short loc_18005F338
0x18005f2d8  sub     ecx, 1
0x18005f2db  jz      short loc_18005F332
0x18005f2dd  sub     ecx, 1
0x18005f2e0  jz      short loc_18005F32C
0x18005f2e2  cmp     ecx, 1
0x18005f2e5  jnz     short loc_18005F320
0x18005f2e7  mov     r15, [rdx+r15*8+8]
0x18005f2ec  cmp     rbx, r15
0x18005f2ef  jz      short loc_18005F320
0x18005f2f1  test    r15, r15
0x18005f2f4  jz      short loc_18005F305
0x18005f2f6  mov     rax, [r15]
0x18005f2f9  mov     rcx, r15
0x18005f2fc  mov     rax, [rax+8]
0x18005f300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f305  test    rbx, rbx
0x18005f308  jz      short loc_18005F319
0x18005f30a  mov     rax, [rbx]
0x18005f30d  mov     rcx, rbx
0x18005f310  mov     rax, [rax+10h]
0x18005f314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f319  mov     rbx, r15
0x18005f31c  mov     [rbp+var_18], rbx
0x18005f320  mov     al, [rbp+var_48]
0x18005f323  inc     r12d
0x18005f326  mov     r15, [rbp+arg_8]
0x18005f32a  jmp     short loc_18005F2B0
0x18005f32c  mov     [rbp+var_46], 1
0x18005f330  jmp     short loc_18005F320
0x18005f332  mov     [rbp+var_47], 1
0x18005f336  jmp     short loc_18005F320
0x18005f338  mov     al, 1
0x18005f33a  mov     [rbp+var_48], al
0x18005f33d  jmp     short loc_18005F323
0x18005f33f  mov     esi, 0Dh
0x18005f344  lea     rax, WPP_GLOBAL_Control
0x18005f34b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f352  cmp     rcx, rax
0x18005f355  jz      loc_18005F5DC
0x18005f35b  mov     edx, 8Dh
0x18005f360  mov     r9d, r12d
0x18005f363  jmp     loc_18005F5CC
0x18005f368  xor     r12d, r12d
0x18005f36b  cmp     [rbp+var_47], r12b
0x18005f36f  jz      short loc_18005F377
0x18005f371  or      dword ptr [rdi+0Ch], 8
0x18005f375  jmp     short loc_18005F37B
0x18005f377  and     dword ptr [rdi+0Ch], 0FFFFFFF7h
0x18005f37b  cmp     [rbp+var_46], r12b
0x18005f37f  jz      short loc_18005F387
0x18005f381  or      dword ptr [rdi+0Ch], 1
0x18005f385  jmp     short loc_18005F38B
0x18005f387  and     dword ptr [rdi+0Ch], 0FFFFFFFEh
0x18005f38b  test    al, al
0x18005f38d  jnz     short loc_18005F395
0x18005f38f  or      dword ptr [rdi+18h], 6
0x18005f393  jmp     short loc_18005F399
0x18005f395  and     dword ptr [rdi+18h], 0FFFFFFF9h
0x18005f399  test    rbx, rbx
0x18005f39c  jz      loc_18005F4B4
0x18005f3a2  mov     [rbp+var_10], r12
0x18005f3a6  mov     [rbp+Src], r12
0x18005f3aa  lea     r9, [rbp+Src]; unsigned __int16 **
0x18005f3ae  lea     r8, [rbp+var_10]; unsigned __int16 **
0x18005f3b2  lea     rdx, aXmlnsEaphostco; "xmlns:EapHostConfig='http://www.microso"...
0x18005f3b9  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18005f3bc  call    ?SetNsAndSchema@@YAJPEAUIXMLDOMDocument2@@PEBGPEAPEBG2KK@Z; SetNsAndSchema(IXMLDOMDocument2 *,ushort const *,ushort const * *,ushort const * *,ulong,ulong)
0x18005f3c1  mov     r9d, eax
0x18005f3c4  test    eax, eax
0x18005f3c6  jz      short loc_18005F40F
0x18005f3c8  mov     ecx, eax
0x18005f3ca  and     ecx, 1FFF0000h
0x18005f3d0  cmp     ecx, 70000h
0x18005f3d6  movzx   esi, r9w
0x18005f3da  jz      short loc_18005F3DE
0x18005f3dc  mov     esi, eax
0x18005f3de  lea     rax, WPP_GLOBAL_Control
0x18005f3e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f3ec  cmp     rcx, rax
0x18005f3ef  jz      loc_18005F5DC
0x18005f3f5  mov     edx, 8Fh
0x18005f3fa  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005f401  mov     rcx, [rcx+10h]
0x18005f405  call    WPP_SF_d
0x18005f40a  jmp     loc_18005F5DC
0x18005f40f  mov     rax, [rbx]
0x18005f412  lea     r8, [rbp+var_28]
0x18005f416  lea     rdx, IID_IXMLDOMNode
0x18005f41d  mov     rcx, rbx
0x18005f420  mov     rax, [rax]
0x18005f423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f428  mov     r9d, eax
0x18005f42b  test    eax, eax
0x18005f42d  jz      short loc_18005F44D
0x18005f42f  lea     rax, WPP_GLOBAL_Control
0x18005f436  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f43d  cmp     rcx, rax
0x18005f440  jz      loc_18005F5DC
0x18005f446  mov     edx, 90h
0x18005f44b  jmp     short loc_18005F3FA
0x18005f44d  lea     rax, [rbp+var_44]
0x18005f451  mov     [rsp+78h+var_50], rax; unsigned int *
0x18005f456  lea     rax, [rbp+var_38]
0x18005f45a  mov     [rsp+78h+var_58], rax; unsigned __int8 **
0x18005f45f  mov     r9, rdi; struct _PEAP_CONN_PROPERTIES *
0x18005f462  lea     r8, [rbp+var_40]; unsigned int *
0x18005f466  mov     edx, [rbp+arg_0]; unsigned int
0x18005f469  mov     rcx, [rbp+var_28]; struct IXMLDOMNode *
0x18005f46d  call    ?getInnerConnectionPropertiesFromDOMNode@@YAKPEAUIXMLDOMNode@@KPEAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEAE1@Z; getInnerConnectionPropertiesFromDOMNode(IXMLDOMNode *,ulong,ulong *,_PEAP_CONN_PROPERTIES *,uchar * *,ulong *)
0x18005f472  mov     esi, eax
0x18005f474  test    eax, eax
0x18005f476  jz      short loc_18005F4AC
0x18005f478  lea     rax, WPP_GLOBAL_Control
0x18005f47f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f486  cmp     rcx, rax
0x18005f489  jz      short loc_18005F4A3
0x18005f48b  mov     edx, 91h
0x18005f490  mov     r9d, esi
0x18005f493  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005f49a  mov     rcx, [rcx+10h]
0x18005f49e  call    WPP_SF_d
0x18005f4a3  mov     r14, [rbp+var_38]
0x18005f4a7  jmp     loc_18005F5DC
0x18005f4ac  mov     r14, [rbp+var_38]
0x18005f4b0  mov     r13d, [rbp+var_44]
0x18005f4b4  mov     r15d, [rdi+4]
0x18005f4b8  add     r15d, r13d
0x18005f4bb  mov     edx, r15d; uBytes
0x18005f4be  mov     ecx, 40h ; '@'; uFlags
0x18005f4c3  call    cs:__imp_LocalAlloc
0x18005f4c9  mov     rbx, rax
0x18005f4cc  test    rax, rax
0x18005f4cf  jnz     short loc_18005F4F9
0x18005f4d1  lea     r9d, [rax+8]
0x18005f4d5  mov     esi, r9d
0x18005f4d8  lea     rax, WPP_GLOBAL_Control
0x18005f4df  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f4e6  cmp     rcx, rax
0x18005f4e9  jz      loc_18005F5DC
0x18005f4ef  mov     edx, 92h
0x18005f4f4  jmp     loc_18005F5CC
0x18005f4f9  mov     r8d, [rdi+4]; Size
0x18005f4fd  mov     rdx, rdi; Src
0x18005f500  mov     rcx, rbx; void *
0x18005f503  call    memcpy_0
0x18005f508  mov     [rbx+4], r15d
0x18005f50c  test    r14, r14
0x18005f50f  jz      short loc_18005F577
0x18005f511  test    r13d, r13d
0x18005f514  jz      short loc_18005F577
0x18005f516  lea     rdx, [rbp+var_20]; struct _PEAP_ENTRY_CONN_PROPERTIES **
0x18005f51a  mov     rcx, rbx; struct _PEAP_CONN_PROPERTIES *
0x18005f51d  call    ?PeapGetFirstEntryConnProp@@YAKPEAU_PEAP_CONN_PROPERTIES@@PEAPEFAU_PEAP_ENTRY_CONN_PROPERTIES@@@Z; PeapGetFirstEntryConnProp(_PEAP_CONN_PROPERTIES *,_PEAP_ENTRY_CONN_PROPERTIES * *)
0x18005f522  mov     rcx, [rbp+var_20]
0x18005f526  mov     dword ptr [rcx], 1
0x18005f52c  mov     r15d, [rbp+var_40]
0x18005f530  mov     [rcx+8], r15d
0x18005f534  lea     eax, [r13+0Fh]
0x18005f538  mov     [rcx+4], eax
0x18005f53b  mov     r8d, r13d; Size
0x18005f53e  add     rcx, 0Ch; void *
0x18005f542  mov     rdx, r14; Src
0x18005f545  call    memcpy_0
0x18005f54a  lea     rax, WPP_GLOBAL_Control
0x18005f551  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f558  cmp     rcx, rax
0x18005f55b  jz      short loc_18005F59F
0x18005f55d  mov     edx, 93h
0x18005f562  mov     r9d, r15d
0x18005f565  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005f56c  mov     rcx, [rcx+10h]
0x18005f570  call    WPP_SF_d
0x18005f575  jmp     short loc_18005F59F
0x18005f577  lea     rax, WPP_GLOBAL_Control
0x18005f57e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f585  cmp     rcx, rax
0x18005f588  jz      short loc_18005F59F
0x18005f58a  mov     edx, 94h
0x18005f58f  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005f596  mov     rcx, [rcx+10h]
0x18005f59a  call    WPP_SF_
0x18005f59f  mov     eax, [rbx+4]
0x18005f5a2  mov     rcx, [rbp+arg_10]
0x18005f5a6  mov     [rcx], eax
0x18005f5a8  mov     rax, [rbp+arg_18]
0x18005f5ac  mov     [rax], rbx
0x18005f5af  jmp     short loc_18005F5DC
0x18005f5b1  lea     rax, WPP_GLOBAL_Control
0x18005f5b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f5bf  cmp     rcx, rax
0x18005f5c2  jz      short loc_18005F5DC
0x18005f5c4  mov     edx, 8Eh
0x18005f5c9  mov     r9d, esi
0x18005f5cc  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18005f5d3  mov     rcx, [rcx+10h]
0x18005f5d7  call    WPP_SF_d
0x18005f5dc  test    rdi, rdi
0x18005f5df  jz      short loc_18005F5EA
0x18005f5e1  mov     rcx, rdi; hMem
0x18005f5e4  call    cs:__imp_LocalFree
0x18005f5ea  test    r14, r14
0x18005f5ed  jz      short loc_18005F5F9
0x18005f5ef  mov     rcx, r14; hMem
0x18005f5f2  call    cs:__imp_LocalFree
0x18005f5f8  nop
0x18005f5f9  lea     rcx, [rbp+var_28]
0x18005f5fd  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18005f602  nop
0x18005f603  lea     rcx, [rbp+var_18]
0x18005f607  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18005f60c  mov     eax, esi
0x18005f60e  add     rsp, 78h
0x18005f612  pop     r15
0x18005f614  pop     r14
0x18005f616  pop     r13
0x18005f618  pop     r12
0x18005f61a  pop     rdi
0x18005f61b  pop     rsi
0x18005f61c  pop     rbx
0x18005f61d  pop     rbp
0x18005f61e  retn
```
