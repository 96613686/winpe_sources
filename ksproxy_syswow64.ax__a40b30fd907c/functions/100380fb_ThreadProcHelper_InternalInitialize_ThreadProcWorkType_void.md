# ThreadProcHelper::InternalInitialize(ThreadProcWorkType,void *)

- ea: `0x100380fb`
- end: `0x100381d2`
- name: `?InternalInitialize@ThreadProcHelper@@IAEJW4ThreadProcWorkType@@PAX@Z`
- size: `215`
- prototype: `int __thiscall(int this, int, HANDLE hSourceHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x10037eb2`

## callees

- `0x100075ad`
- `0x100075cd`
- `0x1000f6d4`
- `0x1000f70b`
- `0x100380fb`
- `0x1003883c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100381a1`
- `KERNEL32!GetLastError` at `0x100381a1`
- `KERNEL32!CreateThread` at `0x10038179`
- `KERNEL32!CreateThread` at `0x10038179`
- `KERNEL32!GetCurrentProcess` at `0x10038136`
- `KERNEL32!GetCurrentProcess` at `0x1003813e`
- `KERNEL32!GetCurrentProcess` at `0x10038136`
- `KERNEL32!GetCurrentProcess` at `0x1003813e`
- `KERNEL32!DuplicateHandle` at `0x10038150`
- `KERNEL32!DuplicateHandle` at `0x10038150`

## string_xrefs

- `0x10038116`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`
- `0x1003815e`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`
- `0x100381ba`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\threadprochelper.cpp`

## pseudocode

```c
int __thiscall ThreadProcHelper::InternalInitialize(int this, int a2, HANDLE hSourceHandle)
{
  signed int v4; // esi
  HANDLE CurrentProcess; // esi
  HANDLE v6; // eax
  HANDLE Thread; // eax
  signed int LastError; // eax
  void *v10; // [esp+0h] [ebp-8h]
  const char *v11; // [esp+4h] [ebp-4h]
  const char *savedregs; // [esp+8h] [ebp+0h]
  int retaddr; // [esp+Ch] [ebp+4h]

  if ( !*(_DWORD *)(this + 16) || *(_DWORD *)(this + 16) == -1 )
  {
    *(_DWORD *)(this + 56) = 0;
    _reset___unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__QAEXPAX_Z(
      (void **)(this + 24),
      0);
    CurrentProcess = GetCurrentProcess();
    v6 = GetCurrentProcess();
    if ( !DuplicateHandle(v6, hSourceHandle, CurrentProcess, (LPHANDLE)(this + 24), 0, 0, 2u) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
               v10,
               (unsigned int)v11,
               savedregs);
    Thread = CreateThread(0, 0, ThreadProcHelper::ThreadProc, (LPVOID)this, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__stdcall *)(void *),&int CloseHandle(void *)>>::reset(
      (void **)(this + 16),
      Thread);
    if ( *(_DWORD *)(this + 16) && *(_DWORD *)(this + 16) != -1 )
    {
      wil::slim_event_t<1>::wait(this + 8);
      return *(_DWORD *)(this + 20);
    }
    LastError = GetLastError();
    v4 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v4 = LastError;
    if ( v4 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
        (void *)v4,
        (unsigned int)v10,
        v11,
        (int)savedregs);
  }
  else
  {
    v4 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (wil::details::in1diag3 *)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\threadprochelper.cpp",
      (void *)0x8000FFFF,
      (unsigned int)v10,
      v11,
      (int)savedregs);
  }
  return v4;
}

```

## disassembly

```asm
0x100380fb  mov     edi, edi
0x100380fd  push    ebp; int
0x100380fe  mov     ebp, esp
0x10038100  push    ebx; char *
0x10038101  mov     ebx, ecx
0x10038103  push    esi; unsigned int
0x10038104  cmp     dword ptr [ebx+10h], 0
0x10038108  jz      short loc_10038122
0x1003810a  cmp     dword ptr [ebx+10h], 0FFFFFFFFh
0x1003810e  jz      short loc_10038122
0x10038110  mov     esi, 8000FFFFh
0x10038115  push    esi
0x10038116  push    offset aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1003811b  push    5Ah ; 'Z'
0x1003811d  jmp     loc_100381C1
0x10038122  push    edi
0x10038123  lea     edi, [ebx+18h]
0x10038126  mov     dword ptr [ebx+38h], 0
0x1003812d  push    0
0x1003812f  mov     ecx, edi
0x10038131  call    ?reset@?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAEXPAX@Z
0x10038136  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x1003813c  mov     esi, eax
0x1003813e  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x10038144  push    2; dwOptions
0x10038146  push    0; bInheritHandle
0x10038148  push    0; dwDesiredAccess
0x1003814a  push    edi; lpTargetHandle
0x1003814b  push    esi; hTargetProcessHandle
0x1003814c  push    [ebp+hSourceHandle]; hSourceHandle
0x1003814f  push    eax; hSourceProcessHandle
0x10038150  call    ds:__imp__DuplicateHandle@28; DuplicateHandle(x,x,x,x,x,x,x)
0x10038156  pop     edi
0x10038157  test    eax, eax
0x10038159  jnz     short loc_1003816D
0x1003815b  mov     ecx, [ebp+4]
0x1003815e  push    offset aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x10038163  push    64h ; 'd'
0x10038165  pop     edx
0x10038166  call    ?Return_GetLastError@in1diag3@details@wil@@YGJPAXIPBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1003816b  jmp     short loc_100381CC
0x1003816d  xor     eax, eax
0x1003816f  push    eax; lpThreadId
0x10038170  push    eax; dwCreationFlags
0x10038171  push    ebx; lpParameter
0x10038172  push    offset ?ThreadProc@ThreadProcHelper@@CGKPAX@Z; lpStartAddress
0x10038177  push    eax; dwStackSize
0x10038178  push    eax; lpThreadAttributes
0x10038179  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x1003817f  lea     esi, [ebx+10h]
0x10038182  push    eax
0x10038183  mov     ecx, esi
0x10038185  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6GHPAX@Z$1?CloseHandle@@YGH0@Z@details@wil@@@details@wil@@QAEXPAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1003818a  cmp     dword ptr [esi], 0
0x1003818d  jz      short loc_100381A1
0x1003818f  cmp     dword ptr [esi], 0FFFFFFFFh
0x10038192  jz      short loc_100381A1
0x10038194  lea     ecx, [ebx+8]; unsigned int
0x10038197  call    ?wait@?$slim_event_t@$00@wil@@QAE_NXZ; wil::slim_event_t<1>::wait(void)
0x1003819c  mov     eax, [ebx+14h]
0x1003819f  jmp     short loc_100381CC
0x100381a1  call    ds:__imp__GetLastError@0; GetLastError()
0x100381a7  movzx   esi, ax
0x100381aa  or      esi, 80070000h
0x100381b0  test    eax, eax
0x100381b2  cmovle  esi, eax
0x100381b5  test    esi, esi
0x100381b7  jns     short loc_100381CA
0x100381b9  push    esi; void *
0x100381ba  push    offset aMultimediaDsho_3; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x100381bf  push    6Ch ; 'l'
0x100381c1  mov     ecx, [ebp+4]
0x100381c4  pop     edx
0x100381c5  call    ?Return_Hr@in1diag3@details@wil@@YGXPAXIPBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x100381ca  mov     eax, esi
0x100381cc  pop     esi
0x100381cd  pop     ebx
0x100381ce  pop     ebp
0x100381cf  retn    8
```
