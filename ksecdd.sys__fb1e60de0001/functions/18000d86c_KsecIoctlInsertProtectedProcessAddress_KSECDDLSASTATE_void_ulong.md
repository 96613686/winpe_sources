# KsecIoctlInsertProtectedProcessAddress(_KSECDDLSASTATE *,void *,ulong)

- ea: `0x18000d86c`
- end: `0x18000d946`
- name: `?KsecIoctlInsertProtectedProcessAddress@@YAJPEAU_KSECDDLSASTATE@@PEAXK@Z`
- size: `218`
- prototype: `__int64 __fastcall(struct _KSECDDLSASTATE *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800053e0`

## callees

- `0x180007a64`
- `0x18000c7a0`
- `0x18000d86c`
- `0x18000df18`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x18000d8cd`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000d8cd`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000d895`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000d895`
- `ntoskrnl!ProbeForRead` at `0x18000d8c0`
- `ntoskrnl!ProbeForRead` at `0x18000d8c0`

## pseudocode

```c
__int64 __fastcall KsecIoctlInsertProtectedProcessAddress(struct _KSECDDLSASTATE *a1, void *a2, __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  struct _EPROCESS *CurrentProcess; // rax
  int inserted; // eax
  unsigned int v10; // ecx
  volatile void *Address[2]; // [rsp+30h] [rbp-18h] BYREF

  *(_OWORD *)Address = 0;
  if ( a2 && (_DWORD)a3 == 16 )
  {
    if ( ((unsigned __int8)a2 & 7) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(Address, a2, 0x10u);
    ProbeForRead(Address[0], LODWORD(Address[1]), 1u);
    CurrentProcess = (struct _EPROCESS *)PsGetCurrentProcess(v5, v4, v6, v7);
    inserted = KsecInsertValidVm(a1, 0, CurrentProcess, (unsigned __int8 *)Address[0], (unsigned int)Address[1], 1u);
    v10 = 0;
    if ( inserted < 0 )
      return (unsigned int)inserted;
    return v10;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 3), 56, a3, a2, a3);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x18000d86c  push    rbx
0x18000d86e  sub     rsp, 40h
0x18000d872  mov     r9, rdx
0x18000d875  mov     rbx, rcx
0x18000d878  xorps   xmm0, xmm0
0x18000d87b  movups  xmmword ptr [rsp+48h+Address], xmm0
0x18000d880  test    rdx, rdx
0x18000d883  jz      loc_18000D90D
0x18000d889  cmp     r8d, 10h
0x18000d88d  jnz     short loc_18000D90D
0x18000d88f  test    r9b, 7
0x18000d893  jz      short loc_18000D8A1
0x18000d895  call    cs:__imp_ExRaiseDatatypeMisalignment
0x18000d89c  nop     dword ptr [rax+rax+00h]
0x18000d8a1  mov     r8d, 10h; Size
0x18000d8a7  lea     rcx, [rsp+48h+Address]; void *
0x18000d8ac  call    RtlCopyFromUser
0x18000d8b1  mov     edx, dword ptr [rsp+48h+Address+8]; Length
0x18000d8b5  mov     r8d, 1; Alignment
0x18000d8bb  mov     rcx, [rsp+48h+Address]; Address
0x18000d8c0  call    cs:__imp_ProbeForRead
0x18000d8c7  nop     dword ptr [rax+rax+00h]
0x18000d8cc  nop
0x18000d8cd  call    cs:__imp_PsGetCurrentProcess
0x18000d8d4  nop     dword ptr [rax+rax+00h]
0x18000d8d9  mov     r8, rax; struct _EPROCESS *
0x18000d8dc  mov     [rsp+48h+var_20], 1; unsigned int
0x18000d8e4  mov     eax, dword ptr [rsp+48h+Address+8]
0x18000d8e8  mov     [rsp+48h+var_28], eax; unsigned int
0x18000d8ec  mov     r9, [rsp+48h+Address]; unsigned __int8 *
0x18000d8f1  xor     edx, edx; void *
0x18000d8f3  mov     rcx, rbx; struct _KSECDDLSASTATE *
0x18000d8f6  call    ?KsecInsertValidVm@@YAJPEAU_KSECDDLSASTATE@@PEAXPEAU_EPROCESS@@PEAEKK@Z; KsecInsertValidVm(_KSECDDLSASTATE *,void *,_EPROCESS *,uchar *,ulong,ulong)
0x18000d8fb  xor     ecx, ecx
0x18000d8fd  test    eax, eax
0x18000d8ff  cmovs   ecx, eax
0x18000d902  mov     eax, ecx
0x18000d904  jmp     short loc_18000D93F
0x18000d906  mov     eax, 0C0000005h
0x18000d90b  jmp     short loc_18000D93F
0x18000d90d  lea     rax, WPP_GLOBAL_Control
0x18000d914  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d91b  cmp     rcx, rax
0x18000d91e  jz      short loc_18000D93A
0x18000d920  mov     eax, [rcx+2Ch]
0x18000d923  test    al, 1
0x18000d925  jz      short loc_18000D93A
0x18000d927  mov     edx, 38h ; '8'
0x18000d92c  mov     [rsp+48h+var_28], r8d
0x18000d931  mov     rcx, [rcx+18h]
0x18000d935  call    WPP_SF_qL
0x18000d93a  mov     eax, 0C000000Dh
0x18000d93f  add     rsp, 40h
0x18000d943  pop     rbx
0x18000d944  retn
```
