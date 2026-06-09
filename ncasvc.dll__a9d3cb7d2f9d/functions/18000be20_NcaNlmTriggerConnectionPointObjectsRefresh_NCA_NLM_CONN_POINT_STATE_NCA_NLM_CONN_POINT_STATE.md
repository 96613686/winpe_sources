# NcaNlmTriggerConnectionPointObjectsRefresh(NCA_NLM_CONN_POINT_STATE *,NCA_NLM_CONN_POINT_STATE *)

- ea: `0x18000be20`
- end: `0x18000bfd9`
- name: `?NcaNlmTriggerConnectionPointObjectsRefresh@@YAJPEAUNCA_NLM_CONN_POINT_STATE@@0@Z`
- size: `441`
- prototype: `__int64 __fastcall(struct NCA_NLM_CONN_POINT_STATE *, struct NCA_NLM_CONN_POINT_STATE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c1d0`

## callees

- `0x1800043bc`
- `0x180004f34`
- `0x18000bb90`
- `0x18000be20`
- `0x18000c174`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000be4e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000be4e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000befe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000befe`

## pseudocode

```c
__int64 __fastcall NcaNlmTriggerConnectionPointObjectsRefresh(
        struct NCA_NLM_CONN_POINT_STATE *a1,
        struct NCA_NLM_CONN_POINT_STATE *a2)
{
  DWORD v4; // eax
  struct _tag_NCA_CANCELABLE_LOCK *v5; // rcx
  HRESULT Instance; // ebx
  struct _tag_NCA_CANCELABLE_LOCK *v7; // rcx
  __int64 v8; // rdx

