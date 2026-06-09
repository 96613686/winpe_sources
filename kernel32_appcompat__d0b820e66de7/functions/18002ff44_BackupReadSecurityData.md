# BackupReadSecurityData

- ea: `0x18002ff44`
- end: `0x1800300e3`
- name: `BackupReadSecurityData`
- size: `415`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180032610`

## callees

- `0x18002ff44`
- `0x180033054`
- `0x180056e20`
- `0x18008275d`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18002ffe9`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18002ffe9`
- `ntdll!NtQuerySecurityObject` at `0x18002ffad`
- `ntdll!NtQuerySecurityObject` at `0x180030066`
- `ntdll!NtQuerySecurityObject` at `0x1800300a4`
- `ntdll!NtQuerySecurityObject` at `0x18002ffad`
- `ntdll!NtQuerySecurityObject` at `0x180030066`
- `ntdll!NtQuerySecurityObject` at `0x1800300a4`

## pseudocode

```c
__int64 __fastcall BackupReadSecurityData(HANDLE Handle, __int64 a2, __int64 a3)
{
  ULONG *v5; // rdi
  size_t v6; // r8
  void *v7; // rcx
  NTSTATUS v8; // eax
  void *v9; // rcx
  __int64 result; // rax
  NTSTATUS v11; // eax
  NTSTATUS v12; // eax
  ULONG LengthNeeded; // [rsp+50h] [rbp+18h] BYREF

  if ( *(_BYTE *)(a3 + 20) )
  {
    if ( *(_BYTE *)(a2 + 1129) )
    {
      v5 = (ULONG *)(a2 + 1080);
      while ( 1 )
      {
        v6 = *v5;
        v7 = *(void **)(a2 + 1088);
        LengthNeeded = 0;
        memset_0(v7, 0, v6);
        v8 = NtQuerySecurityObject(Handle, 0x1007Fu, *(PSECURITY_DESCRIPTOR *)(a2 + 1088), *v5, &LengthNeeded);
        if ( v8 >= 0 )
          break;
        if ( v8 != -2147483643 && v8 != -1073741789 )
        {
          v11 = NtQuerySecurityObject(Handle, 0x7Fu, *(PSECURITY_DESCRIPTOR *)(a2 + 1088), *v5, &LengthNeeded);
          if ( v11 >= 0 )
            break;
          if ( v11 != -2147483643 && v11 != -1073741789 )
          {
            v12 = NtQuerySecurityObject(Handle, 0x77u, *(PSECURITY_DESCRIPTOR *)(a2 + 1088), *v5, &LengthNeeded);
            if ( v12 >= 0 )
              break;
            if ( v12 != -2147483643 && v12 != -1073741789 )
              return 1;
          }
        }
        result = GrowBuffer(v5, LengthNeeded);
        if ( !(_DWORD)result )
          return result;
      }
      v9 = *(void **)(a2 + 1088);
      *(_BYTE *)(a2 + 1128) = 1;
      *(_DWORD *)a2 = 3;
      *(_DWORD *)(a2 + 4) = 2;
      *(_DWORD *)(a2 + 16) = 0;
      *(_DWORD *)(a2 + 1068) = 20;
      *(_QWORD *)(a2 + 8) = RtlLengthSecurityDescriptor(v9);
      *(_BYTE *)(a2 + 1129) = 0;
    }
    else if ( *(_QWORD *)(a2 + 1056) >= (__int64)*(unsigned int *)(a2 + 1068) )
    {
      BackupReadBuffer(a2, a3);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18002ff44  mov     [rsp+arg_0], rbx
0x18002ff49  mov     [rsp+arg_8], rsi
0x18002ff4e  push    rdi
0x18002ff4f  sub     rsp, 30h
0x18002ff53  cmp     byte ptr [r8+14h], 0
0x18002ff58  mov     rbx, rdx
0x18002ff5b  mov     rsi, rcx
0x18002ff5e  jz      loc_180030002
0x18002ff64  cmp     byte ptr [rdx+469h], 0
0x18002ff6b  jz      loc_180030018
0x18002ff71  lea     rdi, [rdx+438h]
0x18002ff78  mov     r8d, [rdi]; Size
0x18002ff7b  xor     edx, edx; Val
0x18002ff7d  mov     rcx, [rbx+440h]; void *
0x18002ff84  mov     [rsp+38h+arg_10], 0
0x18002ff8c  call    memset_0
0x18002ff91  mov     r9d, [rdi]; Length
0x18002ff94  lea     rax, [rsp+38h+arg_10]
0x18002ff99  mov     r8, [rbx+440h]; SecurityDescriptor
0x18002ffa0  mov     edx, 1007Fh; SecurityInformation
0x18002ffa5  mov     rcx, rsi; Handle
0x18002ffa8  mov     [rsp+38h+LengthNeeded], rax; LengthNeeded
0x18002ffad  call    cs:__imp_NtQuerySecurityObject
0x18002ffb4  nop     dword ptr [rax+rax+00h]
0x18002ffb9  test    eax, eax
0x18002ffbb  js      short loc_180030034
0x18002ffbd  mov     rcx, [rbx+440h]; SecurityDescriptor
0x18002ffc4  mov     byte ptr [rbx+468h], 1
0x18002ffcb  mov     dword ptr [rbx], 3
0x18002ffd1  mov     dword ptr [rbx+4], 2
0x18002ffd8  mov     dword ptr [rbx+10h], 0
0x18002ffdf  mov     dword ptr [rbx+42Ch], 14h
0x18002ffe9  call    cs:__imp_RtlLengthSecurityDescriptor
0x18002fff0  nop     dword ptr [rax+rax+00h]
0x18002fff5  mov     eax, eax
0x18002fff7  mov     [rbx+8], rax
0x18002fffb  mov     byte ptr [rbx+469h], 0
0x180030002  mov     eax, 1
0x180030007  mov     rbx, [rsp+38h+arg_0]
0x18003000c  mov     rsi, [rsp+38h+arg_8]
0x180030011  add     rsp, 30h
0x180030015  pop     rdi
0x180030016  retn
0x180030018  mov     ecx, [rdx+42Ch]
0x18003001e  cmp     [rdx+420h], rcx
0x180030025  jl      short loc_180030002
0x180030027  mov     rdx, r8
0x18003002a  mov     rcx, rbx
0x18003002d  call    BackupReadBuffer
0x180030032  jmp     short loc_180030002
0x180030034  cmp     eax, 80000005h
0x180030039  jz      loc_1800300CA
0x18003003f  cmp     eax, 0C0000023h
0x180030044  jz      loc_1800300CA
0x18003004a  mov     r9d, [rdi]; Length
0x18003004d  lea     rax, [rsp+38h+arg_10]
0x180030052  mov     r8, [rbx+440h]; SecurityDescriptor
0x180030059  mov     edx, 7Fh; SecurityInformation
0x18003005e  mov     rcx, rsi; Handle
0x180030061  mov     [rsp+38h+LengthNeeded], rax; LengthNeeded
0x180030066  call    cs:__imp_NtQuerySecurityObject
0x18003006d  nop     dword ptr [rax+rax+00h]
0x180030072  test    eax, eax
0x180030074  jns     loc_18002FFBD
0x18003007a  cmp     eax, 80000005h
0x18003007f  jz      short loc_1800300CA
0x180030081  cmp     eax, 0C0000023h
0x180030086  jz      short loc_1800300CA
0x180030088  mov     r9d, [rdi]; Length
0x18003008b  lea     rax, [rsp+38h+arg_10]
0x180030090  mov     r8, [rbx+440h]; SecurityDescriptor
0x180030097  mov     edx, 77h ; 'w'; SecurityInformation
0x18003009c  mov     rcx, rsi; Handle
0x18003009f  mov     [rsp+38h+LengthNeeded], rax; LengthNeeded
0x1800300a4  call    cs:__imp_NtQuerySecurityObject
0x1800300ab  nop     dword ptr [rax+rax+00h]
0x1800300b0  test    eax, eax
0x1800300b2  jns     loc_18002FFBD
0x1800300b8  cmp     eax, 80000005h
0x1800300bd  jz      short loc_1800300CA
0x1800300bf  cmp     eax, 0C0000023h
0x1800300c4  jnz     loc_180030002
0x1800300ca  mov     edx, [rsp+38h+arg_10]
0x1800300ce  mov     rcx, rdi
0x1800300d1  call    GrowBuffer
0x1800300d6  test    eax, eax
0x1800300d8  jnz     loc_18002FF78
0x1800300de  jmp     loc_180030007
```
