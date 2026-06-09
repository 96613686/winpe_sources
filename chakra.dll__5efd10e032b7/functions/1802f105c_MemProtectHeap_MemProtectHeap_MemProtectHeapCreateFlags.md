# MemProtectHeap::MemProtectHeap(MemProtectHeapCreateFlags)

- ea: `0x1802f105c`
- end: `0x1802f12e1`
- name: `??0MemProtectHeap@@QEAA@W4MemProtectHeapCreateFlags@@@Z`
- size: `645`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802f0ff0`

## callees

- `0x1802efef0`
- `0x1802f04b8`
- `0x1802f079c`
- `0x1802f105c`
- `0x1802f12e8`
- `0x1802f1324`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1802f10ca`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1802f10ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802f1250`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802f1250`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x1802f121a`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x1802f121a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1802f1187`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1802f11a8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1802f11e6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1802f1234`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1802f126c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1802f1187`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1802f11a8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1802f11e6`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1802f1234`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RaiseFailFastException` at `0x1802f126c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MemProtectHeap::MemProtectHeap(__int64 a1, char a2)
{
  char v3; // r12
  _DWORD *v4; // r15
  _DWORD *v5; // r14
  char v6; // r14
  bool v7; // di
  DWORD v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r9
  HANDLE EventW; // rax
  int v13; // [rsp+20h] [rbp-78h]
  int v14; // [rsp+28h] [rbp-70h]

  *(_DWORD *)a1 = -1;
  *(_QWORD *)(a1 + 8) = 0x80000;
  v3 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_BYTE *)(a1 + 48) = 0;
  v4 = (_DWORD *)(a1 + 52);
  *(_DWORD *)(a1 + 52) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_WORD *)(a1 + 84) = 0;
  *(_BYTE *)(a1 + 86) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(a1 + 96), 0xFA0u);
  *(_DWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 136) = &MemProtectRecyclerCollectionWrapper::`vftable';
  *(_QWORD *)(a1 + 152) = a1;
  *(_BYTE *)(a1 + 160) = 0;
  Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::BackgroundPageQueue::BackgroundPageQueue(a1 + 176);
  Memory::IdleDecommitPageAllocator::IdleDecommitPageAllocator(
    a1 + 240,
    0,
    6,
    (unsigned int)MemProtectHeap::ConfigurationLoader::s_userConfig);
  Memory::Recycler::Recycler(
    (Memory::Recycler *)(a1 + 560),
    0,
    (struct Memory::IdleDecommitPageAllocator *)(a1 + 240),
    (void (*)(void))Js::Throw::InternalError,
    (struct Js::ConfigFlagsTable *)MemProtectHeap::ConfigurationLoader::s_userConfig,
    0);
  if ( (a2 & 2) != 0 )
  {
    if ( (a2 & 1) != 0 )
    {
      RaiseFailFastException(0, 0, 0);
      v5 = (_DWORD *)(a1 + 52);
    }
    else
    {
      v5 = v4;
    }
    if ( (a2 & 4) != 0 )
      RaiseFailFastException(0, 0, 0);
    *v4 = 1;
  }
  else
  {
    v5 = v4;
  }
  if ( (a2 & 1) != 0 )
    *v5 = 2;
  v6 = 0;
  v7 = 0;
  if ( (a2 & 8) != 0 )
  {
    if ( (a2 & 0x10) != 0 )
    {
      RaiseFailFastException(0, 0, 0);
      goto LABEL_19;
    }
    v6 = 1;
  }
  else
  {
    if ( (a2 & 0x10) == 0 )
      goto LABEL_19;
    v6 = 2;
  }
  v7 = (a2 & 0x20) != 0;
  if ( (a2 & 0x40) != 0 )
    v3 = 1;
LABEL_19:
  *(_BYTE *)(a1 + 86) = (a2 & 4) != 0;
  v8 = TlsAlloc();
  *(_DWORD *)a1 = v8;
  if ( v8 == -1 )
    RaiseFailFastException(0, 0, 0);
  if ( *(_DWORD *)(a1 + 52) == 2 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *(_QWORD *)(a1 + 72) = EventW;
    if ( !EventW )
      RaiseFailFastException(0, 0, 0);
  }
  LOBYTE(v10) = *v4 && !*(_BYTE *)(a1 + 86);
  LOBYTE(v14) = v7;
  LOBYTE(v13) = v6;
  LOBYTE(v9) = *(_BYTE *)(a1 + 86);
  Memory::Recycler::Initialize(a1 + 560, v9, 0, v10, v13, v14, v3, a1 + 176, 32, 0, -2);
  *(_WORD *)(a1 + 2697) = 257;
  *(_BYTE *)(a1 + 2699) = 1;
  Memory::Recycler::SetCollectionWrapper(
    (Memory::Recycler *)(a1 + 560),
    (struct Memory::RecyclerCollectionWrapper *)(a1 + 136));
  return a1;
}

```

