# RawInputProvidersTracing::SpatialInputTelemetryProperties::~SpatialInputTelemetryProperties(void)

- ea: `0x180119bd4`
- end: `0x180119c3d`
- name: `??1SpatialInputTelemetryProperties@RawInputProvidersTracing@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(RawInputProvidersTracing::SpatialInputTelemetryProperties *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18011c440`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119be1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119bf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119c05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119c17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119c29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119be1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119bf3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119c05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119c17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180119c29`

## pseudocode

```c
void __fastcall RawInputProvidersTracing::SpatialInputTelemetryProperties::~SpatialInputTelemetryProperties(
        HSTRING *this)
{
  WindowsDeleteString(this[7]);
  this[7] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
  WindowsDeleteString(this[5]);
  this[5] = 0;
  WindowsDeleteString(this[4]);
  this[4] = 0;
  WindowsDeleteString(this[1]);
  this[1] = 0;
}

```

## disassembly

```asm
0x180119bd4  push    rbx
0x180119bd6  sub     rsp, 20h
0x180119bda  mov     rbx, rcx
0x180119bdd  mov     rcx, [rcx+38h]; string
0x180119be1  call    cs:__imp_WindowsDeleteString
0x180119be7  mov     qword ptr [rbx+38h], 0
0x180119bef  mov     rcx, [rbx+30h]; string
0x180119bf3  call    cs:__imp_WindowsDeleteString
0x180119bf9  mov     qword ptr [rbx+30h], 0
0x180119c01  mov     rcx, [rbx+28h]; string
0x180119c05  call    cs:__imp_WindowsDeleteString
0x180119c0b  mov     qword ptr [rbx+28h], 0
0x180119c13  mov     rcx, [rbx+20h]; string
0x180119c17  call    cs:__imp_WindowsDeleteString
0x180119c1d  mov     qword ptr [rbx+20h], 0
0x180119c25  mov     rcx, [rbx+8]; string
0x180119c29  call    cs:__imp_WindowsDeleteString
0x180119c2f  mov     qword ptr [rbx+8], 0
0x180119c37  add     rsp, 20h
0x180119c3b  pop     rbx
0x180119c3c  retn
```
