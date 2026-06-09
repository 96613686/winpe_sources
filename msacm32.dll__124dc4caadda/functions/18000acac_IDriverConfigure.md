# IDriverConfigure

- ea: `0x18000acac`
- end: `0x18000ad33`
- name: `IDriverConfigure`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b420`

## callees

- `0x1800018e0`
- `0x1800043d0`
- `0x18000acac`

## pseudocode

```c

```

## disassembly

```asm
0x18000acac  sub     rsp, 48h
0x18000acb0  xor     eax, eax
0x18000acb2  xorps   xmm0, xmm0
0x18000acb5  cmp     dword ptr [rcx], 2
0x18000acb8  movups  [rsp+48h+var_28], xmm0
0x18000acbd  mov     [rsp+48h+var_18], eax
0x18000acc1  jnz     short loc_18000ACCC
0x18000acc3  mov     r10, rcx
0x18000acc6  mov     rcx, [rcx+14h]
0x18000acca  jmp     short loc_18000ACD4
0x18000accc  cmp     dword ptr [rcx], 1
0x18000accf  jnz     short loc_18000AD2E
0x18000acd1  xor     r10d, r10d
0x18000acd4  test    dword ptr [rcx+38h], 10000000h
0x18000acdb  jz      short loc_18000ACE4
0x18000acdd  mov     eax, 5
0x18000ace2  jmp     short loc_18000AD2E
0x18000ace4  mov     eax, [rcx+34h]
0x18000ace7  xor     r9d, r9d
0x18000acea  lea     r11d, [r9+7]
0x18000acee  and     eax, r11d
0x18000acf1  cmp     al, 1
0x18000acf3  jnz     short loc_18000AD14
0x18000acf5  mov     dword ptr [rsp+48h+var_28], 14h
0x18000acfd  lea     r9, [rsp+48h+var_28]
0x18000ad02  mov     rax, [rcx+70h]
0x18000ad06  mov     qword ptr [rsp+48h+var_28+4], rax
0x18000ad0b  lea     rax, [rcx+78h]
0x18000ad0f  mov     qword ptr [rsp+48h+var_28+0Ch], rax
0x18000ad14  mov     r8, rdx
0x18000ad17  mov     edx, r11d
0x18000ad1a  test    r10, r10
0x18000ad1d  jz      short loc_18000AD29
0x18000ad1f  mov     rcx, r10
0x18000ad22  call    IDriverMessage
0x18000ad27  jmp     short loc_18000AD2E
0x18000ad29  call    IDriverMessageId
0x18000ad2e  add     rsp, 48h
0x18000ad32  retn
```
