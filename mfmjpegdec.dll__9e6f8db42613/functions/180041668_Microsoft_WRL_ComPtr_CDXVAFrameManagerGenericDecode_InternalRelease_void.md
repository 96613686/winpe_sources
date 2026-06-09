# Microsoft::WRL::ComPtr<CDXVAFrameManagerGenericDecode>::InternalRelease(void)

- ea: `0x180041668`
- end: `0x180041686`
- name: `?InternalRelease@?$ComPtr@VCDXVAFrameManagerGenericDecode@@@WRL@Microsoft@@IEAAKXZ`
- size: `30`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003f104`
- `0x18003f2e0`
- `0x18004ac0c`
- `0x18004b21c`
- `0x18004d088`
- `0x18004d23c`

## callees

- `0x180041668`
- `0x1800426e0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<CDXVAFrameManagerGenericDecode>::InternalRelease(__int64 *a1)
{
  __int64 v1; // rdx
  __int64 result; // rax

  v1 = *a1;
  result = 0;
  if ( *a1 )
  {
    *a1 = 0;
    return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CDXVAFrameManager>::Release(v1);
  }
  return result;
}

```

## disassembly

```asm
0x180041668  sub     rsp, 28h
0x18004166c  mov     rdx, [rcx]
0x18004166f  xor     eax, eax
0x180041671  test    rdx, rdx
0x180041674  jz      short loc_180041681
0x180041676  mov     [rcx], rax
0x180041679  mov     rcx, rdx
0x18004167c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCDXVAFrameManager@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CDXVAFrameManager>::Release(void)
0x180041681  add     rsp, 28h
0x180041685  retn
```
