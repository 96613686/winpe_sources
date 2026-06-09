# UpdateQoSPolicies

- ea: `0x140011940`
- end: `0x140011bcb`
- name: `UpdateQoSPolicies`
- size: `651`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callees

- `0x14000a290`
- `0x140011410`
- `0x140011940`
- `0x140013940`
- `0x140013b68`
- `0x140013bc4`
- `0x1400161f0`
- `0x140016700`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x140011acf`
- `ntoskrnl!KeClearEvent` at `0x140011acf`
- `ntoskrnl!KeInitializeEvent` at `0x140011a41`
- `ntoskrnl!KeInitializeEvent` at `0x140011a41`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400119d7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400119d7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400119ec`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400119ec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011b82`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011b82`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011b8e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011b8e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011abc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140011abc`
- `NDIS!NdisCoOidRequest` at `0x140011a92`
- `NDIS!NdisCoOidRequest` at `0x140011a92`
- `NDIS!NdisSetEvent` at `0x140011af0`
- `NDIS!NdisSetEvent` at `0x140011af0`

## pseudocode

```c
__int64 __fastcall UpdateQoSPolicies(_DWORD *a1, unsigned int a2)
{
  NDIS_STATUS MiniportBindingHandle; // ebx
  __int64 i; // rdi
  volatile signed __int32 *QoSPolicyFromPolicyIndex; // rax
  __int64 v7; // rcx
  __int64 v8; // r14
  __int64 v9; // r14
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  _QWORD OidRequest[44]; // [rsp+30h] [rbp-D0h] BYREF

  memset(&OidRequest[2], 0, 0x148u);
  OidRequest[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids);
  }
  if ( a2 < 0x1C || *a1 > 2u )
    return (unsigned int)-1073741811;
  MiniportBindingHandle = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&QoSPolicyResourceLock, 1u);
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *a1 )
      goto LABEL_26;
    QoSPolicyFromPolicyIndex = BwcFindQoSPolicyFromPolicyIndex(a1[3 * i + 3]);
    v8 = (__int64)QoSPolicyFromPolicyIndex;
    if ( QoSPolicyFromPolicyIndex )
      break;
    MiniportBindingHandle = GetMiniportBindingHandle(v7, OidRequest);
    if ( MiniportBindingHandle )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v11 = 14;
LABEL_25:
        WPP_SF_(v10->AttachedDevice, v11, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids);
        goto LABEL_26;
      }
      goto LABEL_26;
    }
    OidRequest[4] = 1;
    KeInitializeEvent((PRKEVENT)&OidRequest[40], NotificationEvent, 0);
    OidRequest[7] = 0;
    v9 = OidRequest[0];
    OidRequest[8] = 0x100EC0196LL;
    LODWORD(OidRequest[12]) = 67175043;
    OidRequest[13] = a1;
    LODWORD(OidRequest[14]) = 28;
    MiniportBindingHandle = NdisCoOidRequest(
                              *(NDIS_HANDLE *)(OidRequest[0] + 56LL),
                              (NDIS_HANDLE)OidRequest[6],
                              0,
                              0,
                              (PNDIS_OID_REQUEST)&OidRequest[8]);
    if ( MiniportBindingHandle == 259 )
    {
      KeWaitForSingleObject(&OidRequest[40], Executive, 0, 1u, 0);
      MiniportBindingHandle = OidRequest[39];
      KeClearEvent((PRKEVENT)&OidRequest[40]);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 16), 0xFFFFFFFF) == 1 )
      NdisSetEvent((PNDIS_EVENT)(v9 + 552));
LABEL_16:
    ;
  }
  MiniportBindingHandle = BwcUpdateQoSPolicy(QoSPolicyFromPolicyIndex, (unsigned int)a1[3 * i + 1]);
  BwcDereferenceQoSPolicy(v8);
  if ( MiniportBindingHandle >= 0 )
    goto LABEL_16;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    v11 = 15;
    goto LABEL_25;
  }
LABEL_26:
  ExReleaseResourceLite(&QoSPolicyResourceLock);
  KeLeaveCriticalRegion();
  return (unsigned int)MiniportBindingHandle;
}

