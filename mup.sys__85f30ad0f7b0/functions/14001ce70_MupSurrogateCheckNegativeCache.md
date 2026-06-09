# MupSurrogateCheckNegativeCache

- ea: `0x14001ce70`
- end: `0x14001d03a`
- name: `MupSurrogateCheckNegativeCache`
- size: `458`
- prototype: `__int64 __fastcall(__int64 *, const UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update`

## callees

- `0x140002754`
- `0x140002b18`
- `0x1400036c8`
- `0x14001bae0`
- `0x14001bb80`
- `0x14001c7b0`
- `0x14001c8c0`
- `0x14001ce70`
- `0x14001d260`
- `0x14001dacc`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001cefc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001cefc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cf72`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001cf72`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001cee7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001cee7`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001cf1a`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001cf1a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001cf7e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001cf7e`

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
0x14001ce70  push    rbx
0x14001ce72  push    rsi
0x14001ce73  push    rdi
0x14001ce74  push    r15
0x14001ce76  sub     rsp, 38h
0x14001ce7a  mov     [rsp+58h+arg_0], 0
0x14001ce83  mov     rdi, rdx
0x14001ce86  test    rcx, rcx
0x14001ce89  jz      loc_14001CFC5
0x14001ce8f  mov     rcx, [rcx]
0x14001ce92  test    rcx, rcx
0x14001ce95  jz      loc_14001CFC5
0x14001ce9b  mov     rcx, [rcx+0B8h]
0x14001cea2  mov     rcx, [rcx+30h]
0x14001cea6  call    MupGetSiloFromFileObject
0x14001ceab  mov     rcx, rax
0x14001ceae  lea     rdx, [rsp+58h+arg_0]
0x14001ceb3  call    MupGetContainerContextFromSilo
0x14001ceb8  test    eax, eax
0x14001ceba  jnz     loc_14001CFA9
0x14001cec0  mov     rsi, [rsp+58h+arg_0]
0x14001cec5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cecc  lea     r15, WPP_GLOBAL_Control
0x14001ced3  cmp     rcx, r15
0x14001ced6  jz      short loc_14001CEE5
0x14001ced8  test    dword ptr [rcx+2Ch], 2000000h
0x14001cedf  jnz     loc_14001CFDE
0x14001cee5  xor     ebx, ebx
0x14001cee7  call    cs:__imp_KeEnterCriticalRegion
0x14001ceee  nop     dword ptr [rax+rax+00h]
0x14001cef3  mov     dl, 1; Wait
0x14001cef5  lea     rcx, Resource; Resource
0x14001cefc  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001cf03  nop     dword ptr [rax+rax+00h]
0x14001cf08  mov     rcx, rsi
0x14001cf0b  call    MupGetUncCachePrefixTable
0x14001cf10  mov     rcx, rax; PrefixTable
0x14001cf13  lea     r8d, [rbx+1]; CaseInsensitiveIndex
0x14001cf17  mov     rdx, rdi; FullName
0x14001cf1a  call    cs:__imp_RtlFindUnicodePrefix
0x14001cf21  nop     dword ptr [rax+rax+00h]
0x14001cf26  lea     rcx, [rax-10h]
0x14001cf2a  neg     rax
0x14001cf2d  sbb     rsi, rsi
0x14001cf30  and     rsi, rcx
0x14001cf33  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cf3a  cmp     rcx, r15
0x14001cf3d  jz      short loc_14001CF4C
0x14001cf3f  test    dword ptr [rcx+2Ch], 2000000h
0x14001cf46  jnz     loc_14001CFFB
0x14001cf4c  xor     edi, edi
0x14001cf4e  test    rsi, rsi
0x14001cf51  jz      short loc_14001CF6B
0x14001cf53  mov     rbx, [rsi+68h]
0x14001cf57  lock inc dword ptr [rbx+4]
0x14001cf5b  mov     rax, [rsi+70h]
0x14001cf5f  test    rax, rax
0x14001cf62  jz      short loc_14001CF6B
0x14001cf64  mov     rdi, rax
0x14001cf67  lock inc dword ptr [rax+4]
0x14001cf6b  lea     rcx, Resource; Resource
0x14001cf72  call    cs:__imp_ExReleaseResourceLite
0x14001cf79  nop     dword ptr [rax+rax+00h]
0x14001cf7e  call    cs:__imp_KeLeaveCriticalRegion
0x14001cf85  nop     dword ptr [rax+rax+00h]
0x14001cf8a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cf91  cmp     rcx, r15
0x14001cf94  jz      short loc_14001CF9F
0x14001cf96  test    dword ptr [rcx+2Ch], 2000000h
0x14001cf9d  jnz     short loc_14001D01D
0x14001cf9f  test    rbx, rbx
0x14001cfa2  jnz     short loc_14001CFB4
0x14001cfa4  mov     eax, 0C0000225h
0x14001cfa9  add     rsp, 38h
0x14001cfad  pop     r15
0x14001cfaf  pop     rdi
0x14001cfb0  pop     rsi
0x14001cfb1  pop     rbx
0x14001cfb2  retn
0x14001cfb4  mov     rcx, rbx
0x14001cfb7  call    MupReleaseUncProvider
0x14001cfbc  test    rdi, rdi
0x14001cfbf  jnz     short loc_14001CFD4
0x14001cfc1  xor     eax, eax
0x14001cfc3  jmp     short loc_14001CFA9
0x14001cfc5  lea     rcx, [rsp+58h+arg_0]
0x14001cfca  call    MupGetContainerContextFromThread
0x14001cfcf  jmp     loc_14001CEB8
0x14001cfd4  mov     rcx, rdi; P
0x14001cfd7  call    MupReleaseSurrogateProvider
0x14001cfdc  jmp     short loc_14001CFA4
0x14001cfde  mov     rcx, [rcx+18h]
0x14001cfe2  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x14001cfe9  mov     edx, 11h
0x14001cfee  mov     r9, rdi
0x14001cff1  call    WPP_SF_Z
0x14001cff6  jmp     loc_14001CEE5
0x14001cffb  mov     rcx, [rcx+18h]
0x14001cfff  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x14001d006  mov     edx, 19h
0x14001d00b  mov     [rsp+58h+var_38], rsi
0x14001d010  mov     r9, rdi
0x14001d013  call    WPP_SF_Zq
0x14001d018  jmp     loc_14001CF4C
0x14001d01d  mov     rcx, [rcx+18h]
0x14001d021  lea     r8, WPP_ea0133f9b224365980f4880a222ef939_Traceguids
0x14001d028  mov     edx, 12h
0x14001d02d  mov     r9, rbx
0x14001d030  call    WPP_SF_q
0x14001d035  jmp     loc_14001CF9F
```
