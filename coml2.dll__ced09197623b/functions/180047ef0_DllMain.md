# DllMain

- ea: `0x180047ef0`
- end: `0x180047f71`
- name: `DllMain`
- size: `129`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180042674`

## callees

- `0x180034b30`
- `0x180038588`
- `0x180038abc`
- `0x180038e84`
- `0x1800438ac`
- `0x180047ef0`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-1!CleanupComl2StateInAllTls` at `0x180047f2b`
- `api-ms-win-core-com-private-l1-1-1!CleanupComl2StateInAllTls` at `0x180047f2b`
- `api-ms-win-core-com-private-l1-1-1!CleanupTlsComl2State` at `0x180047f63`
- `api-ms-win-core-com-private-l1-1-1!CleanupTlsComl2State` at `0x180047f63`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v3; // ebx
  const unsigned __int16 *v4; // rcx
  const unsigned __int16 *v5; // rcx
  __int64 v6; // rdx
  PVOID ReservedForOle; // [rsp+48h] [rbp+20h] BYREF

  v3 = 1;
  if ( fdwReason == 1 )
  {
    SafeAllocaInitialize(hinstDLL, fdwReason, lpvReserved);
    gfEnableTracing = IsCurrentBinaryEnabledForTracing();
    InitializeTracing(v4);
    return g_hHeap != 0;
  }
  else if ( fdwReason )
  {
    if ( fdwReason == 3 )
    {
      ReservedForOle = NtCurrentTeb()->ReservedForOle;
      if ( !COleTls::IsNULL((COleTls *)&ReservedForOle) )
        CleanupTlsComl2State(v6);
    }
  }
  else
  {
    CleanupComl2StateInAllTls(hinstDLL, fdwReason, lpvReserved);
    UninitializeTracing(v5);
  }
  return v3;
}

```

## disassembly

```asm
0x180047ef0  push    rbx
0x180047ef2  sub     rsp, 20h
0x180047ef6  mov     ebx, 1
0x180047efb  cmp     edx, ebx
0x180047efd  jnz     short loc_180047F27
0x180047eff  call    SafeAllocaInitialize
0x180047f04  call    ?IsCurrentBinaryEnabledForTracing@@YAHXZ; IsCurrentBinaryEnabledForTracing(void)
0x180047f09  mov     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180047f0f  call    ?InitializeTracing@@YAXPEBG@Z; InitializeTracing(ushort const *)
0x180047f14  xor     r8d, r8d
0x180047f17  cmp     cs:?g_hHeap@@3QEAXEA, r8; void * g_hHeap
0x180047f1e  setnz   r8b
0x180047f22  mov     ebx, r8d
0x180047f25  jmp     short loc_180047F69
0x180047f27  test    edx, edx
0x180047f29  jnz     short loc_180047F38
0x180047f2b  call    cs:__imp_CleanupComl2StateInAllTls
0x180047f31  call    ?UninitializeTracing@@YAXPEBG@Z; UninitializeTracing(ushort const *)
0x180047f36  jmp     short loc_180047F69
0x180047f38  cmp     edx, 3
0x180047f3b  jnz     short loc_180047F69
0x180047f3d  mov     rdx, gs:30h
0x180047f46  lea     rcx, [rsp+28h+arg_18]; this
0x180047f4b  mov     rdx, [rdx+1758h]
0x180047f52  mov     [rsp+28h+arg_18], rdx
0x180047f57  call    ?IsNULL@COleTls@@QEBA_NXZ; COleTls::IsNULL(void)
0x180047f5c  test    al, al
0x180047f5e  jnz     short loc_180047F69
0x180047f60  mov     rcx, rdx
0x180047f63  call    cs:__imp_CleanupTlsComl2State
0x180047f69  mov     eax, ebx
0x180047f6b  add     rsp, 20h
0x180047f6f  pop     rbx
0x180047f70  retn
```
