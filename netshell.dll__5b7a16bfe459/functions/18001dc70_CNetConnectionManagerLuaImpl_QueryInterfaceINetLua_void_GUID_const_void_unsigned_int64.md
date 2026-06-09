# CNetConnectionManagerLuaImpl::QueryInterfaceINetLua(void *,_GUID const &,void * *,unsigned __int64)

- ea: `0x18001dc70`
- end: `0x18001ddde`
- name: `?QueryInterfaceINetLua@CNetConnectionManagerLuaImpl@@SAJPEAXAEBU_GUID@@PEAPEAX_K@Z`
- size: `366`
- prototype: `__int64 __fastcall(char *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18001dc70`
- `0x180027dc0`
- `0x180065010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001ddc3`
- `ole32!CoTaskMemFree` at `0x18001ddc3`
- `ole32!StringFromCLSID` at `0x18001ddb5`
- `ole32!StringFromCLSID` at `0x18001ddb5`

## pseudocode

```c
__int64 __fastcall CNetConnectionManagerLuaImpl::QueryInterfaceINetLua(char *a1, const struct _GUID *a2, void **a3)
{
  __int64 v4; // rax
  int InnerObject; // edi
  void *v8; // rbx
  __int64 v9; // rax
  void *v10; // rbx
  __int64 v11; // rax
  LPOLESTR v12; // rcx
  GUID v14; // [rsp+20h] [rbp-10h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp+20h] BYREF

  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_INetLua.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_INetLua.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_INetLua.Data4;
  if ( !v4 )
  {
    InnerObject = 0;
    v8 = (void *)((unsigned __int64)(a1 + 24) & -(__int64)(a1 != 0));
    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 8LL))(v8);
    *a3 = v8;
    return (unsigned int)InnerObject;
  }
  v9 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_faedcf69_31fe_11d1_aad2_00805fc1270e.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_faedcf69_31fe_11d1_aad2_00805fc1270e.Data1 )
    v9 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_faedcf69_31fe_11d1_aad2_00805fc1270e.Data4;
  if ( v9 )
  {
    v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_faedcf71_31fe_11d1_aad2_00805fc1270e.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_faedcf71_31fe_11d1_aad2_00805fc1270e.Data1 )
      v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_faedcf71_31fe_11d1_aad2_00805fc1270e.Data4;
    if ( v11 )
    {
      InnerObject = -2147467262;
    }
    else
    {
      lpsz = 0;
      v14 = GUID_faedcf71_31fe_11d1_aad2_00805fc1270e;
      InnerObject = CNetLuaImpl<INetConnectionManager>::GetInnerObject(a1 + 24, &v14, &lpsz);
      if ( InnerObject >= 0 )
      {
        v10 = (void *)((unsigned __int64)(a1 + 16) & -(__int64)(a1 != 0));
        (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 8LL))(v10);
        goto LABEL_15;
      }
    }
  }
  else
  {
    lpsz = 0;
    v14 = GUID_faedcf69_31fe_11d1_aad2_00805fc1270e;
    InnerObject = CNetLuaImpl<INetConnectionManager>::GetInnerObject(a1 + 24, &v14, &lpsz);
    if ( InnerObject >= 0 )
    {
      v10 = (void *)((unsigned __int64)(a1 + 8) & -(__int64)(a1 != 0));
      (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 8LL))(v10);
LABEL_15:
      v12 = lpsz;
      *a3 = v10;
      (*(void (__fastcall **)(LPOLESTR))(*(_QWORD *)v12 + 16LL))(v12);
      return (unsigned int)InnerObject;
    }
  }
  lpsz = 0;
  if ( StringFromCLSID(a2, &lpsz) >= 0 )
    CoTaskMemFree(lpsz);
  return (unsigned int)InnerObject;
}

```

## disassembly

