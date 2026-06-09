# KsLoadResource

- ea: `0x180039460`
- end: `0x18003959a`
- name: `KsLoadResource`
- size: `314`
- prototype: `NTSTATUS __stdcall(PVOID ImageBase, POOL_TYPE PoolType, ULONG_PTR ResourceName, ULONG ResourceType, PVOID *Resource, PULONG ResourceSize)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019b80`
- `0x180019cc0`
- `0x180039460`

## import_xrefs

- `ntoskrnl!LdrFindResource_U` at `0x1800394e1`
- `ntoskrnl!LdrFindResource_U` at `0x1800394e1`
- `ntoskrnl!LdrAccessResource` at `0x180039521`
- `ntoskrnl!LdrAccessResource` at `0x180039521`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180039540`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180039540`

## pseudocode

```c
NTSTATUS __stdcall KsLoadResource(
        PVOID ImageBase,
        POOL_TYPE PoolType,
        ULONG_PTR ResourceName,
        ULONG ResourceType,
        PVOID *Resource,
        PULONG ResourceSize)
{
  void *v6; // rdi
  NTSTATUS result; // eax
  PVOID PoolWithTag; // rax
  ULONG Size[2]; // [rsp+20h] [rbp-58h] BYREF
  PIMAGE_RESOURCE_DATA_ENTRY ResourceDataEntry; // [rsp+28h] [rbp-50h] BYREF
  PVOID Src[4]; // [rsp+30h] [rbp-48h] BYREF
  struct _LDR_RESOURCE_INFO v12; // [rsp+50h] [rbp-28h] BYREF

  Src[1] = Resource;
  Src[2] = ResourceSize;
  ResourceDataEntry = 0;
  Src[0] = 0;
  Size[0] = 0;
  v12.Type = ResourceType;
  v12.Name = ResourceName;
  v12.Language = 0;
  v6 = (void *)((unsigned __int64)ImageBase | 1);
  Src[3] = (PVOID)((unsigned __int64)ImageBase | 1);
  result = LdrFindResource_U((PVOID)((unsigned __int64)ImageBase | 1), &v12, 3u, &ResourceDataEntry);
  Size[1] = result;
  if ( result >= 0 )
  {
    result = LdrAccessResource(v6, ResourceDataEntry, Src, Size);
    if ( result >= 0 )
    {
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, Size[0], 0x7372534Bu);
      *Resource = PoolWithTag;
      if ( PoolWithTag )
      {
        memmove(PoolWithTag, Src[0], Size[0]);
        if ( ResourceSize )
          *ResourceSize = Size[0];
        return 0;
      }
      else
      {
        return -1073741670;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180039460  mov     r11, rsp
0x180039463  mov     [r11+10h], rbx
0x180039467  mov     [r11+18h], rsi
0x18003946b  push    rdi
0x18003946c  sub     rsp, 70h
0x180039470  mov     rax, cs:__security_cookie
0x180039477  xor     rax, rsp
0x18003947a  mov     [rsp+78h+var_10], rax
0x18003947f  mov     rdi, rcx
0x180039482  mov     rsi, [rsp+78h+Resource]
0x18003948a  mov     [rsp+78h+var_40], rsi
0x18003948f  mov     rbx, [rsp+78h+ResourceSize]
0x180039497  mov     [rsp+78h+var_38], rbx
0x18003949c  mov     qword ptr [r11-50h], 0
0x1800394a4  mov     qword ptr [r11-48h], 0
0x1800394ac  mov     [rsp+78h+Size], 0
0x1800394b4  mov     eax, r9d
0x1800394b7  mov     [r11-28h], rax
0x1800394bb  mov     [r11-20h], r8
0x1800394bf  mov     qword ptr [r11-18h], 0
0x1800394c7  or      rdi, 1
0x1800394cb  mov     [rsp+78h+var_30], rdi
0x1800394d0  lea     r9, [r11-50h]; ResourceDataEntry
0x1800394d4  mov     r8d, 3; Level
0x1800394da  lea     rdx, [r11-28h]; ResourceInfo
0x1800394de  mov     rcx, rdi; BaseAddress
0x1800394e1  call    cs:__imp_LdrFindResource_U
0x1800394e8  nop     dword ptr [rax+rax+00h]
0x1800394ed  mov     [rsp+78h+var_54], eax
0x1800394f1  jmp     short loc_18003950B
0x1800394f3  mov     eax, 0C0000001h
0x1800394f8  mov     [rsp+78h+var_54], eax
0x1800394fc  mov     rsi, [rsp+78h+var_40]
0x180039501  mov     rbx, [rsp+78h+var_38]
0x180039506  mov     rdi, [rsp+78h+var_30]
0x18003950b  test    eax, eax
0x18003950d  js      short loc_18003957A
0x18003950f  lea     r9, [rsp+78h+Size]; Size
0x180039514  lea     r8, [rsp+78h+Src]; Resource
0x180039519  mov     rdx, [rsp+78h+ResourceDataEntry]; ResourceDataEntry
0x18003951e  mov     rcx, rdi; BaseAddress
0x180039521  call    cs:__imp_LdrAccessResource
0x180039528  nop     dword ptr [rax+rax+00h]
0x18003952d  test    eax, eax
0x18003952f  js      short loc_18003957A
0x180039531  mov     edx, [rsp+78h+Size]; NumberOfBytes
0x180039535  mov     ecx, 1; PoolType
0x18003953a  mov     r8d, 7372534Bh; Tag
0x180039540  call    cs:__imp_ExAllocatePoolWithTag
0x180039547  nop     dword ptr [rax+rax+00h]
0x18003954c  mov     [rsi], rax
0x18003954f  test    rax, rax
0x180039552  jz      short loc_180039575
0x180039554  mov     r8d, [rsp+78h+Size]; Size
0x180039559  mov     rdx, [rsp+78h+Src]; Src
0x18003955e  mov     rcx, rax; void *
0x180039561  call    memmove
0x180039566  test    rbx, rbx
0x180039569  jz      short loc_180039571
0x18003956b  mov     eax, [rsp+78h+Size]
0x18003956f  mov     [rbx], eax
0x180039571  xor     eax, eax
0x180039573  jmp     short loc_18003957A
0x180039575  mov     eax, 0C000009Ah
0x18003957a  mov     rcx, [rsp+78h+var_10]
0x18003957f  xor     rcx, rsp; StackCookie
0x180039582  call    __security_check_cookie
0x180039587  lea     r11, [rsp+78h+var_8]
0x18003958c  mov     rbx, [r11+18h]
0x180039590  mov     rsi, [r11+20h]
0x180039594  mov     rsp, r11
0x180039597  pop     rdi
0x180039598  retn
```
