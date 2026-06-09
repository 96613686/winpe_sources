# [thunk]:CIVIAudioFilter::GetClassID`adjustor{15376}' (_GUID *)

- ea: `0x18000e620`
- end: `0x18000e62c`
- name: `?GetClassID@CIVIAudioFilter@@WDMBA@EAAJPEAU_GUID@@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000e600`

## pseudocode

```c
__int64 __fastcall CIVIAudioFilter::GetClassID(__int64 a1, struct _GUID *a2)
{
  return CIVIAudioFilter::GetClassID((CIVIAudioFilter *)(a1 - 15376), a2);
}

```

## disassembly

```asm
0x18000e620  sub     rcx, 3C10h; this
0x18000e627  jmp     ?GetClassID@CIVIAudioFilter@@UEAAJPEAU_GUID@@@Z; CIVIAudioFilter::GetClassID(_GUID *)
```
