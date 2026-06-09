# Windows::Storage::Streams::CBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::DefaultMarshaler>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18001c040`
- end: `0x18001c05d`
- name: `?GetRuntimeClassName@?$CBuffer@VCBuffer_StandardCleanup@Streams@Storage@Windows@@UDefaultMarshaler@234@@Streams@Storage@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(__int64, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001c056`

## pseudocode

```c
HRESULT __fastcall Windows::Storage::Streams::CBuffer<Windows::Storage::Streams::CBuffer_StandardCleanup,Windows::Storage::Streams::DefaultMarshaler>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Storage.Streams.IBuffer", 0x1Fu, a2);
}

```

## disassembly

```asm
0x18001c040  mov     qword ptr [rdx], 0
0x18001c047  lea     rcx, aWindowsStorage; "Windows.Storage.Streams.IBuffer"
0x18001c04e  mov     r8, rdx
0x18001c051  mov     edx, 1Fh
0x18001c056  jmp     cs:__imp_WindowsCreateString
```
