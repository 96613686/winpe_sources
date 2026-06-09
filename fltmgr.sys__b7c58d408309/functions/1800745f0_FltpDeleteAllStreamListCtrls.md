# FltpDeleteAllStreamListCtrls

- ea: `0x1800745f0`
- end: `0x180074804`
- name: `FltpDeleteAllStreamListCtrls`
- size: `532`
- prototype: `_QWORD *__fastcall(char *OwnerId)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180068e20`

## callees

- `0x18000f5b0`
- `0x1800148b0`
- `0x180015240`
- `0x180062050`
- `0x1800745f0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1800746e9`
- `ntoskrnl!KeBugCheckEx` at `0x18007470b`
- `ntoskrnl!KeBugCheckEx` at `0x1800746e9`
- `ntoskrnl!KeBugCheckEx` at `0x18007470b`
- `ntoskrnl!ExReleaseFastResource` at `0x18007466d`
- `ntoskrnl!ExReleaseFastResource` at `0x18007466d`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180074628`
- `ntoskrnl!KeEnterGuardedRegion` at `0x180074628`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180074679`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x180074679`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18007463c`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18007463c`
- `ntoskrnl!FsRtlRemovePerStreamContext` at `0x18007b2a5`
- `ntoskrnl!FsRtlRemovePerStreamContext` at `0x18007b2a5`

## string_xrefs

- `0x18007471d`: `FltpDeleteAllStreamListCtrls`
- `0x1800747ec`: `FltpDeleteAllStreamListCtrls`

## pseudocode

```c
_QWORD *__fastcall FltpDeleteAllStreamListCtrls(char *OwnerId)
{
  char *v2; // rbx
  __int64 v3; // r8
  __int64 v4; // rcx
  _QWORD *result; // rax
  __int64 v6; // rcx
  char *v7; // rbx
  __int64 v8; // rax
  _QWORD *v9; // rcx
  volatile signed __int32 *v10; // r14
  __int64 v11; // rdx
  __int64 v12; // rcx
  PFSRTL_PER_STREAM_CONTEXT v13; // rax
  _QWORD v14[3]; // [rsp+30h] [rbp-18h] BYREF

  v14[1] = v14;
  v2 = OwnerId + 1472;
  v14[0] = v14;
  if ( (*((_DWORD *)OwnerId + 399) & 1) != 0 )
    KeBugCheckEx(0xF5u, 0x70u, (ULONG_PTR)(OwnerId + 1472), 0, 0);
  KeEnterGuardedRegion();
  LOBYTE(v3) = 1;
  ExAcquireFastResourceExclusive(v2, 0, v3);
  while ( *((_DWORD *)OwnerId + 398) )
  {
    _InterlockedDecrement((volatile signed __int32 *)v2 + 30);
    v9 = v2 + 104;
    v10 = (volatile signed __int32 *)*((_QWORD *)v2 + 13);
    v11 = *(_QWORD *)v10;
    if ( *((char **)v10 + 1) != v2 + 104 || *(volatile signed __int32 **)(v11 + 8) != v10 )
LABEL_12:
      __fastfail(3u);
    *v9 = v11;
    *(_QWORD *)(v11 + 8) = v9;
    *(_QWORD *)v10 = 0;
    if ( (v10[4] & 1) != 0 )
    {
      v12 = *((_QWORD *)v10 - 2);
      if ( v12
        && (*(_BYTE *)(v12 + 7) & 0xF0u) >= 0x50
        && (v13 = *(PFSRTL_PER_STREAM_CONTEXT *)(v12 + 112)) != 0
        && v13->OwnerId == OwnerId
        && v13->InstanceId == (void *)v12 )
      {
        *(_QWORD *)(v12 + 112) = 0;
      }
      else
      {
        v13 = FsRtlRemovePerStreamContext((PFSRTL_ADVANCED_FCB_HEADER)v12, OwnerId, *((PVOID *)v10 - 2));
      }
      if ( (v10[4] & 1) != 0 )
        _InterlockedAnd(v10 + 4, 0xFFFFFFFE);
      if ( v13 )
      {
        v8 = v14[0];
        if ( *(_QWORD **)(v14[0] + 8LL) != v14 )
          goto LABEL_12;
        *(_QWORD *)v10 = v14[0];
        *((_QWORD *)v10 + 1) = v14;
        *(_QWORD *)(v8 + 8) = v10;
        v14[0] = v10;
      }
    }
  }
  if ( (*((_DWORD *)v2 + 31) & 1) != 0 )
    KeBugCheckEx(0xF5u, 0x70u, (ULONG_PTR)v2, 0, 0);
  ExReleaseFastResource(v2, 0);
  KeLeaveGuardedRegion();
  if ( (byte_1800404C2 & 1) != 0 )
    McTemplateU0sp_EtwWriteTransfer(v4, (__int64)StreamListCtrlSup_c177, "FltpDeleteAllStreamListCtrls", v14);
  while ( 1 )
  {
    result = (_QWORD *)v14[0];
    if ( (_QWORD *)v14[0] == v14 )
      break;
    if ( *(_QWORD **)(v14[0] + 8LL) != v14 )
      goto LABEL_12;
    v6 = *(_QWORD *)v14[0];
    if ( *(_QWORD *)(*(_QWORD *)v14[0] + 8LL) != v14[0] )
      goto LABEL_12;
    v14[0] = *(_QWORD *)v14[0];
    *(_QWORD *)(v6 + 8) = v14;
    v7 = (char *)(result - 6);
    *result = 0;
    CleanupStreamListCtrl((__int64)(result - 6));
    FltpReleaseStreamListCtrl(v7);
  }
  if ( (byte_1800404C2 & 1) != 0 )
    return (_QWORD *)McTemplateU0sw_EtwWriteTransfer(
                       (__int64)v14,
                       (__int64)StreamListCtrlSup_c205,
                       "FltpDeleteAllStreamListCtrls",
                       *((_WORD *)OwnerId + 56) >> 1,
                       *((_QWORD *)OwnerId + 15));
  return result;
}

