# UlpCleanupLoggingConfig

- ea: `0x1c00338b4`
- end: `0x1c0033a38`
- name: `UlpCleanupLoggingConfig`
- size: `388`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1c0032530`
- `0x1c00325a8`

## callees

- `0x1c0016fcc`
- `0x1c00338b4`
- `0x1c0033ed0`
- `0x1c008f680`
- `0x1c011f6cc`

## import_xrefs

- `ntoskrnl!SeTokenType` at `0x1c0033985`
- `ntoskrnl!SeTokenType` at `0x1c0033985`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1c00339a1`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x1c00339a1`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1c00339af`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x1c00339af`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c0033969`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c0033969`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0033933`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c003394f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00339c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00339f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0033933`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c003394f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00339c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00339f4`

## pseudocode

```c
void __fastcall UlpCleanupLoggingConfig(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  char *v5; // rbx
  _QWORD *v6; // rax
  __int64 v7; // rdx
  _QWORD *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  TOKEN_TYPE v13; // eax
  void *v14; // rcx
  struct _SLIST_ENTRY *v15; // rcx

  UlpCleanupLoggingInfo((void *)(a2 + 8));
  v5 = *(char **)(a2 + 120);
  *(_QWORD *)(a2 + 120) = 0;
  if ( v5 )
  {
    v6 = v5 + 64;
    v7 = *((_QWORD *)v5 + 8);
    if ( *(char **)(v7 + 8) != v5 + 64 || (v8 = (_QWORD *)*((_QWORD *)v5 + 9), (_QWORD *)*v8 != v6) )
      __fastfail(3u);
    *v8 = v7;
    *(_QWORD *)(v7 + 8) = v8;
    *((_QWORD *)v5 + 9) = 0;
    *v6 = 0;
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 3028));
    if ( *((_QWORD *)v5 + 7) )
      UlpDisableLogFileEntry(v5);
    v9 = (void *)*((_QWORD *)v5 + 5);
    if ( v9 )
    {
      ExFreePoolWithTag(v9, 0);
      *((_QWORD *)v5 + 5) = 0;
    }
    v10 = (void *)*((_QWORD *)v5 + 2);
    if ( v10 )
      ExFreePoolWithTag(v10, 0);
    v11 = *((_QWORD *)v5 + 15);
    if ( v11 )
    {
      LOBYTE(v4) = 1;
      SeReleaseSecurityDescriptor(v11, 0, v4);
    }
    v12 = *((_QWORD *)v5 + 17);
    if ( v12 )
    {
      v13 = SeTokenType(*(PACCESS_TOKEN *)(v12 + 16));
      v14 = *(void **)(*((_QWORD *)v5 + 17) + 16LL);
      if ( v13 == TokenPrimary )
        PsDereferencePrimaryToken(v14);
      else
        PsDereferenceImpersonationToken(v14);
      ExFreePoolWithTag(*((PVOID *)v5 + 17), 0);
      *((_QWORD *)v5 + 17) = 0;
    }
    v15 = (struct _SLIST_ENTRY *)*((_QWORD *)v5 + 20);
    if ( v15 )
      UlFreeLogFileBuffer(v15);
    *(_DWORD *)v5 = 1718373493;
    ExFreePoolWithTag(v5, 0);
  }
  if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x400) != 0 )
    WPP_SF_q(48, WPP_07d3f8078d093d4b6da456c67947dc87_Traceguids, a2);
}

```

## disassembly

