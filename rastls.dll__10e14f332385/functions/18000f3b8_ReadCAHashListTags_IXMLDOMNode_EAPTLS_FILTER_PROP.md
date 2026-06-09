# ReadCAHashListTags(IXMLDOMNode *,_EAPTLS_FILTER_PROP *)

- ea: `0x18000f3b8`
- end: `0x18000f680`
- name: `?ReadCAHashListTags@@YAKPEAUIXMLDOMNode@@PEAU_EAPTLS_FILTER_PROP@@@Z`
- size: `712`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, struct _EAPTLS_FILTER_PROP *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f750`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18000f0c0`
- `0x18000f350`
- `0x18000f3b8`
- `0x180010d2c`
- `0x1800160c0`
- `0x180035680`
- `0x18003623c`
- `0x18005e7c8`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4f0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f4d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f4d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f5a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f5a4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f450`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f450`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f496`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f5bb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f619`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f626`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f496`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f5bb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f619`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f626`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ReadCAHashListTags(struct IXMLDOMNode *a1, struct _EAPTLS_FILTER_PROP *a2)
{
  BSTR v4; // rax
  int v5; // ecx
  OLECHAR *v6; // rbx
  unsigned int v7; // ebx
  _QWORD *v8; // r14
  DWORD LastError; // eax
  unsigned __int16 v10; // di
  int BytesFromHex; // eax
  __int64 v12; // rdx
  __int64 v14; // [rsp+20h] [rbp-50h] BYREF
  int v15; // [rsp+28h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+30h] [rbp-40h] BYREF
  __int64 v17; // [rsp+38h] [rbp-38h] BYREF
  void *Src; // [rsp+40h] [rbp-30h] BYREF
  int v19[2]; // [rsp+48h] [rbp-28h] BYREF
  __int128 v20; // [rsp+50h] [rbp-20h] BYREF
  __int64 v21; // [rsp+60h] [rbp-10h]

  v14 = 0;
  v17 = 0;
  v19[0] = 0;
  v15 = 0;
  Src = 0;
  bstrString = 0;
  if ( !GetAttributeValueFromNode(a1, L"Enabled", 0, v19) && v19[0] )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 188, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids);
    *(_WORD *)a2 |= 1u;
  }
  v4 = SysAllocString(L"eaptlsconnectionpropertiesv3:IssuerHash");
  v6 = v4;
  *(_QWORD *)v19 = v4;
  if ( !v4 )
    ATL::AtlThrowImpl(v5);
  if ( ((unsigned int (__fastcall *)(struct IXMLDOMNode *, BSTR, __int64 *))a1->lpVtbl->selectNodes)(a1, v4, &v14)
    || !v14 )
  {
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        254,
        WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids,
        L"eaptlsconnectionpropertiesv3:IssuerHash");
    SysFreeString(v6);
    v7 = 0;
  }
  else
  {
    SysFreeString(v6);
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v14 + 64LL))(v14, &v15);
    v7 = 0;
    if ( v15 > 0 )
    {
      v20 = 0;
      v21 = 0;
      v8 = LocalAlloc(0x40u, 24LL * v15);
      if ( v8 )
      {
        v10 = 0;
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 72LL))(v14, &v17);
        v7 = 0;
        while ( v17 )
        {
          (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v17 + 208LL))(v17, &bstrString);
          BytesFromHex = getBytesFromHex(bstrString, (unsigned __int8 **)&Src);
          if ( (unsigned int)(BytesFromHex - 1) <= 0x13 )
          {
            LODWORD(v20) = BytesFromHex;
            memcpy_0((char *)&v20 + 4, Src, BytesFromHex);
            v12 = 3LL * v10;
            *(_OWORD *)&v8[v12] = v20;
            v8[v12 + 2] = v21;
            ++v10;
          }
          LocalFree(Src);
          Src = 0;
          ATL::CComPtrBase<IXMLDOMNode>::Release(&v17);
          SysFreeString(bstrString);
          bstrString = 0;
          (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v14 + 72LL))(v14, &v17);
        }
        *((_WORD *)a2 + 1) = v10;
        if ( v10 )
          *((_QWORD *)a2 + 1) = v8;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          LastError = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, LastError);
        }
        v7 = 14;
      }
    }
  }
  SysFreeString(bstrString);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  return v7;
}

