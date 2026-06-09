# CiSetDebugAuthInformation

- ea: `0x1800629fc`
- end: `0x180062bc2`
- name: `CiSetDebugAuthInformation`
- size: `454`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18005ec10`

## callees

- `0x180020768`
- `0x180020ba8`
- `0x18002c000`
- `0x18005dcb0`
- `0x1800629fc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180062acd`
- `ntoskrnl!ExAllocatePool2` at `0x180062acd`
- `ntoskrnl!ObfDereferenceObject` at `0x180062b9d`
- `ntoskrnl!ObfDereferenceObject` at `0x180062b9d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180062aa5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180062aa5`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x180062b1f`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x180062b1f`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x180062b78`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x180062b78`
- `ntoskrnl!PsProcessType` at `0x180062a81`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x180062b38`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x180062b38`
- `ntoskrnl!RtlCreateUnicodeString` at `0x180062afb`
- `ntoskrnl!RtlCreateUnicodeString` at `0x180062afb`

## pseudocode

```c
__int64 __fastcall CiSetDebugAuthInformation(HANDLE Handle, int a2, int a3)
{
  PVOID v4; // r14
  _QWORD *v5; // rdi
  __int64 v6; // rcx
  NTSTATUS v7; // ebx
  char v8; // si
  NTSTATUS v9; // eax
  __int64 Pool2; // rax
  const WCHAR *v11; // rdx
  _QWORD *v12; // rax
  __int64 v14; // [rsp+30h] [rbp-28h] BYREF
  PCWSTR SourceString[2]; // [rsp+38h] [rbp-20h] BYREF
  PVOID Object; // [rsp+A8h] [rbp+50h] BYREF

  v4 = 0;
  v14 = 0;
  LODWORD(Object) = 0;
  v5 = 0;
  *(_OWORD *)SourceString = 0;
  v7 = SbValidateAndParseDebugAuthToken(a2, a3, (unsigned int)&v14, (unsigned int)&Object, (__int64)SourceString);
  if ( v7 >= 0 )
  {
    v8 = (char)Object;
    if ( (unsigned int)Object <= 0xFF
      && (LOBYTE(v6) = (_BYTE)Object, (*((unsigned __int8 (__fastcall **)(__int64))&xmmword_18004A5A0 + 1))(v6))
      && (v8 & 7) == 1 )
    {
      Object = 0;
      v9 = ObReferenceObjectByHandle(Handle, 0, (POBJECT_TYPE)PsProcessType, 0, &Object, 0);
      v4 = Object;
      v7 = v9;
      if ( v9 >= 0 )
      {
        Pool2 = ExAllocatePool2(256, 48, 1668499779);
        v5 = (_QWORD *)Pool2;
        if ( Pool2
          && (v11 = SourceString[1],
              *(_QWORD *)(Pool2 + 16) = v4,
              *(_BYTE *)(Pool2 + 24) = v8,
              RtlCreateUnicodeString((PUNICODE_STRING)(Pool2 + 32), v11)) )
        {
          v7 = RtlRunOnceExecuteOnce(&RunOnce, CiDebugAuthInitRunOnce, 0, 0);
          if ( v7 >= 0 )
          {
            ExEnterCriticalRegionAndAcquireResourceExclusive(&Resource);
            v12 = qword_1800497E8;
            if ( *((PVOID **)qword_1800497E8 + 1) != &qword_1800497E8 )
              __fastfail(3u);
            v5[1] = &qword_1800497E8;
            *v5 = v12;
            v12[1] = v5;
            qword_1800497E8 = v5;
            ExReleaseResourceAndLeaveCriticalRegion(&Resource);
            v5 = 0;
          }
        }
        else
        {
          v7 = -1073741801;
        }
      }
    }
    else
    {
      v7 = -1073741496;
    }
  }
  CiDeleteDebugAuth(v5);
  if ( v4 )
    ObfDereferenceObject(v4);
  SbFreePolicy(v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800629fc  push    rbp
0x1800629fe  push    rbx
0x1800629ff  push    rsi
0x180062a00  push    rdi
0x180062a01  push    r14
0x180062a03  push    r15
0x180062a05  mov     rbp, rsp
0x180062a08  sub     rsp, 58h
0x180062a0c  mov     r15, rcx
0x180062a0f  lea     r9, [rbp+arg_18]
0x180062a13  mov     eax, r8d
0x180062a16  lea     rcx, [rbp+SourceString]
0x180062a1a  mov     r10, rdx
0x180062a1d  mov     [rsp+58h+Object], rcx
0x180062a22  xor     r14d, r14d
0x180062a25  lea     r8, [rbp+var_28]
0x180062a29  xorps   xmm0, xmm0
0x180062a2c  mov     [rbp+var_28], r14
0x180062a30  mov     rcx, r10
0x180062a33  mov     dword ptr [rbp+arg_18], r14d
0x180062a37  mov     edx, eax
0x180062a39  xor     edi, edi
0x180062a3b  movups  xmmword ptr [rbp+SourceString], xmm0
0x180062a3f  call    SbValidateAndParseDebugAuthToken
0x180062a44  mov     ebx, eax
0x180062a46  test    eax, eax
0x180062a48  js      loc_180062B8D
0x180062a4e  mov     esi, dword ptr [rbp+arg_18]
0x180062a51  cmp     esi, 0FFh
0x180062a57  ja      loc_180062B88
0x180062a5d  mov     rax, qword ptr cs:xmmword_18004A5A0+8
0x180062a64  mov     cl, sil
0x180062a67  call    _guard_dispatch_icall
0x180062a6c  test    al, al
0x180062a6e  jz      loc_180062B88
0x180062a74  mov     al, sil
0x180062a77  and     al, 7
0x180062a79  cmp     al, 1
0x180062a7b  jnz     loc_180062B88
0x180062a81  mov     r8, cs:__imp_PsProcessType
0x180062a88  lea     rax, [rbp+arg_18]
0x180062a8c  mov     [rsp+58h+HandleInformation], rdi; HandleInformation
0x180062a91  xor     r9d, r9d; AccessMode
0x180062a94  xor     edx, edx; DesiredAccess
0x180062a96  mov     [rbp+arg_18], rdi
0x180062a9a  mov     rcx, r15; Handle
0x180062a9d  mov     [rsp+58h+Object], rax; Object
0x180062aa2  mov     r8, [r8]; ObjectType
0x180062aa5  call    cs:__imp_ObReferenceObjectByHandle
0x180062aac  nop     dword ptr [rax+rax+00h]
0x180062ab1  mov     r14, [rbp+arg_18]
0x180062ab5  mov     ebx, eax
0x180062ab7  test    eax, eax
0x180062ab9  js      loc_180062B8D
0x180062abf  lea     edx, [rdi+30h]
0x180062ac2  mov     ecx, 100h
0x180062ac7  mov     r8d, 63734943h
0x180062acd  call    cs:__imp_ExAllocatePool2
0x180062ad4  nop     dword ptr [rax+rax+00h]
0x180062ad9  mov     rdi, rax
0x180062adc  test    rax, rax
0x180062adf  jnz     short loc_180062AEB
0x180062ae1  mov     ebx, 0C0000017h
0x180062ae6  jmp     loc_180062B8D
0x180062aeb  mov     rdx, [rbp+SourceString+8]; SourceString
0x180062aef  lea     rcx, [rax+20h]; DestinationString
0x180062af3  mov     [rax+10h], r14
0x180062af7  mov     [rax+18h], sil
0x180062afb  call    cs:__imp_RtlCreateUnicodeString
0x180062b02  nop     dword ptr [rax+rax+00h]
0x180062b07  test    al, al
0x180062b09  jz      short loc_180062AE1
0x180062b0b  xor     r9d, r9d; Context
0x180062b0e  lea     rdx, CiDebugAuthInitRunOnce; InitFn
0x180062b15  xor     r8d, r8d; Parameter
0x180062b18  lea     rcx, RunOnce; RunOnce
0x180062b1f  call    cs:__imp_RtlRunOnceExecuteOnce
0x180062b26  nop     dword ptr [rax+rax+00h]
0x180062b2b  mov     ebx, eax
0x180062b2d  test    eax, eax
0x180062b2f  js      short loc_180062B8D
0x180062b31  lea     rcx, Resource; Resource
0x180062b38  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x180062b3f  nop     dword ptr [rax+rax+00h]
0x180062b44  mov     rax, cs:qword_1800497E8
0x180062b4b  lea     rcx, qword_1800497E8
0x180062b52  cmp     [rax+8], rcx
0x180062b56  jz      short loc_180062B5F
0x180062b58  mov     ecx, 3
0x180062b5d  int     29h; Win8: RtlFailFast(ecx)
0x180062b5f  mov     [rdi+8], rcx
0x180062b63  lea     rcx, Resource; Resource
0x180062b6a  mov     [rdi], rax
0x180062b6d  mov     [rax+8], rdi
0x180062b71  mov     cs:qword_1800497E8, rdi
0x180062b78  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x180062b7f  nop     dword ptr [rax+rax+00h]
0x180062b84  xor     edi, edi
0x180062b86  jmp     short loc_180062B8D
0x180062b88  mov     ebx, 0C0000148h
0x180062b8d  mov     rcx, rdi; P
0x180062b90  call    CiDeleteDebugAuth
0x180062b95  test    r14, r14
0x180062b98  jz      short loc_180062BA9
0x180062b9a  mov     rcx, r14; Object
0x180062b9d  call    cs:__imp_ObfDereferenceObject
0x180062ba4  nop     dword ptr [rax+rax+00h]
0x180062ba9  mov     rcx, [rbp+var_28]
0x180062bad  call    SbFreePolicy
0x180062bb2  mov     eax, ebx
0x180062bb4  add     rsp, 58h
0x180062bb8  pop     r15
0x180062bba  pop     r14
0x180062bbc  pop     rdi
0x180062bbd  pop     rsi
0x180062bbe  pop     rbx
0x180062bbf  pop     rbp
0x180062bc0  retn
```
