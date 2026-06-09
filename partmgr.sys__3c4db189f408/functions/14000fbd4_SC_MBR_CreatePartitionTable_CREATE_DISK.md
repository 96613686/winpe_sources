# SC_MBR::CreatePartitionTable(_CREATE_DISK *)

- ea: `0x14000fbd4`
- end: `0x14000fc7c`
- name: `?CreatePartitionTable@SC_MBR@@QEAAJPEAU_CREATE_DISK@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(SC_MBR *__hidden this, struct _CREATE_DISK *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ea44`

## callees

- `0x14000fc84`
- `0x140010f20`
- `0x140011440`

## pseudocode

```c
__int64 __fastcall SC_MBR::CreatePartitionTable(SC_DISK **this, struct _CREATE_DISK *a2)
{
  __int64 v4; // rbx
  DWORD Signature; // eax
  __int64 v7; // [rsp+20h] [rbp-D8h] BYREF
  DWORD v8; // [rsp+28h] [rbp-D0h]
  _BYTE v9[180]; // [rsp+2Ch] [rbp-CCh] BYREF

  memset(v9, 0, sizeof(v9));
  v4 = *((_QWORD *)*this + 33);
  memset((void *)(v4 + 446), 0, 0x40u);
  *(_WORD *)(v4 + 510) = -21931;
  *(_DWORD *)(v4 + 440) = 0;
  Signature = a2->Mbr.Signature;
  v7 = 0;
  v8 = Signature;
  return SC_MBR::WritePartitionTable(this, (struct SC_DISK_LAYOUT *)&v7);
}

```

## disassembly

```asm
0x14000fbd4  mov     [rsp+arg_8], rbx
0x14000fbd9  mov     [rsp+arg_10], rsi
0x14000fbde  push    rdi
0x14000fbdf  sub     rsp, 0F0h
0x14000fbe6  mov     rax, cs:__security_cookie
0x14000fbed  xor     rax, rsp
0x14000fbf0  mov     [rsp+0F8h+var_18], rax
0x14000fbf8  mov     rdi, rdx
0x14000fbfb  mov     rsi, rcx
0x14000fbfe  xor     edx, edx; Val
0x14000fc00  lea     rcx, [rsp+0F8h+var_CC]; void *
0x14000fc05  mov     r8d, 0B4h; Size
0x14000fc0b  call    memset
0x14000fc10  mov     rax, [rsi]
0x14000fc13  xor     edx, edx; Val
0x14000fc15  mov     rbx, [rax+108h]
0x14000fc1c  lea     r8d, [rdx+40h]; Size
0x14000fc20  lea     rcx, [rbx+1BEh]; void *
0x14000fc27  call    memset
0x14000fc2c  xor     ecx, ecx
0x14000fc2e  mov     word ptr [rbx+1FEh], 0AA55h
0x14000fc37  mov     [rbx+1B8h], ecx
0x14000fc3d  lea     rdx, [rsp+0F8h+var_D8]; struct SC_DISK_LAYOUT *
0x14000fc42  mov     eax, [rdi+4]
0x14000fc45  mov     [rsp+0F8h+var_D8], rcx
0x14000fc4a  mov     rcx, rsi; this
0x14000fc4d  mov     [rsp+0F8h+var_D0], eax
0x14000fc51  call    ?WritePartitionTable@SC_MBR@@QEAAJPEAVSC_DISK_LAYOUT@@@Z; SC_MBR::WritePartitionTable(SC_DISK_LAYOUT *)
0x14000fc56  mov     rcx, [rsp+0F8h+var_18]
0x14000fc5e  xor     rcx, rsp; StackCookie
0x14000fc61  call    __security_check_cookie
0x14000fc66  lea     r11, [rsp+0F8h+var_8]
0x14000fc6e  mov     rbx, [r11+18h]
0x14000fc72  mov     rsi, [r11+20h]
0x14000fc76  mov     rsp, r11
0x14000fc79  pop     rdi
0x14000fc7a  retn
```
