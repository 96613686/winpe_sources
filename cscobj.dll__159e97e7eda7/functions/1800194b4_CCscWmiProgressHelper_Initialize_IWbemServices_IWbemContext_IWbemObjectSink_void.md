# CCscWmiProgressHelper::Initialize(IWbemServices *,IWbemContext *,IWbemObjectSink *,void *)

- ea: `0x1800194b4`
- end: `0x180019576`
- name: `?Initialize@CCscWmiProgressHelper@@QEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@PEAX@Z`
- size: `194`
- prototype: `__int64 __fastcall(struct IStream **this, struct IWbemServices *, struct IWbemContext *, struct IWbemObjectSink *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180018a28`
- `0x180018ac8`

## callees

- `0x180009864`
- `0x18000f5a4`
- `0x18000f5cc`
- `0x1800194b4`
- `0x18001ba54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180019502`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180019502`

## pseudocode

```c
__int64 __fastcall CCscWmiProgressHelper::Initialize(
        struct IStream **this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemObjectSink *a4,
        struct IStream *a5)
{
  UstVarLib *v9; // rcx
  int Error; // ebx

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids);
  }
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(this + 4), 0) )
  {
    *((_DWORD *)this + 18) = 1;
    Error = CCscWmiProgressHelper::_MarshalWbemInterfaces(this, a2, a3, a4);
    if ( Error >= 0 )
      this[3] = a5;
  }
  else
  {
    Error = UstVarLib::ResultFromLastError(v9);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      24,
      WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids,
      (unsigned int)Error);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800194b4  push    rbx
0x1800194b6  push    rbp
0x1800194b7  push    rsi
0x1800194b8  push    rdi
0x1800194b9  push    r15
0x1800194bb  sub     rsp, 20h
0x1800194bf  mov     rbx, r9
0x1800194c2  mov     rsi, r8
0x1800194c5  mov     rbp, rdx
0x1800194c8  mov     rdi, rcx
0x1800194cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194d2  lea     r15, WPP_GLOBAL_Control
0x1800194d9  cmp     rcx, r15
0x1800194dc  jz      short loc_1800194FC
0x1800194de  test    dword ptr [rcx+1Ch], 4000000h
0x1800194e5  jz      short loc_1800194FC
0x1800194e7  mov     rcx, [rcx+10h]
0x1800194eb  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x1800194f2  mov     edx, 17h
0x1800194f7  call    WPP_SF_
0x1800194fc  lea     rcx, [rdi+20h]; lpCriticalSection
0x180019500  xor     edx, edx; dwSpinCount
0x180019502  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180019508  test    eax, eax
0x18001950a  jz      short loc_180019535
0x18001950c  mov     r9, rbx; struct IWbemObjectSink *
0x18001950f  mov     dword ptr [rdi+48h], 1
0x180019516  mov     r8, rsi; struct IWbemContext *
0x180019519  mov     rdx, rbp; struct IWbemServices *
0x18001951c  mov     rcx, rdi; this
0x18001951f  call    ?_MarshalWbemInterfaces@CCscWmiProgressHelper@@AEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemObjectSink@@@Z; CCscWmiProgressHelper::_MarshalWbemInterfaces(IWbemServices *,IWbemContext *,IWbemObjectSink *)
0x180019524  mov     ebx, eax
0x180019526  test    eax, eax
0x180019528  js      short loc_18001953C
0x18001952a  mov     rcx, [rsp+48h+arg_20]
0x18001952f  mov     [rdi+18h], rcx
0x180019533  jmp     short loc_18001953C
0x180019535  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x18001953a  mov     ebx, eax
0x18001953c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019543  cmp     rcx, r15
0x180019546  jz      short loc_180019569
0x180019548  test    dword ptr [rcx+1Ch], 4000000h
0x18001954f  jz      short loc_180019569
0x180019551  mov     rcx, [rcx+10h]
0x180019555  lea     r8, WPP_8f02c74e8a0b38c6d20a40430033a0d7_Traceguids
0x18001955c  mov     edx, 18h
0x180019561  mov     r9d, ebx
0x180019564  call    WPP_SF_d
0x180019569  mov     eax, ebx
0x18001956b  add     rsp, 20h
0x18001956f  pop     r15
0x180019571  pop     rdi
0x180019572  pop     rsi
0x180019573  pop     rbp
0x180019574  pop     rbx
0x180019575  retn
```
