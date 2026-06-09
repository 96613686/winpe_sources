# ATL::CComSafeArray<ushort *,8>::Destroy(void)

- ea: `0x18001d74c`
- end: `0x18001d783`
- name: `?Destroy@?$CComSafeArray@PEAG$07@ATL@@QEAAJXZ`
- size: `55`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c7bc`
- `0x18001caec`
- `0x18001d3f0`
- `0x18001dc18`
- `0x18001e100`
- `0x18001e4f8`
- `0x18001e9b8`
- `0x18001ec30`
- `0x18001ef70`
- `0x18001f22c`
- `0x1800281bc`
- `0x180028d64`

## callees

- `0x18001d74c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001d76c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001d76c`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001d75f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001d75f`

## pseudocode

```c
HRESULT __fastcall ATL::CComSafeArray<unsigned short *,8>::Destroy(SAFEARRAY **a1)
{
  HRESULT result; // eax
  SAFEARRAY *v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    result = SafeArrayUnlock(v3);
    if ( result >= 0 )
    {
      result = SafeArrayDestroy(*a1);
      if ( result >= 0 )
        *a1 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001d74c  push    rbx
0x18001d74e  sub     rsp, 20h
0x18001d752  mov     rbx, rcx
0x18001d755  xor     eax, eax
0x18001d757  mov     rcx, [rcx]; psa
0x18001d75a  test    rcx, rcx
0x18001d75d  jz      short loc_18001D77D
0x18001d75f  call    cs:__imp_SafeArrayUnlock
0x18001d765  test    eax, eax
0x18001d767  js      short loc_18001D77D
0x18001d769  mov     rcx, [rbx]; psa
0x18001d76c  call    cs:__imp_SafeArrayDestroy
0x18001d772  test    eax, eax
0x18001d774  js      short loc_18001D77D
0x18001d776  mov     qword ptr [rbx], 0
0x18001d77d  add     rsp, 20h
0x18001d781  pop     rbx
0x18001d782  retn
```
