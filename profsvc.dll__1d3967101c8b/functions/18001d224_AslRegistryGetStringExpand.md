# AslRegistryGetStringExpand

- ea: `0x18001d224`
- end: `0x18001d69e`
- name: `AslRegistryGetStringExpand`
- size: `1146`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001b710`

## callees

- `0x18001d03c`
- `0x18001d224`
- `0x18001d6a4`
- `0x18001d8a4`
- `0x180035ea4`
- `0x18003a730`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001d362`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001d362`
- `ntdll!RtlInitUnicodeString` at `0x18001d268`
- `ntdll!RtlInitUnicodeString` at `0x18001d268`
- `ntdll!RtlAllocateHeap` at `0x18001d2ba`
- `ntdll!RtlAllocateHeap` at `0x18001d3e3`
- `ntdll!RtlAllocateHeap` at `0x18001d538`
- `ntdll!RtlAllocateHeap` at `0x18001d2ba`
- `ntdll!RtlAllocateHeap` at `0x18001d3e3`
- `ntdll!RtlAllocateHeap` at `0x18001d538`
- `ntdll!RtlFreeHeap` at `0x18001d34c`
- `ntdll!RtlFreeHeap` at `0x18001d49e`
- `ntdll!RtlFreeHeap` at `0x18001d518`
- `ntdll!RtlFreeHeap` at `0x18001d34c`
- `ntdll!RtlFreeHeap` at `0x18001d49e`
- `ntdll!RtlFreeHeap` at `0x18001d518`
- `ntdll!RtlGetNativeSystemInformation` at `0x18001d38f`
- `ntdll!RtlGetNativeSystemInformation` at `0x18001d38f`
- `ntdll!ZwQuerySystemInformation` at `0x18001d3b2`
- `ntdll!ZwQuerySystemInformation` at `0x18001d3b2`
- `ntdll!ZwQueryValueKey` at `0x18001d289`
- `ntdll!ZwQueryValueKey` at `0x18001d2ec`
- `ntdll!ZwQueryValueKey` at `0x18001d289`
- `ntdll!ZwQueryValueKey` at `0x18001d2ec`

## string_xrefs

- `0x18001d470`: `AslRegistryGetString`
- `0x18001d4ba`: `AslRegistryGetString`
- `0x18001d569`: `AslRegistryGetString`
- `0x18001d58a`: `AslRegistryGetString`
- `0x18001d5b2`: `AslRegistryGetString`
- `0x18001d3fe`: `AslRegistryGetStringExpand`
- `0x18001d60b`: `AslRegistryGetStringExpand`
- `0x18001d661`: `AslRegistryGetStringExpand`

## pseudocode

```c
__int64 __fastcall AslRegistryGetStringExpand(wchar_t **a1, void *a2, const WCHAR *a3, __int64 a4)
{
  PVOID v6; // rsi
  wchar_t *v7; // rdi
  NTSTATUS v9; // eax
  int v10; // ebx
  _DWORD *Heap; // rax
  _DWORD *v12; // r14
  NTSTATUS v13; // eax
  int v14; // eax
  NTSTATUS NativeSystemInformation; // eax
  __int16 v16; // r14
  __int64 v17; // r8
  USHORT v19; // r15
  wchar_t *v20; // rbx
  __int64 v21; // r8
  const char *v22; // r9
  ULONG Length[2]; // [rsp+20h] [rbp-58h]
  int ResultLength; // [rsp+28h] [rbp-50h]
  PULONG ResultLengtha; // [rsp+28h] [rbp-50h]
  int v26; // [rsp+30h] [rbp-48h]
  ULONG v27; // [rsp+40h] [rbp-38h] BYREF
  wchar_t *Str; // [rsp+48h] [rbp-30h] BYREF
  int v29; // [rsp+50h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-20h] BYREF

  v6 = 0;
  v7 = 0;
  Str = 0;
  DestinationString = 0;
  v27 = 0;
  RtlInitUnicodeString(&DestinationString, a3);
  v9 = ZwQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, 0, 0, &v27);
  v10 = v9;
  if ( v9 == -2147483643 || v9 == -1073741789 )
  {
    v27 += 2;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v27);
    v12 = Heap;
    if ( !Heap )
    {
      v10 = -1073741801;
      AslLogCallPrintf(1, "AslRegistryGetString", 1348, "Out of memory");
      goto LABEL_16;
    }
    v13 = ZwQueryValueKey(a2, &DestinationString, KeyValuePartialInformation, Heap, v27, &v27);
    v10 = v13;
    if ( v13 < 0 )
    {
      AslLogCallPrintf(1, "AslRegistryGetString", 1360, "Failed to query key value [%x]", v13);
    }
    else if ( (unsigned int)(v12[1] - 1) > 1 )
    {
      AslLogCallPrintf(1, "AslRegistryGetString", 1368, "Invalid value type");
      v10 = -1073741788;
    }
    else
    {
      *((_WORD *)v12 + ((unsigned __int64)(unsigned int)v12[2] >> 1) + 6) = 0;
      v14 = AslStringDuplicate(&Str);
      v10 = v14;
      if ( v14 < 0 )
        AslLogCallPrintf(1, "AslRegistryGetString", 1378, "Out of memory [%x]", v14);
      v7 = Str;
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  }
  else if ( v9 != -1073741772 )
  {
    AslLogCallPrintf(1, "AslRegistryGetString", 1334, "Failed to query key value [%x]", v9);
  }
  if ( v10 >= 0 )
  {
    if ( !wcschr(v7, 0x25u) )
    {
      *a1 = v7;
      return 0;
    }
    Str = 0;
    v29 = 0;
    *(_QWORD *)&DestinationString.Length = 0;
    LODWORD(DestinationString.Buffer) = 0;
    NativeSystemInformation = RtlGetNativeSystemInformation(1, &Str, 12, 0);
    v10 = NativeSystemInformation;
    if ( NativeSystemInformation < 0 )
    {
      v21 = 1953;
      v22 = "RtlGetNativeSystemInformation failed [%x]";
    }
    else
    {
      v16 = (__int16)Str;
      NativeSystemInformation = ZwQuerySystemInformation(SystemProcessorInformation, &DestinationString, 0xCu, 0);
      v10 = NativeSystemInformation;
      if ( NativeSystemInformation >= 0 )
      {
        Str = (wchar_t *)260;
        v6 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
        if ( !v6 )
        {
          v17 = 1476;
LABEL_15:
          AslLogCallPrintf(1, "AslRegistryGetStringExpand", v17, "Out of memory");
          v10 = -1073741801;
          goto LABEL_16;
        }
        v19 = DestinationString.Length;
        LOWORD(ResultLength) = v16;
        v10 = AslEnvExpandStrings2(a4, v7, v6, 260, &Str, ResultLength, DestinationString.Length);
        if ( v10 == -1073741789 )
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
          v20 = Str;
          v6 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (_QWORD)Str);
          if ( !v6 )
          {
            v17 = 1494;
            goto LABEL_15;
          }
          LOWORD(v26) = v19;
          LOWORD(ResultLengtha) = v16;
          v10 = AslEnvExpandStrings2(a4, v7, v6, v20, &Str, (_DWORD)ResultLengtha, v26);
        }
        if ( v10 >= 0 )
        {
          *a1 = (wchar_t *)v6;
          v6 = 0;
          v10 = 0;
        }
        else
        {
          LODWORD(ResultLengtha) = v10;
          AslLogCallPrintf(
            1,
            "AslRegistryGetStringExpand",
            1509,
            "AslEnvExpandStrings2 failed to expand strings for %ws [%x]",
            v7,
            ResultLengtha);
        }
        goto LABEL_16;
      }
      v22 = "ZwQuerySystemInformation failed [%x]";
      v21 = 1987;
    }
    Length[0] = NativeSystemInformation;
    AslLogCallPrintf(1, "AslEnvGetProcessWowInfo", v21, v22, *(_QWORD *)Length);
    AslLogCallPrintf(1, "AslRegistryGetStringExpand", 1464, "AslEnvGetProcessWowInfo failed [%x]", v10);
  }
