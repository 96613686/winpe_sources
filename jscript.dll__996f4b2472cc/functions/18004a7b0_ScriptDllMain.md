# ScriptDllMain

- ea: `0x18004a7b0`
- end: `0x18004a8f2`
- name: `ScriptDllMain`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18004a7a4`

## callees

- `0x18000c860`
- `0x18000c8c0`
- `0x1800491ac`
- `0x180049d30`
- `0x180049e5c`
- `0x18004a7b0`
- `0x18004dbdc`
- `0x1800539b4`
- `0x1800585d0`
- `0x180074db0`

## import_xrefs

- `KERNEL32!TlsFree` at `0x18004a8d0`
- `KERNEL32!TlsFree` at `0x18004a8d0`
- `KERNEL32!TlsSetValue` at `0x18004a80e`
- `KERNEL32!TlsSetValue` at `0x18004a80e`
- `KERNEL32!TlsGetValue` at `0x18004a7e4`
- `KERNEL32!TlsGetValue` at `0x18004a7e4`

## pseudocode

```c
__int64 __fastcall ScriptDllMain(__int64 a1, int a2, __int64 a3)
{
  int v5; // edx
  int v6; // edx
  ThreadGlobals *Value; // rax
  unsigned int v9; // edx
  RegistryBasedThrottle *v10; // rax
  RegistryBasedThrottle *v11; // rbx
  unsigned int v12; // edx
  unsigned int v13; // ebx
  unsigned int v14; // edx

  if ( !a2 )
  {
    if ( g_pTraceLoggingClient )
    {
      TraceLoggingClient::`scalar deleting destructor'(g_pTraceLoggingClient, 0);
      g_pTraceLoggingClient = 0;
    }
    if ( !a3 && (unsigned int)MUTX::Enter((MUTX *)&ThreadGlobals::g_mutx) )
    {
      while ( ThreadGlobals::g_ptgFirst )
        ThreadGlobals::`scalar deleting destructor'(ThreadGlobals::g_ptgFirst, v14);
      MUTX::Leave((MUTX *)&ThreadGlobals::g_mutx);
    }
    TlsFree(g_luTls);
    CleanupResDLLMap();
    return 1;
  }
  v5 = a2 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
        return 0;
      Value = (ThreadGlobals *)TlsGetValue(g_luTls);
      if ( Value )
        ThreadGlobals::`scalar deleting destructor'(Value, v9);
    }
    else
    {
      TlsSetValue(g_luTls, 0);
    }
    return 1;
  }
  v10 = (RegistryBasedThrottle *)operator new(0x1B70u);
  v11 = v10;
  if ( v10 )
  {
    RegistryBasedThrottle::RegistryBasedThrottle(v10);
    TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  }
  else
  {
    v11 = 0;
  }
  g_pTraceLoggingClient = v11;
  v13 = AttachProcess(a1);
  if ( !v13 && g_pTraceLoggingClient )
  {
    TraceLoggingClient::`scalar deleting destructor'(g_pTraceLoggingClient, v12);
    g_pTraceLoggingClient = 0;
  }
  return v13;
}

```

## disassembly

```asm
0x18004a7b0  mov     [rsp+arg_0], rbx
0x18004a7b5  push    rdi
0x18004a7b6  sub     rsp, 20h
0x18004a7ba  mov     rbx, r8
0x18004a7bd  mov     rdi, rcx
0x18004a7c0  test    edx, edx
0x18004a7c2  jz      loc_18004A877
0x18004a7c8  sub     edx, 1
0x18004a7cb  jz      short loc_18004A81F
0x18004a7cd  sub     edx, 1
0x18004a7d0  jz      short loc_18004A806
0x18004a7d2  cmp     edx, 1
0x18004a7d5  jz      short loc_18004A7DE
0x18004a7d7  xor     eax, eax
0x18004a7d9  jmp     loc_18004A8E6
0x18004a7de  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18004a7e4  call    cs:__imp_TlsGetValue
0x18004a7eb  nop     dword ptr [rax+rax+00h]
0x18004a7f0  test    rax, rax
0x18004a7f3  jz      loc_18004A8E1
0x18004a7f9  mov     rcx, rax; this
0x18004a7fc  call    ??_GThreadGlobals@@AEAAPEAXI@Z; ThreadGlobals::`scalar deleting destructor'(uint)
0x18004a801  jmp     loc_18004A8E1
0x18004a806  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18004a80c  xor     edx, edx; lpTlsValue
0x18004a80e  call    cs:__imp_TlsSetValue
0x18004a815  nop     dword ptr [rax+rax+00h]
0x18004a81a  jmp     loc_18004A8E1
0x18004a81f  mov     ecx, 1B70h; Size
0x18004a824  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004a829  mov     rbx, rax
0x18004a82c  test    rax, rax
0x18004a82f  jz      short loc_18004A840
0x18004a831  mov     rcx, rax; this
0x18004a834  call    ??0RegistryBasedThrottle@@QEAA@XZ; RegistryBasedThrottle::RegistryBasedThrottle(void)
0x18004a839  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18004a83e  jmp     short loc_18004A842
0x18004a840  xor     ebx, ebx
0x18004a842  mov     rcx, rdi
0x18004a845  mov     cs:g_pTraceLoggingClient, rbx
0x18004a84c  call    AttachProcess
0x18004a851  mov     ebx, eax
0x18004a853  test    eax, eax
0x18004a855  jnz     short loc_18004A873
0x18004a857  mov     rcx, cs:g_pTraceLoggingClient; this
0x18004a85e  test    rcx, rcx
0x18004a861  jz      short loc_18004A873
0x18004a863  call    ??_GTraceLoggingClient@@QEAAPEAXI@Z; TraceLoggingClient::`scalar deleting destructor'(uint)
0x18004a868  mov     cs:g_pTraceLoggingClient, 0
0x18004a873  mov     eax, ebx
0x18004a875  jmp     short loc_18004A8E6
0x18004a877  mov     rcx, cs:g_pTraceLoggingClient; this
0x18004a87e  test    rcx, rcx
0x18004a881  jz      short loc_18004A893
0x18004a883  call    ??_GTraceLoggingClient@@QEAAPEAXI@Z; TraceLoggingClient::`scalar deleting destructor'(uint)
0x18004a888  mov     cs:g_pTraceLoggingClient, 0
0x18004a893  test    rbx, rbx
0x18004a896  jnz     short loc_18004A8CA
0x18004a898  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; this
0x18004a89f  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18004a8a4  test    eax, eax
0x18004a8a6  jz      short loc_18004A8CA
0x18004a8a8  jmp     short loc_18004A8B2
0x18004a8aa  mov     rcx, rax; this
0x18004a8ad  call    ??_GThreadGlobals@@AEAAPEAXI@Z; ThreadGlobals::`scalar deleting destructor'(uint)
0x18004a8b2  mov     rax, cs:?g_ptgFirst@ThreadGlobals@@0PEAV1@EA; ThreadGlobals * ThreadGlobals::g_ptgFirst
0x18004a8b9  test    rax, rax
0x18004a8bc  jnz     short loc_18004A8AA
0x18004a8be  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; this
0x18004a8c5  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18004a8ca  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x18004a8d0  call    cs:__imp_TlsFree
0x18004a8d7  nop     dword ptr [rax+rax+00h]
0x18004a8dc  call    CleanupResDLLMap
0x18004a8e1  mov     eax, 1
0x18004a8e6  mov     rbx, [rsp+28h+arg_0]
0x18004a8eb  add     rsp, 20h
0x18004a8ef  pop     rdi
0x18004a8f0  retn
```
