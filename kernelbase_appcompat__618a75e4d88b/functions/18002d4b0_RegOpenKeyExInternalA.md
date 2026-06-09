# RegOpenKeyExInternalA

- ea: `0x18002d4b0`
- end: `0x18002d7cc`
- name: `RegOpenKeyExInternalA`
- size: `796`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18002bf6c`
- `0x18002c7a0`
- `0x18002d480`
- `0x1800e6b90`

## callees

- `0x18002d4b0`
- `0x18002d7e0`
- `0x18002e0c4`
- `0x18005e040`
- `0x18005e7e0`
- `0x18005ebc0`
- `0x18005fcf0`
- `0x180136e28`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18002d5e7`
- `ntdll!RtlFreeUnicodeString` at `0x18002d5e7`
- `ntdll!RtlNtStatusToDosError` at `0x18002d799`
- `ntdll!RtlNtStatusToDosError` at `0x18002d799`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002d63a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002d63a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002d668`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002d668`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18002d590`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18002d590`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18002d75b`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegGetVersion` at `0x18002d75b`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegOpenKey` at `0x18002d70e`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegOpenKey` at `0x18002d70e`

## pseudocode

```c
LSTATUS __fastcall RegOpenKeyExInternalA(
        HKEY a1,
        const char *a2,
        unsigned int a3,
        unsigned int a4,
        PHANDLE a5,
        __int64 a6)
{
  HKEY *v9; // r15
  PHANDLE v10; // r14
  const char *v11; // rbx
  ULONG v12; // esi
  unsigned __int64 v13; // rbx
  __int64 v14; // rbx
  LSTATUS result; // eax
  _QWORD *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r8
  bool v21; // al
  __int64 v22; // r9
  unsigned __int64 v23; // rbx
  int v24; // [rsp+20h] [rbp-78h]
  char v25; // [rsp+40h] [rbp-58h] BYREF
  ULONG v26; // [rsp+44h] [rbp-54h]
  __int64 v27; // [rsp+48h] [rbp-50h] BYREF
  __int64 v28; // [rsp+50h] [rbp-48h] BYREF
  __int64 v29; // [rsp+58h] [rbp-40h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+60h] [rbp-38h] BYREF
  HANDLE KeyHandle; // [rsp+A0h] [rbp+8h] BYREF

  KeyHandle = a1;
  Destination = 0;
  v25 = 0;
  v9 = 0;
  v27 = 0;
  v28 = 0;
  if ( a1 == HKEY_PERFORMANCE_DATA || a1 == HKEY_PERFORMANCE_TEXT || a1 == HKEY_PERFORMANCE_NLSTEXT )
    return 6;
  v10 = a5;
  if ( !a5 )
    return 87;
  v11 = &v25;
  if ( a2 )
    v11 = a2;
  if ( ((unsigned __int64)(a1 + 0x20000000) & 0xFFFFFFFFFFFFFFF8uLL) != 0 || (a4 & 0x300) != 0 || v11 && *v11 )
  {
    if ( v11 )
    {
      v12 = MapPredefinedHandleInternal(a1, &KeyHandle, &v27, &v28);
      if ( !v12 )
      {
        if ( RtlCreateUnicodeStringFromAsciiz(&Destination, v11) )
        {
          Destination.Length += 2;
          v13 = (unsigned __int64)KeyHandle;
          if ( ((unsigned __int8)KeyHandle & 1) != 0 )
          {
            if ( (unsigned __int8)IsBaseRegCloseKeyPresent() )
            {
              LODWORD(KeyHandle) = 0;
              v23 = v13 & 0xFFFFFFFFFFFFFFFEuLL;
              v21 = (unsigned __int8)IsBaseRegCloseKeyPresent()
                 && !(unsigned int)BaseRegGetVersion(v23, &KeyHandle)
                 && (_DWORD)KeyHandle == 6;
              v22 = a4 & 0xFFFFFCFF;
              if ( v21 )
                v22 = a4;
              v12 = BaseRegOpenKey(v23, &Destination, a3, v22, v10);
              v26 = v12;
              if ( !v12 )
                *v10 = (HANDLE)((unsigned __int64)*v10 | 1);
            }
          }
          else
          {
            v12 = BaseRegOpenKeyInternal(KeyHandle, &Destination, a3, a4, v24, v10, a6);
          }
          RtlFreeUnicodeString(&Destination);
        }
        else
        {
          v12 = RtlNtStatusToDosError(-1073741801);
        }
      }
    }
    else
    {
      v12 = 1010;
    }
  }
  else
  {
    if ( a1 == HKEY_CLASSES_ROOT )
      goto LABEL_30;
    result = RegCloseKey(a1);
    if ( result )
      return result;
    v12 = MapPredefinedHandleInternal(a1, 0, &v27, &v28);
    if ( !v12 )
    {
LABEL_30:
      *v10 = a1;
      v12 = 0;
    }
  }
  v29 = v27;
  v14 = v28;
  if ( v27 )
    BaseRegCloseKeyInternal(&v29);
  if ( v14 )
  {
    RtlAcquireSRWLockExclusive(&PredefinedHandleTableSRWLock);
    if ( (*(_DWORD *)(v14 + 8))-- == 1 )
    {
      v17 = *(_QWORD **)(v14 + 16);
      v18 = v17[1];
      if ( v14 != v18 || *(_QWORD *)v14 != *v17 )
      {
        v9 = (HKEY *)v14;
        v19 = RemoveUnitFromList(v18, v14, *(_QWORD *)(v14 + 16));
        *(_QWORD *)(v20 + 8) = v19;
      }
    }
    RtlReleaseSRWLockExclusive(&PredefinedHandleTableSRWLock);
    if ( v9 )
    {
      RegCloseKey(*v9);
      FreeEnvironmentStringsW((LPWCH)v9);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18002d4b0  mov     rax, rsp
0x18002d4b3  mov     [rax+10h], rbx
0x18002d4b7  mov     [rax+18h], rsi
0x18002d4bb  mov     [rax+8], rcx
0x18002d4bf  push    rdi
0x18002d4c0  push    r12
0x18002d4c2  push    r13
0x18002d4c4  push    r14
0x18002d4c6  push    r15
0x18002d4c8  sub     rsp, 70h
0x18002d4cc  mov     r12d, r9d
0x18002d4cf  mov     r13d, r8d
0x18002d4d2  mov     rdi, rcx
0x18002d4d5  xorps   xmm0, xmm0
0x18002d4d8  movups  xmmword ptr [rax-38h], xmm0
0x18002d4dc  mov     byte ptr [rax-58h], 0
0x18002d4e0  xor     r15d, r15d
0x18002d4e3  mov     [rax-50h], r15
0x18002d4e7  mov     [rax-48h], r15
0x18002d4eb  cmp     rcx, 0FFFFFFFF80000004h
0x18002d4f2  jz      loc_18002D6CA
0x18002d4f8  cmp     rcx, 0FFFFFFFF80000050h
0x18002d4ff  jz      loc_18002D6CA
0x18002d505  cmp     rcx, 0FFFFFFFF80000060h
0x18002d50c  jz      loc_18002D6CA
0x18002d512  mov     r14, [rsp+98h+arg_20]
0x18002d51a  test    r14, r14
0x18002d51d  jz      loc_18002D780
0x18002d523  lea     rbx, [rax-58h]
0x18002d527  test    rdx, rdx
0x18002d52a  cmovnz  rbx, rdx
0x18002d52e  mov     eax, 80000000h
0x18002d533  add     rax, rcx
0x18002d536  test    rax, 0FFFFFFFFFFFFFFF8h
0x18002d53c  jnz     short loc_18002D562
0x18002d53e  cmp     rcx, 0FFFFFFFF80000004h
0x18002d545  jz      short loc_18002D562
0x18002d547  test    r9d, 300h
0x18002d54e  jnz     short loc_18002D562
0x18002d550  test    rbx, rbx
0x18002d553  jz      loc_18002D68B
0x18002d559  cmp     [rbx], r15b
0x18002d55c  jz      loc_18002D68B
0x18002d562  test    rbx, rbx
0x18002d565  jz      loc_18002D78A
0x18002d56b  lea     r9, [rsp+98h+var_48]
0x18002d570  lea     r8, [rsp+98h+var_50]
0x18002d575  lea     rdx, [rsp+98h+KeyHandle]
0x18002d57d  call    MapPredefinedHandleInternal
0x18002d582  mov     esi, eax
0x18002d584  test    eax, eax
0x18002d586  jnz     short loc_18002D5F3
0x18002d588  mov     rdx, rbx; Source
0x18002d58b  lea     rcx, [rsp+98h+Destination]; Destination
0x18002d590  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18002d597  nop     dword ptr [rax+rax+00h]
0x18002d59c  test    al, al
0x18002d59e  jz      loc_18002D794
0x18002d5a4  add     [rsp+98h+Destination.Length], 2
0x18002d5aa  mov     rbx, [rsp+98h+KeyHandle]
0x18002d5b2  test    bl, 1
0x18002d5b5  jnz     loc_18002D7AC
0x18002d5bb  mov     rax, [rsp+98h+arg_28]
0x18002d5c3  mov     [rsp+98h+var_68], rax; __int64
0x18002d5c8  mov     [rsp+98h+var_70], r14; PHANDLE
0x18002d5cd  mov     r9d, r12d
0x18002d5d0  mov     r8d, r13d
0x18002d5d3  lea     rdx, [rsp+98h+Destination]; Source
0x18002d5d8  mov     rcx, rbx; KeyHandle
0x18002d5db  call    BaseRegOpenKeyInternal
0x18002d5e0  mov     esi, eax
0x18002d5e2  lea     rcx, [rsp+98h+Destination]; UnicodeString
0x18002d5e7  call    cs:__imp_RtlFreeUnicodeString
0x18002d5ee  nop     dword ptr [rax+rax+00h]
0x18002d5f3  mov     rax, [rsp+98h+var_50]
0x18002d5f8  mov     [rsp+98h+var_40], rax
0x18002d5fd  mov     rbx, [rsp+98h+var_48]
0x18002d602  test    rax, rax
0x18002d605  jz      short loc_18002D611
0x18002d607  lea     rcx, [rsp+98h+var_40]
0x18002d60c  call    BaseRegCloseKeyInternal
0x18002d611  test    rbx, rbx
0x18002d614  jnz     short loc_18002D633
0x18002d616  mov     eax, esi
0x18002d618  lea     r11, [rsp+98h+var_28]
0x18002d61d  mov     rbx, [r11+38h]
0x18002d621  mov     rsi, [r11+40h]
0x18002d625  mov     rsp, r11
0x18002d628  pop     r15
0x18002d62a  pop     r14
0x18002d62c  pop     r13
0x18002d62e  pop     r12
0x18002d630  pop     rdi
0x18002d631  retn
0x18002d633  lea     rcx, PredefinedHandleTableSRWLock
0x18002d63a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002d641  nop     dword ptr [rax+rax+00h]
0x18002d646  add     dword ptr [rbx+8], 0FFFFFFFFh
0x18002d64a  jnz     short loc_18002D661
0x18002d64c  mov     rax, [rbx+10h]
0x18002d650  mov     rcx, [rax+8]
0x18002d654  cmp     rbx, rcx
0x18002d657  jnz     short loc_18002D6D4
0x18002d659  mov     rax, [rax]
0x18002d65c  cmp     [rbx], rax
0x18002d65f  jnz     short loc_18002D6D4
0x18002d661  lea     rcx, PredefinedHandleTableSRWLock
0x18002d668  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002d66f  nop     dword ptr [rax+rax+00h]
0x18002d674  test    r15, r15
0x18002d677  jz      short loc_18002D616
0x18002d679  mov     rcx, [r15]; hKey
0x18002d67c  call    RegCloseKey
0x18002d681  mov     rcx, r15; penv
0x18002d684  call    FreeEnvironmentStringsW
0x18002d689  jmp     short loc_18002D616
0x18002d68b  cmp     rdi, 0FFFFFFFF80000000h
0x18002d692  jz      short loc_18002D6BF
0x18002d694  call    RegCloseKey
0x18002d699  test    eax, eax
0x18002d69b  jnz     loc_18002D618
0x18002d6a1  lea     r9, [rsp+98h+var_48]
0x18002d6a6  lea     r8, [rsp+98h+var_50]
0x18002d6ab  xor     edx, edx
0x18002d6ad  mov     rcx, rdi
0x18002d6b0  call    MapPredefinedHandleInternal
0x18002d6b5  mov     esi, eax
0x18002d6b7  test    eax, eax
0x18002d6b9  jnz     loc_18002D5F3
0x18002d6bf  mov     [r14], rdi
0x18002d6c2  mov     esi, r15d
0x18002d6c5  jmp     loc_18002D5F3
0x18002d6ca  mov     eax, 6
0x18002d6cf  jmp     loc_18002D618
0x18002d6d4  mov     r15, rbx
0x18002d6d7  mov     r8, [rbx+10h]
0x18002d6db  mov     rdx, rbx
0x18002d6de  call    RemoveUnitFromList
0x18002d6e3  mov     [r8+8], rax
0x18002d6e7  jmp     loc_18002D661
0x18002d6ec  xor     al, al
0x18002d6ee  mov     r9d, r12d
0x18002d6f1  and     r9d, 0FFFFFCFFh
0x18002d6f8  test    al, al
0x18002d6fa  cmovnz  r9d, r12d
0x18002d6fe  mov     [rsp+98h+var_78], r14
0x18002d703  mov     r8d, r13d
0x18002d706  lea     rdx, [rsp+98h+Destination]
0x18002d70b  mov     rcx, rbx
0x18002d70e  call    cs:__imp_BaseRegOpenKey
0x18002d715  nop     dword ptr [rax+rax+00h]
0x18002d71a  mov     esi, eax
0x18002d71c  mov     [rsp+98h+var_54], eax
0x18002d720  jmp     loc_18002D7BB
0x18002d725  mov     esi, eax
0x18002d727  mov     [rsp+98h+var_54], eax
0x18002d72b  xor     r15d, r15d
0x18002d72e  mov     r14, [rsp+98h+arg_20]
0x18002d736  jmp     loc_18002D7BB
0x18002d73b  mov     dword ptr [rsp+98h+KeyHandle], r15d
0x18002d743  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18002d747  call    IsBaseRegCloseKeyPresent
0x18002d74c  test    al, al
0x18002d74e  jz      short loc_18002D6EC
0x18002d750  lea     rdx, [rsp+98h+KeyHandle]
0x18002d758  mov     rcx, rbx
0x18002d75b  call    cs:__imp_BaseRegGetVersion
0x18002d762  nop     dword ptr [rax+rax+00h]
0x18002d767  test    eax, eax
0x18002d769  jnz     short loc_18002D6EC
0x18002d76b  cmp     dword ptr [rsp+98h+KeyHandle], 6
0x18002d773  jnz     loc_18002D6EC
0x18002d779  mov     al, 1
0x18002d77b  jmp     loc_18002D6EE
0x18002d780  mov     eax, 57h ; 'W'
0x18002d785  jmp     loc_18002D618
0x18002d78a  mov     esi, 3F2h
0x18002d78f  jmp     loc_18002D5F3
0x18002d794  mov     ecx, 0C0000017h; Status
0x18002d799  call    cs:__imp_RtlNtStatusToDosError
0x18002d7a0  nop     dword ptr [rax+rax+00h]
0x18002d7a5  mov     esi, eax
0x18002d7a7  jmp     loc_18002D5F3
0x18002d7ac  call    IsBaseRegCloseKeyPresent
0x18002d7b1  test    al, al
0x18002d7b3  jz      loc_18002D5E2
0x18002d7b9  jmp     short loc_18002D73B
0x18002d7bb  test    esi, esi
0x18002d7bd  jnz     loc_18002D5E2
0x18002d7c3  or      qword ptr [r14], 1
0x18002d7c7  jmp     loc_18002D5E2
```
