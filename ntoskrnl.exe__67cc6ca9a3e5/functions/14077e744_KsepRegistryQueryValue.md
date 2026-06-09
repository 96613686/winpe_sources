# KsepRegistryQueryValue

- ea: `0x14077e744`
- end: `0x14077e9ac`
- name: `KsepRegistryQueryValue`
- size: `616`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCWSTR SourceString, _DWORD *, void *, unsigned __int64, size_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14097a68c`

## callees

- `0x1403f2d50`
- `0x1404a9424`
- `0x1404adb80`
- `0x140613770`
- `0x1406dab70`
- `0x1406f4480`
- `0x14077e744`

## string_xrefs

- `0x14077e7c0`: `minkernel\ntos\kshim\kseregistry.c`
- `0x14077e810`: `minkernel\ntos\kshim\kseregistry.c`
- `0x14077e868`: `minkernel\ntos\kshim\kseregistry.c`
- `0x14077e8f8`: `minkernel\ntos\kshim\kseregistry.c`

## pseudocode

```c
__int64 __fastcall KsepRegistryQueryValue(
        HANDLE KeyHandle,
        PCWSTR SourceString,
        _DWORD *a3,
        void *a4,
        unsigned __int64 a5,
        size_t *a6)
{
  __int64 v10; // rax
  __int64 v11; // rax
  size_t *v12; // rsi
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
    *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v10) = 263111;
    if ( ((__int64)stru_140E4CF30.StackBase & 4) != 0 )
      RtlAssert("KeyHandle != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x3C7u, 0);
  }
  if ( !a4 )
  {
    v11 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u)
         + 1)
        & 0x3F;
    *(&AlpcpMessageLogLock.Timer.Period + 2 * v11) = -1073740768;
    *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v11) = 263112;
    if ( ((__int64)stru_140E4CF30.StackBase & 4) != 0 )
      RtlAssert("ValueBuffer != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x3C8u, 0);
  }
  v12 = a6;
  if ( !a6 )
  {
    v13 = ((unsigned __int8)_InterlockedExchangeAdd((volatile signed __int32 *)&AlpcpMessageLogLock.Timer.DueTime, 1u)
         + 1)
        & 0x3F;
    *(&AlpcpMessageLogLock.Timer.Period + 2 * v13) = -1073740768;
    *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * v13) = 263113;
    if ( ((__int64)stru_140E4CF30.StackBase & 4) != 0 )
      RtlAssert("ActualLength != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x3C9u, 0);
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
          memmove(a4, v20 + 3, v22);
          *a3 = v20[1];
          *v12 = (unsigned int)v20[2];
        }
        else
        {
          *v12 = v22;
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
      *((_DWORD *)&AlpcpMessageLogLock.Timer.Processor + 2 * (unsigned int)v17) = 263131;
      if ( (StackBase & 4) != 0 )
        RtlAssert("!NT_SUCCESS(Status)", "minkernel\\ntos\\kshim\\kseregistry.c", 0x3DBu, 0);
    }
    return v15;
  }
}

