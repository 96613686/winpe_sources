# PrivacieDllMain

- ea: `0x180614a94`
- end: `0x180614c55`
- name: `PrivacieDllMain`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180614934`

## callees

- `0x180614a94`
- `0x18075a75c`
- `0x181095034`
- `0x1810a1650`
- `0x1810f65c0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180614b1e`
- `KERNEL32!InitializeCriticalSection` at `0x180614b1e`
- `KERNEL32!CreateMutexW` at `0x180614b67`
- `KERNEL32!CreateMutexW` at `0x180614b67`
- `KERNEL32!DeleteCriticalSection` at `0x180614bfa`
- `KERNEL32!DeleteCriticalSection` at `0x180614bfa`
- `KERNEL32!GetLastError` at `0x180614b83`
- `KERNEL32!GetLastError` at `0x180614b83`
- `KERNEL32!CloseHandle` at `0x180614c2e`
- `KERNEL32!CloseHandle` at `0x180614c2e`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x180614ba8`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x180614ba8`
- `iertutil!__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z` at `0x180614b52`
- `iertutil!__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z` at `0x180614bc8`
- `iertutil!__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z` at `0x180614b52`
- `iertutil!__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z` at `0x180614bc8`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180614ac0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180614ad5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180614ac0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180614ad5`

## pseudocode

```c
__int64 __fastcall PrivacieDllMain(__int64 a1, int a2)
{
  int v3; // r9d
  unsigned int v4; // [rsp+20h] [rbp-2C8h]
  WCHAR Name[168]; // [rsp+30h] [rbp-2B8h] BYREF
  unsigned __int16 v6[168]; // [rsp+180h] [rbp-168h] BYREF

  if ( !(unsigned __int8)IEConfiguration_GetBool(268435482) && !(unsigned __int8)IEConfiguration_GetBool(268435481) )
    return 1;
  if ( !a2 )
  {
    DeleteCriticalSection(&stru_1815C36B0);
    if ( g_pPrivaceIEAdvisor )
    {
      CPrivacIEAdvisor::Release(g_pPrivaceIEAdvisor);
      g_pPrivaceIEAdvisor = 0;
    }
    if ( g_hPrivacIEMutex )
      CloseHandle(g_hPrivacIEMutex);
    CSharedMem::Release((CSharedMem *)g_sharedPrivacIECounter);
    goto LABEL_16;
  }
  if ( a2 != 1 )
    return 1;
  InitializeCriticalSection(&stru_1815C36B0);
  g_bPrivacIEInit = 1;
  IsoPrefixUserQualifierToName(Name, 0xA2u, L"!PrivacIE!SharedMem!Mutex");
  g_hPrivacIEMutex = CreateMutexW(0, 0, Name);
  if ( !g_hPrivacIEMutex )
  {
LABEL_16:
    g_bPrivacIEInit = 0;
    return 1;
  }
  if ( GetLastError() != 183 )
    SetWindowsHandleAccess(g_hPrivacIEMutex, 0x114Fu, 0x801F0003);
  IsoPrefixUserQualifierToName(v6, 0xA4u, L"!PrivacIE!SharedMem!Counter");
  CSharedMem::_InitInternal((CSharedMem *)g_sharedPrivacIECounter, v6, 0x10u, v3, v4);
  return 1;
}

```

## disassembly

