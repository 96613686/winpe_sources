# DasHostStartWriteCeremonyData

- ea: `0x14000cb50`
- end: `0x14000cc5b`
- name: `DasHostStartWriteCeremonyData`
- size: `267`
- prototype: `__int64 __fastcall(__int64, __int64 *, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x14000bbac`
- `0x14000cb50`
- `0x140018438`
- `0x14001c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000cbb4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14000cbb4`

## pseudocode

```c
__int64 __fastcall DasHostStartWriteCeremonyData(__int64 a1, __int64 *a2, unsigned int a3, __int64 a4)
{
  __int64 v4; // rsi
  __int64 result; // rax
  int v9; // edx
  int v10; // r8d
  int v11; // edi
  struct IAepAssociationWriteCallback *v12; // rbx
  int v13; // [rsp+28h] [rbp-40h]
  struct IAepAssociationWriteCallback *v14; // [rsp+70h] [rbp+8h] BYREF

  v4 = *a2;
  v14 = 0;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      a3,
      31,
      &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids);
  EventActivityIdControl(2u, (LPGUID)v4);
  *(_DWORD *)(v4 + 160) = 0;
  *(_QWORD *)(v4 + 96) = a1;
  result = CAssociationWriteCallback::Create((void *)v4, &v14);
  v11 = result;
  if ( !(_DWORD)result )
  {
    v12 = v14;
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, struct IAepAssociationWriteCallback *))(**(_QWORD **)(v4 + 48) + 56LL))(
            *(_QWORD *)(v4 + 48),
            a3,
            a4,
            v14);
    result = (*(__int64 (__fastcall **)(struct IAepAssociationWriteCallback *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( v11 < 0 )
  {
    result = OnWriteCeremonyDataCompleteStub(v11, (RTL_SRWLOCK *)v4, v10);
    LOBYTE(v11) = result;
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_sd(
             *((_QWORD *)WPP_GLOBAL_Control + 5),
             v9,
             v10,
             32,
             &WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids,
             v13,
             v11);
  return result;
}

```

## disassembly

```asm
0x14000cb50  mov     rax, rsp
0x14000cb53  mov     [rax+10h], rbx
0x14000cb57  mov     [rax+18h], rbp
0x14000cb5b  push    rsi
0x14000cb5c  push    rdi
0x14000cb5d  push    r12
0x14000cb5f  push    r14
0x14000cb61  push    r15
0x14000cb63  sub     rsp, 40h
0x14000cb67  mov     rsi, [rdx]
0x14000cb6a  mov     rbp, r9
0x14000cb6d  mov     r14d, r8d
0x14000cb70  mov     qword ptr [rax+8], 0
0x14000cb78  mov     rbx, rcx
0x14000cb7b  lea     r12, WPP_RECORDER_INITIALIZED
0x14000cb82  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000cb89  lea     r15, WPP_c086fa40671c3989c8f4ec8bc168966d_Traceguids
0x14000cb90  jz      short loc_14000CBAC
0x14000cb92  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cb99  mov     r9d, 1Fh; int
0x14000cb9f  mov     [rax-48h], r15
0x14000cba3  mov     rcx, [rcx+28h]; int
0x14000cba7  call    WPP_RECORDER_SF_s
0x14000cbac  mov     rdx, rsi; ActivityId
0x14000cbaf  mov     ecx, 2; ControlCode
0x14000cbb4  call    cs:__imp_EventActivityIdControl
0x14000cbba  lea     rdx, [rsp+68h+arg_0]; struct IAepAssociationWriteCallback **
0x14000cbbf  mov     dword ptr [rsi+0A0h], 0
0x14000cbc9  mov     rcx, rsi; void *
0x14000cbcc  mov     [rsi+60h], rbx
0x14000cbd0  call    ?Create@CAssociationWriteCallback@@SAJPEAXPEAPEAUIAepAssociationWriteCallback@@@Z; CAssociationWriteCallback::Create(void *,IAepAssociationWriteCallback * *)
0x14000cbd5  mov     edi, eax
0x14000cbd7  test    eax, eax
0x14000cbd9  jnz     short loc_14000CC0A
0x14000cbdb  mov     rcx, [rsi+30h]
0x14000cbdf  mov     r8, rbp
0x14000cbe2  mov     rbx, [rsp+68h+arg_0]
0x14000cbe7  mov     edx, r14d
0x14000cbea  mov     r9, rbx
0x14000cbed  mov     rax, [rcx]
0x14000cbf0  mov     rax, [rax+38h]
0x14000cbf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cbf9  mov     edi, eax
0x14000cbfb  mov     rcx, rbx
0x14000cbfe  mov     rax, [rbx]
0x14000cc01  mov     rax, [rax+10h]
0x14000cc05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc0a  test    edi, edi
0x14000cc0c  jns     short loc_14000CC1A
0x14000cc0e  mov     rdx, rsi; void *
0x14000cc11  mov     ecx, edi; int
0x14000cc13  call    ?OnWriteCeremonyDataCompleteStub@@YAJJPEAX@Z; OnWriteCeremonyDataCompleteStub(long,void *)
0x14000cc18  mov     edi, eax
0x14000cc1a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000cc21  jz      short loc_14000CC42
0x14000cc23  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cc2a  mov     r9d, 20h ; ' '; int
0x14000cc30  mov     dword ptr [rsp+68h+var_38], edi; char
0x14000cc34  mov     [rsp+68h+MessageGuid], r15; MessageGuid
0x14000cc39  mov     rcx, [rcx+28h]; int
0x14000cc3d  call    WPP_RECORDER_SF_sd
0x14000cc42  lea     r11, [rsp+68h+var_28]
0x14000cc47  mov     rbx, [r11+38h]
0x14000cc4b  mov     rbp, [r11+40h]
0x14000cc4f  mov     rsp, r11
0x14000cc52  pop     r15
0x14000cc54  pop     r14
0x14000cc56  pop     r12
0x14000cc58  pop     rdi
0x14000cc59  pop     rsi
0x14000cc5a  retn
```
