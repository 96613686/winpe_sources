# NatpExecuteWmiMethod

- ea: `0x140042670`
- end: `0x140042731`
- name: `NatpExecuteWmiMethod`
- size: `193`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, PIRP Irp@<rdx>, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400021bc`
- `0x1400052a0`
- `0x140042670`

## import_xrefs

- `WMILIB!WmiCompleteRequest` at `0x1400426de`
- `WMILIB!WmiCompleteRequest` at `0x1400426de`

## pseudocode

```c
__int64 __fastcall NatpExecuteWmiMethod(PDEVICE_OBJECT DeviceObject, PIRP Irp, unsigned int a3, int a4, int a5)
{
  unsigned int v7; // eax
  unsigned int v8; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_DDD(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, a3, a4, a5);
  }
  v7 = WmiCompleteRequest(DeviceObject, Irp, -1073741163, 0, 0);
  v8 = v7;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids, v7);
  }
  return v8;
}

```

## disassembly

```asm
0x140042670  mov     [rsp+arg_0], rbx
0x140042675  mov     [rsp+arg_8], rsi
0x14004267a  push    rdi
0x14004267b  sub     rsp, 30h
0x14004267f  mov     rbx, rdx
0x140042682  mov     rdi, rcx
0x140042685  mov     rcx, cs:WPP_GLOBAL_Control
0x14004268c  lea     rsi, WPP_GLOBAL_Control
0x140042693  cmp     rcx, rsi
0x140042696  jz      short loc_1400426CA
0x140042698  mov     eax, [rcx+2Ch]
0x14004269b  test    al, 1
0x14004269d  jz      short loc_1400426CA
0x14004269f  cmp     byte ptr [rcx+29h], 6
0x1400426a3  jb      short loc_1400426CA
0x1400426a5  mov     eax, [rsp+38h+arg_20]
0x1400426a9  mov     edx, 28h ; '('
0x1400426ae  mov     rcx, [rcx+18h]
0x1400426b2  mov     [rsp+38h+var_10], eax
0x1400426b6  mov     dword ptr [rsp+38h+PriorityBoost], r9d
0x1400426bb  mov     r9d, r8d
0x1400426be  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x1400426c5  call    WPP_SF_DDD
0x1400426ca  xor     r9d, r9d; BufferUsed
0x1400426cd  mov     [rsp+38h+PriorityBoost], 0; PriorityBoost
0x1400426d2  mov     r8d, 0C0000295h; Status
0x1400426d8  mov     rdx, rbx; Irp
0x1400426db  mov     rcx, rdi; DeviceObject
0x1400426de  call    cs:__imp_WmiCompleteRequest
0x1400426e5  nop     dword ptr [rax+rax+00h]
0x1400426ea  mov     ebx, eax
0x1400426ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400426f3  cmp     rcx, rsi
0x1400426f6  jz      short loc_14004271E
0x1400426f8  mov     edx, [rcx+2Ch]
0x1400426fb  test    dl, 1
0x1400426fe  jz      short loc_14004271E
0x140042700  cmp     byte ptr [rcx+29h], 6
0x140042704  jb      short loc_14004271E
0x140042706  mov     rcx, [rcx+18h]
0x14004270a  lea     r8, WPP_d34def7825f63283a7d86b09b44e42bc_Traceguids
0x140042711  mov     edx, 29h ; ')'
0x140042716  mov     r9d, eax
0x140042719  call    WPP_SF_d
0x14004271e  mov     rsi, [rsp+38h+arg_8]
0x140042723  mov     eax, ebx
0x140042725  mov     rbx, [rsp+38h+arg_0]
0x14004272a  add     rsp, 30h
0x14004272e  pop     rdi
0x14004272f  retn
```
