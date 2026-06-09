# KsepRegistryQueryValue

- ea: `0x140782bb4`
- end: `0x140782e1c`
- name: `KsepRegistryQueryValue`
- size: `616`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCWSTR SourceString, _DWORD *, void *, unsigned __int64, size_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1408c04bc`

## callees

- `0x140403380`
- `0x1404b8304`
- `0x1404bd2d0`
- `0x1406191e0`
- `0x1406dd6c0`
- `0x1406f6f80`
- `0x140782bb4`

## string_xrefs

- `0x140782c30`: `minkernel\ntos\kshim\kseregistry.c`
- `0x140782c80`: `minkernel\ntos\kshim\kseregistry.c`
- `0x140782cd8`: `minkernel\ntos\kshim\kseregistry.c`
- `0x140782d68`: `minkernel\ntos\kshim\kseregistry.c`

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
  char v16; // al
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
    v10 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
    KsepHistoryErrors[2 * v10 + 1] = -1073740768;
    KsepHistoryErrors[2 * v10] = 263111;
    if ( (KsepDebugFlag & 4) != 0 )
      RtlAssert("KeyHandle != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x3C7u, 0);
  }
  if ( !a4 )
  {
    v11 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
    KsepHistoryErrors[2 * v11 + 1] = -1073740768;
    KsepHistoryErrors[2 * v11] = 263112;
    if ( (KsepDebugFlag & 4) != 0 )
      RtlAssert("ValueBuffer != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x3C8u, 0);
  }
  v12 = a6;
  if ( !a6 )
  {
    v13 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
    KsepHistoryErrors[2 * v13 + 1] = -1073740768;
    KsepHistoryErrors[2 * v13] = 263113;
    if ( (KsepDebugFlag & 4) != 0 )
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
      v16 = KsepDebugFlag;
      v17 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
      KsepHistoryErrors[2 * v17 + 1] = -1073740768;
      KsepHistoryErrors[2 * (unsigned int)v17] = 263131;
      if ( (v16 & 4) != 0 )
        RtlAssert("!NT_SUCCESS(Status)", "minkernel\\ntos\\kshim\\kseregistry.c", 0x3DBu, 0);
    }
    return v15;
  }
}

```

## disassembly

