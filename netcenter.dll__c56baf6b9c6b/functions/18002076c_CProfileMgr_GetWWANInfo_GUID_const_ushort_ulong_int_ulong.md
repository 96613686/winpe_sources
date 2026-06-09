# CProfileMgr::GetWWANInfo(_GUID const &,ushort *,ulong,int *,ulong *)

- ea: `0x18002076c`
- end: `0x180020921`
- name: `?GetWWANInfo@CProfileMgr@@QEAAJAEBU_GUID@@PEAGKPEAHPEAK@Z`
- size: `437`
- prototype: `int(CProfileMgr *__hidden this, const struct _GUID *, unsigned __int16 *, unsigned int, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001fde8`

## callees

- `0x180012408`
- `0x180014274`
- `0x180016fc0`
- `0x18001f2ac`
- `0x18002076c`

## import_xrefs

- `wwapi!WwanFreeMemory` at `0x1800208fb`
- `wwapi!WwanFreeMemory` at `0x1800208fb`
- `wwapi!WwanOpenHandle` at `0x1800207bb`
- `wwapi!WwanOpenHandle` at `0x1800207bb`
- `wwapi!WwanQueryInterface` at `0x180020825`
- `wwapi!WwanQueryInterface` at `0x180020825`

## pseudocode

```c
__int64 __fastcall CProfileMgr::GetWWANInfo(
        CProfileMgr *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        __int64 a4,
        int *a5,
        unsigned int *a6)
{
  int v8; // eax
  signed int v9; // ebx
  int Interface; // eax
  __int64 v11; // rdx
  const unsigned __int16 *v12; // r8
  PVOID *v13; // rcx
  __int64 v15; // [rsp+40h] [rbp-30h] BYREF
  __int64 v16; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v17[2]; // [rsp+50h] [rbp-20h] BYREF
  char v18; // [rsp+60h] [rbp-10h]
  int v19; // [rsp+A8h] [rbp+38h] BYREF

  v15 = 0;
  v19 = 0;
  v16 = -1;
  v8 = WwanOpenHandle(1, 0, &v19);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_16;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_13:
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 1) != 0 )
        WPP_SF_d(v13[2], 58, &WPP_edb4701937c33b484ee7d731345f6be9_Traceguids, (unsigned int)v9);
      goto LABEL_16;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      &WPP_edb4701937c33b484ee7d731345f6be9_Traceguids,
      (unsigned int)v9);
LABEL_12:
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_13;
  }
  v17[0] = &v15;
  v17[1] = 0;
  v18 = 1;
  Interface = WwanQueryInterface(v16, a2, 7);
  v9 = Interface;
  if ( Interface > 0 )
    v9 = (unsigned __int16)Interface | 0x80070000;
  wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>(v17);
  if ( v9 < 0 )
    goto LABEL_12;
  v11 = v15;
  if ( *(_DWORD *)(v15 + 1700) != 1 )
    goto LABEL_17;
  v12 = (const unsigned __int16 *)(v15 + 1466);
  *a6 = *(_DWORD *)(v15 + 1220);
  *a5 = (unsigned int)(*(_DWORD *)(v11 + 1444) - 4) <= 1;
  v9 = StringCchCopyW(a3, 0x100u, v12);
LABEL_16:
  v11 = v15;
LABEL_17:
  v15 = 0;
  if ( v11 )
    WwanFreeMemory(v11);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002076c  mov     rax, rsp
0x18002076f  mov     [rax+10h], rbx
0x180020773  mov     [rax+18h], rsi
0x180020777  mov     [rax+20h], r9d
0x18002077b  mov     [rax+8], rcx
0x18002077f  push    rbp
0x180020780  push    rdi
0x180020781  push    r12
0x180020783  mov     rbp, rsp
0x180020786  sub     rsp, 70h
0x18002078a  mov     rdi, rdx
0x18002078d  mov     [rbp+var_30], 0
0x180020795  xor     edx, edx
0x180020797  mov     [rbp+arg_18], 0
0x18002079e  mov     rsi, r8
0x1800207a1  mov     [rbp+arg_0], 0
0x1800207a8  lea     r9, [rbp+var_28]
0x1800207ac  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFFh
0x1800207b4  lea     r8, [rbp+arg_18]
0x1800207b8  lea     ecx, [rdx+1]
0x1800207bb  call    cs:__imp_WwanOpenHandle
0x1800207c1  mov     ebx, eax
0x1800207c3  test    eax, eax
0x1800207c5  jle     short loc_1800207D0
0x1800207c7  movzx   ebx, ax
0x1800207ca  or      ebx, 80070000h
0x1800207d0  lea     r12, WPP_GLOBAL_Control
0x1800207d7  test    ebx, ebx
0x1800207d9  js      loc_180020893
0x1800207df  mov     rcx, [rbp+var_28]
0x1800207e3  lea     rax, [rbp+var_30]
0x1800207e7  mov     [rbp+var_20], rax
0x1800207eb  xor     r9d, r9d
0x1800207ee  mov     [rsp+70h+var_38], 0
0x1800207f7  lea     rax, [rbp+var_18]
0x1800207fb  mov     [rsp+70h+var_40], 0
0x180020804  mov     rdx, rdi
0x180020807  mov     [rsp+70h+var_48], rax
0x18002080c  lea     rax, [rbp+arg_0]
0x180020810  lea     r8d, [r9+7]
0x180020814  mov     [rsp+70h+var_50], rax
0x180020819  mov     [rbp+var_18], 0
0x180020821  mov     [rbp+var_10], 1
0x180020825  call    cs:__imp_WwanQueryInterface
0x18002082b  mov     ebx, eax
0x18002082d  test    eax, eax
0x18002082f  jle     short loc_18002083A
0x180020831  movzx   ebx, ax
0x180020834  or      ebx, 80070000h
0x18002083a  lea     rcx, [rbp+var_20]
0x18002083e  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@UWWAN_INTERFACE_OBJECT@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x180020843  test    ebx, ebx
0x180020845  js      short loc_1800208BD
0x180020847  mov     rdx, [rbp+var_30]
0x18002084b  cmp     dword ptr [rdx+6A4h], 1
0x180020852  jnz     loc_1800208EB
0x180020858  mov     ecx, [rdx+4C4h]
0x18002085e  lea     r8, [rdx+5BAh]; unsigned __int16 *
0x180020865  mov     rax, [rbp+arg_28]
0x180020869  mov     [rax], ecx
0x18002086b  xor     ecx, ecx
0x18002086d  mov     eax, [rdx+5A4h]
0x180020873  mov     edx, 100h; unsigned __int64
0x180020878  sub     eax, 4
0x18002087b  cmp     eax, 1
0x18002087e  mov     rax, [rbp+arg_20]
0x180020882  setbe   cl
0x180020885  mov     [rax], ecx
0x180020887  mov     rcx, rsi; unsigned __int16 *
0x18002088a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002088f  mov     ebx, eax
0x180020891  jmp     short loc_1800208E7
0x180020893  mov     rcx, cs:WPP_GLOBAL_Control
0x18002089a  cmp     rcx, r12
0x18002089d  jz      short loc_1800208E7
0x18002089f  test    byte ptr [rcx+1Ch], 1
0x1800208a3  jz      short loc_1800208C4
0x1800208a5  mov     rcx, [rcx+10h]
0x1800208a9  lea     r8, WPP_edb4701937c33b484ee7d731345f6be9_Traceguids
0x1800208b0  mov     edx, 39h ; '9'
0x1800208b5  mov     r9d, ebx
0x1800208b8  call    WPP_SF_d
0x1800208bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800208c4  cmp     rcx, r12
0x1800208c7  jz      short loc_1800208E7
0x1800208c9  test    byte ptr [rcx+1Ch], 1
0x1800208cd  jz      short loc_1800208E7
0x1800208cf  mov     rcx, [rcx+10h]
0x1800208d3  lea     r8, WPP_edb4701937c33b484ee7d731345f6be9_Traceguids
0x1800208da  mov     edx, 3Ah ; ':'
0x1800208df  mov     r9d, ebx
0x1800208e2  call    WPP_SF_d
0x1800208e7  mov     rdx, [rbp+var_30]
0x1800208eb  mov     [rbp+var_30], 0
0x1800208f3  test    rdx, rdx
0x1800208f6  jz      short loc_180020901
0x1800208f8  mov     rcx, rdx
0x1800208fb  call    cs:__imp_WwanFreeMemory
0x180020901  lea     rcx, [rbp+var_28]
0x180020905  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x18002090a  lea     r11, [rsp+70h+var_s0]
0x18002090f  mov     eax, ebx
0x180020911  mov     rbx, [r11+28h]
0x180020915  mov     rsi, [r11+30h]
0x180020919  mov     rsp, r11
0x18002091c  pop     r12
0x18002091e  pop     rdi
0x18002091f  pop     rbp
0x180020920  retn
```
