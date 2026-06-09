# GdiAddFontResourceW

- ea: `0x1800449e0`
- end: `0x180044b83`
- name: `GdiAddFontResourceW`
- size: `419`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800448c0`
- `0x18006e850`
- `0x180082770`
- `0x180082900`
- `0x180082910`

## callees

- `0x1800449e0`
- `0x180044b8c`
- `0x180045c28`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180044a8e`
- `ntdll!RtlFreeHeap` at `0x180044b11`
- `ntdll!RtlFreeHeap` at `0x180044a8e`
- `ntdll!RtlFreeHeap` at `0x180044b11`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180044b33`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180044b33`
- `ntdll!RtlFreeUnicodeString` at `0x180044b72`
- `ntdll!RtlFreeUnicodeString` at `0x180044b72`

## pseudocode

```c
__int64 __fastcall GdiAddFontResourceW(WCHAR *a1, int a2, __int64 a3)
{
  unsigned int v3; // ebx
  void *v6; // rax
  void *v7; // r15
  void *v9; // rax
  void *v10; // rdi
  unsigned int v11; // [rsp+40h] [rbp-20h] BYREF
  int v12; // [rsp+44h] [rbp-1Ch] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+48h] [rbp-18h] BYREF
  int v14; // [rsp+98h] [rbp+38h] BYREF
  int v15; // [rsp+A8h] [rbp+48h] BYREF

  v14 = a2;
  v3 = 0;
  v11 = 0;
  v12 = 0;
  v15 = 0;
  if ( a2 == 0x80000000 )
  {
    NtPathName = 0;
    if ( RtlDosPathNameToNtPathName_U(a1, &NtPathName, 0, 0) )
    {
      v3 = NtGdiAddFontResourceWWrapper(NtPathName.Buffer, (NtPathName.Length >> 1) + 1, 1, 0x80000000, 0, a3);
      RtlFreeUnicodeString(&NtPathName);
    }
  }
  else
  {
    v6 = pwszAllocNtMultiplePath(a1, &v14, &v12, &v11, 1, (__int64)&v15, 0);
    v7 = v6;
    if ( v6 )
    {
      v3 = NtGdiAddFontResourceWWrapper((_DWORD)v6, v12, v11, v14, v15, a3);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      if ( !v3 && (v14 & 0x40) == 0 )
      {
        v11 = 0;
        v12 = 0;
        v15 = 0;
        v9 = pwszAllocNtMultiplePath(a1, &v14, &v12, &v11, 1, (__int64)&v15, 1);
        v10 = v9;
        if ( v9 )
        {
          v3 = NtGdiAddFontResourceWWrapper((_DWORD)v9, v12, v11, v14, v15, a3);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
        }
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800449e0  mov     [rsp-28h+arg_0], rbx
0x1800449e5  mov     [rsp-28h+arg_8], edx
0x1800449e9  push    rbp
0x1800449ea  push    rsi
0x1800449eb  push    rdi
0x1800449ec  push    r14
0x1800449ee  push    r15
0x1800449f0  mov     rbp, rsp
0x1800449f3  sub     rsp, 60h
0x1800449f7  xor     ebx, ebx
0x1800449f9  mov     r15d, 80000000h
0x1800449ff  mov     [rbp+var_20], ebx
0x180044a02  mov     r14, r8
0x180044a05  mov     [rbp+var_1C], ebx
0x180044a08  mov     rsi, rcx
0x180044a0b  mov     [rbp+arg_18], ebx
0x180044a0e  cmp     edx, r15d
0x180044a11  jz      loc_180044B22
0x180044a17  lea     rax, [rbp+arg_18]
0x180044a1b  mov     [rsp+60h+var_30], ebx
0x180044a1f  mov     [rsp+60h+var_38], rax
0x180044a24  lea     edi, [rbx+1]
0x180044a27  lea     r9, [rbp+var_20]
0x180044a2b  mov     [rsp+60h+var_40], edi
0x180044a2f  lea     r8, [rbp+var_1C]
0x180044a33  lea     rdx, [rbp+arg_8]
0x180044a37  call    pwszAllocNtMultiplePath
0x180044a3c  mov     r15, rax
0x180044a3f  test    rax, rax
0x180044a42  jnz     short loc_180044A5B
0x180044a44  mov     eax, ebx
0x180044a46  mov     rbx, [rsp+60h+arg_0]
0x180044a4e  add     rsp, 60h
0x180044a52  pop     r15
0x180044a54  pop     r14
0x180044a56  pop     rdi
0x180044a57  pop     rsi
0x180044a58  pop     rbp
0x180044a59  retn
0x180044a5b  mov     ecx, [rbp+arg_18]
0x180044a5e  mov     r9d, [rbp+arg_8]
0x180044a62  mov     r8d, [rbp+var_20]
0x180044a66  mov     edx, [rbp+var_1C]
0x180044a69  mov     [rsp+60h+var_38], r14
0x180044a6e  mov     [rsp+60h+var_40], ecx
0x180044a72  mov     rcx, r15
0x180044a75  call    NtGdiAddFontResourceWWrapper
0x180044a7a  mov     rcx, gs:60h
0x180044a83  mov     r8, r15; P
0x180044a86  xor     edx, edx; Flags
0x180044a88  mov     ebx, eax
0x180044a8a  mov     rcx, [rcx+30h]; HeapHandle
0x180044a8e  call    cs:__imp_RtlFreeHeap
0x180044a95  nop     dword ptr [rax+rax+00h]
0x180044a9a  test    ebx, ebx
0x180044a9c  jnz     short loc_180044A44
0x180044a9e  test    byte ptr [rbp+arg_8], 40h
0x180044aa2  jnz     short loc_180044A44
0x180044aa4  lea     rax, [rbp+arg_18]
0x180044aa8  mov     [rsp+60h+var_30], edi
0x180044aac  mov     [rsp+60h+var_38], rax
0x180044ab1  lea     r9, [rbp+var_20]
0x180044ab5  lea     r8, [rbp+var_1C]
0x180044ab9  mov     [rsp+60h+var_40], edi
0x180044abd  lea     rdx, [rbp+arg_8]
0x180044ac1  mov     [rbp+var_20], ebx
0x180044ac4  mov     rcx, rsi
0x180044ac7  mov     [rbp+var_1C], ebx
0x180044aca  mov     [rbp+arg_18], ebx
0x180044acd  call    pwszAllocNtMultiplePath
0x180044ad2  mov     rdi, rax
0x180044ad5  test    rax, rax
0x180044ad8  jz      loc_180044A44
0x180044ade  mov     ecx, [rbp+arg_18]
0x180044ae1  mov     r9d, [rbp+arg_8]
0x180044ae5  mov     r8d, [rbp+var_20]
0x180044ae9  mov     edx, [rbp+var_1C]
0x180044aec  mov     [rsp+60h+var_38], r14
0x180044af1  mov     [rsp+60h+var_40], ecx
0x180044af5  mov     rcx, rax
0x180044af8  call    NtGdiAddFontResourceWWrapper
0x180044afd  mov     rcx, gs:60h
0x180044b06  mov     r8, rdi; P
0x180044b09  xor     edx, edx; Flags
0x180044b0b  mov     ebx, eax
0x180044b0d  mov     rcx, [rcx+30h]; HeapHandle
0x180044b11  call    cs:__imp_RtlFreeHeap
0x180044b18  nop     dword ptr [rax+rax+00h]
0x180044b1d  jmp     loc_180044A44
0x180044b22  xorps   xmm0, xmm0
0x180044b25  lea     rdx, [rbp+NtPathName]; NtPathName
0x180044b29  xor     r9d, r9d; DirectoryInfo
0x180044b2c  xor     r8d, r8d; NtFileNamePart
0x180044b2f  movups  xmmword ptr [rbp+NtPathName.Length], xmm0
0x180044b33  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180044b3a  nop     dword ptr [rax+rax+00h]
0x180044b3f  test    al, al
0x180044b41  jz      loc_180044A44
0x180044b47  movzx   edx, [rbp+NtPathName.Length]
0x180044b4b  mov     edi, 1
0x180044b50  mov     rcx, [rbp+NtPathName.Buffer]
0x180044b54  mov     r9d, r15d
0x180044b57  shr     edx, 1
0x180044b59  mov     r8d, edi
0x180044b5c  add     edx, edi
0x180044b5e  mov     [rsp+60h+var_38], r14
0x180044b63  mov     [rsp+60h+var_40], ebx
0x180044b67  call    NtGdiAddFontResourceWWrapper
0x180044b6c  lea     rcx, [rbp+NtPathName]; UnicodeString
0x180044b70  mov     ebx, eax
0x180044b72  call    cs:__imp_RtlFreeUnicodeString
0x180044b79  nop     dword ptr [rax+rax+00h]
0x180044b7e  jmp     loc_180044A44
```
