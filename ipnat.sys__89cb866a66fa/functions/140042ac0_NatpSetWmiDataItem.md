# NatpSetWmiDataItem

- ea: `0x140042ac0`
- end: `0x140042bbe`
- name: `NatpSetWmiDataItem`
- size: `254`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400021bc`
- `0x140010ce4`
- `0x140042ac0`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x140042b36`
- `WMILIB!WmiCompleteRequest` at `0x140042b36`

## pseudocode

```c
__int64 __fastcall NatpSetWmiDataItem(PDEVICE_OBJECT DeviceObject, PIRP Irp, unsigned int a3, int a4, int a5, int a6)
{
  unsigned int v8; // eax
  unsigned int v9; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_dddd(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, a3, a4, a5, a6);
  }
  v8 = WmiCompleteRequest(DeviceObject, Irp, -1073741163, 0, 0);
  v9 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v9;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, v8);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x140042ac0  mov     [rsp+arg_0], rbx
0x140042ac5  mov     [rsp+arg_8], rbp
0x140042aca  push    rdi
0x140042acb  sub     rsp, 40h
0x140042acf  mov     rbx, rdx
0x140042ad2  mov     rdi, rcx
0x140042ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x140042adc  lea     rbp, WPP_GLOBAL_Control
0x140042ae3  cmp     rcx, rbp
0x140042ae6  jz      short loc_140042B22
0x140042ae8  mov     eax, [rcx+2Ch]
0x140042aeb  test    al, 1
0x140042aed  jz      short loc_140042B22
0x140042aef  cmp     byte ptr [rcx+29h], 6
0x140042af3  jb      short loc_140042B22
0x140042af5  mov     eax, [rsp+48h+arg_28]
0x140042af9  mov     edx, 34h ; '4'
0x140042afe  mov     rcx, [rcx+18h]
0x140042b02  mov     [rsp+48h+var_18], eax
0x140042b06  mov     eax, [rsp+48h+arg_20]
0x140042b0a  mov     [rsp+48h+var_20], eax
0x140042b0e  mov     dword ptr [rsp+48h+PriorityBoost], r9d
0x140042b13  mov     r9d, r8d
0x140042b16  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140042b1d  call    WPP_SF_dddd
0x140042b22  xor     r9d, r9d; BufferUsed
0x140042b25  mov     [rsp+48h+PriorityBoost], 0; PriorityBoost
0x140042b2a  mov     r8d, 0C0000295h; Status
0x140042b30  mov     rdx, rbx; Irp
0x140042b33  mov     rcx, rdi; DeviceObject
0x140042b36  call    cs:__imp_WmiCompleteRequest
0x140042b3d  nop     dword ptr [rax+rax+00h]
0x140042b42  mov     ebx, eax
0x140042b44  test    eax, eax
0x140042b46  jz      short loc_140042B7A
0x140042b48  mov     rcx, cs:WPP_GLOBAL_Control
0x140042b4f  cmp     rcx, rbp
0x140042b52  jz      short loc_140042BAB
0x140042b54  mov     edx, [rcx+2Ch]
0x140042b57  test    dl, 1
0x140042b5a  jz      short loc_140042B7A
0x140042b5c  cmp     byte ptr [rcx+29h], 2
0x140042b60  jb      short loc_140042B7A
0x140042b62  mov     rcx, [rcx+18h]
0x140042b66  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140042b6d  mov     edx, 35h ; '5'
0x140042b72  mov     r9d, eax
0x140042b75  call    WPP_SF_d
0x140042b7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140042b81  cmp     rcx, rbp
0x140042b84  jz      short loc_140042BAB
0x140042b86  mov     eax, [rcx+2Ch]
0x140042b89  test    al, 1
0x140042b8b  jz      short loc_140042BAB
0x140042b8d  cmp     byte ptr [rcx+29h], 6
0x140042b91  jb      short loc_140042BAB
0x140042b93  mov     rcx, [rcx+18h]
0x140042b97  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140042b9e  mov     edx, 36h ; '6'
0x140042ba3  mov     r9d, ebx
0x140042ba6  call    WPP_SF_d
0x140042bab  mov     rbp, [rsp+48h+arg_8]
0x140042bb0  mov     eax, ebx
0x140042bb2  mov     rbx, [rsp+48h+arg_0]
0x140042bb7  add     rsp, 40h
0x140042bbb  pop     rdi
0x140042bbc  retn
```
