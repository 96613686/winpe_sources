# KsecIoctlRemoveProtectedProcessAddress(_KSECDDLSASTATE *,void *,ulong)

- ea: `0x18000d94c`
- end: `0x18000d9fe`
- name: `?KsecIoctlRemoveProtectedProcessAddress@@YAJPEAU_KSECDDLSASTATE@@PEAXK@Z`
- size: `178`
- prototype: `__int64 __fastcall(struct _KSECDDLSASTATE *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800053e0`

## callees

- `0x180005b58`
- `0x180007a64`
- `0x18000d94c`
- `0x18000df18`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x18000d9a2`
- `ntoskrnl!PsGetCurrentProcess` at `0x18000d9a2`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000d96c`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000d96c`
- `ntoskrnl!ProbeForRead` at `0x18000d995`
- `ntoskrnl!ProbeForRead` at `0x18000d995`

## pseudocode

```c
__int64 __fastcall KsecIoctlRemoveProtectedProcessAddress(struct _KSECDDLSASTATE *a1, void *a2, __int64 a3)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  struct _EPROCESS *CurrentProcess; // rax
  volatile void *Address[2]; // [rsp+30h] [rbp-18h] BYREF

  *(_OWORD *)Address = 0;
  if ( a2 && (_DWORD)a3 == 16 )
  {
    if ( ((unsigned __int8)a2 & 7) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(Address, a2, 0x10u);
    ProbeForRead(Address[0], 1u, 1u);
    CurrentProcess = (struct _EPROCESS *)PsGetCurrentProcess(v4, v3, v5, v6);
    KsecRemoveValidVm(CurrentProcess, (unsigned __int8 *)Address[0]);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 3), 57, a3, a2, a3);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x18000d94c  sub     rsp, 48h
0x18000d950  mov     r9, rdx
0x18000d953  xorps   xmm0, xmm0
0x18000d956  movups  xmmword ptr [rsp+48h+Address], xmm0
0x18000d95b  test    rdx, rdx
0x18000d95e  jz      short loc_18000D9C6
0x18000d960  cmp     r8d, 10h
0x18000d964  jnz     short loc_18000D9C6
0x18000d966  test    r9b, 7
0x18000d96a  jz      short loc_18000D978
0x18000d96c  call    cs:__imp_ExRaiseDatatypeMisalignment
0x18000d973  nop     dword ptr [rax+rax+00h]
0x18000d978  mov     r8d, 10h; Size
0x18000d97e  lea     rcx, [rsp+48h+Address]; void *
0x18000d983  call    RtlCopyFromUser
0x18000d988  mov     edx, 1; Length
0x18000d98d  mov     r8d, edx; Alignment
0x18000d990  mov     rcx, [rsp+48h+Address]; Address
0x18000d995  call    cs:__imp_ProbeForRead
0x18000d99c  nop     dword ptr [rax+rax+00h]
0x18000d9a1  nop
0x18000d9a2  call    cs:__imp_PsGetCurrentProcess
0x18000d9a9  nop     dword ptr [rax+rax+00h]
0x18000d9ae  mov     rcx, rax; struct _EPROCESS *
0x18000d9b1  mov     rdx, [rsp+48h+Address]; unsigned __int8 *
0x18000d9b6  call    KsecRemoveValidVm
0x18000d9bb  xor     eax, eax
0x18000d9bd  jmp     short loc_18000D9F8
0x18000d9bf  mov     eax, 0C0000005h
0x18000d9c4  jmp     short loc_18000D9F8
0x18000d9c6  lea     rax, WPP_GLOBAL_Control
0x18000d9cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9d4  cmp     rcx, rax
0x18000d9d7  jz      short loc_18000D9F3
0x18000d9d9  mov     eax, [rcx+2Ch]
0x18000d9dc  test    al, 1
0x18000d9de  jz      short loc_18000D9F3
0x18000d9e0  mov     edx, 39h ; '9'
0x18000d9e5  mov     [rsp+48h+var_28], r8d
0x18000d9ea  mov     rcx, [rcx+18h]
0x18000d9ee  call    WPP_SF_qL
0x18000d9f3  mov     eax, 0C000000Dh
0x18000d9f8  add     rsp, 48h
0x18000d9fc  retn
```
