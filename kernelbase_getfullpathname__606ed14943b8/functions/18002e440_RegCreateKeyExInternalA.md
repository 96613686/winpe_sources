# RegCreateKeyExInternalA

- ea: `0x18002e440`
- end: `0x18002e7c8`
- name: `RegCreateKeyExInternalA`
- size: `904`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18002e300`
- `0x18002e360`

## callees

- `0x18002e440`
- `0x18005cc70`
- `0x18005e7e0`
- `0x18005feb0`
- `0x1800ebed0`
- `0x180136e28`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x18002e626`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18002e626`
- `ntdll!RtlFreeUnicodeString` at `0x18002e5a0`
- `ntdll!RtlFreeUnicodeString` at `0x18002e5ba`
- `ntdll!RtlFreeUnicodeString` at `0x18002e7b7`
- `ntdll!RtlFreeUnicodeString` at `0x18002e5a0`
- `ntdll!RtlFreeUnicodeString` at `0x18002e5ba`
- `ntdll!RtlFreeUnicodeString` at `0x18002e7b7`
- `ntdll!RtlNtStatusToDosError` at `0x18002e77d`
- `ntdll!RtlNtStatusToDosError` at `0x18002e79f`
- `ntdll!RtlNtStatusToDosError` at `0x18002e77d`
- `ntdll!RtlNtStatusToDosError` at `0x18002e79f`
- `ntdll!RtlInitAnsiStringEx` at `0x18002e602`
- `ntdll!RtlInitAnsiStringEx` at `0x18002e602`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18002e4f9`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18002e4f9`
- `ntdll!RtlFreeHeap` at `0x18002e76a`
- `ntdll!RtlFreeHeap` at `0x18002e76a`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18002e724`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18002e724`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegCreateKey` at `0x18002e6d7`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegCreateKey` at `0x18002e6d7`

## pseudocode

```c
__int64 __fastcall RegCreateKeyExInternalA(
        void *a1,
        const char *a2,
        int a3,
        const char *a4,
        ULONG a5,
        int a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  HANDLE *v12; // r15
  ULONG v13; // edi
  PVOID *v14; // rsi
  unsigned __int64 v15; // r14
  int inited; // eax
  unsigned __int64 v18; // r14
  char v19; // al
  unsigned int v20; // ecx
  int v21; // [rsp+30h] [rbp-A8h]
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-88h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+60h] [rbp-78h] BYREF
  ULONG v24; // [rsp+70h] [rbp-68h]
  PVOID *v25; // [rsp+78h] [rbp-60h]
  __int64 v26; // [rsp+80h] [rbp-58h] BYREF
  __int64 v27; // [rsp+88h] [rbp-50h] BYREF
  struct _STRING DestinationString; // [rsp+90h] [rbp-48h] BYREF
  _BYTE v29[32]; // [rsp+A0h] [rbp-38h] BYREF
  HANDLE KeyHandle; // [rsp+E0h] [rbp+8h] BYREF

  KeyHandle = a1;
  Destination = 0;
  UnicodeString = 0;
  DestinationString = 0;
  memset(v29, 0, 28);
  v27 = 0;
  v26 = 0;
  if ( a1 == (void *)-2147483644LL || a1 == (void *)-2147483568LL || a1 == (void *)-2147483552LL )
    return 6;
  if ( a3 )
    return 87;
  if ( a2 )
  {
    v12 = (HANDLE *)a8;
    if ( a8 )
    {
      v13 = MapPredefinedHandleInternal(a1, &KeyHandle, &v27, &v26);
      if ( v13 )
      {
LABEL_18:
        CLOSE_LOCAL_HANDLE_INTERNAL(v27, v26);
        return v13;
      }
      if ( !RtlCreateUnicodeStringFromAsciiz(&Destination, a2) )
      {
        v13 = RtlNtStatusToDosError(-1073741801);
        goto LABEL_18;
      }
      Destination.Length += 2;
      if ( a4 )
      {
        inited = RtlInitAnsiStringEx(&DestinationString, a4);
        if ( inited < 0 || (inited = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u), inited < 0) )
        {
          v13 = RtlNtStatusToDosError(inited);
          goto LABEL_17;
        }
        UnicodeString.Length += 2;
      }
      else
      {
        *(_DWORD *)&UnicodeString.Length = 0;
        UnicodeString.Buffer = 0;
      }
      if ( !a7 )
      {
        v14 = 0;
LABEL_13:
        v25 = v14;
        v15 = (unsigned __int64)KeyHandle;
        if ( ((unsigned __int8)KeyHandle & 1) != 0 )
        {
          if ( (unsigned __int8)IsBaseRegCloseKeyPresent() )
          {
            LODWORD(KeyHandle) = 0;
            v18 = v15 & 0xFFFFFFFFFFFFFFFEuLL;
            if ( !(unsigned __int8)IsBaseRegCloseKeyPresent()
              || (unsigned int)BaseRegGetVersion(v18, &KeyHandle)
              || (v19 = 1, (_DWORD)KeyHandle != 6) )
            {
              v19 = 0;
            }
            v20 = a6 & 0xFFFFFCFF;
            if ( v19 )
              v20 = a6;
            v13 = BaseRegCreateKey(v18, &Destination, &UnicodeString, a5, v20, v14, v12, a9);
            v24 = v13;
            if ( !v13 )
              *v12 = (HANDLE)((unsigned __int64)*v12 | 1);
          }
        }
        else
        {
          v13 = BaseRegCreateKeyInternal(
                  KeyHandle,
                  &Destination,
                  &UnicodeString,
                  a5,
                  a6,
                  (__int64)v14,
                  v21,
                  v12,
                  (_DWORD *)a9,
                  (void *)a10);
        }
        RtlFreeUnicodeString(&UnicodeString);
        if ( v14 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14[1]);
        goto LABEL_17;
      }
      v13 = MapSAToRpcSA(a7, v29);
      if ( !v13 )
      {
        v14 = (PVOID *)v29;
        goto LABEL_13;
      }
      RtlFreeUnicodeString(&UnicodeString);
LABEL_17:
      RtlFreeUnicodeString(&Destination);
      goto LABEL_18;
    }
  }
  return 1010;
}

