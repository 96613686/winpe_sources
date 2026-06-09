# CClfsContainer::SetDefaultSaclSecurityDescriptor(void * &,ulong &)

- ea: `0x14003f09c`
- end: `0x14003f1a9`
- name: `?SetDefaultSaclSecurityDescriptor@CClfsContainer@@CAJAEAPEAXAEAK@Z`
- size: `269`
- prototype: `__int64 __fastcall(void **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003be98`

## callees

- `0x140017f80`
- `0x14003f09c`

## import_xrefs

- `ntoskrnl!RtlSelfRelativeToAbsoluteSD2` at `0x14003f0dc`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD2` at `0x14003f131`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD2` at `0x14003f0dc`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD2` at `0x14003f131`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x14003f185`
- `ntoskrnl!RtlSetSaclSecurityDescriptor` at `0x14003f185`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f148`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f15b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f148`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003f15b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f100`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003f100`

## pseudocode

```c
int __fastcall CClfsContainer::SetDefaultSaclSecurityDescriptor(void **a1, unsigned int *a2)
{
  _WORD *v2; // rbx
  __int16 v5; // ax
  void *v6; // rcx
  int result; // eax
  PVOID PoolWithTag; // rax
  void *v9; // rdi
  NTSTATUS v10; // ebx
  ULONG v11; // eax
  ULONG BufferSize; // [rsp+40h] [rbp+8h] BYREF

  v2 = *a1;
  v5 = *((_WORD *)*a1 + 1);
  if ( (v5 & 0x10) == 0 )
    return 0;
  if ( v5 < 0 )
  {
    v6 = *a1;
    BufferSize = *a2;
    result = RtlSelfRelativeToAbsoluteSD2(v6, &BufferSize);
    if ( result == -1073741789 )
    {
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, BufferSize, 0x73666C43u);
      v9 = PoolWithTag;
      if ( !PoolWithTag )
        return -1073741670;
      memmove(PoolWithTag, v2, *a2);
      v10 = RtlSelfRelativeToAbsoluteSD2(v9, &BufferSize);
      if ( v10 < 0 )
      {
        ExFreePoolWithTag(v9, 0);
        return v10;
      }
      ExFreePoolWithTag(*a1, 0);
      v11 = BufferSize;
      *a1 = v9;
      *a2 = v11;
      v2 = *a1;
    }
    else if ( result < 0 )
    {
      return result;
    }
  }
  return RtlSetSaclSecurityDescriptor(v2, 0, 0, 0);
}

```

## disassembly

```asm
0x14003f09c  mov     [rsp+arg_8], rbx
0x14003f0a1  mov     [rsp+arg_10], rbp
0x14003f0a6  push    rsi
0x14003f0a7  push    rdi
0x14003f0a8  push    r14
0x14003f0aa  sub     rsp, 20h
0x14003f0ae  mov     rbx, [rcx]
0x14003f0b1  mov     r14, rdx
0x14003f0b4  mov     rsi, rcx
0x14003f0b7  movzx   eax, word ptr [rbx+2]
0x14003f0bb  test    al, 10h
0x14003f0bd  jz      loc_14003F193
0x14003f0c3  xor     ebp, ebp
0x14003f0c5  test    ax, ax
0x14003f0c8  jns     loc_14003F17A
0x14003f0ce  mov     eax, [rdx]
0x14003f0d0  mov     rcx, rbx; SelfRelativeSD
0x14003f0d3  lea     rdx, [rsp+38h+BufferSize]; BufferSize
0x14003f0d8  mov     [rsp+38h+BufferSize], eax
0x14003f0dc  call    cs:__imp_RtlSelfRelativeToAbsoluteSD2
0x14003f0e3  nop     dword ptr [rax+rax+00h]
0x14003f0e8  cmp     eax, 0C0000023h
0x14003f0ed  jnz     loc_14003F176
0x14003f0f3  mov     edx, [rsp+38h+BufferSize]; NumberOfBytes
0x14003f0f7  lea     ecx, [rbp+1]; PoolType
0x14003f0fa  mov     r8d, 73666C43h; Tag
0x14003f100  call    cs:__imp_ExAllocatePoolWithTag
0x14003f107  nop     dword ptr [rax+rax+00h]
0x14003f10c  mov     rdi, rax
0x14003f10f  test    rax, rax
0x14003f112  jnz     short loc_14003F11B
0x14003f114  mov     eax, 0C000009Ah
0x14003f119  jmp     short loc_14003F195
0x14003f11b  mov     r8d, [r14]; Size
0x14003f11e  mov     rdx, rbx; Src
0x14003f121  mov     rcx, rdi; void *
0x14003f124  call    memmove
0x14003f129  lea     rdx, [rsp+38h+BufferSize]; BufferSize
0x14003f12e  mov     rcx, rdi; SelfRelativeSD
0x14003f131  call    cs:__imp_RtlSelfRelativeToAbsoluteSD2
0x14003f138  nop     dword ptr [rax+rax+00h]
0x14003f13d  xor     edx, edx; Tag
0x14003f13f  mov     ebx, eax
0x14003f141  test    eax, eax
0x14003f143  jns     short loc_14003F158
0x14003f145  mov     rcx, rdi; P
0x14003f148  call    cs:__imp_ExFreePoolWithTag
0x14003f14f  nop     dword ptr [rax+rax+00h]
0x14003f154  mov     eax, ebx
0x14003f156  jmp     short loc_14003F195
0x14003f158  mov     rcx, [rsi]; P
0x14003f15b  call    cs:__imp_ExFreePoolWithTag
0x14003f162  nop     dword ptr [rax+rax+00h]
0x14003f167  mov     eax, [rsp+38h+BufferSize]
0x14003f16b  mov     [rsi], rdi
0x14003f16e  mov     [r14], eax
0x14003f171  mov     rbx, [rsi]
0x14003f174  jmp     short loc_14003F17A
0x14003f176  test    eax, eax
0x14003f178  js      short loc_14003F195
0x14003f17a  xor     r9d, r9d; SaclDefaulted
0x14003f17d  xor     r8d, r8d; Sacl
0x14003f180  xor     edx, edx; SaclPresent
0x14003f182  mov     rcx, rbx; SecurityDescriptor
0x14003f185  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x14003f18c  nop     dword ptr [rax+rax+00h]
0x14003f191  jmp     short loc_14003F195
0x14003f193  xor     eax, eax
0x14003f195  mov     rbx, [rsp+38h+arg_8]
0x14003f19a  mov     rbp, [rsp+38h+arg_10]
0x14003f19f  add     rsp, 20h
0x14003f1a3  pop     r14
0x14003f1a5  pop     rdi
0x14003f1a6  pop     rsi
0x14003f1a7  retn
```
