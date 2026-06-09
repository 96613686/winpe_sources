# GdiInitializeHandleTracker(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1800a09a0`
- end: `0x1800a0a61`
- name: `?GdiInitializeHandleTracker@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `193`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800a09a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a0a2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a0a2f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a0a0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a0a0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a09d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a09d1`

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
0x1800a09a0  push    rbp
0x1800a09a2  mov     rbp, rsp
0x1800a09a5  sub     rsp, 40h
0x1800a09a9  lea     rax, [rbp+hKey]
0x1800a09ad  mov     [rbp+hKey], 0
0x1800a09b5  mov     r9d, 1; samDesired
0x1800a09bb  mov     [rsp+40h+phkResult], rax; phkResult
0x1800a09c0  xor     r8d, r8d; ulOptions
0x1800a09c3  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800a09ca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a09d1  call    cs:__imp_RegOpenKeyExW
0x1800a09d7  test    eax, eax
0x1800a09d9  jnz     short loc_1800A0A35
0x1800a09db  mov     rcx, [rbp+hKey]; hKey
0x1800a09df  lea     r9, [rbp+Type]; lpType
0x1800a09e3  mov     [rbp+Type], eax
0x1800a09e6  lea     rdx, aGdiprocesshand; "GDIProcessHandleQuota"
0x1800a09ed  mov     dword ptr [rbp+Data], eax
0x1800a09f0  xor     r8d, r8d; lpReserved
0x1800a09f3  lea     rax, [rbp+cbData]
0x1800a09f7  mov     [rbp+cbData], 4
0x1800a09fe  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800a0a03  lea     rax, [rbp+Data]
0x1800a0a07  mov     [rsp+40h+phkResult], rax; lpData
0x1800a0a0c  call    cs:__imp_RegQueryValueExW
0x1800a0a12  test    eax, eax
0x1800a0a14  jnz     short loc_1800A0A2B
0x1800a0a16  cmp     [rbp+Type], 4
0x1800a0a1a  jnz     short loc_1800A0A2B
0x1800a0a1c  cmp     [rbp+cbData], 4
0x1800a0a20  jnz     short loc_1800A0A2B
0x1800a0a22  mov     ecx, dword ptr [rbp+Data]
0x1800a0a25  mov     cs:?g_DefaultHandleQuota@@3KA, ecx; ulong g_DefaultHandleQuota
0x1800a0a2b  mov     rcx, [rbp+hKey]; hKey
0x1800a0a2f  call    cs:__imp_RegCloseKey
0x1800a0a35  mov     ecx, cs:?g_DefaultHandleQuota@@3KA; ulong g_DefaultHandleQuota
0x1800a0a3b  xorps   xmm0, xmm0
0x1800a0a3e  mov     eax, 1
0x1800a0a43  cvtsi2sd xmm0, rcx
0x1800a0a48  mulsd   xmm0, cs:__real@3fe999999999999a
0x1800a0a50  cvttsd2si rcx, xmm0
0x1800a0a55  mov     cs:?g_LeakTrackingThreshold@@3KA, ecx; ulong g_LeakTrackingThreshold
0x1800a0a5b  add     rsp, 40h
0x1800a0a5f  pop     rbp
0x1800a0a60  retn
```
