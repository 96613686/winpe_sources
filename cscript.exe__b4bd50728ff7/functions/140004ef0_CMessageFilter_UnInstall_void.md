# CMessageFilter::UnInstall(void)

- ea: `0x140004ef0`
- end: `0x140004f4c`
- name: `?UnInstall@CMessageFilter@@QEAAXXZ`
- size: `92`
- prototype: `void __fastcall(CMessageFilter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400035a0`

## callees

- `0x140004ef0`
- `0x140017010`

## import_xrefs

- `ole32!CoRegisterMessageFilter` at `0x140004f11`
- `ole32!CoRegisterMessageFilter` at `0x140004f22`
- `ole32!CoRegisterMessageFilter` at `0x140004f11`
- `ole32!CoRegisterMessageFilter` at `0x140004f22`

## pseudocode

```c
void __fastcall CMessageFilter::UnInstall(CMessageFilter *this)
{
  bool v1; // zf
  LPMESSAGEFILTER lpMessageFilter; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_BYTE *)this + 8) == 0;
  lpMessageFilter = 0;
  if ( !v1
    && (CoRegisterMessageFilter(*((LPMESSAGEFILTER *)this + 2), &lpMessageFilter) >= 0
     || CoRegisterMessageFilter(0, &lpMessageFilter) >= 0) )
  {
    if ( lpMessageFilter )
      ((void (__fastcall *)(LPMESSAGEFILTER))lpMessageFilter->lpVtbl->Release)(lpMessageFilter);
    *((_BYTE *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x140004ef0  push    rbx
0x140004ef2  sub     rsp, 20h
0x140004ef6  cmp     byte ptr [rcx+8], 0
0x140004efa  mov     rbx, rcx
0x140004efd  mov     [rsp+28h+lpMessageFilter], 0
0x140004f06  jz      short loc_140004F46
0x140004f08  mov     rcx, [rcx+10h]; lpMessageFilter
0x140004f0c  lea     rdx, [rsp+28h+lpMessageFilter]; lplpMessageFilter
0x140004f11  call    cs:__imp_CoRegisterMessageFilter
0x140004f17  test    eax, eax
0x140004f19  jns     short loc_140004F2C
0x140004f1b  lea     rdx, [rsp+28h+lpMessageFilter]; lplpMessageFilter
0x140004f20  xor     ecx, ecx; lpMessageFilter
0x140004f22  call    cs:__imp_CoRegisterMessageFilter
0x140004f28  test    eax, eax
0x140004f2a  js      short loc_140004F46
0x140004f2c  mov     rcx, [rsp+28h+lpMessageFilter]
0x140004f31  test    rcx, rcx
0x140004f34  jz      short loc_140004F42
0x140004f36  mov     rax, [rcx]
0x140004f39  mov     rax, [rax+10h]
0x140004f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f42  mov     byte ptr [rbx+8], 0
0x140004f46  add     rsp, 20h
0x140004f4a  pop     rbx
0x140004f4b  retn
```
