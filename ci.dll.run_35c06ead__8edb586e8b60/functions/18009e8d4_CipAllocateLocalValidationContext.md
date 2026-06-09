# CipAllocateLocalValidationContext

- ea: `0x18009e8d4`
- end: `0x18009e9a8`
- name: `CipAllocateLocalValidationContext`
- size: `212`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180060c60`
- `0x1800751e4`
- `0x18009e9b0`
- `0x18009f338`

## callees

- `0x18009df48`
- `0x18009df84`
- `0x18009e8d4`
- `0x1800a4350`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18009e94c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18009e94c`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009e8f2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009e8f2`

## pseudocode

```c
__int64 __fastcall CipAllocateLocalValidationContext(
        unsigned int a1,
        WCHAR *a2,
        struct _KPROCESS *a3,
        __int64 a4,
        struct _UNICODE_STRING **a5)
{
  struct _UNICODE_STRING *v9; // rax
  struct _UNICODE_STRING *v10; // rdi
  int v12; // ebx
  __int64 v13; // r8
  int ProcessAppID; // eax

  v9 = (struct _UNICODE_STRING *)ExAllocateFromPagedLookasideList(&g_CiValidationLookasideList);
  v10 = v9;
  if ( !v9 )
    return 3221225495LL;
  v12 = CiInitializeValidationContext(a1, a4, v9);
  v10[190].Buffer = a2;
  *(_QWORD *)&v10[208].Length = a3;
  *(_QWORD *)&v10[190].Length = &off_18002EEF0;
  if ( v12 < 0 )
    goto LABEL_11;
  RtlInitUnicodeString(v10 + 53, 0);
  if ( !a3 || (g_CiPolicyState & 0x40) == 0 )
    goto LABEL_10;
  if ( (g_CiPolicyState & 2) == 0 )
    goto LABEL_9;
  ProcessAppID = CipTryGetProcessAppID(a3, v10 + 53, v13, 0);
  v12 = ProcessAppID;
  if ( ProcessAppID < 0 )
  {
    if ( ProcessAppID == -1073741275 )
    {
LABEL_9:
      v12 = 0;
      goto LABEL_10;
    }
LABEL_11:
    CiFreeValidationContext((void (***)(void))v10);
    return (unsigned int)v12;
  }
LABEL_10:
  *a5 = v10;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18009e8d4  push    rbx
0x18009e8d6  push    rbp
0x18009e8d7  push    rsi
0x18009e8d8  push    rdi
0x18009e8d9  push    r14
0x18009e8db  sub     rsp, 20h
0x18009e8df  mov     r14d, ecx
0x18009e8e2  mov     rbx, r9
0x18009e8e5  lea     rcx, g_CiValidationLookasideList; Lookaside
0x18009e8ec  mov     rbp, r8
0x18009e8ef  mov     rsi, rdx
0x18009e8f2  call    cs:__imp_ExAllocateFromPagedLookasideList
0x18009e8f9  nop     dword ptr [rax+rax+00h]
0x18009e8fe  mov     rdi, rax
0x18009e901  test    rax, rax
0x18009e904  jnz     short loc_18009E910
0x18009e906  mov     eax, 0C0000017h
0x18009e90b  jmp     loc_18009E99C
0x18009e910  mov     r8, rdi
0x18009e913  mov     rdx, rbx
0x18009e916  mov     ecx, r14d
0x18009e919  call    CiInitializeValidationContext
0x18009e91e  mov     ebx, eax
0x18009e920  mov     [rdi+0BE8h], rsi
0x18009e927  mov     [rdi+0D00h], rbp
0x18009e92e  lea     rax, off_18002EEF0
0x18009e935  mov     [rdi+0BE0h], rax
0x18009e93c  test    ebx, ebx
0x18009e93e  js      short loc_18009E992
0x18009e940  lea     rsi, [rdi+350h]
0x18009e947  xor     edx, edx; SourceString
0x18009e949  mov     rcx, rsi; DestinationString
0x18009e94c  call    cs:__imp_RtlInitUnicodeString
0x18009e953  nop     dword ptr [rax+rax+00h]
0x18009e958  test    rbp, rbp
0x18009e95b  jz      short loc_18009E988
0x18009e95d  mov     eax, cs:g_CiPolicyState
0x18009e963  test    al, 40h
0x18009e965  jz      short loc_18009E988
0x18009e967  test    al, 2
0x18009e969  jz      short loc_18009E986
0x18009e96b  xor     r9d, r9d
0x18009e96e  mov     rdx, rsi; StringOut
0x18009e971  mov     rcx, rbp; PROCESS
0x18009e974  call    CipTryGetProcessAppID
0x18009e979  mov     ebx, eax
0x18009e97b  test    eax, eax
0x18009e97d  jns     short loc_18009E988
0x18009e97f  cmp     eax, 0C0000225h
0x18009e984  jnz     short loc_18009E992
0x18009e986  xor     ebx, ebx
0x18009e988  mov     rax, [rsp+48h+arg_20]
0x18009e98d  mov     [rax], rdi
0x18009e990  jmp     short loc_18009E99A
0x18009e992  mov     rcx, rdi; Entry
0x18009e995  call    CiFreeValidationContext
0x18009e99a  mov     eax, ebx
0x18009e99c  add     rsp, 20h
0x18009e9a0  pop     r14
0x18009e9a2  pop     rdi
0x18009e9a3  pop     rsi
0x18009e9a4  pop     rbp
0x18009e9a5  pop     rbx
0x18009e9a6  retn
```
