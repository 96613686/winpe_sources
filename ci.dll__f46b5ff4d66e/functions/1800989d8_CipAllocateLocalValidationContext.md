# CipAllocateLocalValidationContext

- ea: `0x1800989d8`
- end: `0x180098aac`
- name: `CipAllocateLocalValidationContext`
- size: `212`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18006050c`
- `0x180073c54`
- `0x180098474`
- `0x180098818`

## callees

- `0x180097ae8`
- `0x180097b24`
- `0x1800989d8`
- `0x1800a2880`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180098a50`
- `ntoskrnl!RtlInitUnicodeString` at `0x180098a50`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1800989f6`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1800989f6`

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
0x1800989d8  push    rbx
0x1800989da  push    rbp
0x1800989db  push    rsi
0x1800989dc  push    rdi
0x1800989dd  push    r14
0x1800989df  sub     rsp, 20h
0x1800989e3  mov     r14d, ecx
0x1800989e6  mov     rbx, r9
0x1800989e9  lea     rcx, g_CiValidationLookasideList; Lookaside
0x1800989f0  mov     rbp, r8
0x1800989f3  mov     rsi, rdx
0x1800989f6  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1800989fd  nop     dword ptr [rax+rax+00h]
0x180098a02  mov     rdi, rax
0x180098a05  test    rax, rax
0x180098a08  jnz     short loc_180098A14
0x180098a0a  mov     eax, 0C0000017h
0x180098a0f  jmp     loc_180098AA0
0x180098a14  mov     r8, rdi
0x180098a17  mov     rdx, rbx
0x180098a1a  mov     ecx, r14d
0x180098a1d  call    CiInitializeValidationContext
0x180098a22  mov     ebx, eax
0x180098a24  mov     [rdi+0BE0h], rsi
0x180098a2b  mov     [rdi+0CF0h], rbp
0x180098a32  lea     rax, off_18002EE80
0x180098a39  mov     [rdi+0BD8h], rax
0x180098a40  test    ebx, ebx
0x180098a42  js      short loc_180098A96
0x180098a44  lea     rsi, [rdi+350h]
0x180098a4b  xor     edx, edx; SourceString
0x180098a4d  mov     rcx, rsi; DestinationString
0x180098a50  call    cs:__imp_RtlInitUnicodeString
0x180098a57  nop     dword ptr [rax+rax+00h]
0x180098a5c  test    rbp, rbp
0x180098a5f  jz      short loc_180098A8C
0x180098a61  mov     eax, cs:g_CiPolicyState
0x180098a67  test    al, 40h
0x180098a69  jz      short loc_180098A8C
0x180098a6b  test    al, 2
0x180098a6d  jz      short loc_180098A8A
0x180098a6f  xor     r9d, r9d
0x180098a72  mov     rdx, rsi; StringOut
0x180098a75  mov     rcx, rbp; PROCESS
0x180098a78  call    CipTryGetProcessAppID
0x180098a7d  mov     ebx, eax
0x180098a7f  test    eax, eax
0x180098a81  jns     short loc_180098A8C
0x180098a83  cmp     eax, 0C0000225h
0x180098a88  jnz     short loc_180098A96
0x180098a8a  xor     ebx, ebx
0x180098a8c  mov     rax, [rsp+48h+arg_20]
0x180098a91  mov     [rax], rdi
0x180098a94  jmp     short loc_180098A9E
0x180098a96  mov     rcx, rdi; Entry
0x180098a99  call    CiFreeValidationContext
0x180098a9e  mov     eax, ebx
0x180098aa0  add     rsp, 20h
0x180098aa4  pop     r14
0x180098aa6  pop     rdi
0x180098aa7  pop     rsi
0x180098aa8  pop     rbp
0x180098aa9  pop     rbx
0x180098aaa  retn
```
