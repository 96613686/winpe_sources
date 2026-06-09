# WcmCommon::details::TPEnvironment::~TPEnvironment(void)

- ea: `0x18000d3a0`
- end: `0x18000d3b8`
- name: `??1TPEnvironment@details@WcmCommon@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(WcmCommon::details::TPEnvironment *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180058e47`

## callees

- `0x18000d3a0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000d3ad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18000d3ad`

## pseudocode

```c
void __fastcall WcmCommon::details::TPEnvironment::~TPEnvironment(WcmCommon::details::TPEnvironment *this)
{
  struct _TP_POOL *v1; // rcx

  v1 = (struct _TP_POOL *)*((_QWORD *)this + 9);
  if ( v1 )
    CloseThreadpool(v1);
}

```

## disassembly

```asm
0x18000d3a0  sub     rsp, 28h
0x18000d3a4  mov     rcx, [rcx+48h]; ptpp
0x18000d3a8  test    rcx, rcx
0x18000d3ab  jz      short loc_18000D3B3
0x18000d3ad  call    cs:__imp_CloseThreadpool
0x18000d3b3  add     rsp, 28h
0x18000d3b7  retn
```
