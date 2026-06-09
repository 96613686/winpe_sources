# KsepRegistryQuerySZ

- ea: `0x140782940`
- end: `0x140782bac`
- name: `KsepRegistryQuerySZ`
- size: `620`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PCWSTR SourceString@<rdx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140782910`
- `0x1408bee84`
- `0x140c74414`

## callees

- `0x140403380`
- `0x1404b8304`
- `0x1404bd2d0`
- `0x1406191e0`
- `0x1406dd6c0`
- `0x1406f6f80`
- `0x140782940`

## string_xrefs

- `0x1407829bc`: `minkernel\ntos\kshim\kseregistry.c`
- `0x140782a0c`: `minkernel\ntos\kshim\kseregistry.c`
- `0x140782a64`: `minkernel\ntos\kshim\kseregistry.c`
- `0x140782af4`: `minkernel\ntos\kshim\kseregistry.c`

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
    KsepHistoryErrors[2 * v10] = 262991;
    if ( (KsepDebugFlag & 4) != 0 )
      RtlAssert("KeyHandle != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x34Fu, 0);
  }
  if ( !a4 )
  {
    v11 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
    KsepHistoryErrors[2 * v11 + 1] = -1073740768;
    KsepHistoryErrors[2 * v11] = 262992;
    if ( (KsepDebugFlag & 4) != 0 )
      RtlAssert("ValueBuffer != NULL", "minkernel\\ntos\\kshim\\kseregistry.c", 0x350u, 0);
  }
  v12 = a6;
  if ( !a6 )
  {
    v13 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
    KsepHistoryErrors[2 * v13 + 1] = -1073740768;
    KsepHistoryErrors[2 * v13] = 262993;
    if ( (KsepDebugFlag & 4) != 0 )
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
      v16 = KsepDebugFlag;
      v17 = ((unsigned __int8)_InterlockedExchangeAdd(&KsepHistoryErrorsIndex, 1u) + 1) & 0x3F;
      KsepHistoryErrors[2 * v17 + 1] = -1073740768;
      KsepHistoryErrors[2 * (unsigned int)v17] = 263011;
      if ( (v16 & 4) != 0 )
        RtlAssert("!NT_SUCCESS(Status)", "minkernel\\ntos\\kshim\\kseregistry.c", 0x363u, 0);
    }
    return v15;
  }
}

```

## disassembly

