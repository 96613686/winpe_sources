# ATL::CComObject<CRAHelperClass>::`scalar deleting destructor'(uint)

- ea: `0x180008a70`
- end: `0x180008aa0`
- name: `??_G?$CComObject@VCRAHelperClass@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CRAHelperClass *__fastcall(CRAHelperClass *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800088ac`
- `0x180008a70`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008a8c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008a8c`

## pseudocode

```c
CRAHelperClass *__fastcall ATL::CComObject<CRAHelperClass>::`scalar deleting destructor'(CRAHelperClass *a1, char a2)
{
  ATL::CComObject<CRAHelperClass>::~CComObject<CRAHelperClass>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180008a70  mov     [rsp+arg_0], rbx
0x180008a75  push    rdi
0x180008a76  sub     rsp, 20h
0x180008a7a  mov     ebx, edx
0x180008a7c  mov     rdi, rcx
0x180008a7f  call    ??1?$CComObject@VCRAHelperClass@@@ATL@@UEAA@XZ; ATL::CComObject<CRAHelperClass>::~CComObject<CRAHelperClass>(void)
0x180008a84  test    bl, 1
0x180008a87  jz      short loc_180008A92
0x180008a89  mov     rcx, rdi
0x180008a8c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008a92  mov     rbx, [rsp+28h+arg_0]
0x180008a97  mov     rax, rdi
0x180008a9a  add     rsp, 20h
0x180008a9e  pop     rdi
0x180008a9f  retn
```
