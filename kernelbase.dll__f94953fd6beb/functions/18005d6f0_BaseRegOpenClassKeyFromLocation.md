# BaseRegOpenClassKeyFromLocation

- ea: `0x18005d6f0`
- end: `0x18005dd1c`
- name: `BaseRegOpenClassKeyFromLocation`
- size: `1580`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180051e34`
- `0x18005a0c0`
- `0x18005bf10`
- `0x18005e150`
- `0x18005e2a0`
- `0x18005e890`
- `0x18005f0f8`
- `0x180061268`
- `0x1800a6880`

## callees

- `0x18005cb00`
- `0x18005cc40`
- `0x18005d6f0`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18005d8ac`
- `ntdll!RtlFreeUnicodeString` at `0x18005d8ac`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005d8d7`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005da70`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005d8d7`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005da70`
- `ntdll!RtlAppendUnicodeToString` at `0x18005d8be`
- `ntdll!RtlAppendUnicodeToString` at `0x18005d8be`
- `ntdll!RtlCopyUnicodeString` at `0x18005d8a1`
- `ntdll!RtlCopyUnicodeString` at `0x18005da60`
- `ntdll!RtlCopyUnicodeString` at `0x18005d8a1`
- `ntdll!RtlCopyUnicodeString` at `0x18005da60`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005da18`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005da18`
- `ntdll!NtClose` at `0x18005dc64`
- `ntdll!NtClose` at `0x18005dcae`
- `ntdll!NtClose` at `0x18005dc64`
- `ntdll!NtClose` at `0x18005dcae`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18005d887`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x18005d887`
- `ntdll!NtQueryKey` at `0x18005d7f9`
- `ntdll!NtQueryKey` at `0x18005d7f9`
- `ntdll!RtlFreeHeap` at `0x18005d9c0`
- `ntdll!RtlFreeHeap` at `0x18005db54`
- `ntdll!RtlFreeHeap` at `0x18005db9b`
- `ntdll!RtlFreeHeap` at `0x18005d9c0`
- `ntdll!RtlFreeHeap` at `0x18005db54`
- `ntdll!RtlFreeHeap` at `0x18005db9b`
- `ntdll!RtlAllocateHeap` at `0x18005d778`
- `ntdll!RtlAllocateHeap` at `0x18005d778`
- `ntdll!NtOpenKeyEx` at `0x18005d99c`
- `ntdll!NtOpenKeyEx` at `0x18005db33`
- `ntdll!NtOpenKeyEx` at `0x18005d99c`
- `ntdll!NtOpenKeyEx` at `0x18005db33`
- `ntdll!NtSetInformationKey` at `0x18005dc4f`
- `ntdll!NtSetInformationKey` at `0x18005dc99`
- `ntdll!NtSetInformationKey` at `0x18005dc4f`
- `ntdll!NtSetInformationKey` at `0x18005dc99`

## string_xrefs

- `0x18005da01`: `\Registry\Machine\Software\Classes`

## pseudocode

