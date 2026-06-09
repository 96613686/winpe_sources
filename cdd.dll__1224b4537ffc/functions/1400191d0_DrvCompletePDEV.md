# DrvCompletePDEV

- ea: `0x1400191d0`
- end: `0x140019219`
- name: `DrvCompletePDEV`
- size: `73`
- prototype: `FN_DrvCompletePDEV`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400191d0`
- `0x140019220`

## pseudocode

```c
void __stdcall DrvCompletePDEV(DHPDEV dhpdev, HDEV hdev)
{
  *((_QWORD *)dhpdev + 1) = hdev;
  CStagingPool::AssociateGdiSurfaces((CStagingPool *)(dhpdev + 1376), hdev);
  if ( ((_DWORD)dhpdev[475] & 0x20000000) != 0 )
    CStagingPool::AssociateGdiSurfaces((CStagingPool *)(dhpdev + 1580), hdev);
}

```

## disassembly

```asm
0x1400191d0  mov     [rsp+arg_0], rbx
0x1400191d5  push    rdi
0x1400191d6  sub     rsp, 20h
0x1400191da  mov     rbx, rcx
0x1400191dd  mov     [rcx+8], rdx
0x1400191e1  add     rcx, 1580h; this
0x1400191e8  mov     rdi, rdx
0x1400191eb  call    ?AssociateGdiSurfaces@CStagingPool@@QEAAXPEAUHDEV__@@@Z; CStagingPool::AssociateGdiSurfaces(HDEV__ *)
0x1400191f0  test    dword ptr [rbx+76Ch], 20000000h
0x1400191fa  jnz     short loc_140019208
0x1400191fc  mov     rbx, [rsp+28h+arg_0]
0x140019201  add     rsp, 20h
0x140019205  pop     rdi
0x140019206  retn
0x140019208  lea     rcx, [rbx+18B0h]; this
0x14001920f  mov     rdx, rdi; HDEV
0x140019212  call    ?AssociateGdiSurfaces@CStagingPool@@QEAAXPEAUHDEV__@@@Z; CStagingPool::AssociateGdiSurfaces(HDEV__ *)
0x140019217  jmp     short loc_1400191FC
```
