# BaseRegReplaceKeyInternal

- ea: `0x18001c34c`
- end: `0x18001c641`
- name: `BaseRegReplaceKeyInternal`
- size: `757`
- prototype: `ULONG __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019cb0`

## callees

- `0x18001c34c`
- `0x18001d38c`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18001c4a6`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18001c549`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18001c4a6`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18001c549`
- `ntdll!RtlReleaseRelativeName` at `0x18001c558`
- `ntdll!RtlReleaseRelativeName` at `0x18001c5f0`
- `ntdll!RtlReleaseRelativeName` at `0x18001c5fa`
- `ntdll!RtlReleaseRelativeName` at `0x18001c558`
- `ntdll!RtlReleaseRelativeName` at `0x18001c5f0`
- `ntdll!RtlReleaseRelativeName` at `0x18001c5fa`
- `ntdll!NtReplaceKey` at `0x18001c5e3`
- `ntdll!NtReplaceKey` at `0x18001c5e3`
- `ntdll!RtlNtStatusToDosError` at `0x18001c48d`
- `ntdll!RtlNtStatusToDosError` at `0x18001c48d`
- `ntdll!NtClose` at `0x18001c4b4`
- `ntdll!NtClose` at `0x18001c634`
- `ntdll!NtClose` at `0x18001c4b4`
- `ntdll!NtClose` at `0x18001c634`
- `ntdll!RtlFreeHeap` at `0x18001c570`
- `ntdll!RtlFreeHeap` at `0x18001c612`
- `ntdll!RtlFreeHeap` at `0x18001c62a`
- `ntdll!RtlFreeHeap` at `0x18001c570`
- `ntdll!RtlFreeHeap` at `0x18001c612`
- `ntdll!RtlFreeHeap` at `0x18001c62a`

## pseudocode

```c
ULONG __fastcall BaseRegReplaceKeyInternal(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v6; // eax
  NTSTATUS v7; // ecx
  PWSTR Buffer; // rsi
  HANDLE ContainingDirectory; // rax
  const WCHAR *v11; // rcx
  PWSTR v12; // rdi
  HANDLE v13; // rax
  NTSTATUS v14; // ebx
  struct _UNICODE_STRING NtName; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING v16; // [rsp+50h] [rbp-B0h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+60h] [rbp-A0h] BYREF
  struct _RTL_RELATIVE_NAME_U v18; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ReplacedObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v21[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v22; // [rsp+108h] [rbp+8h]
  __int64 v23; // [rsp+110h] [rbp+10h]
  int v24; // [rsp+118h] [rbp+18h]
  int v25; // [rsp+11Ch] [rbp+1Ch]
  __int128 v26; // [rsp+120h] [rbp+20h]
  HANDLE Handle; // [rsp+150h] [rbp+50h] BYREF

  Handle = 0;
  v21[1] = 0;
  v25 = 0;
  NtName = 0;
  v16 = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  memset(&v18, 0, sizeof(v18));
  memset(&ObjectAttributes, 0, 44);
  memset(&ReplacedObjectAttributes, 0, 44);
  if ( !a1
    || !a3
    || !*(_QWORD *)(a3 + 8)
    || (*(_BYTE *)a3 & 1) != 0
    || !a4
    || !*(_QWORD *)(a4 + 8)
    || (*(_BYTE *)a4 & 1) != 0 )
  {
    return 87;
  }
  if ( a2 )
  {
    if ( (*(_BYTE *)a2 & 1) != 0 || *(_WORD *)a2 && !*(_QWORD *)(a2 + 8) )
      return 87;
    if ( *(_WORD *)a2 )
      *(_WORD *)a2 -= 2;
  }
  if ( *(_WORD *)a3 )
    *(_WORD *)a3 -= 2;
  if ( *(_WORD *)a4 )
    *(_WORD *)a4 -= 2;
  v22 = a1;
  v23 = a2;
  v21[0] = 48;
  v24 = 64;
  v26 = 0;
  v6 = Wow64NtCreateKey(&Handle, 0x2000000, v21);
  if ( v6 < 0 )
  {
    v7 = v6;
    return RtlNtStatusToDosError(v7);
  }
  if ( RtlDosPathNameToRelativeNtPathName_U(*(PCWSTR *)(a3 + 8), &NtName, 0, &RelativeName) )
  {
    Buffer = NtName.Buffer;
    if ( RelativeName.RelativeName.Length )
    {
      NtName = RelativeName.RelativeName;
      ContainingDirectory = RelativeName.ContainingDirectory;
    }
    else
    {
      ContainingDirectory = 0;
      RelativeName.ContainingDirectory = 0;
    }
    v11 = *(const WCHAR **)(a4 + 8);
    ObjectAttributes.RootDirectory = ContainingDirectory;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &NtName;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( RtlDosPathNameToRelativeNtPathName_U(v11, &v16, 0, &v18) )
    {
      v12 = v16.Buffer;
      if ( v18.RelativeName.Length )
      {
        v16 = v18.RelativeName;
        v13 = v18.ContainingDirectory;
      }
      else
      {
        v13 = 0;
        v18.ContainingDirectory = 0;
      }
      ReplacedObjectAttributes.RootDirectory = v13;
      ReplacedObjectAttributes.Length = 48;
      ReplacedObjectAttributes.ObjectName = &v16;
      ReplacedObjectAttributes.Attributes = 64;
      *(_OWORD *)&ReplacedObjectAttributes.SecurityDescriptor = 0;
      v14 = NtReplaceKey(&ObjectAttributes, Handle, &ReplacedObjectAttributes);
      RtlReleaseRelativeName(&RelativeName);
      RtlReleaseRelativeName(&v18);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
      NtClose(Handle);
      v7 = v14;
      return RtlNtStatusToDosError(v7);
    }
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  }
  NtClose(Handle);
  return 87;
}

```

