# Dot11OpenVElan

- ea: `0x1400351a0`
- end: `0x140035318`
- name: `Dot11OpenVElan`
- size: `376`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400b9250`

## callees

- `0x140024944`
- `0x140032d8c`
- `0x1400351a0`
- `0x14009a3d0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!RtlGUIDFromString` at `0x1400351f9`
- `ntoskrnl!RtlGUIDFromString` at `0x1400351f9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140035256`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140035256`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035307`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035307`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400352bf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400352bf`

## pseudocode

```c
__int64 __fastcall Dot11OpenVElan(__int64 a1)
{
  _WORD *v1; // rax
  NTSTATUS v3; // edi
  struct _VELAN *Interface; // rbx
  char *v6; // rax
  unsigned int v7; // edx
  _LIST_ENTRY *v8; // r14
  _LIST_ENTRY *Blink; // rcx
  UNICODE_STRING GuidString; // [rsp+20h] [rbp-58h] BYREF
  GUID Guid; // [rsp+30h] [rbp-48h] BYREF

  v1 = *(_WORD **)(a1 + 96);
  GuidString = *(UNICODE_STRING *)(a1 + 88);
  Guid = 0;
  if ( *v1 == 92 )
  {
    GuidString.Buffer = v1 + 1;
    GuidString.Length -= 2;
    GuidString.MaximumLength -= 2;
  }
  v3 = RtlGUIDFromString(&GuidString, &Guid);
  if ( v3 < 0 )
    goto LABEL_6;
  Interface = FindInterface(&Guid);
  if ( !Interface )
  {
    v3 = -1073741810;
LABEL_6:
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    return (unsigned int)v3;
  }
  v6 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
  if ( !v6 )
  {
    v3 = -1073741670;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&Interface->RefCount, 0xFFFFFFFF) == 1 )
      PtDeallocateVElan(Interface, v7);
    goto LABEL_6;
  }
  v8 = (_LIST_ENTRY *)(v6 + 16);
  *(_QWORD *)v6 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  *((_DWORD *)v6 + 2) = 1936290679;
  memset(v6 + 16, 0, 0xC8u);
  v8[1].Flink = &Interface->Link;
  v8[1].Blink = (_LIST_ENTRY *)a1;
  *(_QWORD *)(a1 + 24) = v8;
  *(_QWORD *)(a1 + 32) = 0;
  Interface->IoctlModule.CsqLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&Interface->IoctlModule.CsqLock.SpinLock);
  Blink = Interface->IoctlModule.FileObjectList.Blink;
  if ( Blink->Flink != &Interface->IoctlModule.FileObjectList )
    __fastfail(3u);
  v8->Blink = Blink;
  v3 = 0;
  v8->Flink = &Interface->IoctlModule.FileObjectList;
  Blink->Flink = v8;
  Interface->IoctlModule.FileObjectList.Blink = v8;
  ++Interface->IoctlModule.uNumFileObjects;
  KeReleaseSpinLock(&Interface->IoctlModule.CsqLock.SpinLock, Interface->IoctlModule.CsqLock.OldIrql);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400351a0  push    rbx
