# Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(void)

- ea: `0x180041620`
- end: `0x18004163d`
- name: `?InternalAddRef@?$ComPtr@UIMFTelemetrySession@@@WRL@Microsoft@@IEBAXXZ`
- size: `29`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003f97c`
- `0x180040690`
- `0x180041040`
- `0x180041130`
- `0x18004bd00`

## callees

- `0x180041620`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IMFTelemetrySession>::InternalAddRef(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180041620  sub     rsp, 28h
0x180041624  mov     rcx, [rcx]
0x180041627  test    rcx, rcx
0x18004162a  jz      short loc_180041638
0x18004162c  mov     rax, [rcx]
0x18004162f  mov     rax, [rax+8]
0x180041633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041638  add     rsp, 28h
0x18004163c  retn
```
