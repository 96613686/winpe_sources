# OpenCombinedClassesRoot

- ea: `0x1800d18b8`
- end: `0x1800d1af2`
- name: `OpenCombinedClassesRoot`
- size: `570`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800d1400`
- `0x1800d1550`

## callees

- `0x18005f8a0`
- `0x18005fa00`
- `0x1800d18b8`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800d1a42`
- `ntdll!RtlFreeUnicodeString` at `0x1800d1a52`
- `ntdll!RtlFreeUnicodeString` at `0x1800d1a93`
- `ntdll!RtlFreeUnicodeString` at `0x1800d1a42`
- `ntdll!RtlFreeUnicodeString` at `0x1800d1a52`
- `ntdll!RtlFreeUnicodeString` at `0x1800d1a93`
- `ntdll!RtlAppendUnicodeToString` at `0x1800d1957`
- `ntdll!RtlAppendUnicodeToString` at `0x1800d1957`
- `ntdll!RtlCopyUnicodeString` at `0x1800d1940`
- `ntdll!RtlCopyUnicodeString` at `0x1800d1940`
- `ntdll!NtClose` at `0x1800d1ae1`
- `ntdll!NtClose` at `0x1800d1ae1`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800d18eb`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800d18eb`
- `ntdll!RtlFreeHeap` at `0x1800d1a1f`
- `ntdll!RtlFreeHeap` at `0x1800d1a1f`
- `ntdll!RtlAllocateHeap` at `0x1800d191f`
- `ntdll!RtlAllocateHeap` at `0x1800d191f`
- `ntdll!NtOpenKeyEx` at `0x1800d19f9`
- `ntdll!NtOpenKeyEx` at `0x1800d19f9`
- `ntdll!NtSetInformationKey` at `0x1800d1ac7`
- `ntdll!NtSetInformationKey` at `0x1800d1ac7`

## pseudocode

```c
NTSTATUS __fastcall OpenCombinedClassesRoot(unsigned int a1, _QWORD *a2, __int64 a3)
{
  NTSTATUS result; // eax
  NTSTATUS v7; // ebx
  int v8; // esi
  int KeySetInformation; // [rsp+30h] [rbp-79h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-71h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-69h] BYREF
  __int64 v12; // [rsp+50h] [rbp-59h] BYREF
  __int16 v13; // [rsp+58h] [rbp-51h]
  char v14; // [rsp+5Ah] [rbp-4Fh]
  PVOID P; // [rsp+60h] [rbp-49h] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+68h] [rbp-41h] BYREF
  __int128 v17; // [rsp+78h] [rbp-31h] BYREF
  __int128 v18; // [rsp+88h] [rbp-21h]
  __int128 v19; // [rsp+98h] [rbp-11h]
  _OWORD v20[5]; // [rsp+A8h] [rbp-1h] BYREF
  char v21; // [rsp+128h] [rbp+7Fh] BYREF

  DWORD1(v17) = 0;
  HIDWORD(v18) = 0;
  KeyPath = 0;
  DestinationString = 0;
  result = RtlFormatCurrentUserKeyPath(&KeyPath);
  if ( result < 0 )
    return result;
  DestinationString.MaximumLength = KeyPath.MaximumLength + 18;
  DestinationString.Buffer = (PWSTR)RtlAllocateHeap(
                                      NtCurrentPeb()->ProcessHeap,
                                      0,
                                      (unsigned __int16)(KeyPath.MaximumLength + 18));
  if ( !DestinationString.Buffer )
  {
    RtlFreeUnicodeString(&KeyPath);
    return -1073741670;
  }
  RtlCopyUnicodeString(&DestinationString, &KeyPath);
  RtlAppendUnicodeToString(&DestinationString, L"_Classes");
  LODWORD(v17) = 48;
  *(_QWORD *)&v18 = &DestinationString;
  *((_QWORD *)&v17 + 1) = 0;
  DWORD2(v18) = 64;
  v19 = 0;
  if ( a3 )
  {
    v7 = Wow64NtOpenKey((_DWORD)a2, a1, (unsigned int)&v17, 0, a3);
  }
  else
  {
    v12 = 0;
    v13 = 0;
    v14 = 0;
    KeyHandle = 0;
    v21 = 0;
    P = 0;
    v20[0] = v17;
    KeySetInformation = 0;
    v20[1] = v18;
    v20[2] = 0;
    v7 = ConstructKernelKeyPath(
           a1,
           (unsigned int)v20,
           (unsigned int)&KeySetInformation,
           (unsigned int)&v12,
           (__int64)&v21,
           (__int64)&P);
    if ( v7 >= 0 )
    {
      v8 = NtOpenKeyEx(&KeyHandle, a1, v20, 0);
      if ( P )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
      if ( v8 >= 0 )
      {
        if ( v21 )
        {
          if ( KeySetInformation )
          {
            KeySetInformation &= 0xF01u;
            v7 = NtSetInformationKey(KeyHandle, KeySetHandleTagsInformation, &KeySetInformation, 4u);
            if ( v7 < 0 )
            {
              NtClose(KeyHandle);
              goto LABEL_11;
            }
          }
        }
        *a2 = KeyHandle;
      }
      v7 = v8;
    }
  }
LABEL_11:
  RtlFreeUnicodeString(&DestinationString);
  RtlFreeUnicodeString(&KeyPath);
  if ( v7 >= 0 )
    *a2 |= 2uLL;
  return v7;
}

```

