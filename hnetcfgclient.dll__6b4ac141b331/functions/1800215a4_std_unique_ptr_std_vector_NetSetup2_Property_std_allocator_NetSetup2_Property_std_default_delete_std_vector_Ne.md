# std::unique_ptr<std::vector<NetSetup2::Property,std::allocator<NetSetup2::Property>>,std::default_delete<std::vector<NetSetup2::Property,std::allocator<NetSetup2::Property>>>>::_Delete(void)

- ea: `0x1800215a4`
- end: `0x1800215f2`
- name: `?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ`
- size: `78`
- prototype: `void __fastcall(_QWORD **)`
- caller_count: `11`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x180018200`
- `0x180018220`
- `0x180025364`
- `0x180025390`
- `0x180025410`
- `0x180025484`
- `0x1800256f0`
- `0x180026144`
- `0x18002af2c`
- `0x18002c1a0`
- `0x18002c3b8`

## callees

- `0x1800215a4`
- `0x1800215f8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800215c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800215e6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800215c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800215e6`

## pseudocode

```c
void __fastcall std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(_QWORD **a1)
{
  _QWORD *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( *v1 )
    {
      std::vector<NetSetup2::Property>::_Destroy(a1, *v1, v1[1]);
      operator delete((void *)*v1);
      *v1 = 0;
      v1[1] = 0;
      v1[2] = 0;
    }
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x1800215a4  push    rbx
0x1800215a6  sub     rsp, 20h
0x1800215aa  mov     rbx, [rcx]
0x1800215ad  test    rbx, rbx
0x1800215b0  jz      short loc_1800215EC
0x1800215b2  mov     rdx, [rbx]
0x1800215b5  test    rdx, rdx
0x1800215b8  jz      short loc_1800215E3
0x1800215ba  mov     r8, [rbx+8]
0x1800215be  call    ?_Destroy@?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@IEAAXPEAVProperty@NetSetup2@@0@Z; std::vector<NetSetup2::Property>::_Destroy(NetSetup2::Property *,NetSetup2::Property *)
0x1800215c3  mov     rcx, [rbx]
0x1800215c6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800215cc  mov     qword ptr [rbx], 0
0x1800215d3  mov     qword ptr [rbx+8], 0
0x1800215db  mov     qword ptr [rbx+10h], 0
0x1800215e3  mov     rcx, rbx
0x1800215e6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800215ec  add     rsp, 20h
0x1800215f0  pop     rbx
0x1800215f1  retn
```
