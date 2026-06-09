# Microsoft::IoT::Utility::MTAThread::_WorkerThread(void *)

- ea: `0x18000e9e0`
- end: `0x18000ea15`
- name: `?_WorkerThread@MTAThread@Utility@IoT@Microsoft@@CAKPEAX@Z`
- size: `53`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180008358`
- `0x18000e9e0`
- `0x18001b010`

## string_xrefs

- `0x18000e9f9`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::IoT::Utility::MTAThread::_WorkerThread(PVOID Parameter)
{
  int v1; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)Parameter + 8LL))(Parameter);
  if ( v1 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
      (const char *)(unsigned int)v1,
      v3);
  return 0;
}

```

## disassembly

```asm
0x18000e9e0  sub     rsp, 28h
0x18000e9e4  mov     rax, [rcx]
0x18000e9e7  mov     rax, [rax+8]
0x18000e9eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9f0  test    eax, eax
0x18000e9f2  jns     short loc_18000EA0E
0x18000e9f4  mov     rcx, [rsp+28h]; this
0x18000e9f9  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18000ea00  mov     r9d, eax; char *
0x18000ea03  mov     edx, 0A3h; void *
0x18000ea08  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000ea0e  xor     eax, eax
0x18000ea10  add     rsp, 28h
0x18000ea14  retn
```
