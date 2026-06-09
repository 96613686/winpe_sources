# IsRetailOs(void)

- ea: `0x140003608`
- end: `0x140003730`
- name: `?IsRetailOs@@YAHXZ`
- size: `296`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140009ee0`

## callees

- `0x140003608`
- `0x14000d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000367a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000367a`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x14000362e`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x14000362e`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1400036cb`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1400036cb`

## pseudocode

```c
__int64 IsRetailOs(void)
{
  int v0; // edi
  HRESULT v1; // ebx
  LPVOID v2; // rcx
  LPVOID v3; // r8
  unsigned int v5; // ebx
  __int16 v6; // [rsp+40h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+18h] BYREF

  ppv = 0;
  v6 = -1;
  v0 = 0;
  v1 = RoInitialize(1);
  if ( v1 >= 0 )
  {
    v0 = 1;
    v2 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
    }
    v1 = CoCreateInstance(&CLSID_FlightSettingsAPIBroker, 0, 1u, &GUID_e833feb2_c58a_45e4_8d93_08874744febb, &ppv);
    if ( v1 >= 0 )
    {
      v1 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 112LL))(ppv, &v6);
      if ( v1 >= 0 )
        v1 = 0;
    }
  }
  v3 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v3 + 16LL))(v3);
    v3 = ppv;
  }
  if ( v0 )
  {
    RoUninitialize();
    v3 = ppv;
  }
  if ( v1 >= 0 )
  {
    v5 = v6;
    if ( v3 )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v3 + 16LL))(v3);
    }
    return v5;
  }
  else
  {
    if ( v3 )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v3 + 16LL))(v3);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x140003608  mov     [rsp-8+arg_10], rbx
0x14000360d  mov     [rsp-8+arg_18], rdi
0x140003612  push    rbp
0x140003613  mov     rbp, rsp
0x140003616  sub     rsp, 30h
0x14000361a  mov     [rbp+arg_8], 0
0x140003622  or      eax, 0FFFFFFFFh
0x140003625  mov     [rbp+arg_0], ax
0x140003629  xor     edi, edi
0x14000362b  lea     ecx, [rax+2]
0x14000362e  call    cs:__imp_RoInitialize
0x140003634  mov     ebx, eax
0x140003636  test    eax, eax
0x140003638  js      short loc_1400036A3
0x14000363a  mov     edi, 1
0x14000363f  mov     rcx, [rbp+arg_8]
0x140003643  test    rcx, rcx
0x140003646  jz      short loc_14000365D
0x140003648  mov     [rbp+arg_8], 0
0x140003650  mov     rax, [rcx]
0x140003653  mov     rax, [rax+10h]
0x140003657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000365c  nop
0x14000365d  lea     rax, [rbp+arg_8]
0x140003661  mov     [rsp+30h+ppv], rax; ppv
0x140003666  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x14000366d  xor     edx, edx; pUnkOuter
0x14000366f  lea     r8d, [rdx+1]; dwClsContext
0x140003673  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x14000367a  call    cs:__imp_CoCreateInstance
0x140003680  mov     ebx, eax
0x140003682  test    eax, eax
0x140003684  js      short loc_1400036A3
0x140003686  mov     rcx, [rbp+arg_8]
0x14000368a  mov     rax, [rcx]
0x14000368d  lea     rdx, [rbp+arg_0]
0x140003691  mov     rax, [rax+70h]
0x140003695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000369a  mov     ebx, eax
0x14000369c  xor     eax, eax
0x14000369e  test    ebx, ebx
0x1400036a0  cmovns  ebx, eax
0x1400036a3  mov     r8, [rbp+arg_8]
0x1400036a7  test    r8, r8
0x1400036aa  jz      short loc_1400036C7
0x1400036ac  mov     [rbp+arg_8], 0
0x1400036b4  mov     rax, [r8]
0x1400036b7  mov     rcx, r8
0x1400036ba  mov     rax, [rax+10h]
0x1400036be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036c3  mov     r8, [rbp+arg_8]
0x1400036c7  test    edi, edi
0x1400036c9  jz      short loc_1400036D5
0x1400036cb  call    cs:__imp_RoUninitialize
0x1400036d1  mov     r8, [rbp+arg_8]
0x1400036d5  test    ebx, ebx
0x1400036d7  jns     short loc_1400036FD
0x1400036d9  test    r8, r8
0x1400036dc  jz      short loc_1400036F6
0x1400036de  mov     [rbp+arg_8], 0
0x1400036e6  mov     rcx, [r8]
0x1400036e9  mov     rax, [rcx+10h]
0x1400036ed  mov     rcx, r8
0x1400036f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400036f5  nop
0x1400036f6  mov     eax, 1
0x1400036fb  jmp     short loc_140003720
0x1400036fd  movsx   ebx, [rbp+arg_0]
0x140003701  test    r8, r8
0x140003704  jz      short loc_14000371E
0x140003706  mov     [rbp+arg_8], 0
0x14000370e  mov     rdx, [r8]
0x140003711  mov     rcx, r8
0x140003714  mov     rax, [rdx+10h]
0x140003718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000371d  nop
0x14000371e  mov     eax, ebx
0x140003720  mov     rbx, [rsp+30h+arg_10]
0x140003725  mov     rdi, [rsp+30h+arg_18]
0x14000372a  add     rsp, 30h
0x14000372e  pop     rbp
0x14000372f  retn
```
