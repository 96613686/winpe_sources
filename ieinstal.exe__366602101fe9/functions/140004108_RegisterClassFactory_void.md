# RegisterClassFactory(void)

- ea: `0x140004108`
- end: `0x14000422b`
- name: `?RegisterClassFactory@@YAJXZ`
- size: `291`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140003a10`
- `0x140003cd0`
- `0x14000ca10`

## callees

- `0x140003978`
- `0x140003af8`
- `0x140003bf8`
- `0x140004108`
- `0x140011010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x140004206`
- `KERNEL32!InitializeCriticalSection` at `0x140004206`
- `KERNEL32!SetProcessShutdownParameters` at `0x140004136`
- `KERNEL32!SetProcessShutdownParameters` at `0x140004136`
- `ole32!CoRegisterClassObject` at `0x1400041de`
- `ole32!CoRegisterClassObject` at `0x1400041de`
- `iertutil!__imp_?GetProcessIntegrityLevel@@YAJPEAXPEAK@Z` at `0x140004151`
- `iertutil!__imp_?GetProcessIntegrityLevel@@YAJPEAXPEAK@Z` at `0x140004151`

## pseudocode

```c
__int64 RegisterClassFactory(void)
{
  unsigned int ProcessIntegrityLevel; // ebx
  _DWORD *v1; // rax
  _DWORD *v2; // rdi
  unsigned int v4; // [rsp+40h] [rbp+8h] BYREF

  g_fRunningAsSystem = IsSystem();
  if ( !g_fRunningAsSystem )
    g_fRunningAsAdminWithHighIL = IsAdminWithHighIL();
  SetProcessShutdownParameters(0x100u, 1u);
  v4 = 4096;
  ProcessIntegrityLevel = GetProcessIntegrityLevel(0, &v4);
  if ( !ProcessIntegrityLevel )
  {
    if ( v4 >= 0x2000 )
    {
      if ( !_InterlockedExchange(&g_fClassRegistered, 1) )
      {
        v1 = operator new(0x10u);
        v2 = v1;
        if ( v1 )
        {
          v1[2] = 1;
          *(_QWORD *)v1 = &CIEAdminBrokerClassFactory::`vftable';
          _InterlockedIncrement(&g_ObjectCount);
          ProcessIntegrityLevel = CoRegisterClassObject(&CLSID_CIeAxiInstaller, (LPUNKNOWN)v1, 4u, 1u, &g_dwRegister);
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 16LL))(v2);
        }
        else
        {
          v2 = 0;
        }
        InitializeCriticalSection(&g_DetourCriticalSection);
        if ( !v2 )
          return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)-2147024891;
    }
  }
  return ProcessIntegrityLevel;
}

```

## disassembly

```asm
0x140004108  mov     [rsp+arg_8], rbx
0x14000410d  push    rdi
0x14000410e  sub     rsp, 30h
0x140004112  call    ?IsSystem@@YAHXZ; IsSystem(void)
0x140004117  mov     cs:?g_fRunningAsSystem@@3HA, eax; int g_fRunningAsSystem
0x14000411d  test    eax, eax
0x14000411f  jnz     short loc_14000412C
0x140004121  call    ?IsAdminWithHighIL@@YAHXZ; IsAdminWithHighIL(void)
0x140004126  mov     cs:?g_fRunningAsAdminWithHighIL@@3HA, eax; int g_fRunningAsAdminWithHighIL
0x14000412c  mov     edx, 1; dwFlags
0x140004131  mov     ecx, 100h; dwLevel
0x140004136  call    cs:__imp_SetProcessShutdownParameters
0x14000413d  nop     dword ptr [rax+rax+00h]
0x140004142  lea     rdx, [rsp+38h+arg_0]
0x140004147  mov     [rsp+38h+arg_0], 1000h
0x14000414f  xor     ecx, ecx
0x140004151  call    cs:__imp_?GetProcessIntegrityLevel@@YAJPEAXPEAK@Z; GetProcessIntegrityLevel(void *,ulong *)
0x140004158  nop     dword ptr [rax+rax+00h]
0x14000415d  mov     ebx, eax
0x14000415f  test    eax, eax
0x140004161  jnz     loc_14000421D
0x140004167  cmp     [rsp+38h+arg_0], 2000h
0x14000416f  jnb     short loc_14000417B
0x140004171  mov     ebx, 80070005h
0x140004176  jmp     loc_14000421D
0x14000417b  test    eax, eax
0x14000417d  jnz     loc_14000421D
0x140004183  mov     eax, 1
0x140004188  xchg    eax, cs:?g_fClassRegistered@@3JA; long g_fClassRegistered
0x14000418e  test    eax, eax
0x140004190  jnz     loc_14000421D
0x140004196  lea     ecx, [rax+10h]; dwBytes
0x140004199  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000419e  mov     rdi, rax
0x1400041a1  test    rax, rax
0x1400041a4  jz      short loc_1400041FD
0x1400041a6  lea     rax, ??_7CIEAdminBrokerClassFactory@@6B@; const CIEAdminBrokerClassFactory::`vftable'
0x1400041ad  mov     dword ptr [rdi+8], 1
0x1400041b4  mov     [rdi], rax
0x1400041b7  lock inc cs:?g_ObjectCount@@3JA; long g_ObjectCount
0x1400041be  mov     r9d, 1; flags
0x1400041c4  lea     rax, ?g_dwRegister@@3KA; ulong g_dwRegister
0x1400041cb  mov     rdx, rdi; pUnk
0x1400041ce  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x1400041d3  lea     rcx, CLSID_CIeAxiInstaller; rclsid
0x1400041da  lea     r8d, [r9+3]; dwClsContext
0x1400041de  call    cs:__imp_CoRegisterClassObject
0x1400041e5  nop     dword ptr [rax+rax+00h]
0x1400041ea  mov     rcx, [rdi]
0x1400041ed  mov     ebx, eax
0x1400041ef  mov     rax, [rcx+10h]
0x1400041f3  mov     rcx, rdi
0x1400041f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041fb  jmp     short loc_1400041FF
0x1400041fd  xor     edi, edi
0x1400041ff  lea     rcx, ?g_DetourCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140004206  call    cs:__imp_InitializeCriticalSection
0x14000420d  nop     dword ptr [rax+rax+00h]
0x140004212  test    rdi, rdi
0x140004215  mov     eax, 8007000Eh
0x14000421a  cmovz   ebx, eax
0x14000421d  mov     eax, ebx
0x14000421f  mov     rbx, [rsp+38h+arg_8]
0x140004224  add     rsp, 30h
0x140004228  pop     rdi
0x140004229  retn
```
