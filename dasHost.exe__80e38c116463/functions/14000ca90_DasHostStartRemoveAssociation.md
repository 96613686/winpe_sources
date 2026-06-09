# DasHostStartRemoveAssociation

- ea: `0x14000ca90`
- end: `0x14000cb49`
- name: `DasHostStartRemoveAssociation`
- size: `185`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x14000bacc`
- `0x14000ca90`
- `0x14001c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000cade`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000cade`

## pseudocode

```c
__int64 __fastcall DasHostStartRemoveAssociation(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v6; // rcx
  __int64 result; // rax
  int v8; // edx
  int v9; // r8d
  int v10; // [rsp+28h] [rbp-40h]

  v3 = *a2;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      a3,
      37,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids);
  EventActivityIdControl(2u, (LPGUID)v3);
  v6 = *(_QWORD *)(v3 + 48);
  *(_DWORD *)(v3 + 160) = 0;
  *(_QWORD *)(v3 + 96) = a1;
  *(_QWORD *)(v3 + 104) = a3;
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 88LL))(v6);
  if ( (int)result < 0 )
    result = OnRemoveCompleteStub(0, result, (RTL_SRWLOCK *)v3);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_sd(
             *((_QWORD *)WPP_GLOBAL_Control + 5),
             v8,
             v9,
             38,
             &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids,
             v10,
             result);
  return result;
}

```

## disassembly

```asm
0x14000ca90  push    rbx
0x14000ca92  push    rbp
0x14000ca93  push    rsi
0x14000ca94  push    rdi
0x14000ca95  push    r14
0x14000ca97  sub     rsp, 40h
0x14000ca9b  mov     rbx, [rdx]
0x14000ca9e  mov     rdi, r8
0x14000caa1  mov     rsi, rcx
0x14000caa4  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000caab  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000cab2  lea     r14, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000cab9  jz      short loc_14000CAD6
0x14000cabb  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cac2  mov     r9d, 25h ; '%'; int
0x14000cac8  mov     [rsp+68h+MessageGuid], r14; MessageGuid
0x14000cacd  mov     rcx, [rcx+28h]; int
0x14000cad1  call    WPP_RECORDER_SF_s
0x14000cad6  mov     rdx, rbx; ActivityId
0x14000cad9  mov     ecx, 2; ControlCode
0x14000cade  call    cs:__imp_EventActivityIdControl
0x14000cae4  mov     rcx, [rbx+30h]
0x14000cae8  mov     dword ptr [rbx+0A0h], 0
0x14000caf2  mov     [rbx+60h], rsi
0x14000caf6  mov     [rbx+68h], rdi
0x14000cafa  mov     rax, [rcx]
0x14000cafd  mov     rax, [rax+58h]
0x14000cb01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb06  test    eax, eax
0x14000cb08  jns     short loc_14000CB16
0x14000cb0a  mov     r8, rbx; void *
0x14000cb0d  mov     edx, eax; int
0x14000cb0f  xor     ecx, ecx; int
0x14000cb11  call    ?OnRemoveCompleteStub@@YAJHJPEAX@Z; OnRemoveCompleteStub(int,long,void *)
0x14000cb16  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000cb1d  jz      short loc_14000CB3E
0x14000cb1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb26  mov     r9d, 26h ; '&'; int
0x14000cb2c  mov     dword ptr [rsp+68h+var_38], eax; char
0x14000cb30  mov     [rsp+68h+MessageGuid], r14; MessageGuid
0x14000cb35  mov     rcx, [rcx+28h]; int
0x14000cb39  call    WPP_RECORDER_SF_sd
0x14000cb3e  add     rsp, 40h
0x14000cb42  pop     r14
0x14000cb44  pop     rdi
0x14000cb45  pop     rsi
0x14000cb46  pop     rbp
0x14000cb47  pop     rbx
0x14000cb48  retn
```
