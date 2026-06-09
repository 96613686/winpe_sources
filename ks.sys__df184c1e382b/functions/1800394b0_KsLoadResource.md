# KsLoadResource

- ea: `0x1800394b0`
- end: `0x1800395ea`
- name: `KsLoadResource`
- size: `314`
- prototype: `NTSTATUS __stdcall(PVOID ImageBase, POOL_TYPE PoolType, ULONG_PTR ResourceName, ULONG ResourceType, PVOID *Resource, PULONG ResourceSize)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180019bd0`
- `0x180019d00`
- `0x1800394b0`

## import_xrefs

- `ntoskrnl!LdrFindResource_U` at `0x180039531`
- `ntoskrnl!LdrFindResource_U` at `0x180039531`
- `ntoskrnl!LdrAccessResource` at `0x180039571`
- `ntoskrnl!LdrAccessResource` at `0x180039571`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180039590`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180039590`

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
0x1800394b0  mov     r11, rsp
0x1800394b3  mov     [r11+10h], rbx
0x1800394b7  mov     [r11+18h], rsi
0x1800394bb  push    rdi
0x1800394bc  sub     rsp, 70h
0x1800394c0  mov     rax, cs:__security_cookie
0x1800394c7  xor     rax, rsp
0x1800394ca  mov     [rsp+78h+var_10], rax
0x1800394cf  mov     rdi, rcx
0x1800394d2  mov     rsi, [rsp+78h+Resource]
0x1800394da  mov     [rsp+78h+var_40], rsi
0x1800394df  mov     rbx, [rsp+78h+ResourceSize]
0x1800394e7  mov     [rsp+78h+var_38], rbx
0x1800394ec  mov     qword ptr [r11-50h], 0
0x1800394f4  mov     qword ptr [r11-48h], 0
0x1800394fc  mov     [rsp+78h+Size], 0
0x180039504  mov     eax, r9d
0x180039507  mov     [r11-28h], rax
0x18003950b  mov     [r11-20h], r8
0x18003950f  mov     qword ptr [r11-18h], 0
0x180039517  or      rdi, 1
0x18003951b  mov     [rsp+78h+var_30], rdi
0x180039520  lea     r9, [r11-50h]; ResourceDataEntry
0x180039524  mov     r8d, 3; Level
0x18003952a  lea     rdx, [r11-28h]; ResourceInfo
0x18003952e  mov     rcx, rdi; BaseAddress
0x180039531  call    cs:__imp_LdrFindResource_U
0x180039538  nop     dword ptr [rax+rax+00h]
0x18003953d  mov     [rsp+78h+var_54], eax
0x180039541  jmp     short loc_18003955B
0x180039543  mov     eax, 0C0000001h
0x180039548  mov     [rsp+78h+var_54], eax
0x18003954c  mov     rsi, [rsp+78h+var_40]
0x180039551  mov     rbx, [rsp+78h+var_38]
0x180039556  mov     rdi, [rsp+78h+var_30]
0x18003955b  test    eax, eax
0x18003955d  js      short loc_1800395CA
0x18003955f  lea     r9, [rsp+78h+Size]; Size
0x180039564  lea     r8, [rsp+78h+Src]; Resource
0x180039569  mov     rdx, [rsp+78h+ResourceDataEntry]; ResourceDataEntry
0x18003956e  mov     rcx, rdi; BaseAddress
0x180039571  call    cs:__imp_LdrAccessResource
0x180039578  nop     dword ptr [rax+rax+00h]
0x18003957d  test    eax, eax
0x18003957f  js      short loc_1800395CA
0x180039581  mov     edx, [rsp+78h+Size]; NumberOfBytes
0x180039585  mov     ecx, 1; PoolType
0x18003958a  mov     r8d, 7372534Bh; Tag
0x180039590  call    cs:__imp_ExAllocatePoolWithTag
0x180039597  nop     dword ptr [rax+rax+00h]
0x18003959c  mov     [rsi], rax
0x18003959f  test    rax, rax
0x1800395a2  jz      short loc_1800395C5
0x1800395a4  mov     r8d, [rsp+78h+Size]; Size
0x1800395a9  mov     rdx, [rsp+78h+Src]; Src
0x1800395ae  mov     rcx, rax; void *
0x1800395b1  call    memmove
0x1800395b6  test    rbx, rbx
0x1800395b9  jz      short loc_1800395C1
0x1800395bb  mov     eax, [rsp+78h+Size]
0x1800395bf  mov     [rbx], eax
0x1800395c1  xor     eax, eax
0x1800395c3  jmp     short loc_1800395CA
0x1800395c5  mov     eax, 0C000009Ah
0x1800395ca  mov     rcx, [rsp+78h+var_10]
0x1800395cf  xor     rcx, rsp; StackCookie
0x1800395d2  call    __security_check_cookie
0x1800395d7  lea     r11, [rsp+78h+var_8]
0x1800395dc  mov     rbx, [r11+18h]
0x1800395e0  mov     rsi, [r11+20h]
0x1800395e4  mov     rsp, r11
0x1800395e7  pop     rdi
0x1800395e8  retn
```
