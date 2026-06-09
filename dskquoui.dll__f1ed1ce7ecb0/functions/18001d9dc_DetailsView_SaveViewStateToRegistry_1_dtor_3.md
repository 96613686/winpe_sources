# _DetailsView::SaveViewStateToRegistry_::_1_::dtor$3

- ea: `0x18001d9dc`
- end: `0x18001d9ec`
- name: `_DetailsView::SaveViewStateToRegistry_::_1_::dtor$3`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180007834`

## pseudocode

```c
void __fastcall DetailsView::SaveViewStateToRegistry_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  CCriticalSection::~CCriticalSection((LPCRITICAL_SECTION)(a2 + 96));
}

```

## disassembly

```asm
0x18001d9dc  lea     rcx, [rdx+40h]
0x18001d9e3  add     rcx, 20h ; ' '; lpCriticalSection
0x18001d9e7  jmp     ??1CCriticalSection@@QEAA@XZ; CCriticalSection::~CCriticalSection(void)
```
