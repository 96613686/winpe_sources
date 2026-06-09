# Pku2uCreateLinkedLogonSession(_LUID *,_PKU2U_LOGON_SESSION * *)

- ea: `0x180016cdc`
- end: `0x180016e0d`
- name: `?Pku2uCreateLinkedLogonSession@@YAJPEAU_LUID@@PEAPEAU_PKU2U_LOGON_SESSION@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(struct _LUID *, struct _PKU2U_LOGON_SESSION **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000bcd0`

## callees

- `0x18000af80`
- `0x180016cdc`
- `0x180016e14`
- `0x180021a54`
- `0x18002cce4`
- `0x180046010`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x180016d85`
- `ntdll!RtlInitializeCriticalSection` at `0x180016d85`
- `LSASRV!LsaIRegisterNotification` at `0x180016dcd`
- `LSASRV!LsaIRegisterNotification` at `0x180016dcd`

## pseudocode

```c
__int64 __fastcall Pku2uCreateLinkedLogonSession(struct _LUID *a1, struct _PKU2U_LOGON_SESSION **a2)
{
  struct _PKU2U_LOGON_SESSION *v4; // rsi
  __int64 v5; // rbx
  NTSTATUS v6; // edi
  void *v7; // rax
  struct _PKU2U_LOGON_SESSION *v8; // rbx
  struct _PKU2U_LOGON_SESSION *v10; // [rsp+70h] [rbp+18h] BYREF

  v4 = 0;
  if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))(88);
  }
  else
  {
    v7 = (void *)(**((__int64 (__fastcall ***)(__int64))Pku2uGlobalBaseSSP + 31))(88);
    v5 = (__int64)v7;
    if ( v7 )
    {
      memset_0(v7, 0, 0x58u);
      goto LABEL_7;
    }
  }
  if ( !v5 )
  {
    v6 = -1073741670;
    goto LABEL_12;
  }
LABEL_7:
  *(_DWORD *)(v5 + 8) = 1;
  *(_QWORD *)v5 = 0x5353455355554B50LL;
  *(struct _LUID *)(v5 + 12) = *a1;
  *(_QWORD *)(v5 + 32) = v5 + 24;
  *(_QWORD *)(v5 + 24) = v5 + 24;
  v6 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v5 + 40));
  if ( v6 < 0 )
  {
    Pku2uFreeLogonSession((struct _PKU2U_LOGON_SESSION *)v5);
  }
  else
  {
    v10 = (struct _PKU2U_LOGON_SESSION *)v5;
    v6 = Pku2uLogonSessionTableInsertOrLocate(&v10);
    if ( v6 >= 0 )
    {
      v8 = v10;
      *((_QWORD *)v8 + 10) = LsaIRegisterNotification(Pku2uScavengerCleanupStaleCreds, v10, 1, 0, 0, 36000, 0);
      *a2 = v8;
      return (unsigned int)v6;
    }
    v4 = v10;
  }