```c
__int64 __fastcall BaseRegOpenClassKeyFromLocation(
        __int64 a1,
        void *a2,
        __int64 a3,
        int a4,
        char a5,
        char a6,
        HANDLE *a7,
        void *a8)
{
  _WORD *v9; // rax
  void *v11; // r10
  USHORT v12; // di
  WCHAR *Heap; // r15
  int v15; // edi
  unsigned int v16; // r14d
  int appended; // ebx
  char v18; // al
  unsigned int v19; // r14d
  __int16 v20; // di
  __int64 v21; // rdx
  _WORD *v22; // r8
  __int16 v23; // cx
  __int64 v24; // r9
  struct _UNICODE_STRING *p_DestinationString; // rax
  __int64 v26; // rcx
  _WORD *v27; // rdx
  __int64 v28; // r8
  struct _UNICODE_STRING *v29; // rax
  int v30; // edi
  _BYTE v31[4]; // [rsp+30h] [rbp-D0h] BYREF
  int KeyInformation; // [rsp+34h] [rbp-CCh] BYREF
  struct _UNICODE_STRING KeyPath; // [rsp+38h] [rbp-C8h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  PVOID P; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE KeyHandle[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  __int128 v38; // [rsp+78h] [rbp-88h] BYREF
  __int128 v39; // [rsp+88h] [rbp-78h]
  __int128 v40; // [rsp+98h] [rbp-68h]
  void *v41; // [rsp+A8h] [rbp-58h]
  UNICODE_STRING Source; // [rsp+B0h] [rbp-50h] BYREF
  UNICODE_STRING SourceString; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v44; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v45; // [rsp+E0h] [rbp-20h]
  __int128 v46; // [rsp+F0h] [rbp-10h]
  _BYTE v47[528]; // [rsp+100h] [rbp+0h] BYREF

  P = a8;
  *(_QWORD *)&SourceString.Length = a3;
  v9 = *(_WORD **)(a1 + 16);
  DestinationString = 0;
  v11 = a2;
  v41 = a2;
  DWORD1(v38) = 0;
  v12 = *v9 + 362;
  HIDWORD(v39) = 0;
  if ( v12 <= 0x208u )
  {
    Heap = (WCHAR *)v47;
  }
  else
  {
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
    if ( !Heap )
      return 3221225495LL;
    v11 = v41;
  }
  DestinationString.MaximumLength = v12;
  v15 = a4 & 0x300;
  v16 = a4 & 0xFFFFFCFF;
  appended = -1073741772;
  DestinationString.Buffer = Heap;
  if ( g_Win64Registry )
  {
    if ( !v15 )
    {
      KeyInformation = 0;
      ResultLength = 0;
      if ( NtQueryKey(v11, KeyHandleTagsInformation, &KeyInformation, 4u, &ResultLength) >= 0 )
        v15 = KeyInformation & 0x300;
    }
  }
  v18 = a5;
  v19 = v15 | v16;
  v20 = 1;
  if ( (a5 & 2) != 0 )
  {
    if ( (*(_BYTE *)a1 & 1) != 0 )
    {
      *((_QWORD *)&v38 + 1) = v41;
      DWORD2(v39) = 32 * (a6 & 8 | 2);
      p_DestinationString = *(struct _UNICODE_STRING **)&SourceString.Length;
    }
    else
    {
      v21 = *(unsigned __int16 *)(a1 + 4);
      v22 = *(_WORD **)(a1 + 16);
      Source = 0;
      if ( v22[v21 + 2] )
      {
        v23 = 1;
        v24 = 1;
      }
      else
      {
        v23 = 0;
        v24 = 0;
      }
      *(_OWORD *)KeyHandle = 0;
      KeyPath = 0;
      Source.Buffer = &v22[v21 - v24 + 2];
      Source.Length = *v22 + 2 * (v23 - v21);
      appended = RtlFormatCurrentUserKeyPath(&KeyPath);
      if ( appended < 0 )
        goto LABEL_41;
      RtlCopyUnicodeString(&DestinationString, &KeyPath);
      RtlFreeUnicodeString(&KeyPath);
      appended = RtlAppendUnicodeToString(&DestinationString, L"_Classes");
      if ( appended < 0 )
        goto LABEL_41;
      appended = RtlAppendUnicodeStringToString(&DestinationString, &Source);
      if ( appended < 0 )
        goto LABEL_41;
      *((_QWORD *)&v38 + 1) = 0;
      DWORD2(v39) = 32 * (a6 & 8 | 2);
      p_DestinationString = &DestinationString;
    }
    *(_QWORD *)&v39 = p_DestinationString;
    LODWORD(v38) = 48;
    v40 = 0;
    if ( P )
    {
      appended = Wow64NtOpenKey((_DWORD)a7, v19, (unsigned int)&v38, a6 & 0x1C, (__int64)P);
      goto LABEL_24;
    }
    *(_QWORD *)&Source.Length = 0;
    KeyInformation = 0;
    *(_QWORD *)&KeyPath.Length = 0;
    LOWORD(KeyPath.Buffer) = 0;
    BYTE2(KeyPath.Buffer) = 0;
    KeyHandle[0] = 0;
    v31[0] = 0;
    v44 = v38;
    v45 = v39;
    v46 = 0;
    appended = ConstructKernelKeyPath(
                 v19,
                 (unsigned int)&v44,
                 (unsigned int)&KeyInformation,
                 (unsigned int)&KeyPath,
                 (__int64)v31,
                 (__int64)&Source);
    if ( appended < 0 )
      goto LABEL_24;
    appended = NtOpenKeyEx(KeyHandle, v19, &v44, a6 & 0x1C);
    ResultLength = appended;
    if ( *(_QWORD *)&Source.Length )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)&Source.Length);
    if ( appended < 0 )
      goto LABEL_24;
    if ( v31[0] && KeyInformation )
    {
      KeyInformation &= 0xF01u;
      appended = NtSetInformationKey(KeyHandle[0], KeySetHandleTagsInformation, &KeyInformation, 4u);
      if ( appended < 0 )
      {
        NtClose(KeyHandle[0]);
        goto LABEL_24;
      }
      appended = ResultLength;
    }
    *a7 = KeyHandle[0];
LABEL_24:
    v18 = a5;
  }
  if ( (v18 & 1) == 0 )
  {
    if ( appended < 0 )
      goto LABEL_41;
LABEL_45:
    *a7 = (HANDLE)((unsigned __int64)*a7 | 2);
    goto LABEL_41;
  }
  if ( appended >= 0 )
    goto LABEL_45;
  if ( (*(_BYTE *)a1 & 2) != 0 )
  {
    *((_QWORD *)&v38 + 1) = v41;
    DWORD2(v39) = 32 * (a6 & 8 | 2);
    v29 = *(struct _UNICODE_STRING **)&SourceString.Length;
  }
  else
  {
    SourceString = 0;
    KeyPath = 0;
    RtlInitUnicodeStringEx(&SourceString, L"\\Registry\\Machine\\Software\\Classes");
    v26 = *(unsigned __int16 *)(a1 + 4);
    v27 = *(_WORD **)(a1 + 16);
    if ( v27[v26 + 2] )
    {
      v28 = 1;
    }
    else
    {
      v20 = 0;
      v28 = 0;
    }
    KeyPath.Buffer = &v27[v26 - v28 + 2];
    KeyPath.Length = *v27 + 2 * (v20 - v26);
    RtlCopyUnicodeString(&DestinationString, &SourceString);
    appended = RtlAppendUnicodeStringToString(&DestinationString, &KeyPath);
    if ( appended < 0 )
      goto LABEL_41;
    *((_QWORD *)&v38 + 1) = 0;
    DWORD2(v39) = 32 * (a6 & 8 | 2);
    v29 = &DestinationString;
  }
  *(_QWORD *)&v39 = v29;
  LODWORD(v38) = 48;
  v40 = 0;
  if ( !P )
  {
    *(_QWORD *)&KeyPath.Length = 0;
    LOWORD(KeyPath.Buffer) = 0;
    BYTE2(KeyPath.Buffer) = 0;
    v31[0] = 0;
    P = 0;
    v44 = v38;
    KeyInformation = 0;
    v45 = v39;
    KeyHandle[0] = 0;
    v46 = 0;
    appended = ConstructKernelKeyPath(
                 v19,
                 (unsigned int)&v44,
                 (unsigned int)&KeyInformation,
                 (unsigned int)&KeyPath,
                 (__int64)v31,
                 (__int64)&P);
    if ( appended < 0 )
      goto LABEL_40;
    v30 = NtOpenKeyEx(KeyHandle, v19, &v44, a6 & 0x1C);
    if ( P )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    if ( v30 >= 0 )
    {
      if ( v31[0] )
      {
        if ( KeyInformation )
        {
          KeyInformation &= 0xF01u;
          appended = NtSetInformationKey(KeyHandle[0], KeySetHandleTagsInformation, &KeyInformation, 4u);
          if ( appended < 0 )
          {
            NtClose(KeyHandle[0]);
            goto LABEL_40;
          }
        }
      }
      *a7 = KeyHandle[0];
    }
    appended = v30;
    goto LABEL_40;
  }
  appended = Wow64NtOpenKey((_DWORD)a7, v19, (unsigned int)&v38, a6 & 0x1C, (__int64)P);
LABEL_40:
  if ( appended >= 0 )
    goto LABEL_45;
LABEL_41:
  if ( Heap != (WCHAR *)v47 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18005d6f0  push    rbp
0x18005d6f2  push    rsi
0x18005d6f3  push    rdi
0x18005d6f4  push    r12
0x18005d6f6  push    r14
0x18005d6f8  push    r15
0x18005d6fa  lea     rbp, [rsp-238h]
0x18005d702  sub     rsp, 338h
0x18005d709  mov     rax, cs:__security_cookie
0x18005d710  xor     rax, rsp
0x18005d713  mov     [rbp+260h+var_50], rax
0x18005d71a  mov     rax, [rbp+260h+arg_38]
0x18005d721  mov     rsi, rcx
0x18005d724  mov     r12, [rbp+260h+arg_30]
0x18005d72b  xor     ecx, ecx
0x18005d72d  mov     [rsp+360h+P], rax
0x18005d732  xorps   xmm0, xmm0
0x18005d735  mov     edi, 16Ah
0x18005d73a  mov     qword ptr [rbp+260h+SourceString.Length], r8
0x18005d73e  mov     rax, [rsi+10h]
0x18005d742  mov     r14d, r9d
0x18005d745  movups  xmmword ptr [rsp+360h+DestinationString.Length], xmm0
0x18005d74a  mov     r10, rdx
0x18005d74d  mov     [rbp+260h+var_2B8], rdx
0x18005d751  mov     dword ptr [rsp+360h+var_2E8+4], ecx
0x18005d755  add     di, [rax]
0x18005d758  mov     eax, 208h
0x18005d75d  mov     dword ptr [rbp+260h+var_2D8+0Ch], ecx
0x18005d760  cmp     di, ax
0x18005d763  jbe     short loc_18005D794
0x18005d765  mov     rcx, gs:60h
0x18005d76e  xor     edx, edx; Flags
0x18005d770  movzx   r8d, di; Size
0x18005d774  mov     rcx, [rcx+30h]; HeapHandle
0x18005d778  call    cs:__imp_RtlAllocateHeap
0x18005d77e  mov     r15, rax
0x18005d781  test    rax, rax
0x18005d784  jnz     loc_18005DBD6
0x18005d78a  mov     eax, 0C0000017h
0x18005d78f  jmp     loc_18005DBAB
0x18005d794  lea     r15, [rbp+260h+var_260]
0x18005d798  mov     [rsp+360h+DestinationString.MaximumLength], di
0x18005d79d  mov     edi, r14d
0x18005d7a0  mov     [rsp+360h+var_30], rbx
0x18005d7a8  and     edi, 300h
0x18005d7ae  and     r14d, 0FFFFFCFFh
0x18005d7b5  mov     [rsp+360h+var_38], r13
0x18005d7bd  cmp     cs:g_Win64Registry, 0
0x18005d7c4  mov     ebx, 0C0000034h
0x18005d7c9  mov     [rsp+360h+DestinationString.Buffer], r15
0x18005d7ce  jz      short loc_18005D80D
0x18005d7d0  test    edi, edi
0x18005d7d2  jnz     short loc_18005D80D
0x18005d7d4  mov     [rsp+360h+KeyInformation], ecx
0x18005d7d8  lea     rax, [rsp+360h+var_318]
0x18005d7dd  mov     [rsp+360h+var_318], ecx
0x18005d7e1  lea     r8, [rsp+360h+KeyInformation]; KeyInformation
0x18005d7e6  mov     rcx, r10; KeyHandle
0x18005d7e9  mov     [rsp+360h+ResultLength], rax; ResultLength
0x18005d7ee  mov     r9d, 4; Length
0x18005d7f4  mov     edx, 7; KeyInformationClass
0x18005d7f9  call    cs:__imp_NtQueryKey
0x18005d7ff  test    eax, eax
0x18005d801  js      short loc_18005D80D
0x18005d803  mov     edi, [rsp+360h+KeyInformation]
0x18005d807  and     edi, 300h
0x18005d80d  mov     eax, dword ptr [rbp+260h+arg_20]
0x18005d813  or      r14d, edi
0x18005d816  mov     r13d, dword ptr [rbp+260h+arg_28]
0x18005d81d  mov     edi, 1
0x18005d822  test    al, 2
0x18005d824  jz      loc_18005D9E4
0x18005d82a  test    [rsi], dil
0x18005d82d  jnz     loc_18005DBE1
0x18005d833  movzx   edx, word ptr [rsi+4]
0x18005d837  xorps   xmm0, xmm0
0x18005d83a  mov     r8, [rsi+10h]
0x18005d83e  movups  xmmword ptr [rbp+260h+Source.Length], xmm0
0x18005d842  cmp     word ptr [r8+rdx*2+4], 0
0x18005d849  jz      loc_18005DCFF
0x18005d84f  movzx   ecx, di
0x18005d852  mov     r9d, edi
0x18005d855  sub     cx, dx
0x18005d858  mov     rax, rdx
0x18005d85b  sub     rax, r9
0x18005d85e  add     cx, cx
0x18005d861  add     rax, 2
0x18005d865  xorps   xmm1, xmm1
0x18005d868  movups  xmmword ptr [rsp+360h+KeyHandle], xmm0
0x18005d86d  movups  xmmword ptr [rsp+360h+KeyPath.Length], xmm1
0x18005d872  lea     rax, [r8+rax*2]
0x18005d876  mov     [rbp+260h+Source.Buffer], rax
0x18005d87a  add     cx, [r8]
0x18005d87e  mov     [rbp+260h+Source.Length], cx
0x18005d882  lea     rcx, [rsp+360h+KeyPath]; KeyPath
0x18005d887  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x18005d88d  mov     ebx, eax
0x18005d88f  test    eax, eax
0x18005d891  js      loc_18005DB78
0x18005d897  lea     rdx, [rsp+360h+KeyPath]; SourceString
0x18005d89c  lea     rcx, [rsp+360h+DestinationString]; DestinationString
0x18005d8a1  call    cs:__imp_RtlCopyUnicodeString
0x18005d8a7  lea     rcx, [rsp+360h+KeyPath]; UnicodeString
0x18005d8ac  call    cs:__imp_RtlFreeUnicodeString
0x18005d8b2  lea     rdx, aClasses_0; "_Classes"
0x18005d8b9  lea     rcx, [rsp+360h+DestinationString]; Destination
0x18005d8be  call    cs:__imp_RtlAppendUnicodeToString
0x18005d8c4  mov     ebx, eax
0x18005d8c6  test    eax, eax
0x18005d8c8  js      loc_18005DB78
0x18005d8ce  lea     rdx, [rbp+260h+Source]; Source
0x18005d8d2  lea     rcx, [rsp+360h+DestinationString]; Destination
0x18005d8d7  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005d8dd  mov     ebx, eax
0x18005d8df  test    eax, eax
0x18005d8e1  js      loc_18005DB78
0x18005d8e7  movzx   eax, r13b
0x18005d8eb  and     eax, 8
0x18005d8ee  mov     qword ptr [rbp+260h+var_2E8+8], 0
0x18005d8f6  or      eax, 2
0x18005d8f9  shl     eax, 5
0x18005d8fc  mov     dword ptr [rbp+260h+var_2D8+8], eax
0x18005d8ff  lea     rax, [rsp+360h+DestinationString]
0x18005d904  mov     qword ptr [rbp+260h+var_2D8], rax
0x18005d908  xorps   xmm2, xmm2
0x18005d90b  mov     rax, [rsp+360h+P]
0x18005d910  mov     dword ptr [rsp+360h+var_2E8], 30h ; '0'
0x18005d918  movdqu  [rbp+260h+var_2C8], xmm2
0x18005d91d  test    rax, rax
0x18005d920  jnz     loc_18005DCDC
0x18005d926  movups  xmm0, [rsp+360h+var_2E8]
0x18005d92b  mov     qword ptr [rbp+260h+Source.Length], rax
0x18005d92f  lea     r9, [rsp+360h+KeyPath]
0x18005d934  movups  xmm1, [rbp+260h+var_2D8]
0x18005d938  mov     [rsp+360h+KeyInformation], eax
0x18005d93c  lea     r8, [rsp+360h+KeyInformation]
0x18005d941  mov     qword ptr [rsp+360h+KeyPath.Length], rax
0x18005d946  lea     rdx, [rbp+260h+var_290]
0x18005d94a  mov     word ptr [rsp+360h+KeyPath.Buffer], ax
0x18005d94f  mov     ecx, r14d
0x18005d952  mov     byte ptr [rsp+360h+KeyPath.Buffer+2], al
0x18005d956  mov     [rsp+360h+KeyHandle], rax
0x18005d95b  mov     [rsp+360h+var_330], al
0x18005d95f  lea     rax, [rbp+260h+Source]
0x18005d963  mov     [rsp+360h+var_338], rax
0x18005d968  lea     rax, [rsp+360h+var_330]
0x18005d96d  mov     [rsp+360h+ResultLength], rax
0x18005d972  movups  [rbp+260h+var_290], xmm0
0x18005d976  movups  [rbp+260h+var_280], xmm1
0x18005d97a  movups  [rbp+260h+var_270], xmm2
0x18005d97e  call    ConstructKernelKeyPath
0x18005d983  mov     ebx, eax
0x18005d985  test    eax, eax
0x18005d987  js      short loc_18005D9DE
0x18005d989  mov     r9d, r13d
0x18005d98c  lea     r8, [rbp+260h+var_290]
0x18005d990  and     r9d, 1Ch
0x18005d994  lea     rcx, [rsp+360h+KeyHandle]
0x18005d999  mov     edx, r14d
0x18005d99c  call    cs:__imp_NtOpenKeyEx
0x18005d9a2  mov     r8, qword ptr [rbp+260h+Source.Length]; P
0x18005d9a6  mov     ebx, eax
0x18005d9a8  mov     [rsp+360h+var_318], eax
0x18005d9ac  test    r8, r8
0x18005d9af  jz      short loc_18005D9C6
0x18005d9b1  mov     rcx, gs:60h
0x18005d9ba  xor     edx, edx; Flags
0x18005d9bc  mov     rcx, [rcx+30h]; HeapHandle
0x18005d9c0  call    cs:__imp_RtlFreeHeap
0x18005d9c6  test    ebx, ebx
0x18005d9c8  js      short loc_18005D9DE
0x18005d9ca  cmp     [rsp+360h+var_330], 0
0x18005d9cf  jnz     loc_18005DC25
0x18005d9d5  mov     rax, [rsp+360h+KeyHandle]
0x18005d9da  mov     [r12], rax
0x18005d9de  mov     eax, dword ptr [rbp+260h+arg_20]
0x18005d9e4  test    dil, al
0x18005d9e7  jz      loc_18005DBCB
0x18005d9ed  test    ebx, ebx
0x18005d9ef  jns     loc_18005DBCF
0x18005d9f5  test    byte ptr [rsi], 2
0x18005d9f8  jnz     loc_18005DC02
0x18005d9fe  xorps   xmm0, xmm0
0x18005da01  lea     rdx, aRegistryMachin_17; "\\Registry\\Machine\\Software\\Classes"
0x18005da08  xorps   xmm1, xmm1
0x18005da0b  lea     rcx, [rbp+260h+SourceString]; DestinationString
0x18005da0f  movups  xmmword ptr [rbp+260h+SourceString.Length], xmm0
0x18005da13  movups  xmmword ptr [rsp+360h+KeyPath.Length], xmm1
0x18005da18  call    cs:__imp_RtlInitUnicodeStringEx
0x18005da1e  movzx   ecx, word ptr [rsi+4]
0x18005da22  mov     rdx, [rsi+10h]
0x18005da26  xor     esi, esi
0x18005da28  cmp     [rdx+rcx*2+4], si
0x18005da2d  jz      loc_18005DD12
0x18005da33  mov     r8, rdi
0x18005da36  sub     di, cx
0x18005da39  mov     rax, rcx
0x18005da3c  sub     rax, r8
0x18005da3f  lea     rcx, [rsp+360h+DestinationString]; DestinationString
0x18005da44  add     rax, 2
0x18005da48  add     di, di
0x18005da4b  lea     rax, [rdx+rax*2]
0x18005da4f  mov     [rsp+360h+KeyPath.Buffer], rax
0x18005da54  add     di, [rdx]
0x18005da57  lea     rdx, [rbp+260h+SourceString]; SourceString
0x18005da5b  mov     [rsp+360h+KeyPath.Length], di
0x18005da60  call    cs:__imp_RtlCopyUnicodeString
0x18005da66  lea     rdx, [rsp+360h+KeyPath]; Source
0x18005da6b  lea     rcx, [rsp+360h+DestinationString]; Destination
0x18005da70  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005da76  mov     ebx, eax
0x18005da78  test    eax, eax
0x18005da7a  js      loc_18005DB78
0x18005da80  movzx   eax, r13b
0x18005da84  and     eax, 8
0x18005da87  mov     qword ptr [rbp+260h+var_2E8+8], rsi
0x18005da8b  or      eax, 2
0x18005da8e  shl     eax, 5
0x18005da91  mov     dword ptr [rbp+260h+var_2D8+8], eax
0x18005da94  lea     rax, [rsp+360h+DestinationString]
0x18005da99  mov     qword ptr [rbp+260h+var_2D8], rax
0x18005da9d  xorps   xmm2, xmm2
0x18005daa0  mov     rax, [rsp+360h+P]
0x18005daa5  mov     dword ptr [rsp+360h+var_2E8], 30h ; '0'
0x18005daad  movdqu  [rbp+260h+var_2C8], xmm2
0x18005dab2  test    rax, rax
0x18005dab5  jnz     loc_18005DCB9
0x18005dabb  movups  xmm0, [rsp+360h+var_2E8]
0x18005dac0  mov     qword ptr [rsp+360h+KeyPath.Length], rax
0x18005dac5  lea     r9, [rsp+360h+KeyPath]
0x18005daca  movups  xmm1, [rbp+260h+var_2D8]
0x18005dace  mov     word ptr [rsp+360h+KeyPath.Buffer], ax
0x18005dad3  lea     r8, [rsp+360h+KeyInformation]
0x18005dad8  mov     byte ptr [rsp+360h+KeyPath.Buffer+2], al
0x18005dadc  lea     rdx, [rbp+260h+var_290]
0x18005dae0  mov     [rsp+360h+var_330], al
0x18005dae4  mov     ecx, r14d
0x18005dae7  lea     rax, [rsp+360h+P]
0x18005daec  mov     [rsp+360h+P], rsi
0x18005daf1  mov     [rsp+360h+var_338], rax
0x18005daf6  lea     rax, [rsp+360h+var_330]
0x18005dafb  mov     [rsp+360h+ResultLength], rax
0x18005db00  movups  [rbp+260h+var_290], xmm0
0x18005db04  mov     [rsp+360h+KeyInformation], esi
0x18005db08  movups  [rbp+260h+var_280], xmm1
0x18005db0c  mov     [rsp+360h+KeyHandle], rsi
0x18005db11  movups  [rbp+260h+var_270], xmm2
0x18005db15  call    ConstructKernelKeyPath
0x18005db1a  mov     ebx, eax
0x18005db1c  test    eax, eax
0x18005db1e  js      short loc_18005DB74
0x18005db20  and     r13d, 1Ch
0x18005db24  lea     r8, [rbp+260h+var_290]
0x18005db28  mov     r9d, r13d
0x18005db2b  lea     rcx, [rsp+360h+KeyHandle]
0x18005db30  mov     edx, r14d
0x18005db33  call    cs:__imp_NtOpenKeyEx
0x18005db39  mov     r8, [rsp+360h+P]; P
0x18005db3e  mov     edi, eax
0x18005db40  test    r8, r8
0x18005db43  jz      short loc_18005DB5A
0x18005db45  mov     rcx, gs:60h
0x18005db4e  xor     edx, edx; Flags
0x18005db50  mov     rcx, [rcx+30h]; HeapHandle
0x18005db54  call    cs:__imp_RtlFreeHeap
0x18005db5a  test    edi, edi
0x18005db5c  js      short loc_18005DB72
0x18005db5e  cmp     [rsp+360h+var_330], 0
0x18005db63  jnz     loc_18005DC6F
0x18005db69  mov     rax, [rsp+360h+KeyHandle]
0x18005db6e  mov     [r12], rax
0x18005db72  mov     ebx, edi
0x18005db74  test    ebx, ebx
0x18005db76  jns     short loc_18005DBCF
0x18005db78  mov     r13, [rsp+360h+var_38]
0x18005db80  lea     rax, [rbp+260h+var_260]
0x18005db84  cmp     r15, rax
0x18005db87  jz      short loc_18005DBA1
0x18005db89  mov     rcx, gs:60h
0x18005db92  mov     r8, r15; P
0x18005db95  xor     edx, edx; Flags
0x18005db97  mov     rcx, [rcx+30h]; HeapHandle
0x18005db9b  call    cs:__imp_RtlFreeHeap
0x18005dba1  mov     eax, ebx
0x18005dba3  mov     rbx, [rsp+360h+var_30]
0x18005dbab  mov     rcx, [rbp+260h+var_50]
0x18005dbb2  xor     rcx, rsp; StackCookie
0x18005dbb5  call    __security_check_cookie
0x18005dbba  add     rsp, 338h
0x18005dbc1  pop     r15
0x18005dbc3  pop     r14
0x18005dbc5  pop     r12
0x18005dbc7  pop     rdi
0x18005dbc8  pop     rsi
0x18005dbc9  pop     rbp
0x18005dbca  retn
0x18005dbcb  test    ebx, ebx
0x18005dbcd  js      short loc_18005DB78
0x18005dbcf  or      qword ptr [r12], 2
0x18005dbd4  jmp     short loc_18005DB78
  ... truncated ...
```
