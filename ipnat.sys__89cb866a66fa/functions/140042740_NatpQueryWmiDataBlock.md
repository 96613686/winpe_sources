# NatpQueryWmiDataBlock

- ea: `0x140042740`
- end: `0x140042836`
- name: `NatpQueryWmiDataBlock`
- size: `246`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400021bc`
- `0x1400052a0`
- `0x140042740`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x1400427ae`
- `WMILIB!WmiCompleteRequest` at `0x1400427ae`

## pseudocode

```c
__int64 __fastcall NatpQueryWmiDataBlock(PDEVICE_OBJECT DeviceObject, PIRP Irp, unsigned int a3, int a4, int a5)
{
  unsigned int v7; // eax
  unsigned int v8; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_DDD(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, a3, a4, a5);
  }
  v7 = WmiCompleteRequest(DeviceObject, Irp, -1073741163, 0, 0);
  v8 = v7;
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v8;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, v7);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140042740  mov     [rsp+arg_0], rbx
0x140042745  mov     [rsp+arg_8], rbp
0x14004274a  push    rdi
0x14004274b  sub     rsp, 30h
0x14004274f  mov     rbx, rdx
0x140042752  mov     rdi, rcx
0x140042755  mov     rcx, cs:WPP_GLOBAL_Control
0x14004275c  lea     rbp, WPP_GLOBAL_Control
0x140042763  cmp     rcx, rbp
0x140042766  jz      short loc_14004279A
0x140042768  mov     eax, [rcx+2Ch]
0x14004276b  test    al, 1
0x14004276d  jz      short loc_14004279A
0x14004276f  cmp     byte ptr [rcx+29h], 6
0x140042773  jb      short loc_14004279A
0x140042775  mov     eax, [rsp+38h+arg_20]
0x140042779  mov     edx, 2Ah ; '*'
0x14004277e  mov     rcx, [rcx+18h]
0x140042782  mov     [rsp+38h+var_10], eax
0x140042786  mov     dword ptr [rsp+38h+PriorityBoost], r9d
0x14004278b  mov     r9d, r8d
0x14004278e  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140042795  call    WPP_SF_DDD
0x14004279a  xor     r9d, r9d; BufferUsed
0x14004279d  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x1400427a2  mov     r8d, 0C0000295h; Status
0x1400427a8  mov     rdx, rbx; Irp
0x1400427ab  mov     rcx, rdi; DeviceObject
0x1400427ae  call    cs:__imp_WmiCompleteRequest
0x1400427b5  nop     dword ptr [rax+rax+00h]
0x1400427ba  mov     ebx, eax
0x1400427bc  test    eax, eax
0x1400427be  jz      short loc_1400427F2
0x1400427c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400427c7  cmp     rcx, rbp
0x1400427ca  jz      short loc_140042823
0x1400427cc  mov     edx, [rcx+2Ch]
0x1400427cf  test    dl, 1
0x1400427d2  jz      short loc_1400427F2
0x1400427d4  cmp     byte ptr [rcx+29h], 2
0x1400427d8  jb      short loc_1400427F2
0x1400427da  mov     rcx, [rcx+18h]
0x1400427de  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x1400427e5  mov     edx, 2Bh ; '+'
0x1400427ea  mov     r9d, eax
0x1400427ed  call    WPP_SF_d
0x1400427f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400427f9  cmp     rcx, rbp
0x1400427fc  jz      short loc_140042823
0x1400427fe  mov     eax, [rcx+2Ch]
0x140042801  test    al, 1
0x140042803  jz      short loc_140042823
0x140042805  cmp     byte ptr [rcx+29h], 6
0x140042809  jb      short loc_140042823
0x14004280b  mov     rcx, [rcx+18h]
0x14004280f  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140042816  mov     edx, 2Ch ; ','
0x14004281b  mov     r9d, ebx
0x14004281e  call    WPP_SF_d
0x140042823  mov     rbp, [rsp+38h+arg_8]
0x140042828  mov     eax, ebx
0x14004282a  mov     rbx, [rsp+38h+arg_0]
0x14004282f  add     rsp, 30h
0x140042833  pop     rdi
0x140042834  retn
```
