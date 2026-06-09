# PcpEtwWriteEvent

- ea: `0x14001155c`
- end: `0x14001166a`
- name: `PcpEtwWriteEvent`
- size: `270`
- prototype: `__int64 __usercall@<rax>(PCEVENT_DESCRIPTOR EventDescriptor@<rcx>, LPCGUID ActivityId@<rdx>, LPCGUID RelatedActivityId@<r8>, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140011670`
- `0x1400116ec`

## callees

- `0x14001155c`
- `0x140013110`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14001160b`
- `ntoskrnl!EtwWrite` at `0x14001160b`
- `ntoskrnl!EtwWriteTransfer` at `0x140011629`
- `ntoskrnl!EtwWriteTransfer` at `0x140011629`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001163f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001163f`
- `ntoskrnl!ExAllocatePool2` at `0x1400115a9`
- `ntoskrnl!ExAllocatePool2` at `0x1400115a9`

## pseudocode

```c
void __fastcall PcpEtwWriteEvent(
        PCEVENT_DESCRIPTOR EventDescriptor,
        LPCGUID ActivityId,
        LPCGUID RelatedActivityId,
        unsigned __int16 a4,
        _QWORD *a5)
{
  ULONG v5; // edi
  void *v9; // rbx
  struct _EVENT_DATA_DESCRIPTOR *UserData; // rdx
  __int64 Pool2; // rax
  ULONG i; // r9d
  ULONGLONG v14; // rax
  __int64 v15; // rcx
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+30h] [rbp-B8h] BYREF

  v5 = a4;
  if ( a4 > 8u )
  {
    Pool2 = ExAllocatePool2(64, 16LL * a4, 2004116816);
    v9 = (void *)Pool2;
    if ( !Pool2 )
      return;
    UserData = (struct _EVENT_DATA_DESCRIPTOR *)Pool2;
  }
  else
  {
    v9 = 0;
    UserData = &v16;
  }
  for ( i = 0; i < v5; *(&UserData->Size + 2 * v15) = *((_DWORD *)a5 - 2) )
  {
    v14 = *a5;
    a5 += 2;
    v15 = i++;
    v15 *= 2;
    *(&UserData->Ptr + v15) = v14;
  }
  if ( RelatedActivityId )
    EtwWriteTransfer(PcgEventTraceHandle, EventDescriptor, ActivityId, RelatedActivityId, i, UserData);
  else
    EtwWrite(PcgEventTraceHandle, EventDescriptor, ActivityId, i, UserData);
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
}

```

## disassembly

```asm
0x14001155c  push    rbx
0x14001155e  push    rbp
0x14001155f  push    rsi
0x140011560  push    rdi
0x140011561  push    r14
0x140011563  sub     rsp, 0C0h
0x14001156a  mov     rax, cs:__security_cookie
0x140011571  xor     rax, rsp
0x140011574  mov     [rsp+0E8h+var_38], rax
0x14001157c  movzx   edi, r9w
0x140011580  mov     rsi, r8
0x140011583  mov     r14, rdx
0x140011586  mov     rbp, rcx
0x140011589  cmp     edi, 8
0x14001158c  ja      short loc_140011597
0x14001158e  xor     ebx, ebx
0x140011590  lea     rdx, [rsp+0E8h+var_B8]
0x140011595  jmp     short loc_1400115C4
0x140011597  mov     rdx, rdi
0x14001159a  mov     ecx, 40h ; '@'
0x14001159f  shl     rdx, 4
0x1400115a3  mov     r8d, 77746550h
0x1400115a9  call    cs:__imp_ExAllocatePool2
0x1400115b0  nop     dword ptr [rax+rax+00h]
0x1400115b5  mov     rbx, rax
0x1400115b8  test    rax, rax
0x1400115bb  jz      loc_14001164B
0x1400115c1  mov     rdx, rax
0x1400115c4  xor     r9d, r9d
0x1400115c7  test    edi, edi
0x1400115c9  jz      short loc_1400115F4
0x1400115cb  mov     r10, [rsp+0E8h+arg_20]
0x1400115d3  mov     rax, [r10]
0x1400115d6  lea     r10, [r10+10h]
0x1400115da  mov     ecx, r9d
0x1400115dd  inc     r9d; UserDataCount
0x1400115e0  add     rcx, rcx
0x1400115e3  mov     [rdx+rcx*8], rax
0x1400115e7  mov     eax, [r10-8]
0x1400115eb  mov     [rdx+rcx*8+8], eax
0x1400115ef  cmp     r9d, edi
0x1400115f2  jb      short loc_1400115D3
0x1400115f4  mov     rcx, cs:PcgEventTraceHandle; RegHandle
0x1400115fb  mov     r8, r14; ActivityId
0x1400115fe  test    rsi, rsi
0x140011601  jnz     short loc_140011619
0x140011603  mov     [rsp+0E8h+UserData], rdx; UserData
0x140011608  mov     rdx, rbp; EventDescriptor
0x14001160b  call    cs:__imp_EtwWrite
0x140011612  nop     dword ptr [rax+rax+00h]
0x140011617  jmp     short loc_140011635
0x140011619  mov     [rsp+0E8h+var_C0], rdx; UserData
0x14001161e  mov     rdx, rbp; EventDescriptor
0x140011621  mov     dword ptr [rsp+0E8h+UserData], r9d; UserDataCount
0x140011626  mov     r9, rsi; RelatedActivityId
0x140011629  call    cs:__imp_EtwWriteTransfer
0x140011630  nop     dword ptr [rax+rax+00h]
0x140011635  test    rbx, rbx
0x140011638  jz      short loc_14001164B
0x14001163a  xor     edx, edx; Tag
0x14001163c  mov     rcx, rbx; P
0x14001163f  call    cs:__imp_ExFreePoolWithTag
0x140011646  nop     dword ptr [rax+rax+00h]
0x14001164b  mov     rcx, [rsp+0E8h+var_38]
0x140011653  xor     rcx, rsp; StackCookie
0x140011656  call    __security_check_cookie
0x14001165b  add     rsp, 0C0h
0x140011662  pop     r14
0x140011664  pop     rdi
0x140011665  pop     rsi
0x140011666  pop     rbp
0x140011667  pop     rbx
0x140011668  retn
```
