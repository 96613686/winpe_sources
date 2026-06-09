# __scrt_dllmain_uninitialize_c

- ea: `0x180001894`
- end: `0x1800018c4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001428`

## callees

- `0x180001894`
- `0x180001e6c`
- `0x180001eda`
- `0x180001efe`
- `0x180004b10`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::EndPresent(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001894  sub     rsp, 28h
0x180001898  call    __scrt_is_ucrt_dll_in_use
0x18000189d  test    eax, eax
0x18000189f  jz      short loc_1800018B1
0x1800018a1  lea     rcx, Table; Table
0x1800018a8  add     rsp, 28h
0x1800018ac  jmp     _execute_onexit_table
0x1800018b1  call    ?EndPresent@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@UEAAJXZ; winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::EndPresent(void)
0x1800018b6  test    eax, eax
0x1800018b8  jnz     short loc_1800018BF
0x1800018ba  call    _o__cexit_0
0x1800018bf  add     rsp, 28h
0x1800018c3  retn
```
