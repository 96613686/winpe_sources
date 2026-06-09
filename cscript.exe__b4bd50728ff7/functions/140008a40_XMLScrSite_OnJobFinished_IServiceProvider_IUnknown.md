# XMLScrSite::OnJobFinished(IServiceProvider *,IUnknown *)

- ea: `0x140008a40`
- end: `0x140008a75`
- name: `?OnJobFinished@XMLScrSite@@UEAAJPEAUIServiceProvider@@PEAUIUnknown@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, struct IServiceProvider *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x140008a40`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall XMLScrSite::OnJobFinished(XMLScrSite *this, struct IServiceProvider *a2, struct IUnknown *a3)
{
  __int64 v3; // rbx
  __int64 v4; // rcx

  v3 = *((_QWORD *)this + 2);
  v4 = *(_QWORD *)(v3 + 672);
  if ( v4 )
    (*(void (__fastcall **)(__int64, struct IServiceProvider *, struct IUnknown *))(*(_QWORD *)v4 + 16LL))(v4, a2, a3);
  *(_QWORD *)(v3 + 672) = 0;
  return 0;
}

```

## disassembly

```asm
0x140008a40  push    rbx
0x140008a42  sub     rsp, 20h
0x140008a46  mov     rbx, [rcx+10h]
0x140008a4a  mov     rcx, [rbx+2A0h]
0x140008a51  test    rcx, rcx
0x140008a54  jz      short loc_140008A62
0x140008a56  mov     rax, [rcx]
0x140008a59  mov     rax, [rax+10h]
0x140008a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a62  mov     qword ptr [rbx+2A0h], 0
0x140008a6d  xor     eax, eax
0x140008a6f  add     rsp, 20h
0x140008a73  pop     rbx
0x140008a74  retn
```
