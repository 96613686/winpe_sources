# ATL::CComObject<CFaxCommon>::Release(void)

- ea: `0x180004360`
- end: `0x1800043b8`
- name: `?Release@?$CComObject@VCFaxCommon@@@ATL@@UEAAKXZ`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800012d0`
- `0x180004360`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFaxCommon>::Release(_DWORD *a1)
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
      _InterlockedIncrement(&dword_18001EB58);
      if ( a1 )
      {
        a1[2] = 1;
        *(_QWORD *)a1 = &ATL::CComObject<CFaxCommon>::`vftable';
        _InterlockedDecrement(&dword_18001EB58);
        operator delete(a1);
      }
      _InterlockedDecrement(&dword_18001EB58);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180004360  push    rbx
0x180004362  sub     rsp, 20h
0x180004366  mov     ebx, [rcx+8]
0x180004369  cmp     ebx, 7FFFFFFFh
0x18000436f  jnz     short loc_180004378
0x180004371  mov     ebx, 7FFFFFFEh
0x180004376  jmp     short loc_1800043B0
0x180004378  sub     ebx, 1
0x18000437b  mov     [rcx+8], ebx
0x18000437e  jnz     short loc_1800043B0
0x180004380  lock inc cs:dword_18001EB58
0x180004387  test    rcx, rcx
0x18000438a  jz      short loc_1800043A9
0x18000438c  lea     rax, ??_7?$CComObject@VCFaxCommon@@@ATL@@6B@; const ATL::CComObject<CFaxCommon>::`vftable'
0x180004393  mov     dword ptr [rcx+8], 1
0x18000439a  mov     [rcx], rax
0x18000439d  lock dec cs:dword_18001EB58
0x1800043a4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800043a9  lock dec cs:dword_18001EB58
0x1800043b0  mov     eax, ebx
0x1800043b2  add     rsp, 20h
0x1800043b6  pop     rbx
0x1800043b7  retn
```
