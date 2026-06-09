# DhcpValidateClient

- ea: `0x180008e38`
- end: `0x180008f7c`
- name: `DhcpValidateClient`
- size: `324`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180058c00`
- `0x18005a5cc`
- `0x18005a9ec`

## callees

- `0x180008e38`
- `0x18000e284`
- `0x18000e450`
- `0x180030f3c`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x180008ef2`
- `ntdll!RtlCompareMemory` at `0x180008f23`
- `ntdll!RtlCompareMemory` at `0x180008ef2`
- `ntdll!RtlCompareMemory` at `0x180008f23`
- `KERNEL32!LocalFree` at `0x180008f5a`
- `KERNEL32!LocalFree` at `0x180008f5a`
- `KERNEL32!EnterCriticalSection` at `0x180008e6f`
- `KERNEL32!EnterCriticalSection` at `0x180008e6f`
- `KERNEL32!LeaveCriticalSection` at `0x180008f45`
- `KERNEL32!LeaveCriticalSection` at `0x180008f45`

## pseudocode

```c
_BOOL8 __fastcall DhcpValidateClient(int a1, unsigned int *a2, unsigned int a3)
{
  __int64 v3; // rsi
  BOOL v5; // edi
  unsigned int v6; // eax
  void *v7; // rcx
  SIZE_T v8; // rbx
  void *Source1; // [rsp+20h] [rbp-10h] BYREF
  int v11; // [rsp+50h] [rbp+20h] BYREF
  SIZE_T Length; // [rsp+68h] [rbp+38h] BYREF

  v11 = a1;
  v3 = a3;
  Source1 = 0;
  LODWORD(Length) = 0;
  v5 = 0;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( !(unsigned int)DhcpJetOpenKey(*(_QWORD *)DhcpGlobalClientTable, &v11, 4)
    && !(unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 24), &Source1, (unsigned int *)&Length) )
  {
    v6 = Length;
    if ( (unsigned int)Length >= 4 )
    {
      v7 = Source1;
      if ( Source1 )
      {
        if ( (_DWORD)Length == (_DWORD)v3 )
        {
          if ( (unsigned int)DhcpInSameSuperScope(*(unsigned int *)Source1, *a2) )
          {
            v8 = (unsigned int)Length - 4LL;
            if ( RtlCompareMemory((char *)Source1 + 4, a2 + 1, v8) == v8 )
            {
              v5 = 1;
              goto LABEL_12;
            }
          }
          v7 = Source1;
          v6 = Length;
        }
        if ( v6 == v3 - 5 )
          v5 = RtlCompareMemory(v7, (char *)a2 + 5, v6) == v6;
      }
    }
  }
LABEL_12:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( Source1 )
    LocalFree(Source1);
  return v5;
}

```

## disassembly

```asm
0x180008e38  mov     [rsp-18h+arg_8], rbx
0x180008e3d  mov     [rsp-18h+arg_10], rsi
0x180008e42  mov     [rsp-18h+arg_0], ecx
0x180008e46  push    rbp
0x180008e47  push    rdi
0x180008e48  push    r14
0x180008e4a  mov     rbp, rsp
0x180008e4d  sub     rsp, 30h
0x180008e51  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180008e58  mov     esi, r8d
0x180008e5b  mov     r14, rdx
0x180008e5e  mov     [rbp+Source1], 0
0x180008e66  mov     dword ptr [rbp+Length], 0
0x180008e6d  xor     edi, edi
0x180008e6f  call    cs:__imp_EnterCriticalSection
0x180008e76  nop     dword ptr [rax+rax+00h]
0x180008e7b  mov     rcx, cs:DhcpGlobalClientTable
0x180008e82  lea     r8d, [rdi+4]
0x180008e86  lea     rdx, [rbp+arg_0]
0x180008e8a  mov     rcx, [rcx]
0x180008e8d  call    DhcpJetOpenKey
0x180008e92  test    eax, eax
0x180008e94  jnz     loc_180008F3E
0x180008e9a  mov     rcx, cs:DhcpGlobalClientTable
0x180008ea1  lea     r8, [rbp+Length]; pcbActual
0x180008ea5  lea     rdx, [rbp+Source1]; pvData
0x180008ea9  mov     ecx, [rcx+18h]; columnid
0x180008eac  call    DhcpJetGetValue
0x180008eb1  test    eax, eax
0x180008eb3  jnz     loc_180008F3E
0x180008eb9  mov     eax, dword ptr [rbp+Length]
0x180008ebc  cmp     eax, 4
0x180008ebf  jb      short loc_180008F3E
0x180008ec1  mov     rcx, [rbp+Source1]
0x180008ec5  test    rcx, rcx
0x180008ec8  jz      short loc_180008F3E
0x180008eca  cmp     eax, esi
0x180008ecc  jnz     short loc_180008F11
0x180008ece  mov     edx, [r14]
0x180008ed1  mov     ecx, [rcx]
0x180008ed3  call    DhcpInSameSuperScope
0x180008ed8  test    eax, eax
0x180008eda  jz      short loc_180008F0A
0x180008edc  mov     ebx, dword ptr [rbp+Length]
0x180008edf  lea     rdx, [r14+4]; Source2
0x180008ee3  mov     rcx, [rbp+Source1]
0x180008ee7  add     rbx, 0FFFFFFFFFFFFFFFCh
0x180008eeb  mov     r8, rbx; Length
0x180008eee  add     rcx, 4; Source1
0x180008ef2  call    cs:__imp_RtlCompareMemory
0x180008ef9  nop     dword ptr [rax+rax+00h]
0x180008efe  cmp     rax, rbx
0x180008f01  jnz     short loc_180008F0A
0x180008f03  mov     edi, 1
0x180008f08  jmp     short loc_180008F3E
0x180008f0a  mov     rcx, [rbp+Source1]; Source1
0x180008f0e  mov     eax, dword ptr [rbp+Length]
0x180008f11  mov     ebx, eax
0x180008f13  lea     rax, [rsi-5]
0x180008f17  cmp     rbx, rax
0x180008f1a  jnz     short loc_180008F3E
0x180008f1c  lea     rdx, [r14+5]; Source2
0x180008f20  mov     r8d, ebx; Length
0x180008f23  call    cs:__imp_RtlCompareMemory
0x180008f2a  nop     dword ptr [rax+rax+00h]
0x180008f2f  mov     edx, edi
0x180008f31  mov     edi, 1
0x180008f36  cmp     rax, rbx
0x180008f39  cmovz   edx, edi
0x180008f3c  mov     edi, edx
0x180008f3e  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180008f45  call    cs:__imp_LeaveCriticalSection
0x180008f4c  nop     dword ptr [rax+rax+00h]
0x180008f51  mov     rcx, [rbp+Source1]; hMem
0x180008f55  test    rcx, rcx
0x180008f58  jz      short loc_180008F66
0x180008f5a  call    cs:__imp_LocalFree
0x180008f61  nop     dword ptr [rax+rax+00h]
0x180008f66  mov     rbx, [rsp+30h+arg_8]
0x180008f6b  mov     eax, edi
0x180008f6d  mov     rsi, [rsp+30h+arg_10]
0x180008f72  add     rsp, 30h
0x180008f76  pop     r14
0x180008f78  pop     rdi
0x180008f79  pop     rbp
0x180008f7a  retn
```
