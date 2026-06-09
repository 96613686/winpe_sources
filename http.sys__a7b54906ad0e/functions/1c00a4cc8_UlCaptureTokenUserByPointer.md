# UlCaptureTokenUserByPointer

- ea: `0x1c00a4cc8`
- end: `0x1c00a4dad`
- name: `UlCaptureTokenUserByPointer`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1c00a4c1c`

## callees

- `0x1c001b900`
- `0x1c00a4cc8`

## import_xrefs

- `ntoskrnl!SeQueryInformationToken` at `0x1c00a4cf7`
- `ntoskrnl!SeQueryInformationToken` at `0x1c00a4cf7`
- `ntoskrnl!RtlCopySid` at `0x1c00a4d4e`
- `ntoskrnl!RtlCopySid` at `0x1c00a4d4e`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00a4d17`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00a4d17`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a4d88`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00dedf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a4d88`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00dedf1`

## pseudocode

```c
__int64 __fastcall UlCaptureTokenUserByPointer(void *a1, POOL_TYPE a2, ULONG a3, _QWORD *a4)
{
  NTSTATUS v7; // edi
  _DWORD *PoolWithTagPriority; // rax
  _DWORD *v9; // rbx
  _DWORD *v10; // rax
  PVOID P; // [rsp+48h] [rbp+20h] BYREF

  P = 0;
  *a4 = 0;
  v7 = SeQueryInformationToken(a1, TokenUser, &P);
  if ( v7 >= 0 )
  {
    PoolWithTagPriority = ExAllocatePoolWithTagPriority(a2, 0x54u, a3, LowPoolPriority);
    v9 = PoolWithTagPriority;
    if ( PoolWithTagPriority )
    {
      memset(PoolWithTagPriority, 0, 0x54u);
      v7 = RtlCopySid(0x44u, v9 + 4, *(PSID *)P);
      if ( v7 >= 0 )
      {
        v10 = P;
        *a4 = v9;
        v9[2] = v10[2];
        *(_QWORD *)v9 = v9 + 4;
        v9 = 0;
      }
      if ( v9 )
        ExFreePoolWithTag(v9, 0);
    }
    else
    {
      v7 = -1073741801;
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1c00a4cc8  mov     rax, rsp
0x1c00a4ccb  mov     [rax+8], rbx
0x1c00a4ccf  mov     [rax+10h], rsi
0x1c00a4cd3  mov     [rax+18h], rdi
0x1c00a4cd7  push    r14
0x1c00a4cd9  sub     rsp, 20h
0x1c00a4cdd  and     qword ptr [rax+20h], 0
0x1c00a4ce2  mov     ebx, r8d
0x1c00a4ce5  and     qword ptr [r9], 0
0x1c00a4ce9  lea     r8, [rax+20h]; TokenInformation
0x1c00a4ced  mov     esi, edx
0x1c00a4cef  mov     r14, r9
0x1c00a4cf2  mov     edx, 1; TokenInformationClass
0x1c00a4cf7  call    cs:__imp_SeQueryInformationToken
0x1c00a4cfe  nop     dword ptr [rax+rax+00h]
0x1c00a4d03  mov     edi, eax
0x1c00a4d05  test    eax, eax
0x1c00a4d07  js      short loc_1C00A4D7C
0x1c00a4d09  xor     r9d, r9d; Priority
0x1c00a4d0c  mov     r8d, ebx; Tag
0x1c00a4d0f  mov     ecx, esi; PoolType
0x1c00a4d11  lea     edi, [r9+54h]
0x1c00a4d15  mov     edx, edi; NumberOfBytes
0x1c00a4d17  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00a4d1e  nop     dword ptr [rax+rax+00h]
0x1c00a4d23  mov     rbx, rax
0x1c00a4d26  test    rax, rax
0x1c00a4d29  jz      loc_1C00DEDE2
0x1c00a4d2f  mov     r8d, edi; Size
0x1c00a4d32  xor     edx, edx; Val
0x1c00a4d34  mov     rcx, rax; void *
0x1c00a4d37  call    memset
0x1c00a4d3c  mov     r8, [rsp+28h+P]
0x1c00a4d41  lea     rsi, [rbx+10h]
0x1c00a4d45  mov     rdx, rsi; DestinationSid
0x1c00a4d48  lea     ecx, [rdi-10h]; DestinationSidLength
0x1c00a4d4b  mov     r8, [r8]; SourceSid
0x1c00a4d4e  call    cs:__imp_RtlCopySid
0x1c00a4d55  nop     dword ptr [rax+rax+00h]
0x1c00a4d5a  mov     edi, eax
0x1c00a4d5c  test    eax, eax
0x1c00a4d5e  js      short loc_1C00A4D73
0x1c00a4d60  mov     rax, [rsp+28h+P]
0x1c00a4d65  mov     [r14], rbx
0x1c00a4d68  mov     ecx, [rax+8]
0x1c00a4d6b  mov     [rbx+8], ecx
0x1c00a4d6e  mov     [rbx], rsi
0x1c00a4d71  xor     ebx, ebx
0x1c00a4d73  test    rbx, rbx
0x1c00a4d76  jnz     loc_1C00DEDEC
0x1c00a4d7c  mov     rcx, [rsp+28h+P]; P
0x1c00a4d81  test    rcx, rcx
0x1c00a4d84  jz      short loc_1C00A4D94
0x1c00a4d86  xor     edx, edx; Tag
0x1c00a4d88  call    cs:__imp_ExFreePoolWithTag
0x1c00a4d8f  nop     dword ptr [rax+rax+00h]
0x1c00a4d94  mov     rbx, [rsp+28h+arg_0]
0x1c00a4d99  mov     eax, edi
0x1c00a4d9b  mov     rdi, [rsp+28h+arg_10]
0x1c00a4da0  mov     rsi, [rsp+28h+arg_8]
0x1c00a4da5  add     rsp, 20h
0x1c00a4da9  pop     r14
0x1c00a4dab  retn
0x1c00dede2  mov     edi, 0C0000017h
0x1c00dede7  jmp     loc_1C00A4D7C
0x1c00dedec  xor     edx, edx; Tag
0x1c00dedee  mov     rcx, rbx; P
0x1c00dedf1  call    cs:__imp_ExFreePoolWithTag
0x1c00dedf8  nop     dword ptr [rax+rax+00h]
0x1c00dedfd  nop
0x1c00dedfe  jmp     loc_1C00A4D7C
```
