# DAS::DevnodeManagment::DevnodeManager::StartDevnodeManagementForStore(Microsoft::WRL::ComPtr<Windows::Devices::Pnp::Internal::PnpObjectStore> &,ushort const *)

- ea: `0x18003961c`
- end: `0x1800397ed`
- name: `?StartDevnodeManagementForStore@DevnodeManager@DevnodeManagment@DAS@@AEAAJAEAV?$ComPtr@VPnpObjectStore@Internal@Pnp@Devices@Windows@@@WRL@Microsoft@@PEBG@Z`
- size: `465`
- prototype: `__int64 __fastcall(DAS::DevnodeManagment::DevnodeManager *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800395b0`
- `0x18003997c`

## callees

- `0x1800074c0`
- `0x180013be0`
- `0x18001f654`
- `0x180027b2c`
- `0x18002a948`
- `0x18003961c`
- `0x18003bc80`
- `0x180045df0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039727`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003973f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003978a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800397a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039727`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003973f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003978a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800397a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039735`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003974d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039798`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800397b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039735`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003974d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039798`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800397b0`

## string_xrefs

- `0x180039672`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x180039772`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::DevnodeManager::StartDevnodeManagementForStore(
        DAS::DevnodeManagment::DevnodeManager *this,
        Windows::Devices::Pnp::Internal::PnpObjectStore **a2,
        const unsigned __int16 *a3)
{
  Windows::Devices::Pnp::Internal::PnpObjectStore *v6; // rcx
  int Ids; // eax
  unsigned __int16 *i; // rdi
  Windows::Devices::Pnp::Internal::PnpObjectStore *v9; // rcx
  int Property; // eax
  int started; // eax
  unsigned int v12; // esi
  WCHAR *v13; // rbx
  HANDLE v14; // rax
  PVOID v15; // rbx
  HANDLE v16; // rax
  __int64 v17; // rax
  WCHAR *LocaleName; // rbx
  HANDLE ProcessHeap; // rax
  PVOID Buffer; // rbx
  HANDLE v21; // rax
  int v23; // [rsp+20h] [rbp-59h]
  unsigned __int16 *v24; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v25; // [rsp+38h] [rbp-41h] BYREF
  struct _DEVPROPERTY v26; // [rsp+40h] [rbp-39h] BYREF
  struct _DEVPROPCOMPKEY v27; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v25 = 0;
  v6 = *a2;
  v24 = 0;
  Ids = Windows::Devices::Pnp::Internal::PnpObjectStore::GetIds(v6, &v25, &v24);
  if ( Ids < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA0,
      (int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
      (const char *)(unsigned int)Ids);
  for ( i = v24; i && *i; i += v17 + 1 )
  {
    v9 = *a2;
    v27.Key.fmtid = (DEVPROPGUID)DEVPKEY_Aep_IsAssociatedPerUser;
    v27.Key.pid = 20;
    v27.Store = DEVPROP_STORE_SYSTEM;
    v27.LocaleName = 0;
    memset(&v26, 0, sizeof(v26));
    Property = Windows::Devices::Pnp::Internal::PnpObjectStore::GetProperty(v9, i, &v27, 0, &v26);
    if ( Property == -2147023728
      || Property >= 0 && v26.Type == 17 && v26.BufferSize == 1 && v26.Buffer && !*(_BYTE *)v26.Buffer )
    {
      started = DAS::DevnodeManagment::DevnodeManager::StartDevnodeManagement(this, i, a3, 0);
      v12 = started;
      if ( started < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB6,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
          (const char *)(unsigned int)started,
          v23);
        LocaleName = (WCHAR *)v26.CompKey.LocaleName;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, LocaleName);
        Buffer = v26.Buffer;
        v21 = GetProcessHeap();
        HeapFree(v21, 0, Buffer);
        goto LABEL_18;
      }
    }
    v13 = (WCHAR *)v26.CompKey.LocaleName;
    v14 = GetProcessHeap();
    HeapFree(v14, 0, v13);
    v15 = v26.Buffer;
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v15);
    v17 = -1;
    do
      ++v17;
    while ( i[v17] );
  }
  v12 = 0;
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v24);
  return v12;
}

```