```

## disassembly

```asm
0x18000f3b8  mov     [rsp-28h+arg_10], rbx
0x18000f3bd  mov     [rsp-28h+arg_18], rsi
0x18000f3c2  push    rbp
0x18000f3c3  push    rdi
0x18000f3c4  push    r12
0x18000f3c6  push    r14
0x18000f3c8  push    r15
0x18000f3ca  mov     rbp, rsp
0x18000f3cd  sub     rsp, 70h
0x18000f3d1  mov     rax, cs:__security_cookie
0x18000f3d8  xor     rax, rsp
0x18000f3db  mov     [rbp+var_8], rax
0x18000f3df  mov     rsi, rdx
0x18000f3e2  mov     rdi, rcx
0x18000f3e5  xor     r15d, r15d
0x18000f3e8  mov     [rbp+var_50], r15
0x18000f3ec  mov     [rbp+var_38], r15
0x18000f3f0  mov     [rbp+var_28], r15d
0x18000f3f4  mov     [rbp+var_48], r15d
0x18000f3f8  mov     [rbp+Src], r15
0x18000f3fc  mov     [rbp+bstrString], r15
0x18000f400  lea     r9, [rbp+var_28]; int *
0x18000f404  xor     r8d, r8d; int
0x18000f407  lea     rdx, aEnabled; "Enabled"
0x18000f40e  call    ?GetAttributeValueFromNode@@YAJPEAUIXMLDOMNode@@PEAGHPEAH@Z; GetAttributeValueFromNode(IXMLDOMNode *,ushort *,int,int *)
0x18000f413  lea     r12, WPP_GLOBAL_Control
0x18000f41a  test    eax, eax
0x18000f41c  jnz     short loc_18000F449
0x18000f41e  cmp     [rbp+var_28], r15d
0x18000f422  jz      short loc_18000F449
0x18000f424  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f42b  cmp     rcx, r12
0x18000f42e  jz      short loc_18000F445
0x18000f430  mov     edx, 0BCh
0x18000f435  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000f43c  mov     rcx, [rcx+10h]
0x18000f440  call    WPP_SF_
0x18000f445  or      word ptr [rsi], 1
0x18000f449  lea     rcx, aEaptlsconnecti; "eaptlsconnectionpropertiesv3:IssuerHash"
0x18000f450  call    cs:__imp_SysAllocString
0x18000f456  mov     rbx, rax
0x18000f459  mov     qword ptr [rbp+var_28], rax
0x18000f45d  test    rax, rax
0x18000f460  jnz     short loc_18000F468
0x18000f462  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000f468  mov     rax, [rdi]
0x18000f46b  lea     r8, [rbp+var_50]
0x18000f46f  mov     rdx, rbx
0x18000f472  mov     rcx, rdi
0x18000f475  mov     rax, [rax+120h]
0x18000f47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f481  test    eax, eax
0x18000f483  jnz     loc_18000F5ED
0x18000f489  cmp     [rbp+var_50], r15
0x18000f48d  jz      loc_18000F5ED
0x18000f493  mov     rcx, rbx; bstrString
0x18000f496  call    cs:__imp_SysFreeString
0x18000f49c  mov     rcx, [rbp+var_50]
0x18000f4a0  mov     rax, [rcx]
0x18000f4a3  lea     rdx, [rbp+var_48]
0x18000f4a7  mov     rax, [rax+40h]
0x18000f4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4b0  mov     ebx, r15d
0x18000f4b3  movsxd  rax, [rbp+var_48]
0x18000f4b7  test    eax, eax
0x18000f4b9  jle     loc_18000F622
0x18000f4bf  xorps   xmm0, xmm0
0x18000f4c2  xor     ecx, ecx
0x18000f4c4  movups  [rbp+var_20], xmm0
0x18000f4c8  mov     [rbp+var_10], rcx
0x18000f4cc  lea     rdx, [rax+rax*2]
0x18000f4d0  shl     rdx, 3; uBytes
0x18000f4d4  mov     ecx, 40h ; '@'; uFlags
0x18000f4d9  call    cs:__imp_LocalAlloc
0x18000f4df  mov     r14, rax
0x18000f4e2  test    rax, rax
0x18000f4e5  jnz     short loc_18000F51F
0x18000f4e7  cmp     cs:WPP_GLOBAL_Control, r12
0x18000f4ee  jz      short loc_18000F515
0x18000f4f0  call    cs:__imp_GetLastError
0x18000f4f6  mov     edx, 0BDh
0x18000f4fb  mov     r9d, eax
0x18000f4fe  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000f505  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f50c  mov     rcx, [rcx+10h]
0x18000f510  call    WPP_SF_d
0x18000f515  mov     ebx, 0Eh
0x18000f51a  jmp     loc_18000F622
0x18000f51f  mov     edi, r15d
0x18000f522  mov     rcx, [rbp+var_50]
0x18000f526  mov     rax, [rcx]
0x18000f529  lea     rdx, [rbp+var_38]
0x18000f52d  mov     rax, [rax+48h]
0x18000f531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f536  mov     ebx, r15d
0x18000f539  mov     rcx, [rbp+var_38]
0x18000f53d  test    rcx, rcx
0x18000f540  jz      loc_18000F5DE
0x18000f546  mov     rax, [rcx]
0x18000f549  lea     rdx, [rbp+bstrString]
0x18000f54d  mov     rax, [rax+0D0h]
0x18000f554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f559  lea     rdx, [rbp+Src]; unsigned __int8 **
0x18000f55d  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x18000f561  call    ?getBytesFromHex@@YAJPEAGPEAPEAE@Z; getBytesFromHex(ushort *,uchar * *)
0x18000f566  lea     ecx, [rax-1]
0x18000f569  cmp     ecx, 13h
0x18000f56c  ja      short loc_18000F5A0
0x18000f56e  mov     dword ptr [rbp+var_20], eax
0x18000f571  movsxd  r8, eax; Size
0x18000f574  mov     rdx, [rbp+Src]; Src
0x18000f578  lea     rcx, [rbp+var_20+4]; void *
0x18000f57c  call    memcpy_0
0x18000f581  movzx   eax, di
0x18000f584  lea     rdx, [rax+rax*2]
0x18000f588  movups  xmm0, [rbp+var_20]
0x18000f58c  movups  xmmword ptr [r14+rdx*8], xmm0
0x18000f591  movsd   xmm1, [rbp+var_10]
0x18000f596  movsd   qword ptr [r14+rdx*8+10h], xmm1
0x18000f59d  inc     di
0x18000f5a0  mov     rcx, [rbp+Src]; hMem
0x18000f5a4  call    cs:__imp_LocalFree
0x18000f5aa  mov     [rbp+Src], r15
0x18000f5ae  lea     rcx, [rbp+var_38]
0x18000f5b2  call    ?Release@?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMNode>::Release(void)
0x18000f5b7  mov     rcx, [rbp+bstrString]; bstrString
0x18000f5bb  call    cs:__imp_SysFreeString
0x18000f5c1  mov     [rbp+bstrString], r15
0x18000f5c5  mov     rcx, [rbp+var_50]
0x18000f5c9  mov     rax, [rcx]
0x18000f5cc  lea     rdx, [rbp+var_38]
0x18000f5d0  mov     rax, [rax+48h]
0x18000f5d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5d9  jmp     loc_18000F539
0x18000f5de  mov     [rsi+2], di
0x18000f5e2  test    di, di
0x18000f5e5  jz      short loc_18000F622
0x18000f5e7  mov     [rsi+8], r14
0x18000f5eb  jmp     short loc_18000F622
0x18000f5ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5f4  cmp     rcx, r12
0x18000f5f7  jz      short loc_18000F616
0x18000f5f9  mov     edx, 0FEh
0x18000f5fe  lea     r9, aEaptlsconnecti; "eaptlsconnectionpropertiesv3:IssuerHash"
0x18000f605  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000f60c  mov     rcx, [rcx+10h]
0x18000f610  call    WPP_SF_S
0x18000f615  nop
0x18000f616  mov     rcx, rbx; bstrString
0x18000f619  call    cs:__imp_SysFreeString
0x18000f61f  mov     ebx, r15d
0x18000f622  mov     rcx, [rbp+bstrString]; bstrString
0x18000f626  call    cs:__imp_SysFreeString
0x18000f62c  nop
0x18000f62d  mov     rcx, [rbp+var_38]
0x18000f631  test    rcx, rcx
0x18000f634  jz      short loc_18000F643
0x18000f636  mov     rax, [rcx]
0x18000f639  mov     rax, [rax+10h]
0x18000f63d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f642  nop
0x18000f643  mov     rcx, [rbp+var_50]
0x18000f647  test    rcx, rcx
0x18000f64a  jz      short loc_18000F659
0x18000f64c  mov     rdx, [rcx]
0x18000f64f  mov     rax, [rdx+10h]
0x18000f653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f658  nop
0x18000f659  mov     eax, ebx
0x18000f65b  mov     rcx, [rbp+var_8]
0x18000f65f  xor     rcx, rsp; StackCookie
0x18000f662  call    __security_check_cookie
0x18000f667  lea     r11, [rsp+70h+var_s0]
0x18000f66c  mov     rbx, [r11+40h]
0x18000f670  mov     rsi, [r11+48h]
0x18000f674  mov     rsp, r11
0x18000f677  pop     r15
0x18000f679  pop     r14
0x18000f67b  pop     r12
0x18000f67d  pop     rdi
0x18000f67e  pop     rbp
0x18000f67f  retn
```
