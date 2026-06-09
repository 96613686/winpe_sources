# std::default_delete<VolumeEntry>::operator()(VolumeEntry *)

- ea: `0x1800144e0`
- end: `0x180014509`
- name: `??R?$default_delete@UVolumeEntry@@@std@@QEBAXPEAUVolumeEntry@@@Z`
- size: `41`
- prototype: `void __fastcall(__int64, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800143e4`

## callees

- `0x180001bd4`
- `0x180014370`
- `0x1800144e0`

## pseudocode

```c
void __fastcall std::default_delete<VolumeEntry>::operator()(__int64 a1, char *a2)
{
  if ( a2 )
  {
    std::wstring::~wstring(a2 + 40);
    operator delete(a2);
  }
}

```

## disassembly

```asm
0x1800144e0  test    rdx, rdx
0x1800144e3  jz      short locret_180014508
0x1800144e5  push    rbx
0x1800144e6  sub     rsp, 20h
0x1800144ea  lea     rcx, [rdx+28h]
0x1800144ee  mov     rbx, rdx
0x1800144f1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800144f6  mov     edx, 70h ; 'p'; unsigned __int64
0x1800144fb  mov     rcx, rbx; void *
0x1800144fe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014503  add     rsp, 20h
0x180014507  pop     rbx
0x180014508  retn
```
