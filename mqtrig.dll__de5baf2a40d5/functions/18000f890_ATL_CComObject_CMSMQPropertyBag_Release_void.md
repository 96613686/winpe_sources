# ATL::CComObject<CMSMQPropertyBag>::Release(void)

- ea: `0x18000f890`
- end: `0x18000f8d0`
- name: `?Release@?$CComObject@VCMSMQPropertyBag@@@ATL@@UEAAKXZ`
- size: `64`
- prototype: `__int64 __fastcall(CMSMQPropertyBag *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f8e0`

## callees

- `0x18000dc1c`
- `0x18000f890`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CMSMQPropertyBag>::Release(CMSMQPropertyBag *a1)
{
  int v1; // ebx
  unsigned int v2; // ebx

  v1 = *((_DWORD *)a1 + 4);
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v2 = v1 - 1;
    *((_DWORD *)a1 + 4) = v2;
    if ( !v2 )
    {
      _InterlockedIncrement(&dword_18002CFF8);
      if ( a1 )
        ATL::CComObject<CMSMQPropertyBag>::`scalar deleting destructor'(a1);
      _InterlockedDecrement(&dword_18002CFF8);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000f890  push    rbx
0x18000f892  sub     rsp, 20h
0x18000f896  mov     ebx, [rcx+10h]
0x18000f899  cmp     ebx, 7FFFFFFFh
0x18000f89f  jnz     short loc_18000F8A8
0x18000f8a1  mov     ebx, 7FFFFFFEh
0x18000f8a6  jmp     short loc_18000F8C8
0x18000f8a8  sub     ebx, 1
0x18000f8ab  mov     [rcx+10h], ebx
0x18000f8ae  jnz     short loc_18000F8C8
0x18000f8b0  lock inc cs:dword_18002CFF8
0x18000f8b7  test    rcx, rcx
0x18000f8ba  jz      short loc_18000F8C1
0x18000f8bc  call    ??_G?$CComObject@VCMSMQPropertyBag@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<CMSMQPropertyBag>::`scalar deleting destructor'(uint)
0x18000f8c1  lock dec cs:dword_18002CFF8
0x18000f8c8  mov     eax, ebx
0x18000f8ca  add     rsp, 20h
0x18000f8ce  pop     rbx
0x18000f8cf  retn
```
