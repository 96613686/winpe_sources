# OfflineMapsTelemetry::Initialize(void)

- ea: `0x180006570`
- end: `0x180006594`
- name: `?Initialize@OfflineMapsTelemetry@@EEAAXXZ`
- size: `36`
- prototype: `void __fastcall(OfflineMapsTelemetry *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006570`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000657d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18000657d`

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
0x180006570  push    rbx
0x180006572  sub     rsp, 20h
0x180006576  lea     rbx, [rcx+18h]
0x18000657a  mov     rcx, rbx; pguid
0x18000657d  call    cs:__imp_CoCreateGuid
0x180006583  test    eax, eax
0x180006585  jns     short loc_18000658E
0x180006587  xorps   xmm0, xmm0
0x18000658a  movdqu  xmmword ptr [rbx], xmm0
0x18000658e  add     rsp, 20h
0x180006592  pop     rbx
0x180006593  retn
```
