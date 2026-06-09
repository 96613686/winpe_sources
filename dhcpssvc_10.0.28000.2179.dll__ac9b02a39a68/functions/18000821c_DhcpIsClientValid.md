# DhcpIsClientValid

- ea: `0x18000821c`
- end: `0x1800083c3`
- name: `DhcpIsClientValid`
- size: `423`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180054bd8`
- `0x18005a9ec`

## callees

- `0x18000821c`
- `0x18000e284`
- `0x18000e450`
- `0x18008f58c`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1800082c8`
- `ntdll!RtlCompareMemory` at `0x1800082f0`
- `ntdll!RtlCompareMemory` at `0x18000831b`
- `ntdll!RtlCompareMemory` at `0x180008374`
- `ntdll!RtlCompareMemory` at `0x1800082c8`
- `ntdll!RtlCompareMemory` at `0x1800082f0`
- `ntdll!RtlCompareMemory` at `0x18000831b`
- `ntdll!RtlCompareMemory` at `0x180008374`
- `KERNEL32!LocalFree` at `0x1800083a3`
- `KERNEL32!LocalFree` at `0x1800083a3`
- `KERNEL32!EnterCriticalSection` at `0x18000825e`
- `KERNEL32!EnterCriticalSection` at `0x18000825e`
- `KERNEL32!LeaveCriticalSection` at `0x18000838e`
- `KERNEL32!LeaveCriticalSection` at `0x18000838e`

## pseudocode

```c
__int64 __fastcall DhcpIsClientValid(unsigned int a1, const void *a2, unsigned int a3, _DWORD *a4)
{
  __int64 v4; // rsi
  unsigned int v7; // edi
  unsigned int v8; // ecx
  SIZE_T v9; // rbx
  _BYTE *v10; // rax
  SIZE_T v11; // r8
  unsigned __int64 v12; // rcx
  __int64 v13; // rbx
  void *Source1; // [rsp+20h] [rbp-10h] BYREF
  unsigned int Source2; // [rsp+60h] [rbp+30h] BYREF
  SIZE_T Length; // [rsp+78h] [rbp+48h] BYREF

  Source2 = a1;
  v4 = a3;
  Source1 = 0;
  LODWORD(Length) = 0;
  v7 = 1;
  *a4 = 0;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( !(unsigned int)DhcpJetOpenKey(*(_QWORD *)DhcpGlobalClientTable, &Source2, 4) )
  {
    if ( (unsigned int)DhcpJetGetValue(*(_DWORD *)(DhcpGlobalClientTable + 24), &Source1, (unsigned int *)&Length) )
      goto LABEL_20;
    v8 = Length;
    if ( (unsigned int)Length == v4 + 5 )
    {
      v9 = (unsigned int)Length - 5LL;
      if ( RtlCompareMemory((char *)Source1 + 5, a2, v9) == v9 )
        goto LABEL_21;
      v8 = Length;
    }
    if ( v8 == (_DWORD)v4 )
    {
      if ( RtlCompareMemory(Source1, a2, v8) == v8 )
        goto LABEL_21;
      v8 = Length;
    }
    if ( v8 >= 4 && RtlCompareMemory(Source1, &Source2, 4u) == 4 )
      goto LABEL_11;
    v10 = (_BYTE *)DhcpIpAddressToDottedString(Source2);
    if ( !v10 )
      goto LABEL_20;
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( v10[v12] );
    if ( (unsigned int)Length < v12 )
      goto LABEL_20;
    v13 = -1;
    do
      ++v13;
    while ( v10[v13] );
    do
      ++v11;
    while ( v10[v11] );
    if ( RtlCompareMemory(Source1, v10, v11) == v13 )
LABEL_11:
      *a4 = 1;
    else
LABEL_20:
      v7 = 0;
  }
LABEL_21:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( Source1 )
    LocalFree(Source1);
  return v7;
}

```

## disassembly

