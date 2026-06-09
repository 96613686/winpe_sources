# HrIsLanCapableAdapter(INetCfgComponent *)

- ea: `0x180034a8c`
- end: `0x180034c17`
- name: `?HrIsLanCapableAdapter@@YAJPEAUINetCfgComponent@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(struct INetCfgComponent *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032110`

## callees

- `0x1800306f8`
- `0x180034a8c`
- `0x180036010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034aca`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180034aca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034ad9`

## pseudocode

```c
__int64 __fastcall HrIsLanCapableAdapter(struct INetCfgComponent *a1)
{
  struct INetCfgComponentVtbl *lpVtbl; // rax
  int v3; // ebx
  struct INetCfgComponentVtbl *v5; // rax
  unsigned int v6; // ebx
  struct IUnknown *v7; // [rsp+30h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+38h] [rbp+18h] BYREF

  lpVtbl = a1->lpVtbl;
  pv = 0;
  v3 = ((__int64 (__fastcall *)(struct INetCfgComponent *, LPVOID *))lpVtbl->GetId)(a1, &pv);
  if ( !v3 )
  {
    v3 = _o__wcsicmp(pv, L"BTH\\MS_BTHPAN") == 0;
    CoTaskMemFree(pv);
  }
  if ( v3 == 1 )
    return 1;
  v5 = a1->lpVtbl;
  v7 = 0;
  v6 = ((__int64 (__fastcall *)(struct INetCfgComponent *, GUID *, struct IUnknown **))v5->QueryInterface)(
         a1,
         &IID_INetCfgComponentBindings,
         &v7);
  if ( !v6 )
  {
    v6 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, const unsigned __int16 *))v7->lpVtbl[1].Release)(
           v7,
           2,
           L"ndis4");
    if ( v6 == 1 )
    {
      v6 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, const unsigned __int16 *))v7->lpVtbl[1].Release)(
             v7,
             2,
             L"ndis5");
      if ( v6 == 1 )
      {
        v6 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, const unsigned __int16 *))v7->lpVtbl[1].Release)(
               v7,
               2,
               L"ndis5_ip");
        if ( v6 == 1 )
        {
          v6 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, const unsigned __int16 *))v7->lpVtbl[1].Release)(
                 v7,
                 2,
                 L"flpp4");
          if ( v6 == 1 )
          {
            v6 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, const unsigned __int16 *))v7->lpVtbl[1].Release)(
                   v7,
                   2,
                   L"flpp6");
            if ( v6 == 1 )
            {
              v6 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, const WCHAR *))v7->lpVtbl[1].Release)(
                     v7,
                     1,
                     L"LocalTalk");
              if ( v6 == 1 )
                v6 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, const unsigned __int16 *))v7->lpVtbl[1].Release)(
                       v7,
                       2,
                       L"ndis1394");
            }
          }
        }
      }
    }
    ReleaseObj(v7);
  }
  return v6;
}

