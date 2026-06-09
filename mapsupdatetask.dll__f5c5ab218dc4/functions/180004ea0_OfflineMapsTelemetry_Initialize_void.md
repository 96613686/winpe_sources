# OfflineMapsTelemetry::Initialize(void)

- ea: `0x180004ea0`
- end: `0x180004ec4`
- name: `?Initialize@OfflineMapsTelemetry@@EEAAXXZ`
- size: `36`
- prototype: `void __fastcall(OfflineMapsTelemetry *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004ea0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180004ead`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180004ead`

## pseudocode

```c
void __fastcall OfflineMapsTelemetry::Initialize(OfflineMapsTelemetry *this)
{
  _OWORD *v1; // rbx

  v1 = (_OWORD *)((char *)this + 24);
  if ( CoCreateGuid((GUID *)((char *)this + 24)) < 0 )
    *v1 = 0;
}

```

## disassembly

```asm
0x180004ea0  push    rbx
0x180004ea2  sub     rsp, 20h
0x180004ea6  lea     rbx, [rcx+18h]
0x180004eaa  mov     rcx, rbx; pguid
0x180004ead  call    cs:__imp_CoCreateGuid
0x180004eb3  test    eax, eax
0x180004eb5  jns     short loc_180004EBE
0x180004eb7  xorps   xmm0, xmm0
0x180004eba  movdqu  xmmword ptr [rbx], xmm0
0x180004ebe  add     rsp, 20h
0x180004ec2  pop     rbx
0x180004ec3  retn
```
