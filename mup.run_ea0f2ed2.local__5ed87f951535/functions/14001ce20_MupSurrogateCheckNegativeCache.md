# MupSurrogateCheckNegativeCache

- ea: `0x14001ce20`
- end: `0x14001cfea`
- name: `MupSurrogateCheckNegativeCache`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x140002754`
- `0x140002b18`
- `0x1400036c8`
- `0x14001ba90`
- `0x14001bb30`
- `0x14001c760`
- `0x14001c870`
- `0x14001ce20`
- `0x14001d210`
- `0x14001da7c`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001ceac`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001ceac`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cf22`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cf22`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001ce97`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001ce97`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001ceca`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001ceca`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001cf2e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001cf2e`

## pseudocode

```c
__int64 __fastcall MupSurrogateCheckNegativeCache(__int64 *a1, const UNICODE_STRING *a2)
{
  __int64 v3; // rcx
  __int64 SiloFromFileObject; // rax
  __int64 result; // rax
  __int64 v6; // rsi
  __int64 v7; // rbx
  struct _UNICODE_PREFIX_TABLE *UncCachePrefixTable; // rax
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  __int64 v10; // rsi
  void *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF

  v13 = 0;
  if ( a1 && (v3 = *a1) != 0 )
  {
    SiloFromFileObject = MupGetSiloFromFileObject(*(_QWORD *)(*(_QWORD *)(v3 + 184) + 48LL));
    result = MupGetContainerContextFromSilo(SiloFromFileObject, &v13);
  }
  else
  {
    result = MupGetContainerContextFromThread(&v13);
  }
  if ( !(_DWORD)result )
  {
    v6 = v13;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_ea0133f9b224365980f4880a222ef939_Traceguids, a2);
    }
    v7 = 0;
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&Resource, 1u);
    UncCachePrefixTable = (struct _UNICODE_PREFIX_TABLE *)MupGetUncCachePrefixTable(v6);
    UnicodePrefix = RtlFindUnicodePrefix(UncCachePrefixTable, a2, 1u);
    v10 = (unsigned __int64)&UnicodePrefix[-1].Links.RightChild & -(__int64)(UnicodePrefix != 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
    {
      WPP_SF_Zq(
        WPP_GLOBAL_Control->AttachedDevice,
        25,
        (unsigned int)WPP_ea0133f9b224365980f4880a222ef939_Traceguids,
        (_DWORD)a2,
        v10);
    }
    v11 = 0;
    if ( v10 )
    {
      v7 = *(_QWORD *)(v10 + 104);
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 4));
      v12 = *(_QWORD *)(v10 + 112);
      if ( v12 )
      {
        v11 = *(void **)(v10 + 112);
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 4));
      }
    }
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_ea0133f9b224365980f4880a222ef939_Traceguids, v7);
    }
    if ( v7 )
    {
      MupReleaseUncProvider(v7);
      if ( !v11 )
        return 0;
      MupReleaseSurrogateProvider(v11);
    }
    return 3221226021LL;
  }
  return result;
}

```

## disassembly

