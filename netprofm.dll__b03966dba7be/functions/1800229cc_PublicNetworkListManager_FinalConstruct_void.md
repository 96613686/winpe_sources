# PublicNetworkListManager::FinalConstruct(void)

- ea: `0x1800229cc`
- end: `0x180022b25`
- name: `?FinalConstruct@PublicNetworkListManager@@QEAAJXZ`
- size: `345`
- prototype: `__int64 __fastcall(PublicNetworkListManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017154`
- `0x180017254`

## callees

- `0x180006770`
- `0x180006810`
- `0x180021dd0`
- `0x1800229cc`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a0d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a1a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a27`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a34`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a41`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a4e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a5b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a68`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a75`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a0d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a1a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a27`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a34`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a41`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a4e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a5b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a68`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180022a75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022ae8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022ae8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022ad8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022ad8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022a9b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022a9b`

## pseudocode

```c
__int64 __fastcall PublicNetworkListManager::FinalConstruct(PublicNetworkListManager *this)
{
  int Instance; // ebx
  _QWORD *v3; // rdi
  __int64 v4; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rdi

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids);
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 7);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 336));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 504));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 448));
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 14);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 664));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 616));
  Instance = CoCreateInstance(
               &CLSID_StdGlobalInterfaceTable,
               0,
               1u,
               &GUID_00000146_0000_0000_c000_000000000046,
               (LPVOID *)this + 28);
  if ( !Instance )
  {
    v3 = (_QWORD *)((char *)this + 216);
    Instance = ATL::CComObject<PublicNetworkListManager::PrivateNetworkEventSync>::CreateInstance((PublicNetworkListManager::PrivateNetworkEventSync **)this + 27);
    if ( Instance >= 0 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 8LL))(*v3);
      v4 = *v3;
      v5 = (struct _RTL_CRITICAL_SECTION *)(*v3 + 608LL);
      EnterCriticalSection(v5);
      *(_QWORD *)(v4 + 648) = this;
      LeaveCriticalSection(v5);
      Instance = 0;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids,
      (unsigned int)Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800229cc  push    rbx
0x1800229ce  push    rbp
0x1800229cf  push    rsi
0x1800229d0  push    rdi
0x1800229d1  sub     rsp, 38h
0x1800229d5  mov     rsi, rcx
0x1800229d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229df  lea     rbp, WPP_GLOBAL_Control
0x1800229e6  cmp     rcx, rbp
0x1800229e9  jz      short loc_180022A06
0x1800229eb  test    byte ptr [rcx+1Ch], 8
0x1800229ef  jz      short loc_180022A06
0x1800229f1  mov     rcx, [rcx+10h]
0x1800229f5  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x1800229fc  mov     edx, 0Ch
0x180022a01  call    WPP_SF_
0x180022a06  lea     rcx, [rsi+118h]; lpCriticalSection
0x180022a0d  call    cs:__imp_InitializeCriticalSection
0x180022a13  lea     rcx, [rsi+150h]; lpCriticalSection
0x180022a1a  call    cs:__imp_InitializeCriticalSection
0x180022a20  lea     rcx, [rsi+188h]; lpCriticalSection
0x180022a27  call    cs:__imp_InitializeCriticalSection
0x180022a2d  lea     rcx, [rsi+1F8h]; lpCriticalSection
0x180022a34  call    cs:__imp_InitializeCriticalSection
0x180022a3a  lea     rcx, [rsi+1C0h]; lpCriticalSection
0x180022a41  call    cs:__imp_InitializeCriticalSection
0x180022a47  lea     rcx, [rsi+230h]; lpCriticalSection
0x180022a4e  call    cs:__imp_InitializeCriticalSection
0x180022a54  lea     rcx, [rsi+298h]; lpCriticalSection
0x180022a5b  call    cs:__imp_InitializeCriticalSection
0x180022a61  lea     rcx, [rsi+0E8h]; lpCriticalSection
0x180022a68  call    cs:__imp_InitializeCriticalSection
0x180022a6e  lea     rcx, [rsi+268h]; lpCriticalSection
0x180022a75  call    cs:__imp_InitializeCriticalSection
0x180022a7b  xor     edx, edx; pUnkOuter
0x180022a7d  lea     rax, [rsi+0E0h]
0x180022a84  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180022a8b  mov     [rsp+58h+ppv], rax; ppv
0x180022a90  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180022a97  lea     r8d, [rdx+1]; dwClsContext
0x180022a9b  call    cs:__imp_CoCreateInstance
0x180022aa1  mov     ebx, eax
0x180022aa3  test    eax, eax
0x180022aa5  jnz     short loc_180022AF0
0x180022aa7  lea     rdi, [rsi+0D8h]
0x180022aae  mov     rcx, rdi
0x180022ab1  call    ?CreateInstance@?$CComObject@VPrivateNetworkEventSync@PublicNetworkListManager@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<PublicNetworkListManager::PrivateNetworkEventSync>::CreateInstance(ATL::CComObject<PublicNetworkListManager::PrivateNetworkEventSync> * *)
0x180022ab6  mov     ebx, eax
0x180022ab8  test    eax, eax
0x180022aba  js      short loc_180022AF0
0x180022abc  mov     rcx, [rdi]
0x180022abf  mov     rax, [rcx]
0x180022ac2  mov     rax, [rax+8]
0x180022ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022acb  mov     rbx, [rdi]
0x180022ace  lea     rdi, [rbx+260h]
0x180022ad5  mov     rcx, rdi; lpCriticalSection
0x180022ad8  call    cs:__imp_EnterCriticalSection
0x180022ade  mov     rcx, rdi; lpCriticalSection
0x180022ae1  mov     [rbx+288h], rsi
0x180022ae8  call    cs:__imp_LeaveCriticalSection
0x180022aee  xor     ebx, ebx
0x180022af0  mov     rcx, cs:WPP_GLOBAL_Control
0x180022af7  cmp     rcx, rbp
0x180022afa  jz      short loc_180022B1A
0x180022afc  test    byte ptr [rcx+1Ch], 8
0x180022b00  jz      short loc_180022B1A
0x180022b02  mov     rcx, [rcx+10h]
0x180022b06  lea     r8, WPP_2a09da79722d3917dcee4c06fb5ea945_Traceguids
0x180022b0d  mov     edx, 0Dh
0x180022b12  mov     r9d, ebx
0x180022b15  call    WPP_SF_d
0x180022b1a  mov     eax, ebx
0x180022b1c  add     rsp, 38h
0x180022b20  pop     rdi
0x180022b21  pop     rsi
0x180022b22  pop     rbp
0x180022b23  pop     rbx
0x180022b24  retn
```
