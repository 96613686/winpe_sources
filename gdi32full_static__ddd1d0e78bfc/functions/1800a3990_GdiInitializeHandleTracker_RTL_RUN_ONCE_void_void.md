# GdiInitializeHandleTracker(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800a3990`
- end: `0x1800a3a64`
- name: `?GdiInitializeHandleTracker@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `212`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800a3990`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3a2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a3a2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a3a02`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a3a02`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a39c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a39c1`

## pseudocode

```c
__int64 __fastcall GdiInitializeHandleTracker(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  __int64 result; // rax
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Windows", 0, 1u, &hKey) )
  {
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"GDIProcessHandleQuota", 0, &Type, Data, &cbData) && Type == 4 && cbData == 4 )
      g_DefaultHandleQuota = *(_DWORD *)Data;
    RegCloseKey(hKey);
  }
  result = 1;
  g_LeakTrackingThreshold = (int)((double)(int)g_DefaultHandleQuota * 0.8);
  return result;
}

```

## disassembly

```asm
0x1800a3990  push    rbp
0x1800a3992  mov     rbp, rsp
0x1800a3995  sub     rsp, 40h
0x1800a3999  lea     rax, [rbp+hKey]
0x1800a399d  mov     [rbp+hKey], 0
0x1800a39a5  mov     r9d, 1; samDesired
0x1800a39ab  mov     [rsp+40h+phkResult], rax; phkResult
0x1800a39b0  xor     r8d, r8d; ulOptions
0x1800a39b3  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800a39ba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a39c1  call    cs:__imp_RegOpenKeyExW
0x1800a39c8  nop     dword ptr [rax+rax+00h]
0x1800a39cd  test    eax, eax
0x1800a39cf  jnz     short loc_1800A3A37
0x1800a39d1  mov     rcx, [rbp+hKey]; hKey
0x1800a39d5  lea     r9, [rbp+Type]; lpType
0x1800a39d9  mov     [rbp+Type], eax
0x1800a39dc  lea     rdx, aGdiprocesshand; "GDIProcessHandleQuota"
0x1800a39e3  mov     dword ptr [rbp+Data], eax
0x1800a39e6  xor     r8d, r8d; lpReserved
0x1800a39e9  lea     rax, [rbp+cbData]
0x1800a39ed  mov     [rbp+cbData], 4
0x1800a39f4  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a39f9  lea     rax, [rbp+Data]
0x1800a39fd  mov     [rsp+40h+phkResult], rax; lpData
0x1800a3a02  call    cs:__imp_RegQueryValueExW
0x1800a3a09  nop     dword ptr [rax+rax+00h]
0x1800a3a0e  test    eax, eax
0x1800a3a10  jnz     short loc_1800A3A27
0x1800a3a12  cmp     [rbp+Type], 4
0x1800a3a16  jnz     short loc_1800A3A27
0x1800a3a18  cmp     [rbp+cbData], 4
0x1800a3a1c  jnz     short loc_1800A3A27
0x1800a3a1e  mov     ecx, dword ptr [rbp+Data]
0x1800a3a21  mov     cs:?g_DefaultHandleQuota@@3KA, ecx; ulong g_DefaultHandleQuota
0x1800a3a27  mov     rcx, [rbp+hKey]; hKey
0x1800a3a2b  call    cs:__imp_RegCloseKey
0x1800a3a32  nop     dword ptr [rax+rax+00h]
0x1800a3a37  mov     ecx, cs:?g_DefaultHandleQuota@@3KA; ulong g_DefaultHandleQuota
0x1800a3a3d  xorps   xmm0, xmm0
0x1800a3a40  mov     eax, 1
0x1800a3a45  cvtsi2sd xmm0, rcx
0x1800a3a4a  mulsd   xmm0, cs:__real@3fe999999999999a
0x1800a3a52  cvttsd2si rcx, xmm0
0x1800a3a57  mov     cs:?g_LeakTrackingThreshold@@3KA, ecx; ulong g_LeakTrackingThreshold
0x1800a3a5d  add     rsp, 40h
0x1800a3a61  pop     rbp
0x1800a3a62  retn
```
