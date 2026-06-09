# KsepRegistryQuerySZ

- ea: `0x14077e4d0`
- end: `0x14077e73c`
- name: `KsepRegistryQuerySZ`
- size: `620`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCWSTR SourceString, int, void *, unsigned __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14077e4a0`
- `0x1409790bc`
- `0x140c6f164`

## callees

- `0x1403f2d50`
- `0x1404a9424`
- `0x1404adb80`
- `0x140613770`
- `0x1406dab70`
- `0x1406f4480`
- `0x14077e4d0`

## string_xrefs

- `0x14077e54c`: `minkernel\ntos\kshim\kseregistry.c`
- `0x14077e59c`: `minkernel\ntos\kshim\kseregistry.c`
- `0x14077e5f4`: `minkernel\ntos\kshim\kseregistry.c`
- `0x14077e684`: `minkernel\ntos\kshim\kseregistry.c`

## pseudocode

```c
__int64 __fastcall KsepRegistryQuerySZ(
        HANDLE KeyHandle,
        PCWSTR SourceString,
        int a3,
        void *a4,
        unsigned __int64 a5,
        _QWORD *a6)
{
  __int64 v10; // rax
  __int64 v11; // rax
  _QWORD *v12; // rsi
  __int64 v13; // rax
  NTSTATUS v14; // eax
  unsigned int v15; // ebx
  char StackBase; // al
  __int64 v17; // rcx
  _DWORD *Paged; // rax
  _DWORD *v20; // rbx
  unsigned int v21; // edi
  size_t v22; // r8
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp+8h] BYREF

  ResultLength = 0;
  DestinationString = 0;
  if ( !KeyHandle )
  {
    v10 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u)
         + 1)
        & 0x3F;
    *(&AlpcpMessageLogLock.Timer.Period + 2 * v10) = -1073740768;
    *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v10) = 262991;
    if ( ((__int64)stru_140E4CF30.StackBase & 4) != 0 )
      RtlAssert("KeyHandle != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x34Fu, 0);
  }
  if ( !a4 )
  {
    v11 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u)
         + 1)
        & 0x3F;
    *(&AlpcpMessageLogLock.Timer.Period + 2 * v11) = -1073740768;
    *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v11) = 262992;
    if ( ((__int64)stru_140E4CF30.StackBase & 4) != 0 )
      RtlAssert("ValueBuffer != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x350u, 0);
  }
  v12 = a6;
  if ( !a6 )
  {
    v13 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u)
         + 1)
        & 0x3F;
    *(&AlpcpMessageLogLock.Timer.Period + 2 * v13) = -1073740768;
    *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v13) = 262993;
    if ( ((__int64)stru_140E4CF30.StackBase & 4) != 0 )
      RtlAssert("ActualLength != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x351u, 0);
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  v14 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength);
  v15 = v14;
  if ( v14 == -1073741789 )
  {
    Paged = (_DWORD *)KsepPoolAllocatePaged(ResultLength);
    v20 = Paged;
    if ( Paged )
    {
      v21 = ZwQueryValueKey(
              KeyHandle,
              &DestinationString,
              KeyValuePartialInformation,
              Paged,
              ResultLength,
              &ResultLength);
      if ( !v21 )
      {
        v22 = (unsigned int)v20[2];
        if ( v22 <= a5 )
        {
          if ( v20[1] == a3 )
          {
            memmove(a4, v20 + 3, v22);
            *v12 = (unsigned int)v20[2];
          }
          else
          {
            v21 = -1073741788;
          }
        }
        else
        {
          v21 = -1073741789;
        }
      }
      KsepPoolFreePaged(v20);
      return v21;
    }
    else
    {
      return 3221225495LL;
    }
  }
  else
  {
    if ( v14 >= 0 )
    {
      StackBase = (char)stru_140E4CF30.StackBase;
      v17 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u)
           + 1)
          & 0x3F;
      *(&AlpcpMessageLogLock.Timer.Period + 2 * v17) = -1073740768;
      *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * (unsigned int)v17) = 263011;
      if ( (StackBase & 4) != 0 )
        RtlAssert("!NT_SUCCESS(Status)", "minkernel\\ntos\\kshim\\kseregistry.c", 0x363u, 0);
    }
    return v15;
  }
}