```asm
0x140782940  mov     rax, rsp
0x140782943  mov     [rax+10h], rbx
0x140782947  mov     [rax+18h], rbp
0x14078294b  push    rsi
0x14078294c  push    rdi
0x14078294d  push    r13
0x14078294f  push    r14
0x140782951  push    r15
0x140782953  sub     rsp, 40h
0x140782957  mov     dword ptr [rax+8], 0
0x14078295e  mov     r13d, 1
0x140782964  lea     r15, KsepHistoryErrors
0x14078296b  xorps   xmm0, xmm0
0x14078296e  mov     rbx, rdx
0x140782971  mov     rbp, r9
0x140782974  mov     r14d, r8d
0x140782977  mov     rdi, rcx
0x14078297a  lea     edx, [r13+3]
0x14078297e  movups  xmmword ptr [rax-38h], xmm0
0x140782982  test    rcx, rcx
0x140782985  jnz     short loc_1407829D2
0x140782987  mov     eax, r13d
0x14078298a  lock xadd cs:KsepHistoryErrorsIndex, eax
0x140782992  add     eax, r13d
0x140782995  mov     r8d, 34Fh; LineNumber
0x14078299b  and     eax, 3Fh
0x14078299e  mov     dword ptr [r15+rax*8+4], 0C0000420h
0x1407829a7  mov     dword ptr [r15+rax*8], 4034Fh
0x1407829af  mov     eax, cs:KsepDebugFlag
0x1407829b5  test    dl, al
0x1407829b7  jz      short loc_1407829D2
0x1407829b9  xor     r9d, r9d; MutableMessage
0x1407829bc  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x1407829c3  lea     rcx, aKeyhandleNull; "KeyHandle != NULL"
0x1407829ca  call    RtlAssert
0x1407829cf  lea     edx, [rdi+4]
0x1407829d2  test    rbp, rbp
0x1407829d5  jnz     short loc_140782A1F
0x1407829d7  mov     eax, r13d
0x1407829da  lock xadd cs:KsepHistoryErrorsIndex, eax
0x1407829e2  add     eax, r13d
0x1407829e5  mov     r8d, 350h; LineNumber
0x1407829eb  and     eax, 3Fh
0x1407829ee  mov     dword ptr [r15+rax*8+4], 0C0000420h
0x1407829f7  mov     dword ptr [r15+rax*8], 40350h
0x1407829ff  mov     eax, cs:KsepDebugFlag
0x140782a05  test    dl, al
0x140782a07  jz      short loc_140782A1F
0x140782a09  xor     r9d, r9d; MutableMessage
0x140782a0c  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140782a13  lea     rcx, aValuebufferNul; "ValueBuffer != NULL"
0x140782a1a  call    RtlAssert
0x140782a1f  mov     rsi, [rsp+68h+arg_28]
0x140782a27  test    rsi, rsi
0x140782a2a  jnz     short loc_140782A77
0x140782a2c  mov     eax, r13d
0x140782a2f  lock xadd cs:KsepHistoryErrorsIndex, eax
0x140782a37  add     eax, r13d
0x140782a3a  lea     edx, [rsi+4]
0x140782a3d  and     eax, 3Fh
0x140782a40  mov     r8d, 351h; LineNumber
0x140782a46  mov     dword ptr [r15+rax*8+4], 0C0000420h
0x140782a4f  mov     dword ptr [r15+rax*8], 40351h
0x140782a57  mov     eax, cs:KsepDebugFlag
0x140782a5d  test    dl, al
0x140782a5f  jz      short loc_140782A77
0x140782a61  xor     r9d, r9d; MutableMessage
0x140782a64  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140782a6b  lea     rcx, aActuallengthNu; "ActualLength != NULL"
0x140782a72  call    RtlAssert
0x140782a77  mov     rdx, rbx; SourceString
0x140782a7a  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140782a7f  call    RtlInitUnicodeString
0x140782a84  xor     r9d, r9d; KeyValueInformation
0x140782a87  lea     rax, [rsp+68h+arg_0]
0x140782a8c  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140782a91  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x140782a96  mov     rcx, rdi; KeyHandle
0x140782a99  mov     [rsp+68h+Length], 0; Length
0x140782aa1  lea     r8d, [r9+2]; KeyValueInformationClass
0x140782aa5  call    ZwQueryValueKey
0x140782aaa  mov     ebx, eax
0x140782aac  cmp     eax, 0C0000023h
0x140782ab1  jz      short loc_140782B0E
0x140782ab3  test    eax, eax
0x140782ab5  js      short loc_140782B07
0x140782ab7  mov     ecx, r13d
0x140782aba  lock xadd cs:KsepHistoryErrorsIndex, ecx
0x140782ac2  mov     eax, cs:KsepDebugFlag
0x140782ac8  add     ecx, r13d
0x140782acb  and     ecx, 3Fh
0x140782ace  mov     r8d, 363h; LineNumber
0x140782ad4  mov     r9d, ecx
0x140782ad7  mov     dword ptr [r15+rcx*8+4], 0C0000420h
0x140782ae0  mov     ecx, 4
0x140782ae5  mov     dword ptr [r15+r9*8], 40363h
0x140782aed  test    cl, al
0x140782aef  jz      short loc_140782B07
0x140782af1  xor     r9d, r9d; MutableMessage
0x140782af4  lea     rdx, aMinkernelNtosK_3; "minkernel\\ntos\\kshim\\kseregistry.c"
0x140782afb  lea     rcx, aNtSuccessStatu; "!NT_SUCCESS(Status)"
0x140782b02  call    RtlAssert
0x140782b07  mov     eax, ebx
0x140782b09  jmp     loc_140782B92
0x140782b0e  mov     ecx, [rsp+68h+arg_0]
0x140782b12  call    KsepPoolAllocatePaged
0x140782b17  mov     rbx, rax
0x140782b1a  test    rax, rax
0x140782b1d  jnz     short loc_140782B26
0x140782b1f  mov     eax, 0C0000017h
0x140782b24  jmp     short loc_140782B92
0x140782b26  lea     rax, [rsp+68h+arg_0]
0x140782b2b  mov     r9, rbx; KeyValueInformation
0x140782b2e  mov     [rsp+68h+ResultLength], rax; ResultLength
0x140782b33  lea     rdx, [rsp+68h+DestinationString]; ValueName
0x140782b38  mov     eax, [rsp+68h+arg_0]
0x140782b3c  mov     r8d, 2; KeyValueInformationClass
0x140782b42  mov     rcx, rdi; KeyHandle
0x140782b45  mov     [rsp+68h+Length], eax; Length
0x140782b49  call    ZwQueryValueKey
0x140782b4e  mov     edi, eax
0x140782b50  test    eax, eax
0x140782b52  jnz     short loc_140782B88
0x140782b54  mov     r8d, [rbx+8]; Size
0x140782b58  cmp     r8, [rsp+68h+arg_20]
0x140782b60  jbe     short loc_140782B69
0x140782b62  mov     edi, 0C0000023h
0x140782b67  jmp     short loc_140782B88
0x140782b69  cmp     [rbx+4], r14d
0x140782b6d  jz      short loc_140782B76
0x140782b6f  mov     edi, 0C0000024h
0x140782b74  jmp     short loc_140782B88
0x140782b76  lea     rdx, [rbx+0Ch]; Src
0x140782b7a  mov     rcx, rbp; void *
0x140782b7d  call    memmove
0x140782b82  mov     eax, [rbx+8]
0x140782b85  mov     [rsi], rax
0x140782b88  mov     rcx, rbx
0x140782b8b  call    KsepPoolFreePaged
0x140782b90  mov     eax, edi
0x140782b92  lea     r11, [rsp+68h+var_28]
0x140782b97  mov     rbx, [r11+38h]
0x140782b9b  mov     rbp, [r11+40h]
0x140782b9f  mov     rsp, r11
0x140782ba2  pop     r15
0x140782ba4  pop     r14
0x140782ba6  pop     r13
0x140782ba8  pop     rdi
0x140782ba9  pop     rsi
0x140782baa  retn
```
