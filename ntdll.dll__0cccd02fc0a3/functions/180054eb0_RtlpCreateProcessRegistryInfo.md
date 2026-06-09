# RtlpCreateProcessRegistryInfo

- ea: `0x180054eb0`
- end: `0x180054f79`
- name: `RtlpCreateProcessRegistryInfo`
- size: `201`
- prototype: ``
- caller_count: `15`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007de0`
- `0x18000be70`
- `0x18000c9a0`
- `0x18000ca60`
- `0x18000d0c0`
- `0x18000d3e0`
- `0x18000fd10`
- `0x18005d8e0`
- `0x1800c0470`
- `0x180103010`
- `0x180124a40`
- `0x1801422a0`
- `0x1801428e0`
- `0x180143470`
- `0x18014cea0`

## callees

- `0x1800535c0`
- `0x180053ab0`
- `0x180054eb0`
- `0x180054f80`
- `0x180079610`
- `0x18015e950`

## pseudocode

```c
__int64 __fastcall RtlpCreateProcessRegistryInfo(__int64 *a1)
{
  __int64 v1; // rdx
  int RegistryInfo; // ebx
  int v4; // eax
  __int64 v5; // rax
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v1 = g_RegInfo;
  RegistryInfo = 0;
  if ( !g_RegInfo )
  {
    v7 = -1000000;
    while ( _InterlockedCompareExchange(&InitRegistryInfoCritSect, 1, 0) )
    {
      v4 = InitRegistryInfoCritSect;
      if ( InitRegistryInfoCritSect == 1 )
      {
        ZwDelayExecution(0, &v7);
        v4 = InitRegistryInfoCritSect;
      }
      if ( v4 == 2 )
        goto LABEL_7;
    }
    RtlInitializeCriticalSectionEx(RegistryInfoCritSect, 0, 0);
    InitRegistryInfoCritSect = 2;
LABEL_7:
    RtlEnterCriticalSection(RegistryInfoCritSect);
    RegistryInfo = 0;
    if ( !g_RegInfo )
      RegistryInfo = RtlpMuiRegCreateAndLoadRegistryInfo(&g_RegInfo);
    RtlLeaveCriticalSection(RegistryInfoCritSect);
    v1 = g_RegInfo;
  }
  if ( a1 )
  {
    v5 = 0;
    if ( RegistryInfo >= 0 )
      v5 = v1;
    *a1 = v5;
  }
  return (unsigned int)RegistryInfo;
}

```

## disassembly

```asm
0x180054eb0  mov     [rsp+arg_8], rbx
0x180054eb5  push    rdi
0x180054eb6  sub     rsp, 20h
0x180054eba  mov     rdx, cs:g_RegInfo
0x180054ec1  xor     ebx, ebx
0x180054ec3  mov     rdi, rcx
0x180054ec6  test    rdx, rdx
0x180054ec9  jnz     short loc_180054F3E
0x180054ecb  mov     [rsp+28h+arg_0], 0FFFFFFFFFFF0BDC0h
0x180054ed4  mov     ebx, 1
0x180054ed9  xor     eax, eax
0x180054edb  lock cmpxchg cs:InitRegistryInfoCritSect, ebx
0x180054ee3  jz      short loc_180054F5C
0x180054ee5  mov     eax, cs:InitRegistryInfoCritSect
0x180054eeb  cmp     eax, ebx
0x180054eed  jnz     short loc_180054F01
0x180054eef  lea     rdx, [rsp+28h+arg_0]
0x180054ef4  xor     ecx, ecx
0x180054ef6  call    ZwDelayExecution
0x180054efb  mov     eax, cs:InitRegistryInfoCritSect
0x180054f01  cmp     eax, 2
0x180054f04  jnz     short loc_180054ED9
0x180054f06  lea     rcx, RegistryInfoCritSect
0x180054f0d  call    RtlEnterCriticalSection
0x180054f12  xor     ebx, ebx
0x180054f14  cmp     cs:g_RegInfo, rbx
0x180054f1b  jnz     short loc_180054F2B
0x180054f1d  lea     rcx, g_RegInfo
0x180054f24  call    RtlpMuiRegCreateAndLoadRegistryInfo
0x180054f29  mov     ebx, eax
0x180054f2b  lea     rcx, RegistryInfoCritSect
0x180054f32  call    RtlLeaveCriticalSection
0x180054f37  mov     rdx, cs:g_RegInfo
0x180054f3e  test    rdi, rdi
0x180054f41  jz      short loc_180054F4E
0x180054f43  xor     eax, eax
0x180054f45  test    ebx, ebx
0x180054f47  cmovns  rax, rdx
0x180054f4b  mov     [rdi], rax
0x180054f4e  mov     eax, ebx
0x180054f50  mov     rbx, [rsp+28h+arg_8]
0x180054f55  add     rsp, 20h
0x180054f59  pop     rdi
0x180054f5a  retn
0x180054f5c  xor     r8d, r8d
0x180054f5f  lea     rcx, RegistryInfoCritSect
0x180054f66  xor     edx, edx
0x180054f68  call    RtlInitializeCriticalSectionEx
0x180054f6d  mov     cs:InitRegistryInfoCritSect, 2
0x180054f77  jmp     short loc_180054F06
```
