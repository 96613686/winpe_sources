# DeleteDirCache

- ea: `0x14001837c`
- end: `0x1400184b0`
- name: `DeleteDirCache`
- size: `308`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x1400029d0`
- `0x140004530`
- `0x140005c90`
- `0x140008e10`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140010904`
- `0x1400124ec`
- `0x1400184b8`
- `0x140018804`
- `0x14001fad0`
- `0x1400209b0`
- `0x14002a9e0`
- `0x140034680`

## callees

- `0x1400159cc`
- `0x14001837c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140018439`
- `ntoskrnl!KeWaitForSingleObject` at `0x140018439`
- `ntoskrnl!KeReleaseMutex` at `0x140018457`
- `ntoskrnl!KeReleaseMutex` at `0x140018457`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018411`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018469`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018411`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018469`

## pseudocode

```c
void __fastcall DeleteDirCache(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  _QWORD **v5; // rax
  _QWORD *v6; // rbx
  void *v7; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids);
  if ( a2 )
  {
    v4 = *(_QWORD *)(a2 + 32);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids);
      }
      v5 = *(_QWORD ***)(v4 + 8);
      v6 = *v5;
      *v5 = 0;
      while ( v6 )
      {
        v7 = v6;
        v6 = (_QWORD *)*v6;
        ExFreePoolWithTag(v7, 0);
      }
      KeWaitForSingleObject((PVOID)(a1 + 2152), Executive, 0, 0, 0);
      *(_DWORD *)(a1 + 2340) += *(_DWORD *)(*(_QWORD *)(a2 + 32) + 16LL);
      KeReleaseMutex((PRKMUTEX)(a1 + 2152), 0);
      ExFreePoolWithTag(*(PVOID *)(a2 + 32), 0);
      *(_QWORD *)(a2 + 32) = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids);
}

```

## disassembly

```asm
0x14001837c  push    rbx
0x14001837e  push    rsi
0x14001837f  push    rdi
0x140018380  push    r14
0x140018382  sub     rsp, 38h
0x140018386  mov     rdi, rdx
0x140018389  mov     rsi, rcx
0x14001838c  mov     rcx, cs:WPP_GLOBAL_Control
0x140018393  lea     r14, WPP_GLOBAL_Control
0x14001839a  cmp     rcx, r14
0x14001839d  jz      short loc_1400183BB
0x14001839f  mov     eax, [rcx+2Ch]
0x1400183a2  test    al, 40h
0x1400183a4  jz      short loc_1400183BB
0x1400183a6  mov     rcx, [rcx+18h]
0x1400183aa  lea     r8, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids
0x1400183b1  mov     edx, 0Ch
0x1400183b6  call    WPP_SF_
0x1400183bb  test    rdi, rdi
0x1400183be  jz      loc_14001847D
0x1400183c4  mov     rbx, [rdi+20h]
0x1400183c8  test    rbx, rbx
0x1400183cb  jz      loc_14001847D
0x1400183d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400183d8  cmp     rcx, r14
0x1400183db  jz      short loc_1400183FB
0x1400183dd  test    dword ptr [rcx+2Ch], 100h
0x1400183e4  jz      short loc_1400183FB
0x1400183e6  mov     rcx, [rcx+18h]
0x1400183ea  lea     r8, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids
0x1400183f1  mov     edx, 0Dh
0x1400183f6  call    WPP_SF_
0x1400183fb  mov     rax, [rbx+8]
0x1400183ff  mov     rbx, [rax]
0x140018402  mov     qword ptr [rax], 0
0x140018409  jmp     short loc_14001841D
0x14001840b  mov     rcx, rbx; P
0x14001840e  mov     rbx, [rbx]
0x140018411  call    cs:__imp_ExFreePoolWithTag
0x140018418  nop     dword ptr [rax+rax+00h]
0x14001841d  xor     edx, edx; WaitReason
0x14001841f  test    rbx, rbx
0x140018422  jnz     short loc_14001840B
0x140018424  lea     rbx, [rsi+868h]
0x14001842b  mov     [rsp+58h+Timeout], rdx; Timeout
0x140018430  mov     rcx, rbx; Object
0x140018433  xor     r9d, r9d; Alertable
0x140018436  xor     r8d, r8d; WaitMode
0x140018439  call    cs:__imp_KeWaitForSingleObject
0x140018440  nop     dword ptr [rax+rax+00h]
0x140018445  mov     rax, [rdi+20h]
0x140018449  mov     rcx, rbx; Mutex
0x14001844c  mov     edx, [rax+10h]
0x14001844f  add     [rsi+924h], edx
0x140018455  xor     edx, edx; Wait
0x140018457  call    cs:__imp_KeReleaseMutex
0x14001845e  nop     dword ptr [rax+rax+00h]
0x140018463  mov     rcx, [rdi+20h]; P
0x140018467  xor     edx, edx; Tag
0x140018469  call    cs:__imp_ExFreePoolWithTag
0x140018470  nop     dword ptr [rax+rax+00h]
0x140018475  mov     qword ptr [rdi+20h], 0
0x14001847d  mov     rcx, cs:WPP_GLOBAL_Control
0x140018484  cmp     rcx, r14
0x140018487  jz      short loc_1400184A5
0x140018489  mov     eax, [rcx+2Ch]
0x14001848c  test    al, 40h
0x14001848e  jz      short loc_1400184A5
0x140018490  mov     rcx, [rcx+18h]
0x140018494  lea     r8, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids
0x14001849b  mov     edx, 0Eh
0x1400184a0  call    WPP_SF_
0x1400184a5  add     rsp, 38h
0x1400184a9  pop     r14
0x1400184ab  pop     rdi
0x1400184ac  pop     rsi
0x1400184ad  pop     rbx
0x1400184ae  retn
```
