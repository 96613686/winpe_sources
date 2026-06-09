# DuplicateSid(void *,void * *)

- ea: `0x18000aee8`
- end: `0x18000afb2`
- name: `?DuplicateSid@@YAJPEAXPEAPEAX@Z`
- size: `202`
- prototype: `__int64 __fastcall(PSID SourceSid, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18000f454`

## callees

- `0x18000aee8`
- `0x18001a000`

## import_xrefs

- `ntoskrnl!RtlValidSid` at `0x18000af6d`
- `ntoskrnl!RtlValidSid` at `0x18000af6d`
- `ntoskrnl!RtlLengthSid` at `0x18000aef9`
- `ntoskrnl!RtlLengthSid` at `0x18000af44`
- `ntoskrnl!RtlLengthSid` at `0x18000aef9`
- `ntoskrnl!RtlLengthSid` at `0x18000af44`
- `ntoskrnl!RtlCopySid` at `0x18000af58`
- `ntoskrnl!RtlCopySid` at `0x18000af58`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000af87`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000af87`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000af14`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18000af14`

## pseudocode

```c
__int64 __fastcall DuplicateSid(PSID SourceSid, void **a2)
{
  ULONG v4; // edi
  PVOID PoolWithTag; // rax
  void *v6; // rbx
  ULONG v7; // eax
  NTSTATUS v8; // edi

  v4 = RtlLengthSid(SourceSid);
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, v4, 0x656C534Bu);
  v6 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
      goto LABEL_4;
    return (unsigned int)-1073741670;
  }
  if ( !PoolWithTag )
    return (unsigned int)-1073741670;
  memset(PoolWithTag, 0, v4);
LABEL_4:
  v7 = RtlLengthSid(SourceSid);
  v8 = RtlCopySid(v7, v6, SourceSid);
  if ( v8 >= 0 )
  {
    if ( RtlValidSid(v6) )
    {
      *a2 = v6;
      return (unsigned int)v8;
    }
    v8 = -1073741811;
  }
  ExFreePoolWithTag(v6, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000aee8  push    rbx
0x18000aeea  push    rbp
0x18000aeeb  push    rsi
0x18000aeec  push    rdi
0x18000aeed  push    r14
0x18000aeef  sub     rsp, 20h
0x18000aef3  mov     r14, rdx
0x18000aef6  mov     rbp, rcx
0x18000aef9  call    cs:__imp_RtlLengthSid
0x18000af00  nop     dword ptr [rax+rax+00h]
0x18000af05  mov     edx, eax; NumberOfBytes
0x18000af07  mov     r8d, 656C534Bh; Tag
0x18000af0d  mov     ecx, 401h; PoolType
0x18000af12  mov     edi, eax
0x18000af14  call    cs:__imp_ExAllocatePoolWithTag
0x18000af1b  nop     dword ptr [rax+rax+00h]
0x18000af20  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18000af27  mov     rbx, rax
0x18000af2a  jnz     short loc_18000AFA1
0x18000af2c  test    rax, rax
0x18000af2f  jz      short loc_18000AFA6
0x18000af31  mov     r8d, edi; Size
0x18000af34  xor     edx, edx; Val
0x18000af36  mov     rcx, rax; void *
0x18000af39  call    memset
0x18000af3e  mov     rcx, rbp; Sid
0x18000af41  mov     rsi, rbx
0x18000af44  call    cs:__imp_RtlLengthSid
0x18000af4b  nop     dword ptr [rax+rax+00h]
0x18000af50  mov     r8, rbp; SourceSid
0x18000af53  mov     rdx, rbx; DestinationSid
0x18000af56  mov     ecx, eax; DestinationSidLength
0x18000af58  call    cs:__imp_RtlCopySid
0x18000af5f  nop     dword ptr [rax+rax+00h]
0x18000af64  mov     edi, eax
0x18000af66  test    eax, eax
0x18000af68  js      short loc_18000AF82
0x18000af6a  mov     rcx, rbx; Sid
0x18000af6d  call    cs:__imp_RtlValidSid
0x18000af74  nop     dword ptr [rax+rax+00h]
0x18000af79  test    al, al
0x18000af7b  jnz     short loc_18000AFAD
0x18000af7d  mov     edi, 0C000000Dh
0x18000af82  xor     edx, edx; Tag
0x18000af84  mov     rcx, rsi; P
0x18000af87  call    cs:__imp_ExFreePoolWithTag
0x18000af8e  nop     dword ptr [rax+rax+00h]
0x18000af93  mov     eax, edi
0x18000af95  add     rsp, 20h
0x18000af99  pop     r14
0x18000af9b  pop     rdi
0x18000af9c  pop     rsi
0x18000af9d  pop     rbp
0x18000af9e  pop     rbx
0x18000af9f  retn
0x18000afa1  test    rbx, rbx
0x18000afa4  jnz     short loc_18000AF3E
0x18000afa6  mov     edi, 0C000009Ah
0x18000afab  jmp     short loc_18000AF93
0x18000afad  mov     [r14], rbx
0x18000afb0  jmp     short loc_18000AF93
```
