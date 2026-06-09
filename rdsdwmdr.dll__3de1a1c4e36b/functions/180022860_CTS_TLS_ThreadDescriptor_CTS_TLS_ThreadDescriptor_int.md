# CTS_TLS_ThreadDescriptor::CTS_TLS_ThreadDescriptor(int)

- ea: `0x180022860`
- end: `0x1800228e5`
- name: `??0CTS_TLS_ThreadDescriptor@@AEAA@H@Z`
- size: `133`
- prototype: `CTS_TLS_ThreadDescriptor *__fastcall(CTS_TLS_ThreadDescriptor *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180023fec`

## callees

- `0x1800228ec`

## string_xrefs

- `0x180022871`: `CTS_TLS_ThreadDescriptor`

## pseudocode

```c
CTS_TLS_ThreadDescriptor *__fastcall CTS_TLS_ThreadDescriptor::CTS_TLS_ThreadDescriptor(
        CTS_TLS_ThreadDescriptor *this,
        int a2)
{
  CTS_TLS_ThreadDescriptor *result; // rax

  *((_DWORD *)this + 6) = -607474739;
  *((_QWORD *)this + 2) = "CTS_TLS_ThreadDescriptor";
  *((_DWORD *)this + 7) = 1;
  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 4) = this;
  *((_QWORD *)this + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
  *(_QWORD *)this = &CServerVCChannel::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)this + 1) = &CTS_TLS_ThreadDescriptor::`vftable'{for `CTSObject'};
  *((_DWORD *)this + 10) = 0;
  CVPtrList::CVPtrList((CTS_TLS_ThreadDescriptor *)((char *)this + 48));
  *((_DWORD *)this + 124) = a2;
  result = this;
  *(_QWORD *)((char *)this + 500) = 0;
  return result;
}

```

## disassembly

```asm
0x180022860  mov     [rsp+arg_0], rbx
0x180022865  push    rdi
0x180022866  sub     rsp, 20h
0x18002286a  mov     dword ptr [rcx+18h], 0DBCAABCDh
0x180022871  lea     rax, aCtsTlsThreadde; "CTS_TLS_ThreadDescriptor"
0x180022878  mov     [rcx+10h], rax
0x18002287c  mov     rdi, rcx
0x18002287f  mov     dword ptr [rcx+1Ch], 1
0x180022886  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x18002288d  mov     [rcx], rax
0x180022890  mov     ebx, edx
0x180022892  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180022899  mov     [rcx+20h], rcx
0x18002289d  mov     [rcx+8], rax
0x1800228a1  lea     rax, ??_7CServerVCChannel@@6BINonDelegatingUnknown@@@; const CServerVCChannel::`vftable'{for `INonDelegatingUnknown'}
0x1800228a8  mov     [rcx], rax
0x1800228ab  lea     rax, ??_7CTS_TLS_ThreadDescriptor@@6BCTSObject@@@; const CTS_TLS_ThreadDescriptor::`vftable'{for `CTSObject'}
0x1800228b2  mov     [rcx+8], rax
0x1800228b6  mov     dword ptr [rcx+28h], 0
0x1800228bd  add     rcx, 30h ; '0'; this
0x1800228c1  call    ??0CVPtrList@@QEAA@XZ; CVPtrList::CVPtrList(void)
0x1800228c6  mov     [rdi+1F0h], ebx
0x1800228cc  mov     rax, rdi
0x1800228cf  mov     rbx, [rsp+28h+arg_0]
0x1800228d4  mov     qword ptr [rdi+1F4h], 0
0x1800228df  add     rsp, 20h
0x1800228e3  pop     rdi
0x1800228e4  retn
```
