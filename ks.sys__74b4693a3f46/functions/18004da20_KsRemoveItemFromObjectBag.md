# KsRemoveItemFromObjectBag

- ea: `0x18004da20`
- end: `0x18004db25`
- name: `KsRemoveItemFromObjectBag`
- size: `261`
- prototype: `ULONG __stdcall(KSOBJECT_BAG ObjectBag, PVOID Item, BOOLEAN Free)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180004348`
- `0x180013ea0`
- `0x18004e370`
- `0x180071ad0`

## callees

- `0x18000b7bc`
- `0x18000da50`
- `0x18004da20`
- `0x18004ed54`
- `0x1800573f0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18004da83`
- `ntoskrnl!KeReleaseMutex` at `0x18004da83`
- `ntoskrnl!KeWaitForSingleObject` at `0x18004da5d`
- `ntoskrnl!KeWaitForSingleObject` at `0x18004da5d`

## pseudocode

```c
ULONG __stdcall KsRemoveItemFromObjectBag(KSOBJECT_BAG ObjectBag, PVOID Item, BOOLEAN Free)
{
  PVOID v4; // rsi
  ULONG v6; // edi
  __int64 ObjectBagEntry; // rax
  __int64 v8; // r8

  v4 = Item;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(Item) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)Item,
        1,
        66,
        (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(Item) = 5;
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)Item,
        Free,
        67,
        (__int64)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids,
        (char)ObjectBag,
        (char)v4);
    }
  }
  v6 = 0;
  KeWaitForSingleObject(*((PVOID *)ObjectBag + 3), Executive, 0, 0, 0);
  ObjectBagEntry = KspFindObjectBagEntry(ObjectBag, v4);
  if ( ObjectBagEntry )
  {
    LOBYTE(v8) = Free;
    v6 = KspRemoveObjectBagEntry(ObjectBag, ObjectBagEntry, v8);
  }
  KeReleaseMutex(*((PRKMUTEX *)ObjectBag + 3), 0);
  return v6;
}

```

## disassembly

```asm
0x18004da20  push    rbx
0x18004da22  push    rbp
0x18004da23  push    rsi
0x18004da24  push    rdi
0x18004da25  push    r14
0x18004da27  push    r15
0x18004da29  sub     rsp, 48h
0x18004da2d  mov     bpl, r8b
0x18004da30  mov     rsi, rdx
0x18004da33  mov     rbx, rcx
0x18004da36  lea     rdi, WPP_RECORDER_INITIALIZED
0x18004da3d  xor     r14d, r14d
0x18004da40  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18004da47  jnz     short loc_18004DA9F
0x18004da49  mov     rcx, [rbx+18h]; Object
0x18004da4d  xor     r9d, r9d; Alertable
0x18004da50  xor     r8d, r8d; WaitMode
0x18004da53  mov     [rsp+78h+Timeout], r14; Timeout
0x18004da58  xor     edx, edx; WaitReason
0x18004da5a  mov     edi, r14d
0x18004da5d  call    cs:__imp_KeWaitForSingleObject
0x18004da64  nop     dword ptr [rax+rax+00h]
0x18004da69  mov     rdx, rsi
0x18004da6c  mov     rcx, rbx
0x18004da6f  call    KspFindObjectBagEntry
0x18004da74  test    rax, rax
0x18004da77  jnz     loc_18004DB10
0x18004da7d  mov     rcx, [rbx+18h]; Mutex
0x18004da81  xor     edx, edx; Wait
0x18004da83  call    cs:__imp_KeReleaseMutex
0x18004da8a  nop     dword ptr [rax+rax+00h]
0x18004da8f  mov     eax, edi
0x18004da91  add     rsp, 48h
0x18004da95  pop     r15
0x18004da97  pop     r14
0x18004da99  pop     rdi
0x18004da9a  pop     rsi
0x18004da9b  pop     rbp
0x18004da9c  pop     rbx
0x18004da9d  retn
0x18004da9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004daa6  lea     r15, WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids
0x18004daad  cmp     [rcx+48h], r14w
0x18004dab2  jnz     short loc_18004DAF4
0x18004dab4  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18004dabb  jz      short loc_18004DA49
0x18004dabd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dac4  cmp     [rcx+48h], r14w
0x18004dac9  jz      loc_18004DA49
0x18004dacf  mov     rcx, [rcx+40h]
0x18004dad3  mov     r9d, 43h ; 'C'
0x18004dad9  mov     [rsp+78h+var_48], rsi
0x18004dade  mov     dl, 5
0x18004dae0  mov     [rsp+78h+var_50], rbx
0x18004dae5  mov     [rsp+78h+Timeout], r15
0x18004daea  call    WPP_RECORDER_SF_qq
0x18004daef  jmp     loc_18004DA49
0x18004daf4  mov     rcx, [rcx+40h]
0x18004daf8  mov     r9d, 42h ; 'B'
0x18004dafe  mov     dl, 5
0x18004db00  mov     [rsp+78h+Timeout], r15
0x18004db05  lea     r8d, [r9-41h]
0x18004db09  call    WPP_RECORDER_SF_
0x18004db0e  jmp     short loc_18004DAB4
0x18004db10  mov     r8b, bpl
0x18004db13  mov     rdx, rax
0x18004db16  mov     rcx, rbx
0x18004db19  call    KspRemoveObjectBagEntry
0x18004db1e  mov     edi, eax
0x18004db20  jmp     loc_18004DA7D
```
