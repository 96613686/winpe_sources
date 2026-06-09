# DhcpIsClientValid

- ea: `0x180008224`
- end: `0x1800083c9`
- name: `DhcpIsClientValid`
- size: `421`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180054ec4`
- `0x18005ad38`

## callees

- `0x180008224`
- `0x18000ebd4`
- `0x18000ed88`
- `0x18008f3f0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1800082c7`
- `ntdll!RtlCompareMemory` at `0x1800082f1`
- `ntdll!RtlCompareMemory` at `0x18000831c`
- `ntdll!RtlCompareMemory` at `0x18000836f`
- `ntdll!RtlCompareMemory` at `0x1800082c7`
- `ntdll!RtlCompareMemory` at `0x1800082f1`
- `ntdll!RtlCompareMemory` at `0x18000831c`
- `ntdll!RtlCompareMemory` at `0x18000836f`
- `KERNEL32!LocalFree` at `0x1800083a7`
- `KERNEL32!LocalFree` at `0x1800083a7`
- `KERNEL32!EnterCriticalSection` at `0x18000825f`
- `KERNEL32!EnterCriticalSection` at `0x18000825f`
- `KERNEL32!LeaveCriticalSection` at `0x180008392`
- `KERNEL32!LeaveCriticalSection` at `0x180008392`

## pseudocode

```c
__int64 __fastcall DhcpIsClientValid(unsigned int a1, const void *a2, unsigned int a3, _DWORD *a4)
{
  __int64 v6; // rdi
  unsigned int v7; // ebx
  unsigned int v8; // edx
  SIZE_T v9; // rax
  SIZE_T v10; // rax
  _BYTE *v11; // rax
  _BYTE *v12; // rsi
  __int64 v13; // rdi
  unsigned __int64 v14; // rcx
  SIZE_T v15; // r8
  SIZE_T v16; // rax
  void *Source1; // [rsp+20h] [rbp-10h] BYREF
  unsigned int Source2; // [rsp+50h] [rbp+20h] BYREF
  SIZE_T Length; // [rsp+68h] [rbp+38h] BYREF

  Source2 = a1;
  Source1 = 0;
  LODWORD(Length) = 0;
  *a4 = 0;
  v6 = a3;
  v7 = 1;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( !(unsigned int)DhcpJetOpenKey(*(_QWORD *)DhcpGlobalClientTable, &Source2, 4) )
  {
    if ( (unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 24), &Source1, (unsigned int *)&Length) )
      goto LABEL_19;
    v8 = Length;
    if ( (unsigned int)Length == v6 + 5 )
    {
      v9 = RtlCompareMemory((char *)Source1 + 5, a2, (unsigned int)Length - 5LL);
      v8 = Length;
      if ( v9 == (unsigned int)Length - 5LL )
        goto LABEL_20;
    }
    if ( v8 == (_DWORD)v6 )
    {
      v10 = RtlCompareMemory(Source1, a2, v8);
      v8 = Length;
      if ( v10 == (unsigned int)Length )
        goto LABEL_20;
    }
    if ( v8 >= 4 && RtlCompareMemory(Source1, &Source2, 4u) == 4 )
      goto LABEL_9;
    v11 = (_BYTE *)DhcpIpAddressToDottedString(Source2);
    v12 = v11;
    if ( !v11 )
      goto LABEL_19;
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( v11[v14] );
    if ( (unsigned int)Length < v14 )
      goto LABEL_19;
    v15 = -1;
    do
      ++v15;
    while ( v11[v15] );
    v16 = RtlCompareMemory(Source1, v11, v15);
    do
      ++v13;
    while ( v12[v13] );
    if ( v16 == v13 )
LABEL_9:
      *a4 = 1;
    else
LABEL_19:
      v7 = 0;
  }
LABEL_20:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( Source1 )
    LocalFree(Source1);
  return v7;
}

