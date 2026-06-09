# std::vector<std::unique_ptr<NetSetup2::NetworkInterface,std::default_delete<NetSetup2::NetworkInterface>>,std::allocator<std::unique_ptr<NetSetup2::NetworkInterface,std::default_delete<NetSetup2::NetworkInterface>>>>::~vector<std::unique_ptr<NetSetup2::NetworkInterface,std::default_delete<NetSetup2::NetworkInterface>>,std::allocator<std::unique_ptr<NetSetup2::NetworkInterface,std::default_delete<NetSetup2::NetworkInterface>>>>(void)

- ea: `0x18002543c`
- end: `0x18002547c`
- name: `??1?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x18002dc6b`
- `0x18002dd7d`
- `0x18002dd8f`
- `0x18002ddb3`
- `0x18002ddc5`
- `0x18002ddd7`

## callees

- `0x18002543c`
- `0x18002568c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180025459`
- `msvcrt!??3@YAXPEAX@Z` at `0x180025459`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::~vector<std::unique_ptr<NetSetup2::NetworkInterface>>(
        _QWORD *a1)
{
  if ( *a1 )
  {
    std::vector<std::unique_ptr<NetSetup2::Mux>>::_Destroy(a1, *a1, a1[1]);
    operator delete((void *)*a1);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18002543c  push    rbx
0x18002543e  sub     rsp, 20h
0x180025442  mov     rdx, [rcx]
0x180025445  mov     rbx, rcx
0x180025448  test    rdx, rdx
0x18002544b  jz      short loc_180025476
0x18002544d  mov     r8, [rcx+8]
0x180025451  call    ?_Destroy@?$vector@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@2@0@Z; std::vector<std::unique_ptr<NetSetup2::Mux>>::_Destroy(std::unique_ptr<NetSetup2::Mux> *,std::unique_ptr<NetSetup2::Mux> *)
0x180025456  mov     rcx, [rbx]
0x180025459  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002545f  mov     qword ptr [rbx], 0
0x180025466  mov     qword ptr [rbx+8], 0
0x18002546e  mov     qword ptr [rbx+10h], 0
0x180025476  add     rsp, 20h
0x18002547a  pop     rbx
0x18002547b  retn
```