```

## disassembly

```asm
0x18002e440  mov     r11, rsp
0x18002e443  mov     [r11+10h], rbx
0x18002e447  mov     [r11+18h], rsi
0x18002e44b  mov     [r11+8], rcx
0x18002e44f  push    rdi
0x18002e450  push    r14
0x18002e452  push    r15
0x18002e454  sub     rsp, 0C0h
0x18002e45b  mov     r14, r9
0x18002e45e  mov     rsi, rdx
0x18002e461  xorps   xmm0, xmm0
0x18002e464  movups  xmmword ptr [rsp+0D8h+Destination.Length], xmm0
0x18002e469  xorps   xmm1, xmm1
0x18002e46c  movups  xmmword ptr [rsp+0D8h+UnicodeString.Length], xmm1
0x18002e471  movups  xmmword ptr [r11-48h], xmm0
0x18002e476  xor     eax, eax
0x18002e478  movups  xmmword ptr [r11-38h], xmm0
0x18002e47d  movups  xmmword ptr [r11-2Ch], xmm0
0x18002e482  xor     ebx, ebx
0x18002e484  mov     [r11-50h], rbx
0x18002e488  mov     [r11-58h], rbx
0x18002e48c  cmp     rcx, 0FFFFFFFF80000004h
0x18002e493  jz      loc_18002E74D
0x18002e499  cmp     rcx, 0FFFFFFFF80000050h
0x18002e4a0  jz      loc_18002E74D
0x18002e4a6  cmp     rcx, 0FFFFFFFF80000060h
0x18002e4ad  jz      loc_18002E74D
0x18002e4b3  test    r8d, r8d
0x18002e4b6  jnz     loc_18002E790
0x18002e4bc  test    rdx, rdx
0x18002e4bf  jz      loc_18002E70F
0x18002e4c5  mov     r15, [rsp+0D8h+arg_38]
0x18002e4cd  test    r15, r15
0x18002e4d0  jz      loc_18002E70F
0x18002e4d6  lea     r9, [r11-58h]
0x18002e4da  lea     r8, [r11-50h]
0x18002e4de  lea     rdx, [r11+8]
0x18002e4e2  call    MapPredefinedHandleInternal
0x18002e4e7  mov     edi, eax
0x18002e4e9  test    eax, eax
0x18002e4eb  jnz     loc_18002E5C6
0x18002e4f1  mov     rdx, rsi; Source
0x18002e4f4  lea     rcx, [rsp+0D8h+Destination]; Destination
0x18002e4f9  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18002e500  nop     dword ptr [rax+rax+00h]
0x18002e505  test    al, al
0x18002e507  jz      loc_18002E79A
0x18002e50d  add     [rsp+0D8h+Destination.Length], 2
0x18002e513  test    r14, r14
0x18002e516  jnz     loc_18002E5F7
0x18002e51c  mov     dword ptr [rsp+0D8h+UnicodeString.Length], ebx
0x18002e520  mov     [rsp+0D8h+UnicodeString.Buffer], rbx
0x18002e525  mov     rcx, [rsp+0D8h+arg_30]
0x18002e52d  test    rcx, rcx
0x18002e530  jnz     loc_18002E645
0x18002e536  mov     rsi, rbx
0x18002e539  mov     [rsp+0D8h+var_60], rsi
0x18002e53e  mov     r14, [rsp+0D8h+KeyHandle]
0x18002e546  test    r14b, 1
0x18002e54a  jnz     loc_18002E669
0x18002e550  mov     rax, [rsp+0D8h+arg_48]
0x18002e558  mov     [rsp+0D8h+var_90], rax; __int64
0x18002e55d  mov     rax, [rsp+0D8h+arg_40]
0x18002e565  mov     [rsp+0D8h+var_98], rax; __int64
0x18002e56a  mov     [rsp+0D8h+var_A0], r15; __int64
0x18002e56f  mov     [rsp+0D8h+var_B0], rsi; __int64
0x18002e574  mov     eax, [rsp+0D8h+arg_28]
0x18002e57b  mov     [rsp+0D8h+var_B8], eax; int
0x18002e57f  mov     r9d, [rsp+0D8h+arg_20]
0x18002e587  lea     r8, [rsp+0D8h+UnicodeString]
0x18002e58c  lea     rdx, [rsp+0D8h+Destination]; Source
0x18002e591  mov     rcx, r14; KeyHandle
0x18002e594  call    BaseRegCreateKeyInternal
0x18002e599  mov     edi, eax
0x18002e59b  lea     rcx, [rsp+0D8h+UnicodeString]; UnicodeString
0x18002e5a0  call    cs:__imp_RtlFreeUnicodeString
0x18002e5a7  nop     dword ptr [rax+rax+00h]
0x18002e5ac  test    rsi, rsi
0x18002e5af  jnz     loc_18002E757
0x18002e5b5  lea     rcx, [rsp+0D8h+Destination]; UnicodeString
0x18002e5ba  call    cs:__imp_RtlFreeUnicodeString
0x18002e5c1  nop     dword ptr [rax+rax+00h]
0x18002e5c6  mov     rdx, [rsp+0D8h+var_58]
0x18002e5ce  mov     rcx, [rsp+0D8h+var_50]
0x18002e5d6  call    CLOSE_LOCAL_HANDLE_INTERNAL
0x18002e5db  mov     eax, edi
0x18002e5dd  lea     r11, [rsp+0D8h+var_18]
0x18002e5e5  mov     rbx, [r11+28h]
0x18002e5e9  mov     rsi, [r11+30h]
0x18002e5ed  mov     rsp, r11
0x18002e5f0  pop     r15
0x18002e5f2  pop     r14
0x18002e5f4  pop     rdi
0x18002e5f5  retn
0x18002e5f7  mov     rdx, r14; SourceString
0x18002e5fa  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x18002e602  call    cs:__imp_RtlInitAnsiStringEx
0x18002e609  nop     dword ptr [rax+rax+00h]
0x18002e60e  test    eax, eax
0x18002e610  js      loc_18002E77B
0x18002e616  mov     r8b, 1; AllocateDestinationString
0x18002e619  lea     rdx, [rsp+0D8h+DestinationString]; SourceString
0x18002e621  lea     rcx, [rsp+0D8h+UnicodeString]; DestinationString
0x18002e626  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18002e62d  nop     dword ptr [rax+rax+00h]
0x18002e632  test    eax, eax
0x18002e634  js      loc_18002E77B
0x18002e63a  add     [rsp+0D8h+UnicodeString.Length], 2
0x18002e640  jmp     loc_18002E525
0x18002e645  lea     rdx, [rsp+0D8h+var_38]
0x18002e64d  call    MapSAToRpcSA
0x18002e652  mov     edi, eax
0x18002e654  test    eax, eax
0x18002e656  jnz     loc_18002E7B2
0x18002e65c  lea     rsi, [rsp+0D8h+var_38]
0x18002e664  jmp     loc_18002E539
0x18002e669  call    IsBaseRegCloseKeyPresent
0x18002e66e  test    al, al
0x18002e670  jz      loc_18002E59B
0x18002e676  mov     dword ptr [rsp+0D8h+KeyHandle], ebx
0x18002e67d  and     r14, 0FFFFFFFFFFFFFFFEh
0x18002e681  call    IsBaseRegCloseKeyPresent
0x18002e686  test    al, al
0x18002e688  jnz     loc_18002E719
0x18002e68e  mov     al, bl
0x18002e690  mov     ecx, [rsp+0D8h+arg_28]
0x18002e697  and     ecx, 0FFFFFCFFh
0x18002e69d  test    al, al
0x18002e69f  cmovnz  ecx, [rsp+0D8h+arg_28]
0x18002e6a7  mov     rax, [rsp+0D8h+arg_40]
0x18002e6af  mov     [rsp+0D8h+var_A0], rax
0x18002e6b4  mov     [rsp+0D8h+var_A8], r15
0x18002e6b9  mov     [rsp+0D8h+var_B0], rsi
0x18002e6be  mov     [rsp+0D8h+var_B8], ecx
0x18002e6c2  mov     r9d, [rsp+0D8h+arg_20]
0x18002e6ca  lea     r8, [rsp+0D8h+UnicodeString]
0x18002e6cf  lea     rdx, [rsp+0D8h+Destination]
0x18002e6d4  mov     rcx, r14
0x18002e6d7  call    cs:__imp_BaseRegCreateKey
0x18002e6de  nop     dword ptr [rax+rax+00h]
0x18002e6e3  mov     edi, eax
0x18002e6e5  mov     [rsp+0D8h+var_68], eax
0x18002e6e9  jmp     short loc_18002E6FE
0x18002e6eb  mov     edi, eax
0x18002e6ed  mov     [rsp+0D8h+var_68], eax
0x18002e6f1  mov     r15, [rsp+0D8h+arg_38]
0x18002e6f9  mov     rsi, [rsp+0D8h+var_60]
0x18002e6fe  test    edi, edi
0x18002e700  jnz     loc_18002E59B
0x18002e706  or      qword ptr [r15], 1
0x18002e70a  jmp     loc_18002E59B
0x18002e70f  mov     eax, 3F2h
0x18002e714  jmp     loc_18002E5DD
0x18002e719  lea     rdx, [rsp+0D8h+KeyHandle]
0x18002e721  mov     rcx, r14
0x18002e724  call    cs:__imp_BaseRegGetVersion
0x18002e72b  nop     dword ptr [rax+rax+00h]
0x18002e730  test    eax, eax
0x18002e732  jnz     loc_18002E68E
0x18002e738  cmp     dword ptr [rsp+0D8h+KeyHandle], 6
0x18002e740  mov     al, 1
0x18002e742  jz      loc_18002E690
0x18002e748  jmp     loc_18002E68E
0x18002e74d  mov     eax, 6
0x18002e752  jmp     loc_18002E5DD
0x18002e757  mov     rcx, gs:60h
0x18002e760  mov     r8, [rsi+8]; P
0x18002e764  xor     edx, edx; Flags
0x18002e766  mov     rcx, [rcx+30h]; HeapHandle
0x18002e76a  call    cs:__imp_RtlFreeHeap
0x18002e771  nop     dword ptr [rax+rax+00h]
0x18002e776  jmp     loc_18002E5B5
0x18002e77b  mov     ecx, eax; Status
0x18002e77d  call    cs:__imp_RtlNtStatusToDosError
0x18002e784  nop     dword ptr [rax+rax+00h]
0x18002e789  mov     edi, eax
0x18002e78b  jmp     loc_18002E5B5
0x18002e790  mov     eax, 57h ; 'W'
0x18002e795  jmp     loc_18002E5DD
0x18002e79a  mov     ecx, 0C0000017h; Status
0x18002e79f  call    cs:__imp_RtlNtStatusToDosError
0x18002e7a6  nop     dword ptr [rax+rax+00h]
0x18002e7ab  mov     edi, eax
0x18002e7ad  jmp     loc_18002E5C6
0x18002e7b2  lea     rcx, [rsp+0D8h+UnicodeString]; UnicodeString
0x18002e7b7  call    cs:__imp_RtlFreeUnicodeString
0x18002e7be  nop     dword ptr [rax+rax+00h]
0x18002e7c3  jmp     loc_18002E5B5
```