```asm
0x18001dc70  mov     [rsp-18h+arg_8], rbx
0x18001dc75  mov     [rsp-18h+arg_10], rsi
0x18001dc7a  push    rbp
0x18001dc7b  push    rdi
0x18001dc7c  push    r14
0x18001dc7e  mov     rbp, rsp
0x18001dc81  sub     rsp, 30h
0x18001dc85  mov     rax, [rdx]
0x18001dc88  mov     r14, r8
0x18001dc8b  sub     rax, qword ptr cs:IID_INetLua.Data1
0x18001dc92  mov     rbx, rdx
0x18001dc95  mov     rsi, rcx
0x18001dc98  jnz     short loc_18001DCA5
0x18001dc9a  mov     rax, [rdx+8]
0x18001dc9e  sub     rax, qword ptr cs:IID_INetLua.Data4
0x18001dca5  test    rax, rax
0x18001dca8  jnz     short loc_18001DCD0
0x18001dcaa  lea     rax, [rcx+18h]
0x18001dcae  xor     edi, edi
0x18001dcb0  neg     rsi
0x18001dcb3  sbb     rbx, rbx
0x18001dcb6  and     rbx, rax
0x18001dcb9  mov     rcx, rbx
0x18001dcbc  mov     rax, [rbx]
0x18001dcbf  mov     rax, [rax+8]
0x18001dcc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcc8  mov     [r14], rbx
0x18001dccb  jmp     loc_18001DDC9
0x18001dcd0  mov     rax, [rdx]
0x18001dcd3  sub     rax, qword ptr cs:_GUID_faedcf69_31fe_11d1_aad2_00805fc1270e.Data1
0x18001dcda  jnz     short loc_18001DCE7
0x18001dcdc  mov     rax, [rdx+8]
0x18001dce0  sub     rax, qword ptr cs:_GUID_faedcf69_31fe_11d1_aad2_00805fc1270e.Data4
0x18001dce7  test    rax, rax
0x18001dcea  jnz     short loc_18001DD2D
0x18001dcec  movups  xmm0, xmmword ptr cs:_GUID_faedcf69_31fe_11d1_aad2_00805fc1270e.Data1
0x18001dcf3  add     rcx, 18h
0x18001dcf7  mov     [rbp+lpsz], rax
0x18001dcfb  lea     r8, [rbp+lpsz]
0x18001dcff  lea     rdx, [rbp+var_10]
0x18001dd03  movdqu  [rbp+var_10], xmm0
0x18001dd08  call    ?GetInnerObject@?$CNetLuaImpl@UINetConnectionManager@@@@IEAAJU_GUID@@PEAPEAX@Z; CNetLuaImpl<INetConnectionManager>::GetInnerObject(_GUID,void * *)
0x18001dd0d  mov     edi, eax
0x18001dd0f  test    eax, eax
0x18001dd11  js      loc_18001DDA6
0x18001dd17  lea     rcx, [rsi+8]
0x18001dd1b  neg     rsi
0x18001dd1e  sbb     rbx, rbx
0x18001dd21  and     rbx, rcx
0x18001dd24  mov     rcx, [rbx]
0x18001dd27  mov     rax, [rcx+8]
0x18001dd2b  jmp     short loc_18001DD84
0x18001dd2d  mov     rax, [rdx]
0x18001dd30  sub     rax, qword ptr cs:_GUID_faedcf71_31fe_11d1_aad2_00805fc1270e.Data1
0x18001dd37  jnz     short loc_18001DD44
0x18001dd39  mov     rax, [rdx+8]
0x18001dd3d  sub     rax, qword ptr cs:_GUID_faedcf71_31fe_11d1_aad2_00805fc1270e.Data4
0x18001dd44  test    rax, rax
0x18001dd47  jnz     short loc_18001DDA1
0x18001dd49  movups  xmm0, xmmword ptr cs:_GUID_faedcf71_31fe_11d1_aad2_00805fc1270e.Data1
0x18001dd50  add     rcx, 18h
0x18001dd54  mov     [rbp+lpsz], rax
0x18001dd58  lea     r8, [rbp+lpsz]
0x18001dd5c  lea     rdx, [rbp+var_10]
0x18001dd60  movdqu  [rbp+var_10], xmm0
0x18001dd65  call    ?GetInnerObject@?$CNetLuaImpl@UINetConnectionManager@@@@IEAAJU_GUID@@PEAPEAX@Z; CNetLuaImpl<INetConnectionManager>::GetInnerObject(_GUID,void * *)
0x18001dd6a  mov     edi, eax
0x18001dd6c  test    eax, eax
0x18001dd6e  js      short loc_18001DDA6
0x18001dd70  lea     rax, [rsi+10h]
0x18001dd74  neg     rsi
0x18001dd77  sbb     rbx, rbx
0x18001dd7a  and     rbx, rax
0x18001dd7d  mov     rax, [rbx]
0x18001dd80  mov     rax, [rax+8]
0x18001dd84  mov     rcx, rbx
0x18001dd87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd8c  mov     rcx, [rbp+lpsz]
0x18001dd90  mov     [r14], rbx
0x18001dd93  mov     rax, [rcx]
0x18001dd96  mov     rax, [rax+10h]
0x18001dd9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd9f  jmp     short loc_18001DDC9
0x18001dda1  mov     edi, 80004002h
0x18001dda6  lea     rdx, [rbp+lpsz]; lplpsz
0x18001ddaa  mov     [rbp+lpsz], 0
0x18001ddb2  mov     rcx, rbx; rclsid
0x18001ddb5  call    cs:__imp_StringFromCLSID
0x18001ddbb  test    eax, eax
0x18001ddbd  js      short loc_18001DDC9
0x18001ddbf  mov     rcx, [rbp+lpsz]; pv
0x18001ddc3  call    cs:__imp_CoTaskMemFree
0x18001ddc9  mov     rbx, [rsp+30h+arg_8]
0x18001ddce  mov     eax, edi
0x18001ddd0  mov     rsi, [rsp+30h+arg_10]
0x18001ddd5  add     rsp, 30h
0x18001ddd9  pop     r14
0x18001dddb  pop     rdi
0x18001dddc  pop     rbp
0x18001dddd  retn
```
