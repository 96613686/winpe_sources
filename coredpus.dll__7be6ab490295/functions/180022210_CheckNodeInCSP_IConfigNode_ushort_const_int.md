# CheckNodeInCSP(IConfigNode *,ushort const *,int *)

- ea: `0x180022210`
- end: `0x180022331`
- name: `?CheckNodeInCSP@@YAJPEAUIConfigNode@@PEBGPEAH@Z`
- size: `289`
- prototype: `__int64 __fastcall(struct IConfigNode *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b560`

## callees

- `0x180022210`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002227a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002227a`

## pseudocode

```c
__int64 __fastcall CheckNodeInCSP(struct IConfigNode *a1, const unsigned __int16 *a2, int *a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IConfigNode *, __int64 *); // rax
  HRESULT v7; // ebx
  LPVOID ppv; // [rsp+30h] [rbp-10h] BYREF
  __int64 v10; // [rsp+38h] [rbp-8h] BYREF
  int v11; // [rsp+60h] [rbp+20h] BYREF
  unsigned int v12; // [rsp+78h] [rbp+38h] BYREF

  v3 = *(_QWORD *)a1;
  v11 = 0;
  v12 = 0;
  v10 = 0;
  v6 = *(__int64 (__fastcall **)(struct IConfigNode *, __int64 *))(v3 + 120);
  ppv = 0;
  v7 = v6(a1, &v10);
  if ( v7 >= 0 )
  {
    v7 = CoCreateInstance(
           &GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4,
           0,
           1u,
           &GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6,
           &ppv);
    if ( v7 >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)ppv + 40LL))(ppv, a2);
      v7 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 136LL))(ppv, &v11);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, unsigned int *))(*(_QWORD *)ppv + 112LL))(
               ppv,
               v10,
               1,
               &v12);
        if ( v7 >= 0 )
          *a3 = v12 >= v11 - 1;
      }
    }
  }
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180022210  mov     [rsp-18h+arg_8], rbx
0x180022215  push    rbp
0x180022216  push    rsi
0x180022217  push    rdi
0x180022218  mov     rbp, rsp
0x18002221b  sub     rsp, 40h
0x18002221f  mov     rax, [rcx]
0x180022222  mov     rsi, rdx
0x180022225  lea     rdx, [rbp+var_8]
0x180022229  mov     [rbp+arg_0], 0
0x180022230  mov     rdi, r8
0x180022233  mov     [rbp+arg_18], 0
0x18002223a  mov     [rbp+var_8], 0
0x180022242  mov     rax, [rax+78h]
0x180022246  mov     [rbp+var_10], 0
0x18002224e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022253  mov     ebx, eax
0x180022255  test    eax, eax
0x180022257  js      loc_1800222EF
0x18002225d  xor     edx, edx; pUnkOuter
0x18002225f  lea     rax, [rbp+var_10]
0x180022263  lea     r9, _GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6; riid
0x18002226a  mov     [rsp+40h+ppv], rax; ppv
0x18002226f  lea     rcx, _GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4; rclsid
0x180022276  lea     r8d, [rdx+1]; dwClsContext
0x18002227a  call    cs:__imp_CoCreateInstance
0x180022281  nop     dword ptr [rax+rax+00h]
0x180022286  mov     ebx, eax
0x180022288  test    eax, eax
0x18002228a  js      short loc_1800222EF
0x18002228c  mov     rcx, [rbp+var_10]
0x180022290  mov     rdx, rsi
0x180022293  mov     rax, [rcx]
0x180022296  mov     rax, [rax+28h]
0x18002229a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002229f  mov     rcx, [rbp+var_10]
0x1800222a3  lea     rdx, [rbp+arg_0]
0x1800222a7  mov     rax, [rcx]
0x1800222aa  mov     rax, [rax+88h]
0x1800222b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222b6  mov     ebx, eax
0x1800222b8  test    eax, eax
0x1800222ba  js      short loc_1800222EF
0x1800222bc  mov     rcx, [rbp+var_10]
0x1800222c0  lea     r9, [rbp+arg_18]
0x1800222c4  mov     rdx, [rbp+var_8]
0x1800222c8  mov     r8d, 1
0x1800222ce  mov     rax, [rcx]
0x1800222d1  mov     rax, [rax+70h]
0x1800222d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222da  mov     ebx, eax
0x1800222dc  test    eax, eax
0x1800222de  js      short loc_1800222EF
0x1800222e0  mov     eax, [rbp+arg_0]
0x1800222e3  xor     ecx, ecx
0x1800222e5  dec     eax
0x1800222e7  cmp     [rbp+arg_18], eax
0x1800222ea  setnb   cl
0x1800222ed  mov     [rdi], ecx
0x1800222ef  mov     rcx, [rbp+var_8]
0x1800222f3  test    rcx, rcx
0x1800222f6  jz      short loc_18002230C
0x1800222f8  mov     rax, [rcx]
0x1800222fb  mov     rax, [rax+10h]
0x1800222ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022304  mov     [rbp+var_8], 0
0x18002230c  mov     rcx, [rbp+var_10]
0x180022310  test    rcx, rcx
0x180022313  jz      short loc_180022321
0x180022315  mov     rax, [rcx]
0x180022318  mov     rax, [rax+10h]
0x18002231c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022321  mov     eax, ebx
0x180022323  mov     rbx, [rsp+40h+arg_8]
0x180022328  add     rsp, 40h
0x18002232c  pop     rdi
0x18002232d  pop     rsi
0x18002232e  pop     rbp
0x18002232f  retn
```
