# KsRemoveItemFromObjectBag

- ea: `0x18004dbc0`
- end: `0x18004dcc5`
- name: `KsRemoveItemFromObjectBag`
- size: `261`
- prototype: `ULONG __stdcall(KSOBJECT_BAG ObjectBag, PVOID Item, BOOLEAN Free)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180004348`
- `0x180013ea0`
- `0x18004e510`
- `0x180071ad0`

## callees

- `0x18000b7bc`
- `0x18000da50`
- `0x18004dbc0`
- `0x18004eef4`
- `0x180057590`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x18004dc23`
- `ntoskrnl!KeReleaseMutex` at `0x18004dc23`
- `ntoskrnl!KeWaitForSingleObject` at `0x18004dbfd`
- `ntoskrnl!KeWaitForSingleObject` at `0x18004dbfd`

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
        (char)WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids,
        (char)ObjectBag);
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
0x18004dbc0  push    rbx
0x18004dbc2  push    rbp
0x18004dbc3  push    rsi
0x18004dbc4  push    rdi
0x18004dbc5  push    r14
0x18004dbc7  push    r15
0x18004dbc9  sub     rsp, 48h
0x18004dbcd  mov     bpl, r8b
0x18004dbd0  mov     rsi, rdx
0x18004dbd3  mov     rbx, rcx
0x18004dbd6  lea     rdi, WPP_RECORDER_INITIALIZED
0x18004dbdd  xor     r14d, r14d
0x18004dbe0  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18004dbe7  jnz     short loc_18004DC3F
0x18004dbe9  mov     rcx, [rbx+18h]; Object
0x18004dbed  xor     r9d, r9d; Alertable
0x18004dbf0  xor     r8d, r8d; WaitMode
0x18004dbf3  mov     [rsp+78h+Timeout], r14; Timeout
0x18004dbf8  xor     edx, edx; WaitReason
0x18004dbfa  mov     edi, r14d
0x18004dbfd  call    cs:__imp_KeWaitForSingleObject
0x18004dc04  nop     dword ptr [rax+rax+00h]
0x18004dc09  mov     rdx, rsi
0x18004dc0c  mov     rcx, rbx
0x18004dc0f  call    KspFindObjectBagEntry
0x18004dc14  test    rax, rax
0x18004dc17  jnz     loc_18004DCB0
0x18004dc1d  mov     rcx, [rbx+18h]; Mutex
0x18004dc21  xor     edx, edx; Wait
0x18004dc23  call    cs:__imp_KeReleaseMutex
0x18004dc2a  nop     dword ptr [rax+rax+00h]
0x18004dc2f  mov     eax, edi
0x18004dc31  add     rsp, 48h
0x18004dc35  pop     r15
0x18004dc37  pop     r14
0x18004dc39  pop     rdi
0x18004dc3a  pop     rsi
0x18004dc3b  pop     rbp
0x18004dc3c  pop     rbx
0x18004dc3d  retn
0x18004dc3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dc46  lea     r15, WPP_482f7f79f92e3c069ac85fa6c9d306ca_Traceguids
0x18004dc4d  cmp     [rcx+48h], r14w
0x18004dc52  jnz     short loc_18004DC94
0x18004dc54  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x18004dc5b  jz      short loc_18004DBE9
0x18004dc5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dc64  cmp     [rcx+48h], r14w
0x18004dc69  jz      loc_18004DBE9
0x18004dc6f  mov     rcx, [rcx+40h]
0x18004dc73  mov     r9d, 43h ; 'C'
0x18004dc79  mov     [rsp+78h+var_48], rsi
0x18004dc7e  mov     dl, 5
0x18004dc80  mov     [rsp+78h+var_50], rbx
0x18004dc85  mov     [rsp+78h+Timeout], r15
0x18004dc8a  call    WPP_RECORDER_SF_qq
0x18004dc8f  jmp     loc_18004DBE9
0x18004dc94  mov     rcx, [rcx+40h]
0x18004dc98  mov     r9d, 42h ; 'B'
0x18004dc9e  mov     dl, 5
0x18004dca0  mov     [rsp+78h+Timeout], r15
0x18004dca5  lea     r8d, [r9-41h]
0x18004dca9  call    WPP_RECORDER_SF_
0x18004dcae  jmp     short loc_18004DC54
0x18004dcb0  mov     r8b, bpl
0x18004dcb3  mov     rdx, rax
0x18004dcb6  mov     rcx, rbx
0x18004dcb9  call    KspRemoveObjectBagEntry
0x18004dcbe  mov     edi, eax
0x18004dcc0  jmp     loc_18004DC1D
```
