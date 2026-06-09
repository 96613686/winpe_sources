# RasEapCreateConnectionProperties

- ea: `0x1800059b0`
- end: `0x180005bd7`
- name: `RasEapCreateConnectionProperties`
- size: `551`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005010`
- `0x1800055e0`
- `0x1800059b0`
- `0x180005f80`
- `0x180062228`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005aad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005aad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RasEapCreateConnectionProperties(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        struct _PEAP_CONN_PROPERTIES *a4,
        unsigned int a5,
        struct _EAPTLS_CONN_PROPERTIES **a6,
        unsigned int *a7)
{
  struct _EAPTLS_CONN_PROPERTIES **v11; // r14
  unsigned int *v12; // r15
  unsigned int ConnectionProperties; // edi
  unsigned int Instance; // ebx
  struct IXMLDOMDocument2 *v15; // rcx
  struct _EAPTLS_CONTROL_BLOCK *v16; // rax
  _QWORD v18[11]; // [rsp+30h] [rbp-58h] BYREF
  struct IXMLDOMDocument2 *ppv; // [rsp+A0h] [rbp+18h] BYREF

  ppv = 0;
  EapTlsInitialize2(1, 0);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, a1);
  if ( a3 && (v11 = a6) != 0 && (v12 = a7) != 0 )
  {
    ConnectionProperties = 0;
    *a6 = 0;
    *v12 = 0;
    v18[0] = 0;
    Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)a3 + 192LL))(a3, 0xFFFFFFFFLL, v18);
    if ( !Instance )
    {
      v15 = ppv;
      if ( ppv )
      {
        ppv = 0;
        ((void (__fastcall *)(struct IXMLDOMDocument2 *))v15->lpVtbl->Release)(v15);
      }
      Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, (LPVOID *)&ppv);
      if ( !Instance )
        Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD, _QWORD))ppv->lpVtbl->appendChild)(
                     ppv,
                     v18[0],
                     0);
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 250, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, Instance);
      v16 = WPP_GLOBAL_Control;
    }
    if ( v18[0] )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v18[0] + 16LL))(v18[0]);
      v16 = WPP_GLOBAL_Control;
    }
    if ( !Instance )
    {
      if ( a1 == 25 )
      {
        ConnectionProperties = PeapCreateConnectionProperties(a2, ppv, a4, a5, v11, v12);
      }
      else if ( a1 == 13 )
      {
        ConnectionProperties = EapTlsCreateConnectionProperties(a2, ppv, v11, v12);
      }
      else
      {
        if ( v16 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)v16 + 2), 154, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids, a1);
        ConnectionProperties = 50;
      }
    }
  }
  else
  {
    ConnectionProperties = 160;
  }
  EapTlsInitialize2(0, 0);
  if ( ppv )
    ((void (__fastcall *)(struct IXMLDOMDocument2 *))ppv->lpVtbl->Release)(ppv);
  return ConnectionProperties;
}

```

## disassembly

