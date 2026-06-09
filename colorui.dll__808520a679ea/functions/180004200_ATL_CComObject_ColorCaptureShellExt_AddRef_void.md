# ATL::CComObject<ColorCaptureShellExt>::AddRef(void)

- ea: `0x180004200`
- end: `0x180004213`
- name: `?AddRef@?$CComObject@VColorCaptureShellExt@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004220`

## callees

- `0x180004200`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ColorCaptureShellExt>::AddRef(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 32);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 32) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180004200  mov     edx, [rcx+20h]
0x180004203  mov     eax, 7FFFFFFFh
0x180004208  cmp     edx, eax
0x18000420a  jz      short locret_180004212
0x18000420c  lea     eax, [rdx+1]
0x18000420f  mov     [rcx+20h], eax
0x180004212  retn
```