## disassembly

```asm
0x1802f105c  mov     rax, rsp
0x1802f105f  mov     [rax+10h], edx
0x1802f1062  mov     [rax+8], rcx
0x1802f1066  push    rbp
0x1802f1067  push    rsi
0x1802f1068  push    rdi
0x1802f1069  push    r12
0x1802f106b  push    r13
0x1802f106d  push    r14
0x1802f106f  push    r15
0x1802f1071  sub     rsp, 60h
0x1802f1075  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1802f107d  mov     [rax+18h], rbx
0x1802f1081  mov     rsi, rcx
0x1802f1084  mov     dword ptr [rcx], 0FFFFFFFFh
0x1802f108a  mov     qword ptr [rcx+8], 80000h
0x1802f1092  xor     r12d, r12d
0x1802f1095  mov     [rcx+10h], r12
0x1802f1099  mov     [rcx+18h], r12
0x1802f109d  mov     [rcx+30h], r12b
0x1802f10a1  lea     r15, [rcx+34h]
0x1802f10a5  mov     [r15], r12d
0x1802f10a8  mov     [rcx+38h], r12
0x1802f10ac  mov     [rcx+40h], r12
0x1802f10b0  mov     [rcx+48h], r12
0x1802f10b4  mov     [rcx+54h], r12w
0x1802f10b9  mov     [rcx+56h], r12b
0x1802f10bd  mov     [rcx+58h], r12
0x1802f10c1  lea     rcx, [rcx+60h]; lpCriticalSection
0x1802f10c5  mov     edx, 0FA0h; dwSpinCount
0x1802f10ca  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1802f10d1  nop     dword ptr [rax+rax+00h]
0x1802f10d6  nop
0x1802f10d7  lea     r13, [rsi+88h]
0x1802f10de  mov     [r13+8], r12d
0x1802f10e2  lea     rax, ??_7MemProtectRecyclerCollectionWrapper@@6B@; const MemProtectRecyclerCollectionWrapper::`vftable'
0x1802f10e9  mov     [r13+0], rax
0x1802f10ed  mov     [r13+10h], rsi
0x1802f10f1  mov     [r13+18h], r12b
0x1802f10f5  lea     rbx, [rsi+0B0h]
0x1802f10fc  mov     rcx, rbx
0x1802f10ff  call    ??0BackgroundPageQueue@?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@Memory@@QEAA@XZ; Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::BackgroundPageQueue::BackgroundPageQueue(void)
0x1802f1104  nop
0x1802f1105  lea     rdi, [rsi+0F0h]
0x1802f110c  mov     [rsp+98h+var_50], r12b
0x1802f1111  mov     [rsp+98h+var_58], 20h ; ' '
0x1802f1119  mov     [rsp+98h+var_60], rbx
0x1802f111e  mov     [rsp+98h+var_68], r12b
0x1802f1123  mov     dword ptr [rsp+98h+var_70], 400h
0x1802f112b  lea     rbx, ?s_userConfig@ConfigurationLoader@MemProtectHeap@@0VConfiguration@Js@@A; Js::Configuration MemProtectHeap::ConfigurationLoader::s_userConfig
0x1802f1132  mov     r9, rbx
0x1802f1135  xor     edx, edx
0x1802f1137  lea     r8d, [r12+6]
0x1802f113c  mov     rcx, rdi
0x1802f113f  call    ??0IdleDecommitPageAllocator@Memory@@QEAA@PEAVAllocationPolicyManager@@W4PageAllocatorType@@AEAVConfigFlagsTable@Js@@II_NPEAUBackgroundPageQueue@?$PageAllocatorBase@VVirtualAllocWrapper@Memory@@V?$SegmentBase@VVirtualAllocWrapper@Memory@@@2@V?$PageSegmentBase@VVirtualAllocWrapper@Memory@@@2@@1@I3@Z; Memory::IdleDecommitPageAllocator::IdleDecommitPageAllocator(AllocationPolicyManager *,PageAllocatorType,Js::ConfigFlagsTable &,uint,uint,bool,Memory::PageAllocatorBase<Memory::VirtualAllocWrapper,Memory::SegmentBase<Memory::VirtualAllocWrapper>,Memory::PageSegmentBase<Memory::VirtualAllocWrapper>>::BackgroundPageQueue *,uint,bool)
0x1802f1144  nop
0x1802f1145  lea     rbp, [rsi+230h]
0x1802f114c  mov     [rsp+98h+var_70], r12; struct Memory::RecyclerTelemetryHostInterface *
0x1802f1151  mov     [rsp+98h+var_78], rbx; struct Js::ConfigFlagsTable *
0x1802f1156  lea     r9, ?InternalError@Throw@Js@@SAXXZ; void (*)(void)
0x1802f115d  mov     r8, rdi; struct Memory::IdleDecommitPageAllocator *
0x1802f1160  xor     edx, edx; struct AllocationPolicyManager *
0x1802f1162  mov     rcx, rbp; this
0x1802f1165  call    ??0Recycler@Memory@@QEAA@PEAVAllocationPolicyManager@@PEAVIdleDecommitPageAllocator@1@P6AXXZAEAVConfigFlagsTable@Js@@PEAVRecyclerTelemetryHostInterface@1@@Z; Memory::Recycler::Recycler(AllocationPolicyManager *,Memory::IdleDecommitPageAllocator *,void (*)(void),Js::ConfigFlagsTable &,Memory::RecyclerTelemetryHostInterface *)
0x1802f116a  nop
0x1802f116b  mov     ebx, [rsp+98h+arg_8]
0x1802f1172  mov     edi, ebx
0x1802f1174  and     edi, 1
0x1802f1177  test    bl, 2
0x1802f117a  jz      short loc_1802F11BD
0x1802f117c  test    edi, edi
0x1802f117e  jz      short loc_1802F1199
0x1802f1180  xor     r8d, r8d; dwFlags
0x1802f1183  xor     edx, edx; pContextRecord
0x1802f1185  xor     ecx, ecx; pExceptionRecord
0x1802f1187  call    cs:__imp_RaiseFailFastException
0x1802f118e  nop     dword ptr [rax+rax+00h]
0x1802f1193  lea     r14, [rsi+34h]
0x1802f1197  jmp     short loc_1802F119C
0x1802f1199  mov     r14, r15
0x1802f119c  test    bl, 4
0x1802f119f  jz      short loc_1802F11B4
0x1802f11a1  xor     r8d, r8d; dwFlags
0x1802f11a4  xor     edx, edx; pContextRecord
0x1802f11a6  xor     ecx, ecx; pExceptionRecord
0x1802f11a8  call    cs:__imp_RaiseFailFastException
0x1802f11af  nop     dword ptr [rax+rax+00h]
0x1802f11b4  mov     dword ptr [r15], 1
0x1802f11bb  jmp     short loc_1802F11C0
0x1802f11bd  mov     r14, r15
0x1802f11c0  test    edi, edi
0x1802f11c2  jz      short loc_1802F11CB
0x1802f11c4  mov     dword ptr [r14], 2
0x1802f11cb  mov     r14b, r12b
0x1802f11ce  mov     dil, r12b
0x1802f11d1  mov     eax, ebx
0x1802f11d3  and     eax, 10h
0x1802f11d6  test    bl, 8
0x1802f11d9  jz      short loc_1802F11F9
0x1802f11db  test    eax, eax
0x1802f11dd  jz      short loc_1802F11F4
0x1802f11df  xor     r8d, r8d; dwFlags
0x1802f11e2  xor     edx, edx; pContextRecord
0x1802f11e4  xor     ecx, ecx; pExceptionRecord
0x1802f11e6  call    cs:__imp_RaiseFailFastException
0x1802f11ed  nop     dword ptr [rax+rax+00h]
0x1802f11f2  jmp     short loc_1802F1211
0x1802f11f4  mov     r14b, 1
0x1802f11f7  jmp     short loc_1802F1200
0x1802f11f9  test    eax, eax
0x1802f11fb  jz      short loc_1802F1211
0x1802f11fd  mov     r14b, 2
0x1802f1200  mov     edi, ebx
0x1802f1202  shr     edi, 5
0x1802f1205  and     dil, 1
0x1802f1209  test    bl, 40h
0x1802f120c  jz      short loc_1802F1211
0x1802f120e  mov     r12b, 1
0x1802f1211  shr     ebx, 2
0x1802f1214  and     bl, 1
0x1802f1217  mov     [rsi+56h], bl
0x1802f121a  call    cs:__imp_TlsAlloc
0x1802f1221  nop     dword ptr [rax+rax+00h]
0x1802f1226  mov     [rsi], eax
0x1802f1228  cmp     eax, 0FFFFFFFFh
0x1802f122b  jnz     short loc_1802F1240
0x1802f122d  xor     r8d, r8d; dwFlags
0x1802f1230  xor     edx, edx; pContextRecord
0x1802f1232  xor     ecx, ecx; pExceptionRecord
0x1802f1234  call    cs:__imp_RaiseFailFastException
0x1802f123b  nop     dword ptr [rax+rax+00h]
0x1802f1240  cmp     dword ptr [rsi+34h], 2
0x1802f1244  jnz     short loc_1802F1278
0x1802f1246  xor     r9d, r9d; lpName
0x1802f1249  xor     r8d, r8d; bInitialState
0x1802f124c  xor     edx, edx; bManualReset
0x1802f124e  xor     ecx, ecx; lpEventAttributes
0x1802f1250  call    cs:__imp_CreateEventW
0x1802f1257  nop     dword ptr [rax+rax+00h]
0x1802f125c  mov     [rsi+48h], rax
0x1802f1260  test    rax, rax
0x1802f1263  jnz     short loc_1802F1278
0x1802f1265  xor     r8d, r8d; dwFlags
0x1802f1268  xor     edx, edx; pContextRecord
0x1802f126a  xor     ecx, ecx; pExceptionRecord
0x1802f126c  call    cs:__imp_RaiseFailFastException
0x1802f1273  nop     dword ptr [rax+rax+00h]
0x1802f1278  cmp     dword ptr [r15], 0
0x1802f127c  jz      short loc_1802F1289
0x1802f127e  cmp     byte ptr [rsi+56h], 0
0x1802f1282  jnz     short loc_1802F1289
0x1802f1284  mov     r9b, 1
0x1802f1287  jmp     short loc_1802F128C
0x1802f1289  xor     r9b, r9b
0x1802f128c  mov     [rsp+98h+var_68], r12b
0x1802f1291  mov     byte ptr [rsp+98h+var_70], dil
0x1802f1296  mov     byte ptr [rsp+98h+var_78], r14b
0x1802f129b  xor     r8d, r8d
0x1802f129e  mov     dl, [rsi+56h]
0x1802f12a1  mov     rcx, rbp
0x1802f12a4  call    ?Initialize@Recycler@Memory@@QEAAX_NPEAVThreadService@JsUtil@@0W4PageHeapMode@@_N3@Z; Memory::Recycler::Initialize(bool,JsUtil::ThreadService *,bool,PageHeapMode,bool,bool)
0x1802f12a9  mov     word ptr [rbp+859h], 101h
0x1802f12b2  mov     byte ptr [rbp+85Bh], 1
0x1802f12b9  mov     rdx, r13; struct Memory::RecyclerCollectionWrapper *
0x1802f12bc  mov     rcx, rbp; this
0x1802f12bf  call    ?SetCollectionWrapper@Recycler@Memory@@QEAAXPEAVRecyclerCollectionWrapper@2@@Z; Memory::Recycler::SetCollectionWrapper(Memory::RecyclerCollectionWrapper *)
0x1802f12c4  nop
0x1802f12c5  mov     rax, rsi
0x1802f12c8  mov     rbx, [rsp+98h+arg_10]
0x1802f12d0  add     rsp, 60h
0x1802f12d4  pop     r15
0x1802f12d6  pop     r14
0x1802f12d8  pop     r13
0x1802f12da  pop     r12
0x1802f12dc  pop     rdi
0x1802f12dd  pop     rsi
0x1802f12de  pop     rbp
0x1802f12df  retn
```
