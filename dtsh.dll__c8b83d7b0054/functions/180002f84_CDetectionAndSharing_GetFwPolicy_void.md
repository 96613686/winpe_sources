# CDetectionAndSharing::GetFwPolicy(void)

- ea: `0x180002f84`
- end: `0x180002fbc`
- name: `?GetFwPolicy@CDetectionAndSharing@@AEAAJXZ`
- size: `56`
- prototype: `__int64 __fastcall(CDetectionAndSharing *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800025c8`
- `0x180002b64`
- `0x180002dd0`

## callees

- `0x180002f84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002fb1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002fb1`

## pseudocode

```c
HRESULT __fastcall CDetectionAndSharing::GetFwPolicy(CDetectionAndSharing *this)
{
  LPVOID *ppv; // rcx

  ppv = (LPVOID *)((char *)this + 72);
  if ( *ppv )
    return 0;
  else
    return CoCreateInstance(
             &GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd,
             0,
             0x401u,
             &GUID_98325047_c671_4174_8d81_defcd3f03186,
             ppv);
}

```

## disassembly

```asm
0x180002f84  sub     rsp, 38h
0x180002f88  add     rcx, 48h ; 'H'
0x180002f8c  cmp     qword ptr [rcx], 0
0x180002f90  jz      short loc_180002F96
0x180002f92  xor     eax, eax
0x180002f94  jmp     short loc_180002FB7
0x180002f96  mov     [rsp+38h+ppv], rcx; ppv
0x180002f9b  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x180002fa2  lea     rcx, _GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd; rclsid
0x180002fa9  xor     edx, edx; pUnkOuter
0x180002fab  mov     r8d, 401h; dwClsContext
0x180002fb1  call    cs:__imp_CoCreateInstance
0x180002fb7  add     rsp, 38h
0x180002fbb  retn
```
