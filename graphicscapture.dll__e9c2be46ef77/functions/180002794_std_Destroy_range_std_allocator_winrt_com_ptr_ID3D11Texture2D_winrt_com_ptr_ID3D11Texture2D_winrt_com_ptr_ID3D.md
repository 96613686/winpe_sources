# std::_Destroy_range<std::allocator<winrt::com_ptr<ID3D11Texture2D>>>(winrt::com_ptr<ID3D11Texture2D> *,winrt::com_ptr<ID3D11Texture2D> * const,std::allocator<winrt::com_ptr<ID3D11Texture2D>> &)

- ea: `0x180002794`
- end: `0x1800027cb`
- name: `??$_Destroy_range@V?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@std@@@std@@YAXPEAU?$com_ptr@UID3D11Texture2D@@@winrt@@QEAU12@AEAV?$allocator@U?$com_ptr@UID3D11Texture2D@@@winrt@@@0@@Z`
- size: `55`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003644`
- `0x180003740`
- `0x18000d974`
- `0x18000dd88`
- `0x18000eddc`
- `0x180011dec`

## callees

- `0x180002794`
- `0x180006610`

## pseudocode

```c
__int64 __fastcall std::_Destroy_range<std::allocator<winrt::com_ptr<ID3D11Texture2D>>>(__int64 *a1, __int64 *a2)
{
  __int64 *v3; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      if ( *v3 )
        result = winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(v3);
      ++v3;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x180002794  cmp     rcx, rdx
0x180002797  jz      short locret_1800027CA
0x180002799  mov     [rsp+arg_0], rbx
0x18000279e  push    rdi
0x18000279f  sub     rsp, 20h
0x1800027a3  mov     rdi, rdx
0x1800027a6  mov     rbx, rcx
0x1800027a9  cmp     qword ptr [rbx], 0
0x1800027ad  jz      short loc_1800027B7
0x1800027af  mov     rcx, rbx
0x1800027b2  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x1800027b7  add     rbx, 8
0x1800027bb  cmp     rbx, rdi
0x1800027be  jnz     short loc_1800027A9
0x1800027c0  mov     rbx, [rsp+28h+arg_0]
0x1800027c5  add     rsp, 20h
0x1800027c9  pop     rdi
0x1800027ca  retn
```