```asm
0x140782bb4  mov     rax, rsp
0x140782bb7  mov     [rax+10h], rbx
0x140782bbb  mov     [rax+18h], rbp
0x140782bbf  push    rsi
0x140782bc0  push    rdi
0x140782bc1  push    r13
0x140782bc3  push    r14
0x140782bc5  push    r15
0x140782bc7  sub     rsp, 40h
0x140782bcb  mov     dword ptr [rax+8], 0
0x140782bd2  mov     r13d, 1
0x140782bd8  lea     r15, KsepHistoryErrors
0x140782bdf  xorps   xmm0, xmm0
0x140782be2  mov     rbx, rdx
0x140782be5  mov     rbp, r9
0x140782be8  mov     r14, r8
0x140782beb  mov     rdi, rcx
0x140782bee  lea     edx, [r13+3]
0x140782bf2  movups  xmmword ptr [rax-38h], xmm0
0x140782bf6  test    rcx, rcx
0x140782bf9  jnz     short loc_140782C46
0x140782bfb  mov     eax, r13d
0x140782bfe  lock xadd cs:KsepHistoryErrorsIndex, eax
0x140782c06  add     eax, r13d
0x140782c09  mov     r8d, 3C7h; LineNumber
0x140782c0f  and     eax, 3Fh
0x140782c12  mov     dword ptr [r15+rax*8+4], 0C0000420h
0x140782c1b  mov     dword ptr [r15+rax*8], 403C7h
0x140782c23  mov     eax, cs:KsepDebugFlag
0x140782c29  test    dl, al
0x140782c2b  jz      short loc_140782C46
0x140782c2d  xor     r9d, r9d; MutableMessage
0x140782c30  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140782c37  lea     rcx, aKeyhandleNull; "KeyHandle != NULL"
0x140782c3e  call    RtlAssert
0x140782c43  lea     edx, [rdi+4]
0x140782c46  test    rbp, rbp
0x140782c49  jnz     short loc_140782C93
0x140782c4b  mov     eax, r13d
0x140782c4e  lock xadd cs:KsepHistoryErrorsIndex, eax
0x140782c56  add     eax, r13d
0x140782c59  mov     r8d, 3C8h; LineNumber
0x140782c5f  and     eax, 3Fh
0x140782c62  mov     dword ptr [r15+rax*8+4], 0C0000420h
0x140782c6b  mov     dword ptr [r15+rax*8], 403C8h
0x140782c73  mov     eax, cs:KsepDebugFlag
0x140782c79  test    dl, al
0x140782c7b  jz      short loc_140782C93
0x140782c7d  xor     r9d, r9d; MutableMessage
0x140782c80  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140782c87  lea     rcx, aValuebufferNul; "ValueBuffer != NULL"
0x140782c8e  call    RtlAssert
0x140782c93  mov     rsi, [rsp+68h+arg_28]
0x140782c9b  test    rsi, rsi
0x140782c9e  jnz     short loc_140782CEB
0x140782ca0  mov     eax, r13d
0x140782ca3  lock xadd cs:KsepHistoryErrorsIndex, eax
0x140782cab  add     eax, r13d
0x140782cae  lea     edx, [rsi+4]
0x140782cb1  and     eax, 3Fh
0x140782cb4  mov     r8d, 3C9h; LineNumber
0x140782cba  mov     dword ptr [r15+rax*8+4], 0C0000420h
0x140782cc3  mov     dword ptr [r15+rax*8], 403C9h
0x140782ccb  mov     eax, cs:KsepDebugFlag
0x140782cd1  test    dl, al
0x140782cd3  jz      short loc_140782CEB
0x140782cd5  xor     r9d, r9d; MutableMessage
0x140782cd8  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140782cdf  lea     rcx, aActuallengthNu; "ActualLength != NULL"
0x140782ce6  call    RtlAssert
0x140782ceb  mov     rdx, rbx; SourceString
0x140782cee  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140782cf3  call    RtlInitUnicodeString
0x140782cf8  xor     r9d, r9d; KeyValueInformation
0x140782cfb  lea     rax, [rsp+68h+arg_0]
0x140782d00  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140782d05  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x140782d0a  mov     rcx, rdi; KeyHandle
0x140782d0d  mov     [rsp+68h+Length], 0; Length
0x140782d15  lea     r8d, [r9+2]; KeyValueInformationClass
0x140782d19  call    ZwQueryValueKey
0x140782d1e  mov     ebx, eax
0x140782d20  cmp     eax, 0C0000023h
0x140782d25  jz      short loc_140782D82
0x140782d27  test    eax, eax
0x140782d29  js      short loc_140782D7B
0x140782d2b  mov     ecx, r13d
0x140782d2e  lock xadd cs:KsepHistoryErrorsIndex, ecx
0x140782d36  mov     eax, cs:KsepDebugFlag
0x140782d3c  add     ecx, r13d
0x140782d3f  and     ecx, 3Fh
0x140782d42  mov     r8d, 3DBh; LineNumber
0x140782d48  mov     r9d, ecx
0x140782d4b  mov     dword ptr [r15+rcx*8+4], 0C0000420h
0x140782d54  mov     ecx, 4
0x140782d59  mov     dword ptr [r15+r9*8], 403DBh
0x140782d61  test    cl, al
0x140782d63  jz      short loc_140782D7B
0x140782d65  xor     r9d, r9d; MutableMessage
0x140782d68  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140782d6f  lea     rcx, aNtSuccessStatu; "!NT_SUCCESS(Status)"
0x140782d76  call    RtlAssert
0x140782d7b  mov     eax, ebx
0x140782d7d  jmp     loc_140782E02
0x140782d82  mov     ecx, [rsp+68h+arg_0]
0x140782d86  call    KsepPoolAllocatePaged
0x140782d8b  mov     rbx, rax
0x140782d8e  test    rax, rax
0x140782d91  jnz     short loc_140782D9A
0x140782d93  mov     eax, 0C0000017h
0x140782d98  jmp     short loc_140782E02
0x140782d9a  lea     rax, [rsp+68h+arg_0]
0x140782d9f  mov     r9, rbx; KeyValueInformation
0x140782da2  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140782da7  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x140782dac  mov     eax, [rsp+68h+arg_0]
0x140782db0  mov     r8d, 2; KeyValueInformationClass
0x140782db6  mov     rcx, rdi; KeyHandle
0x140782db9  mov     [rsp+68h+Length], eax; Length
0x140782dbd  call    ZwQueryValueKey
0x140782dc2  mov     edi, eax
0x140782dc4  test    eax, eax
0x140782dc6  jnz     short loc_140782DF8
0x140782dc8  mov     r8d, [rbx+8]; Size
0x140782dcc  cmp     r8, [rsp+68h+arg_20]
0x140782dd4  jbe     short loc_140782DE0
0x140782dd6  mov     [rsi], r8
0x140782dd9  mov     edi, 0C0000023h
0x140782dde  jmp     short loc_140782DF8
0x140782de0  lea     rdx, [rbx+0Ch]; Src
0x140782de4  mov     rcx, rbp; void *
0x140782de7  call    memmove
0x140782dec  mov     eax, [rbx+4]
0x140782def  mov     [r14], eax
0x140782df2  mov     eax, [rbx+8]
0x140782df5  mov     [rsi], rax
0x140782df8  mov     rcx, rbx
0x140782dfb  call    KsepPoolFreePaged
0x140782e00  mov     eax, edi
0x140782e02  lea     r11, [rsp+68h+var_28]
0x140782e07  mov     rbx, [r11+38h]
0x140782e0b  mov     rbp, [r11+40h]
0x140782e0f  mov     rsp, r11
0x140782e12  pop     r15
0x140782e14  pop     r14
0x140782e16  pop     r13
0x140782e18  pop     rdi
0x140782e19  pop     rsi
0x140782e1a  retn
```
