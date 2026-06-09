# DepFSDecrementActiveMountCountForVolume

- ea: `0x18000baa0`
- end: `0x18000bb3f`
- name: `DepFSDecrementActiveMountCountForVolume`
- size: `159`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001430`
- `0x18000baa0`
- `0x18000bb48`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x18000bb22`
- `ntoskrnl!KeSetEvent` at `0x18000bb22`
- `ntoskrnl!ObfDereferenceObject` at `0x18000bad1`
- `ntoskrnl!ObfDereferenceObject` at `0x18000bad1`
- `FLTMGR!FltFreeGenericWorkItem` at `0x18000bac2`
- `FLTMGR!FltFreeGenericWorkItem` at `0x18000bac2`

## pseudocode

```c
void __fastcall DepFSDecrementActiveMountCountForVolume(
        PFLT_GENERIC_WORKITEM FltWorkItem,
        PVOID FltObject,
        PVOID Context)
{
  int v5; // edi

  v5 = DepFSForEachDependency(Context);
  FltFreeGenericWorkItem(FltWorkItem);
  ObfDereferenceObject(Context);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_bc64936b77293105c4440102cf4189d6_Traceguids);
    }
    KeSetEvent(&Event, 0, 0);
  }
}

```

## disassembly

```asm
0x18000baa0  mov     [rsp+arg_0], rbx
0x18000baa5  mov     [rsp+arg_8], rsi
0x18000baaa  push    rdi
0x18000baab  sub     rsp, 20h
0x18000baaf  mov     rbx, rcx
0x18000bab2  mov     rsi, r8
0x18000bab5  mov     rcx, r8
0x18000bab8  call    DepFSForEachDependency
0x18000babd  mov     rcx, rbx; FltWorkItem
0x18000bac0  mov     edi, eax
0x18000bac2  call    cs:__imp_FltFreeGenericWorkItem
0x18000bac9  nop     dword ptr [rax+rax+00h]
0x18000bace  mov     rcx, rsi; Object
0x18000bad1  call    cs:__imp_ObfDereferenceObject
0x18000bad8  nop     dword ptr [rax+rax+00h]
0x18000badd  test    edi, edi
0x18000badf  jns     short loc_18000BB2E
0x18000bae1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bae8  lea     rax, WPP_GLOBAL_Control
0x18000baef  cmp     rcx, rax
0x18000baf2  jz      short loc_18000BB16
0x18000baf4  mov     eax, [rcx+2Ch]
0x18000baf7  test    al, 1
0x18000baf9  jz      short loc_18000BB16
0x18000bafb  cmp     byte ptr [rcx+29h], 2
0x18000baff  jb      short loc_18000BB16
0x18000bb01  mov     rcx, [rcx+18h]
0x18000bb05  lea     r8, WPP_bc64936b77293105c4440102cf4189d6_Traceguids
0x18000bb0c  mov     edx, 29h ; ')'
0x18000bb11  call    WPP_SF_
0x18000bb16  xor     r8d, r8d; Wait
0x18000bb19  lea     rcx, Event; Event
0x18000bb20  xor     edx, edx; Increment
0x18000bb22  call    cs:__imp_KeSetEvent
0x18000bb29  nop     dword ptr [rax+rax+00h]
0x18000bb2e  mov     rbx, [rsp+28h+arg_0]
0x18000bb33  mov     rsi, [rsp+28h+arg_8]
0x18000bb38  add     rsp, 20h
0x18000bb3c  pop     rdi
0x18000bb3d  retn
```
