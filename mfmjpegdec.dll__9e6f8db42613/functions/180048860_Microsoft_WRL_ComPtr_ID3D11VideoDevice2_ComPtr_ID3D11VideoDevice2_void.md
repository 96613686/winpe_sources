# Microsoft::WRL::ComPtr<ID3D11VideoDevice2>::~ComPtr<ID3D11VideoDevice2>(void)

- ea: `0x180048860`
- end: `0x180048865`
- name: `??1?$ComPtr@UID3D11VideoDevice2@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `void(void *)`
- caller_count: `26`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006f280`
- `0x18006f380`
- `0x18006f3a4`
- `0x18006f434`
- `0x18006f4a0`
- `0x18006f4b2`
- `0x18006f4c4`
- `0x18006f4d6`
- `0x18006f4fa`
- `0x18006f526`
- `0x18006f53c`
- `0x18006f552`
- `0x18006f568`
- `0x18006f581`
- `0x18006f59a`
- `0x18006f5b3`
- `0x18006f667`
- `0x18006f679`
- `0x18006f68b`
- `0x18006f69d`
- `0x18006f6af`
- `0x18006f6c1`
- `0x18006f6e5`
- `0x18006f6f7`
- `0x18006f799`
- `0x18006f8ea`

## callees

- `0x18004a11c`

## pseudocode

```c
// attributes: thunk
void __fastcall Microsoft::WRL::ComPtr<ID3D11VideoDevice2>::~ComPtr<ID3D11VideoDevice2>(__int64 *a1)
{
  Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180048860  jmp     ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
```
