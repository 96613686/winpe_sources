# CscPolicy_ProcessAdminPinPolicy(void)

- ea: `0x1800128e4`
- end: `0x180012a5e`
- name: `?CscPolicy_ProcessAdminPinPolicy@@YAJXZ`
- size: `378`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012120`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x180011f54`
- `0x1800128e4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012942`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012942`

## pseudocode

```c
__int64 CscPolicy_ProcessAdminPinPolicy(void)
{
  HRESULT v0; // eax
  const struct _GUID *v1; // rdx
  int v2; // ebx
  const struct _GUID *v3; // rdx
  int v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  void *v9; // [rsp+50h] [rbp+20h] BYREF
  void *v10; // [rsp+58h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+30h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(char *)(WPP_GLOBAL_Control + 28LL) < 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 53, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids);
  ppv = 0;
  v0 = CoCreateInstance(&CLSID_OfflineFilesCache, 0, 1u, &IID_IOfflineFilesCache, &ppv);
  v2 = v0;
  if ( v0 >= 0 )
  {
    v9 = 0;
    v10 = 0;
    v2 = CAdminPinProgress::CreateInstance(1, v1, &v9);
    if ( v2 < 0 || (v2 = CAdminPinProgress::CreateInstance(0, v3, &v10), v2 < 0) )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_15;
      v6 = 55;
      v7 = (unsigned int)v2;
    }
    else
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, void *, void *))(*(_QWORD *)ppv + 128LL))(ppv, v9, v10);
      v2 = v4;
      if ( v4 >= 0 )
        goto LABEL_15;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_15;
      v6 = 54;
      v7 = (unsigned int)v4;
    }
    WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, v7);
LABEL_15:
    if ( v9 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
    if ( v10 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v2;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      56,
      WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
      (unsigned int)v0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800128e4  push    rbp
0x1800128e6  push    rbx
0x1800128e7  push    rsi
0x1800128e8  mov     rbp, rsp
0x1800128eb  sub     rsp, 30h
0x1800128ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800128f6  lea     rsi, WPP_GLOBAL_Control
0x1800128fd  cmp     rcx, rsi
0x180012900  jz      short loc_18001291D
0x180012902  test    byte ptr [rcx+1Ch], 80h
0x180012906  jz      short loc_18001291D
0x180012908  mov     rcx, [rcx+10h]
0x18001290c  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180012913  mov     edx, 35h ; '5'
0x180012918  call    WPP_SF_
0x18001291d  xor     edx, edx; pUnkOuter
0x18001291f  mov     [rbp+arg_10], 0
0x180012927  lea     rax, [rbp+arg_10]
0x18001292b  lea     r9, IID_IOfflineFilesCache; riid
0x180012932  mov     [rsp+30h+ppv], rax; ppv
0x180012937  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x18001293e  lea     r8d, [rdx+1]; dwClsContext
0x180012942  call    cs:__imp_CoCreateInstance
0x180012948  mov     ebx, eax
0x18001294a  test    eax, eax
0x18001294c  js      loc_180012A2A
0x180012952  lea     r8, [rbp+arg_0]; void **
0x180012956  mov     [rbp+arg_0], 0
0x18001295e  mov     ecx, 1; int
0x180012963  mov     [rbp+arg_8], 0
0x18001296b  call    ?CreateInstance@CAdminPinProgress@@SAJHAEBU_GUID@@PEAPEAX@Z; CAdminPinProgress::CreateInstance(int,_GUID const &,void * *)
0x180012970  mov     ebx, eax
0x180012972  test    eax, eax
0x180012974  js      short loc_1800129C4
0x180012976  lea     r8, [rbp+arg_8]; void **
0x18001297a  xor     ecx, ecx; int
0x18001297c  call    ?CreateInstance@CAdminPinProgress@@SAJHAEBU_GUID@@PEAPEAX@Z; CAdminPinProgress::CreateInstance(int,_GUID const &,void * *)
0x180012981  mov     ebx, eax
0x180012983  test    eax, eax
0x180012985  js      short loc_1800129C4
0x180012987  mov     rcx, [rbp+arg_10]
0x18001298b  mov     r8, [rbp+arg_8]
0x18001298f  mov     rdx, [rbp+arg_0]
0x180012993  mov     rax, [rcx]
0x180012996  mov     rax, [rax+80h]
0x18001299d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129a2  mov     ebx, eax
0x1800129a4  test    eax, eax
0x1800129a6  jns     short loc_1800129EE
0x1800129a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129af  cmp     rcx, rsi
0x1800129b2  jz      short loc_1800129EE
0x1800129b4  test    byte ptr [rcx+1Ch], 2
0x1800129b8  jz      short loc_1800129EE
0x1800129ba  mov     edx, 36h ; '6'
0x1800129bf  mov     r9d, eax
0x1800129c2  jmp     short loc_1800129DE
0x1800129c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129cb  cmp     rcx, rsi
0x1800129ce  jz      short loc_1800129EE
0x1800129d0  test    byte ptr [rcx+1Ch], 2
0x1800129d4  jz      short loc_1800129EE
0x1800129d6  mov     edx, 37h ; '7'
0x1800129db  mov     r9d, ebx
0x1800129de  mov     rcx, [rcx+10h]
0x1800129e2  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x1800129e9  call    WPP_SF_d
0x1800129ee  mov     rcx, [rbp+arg_0]
0x1800129f2  test    rcx, rcx
0x1800129f5  jz      short loc_180012A03
0x1800129f7  mov     rax, [rcx]
0x1800129fa  mov     rax, [rax+10h]
0x1800129fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a03  mov     rcx, [rbp+arg_8]
0x180012a07  test    rcx, rcx
0x180012a0a  jz      short loc_180012A18
0x180012a0c  mov     rax, [rcx]
0x180012a0f  mov     rax, [rax+10h]
0x180012a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a18  mov     rcx, [rbp+arg_10]
0x180012a1c  mov     rax, [rcx]
0x180012a1f  mov     rax, [rax+10h]
0x180012a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a28  jmp     short loc_180012A54
0x180012a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a31  cmp     rcx, rsi
0x180012a34  jz      short loc_180012A54
0x180012a36  test    byte ptr [rcx+1Ch], 2
0x180012a3a  jz      short loc_180012A54
0x180012a3c  mov     rcx, [rcx+10h]
0x180012a40  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180012a47  mov     edx, 38h ; '8'
0x180012a4c  mov     r9d, eax
0x180012a4f  call    WPP_SF_d
0x180012a54  mov     eax, ebx
0x180012a56  add     rsp, 30h
0x180012a5a  pop     rsi
0x180012a5b  pop     rbx
0x180012a5c  pop     rbp
0x180012a5d  retn
```