```asm
0x1800059b0  push    rbx
0x1800059b2  push    rbp
0x1800059b3  push    rsi
0x1800059b4  push    rdi
0x1800059b5  push    r12
0x1800059b7  push    r13
0x1800059b9  push    r14
0x1800059bb  push    r15
0x1800059bd  sub     rsp, 48h
0x1800059c1  mov     r12, r9
0x1800059c4  mov     rbx, r8
0x1800059c7  mov     ebp, edx
0x1800059c9  mov     esi, ecx
0x1800059cb  xor     r13d, r13d
0x1800059ce  mov     [rsp+88h+arg_10], r13
0x1800059d6  xor     edx, edx; int
0x1800059d8  mov     ecx, 1; int
0x1800059dd  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x1800059e2  lea     rax, WPP_GLOBAL_Control
0x1800059e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059f0  cmp     rcx, rax
0x1800059f3  jz      short loc_180005A0D
0x1800059f5  mov     edx, 98h
0x1800059fa  mov     r9d, esi
0x1800059fd  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005a04  mov     rcx, [rcx+10h]
0x180005a08  call    WPP_SF_d
0x180005a0d  test    rbx, rbx
0x180005a10  jz      loc_180005B9A
0x180005a16  mov     r14, [rsp+88h+arg_28]
0x180005a1e  test    r14, r14
0x180005a21  jz      loc_180005B9A
0x180005a27  mov     r15, [rsp+88h+arg_30]
0x180005a2f  test    r15, r15
0x180005a32  jz      loc_180005B9A
0x180005a38  mov     edi, r13d
0x180005a3b  mov     [r14], r13
0x180005a3e  mov     [r15], r13d
0x180005a41  mov     [rsp+88h+var_58], r13
0x180005a46  mov     rax, [rbx]
0x180005a49  mov     edx, 0FFFFFFFFh
0x180005a4e  lea     r8, [rsp+88h+var_58]
0x180005a53  mov     rcx, rbx
0x180005a56  mov     rax, [rax+0C0h]
0x180005a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a62  mov     ebx, eax
0x180005a64  test    eax, eax
0x180005a66  jnz     short loc_180005AE0
0x180005a68  mov     rcx, [rsp+88h+arg_10]
0x180005a70  test    rcx, rcx
0x180005a73  jz      short loc_180005A8A
0x180005a75  mov     [rsp+88h+arg_10], r13
0x180005a7d  mov     rax, [rcx]
0x180005a80  mov     rax, [rax+10h]
0x180005a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a89  nop
0x180005a8a  lea     rax, [rsp+88h+arg_10]
0x180005a92  mov     [rsp+88h+ppv], rax; ppv
0x180005a97  lea     r9, IID_IXMLDOMDocument2; riid
0x180005a9e  xor     edx, edx; pUnkOuter
0x180005aa0  mov     r8d, 1; dwClsContext
0x180005aa6  lea     rcx, CLSID_DOMDocument60; rclsid
0x180005aad  call    cs:__imp_CoCreateInstance
0x180005ab4  nop     dword ptr [rax+rax+00h]
0x180005ab9  mov     ebx, eax
0x180005abb  test    eax, eax
0x180005abd  jnz     short loc_180005AE0
0x180005abf  mov     rcx, [rsp+88h+arg_10]
0x180005ac7  mov     rax, [rcx]
0x180005aca  xor     r8d, r8d
0x180005acd  mov     rdx, [rsp+88h+var_58]
0x180005ad2  mov     rax, [rax+0A8h]
0x180005ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ade  mov     ebx, eax
0x180005ae0  mov     rax, cs:WPP_GLOBAL_Control
0x180005ae7  lea     r13, WPP_GLOBAL_Control
0x180005aee  cmp     rax, r13
0x180005af1  jz      short loc_180005B12
0x180005af3  mov     edx, 0FAh
0x180005af8  mov     r9d, ebx
0x180005afb  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005b02  mov     rcx, [rax+10h]
0x180005b06  call    WPP_SF_d
0x180005b0b  mov     rax, cs:WPP_GLOBAL_Control
0x180005b12  mov     rcx, [rsp+88h+var_58]
0x180005b17  test    rcx, rcx
0x180005b1a  jz      short loc_180005B2F
0x180005b1c  mov     rax, [rcx]
0x180005b1f  mov     rax, [rax+10h]
0x180005b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b28  mov     rax, cs:WPP_GLOBAL_Control
0x180005b2f  test    ebx, ebx
0x180005b31  jnz     short loc_180005B9F
0x180005b33  mov     rdx, [rsp+88h+arg_10]; struct IXMLDOMDocument2 *
0x180005b3b  cmp     esi, 19h
0x180005b3e  jz      short loc_180005B69
0x180005b40  cmp     esi, 0Dh
0x180005b43  jz      short loc_180005B89
0x180005b45  cmp     rax, r13
0x180005b48  jz      short loc_180005B62
0x180005b4a  mov     edx, 9Ah
0x180005b4f  mov     r9d, esi
0x180005b52  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005b59  mov     rcx, [rax+10h]
0x180005b5d  call    WPP_SF_d
0x180005b62  mov     edi, 32h ; '2'
0x180005b67  jmp     short loc_180005B9F
0x180005b69  mov     [rsp+88h+var_60], r15; unsigned int *
0x180005b6e  mov     [rsp+88h+ppv], r14; struct _PEAP_CONN_PROPERTIES **
0x180005b73  mov     r9d, [rsp+88h+arg_20]; unsigned int
0x180005b7b  mov     r8, r12; struct _PEAP_CONN_PROPERTIES *
0x180005b7e  mov     ecx, ebp; unsigned int
0x180005b80  call    ?PeapCreateConnectionProperties@@YAKKPEAUIXMLDOMDocument2@@PEAU_PEAP_CONN_PROPERTIES@@KPEAPEAU2@PEAK@Z; PeapCreateConnectionProperties(ulong,IXMLDOMDocument2 *,_PEAP_CONN_PROPERTIES *,ulong,_PEAP_CONN_PROPERTIES * *,ulong *)
0x180005b85  mov     edi, eax
0x180005b87  jmp     short loc_180005B9F
0x180005b89  mov     r9, r15; unsigned int *
0x180005b8c  mov     r8, r14; struct _EAPTLS_CONN_PROPERTIES **
0x180005b8f  mov     ecx, ebp; unsigned int
0x180005b91  call    ?EapTlsCreateConnectionProperties@@YAKKPEAUIXMLDOMDocument2@@PEAPEAU_EAPTLS_CONN_PROPERTIES@@PEAK@Z; EapTlsCreateConnectionProperties(ulong,IXMLDOMDocument2 *,_EAPTLS_CONN_PROPERTIES * *,ulong *)
0x180005b96  mov     edi, eax
0x180005b98  jmp     short loc_180005B9F
0x180005b9a  mov     edi, 0A0h
0x180005b9f  xor     edx, edx; int
0x180005ba1  xor     ecx, ecx; int
0x180005ba3  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180005ba8  nop
0x180005ba9  mov     rcx, [rsp+88h+arg_10]
0x180005bb1  test    rcx, rcx
0x180005bb4  jz      short loc_180005BC3
0x180005bb6  mov     rdx, [rcx]
0x180005bb9  mov     rax, [rdx+10h]
0x180005bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bc2  nop
0x180005bc3  mov     eax, edi
0x180005bc5  add     rsp, 48h
0x180005bc9  pop     r15
0x180005bcb  pop     r14
0x180005bcd  pop     r13
0x180005bcf  pop     r12
0x180005bd1  pop     rdi
0x180005bd2  pop     rsi
0x180005bd3  pop     rbp
0x180005bd4  pop     rbx
0x180005bd5  retn
```
