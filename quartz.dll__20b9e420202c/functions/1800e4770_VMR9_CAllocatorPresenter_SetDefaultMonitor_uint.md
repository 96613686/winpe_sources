# VMR9::CAllocatorPresenter::SetDefaultMonitor(uint)

- ea: `0x1800e4770`
- end: `0x1800e4877`
- name: `?SetDefaultMonitor@CAllocatorPresenter@VMR9@@UEAAJI@Z`
- size: `263`
- prototype: `int(VMR9::CAllocatorPresenter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800e4318`
- `0x1800e4770`
- `0x1800e4930`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800e4833`
- `KERNEL32!LeaveCriticalSection` at `0x1800e4858`
- `KERNEL32!LeaveCriticalSection` at `0x1800e4833`
- `KERNEL32!LeaveCriticalSection` at `0x1800e4858`
- `KERNEL32!EnterCriticalSection` at `0x1800e478b`
- `KERNEL32!EnterCriticalSection` at `0x1800e478b`
- `ADVAPI32!RegDeleteValueW` at `0x1800e4809`
- `ADVAPI32!RegDeleteValueW` at `0x1800e4809`
- `ADVAPI32!RegOpenKeyExW` at `0x1800e47e6`
- `ADVAPI32!RegOpenKeyExW` at `0x1800e47e6`
- `ADVAPI32!RegCloseKey` at `0x1800e4820`
- `ADVAPI32!RegCloseKey` at `0x1800e4820`

## pseudocode

```c
__int64 __fastcall VMR9::CAllocatorPresenter::SetDefaultMonitor(VMR9::CAllocatorPresenter *this, unsigned int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  HKEY v5; // rdx
  VMR9 *v6; // rcx
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  LSTATUS v9; // ebx
  LSTATUS v10; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( (unsigned int)VMR9::CMonitorArray::MatchGUID(
                       (VMR9::CAllocatorPresenter *)((char *)this + 48),
                       a2,
                       (unsigned int *)&hKey) == 1 )
  {
    v7 = -2147024809;
LABEL_12:
    LeaveCriticalSection(v2);
    return v7;
  }
  if ( a2 )
  {
    v7 = VMR9::SetRegistryUINT(v6, v5, (const unsigned __int16 *)a2);
    goto LABEL_12;
  }
  hKey = 0;
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Multimedia\\ActiveMovie Filters\\Video Mixing Renderer 9",
         0,
         2u,
         &hKey);
  v9 = v8;
  if ( v8 == 2 )
    goto LABEL_10;
  if ( !v8 )
  {
    v10 = RegDeleteValueW(hKey, L"D3D9 Connection Device ID");
    if ( v10 != 2 )
      v9 = v10;
    RegCloseKey(hKey);
    if ( !v9 )
    {
LABEL_10:
      v7 = 0;
      goto LABEL_12;
    }
  }
  LeaveCriticalSection(v2);
  return v9 | 0x80070000;
}

```

## disassembly

```asm
0x1800e4770  mov     [rsp+arg_8], rbx
0x1800e4775  mov     [rsp+arg_10], rsi
0x1800e477a  push    rdi
0x1800e477b  sub     rsp, 30h
0x1800e477f  lea     rdi, [rcx+8]
0x1800e4783  mov     rbx, rcx
0x1800e4786  mov     rcx, rdi; lpCriticalSection
0x1800e4789  mov     esi, edx
0x1800e478b  call    cs:__imp_EnterCriticalSection
0x1800e4792  nop     dword ptr [rax+rax+00h]
0x1800e4797  lea     rcx, [rbx+30h]; this
0x1800e479b  mov     edx, esi; unsigned int
0x1800e479d  lea     r8, [rsp+38h+hKey]; unsigned int *
0x1800e47a2  call    ?MatchGUID@CMonitorArray@VMR9@@QEAAJIPEAK@Z; VMR9::CMonitorArray::MatchGUID(uint,ulong *)
0x1800e47a7  cmp     eax, 1
0x1800e47aa  jnz     short loc_1800E47B6
0x1800e47ac  mov     ebx, 80070057h
0x1800e47b1  jmp     loc_1800E4855
0x1800e47b6  test    esi, esi
0x1800e47b8  jnz     loc_1800E484B
0x1800e47be  lea     rax, [rsp+38h+hKey]
0x1800e47c3  mov     [rsp+38h+hKey], 0
0x1800e47cc  lea     r9d, [rsi+2]; samDesired
0x1800e47d0  mov     [rsp+38h+phkResult], rax; phkResult
0x1800e47d5  xor     r8d, r8d; ulOptions
0x1800e47d8  lea     rdx, chRegistryKey9; "Software\\Microsoft\\Multimedia\\Active"...
0x1800e47df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e47e6  call    cs:__imp_RegOpenKeyExW
0x1800e47ed  nop     dword ptr [rax+rax+00h]
0x1800e47f2  mov     ebx, eax
0x1800e47f4  cmp     eax, 2
0x1800e47f7  jz      short loc_1800E4847
0x1800e47f9  test    eax, eax
0x1800e47fb  jnz     short loc_1800E4830
0x1800e47fd  mov     rcx, [rsp+38h+hKey]; hKey
0x1800e4802  lea     rdx, aD3d9Connection; "D3D9 Connection Device ID"
0x1800e4809  call    cs:__imp_RegDeleteValueW
0x1800e4810  nop     dword ptr [rax+rax+00h]
0x1800e4815  mov     rcx, [rsp+38h+hKey]; hKey
0x1800e481a  cmp     eax, 2
0x1800e481d  cmovnz  ebx, eax
0x1800e4820  call    cs:__imp_RegCloseKey
0x1800e4827  nop     dword ptr [rax+rax+00h]
0x1800e482c  test    ebx, ebx
0x1800e482e  jz      short loc_1800E4847
0x1800e4830  mov     rcx, rdi; lpCriticalSection
0x1800e4833  call    cs:__imp_LeaveCriticalSection
0x1800e483a  nop     dword ptr [rax+rax+00h]
0x1800e483f  or      ebx, 80070000h
0x1800e4845  jmp     short loc_1800E4864
0x1800e4847  xor     ebx, ebx
0x1800e4849  jmp     short loc_1800E4855
0x1800e484b  mov     r8d, esi; unsigned __int16 *
0x1800e484e  call    ?SetRegistryUINT@VMR9@@YAJPEAUHKEY__@@PEBGK@Z; VMR9::SetRegistryUINT(HKEY__ *,ushort const *,ulong)
0x1800e4853  mov     ebx, eax
0x1800e4855  mov     rcx, rdi; lpCriticalSection
0x1800e4858  call    cs:__imp_LeaveCriticalSection
0x1800e485f  nop     dword ptr [rax+rax+00h]
0x1800e4864  mov     rsi, [rsp+38h+arg_10]
0x1800e4869  mov     eax, ebx
0x1800e486b  mov     rbx, [rsp+38h+arg_8]
0x1800e4870  add     rsp, 30h
0x1800e4874  pop     rdi
0x1800e4875  retn
```
