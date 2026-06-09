# GdiAddFontResourceW

- ea: `0x180038fc0`
- end: `0x18003914a`
- name: `GdiAddFontResourceW`
- size: `394`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x180038ec0`
- `0x18006a0a0`
- `0x18007db20`
- `0x18007dca0`
- `0x18007dcb0`

## callees

- `0x180038fc0`
- `0x180039150`
- `0x18003a154`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003906d`
- `ntdll!RtlFreeHeap` at `0x1800390ea`
- `ntdll!RtlFreeHeap` at `0x18003906d`
- `ntdll!RtlFreeHeap` at `0x1800390ea`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180039106`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180039106`
- `ntdll!RtlFreeUnicodeString` at `0x18003913f`
- `ntdll!RtlFreeUnicodeString` at `0x18003913f`

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
0x180038fc0  mov     [rsp-28h+arg_0], rbx
0x180038fc5  mov     [rsp-28h+arg_8], edx
0x180038fc9  push    rbp
0x180038fca  push    rsi
0x180038fcb  push    rdi
0x180038fcc  push    r14
0x180038fce  push    r15
0x180038fd0  mov     rbp, rsp
0x180038fd3  sub     rsp, 60h
0x180038fd7  xor     ebx, ebx
0x180038fd9  mov     r15d, 80000000h
0x180038fdf  mov     [rbp+var_20], ebx
0x180038fe2  mov     r14, r8
0x180038fe5  mov     [rbp+var_1C], ebx
0x180038fe8  mov     rsi, rcx
0x180038feb  mov     [rbp+arg_18], ebx
0x180038fee  cmp     edx, r15d
0x180038ff1  jz      loc_1800390F5
0x180038ff7  lea     rax, [rbp+arg_18]
0x180038ffb  mov     [rsp+60h+var_30], ebx
0x180038fff  mov     [rsp+60h+var_38], rax
0x180039004  lea     edi, [rbx+1]
0x180039007  lea     r9, [rbp+var_20]
0x18003900b  mov     [rsp+60h+var_40], edi
0x18003900f  lea     r8, [rbp+var_1C]
0x180039013  lea     rdx, [rbp+arg_8]
0x180039017  call    pwszAllocNtMultiplePath
0x18003901c  mov     r15, rax
0x18003901f  test    rax, rax
0x180039022  jnz     short loc_18003903A
0x180039024  mov     eax, ebx
0x180039026  mov     rbx, [rsp+60h+arg_0]
0x18003902e  add     rsp, 60h
0x180039032  pop     r15
0x180039034  pop     r14
0x180039036  pop     rdi
0x180039037  pop     rsi
0x180039038  pop     rbp
0x180039039  retn
0x18003903a  mov     ecx, [rbp+arg_18]
0x18003903d  mov     r9d, [rbp+arg_8]
0x180039041  mov     r8d, [rbp+var_20]
0x180039045  mov     edx, [rbp+var_1C]
0x180039048  mov     [rsp+60h+var_38], r14
0x18003904d  mov     [rsp+60h+var_40], ecx
0x180039051  mov     rcx, r15
0x180039054  call    NtGdiAddFontResourceWWrapper
0x180039059  mov     rcx, gs:60h
0x180039062  mov     r8, r15; P
0x180039065  xor     edx, edx; Flags
0x180039067  mov     ebx, eax
0x180039069  mov     rcx, [rcx+30h]; HeapHandle
0x18003906d  call    cs:__imp_RtlFreeHeap
0x180039073  test    ebx, ebx
0x180039075  jnz     short loc_180039024
0x180039077  test    byte ptr [rbp+arg_8], 40h
0x18003907b  jnz     short loc_180039024
0x18003907d  lea     rax, [rbp+arg_18]
0x180039081  mov     [rsp+60h+var_30], edi
0x180039085  mov     [rsp+60h+var_38], rax
0x18003908a  lea     r9, [rbp+var_20]
0x18003908e  lea     r8, [rbp+var_1C]
0x180039092  mov     [rsp+60h+var_40], edi
0x180039096  lea     rdx, [rbp+arg_8]
0x18003909a  mov     [rbp+var_20], ebx
0x18003909d  mov     rcx, rsi
0x1800390a0  mov     [rbp+var_1C], ebx
0x1800390a3  mov     [rbp+arg_18], ebx
0x1800390a6  call    pwszAllocNtMultiplePath
0x1800390ab  mov     rdi, rax
0x1800390ae  test    rax, rax
0x1800390b1  jz      loc_180039024
0x1800390b7  mov     ecx, [rbp+arg_18]
0x1800390ba  mov     r9d, [rbp+arg_8]
0x1800390be  mov     r8d, [rbp+var_20]
0x1800390c2  mov     edx, [rbp+var_1C]
0x1800390c5  mov     [rsp+60h+var_38], r14
0x1800390ca  mov     [rsp+60h+var_40], ecx
0x1800390ce  mov     rcx, rax
0x1800390d1  call    NtGdiAddFontResourceWWrapper
0x1800390d6  mov     rcx, gs:60h
0x1800390df  mov     r8, rdi; P
0x1800390e2  xor     edx, edx; Flags
0x1800390e4  mov     ebx, eax
0x1800390e6  mov     rcx, [rcx+30h]; HeapHandle
0x1800390ea  call    cs:__imp_RtlFreeHeap
0x1800390f0  jmp     loc_180039024
0x1800390f5  xorps   xmm0, xmm0
0x1800390f8  lea     rdx, [rbp+NtPathName]; NtPathName
0x1800390fc  xor     r9d, r9d; DirectoryInfo
0x1800390ff  xor     r8d, r8d; NtFileNamePart
0x180039102  movups  xmmword ptr [rbp+NtPathName.Length], xmm0
0x180039106  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18003910c  test    al, al
0x18003910e  jz      loc_180039024
0x180039114  movzx   edx, [rbp+NtPathName.Length]
0x180039118  mov     edi, 1
0x18003911d  mov     rcx, [rbp+NtPathName.Buffer]
0x180039121  mov     r9d, r15d
0x180039124  shr     edx, 1
0x180039126  mov     r8d, edi
0x180039129  add     edx, edi
0x18003912b  mov     [rsp+60h+var_38], r14
0x180039130  mov     [rsp+60h+var_40], ebx
0x180039134  call    NtGdiAddFontResourceWWrapper
0x180039139  lea     rcx, [rbp+NtPathName]; UnicodeString
0x18003913d  mov     ebx, eax
0x18003913f  call    cs:__imp_RtlFreeUnicodeString
0x180039145  jmp     loc_180039024
```