```

## disassembly

```asm
0x14077e4d0  mov     rax, rsp
0x14077e4d3  mov     [rax+10h], rbx
0x14077e4d7  mov     [rax+18h], rbp
0x14077e4db  push    rsi
0x14077e4dc  push    rdi
0x14077e4dd  push    r13
0x14077e4df  push    r14
0x14077e4e1  push    r15
0x14077e4e3  sub     rsp, 40h
0x14077e4e7  mov     dword ptr [rax+8], 0
0x14077e4ee  mov     r13d, 1
0x14077e4f4  lea     r15, AlpcpMessageLogLock.Timer.Processor
0x14077e4fb  xorps   xmm0, xmm0
0x14077e4fe  mov     rbx, rdx
0x14077e501  mov     rbp, r9
0x14077e504  mov     r14d, r8d
0x14077e507  mov     rdi, rcx
0x14077e50a  lea     edx, [r13+3]
0x14077e50e  movups  xmmword ptr [rax-38h], xmm0
0x14077e512  test    rcx, rcx
0x14077e515  jnz     short loc_14077E562
0x14077e517  mov     eax, r13d
0x14077e51a  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, eax
0x14077e522  add     eax, r13d
0x14077e525  mov     r8d, 34Fh; LineNumber
0x14077e52b  and     eax, 3Fh
0x14077e52e  mov     dword ptr [r15+rax*8+4], 0C0000420h
0x14077e537  mov     dword ptr [r15+rax*8], 4034Fh
0x14077e53f  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x14077e545  test    dl, al
0x14077e547  jz      short loc_14077E562
0x14077e549  xor     r9d, r9d; MutableMessage
0x14077e54c  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x14077e553  lea     rcx, aKeyhandleNull; "KeyHandle != NULL"
0x14077e55a  call    RtlAssert
0x14077e55f  lea     edx, [rdi+4]
0x14077e562  test    rbp, rbp
0x14077e565  jnz     short loc_14077E5AF
0x14077e567  mov     eax, r13d
0x14077e56a  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, eax
0x14077e572  add     eax, r13d
0x14077e575  mov     r8d, 350h; LineNumber
0x14077e57b  and     eax, 3Fh
0x14077e57e  mov     dword ptr [r15+rax*8+4], 0C0000420h
0x14077e587  mov     dword ptr [r15+rax*8], 40350h
0x14077e58f  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x14077e595  test    dl, al
0x14077e597  jz      short loc_14077E5AF
0x14077e599  xor     r9d, r9d; MutableMessage
0x14077e59c  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x14077e5a3  lea     rcx, aValuebufferNul; "ValueBuffer != NULL"
0x14077e5aa  call    RtlAssert
0x14077e5af  mov     rsi, [rsp+68h+arg_28]
0x14077e5b7  test    rsi, rsi
0x14077e5ba  jnz     short loc_14077E607
0x14077e5bc  mov     eax, r13d
0x14077e5bf  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, eax
0x14077e5c7  add     eax, r13d
0x14077e5ca  lea     edx, [rsi+4]
0x14077e5cd  and     eax, 3Fh
0x14077e5d0  mov     r8d, 351h; LineNumber
0x14077e5d6  mov     dword ptr [r15+rax*8+4], 0C0000420h
0x14077e5df  mov     dword ptr [r15+rax*8], 40351h
0x14077e5e7  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x14077e5ed  test    dl, al
0x14077e5ef  jz      short loc_14077E607
0x14077e5f1  xor     r9d, r9d; MutableMessage
0x14077e5f4  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x14077e5fb  lea     rcx, aActuallengthNu; "ActualLength != NULL"
0x14077e602  call    RtlAssert
0x14077e607  mov     rdx, rbx; SourceString
0x14077e60a  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14077e60f  call    RtlInitUnicodeString
0x14077e614  xor     r9d, r9d; KeyValueInformation
0x14077e617  lea     rax, [rsp+68h+arg_0]
0x14077e61c  mov     [rsp+68h+ResultLength], rax; ResultLength
0x14077e621  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x14077e626  mov     rcx, rdi; KeyHandle
0x14077e629  mov     [rsp+68h+Length], 0; Length
0x14077e631  lea     r8d, [r9+2]; KeyValueInformationClass
0x14077e635  call    ZwQueryValueKey
0x14077e63a  mov     ebx, eax
0x14077e63c  cmp     eax, 0C0000023h
0x14077e641  jz      short loc_14077E69E
0x14077e643  test    eax, eax
0x14077e645  js      short loc_14077E697
0x14077e647  mov     ecx, r13d
0x14077e64a  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, ecx
0x14077e652  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x14077e658  add     ecx, r13d
0x14077e65b  and     ecx, 3Fh
0x14077e65e  mov     r8d, 363h; LineNumber
0x14077e664  mov     r9d, ecx
0x14077e667  mov     dword ptr [r15+rcx*8+4], 0C0000420h
0x14077e670  mov     ecx, 4
0x14077e675  mov     dword ptr [r15+r9*8], 40363h
0x14077e67d  test    cl, al
0x14077e67f  jz      short loc_14077E697
0x14077e681  xor     r9d, r9d; MutableMessage
0x14077e684  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x14077e68b  lea     rcx, aNtSuccessStatu; "!NT_SUCCESS(Status)"
0x14077e692  call    RtlAssert
0x14077e697  mov     eax, ebx
0x14077e699  jmp     loc_14077E722
0x14077e69e  mov     ecx, [rsp+68h+arg_0]
0x14077e6a2  call    KsepPoolAllocatePaged
0x14077e6a7  mov     rbx, rax
0x14077e6aa  test    rax, rax
0x14077e6ad  jnz     short loc_14077E6B6
0x14077e6af  mov     eax, 0C0000017h
0x14077e6b4  jmp     short loc_14077E722
0x14077e6b6  lea     rax, [rsp+68h+arg_0]
0x14077e6bb  mov     r9, rbx; KeyValueInformation
0x14077e6be  mov     [rsp+68h+ResultLength], rax; ResultLength
0x14077e6c3  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x14077e6c8  mov     eax, [rsp+68h+arg_0]
0x14077e6cc  mov     r8d, 2; KeyValueInformationClass
0x14077e6d2  mov     rcx, rdi; KeyHandle
0x14077e6d5  mov     [rsp+68h+Length], eax; Length
0x14077e6d9  call    ZwQueryValueKey
0x14077e6de  mov     edi, eax
0x14077e6e0  test    eax, eax
0x14077e6e2  jnz     short loc_14077E718
0x14077e6e4  mov     r8d, [rbx+8]; Size
0x14077e6e8  cmp     r8, [rsp+68h+arg_20]
0x14077e6f0  jbe     short loc_14077E6F9
0x14077e6f2  mov     edi, 0C0000023h
0x14077e6f7  jmp     short loc_14077E718
0x14077e6f9  cmp     [rbx+4], r14d
0x14077e6fd  jz      short loc_14077E706
0x14077e6ff  mov     edi, 0C0000024h
0x14077e704  jmp     short loc_14077E718
0x14077e706  lea     rdx, [rbx+0Ch]; Src
0x14077e70a  mov     rcx, rbp; void *
0x14077e70d  call    memmove
0x14077e712  mov     eax, [rbx+8]
0x14077e715  mov     [rsi], rax
0x14077e718  mov     rcx, rbx
0x14077e71b  call    KsepPoolFreePaged
0x14077e720  mov     eax, edi
0x14077e722  lea     r11, [rsp+68h+var_28]
0x14077e727  mov     rbx, [r11+38h]
0x14077e72b  mov     rbp, [r11+40h]
0x14077e72f  mov     rsp, r11
0x14077e732  pop     r15
0x14077e734  pop     r14
0x14077e736  pop     r13
0x14077e738  pop     rdi
0x14077e739  pop     rsi
0x14077e73a  retn
```
