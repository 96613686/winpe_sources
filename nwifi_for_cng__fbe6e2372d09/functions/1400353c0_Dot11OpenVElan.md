# Dot11OpenVElan

- ea: `0x1400353c0`
- end: `0x140035538`
- name: `Dot11OpenVElan`
- size: `376`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400bc250`

## callees

- `0x140024944`
- `0x140032fac`
- `0x1400353c0`
- `0x14009bbb0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!RtlGUIDFromString` at `0x140035419`
- `ntoskrnl!RtlGUIDFromString` at `0x140035419`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140035476`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140035476`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035527`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035527`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400354df`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400354df`

## pseudocode

```c
__int64 __fastcall Dot11OpenVElan(__int64 a1)
{
  _WORD *v1; // rax
  NTSTATUS v3; // edi
  struct _VELAN *Interface; // rbx
  char *v6; // rax
  _LIST_ENTRY *v7; // r14
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
      PtDeallocateVElan(Interface);
    goto LABEL_6;
  }
  v7 = (_LIST_ENTRY *)(v6 + 16);
  *(_QWORD *)v6 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  *((_DWORD *)v6 + 2) = 1936290679;
  memset(v6 + 16, 0, 0xC8u);
  v7[1].Flink = &Interface->Link;
  v7[1].Blink = (_LIST_ENTRY *)a1;
  *(_QWORD *)(a1 + 24) = v7;
  *(_QWORD *)(a1 + 32) = 0;
  Interface->IoctlModule.CsqLock.OldIrql = KeAcquireSpinLockRaiseToDpc(&Interface->IoctlModule.CsqLock.SpinLock);
  Blink = Interface->IoctlModule.FileObjectList.Blink;
  if ( Blink->Flink != &Interface->IoctlModule.FileObjectList )
    __fastfail(3u);
  v7->Blink = Blink;
  v3 = 0;
  v7->Flink = &Interface->IoctlModule.FileObjectList;
  Blink->Flink = v7;
  Interface->IoctlModule.FileObjectList.Blink = v7;
  ++Interface->IoctlModule.uNumFileObjects;
  KeReleaseSpinLock(&Interface->IoctlModule.CsqLock.SpinLock, Interface->IoctlModule.CsqLock.OldIrql);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400353c0  push    rbx
0x1400353c2  push    rsi
0x1400353c3  push    rdi
0x1400353c4  push    r14
0x1400353c6  sub     rsp, 58h
0x1400353ca  mov     rax, cs:__security_cookie
0x1400353d1  xor     rax, rsp
0x1400353d4  mov     [rsp+78h+var_38], rax
0x1400353d9  movups  xmm1, xmmword ptr [rcx+58h]
0x1400353dd  mov     rax, [rcx+60h]
0x1400353e1  mov     rsi, rcx
0x1400353e4  xorps   xmm0, xmm0
0x1400353e7  movups  xmmword ptr [rsp+78h+GuidString.Length], xmm1
0x1400353ec  movups  xmmword ptr [rsp+78h+Guid.Data1], xmm0
0x1400353f1  cmp     word ptr [rax], 5Ch ; '\'
0x1400353f5  jnz     short loc_14003540F
0x1400353f7  add     rax, 2
0x1400353fb  mov     [rsp+78h+GuidString.Buffer], rax
0x140035400  mov     eax, 0FFFEh
0x140035405  add     [rsp+78h+GuidString.Length], ax
0x14003540a  add     [rsp+78h+GuidString.MaximumLength], ax
0x14003540f  lea     rdx, [rsp+78h+Guid]; Guid
0x140035414  lea     rcx, [rsp+78h+GuidString]; GuidString
0x140035419  call    cs:__imp_RtlGUIDFromString
0x140035420  nop     dword ptr [rax+rax+00h]
0x140035425  mov     edi, eax
0x140035427  test    eax, eax
0x140035429  js      short loc_140035442
0x14003542b  lea     rcx, [rsp+78h+Guid]; struct _GUID *
0x140035430  call    ?FindInterface@@YAPEAU_VELAN@@PEBU_GUID@@@Z; FindInterface(_GUID const *)
0x140035435  mov     rbx, rax
0x140035438  test    rax, rax
0x14003543b  jnz     short loc_14003546C
0x14003543d  mov     edi, 0C000000Eh
0x140035442  mov     qword ptr [rsi+20h], 0
0x14003544a  mov     qword ptr [rsi+18h], 0
0x140035452  mov     eax, edi
0x140035454  mov     rcx, [rsp+78h+var_38]
0x140035459  xor     rcx, rsp; StackCookie
0x14003545c  call    __security_check_cookie
0x140035461  add     rsp, 58h
0x140035465  pop     r14
0x140035467  pop     rdi
0x140035468  pop     rsi
0x140035469  pop     rbx
0x14003546a  retn
0x14003546c  lea     rdi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140035473  mov     rcx, rdi; Lookaside
0x140035476  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003547d  nop     dword ptr [rax+rax+00h]
0x140035482  test    rax, rax
0x140035485  jnz     short loc_1400354A3
0x140035487  mov     edi, 0C000009Ah
0x14003548c  or      eax, 0FFFFFFFFh
0x14003548f  lock xadd [rbx+1Ch], eax
0x140035494  cmp     eax, 1
0x140035497  jnz     short loc_140035442
0x140035499  mov     rcx, rbx; struct _VELAN *
0x14003549c  call    ?PtDeallocateVElan@@YAXPEAU_VELAN@@@Z; PtDeallocateVElan(_VELAN *)
0x1400354a1  jmp     short loc_140035442
0x1400354a3  lea     r14, [rax+10h]
0x1400354a7  mov     [rax], rdi
0x1400354aa  mov     rcx, r14; void *
0x1400354ad  mov     dword ptr [rax+8], 73697377h
0x1400354b4  xor     edx, edx; Val
0x1400354b6  mov     r8d, 0C8h; Size
0x1400354bc  call    memset
0x1400354c1  mov     [r14+10h], rbx
0x1400354c5  mov     [r14+18h], rsi
0x1400354c9  mov     [rsi+18h], r14
0x1400354cd  mov     qword ptr [rsi+20h], 0
0x1400354d5  lea     rsi, [rbx+1580h]
0x1400354dc  mov     rcx, rsi; SpinLock
0x1400354df  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400354e6  nop     dword ptr [rax+rax+00h]
0x1400354eb  mov     [rbx+1588h], al
0x1400354f1  lea     rax, [rbx+15A8h]
0x1400354f8  mov     rcx, [rax+8]
0x1400354fc  cmp     [rcx], rax
0x1400354ff  jz      short loc_140035508
0x140035501  mov     ecx, 3
0x140035506  int     29h; Win8: RtlFailFast(ecx)
0x140035508  mov     [r14+8], rcx
0x14003550c  xor     edi, edi
0x14003550e  mov     [r14], rax
0x140035511  mov     [rcx], r14
0x140035514  mov     rcx, rsi; SpinLock
0x140035517  mov     [rax+8], r14
0x14003551b  inc     dword ptr [rbx+15B8h]
0x140035521  mov     dl, [rbx+1588h]; NewIrql
0x140035527  call    cs:__imp_KeReleaseSpinLock
0x14003552e  nop     dword ptr [rax+rax+00h]
0x140035533  jmp     loc_140035452
```