  _InterlockedIncrement(&dword_180028AE8);
  v4 = WaitForMultipleObjects(2u, &gNcaMain, 0, 0xFFFFFFFF);
  if ( v4 )
  {
    if ( v4 != 1 )
      goto LABEL_4;
    NcaNlmTriggerConnectionStateUnadviceRelease(a1);
    NcaNlmTriggerConnectionStateUnadviceRelease(a2);
    if ( gNcaNlmTriggerComp )
    {
      ((void (__fastcall *)(struct INetworkListManager *))gNcaNlmTriggerComp->lpVtbl->Release)(gNcaNlmTriggerComp);
      gNcaNlmTriggerComp = 0;
    }
    Instance = CoCreateInstance(
                 &CLSID_NetworkListManager,
                 0,
                 1u,
                 &IID_INetworkListManager,
                 (LPVOID *)&gNcaNlmTriggerComp);
    if ( Instance >= 0 )
    {
      Instance = GetConnectionPoints(gNcaNlmTriggerComp, &IID_INetworkEvents, (struct IConnectionPoint **)a1);
      if ( Instance >= 0 )
      {
        Instance = GetConnectionPoints(
                     gNcaNlmTriggerComp,
                     &IID_INetworkListManagerEvents,
                     (struct IConnectionPoint **)a2);
        if ( Instance >= 0 )
          goto LABEL_22;
        v7 = (struct _tag_NCA_CANCELABLE_LOCK *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_22;
        v8 = 26;
      }
      else
      {
        v7 = (struct _tag_NCA_CANCELABLE_LOCK *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_22;
        v8 = 25;
      }
    }
    else
    {
      v7 = (struct _tag_NCA_CANCELABLE_LOCK *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_22;
      v8 = 24;
    }
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_e3f5ab3ee88d3b7229a13de75aa7d1b1_Traceguids, (unsigned int)Instance);
LABEL_22:
    NcaReleaseCancelableLock(v7);
    return (unsigned int)Instance;
  }
  NcaReleaseCancelableLock(v5);
LABEL_4:
  Instance = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_e3f5ab3ee88d3b7229a13de75aa7d1b1_Traceguids, 1115);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000be20  mov     [rsp+arg_0], rbx
0x18000be25  mov     [rsp+arg_8], rsi
0x18000be2a  push    rdi
0x18000be2b  sub     rsp, 30h
0x18000be2f  mov     rsi, rdx
0x18000be32  mov     rdi, rcx
0x18000be35  lock inc cs:dword_180028AE8
0x18000be3c  xor     r8d, r8d; bWaitAll
0x18000be3f  lea     rdx, ?gNcaMain@@3UNCA_MAIN_COMPONENT_@@A; lpHandles
0x18000be46  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000be4a  lea     ecx, [r8+2]; nCount
0x18000be4e  call    cs:__imp_WaitForMultipleObjects
0x18000be55  nop     dword ptr [rax+rax+00h]
0x18000be5a  test    eax, eax
0x18000be5c  jnz     short loc_18000BE65
0x18000be5e  call    ?NcaReleaseCancelableLock@@YAXPEAU_tag_NCA_CANCELABLE_LOCK@@@Z; NcaReleaseCancelableLock(_tag_NCA_CANCELABLE_LOCK *)
0x18000be63  jmp     short loc_18000BE6A
0x18000be65  cmp     eax, 1
0x18000be68  jz      short loc_18000BEAB
0x18000be6a  xor     ebx, ebx
0x18000be6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be73  lea     rax, WPP_GLOBAL_Control
0x18000be7a  cmp     rcx, rax
0x18000be7d  jz      loc_18000BFC6
0x18000be83  test    byte ptr [rcx+1Ch], 1
0x18000be87  jz      loc_18000BFC6
0x18000be8d  mov     rcx, [rcx+10h]
0x18000be91  lea     edx, [rbx+17h]
0x18000be94  mov     r9d, 45Bh
0x18000be9a  lea     r8, WPP_e3f5ab3ee88d3b7229a13de75aa7d1b1_Traceguids
0x18000bea1  call    WPP_SF_d
0x18000bea6  jmp     loc_18000BFC6
0x18000beab  mov     rcx, rdi; struct NCA_NLM_CONN_POINT_STATE *
0x18000beae  call    ?NcaNlmTriggerConnectionStateUnadviceRelease@@YAXPEAUNCA_NLM_CONN_POINT_STATE@@@Z; NcaNlmTriggerConnectionStateUnadviceRelease(NCA_NLM_CONN_POINT_STATE *)
0x18000beb3  mov     rcx, rsi; struct NCA_NLM_CONN_POINT_STATE *
0x18000beb6  call    ?NcaNlmTriggerConnectionStateUnadviceRelease@@YAXPEAUNCA_NLM_CONN_POINT_STATE@@@Z; NcaNlmTriggerConnectionStateUnadviceRelease(NCA_NLM_CONN_POINT_STATE *)
0x18000bebb  mov     rcx, cs:?gNcaNlmTriggerComp@@3UNCA_NLM_TRIGGER_COMP_@@A; NCA_NLM_TRIGGER_COMP_ gNcaNlmTriggerComp
0x18000bec2  test    rcx, rcx
0x18000bec5  jz      short loc_18000BEDE
0x18000bec7  mov     rax, [rcx]
0x18000beca  mov     rax, [rax+10h]
0x18000bece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bed3  mov     cs:?gNcaNlmTriggerComp@@3UNCA_NLM_TRIGGER_COMP_@@A, 0; NCA_NLM_TRIGGER_COMP_ gNcaNlmTriggerComp
0x18000bede  xor     edx, edx; pUnkOuter
0x18000bee0  lea     rax, ?gNcaNlmTriggerComp@@3UNCA_NLM_TRIGGER_COMP_@@A; NCA_NLM_TRIGGER_COMP_ gNcaNlmTriggerComp
0x18000bee7  lea     r9, IID_INetworkListManager; riid
0x18000beee  mov     [rsp+38h+ppv], rax; ppv
0x18000bef3  lea     rcx, CLSID_NetworkListManager; rclsid
0x18000befa  lea     r8d, [rdx+1]; dwClsContext
0x18000befe  call    cs:__imp_CoCreateInstance
0x18000bf05  nop     dword ptr [rax+rax+00h]
0x18000bf0a  mov     ebx, eax
0x18000bf0c  test    eax, eax
0x18000bf0e  jns     short loc_18000BF38
0x18000bf10  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf17  lea     rax, WPP_GLOBAL_Control
0x18000bf1e  cmp     rcx, rax
0x18000bf21  jz      loc_18000BFC1
0x18000bf27  test    byte ptr [rcx+1Ch], 1
0x18000bf2b  jz      loc_18000BFC1
0x18000bf31  mov     edx, 18h
0x18000bf36  jmp     short loc_18000BFAE
0x18000bf38  mov     rcx, cs:?gNcaNlmTriggerComp@@3UNCA_NLM_TRIGGER_COMP_@@A; struct INetworkListManager *
0x18000bf3f  lea     rdx, IID_INetworkEvents; struct _GUID *
0x18000bf46  mov     r8, rdi; struct IConnectionPoint **
0x18000bf49  call    ?GetConnectionPoints@@YAJPEAUINetworkListManager@@AEBU_GUID@@PEAPEAUIConnectionPoint@@@Z; GetConnectionPoints(INetworkListManager *,_GUID const &,IConnectionPoint * *)
0x18000bf4e  mov     ebx, eax
0x18000bf50  test    eax, eax
0x18000bf52  jns     short loc_18000BF74
0x18000bf54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf5b  lea     rax, WPP_GLOBAL_Control
0x18000bf62  cmp     rcx, rax
0x18000bf65  jz      short loc_18000BFC1
0x18000bf67  test    byte ptr [rcx+1Ch], 1
0x18000bf6b  jz      short loc_18000BFC1
0x18000bf6d  mov     edx, 19h
0x18000bf72  jmp     short loc_18000BFAE
0x18000bf74  mov     rcx, cs:?gNcaNlmTriggerComp@@3UNCA_NLM_TRIGGER_COMP_@@A; struct INetworkListManager *
0x18000bf7b  lea     rdx, IID_INetworkListManagerEvents; struct _GUID *
0x18000bf82  mov     r8, rsi; struct IConnectionPoint **
0x18000bf85  call    ?GetConnectionPoints@@YAJPEAUINetworkListManager@@AEBU_GUID@@PEAPEAUIConnectionPoint@@@Z; GetConnectionPoints(INetworkListManager *,_GUID const &,IConnectionPoint * *)
0x18000bf8a  mov     ebx, eax
0x18000bf8c  test    eax, eax
0x18000bf8e  jns     short loc_18000BFC1
0x18000bf90  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf97  lea     rax, WPP_GLOBAL_Control
0x18000bf9e  cmp     rcx, rax
0x18000bfa1  jz      short loc_18000BFC1
0x18000bfa3  test    byte ptr [rcx+1Ch], 1
0x18000bfa7  jz      short loc_18000BFC1
0x18000bfa9  mov     edx, 1Ah
0x18000bfae  mov     rcx, [rcx+10h]
0x18000bfb2  lea     r8, WPP_e3f5ab3ee88d3b7229a13de75aa7d1b1_Traceguids
0x18000bfb9  mov     r9d, ebx
0x18000bfbc  call    WPP_SF_d
0x18000bfc1  call    ?NcaReleaseCancelableLock@@YAXPEAU_tag_NCA_CANCELABLE_LOCK@@@Z; NcaReleaseCancelableLock(_tag_NCA_CANCELABLE_LOCK *)
0x18000bfc6  mov     rsi, [rsp+38h+arg_8]
0x18000bfcb  mov     eax, ebx
0x18000bfcd  mov     rbx, [rsp+38h+arg_0]
0x18000bfd2  add     rsp, 30h
0x18000bfd6  pop     rdi
0x18000bfd7  retn
```
