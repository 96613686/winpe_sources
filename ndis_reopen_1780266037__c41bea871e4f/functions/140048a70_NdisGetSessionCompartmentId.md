# NdisGetSessionCompartmentId

- ea: `0x140048a70`
- end: `0x140048ba2`
- name: `NdisGetSessionCompartmentId`
- size: `306`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400485c0`
- `0x1400489b0`
- `0x140048a10`
- `0x1400cebe0`

## callees

- `0x140048a70`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140048aa2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140048aa2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140048b74`
- `ntoskrnl!KeReleaseSpinLock` at `0x140048b74`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140048b45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140048b45`
- `ntoskrnl!SeQueryInformationToken` at `0x140048b15`
- `ntoskrnl!SeQueryInformationToken` at `0x140048b15`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140048b91`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140048b91`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140048ac8`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140048ac8`
- `ntoskrnl!PsGetThreadSessionId` at `0x140048adf`
- `ntoskrnl!PsGetThreadSessionId` at `0x140048adf`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140048b26`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140048b26`

## pseudocode

```c
__int64 __fastcall NdisGetSessionCompartmentId(unsigned int a1)
{
  unsigned int v1; // ebx
  struct _KTHREAD *CurrentThread; // rdi
  __int64 v3; // rcx
  PACCESS_TOKEN v4; // rax
  void *v5; // rsi
  unsigned int CurrentProcessSessionId; // eax
  NTSTATUS v8; // ebx
  unsigned int v9; // edi
  KIRQL v10; // al
  unsigned __int8 EffectiveOnly; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int8 CopyOnOpen; // [rsp+58h] [rbp+10h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+60h] [rbp+18h] BYREF
  PVOID TokenInformation; // [rsp+68h] [rbp+20h] BYREF

  v1 = a1;
  if ( a1 == -1 )
  {
    CurrentThread = KeGetCurrentThread();
    CopyOnOpen = 0;
    EffectiveOnly = 0;
    ImpersonationLevel = SecurityAnonymous;
    TokenInformation = 0;
    if ( KeGetCurrentIrql() >= 2u )
    {
      CurrentProcessSessionId = PsGetCurrentProcessSessionId(v3);
    }
    else
    {
      v4 = PsReferenceImpersonationToken(CurrentThread, &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
      v5 = v4;
      if ( v4 )
      {
        v8 = SeQueryInformationToken(v4, TokenSessionId, &TokenInformation);
        PsDereferenceImpersonationToken(v5);
        if ( v8 >= 0 )
        {
          v1 = (unsigned int)TokenInformation;
          goto LABEL_6;
        }
      }
      CurrentProcessSessionId = PsGetThreadSessionId(CurrentThread);
    }
    v1 = CurrentProcessSessionId;
  }
LABEL_6:
  if ( v1 >= dword_140122898 )
    return 1;
  v9 = 0;
  v10 = KeAcquireSpinLockRaiseToDpc(&qword_1401228E0);
  if ( v1 < dword_140122898 )
    v9 = *((_DWORD *)qword_1401228E8 + 6 * v1);
  KeReleaseSpinLock(&qword_1401228E0, v10);
  if ( !v9 )
    return 1;
  return v9;
}

```

## disassembly

```asm
0x140048a70  push    rbx
0x140048a72  push    rbp
0x140048a73  push    rdi
0x140048a74  sub     rsp, 30h
0x140048a78  xor     ebp, ebp
0x140048a7a  mov     [rsp+48h+var_20], rsi
0x140048a7f  mov     ebx, ecx
0x140048a81  cmp     ecx, 0FFFFFFFFh
0x140048a84  jnz     short loc_140048AED
0x140048a86  mov     rdi, gs:188h
0x140048a8f  mov     [rsp+48h+CopyOnOpen], bpl
0x140048a94  mov     [rsp+48h+EffectiveOnly], bpl
0x140048a99  mov     [rsp+48h+ImpersonationLevel], ebp
0x140048a9d  mov     [rsp+48h+TokenInformation], rbp
0x140048aa2  call    cs:__imp_KeGetCurrentIrql
0x140048aa9  nop     dword ptr [rax+rax+00h]
0x140048aae  cmp     al, 2
0x140048ab0  jnb     loc_140048B91
0x140048ab6  lea     r9, [rsp+48h+ImpersonationLevel]; ImpersonationLevel
0x140048abb  mov     rcx, rdi; Thread
0x140048abe  lea     r8, [rsp+48h+EffectiveOnly]; EffectiveOnly
0x140048ac3  lea     rdx, [rsp+48h+CopyOnOpen]; CopyOnOpen
0x140048ac8  call    cs:__imp_PsReferenceImpersonationToken
0x140048acf  nop     dword ptr [rax+rax+00h]
0x140048ad4  mov     rsi, rax
0x140048ad7  test    rax, rax
0x140048ada  jnz     short loc_140048B08
0x140048adc  mov     rcx, rdi
0x140048adf  call    cs:__imp_PsGetThreadSessionId
0x140048ae6  nop     dword ptr [rax+rax+00h]
0x140048aeb  mov     ebx, eax
0x140048aed  cmp     ebx, cs:dword_140122898
0x140048af3  mov     rsi, [rsp+48h+var_20]
0x140048af8  jb      short loc_140048B3C
0x140048afa  mov     eax, 1
0x140048aff  add     rsp, 30h
0x140048b03  pop     rdi
0x140048b04  pop     rbp
0x140048b05  pop     rbx
0x140048b06  retn
0x140048b08  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x140048b0d  mov     edx, 0Ch; TokenInformationClass
0x140048b12  mov     rcx, rsi; Token
0x140048b15  call    cs:__imp_SeQueryInformationToken
0x140048b1c  nop     dword ptr [rax+rax+00h]
0x140048b21  mov     rcx, rsi; ImpersonationToken
0x140048b24  mov     ebx, eax
0x140048b26  call    cs:__imp_PsDereferenceImpersonationToken
0x140048b2d  nop     dword ptr [rax+rax+00h]
0x140048b32  test    ebx, ebx
0x140048b34  js      short loc_140048ADC
0x140048b36  mov     ebx, dword ptr [rsp+48h+TokenInformation]
0x140048b3a  jmp     short loc_140048AED
0x140048b3c  lea     rcx, qword_1401228E0; SpinLock
0x140048b43  mov     edi, ebp
0x140048b45  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140048b4c  nop     dword ptr [rax+rax+00h]
0x140048b51  cmp     ebx, cs:dword_140122898
0x140048b57  jnb     short loc_140048B6A
0x140048b59  mov     edx, ebx
0x140048b5b  lea     r8, [rdx+rdx*2]
0x140048b5f  mov     rdx, cs:qword_1401228E8
0x140048b66  mov     edi, [rdx+r8*8]
0x140048b6a  movzx   edx, al; NewIrql
0x140048b6d  lea     rcx, qword_1401228E0; SpinLock
0x140048b74  call    cs:__imp_KeReleaseSpinLock
0x140048b7b  nop     dword ptr [rax+rax+00h]
0x140048b80  mov     eax, 1
0x140048b85  test    edi, edi
0x140048b87  cmovz   edi, eax
0x140048b8a  mov     eax, edi
0x140048b8c  jmp     loc_140048AFF
0x140048b91  call    cs:__imp_PsGetCurrentProcessSessionId
0x140048b98  nop     dword ptr [rax+rax+00h]
0x140048b9d  jmp     loc_140048AEB
```
