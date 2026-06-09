# AslRegistryGetStringExpand

- ea: `0x18002119c`
- end: `0x18002165f`
- name: `AslRegistryGetStringExpand`
- size: `1219`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001f680`

## callees

- `0x180020fac`
- `0x18002119c`
- `0x180021668`
- `0x18002186c`
- `0x180036388`
- `0x18003bc70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800212f8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800212f8`
- `ntdll!RtlInitUnicodeString` at `0x1800211e0`
- `ntdll!RtlInitUnicodeString` at `0x1800211e0`
- `ntdll!RtlAllocateHeap` at `0x18002123e`
- `ntdll!RtlAllocateHeap` at `0x18002138b`
- `ntdll!RtlAllocateHeap` at `0x1800214f3`
- `ntdll!RtlAllocateHeap` at `0x18002123e`
- `ntdll!RtlAllocateHeap` at `0x18002138b`
- `ntdll!RtlAllocateHeap` at `0x1800214f3`
- `ntdll!RtlFreeHeap` at `0x1800212dc`
- `ntdll!RtlFreeHeap` at `0x18002144d`
- `ntdll!RtlFreeHeap` at `0x1800214cd`
- `ntdll!RtlFreeHeap` at `0x1800212dc`
- `ntdll!RtlFreeHeap` at `0x18002144d`
- `ntdll!RtlFreeHeap` at `0x1800214cd`
- `ntdll!RtlGetNativeSystemInformation` at `0x18002132b`
- `ntdll!RtlGetNativeSystemInformation` at `0x18002132b`
- `ntdll!ZwQuerySystemInformation` at `0x180021354`
- `ntdll!ZwQuerySystemInformation` at `0x180021354`
- `ntdll!ZwQueryValueKey` at `0x180021207`
- `ntdll!ZwQueryValueKey` at `0x180021276`
- `ntdll!ZwQueryValueKey` at `0x180021207`
- `ntdll!ZwQueryValueKey` at `0x180021276`

## string_xrefs

- `0x18002141f`: `AslRegistryGetString`
- `0x18002146f`: `AslRegistryGetString`
- `0x18002152a`: `AslRegistryGetString`
- `0x18002154b`: `AslRegistryGetString`
- `0x180021573`: `AslRegistryGetString`
- `0x1800213ac`: `AslRegistryGetStringExpand`
- `0x1800215cc`: `AslRegistryGetStringExpand`
- `0x180021622`: `AslRegistryGetStringExpand`

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
0x18002119c  push    rbp
0x18002119e  push    rbx
0x18002119f  push    rsi
0x1800211a0  push    rdi
0x1800211a1  push    r12
0x1800211a3  push    r13
0x1800211a5  push    r14
0x1800211a7  push    r15
0x1800211a9  mov     rbp, rsp
0x1800211ac  sub     rsp, 78h
0x1800211b0  mov     rax, cs:__security_cookie
0x1800211b7  xor     rax, rsp
0x1800211ba  mov     [rbp+var_10], rax
0x1800211be  mov     r15, rdx
0x1800211c1  mov     r12, rcx
0x1800211c4  xorps   xmm0, xmm0
0x1800211c7  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800211cb  xor     esi, esi
0x1800211cd  xor     edi, edi
0x1800211cf  mov     rdx, r8; SourceString
0x1800211d2  mov     [rbp+Str], rdi
0x1800211d6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800211da  mov     [rbp+var_38], esi
0x1800211dd  mov     r13, r9
0x1800211e0  call    cs:__imp_RtlInitUnicodeString
0x1800211e7  nop     dword ptr [rax+rax+00h]
0x1800211ec  lea     rax, [rbp+var_38]
0x1800211f0  xor     r9d, r9d; KeyValueInformation
0x1800211f3  mov     [rsp+78h+ResultLength], rax; ResultLength
0x1800211f8  lea     r8d, [rsi+2]; KeyValueInformationClass
0x1800211fc  lea     rdx, [rbp+DestinationString]; ValueName
0x180021200  mov     [rsp+78h+Length], esi; Length
0x180021204  mov     rcx, r15; KeyHandle
0x180021207  call    cs:__imp_ZwQueryValueKey
0x18002120e  nop     dword ptr [rax+rax+00h]
0x180021213  mov     ebx, eax
0x180021215  cmp     eax, 80000005h
0x18002121a  jnz     loc_1800213F2
0x180021220  mov     eax, [rbp+var_38]
0x180021223  mov     edx, 8; Flags
0x180021228  add     eax, 2
0x18002122b  mov     [rbp+var_38], eax
0x18002122e  mov     rcx, gs:60h
0x180021237  mov     r8d, eax; Size
0x18002123a  mov     rcx, [rcx+30h]; HeapHandle
0x18002123e  call    cs:__imp_RtlAllocateHeap
0x180021245  nop     dword ptr [rax+rax+00h]
0x18002124a  mov     r14, rax
0x18002124d  test    rax, rax
0x180021250  jz      loc_18002153E
0x180021256  lea     rax, [rbp+var_38]
0x18002125a  mov     r9, r14; KeyValueInformation
0x18002125d  mov     [rsp+78h+ResultLength], rax; ResultLength
0x180021262  lea     rdx, [rbp+DestinationString]; ValueName
0x180021266  mov     eax, [rbp+var_38]
0x180021269  mov     r8d, 2; KeyValueInformationClass
0x18002126f  mov     rcx, r15; KeyHandle
0x180021272  mov     [rsp+78h+Length], eax; Length
0x180021276  call    cs:__imp_ZwQueryValueKey
0x18002127d  nop     dword ptr [rax+rax+00h]
0x180021282  mov     ebx, eax
0x180021284  mov     r15d, 1
0x18002128a  test    eax, eax
0x18002128c  js      loc_18002145E
0x180021292  mov     eax, [r14+4]
0x180021296  sub     eax, r15d
0x180021299  cmp     eax, r15d
0x18002129c  ja      loc_180021566
0x1800212a2  mov     ecx, [r14+8]
0x1800212a6  lea     rdx, [r14+0Ch]
0x1800212aa  shr     rcx, 1
0x1800212ad  xor     eax, eax
0x1800212af  mov     [rdx+rcx*2], ax
0x1800212b3  lea     rcx, [rbp+Str]
0x1800212b7  call    AslStringDuplicate
0x1800212bc  mov     ebx, eax
0x1800212be  test    eax, eax
0x1800212c0  js      loc_180021519
0x1800212c6  mov     rdi, [rbp+Str]
0x1800212ca  mov     rcx, gs:60h
0x1800212d3  mov     r8, r14; P
0x1800212d6  xor     edx, edx; Flags
0x1800212d8  mov     rcx, [rcx+30h]; HeapHandle
0x1800212dc  call    cs:__imp_RtlFreeHeap
0x1800212e3  nop     dword ptr [rax+rax+00h]
0x1800212e8  test    ebx, ebx
0x1800212ea  js      loc_1800213C4
0x1800212f0  mov     edx, 25h ; '%'; Ch
0x1800212f5  mov     rcx, rdi; Str
0x1800212f8  call    cs:__imp_wcschr
0x1800212ff  nop     dword ptr [rax+rax+00h]
0x180021304  test    rax, rax
0x180021307  jz      loc_180021433
0x18002130d  xor     eax, eax
0x18002130f  lea     rdx, [rbp+Str]
0x180021313  xor     r9d, r9d
0x180021316  mov     [rbp+Str], rax
0x18002131a  mov     ecx, r15d
0x18002131d  mov     [rbp+var_28], eax
0x180021320  mov     qword ptr [rbp+DestinationString.Length], rax
0x180021324  lea     r8d, [rax+0Ch]
0x180021328  mov     dword ptr [rbp+DestinationString.Buffer], eax
0x18002132b  call    cs:__imp_RtlGetNativeSystemInformation
0x180021332  nop     dword ptr [rax+rax+00h]
0x180021337  mov     ebx, eax
0x180021339  mov     ecx, r15d; SystemInformationClass
0x18002133c  test    eax, eax
0x18002133e  js      loc_18002158C
0x180021344  movzx   r14d, word ptr [rbp+Str]
0x180021349  lea     rdx, [rbp+DestinationString]; SystemInformation
0x18002134d  xor     r9d, r9d; ReturnLength
0x180021350  lea     r8d, [r9+0Ch]; SystemInformationLength
0x180021354  call    cs:__imp_ZwQuerySystemInformation
0x18002135b  nop     dword ptr [rax+rax+00h]
0x180021360  mov     ebx, eax
0x180021362  test    eax, eax
0x180021364  js      loc_18002159B
0x18002136a  mov     rcx, gs:60h
0x180021373  mov     ebx, 104h
0x180021378  mov     edx, 8; Flags
0x18002137d  mov     [rbp+Str], rbx
0x180021381  mov     r8d, 208h; Size
0x180021387  mov     rcx, [rcx+30h]; HeapHandle
0x18002138b  call    cs:__imp_RtlAllocateHeap
0x180021392  nop     dword ptr [rax+rax+00h]
0x180021397  mov     rsi, rax
0x18002139a  test    rax, rax
0x18002139d  jnz     loc_180021483
0x1800213a3  mov     r8d, 5C4h
0x1800213a9  mov     ecx, r15d
0x1800213ac  lea     rdx, aAslregistryget_0; "AslRegistryGetStringExpand"
0x1800213b3  lea     r9, aOutOfMemory; "Out of memory"
0x1800213ba  call    AslLogCallPrintf
0x1800213bf  mov     ebx, 0C0000017h
0x1800213c4  test    rdi, rdi
0x1800213c7  jnz     short loc_18002143B
0x1800213c9  test    rsi, rsi
0x1800213cc  jnz     loc_180021645
0x1800213d2  mov     eax, ebx
0x1800213d4  mov     rcx, [rbp+var_10]
0x1800213d8  xor     rcx, rsp; StackCookie
0x1800213db  call    __security_check_cookie
0x1800213e0  add     rsp, 78h
0x1800213e4  pop     r15
0x1800213e6  pop     r14
0x1800213e8  pop     r13
0x1800213ea  pop     r12
0x1800213ec  pop     rdi
0x1800213ed  pop     rsi
0x1800213ee  pop     rbx
0x1800213ef  pop     rbp
0x1800213f0  retn
0x1800213f2  cmp     eax, 0C0000023h
0x1800213f7  jz      loc_180021220
0x1800213fd  mov     r15d, 1
0x180021403  cmp     eax, 0C0000034h
0x180021408  jz      loc_1800212E8
0x18002140e  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x180021415  mov     [rsp+78h+Length], eax
0x180021419  mov     r8d, 536h
0x18002141f  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x180021426  mov     ecx, r15d
0x180021429  call    AslLogCallPrintf
0x18002142e  jmp     loc_1800212E8
0x180021433  mov     [r12], rdi
0x180021437  xor     ebx, ebx
0x180021439  jmp     short loc_1800213D2
0x18002143b  mov     rcx, gs:60h
0x180021444  mov     r8, rdi; P
0x180021447  xor     edx, edx; Flags
0x180021449  mov     rcx, [rcx+30h]; HeapHandle
0x18002144d  call    cs:__imp_RtlFreeHeap
0x180021454  nop     dword ptr [rax+rax+00h]
0x180021459  jmp     loc_1800213C9
0x18002145e  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x180021465  mov     [rsp+78h+Length], eax
0x180021469  mov     r8d, 550h
0x18002146f  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x180021476  mov     ecx, r15d
0x180021479  call    AslLogCallPrintf
0x18002147e  jmp     loc_1800212CA
0x180021483  movzx   r15d, [rbp+DestinationString.Length]
0x180021488  lea     rax, [rbp+Str]
0x18002148c  mov     word ptr [rsp+78h+var_48], r15w
0x180021492  mov     r9, rbx
0x180021495  mov     word ptr [rsp+78h+ResultLength], r14w
0x18002149b  mov     r8, rsi
0x18002149e  mov     rdx, rdi
0x1800214a1  mov     qword ptr [rsp+78h+Length], rax
0x1800214a6  mov     rcx, r13
0x1800214a9  call    AslEnvExpandStrings2
0x1800214ae  mov     ebx, eax
0x1800214b0  cmp     eax, 0C0000023h
0x1800214b5  jnz     loc_180021608
0x1800214bb  mov     rcx, gs:60h
0x1800214c4  mov     r8, rsi; P
0x1800214c7  xor     edx, edx; Flags
0x1800214c9  mov     rcx, [rcx+30h]; HeapHandle
0x1800214cd  call    cs:__imp_RtlFreeHeap
0x1800214d4  nop     dword ptr [rax+rax+00h]
0x1800214d9  mov     rcx, gs:60h
0x1800214e2  mov     edx, 8; Flags
0x1800214e7  mov     rbx, [rbp+Str]
0x1800214eb  mov     rcx, [rcx+30h]; HeapHandle
0x1800214ef  lea     r8, [rbx+rbx]; Size
0x1800214f3  call    cs:__imp_RtlAllocateHeap
0x1800214fa  nop     dword ptr [rax+rax+00h]
0x1800214ff  mov     rsi, rax
0x180021502  test    rax, rax
0x180021505  jnz     loc_1800215E0
0x18002150b  mov     r8d, 5D6h
0x180021511  lea     ecx, [rax+1]
0x180021514  jmp     loc_1800213AC
0x180021519  lea     r9, aOutOfMemoryX; "Out of memory [%x]"
0x180021520  mov     [rsp+78h+Length], eax
0x180021524  mov     r8d, 562h
0x18002152a  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x180021531  mov     ecx, r15d
0x180021534  call    AslLogCallPrintf
0x180021539  jmp     loc_1800212C6
0x18002153e  lea     r9, aOutOfMemory; "Out of memory"
0x180021545  mov     r8d, 544h
0x18002154b  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x180021552  mov     ecx, 1
0x180021557  mov     ebx, 0C0000017h
0x18002155c  call    AslLogCallPrintf
0x180021561  jmp     loc_1800213C4
0x180021566  lea     r9, aInvalidValueTy; "Invalid value type"
0x18002156d  mov     r8d, 558h
0x180021573  lea     rdx, aAslregistryget; "AslRegistryGetString"
0x18002157a  mov     ecx, r15d
0x18002157d  call    AslLogCallPrintf
0x180021582  mov     ebx, 0C0000024h
0x180021587  jmp     loc_1800212CA
0x18002158c  mov     r8d, 7A1h
0x180021592  lea     r9, aRtlgetnativesy; "RtlGetNativeSystemInformation failed [%"...
0x180021599  jmp     short loc_1800215AB
0x18002159b  mov     ecx, r15d
0x18002159e  lea     r9, aZwquerysystemi; "ZwQuerySystemInformation failed [%x]"
0x1800215a5  mov     r8d, 7C3h
0x1800215ab  lea     rdx, aAslenvgetproce; "AslEnvGetProcessWowInfo"
0x1800215b2  mov     [rsp+78h+Length], eax
0x1800215b6  call    AslLogCallPrintf
0x1800215bb  lea     r9, aAslenvgetproce_0; "AslEnvGetProcessWowInfo failed [%x]"
0x1800215c2  mov     [rsp+78h+Length], ebx
0x1800215c6  mov     r8d, 5B8h
0x1800215cc  lea     rdx, aAslregistryget_0; "AslRegistryGetStringExpand"
0x1800215d3  mov     ecx, r15d
0x1800215d6  call    AslLogCallPrintf
0x1800215db  jmp     loc_1800213C4
0x1800215e0  mov     word ptr [rsp+78h+var_48], r15w
0x1800215e6  lea     rax, [rbp+Str]
0x1800215ea  mov     word ptr [rsp+78h+ResultLength], r14w
0x1800215f0  mov     r9, rbx
0x1800215f3  mov     r8, rsi
0x1800215f6  mov     qword ptr [rsp+78h+Length], rax
0x1800215fb  mov     rdx, rdi
0x1800215fe  mov     rcx, r13
0x180021601  call    AslEnvExpandStrings2
0x180021606  mov     ebx, eax
0x180021608  test    ebx, ebx
0x18002160a  jns     short loc_180021638
0x18002160c  mov     dword ptr [rsp+78h+ResultLength], ebx
0x180021610  lea     r9, aAslenvexpandst; "AslEnvExpandStrings2 failed to expand s"...
0x180021617  mov     r8d, 5E5h
0x18002161d  mov     qword ptr [rsp+78h+Length], rdi
0x180021622  lea     rdx, aAslregistryget_0; "AslRegistryGetStringExpand"
0x180021629  mov     ecx, 1
0x18002162e  call    AslLogCallPrintf
0x180021633  jmp     loc_1800213C4
0x180021638  mov     [r12], rsi
0x18002163c  xor     esi, esi
0x18002163e  xor     ebx, ebx
0x180021640  jmp     loc_1800213C4
0x180021645  mov     rcx, gs:60h
0x18002164e  mov     rdx, rsi
0x180021651  mov     rcx, [rcx+30h]
0x180021655  call    AslFree
0x18002165a  jmp     loc_1800213D2
```
