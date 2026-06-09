# CipAllocateLocalValidationContext

- ea: `0x18009a008`
- end: `0x18009a0dc`
- name: `CipAllocateLocalValidationContext`
- size: `212`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180060cc0`
- `0x180074f04`
- `0x180099aa4`
- `0x180099e48`

## callees

- `0x180099118`
- `0x180099154`
- `0x18009a008`
- `0x1800a3eb0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18009a080`
- `ntoskrnl!RtlInitUnicodeString` at `0x18009a080`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009a026`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18009a026`

## pseudocode

```c
__int64 __fastcall CipAllocateLocalValidationContext(
        unsigned int a1,
        __int64 a2,
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
  *(_QWORD *)&v10[190].Length = a2;
  *(_QWORD *)&v10[207].Length = a3;
  v10[189].Buffer = (PWSTR)&off_18002EE80;
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
0x18009a008  push    rbx
0x18009a00a  push    rbp
0x18009a00b  push    rsi
0x18009a00c  push    rdi
0x18009a00d  push    r14
0x18009a00f  sub     rsp, 20h
0x18009a013  mov     r14d, ecx
0x18009a016  mov     rbx, r9
0x18009a019  lea     rcx, g_CiValidationLookasideList; Lookaside
0x18009a020  mov     rbp, r8
0x18009a023  mov     rsi, rdx
0x18009a026  call    cs:__imp_ExAllocateFromPagedLookasideList
0x18009a02d  nop     dword ptr [rax+rax+00h]
0x18009a032  mov     rdi, rax
0x18009a035  test    rax, rax
0x18009a038  jnz     short loc_18009A044
0x18009a03a  mov     eax, 0C0000017h
0x18009a03f  jmp     loc_18009A0D0
0x18009a044  mov     r8, rdi
0x18009a047  mov     rdx, rbx
0x18009a04a  mov     ecx, r14d
0x18009a04d  call    CiInitializeValidationContext
0x18009a052  mov     ebx, eax
0x18009a054  mov     [rdi+0BE0h], rsi
0x18009a05b  mov     [rdi+0CF0h], rbp
0x18009a062  lea     rax, off_18002EE80
0x18009a069  mov     [rdi+0BD8h], rax
0x18009a070  test    ebx, ebx
0x18009a072  js      short loc_18009A0C6
0x18009a074  lea     rsi, [rdi+350h]
0x18009a07b  xor     edx, edx; SourceString
0x18009a07d  mov     rcx, rsi; DestinationString
0x18009a080  call    cs:__imp_RtlInitUnicodeString
0x18009a087  nop     dword ptr [rax+rax+00h]
0x18009a08c  test    rbp, rbp
0x18009a08f  jz      short loc_18009A0BC
0x18009a091  mov     eax, cs:g_CiPolicyState
0x18009a097  test    al, 40h
0x18009a099  jz      short loc_18009A0BC
0x18009a09b  test    al, 2
0x18009a09d  jz      short loc_18009A0BA
0x18009a09f  xor     r9d, r9d
0x18009a0a2  mov     rdx, rsi; StringOut
0x18009a0a5  mov     rcx, rbp; PROCESS
0x18009a0a8  call    CipTryGetProcessAppID
0x18009a0ad  mov     ebx, eax
0x18009a0af  test    eax, eax
0x18009a0b1  jns     short loc_18009A0BC
0x18009a0b3  cmp     eax, 0C0000225h
0x18009a0b8  jnz     short loc_18009A0C6
0x18009a0ba  xor     ebx, ebx
0x18009a0bc  mov     rax, [rsp+48h+arg_20]
0x18009a0c1  mov     [rax], rdi
0x18009a0c4  jmp     short loc_18009A0CE
0x18009a0c6  mov     rcx, rdi; Entry
0x18009a0c9  call    CiFreeValidationContext
0x18009a0ce  mov     eax, ebx
0x18009a0d0  add     rsp, 20h
0x18009a0d4  pop     r14
0x18009a0d6  pop     rdi
0x18009a0d7  pop     rsi
0x18009a0d8  pop     rbp
0x18009a0d9  pop     rbx
0x18009a0da  retn
```
