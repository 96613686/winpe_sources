# CscCreateLogicalView

- ea: `0x140075770`
- end: `0x1400759c3`
- name: `CscCreateLogicalView`
- size: `595`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140018930`
- `0x1400190ec`
- `0x14001ac1c`
- `0x140020634`
- `0x1400709b0`
- `0x140075770`
- `0x140075f70`
- `0x1400761e0`
- `0x140076a9c`
- `0x140076afc`
- `0x140076f00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400757ea`
- `ntoskrnl!ExAllocatePool2` at `0x1400757ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075969`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075969`
- `ntoskrnl!KeInitializeEvent` at `0x140075834`
- `ntoskrnl!KeInitializeEvent` at `0x140075834`
- `ntoskrnl!ExInitializeResourceLite` at `0x140075847`
- `ntoskrnl!ExInitializeResourceLite` at `0x140075847`
- `rdbss!RxQueryNetRootCachingMode` at `0x1400757ac`
- `rdbss!RxQueryNetRootCachingMode` at `0x1400757ac`

## pseudocode

```c
__int64 __fastcall CscCreateLogicalView(__int64 a1)
{
  _QWORD *v1; // rbp
  __int64 v3; // rsi
  struct _DEVICE_OBJECT *AttachedDevice; // rbx
  int NetRootCachingMode; // eax
  __int64 v6; // r15
  __int64 Pool2; // rax
  _DWORD *v8; // rdi
  unsigned int v9; // ebx
  _QWORD *v10; // rax
  bool v11; // r8
  int v12; // eax

  v1 = *(_QWORD **)a1;
  v3 = *(_QWORD *)(a1 + 32);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    NetRootCachingMode = RxQueryNetRootCachingMode(v1[81]);
    WPP_SF_qD(AttachedDevice, 45, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids, v3, NetRootCachingMode);
  }
  v6 = v1[82];
  Pool2 = ExAllocatePool2(64, 240, 1061124178);
  v8 = (_DWORD *)Pool2;
  if ( !Pool2 )
  {
    v9 = -1073741670;
LABEL_22:
    *(_QWORD *)(v3 + 48) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids, v9);
    goto LABEL_25;
  }
  v10 = (_QWORD *)(Pool2 + 16);
  v10[1] = v10;
  *v10 = v10;
  v8[14] = 1;
  *((_QWORD *)v8 + 8) = 0;
  v8[18] = 0;
  KeInitializeEvent((PRKEVENT)(v8 + 20), SynchronizationEvent, 0);
  v9 = ExInitializeResourceLite((PERESOURCE)(v8 + 32));
  if ( (v9 & 0x80000000) != 0 )
  {
    ExFreePoolWithTag(v8, 0);
    goto LABEL_22;
  }
  CscNotifyInitializeSync(v8);
  v8[1] |= 0x10u;
  *v8 = 15788704;
  *(_QWORD *)(v3 + 48) = v8;
  CscLoadLViewWasPreviouslyOffline(v3);
  if ( (v8[1] & 0x2000) == 0 && !(unsigned __int8)CscLViewIsRootGhosted(v3) )
  {
    v11 = (*(_DWORD *)(v6 + 56) & 0x10) != 0;
    if ( *(PDEVICE_OBJECT *)(*(_QWORD *)(*(_QWORD *)(v6 + 32) + 32LL) + 48LL) == CscDeviceObject )
      v11 = (unsigned __int8)CscEcpGetTypeValue(v1[5], 1) == 0;
    if ( v11 )
      CscTransitionLViewOffline(v3, 2);
  }
  v12 = v8[1];
  if ( (v12 & 0x23) == 0 || (v12 & 0x21) != 0 )
    v8[2] = 1;
  CscFlushLViewWasPreviouslyOffline(v3);
  if ( (v8[1] & 0x27) != 0 )
  {
    _InterlockedCompareExchange64((volatile signed __int64 *)(*(_QWORD *)(v3 + 48) + 40LL), 0, 0);
    CscOfflineLviewCacheAddEntryEx((PERESOURCE)(CscDevExtn + 384), 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids, v9, v8[1]);
LABEL_25:
  *(_DWORD *)(a1 + 40) = v9;
  return v9;
}

```