```asm
0x180614a94  mov     [rsp+arg_10], r8
0x180614a99  mov     [rsp+arg_8], edx
0x180614a9d  mov     [rsp+arg_0], rcx
0x180614aa2  sub     rsp, 2E8h
0x180614aa9  mov     rax, cs:__security_cookie
0x180614ab0  xor     rax, rsp
0x180614ab3  mov     [rsp+2E8h+var_18], rax
0x180614abb  mov     ecx, 1000001Ah
0x180614ac0  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180614ac7  nop     dword ptr [rax+rax+00h]
0x180614acc  test    al, al
0x180614ace  jnz     short loc_180614B03
0x180614ad0  mov     ecx, 10000019h
0x180614ad5  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180614adc  nop     dword ptr [rax+rax+00h]
0x180614ae1  test    al, al
0x180614ae3  jnz     short loc_180614B03
0x180614ae5  mov     eax, 1
0x180614aea  mov     rcx, [rsp+2E8h+var_18]
0x180614af2  xor     rcx, rsp; StackCookie
0x180614af5  call    __security_check_cookie
0x180614afa  add     rsp, 2E8h
0x180614b01  retn
0x180614b03  mov     eax, [rsp+2E8h+arg_8]
0x180614b0a  test    eax, eax
0x180614b0c  jz      loc_180614BF3
0x180614b12  cmp     eax, 1
0x180614b15  jnz     short loc_180614AE5
0x180614b17  lea     rcx, stru_1815C36B0; lpCriticalSection
0x180614b1e  call    cs:__imp_InitializeCriticalSection
0x180614b25  nop     dword ptr [rax+rax+00h]
0x180614b2a  mov     eax, 1
0x180614b2f  mov     cs:?g_bPrivacIEInit@@3HA, eax; int g_bPrivacIEInit
0x180614b35  jmp     short loc_180614B3D
0x180614b37  mov     eax, cs:?g_bPrivacIEInit@@3HA; int g_bPrivacIEInit
0x180614b3d  test    eax, eax
0x180614b3f  jz      short loc_180614AE5
0x180614b41  lea     r8, aPrivacieShared_0; "!PrivacIE!SharedMem!Mutex"
0x180614b48  mov     edx, 0A2h
0x180614b4d  lea     rcx, [rsp+2E8h+Name]
0x180614b52  call    cs:__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z; IsoPrefixUserQualifierToName(ushort *,ulong,ushort const *)
0x180614b59  nop     dword ptr [rax+rax+00h]
0x180614b5e  lea     r8, [rsp+2E8h+Name]; lpName
0x180614b63  xor     edx, edx; bInitialOwner
0x180614b65  xor     ecx, ecx; lpMutexAttributes
0x180614b67  call    cs:__imp_CreateMutexW
0x180614b6e  nop     dword ptr [rax+rax+00h]
0x180614b73  mov     cs:?g_hPrivacIEMutex@@3PEAXEA, rax; void * g_hPrivacIEMutex
0x180614b7a  test    rax, rax
0x180614b7d  jz      loc_180614C46
0x180614b83  call    cs:__imp_GetLastError
0x180614b8a  nop     dword ptr [rax+rax+00h]
0x180614b8f  cmp     eax, 0B7h
0x180614b94  jz      short loc_180614BB4
0x180614b96  mov     edx, 114Fh
0x180614b9b  mov     r8d, 801F0003h
0x180614ba1  mov     rcx, cs:?g_hPrivacIEMutex@@3PEAXEA; void * g_hPrivacIEMutex
0x180614ba8  call    cs:__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x180614baf  nop     dword ptr [rax+rax+00h]
0x180614bb4  lea     r8, aPrivacieShared_1; "!PrivacIE!SharedMem!Counter"
0x180614bbb  mov     edx, 0A4h
0x180614bc0  lea     rcx, [rsp+2E8h+var_168]
0x180614bc8  call    cs:__imp_?IsoPrefixUserQualifierToName@@YAPEBGPEAGKPEBG@Z; IsoPrefixUserQualifierToName(ushort *,ulong,ushort const *)
0x180614bcf  nop     dword ptr [rax+rax+00h]
0x180614bd4  mov     r8d, 10h; unsigned int
0x180614bda  lea     rdx, [rsp+2E8h+var_168]; unsigned __int16 *
0x180614be2  lea     rcx, ?g_sharedPrivacIECounter@@3VCSharedMem@@A; this
0x180614be9  call    ?_InitInternal@CSharedMem@@AEAAJPEBGKHK@Z; CSharedMem::_InitInternal(ushort const *,ulong,int,ulong)
0x180614bee  jmp     loc_180614AE5
0x180614bf3  lea     rcx, stru_1815C36B0; lpCriticalSection
0x180614bfa  call    cs:__imp_DeleteCriticalSection
0x180614c01  nop     dword ptr [rax+rax+00h]
0x180614c06  mov     rcx, cs:?g_pPrivaceIEAdvisor@@3PEAVCPrivacIEAdvisor@@EA; this
0x180614c0d  test    rcx, rcx
0x180614c10  jz      short loc_180614C22
0x180614c12  call    ?Release@CPrivacIEAdvisor@@UEAAKXZ; CPrivacIEAdvisor::Release(void)
0x180614c17  mov     cs:?g_pPrivaceIEAdvisor@@3PEAVCPrivacIEAdvisor@@EA, 0; CPrivacIEAdvisor * g_pPrivaceIEAdvisor
0x180614c22  mov     rcx, cs:?g_hPrivacIEMutex@@3PEAXEA; hObject
0x180614c29  test    rcx, rcx
0x180614c2c  jz      short loc_180614C3A
0x180614c2e  call    cs:__imp_CloseHandle
0x180614c35  nop     dword ptr [rax+rax+00h]
0x180614c3a  lea     rcx, ?g_sharedPrivacIECounter@@3VCSharedMem@@A; this
0x180614c41  call    ?Release@CSharedMem@@QEAAXXZ; CSharedMem::Release(void)
0x180614c46  mov     cs:?g_bPrivacIEInit@@3HA, 0; int g_bPrivacIEInit
0x180614c50  jmp     loc_180614AE5
0x1811012b3  mov     [rsp+arg_0], rcx
0x1811012b8  mov     qword ptr [rsp+arg_8], rdx
0x1811012bd  push    rbp
0x1811012be  sub     rsp, 30h
0x1811012c2  mov     rbp, rdx
0x1811012c5  mov     rax, [rcx]
0x1811012c8  xor     ecx, ecx
0x1811012ca  cmp     dword ptr [rax], 0C0000017h
0x1811012d0  setz    cl
0x1811012d3  mov     eax, ecx
0x1811012d5  add     rsp, 30h
0x1811012d9  pop     rbp
0x1811012da  retn
```
