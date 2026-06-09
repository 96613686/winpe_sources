# CiSetDebugAuthInformation

- ea: `0x1800621bc`
- end: `0x180062382`
- name: `CiSetDebugAuthInformation`
- size: `454`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18005e510`

## callees

- `0x1800207f8`
- `0x180020c38`
- `0x18002bfd0`
- `0x18005d648`
- `0x1800621bc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18006228d`
- `ntoskrnl!ExAllocatePool2` at `0x18006228d`
- `ntoskrnl!ObfDereferenceObject` at `0x18006235d`
- `ntoskrnl!ObfDereferenceObject` at `0x18006235d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180062265`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x180062265`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1800622df`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x1800622df`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x180062338`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x180062338`
- `ntoskrnl!PsProcessType` at `0x180062241`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1800622f8`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x1800622f8`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1800622bb`
- `ntoskrnl!RtlCreateUnicodeString` at `0x1800622bb`

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
      && (LOBYTE(v6) = (_BYTE)Object, (*((unsigned __int8 (__fastcall **)(__int64))&xmmword_180049640 + 1))(v6))
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
            v12 = qword_1800487E8;
            if ( *((PVOID **)qword_1800487E8 + 1) != &qword_1800487E8 )
              __fastfail(3u);
            v5[1] = &qword_1800487E8;
            *v5 = v12;
            v12[1] = v5;
            qword_1800487E8 = v5;
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
0x1800621bc  push    rbp
0x1800621be  push    rbx
0x1800621bf  push    rsi
0x1800621c0  push    rdi
0x1800621c1  push    r14
0x1800621c3  push    r15
0x1800621c5  mov     rbp, rsp
0x1800621c8  sub     rsp, 58h
0x1800621cc  mov     r15, rcx
0x1800621cf  lea     r9, [rbp+arg_18]
0x1800621d3  mov     eax, r8d
0x1800621d6  lea     rcx, [rbp+SourceString]
0x1800621da  mov     r10, rdx
0x1800621dd  mov     [rsp+58h+Object], rcx
0x1800621e2  xor     r14d, r14d
0x1800621e5  lea     r8, [rbp+var_28]
0x1800621e9  xorps   xmm0, xmm0
0x1800621ec  mov     [rbp+var_28], r14
0x1800621f0  mov     rcx, r10
0x1800621f3  mov     dword ptr [rbp+arg_18], r14d
0x1800621f7  mov     edx, eax
0x1800621f9  xor     edi, edi
0x1800621fb  movups  xmmword ptr [rbp+SourceString], xmm0
0x1800621ff  call    SbValidateAndParseDebugAuthToken
0x180062204  mov     ebx, eax
0x180062206  test    eax, eax
0x180062208  js      loc_18006234D
0x18006220e  mov     esi, dword ptr [rbp+arg_18]
0x180062211  cmp     esi, 0FFh
0x180062217  ja      loc_180062348
0x18006221d  mov     rax, qword ptr cs:xmmword_180049640+8
0x180062224  mov     cl, sil
0x180062227  call    _guard_dispatch_icall
0x18006222c  test    al, al
0x18006222e  jz      loc_180062348
0x180062234  mov     al, sil
0x180062237  and     al, 7
0x180062239  cmp     al, 1
0x18006223b  jnz     loc_180062348
0x180062241  mov     r8, cs:__imp_PsProcessType
0x180062248  lea     rax, [rbp+arg_18]
0x18006224c  mov     [rsp+58h+HandleInformation], rdi; HandleInformation
0x180062251  xor     r9d, r9d; AccessMode
0x180062254  xor     edx, edx; DesiredAccess
0x180062256  mov     [rbp+arg_18], rdi
0x18006225a  mov     rcx, r15; Handle
0x18006225d  mov     [rsp+58h+Object], rax; Object
0x180062262  mov     r8, [r8]; ObjectType
0x180062265  call    cs:__imp_ObReferenceObjectByHandle
0x18006226c  nop     dword ptr [rax+rax+00h]
0x180062271  mov     r14, [rbp+arg_18]
0x180062275  mov     ebx, eax
0x180062277  test    eax, eax
0x180062279  js      loc_18006234D
0x18006227f  lea     edx, [rdi+30h]
0x180062282  mov     ecx, 100h
0x180062287  mov     r8d, 63734943h
0x18006228d  call    cs:__imp_ExAllocatePool2
0x180062294  nop     dword ptr [rax+rax+00h]
0x180062299  mov     rdi, rax
0x18006229c  test    rax, rax
0x18006229f  jnz     short loc_1800622AB
0x1800622a1  mov     ebx, 0C0000017h
0x1800622a6  jmp     loc_18006234D
0x1800622ab  mov     rdx, [rbp+SourceString+8]; SourceString
0x1800622af  lea     rcx, [rax+20h]; DestinationString
0x1800622b3  mov     [rax+10h], r14
0x1800622b7  mov     [rax+18h], sil
0x1800622bb  call    cs:__imp_RtlCreateUnicodeString
0x1800622c2  nop     dword ptr [rax+rax+00h]
0x1800622c7  test    al, al
0x1800622c9  jz      short loc_1800622A1
0x1800622cb  xor     r9d, r9d; Context
0x1800622ce  lea     rdx, CiDebugAuthInitRunOnce; InitFn
0x1800622d5  xor     r8d, r8d; Parameter
0x1800622d8  lea     rcx, RunOnce; RunOnce
0x1800622df  call    cs:__imp_RtlRunOnceExecuteOnce
0x1800622e6  nop     dword ptr [rax+rax+00h]
0x1800622eb  mov     ebx, eax
0x1800622ed  test    eax, eax
0x1800622ef  js      short loc_18006234D
0x1800622f1  lea     rcx, Resource; Resource
0x1800622f8  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x1800622ff  nop     dword ptr [rax+rax+00h]
0x180062304  mov     rax, cs:qword_1800487E8
0x18006230b  lea     rcx, qword_1800487E8
0x180062312  cmp     [rax+8], rcx
0x180062316  jz      short loc_18006231F
0x180062318  mov     ecx, 3
0x18006231d  int     29h; Win8: RtlFailFast(ecx)
0x18006231f  mov     [rdi+8], rcx
0x180062323  lea     rcx, Resource; Resource
0x18006232a  mov     [rdi], rax
0x18006232d  mov     [rax+8], rdi
0x180062331  mov     cs:qword_1800487E8, rdi
0x180062338  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x18006233f  nop     dword ptr [rax+rax+00h]
0x180062344  xor     edi, edi
0x180062346  jmp     short loc_18006234D
0x180062348  mov     ebx, 0C0000148h
0x18006234d  mov     rcx, rdi; P
0x180062350  call    CiDeleteDebugAuth
0x180062355  test    r14, r14
0x180062358  jz      short loc_180062369
0x18006235a  mov     rcx, r14; Object
0x18006235d  call    cs:__imp_ObfDereferenceObject
0x180062364  nop     dword ptr [rax+rax+00h]
0x180062369  mov     rcx, [rbp+var_28]
0x18006236d  call    SbFreePolicy
0x180062372  mov     eax, ebx
0x180062374  add     rsp, 58h
0x180062378  pop     r15
0x18006237a  pop     r14
0x18006237c  pop     rdi
0x18006237d  pop     rsi
0x18006237e  pop     rbx
0x18006237f  pop     rbp
0x180062380  retn
```