```

## disassembly

```asm
0x180008224  mov     [rsp-18h+arg_8], rbx
0x180008229  mov     [rsp-18h+arg_10], rsi
0x18000822e  mov     [rsp-18h+Source2], ecx
0x180008232  push    rbp
0x180008233  push    rdi
0x180008234  push    r14
0x180008236  mov     rbp, rsp
0x180008239  sub     rsp, 30h
0x18000823d  and     [rbp+Source1], 0
0x180008242  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180008249  and     dword ptr [rbp+Length], 0
0x18000824d  mov     r14, r9
0x180008250  and     dword ptr [r9], 0
0x180008254  mov     rsi, rdx
0x180008257  mov     edi, r8d
0x18000825a  mov     ebx, 1
0x18000825f  call    cs:__imp_EnterCriticalSection
0x180008266  nop     dword ptr [rax+rax+00h]
0x18000826b  mov     rcx, cs:DhcpGlobalClientTable
0x180008272  lea     r8d, [rbx+3]
0x180008276  lea     rdx, [rbp+Source2]
0x18000827a  mov     rcx, [rcx]
0x18000827d  call    DhcpJetOpenKey
0x180008282  test    eax, eax
0x180008284  jnz     loc_18000838B
0x18000828a  mov     rcx, cs:DhcpGlobalClientTable
0x180008291  lea     r8, [rbp+Length]; pcbActual
0x180008295  lea     rdx, [rbp+Source1]; pvData
0x180008299  mov     ecx, [rcx+18h]; columnid
0x18000829c  call    DhcpJetGetValue
0x1800082a1  test    eax, eax
0x1800082a3  jnz     loc_180008389
0x1800082a9  mov     edx, dword ptr [rbp+Length]
0x1800082ac  lea     rax, [rdi+5]
0x1800082b0  mov     r8d, edx
0x1800082b3  cmp     rdx, rax
0x1800082b6  jnz     short loc_1800082E3
0x1800082b8  mov     rcx, [rbp+Source1]
0x1800082bc  add     r8, 0FFFFFFFFFFFFFFFBh; Length
0x1800082c0  add     rcx, 5; Source1
0x1800082c4  mov     rdx, rsi; Source2
0x1800082c7  call    cs:__imp_RtlCompareMemory
0x1800082ce  nop     dword ptr [rax+rax+00h]
0x1800082d3  mov     edx, dword ptr [rbp+Length]
0x1800082d6  lea     rcx, [rdx-5]
0x1800082da  cmp     rax, rcx
0x1800082dd  jz      loc_18000838B
0x1800082e3  cmp     edx, edi
0x1800082e5  jnz     short loc_180008309
0x1800082e7  mov     rcx, [rbp+Source1]; Source1
0x1800082eb  mov     r8d, edx; Length
0x1800082ee  mov     rdx, rsi; Source2
0x1800082f1  call    cs:__imp_RtlCompareMemory
0x1800082f8  nop     dword ptr [rax+rax+00h]
0x1800082fd  mov     edx, dword ptr [rbp+Length]
0x180008300  cmp     rax, rdx
0x180008303  jz      loc_18000838B
0x180008309  cmp     edx, 4
0x18000830c  jb      short loc_180008333
0x18000830e  mov     rcx, [rbp+Source1]; Source1
0x180008312  lea     rdx, [rbp+Source2]; Source2
0x180008316  mov     r8d, 4; Length
0x18000831c  call    cs:__imp_RtlCompareMemory
0x180008323  nop     dword ptr [rax+rax+00h]
0x180008328  cmp     rax, 4
0x18000832c  jnz     short loc_180008333
0x18000832e  mov     [r14], ebx
0x180008331  jmp     short loc_18000838B
0x180008333  mov     ecx, [rbp+Source2]
0x180008336  call    DhcpIpAddressToDottedString
0x18000833b  mov     rsi, rax
0x18000833e  test    rax, rax
0x180008341  jz      short loc_180008389
0x180008343  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180008347  mov     rcx, rdi
0x18000834a  inc     rcx
0x18000834d  cmp     byte ptr [rax+rcx], 0
0x180008351  jnz     short loc_18000834A
0x180008353  mov     eax, dword ptr [rbp+Length]
0x180008356  cmp     rax, rcx
0x180008359  jb      short loc_180008389
0x18000835b  mov     r8, rdi
0x18000835e  inc     r8; Length
0x180008361  cmp     byte ptr [rsi+r8], 0
0x180008366  jnz     short loc_18000835E
0x180008368  mov     rcx, [rbp+Source1]; Source1
0x18000836c  mov     rdx, rsi; Source2
0x18000836f  call    cs:__imp_RtlCompareMemory
0x180008376  nop     dword ptr [rax+rax+00h]
0x18000837b  inc     rdi
0x18000837e  cmp     byte ptr [rsi+rdi], 0
0x180008382  jnz     short loc_18000837B
0x180008384  cmp     rax, rdi
0x180008387  jz      short loc_18000832E
0x180008389  xor     ebx, ebx
0x18000838b  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180008392  call    cs:__imp_LeaveCriticalSection
0x180008399  nop     dword ptr [rax+rax+00h]
0x18000839e  mov     rcx, [rbp+Source1]; hMem
0x1800083a2  test    rcx, rcx
0x1800083a5  jz      short loc_1800083B3
0x1800083a7  call    cs:__imp_LocalFree
0x1800083ae  nop     dword ptr [rax+rax+00h]
0x1800083b3  mov     rsi, [rsp+30h+arg_10]
0x1800083b8  mov     eax, ebx
0x1800083ba  mov     rbx, [rsp+30h+arg_8]
0x1800083bf  add     rsp, 30h
0x1800083c3  pop     r14
0x1800083c5  pop     rdi
0x1800083c6  pop     rbp
0x1800083c7  retn
```