## disassembly

```asm
0x140075770  push    rbx
0x140075772  push    rbp
0x140075773  push    rsi
0x140075774  push    rdi
0x140075775  push    r14
0x140075777  push    r15
0x140075779  sub     rsp, 38h
0x14007577d  mov     rbp, [rcx]
0x140075780  mov     r14, rcx
0x140075783  mov     rsi, [rcx+20h]
0x140075787  mov     rbx, cs:WPP_GLOBAL_Control
0x14007578e  lea     rax, WPP_GLOBAL_Control
0x140075795  cmp     rbx, rax
0x140075798  jz      short loc_1400757D3
0x14007579a  mov     eax, [rbx+2Ch]
0x14007579d  test    al, 40h
0x14007579f  jz      short loc_1400757D3
0x1400757a1  mov     rcx, [rbp+288h]
0x1400757a8  mov     rbx, [rbx+18h]
0x1400757ac  call    cs:__imp_RxQueryNetRootCachingMode
0x1400757b3  nop     dword ptr [rax+rax+00h]
0x1400757b8  mov     edx, 2Dh ; '-'
0x1400757bd  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x1400757c4  mov     r9, rsi
0x1400757c7  mov     dword ptr [rsp+68h+var_48], eax
0x1400757cb  mov     rcx, rbx
0x1400757ce  call    WPP_SF_qD
0x1400757d3  mov     r15, [rbp+290h]
0x1400757da  mov     edx, 0F0h
0x1400757df  mov     ecx, 40h ; '@'
0x1400757e4  mov     r8d, 3F3F7852h
0x1400757ea  call    cs:__imp_ExAllocatePool2
0x1400757f1  nop     dword ptr [rax+rax+00h]
0x1400757f6  mov     rdi, rax
0x1400757f9  test    rax, rax
0x1400757fc  jnz     short loc_140075808
0x1400757fe  mov     ebx, 0C000009Ah
0x140075803  jmp     loc_140075975
0x140075808  add     rax, 10h
0x14007580c  lea     rcx, [rdi+50h]; Event
0x140075810  xor     r8d, r8d; State
0x140075813  mov     [rax+8], rax
0x140075817  mov     [rax], rax
0x14007581a  lea     edx, [r8+1]; Type
0x14007581e  mov     dword ptr [rdi+38h], 1
0x140075825  mov     qword ptr [rdi+40h], 0
0x14007582d  mov     dword ptr [rdi+48h], 0
0x140075834  call    cs:__imp_KeInitializeEvent
0x14007583b  nop     dword ptr [rax+rax+00h]
0x140075840  lea     rcx, [rdi+80h]; Resource
0x140075847  call    cs:__imp_ExInitializeResourceLite
0x14007584e  nop     dword ptr [rax+rax+00h]
0x140075853  mov     ebx, eax
0x140075855  mov     rcx, rdi; P
0x140075858  test    eax, eax
0x14007585a  js      loc_140075967
0x140075860  call    CscNotifyInitializeSync
0x140075865  or      dword ptr [rdi+4], 10h
0x140075869  mov     rcx, rsi
0x14007586c  mov     dword ptr [rdi], 0F0EAA0h
0x140075872  mov     [rsi+30h], rdi
0x140075876  call    CscLoadLViewWasPreviouslyOffline
0x14007587b  test    dword ptr [rdi+4], 2000h
0x140075882  jnz     short loc_1400758D7
0x140075884  mov     rcx, rsi
0x140075887  call    CscLViewIsRootGhosted
0x14007588c  test    al, al
0x14007588e  jnz     short loc_1400758D7
0x140075890  mov     rax, [r15+20h]
0x140075894  mov     r8d, [r15+38h]
0x140075898  shr     r8d, 4
0x14007589c  and     r8b, 1
0x1400758a0  mov     rdx, [rax+20h]
0x1400758a4  mov     rax, cs:CscDeviceObject
0x1400758ab  cmp     [rdx+30h], rax
0x1400758af  jnz     short loc_1400758C5
0x1400758b1  mov     rcx, [rbp+28h]
0x1400758b5  mov     edx, 1
0x1400758ba  call    CscEcpGetTypeValue
0x1400758bf  test    al, al
0x1400758c1  setz    r8b
0x1400758c5  test    r8b, r8b
0x1400758c8  jz      short loc_1400758D7
0x1400758ca  mov     edx, 2
0x1400758cf  mov     rcx, rsi
0x1400758d2  call    CscTransitionLViewOffline
0x1400758d7  mov     eax, [rdi+4]
0x1400758da  test    al, 23h
0x1400758dc  jz      short loc_1400758E2
0x1400758de  test    al, 21h
0x1400758e0  jz      short loc_1400758E9
0x1400758e2  mov     dword ptr [rdi+8], 1
0x1400758e9  mov     rcx, rsi
0x1400758ec  call    CscFlushLViewWasPreviouslyOffline
0x1400758f1  mov     eax, [rdi+4]
0x1400758f4  test    al, 27h
0x1400758f6  jz      short loc_14007592C
0x1400758f8  mov     r8, [rsi+30h]
0x1400758fc  xor     ecx, ecx
0x1400758fe  xor     eax, eax
0x140075900  lock cmpxchg [r8+28h], rcx
0x140075906  mov     rcx, cs:CscDevExtn
0x14007590d  xor     r9d, r9d
0x140075910  mov     rdx, [rsi+38h]
0x140075914  add     rcx, 180h; Resource
0x14007591b  mov     r8, rax
0x14007591e  mov     [rsp+68h+var_48], 0; __int64
0x140075927  call    CscOfflineLviewCacheAddEntryEx
0x14007592c  mov     rcx, cs:WPP_GLOBAL_Control
0x140075933  lea     rax, WPP_GLOBAL_Control
0x14007593a  cmp     rcx, rax
0x14007593d  jz      short loc_1400759AF
0x14007593f  mov     eax, [rcx+2Ch]
0x140075942  test    al, 20h
0x140075944  jz      short loc_1400759AF
0x140075946  mov     eax, [rdi+4]
0x140075949  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x140075950  mov     rcx, [rcx+18h]
0x140075954  mov     edx, 2Eh ; '.'
0x140075959  mov     r9d, ebx
0x14007595c  mov     dword ptr [rsp+68h+var_48], eax
0x140075960  call    WPP_SF_Dd
0x140075965  jmp     short loc_1400759AF
0x140075967  xor     edx, edx; Tag
0x140075969  call    cs:__imp_ExFreePoolWithTag
0x140075970  nop     dword ptr [rax+rax+00h]
0x140075975  mov     qword ptr [rsi+30h], 0
0x14007597d  mov     rcx, cs:WPP_GLOBAL_Control
0x140075984  lea     rax, WPP_GLOBAL_Control
0x14007598b  cmp     rcx, rax
0x14007598e  jz      short loc_1400759AF
0x140075990  mov     eax, [rcx+2Ch]
0x140075993  test    al, 20h
0x140075995  jz      short loc_1400759AF
0x140075997  mov     rcx, [rcx+18h]
0x14007599b  lea     r8, WPP_d263cc2461ba3b624f93eda7f8efb7f6_Traceguids
0x1400759a2  mov     edx, 2Fh ; '/'
0x1400759a7  mov     r9d, ebx
0x1400759aa  call    WPP_SF_d
0x1400759af  mov     [r14+28h], ebx
0x1400759b3  mov     eax, ebx
0x1400759b5  add     rsp, 38h
0x1400759b9  pop     r15
0x1400759bb  pop     r14
0x1400759bd  pop     rdi
0x1400759be  pop     rsi
0x1400759bf  pop     rbp
0x1400759c0  pop     rbx
0x1400759c1  retn
```
