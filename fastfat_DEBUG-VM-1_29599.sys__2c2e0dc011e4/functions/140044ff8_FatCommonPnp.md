# FatCommonPnp

- ea: `0x140044ff8`
- end: `0x140045126`
- name: `FatCommonPnp`
- size: `302`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400438e0`
- `0x140045130`

## callees

- `0x140038eb4`
- `0x140044ff8`
- `0x1400451fc`
- `0x1400452a0`
- `0x1400454a0`
- `0x1400455f4`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140045093`
- `ntoskrnl!IofCallDriver` at `0x140045093`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004501f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004501f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045072`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400450fb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045072`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400450fb`

## pseudocode

```c
__int64 __fastcall FatCommonPnp(_DWORD *Entry, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  PDEVICE_OBJECT DeviceObject; // rsi
  __int64 p_Queue; // rsi
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v11; // r9

  Entry[17] |= 2u;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  DeviceObject = CurrentStackLocation->DeviceObject;
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  if ( DeviceObject->Size == 1776 )
  {
    p_Queue = (__int64)&DeviceObject[1].Queue;
    if ( *(_WORD *)p_Queue == 1281 )
    {
      switch ( CurrentStackLocation->MinorFunction )
      {
        case 1u:
          return (unsigned int)FatPnpQueryRemove(Entry, Irp, p_Queue);
        case 2u:
          return (unsigned int)FatPnpRemove(Entry, Irp);
        case 3u:
          return (unsigned int)FatPnpCancelRemove(Entry, Irp);
        case 0x17u:
          return (unsigned int)FatPnpSurpriseRemove(Entry, Irp);
        default:
          ExReleaseResourceLite(&Resource);
          ++Irp->CurrentLocation;
          ++Irp->Tail.Overlay.CurrentStackLocation;
          v7 = IofCallDriver(*(PDEVICE_OBJECT *)(p_Queue + 136), Irp);
          FatCompleteRequest_Real(Entry, 0, 0, v8);
          return v7;
      }
    }
  }
  ExReleaseResourceLite(&Resource);
  FatCompleteRequest_Real(Entry, Irp, 3221225485LL, v11);
  return 3221225485LL;
}

```

## disassembly

```asm
0x140044ff8  push    rbx
0x140044ffa  push    rbp
0x140044ffb  push    rsi
0x140044ffc  push    rdi
0x140044ffd  sub     rsp, 28h
0x140045001  or      dword ptr [rcx+44h], 2
0x140045005  mov     rbx, rdx
0x140045008  mov     rbp, [rdx+0B8h]
0x14004500f  mov     rdi, rcx
0x140045012  mov     dl, 1; Wait
0x140045014  lea     rcx, Resource; Resource
0x14004501b  mov     rsi, [rbp+28h]
0x14004501f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140045026  nop     dword ptr [rax+rax+00h]
0x14004502b  mov     eax, 6F0h
0x140045030  cmp     [rsi+2], ax
0x140045034  jnz     loc_1400450F4
0x14004503a  add     rsi, 1A0h
0x140045041  mov     eax, 501h
0x140045046  cmp     [rsi], ax
0x140045049  jnz     loc_1400450F4
0x14004504f  movzx   edx, byte ptr [rbp+1]
0x140045053  sub     edx, 1
0x140045056  jz      loc_1400450E0
0x14004505c  sub     edx, 1
0x14004505f  jz      short loc_1400450D0
0x140045061  sub     edx, 1
0x140045064  jz      short loc_1400450C0
0x140045066  cmp     edx, 14h
0x140045069  jz      short loc_1400450B0
0x14004506b  lea     rcx, Resource; Resource
0x140045072  call    cs:__imp_ExReleaseResourceLite
0x140045079  nop     dword ptr [rax+rax+00h]
0x14004507e  inc     byte ptr [rbx+43h]
0x140045081  mov     rdx, rbx; Irp
0x140045084  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14004508c  mov     rcx, [rsi+88h]; DeviceObject
0x140045093  call    cs:__imp_IofCallDriver
0x14004509a  nop     dword ptr [rax+rax+00h]
0x14004509f  xor     r8d, r8d
0x1400450a2  xor     edx, edx; Irp
0x1400450a4  mov     rcx, rdi; Entry
0x1400450a7  mov     ebx, eax
0x1400450a9  call    FatCompleteRequest_Real
0x1400450ae  jmp     short loc_1400450F0
0x1400450b0  mov     r8, rsi
0x1400450b3  mov     rdx, rbx; Irp
0x1400450b6  mov     rcx, rdi; Entry
0x1400450b9  call    FatPnpSurpriseRemove
0x1400450be  jmp     short loc_1400450EE
0x1400450c0  mov     r8, rsi
0x1400450c3  mov     rdx, rbx; Irp
0x1400450c6  mov     rcx, rdi; Entry
0x1400450c9  call    FatPnpCancelRemove
0x1400450ce  jmp     short loc_1400450EE
0x1400450d0  mov     r8, rsi
0x1400450d3  mov     rdx, rbx; Irp
0x1400450d6  mov     rcx, rdi; Entry
0x1400450d9  call    FatPnpRemove
0x1400450de  jmp     short loc_1400450EE
0x1400450e0  mov     r8, rsi
0x1400450e3  mov     rdx, rbx; Irp
0x1400450e6  mov     rcx, rdi; Entry
0x1400450e9  call    FatPnpQueryRemove
0x1400450ee  mov     ebx, eax
0x1400450f0  mov     eax, ebx
0x1400450f2  jmp     short loc_14004511C
0x1400450f4  lea     rcx, Resource; Resource
0x1400450fb  call    cs:__imp_ExReleaseResourceLite
0x140045102  nop     dword ptr [rax+rax+00h]
0x140045107  mov     esi, 0C000000Dh
0x14004510c  mov     rdx, rbx; Irp
0x14004510f  mov     r8d, esi
0x140045112  mov     rcx, rdi; Entry
0x140045115  call    FatCompleteRequest_Real
0x14004511a  mov     eax, esi
0x14004511c  add     rsp, 28h
0x140045120  pop     rdi
0x140045121  pop     rsi
0x140045122  pop     rbp
0x140045123  pop     rbx
0x140045124  retn
```