## disassembly

```asm
0x1800d18b8  push    rbp
0x1800d18ba  push    rbx
0x1800d18bb  push    rsi
0x1800d18bc  push    rdi
0x1800d18bd  lea     rbp, [rsp-3Fh]
0x1800d18c2  sub     rsp, 0E8h
0x1800d18c9  xor     eax, eax
0x1800d18cb  mov     esi, ecx
0x1800d18cd  xorps   xmm0, xmm0
0x1800d18d0  mov     dword ptr [rbp+57h+var_88+4], eax
0x1800d18d3  xorps   xmm1, xmm1
0x1800d18d6  mov     dword ptr [rbp+57h+var_78+0Ch], eax
0x1800d18d9  lea     rcx, [rbp+57h+KeyPath]; KeyPath
0x1800d18dd  mov     rbx, r8
0x1800d18e0  movups  xmmword ptr [rbp+57h+KeyPath.Length], xmm0
0x1800d18e4  mov     rdi, rdx
0x1800d18e7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1800d18eb  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x1800d18f2  nop     dword ptr [rax+rax+00h]
0x1800d18f7  test    eax, eax
0x1800d18f9  js      loc_1800D1A68
0x1800d18ff  movzx   eax, [rbp+57h+KeyPath.MaximumLength]
0x1800d1903  xor     edx, edx; Flags
0x1800d1905  add     ax, 12h
0x1800d1909  movzx   r8d, ax; Size
0x1800d190d  mov     [rbp+57h+DestinationString.MaximumLength], r8w
0x1800d1912  mov     rcx, gs:60h
0x1800d191b  mov     rcx, [rcx+30h]; HeapHandle
0x1800d191f  call    cs:__imp_RtlAllocateHeap
0x1800d1926  nop     dword ptr [rax+rax+00h]
0x1800d192b  mov     [rbp+57h+DestinationString.Buffer], rax
0x1800d192f  test    rax, rax
0x1800d1932  jz      loc_1800D1A8F
0x1800d1938  lea     rdx, [rbp+57h+KeyPath]; SourceString
0x1800d193c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800d1940  call    cs:__imp_RtlCopyUnicodeString
0x1800d1947  nop     dword ptr [rax+rax+00h]
0x1800d194c  lea     rdx, aClasses_0; "_Classes"
0x1800d1953  lea     rcx, [rbp+57h+DestinationString]; Destination
0x1800d1957  call    cs:__imp_RtlAppendUnicodeToString
0x1800d195e  nop     dword ptr [rax+rax+00h]
0x1800d1963  mov     dword ptr [rbp+57h+var_88], 30h ; '0'
0x1800d196a  lea     rax, [rbp+57h+DestinationString]
0x1800d196e  mov     qword ptr [rbp+57h+var_78], rax
0x1800d1972  xorps   xmm2, xmm2
0x1800d1975  mov     qword ptr [rbp+57h+var_88+8], 0
0x1800d197d  mov     dword ptr [rbp+57h+var_78+8], 40h ; '@'
0x1800d1984  movdqu  [rbp+57h+var_68], xmm2
0x1800d1989  test    rbx, rbx
0x1800d198c  jnz     loc_1800D1A75
0x1800d1992  movups  xmm0, [rbp+57h+var_88]
0x1800d1996  xor     eax, eax
0x1800d1998  lea     r9, [rbp+57h+var_B0]
0x1800d199c  movups  xmm1, [rbp+57h+var_78]
0x1800d19a0  mov     [rbp+57h+var_B0], rax
0x1800d19a4  lea     r8, [rbp+57h+KeySetInformation]
0x1800d19a8  mov     [rbp+57h+var_A8], ax
0x1800d19ac  lea     rdx, [rbp+57h+var_58]
0x1800d19b0  mov     [rbp+57h+var_A6], al
0x1800d19b3  mov     ecx, esi
0x1800d19b5  mov     [rbp+57h+KeyHandle], rax
0x1800d19b9  mov     [rbp+57h+arg_18], al
0x1800d19bc  lea     rax, [rbp+57h+P]
0x1800d19c0  mov     [rsp+100h+var_D8], rax
0x1800d19c5  lea     rax, [rbp+57h+arg_18]
0x1800d19c9  mov     [rsp+100h+var_E0], rax
0x1800d19ce  mov     [rbp+57h+P], rbx
0x1800d19d2  movups  [rbp+57h+var_58], xmm0
0x1800d19d6  mov     [rbp+57h+KeySetInformation], ebx
0x1800d19d9  movups  [rbp+57h+var_48], xmm1
0x1800d19dd  movups  [rbp+57h+var_38], xmm2
0x1800d19e1  call    ConstructKernelKeyPath
0x1800d19e6  mov     ebx, eax
0x1800d19e8  test    eax, eax
0x1800d19ea  js      short loc_1800D1A3E
0x1800d19ec  xor     r9d, r9d
0x1800d19ef  lea     r8, [rbp+57h+var_58]
0x1800d19f3  mov     edx, esi
0x1800d19f5  lea     rcx, [rbp+57h+KeyHandle]
0x1800d19f9  call    cs:__imp_NtOpenKeyEx
0x1800d1a00  nop     dword ptr [rax+rax+00h]
0x1800d1a05  mov     r8, [rbp+57h+P]; P
0x1800d1a09  mov     esi, eax
0x1800d1a0b  test    r8, r8
0x1800d1a0e  jz      short loc_1800D1A2B
0x1800d1a10  mov     rcx, gs:60h
0x1800d1a19  xor     edx, edx; Flags
0x1800d1a1b  mov     rcx, [rcx+30h]; HeapHandle
0x1800d1a1f  call    cs:__imp_RtlFreeHeap
0x1800d1a26  nop     dword ptr [rax+rax+00h]
0x1800d1a2b  test    esi, esi
0x1800d1a2d  js      short loc_1800D1A3C
0x1800d1a2f  cmp     [rbp+57h+arg_18], 0
0x1800d1a33  jnz     short loc_1800D1AA6
0x1800d1a35  mov     rax, [rbp+57h+KeyHandle]
0x1800d1a39  mov     [rdi], rax
0x1800d1a3c  mov     ebx, esi
0x1800d1a3e  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1800d1a42  call    cs:__imp_RtlFreeUnicodeString
0x1800d1a49  nop     dword ptr [rax+rax+00h]
0x1800d1a4e  lea     rcx, [rbp+57h+KeyPath]; UnicodeString
0x1800d1a52  call    cs:__imp_RtlFreeUnicodeString
0x1800d1a59  nop     dword ptr [rax+rax+00h]
0x1800d1a5e  test    ebx, ebx
0x1800d1a60  js      short loc_1800D1A66
0x1800d1a62  or      qword ptr [rdi], 2
0x1800d1a66  mov     eax, ebx
0x1800d1a68  add     rsp, 0E8h
0x1800d1a6f  pop     rdi
0x1800d1a70  pop     rsi
0x1800d1a71  pop     rbx
0x1800d1a72  pop     rbp
0x1800d1a73  retn
0x1800d1a75  xor     r9d, r9d
0x1800d1a78  mov     [rsp+100h+var_E0], rbx
0x1800d1a7d  lea     r8, [rbp+57h+var_88]
0x1800d1a81  mov     edx, esi
0x1800d1a83  mov     rcx, rdi
0x1800d1a86  call    Wow64NtOpenKey
0x1800d1a8b  mov     ebx, eax
0x1800d1a8d  jmp     short loc_1800D1A3E
0x1800d1a8f  lea     rcx, [rbp+57h+KeyPath]; UnicodeString
0x1800d1a93  call    cs:__imp_RtlFreeUnicodeString
0x1800d1a9a  nop     dword ptr [rax+rax+00h]
0x1800d1a9f  mov     eax, 0C000009Ah
0x1800d1aa4  jmp     short loc_1800D1A68
0x1800d1aa6  mov     eax, [rbp+57h+KeySetInformation]
0x1800d1aa9  test    eax, eax
0x1800d1aab  jz      short loc_1800D1A35
0x1800d1aad  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800d1ab1  lea     r8, [rbp+57h+KeySetInformation]; KeySetInformation
0x1800d1ab5  mov     r9d, 4; KeySetInformationLength
0x1800d1abb  and     eax, 0F01h
0x1800d1ac0  mov     [rbp+57h+KeySetInformation], eax
0x1800d1ac3  lea     edx, [r9+1]; KeySetInformationClass
0x1800d1ac7  call    cs:__imp_NtSetInformationKey
0x1800d1ace  nop     dword ptr [rax+rax+00h]
0x1800d1ad3  mov     ebx, eax
0x1800d1ad5  test    eax, eax
0x1800d1ad7  jns     loc_1800D1A35
0x1800d1add  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800d1ae1  call    cs:__imp_NtClose
0x1800d1ae8  nop     dword ptr [rax+rax+00h]
0x1800d1aed  jmp     loc_1800D1A3E
```
