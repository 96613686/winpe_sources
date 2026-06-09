# tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)

- ea: `0x180006f78`
- end: `0x180007002`
- name: `?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ`
- size: `138`
- prototype: `int *__fastcall(__int64)`
- caller_count: `97`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800047f4`
- `0x180005508`
- `0x180007220`
- `0x180007300`
- `0x180007440`
- `0x180007530`
- `0x1800075e0`
- `0x1800076f0`
- `0x180007800`
- `0x180007870`
- `0x1800083c0`
- `0x18000847c`
- `0x18000acb0`
- `0x18000b700`
- `0x18000bc50`
- `0x18000ca4c`
- `0x18000ceb4`
- `0x18000cfcc`
- `0x18000d0d0`
- `0x18000d21c`
- `0x18000d3e4`
- `0x18000d68c`
- `0x18000d7b8`
- `0x18000d860`
- `0x18000da68`
- `0x18000e020`
- `0x18000e2b0`
- `0x18000e364`
- `0x18000f068`
- `0x18000f740`
- `0x18000fcd4`
- `0x18000fd9c`
- `0x180010220`
- `0x1800102d8`
- `0x180010500`
- `0x1800105bc`
- `0x1800107c4`
- `0x180010844`
- `0x1800109d8`
- `0x1800111c0`
- `0x180011548`
- `0x18001182c`
- `0x180011914`
- `0x180011a78`
- `0x180011b38`
- `0x180011bdc`
- `0x180011c64`
- `0x180011d20`
- `0x180011fc0`
- `0x1800120ac`

## callees

- `0x1800044cc`
- `0x180006f78`
- `0x18000c328`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006fa4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006fa4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006fe9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006fe9`

## pseudocode

```c
int *__fastcall tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
        __int64 a1)
{
  int *v1; // rbx
  union _RTL_RUN_ONCE *v3; // [rsp+30h] [rbp+8h] BYREF
  int *v4; // [rsp+38h] [rbp+10h] BYREF

  HIDWORD(v3) = HIDWORD(a1);
  LODWORD(v3) = 0;
  v4 = 0;
  InitOnceBeginInitialize(&DSLoggerSingleton, 0, (PBOOL)&v3, (LPVOID *)&v4);
  v1 = v4;
  if ( !v4 )
  {
    dword_18002B4A0 = McGenEventRegister_EventRegister() == 0;
    v1 = &dword_18002B4A0;
    v3 = 0;
    InitOnceComplete(&DSLoggerSingleton, 0, &dword_18002B4A0);
    tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::_Initializer::~_Initializer(&v3);
  }
  return v1;
}

```

## disassembly

```asm
0x180006f78  mov     rax, rsp
0x180006f7b  mov     [rax+8], rcx
0x180006f7f  push    rbx
0x180006f80  sub     rsp, 20h
0x180006f84  lea     r9, [rax+10h]; lpContext
0x180006f88  mov     dword ptr [rax+8], 0
0x180006f8f  lea     r8, [rax+8]; fPending
0x180006f93  mov     qword ptr [rax+10h], 0
0x180006f9b  xor     edx, edx; dwFlags
0x180006f9d  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x180006fa4  call    cs:__imp_InitOnceBeginInitialize
0x180006faa  mov     rbx, [rsp+28h+arg_8]
0x180006faf  test    rbx, rbx
0x180006fb2  jnz     short loc_180006FF9
0x180006fb4  mov     cs:dword_18002B4A0, ebx
0x180006fba  call    McGenEventRegister_EventRegister
0x180006fbf  test    eax, eax
0x180006fc1  jnz     short loc_180006FCD
0x180006fc3  mov     cs:dword_18002B4A0, 1
0x180006fcd  lea     rbx, dword_18002B4A0
0x180006fd4  mov     [rsp+28h+arg_0], 0
0x180006fdd  mov     r8, rbx; lpContext
0x180006fe0  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x180006fe7  xor     edx, edx; dwFlags
0x180006fe9  call    cs:__imp_InitOnceComplete
0x180006fef  lea     rcx, [rsp+28h+arg_0]
0x180006ff4  call    ??1_Initializer@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::_Initializer::~_Initializer(void)
0x180006ff9  mov     rax, rbx
0x180006ffc  add     rsp, 20h
0x180007000  pop     rbx
0x180007001  retn
```
