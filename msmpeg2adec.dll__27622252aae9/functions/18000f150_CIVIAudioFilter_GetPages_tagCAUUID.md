# CIVIAudioFilter::GetPages(tagCAUUID *)

- ea: `0x18000f150`
- end: `0x18000f1a7`
- name: `?GetPages@CIVIAudioFilter@@UEAAJPEAUtagCAUUID@@@Z`
- size: `87`
- prototype: `__int64 __fastcall(CIVIAudioFilter *__hidden this, struct tagCAUUID *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000f150`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f164`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f164`

## pseudocode

```c
__int64 __fastcall CIVIAudioFilter::GetPages(CIVIAudioFilter *this, struct tagCAUUID *a2)
{
  GUID *v3; // rax

  a2->cElems = 2;
  v3 = (GUID *)CoTaskMemAlloc(0x20u);
  a2->pElems = v3;
  if ( !v3 )
    return 2147942414LL;
  *v3 = CLSID_CMPEG2AudDecoderProp;
  a2->pElems[1] = CLSID_CMPEG2AudDecoderProp4Pin;
  return 0;
}

```

## disassembly

```asm
0x18000f150  push    rbx
0x18000f152  sub     rsp, 20h
0x18000f156  mov     ecx, 20h ; ' '; cb
0x18000f15b  mov     dword ptr [rdx], 2
0x18000f161  mov     rbx, rdx
0x18000f164  call    cs:__imp_CoTaskMemAlloc
0x18000f16b  nop     dword ptr [rax+rax+00h]
0x18000f170  mov     [rbx+8], rax
0x18000f174  test    rax, rax
0x18000f177  jnz     short loc_18000F185
0x18000f179  mov     eax, 8007000Eh
0x18000f17e  add     rsp, 20h
0x18000f182  pop     rbx
0x18000f183  retn
0x18000f185  movups  xmm0, xmmword ptr cs:CLSID_CMPEG2AudDecoderProp.Data1
0x18000f18c  movups  xmmword ptr [rax], xmm0
0x18000f18f  mov     rax, [rbx+8]
0x18000f193  movups  xmm0, xmmword ptr cs:CLSID_CMPEG2AudDecoderProp4Pin.Data1
0x18000f19a  movups  xmmword ptr [rax+10h], xmm0
0x18000f19e  xor     eax, eax
0x18000f1a0  add     rsp, 20h
0x18000f1a4  pop     rbx
0x18000f1a5  retn
```
