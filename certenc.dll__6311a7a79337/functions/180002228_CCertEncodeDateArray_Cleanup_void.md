# CCertEncodeDateArray::_Cleanup(void)

- ea: `0x180002228`
- end: `0x18000225d`
- name: `?_Cleanup@CCertEncodeDateArray@@AEAAXXZ`
- size: `53`
- prototype: `void __fastcall(CCertEncodeDateArray *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a2c`
- `0x180001a70`
- `0x180002140`
- `0x1800022ac`
- `0x1800022f0`
- `0x180002990`

## callees

- `0x180002228`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000223a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000223a`

## pseudocode

```c
void __fastcall CCertEncodeDateArray::_Cleanup(CCertEncodeDateArray *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    LocalFree(v2);
    *((_QWORD *)this + 8) = 0;
  }
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
}

```

## disassembly

```asm
0x180002228  push    rbx
0x18000222a  sub     rsp, 20h
0x18000222e  mov     rbx, rcx
0x180002231  mov     rcx, [rcx+40h]; hMem
0x180002235  test    rcx, rcx
0x180002238  jz      short loc_180002248
0x18000223a  call    cs:__imp_LocalFree
0x180002240  mov     qword ptr [rbx+40h], 0
0x180002248  mov     qword ptr [rbx+48h], 0
0x180002250  mov     dword ptr [rbx+50h], 0
0x180002257  add     rsp, 20h
0x18000225b  pop     rbx
0x18000225c  retn
```
