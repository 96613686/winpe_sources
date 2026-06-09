# UninitializeCNGNcrypt

- ea: `0x180013d38`
- end: `0x180013e5f`
- name: `UninitializeCNGNcrypt`
- size: `295`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180013880`
- `0x180013a7c`

## callees

- `0x180006f40`
- `0x180007ae0`
- `0x18000a770`
- `0x180013d38`
- `0x180018938`
- `0x180018e18`
- `0x180019a98`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180013dac`
- `ntdll!RtlLeaveCriticalSection` at `0x180013dac`
- `ntdll!RtlEnterCriticalSection` at `0x180013d65`
- `ntdll!RtlEnterCriticalSection` at `0x180013d65`
- `ntdll!RtlDeleteCriticalSection` at `0x180013db5`
- `ntdll!RtlDeleteCriticalSection` at `0x180013e2b`
- `ntdll!RtlDeleteCriticalSection` at `0x180013db5`
- `ntdll!RtlDeleteCriticalSection` at `0x180013e2b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180013df9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180013df9`

## pseudocode

```c
__int64 UninitializeCNGNcrypt()
{
  char v0; // cl
  __int64 v1; // rcx
  __int64 i; // rbx
  void *v3; // rcx

  v0 = dword_18002AB28;
  if ( (dword_18002AB28 & 4) != 0 )
  {
    if ( dword_18002AF1C )
    {
      RtlEnterCriticalSection(&g_csKeyProtectorLock);
      v1 = qword_18002AF48;
      if ( qword_18002AF48 )
      {
        if ( *(_QWORD *)(qword_18002AF48 + 24) )
        {
          NCryptCloseProtectionDescriptor(*(_QWORD *)(qword_18002AF48 + 24));
          v1 = qword_18002AF48;
        }
        MSCryptFree(v1);
        qword_18002AF48 = 0;
        dword_18002AF50 = 0;
      }
      RtlLeaveCriticalSection(&g_csKeyProtectorLock);
      RtlDeleteCriticalSection(&g_csKeyProtectorLock);
      dword_18002AF1C = 0;
    }
    v0 = dword_18002AB28 & 0xFB;
    dword_18002AB28 &= ~4u;
  }
  if ( (v0 & 2) != 0 )
  {
    UninitializeLoader();
    dword_18002AB28 &= ~2u;
  }
  for ( i = 0; i != 43; ++i )
  {
    v3 = (void *)qword_18002ADC0[i];
    if ( v3 )
    {
      BCryptCloseAlgorithmProvider(v3, 0);
      qword_18002ADC0[i] = 0;
    }
  }
  if ( (dword_18002AB28 & 1) != 0 )
  {
    if ( dword_18002ADB0 )
    {
      RtlDeleteCriticalSection(&CriticalSection);
      dword_18002ADB0 = 0;
    }
    dword_18002AB28 &= ~1u;
  }
  if ( (unsigned int)Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline() )
    TlgUnregisterAggregateProvider();
  return CertInUseCleanup();
}

```

## disassembly

```asm
0x180013d38  mov     [rsp+arg_0], rbx
0x180013d3d  push    rsi
0x180013d3e  sub     rsp, 20h
0x180013d42  mov     ecx, cs:dword_18002AB28
0x180013d48  test    cl, 4
0x180013d4b  jz      loc_180013DD4
0x180013d51  mov     eax, cs:dword_18002AF1C
0x180013d57  test    eax, eax
0x180013d59  jz      short loc_180013DC5
0x180013d5b  lea     rbx, g_csKeyProtectorLock
0x180013d62  mov     rcx, rbx; CriticalSection
0x180013d65  call    cs:__imp_RtlEnterCriticalSection
0x180013d6b  mov     rcx, cs:qword_18002AF48
0x180013d72  test    rcx, rcx
0x180013d75  jz      short loc_180013DA9
0x180013d77  mov     rax, [rcx+18h]
0x180013d7b  test    rax, rax
0x180013d7e  jz      short loc_180013D8F
0x180013d80  mov     rcx, rax
0x180013d83  call    NCryptCloseProtectionDescriptor
0x180013d88  mov     rcx, cs:qword_18002AF48
0x180013d8f  call    MSCryptFree
0x180013d94  mov     cs:qword_18002AF48, 0
0x180013d9f  mov     cs:dword_18002AF50, 0
0x180013da9  mov     rcx, rbx; CriticalSection
0x180013dac  call    cs:__imp_RtlLeaveCriticalSection
0x180013db2  mov     rcx, rbx; CriticalSection
0x180013db5  call    cs:__imp_RtlDeleteCriticalSection
0x180013dbb  mov     cs:dword_18002AF1C, 0
0x180013dc5  mov     ecx, cs:dword_18002AB28
0x180013dcb  and     ecx, 0FFFFFFFBh
0x180013dce  mov     cs:dword_18002AB28, ecx
0x180013dd4  test    cl, 2
0x180013dd7  jz      short loc_180013DE5
0x180013dd9  call    UninitializeLoader
0x180013dde  and     cs:dword_18002AB28, 0FFFFFFFDh
0x180013de5  xor     ebx, ebx
0x180013de7  lea     rsi, qword_18002ADC0
0x180013dee  mov     rcx, [rsi+rbx*8]; hAlgorithm
0x180013df2  test    rcx, rcx
0x180013df5  jz      short loc_180013E07
0x180013df7  xor     edx, edx; dwFlags
0x180013df9  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180013dff  mov     qword ptr [rsi+rbx*8], 0
0x180013e07  inc     rbx
0x180013e0a  cmp     rbx, 2Bh ; '+'
0x180013e0e  jnz     short loc_180013DE7
0x180013e10  mov     eax, cs:dword_18002AB28
0x180013e16  test    al, 1
0x180013e18  jz      short loc_180013E42
0x180013e1a  mov     eax, cs:dword_18002ADB0
0x180013e20  test    eax, eax
0x180013e22  jz      short loc_180013E3B
0x180013e24  lea     rcx, CriticalSection; CriticalSection
0x180013e2b  call    cs:__imp_RtlDeleteCriticalSection
0x180013e31  mov     cs:dword_18002ADB0, 0
0x180013e3b  and     cs:dword_18002AB28, 0FFFFFFFEh
0x180013e42  call    Feature_KG_Ncrypt_Telemetry__private_IsEnabledDeviceUsageNoInline
0x180013e47  test    eax, eax
0x180013e49  jz      short loc_180013E50
0x180013e4b  call    TlgUnregisterAggregateProvider
0x180013e50  mov     rbx, [rsp+28h+arg_0]
0x180013e55  add     rsp, 20h
0x180013e59  pop     rsi
0x180013e5a  jmp     CertInUseCleanup
```