```

## disassembly

```asm
0x1800745f0  mov     [rsp+arg_8], rbx
0x1800745f5  mov     [rsp+arg_10], rsi
0x1800745fa  push    rdi
0x1800745fb  sub     rsp, 40h
0x1800745ff  lea     rax, [rsp+48h+var_18]
0x180074604  mov     rdi, rcx
0x180074607  mov     [rsp+48h+var_10], rax
0x18007460c  lea     rbx, [rcx+5C0h]
0x180074613  lea     rax, [rsp+48h+var_18]
0x180074618  mov     [rsp+48h+var_18], rax
0x18007461d  mov     eax, [rbx+7Ch]
0x180074620  test    al, 1
0x180074622  jnz     loc_1800746D2
0x180074628  call    cs:__imp_KeEnterGuardedRegion
0x18007462f  nop     dword ptr [rax+rax+00h]
0x180074634  mov     r8b, 1
0x180074637  xor     edx, edx
0x180074639  mov     rcx, rbx
0x18007463c  call    cs:__imp_ExAcquireFastResourceExclusive
0x180074643  nop     dword ptr [rax+rax+00h]
0x180074648  xor     esi, esi
0x18007464a  mov     [rsp+48h+arg_0], r14
0x18007464f  mov     eax, [rdi+638h]
0x180074655  test    eax, eax
0x180074657  jnz     loc_1800747BA
0x18007465d  mov     eax, [rbx+7Ch]
0x180074660  test    al, 1
0x180074662  jnz     loc_1800746F6
0x180074668  xor     edx, edx
0x18007466a  mov     rcx, rbx
0x18007466d  call    cs:__imp_ExReleaseFastResource
0x180074674  nop     dword ptr [rax+rax+00h]
0x180074679  call    cs:__imp_KeLeaveGuardedRegion
0x180074680  nop     dword ptr [rax+rax+00h]
0x180074685  test    cs:byte_1800404C2, 1
0x18007468c  jnz     loc_1800747E7
0x180074692  mov     rax, [rsp+48h+var_18]
0x180074697  lea     rcx, [rsp+48h+var_18]
0x18007469c  cmp     rax, rcx
0x18007469f  jnz     short loc_1800746C0
0x1800746a1  test    cs:byte_1800404C2, 1
0x1800746a8  jnz     short loc_180074718
0x1800746aa  mov     r14, [rsp+48h+arg_0]
0x1800746af  mov     rbx, [rsp+48h+arg_8]
0x1800746b4  mov     rsi, [rsp+48h+arg_10]
0x1800746b9  add     rsp, 40h
0x1800746bd  pop     rdi
0x1800746be  retn
0x1800746c0  lea     rcx, [rsp+48h+var_18]
0x1800746c5  cmp     [rax+8], rcx
0x1800746c9  jz      short loc_180074741
0x1800746cb  mov     ecx, 3
0x1800746d0  int     29h; Win8: RtlFailFast(ecx)
0x1800746d2  xor     esi, esi
0x1800746d4  xor     r9d, r9d; BugCheckParameter3
0x1800746d7  mov     r8, rbx; BugCheckParameter2
0x1800746da  mov     [rsp+48h+BugCheckParameter4], rsi; BugCheckParameter4
0x1800746df  mov     edx, 70h ; 'p'; BugCheckParameter1
0x1800746e4  mov     ecx, 0F5h; BugCheckCode
0x1800746e9  call    cs:__imp_KeBugCheckEx
0x1800746f6  xor     r9d, r9d; BugCheckParameter3
0x1800746f9  mov     [rsp+48h+BugCheckParameter4], rsi; BugCheckParameter4
0x1800746fe  mov     r8, rbx; BugCheckParameter2
0x180074701  mov     edx, 70h ; 'p'; BugCheckParameter1
0x180074706  mov     ecx, 0F5h; BugCheckCode
0x18007470b  call    cs:__imp_KeBugCheckEx
0x180074718  movzx   r9d, word ptr [rdi+70h]
0x18007471d  lea     r8, aFltpdeletealls; "FltpDeleteAllStreamListCtrls"
0x180074724  mov     rax, [rdi+78h]
0x180074728  lea     rdx, StreamListCtrlSup_c205
0x18007472f  shr     r9d, 1
0x180074732  mov     [rsp+48h+BugCheckParameter4], rax
0x180074737  call    McTemplateU0sw_EtwWriteTransfer
0x18007473c  jmp     loc_1800746AA
0x180074741  mov     rcx, [rax]
0x180074744  cmp     [rcx+8], rax
0x180074748  jnz     short loc_1800746CB
0x18007474a  mov     [rsp+48h+var_18], rcx
0x18007474f  lea     rdx, [rsp+48h+var_18]
0x180074754  mov     [rcx+8], rdx
0x180074758  lea     rbx, [rax-30h]
0x18007475c  mov     rcx, rbx
0x18007475f  mov     [rax], rsi
0x180074762  call    CleanupStreamListCtrl
0x180074767  mov     rcx, rbx; Entry
0x18007476a  call    FltpReleaseStreamListCtrl
0x18007476f  jmp     loc_180074692
0x180074774  mov     ecx, [r14+10h]
0x180074778  test    cl, 1
0x18007477b  jz      short loc_180074783
0x18007477d  lock and dword ptr [r14+10h], 0FFFFFFFEh
0x180074783  test    rax, rax
0x180074786  jz      loc_18007464F
0x18007478c  mov     rax, [rsp+48h+var_18]
0x180074791  lea     rcx, [rsp+48h+var_18]
0x180074796  cmp     [rax+8], rcx
0x18007479a  jnz     loc_1800746CB
0x1800747a0  mov     [r14], rax
0x1800747a3  lea     rcx, [rsp+48h+var_18]
0x1800747a8  mov     [r14+8], rcx
0x1800747ac  mov     [rax+8], r14
0x1800747b0  mov     [rsp+48h+var_18], r14
0x1800747b5  jmp     loc_18007464F
0x1800747ba  lock dec dword ptr [rbx+78h]
0x1800747be  lea     rcx, [rbx+68h]
0x1800747c2  mov     r14, [rcx]
0x1800747c5  mov     rdx, [r14]
0x1800747c8  mov     rax, [r14+8]
0x1800747cc  cmp     rax, rcx
0x1800747cf  jnz     loc_1800746CB
0x1800747d5  mov     rax, [rdx+8]
0x1800747d9  cmp     rax, r14
0x1800747dc  jnz     loc_1800746CB
0x1800747e2  jmp     loc_18007B258
0x1800747e7  lea     r9, [rsp+48h+var_18]
0x1800747ec  lea     r8, aFltpdeletealls; "FltpDeleteAllStreamListCtrls"
0x1800747f3  lea     rdx, StreamListCtrlSup_c177
0x1800747fa  call    McTemplateU0sp_EtwWriteTransfer
0x1800747ff  jmp     loc_180074692
0x18007b258  mov     [rcx], rdx
0x18007b25b  mov     [rdx+8], rcx
0x18007b25f  mov     [r14], rsi
0x18007b262  mov     eax, [r14+10h]
0x18007b266  test    al, 1
0x18007b268  jz      loc_18007464F
0x18007b26e  mov     rcx, [r14-10h]; StreamContext
0x18007b272  test    rcx, rcx
0x18007b275  jz      short loc_18007B29F
0x18007b277  movzx   eax, byte ptr [rcx+7]
0x18007b27b  and     al, 0F0h
0x18007b27d  cmp     al, 50h ; 'P'
0x18007b27f  jb      short loc_18007B29F
0x18007b281  mov     rax, [rcx+70h]
0x18007b285  test    rax, rax
0x18007b288  jz      short loc_18007B29F
0x18007b28a  cmp     [rax+10h], rdi
0x18007b28e  jnz     short loc_18007B29F
0x18007b290  cmp     [rax+18h], rcx
0x18007b294  jnz     short loc_18007B29F
0x18007b296  mov     [rcx+70h], rsi
0x18007b29a  jmp     loc_180074774
0x18007b29f  mov     r8, rcx; InstanceId
0x18007b2a2  mov     rdx, rdi; OwnerId
0x18007b2a5  call    cs:__imp_FsRtlRemovePerStreamContext
0x18007b2ac  nop     dword ptr [rax+rax+00h]
0x18007b2b1  nop
0x18007b2b2  jmp     loc_180074774
```
