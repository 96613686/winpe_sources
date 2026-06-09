# CNetConnectionLuaImpl::QueryInterfaceINetLua(void *,_GUID const &,void * *,unsigned __int64)

- ea: `0x18001bd60`
- end: `0x18001bfb2`
- name: `?QueryInterfaceINetLua@CNetConnectionLuaImpl@@SAJPEAXAEBU_GUID@@PEAPEAX_K@Z`
- size: `594`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18001bd60`
- `0x18001bfb8`
- `0x180065010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001bf97`
- `ole32!CoTaskMemFree` at `0x18001bf97`
- `ole32!StringFromCLSID` at `0x18001bf89`
- `ole32!StringFromCLSID` at `0x18001bf89`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CNetConnectionLuaImpl::QueryInterfaceINetLua(char *a1, const struct _GUID *a2, void **a3)
{
  __int64 v4; // rax
  int InnerObject; // edi
  void *v8; // rbx
  __int64 v9; // rax
  void *v10; // rbx
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  __int64 v13; // rax
  LPOLESTR v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  GUID v20; // [rsp+20h] [rbp-10h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp+20h] BYREF

  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_INetLua.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_INetLua.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_INetLua.Data4;
  if ( !v4 )
  {
    InnerObject = 0;
    v8 = (void *)((unsigned __int64)(a1 + 40) & -(__int64)(a1 != 0));
    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 8LL))(v8);
    *a3 = v8;
    return (unsigned int)InnerObject;
  }
  v9 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_faedcf54_31fe_11d1_aad2_00805fc1270e.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_faedcf54_31fe_11d1_aad2_00805fc1270e.Data1 )
    v9 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_faedcf54_31fe_11d1_aad2_00805fc1270e.Data4;
  if ( !v9 )
  {
    lpsz = 0;
    v20 = GUID_faedcf54_31fe_11d1_aad2_00805fc1270e;
    InnerObject = CNetLuaImpl<INetConnection>::GetInnerObject(a1 + 40, &v20, &lpsz);
    if ( InnerObject >= 0 )
    {
      v10 = (void *)((unsigned __int64)(a1 + 16) & -(__int64)(a1 != 0));
      (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 8LL))(v10);
LABEL_21:
      v14 = lpsz;
      *a3 = v10;
      (*(void (__fastcall **)(LPOLESTR))(*(_QWORD *)v14 + 16LL))(v14);
      return (unsigned int)InnerObject;
    }
    goto LABEL_37;
  }
  v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_15fd01a3_6e5d_4ecd_9ebd_1813cb3887a1.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_15fd01a3_6e5d_4ecd_9ebd_1813cb3887a1.Data1 )
    v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_15fd01a3_6e5d_4ecd_9ebd_1813cb3887a1.Data4;
  if ( !v11 )
  {
    lpsz = 0;
    v20 = GUID_15fd01a3_6e5d_4ecd_9ebd_1813cb3887a1;
    InnerObject = CNetLuaImpl<INetConnection>::GetInnerObject(a1 + 40, &v20, &lpsz);
    if ( InnerObject < 0 )
      goto LABEL_37;
    v12 = (unsigned __int64)(a1 + 8);
LABEL_20:
    v10 = (void *)(v12 & -(__int64)(a1 != 0));
    (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 8LL))(v10);
    goto LABEL_21;
  }
  v13 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_faedcf66_31fe_11d1_aad2_00805fc1270e.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_faedcf66_31fe_11d1_aad2_00805fc1270e.Data1 )
    v13 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_faedcf66_31fe_11d1_aad2_00805fc1270e.Data4;
  if ( v13 )
  {
    v15 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_faedcf6a_31fe_11d1_aad2_00805fc1270e.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_faedcf6a_31fe_11d1_aad2_00805fc1270e.Data1 )
      v15 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_faedcf6a_31fe_11d1_aad2_00805fc1270e.Data4;
    if ( !v15 )
      goto LABEL_34;
    v16 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_faedcf57_31fe_11d1_aad2_00805fc1270e.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_faedcf57_31fe_11d1_aad2_00805fc1270e.Data1 )
      v16 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_faedcf57_31fe_11d1_aad2_00805fc1270e.Data4;
    if ( !v16 )
      goto LABEL_34;
    v17 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_faedcf53_31fe_11d1_aad2_00805fc1270e.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_faedcf53_31fe_11d1_aad2_00805fc1270e.Data1 )
      v17 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_faedcf53_31fe_11d1_aad2_00805fc1270e.Data4;
    if ( !v17 )
      goto LABEL_34;
    v18 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_faedcf5b_31fe_11d1_aad2_00805fc1270e.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_faedcf5b_31fe_11d1_aad2_00805fc1270e.Data1 )
      v18 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_faedcf5b_31fe_11d1_aad2_00805fc1270e.Data4;
    if ( v18 )
    {
      InnerObject = -2147467262;
    }
    else
    {
LABEL_34:
      v20 = *a2;
      InnerObject = CNetLuaImpl<INetConnection>::GetInnerObject(a1 + 40, &v20, a3);
      if ( InnerObject >= 0 )
        return (unsigned int)InnerObject;
    }
    goto LABEL_37;
  }
  lpsz = 0;
  v20 = GUID_faedcf66_31fe_11d1_aad2_00805fc1270e;
  InnerObject = CNetLuaImpl<INetConnection>::GetInnerObject(a1 + 40, &v20, &lpsz);
  if ( InnerObject >= 0 )
  {
    v12 = (unsigned __int64)(a1 + 24);
    goto LABEL_20;
  }
LABEL_37:
  lpsz = 0;
  if ( StringFromCLSID(a2, &lpsz) >= 0 )
    CoTaskMemFree(lpsz);
  return (unsigned int)InnerObject;
}

```

