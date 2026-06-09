# NatpSetWmiDataBlock

- ea: `0x1400429c0`
- end: `0x140042ab6`
- name: `NatpSetWmiDataBlock`
- size: `246`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400021bc`
- `0x1400052a0`
- `0x1400429c0`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x140042a2e`
- `WMILIB!WmiCompleteRequest` at `0x140042a2e`

## pseudocode

```c
__int64 __fastcall NatpSetWmiDataBlock(PDEVICE_OBJECT DeviceObject, PIRP Irp, unsigned int a3, int a4, int a5)
{
  unsigned int v7; // eax
  unsigned int v8; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_DDD(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, a3, a4, a5);
  }
  v7 = WmiCompleteRequest(DeviceObject, Irp, -1073741163, 0, 0);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v8;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, v7);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x1400429c0  mov     [rsp+arg_0], rbx
0x1400429c5  mov     [rsp+arg_8], rbp
0x1400429ca  push    rdi
0x1400429cb  sub     rsp, 30h
0x1400429cf  mov     rbx, rdx
0x1400429d2  mov     rdi, rcx
0x1400429d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400429dc  lea     rbp, WPP_GLOBAL_Control
0x1400429e3  cmp     rcx, rbp
0x1400429e6  jz      short loc_140042A1A
0x1400429e8  mov     eax, [rcx+2Ch]
0x1400429eb  test    al, 1
0x1400429ed  jz      short loc_140042A1A
0x1400429ef  cmp     byte ptr [rcx+29h], 6
0x1400429f3  jb      short loc_140042A1A
0x1400429f5  mov     eax, [rsp+38h+arg_20]
0x1400429f9  mov     edx, 31h ; '1'
0x1400429fe  mov     rcx, [rcx+18h]
0x140042a02  mov     [rsp+38h+var_10], eax
0x140042a06  mov     dword ptr [rsp+38h+PriorityBoost], r9d
0x140042a0b  mov     r9d, r8d
0x140042a0e  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140042a15  call    WPP_SF_DDD
0x140042a1a  xor     r9d, r9d; BufferUsed
0x140042a1d  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x140042a22  mov     r8d, 0C0000295h; Status
0x140042a28  mov     rdx, rbx; Irp
0x140042a2b  mov     rcx, rdi; DeviceObject
0x140042a2e  call    cs:__imp_WmiCompleteRequest
0x140042a35  nop     dword ptr [rax+rax+00h]
0x140042a3a  mov     ebx, eax
0x140042a3c  test    eax, eax
0x140042a3e  jz      short loc_140042A72
0x140042a40  mov     rcx, cs:WPP_GLOBAL_Control
0x140042a47  cmp     rcx, rbp
0x140042a4a  jz      short loc_140042AA3
0x140042a4c  mov     edx, [rcx+2Ch]
0x140042a4f  test    dl, 1
0x140042a52  jz      short loc_140042A72
0x140042a54  cmp     byte ptr [rcx+29h], 2
0x140042a58  jb      short loc_140042A72
0x140042a5a  mov     rcx, [rcx+18h]
0x140042a5e  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140042a65  mov     edx, 32h ; '2'
0x140042a6a  mov     r9d, eax
0x140042a6d  call    WPP_SF_d
0x140042a72  mov     rcx, cs:WPP_GLOBAL_Control
0x140042a79  cmp     rcx, rbp
0x140042a7c  jz      short loc_140042AA3
0x140042a7e  mov     eax, [rcx+2Ch]
0x140042a81  test    al, 1
0x140042a83  jz      short loc_140042AA3
0x140042a85  cmp     byte ptr [rcx+29h], 6
0x140042a89  jb      short loc_140042AA3
0x140042a8b  mov     rcx, [rcx+18h]
0x140042a8f  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140042a96  mov     edx, 33h ; '3'
0x140042a9b  mov     r9d, ebx
0x140042a9e  call    WPP_SF_d
0x140042aa3  mov     rbp, [rsp+38h+arg_8]
0x140042aa8  mov     eax, ebx
0x140042aaa  mov     rbx, [rsp+38h+arg_0]
0x140042aaf  add     rsp, 30h
0x140042ab3  pop     rdi
0x140042ab4  retn
```
