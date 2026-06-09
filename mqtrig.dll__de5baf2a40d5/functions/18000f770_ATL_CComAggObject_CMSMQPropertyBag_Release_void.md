# ATL::CComAggObject<CMSMQPropertyBag>::Release(void)

- ea: `0x18000f770`
- end: `0x18000f7b0`
- name: `?Release@?$CComAggObject@VCMSMQPropertyBag@@@ATL@@UEAAKXZ`
- size: `64`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000dba4`
- `0x18000f770`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CMSMQPropertyBag>::Release(_DWORD *a1)
{
  int v1; // ebx
  unsigned int v2; // ebx

  v1 = a1[2];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v2 = v1 - 1;
    a1[2] = v2;
    if ( !v2 )
    {
      _InterlockedIncrement(&dword_18002CFF8);
      if ( a1 )
        ATL::CComAggObject<CMSMQPropertyBag>::`scalar deleting destructor'(a1);
      _InterlockedDecrement(&dword_18002CFF8);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000f770  push    rbx
0x18000f772  sub     rsp, 20h
0x18000f776  mov     ebx, [rcx+8]
0x18000f779  cmp     ebx, 7FFFFFFFh
0x18000f77f  jnz     short loc_18000F788
0x18000f781  mov     ebx, 7FFFFFFEh
0x18000f786  jmp     short loc_18000F7A8
0x18000f788  sub     ebx, 1
0x18000f78b  mov     [rcx+8], ebx
0x18000f78e  jnz     short loc_18000F7A8
0x18000f790  lock inc cs:dword_18002CFF8
0x18000f797  test    rcx, rcx
0x18000f79a  jz      short loc_18000F7A1
0x18000f79c  call    ??_G?$CComAggObject@VCMSMQPropertyBag@@@ATL@@QEAAPEAXI@Z; ATL::CComAggObject<CMSMQPropertyBag>::`scalar deleting destructor'(uint)
0x18000f7a1  lock dec cs:dword_18002CFF8
0x18000f7a8  mov     eax, ebx
0x18000f7aa  add     rsp, 20h
0x18000f7ae  pop     rbx
0x18000f7af  retn
```