0x1400351a2  push    rsi
0x1400351a3  push    rdi
0x1400351a4  push    r14
0x1400351a6  sub     rsp, 58h
0x1400351aa  mov     rax, cs:__security_cookie
0x1400351b1  xor     rax, rsp
0x1400351b4  mov     [rsp+78h+var_38], rax
0x1400351b9  movups  xmm1, xmmword ptr [rcx+58h]
0x1400351bd  mov     rax, [rcx+60h]
0x1400351c1  mov     rsi, rcx
0x1400351c4  xorps   xmm0, xmm0
0x1400351c7  movups  xmmword ptr [rsp+78h+GuidString.Length], xmm1
0x1400351cc  movups  xmmword ptr [rsp+78h+Guid.Data1], xmm0
0x1400351d1  cmp     word ptr [rax], 5Ch ; '\'
0x1400351d5  jnz     short loc_1400351EF
0x1400351d7  add     rax, 2
0x1400351db  mov     [rsp+78h+GuidString.Buffer], rax
0x1400351e0  mov     eax, 0FFFEh
0x1400351e5  add     [rsp+78h+GuidString.Length], ax
0x1400351ea  add     [rsp+78h+GuidString.MaximumLength], ax
0x1400351ef  lea     rdx, [rsp+78h+Guid]; Guid
0x1400351f4  lea     rcx, [rsp+78h+GuidString]; GuidString
0x1400351f9  call    cs:__imp_RtlGUIDFromString
0x140035200  nop     dword ptr [rax+rax+00h]
0x140035205  mov     edi, eax
0x140035207  test    eax, eax
0x140035209  js      short loc_140035222
0x14003520b  lea     rcx, [rsp+78h+Guid]; struct _GUID *
0x140035210  call    ?FindInterface@@YAPEAU_VELAN@@PEBU_GUID@@@Z; FindInterface(_GUID const *)
0x140035215  mov     rbx, rax
0x140035218  test    rax, rax
0x14003521b  jnz     short loc_14003524C
0x14003521d  mov     edi, 0C000000Eh
0x140035222  mov     qword ptr [rsi+20h], 0
0x14003522a  mov     qword ptr [rsi+18h], 0
0x140035232  mov     eax, edi
0x140035234  mov     rcx, [rsp+78h+var_38]
0x140035239  xor     rcx, rsp; StackCookie
0x14003523c  call    __security_check_cookie
0x140035241  add     rsp, 58h
0x140035245  pop     r14
0x140035247  pop     rdi
0x140035248  pop     rsi
0x140035249  pop     rbx
0x14003524a  retn
0x14003524c  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140035253  mov     rcx, rdi; Lookaside
0x140035256  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003525d  nop     dword ptr [rax+rax+00h]
0x140035262  test    rax, rax
0x140035265  jnz     short loc_140035283
0x140035267  mov     edi, 0C000009Ah
0x14003526c  or      eax, 0FFFFFFFFh
0x14003526f  lock xadd [rbx+1Ch], eax
0x140035274  cmp     eax, 1
0x140035277  jnz     short loc_140035222
0x140035279  mov     rcx, rbx; struct _VELAN *
0x14003527c  call    ?PtDeallocateVElan@@YAXPEAU_VELAN@@@Z; PtDeallocateVElan(_VELAN *)
0x140035281  jmp     short loc_140035222
0x140035283  lea     r14, [rax+10h]
0x140035287  mov     [rax], rdi
0x14003528a  mov     rcx, r14; void *
0x14003528d  mov     dword ptr [rax+8], 73697377h
0x140035294  xor     edx, edx; Val
0x140035296  mov     r8d, 0C8h; Size
0x14003529c  call    memset
0x1400352a1  mov     [r14+10h], rbx
0x1400352a5  mov     [r14+18h], rsi
0x1400352a9  mov     [rsi+18h], r14
0x1400352ad  mov     qword ptr [rsi+20h], 0
0x1400352b5  lea     rsi, [rbx+1580h]
0x1400352bc  mov     rcx, rsi; SpinLock
0x1400352bf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400352c6  nop     dword ptr [rax+rax+00h]
0x1400352cb  mov     [rbx+1588h], al
0x1400352d1  lea     rax, [rbx+15A8h]
0x1400352d8  mov     rcx, [rax+8]
0x1400352dc  cmp     [rcx], rax
0x1400352df  jz      short loc_1400352E8
0x1400352e1  mov     ecx, 3
0x1400352e6  int     29h; Win8: RtlFailFast(ecx)
0x1400352e8  mov     [r14+8], rcx
0x1400352ec  xor     edi, edi
0x1400352ee  mov     [r14], rax
0x1400352f1  mov     [rcx], r14
0x1400352f4  mov     rcx, rsi; SpinLock
0x1400352f7  mov     [rax+8], r14
0x1400352fb  inc     dword ptr [rbx+15B8h]
0x140035301  mov     dl, [rbx+1588h]; NewIrql
0x140035307  call    cs:__imp_KeReleaseSpinLock
0x14003530e  nop     dword ptr [rax+rax+00h]
0x140035313  jmp     loc_140035232
```
