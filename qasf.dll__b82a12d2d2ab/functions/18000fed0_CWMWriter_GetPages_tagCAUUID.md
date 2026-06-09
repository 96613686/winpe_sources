# CWMWriter::GetPages(tagCAUUID *)

- ea: `0x18000fed0`
- end: `0x18000ff0d`
- name: `?GetPages@CWMWriter@@UEAAJPEAUtagCAUUID@@@Z`
- size: `61`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, struct tagCAUUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000fed0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000fee4`
- `ole32!CoTaskMemAlloc` at `0x18000fee4`

## pseudocode

```c
__int64 __fastcall CWMWriter::GetPages(CWMWriter *this, struct tagCAUUID *a2)
{
  GUID *v3; // rax

  a2->cElems = 1;
  v3 = (GUID *)CoTaskMemAlloc(0x10u);
  a2->pElems = v3;
  if ( !v3 )
    return 2147942414LL;
  *v3 = CLSID_WMAsfWriterProperties;
  return 0;
}

```

## disassembly

```asm
0x18000fed0  push    rbx
0x18000fed2  sub     rsp, 20h
0x18000fed6  mov     ecx, 10h; cb
0x18000fedb  mov     dword ptr [rdx], 1
0x18000fee1  mov     rbx, rdx
0x18000fee4  call    cs:__imp_CoTaskMemAlloc
0x18000feea  mov     [rbx+8], rax
0x18000feee  test    rax, rax
0x18000fef1  jnz     short loc_18000FEFA
0x18000fef3  mov     eax, 8007000Eh
0x18000fef8  jmp     short loc_18000FF07
0x18000fefa  movups  xmm0, xmmword ptr cs:CLSID_WMAsfWriterProperties.Data1
0x18000ff01  movdqu  xmmword ptr [rax], xmm0
0x18000ff05  xor     eax, eax
0x18000ff07  add     rsp, 20h
0x18000ff0b  pop     rbx
0x18000ff0c  retn
```
