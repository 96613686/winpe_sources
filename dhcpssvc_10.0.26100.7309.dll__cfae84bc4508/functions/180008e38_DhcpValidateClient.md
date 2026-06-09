# DhcpValidateClient

- ea: `0x180008e38`
- end: `0x180008f78`
- name: `DhcpValidateClient`
- size: `320`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180058f38`
- `0x18005a8f4`
- `0x18005ad38`

## callees

- `0x180008e38`
- `0x18000ebd4`
- `0x18000ed88`
- `0x180031978`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x180008ee7`
- `ntdll!RtlCompareMemory` at `0x180008f1f`
- `ntdll!RtlCompareMemory` at `0x180008ee7`
- `ntdll!RtlCompareMemory` at `0x180008f1f`
- `KERNEL32!LocalFree` at `0x180008f5c`
- `KERNEL32!LocalFree` at `0x180008f5c`
- `KERNEL32!EnterCriticalSection` at `0x180008e63`
- `KERNEL32!EnterCriticalSection` at `0x180008e63`
- `KERNEL32!LeaveCriticalSection` at `0x180008f47`
- `KERNEL32!LeaveCriticalSection` at `0x180008f47`

## pseudocode

```c
_BOOL8 __fastcall DhcpValidateClient(int a1, unsigned int *a2, unsigned int a3)
{
  __int64 v4; // rdi
  BOOL v5; // ebx
  unsigned int v6; // edx
  void *v7; // rcx
  int v8; // eax
  SIZE_T v9; // rax
  SIZE_T v10; // rax
  void *Source1; // [rsp+20h] [rbp-10h] BYREF
  int v13; // [rsp+50h] [rbp+20h] BYREF
  SIZE_T Length; // [rsp+68h] [rbp+38h] BYREF

  v13 = a1;
  Source1 = 0;
  LODWORD(Length) = 0;
  v4 = a3;
  v5 = 0;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( !(unsigned int)DhcpJetOpenKey(*(_QWORD *)DhcpGlobalClientTable, &v13, 4)
    && !(unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 24), &Source1, (unsigned int *)&Length) )
  {
    v6 = Length;
    if ( (unsigned int)Length >= 4 )
    {
      v7 = Source1;
      if ( Source1 )
      {
        if ( (_DWORD)Length == (_DWORD)v4 )
        {
          v8 = DhcpInSameSuperScope(*(unsigned int *)Source1, *a2);
          v7 = Source1;
          if ( v8 )
          {
            v9 = RtlCompareMemory((char *)Source1 + 4, a2 + 1, (unsigned int)Length - 4LL);
            v6 = Length;
            if ( v9 == (unsigned int)Length - 4LL )
            {
              v5 = 1;
              goto LABEL_13;
            }
            v7 = Source1;
          }
          else
          {
            v6 = Length;
          }
        }
        if ( v6 == v4 - 5 )
        {
          v10 = RtlCompareMemory(v7, (char *)a2 + 5, v6);
          v5 = v10 == Length;
        }
      }
    }
  }
LABEL_13:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( Source1 )
    LocalFree(Source1);
  return v5;
}

```

## disassembly