## disassembly

```asm
0x18001bd60  mov     [rsp-18h+arg_8], rbx
0x18001bd65  mov     [rsp-18h+arg_10], rsi
0x18001bd6a  push    rbp
0x18001bd6b  push    rdi
0x18001bd6c  push    r14
0x18001bd6e  mov     rbp, rsp
0x18001bd71  sub     rsp, 30h
0x18001bd75  mov     rax, [rdx]
0x18001bd78  mov     r14, r8
0x18001bd7b  sub     rax, qword ptr cs:IID_INetLua.Data1
0x18001bd82  mov     rbx, rdx
0x18001bd85  mov     rsi, rcx
0x18001bd88  jnz     short loc_18001BD95
0x18001bd8a  mov     rax, [rdx+8]
0x18001bd8e  sub     rax, qword ptr cs:IID_INetLua.Data4
0x18001bd95  test    rax, rax
0x18001bd98  jnz     short loc_18001BDC0
0x18001bd9a  lea     rax, [rcx+28h]
0x18001bd9e  xor     edi, edi
0x18001bda0  neg     rsi
0x18001bda3  sbb     rbx, rbx
0x18001bda6  and     rbx, rax
0x18001bda9  mov     rcx, rbx
0x18001bdac  mov     rax, [rbx]
0x18001bdaf  mov     rax, [rax+8]
0x18001bdb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdb8  mov     [r14], rbx
0x18001bdbb  jmp     loc_18001BF9D
0x18001bdc0  mov     rax, [rdx]
0x18001bdc3  sub     rax, qword ptr cs:_GUID_faedcf54_31fe_11d1_aad2_00805fc1270e.Data1
0x18001bdca  jnz     short loc_18001BDD7
0x18001bdcc  mov     rax, [rdx+8]
0x18001bdd0  sub     rax, qword ptr cs:_GUID_faedcf54_31fe_11d1_aad2_00805fc1270e.Data4
0x18001bdd7  test    rax, rax
0x18001bdda  jnz     short loc_18001BE20
0x18001bddc  movups  xmm0, xmmword ptr cs:_GUID_faedcf54_31fe_11d1_aad2_00805fc1270e.Data1
0x18001bde3  add     rcx, 28h ; '('
0x18001bde7  mov     [rbp+lpsz], rax
0x18001bdeb  lea     r8, [rbp+lpsz]
0x18001bdef  lea     rdx, [rbp+var_10]
0x18001bdf3  movdqu  [rbp+var_10], xmm0
0x18001bdf8  call    ?GetInnerObject@?$CNetLuaImpl@UINetConnection@@@@IEAAJU_GUID@@PEAPEAX@Z; CNetLuaImpl<INetConnection>::GetInnerObject(_GUID,void * *)
0x18001bdfd  mov     edi, eax
0x18001bdff  test    eax, eax
0x18001be01  js      loc_18001BF7A
0x18001be07  lea     rcx, [rsi+10h]
0x18001be0b  neg     rsi
0x18001be0e  sbb     rbx, rbx
0x18001be11  and     rbx, rcx
0x18001be14  mov     rcx, [rbx]
0x18001be17  mov     rax, [rcx+8]
0x18001be1b  jmp     loc_18001BEC8
0x18001be20  mov     rax, [rdx]
0x18001be23  sub     rax, qword ptr cs:_GUID_15fd01a3_6e5d_4ecd_9ebd_1813cb3887a1.Data1
0x18001be2a  jnz     short loc_18001BE37
0x18001be2c  mov     rax, [rdx+8]
0x18001be30  sub     rax, qword ptr cs:_GUID_15fd01a3_6e5d_4ecd_9ebd_1813cb3887a1.Data4
0x18001be37  test    rax, rax
0x18001be3a  jnz     short loc_18001BE6D
0x18001be3c  movups  xmm0, xmmword ptr cs:_GUID_15fd01a3_6e5d_4ecd_9ebd_1813cb3887a1.Data1
0x18001be43  add     rcx, 28h ; '('
0x18001be47  mov     [rbp+lpsz], rax
0x18001be4b  lea     r8, [rbp+lpsz]
0x18001be4f  lea     rdx, [rbp+var_10]
0x18001be53  movdqu  [rbp+var_10], xmm0
0x18001be58  call    ?GetInnerObject@?$CNetLuaImpl@UINetConnection@@@@IEAAJU_GUID@@PEAPEAX@Z; CNetLuaImpl<INetConnection>::GetInnerObject(_GUID,void * *)
0x18001be5d  mov     edi, eax
0x18001be5f  test    eax, eax
0x18001be61  js      loc_18001BF7A
0x18001be67  lea     rax, [rsi+8]
0x18001be6b  jmp     short loc_18001BEB8
0x18001be6d  mov     rax, [rdx]
0x18001be70  sub     rax, qword ptr cs:_GUID_faedcf66_31fe_11d1_aad2_00805fc1270e.Data1
0x18001be77  jnz     short loc_18001BE84
0x18001be79  mov     rax, [rdx+8]
0x18001be7d  sub     rax, qword ptr cs:_GUID_faedcf66_31fe_11d1_aad2_00805fc1270e.Data4
0x18001be84  test    rax, rax
0x18001be87  jnz     short loc_18001BEE8
0x18001be89  movups  xmm0, xmmword ptr cs:_GUID_faedcf66_31fe_11d1_aad2_00805fc1270e.Data1
0x18001be90  add     rcx, 28h ; '('
0x18001be94  mov     [rbp+lpsz], rax
0x18001be98  lea     r8, [rbp+lpsz]
0x18001be9c  lea     rdx, [rbp+var_10]
0x18001bea0  movdqu  [rbp+var_10], xmm0
0x18001bea5  call    ?GetInnerObject@?$CNetLuaImpl@UINetConnection@@@@IEAAJU_GUID@@PEAPEAX@Z; CNetLuaImpl<INetConnection>::GetInnerObject(_GUID,void * *)
0x18001beaa  mov     edi, eax
0x18001beac  test    eax, eax
0x18001beae  js      loc_18001BF7A
0x18001beb4  lea     rax, [rsi+18h]
0x18001beb8  neg     rsi
0x18001bebb  sbb     rbx, rbx
0x18001bebe  and     rbx, rax
0x18001bec1  mov     rax, [rbx]
0x18001bec4  mov     rax, [rax+8]
0x18001bec8  mov     rcx, rbx
0x18001becb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bed0  mov     rcx, [rbp+lpsz]
0x18001bed4  mov     [r14], rbx
0x18001bed7  mov     rax, [rcx]
0x18001beda  mov     rax, [rax+10h]
0x18001bede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bee3  jmp     loc_18001BF9D
0x18001bee8  mov     rax, [rdx]
0x18001beeb  sub     rax, qword ptr cs:_GUID_faedcf6a_31fe_11d1_aad2_00805fc1270e.Data1
0x18001bef2  jnz     short loc_18001BEFF
0x18001bef4  mov     rax, [rdx+8]
0x18001bef8  sub     rax, qword ptr cs:_GUID_faedcf6a_31fe_11d1_aad2_00805fc1270e.Data4
0x18001beff  test    rax, rax
0x18001bf02  jz      short loc_18001BF58
0x18001bf04  mov     rax, [rdx]
0x18001bf07  sub     rax, qword ptr cs:_GUID_faedcf57_31fe_11d1_aad2_00805fc1270e.Data1
0x18001bf0e  jnz     short loc_18001BF1B
0x18001bf10  mov     rax, [rdx+8]
0x18001bf14  sub     rax, qword ptr cs:_GUID_faedcf57_31fe_11d1_aad2_00805fc1270e.Data4
0x18001bf1b  test    rax, rax
0x18001bf1e  jz      short loc_18001BF58
0x18001bf20  mov     rax, [rdx]
0x18001bf23  sub     rax, qword ptr cs:_GUID_faedcf53_31fe_11d1_aad2_00805fc1270e.Data1
0x18001bf2a  jnz     short loc_18001BF37
0x18001bf2c  mov     rax, [rdx+8]
0x18001bf30  sub     rax, qword ptr cs:_GUID_faedcf53_31fe_11d1_aad2_00805fc1270e.Data4
0x18001bf37  test    rax, rax
0x18001bf3a  jz      short loc_18001BF58
0x18001bf3c  mov     rax, [rdx]
0x18001bf3f  sub     rax, qword ptr cs:_GUID_faedcf5b_31fe_11d1_aad2_00805fc1270e.Data1
0x18001bf46  jnz     short loc_18001BF53
0x18001bf48  mov     rax, [rdx+8]
0x18001bf4c  sub     rax, qword ptr cs:_GUID_faedcf5b_31fe_11d1_aad2_00805fc1270e.Data4
0x18001bf53  test    rax, rax
0x18001bf56  jnz     short loc_18001BF75
0x18001bf58  movups  xmm0, xmmword ptr [rdx]
0x18001bf5b  lea     rdx, [rbp+var_10]
0x18001bf5f  add     rcx, 28h ; '('
0x18001bf63  movdqu  [rbp+var_10], xmm0
0x18001bf68  call    ?GetInnerObject@?$CNetLuaImpl@UINetConnection@@@@IEAAJU_GUID@@PEAPEAX@Z; CNetLuaImpl<INetConnection>::GetInnerObject(_GUID,void * *)
0x18001bf6d  mov     edi, eax
0x18001bf6f  test    eax, eax
0x18001bf71  jns     short loc_18001BF9D
0x18001bf73  jmp     short loc_18001BF7A
0x18001bf75  mov     edi, 80004002h
0x18001bf7a  lea     rdx, [rbp+lpsz]; lplpsz
0x18001bf7e  mov     [rbp+lpsz], 0
0x18001bf86  mov     rcx, rbx; rclsid
0x18001bf89  call    cs:__imp_StringFromCLSID
0x18001bf8f  test    eax, eax
0x18001bf91  js      short loc_18001BF9D
0x18001bf93  mov     rcx, [rbp+lpsz]; pv
0x18001bf97  call    cs:__imp_CoTaskMemFree
0x18001bf9d  mov     rbx, [rsp+30h+arg_8]
0x18001bfa2  mov     eax, edi
0x18001bfa4  mov     rsi, [rsp+30h+arg_10]
0x18001bfa9  add     rsp, 30h
0x18001bfad  pop     r14
0x18001bfaf  pop     rdi
0x18001bfb0  pop     rbp
0x18001bfb1  retn
```