```

## disassembly

```asm
0x14077e744  mov     rax, rsp
0x14077e747  mov     [rax+10h], rbx
0x14077e74b  mov     [rax+18h], rbp
0x14077e74f  push    rsi
0x14077e750  push    rdi
0x14077e751  push    r13
0x14077e753  push    r14
0x14077e755  push    r15
0x14077e757  sub     rsp, 40h
0x14077e75b  mov     dword ptr [rax+8], 0
0x14077e762  mov     r13d, 1
0x14077e768  lea     r15, AlpcpMessageLogLock.Timer.Processor
0x14077e76f  xorps   xmm0, xmm0
0x14077e772  mov     rbx, rdx
0x14077e775  mov     rbp, r9
0x14077e778  mov     r14, r8
0x14077e77b  mov     rdi, rcx
0x14077e77e  lea     edx, [r13+3]
0x14077e782  movups  xmmword ptr [rax-38h], xmm0
0x14077e786  test    rcx, rcx
0x14077e789  jnz     short loc_14077E7D6
0x14077e78b  mov     eax, r13d
0x14077e78e  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, eax
0x14077e796  add     eax, r13d
0x14077e799  mov     r8d, 3C7h; LineNumber
0x14077e79f  and     eax, 3Fh
0x14077e7a2  mov     dword ptr [r15+rax*8+4], 0C0000420h
0x14077e7ab  mov     dword ptr [r15+rax*8], 403C7h
0x14077e7b3  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x14077e7b9  test    dl, al
0x14077e7bb  jz      short loc_14077E7D6
0x14077e7bd  xor     r9d, r9d; MutableMessage
0x14077e7c0  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x14077e7c7  lea     rcx, aKeyhandleNull; "KeyHandle != NULL"
0x14077e7ce  call    RtlAssert
0x14077e7d3  lea     edx, [rdi+4]
0x14077e7d6  test    rbp, rbp
0x14077e7d9  jnz     short loc_14077E823
0x14077e7db  mov     eax, r13d
0x14077e7de  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, eax
0x14077e7e6  add     eax, r13d
0x14077e7e9  mov     r8d, 3C8h; LineNumber
0x14077e7ef  and     eax, 3Fh
0x14077e7f2  mov     dword ptr [r15+rax*8+4], 0C0000420h
0x14077e7fb  mov     dword ptr [r15+rax*8], 403C8h
0x14077e803  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x14077e809  test    dl, al
0x14077e80b  jz      short loc_14077E823
0x14077e80d  xor     r9d, r9d; MutableMessage
0x14077e810  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x14077e817  lea     rcx, aValuebufferNul; "ValueBuffer != NULL"
0x14077e81e  call    RtlAssert
0x14077e823  mov     rsi, [rsp+68h+arg_28]
0x14077e82b  test    rsi, rsi
0x14077e82e  jnz     short loc_14077E87B
0x14077e830  mov     eax, r13d
0x14077e833  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, eax
0x14077e83b  add     eax, r13d
0x14077e83e  lea     edx, [rsi+4]
0x14077e841  and     eax, 3Fh
0x14077e844  mov     r8d, 3C9h; LineNumber
0x14077e84a  mov     dword ptr [r15+rax*8+4], 0C0000420h
0x14077e853  mov     dword ptr [r15+rax*8], 403C9h
0x14077e85b  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x14077e861  test    dl, al
0x14077e863  jz      short loc_14077E87B
0x14077e865  xor     r9d, r9d; MutableMessage
0x14077e868  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x14077e86f  lea     rcx, aActuallengthNu; "ActualLength != NULL"
0x14077e876  call    RtlAssert
0x14077e87b  mov     rdx, rbx; SourceString
0x14077e87e  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14077e883  call    RtlInitUnicodeString
0x14077e888  xor     r9d, r9d; KeyValueInformation
0x14077e88b  lea     rax, [rsp+68h+arg_0]
0x14077e890  mov     [rsp+68h+ResultLength], rax; ResultLength
0x14077e895  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x14077e89a  mov     rcx, rdi; KeyHandle
0x14077e89d  mov     [rsp+68h+Length], 0; Length
0x14077e8a5  lea     r8d, [r9+2]; KeyValueInformationClass
0x14077e8a9  call    ZwQueryValueKey
0x14077e8ae  mov     ebx, eax
0x14077e8b0  cmp     eax, 0C0000023h
0x14077e8b5  jz      short loc_14077E912
0x14077e8b7  test    eax, eax
0x14077e8b9  js      short loc_14077E90B
0x14077e8bb  mov     ecx, r13d
0x14077e8be  lock xadd dword ptr cs:AlpcpMessageLogLock.Timer.DueTime, ecx
0x14077e8c6  mov     eax, dword ptr cs:stru_140E4CF30.StackBase
0x14077e8cc  add     ecx, r13d
0x14077e8cf  and     ecx, 3Fh
0x14077e8d2  mov     r8d, 3DBh; LineNumber
0x14077e8d8  mov     r9d, ecx
0x14077e8db  mov     dword ptr [r15+rcx*8+4], 0C0000420h
0x14077e8e4  mov     ecx, 4
0x14077e8e9  mov     dword ptr [r15+r9*8], 403DBh
0x14077e8f1  test    cl, al
0x14077e8f3  jz      short loc_14077E90B
0x14077e8f5  xor     r9d, r9d; MutableMessage
0x14077e8f8  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x14077e8ff  lea     rcx, aNtSuccessStatu; "!NT_SUCCESS(Status)"
0x14077e906  call    RtlAssert
0x14077e90b  mov     eax, ebx
0x14077e90d  jmp     loc_14077E992
0x14077e912  mov     ecx, [rsp+68h+arg_0]
0x14077e916  call    KsepPoolAllocatePaged
0x14077e91b  mov     rbx, rax
0x14077e91e  test    rax, rax
0x14077e921  jnz     short loc_14077E92A
0x14077e923  mov     eax, 0C0000017h
0x14077e928  jmp     short loc_14077E992
0x14077e92a  lea     rax, [rsp+68h+arg_0]
0x14077e92f  mov     r9, rbx; KeyValueInformation
0x14077e932  mov     [rsp+68h+ResultLength], rax; ResultLength
0x14077e937  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x14077e93c  mov     eax, [rsp+68h+arg_0]
0x14077e940  mov     r8d, 2; KeyValueInformationClass
0x14077e946  mov     rcx, rdi; KeyHandle
0x14077e949  mov     [rsp+68h+Length], eax; Length
0x14077e94d  call    ZwQueryValueKey
0x14077e952  mov     edi, eax
0x14077e954  test    eax, eax
0x14077e956  jnz     short loc_14077E988
0x14077e958  mov     r8d, [rbx+8]; Size
0x14077e95c  cmp     r8, [rsp+68h+arg_20]
0x14077e964  jbe     short loc_14077E970
0x14077e966  mov     [rsi], r8
0x14077e969  mov     edi, 0C0000023h
0x14077e96e  jmp     short loc_14077E988
0x14077e970  lea     rdx, [rbx+0Ch]; Src
0x14077e974  mov     rcx, rbp; void *
0x14077e977  call    memmove
0x14077e97c  mov     eax, [rbx+4]
0x14077e97f  mov     [r14], eax
0x14077e982  mov     eax, [rbx+8]
0x14077e985  mov     [rsi], rax
0x14077e988  mov     rcx, rbx
0x14077e98b  call    KsepPoolFreePaged
0x14077e990  mov     eax, edi
0x14077e992  lea     r11, [rsp+68h+var_28]
0x14077e997  mov     rbx, [r11+38h]
0x14077e99b  mov     rbp, [r11+40h]
0x14077e99f  mov     rsp, r11
0x14077e9a2  pop     r15
0x14077e9a4  pop     r14
0x14077e9a6  pop     r13
0x14077e9a8  pop     rdi
0x14077e9a9  pop     rsi
0x14077e9aa  retn
```
