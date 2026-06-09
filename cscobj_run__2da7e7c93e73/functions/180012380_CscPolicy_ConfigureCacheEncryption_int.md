# CscPolicy_ConfigureCacheEncryption(int)

- ea: `0x180012380`
- end: `0x1800124bb`
- name: `?CscPolicy_ConfigureCacheEncryption@@YAJH@Z`
- size: `315`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012fc4`

## callees

- `0x180002040`
- `0x1800057e0`
- `0x18000f5cc`
- `0x180012380`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001247b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001247b`

## pseudocode

```c
__int64 __fastcall CscPolicy_ConfigureCacheEncryption(unsigned int a1, const struct _GUID *a2)
{
  void *v3; // rdx
  int v4; // ebx
  unsigned int v5; // edi
  _QWORD v7[2]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v8; // [rsp+40h] [rbp-20h]
  __int64 v9; // [rsp+78h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+20h] BYREF

  CObjectInGIT_SvcObj::CObjectInGIT_SvcObj((CObjectInGIT_SvcObj *)v7, a2);
  v9 = 0;
  v4 = CObjectInGIT<CComCoCreator_SvcObj>::CreateInstanceAndMarshalToGIT((__int64)v7, v3, &v9);
  if ( v4 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        18,
        WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
        (unsigned int)v4);
  }
  else
  {
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 104LL))(v9, a1);
    if ( v4 < 0
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        17,
        WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids,
        (unsigned int)v4);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v5 = v8;
  v7[0] = &CInterfaceInGITBase::`vftable';
  if ( v8 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, v5);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180012380  mov     [rsp-8+arg_0], rbx
0x180012385  mov     [rsp-8+arg_18], rdi
0x18001238a  push    rbp
0x18001238b  mov     rbp, rsp
0x18001238e  sub     rsp, 60h
0x180012392  mov     edi, ecx
0x180012394  lea     rcx, [rbp+var_30]; this
0x180012398  call    ??0CObjectInGIT_SvcObj@@QEAA@AEBU_GUID@@@Z; CObjectInGIT_SvcObj::CObjectInGIT_SvcObj(_GUID const &)
0x18001239d  lea     r8, [rbp+arg_8]
0x1800123a1  mov     [rbp+arg_8], 0
0x1800123a9  lea     rcx, [rbp+var_30]
0x1800123ad  call    ?CreateInstanceAndMarshalToGIT@?$CObjectInGIT@VCComCoCreator_SvcObj@@@@QEAAJAEBU_GUID@@PEAPEAX@Z; CObjectInGIT<CComCoCreator_SvcObj>::CreateInstanceAndMarshalToGIT(_GUID const &,void * *)
0x1800123b2  mov     ebx, eax
0x1800123b4  test    eax, eax
0x1800123b6  js      short loc_180012413
0x1800123b8  mov     rcx, [rbp+arg_8]
0x1800123bc  mov     edx, edi
0x1800123be  mov     rax, [rcx]
0x1800123c1  mov     rax, [rax+68h]
0x1800123c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123ca  mov     ebx, eax
0x1800123cc  test    eax, eax
0x1800123ce  jns     short loc_180012401
0x1800123d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123d7  lea     rax, WPP_GLOBAL_Control
0x1800123de  cmp     rcx, rax
0x1800123e1  jz      short loc_180012401
0x1800123e3  test    byte ptr [rcx+1Ch], 2
0x1800123e7  jz      short loc_180012401
0x1800123e9  mov     rcx, [rcx+10h]
0x1800123ed  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x1800123f4  mov     edx, 11h
0x1800123f9  mov     r9d, ebx
0x1800123fc  call    WPP_SF_d
0x180012401  mov     rcx, [rbp+arg_8]
0x180012405  mov     rax, [rcx]
0x180012408  mov     rax, [rax+10h]
0x18001240c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012411  jmp     short loc_180012444
0x180012413  mov     rcx, cs:WPP_GLOBAL_Control
0x18001241a  lea     rax, WPP_GLOBAL_Control
0x180012421  cmp     rcx, rax
0x180012424  jz      short loc_180012444
0x180012426  test    byte ptr [rcx+1Ch], 2
0x18001242a  jz      short loc_180012444
0x18001242c  mov     rcx, [rcx+10h]
0x180012430  lea     r8, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180012437  mov     edx, 12h
0x18001243c  mov     r9d, ebx
0x18001243f  call    WPP_SF_d
0x180012444  mov     edi, [rbp+var_20]
0x180012447  lea     rax, ??_7CInterfaceInGITBase@@6B@; const CInterfaceInGITBase::`vftable'
0x18001244e  mov     [rbp+var_30], rax
0x180012452  test    edi, edi
0x180012454  jz      short loc_1800124A7
0x180012456  xor     edx, edx; pUnkOuter
0x180012458  mov     [rbp+arg_10], 0
0x180012460  lea     rax, [rbp+arg_10]
0x180012464  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18001246b  mov     [rsp+60h+ppv], rax; ppv
0x180012470  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180012477  lea     r8d, [rdx+1]; dwClsContext
0x18001247b  call    cs:__imp_CoCreateInstance
0x180012481  test    eax, eax
0x180012483  js      short loc_1800124A7
0x180012485  mov     rcx, [rbp+arg_10]
0x180012489  mov     edx, edi
0x18001248b  mov     rax, [rcx]
0x18001248e  mov     rax, [rax+20h]
0x180012492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012497  mov     rcx, [rbp+arg_10]
0x18001249b  mov     rax, [rcx]
0x18001249e  mov     rax, [rax+10h]
0x1800124a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124a7  lea     r11, [rsp+60h+var_s0]
0x1800124ac  mov     eax, ebx
0x1800124ae  mov     rbx, [r11+10h]
0x1800124b2  mov     rdi, [r11+28h]
0x1800124b6  mov     rsp, r11
0x1800124b9  pop     rbp
0x1800124ba  retn
```
