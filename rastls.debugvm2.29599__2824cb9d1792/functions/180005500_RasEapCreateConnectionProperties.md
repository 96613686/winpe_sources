# RasEapCreateConnectionProperties

- ea: `0x180005500`
- end: `0x180005720`
- name: `RasEapCreateConnectionProperties`
- size: `544`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004bd0`
- `0x180005170`
- `0x180005500`
- `0x180005ac0`
- `0x18005ea34`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800055fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800055fd`

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
0x180005500  push    rbx
0x180005502  push    rbp
0x180005503  push    rsi
0x180005504  push    rdi
0x180005505  push    r12
0x180005507  push    r13
0x180005509  push    r14
0x18000550b  push    r15
0x18000550d  sub     rsp, 48h
0x180005511  mov     r12, r9
0x180005514  mov     rbx, r8
0x180005517  mov     ebp, edx
0x180005519  mov     esi, ecx
0x18000551b  xor     r13d, r13d
0x18000551e  mov     [rsp+88h+arg_10], r13
0x180005526  xor     edx, edx; int
0x180005528  mov     ecx, 1; int
0x18000552d  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x180005532  lea     rax, WPP_GLOBAL_Control
0x180005539  mov     rcx, cs:WPP_GLOBAL_Control
0x180005540  cmp     rcx, rax
0x180005543  jz      short loc_18000555D
0x180005545  mov     edx, 98h
0x18000554a  mov     r9d, esi
0x18000554d  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x180005554  mov     rcx, [rcx+10h]
0x180005558  call    WPP_SF_d
0x18000555d  test    rbx, rbx
0x180005560  jz      loc_1800056E4
0x180005566  mov     r14, [rsp+88h+arg_28]
0x18000556e  test    r14, r14
0x180005571  jz      loc_1800056E4
0x180005577  mov     r15, [rsp+88h+arg_30]
0x18000557f  test    r15, r15
0x180005582  jz      loc_1800056E4
0x180005588  mov     edi, r13d
0x18000558b  mov     [r14], r13
0x18000558e  mov     [r15], r13d
0x180005591  mov     [rsp+88h+var_58], r13
0x180005596  mov     rax, [rbx]
0x180005599  mov     edx, 0FFFFFFFFh
0x18000559e  lea     r8, [rsp+88h+var_58]
0x1800055a3  mov     rcx, rbx
0x1800055a6  mov     rax, [rax+0C0h]
0x1800055ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055b2  mov     ebx, eax
0x1800055b4  test    eax, eax
0x1800055b6  jnz     short loc_18000562A
0x1800055b8  mov     rcx, [rsp+88h+arg_10]
0x1800055c0  test    rcx, rcx
0x1800055c3  jz      short loc_1800055DA
0x1800055c5  mov     [rsp+88h+arg_10], r13
0x1800055cd  mov     rax, [rcx]
0x1800055d0  mov     rax, [rax+10h]
0x1800055d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055d9  nop
0x1800055da  lea     rax, [rsp+88h+arg_10]
0x1800055e2  mov     [rsp+88h+ppv], rax; ppv
0x1800055e7  lea     r9, IID_IXMLDOMDocument2; riid
0x1800055ee  xor     edx, edx; pUnkOuter
0x1800055f0  mov     r8d, 1; dwClsContext
0x1800055f6  lea     rcx, CLSID_DOMDocument60; rclsid
0x1800055fd  call    cs:__imp_CoCreateInstance
0x180005603  mov     ebx, eax
0x180005605  test    eax, eax
0x180005607  jnz     short loc_18000562A
0x180005609  mov     rcx, [rsp+88h+arg_10]
0x180005611  mov     rax, [rcx]
0x180005614  xor     r8d, r8d
0x180005617  mov     rdx, [rsp+88h+var_58]
0x18000561c  mov     rax, [rax+0A8h]
0x180005623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005628  mov     ebx, eax
0x18000562a  mov     rax, cs:WPP_GLOBAL_Control
0x180005631  lea     r13, WPP_GLOBAL_Control
0x180005638  cmp     rax, r13
0x18000563b  jz      short loc_18000565C
0x18000563d  mov     edx, 0FAh
0x180005642  mov     r9d, ebx
0x180005645  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x18000564c  mov     rcx, [rax+10h]
0x180005650  call    WPP_SF_d
0x180005655  mov     rax, cs:WPP_GLOBAL_Control
0x18000565c  mov     rcx, [rsp+88h+var_58]
0x180005661  test    rcx, rcx
0x180005664  jz      short loc_180005679
0x180005666  mov     rax, [rcx]
0x180005669  mov     rax, [rax+10h]
0x18000566d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005672  mov     rax, cs:WPP_GLOBAL_Control
0x180005679  test    ebx, ebx
0x18000567b  jnz     short loc_1800056E9
0x18000567d  mov     rdx, [rsp+88h+arg_10]; struct IXMLDOMDocument2 *
0x180005685  cmp     esi, 19h
0x180005688  jz      short loc_1800056B3
0x18000568a  cmp     esi, 0Dh
0x18000568d  jz      short loc_1800056D3
0x18000568f  cmp     rax, r13
0x180005692  jz      short loc_1800056AC
0x180005694  mov     edx, 9Ah
0x180005699  mov     r9d, esi
0x18000569c  lea     r8, WPP_1de0dab17d6a309f728ee0028cc45a05_Traceguids
0x1800056a3  mov     rcx, [rax+10h]
0x1800056a7  call    WPP_SF_d
0x1800056ac  mov     edi, 32h ; '2'
0x1800056b1  jmp     short loc_1800056E9
0x1800056b3  mov     [rsp+88h+var_60], r15; unsigned int *
0x1800056b8  mov     [rsp+88h+ppv], r14; struct _PEAP_CONN_PROPERTIES **
0x1800056bd  mov     r9d, [rsp+88h+arg_20]; unsigned int
0x1800056c5  mov     r8, r12; struct _PEAP_CONN_PROPERTIES *
0x1800056c8  mov     ecx, ebp; unsigned int
0x1800056ca  call    ?PeapCreateConnectionProperties@@YAKKPEAUIXMLDOMDocument2@@PEAU_PEAP_CONN_PROPERTIES@@KPEAPEAU2@PEAK@Z; PeapCreateConnectionProperties(ulong,IXMLDOMDocument2 *,_PEAP_CONN_PROPERTIES *,ulong,_PEAP_CONN_PROPERTIES * *,ulong *)
0x1800056cf  mov     edi, eax
0x1800056d1  jmp     short loc_1800056E9
0x1800056d3  mov     r9, r15; unsigned int *
0x1800056d6  mov     r8, r14; struct _EAPTLS_CONN_PROPERTIES **
0x1800056d9  mov     ecx, ebp; unsigned int
0x1800056db  call    ?EapTlsCreateConnectionProperties@@YAKKPEAUIXMLDOMDocument2@@PEAPEAU_EAPTLS_CONN_PROPERTIES@@PEAK@Z; EapTlsCreateConnectionProperties(ulong,IXMLDOMDocument2 *,_EAPTLS_CONN_PROPERTIES * *,ulong *)
0x1800056e0  mov     edi, eax
0x1800056e2  jmp     short loc_1800056E9
0x1800056e4  mov     edi, 0A0h
0x1800056e9  xor     edx, edx; int
0x1800056eb  xor     ecx, ecx; int
0x1800056ed  call    ?EapTlsInitialize2@@YAKHH@Z; EapTlsInitialize2(int,int)
0x1800056f2  nop
0x1800056f3  mov     rcx, [rsp+88h+arg_10]
0x1800056fb  test    rcx, rcx
0x1800056fe  jz      short loc_18000570D
0x180005700  mov     rdx, [rcx]
0x180005703  mov     rax, [rdx+10h]
0x180005707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000570c  nop
0x18000570d  mov     eax, edi
0x18000570f  add     rsp, 48h
0x180005713  pop     r15
0x180005715  pop     r14
0x180005717  pop     r13
0x180005719  pop     r12
0x18000571b  pop     rdi
0x18000571c  pop     rsi
0x18000571d  pop     rbp
0x18000571e  pop     rbx
0x18000571f  retn
```