## disassembly

```asm
0x18003961c  mov     [rsp-8+arg_18], rbx
0x180039621  push    rbp
0x180039622  push    rsi
0x180039623  push    rdi
0x180039624  push    r12
0x180039626  push    r13
0x180039628  push    r14
0x18003962a  push    r15
0x18003962c  lea     rbp, [rsp-27h]
0x180039631  sub     rsp, 0A0h
0x180039638  mov     rax, cs:__security_cookie
0x18003963f  xor     rax, rsp
0x180039642  mov     [rbp+57h+var_40], rax
0x180039646  mov     r14, rdx
0x180039649  mov     r12, r8
0x18003964c  mov     r15, rcx
0x18003964f  lea     r8, [rbp+57h+var_A0]; unsigned __int16 **
0x180039653  xor     r13d, r13d
0x180039656  lea     rdx, [rbp+57h+var_98]; unsigned int *
0x18003965a  mov     [rbp+57h+var_98], r13d
0x18003965e  mov     rcx, [r14]; this
0x180039661  mov     [rbp+57h+var_A0], r13
0x180039665  call    ?GetIds@PnpObjectStore@Internal@Pnp@Devices@Windows@@QEAAJPEAKPEAPEAG@Z; Windows::Devices::Pnp::Internal::PnpObjectStore::GetIds(ulong *,ushort * *)
0x18003966a  test    eax, eax
0x18003966c  jns     short loc_180039686
0x18003966e  mov     rcx, [rbp+5Fh]; this
0x180039672  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180039679  mov     r9d, eax; char *
0x18003967c  mov     edx, 0A0h; void *
0x180039681  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039686  mov     rdi, [rbp+57h+var_A0]
0x18003968a  mov     [rbp+57h+var_A0], rdi
0x18003968e  test    rdi, rdi
0x180039691  jz      loc_1800397B8
0x180039697  cmp     [rdi], r13w
0x18003969b  jz      loc_1800397B8
0x1800396a1  movups  xmm0, cs:DEVPKEY_Aep_IsAssociatedPerUser
0x1800396a8  mov     eax, cs:dword_18008DBE8
0x1800396ae  lea     r8, [rbp+57h+var_60]; struct _DEVPROPCOMPKEY *
0x1800396b2  mov     rcx, [r14]; this
0x1800396b5  xor     r9d, r9d; unsigned __int16 *
0x1800396b8  movups  xmmword ptr [rbp+57h+var_60.Key.fmtid.Data1], xmm0
0x1800396bc  mov     [rbp+57h+var_60.Key.pid], eax
0x1800396bf  lea     rax, [rbp+57h+var_90]
0x1800396c3  xorps   xmm0, xmm0
0x1800396c6  mov     [rbp+57h+var_60.Store], r13d
0x1800396ca  mov     rdx, rdi; unsigned __int16 *
0x1800396cd  mov     [rbp+57h+var_60.LocaleName], r13
0x1800396d1  movups  xmmword ptr [rbp+57h+var_90.CompKey.Key.fmtid.Data1], xmm0
0x1800396d5  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800396da  movups  xmmword ptr [rbp+57h+var_90.CompKey.Key.pid], xmm0
0x1800396de  movups  xmmword ptr [rbp+57h+var_90.Type], xmm0
0x1800396e2  call    ?GetProperty@PnpObjectStore@Internal@Pnp@Devices@Windows@@QEAAJPEBGPEBU_DEVPROPCOMPKEY@@0PEAU_DEVPROPERTY@@@Z; Windows::Devices::Pnp::Internal::PnpObjectStore::GetProperty(ushort const *,_DEVPROPCOMPKEY const *,ushort const *,_DEVPROPERTY *)
0x1800396e7  cmp     eax, 80070490h
0x1800396ec  jz      short loc_18003970C
0x1800396ee  test    eax, eax
0x1800396f0  js      short loc_180039723
0x1800396f2  cmp     [rbp+57h+var_90.Type], 11h
0x1800396f6  jnz     short loc_180039723
0x1800396f8  cmp     [rbp+57h+var_90.BufferSize], 1
0x1800396fc  jnz     short loc_180039723
0x1800396fe  mov     rax, [rbp+57h+var_90.Buffer]
0x180039702  test    rax, rax
0x180039705  jz      short loc_180039723
0x180039707  cmp     [rax], r13b
0x18003970a  jnz     short loc_180039723
0x18003970c  xor     r9d, r9d; void *
0x18003970f  mov     r8, r12; unsigned __int16 *
0x180039712  mov     rdx, rdi; unsigned __int16 *
0x180039715  mov     rcx, r15; this
0x180039718  call    ?StartDevnodeManagement@DevnodeManager@DevnodeManagment@DAS@@QEAAJPEBG0PEAX@Z; DAS::DevnodeManagment::DevnodeManager::StartDevnodeManagement(ushort const *,ushort const *,void *)
0x18003971d  mov     esi, eax
0x18003971f  test    eax, eax
0x180039721  js      short loc_18003976E
0x180039723  mov     rbx, [rbp+57h+var_90.CompKey.LocaleName]
0x180039727  call    cs:__imp_GetProcessHeap
0x18003972d  mov     r8, rbx; lpMem
0x180039730  xor     edx, edx; dwFlags
0x180039732  mov     rcx, rax; hHeap
0x180039735  call    cs:__imp_HeapFree
0x18003973b  mov     rbx, [rbp+57h+var_90.Buffer]
0x18003973f  call    cs:__imp_GetProcessHeap
0x180039745  mov     r8, rbx; lpMem
0x180039748  xor     edx, edx; dwFlags
0x18003974a  mov     rcx, rax; hHeap
0x18003974d  call    cs:__imp_HeapFree
0x180039753  or      rax, 0FFFFFFFFFFFFFFFFh
0x180039757  inc     rax
0x18003975a  cmp     [rdi+rax*2], r13w
0x18003975f  jnz     short loc_180039757
0x180039761  lea     rdi, [rdi+rax*2]
0x180039765  add     rdi, 2
0x180039769  jmp     loc_18003968E
0x18003976e  mov     rcx, [rbp+5Fh]; this
0x180039772  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180039779  mov     r9d, eax; char *
0x18003977c  mov     edx, 0B6h; void *
0x180039781  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039786  mov     rbx, [rbp+57h+var_90.CompKey.LocaleName]
0x18003978a  call    cs:__imp_GetProcessHeap
0x180039790  mov     r8, rbx; lpMem
0x180039793  xor     edx, edx; dwFlags
0x180039795  mov     rcx, rax; hHeap
0x180039798  call    cs:__imp_HeapFree
0x18003979e  mov     rbx, [rbp+57h+var_90.Buffer]
0x1800397a2  call    cs:__imp_GetProcessHeap
0x1800397a8  mov     r8, rbx; lpMem
0x1800397ab  xor     edx, edx; dwFlags
0x1800397ad  mov     rcx, rax; hHeap
0x1800397b0  call    cs:__imp_HeapFree
0x1800397b6  jmp     short loc_1800397BB
0x1800397b8  mov     esi, r13d
0x1800397bb  lea     rcx, [rbp+57h+var_A0]
0x1800397bf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800397c4  mov     eax, esi
0x1800397c6  mov     rcx, [rbp+57h+var_40]
0x1800397ca  xor     rcx, rsp; StackCookie
0x1800397cd  call    __security_check_cookie
0x1800397d2  mov     rbx, [rsp+0D0h+arg_18]
0x1800397da  add     rsp, 0A0h
0x1800397e1  pop     r15
0x1800397e3  pop     r14
0x1800397e5  pop     r13
0x1800397e7  pop     r12
0x1800397e9  pop     rdi
0x1800397ea  pop     rsi
0x1800397eb  pop     rbp
0x1800397ec  retn
```
