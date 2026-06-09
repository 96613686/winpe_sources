# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180020598`
- end: `0x1800205bd`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `37`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `76`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001d420`
- `0x18001e704`
- `0x18001ff00`
- `0x18001ff0c`
- `0x180021cc4`
- `0x180021fec`
- `0x180022210`
- `0x180023b84`
- `0x18003e8fc`
- `0x18003f15c`
- `0x18003f248`
- `0x18003f408`
- `0x18003f8e4`
- `0x18003f930`
- `0x180040020`
- `0x1800412ac`
- `0x180041e20`
- `0x180042480`
- `0x180042e48`
- `0x1800483f8`
- `0x1800485dc`
- `0x1800488a0`
- `0x1800488d8`
- `0x18004897c`
- `0x180048ac4`
- `0x1800492f0`
- `0x180049810`
- `0x1800499c0`
- `0x180049e90`
- `0x18004a148`
- `0x18004a1b8`
- `0x18004a2cc`
- `0x18004a550`
- `0x18004a9f0`
- `0x18004b1e0`
- `0x18004b21c`
- `0x18004b3f0`
- `0x18004c424`
- `0x18004ce10`
- `0x18004d134`
- `0x18004d1c0`
- `0x18004d23c`
- `0x18004e4ec`
- `0x18004ed7c`
- `0x18004f9d0`
- `0x18004fed0`
- `0x180050440`
- `0x180052d30`
- `0x180053ee0`
- `0x180054cf4`

## callees

- `0x180020598`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180020598  sub     rsp, 28h
0x18002059c  mov     rdx, rcx
0x18002059f  xor     eax, eax
0x1800205a1  mov     rcx, [rcx]
0x1800205a4  test    rcx, rcx
0x1800205a7  jz      short loc_1800205B8
0x1800205a9  mov     [rdx], rax
0x1800205ac  mov     rax, [rcx]
0x1800205af  mov     rax, [rax+10h]
0x1800205b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205b8  add     rsp, 28h
0x1800205bc  retn
```