```asm
0x18000821c  mov     [rsp-28h+arg_8], rbx
0x180008221  mov     [rsp-28h+Source2], ecx
0x180008225  push    rbp
0x180008226  push    rsi
0x180008227  push    rdi
0x180008228  push    r14
0x18000822a  push    r15
0x18000822c  mov     rbp, rsp
0x18000822f  sub     rsp, 30h
0x180008233  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18000823a  mov     esi, r8d
0x18000823d  mov     r15, r9
0x180008240  mov     [rbp+Source1], 0
0x180008248  mov     r14, rdx
0x18000824b  mov     dword ptr [rbp+Length], 0
0x180008252  mov     edi, 1
0x180008257  mov     dword ptr [r9], 0
0x18000825e  call    cs:__imp_EnterCriticalSection
0x180008265  nop     dword ptr [rax+rax+00h]
0x18000826a  mov     rcx, cs:DhcpGlobalClientTable
0x180008271  lea     r8d, [rdi+3]
0x180008275  lea     rdx, [rbp+Source2]
0x180008279  mov     rcx, [rcx]
0x18000827c  call    DhcpJetOpenKey
0x180008281  test    eax, eax
0x180008283  jnz     loc_180008387
0x180008289  mov     rcx, cs:DhcpGlobalClientTable
0x180008290  lea     r8, [rbp+Length]; pcbActual
0x180008294  lea     rdx, [rbp+Source1]; pvData
0x180008298  mov     ecx, [rcx+18h]; columnid
0x18000829b  call    DhcpJetGetValue
0x1800082a0  test    eax, eax
0x1800082a2  jnz     loc_180008385
0x1800082a8  mov     ecx, dword ptr [rbp+Length]
0x1800082ab  lea     rax, [rsi+5]
0x1800082af  mov     ebx, ecx
0x1800082b1  cmp     rcx, rax
0x1800082b4  jnz     short loc_1800082E0
0x1800082b6  mov     rcx, [rbp+Source1]
0x1800082ba  add     rbx, 0FFFFFFFFFFFFFFFBh
0x1800082be  add     rcx, 5; Source1
0x1800082c2  mov     r8, rbx; Length
0x1800082c5  mov     rdx, r14; Source2
0x1800082c8  call    cs:__imp_RtlCompareMemory
0x1800082cf  nop     dword ptr [rax+rax+00h]
0x1800082d4  cmp     rax, rbx
0x1800082d7  jz      loc_180008387
0x1800082dd  mov     ecx, dword ptr [rbp+Length]
0x1800082e0  cmp     ecx, esi
0x1800082e2  jnz     short loc_180008308
0x1800082e4  mov     ebx, ecx
0x1800082e6  mov     rdx, r14; Source2
0x1800082e9  mov     r8d, ecx; Length
0x1800082ec  mov     rcx, [rbp+Source1]; Source1
0x1800082f0  call    cs:__imp_RtlCompareMemory
0x1800082f7  nop     dword ptr [rax+rax+00h]
0x1800082fc  cmp     rax, rbx
0x1800082ff  jz      loc_180008387
0x180008305  mov     ecx, dword ptr [rbp+Length]
0x180008308  cmp     ecx, 4
0x18000830b  jb      short loc_180008332
0x18000830d  mov     rcx, [rbp+Source1]; Source1
0x180008311  lea     rdx, [rbp+Source2]; Source2
0x180008315  mov     r8d, 4; Length
0x18000831b  call    cs:__imp_RtlCompareMemory
0x180008322  nop     dword ptr [rax+rax+00h]
0x180008327  cmp     rax, 4
0x18000832b  jnz     short loc_180008332
0x18000832d  mov     [r15], edi
0x180008330  jmp     short loc_180008387
0x180008332  mov     ecx, [rbp+Source2]
0x180008335  call    DhcpIpAddressToDottedString
0x18000833a  mov     rdx, rax; Source2
0x18000833d  test    rax, rax
0x180008340  jz      short loc_180008385
0x180008342  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008346  mov     rcx, r8
0x180008349  inc     rcx
0x18000834c  cmp     byte ptr [rax+rcx], 0
0x180008350  jnz     short loc_180008349
0x180008352  mov     eax, dword ptr [rbp+Length]
0x180008355  cmp     rax, rcx
0x180008358  jb      short loc_180008385
0x18000835a  mov     rbx, r8
0x18000835d  inc     rbx
0x180008360  cmp     byte ptr [rdx+rbx], 0
0x180008364  jnz     short loc_18000835D
0x180008366  inc     r8; Length
0x180008369  cmp     byte ptr [rdx+r8], 0
0x18000836e  jnz     short loc_180008366
0x180008370  mov     rcx, [rbp+Source1]; Source1
0x180008374  call    cs:__imp_RtlCompareMemory
0x18000837b  nop     dword ptr [rax+rax+00h]
0x180008380  cmp     rax, rbx
0x180008383  jz      short loc_18000832D
0x180008385  xor     edi, edi
0x180008387  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18000838e  call    cs:__imp_LeaveCriticalSection
0x180008395  nop     dword ptr [rax+rax+00h]
0x18000839a  mov     rcx, [rbp+Source1]; hMem
0x18000839e  test    rcx, rcx
0x1800083a1  jz      short loc_1800083AF
0x1800083a3  call    cs:__imp_LocalFree
0x1800083aa  nop     dword ptr [rax+rax+00h]
0x1800083af  mov     rbx, [rsp+30h+arg_8]
0x1800083b4  mov     eax, edi
0x1800083b6  add     rsp, 30h
0x1800083ba  pop     r15
0x1800083bc  pop     r14
0x1800083be  pop     rdi
0x1800083bf  pop     rsi
0x1800083c0  pop     rbp
0x1800083c1  retn
```
