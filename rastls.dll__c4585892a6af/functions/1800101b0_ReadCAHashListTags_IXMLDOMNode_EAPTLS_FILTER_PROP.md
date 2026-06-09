# ReadCAHashListTags(IXMLDOMNode *,_EAPTLS_FILTER_PROP *)

- ea: `0x1800101b0`
- end: `0x1800104a9`
- name: `?ReadCAHashListTags@@YAKPEAUIXMLDOMNode@@PEAU_EAPTLS_FILTER_PROP@@@Z`
- size: `761`
- prototype: `unsigned int __fastcall(struct IXMLDOMNode *, struct _EAPTLS_FILTER_PROP *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010580`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18000fe90`
- `0x180010140`
- `0x1800101b0`
- `0x180011d48`
- `0x1800176f0`
- `0x180038270`
- `0x180038e4c`
- `0x180061f9c`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800102dd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800102dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800103b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800103b4`
- `OLEAUT32!__imp_SysAllocString` at `0x180010248`
- `OLEAUT32!__imp_SysAllocString` at `0x180010248`
- `OLEAUT32!__imp_SysFreeString` at `0x180010294`
- `OLEAUT32!__imp_SysFreeString` at `0x1800103d1`
- `OLEAUT32!__imp_SysFreeString` at `0x180010435`
- `OLEAUT32!__imp_SysFreeString` at `0x180010448`
- `OLEAUT32!__imp_SysFreeString` at `0x180010294`
- `OLEAUT32!__imp_SysFreeString` at `0x1800103d1`
- `OLEAUT32!__imp_SysFreeString` at `0x180010435`
- `OLEAUT32!__imp_SysFreeString` at `0x180010448`

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
0x1800101b0  mov     [rsp-28h+arg_10], rbx
0x1800101b5  mov     [rsp-28h+arg_18], rsi
0x1800101ba  push    rbp
0x1800101bb  push    rdi
0x1800101bc  push    r12
0x1800101be  push    r14
0x1800101c0  push    r15
0x1800101c2  mov     rbp, rsp
0x1800101c5  sub     rsp, 70h
0x1800101c9  mov     rax, cs:__security_cookie
0x1800101d0  xor     rax, rsp
0x1800101d3  mov     [rbp+var_8], rax
0x1800101d7  mov     rsi, rdx
0x1800101da  mov     rdi, rcx
0x1800101dd  xor     r15d, r15d
0x1800101e0  mov     [rbp+var_50], r15
0x1800101e4  mov     [rbp+var_38], r15
0x1800101e8  mov     [rbp+var_28], r15d
0x1800101ec  mov     [rbp+var_48], r15d
0x1800101f0  mov     [rbp+Src], r15
0x1800101f4  mov     [rbp+bstrString], r15
0x1800101f8  lea     r9, [rbp+var_28]; int *
0x1800101fc  xor     r8d, r8d; int
0x1800101ff  lea     rdx, aEnabled; "Enabled"
0x180010206  call    ?GetAttributeValueFromNode@@YAJPEAUIXMLDOMNode@@PEAGHPEAH@Z; GetAttributeValueFromNode(IXMLDOMNode *,ushort *,int,int *)
0x18001020b  lea     r12, WPP_GLOBAL_Control
0x180010212  test    eax, eax
0x180010214  jnz     short loc_180010241
0x180010216  cmp     [rbp+var_28], r15d
0x18001021a  jz      short loc_180010241
0x18001021c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010223  cmp     rcx, r12
0x180010226  jz      short loc_18001023D
0x180010228  mov     edx, 0BCh
0x18001022d  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180010234  mov     rcx, [rcx+10h]
0x180010238  call    WPP_SF_
0x18001023d  or      word ptr [rsi], 1
0x180010241  lea     rcx, aEaptlsconnecti; "eaptlsconnectionpropertiesv3:IssuerHash"
0x180010248  call    cs:__imp_SysAllocString
0x18001024f  nop     dword ptr [rax+rax+00h]
0x180010254  mov     rbx, rax
0x180010257  mov     qword ptr [rbp+var_28], rax
0x18001025b  test    rax, rax
0x18001025e  jnz     short loc_180010266
0x180010260  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010266  mov     rax, [rdi]
0x180010269  lea     r8, [rbp+var_50]
0x18001026d  mov     rdx, rbx
0x180010270  mov     rcx, rdi
0x180010273  mov     rax, [rax+120h]
0x18001027a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001027f  test    eax, eax
0x180010281  jnz     loc_180010409
0x180010287  cmp     [rbp+var_50], r15
0x18001028b  jz      loc_180010409
0x180010291  mov     rcx, rbx; bstrString
0x180010294  call    cs:__imp_SysFreeString
0x18001029b  nop     dword ptr [rax+rax+00h]
0x1800102a0  mov     rcx, [rbp+var_50]
0x1800102a4  mov     rax, [rcx]
0x1800102a7  lea     rdx, [rbp+var_48]
0x1800102ab  mov     rax, [rax+40h]
0x1800102af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102b4  mov     ebx, r15d
0x1800102b7  movsxd  rax, [rbp+var_48]
0x1800102bb  test    eax, eax
0x1800102bd  jle     loc_180010444
0x1800102c3  xorps   xmm0, xmm0
0x1800102c6  xor     ecx, ecx
0x1800102c8  movups  [rbp+var_20], xmm0
0x1800102cc  mov     [rbp+var_10], rcx
0x1800102d0  lea     rdx, [rax+rax*2]
0x1800102d4  shl     rdx, 3; uBytes
0x1800102d8  mov     ecx, 40h ; '@'; uFlags
0x1800102dd  call    cs:__imp_LocalAlloc
0x1800102e4  nop     dword ptr [rax+rax+00h]
0x1800102e9  mov     r14, rax
0x1800102ec  test    rax, rax
0x1800102ef  jnz     short loc_18001032F
0x1800102f1  cmp     cs:WPP_GLOBAL_Control, r12
0x1800102f8  jz      short loc_180010325
0x1800102fa  call    cs:__imp_GetLastError
0x180010301  nop     dword ptr [rax+rax+00h]
0x180010306  mov     edx, 0BDh
0x18001030b  mov     r9d, eax
0x18001030e  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180010315  mov     rcx, cs:WPP_GLOBAL_Control
0x18001031c  mov     rcx, [rcx+10h]
0x180010320  call    WPP_SF_d
0x180010325  mov     ebx, 0Eh
0x18001032a  jmp     loc_180010444
0x18001032f  mov     edi, r15d
0x180010332  mov     rcx, [rbp+var_50]
0x180010336  mov     rax, [rcx]
0x180010339  lea     rdx, [rbp+var_38]
0x18001033d  mov     rax, [rax+48h]
0x180010341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010346  mov     ebx, r15d
0x180010349  mov     rcx, [rbp+var_38]
0x18001034d  test    rcx, rcx
0x180010350  jz      loc_1800103FA
0x180010356  mov     rax, [rcx]
0x180010359  lea     rdx, [rbp+bstrString]
0x18001035d  mov     rax, [rax+0D0h]
0x180010364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010369  lea     rdx, [rbp+Src]; unsigned __int8 **
0x18001036d  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x180010371  call    ?getBytesFromHex@@YAJPEAGPEAPEAE@Z; getBytesFromHex(ushort *,uchar * *)
0x180010376  lea     ecx, [rax-1]
0x180010379  cmp     ecx, 13h
0x18001037c  ja      short loc_1800103B0
0x18001037e  mov     dword ptr [rbp+var_20], eax
0x180010381  movsxd  r8, eax; Size
0x180010384  mov     rdx, [rbp+Src]; Src
0x180010388  lea     rcx, [rbp+var_20+4]; void *
0x18001038c  call    memcpy_0
0x180010391  movzx   eax, di
0x180010394  lea     rdx, [rax+rax*2]
0x180010398  movups  xmm0, [rbp+var_20]
0x18001039c  movups  xmmword ptr [r14+rdx*8], xmm0
0x1800103a1  movsd   xmm1, [rbp+var_10]
0x1800103a6  movsd   qword ptr [r14+rdx*8+10h], xmm1
0x1800103ad  inc     di
0x1800103b0  mov     rcx, [rbp+Src]; hMem
0x1800103b4  call    cs:__imp_LocalFree
0x1800103bb  nop     dword ptr [rax+rax+00h]
0x1800103c0  mov     [rbp+Src], r15
0x1800103c4  lea     rcx, [rbp+var_38]
0x1800103c8  call    ?Release@?$CComPtrBase@UIXMLDOMNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IXMLDOMNode>::Release(void)
0x1800103cd  mov     rcx, [rbp+bstrString]; bstrString
0x1800103d1  call    cs:__imp_SysFreeString
0x1800103d8  nop     dword ptr [rax+rax+00h]
0x1800103dd  mov     [rbp+bstrString], r15
0x1800103e1  mov     rcx, [rbp+var_50]
0x1800103e5  mov     rax, [rcx]
0x1800103e8  lea     rdx, [rbp+var_38]
0x1800103ec  mov     rax, [rax+48h]
0x1800103f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103f5  jmp     loc_180010349
0x1800103fa  mov     [rsi+2], di
0x1800103fe  test    di, di
0x180010401  jz      short loc_180010444
0x180010403  mov     [rsi+8], r14
0x180010407  jmp     short loc_180010444
0x180010409  mov     rcx, cs:WPP_GLOBAL_Control
0x180010410  cmp     rcx, r12
0x180010413  jz      short loc_180010432
0x180010415  mov     edx, 0FEh
0x18001041a  lea     r9, aEaptlsconnecti; "eaptlsconnectionpropertiesv3:IssuerHash"
0x180010421  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180010428  mov     rcx, [rcx+10h]
0x18001042c  call    WPP_SF_S
0x180010431  nop
0x180010432  mov     rcx, rbx; bstrString
0x180010435  call    cs:__imp_SysFreeString
0x18001043c  nop     dword ptr [rax+rax+00h]
0x180010441  mov     ebx, r15d
0x180010444  mov     rcx, [rbp+bstrString]; bstrString
0x180010448  call    cs:__imp_SysFreeString
0x18001044f  nop     dword ptr [rax+rax+00h]
0x180010454  nop
0x180010455  mov     rcx, [rbp+var_38]
0x180010459  test    rcx, rcx
0x18001045c  jz      short loc_18001046B
0x18001045e  mov     rax, [rcx]
0x180010461  mov     rax, [rax+10h]
0x180010465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001046a  nop
0x18001046b  mov     rcx, [rbp+var_50]
0x18001046f  test    rcx, rcx
0x180010472  jz      short loc_180010481
0x180010474  mov     rdx, [rcx]
0x180010477  mov     rax, [rdx+10h]
0x18001047b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010480  nop
0x180010481  mov     eax, ebx
0x180010483  mov     rcx, [rbp+var_8]
0x180010487  xor     rcx, rsp; StackCookie
0x18001048a  call    __security_check_cookie
0x18001048f  lea     r11, [rsp+70h+var_s0]
0x180010494  mov     rbx, [r11+40h]
0x180010498  mov     rsi, [r11+48h]
0x18001049c  mov     rsp, r11
0x18001049f  pop     r15
0x1800104a1  pop     r14
0x1800104a3  pop     r12
0x1800104a5  pop     rdi
0x1800104a6  pop     rbp
0x1800104a7  retn
```
