# CSyncMLCmdGet::BatchUpItemExecution(IConfigManager2 *,CSyncMLItem *)

- ea: `0x18000b560`
- end: `0x18000bc5e`
- name: `?BatchUpItemExecution@CSyncMLCmdGet@@EEAAJPEAUIConfigManager2@@PEAVCSyncMLItem@@@Z`
- size: `1790`
- prototype: `__int64 __fastcall(CSyncMLCmdGet *__hidden this, struct IConfigManager2 *, struct CSyncMLItem *)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callees

- `0x1800043a0`
- `0x1800046f0`
- `0x18000a760`
- `0x18000b560`
- `0x18000c600`
- `0x18000cfb0`
- `0x18000e020`
- `0x18000e1a0`
- `0x1800128a0`
- `0x180014330`
- `0x1800146e4`
- `0x180014c60`
- `0x180015c87`
- `0x18001d670`
- `0x180022210`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000bbc9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000bbc9`
- `OLEAUT32!__imp_VariantInit` at `0x18000b609`
- `OLEAUT32!__imp_VariantInit` at `0x18000b609`
- `OLEAUT32!__imp_VariantClear` at `0x18000bac5`
- `OLEAUT32!__imp_VariantClear` at `0x18000bac5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000baa0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bab1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000baa0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bab1`
- `DMCmnUtils!CopyString` at `0x18000b73d`
- `DMCmnUtils!CopyString` at `0x18000b73d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSyncMLCmdGet::BatchUpItemExecution(char **this, struct IConfigManager2 *a2, struct CSyncMLItem *a3)
{
  __int64 v6; // rcx
  __int64 v7; // r14
  unsigned __int16 *v8; // r15
  int NodeDataType; // esi
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int PropFromNode; // eax
  int v15; // ecx
  bool v16; // sf
  int PropertyResult; // eax
  __int64 v18; // rcx
  __int64 v19; // rax
  int i; // edx
  __int64 v21; // r8
  _QWORD *v22; // rax
  char *v23; // r12
  char *v24; // rcx
  char *v25; // rax
  __int64 v26; // r14
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // r15
  size_t v30; // r15
  char *v31; // rdi
  void *v32; // rax
  char *v33; // r8
  char *v34; // rdx
  char *v35; // rcx
  size_t v36; // r8
  char *v37; // rcx
  const struct std::nothrow_t *v38; // rdx
  char *v39; // rax
  struct CSyncMLItem **v40; // rbx
  struct CSyncMLItem **j; // rdi
  const struct std::nothrow_t *v42; // rdx
  void *v43; // rax
  OLECHAR *UserData; // [rsp+28h] [rbp-120h]
  int v46; // [rsp+40h] [rbp-108h] BYREF
  struct IConfigNode *v47; // [rsp+48h] [rbp-100h] BYREF
  int v48[2]; // [rsp+50h] [rbp-F8h] BYREF
  int v49; // [rsp+58h] [rbp-F0h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-E8h] BYREF
  int v51[4]; // [rsp+68h] [rbp-E0h] BYREF
  __int64 v52; // [rsp+78h] [rbp-D0h]
  unsigned __int16 *v53; // [rsp+80h] [rbp-C8h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+88h] [rbp-C0h] BYREF
  __int64 v55; // [rsp+98h] [rbp-B0h]
  __int128 v56; // [rsp+A0h] [rbp-A8h] BYREF
  __int64 v57; // [rsp+B0h] [rbp-98h]
  VARIANTARG pvarg; // [rsp+B8h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v59; // [rsp+D0h] [rbp-78h] BYREF
  char *v60; // [rsp+E0h] [rbp-68h]
  int v61; // [rsp+E8h] [rbp-60h]
  int v62; // [rsp+ECh] [rbp-5Ch]
  int *v63; // [rsp+F0h] [rbp-58h]
  __int64 v64; // [rsp+F8h] [rbp-50h]

  v49 = 0;
  v48[0] = 0;
  v6 = *((_QWORD *)a3 + 9);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  v7 = *((_QWORD *)a3 + 9);
  *(_QWORD *)&EventDescriptor.Id = v7;
  v57 = v7;
  v47 = 0;
  v46 = 1;
  v8 = 0;
  v53 = 0;
  hMem = 0;
  *(_OWORD *)v51 = 0;
  v52 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !v7 )
  {
    NodeDataType = -2102788095;
    goto LABEL_64;
  }
  NodeDataType = (*(__int64 (__fastcall **)(struct IConfigManager2 *, __int64, struct IConfigNode **))(*(_QWORD *)a2 + 88LL))(
                   a2,
                   v7,
                   &v47);
  if ( NodeDataType >= 0 )
  {
    NodeDataType = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v47 + 224LL))(v47, &v49);
    if ( NodeDataType >= 0 )
    {
      if ( !v49 )
      {
        NodeDataType = -2046820350;
        goto LABEL_63;
      }
      NodeDataType = GetNodeDataType(v47, (enum ConfigDataType *)&v46);
      if ( NodeDataType < 0 )
        goto LABEL_63;
      v10 = *((unsigned int *)a3 + 25);
      if ( (_DWORD)v10 == 15 )
      {
        v11 = *((unsigned int *)a3 + 26);
        if ( (_DWORD)v11 )
        {
          v12 = (unsigned int)(v11 - 1);
          if ( (_DWORD)v12 )
          {
            if ( (_DWORD)v12 != 1 )
              goto LABEL_33;
            if ( v46 == 8 )
            {
              NodeDataType = CSyncMLCmdGet::DoShallowGet((CSyncMLCmdGet *)this, v47, &v53);
              if ( NodeDataType < 0 )
                goto LABEL_63;
              v56 = CFGMGR_PROPERTY_SEMANTICTYPE;
              PropFromNode = CSyncMLCmdGet::GetPropFromNode(v13, v47, &v56, 6, &pvarg, &hMem);
              NodeDataType = PropFromNode;
              if ( PropFromNode == -2046820333 )
              {
                PropFromNode = CopyString(L"text/plain", 0xFFFFFFFF, (unsigned __int16 **)&hMem);
                NodeDataType = PropFromNode;
              }
              if ( PropFromNode < 0 )
                goto LABEL_63;
              if ( v53 )
                UserData = v53;
              else
                UserData = (OLECHAR *)&word_180032B28;
              NodeDataType = CSyncMLCmdGet::AppendResultItem(v15, (int)v51, v7, 8, (__int64)hMem, UserData, 0);
              v16 = NodeDataType < 0;
LABEL_32:
              if ( v16 )
                goto LABEL_63;
LABEL_33:
              v18 = *(_QWORD *)v51;
              v19 = (__int64)(*(_QWORD *)&v51[2] - *(_QWORD *)v51) >> 3;
              *(_QWORD *)&v56 = v19;
              for ( i = 0; ; ++i )
              {
                v46 = i;
                if ( i >= (int)v19 )
                  break;
                try
                {
                  v21 = 8LL * i;
                  v55 = v21;
                  v22 = (_QWORD *)(v18 + v21);
                  *(_QWORD *)v48 = v18 + v21;
                  v23 = this[22];
                  v24 = this[23];
                  if ( v23 == v24 )
                  {
                    v25 = this[21];
                    v26 = (v23 - v25) >> 3;
                    if ( v26 == 0x1FFFFFFFFFFFFFFFLL )
                      std::vector<CSyncMLCmd *>::_Xlength();
                    v27 = (v24 - v25) >> 3;
                    v28 = v27 >> 1;
                    if ( v27 > 0x1FFFFFFFFFFFFFFFLL - (v27 >> 1) )
LABEL_80:
                      std::_Throw_bad_array_new_length();
                    v29 = v26 + 1;
                    if ( v28 + v27 >= v26 + 1 )
                      v29 = v28 + v27;
                    if ( v29 > 0x1FFFFFFFFFFFFFFFLL )
                      std::_Throw_bad_array_new_length();
                    v30 = 8 * v29;
                    if ( v30 )
                    {
                      if ( v30 < 0x1000 )
                      {
                        v31 = (char *)operator new(v30);
                      }
                      else
                      {
                        if ( v30 + 39 < v30 )
                          goto LABEL_80;
                        v32 = operator new(v30 + 39);
                        if ( !v32 )
LABEL_57:
                          __fastfail(5u);
                        v31 = (char *)(((unsigned __int64)v32 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                        *((_QWORD *)v31 - 1) = v32;
                      }
                    }
                    else
                    {
                      v31 = 0;
                    }
                    *(_QWORD *)&v31[8 * v26] = **(_QWORD **)v48;
                    v33 = this[22];
                    v34 = this[21];
                    v35 = v31;
                    if ( v23 == v33 )
                    {
                      v36 = v33 - v34;
                    }
                    else
                    {
                      memmove_0(v31, v34, v23 - v34);
                      v36 = this[22] - v23;
                      v35 = &v31[8 * v26 + 8];
                      v34 = v23;
                    }
                    memmove_0(v35, v34, v36);
                    v37 = this[21];
                    if ( v37 )
                    {
                      v38 = (const struct std::nothrow_t *)(8 * ((this[23] - v37) >> 3));
                      if ( (unsigned __int64)v38 < 0x1000 )
                      {
                        v39 = this[21];
                      }
                      else
                      {
                        v39 = (char *)*((_QWORD *)v37 - 1);
                        if ( (unsigned __int64)(v37 - v39 - 8) > 0x1F )
                          goto LABEL_57;
                        v38 = (const struct std::nothrow_t *)((char *)v38 + 39);
                      }
                      operator delete(v39, v38);
                    }
                    this[21] = v31;
                    this[22] = &v31[8 * v26 + 8];
                    this[23] = &v31[v30];
                    i = v46;
                    v21 = v55;
                  }
                  else
                  {
                    *(_QWORD *)v23 = *v22;
                    this[22] += 8;
                  }
                }
                catch ( std::bad_alloc )
                {
                  v46 = -2147024882;
                  NodeDataType = -2147024882;
                  v7 = v57;
                  goto LABEL_63;
                }
                *(_QWORD *)(v21 + *(_QWORD *)v51) = 0;
                v18 = *(_QWORD *)v51;
                LODWORD(v19) = v56;
              }
              v7 = *(_QWORD *)&EventDescriptor.Id;
              goto LABEL_63;
            }
          }
          else
          {
            NodeDataType = CheckNodeInCSP(v47, L"./Vendor/MSFT/FileSystem", v48);
            if ( NodeDataType < 0 )
              goto LABEL_63;
            if ( v48[0] )
              goto LABEL_28;
            NodeDataType = CheckNodeInCSP(v47, L"./Vendor/MSFT/EnterpriseExtFileSystem", v48);
            if ( NodeDataType < 0 )
              goto LABEL_63;
            if ( v48[0] )
            {
LABEL_28:
              NodeDataType = -2147467263;
              goto LABEL_63;
            }
          }
          PropertyResult = CSyncMLCmdGet::DoRecursiveQuery(v12, (__int64)v51, (__int64)v47, 1);
        }
        else
        {
          PropertyResult = CSyncMLCmdGet::DoRecursiveQuery(v11, (__int64)v51, (__int64)v47, 0);
        }
      }
      else
      {
        PropertyResult = CSyncMLCmdGet::GetPropertyResult(v10, v51, v47, v7, v10, v46);
      }
      v16 = PropertyResult < 0;
      NodeDataType = PropertyResult;
      goto LABEL_32;
    }
  }
LABEL_63:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = v53;
LABEL_64:
  if ( v47 )
  {
    (*(void (__fastcall **)(struct IConfigNode *))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
  }
  LocalFree(v8);
  LocalFree(hMem);
  VariantClear(&pvarg);
  v40 = *(struct CSyncMLItem ***)&v51[2];
  for ( j = *(struct CSyncMLItem ***)v51; j != v40; ++j )
    CSyncMLItem::DeallocItem(*j);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v46 = NodeDataType;
    v63 = &v46;
    v64 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    v59.Ptr = (ULONGLONG)off_18003E050;
    v59.Size = (unsigned __int16)*off_18003E050;
    v59.Reserved = 2;
    v60 = byte_1800370BD;
    v61 = 33;
    v62 = 1;
    v48[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &v59);
  }
  if ( *(_QWORD *)v51 )
  {
    v42 = (const struct std::nothrow_t *)(8 * ((v52 - *(_QWORD *)v51) >> 3));
    if ( (unsigned __int64)v42 < 0x1000 )
    {
      v43 = *(void **)v51;
    }
    else
    {
      v43 = *(void **)(*(_QWORD *)v51 - 8LL);
      if ( (unsigned __int64)(*(_QWORD *)v51 - (_QWORD)v43 - 8LL) > 0x1F )
        __fastfail(5u);
      v42 = (const struct std::nothrow_t *)((char *)v42 + 39);
    }
    operator delete(v43, v42);
  }
  return (unsigned int)NodeDataType;
}

```

