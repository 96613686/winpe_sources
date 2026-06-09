# Conflict_NotifySyncMgr(ISyncMgrControl *,ISyncMgrConflict *,SYNCMGR_UPDATE_REASON)

- ea: `0x18001c7ac`
- end: `0x18001c913`
- name: `?Conflict_NotifySyncMgr@@YAJPEAUISyncMgrControl@@PEAUISyncMgrConflict@@W4SYNCMGR_UPDATE_REASON@@@Z`
- size: `359`
- prototype: `__int64 __fastcall(struct ISyncMgrControl *, struct ISyncMgrConflict *, enum SYNCMGR_UPDATE_REASON)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c6f8`

## callees

- `0x18001c7ac`
- `0x18001fd8c`
- `0x180020020`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c81c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c866`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c81c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001c866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c8c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c8cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c8c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c8cd`
- `PROPSYS!PropVariantToStringAlloc` at `0x18001c810`
- `PROPSYS!PropVariantToStringAlloc` at `0x18001c85a`
- `PROPSYS!PropVariantToStringAlloc` at `0x18001c810`
- `PROPSYS!PropVariantToStringAlloc` at `0x18001c85a`

## pseudocode

```c
__int64 __fastcall Conflict_NotifySyncMgr(
        struct ISyncMgrControl *a1,
        struct ISyncMgrConflict *a2,
        enum SYNCMGR_UPDATE_REASON a3)
{
  HRESULT (__stdcall *GetProperty)(ISyncMgrConflict *, const PROPERTYKEY *const, PROPVARIANT *); // rax
  __int64 v7; // rdx
  HRESULT v8; // ebx
  __int64 v9; // r8
  HRESULT v10; // eax
  int v11; // edx
  int v12; // r8d
  PROPVARIANT propvar[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v15; // [rsp+50h] [rbp-10h]
  PWSTR v16; // [rsp+98h] [rbp+38h] BYREF
  PWSTR ppszOut; // [rsp+A8h] [rbp+48h] BYREF

  ppszOut = 0;
  v15 = 0;
  GetProperty = a2->lpVtbl->GetProperty;
  *(_OWORD *)propvar = 0;
  v8 = ((__int64 (__fastcall *)(struct ISyncMgrConflict *, const PROPERTYKEY *, PROPVARIANT *))GetProperty)(
         a2,
         &PKEY_Sync_HandlerID,
         propvar);
  if ( v8 < 0 )
    goto LABEL_11;
  v8 = PropVariantToStringAlloc(propvar, &ppszOut);
  PropVariantClear(propvar);
  if ( v8 < 0 )
    goto LABEL_11;
  v8 = ((__int64 (__fastcall *)(struct ISyncMgrConflict *, const PROPERTYKEY *, PROPVARIANT *))a2->lpVtbl->GetProperty)(
         a2,
         &PKEY_Sync_ItemID,
         propvar);
  if ( v8 >= 0 )
  {
    v16 = 0;
    v8 = PropVariantToStringAlloc(propvar, &v16);
    PropVariantClear(propvar);
    if ( v8 >= 0 )
    {
      v10 = ((__int64 (__fastcall *)(struct ISyncMgrControl *, PWSTR, PWSTR, struct ISyncMgrConflict *, enum SYNCMGR_UPDATE_REASON))a1->lpVtbl->UpdateConflict)(
              a1,
              ppszOut,
              v16,
              a2,
              a3);
      v8 = v10;
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
      {
        WPP_SF_SqdD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, (_DWORD)v16, (char)a2, a3, v10);
      }
      CoTaskMemFree(v16);
    }
  }
  CoTaskMemFree(ppszOut);
  if ( v8 < 0 )
  {
LABEL_11:
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_qdD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v9, a2, a3, v8);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001c7ac  mov     [rsp-28h+arg_0], rbx
0x18001c7b1  push    rbp
0x18001c7b2  push    rsi
0x18001c7b3  push    rdi
0x18001c7b4  push    r14
0x18001c7b6  push    r15
0x18001c7b8  mov     rbp, rsp
0x18001c7bb  sub     rsp, 60h
0x18001c7bf  xor     eax, eax
0x18001c7c1  mov     [rbp+ppszOut], 0
0x18001c7c9  mov     [rbp+var_10], rax
0x18001c7cd  mov     rdi, rdx
0x18001c7d0  mov     rax, [rdx]
0x18001c7d3  mov     esi, r8d
0x18001c7d6  mov     r14, rcx
0x18001c7d9  lea     r8, [rbp+propvar]
0x18001c7dd  xorps   xmm0, xmm0
0x18001c7e0  lea     rdx, PKEY_Sync_HandlerID
0x18001c7e7  mov     rcx, rdi
0x18001c7ea  mov     rax, [rax+18h]
0x18001c7ee  movups  xmmword ptr [rbp+propvar], xmm0
0x18001c7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7f7  lea     r15, WPP_GLOBAL_Control
0x18001c7fe  mov     ebx, eax
0x18001c800  test    eax, eax
0x18001c802  js      loc_18001C8D7
0x18001c808  lea     rdx, [rbp+ppszOut]; ppszOut
0x18001c80c  lea     rcx, [rbp+propvar]; propvar
0x18001c810  call    cs:__imp_PropVariantToStringAlloc
0x18001c816  lea     rcx, [rbp+propvar]; pvar
0x18001c81a  mov     ebx, eax
0x18001c81c  call    cs:__imp_PropVariantClear
0x18001c822  test    ebx, ebx
0x18001c824  js      loc_18001C8D7
0x18001c82a  mov     rax, [rdi]
0x18001c82d  lea     r8, [rbp+propvar]
0x18001c831  lea     rdx, PKEY_Sync_ItemID
0x18001c838  mov     rcx, rdi
0x18001c83b  mov     rax, [rax+18h]
0x18001c83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c844  mov     ebx, eax
0x18001c846  test    eax, eax
0x18001c848  js      short loc_18001C8C9
0x18001c84a  lea     rdx, [rbp+arg_8]; ppszOut
0x18001c84e  mov     [rbp+arg_8], 0
0x18001c856  lea     rcx, [rbp+propvar]; propvar
0x18001c85a  call    cs:__imp_PropVariantToStringAlloc
0x18001c860  lea     rcx, [rbp+propvar]; pvar
0x18001c864  mov     ebx, eax
0x18001c866  call    cs:__imp_PropVariantClear
0x18001c86c  test    ebx, ebx
0x18001c86e  js      short loc_18001C8C9
0x18001c870  mov     rax, [r14]
0x18001c873  mov     r9, rdi
0x18001c876  mov     r8, [rbp+arg_8]
0x18001c87a  mov     rcx, r14
0x18001c87d  mov     rdx, [rbp+ppszOut]
0x18001c881  mov     dword ptr [rsp+60h+var_40], esi
0x18001c885  mov     rax, [rax+68h]
0x18001c889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c88e  mov     ebx, eax
0x18001c890  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c897  cmp     rcx, r15
0x18001c89a  jz      short loc_18001C8BF
0x18001c89c  test    dword ptr [rcx+1Ch], 200000h
0x18001c8a3  jz      short loc_18001C8BF
0x18001c8a5  mov     r9, [rbp+arg_8]
0x18001c8a9  mov     rcx, [rcx+10h]
0x18001c8ad  mov     [rsp+60h+var_30], eax
0x18001c8b1  mov     [rsp+60h+var_38], esi
0x18001c8b5  mov     [rsp+60h+var_40], rdi
0x18001c8ba  call    WPP_SF_SqdD
0x18001c8bf  mov     rcx, [rbp+arg_8]; pv
0x18001c8c3  call    cs:__imp_CoTaskMemFree
0x18001c8c9  mov     rcx, [rbp+ppszOut]; pv
0x18001c8cd  call    cs:__imp_CoTaskMemFree
0x18001c8d3  test    ebx, ebx
0x18001c8d5  jns     short loc_18001C8FD
0x18001c8d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c8de  cmp     rcx, r15
0x18001c8e1  jz      short loc_18001C8FD
0x18001c8e3  test    byte ptr [rcx+1Ch], 2
0x18001c8e7  jz      short loc_18001C8FD
0x18001c8e9  mov     rcx, [rcx+10h]
0x18001c8ed  mov     r9, rdi
0x18001c8f0  mov     [rsp+60h+var_38], ebx
0x18001c8f4  mov     dword ptr [rsp+60h+var_40], esi
0x18001c8f8  call    WPP_SF_qdD
0x18001c8fd  mov     eax, ebx
0x18001c8ff  mov     rbx, [rsp+60h+arg_0]
0x18001c907  add     rsp, 60h
0x18001c90b  pop     r15
0x18001c90d  pop     r14
0x18001c90f  pop     rdi
0x18001c910  pop     rsi
0x18001c911  pop     rbp
0x18001c912  retn
```
