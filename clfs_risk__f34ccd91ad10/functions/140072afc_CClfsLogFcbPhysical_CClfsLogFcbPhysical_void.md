# CClfsLogFcbPhysical::~CClfsLogFcbPhysical(void)

- ea: `0x140072afc`
- end: `0x140072bce`
- name: `??1CClfsLogFcbPhysical@@UEAA@XZ`
- size: `210`
- prototype: `void __fastcall(CClfsLogFcbPhysical *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000e140`

## callees

- `0x14000e634`
- `0x14000e83c`
- `0x140072afc`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140072b60`
- `ntoskrnl!ExDeleteResourceLite` at `0x140072b73`
- `ntoskrnl!ExDeleteResourceLite` at `0x140072b60`
- `ntoskrnl!ExDeleteResourceLite` at `0x140072b73`
- `ntoskrnl!RtlInitUnicodeString` at `0x140072ba2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140072ba2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072b91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072b91`

## pseudocode

```c
void __fastcall CClfsLogFcbPhysical::~CClfsLogFcbPhysical(CClfsLogFcbPhysical *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CClfsLogFcbPhysical::`vftable'{for `CClfsLogFcbCommon'};
  *((_QWORD *)this + 76) = &CClfsLogFcbPhysical::`vftable'{for `IFcbPhysical'};
  *((_QWORD *)this + 77) = &CClfsLogFcbPhysical::`vftable'{for `IFcbCancelIo'};
  *((_QWORD *)this + 78) = &CClfsLogFcbPhysical::`vftable'{for `IPendingRequestQueue'};
  *((_QWORD *)this + 79) = &CClfsLogFcbPhysical::`vftable'{for `IObservable'};
  *((_QWORD *)this + 80) = &CClfsLogFcbPhysical::`vftable'{for `ILogManagementSupport'};
  ExDeleteResourceLite((PERESOURCE)((char *)this + 1096));
  ExDeleteResourceLite((PERESOURCE)((char *)this + 1200));
  v2 = (void *)*((_QWORD *)this + 41);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    RtlInitUnicodeString((PUNICODE_STRING)this + 20, 0);
  }
  CDynamicLsnQ::~CDynamicLsnQ((CClfsLogFcbPhysical *)((char *)this + 5576));
  CClfsLogFcbCommon::~CClfsLogFcbCommon(this);
}

```

## disassembly

```asm
0x140072afc  mov     [rsp+arg_0], rbx
0x140072b01  push    rdi
0x140072b02  sub     rsp, 20h
0x140072b06  lea     rax, ??_7CClfsLogFcbPhysical@@6BCClfsLogFcbCommon@@@; const CClfsLogFcbPhysical::`vftable'{for `CClfsLogFcbCommon'}
0x140072b0d  mov     rbx, rcx
0x140072b10  mov     [rcx], rax
0x140072b13  lea     rax, ??_7CClfsLogFcbPhysical@@6BIFcbPhysical@@@; const CClfsLogFcbPhysical::`vftable'{for `IFcbPhysical'}
0x140072b1a  mov     [rcx+260h], rax
0x140072b21  lea     rax, ??_7CClfsLogFcbPhysical@@6BIFcbCancelIo@@@; const CClfsLogFcbPhysical::`vftable'{for `IFcbCancelIo'}
0x140072b28  mov     [rcx+268h], rax
0x140072b2f  lea     rax, ??_7CClfsLogFcbPhysical@@6BIPendingRequestQueue@@@; const CClfsLogFcbPhysical::`vftable'{for `IPendingRequestQueue'}
0x140072b36  mov     [rcx+270h], rax
0x140072b3d  lea     rax, ??_7CClfsLogFcbPhysical@@6BIObservable@@@; const CClfsLogFcbPhysical::`vftable'{for `IObservable'}
0x140072b44  mov     [rcx+278h], rax
0x140072b4b  lea     rax, ??_7CClfsLogFcbPhysical@@6BILogManagementSupport@@@; const CClfsLogFcbPhysical::`vftable'{for `ILogManagementSupport'}
0x140072b52  mov     [rcx+280h], rax
0x140072b59  add     rcx, 448h; Resource
0x140072b60  call    cs:__imp_ExDeleteResourceLite
0x140072b67  nop     dword ptr [rax+rax+00h]
0x140072b6c  lea     rcx, [rbx+4B0h]; Resource
0x140072b73  call    cs:__imp_ExDeleteResourceLite
0x140072b7a  nop     dword ptr [rax+rax+00h]
0x140072b7f  lea     rdi, [rbx+140h]
0x140072b86  mov     rcx, [rdi+8]; P
0x140072b8a  test    rcx, rcx
0x140072b8d  jz      short loc_140072BAE
0x140072b8f  xor     edx, edx; Tag
0x140072b91  call    cs:__imp_ExFreePoolWithTag
0x140072b98  nop     dword ptr [rax+rax+00h]
0x140072b9d  xor     edx, edx; SourceString
0x140072b9f  mov     rcx, rdi; DestinationString
0x140072ba2  call    cs:__imp_RtlInitUnicodeString
0x140072ba9  nop     dword ptr [rax+rax+00h]
0x140072bae  lea     rcx, [rbx+15C8h]; this
0x140072bb5  call    ??1CDynamicLsnQ@@QEAA@XZ; CDynamicLsnQ::~CDynamicLsnQ(void)
0x140072bba  mov     rcx, rbx; this
0x140072bbd  call    ??1CClfsLogFcbCommon@@UEAA@XZ; CClfsLogFcbCommon::~CClfsLogFcbCommon(void)
0x140072bc2  mov     rbx, [rsp+28h+arg_0]
0x140072bc7  add     rsp, 20h
0x140072bcb  pop     rdi
0x140072bcc  retn
```
