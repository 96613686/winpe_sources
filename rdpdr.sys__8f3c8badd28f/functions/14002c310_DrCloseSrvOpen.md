# DrCloseSrvOpen

- ea: `0x14002c310`
- end: `0x14002c3b2`
- name: `DrCloseSrvOpen`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140001050`
- `0x140001660`
- `0x14000324c`
- `0x140006560`
- `0x14002c310`

## pseudocode

```c
__int64 __fastcall DrCloseSrvOpen(__int64 a1)
{
  RefCount *v2; // rbx
  unsigned int v3; // edi
  RefCount *v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids);
  if ( (unsigned int)GetDeviceFromRxContext(a1, &v5) )
  {
    v2 = v5;
    v3 = (*(__int64 (__fastcall **)(RefCount *, __int64))(*(_QWORD *)v5 + 136LL))(v5, a1);
    if ( v2 )
      RefCount::Release(v2);
    return v3;
  }
  else
  {
    if ( v5 )
      RefCount::Release(v5);
    return 3221225473LL;
  }
}

```

## disassembly

```asm
0x14002c310  mov     [rsp+arg_0], rbx
0x14002c315  push    rdi
0x14002c316  sub     rsp, 20h
0x14002c31a  mov     rdi, rcx
0x14002c31d  mov     [rsp+28h+arg_8], 0
0x14002c326  mov     rcx, cs:WPP_GLOBAL_Control
0x14002c32d  lea     rax, WPP_GLOBAL_Control
0x14002c334  cmp     rcx, rax
0x14002c337  jz      short loc_14002C354
0x14002c339  cmp     byte ptr [rcx+29h], 4
0x14002c33d  jb      short loc_14002C354
0x14002c33f  mov     rcx, [rcx+18h]
0x14002c343  lea     r8, WPP_23e3aaf8fb103772c4980a81685a436e_Traceguids
0x14002c34a  mov     edx, 32h ; '2'
0x14002c34f  call    WPP_SF_
0x14002c354  lea     rdx, [rsp+28h+arg_8]
0x14002c359  mov     rcx, rdi
0x14002c35c  call    ?GetDeviceFromRxContext@@YAHPEAU_RX_CONTEXT@@AEAV?$SmartPtr@VDrDevice@@@@@Z; GetDeviceFromRxContext(_RX_CONTEXT *,SmartPtr<DrDevice> &)
0x14002c361  test    eax, eax
0x14002c363  jz      short loc_14002C392
0x14002c365  mov     rbx, [rsp+28h+arg_8]
0x14002c36a  mov     rdx, rdi
0x14002c36d  mov     rcx, rbx
0x14002c370  mov     rax, [rbx]
0x14002c373  mov     rax, [rax+88h]
0x14002c37a  call    _guard_dispatch_icall
0x14002c37f  mov     edi, eax
0x14002c381  test    rbx, rbx
0x14002c384  jz      short loc_14002C38E
0x14002c386  mov     rcx, rbx; this
0x14002c389  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14002c38e  mov     eax, edi
0x14002c390  jmp     short loc_14002C3A6
0x14002c392  mov     rcx, [rsp+28h+arg_8]; this
0x14002c397  test    rcx, rcx
0x14002c39a  jz      short loc_14002C3A1
0x14002c39c  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14002c3a1  mov     eax, 0C0000001h
0x14002c3a6  mov     rbx, [rsp+28h+arg_0]
0x14002c3ab  add     rsp, 20h
0x14002c3af  pop     rdi
0x14002c3b0  retn
```
