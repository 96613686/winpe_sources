# DllMain

- ea: `0x180001f8c`
- end: `0x18000209e`
- name: `DllMain`
- size: `274`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800018b4`

## callees

- `0x180001f8c`
- `0x180007ed8`
- `0x180008090`

## import_xrefs

- `ntdll!EtwUnregisterTraceGuids` at `0x180002071`
- `ntdll!EtwUnregisterTraceGuids` at `0x180002071`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180002039`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180002039`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 *v3; // rbx
  __int64 *v4; // rdi
  __int64 v5; // r8
  _QWORD *v6; // rbx
  _QWORD v8[3]; // [rsp+40h] [rbp-18h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      qword_18000D930 = 0;
      v3 = &WPP_MAIN_CB;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_HidServGuid;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      v4 = &WPP_REGISTRATION_GUIDS;
      WPP_MAIN_CB = 0;
      qword_18000D938 = 1;
      do
      {
        v5 = *v4;
        v8[0] = v5;
        ++v4;
        v8[1] = 0;
        v3[4] = v5;
        ((void (__fastcall *)(__int64 (__fastcall *)(), __int64 *, __int64, __int64, _QWORD *, _QWORD, _QWORD, __int64 *))EtwRegisterTraceGuidsW)(
          WppControlCallback,
          v3,
          v5,
          1,
          v8,
          0,
          0,
          v3 + 1);
        v3 = (__int64 *)*v3;
      }
      while ( v3 );
      TlgRegisterAggregateProviderEx();
    }
  }
  else
  {
    TlgUnregisterAggregateProvider(hinstDLL, fdwReason, lpvReserved);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v6 )
      {
        if ( v6[1] )
        {
          EtwUnregisterTraceGuids();
          v6[1] = 0;
        }
        v6 = (_QWORD *)*v6;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180001f8c  mov     [rsp+arg_0], rbx
0x180001f91  push    rdi
0x180001f92  sub     rsp, 50h
0x180001f96  test    edx, edx
0x180001f98  jz      loc_18000204E
0x180001f9e  cmp     edx, 1
0x180001fa1  jnz     loc_18000208E
0x180001fa7  lea     rax, WPP_ThisDir_CTLGUID_HidServGuid
0x180001fae  mov     cs:qword_18000D930, 0
0x180001fb9  lea     rbx, WPP_MAIN_CB
0x180001fc0  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180001fc7  mov     cs:WPP_GLOBAL_Control, rbx
0x180001fce  lea     rdi, WPP_REGISTRATION_GUIDS
0x180001fd5  mov     cs:WPP_MAIN_CB, 0
0x180001fe0  mov     cs:qword_18000D938, 1
0x180001feb  mov     r8, [rdi]
0x180001fee  lea     rax, [rbx+8]
0x180001ff2  mov     [rsp+58h+var_20], rax
0x180001ff7  lea     rcx, WppControlCallback
0x180001ffe  mov     [rsp+58h+var_28], 0
0x180002007  lea     rax, [rsp+58h+var_18]
0x18000200c  mov     [rsp+58h+var_18], r8
0x180002011  lea     rdi, [rdi+8]
0x180002015  mov     [rsp+58h+var_10], 0
0x18000201e  mov     r9d, 1
0x180002024  mov     [rsp+58h+var_30], 0
0x18000202d  mov     rdx, rbx
0x180002030  mov     [rsp+58h+var_38], rax
0x180002035  mov     [rbx+20h], r8
0x180002039  call    cs:__imp_EtwRegisterTraceGuidsW
0x18000203f  mov     rbx, [rbx]
0x180002042  test    rbx, rbx
0x180002045  jnz     short loc_180001FEB
0x180002047  call    TlgRegisterAggregateProviderEx
0x18000204c  jmp     short loc_18000208E
0x18000204e  call    TlgUnregisterAggregateProvider
0x180002053  mov     rbx, cs:WPP_GLOBAL_Control
0x18000205a  lea     rdi, WPP_GLOBAL_Control
0x180002061  cmp     rbx, rdi
0x180002064  jz      short loc_18000208E
0x180002066  jmp     short loc_180002082
0x180002068  mov     rcx, [rbx+8]
0x18000206c  test    rcx, rcx
0x18000206f  jz      short loc_18000207F
0x180002071  call    cs:__imp_EtwUnregisterTraceGuids
0x180002077  mov     qword ptr [rbx+8], 0
0x18000207f  mov     rbx, [rbx]
0x180002082  test    rbx, rbx
0x180002085  jnz     short loc_180002068
0x180002087  mov     cs:WPP_GLOBAL_Control, rdi
0x18000208e  mov     rbx, [rsp+58h+arg_0]
0x180002093  mov     eax, 1
0x180002098  add     rsp, 50h
0x18000209c  pop     rdi
0x18000209d  retn
```
