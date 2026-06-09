# ReconcileThisDatabaseWithMaster

- ea: `0x140019140`
- end: `0x140019264`
- name: `ReconcileThisDatabaseWithMaster`
- size: `292`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x14000be4c`
- `0x14000c730`
- `0x14000d494`
- `0x14000db54`
- `0x140014fc0`
- `0x140019f70`

## callees

- `0x140001350`
- `0x140001b30`
- `0x14000f680`
- `0x140019140`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140019188`
- `ntoskrnl!IoAllocateWorkItem` at `0x140019188`
- `ntoskrnl!ExAllocatePool2` at `0x140019171`
- `ntoskrnl!ExAllocatePool2` at `0x140019171`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019208`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019208`

## pseudocode

```c
void __fastcall ReconcileThisDatabaseWithMaster(PDEVICE_OBJECT *Context, __int64 a2)
{
  _QWORD *Pool2; // rbx
  PIO_WORKITEM WorkItem; // rax

  if ( !*(_WORD *)(a2 + 124) )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(66, 56, 1098149453);
    if ( Pool2 )
    {
      WorkItem = IoAllocateWorkItem(*Context);
      Pool2[2] = WorkItem;
      if ( WorkItem )
      {
        Pool2[5] = Context;
        Pool2[3] = ReconcileThisDatabaseWithMasterWorker;
        Pool2[6] = a2;
        QueueWorkItem(Context);
        if ( !*((_DWORD *)Context + 70) && *((_BYTE *)Context + 144) == 1 && !*((_BYTE *)Context + 192) )
          OnlineMountedVolumes((__int64)Context, a2);
      }
      else
      {
        ExFreePoolWithTag(Pool2, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xA4u);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xA3u);
    }
  }
}

```

## disassembly

```asm
0x140019140  mov     [rsp+arg_8], rsi
0x140019145  push    rdi
0x140019146  sub     rsp, 20h
0x14001914a  cmp     byte ptr [rdx+7Ch], 0
0x14001914e  mov     rdi, rdx
0x140019151  mov     rsi, rcx
0x140019154  jnz     short loc_1400191CD
0x140019156  cmp     byte ptr [rdx+7Dh], 0
0x14001915a  jnz     short loc_1400191CD
0x14001915c  mov     edx, 38h ; '8'
0x140019161  mov     [rsp+28h+arg_0], rbx
0x140019166  mov     ecx, 42h ; 'B'
0x14001916b  mov     r8d, 41746E4Dh
0x140019171  call    cs:__imp_ExAllocatePool2
0x140019178  nop     dword ptr [rax+rax+00h]
0x14001917d  mov     rbx, rax
0x140019180  test    rax, rax
0x140019183  jz      short loc_1400191D9
0x140019185  mov     rcx, [rsi]; DeviceObject
0x140019188  call    cs:__imp_IoAllocateWorkItem
0x14001918f  nop     dword ptr [rax+rax+00h]
0x140019194  mov     [rbx+10h], rax
0x140019198  test    rax, rax
0x14001919b  jz      short loc_140019203
0x14001919d  lea     rax, ReconcileThisDatabaseWithMasterWorker
0x1400191a4  mov     [rbx+28h], rsi
0x1400191a8  lea     r8, [rbx+28h]
0x1400191ac  mov     [rbx+18h], rax
0x1400191b0  mov     rdx, rbx
0x1400191b3  mov     [rbx+30h], rdi
0x1400191b7  mov     rcx, rsi; Context
0x1400191ba  call    QueueWorkItem
0x1400191bf  cmp     dword ptr [rsi+118h], 0
0x1400191c6  jz      short loc_14001923E
0x1400191c8  mov     rbx, [rsp+28h+arg_0]
0x1400191cd  mov     rsi, [rsp+28h+arg_8]
0x1400191d2  add     rsp, 20h
0x1400191d6  pop     rdi
0x1400191d7  retn
0x1400191d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400191e0  lea     rax, WPP_GLOBAL_Control
0x1400191e7  cmp     rcx, rax
0x1400191ea  jz      short loc_1400191C8
0x1400191ec  mov     eax, [rcx+2Ch]
0x1400191ef  test    al, 4
0x1400191f1  jz      short loc_1400191C8
0x1400191f3  mov     rcx, [rcx+18h]
0x1400191f7  mov     edx, 0A3h
0x1400191fc  call    WPP_SF_
0x140019201  jmp     short loc_1400191C8
0x140019203  xor     edx, edx; Tag
0x140019205  mov     rcx, rbx; P
0x140019208  call    cs:__imp_ExFreePoolWithTag
0x14001920f  nop     dword ptr [rax+rax+00h]
0x140019214  mov     rcx, cs:WPP_GLOBAL_Control
0x14001921b  lea     rax, WPP_GLOBAL_Control
0x140019222  cmp     rcx, rax
0x140019225  jz      short loc_1400191C8
0x140019227  mov     eax, [rcx+2Ch]
0x14001922a  test    al, 4
0x14001922c  jz      short loc_1400191C8
0x14001922e  mov     rcx, [rcx+18h]
0x140019232  mov     edx, 0A4h
0x140019237  call    WPP_SF_
0x14001923c  jmp     short loc_1400191C8
0x14001923e  cmp     byte ptr [rsi+90h], 1
0x140019245  jnz     short loc_1400191C8
0x140019247  cmp     byte ptr [rsi+0C0h], 0
0x14001924e  jnz     loc_1400191C8
0x140019254  mov     rdx, rdi
0x140019257  mov     rcx, rsi
0x14001925a  call    OnlineMountedVolumes
0x14001925f  jmp     loc_1400191C8
```