```

## disassembly

```asm
0x140011940  mov     [rsp-8+arg_8], rbx
0x140011945  mov     [rsp-8+arg_10], rsi
0x14001194a  push    rbp
0x14001194b  push    rdi
0x14001194c  push    r14
0x14001194e  lea     rbp, [rsp-0A0h]
0x140011956  sub     rsp, 1A0h
0x14001195d  mov     rax, cs:__security_cookie
0x140011964  xor     rax, rsp
0x140011967  mov     [rbp+0B0h+var_20], rax
0x14001196e  mov     ebx, edx
0x140011970  mov     rsi, rcx
0x140011973  xor     edx, edx; Val
0x140011975  lea     rcx, [rsp+1B0h+var_170]; void *
0x14001197a  mov     r8d, 148h; Size
0x140011980  call    memset
0x140011985  mov     [rsp+1B0h+var_180], 0
0x14001198e  mov     rcx, cs:WPP_GLOBAL_Control
0x140011995  lea     rax, WPP_GLOBAL_Control
0x14001199c  cmp     rcx, rax
0x14001199f  jz      short loc_1400119C3
0x1400119a1  mov     eax, [rcx+2Ch]
0x1400119a4  test    al, 20h
0x1400119a6  jz      short loc_1400119C3
0x1400119a8  cmp     byte ptr [rcx+29h], 4
0x1400119ac  jb      short loc_1400119C3
0x1400119ae  mov     rcx, [rcx+18h]
0x1400119b2  lea     r8, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids
0x1400119b9  mov     edx, 0Dh
0x1400119be  call    WPP_SF_
0x1400119c3  cmp     ebx, 1Ch
0x1400119c6  jb      loc_140011B9C
0x1400119cc  cmp     dword ptr [rsi], 2
0x1400119cf  ja      loc_140011B9C
0x1400119d5  xor     ebx, ebx
0x1400119d7  call    cs:__imp_KeEnterCriticalRegion
0x1400119de  nop     dword ptr [rax+rax+00h]
0x1400119e3  mov     dl, 1; Wait
0x1400119e5  lea     rcx, QoSPolicyResourceLock; Resource
0x1400119ec  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400119f3  nop     dword ptr [rax+rax+00h]
0x1400119f8  xor     edi, edi
0x1400119fa  cmp     edi, [rsi]
0x1400119fc  jnb     loc_140011B7B
0x140011a02  lea     rbx, [rdi+rdi*2]
0x140011a06  mov     ecx, [rsi+rbx*4+0Ch]
0x140011a0a  call    BwcFindQoSPolicyFromPolicyIndex
0x140011a0f  mov     r14, rax
0x140011a12  test    rax, rax
0x140011a15  jnz     loc_140011AFE
0x140011a1b  lea     rdx, [rsp+1B0h+var_180]
0x140011a20  call    GetMiniportBindingHandle
0x140011a25  mov     ebx, eax
0x140011a27  test    eax, eax
0x140011a29  jnz     loc_140011B1F
0x140011a2f  xor     r8d, r8d; State
0x140011a32  mov     [rsp+1B0h+var_160], 1
0x140011a3b  xor     edx, edx; Type
0x140011a3d  lea     rcx, [rbp+0B0h+Event]; Event
0x140011a41  call    cs:__imp_KeInitializeEvent
0x140011a48  nop     dword ptr [rax+rax+00h]
0x140011a4d  mov     rdx, [rsp+1B0h+NdisAfHandle]; NdisAfHandle
0x140011a52  lea     rax, [rsp+1B0h+var_140]
0x140011a57  mov     [rsp+1B0h+var_148], r14
0x140011a5c  xor     r9d, r9d; NdisPartyHandle
0x140011a5f  mov     r14, [rsp+1B0h+var_180]
0x140011a64  xor     r8d, r8d; NdisVcHandle
0x140011a67  mov     dword ptr [rsp+1B0h+var_140.Header.Type], 0EC0196h
0x140011a6f  mov     [rsp+1B0h+var_140.RequestType], 1
0x140011a77  mov     dword ptr [rbp+0B0h+var_140.DATA], 4010283h
0x140011a7e  mov     qword ptr [rbp+0B0h+var_140.DATA+8], rsi
0x140011a82  mov     dword ptr [rbp+0B0h+var_140.DATA+10h], 1Ch
0x140011a89  mov     rcx, [r14+38h]; NdisBindingHandle
0x140011a8d  mov     [rsp+1B0h+OidRequest], rax; OidRequest
0x140011a92  call    cs:__imp_NdisCoOidRequest
0x140011a99  nop     dword ptr [rax+rax+00h]
0x140011a9e  mov     ebx, eax
0x140011aa0  cmp     eax, 103h
0x140011aa5  jnz     short loc_140011ADB
0x140011aa7  mov     r9b, 1; Alertable
0x140011aaa  mov     [rsp+1B0h+OidRequest], 0; Timeout
0x140011ab3  xor     r8d, r8d; WaitMode
0x140011ab6  lea     rcx, [rbp+0B0h+Event]; Object
0x140011aba  xor     edx, edx; WaitReason
0x140011abc  call    cs:__imp_KeWaitForSingleObject
0x140011ac3  nop     dword ptr [rax+rax+00h]
0x140011ac8  mov     ebx, [rbp+0B0h+var_48]
0x140011acb  lea     rcx, [rbp+0B0h+Event]; Event
0x140011acf  call    cs:__imp_KeClearEvent
0x140011ad6  nop     dword ptr [rax+rax+00h]
0x140011adb  or      eax, 0FFFFFFFFh
0x140011ade  lock xadd [r14+10h], eax
0x140011ae4  cmp     eax, 1
0x140011ae7  jnz     short loc_140011B18
0x140011ae9  lea     rcx, [r14+228h]; Event
0x140011af0  call    cs:__imp_NdisSetEvent
0x140011af7  nop     dword ptr [rax+rax+00h]
0x140011afc  jmp     short loc_140011B18
0x140011afe  mov     edx, [rsi+rbx*4+4]
0x140011b02  mov     rcx, r14
0x140011b05  call    BwcUpdateQoSPolicy
0x140011b0a  mov     rcx, r14
0x140011b0d  mov     ebx, eax
0x140011b0f  call    BwcDereferenceQoSPolicy
0x140011b14  test    ebx, ebx
0x140011b16  js      short loc_140011B46
0x140011b18  inc     edi
0x140011b1a  jmp     loc_1400119FA
0x140011b1f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b26  lea     rax, WPP_GLOBAL_Control
0x140011b2d  cmp     rcx, rax
0x140011b30  jz      short loc_140011B7B
0x140011b32  mov     eax, [rcx+2Ch]
0x140011b35  test    al, 20h
0x140011b37  jz      short loc_140011B7B
0x140011b39  cmp     byte ptr [rcx+29h], 3
0x140011b3d  jb      short loc_140011B7B
0x140011b3f  mov     edx, 0Eh
0x140011b44  jmp     short loc_140011B6B
0x140011b46  mov     rcx, cs:WPP_GLOBAL_Control
0x140011b4d  lea     rax, WPP_GLOBAL_Control
0x140011b54  cmp     rcx, rax
0x140011b57  jz      short loc_140011B7B
0x140011b59  mov     eax, [rcx+2Ch]
0x140011b5c  test    al, 20h
0x140011b5e  jz      short loc_140011B7B
0x140011b60  cmp     byte ptr [rcx+29h], 3
0x140011b64  jb      short loc_140011B7B
0x140011b66  mov     edx, 0Fh
0x140011b6b  mov     rcx, [rcx+18h]
0x140011b6f  lea     r8, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids
0x140011b76  call    WPP_SF_
0x140011b7b  lea     rcx, QoSPolicyResourceLock; Resource
0x140011b82  call    cs:__imp_ExReleaseResourceLite
0x140011b89  nop     dword ptr [rax+rax+00h]
0x140011b8e  call    cs:__imp_KeLeaveCriticalRegion
0x140011b95  nop     dword ptr [rax+rax+00h]
0x140011b9a  jmp     short loc_140011BA1
0x140011b9c  mov     ebx, 0C000000Dh
0x140011ba1  mov     eax, ebx
0x140011ba3  mov     rcx, [rbp+0B0h+var_20]
0x140011baa  xor     rcx, rsp; StackCookie
0x140011bad  call    __security_check_cookie
0x140011bb2  lea     r11, [rsp+1B0h+var_10]
0x140011bba  mov     rbx, [r11+28h]
0x140011bbe  mov     rsi, [r11+30h]
0x140011bc2  mov     rsp, r11
0x140011bc5  pop     r14
0x140011bc7  pop     rdi
0x140011bc8  pop     rbp
0x140011bc9  retn
```
