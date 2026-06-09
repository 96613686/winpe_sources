# FileExplorerTelemetry::CabViewCopy::~CabViewCopy(void)

- ea: `0x18000faa0`
- end: `0x18000fac5`
- name: `??1CabViewCopy@FileExplorerTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(FileExplorerTelemetry::CabViewCopy *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180010440`

## callees

- `0x18000f968`
- `0x18000fefc`

## pseudocode

```c
void __fastcall FileExplorerTelemetry::CabViewCopy::~CabViewCopy(FileExplorerTelemetry::CabViewCopy *this)
{
  *(_QWORD *)this = &FileExplorerTelemetry::CabViewCopy::`vftable';
  wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x18000faa0  push    rbx
0x18000faa2  sub     rsp, 20h
0x18000faa6  lea     rax, ??_7CabViewCopy@FileExplorerTelemetry@@6B@; const FileExplorerTelemetry::CabViewCopy::`vftable'
0x18000faad  mov     rbx, rcx
0x18000fab0  mov     [rcx], rax
0x18000fab3  call    ?Destroy@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000fab8  mov     rcx, rbx
0x18000fabb  add     rsp, 20h
0x18000fabf  pop     rbx
0x18000fac0  jmp     ??1?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