## disassembly

```asm
0x18001c34c  mov     [rsp-8+arg_8], rbx
0x18001c351  mov     [rsp-8+arg_10], rsi
0x18001c356  push    rbp
0x18001c357  push    rdi
0x18001c358  push    r14
0x18001c35a  lea     rbp, [rsp-30h]
0x18001c35f  sub     rsp, 130h
0x18001c366  xorps   xmm0, xmm0
0x18001c369  xor     r14d, r14d
0x18001c36c  xorps   xmm1, xmm1
0x18001c36f  mov     [rbp+40h+Handle], r14
0x18001c373  xor     eax, eax
0x18001c375  mov     [rbp+40h+var_3C], r14d
0x18001c379  mov     [rbp+40h+var_24], r14d
0x18001c37d  mov     rdi, r9
0x18001c380  mov     rbx, r8
0x18001c383  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x18001c387  movups  xmmword ptr [rbp+40h+ReplacedObjectAttributes.ObjectName], xmm0
0x18001c38b  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x18001c38f  movups  xmmword ptr [rbp+40h+ReplacedObjectAttributes+1Ch], xmm0
0x18001c393  movups  xmmword ptr [rsp+140h+NtName.Length], xmm0
0x18001c398  movups  xmmword ptr [rsp+140h+var_F0.Length], xmm1
0x18001c39d  movups  xmmword ptr [rsp+140h+RelativeName.RelativeName.Length], xmm0
0x18001c3a2  movups  xmmword ptr [rsp+140h+RelativeName.ContainingDirectory], xmm0
0x18001c3a7  movups  xmmword ptr [rbp+40h+var_C0.RelativeName.Length], xmm1
0x18001c3ab  movups  xmmword ptr [rbp+40h+var_C0.ContainingDirectory], xmm1
0x18001c3af  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x18001c3b3  movups  xmmword ptr [rbp+40h+ReplacedObjectAttributes.Length], xmm0
0x18001c3b7  test    rcx, rcx
0x18001c3ba  jz      loc_18001C4BA
0x18001c3c0  test    rbx, rbx
0x18001c3c3  jz      loc_18001C4BA
0x18001c3c9  cmp     [r8+8], r14
0x18001c3cd  jz      loc_18001C4BA
0x18001c3d3  mov     al, 1
0x18001c3d5  test    [r8], al
0x18001c3d8  jnz     loc_18001C4BA
0x18001c3de  test    r9, r9
0x18001c3e1  jz      loc_18001C4BA
0x18001c3e7  cmp     [r9+8], r14
0x18001c3eb  jz      loc_18001C4BA
0x18001c3f1  test    [r9], al
0x18001c3f4  jnz     loc_18001C4BA
0x18001c3fa  test    rdx, rdx
0x18001c3fd  jz      short loc_18001C426
0x18001c3ff  test    [rdx], al
0x18001c401  jnz     loc_18001C4BA
0x18001c407  cmp     [rdx], r14w
0x18001c40b  jz      short loc_18001C417
0x18001c40d  cmp     [rdx+8], r14
0x18001c411  jz      loc_18001C4BA
0x18001c417  movzx   eax, word ptr [rdx]
0x18001c41a  test    ax, ax
0x18001c41d  jz      short loc_18001C426
0x18001c41f  sub     ax, 2
0x18001c423  mov     [rdx], ax
0x18001c426  movzx   eax, word ptr [r8]
0x18001c42a  test    ax, ax
0x18001c42d  jz      short loc_18001C437
0x18001c42f  sub     ax, 2
0x18001c433  mov     [r8], ax
0x18001c437  movzx   eax, word ptr [r9]
0x18001c43b  test    ax, ax
0x18001c43e  jz      short loc_18001C448
0x18001c440  sub     ax, 2
0x18001c444  mov     [r9], ax
0x18001c448  mov     [rbp+40h+var_38], rcx
0x18001c44c  lea     r8, [rbp+40h+var_40]
0x18001c450  mov     [rbp+40h+var_30], rdx
0x18001c454  lea     rcx, [rbp+40h+Handle]
0x18001c458  mov     [rsp+140h+var_108], r14
0x18001c45d  mov     edx, 2000000h
0x18001c462  mov     [rsp+140h+var_118], 4
0x18001c46a  mov     [rsp+140h+var_120], r14
0x18001c46f  mov     [rbp+40h+var_40], 30h ; '0'
0x18001c476  mov     [rbp+40h+var_28], 40h ; '@'
0x18001c47d  movdqu  [rbp+40h+var_20], xmm0
0x18001c482  call    Wow64NtCreateKey
0x18001c487  test    eax, eax
0x18001c489  jns     short loc_18001C495
0x18001c48b  mov     ecx, eax; Status
0x18001c48d  call    cs:__imp_RtlNtStatusToDosError
0x18001c493  jmp     short loc_18001C4BF
0x18001c495  mov     rcx, [rbx+8]; DosName
0x18001c499  lea     r9, [rsp+140h+RelativeName]; RelativeName
0x18001c49e  xor     r8d, r8d; PartName
0x18001c4a1  lea     rdx, [rsp+140h+NtName]; NtName
0x18001c4a6  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18001c4ac  test    al, al
0x18001c4ae  jnz     short loc_18001C4D7
0x18001c4b0  mov     rcx, [rbp+40h+Handle]; Handle
0x18001c4b4  call    cs:__imp_NtClose
0x18001c4ba  mov     eax, 57h ; 'W'
0x18001c4bf  lea     r11, [rsp+140h+var_10]
0x18001c4c7  mov     rbx, [r11+28h]
0x18001c4cb  mov     rsi, [r11+30h]
0x18001c4cf  mov     rsp, r11
0x18001c4d2  pop     r14
0x18001c4d4  pop     rdi
0x18001c4d5  pop     rbp
0x18001c4d6  retn
0x18001c4d7  movzx   eax, [rsp+140h+RelativeName.RelativeName.Length]
0x18001c4dc  mov     rsi, [rsp+140h+NtName.Buffer]
0x18001c4e1  test    ax, ax
0x18001c4e4  jz      short loc_18001C50E
0x18001c4e6  mov     [rsp+140h+NtName.Length], ax
0x18001c4eb  mov     eax, dword ptr [rsp+140h+RelativeName.RelativeName.MaximumLength]
0x18001c4ef  mov     dword ptr [rsp+140h+NtName.MaximumLength], eax
0x18001c4f3  movzx   eax, word ptr [rsp+140h+RelativeName.RelativeName+6]
0x18001c4f8  mov     word ptr [rsp+140h+NtName+6], ax
0x18001c4fd  mov     rax, [rsp+140h+RelativeName.RelativeName.Buffer]
0x18001c502  mov     [rsp+140h+NtName.Buffer], rax
0x18001c507  mov     rax, [rsp+140h+RelativeName.ContainingDirectory]
0x18001c50c  jmp     short loc_18001C516
0x18001c50e  mov     rax, r14
0x18001c511  mov     [rsp+140h+RelativeName.ContainingDirectory], rax
0x18001c516  mov     rcx, [rdi+8]; DosName
0x18001c51a  lea     r9, [rbp+40h+var_C0]; RelativeName
0x18001c51e  mov     [rbp+40h+ObjectAttributes.RootDirectory], rax
0x18001c522  lea     rdx, [rsp+140h+var_F0]; NtName
0x18001c527  lea     rax, [rsp+140h+NtName]
0x18001c52c  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x18001c533  xorps   xmm0, xmm0
0x18001c536  mov     [rbp+40h+ObjectAttributes.ObjectName], rax
0x18001c53a  xor     r8d, r8d; PartName
0x18001c53d  mov     [rbp+40h+ObjectAttributes.Attributes], 40h ; '@'
0x18001c544  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001c549  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18001c54f  test    al, al
0x18001c551  jnz     short loc_18001C57B
0x18001c553  lea     rcx, [rsp+140h+RelativeName]; RelativeName
0x18001c558  call    cs:__imp_RtlReleaseRelativeName
0x18001c55e  mov     rcx, gs:60h
0x18001c567  mov     r8, rsi; P
0x18001c56a  xor     edx, edx; Flags
0x18001c56c  mov     rcx, [rcx+30h]; HeapHandle
0x18001c570  call    cs:__imp_RtlFreeHeap
0x18001c576  jmp     loc_18001C4B0
0x18001c57b  movzx   eax, [rbp+40h+var_C0.RelativeName.Length]
0x18001c57f  mov     rdi, [rsp+140h+var_F0.Buffer]
0x18001c584  test    ax, ax
0x18001c587  jz      short loc_18001C5AD
0x18001c589  mov     [rsp+140h+var_F0.Length], ax
0x18001c58e  mov     eax, dword ptr [rbp+40h+var_C0.RelativeName.MaximumLength]
0x18001c591  mov     dword ptr [rsp+140h+var_F0.MaximumLength], eax
0x18001c595  movzx   eax, word ptr [rbp+40h+var_C0.RelativeName+6]
0x18001c599  mov     word ptr [rsp+140h+var_F0+6], ax
0x18001c59e  mov     rax, [rbp+40h+var_C0.RelativeName.Buffer]
0x18001c5a2  mov     [rsp+140h+var_F0.Buffer], rax
0x18001c5a7  mov     rax, [rbp+40h+var_C0.ContainingDirectory]
0x18001c5ab  jmp     short loc_18001C5B4
0x18001c5ad  mov     rax, r14
0x18001c5b0  mov     [rbp+40h+var_C0.ContainingDirectory], rax
0x18001c5b4  mov     rdx, [rbp+40h+Handle]; Key
0x18001c5b8  lea     r8, [rbp+40h+ReplacedObjectAttributes]; ReplacedObjectAttributes
0x18001c5bc  mov     [rbp+40h+ReplacedObjectAttributes.RootDirectory], rax
0x18001c5c0  lea     rcx, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x18001c5c4  lea     rax, [rsp+140h+var_F0]
0x18001c5c9  mov     [rbp+40h+ReplacedObjectAttributes.Length], 30h ; '0'
0x18001c5d0  xorps   xmm0, xmm0
0x18001c5d3  mov     [rbp+40h+ReplacedObjectAttributes.ObjectName], rax
0x18001c5d7  mov     [rbp+40h+ReplacedObjectAttributes.Attributes], 40h ; '@'
0x18001c5de  movdqu  xmmword ptr [rbp+40h+ReplacedObjectAttributes.SecurityDescriptor], xmm0
0x18001c5e3  call    cs:__imp_NtReplaceKey
0x18001c5e9  lea     rcx, [rsp+140h+RelativeName]; RelativeName
0x18001c5ee  mov     ebx, eax
0x18001c5f0  call    cs:__imp_RtlReleaseRelativeName
0x18001c5f6  lea     rcx, [rbp+40h+var_C0]; RelativeName
0x18001c5fa  call    cs:__imp_RtlReleaseRelativeName
0x18001c600  mov     rcx, gs:60h
0x18001c609  mov     r8, rsi; P
0x18001c60c  xor     edx, edx; Flags
0x18001c60e  mov     rcx, [rcx+30h]; HeapHandle
0x18001c612  call    cs:__imp_RtlFreeHeap
0x18001c618  mov     rcx, gs:60h
0x18001c621  mov     r8, rdi; P
0x18001c624  xor     edx, edx; Flags
0x18001c626  mov     rcx, [rcx+30h]; HeapHandle
0x18001c62a  call    cs:__imp_RtlFreeHeap
0x18001c630  mov     rcx, [rbp+40h+Handle]; Handle
0x18001c634  call    cs:__imp_NtClose
0x18001c63a  mov     ecx, ebx
0x18001c63c  jmp     loc_18001C48D
```
