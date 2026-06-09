# NpWaitForNamedPipe

- ea: `0x14000f610`
- end: `0x14000f8b9`
- name: `NpWaitForNamedPipe`
- size: `681`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000efb0`

## callees

- `0x140001300`
- `0x14000f610`
- `0x140011f60`
- `0x140012730`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14000f89e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000f89e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000f7f0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000f7f0`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f7d2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f857`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f7d2`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f857`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f7b9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000f7b9`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000f789`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000f789`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14000f6e1`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x14000f6e1`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14000f74f`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14000f74f`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000f740`
- `ntoskrnl!PsGetCurrentProcess` at `0x14000f740`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000f728`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14000f728`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14000f837`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14000f837`

## pseudocode

```c
__int64 __fastcall NpWaitForNamedPipe(__int64 a1, __int64 a2)
{
  __int64 v3; // rdx
  __int64 v4; // r13
  int v5; // esi
  __int64 v6; // r12
  unsigned int v7; // edx
  __int64 v8; // rcx
  unsigned int v9; // eax
  PACCESS_TOKEN v10; // rdi
  int v11; // r14d
  int v12; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v17; // r14
  __int64 v18; // r8
  __int64 Prefix; // rbx
  WCHAR *v20; // [rsp+20h] [rbp-38h]
  struct _UNICODE_STRING UnicodeString; // [rsp+28h] [rbp-30h] BYREF
  __int128 v22; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int8 EffectiveOnly; // [rsp+A0h] [rbp+48h] BYREF
  unsigned __int8 CopyOnOpen; // [rsp+A8h] [rbp+50h] BYREF
  int v25; // [rsp+B0h] [rbp+58h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+B8h] [rbp+60h] BYREF

  v3 = *(_QWORD *)(a2 + 184);
  UnicodeString = 0;
  EffectiveOnly = 0;
  CopyOnOpen = 0;
  ImpersonationLevel = SecurityAnonymous;
  v4 = *(_QWORD *)(v3 + 48);
  v22 = 0;
  v25 = 0;
  if ( **(_WORD **)(v4 + 24) != 518 )
    return (unsigned int)-1073741649;
  v5 = 1;
  v6 = *(_QWORD *)(a1 + 64);
  v7 = *(_DWORD *)(v3 + 16);
  if ( (*(_QWORD *)(v4 + 32) & 1) == 0 )
    return (unsigned int)-1073741649;
  if ( v7 < 0x10 )
    return (unsigned int)-1073741811;
  v8 = *(_QWORD *)(a2 + 24);
  v9 = *(_DWORD *)(v8 + 8);
  if ( v9 > 0xFFFD || v9 + 14 > v7 )
    return (unsigned int)-1073741811;
  v10 = 0;
  v11 = 1;
  UnicodeString.Length = *(_WORD *)(v8 + 8);
  v20 = (WCHAR *)(v8 + 14);
  UnicodeString.Buffer = (PWSTR)(v8 + 14);
  if ( *(_BYTE *)(a2 + 64) == 1 )
  {
    v10 = PsReferenceImpersonationToken(KeGetCurrentThread(), &CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
    if ( v10 )
    {
      v11 = 2;
    }
    else
    {
      CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
      v10 = PsReferencePrimaryToken(CurrentProcess);
    }
  }
  v12 = NpTranslateAlias(&UnicodeString, v10, &v25);
  if ( v10 )
  {
    if ( v11 == 1 )
      PsDereferencePrimaryToken(v10);
    else
      PsDereferenceImpersonationToken(v10);
  }
  if ( v12 >= 0 )
  {
    ExAcquirePushLockExclusiveEx(v6 + 192, 0, v13, v14);
    LOBYTE(v18) = 1;
    Prefix = NpFindPrefix(v6, &UnicodeString, v18, &v22);
    if ( Prefix && *(_WORD *)Prefix == 514 && !(_WORD)v22 )
    {
      v17 = Prefix + 128;
      ExAcquirePushLockSharedEx(Prefix + 128, 0);
      if ( (*(_QWORD *)(v4 + 32) & 1) != 0 )
      {
        if ( *(_QWORD *)(Prefix + 312) == Prefix + 312 )
        {
          ExReleasePushLockExclusiveEx(v6 + 192, 0);
          v5 = 0;
          v12 = NpAddWaiter(
                  v6 + 144,
                  *(_QWORD *)(Prefix + 272),
                  a2,
                  (unsigned __int64)&UnicodeString & -(__int64)(UnicodeString.Buffer != v20));
        }
        else
        {
          v12 = 0;
        }
      }
      else
      {
        v12 = -1073741649;
      }
      ExReleasePushLockSharedEx(v17, 0);
      if ( !v5 )
        goto LABEL_11;
    }
    else
    {
      v12 = -1073741772;
    }
    ExReleasePushLockExclusiveEx(v6 + 192, 0);
  }
LABEL_11:
  if ( v25 )
    RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000f610  push    rbp
0x14000f612  push    rbx
0x14000f613  push    rsi
0x14000f614  push    rdi
0x14000f615  push    r12
0x14000f617  push    r13
0x14000f619  push    r14
0x14000f61b  push    r15
0x14000f61d  mov     rbp, rsp
0x14000f620  sub     rsp, 58h
0x14000f624  xor     ebx, ebx
0x14000f626  mov     r15, rdx
0x14000f629  mov     rdx, [rdx+0B8h]
0x14000f630  xorps   xmm0, xmm0
0x14000f633  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x14000f637  mov     [rbp+EffectiveOnly], bl
0x14000f63a  mov     r8d, 206h
0x14000f640  mov     [rbp+CopyOnOpen], bl
0x14000f643  xorps   xmm1, xmm1
0x14000f646  mov     [rbp+ImpersonationLevel], ebx
0x14000f649  mov     r13, [rdx+30h]
0x14000f64d  movups  [rbp+var_20], xmm1
0x14000f651  mov     [rbp+arg_10], ebx
0x14000f654  mov     rax, [r13+18h]
0x14000f658  cmp     [rax], r8w
0x14000f65c  jnz     loc_14000F8AF
0x14000f662  mov     rax, [r13+20h]
0x14000f666  lea     esi, [rbx+1]
0x14000f669  mov     r12, [rcx+40h]
0x14000f66d  mov     edx, [rdx+10h]
0x14000f670  test    sil, al
0x14000f673  jz      loc_14000F8AF
0x14000f679  cmp     edx, 10h
0x14000f67c  jb      loc_14000F822
0x14000f682  mov     rcx, [r15+18h]
0x14000f686  mov     eax, [rcx+8]
0x14000f689  cmp     eax, 0FFFDh
0x14000f68e  ja      loc_14000F822
0x14000f694  add     eax, 0Eh
0x14000f697  cmp     eax, edx
0x14000f699  ja      loc_14000F822
0x14000f69f  mov     edi, ebx
0x14000f6a1  movzx   eax, word ptr [rcx+8]
0x14000f6a5  mov     r14d, esi
0x14000f6a8  mov     [rbp+UnicodeString.Length], ax
0x14000f6ac  lea     rax, [rcx+0Eh]
0x14000f6b0  mov     [rbp+var_38], rax
0x14000f6b4  mov     [rbp+UnicodeString.Buffer], rax
0x14000f6b8  cmp     [r15+40h], sil
0x14000f6bc  jz      short loc_14000F713
0x14000f6be  lea     r8, [rbp+arg_10]
0x14000f6c2  mov     rdx, rdi
0x14000f6c5  lea     rcx, [rbp+UnicodeString]
0x14000f6c9  call    NpTranslateAlias
0x14000f6ce  mov     ebx, eax
0x14000f6d0  test    rdi, rdi
0x14000f6d3  jz      short loc_14000F6ED
0x14000f6d5  mov     rcx, rdi; ImpersonationToken
0x14000f6d8  cmp     r14d, esi
0x14000f6db  jnz     loc_14000F837
0x14000f6e1  call    cs:__imp_PsDereferencePrimaryToken
0x14000f6e8  nop     dword ptr [rax+rax+00h]
0x14000f6ed  test    ebx, ebx
0x14000f6ef  jns     loc_14000F7E3
0x14000f6f5  cmp     [rbp+arg_10], 0
0x14000f6f9  jnz     loc_14000F89A
0x14000f6ff  mov     eax, ebx
0x14000f701  add     rsp, 58h
0x14000f705  pop     r15
0x14000f707  pop     r14
0x14000f709  pop     r13
0x14000f70b  pop     r12
0x14000f70d  pop     rdi
0x14000f70e  pop     rsi
0x14000f70f  pop     rbx
0x14000f710  pop     rbp
0x14000f711  retn
0x14000f713  mov     rcx, gs:188h; Thread
0x14000f71c  lea     r9, [rbp+ImpersonationLevel]; ImpersonationLevel
0x14000f720  lea     r8, [rbp+EffectiveOnly]; EffectiveOnly
0x14000f724  lea     rdx, [rbp+CopyOnOpen]; CopyOnOpen
0x14000f728  call    cs:__imp_PsReferenceImpersonationToken
0x14000f72f  nop     dword ptr [rax+rax+00h]
0x14000f734  mov     rdi, rax
0x14000f737  test    rax, rax
0x14000f73a  jnz     loc_14000F82C
0x14000f740  call    cs:__imp_PsGetCurrentProcess
0x14000f747  nop     dword ptr [rax+rax+00h]
0x14000f74c  mov     rcx, rax; Process
0x14000f74f  call    cs:__imp_PsReferencePrimaryToken
0x14000f756  nop     dword ptr [rax+rax+00h]
0x14000f75b  mov     rdi, rax
0x14000f75e  jmp     loc_14000F6BE
0x14000f763  mov     eax, 202h
0x14000f768  cmp     [rbx], ax
0x14000f76b  jnz     loc_14000F81B
0x14000f771  xor     ecx, ecx
0x14000f773  cmp     cx, word ptr [rbp+var_20]
0x14000f777  jnz     loc_14000F81B
0x14000f77d  lea     r14, [rbx+80h]
0x14000f784  xor     edx, edx
0x14000f786  mov     rcx, r14
0x14000f789  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000f790  nop     dword ptr [rax+rax+00h]
0x14000f795  mov     rax, [r13+20h]
0x14000f799  test    sil, al
0x14000f79c  jz      loc_14000F848
0x14000f7a2  lea     rax, [rbx+138h]
0x14000f7a9  cmp     [rax], rax
0x14000f7ac  jz      loc_14000F852
0x14000f7b2  xor     ebx, ebx
0x14000f7b4  xor     edx, edx
0x14000f7b6  mov     rcx, r14
0x14000f7b9  call    cs:__imp_ExReleasePushLockSharedEx
0x14000f7c0  nop     dword ptr [rax+rax+00h]
0x14000f7c5  test    esi, esi
0x14000f7c7  jz      loc_14000F6F5
0x14000f7cd  xor     edx, edx
0x14000f7cf  mov     rcx, rdi
0x14000f7d2  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000f7d9  nop     dword ptr [rax+rax+00h]
0x14000f7de  jmp     loc_14000F6F5
0x14000f7e3  lea     rdi, [r12+0C0h]
0x14000f7eb  xor     edx, edx
0x14000f7ed  mov     rcx, rdi
0x14000f7f0  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000f7f7  nop     dword ptr [rax+rax+00h]
0x14000f7fc  lea     r9, [rbp+var_20]
0x14000f800  mov     r8b, sil
0x14000f803  lea     rdx, [rbp+UnicodeString]
0x14000f807  mov     rcx, r12
0x14000f80a  call    NpFindPrefix
0x14000f80f  mov     rbx, rax
0x14000f812  test    rax, rax
0x14000f815  jnz     loc_14000F763
0x14000f81b  mov     ebx, 0C0000034h
0x14000f820  jmp     short loc_14000F7CD
0x14000f822  mov     ebx, 0C000000Dh
0x14000f827  jmp     loc_14000F6FF
0x14000f82c  mov     r14d, 2
0x14000f832  jmp     loc_14000F6BE
0x14000f837  call    cs:__imp_PsDereferenceImpersonationToken
0x14000f83e  nop     dword ptr [rax+rax+00h]
0x14000f843  jmp     loc_14000F6ED
0x14000f848  mov     ebx, 0C00000AFh
0x14000f84d  jmp     loc_14000F7B4
0x14000f852  xor     edx, edx
0x14000f854  mov     rcx, rdi
0x14000f857  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000f85e  nop     dword ptr [rax+rax+00h]
0x14000f863  mov     rax, [rbp+var_38]
0x14000f867  lea     rcx, [r12+90h]
0x14000f86f  mov     rdx, [rbx+110h]
0x14000f876  xor     esi, esi
0x14000f878  cmp     [rbp+UnicodeString.Buffer], rax
0x14000f87c  mov     r8, r15
0x14000f87f  setnz   al
0x14000f882  neg     al
0x14000f884  lea     rax, [rbp+UnicodeString]
0x14000f888  sbb     r9, r9
0x14000f88b  and     r9, rax
0x14000f88e  call    NpAddWaiter
0x14000f893  mov     ebx, eax
0x14000f895  jmp     loc_14000F7B4
0x14000f89a  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x14000f89e  call    cs:__imp_RtlFreeUnicodeString
0x14000f8a5  nop     dword ptr [rax+rax+00h]
0x14000f8aa  jmp     loc_14000F6FF
0x14000f8af  mov     ebx, 0C00000AFh
0x14000f8b4  jmp     loc_14000F6FF
```
