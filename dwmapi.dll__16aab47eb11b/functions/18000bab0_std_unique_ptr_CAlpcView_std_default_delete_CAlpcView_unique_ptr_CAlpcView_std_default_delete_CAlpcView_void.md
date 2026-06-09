# std::unique_ptr<CAlpcView,std::default_delete<CAlpcView>>::~unique_ptr<CAlpcView,std::default_delete<CAlpcView>>(void)

- ea: `0x18000bab0`
- end: `0x18000bac6`
- name: `??1?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `23`
- callee_count: `2`
- tags: ``

## callers

- `0x180001570`
- `0x180001a10`
- `0x180002920`
- `0x1800035f0`
- `0x180005060`
- `0x1800052c0`
- `0x180005980`
- `0x180005bc0`
- `0x180006b30`
- `0x180007c50`
- `0x1800080e0`
- `0x1800084b0`
- `0x180008cc0`
- `0x180008ec0`
- `0x18000925c`
- `0x180009340`
- `0x180009690`
- `0x18000a3c0`
- `0x18000a650`
- `0x18000b808`
- `0x18000b8dc`
- `0x18000b92c`
- `0x180015224`

## callees

- `0x18000bab0`
- `0x18001114c`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<CAlpcView>::operator()();
  return result;
}

```

## disassembly

```asm
0x18000bab0  sub     rsp, 28h
0x18000bab4  mov     rdx, [rcx]
0x18000bab7  test    rdx, rdx
0x18000baba  jz      short loc_18000BAC1
0x18000babc  call    ??R?$default_delete@VCAlpcView@@@std@@QEBAXPEAVCAlpcView@@@Z; std::default_delete<CAlpcView>::operator()(CAlpcView *)
0x18000bac1  add     rsp, 28h
0x18000bac5  retn
```
