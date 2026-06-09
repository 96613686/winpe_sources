# wil::details_abi::FeatureStateData::~FeatureStateData(void)

- ea: `0x1000c5c0`
- end: `0x1000c679`
- name: `??1FeatureStateData@details_abi@wil@@QAE@XZ`
- size: `185`
- prototype: `void __thiscall(wil::details_abi::FeatureStateData *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1000ed90`

## callees

- `0x1000af30`
- `0x1000c1a0`
- `0x1000c260`
- `0x1000c5c0`
- `0x1000c7e0`
- `0x1005e3b0`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1000c65b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1000c65b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000c64d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1000c64d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000c654`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1000c654`

## pseudocode

```c
void __thiscall wil::details_abi::FeatureStateData::~FeatureStateData(wil::details_abi::FeatureStateData *this)
{
  wil::details_abi::RawUsageIndex *v2; // ecx
  wil::details_abi::UsageIndexes *v3; // edi
  void *v4; // eax
  struct _RTL_CRITICAL_SECTION *v5; // esi
  HANDLE ProcessHeap; // eax
  void *v7; // [esp-4h] [ebp-88h]
  _BYTE v8[36]; // [esp+Ch] [ebp-78h] BYREF
  _BYTE v9[36]; // [esp+30h] [ebp-54h] BYREF
  _BYTE v10[36]; // [esp+54h] [ebp-30h] BYREF

  wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v8);
  v3 = (wil::details_abi::FeatureStateData *)((char *)this + 4);
  if ( *((_BYTE *)this + 36) )
    wil::details_abi::RawUsageIndex::Swap(v2, (wil::details_abi::FeatureStateData *)((char *)this + 4));
  if ( *((_BYTE *)this + 72) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v9,
      (wil::details_abi::FeatureStateData *)((char *)this + 40));
  if ( *((_BYTE *)this + 108) )
    wil::details_abi::RawUsageIndex::Swap(
      (wil::details_abi::RawUsageIndex *)v10,
      (wil::details_abi::FeatureStateData *)((char *)this + 76));
  wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v8);
  wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v8);
  v4 = (void *)*((_DWORD *)this + 37);
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 112);
  v5[1].OwningThread = 0;
  if ( v4 )
  {
    v7 = v4;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  DeleteCriticalSection(v5);
  wil::details_abi::UsageIndexes::~UsageIndexes(v3);
}

```

## disassembly

```asm
0x1000c5c0  mov     edi, edi
0x1000c5c2  push    ebp
0x1000c5c3  mov     ebp, esp
0x1000c5c5  push    0FFFFFFFFh
0x1000c5c7  push    offset ??1FeatureStateData@details_abi@wil@@QAE@XZ_SEH
0x1000c5cc  mov     eax, large fs:0
0x1000c5d2  push    eax
0x1000c5d3  sub     esp, 6Ch
0x1000c5d6  push    esi
0x1000c5d7  push    edi
0x1000c5d8  mov     eax, ___security_cookie
0x1000c5dd  xor     eax, ebp
0x1000c5df  push    eax
0x1000c5e0  lea     eax, [ebp+var_C]
0x1000c5e3  mov     large fs:0, eax
0x1000c5e9  mov     esi, ecx
0x1000c5eb  lea     ecx, [ebp+var_78]; this
0x1000c5ee  call    ??0UsageIndexes@details_abi@wil@@QAE@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x1000c5f3  cmp     byte ptr [esi+24h], 0
0x1000c5f7  lea     edi, [esi+4]
0x1000c5fa  jz      short loc_1000C602
0x1000c5fc  push    edi; struct wil::details_abi::RawUsageIndex *
0x1000c5fd  call    ?Swap@RawUsageIndex@details_abi@wil@@QAEXAAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1000c602  cmp     byte ptr [esi+48h], 0
0x1000c606  jz      short loc_1000C614
0x1000c608  lea     eax, [esi+28h]
0x1000c60b  push    eax; struct wil::details_abi::RawUsageIndex *
0x1000c60c  lea     ecx, [ebp+var_54]; this
0x1000c60f  call    ?Swap@RawUsageIndex@details_abi@wil@@QAEXAAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1000c614  cmp     byte ptr [esi+6Ch], 0
0x1000c618  jz      short loc_1000C626
0x1000c61a  lea     eax, [esi+4Ch]
0x1000c61d  push    eax; struct wil::details_abi::RawUsageIndex *
0x1000c61e  lea     ecx, [ebp+var_30]; this
0x1000c621  call    ?Swap@RawUsageIndex@details_abi@wil@@QAEXAAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x1000c626  lea     ecx, [ebp+var_78]; this
0x1000c629  call    ?Record@UsageIndexes@details_abi@wil@@QAEXXZ; wil::details_abi::UsageIndexes::Record(void)
0x1000c62e  lea     ecx, [ebp+var_78]; this
0x1000c631  call    ??1UsageIndexes@details_abi@wil@@QAE@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1000c636  mov     eax, [esi+94h]
0x1000c63c  add     esi, 70h ; 'p'
0x1000c63f  mov     dword ptr [esi+24h], 0
0x1000c646  test    eax, eax
0x1000c648  jz      short loc_1000C65A
0x1000c64a  push    eax; lpMem
0x1000c64b  push    0; dwFlags
0x1000c64d  call    ds:__imp__GetProcessHeap@0; GetProcessHeap()
0x1000c653  push    eax; hHeap
0x1000c654  call    ds:__imp__HeapFree@12; HeapFree(x,x,x)
0x1000c65a  push    esi; lpCriticalSection
0x1000c65b  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x1000c661  mov     ecx, edi; this
0x1000c663  call    ??1UsageIndexes@details_abi@wil@@QAE@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x1000c668  mov     ecx, [ebp+var_C]
0x1000c66b  mov     large fs:0, ecx
0x1000c672  pop     ecx
0x1000c673  pop     edi
0x1000c674  pop     esi
0x1000c675  mov     esp, ebp
0x1000c677  pop     ebp
0x1000c678  retn
0x1005f770  nop
0x1005f771  nop
0x1005f772  mov     edx, [esp-4+arg_4]
0x1005f776  lea     eax, [edx+0Ch]
0x1005f779  mov     ecx, [edx-78h]
0x1005f77c  xor     ecx, eax; StackCookie
0x1005f77e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f783  mov     eax, offset stru_10062AB0
0x1005f788  jmp     ___CxxFrameHandler3
```