```

## disassembly

```asm
0x180034a8c  mov     [rsp-8+arg_10], rbx
0x180034a91  mov     [rsp-8+arg_18], rdi
0x180034a96  push    rbp
0x180034a97  mov     rbp, rsp
0x180034a9a  sub     rsp, 20h
0x180034a9e  mov     rax, [rcx]
0x180034aa1  lea     rdx, [rbp+pv]
0x180034aa5  mov     rdi, rcx
0x180034aa8  mov     [rbp+pv], 0
0x180034ab0  mov     rax, [rax+30h]
0x180034ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ab9  mov     ebx, eax
0x180034abb  test    eax, eax
0x180034abd  jnz     short loc_180034ADF
0x180034abf  mov     rcx, [rbp+pv]
0x180034ac3  lea     rdx, aBthMsBthpan; "BTH\\MS_BTHPAN"
0x180034aca  call    cs:__imp__o__wcsicmp
0x180034ad0  mov     rcx, [rbp+pv]; pv
0x180034ad4  test    eax, eax
0x180034ad6  setz    bl
0x180034ad9  call    cs:__imp_CoTaskMemFree
0x180034adf  cmp     ebx, 1
0x180034ae2  jnz     short loc_180034AEB
0x180034ae4  mov     eax, ebx
0x180034ae6  jmp     loc_180034C07
0x180034aeb  mov     rax, [rdi]
0x180034aee  lea     r8, [rbp+arg_0]
0x180034af2  lea     rdx, IID_INetCfgComponentBindings
0x180034af9  mov     [rbp+arg_0], 0
0x180034b01  mov     rcx, rdi
0x180034b04  mov     rax, [rax]
0x180034b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b0c  mov     ebx, eax
0x180034b0e  test    eax, eax
0x180034b10  jnz     loc_180034C05
0x180034b16  mov     rcx, [rbp+arg_0]
0x180034b1a  lea     edi, [rbx+2]
0x180034b1d  lea     r8, ?c_szBiNdis4@@3QBGB; "ndis4"
0x180034b24  mov     edx, edi
0x180034b26  mov     rax, [rcx]
0x180034b29  mov     rax, [rax+28h]
0x180034b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b32  mov     ebx, eax
0x180034b34  cmp     eax, 1
0x180034b37  jnz     loc_180034BFC
0x180034b3d  mov     rcx, [rbp+arg_0]
0x180034b41  lea     r8, ?c_szBiNdis5@@3QBGB; "ndis5"
0x180034b48  mov     edx, edi
0x180034b4a  mov     rax, [rcx]
0x180034b4d  mov     rax, [rax+28h]
0x180034b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b56  mov     ebx, eax
0x180034b58  cmp     eax, 1
0x180034b5b  jnz     loc_180034BFC
0x180034b61  mov     rcx, [rbp+arg_0]
0x180034b65  lea     r8, ?c_szBiNdis5Ip@@3QBGB; "ndis5_ip"
0x180034b6c  mov     edx, edi
0x180034b6e  mov     rax, [rcx]
0x180034b71  mov     rax, [rax+28h]
0x180034b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b7a  mov     ebx, eax
0x180034b7c  cmp     eax, 1
0x180034b7f  jnz     short loc_180034BFC
0x180034b81  mov     rcx, [rbp+arg_0]
0x180034b85  lea     r8, ?c_szBiFlpp4@@3QBGB; "flpp4"
0x180034b8c  mov     edx, edi
0x180034b8e  mov     rax, [rcx]
0x180034b91  mov     rax, [rax+28h]
0x180034b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b9a  mov     ebx, eax
0x180034b9c  cmp     eax, 1
0x180034b9f  jnz     short loc_180034BFC
0x180034ba1  mov     rcx, [rbp+arg_0]
0x180034ba5  lea     r8, ?c_szBiFlpp6@@3QBGB; "flpp6"
0x180034bac  mov     edx, edi
0x180034bae  mov     rax, [rcx]
0x180034bb1  mov     rax, [rax+28h]
0x180034bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bba  mov     ebx, eax
0x180034bbc  cmp     eax, 1
0x180034bbf  jnz     short loc_180034BFC
0x180034bc1  mov     rcx, [rbp+arg_0]
0x180034bc5  lea     r8, ?c_szBiLocalTalk@@3QBGB; "LocalTalk"
0x180034bcc  mov     edx, ebx
0x180034bce  mov     rax, [rcx]
0x180034bd1  mov     rax, [rax+28h]
0x180034bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bda  mov     ebx, eax
0x180034bdc  cmp     eax, 1
0x180034bdf  jnz     short loc_180034BFC
0x180034be1  mov     rcx, [rbp+arg_0]
0x180034be5  lea     r8, ?c_szBiNdis1394@@3QBGB; "ndis1394"
0x180034bec  mov     edx, edi
0x180034bee  mov     rax, [rcx]
0x180034bf1  mov     rax, [rax+28h]
0x180034bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bfa  mov     ebx, eax
0x180034bfc  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x180034c00  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x180034c05  mov     eax, ebx
0x180034c07  mov     rbx, [rsp+20h+arg_10]
0x180034c0c  mov     rdi, [rsp+20h+arg_18]
0x180034c11  add     rsp, 20h
0x180034c15  pop     rbp
0x180034c16  retn
```
