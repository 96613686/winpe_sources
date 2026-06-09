# Pku2uFreeLogonSession(_PKU2U_LOGON_SESSION *)

- ea: `0x18002cce4`
- end: `0x18002cd56`
- name: `?Pku2uFreeLogonSession@@YAXPEAU_PKU2U_LOGON_SESSION@@@Z`
- size: `114`
- prototype: `void __fastcall(struct _PKU2U_LOGON_SESSION *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000af80`
- `0x180016cdc`

## callees

- `0x180005770`
- `0x1800057f0`
- `0x18002cce4`
- `0x18002e540`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18002cd31`
- `ntdll!RtlDeleteCriticalSection` at `0x18002cd31`
- `LSASRV!LsaICancelNotification` at `0x18002ccff`
- `LSASRV!LsaICancelNotification` at `0x18002ccff`

## pseudocode

```c
void __fastcall Pku2uFreeLogonSession(struct _PKU2U_LOGON_SESSION *a1)
{
  __int64 i; // rax
  __int64 *v3; // rbx
  unsigned __int8 *v4; // rdx
  unsigned int v5; // r8d

  if ( *((_QWORD *)a1 + 10) )
  {
    LsaICancelNotification();
    *((_QWORD *)a1 + 10) = 0;
  }
  for ( i = *((_QWORD *)a1 + 3);
        (struct _PKU2U_LOGON_SESSION *)i != (struct _PKU2U_LOGON_SESSION *)((char *)a1 + 24);
        i = *v3 )
  {
    v3 = *(__int64 **)(i + 8);
    Pku2uRemoveAssociatedCredential(a1, (struct _PKU2U_ASSOCIATED_CREDENTIAL *)i);
  }
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)a1 + 1);
  basessp::WSTLowerCase(a1, v4, v5);
  Pku2uFree(a1);
}

```

## disassembly

```asm
0x18002cce4  mov     [rsp+arg_0], rbx
0x18002cce9  mov     [rsp+arg_8], rsi
0x18002ccee  push    rdi
0x18002ccef  sub     rsp, 20h
0x18002ccf3  mov     rdi, rcx
0x18002ccf6  mov     rcx, [rcx+50h]
0x18002ccfa  test    rcx, rcx
0x18002ccfd  jz      short loc_18002CD0D
0x18002ccff  call    cs:__imp_LsaICancelNotification
0x18002cd05  mov     qword ptr [rdi+50h], 0
0x18002cd0d  lea     rsi, [rdi+18h]
0x18002cd11  mov     rax, [rsi]
0x18002cd14  jmp     short loc_18002CD28
0x18002cd16  mov     rbx, [rax+8]
0x18002cd1a  mov     rdx, rax; struct _PKU2U_ASSOCIATED_CREDENTIAL *
0x18002cd1d  mov     rcx, rdi; struct _PKU2U_LOGON_SESSION *
0x18002cd20  call    ?Pku2uRemoveAssociatedCredential@@YAXPEAU_PKU2U_LOGON_SESSION@@PEAU_PKU2U_ASSOCIATED_CREDENTIAL@@@Z; Pku2uRemoveAssociatedCredential(_PKU2U_LOGON_SESSION *,_PKU2U_ASSOCIATED_CREDENTIAL *)
0x18002cd25  mov     rax, [rbx]
0x18002cd28  cmp     rax, rsi
0x18002cd2b  jnz     short loc_18002CD16
0x18002cd2d  lea     rcx, [rdi+28h]; CriticalSection
0x18002cd31  call    cs:__imp_RtlDeleteCriticalSection
0x18002cd37  mov     rcx, rdi; this
0x18002cd3a  call    ?WSTLowerCase@basessp@@YAXPEAEK@Z; basessp::WSTLowerCase(uchar *,ulong)
0x18002cd3f  mov     rcx, rdi; void *
0x18002cd42  mov     rbx, [rsp+28h+arg_0]
0x18002cd47  mov     rsi, [rsp+28h+arg_8]
0x18002cd4c  add     rsp, 20h
0x18002cd50  pop     rdi
0x18002cd51  jmp     ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
```
