# PublisherLookupNLoader<PublisherManifestResource>::~PublisherLookupNLoader<PublisherManifestResource>(void)

- ea: `0x1800086f4`
- end: `0x180008724`
- name: `??1?$PublisherLookupNLoader@VPublisherManifestResource@@@@QEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007e78`
- `0x180008970`
- `0x180018484`
- `0x180026450`
- `0x180026ba8`
- `0x18004a0c0`
- `0x18004a11a`
- `0x18004a674`
- `0x18004aa9c`

## callees

- `0x1800086f4`
- `0x180009b80`
- `0x18004c010`

## pseudocode

```c
void __fastcall PublisherLookupNLoader<PublisherManifestResource>::~PublisherLookupNLoader<PublisherManifestResource>(
        __int64 a1)
{
  PublisherManifestResource *v1; // rbx

  v1 = (PublisherManifestResource *)(a1 + 24);
  if ( *(_BYTE *)(a1 + 12) )
    (*(void (__fastcall **)(_QWORD, PublisherManifestResource *))(**(_QWORD **)(a1 + 16) + 8LL))(
      *(_QWORD *)(a1 + 16),
      v1);
  PublisherManifestResource::~PublisherManifestResource(v1);
}

```

## disassembly

```asm
0x1800086f4  push    rbx
0x1800086f6  sub     rsp, 20h
0x1800086fa  lea     rbx, [rcx+18h]
0x1800086fe  cmp     byte ptr [rcx+0Ch], 0
0x180008702  jz      short loc_180008717
0x180008704  mov     rcx, [rcx+10h]
0x180008708  mov     rax, [rcx]
0x18000870b  mov     rdx, rbx
0x18000870e  mov     rax, [rax+8]
0x180008712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008717  mov     rcx, rbx; this
0x18000871a  add     rsp, 20h
0x18000871e  pop     rbx
0x18000871f  jmp     ??1PublisherManifestResource@@QEAA@XZ; PublisherManifestResource::~PublisherManifestResource(void)
```
