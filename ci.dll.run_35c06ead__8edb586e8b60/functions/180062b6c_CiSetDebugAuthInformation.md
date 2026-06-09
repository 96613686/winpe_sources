# CiSetDebugAuthInformation

- ea: `0x180062b6c`
- end: `0x180062d32`
- name: `CiSetDebugAuthInformation`
- size: `454`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18005ebb0`

## callees

- `0x180020838`
- `0x180020c78`
- `0x18002c1b0`
- `0x18005dc50`
- `0x180062b6c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180062c3d`
- `ntoskrnl!ExAllocatePool2` at `0x180062c3d`
- `ntoskrnl!ObfDereferenceObject` at `0x180062d0d`
- `ntoskrnl!ObfDereferenceObject` at `0x180062d0d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180062c15`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180062c15`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x180062c8f`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x180062c8f`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x180062ce8`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x180062ce8`
- `ntoskrnl!PsProcessType` at `0x180062bf1`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x180062ca8`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x180062ca8`
- `ntoskrnl!RtlCreateUnicodeString` at `0x180062c6b`
- `ntoskrnl!RtlCreateUnicodeString` at `0x180062c6b`

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
      && (LOBYTE(v6) = (_BYTE)Object, (*((unsigned __int8 (__fastcall **)(__int64))&xmmword_18004A640 + 1))(v6))
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
0x180062b6c  push    rbp
0x180062b6e  push    rbx
0x180062b6f  push    rsi
0x180062b70  push    rdi
0x180062b71  push    r14
0x180062b73  push    r15
0x180062b75  mov     rbp, rsp
0x180062b78  sub     rsp, 58h
0x180062b7c  mov     r15, rcx
0x180062b7f  lea     r9, [rbp+arg_18]
0x180062b83  mov     eax, r8d
0x180062b86  lea     rcx, [rbp+SourceString]
0x180062b8a  mov     r10, rdx
0x180062b8d  mov     [rsp+58h+Object], rcx
0x180062b92  xor     r14d, r14d
0x180062b95  lea     r8, [rbp+var_28]
0x180062b99  xorps   xmm0, xmm0
0x180062b9c  mov     [rbp+var_28], r14
0x180062ba0  mov     rcx, r10
0x180062ba3  mov     dword ptr [rbp+arg_18], r14d
0x180062ba7  mov     edx, eax
0x180062ba9  xor     edi, edi
0x180062bab  movups  xmmword ptr [rbp+SourceString], xmm0
0x180062baf  call    SbValidateAndParseDebugAuthToken
0x180062bb4  mov     ebx, eax
0x180062bb6  test    eax, eax
0x180062bb8  js      loc_180062CFD
0x180062bbe  mov     esi, dword ptr [rbp+arg_18]
0x180062bc1  cmp     esi, 0FFh
0x180062bc7  ja      loc_180062CF8
0x180062bcd  mov     rax, qword ptr cs:xmmword_18004A640+8
0x180062bd4  mov     cl, sil
0x180062bd7  call    _guard_dispatch_icall
0x180062bdc  test    al, al
0x180062bde  jz      loc_180062CF8
0x180062be4  mov     al, sil
0x180062be7  and     al, 7
0x180062be9  cmp     al, 1
0x180062beb  jnz     loc_180062CF8
0x180062bf1  mov     r8, cs:__imp_PsProcessType
0x180062bf8  lea     rax, [rbp+arg_18]
0x180062bfc  mov     [rsp+58h+HandleInformation], rdi; HandleInformation
0x180062c01  xor     r9d, r9d; AccessMode
0x180062c04  xor     edx, edx; DesiredAccess
0x180062c06  mov     [rbp+arg_18], rdi
0x180062c0a  mov     rcx, r15; Handle
0x180062c0d  mov     [rsp+58h+Object], rax; Object
0x180062c12  mov     r8, [r8]; ObjectType
0x180062c15  call    cs:__imp_ObReferenceObjectByHandle
0x180062c1c  nop     dword ptr [rax+rax+00h]
0x180062c21  mov     r14, [rbp+arg_18]
0x180062c25  mov     ebx, eax
0x180062c27  test    eax, eax
0x180062c29  js      loc_180062CFD
0x180062c2f  lea     edx, [rdi+30h]
0x180062c32  mov     ecx, 100h
0x180062c37  mov     r8d, 63734943h
0x180062c3d  call    cs:__imp_ExAllocatePool2
0x180062c44  nop     dword ptr [rax+rax+00h]
0x180062c49  mov     rdi, rax
0x180062c4c  test    rax, rax
0x180062c4f  jnz     short loc_180062C5B
0x180062c51  mov     ebx, 0C0000017h
0x180062c56  jmp     loc_180062CFD
0x180062c5b  mov     rdx, [rbp+SourceString+8]; SourceString
0x180062c5f  lea     rcx, [rax+20h]; DestinationString
0x180062c63  mov     [rax+10h], r14
0x180062c67  mov     [rax+18h], sil
0x180062c6b  call    cs:__imp_RtlCreateUnicodeString
0x180062c72  nop     dword ptr [rax+rax+00h]
0x180062c77  test    al, al
0x180062c79  jz      short loc_180062C51
0x180062c7b  xor     r9d, r9d; Context
0x180062c7e  lea     rdx, CiDebugAuthInitRunOnce; InitFn
0x180062c85  xor     r8d, r8d; Parameter
0x180062c88  lea     rcx, RunOnce; RunOnce
0x180062c8f  call    cs:__imp_RtlRunOnceExecuteOnce
0x180062c96  nop     dword ptr [rax+rax+00h]
0x180062c9b  mov     ebx, eax
0x180062c9d  test    eax, eax
0x180062c9f  js      short loc_180062CFD
0x180062ca1  lea     rcx, Resource; Resource
0x180062ca8  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x180062caf  nop     dword ptr [rax+rax+00h]
0x180062cb4  mov     rax, cs:qword_1800497E8
0x180062cbb  lea     rcx, qword_1800497E8
0x180062cc2  cmp     [rax+8], rcx
0x180062cc6  jz      short loc_180062CCF
0x180062cc8  mov     ecx, 3
0x180062ccd  int     29h; Win8: RtlFailFast(ecx)
0x180062ccf  mov     [rdi+8], rcx
0x180062cd3  lea     rcx, Resource; Resource
0x180062cda  mov     [rdi], rax
0x180062cdd  mov     [rax+8], rdi
0x180062ce1  mov     cs:qword_1800497E8, rdi
0x180062ce8  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x180062cef  nop     dword ptr [rax+rax+00h]
0x180062cf4  xor     edi, edi
0x180062cf6  jmp     short loc_180062CFD
0x180062cf8  mov     ebx, 0C0000148h
0x180062cfd  mov     rcx, rdi; P
0x180062d00  call    CiDeleteDebugAuth
0x180062d05  test    r14, r14
0x180062d08  jz      short loc_180062D19
0x180062d0a  mov     rcx, r14; Object
0x180062d0d  call    cs:__imp_ObfDereferenceObject
0x180062d14  nop     dword ptr [rax+rax+00h]
0x180062d19  mov     rcx, [rbp+var_28]
0x180062d1d  call    SbFreePolicy
0x180062d22  mov     eax, ebx
0x180062d24  add     rsp, 58h
0x180062d28  pop     r15
0x180062d2a  pop     r14
0x180062d2c  pop     rdi
0x180062d2d  pop     rsi
0x180062d2e  pop     rbx
0x180062d2f  pop     rbp
0x180062d30  retn
```