```asm
0x180008e38  mov     [rsp-18h+arg_8], rbx
0x180008e3d  mov     [rsp-18h+arg_0], ecx
0x180008e41  push    rbp
0x180008e42  push    rsi
0x180008e43  push    rdi
0x180008e44  mov     rbp, rsp
0x180008e47  sub     rsp, 30h
0x180008e4b  and     [rbp+Source1], 0
0x180008e50  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180008e57  and     dword ptr [rbp+Length], 0
0x180008e5b  mov     rsi, rdx
0x180008e5e  mov     edi, r8d
0x180008e61  xor     ebx, ebx
0x180008e63  call    cs:__imp_EnterCriticalSection
0x180008e6a  nop     dword ptr [rax+rax+00h]
0x180008e6f  mov     rcx, cs:DhcpGlobalClientTable
0x180008e76  lea     r8d, [rbx+4]
0x180008e7a  lea     rdx, [rbp+arg_0]
0x180008e7e  mov     rcx, [rcx]
0x180008e81  call    DhcpJetOpenKey
0x180008e86  test    eax, eax
0x180008e88  jnz     loc_180008F40
0x180008e8e  mov     rcx, cs:DhcpGlobalClientTable
0x180008e95  lea     r8, [rbp+Length]; pcbActual
0x180008e99  lea     rdx, [rbp+Source1]; pvData
0x180008e9d  mov     ecx, [rcx+18h]; columnid
0x180008ea0  call    DhcpJetGetValue
0x180008ea5  test    eax, eax
0x180008ea7  jnz     loc_180008F40
0x180008ead  mov     edx, dword ptr [rbp+Length]
0x180008eb0  cmp     edx, 4
0x180008eb3  jb      loc_180008F40
0x180008eb9  mov     rcx, [rbp+Source1]
0x180008ebd  test    rcx, rcx
0x180008ec0  jz      short loc_180008F40
0x180008ec2  cmp     edx, edi
0x180008ec4  jnz     short loc_180008F0F
0x180008ec6  mov     edx, [rsi]
0x180008ec8  mov     ecx, [rcx]
0x180008eca  call    DhcpInSameSuperScope
0x180008ecf  mov     rcx, [rbp+Source1]; Source1
0x180008ed3  test    eax, eax
0x180008ed5  jz      short loc_180008F0C
0x180008ed7  mov     r8d, dword ptr [rbp+Length]
0x180008edb  lea     rdx, [rsi+4]; Source2
0x180008edf  sub     r8, 4; Length
0x180008ee3  add     rcx, 4; Source1
0x180008ee7  call    cs:__imp_RtlCompareMemory
0x180008eee  nop     dword ptr [rax+rax+00h]
0x180008ef3  mov     edx, dword ptr [rbp+Length]
0x180008ef6  lea     rcx, [rdx-4]
0x180008efa  cmp     rax, rcx
0x180008efd  jnz     short loc_180008F06
0x180008eff  mov     ebx, 1
0x180008f04  jmp     short loc_180008F40
0x180008f06  mov     rcx, [rbp+Source1]
0x180008f0a  jmp     short loc_180008F0F
0x180008f0c  mov     edx, dword ptr [rbp+Length]
0x180008f0f  mov     r8d, edx; Length
0x180008f12  lea     rax, [rdi-5]
0x180008f16  cmp     r8, rax
0x180008f19  jnz     short loc_180008F40
0x180008f1b  lea     rdx, [rsi+5]; Source2
0x180008f1f  call    cs:__imp_RtlCompareMemory
0x180008f26  nop     dword ptr [rax+rax+00h]
0x180008f2b  mov     edx, dword ptr [rbp+Length]
0x180008f2e  mov     r8d, ebx
0x180008f31  mov     ebx, 1
0x180008f36  cmp     rax, rdx
0x180008f39  cmovz   r8d, ebx
0x180008f3d  mov     ebx, r8d
0x180008f40  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180008f47  call    cs:__imp_LeaveCriticalSection
0x180008f4e  nop     dword ptr [rax+rax+00h]
0x180008f53  mov     rcx, [rbp+Source1]; hMem
0x180008f57  test    rcx, rcx
0x180008f5a  jz      short loc_180008F68
0x180008f5c  call    cs:__imp_LocalFree
0x180008f63  nop     dword ptr [rax+rax+00h]
0x180008f68  mov     eax, ebx
0x180008f6a  mov     rbx, [rsp+30h+arg_8]
0x180008f6f  add     rsp, 30h
0x180008f73  pop     rdi
0x180008f74  pop     rsi
0x180008f75  pop     rbp
0x180008f76  retn
```
