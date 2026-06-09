# DrPrinterPort::Remove(void)

- ea: `0x14001ea80`
- end: `0x14001eafb`
- name: `?Remove@DrPrinterPort@@UEAAXXZ`
- size: `123`
- prototype: `void __fastcall(DrPrinterPort *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callees

- `0x1400027b0`
- `0x140003188`
- `0x14000327c`
- `0x14001ea80`

## pseudocode

```c
void __fastcall DrPrinterPort::Remove(DrPrinterPort *this)
{
  _DWORD *v2; // rax

  v2 = operator new(4u, 0x40u);
  if ( v2 )
  {
    *v2 = *((_DWORD *)this + 10);
    RDPDYN_DispatchNewDevMgmtEvent(v2, *(_DWORD *)(*((_QWORD *)this + 4) + 1128LL), 3u, 0);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_6b2c43a11f0a329c1a4acc292f8a4ed9_Traceguids, 4);
  }
  *((_DWORD *)this + 14) = 1;
}

```

## disassembly

```asm
0x14001ea80  push    rbx
0x14001ea82  sub     rsp, 20h
0x14001ea86  mov     edx, 40h ; '@'; unsigned __int64
0x14001ea8b  mov     rbx, rcx
0x14001ea8e  lea     ecx, [rdx-3Ch]; unsigned __int64
0x14001ea91  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x14001ea96  test    rax, rax
0x14001ea99  jz      short loc_14001EABB
0x14001ea9b  mov     edx, [rbx+28h]
0x14001ea9e  xor     r9d, r9d; struct DrDevice *
0x14001eaa1  mov     [rax], edx
0x14001eaa3  mov     rcx, rax; void *
0x14001eaa6  mov     rdx, [rbx+20h]
0x14001eaaa  lea     r8d, [r9+3]; unsigned int
0x14001eaae  mov     edx, [rdx+468h]; unsigned int
0x14001eab4  call    RDPDYN_DispatchNewDevMgmtEvent
0x14001eab9  jmp     short loc_14001EAED
0x14001eabb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eac2  lea     rax, WPP_GLOBAL_Control
0x14001eac9  cmp     rcx, rax
0x14001eacc  jz      short loc_14001EAED
0x14001eace  cmp     byte ptr [rcx+29h], 2
0x14001ead2  jb      short loc_14001EAED
0x14001ead4  mov     rcx, [rcx+18h]
0x14001ead8  lea     r8, WPP_6b2c43a11f0a329c1a4acc292f8a4ed9_Traceguids
0x14001eadf  mov     edx, 1Dh
0x14001eae4  lea     r9d, [rdx-19h]
0x14001eae8  call    WPP_SF_d
0x14001eaed  mov     dword ptr [rbx+38h], 1
0x14001eaf4  add     rsp, 20h
0x14001eaf8  pop     rbx
0x14001eaf9  retn
```
