# CAdapterIpSettings::~CAdapterIpSettings(void)

- ea: `0x1800181b8`
- end: `0x1800181e7`
- name: `??1CAdapterIpSettings@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(CAdapterIpSettings *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180018560`
- `0x18001ee3c`
- `0x18001fc90`
- `0x18001fe80`
- `0x18002db15`
- `0x18002db93`
- `0x18002dba5`
- `0x18002dbb7`

## callees

- `0x1800181b8`
- `0x18001e454`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800181cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800181cf`
- `WS2_32!__imp_WSACleanup` at `0x1800181db`
- `WS2_32!__imp_WSACleanup` at `0x1800181db`

## pseudocode

```c
void __fastcall CAdapterIpSettings::~CAdapterIpSettings(CAdapterIpSettings *this)
{
  void *v2; // rcx

  CAdapterIpSettings::InvalidateAdapterAddresses(this);
  v2 = (void *)*((_QWORD *)this + 4);
  if ( v2 )
    CoTaskMemFree(v2);
  if ( *((_BYTE *)this + 42) )
    WSACleanup();
}

```

## disassembly

```asm
0x1800181b8  push    rbx
0x1800181ba  sub     rsp, 20h
0x1800181be  mov     rbx, rcx
0x1800181c1  call    ?InvalidateAdapterAddresses@CAdapterIpSettings@@AEAAJXZ; CAdapterIpSettings::InvalidateAdapterAddresses(void)
0x1800181c6  mov     rcx, [rbx+20h]; pv
0x1800181ca  test    rcx, rcx
0x1800181cd  jz      short loc_1800181D5
0x1800181cf  call    cs:__imp_CoTaskMemFree
0x1800181d5  cmp     byte ptr [rbx+2Ah], 0
0x1800181d9  jz      short loc_1800181E1
0x1800181db  call    cs:__imp_WSACleanup
0x1800181e1  add     rsp, 20h
0x1800181e5  pop     rbx
0x1800181e6  retn
```