LABEL_16:
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( v6 )
    AslFree(NtCurrentPeb()->ProcessHeap, v6);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001d224  push    rbp
0x18001d226  push    rbx
0x18001d227  push    rsi
0x18001d228  push    rdi
0x18001d229  push    r12
0x18001d22b  push    r13
0x18001d22d  push    r14
0x18001d22f  push    r15
0x18001d231  mov     rbp, rsp
0x18001d234  sub     rsp, 78h
0x18001d238  mov     rax, cs:__security_cookie
0x18001d23f  xor     rax, rsp
0x18001d242  mov     [rbp+var_10], rax
0x18001d246  mov     r15, rdx
0x18001d249  mov     r12, rcx
0x18001d24c  xorps   xmm0, xmm0
0x18001d24f  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001d253  xor     esi, esi
0x18001d255  xor     edi, edi
0x18001d257  mov     rdx, r8; SourceString
0x18001d25a  mov     [rbp+Str], rdi
0x18001d25e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001d262  mov     [rbp+var_38], esi
0x18001d265  mov     r13, r9
0x18001d268  call    cs:__imp_RtlInitUnicodeString
0x18001d26e  lea     rax, [rbp+var_38]
0x18001d272  xor     r9d, r9d; KeyValueInformation
0x18001d275  mov     [rsp+78h+ResultLength], rax; ResultLength
0x18001d27a  lea     r8d, [rsi+2]; KeyValueInformationClass
0x18001d27e  lea     rdx, [rbp+DestinationString]; ValueName
0x18001d282  mov     [rsp+78h+Length], esi; Length
0x18001d286  mov     rcx, r15; KeyHandle
0x18001d289  call    cs:__imp_ZwQueryValueKey
0x18001d28f  mov     ebx, eax
0x18001d291  cmp     eax, 80000005h
0x18001d296  jnz     loc_18001D443
0x18001d29c  mov     eax, [rbp+var_38]
0x18001d29f  mov     edx, 8; Flags
0x18001d2a4  add     eax, 2
0x18001d2a7  mov     [rbp+var_38], eax
0x18001d2aa  mov     rcx, gs:60h
0x18001d2b3  mov     r8d, eax; Size
0x18001d2b6  mov     rcx, [rcx+30h]; HeapHandle
0x18001d2ba  call    cs:__imp_RtlAllocateHeap
0x18001d2c0  mov     r14, rax
0x18001d2c3  test    rax, rax
0x18001d2c6  jz      loc_18001D57D
0x18001d2cc  lea     rax, [rbp+var_38]
0x18001d2d0  mov     r9, r14; KeyValueInformation
0x18001d2d3  mov     [rsp+78h+ResultLength], rax; ResultLength
0x18001d2d8  lea     rdx, [rbp+DestinationString]; ValueName
0x18001d2dc  mov     eax, [rbp+var_38]
0x18001d2df  mov     r8d, 2; KeyValueInformationClass
0x18001d2e5  mov     rcx, r15; KeyHandle
0x18001d2e8  mov     [rsp+78h+Length], eax; Length
0x18001d2ec  call    cs:__imp_ZwQueryValueKey
0x18001d2f2  mov     ebx, eax
0x18001d2f4  mov     r15d, 1
0x18001d2fa  test    eax, eax
0x18001d2fc  js      loc_18001D4A9
0x18001d302  mov     eax, [r14+4]
0x18001d306  sub     eax, r15d
0x18001d309  cmp     eax, r15d
0x18001d30c  ja      loc_18001D5A5
0x18001d312  mov     ecx, [r14+8]
0x18001d316  lea     rdx, [r14+0Ch]
0x18001d31a  shr     rcx, 1
0x18001d31d  xor     eax, eax
0x18001d31f  mov     [rdx+rcx*2], ax
0x18001d323  lea     rcx, [rbp+Str]
0x18001d327  call    AslStringDuplicate
0x18001d32c  mov     ebx, eax
0x18001d32e  test    eax, eax
0x18001d330  js      loc_18001D558
0x18001d336  mov     rdi, [rbp+Str]
0x18001d33a  mov     rcx, gs:60h
0x18001d343  mov     r8, r14; P
0x18001d346  xor     edx, edx; Flags
0x18001d348  mov     rcx, [rcx+30h]; HeapHandle
0x18001d34c  call    cs:__imp_RtlFreeHeap
0x18001d352  test    ebx, ebx
0x18001d354  js      loc_18001D416
0x18001d35a  mov     edx, 25h ; '%'; Ch
0x18001d35f  mov     rcx, rdi; Str
0x18001d362  call    cs:__imp_wcschr
0x18001d368  test    rax, rax
0x18001d36b  jz      loc_18001D484
0x18001d371  xor     eax, eax
0x18001d373  lea     rdx, [rbp+Str]
0x18001d377  xor     r9d, r9d
0x18001d37a  mov     [rbp+Str], rax
0x18001d37e  mov     ecx, r15d
0x18001d381  mov     [rbp+var_28], eax
0x18001d384  mov     qword ptr [rbp+DestinationString.Length], rax
0x18001d388  lea     r8d, [rax+0Ch]
0x18001d38c  mov     dword ptr [rbp+DestinationString.Buffer], eax
0x18001d38f  call    cs:__imp_RtlGetNativeSystemInformation
0x18001d395  mov     ebx, eax
0x18001d397  mov     ecx, r15d; SystemInformationClass
0x18001d39a  test    eax, eax
0x18001d39c  js      loc_18001D5CB
0x18001d3a2  movzx   r14d, word ptr [rbp+Str]
0x18001d3a7  lea     rdx, [rbp+DestinationString]; SystemInformation
0x18001d3ab  xor     r9d, r9d; ReturnLength
0x18001d3ae  lea     r8d, [r9+0Ch]; SystemInformationLength
0x18001d3b2  call    cs:__imp_ZwQuerySystemInformation
0x18001d3b8  mov     ebx, eax
0x18001d3ba  test    eax, eax
0x18001d3bc  js      loc_18001D5DA
0x18001d3c2  mov     rcx, gs:60h
0x18001d3cb  mov     ebx, 104h
0x18001d3d0  mov     edx, 8; Flags
0x18001d3d5  mov     [rbp+Str], rbx
0x18001d3d9  mov     r8d, 208h; Size
0x18001d3df  mov     rcx, [rcx+30h]; HeapHandle
0x18001d3e3  call    cs:__imp_RtlAllocateHeap
0x18001d3e9  mov     rsi, rax
0x18001d3ec  test    rax, rax
0x18001d3ef  jnz     loc_18001D4CE
0x18001d3f5  mov     r8d, 5C4h
0x18001d3fb  mov     ecx, r15d
0x18001d3fe  lea     rdx, aAslregistryget_0; "AslRegistryGetStringExpand"
0x18001d405  lea     r9, aOutOfMemory; "Out of memory"
0x18001d40c  call    AslLogCallPrintf
0x18001d411  mov     ebx, 0C0000017h
0x18001d416  test    rdi, rdi
0x18001d419  jnz     short loc_18001D48C
0x18001d41b  test    rsi, rsi
0x18001d41e  jnz     loc_18001D684
0x18001d424  mov     eax, ebx
0x18001d426  mov     rcx, [rbp+var_10]
0x18001d42a  xor     rcx, rsp; StackCookie
0x18001d42d  call    __security_check_cookie
0x18001d432  add     rsp, 78h
0x18001d436  pop     r15
0x18001d438  pop     r14
0x18001d43a  pop     r13
0x18001d43c  pop     r12
0x18001d43e  pop     rdi
0x18001d43f  pop     rsi
0x18001d440  pop     rbx
0x18001d441  pop     rbp
0x18001d442  retn
0x18001d443  cmp     eax, 0C0000023h
0x18001d448  jz      loc_18001D29C
0x18001d44e  mov     r15d, 1
0x18001d454  cmp     eax, 0C0000034h
0x18001d459  jz      loc_18001D352
0x18001d45f  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x18001d466  mov     [rsp+78h+Length], eax
0x18001d46a  mov     r8d, 536h
0x18001d470  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x18001d477  mov     ecx, r15d
0x18001d47a  call    AslLogCallPrintf
0x18001d47f  jmp     loc_18001D352
0x18001d484  mov     [r12], rdi
0x18001d488  xor     ebx, ebx
0x18001d48a  jmp     short loc_18001D424
0x18001d48c  mov     rcx, gs:60h
0x18001d495  mov     r8, rdi; P
0x18001d498  xor     edx, edx; Flags
0x18001d49a  mov     rcx, [rcx+30h]; HeapHandle
0x18001d49e  call    cs:__imp_RtlFreeHeap
0x18001d4a4  jmp     loc_18001D41B
0x18001d4a9  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x18001d4b0  mov     [rsp+78h+Length], eax
0x18001d4b4  mov     r8d, 550h
0x18001d4ba  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x18001d4c1  mov     ecx, r15d
0x18001d4c4  call    AslLogCallPrintf
0x18001d4c9  jmp     loc_18001D33A
0x18001d4ce  movzx   r15d, [rbp+DestinationString.Length]
0x18001d4d3  lea     rax, [rbp+Str]
0x18001d4d7  mov     word ptr [rsp+78h+var_48], r15w
0x18001d4dd  mov     r9, rbx
0x18001d4e0  mov     word ptr [rsp+78h+ResultLength], r14w
0x18001d4e6  mov     r8, rsi
0x18001d4e9  mov     rdx, rdi
0x18001d4ec  mov     qword ptr [rsp+78h+Length], rax
0x18001d4f1  mov     rcx, r13
0x18001d4f4  call    AslEnvExpandStrings2
0x18001d4f9  mov     ebx, eax
0x18001d4fb  cmp     eax, 0C0000023h
0x18001d500  jnz     loc_18001D647
0x18001d506  mov     rcx, gs:60h
0x18001d50f  mov     r8, rsi; P
0x18001d512  xor     edx, edx; Flags
0x18001d514  mov     rcx, [rcx+30h]; HeapHandle
0x18001d518  call    cs:__imp_RtlFreeHeap
0x18001d51e  mov     rcx, gs:60h
0x18001d527  mov     edx, 8; Flags
0x18001d52c  mov     rbx, [rbp+Str]
0x18001d530  mov     rcx, [rcx+30h]; HeapHandle
0x18001d534  lea     r8, [rbx+rbx]; Size
0x18001d538  call    cs:__imp_RtlAllocateHeap
0x18001d53e  mov     rsi, rax
0x18001d541  test    rax, rax
0x18001d544  jnz     loc_18001D61F
0x18001d54a  mov     r8d, 5D6h
0x18001d550  lea     ecx, [rax+1]
0x18001d553  jmp     loc_18001D3FE
0x18001d558  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x18001d55f  mov     [rsp+78h+Length], eax
0x18001d563  mov     r8d, 562h
0x18001d569  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x18001d570  mov     ecx, r15d
0x18001d573  call    AslLogCallPrintf
0x18001d578  jmp     loc_18001D336
0x18001d57d  lea     r9, aOutOfMemory; "Out of memory"
0x18001d584  mov     r8d, 544h
0x18001d58a  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x18001d591  mov     ecx, 1
0x18001d596  mov     ebx, 0C0000017h
0x18001d59b  call    AslLogCallPrintf
0x18001d5a0  jmp     loc_18001D416
0x18001d5a5  lea     r9, aInvalidValueTy; "Invalid value type"
0x18001d5ac  mov     r8d, 558h
0x18001d5b2  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x18001d5b9  mov     ecx, r15d
0x18001d5bc  call    AslLogCallPrintf
0x18001d5c1  mov     ebx, 0C0000024h
0x18001d5c6  jmp     loc_18001D33A
0x18001d5cb  mov     r8d, 7A1h
0x18001d5d1  lea     r9, aRtlgetnativesy; "RtlGetNativeSystemInformation failed [%"...
0x18001d5d8  jmp     short loc_18001D5EA
0x18001d5da  mov     ecx, r15d
0x18001d5dd  lea     r9, aZwquerysystemi; "ZwQuerySystemInformation failed [%x]"
0x18001d5e4  mov     r8d, 7C3h
0x18001d5ea  lea     rdx, aAslenvgetproce; "AslEnvGetProcessWowInfo"
0x18001d5f1  mov     [rsp+78h+Length], eax
0x18001d5f5  call    AslLogCallPrintf
0x18001d5fa  lea     r9, aAslenvgetproce_0; "AslEnvGetProcessWowInfo failed [%x]"
0x18001d601  mov     [rsp+78h+Length], ebx
0x18001d605  mov     r8d, 5B8h
0x18001d60b  lea     rdx, aAslregistryget_0; "AslRegistryGetStringExpand"
0x18001d612  mov     ecx, r15d
0x18001d615  call    AslLogCallPrintf
0x18001d61a  jmp     loc_18001D416
0x18001d61f  mov     word ptr [rsp+78h+var_48], r15w
0x18001d625  lea     rax, [rbp+Str]
0x18001d629  mov     word ptr [rsp+78h+ResultLength], r14w
0x18001d62f  mov     r9, rbx
0x18001d632  mov     r8, rsi
0x18001d635  mov     qword ptr [rsp+78h+Length], rax
0x18001d63a  mov     rdx, rdi
0x18001d63d  mov     rcx, r13
0x18001d640  call    AslEnvExpandStrings2
0x18001d645  mov     ebx, eax
0x18001d647  test    ebx, ebx
0x18001d649  jns     short loc_18001D677
0x18001d64b  mov     dword ptr [rsp+78h+ResultLength], ebx
0x18001d64f  lea     r9, aAslenvexpandst; "AslEnvExpandStrings2 failed to expand s"...
0x18001d656  mov     r8d, 5E5h
0x18001d65c  mov     qword ptr [rsp+78h+Length], rdi
0x18001d661  lea     rdx, aAslregistryget_0; "AslRegistryGetStringExpand"
0x18001d668  mov     ecx, 1
0x18001d66d  call    AslLogCallPrintf
0x18001d672  jmp     loc_18001D416
0x18001d677  mov     [r12], rsi
0x18001d67b  xor     esi, esi
0x18001d67d  xor     ebx, ebx
0x18001d67f  jmp     loc_18001D416
0x18001d684  mov     rcx, gs:60h
0x18001d68d  mov     rdx, rsi
0x18001d690  mov     rcx, [rcx+30h]
0x18001d694  call    AslFree
0x18001d699  jmp     loc_18001D424
```