```asm
0x14001ce20  push    rbx
0x14001ce22  push    rsi
0x14001ce23  push    rdi
0x14001ce24  push    r15
0x14001ce26  sub     rsp, 38h
0x14001ce2a  mov     [rsp+58h+arg_0], 0
0x14001ce33  mov     rdi, rdx
0x14001ce36  test    rcx, rcx
0x14001ce39  jz      loc_14001CF75
0x14001ce3f  mov     rcx, [rcx]
0x14001ce42  test    rcx, rcx
0x14001ce45  jz      loc_14001CF75
0x14001ce4b  mov     rcx, [rcx+0B8h]
0x14001ce52  mov     rcx, [rcx+30h]
0x14001ce56  call    MupGetSiloFromFileObject
0x14001ce5b  mov     rcx, rax
0x14001ce5e  lea     rdx, [rsp+58h+arg_0]
0x14001ce63  call    MupGetContainerContextFromSilo
0x14001ce68  test    eax, eax
0x14001ce6a  jnz     loc_14001CF59
0x14001ce70  mov     rsi, [rsp+58h+arg_0]
0x14001ce75  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ce7c  lea     r15, WPP_GLOBAL_Control
0x14001ce83  cmp     rcx, r15
0x14001ce86  jz      short loc_14001CE95
0x14001ce88  test    dword ptr [rcx+2Ch], 2000000h
0x14001ce8f  jnz     loc_14001CF8E
0x14001ce95  xor     ebx, ebx
0x14001ce97  call    cs:__imp_KeEnterCriticalRegion
0x14001ce9e  nop     dword ptr [rax+rax+00h]
0x14001cea3  mov     dl, 1; Wait
0x14001cea5  lea     rcx, Resource; Resource
0x14001ceac  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001ceb3  nop     dword ptr [rax+rax+00h]
0x14001ceb8  mov     rcx, rsi
0x14001cebb  call    MupGetUncCachePrefixTable
0x14001cec0  mov     rcx, rax; PrefixTable
0x14001cec3  lea     r8d, [rbx+1]; CaseInsensitiveIndex
0x14001cec7  mov     rdx, rdi; FullName
0x14001ceca  call    cs:__imp_RtlFindUnicodePrefix
0x14001ced1  nop     dword ptr [rax+rax+00h]
0x14001ced6  lea     rcx, [rax-10h]
0x14001ceda  neg     rax
0x14001cedd  sbb     rsi, rsi
0x14001cee0  and     rsi, rcx
0x14001cee3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ceea  cmp     rcx, r15
0x14001ceed  jz      short loc_14001CEFC
0x14001ceef  test    dword ptr [rcx+2Ch], 2000000h
0x14001cef6  jnz     loc_14001CFAB
0x14001cefc  xor     edi, edi
0x14001cefe  test    rsi, rsi
0x14001cf01  jz      short loc_14001CF1B
0x14001cf03  mov     rbx, [rsi+68h]
0x14001cf07  lock inc dword ptr [rbx+4]
0x14001cf0b  mov     rax, [rsi+70h]
0x14001cf0f  test    rax, rax
0x14001cf12  jz      short loc_14001CF1B
0x14001cf14  mov     rdi, rax
0x14001cf17  lock inc dword ptr [rax+4]
0x14001cf1b  lea     rcx, Resource; Resource
0x14001cf22  call    cs:__imp_ExReleaseResourceLite
0x14001cf29  nop     dword ptr [rax+rax+00h]
0x14001cf2e  call    cs:__imp_KeLeaveCriticalRegion
0x14001cf35  nop     dword ptr [rax+rax+00h]
0x14001cf3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cf41  cmp     rcx, r15
0x14001cf44  jz      short loc_14001CF4F
0x14001cf46  test    dword ptr [rcx+2Ch], 2000000h
0x14001cf4d  jnz     short loc_14001CFCD
0x14001cf4f  test    rbx, rbx
0x14001cf52  jnz     short loc_14001CF64
0x14001cf54  mov     eax, 0C0000225h
0x14001cf59  add     rsp, 38h
0x14001cf5d  pop     r15
0x14001cf5f  pop     rdi
0x14001cf60  pop     rsi
0x14001cf61  pop     rbx
0x14001cf62  retn
0x14001cf64  mov     rcx, rbx
0x14001cf67  call    MupReleaseUncProvider
0x14001cf6c  test    rdi, rdi
0x14001cf6f  jnz     short loc_14001CF84
0x14001cf71  xor     eax, eax
0x14001cf73  jmp     short loc_14001CF59
0x14001cf75  lea     rcx, [rsp+58h+arg_0]
0x14001cf7a  call    MupGetContainerContextFromThread
0x14001cf7f  jmp     loc_14001CE68
0x14001cf84  mov     rcx, rdi; P
0x14001cf87  call    MupReleaseSurrogateProvider
0x14001cf8c  jmp     short loc_14001CF54
0x14001cf8e  mov     rcx, [rcx+18h]
0x14001cf92  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x14001cf99  mov     edx, 11h
0x14001cf9e  mov     r9, rdi
0x14001cfa1  call    WPP_SF_Z
0x14001cfa6  jmp     loc_14001CE95
0x14001cfab  mov     rcx, [rcx+18h]
0x14001cfaf  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x14001cfb6  mov     edx, 19h
0x14001cfbb  mov     [rsp+58h+var_38], rsi
0x14001cfc0  mov     r9, rdi
0x14001cfc3  call    WPP_SF_Zq
0x14001cfc8  jmp     loc_14001CEFC
0x14001cfcd  mov     rcx, [rcx+18h]
0x14001cfd1  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x14001cfd8  mov     edx, 12h
0x14001cfdd  mov     r9, rbx
0x14001cfe0  call    WPP_SF_q
0x14001cfe5  jmp     loc_14001CF4F
```
