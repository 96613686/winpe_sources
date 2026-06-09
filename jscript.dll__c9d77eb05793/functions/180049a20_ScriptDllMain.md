# ScriptDllMain

- ea: `0x180049a20`
- end: `0x180049b4f`
- name: `ScriptDllMain`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x180049a14`

## callees

- `0x18000f5e0`
- `0x18000f630`
- `0x180048d00`
- `0x180049038`
- `0x180049144`
- `0x180049a20`
- `0x18004cf94`
- `0x180052bc4`
- `0x1800576a0`
- `0x1800738f4`

## import_xrefs

- `KERNEL32!TlsFree` at `0x180049b34`
- `KERNEL32!TlsFree` at `0x180049b34`
- `KERNEL32!TlsSetValue` at `0x180049a78`
- `KERNEL32!TlsSetValue` at `0x180049a78`
- `KERNEL32!TlsGetValue` at `0x180049a54`
- `KERNEL32!TlsGetValue` at `0x180049a54`

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
0x180049a20  mov     [rsp+arg_0], rbx
0x180049a25  push    rdi
0x180049a26  sub     rsp, 20h
0x180049a2a  mov     rbx, r8
0x180049a2d  mov     rdi, rcx
0x180049a30  test    edx, edx
0x180049a32  jz      loc_180049ADB
0x180049a38  sub     edx, 1
0x180049a3b  jz      short loc_180049A83
0x180049a3d  sub     edx, 1
0x180049a40  jz      short loc_180049A70
0x180049a42  cmp     edx, 1
0x180049a45  jz      short loc_180049A4E
0x180049a47  xor     eax, eax
0x180049a49  jmp     loc_180049B44
0x180049a4e  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180049a54  call    cs:__imp_TlsGetValue
0x180049a5a  test    rax, rax
0x180049a5d  jz      loc_180049B3F
0x180049a63  mov     rcx, rax; this
0x180049a66  call    ??_GThreadGlobals@@AEAAPEAXI@Z; ThreadGlobals::`scalar deleting destructor'(uint)
0x180049a6b  jmp     loc_180049B3F
0x180049a70  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180049a76  xor     edx, edx; lpTlsValue
0x180049a78  call    cs:__imp_TlsSetValue
0x180049a7e  jmp     loc_180049B3F
0x180049a83  mov     ecx, 1B70h; Size
0x180049a88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049a8d  mov     rbx, rax
0x180049a90  test    rax, rax
0x180049a93  jz      short loc_180049AA4
0x180049a95  mov     rcx, rax; this
0x180049a98  call    ??0RegistryBasedThrottle@@QEAA@XZ; RegistryBasedThrottle::RegistryBasedThrottle(void)
0x180049a9d  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180049aa2  jmp     short loc_180049AA6
0x180049aa4  xor     ebx, ebx
0x180049aa6  mov     rcx, rdi
0x180049aa9  mov     cs:g_pTraceLoggingClient, rbx
0x180049ab0  call    AttachProcess
0x180049ab5  mov     ebx, eax
0x180049ab7  test    eax, eax
0x180049ab9  jnz     short loc_180049AD7
0x180049abb  mov     rcx, cs:g_pTraceLoggingClient; this
0x180049ac2  test    rcx, rcx
0x180049ac5  jz      short loc_180049AD7
0x180049ac7  call    ??_GTraceLoggingClient@@QEAAPEAXI@Z; TraceLoggingClient::`scalar deleting destructor'(uint)
0x180049acc  mov     cs:g_pTraceLoggingClient, 0
0x180049ad7  mov     eax, ebx
0x180049ad9  jmp     short loc_180049B44
0x180049adb  mov     rcx, cs:g_pTraceLoggingClient; this
0x180049ae2  test    rcx, rcx
0x180049ae5  jz      short loc_180049AF7
0x180049ae7  call    ??_GTraceLoggingClient@@QEAAPEAXI@Z; TraceLoggingClient::`scalar deleting destructor'(uint)
0x180049aec  mov     cs:g_pTraceLoggingClient, 0
0x180049af7  test    rbx, rbx
0x180049afa  jnz     short loc_180049B2E
0x180049afc  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; this
0x180049b03  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x180049b08  test    eax, eax
0x180049b0a  jz      short loc_180049B2E
0x180049b0c  jmp     short loc_180049B16
0x180049b0e  mov     rcx, rax; this
0x180049b11  call    ??_GThreadGlobals@@AEAAPEAXI@Z; ThreadGlobals::`scalar deleting destructor'(uint)
0x180049b16  mov     rax, cs:?g_ptgFirst@ThreadGlobals@@0PEAV1@EA; ThreadGlobals * ThreadGlobals::g_ptgFirst
0x180049b1d  test    rax, rax
0x180049b20  jnz     short loc_180049B0E
0x180049b22  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; this
0x180049b29  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x180049b2e  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180049b34  call    cs:__imp_TlsFree
0x180049b3a  call    CleanupResDLLMap
0x180049b3f  mov     eax, 1
0x180049b44  mov     rbx, [rsp+28h+arg_0]
0x180049b49  add     rsp, 20h
0x180049b4d  pop     rdi
0x180049b4e  retn
```