LABEL_12:
  if ( v4 )
    Pku2uDereferenceLogonSession(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016cdc  mov     [rsp+arg_0], rbx
0x180016ce1  mov     [rsp+arg_8], rbp
0x180016ce6  push    rsi
0x180016ce7  push    rdi
0x180016ce8  push    r14
0x180016cea  sub     rsp, 40h
0x180016cee  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x180016cf5  mov     r14, rdx
0x180016cf8  mov     rdi, rcx
0x180016cfb  xor     esi, esi
0x180016cfd  cmp     dword ptr [rax+0D0h], 1
0x180016d04  jnz     short loc_180016D2E
0x180016d06  mov     rax, [rax+0F0h]
0x180016d0d  lea     ecx, [rsi+58h]
0x180016d10  mov     rax, [rax+180h]
0x180016d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d1c  mov     rbx, rax
0x180016d1f  test    rbx, rbx
0x180016d22  jnz     short loc_180016D58
0x180016d24  mov     edi, 0C000009Ah
0x180016d29  jmp     loc_180016DEB
0x180016d2e  mov     rax, [rax+0F8h]
0x180016d35  mov     ecx, 58h ; 'X'
0x180016d3a  mov     rax, [rax]
0x180016d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d42  mov     rbx, rax
0x180016d45  test    rax, rax
0x180016d48  jz      short loc_180016D1F
0x180016d4a  xor     edx, edx; Val
0x180016d4c  mov     rcx, rax; void *
0x180016d4f  lea     r8d, [rdx+58h]; Size
0x180016d53  call    memset_0
0x180016d58  mov     dword ptr [rbx+8], 1
0x180016d5f  lea     rcx, [rbx+28h]; CriticalSection
0x180016d63  mov     rax, 5353455355554B50h
0x180016d6d  mov     rbp, rbx
0x180016d70  mov     [rbx], rax
0x180016d73  mov     rax, [rdi]
0x180016d76  mov     [rbx+0Ch], rax
0x180016d7a  lea     rax, [rbx+18h]
0x180016d7e  mov     [rax+8], rax
0x180016d82  mov     [rax], rax
0x180016d85  call    cs:__imp_RtlInitializeCriticalSection
0x180016d8b  mov     edi, eax
0x180016d8d  test    eax, eax
0x180016d8f  js      short loc_180016DE3
0x180016d91  lea     rcx, [rsp+58h+arg_10]; struct _PKU2U_LOGON_SESSION **
0x180016d96  mov     [rsp+58h+arg_10], rbx
0x180016d9b  call    ?Pku2uLogonSessionTableInsertOrLocate@@YAJPEAPEAU_PKU2U_LOGON_SESSION@@@Z; Pku2uLogonSessionTableInsertOrLocate(_PKU2U_LOGON_SESSION * *)
0x180016da0  mov     edi, eax
0x180016da2  test    eax, eax
0x180016da4  js      short loc_180016DDC
0x180016da6  mov     rbx, [rsp+58h+arg_10]
0x180016dab  lea     rcx, ?Pku2uScavengerCleanupStaleCreds@@YAKPEAX@Z; Pku2uScavengerCleanupStaleCreds(void *)
0x180016db2  xor     r9d, r9d
0x180016db5  mov     [rsp+58h+var_28], rsi
0x180016dba  mov     [rsp+58h+var_30], 8CA0h
0x180016dc2  mov     rdx, rbx
0x180016dc5  mov     [rsp+58h+var_38], esi
0x180016dc9  lea     r8d, [r9+1]
0x180016dcd  call    cs:__imp_LsaIRegisterNotification
0x180016dd3  mov     [rbx+50h], rax
0x180016dd7  mov     [r14], rbx
0x180016dda  jmp     short loc_180016DF8
0x180016ddc  mov     rsi, [rsp+58h+arg_10]
0x180016de1  jmp     short loc_180016DEB
0x180016de3  mov     rcx, rbp; struct _PKU2U_LOGON_SESSION *
0x180016de6  call    ?Pku2uFreeLogonSession@@YAXPEAU_PKU2U_LOGON_SESSION@@@Z; Pku2uFreeLogonSession(_PKU2U_LOGON_SESSION *)
0x180016deb  test    rsi, rsi
0x180016dee  jz      short loc_180016DF8
0x180016df0  mov     rcx, rsi; struct _PKU2U_LOGON_SESSION *
0x180016df3  call    ?Pku2uDereferenceLogonSession@@YAXPEAU_PKU2U_LOGON_SESSION@@@Z; Pku2uDereferenceLogonSession(_PKU2U_LOGON_SESSION *)
0x180016df8  mov     rbx, [rsp+58h+arg_0]
0x180016dfd  mov     eax, edi
0x180016dff  mov     rbp, [rsp+58h+arg_8]
0x180016e04  add     rsp, 40h
0x180016e08  pop     r14
0x180016e0a  pop     rdi
0x180016e0b  pop     rsi
0x180016e0c  retn
```