## disassembly

```asm
0x18000b560  push    rbx
0x18000b562  push    rsi
0x18000b563  push    rdi
0x18000b564  push    r12
0x18000b566  push    r13
0x18000b568  push    r14
0x18000b56a  push    r15
0x18000b56c  sub     rsp, 110h
0x18000b573  mov     rax, cs:__security_cookie
0x18000b57a  xor     rax, rsp
0x18000b57d  mov     [rsp+148h+var_48], rax
0x18000b585  mov     rdi, r8
0x18000b588  mov     rsi, rdx
0x18000b58b  mov     rbx, rcx
0x18000b58e  xor     r13d, r13d
0x18000b591  mov     [rsp+148h+var_F0], r13d
0x18000b596  mov     [rsp+148h+var_F8], r13d
0x18000b59b  mov     rcx, [r8+48h]
0x18000b59f  test    rcx, rcx
0x18000b5a2  jz      short loc_18000B5B0
0x18000b5a4  mov     rax, [rcx]
0x18000b5a7  mov     rax, [rax+8]
0x18000b5ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5b0  mov     r14, [rdi+48h]
0x18000b5b4  mov     qword ptr [rsp+148h+EventDescriptor.Id], r14
0x18000b5bc  mov     [rsp+148h+var_98], r14
0x18000b5c4  mov     [rsp+148h+var_100], r13
0x18000b5c9  mov     [rsp+148h+var_108], 1
0x18000b5d1  mov     r15, r13
0x18000b5d4  mov     [rsp+148h+var_C8], r13
0x18000b5dc  mov     [rsp+148h+hMem], r13
0x18000b5e1  xorps   xmm0, xmm0
0x18000b5e4  movdqu  xmmword ptr [rsp+148h+var_E0], xmm0
0x18000b5ea  mov     [rsp+148h+var_D0], r13
0x18000b5ef  xor     eax, eax
0x18000b5f1  movups  xmmword ptr [rsp+148h+pvarg], xmm0
0x18000b5f9  mov     qword ptr [rsp+148h+pvarg+10h], rax
0x18000b601  lea     rcx, [rsp+148h+pvarg]; pvarg
0x18000b609  call    cs:__imp_VariantInit
0x18000b610  nop     dword ptr [rax+rax+00h]
0x18000b615  test    r14, r14
0x18000b618  jnz     short loc_18000B624
0x18000b61a  mov     esi, 82AA0001h
0x18000b61f  jmp     loc_18000BA82
0x18000b624  mov     rax, [rsi]
0x18000b627  lea     r8, [rsp+148h+var_100]
0x18000b62c  mov     rdx, r14
0x18000b62f  mov     rcx, rsi
0x18000b632  mov     rax, [rax+58h]
0x18000b636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b63b  mov     esi, eax
0x18000b63d  test    eax, eax
0x18000b63f  js      loc_18000BA6B
0x18000b645  mov     rcx, [rsp+148h+var_100]
0x18000b64a  mov     rax, [rcx]
0x18000b64d  lea     rdx, [rsp+148h+var_F0]
0x18000b652  mov     rax, [rax+0E0h]
0x18000b659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b65e  mov     esi, eax
0x18000b660  test    eax, eax
0x18000b662  js      loc_18000BA6B
0x18000b668  cmp     [rsp+148h+var_F0], 0
0x18000b66d  jnz     short loc_18000B679
0x18000b66f  mov     esi, 86000002h
0x18000b674  jmp     loc_18000BA6B
0x18000b679  lea     rdx, [rsp+148h+var_108]; enum ConfigDataType *
0x18000b67e  mov     rcx, [rsp+148h+var_100]; struct IConfigNode *
0x18000b683  call    ?GetNodeDataType@@YAJPEAUIConfigNode@@PEAW4ConfigDataType@@@Z; GetNodeDataType(IConfigNode *,ConfigDataType *)
0x18000b688  mov     esi, eax
0x18000b68a  test    eax, eax
0x18000b68c  js      loc_18000BA6B
0x18000b692  mov     ecx, [rdi+64h]
0x18000b695  cmp     ecx, 0Fh
0x18000b698  jnz     loc_18000B821
0x18000b69e  mov     ecx, [rdi+68h]
0x18000b6a1  test    ecx, ecx
0x18000b6a3  jz      loc_18000B80D
0x18000b6a9  sub     ecx, 1
0x18000b6ac  jz      loc_18000B79E
0x18000b6b2  cmp     ecx, 1
0x18000b6b5  jnz     loc_18000B849
0x18000b6bb  cmp     [rsp+148h+var_108], 8
0x18000b6c0  jnz     loc_18000B7EC
0x18000b6c6  lea     r8, [rsp+148h+var_C8]; unsigned __int16 **
0x18000b6ce  mov     rdx, [rsp+148h+var_100]; struct IConfigNode *
0x18000b6d3  mov     rcx, rbx; this
0x18000b6d6  call    ?DoShallowGet@CSyncMLCmdGet@@AEBAJPEAUIConfigNode@@PEAPEAG@Z; CSyncMLCmdGet::DoShallowGet(IConfigNode *,ushort * *)
0x18000b6db  mov     esi, eax
0x18000b6dd  test    eax, eax
0x18000b6df  js      loc_18000BA6B
0x18000b6e5  movups  xmm0, cs:CFGMGR_PROPERTY_SEMANTICTYPE
0x18000b6ec  movaps  [rsp+148h+var_A8], xmm0
0x18000b6f4  lea     rax, [rsp+148h+hMem]
0x18000b6f9  mov     [rsp+148h+UserData], rax
0x18000b6fe  lea     rax, [rsp+148h+pvarg]
0x18000b706  mov     qword ptr [rsp+148h+UserDataCount], rax
0x18000b70b  mov     r9d, 6
0x18000b711  lea     r8, [rsp+148h+var_A8]
0x18000b719  mov     rdx, [rsp+148h+var_100]
0x18000b71e  call    ?GetPropFromNode@CSyncMLCmdGet@@AEBAJPEAUIConfigNode@@U_GUID@@W4SyncMLProp@@PEAUtagVARIANT@@PEAPEAG@Z; CSyncMLCmdGet::GetPropFromNode(IConfigNode *,_GUID,SyncMLProp,tagVARIANT *,ushort * *)
0x18000b723  mov     esi, eax
0x18000b725  cmp     eax, 86000013h
0x18000b72a  jnz     short loc_18000B74B
0x18000b72c  lea     r8, [rsp+148h+hMem]
0x18000b731  mov     edx, 0FFFFFFFFh
0x18000b736  lea     rcx, ?gc_szDefaultType@@3QBGB; "text/plain"
0x18000b73d  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18000b744  nop     dword ptr [rax+rax+00h]
0x18000b749  mov     esi, eax
0x18000b74b  test    eax, eax
0x18000b74d  js      loc_18000BA6B
0x18000b753  mov     r15, [rsp+148h+var_C8]
0x18000b75b  mov     [rsp+148h+var_118], r13d; int
0x18000b760  mov     r9d, 8; int
0x18000b766  mov     r8, r14; int
0x18000b769  lea     rdx, [rsp+148h+var_E0]; int
0x18000b76e  test    r15, r15
0x18000b771  jnz     short loc_18000B781
0x18000b773  lea     rax, word_180032B28
0x18000b77a  mov     [rsp+148h+UserData], rax
0x18000b77f  jmp     short loc_18000B786
0x18000b781  mov     [rsp+148h+UserData], r15; unsigned __int16 *
0x18000b786  mov     rax, [rsp+148h+hMem]
0x18000b78b  mov     qword ptr [rsp+148h+UserDataCount], rax; __int64
0x18000b790  call    ?AppendResultItem@CSyncMLCmdGet@@AEAAJAEAV?$vector@PEAVCSyncMLItem@@V?$allocator@PEAVCSyncMLItem@@@std@@@std@@PEAUIConfigManager2URI@@W4ConfigDataType@@PEBG3H@Z; CSyncMLCmdGet::AppendResultItem(std::vector<CSyncMLItem *> &,IConfigManager2URI *,ConfigDataType,ushort const *,ushort const *,int)
0x18000b795  mov     esi, eax
0x18000b797  test    eax, eax
0x18000b799  jmp     loc_18000B843
0x18000b79e  lea     r8, [rsp+148h+var_F8]; int *
0x18000b7a3  lea     rdx, ?gc_szFileSystemCSPPath@@3QBGB; "./Vendor/MSFT/FileSystem"
0x18000b7aa  mov     rcx, [rsp+148h+var_100]; struct IConfigNode *
0x18000b7af  call    ?CheckNodeInCSP@@YAJPEAUIConfigNode@@PEBGPEAH@Z; CheckNodeInCSP(IConfigNode *,ushort const *,int *)
0x18000b7b4  mov     esi, eax
0x18000b7b6  test    eax, eax
0x18000b7b8  js      loc_18000BA6B
0x18000b7be  cmp     [rsp+148h+var_F8], 0
0x18000b7c3  jnz     short loc_18000B803
0x18000b7c5  lea     r8, [rsp+148h+var_F8]; int *
0x18000b7ca  lea     rdx, ?gc_szEnterpriseExtFileSystemCSPPath@@3QBGB; "./Vendor/MSFT/EnterpriseExtFileSystem"
0x18000b7d1  mov     rcx, [rsp+148h+var_100]; struct IConfigNode *
0x18000b7d6  call    ?CheckNodeInCSP@@YAJPEAUIConfigNode@@PEBGPEAH@Z; CheckNodeInCSP(IConfigNode *,ushort const *,int *)
0x18000b7db  mov     esi, eax
0x18000b7dd  test    eax, eax
0x18000b7df  js      loc_18000BA6B
0x18000b7e5  cmp     [rsp+148h+var_F8], 0
0x18000b7ea  jnz     short loc_18000B803
0x18000b7ec  mov     r9d, 1
0x18000b7f2  mov     r8, [rsp+148h+var_100]
0x18000b7f7  lea     rdx, [rsp+148h+var_E0]
0x18000b7fc  call    ?DoRecursiveQuery@CSyncMLCmdGet@@AEAAJAEAV?$vector@PEAVCSyncMLItem@@V?$allocator@PEAVCSyncMLItem@@@std@@@std@@PEAUIConfigNode@@H@Z; CSyncMLCmdGet::DoRecursiveQuery(std::vector<CSyncMLItem *> &,IConfigNode *,int)
0x18000b801  jmp     short loc_18000B83F
0x18000b803  mov     esi, 80004001h
0x18000b808  jmp     loc_18000BA6B
0x18000b80d  xor     r9d, r9d
0x18000b810  mov     r8, [rsp+148h+var_100]
0x18000b815  lea     rdx, [rsp+148h+var_E0]
0x18000b81a  call    ?DoRecursiveQuery@CSyncMLCmdGet@@AEAAJAEAV?$vector@PEAVCSyncMLItem@@V?$allocator@PEAVCSyncMLItem@@@std@@@std@@PEAUIConfigNode@@H@Z; CSyncMLCmdGet::DoRecursiveQuery(std::vector<CSyncMLItem *> &,IConfigNode *,int)
0x18000b81f  jmp     short loc_18000B83F
0x18000b821  mov     eax, [rsp+148h+var_108]
0x18000b825  mov     dword ptr [rsp+148h+UserData], eax
0x18000b829  mov     [rsp+148h+UserDataCount], ecx
0x18000b82d  mov     r9, r14
0x18000b830  mov     r8, [rsp+148h+var_100]
0x18000b835  lea     rdx, [rsp+148h+var_E0]
0x18000b83a  call    ?GetPropertyResult@CSyncMLCmdGet@@AEAAJAEAV?$vector@PEAVCSyncMLItem@@V?$allocator@PEAVCSyncMLItem@@@std@@@std@@PEAUIConfigNode@@PEAUIConfigManager2URI@@W4SyncMLProp@@W4ConfigDataType@@@Z; CSyncMLCmdGet::GetPropertyResult(std::vector<CSyncMLItem *> &,IConfigNode *,IConfigManager2URI *,SyncMLProp,ConfigDataType)
0x18000b83f  test    eax, eax
0x18000b841  mov     esi, eax
0x18000b843  js      loc_18000BA6B
0x18000b849  mov     rax, qword ptr [rsp+148h+var_E0+8]
0x18000b84e  mov     rcx, qword ptr [rsp+148h+var_E0]
0x18000b853  sub     rax, rcx
0x18000b856  sar     rax, 3
0x18000b85a  mov     qword ptr [rsp+148h+var_A8], rax
0x18000b862  mov     edx, r13d
0x18000b865  mov     r9, 1FFFFFFFFFFFFFFFh
0x18000b86f  mov     [rsp+148h+var_108], edx
0x18000b873  cmp     edx, eax
0x18000b875  jge     loc_18000BA63
0x18000b87b  movsxd  rax, edx
0x18000b87e  lea     r8, ds:0[rax*8]
0x18000b886  mov     [rsp+148h+var_B0], r8
0x18000b88e  lea     rax, [rcx+r8]
0x18000b892  mov     qword ptr [rsp+148h+var_F8], rax
0x18000b897  mov     r12, [rbx+0B0h]
0x18000b89e  mov     rcx, [rbx+0B8h]
0x18000b8a5  cmp     r12, rcx
0x18000b8a8  jz      short loc_18000B8BE
0x18000b8aa  mov     rax, [rax]
0x18000b8ad  mov     [r12], rax
0x18000b8b1  add     qword ptr [rbx+0B0h], 8
0x18000b8b9  jmp     loc_18000BA35
0x18000b8be  mov     rax, [rbx+0A8h]
0x18000b8c5  mov     r14, r12
0x18000b8c8  sub     r14, rax
0x18000b8cb  sar     r14, 3
0x18000b8cf  cmp     r14, r9
0x18000b8d2  jz      loc_18000BC4C
0x18000b8d8  sub     rcx, rax
0x18000b8db  sar     rcx, 3
0x18000b8df  mov     rdx, rcx
0x18000b8e2  shr     rdx, 1
0x18000b8e5  mov     rax, r9
0x18000b8e8  sub     rax, rdx
0x18000b8eb  cmp     rcx, rax
0x18000b8ee  ja      loc_18000BC57
0x18000b8f4  lea     r8, [r14+1]
0x18000b8f8  lea     rax, [rdx+rcx]
0x18000b8fc  mov     r15, r8
0x18000b8ff  cmp     rax, r8
0x18000b902  cmovnb  r15, rax
0x18000b906  cmp     r15, r9
0x18000b909  ja      loc_18000BC52
0x18000b90f  lea     r15, ds:0[r15*8]
0x18000b917  test    r15, r15
0x18000b91a  jnz     short loc_18000B921
0x18000b91c  mov     rdi, r13
0x18000b91f  jmp     short loc_18000B95E
0x18000b921  cmp     r15, 1000h
0x18000b928  jb      short loc_18000B953
0x18000b92a  lea     rcx, [r15+27h]; Size
0x18000b92e  cmp     rcx, r15
0x18000b931  jbe     loc_18000BC57
0x18000b937  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b93c  test    rax, rax
0x18000b93f  jz      loc_18000B9EC
0x18000b945  lea     rdi, [rax+27h]
0x18000b949  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18000b94d  mov     [rdi-8], rax
0x18000b951  jmp     short loc_18000B95E
0x18000b953  mov     rcx, r15; Size
0x18000b956  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b95b  mov     rdi, rax
0x18000b95e  mov     rcx, qword ptr [rsp+148h+var_F8]
0x18000b963  mov     rcx, [rcx]
0x18000b966  mov     [rdi+r14*8], rcx
0x18000b96a  mov     r8, [rbx+0B0h]
0x18000b971  mov     rdx, [rbx+0A8h]; Src
0x18000b978  mov     rcx, rdi; void *
0x18000b97b  cmp     r12, r8
0x18000b97e  jnz     short loc_18000B985
0x18000b980  sub     r8, rdx
0x18000b983  jmp     short loc_18000B9A5
0x18000b985  mov     r8, r12
0x18000b988  sub     r8, rdx; Size
0x18000b98b  call    memmove_0
0x18000b990  mov     r8, [rbx+0B0h]
0x18000b997  sub     r8, r12; Size
0x18000b99a  lea     rcx, [r14+1]
0x18000b99e  lea     rcx, [rdi+rcx*8]; void *
0x18000b9a2  mov     rdx, r12; Src
0x18000b9a5  call    memmove_0
0x18000b9aa  mov     rcx, [rbx+0A8h]
0x18000b9b1  test    rcx, rcx
0x18000b9b4  jz      short loc_18000B9FE
0x18000b9b6  mov     rax, [rbx+0B8h]
0x18000b9bd  sub     rax, rcx
0x18000b9c0  sar     rax, 3
0x18000b9c4  lea     rdx, ds:0[rax*8]; struct std::nothrow_t *
0x18000b9cc  cmp     rdx, 1000h
0x18000b9d3  jb      short loc_18000B9F3
0x18000b9d5  mov     rax, [rcx-8]
0x18000b9d9  sub     rcx, rax
0x18000b9dc  sub     rcx, 8
0x18000b9e0  cmp     rcx, 1Fh
0x18000b9e4  ja      short loc_18000B9EC
0x18000b9e6  add     rdx, 27h ; '''
0x18000b9ea  jmp     short loc_18000B9F6
0x18000b9ec  mov     ecx, 5
0x18000b9f1  int     29h; Win8: RtlFailFast(ecx)
0x18000b9f3  mov     rax, rcx
0x18000b9f6  mov     rcx, rax; void *
0x18000b9f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b9fe  mov     [rbx+0A8h], rdi
0x18000ba05  lea     rax, [r14+1]
0x18000ba09  lea     rax, [rdi+rax*8]
0x18000ba0d  mov     [rbx+0B0h], rax
0x18000ba14  lea     rax, [r15+rdi]
0x18000ba18  mov     [rbx+0B8h], rax
0x18000ba1f  mov     edx, [rsp+148h+var_108]
0x18000ba23  mov     r8, [rsp+148h+var_B0]
0x18000ba2b  mov     r9, 1FFFFFFFFFFFFFFFh
0x18000ba35  mov     rax, qword ptr [rsp+148h+var_E0]
0x18000ba3a  mov     [r8+rax], r13
0x18000ba3e  inc     edx
0x18000ba40  mov     rcx, qword ptr [rsp+148h+var_E0]
0x18000ba45  mov     rax, qword ptr [rsp+148h+var_A8]
0x18000ba4d  jmp     loc_18000B86F
0x18000ba52  xor     r13d, r13d
0x18000ba55  mov     esi, [rsp+148h+var_108]
0x18000ba59  mov     r14, [rsp+148h+var_98]
0x18000ba61  jmp     short loc_18000BA6B
0x18000ba63  mov     r14, qword ptr [rsp+148h+EventDescriptor.Id]
0x18000ba6b  mov     rax, [r14]
0x18000ba6e  mov     rcx, r14
0x18000ba71  mov     rax, [rax+10h]
0x18000ba75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba7a  mov     r15, [rsp+148h+var_C8]
0x18000ba82  mov     rcx, [rsp+148h+var_100]
0x18000ba87  test    rcx, rcx
0x18000ba8a  jz      short loc_18000BA9D
  ... truncated ...
```