```asm
0x1c00338b4  mov     [rsp+arg_0], rbx
0x1c00338b9  mov     [rsp+arg_8], rsi
0x1c00338be  push    rdi
0x1c00338bf  sub     rsp, 20h
0x1c00338c3  mov     rsi, rcx
0x1c00338c6  mov     rdi, rdx
0x1c00338c9  lea     rcx, [rdx+8]; void *
0x1c00338cd  call    UlpCleanupLoggingInfo
0x1c00338d2  mov     rbx, [rdi+78h]
0x1c00338d6  and     qword ptr [rdi+78h], 0
0x1c00338db  test    rbx, rbx
0x1c00338de  jz      loc_1C0033A00
0x1c00338e4  lea     rax, [rbx+40h]
0x1c00338e8  mov     rdx, [rax]
0x1c00338eb  cmp     [rdx+8], rax
0x1c00338ef  jnz     loc_1C0033A31
0x1c00338f5  mov     rcx, [rax+8]
0x1c00338f9  cmp     [rcx], rax
0x1c00338fc  jnz     loc_1C0033A31
0x1c0033902  mov     [rcx], rdx
0x1c0033905  mov     [rdx+8], rcx
0x1c0033909  and     qword ptr [rbx+48h], 0
0x1c003390e  and     qword ptr [rax], 0
0x1c0033912  lock dec dword ptr [rsi+0BD4h]
0x1c0033919  cmp     qword ptr [rbx+38h], 0
0x1c003391e  jz      short loc_1C0033928
0x1c0033920  mov     rcx, rbx
0x1c0033923  call    UlpDisableLogFileEntry
0x1c0033928  mov     rcx, [rbx+28h]; P
0x1c003392c  test    rcx, rcx
0x1c003392f  jz      short loc_1C0033944
0x1c0033931  xor     edx, edx; Tag
0x1c0033933  call    cs:__imp_ExFreePoolWithTag
0x1c003393a  nop     dword ptr [rax+rax+00h]
0x1c003393f  and     qword ptr [rbx+28h], 0
0x1c0033944  mov     rcx, [rbx+10h]; P
0x1c0033948  test    rcx, rcx
0x1c003394b  jz      short loc_1C003395B
0x1c003394d  xor     edx, edx; Tag
0x1c003394f  call    cs:__imp_ExFreePoolWithTag
0x1c0033956  nop     dword ptr [rax+rax+00h]
0x1c003395b  mov     rcx, [rbx+78h]
0x1c003395f  test    rcx, rcx
0x1c0033962  jz      short loc_1C0033975
0x1c0033964  mov     r8b, 1
0x1c0033967  xor     edx, edx
0x1c0033969  call    cs:__imp_SeReleaseSecurityDescriptor
0x1c0033970  nop     dword ptr [rax+rax+00h]
0x1c0033975  mov     rcx, [rbx+88h]
0x1c003397c  test    rcx, rcx
0x1c003397f  jz      short loc_1C00339D8
0x1c0033981  mov     rcx, [rcx+10h]; Token
0x1c0033985  call    cs:__imp_SeTokenType
0x1c003398c  nop     dword ptr [rax+rax+00h]
0x1c0033991  mov     rcx, [rbx+88h]
0x1c0033998  mov     rcx, [rcx+10h]; ImpersonationToken
0x1c003399c  cmp     eax, 1
0x1c003399f  jnz     short loc_1C00339AF
0x1c00339a1  call    cs:__imp_PsDereferencePrimaryToken
0x1c00339a8  nop     dword ptr [rax+rax+00h]
0x1c00339ad  jmp     short loc_1C00339BB
0x1c00339af  call    cs:__imp_PsDereferenceImpersonationToken
0x1c00339b6  nop     dword ptr [rax+rax+00h]
0x1c00339bb  mov     rcx, [rbx+88h]; P
0x1c00339c2  xor     edx, edx; Tag
0x1c00339c4  call    cs:__imp_ExFreePoolWithTag
0x1c00339cb  nop     dword ptr [rax+rax+00h]
0x1c00339d0  and     qword ptr [rbx+88h], 0
0x1c00339d8  mov     rcx, [rbx+0A0h]; ListEntry
0x1c00339df  test    rcx, rcx
0x1c00339e2  jz      short loc_1C00339E9
0x1c00339e4  call    UlFreeLogFileBuffer
0x1c00339e9  xor     edx, edx; Tag
0x1c00339eb  mov     dword ptr [rbx], 666C4C75h
0x1c00339f1  mov     rcx, rbx; P
0x1c00339f4  call    cs:__imp_ExFreePoolWithTag
0x1c00339fb  nop     dword ptr [rax+rax+00h]
0x1c0033a00  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 400h
0x1c0033a0a  jz      short loc_1C0033A20
0x1c0033a0c  mov     ecx, 30h ; '0'
0x1c0033a11  lea     rdx, WPP_07d3f8078d093d4b6da456c67947dc87_Traceguids
0x1c0033a18  mov     r8, rdi
0x1c0033a1b  call    WPP_SF_q
0x1c0033a20  mov     rbx, [rsp+28h+arg_0]
0x1c0033a25  mov     rsi, [rsp+28h+arg_8]
0x1c0033a2a  add     rsp, 20h
0x1c0033a2e  pop     rdi
0x1c0033a2f  retn
0x1c0033a31  mov     ecx, 3
0x1c0033a36  int     29h; Win8: RtlFailFast(ecx)
```
