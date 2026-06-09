# KsepRegistryOpenKey

- ea: `0x1408bfc54`
- end: `0x1408bfd3a`
- name: `KsepRegistryOpenKey`
- size: `230`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1407804c4`
- `0x140c74414`
- `0x140ca9774`

## callees

- `0x1404bd2d0`
- `0x1406191e0`
- `0x1406dd620`
- `0x1408bfc54`
- `0x1408bfd40`
- `0x1408c0758`

## string_xrefs

- `0x140b545b8`: `EnginePath != NULL`
- `0x140b545b1`: `minkernel\ntos\kshim\kseregistry.c`
- `0x140b54605`: `minkernel\ntos\kshim\kseregistry.c`

## pseudocode

```c
__int64 __fastcall KsepRegistryOpenKey(__int64 a1, __int64 a2, HANDLE *a3)
{
  int v6; // eax
  NTSTATUS v7; // ebx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+28h] [rbp-40h]
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-38h] BYREF
  HANDLE KeyHandle; // [rsp+A0h] [rbp+38h] BYREF

  v11 = 0;
  v12 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( !a1 )
  {
    v9 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
    KsepHistoryErrors[2 * v9 + 1] = -1073740768;
    KsepHistoryErrors[2 * v9] = 262564;
    if ( (KsepDebugFlag & 4) != 0 )
      RtlAssert("EnginePath != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x1A4u, 0);
  }
  if ( !a3 )
  {
    v10 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
    KsepHistoryErrors[2 * v10 + 1] = -1073740768;
    KsepHistoryErrors[2 * v10] = 262565;
    if ( (KsepDebugFlag & 4) != 0 )
      RtlAssert("Handle != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x1A5u, 0);
  }
  if ( a2 )
    v6 = KsepStringConcatenate(&v11, a1, a2, 1, v11);
  else
    v6 = KsepStringDuplicate(&v11, a1);
  v7 = v6;
  if ( v6 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v11;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v7 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v7 >= 0 )
    {
      *a3 = KeyHandle;
      _InterlockedIncrement(&dword_140EFE078);
    }
  }
  if ( v12 )
    KsepPoolFreePaged(v12);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1408bfc54  push    rbp
0x1408bfc56  push    rbx
0x1408bfc57  push    rsi
0x1408bfc58  push    rdi
0x1408bfc59  push    r12
0x1408bfc5b  push    r13
0x1408bfc5d  mov     rbp, rsp
0x1408bfc60  sub     rsp, 68h
0x1408bfc64  xor     eax, eax
0x1408bfc66  lea     r12, KsepHistoryErrors
0x1408bfc6d  mov     [rbp+var_48], rax
0x1408bfc71  xorps   xmm0, xmm0
0x1408bfc74  mov     [rbp+var_40], rax
0x1408bfc78  mov     rsi, r8
0x1408bfc7b  mov     [rbp+KeyHandle], rax
0x1408bfc7f  mov     rdi, rdx
0x1408bfc82  lea     r13d, [rax+4]
0x1408bfc86  mov     rbx, rcx
0x1408bfc89  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1408bfc8d  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1408bfc91  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1408bfc95  test    rcx, rcx
0x1408bfc98  jz      loc_140B54576
0x1408bfc9e  test    rsi, rsi
0x1408bfca1  jz      loc_140B545CA
0x1408bfca7  lea     rcx, [rbp+var_48]
0x1408bfcab  mov     rdx, rbx
0x1408bfcae  test    rdi, rdi
0x1408bfcb1  jz      short loc_1408BFD23
0x1408bfcb3  mov     r9d, 1
0x1408bfcb9  mov     r8, rdi
0x1408bfcbc  call    KsepStringConcatenate
0x1408bfcc1  mov     ebx, eax
0x1408bfcc3  test    eax, eax
0x1408bfcc5  js      short loc_1408BFD05
0x1408bfcc7  lea     rax, [rbp+var_48]
0x1408bfccb  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1408bfcd2  xorps   xmm0, xmm0
0x1408bfcd5  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1408bfcd9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1408bfcdd  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1408bfce5  mov     edx, 20019h; DesiredAccess
0x1408bfcea  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1408bfcf1  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1408bfcf5  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1408bfcfa  call    ZwOpenKey
0x1408bfcff  mov     ebx, eax
0x1408bfd01  test    eax, eax
0x1408bfd03  jns     short loc_1408BFD2A
0x1408bfd05  mov     rcx, [rbp+var_40]
0x1408bfd09  test    rcx, rcx
0x1408bfd0c  jz      short loc_1408BFD13
0x1408bfd0e  call    KsepPoolFreePaged
0x1408bfd13  mov     eax, ebx
0x1408bfd15  add     rsp, 68h
0x1408bfd19  pop     r13
0x1408bfd1b  pop     r12
0x1408bfd1d  pop     rdi
0x1408bfd1e  pop     rsi
0x1408bfd1f  pop     rbx
0x1408bfd20  pop     rbp
0x1408bfd21  retn
0x1408bfd23  call    KsepStringDuplicate
0x1408bfd28  jmp     short loc_1408BFCC1
0x1408bfd2a  mov     rax, [rbp+KeyHandle]
0x1408bfd2e  mov     [rsi], rax
0x1408bfd31  lock inc cs:dword_140EFE078
0x1408bfd38  jmp     short loc_1408BFD05
0x140b54576  mov     eax, 1
0x140b5457b  lock xadd cs:KsepHistoryErrorsIndex, eax
0x140b54583  inc     eax
0x140b54585  mov     r8d, 1A4h; LineNumber
0x140b5458b  and     eax, 3Fh
0x140b5458e  mov     dword ptr [r12+rax*8+4], 0C0000420h
0x140b54597  mov     dword ptr [r12+rax*8], 401A4h
0x140b5459f  mov     eax, cs:KsepDebugFlag
0x140b545a5  test    r13b, al
0x140b545a8  jz      loc_1408BFC9E
0x140b545ae  xor     r9d, r9d; MutableMessage
0x140b545b1  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140b545b8  lea     rcx, aEnginepathNull; "EnginePath != NULL"
0x140b545bf  call    RtlAssert
0x140b545c4  nop
0x140b545c5  jmp     loc_1408BFC9E
0x140b545ca  mov     eax, 1
0x140b545cf  lock xadd cs:KsepHistoryErrorsIndex, eax
0x140b545d7  inc     eax
0x140b545d9  mov     r8d, 1A5h; LineNumber
0x140b545df  and     eax, 3Fh
0x140b545e2  mov     dword ptr [r12+rax*8+4], 0C0000420h
0x140b545eb  mov     dword ptr [r12+rax*8], 401A5h
0x140b545f3  mov     eax, cs:KsepDebugFlag
0x140b545f9  test    r13b, al
0x140b545fc  jz      loc_1408BFCA7
0x140b54602  xor     r9d, r9d; MutableMessage
0x140b54605  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140b5460c  lea     rcx, aHandleNull; "Handle != NULL"
0x140b54613  call    RtlAssert
0x140b54618  nop
0x140b54619  jmp     loc_1408BFCA7
```
