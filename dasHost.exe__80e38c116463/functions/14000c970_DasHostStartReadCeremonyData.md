# DasHostStartReadCeremonyData

- ea: `0x14000c970`
- end: `0x14000ca81`
- name: `DasHostStartReadCeremonyData`
- size: `273`
- prototype: `__int64 __fastcall(__int64, __int64 *, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x14000b994`
- `0x14000c970`
- `0x140018290`
- `0x14001c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000c9cc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000c9cc`

## pseudocode

```c
__int64 __fastcall DasHostStartReadCeremonyData(__int64 a1, __int64 *a2, _DWORD *a3, _QWORD *a4)
{
  __int64 v4; // rdi
  __int64 result; // rax
  int v9; // edx
  int v10; // r8d
  int v11; // esi
  struct IAepAssociationReadCallback *v12; // rbx
  int v13; // [rsp+28h] [rbp-50h]
  struct IAepAssociationReadCallback *v14; // [rsp+80h] [rbp+8h] BYREF

  v4 = *a2;
  v14 = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      (int)a3,
      29,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids);
  EventActivityIdControl(2u, (LPGUID)v4);
  *(_DWORD *)(v4 + 160) = 0;
  *(_QWORD *)(v4 + 96) = a1;
  *a3 = 0;
  *a4 = 0;
  *(_QWORD *)(v4 + 104) = a3;
  *(_QWORD *)(v4 + 112) = a4;
  result = CAssociationReadCallback::Create((void *)v4, &v14);
  v11 = result;
  if ( !(_DWORD)result )
  {
    v12 = v14;
    v11 = (*(__int64 (__fastcall **)(_QWORD, struct IAepAssociationReadCallback *))(**(_QWORD **)(v4 + 48) + 64LL))(
            *(_QWORD *)(v4 + 48),
            v14);
    result = (*(__int64 (__fastcall **)(struct IAepAssociationReadCallback *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( v11 < 0 )
  {
    result = OnReadCeremonyDataCompleteStub(0, 0, v11, (void *)v4);
    LOBYTE(v11) = result;
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_sd(
             *((_QWORD *)WPP_GLOBAL_Control + 5),
             v9,
             v10,
             30,
             &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids,
             v13,
             v11);
  return result;
}

```

## disassembly

```asm
0x14000c970  mov     rax, rsp
0x14000c973  push    rbx
0x14000c974  push    rbp
0x14000c975  push    rsi
0x14000c976  push    rdi
0x14000c977  push    r12
0x14000c979  push    r15
0x14000c97b  sub     rsp, 48h
0x14000c97f  mov     rdi, [rdx]
0x14000c982  mov     rbx, r9
0x14000c985  mov     rsi, r8
0x14000c988  mov     qword ptr [rax+8], 0
0x14000c990  mov     rbp, rcx
0x14000c993  lea     r12, WPP_RECORDER_INITIALIZED
0x14000c99a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000c9a1  lea     r15, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000c9a8  jz      short loc_14000C9C4
0x14000c9aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c9b1  mov     r9d, 1Dh; int
0x14000c9b7  mov     [rax-58h], r15
0x14000c9bb  mov     rcx, [rcx+28h]; int
0x14000c9bf  call    WPP_RECORDER_SF_s
0x14000c9c4  mov     rdx, rdi; ActivityId
0x14000c9c7  mov     ecx, 2; ControlCode
0x14000c9cc  call    cs:__imp_EventActivityIdControl
0x14000c9d2  mov     dword ptr [rdi+0A0h], 0
0x14000c9dc  lea     rdx, [rsp+78h+arg_0]; struct IAepAssociationReadCallback **
0x14000c9e4  mov     [rdi+60h], rbp
0x14000c9e8  mov     rcx, rdi; void *
0x14000c9eb  mov     dword ptr [rsi], 0
0x14000c9f1  mov     qword ptr [rbx], 0
0x14000c9f8  mov     [rdi+68h], rsi
0x14000c9fc  mov     [rdi+70h], rbx
0x14000ca00  call    ?Create@CAssociationReadCallback@@SAJPEAXPEAPEAUIAepAssociationReadCallback@@@Z; CAssociationReadCallback::Create(void *,IAepAssociationReadCallback * *)
0x14000ca05  mov     esi, eax
0x14000ca07  test    eax, eax
0x14000ca09  jnz     short loc_14000CA37
0x14000ca0b  mov     rcx, [rdi+30h]
0x14000ca0f  mov     rbx, [rsp+78h+arg_0]
0x14000ca17  mov     rdx, rbx
0x14000ca1a  mov     rax, [rcx]
0x14000ca1d  mov     rax, [rax+40h]
0x14000ca21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca26  mov     esi, eax
0x14000ca28  mov     rcx, rbx
0x14000ca2b  mov     rax, [rbx]
0x14000ca2e  mov     rax, [rax+10h]
0x14000ca32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca37  test    esi, esi
0x14000ca39  jns     short loc_14000CA4C
0x14000ca3b  mov     r9, rdi; void *
0x14000ca3e  mov     r8d, esi; int
0x14000ca41  xor     edx, edx; Src
0x14000ca43  xor     ecx, ecx; Size
0x14000ca45  call    ?OnReadCeremonyDataCompleteStub@@YAJKPEBEJPEAX@Z; OnReadCeremonyDataCompleteStub(ulong,uchar const *,long,void *)
0x14000ca4a  mov     esi, eax
0x14000ca4c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000ca53  jz      short loc_14000CA74
0x14000ca55  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ca5c  mov     r9d, 1Eh; int
0x14000ca62  mov     dword ptr [rsp+78h+var_48], esi; char
0x14000ca66  mov     [rsp+78h+MessageGuid], r15; MessageGuid
0x14000ca6b  mov     rcx, [rcx+28h]; int
0x14000ca6f  call    WPP_RECORDER_SF_sd
0x14000ca74  add     rsp, 48h
0x14000ca78  pop     r15
0x14000ca7a  pop     r12
0x14000ca7c  pop     rdi
0x14000ca7d  pop     rsi
0x14000ca7e  pop     rbp
0x14000ca7f  pop     rbx
0x14000ca80  retn
```
