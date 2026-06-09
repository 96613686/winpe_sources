# CsrApiHandleConnectionRequest

- ea: `0x1800021f0`
- end: `0x18000244b`
- name: `CsrApiHandleConnectionRequest`
- size: `603`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800097f0`

## callees

- `0x1800021f0`
- `0x180002460`
- `0x180002850`
- `0x180002c90`
- `0x1800030a0`
- `0x1800035c0`

## import_xrefs

- `ntdll!NtAlpcAcceptConnectPort` at `0x1800022f6`
- `ntdll!NtAlpcAcceptConnectPort` at `0x1800022f6`
- `ntdll!RtlEnterCriticalSection` at `0x18000221f`
- `ntdll!RtlEnterCriticalSection` at `0x18000221f`
- `ntdll!RtlLeaveCriticalSection` at `0x180002358`
- `ntdll!RtlLeaveCriticalSection` at `0x1800023f5`
- `ntdll!RtlLeaveCriticalSection` at `0x180002358`
- `ntdll!RtlLeaveCriticalSection` at `0x1800023f5`
- `ntdll!NtAlpcDeleteSectionView` at `0x180002413`
- `ntdll!NtAlpcDeleteSectionView` at `0x180002413`

## pseudocode

```c
__int64 __fastcall CsrApiHandleConnectionRequest(__int64 a1, __int64 a2)
{
  char v4; // r14
  __int64 *v5; // rdx
  __int64 *i; // rcx
  __int64 *v7; // rdi
  __int64 v8; // rbx
  int v9; // edi
  __int64 ProcessByClientId; // rax
  int v12; // eax
  __int64 *v13; // rdx
  __int64 *j; // rcx
  __int64 v15; // [rsp+80h] [rbp+8h] BYREF

  v4 = 0;
  v15 = 0;
  RtlEnterCriticalSection(&CsrProcessStructureLock);
  if ( a2 )
  {
    v5 = &CsrThreadHashTable[2 * ((*(_DWORD *)(a1 + 16) >> 2) & 0x3FF)];
    for ( i = (__int64 *)*v5; ; i = (__int64 *)*i )
    {
      if ( i == v5 )
      {
        v7 = 0;
        goto LABEL_17;
      }
      v7 = i - 3;
      if ( i[3] == *(_QWORD *)(a1 + 16) && v7[5] == *(_QWORD *)(a1 + 8) )
        break;
    }
    if ( i != (__int64 *)24 )
    {
LABEL_8:
      v8 = v7[7];
      goto LABEL_9;
    }
LABEL_17:
    ProcessByClientId = CsrLocateProcessByClientId(*(_QWORD *)(a1 + 8));
    if ( ProcessByClientId )
    {
      v12 = CsrRegisterThread(ProcessByClientId, a1);
      v8 = 0;
    }
    else
    {
      v8 = 0;
      v12 = CsrProcessLazyRegister(a1);
    }
    if ( v12 < 0 )
      goto LABEL_12;
    v13 = &CsrThreadHashTable[2 * ((*(_DWORD *)(a1 + 16) >> 2) & 0x3FF)];
    for ( j = (__int64 *)*v13; j != v13; j = (__int64 *)*j )
    {
      v7 = j - 3;
      if ( j[3] == *(_QWORD *)(a1 + 16) && v7[5] == *(_QWORD *)(a1 + 8) )
        goto LABEL_8;
    }
    v8 = 0;
    v7 = 0;
LABEL_9:
    if ( v8 && !*(_QWORD *)(v8 + 56) )
    {
      v4 = 1;
      *(_QWORD *)(a1 + 40) = CsrSrvSharedSectionBase;
      *(_QWORD *)(a1 + 48) = CsrSrvSharedStaticServerData;
    }
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
LABEL_12:
  *(_QWORD *)(a1 + 56) = KeGetPcr()->NtTib.Self[1].StackBase;
  CsrpHandleInlineUserConnect(a1, v8, v7);
  v9 = NtAlpcAcceptConnectPort(&v15, CsrApiPort, 0, 0, 0, v8, a1, 0, v4);
  if ( v9 >= 0 && v4 )
  {
    *(_QWORD *)(v8 + 56) = v15;
    *(_QWORD *)(v8 + 64) = *(_QWORD *)(a2 + 16);
    *(_QWORD *)(v8 + 72) = *(_QWORD *)(a2 + 16) + *(_QWORD *)(a2 + 24);
    *(_DWORD *)(v8 + 92) |= 0x8000u;
    RtlLeaveCriticalSection(&CsrProcessStructureLock);
  }
  else
  {
    RtlLeaveCriticalSection(&CsrProcessStructureLock);
    if ( a2 )
      NtAlpcDeleteSectionView(CsrApiPort, 0, *(_QWORD *)(a2 + 16));
    if ( v9 < 0 )
      CsrpLogFailure("CsrApiHandleConnectionRequest");
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800021f0  mov     rax, rsp
0x1800021f3  push    rbx
0x1800021f4  push    rbp
0x1800021f5  push    rdi
0x1800021f6  push    r14
0x1800021f8  sub     rsp, 58h
0x1800021fc  mov     [rax+10h], rsi
0x180002200  mov     rbp, rdx
0x180002203  mov     [rax+18h], r12
0x180002207  mov     rsi, rcx
0x18000220a  mov     [rax-28h], r15
0x18000220e  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002215  xor     r15d, r15d
0x180002218  xor     r14b, r14b
0x18000221b  mov     [rax+8], r15
0x18000221f  call    cs:__imp_RtlEnterCriticalSection
0x180002226  nop     dword ptr [rax+rax+00h]
0x18000222b  test    rbp, rbp
0x18000222e  jz      loc_180002440
0x180002234  mov     edx, [rsi+10h]
0x180002237  lea     r12, CsrThreadHashTable
0x18000223e  shr     rdx, 2
0x180002242  and     edx, 3FFh
0x180002248  shl     rdx, 4
0x18000224c  add     rdx, r12
0x18000224f  mov     rcx, [rdx]
0x180002252  cmp     rcx, rdx
0x180002255  jz      loc_180002371
0x18000225b  mov     rax, [rsi+10h]
0x18000225f  lea     rdi, [rcx-18h]
0x180002263  cmp     [rdi+30h], rax
0x180002267  jz      short loc_18000226E
0x180002269  mov     rcx, [rcx]
0x18000226c  jmp     short loc_180002252
0x18000226e  mov     rax, [rsi+8]
0x180002272  cmp     [rdi+28h], rax
0x180002276  jnz     short loc_180002269
0x180002278  test    rdi, rdi
0x18000227b  jz      loc_180002374
0x180002281  mov     rbx, [rdi+38h]
0x180002285  test    rbx, rbx
0x180002288  jz      short loc_1800022A9
0x18000228a  cmp     [rbx+38h], r15
0x18000228e  jnz     short loc_1800022A9
0x180002290  mov     rax, cs:CsrSrvSharedSectionBase
0x180002297  mov     r14b, 1
0x18000229a  mov     [rsi+28h], rax
0x18000229e  mov     rax, cs:CsrSrvSharedStaticServerData
0x1800022a5  mov     [rsi+30h], rax
0x1800022a9  mov     rax, gs:30h
0x1800022b2  mov     r8, rdi
0x1800022b5  mov     rdx, rbx
0x1800022b8  mov     rcx, [rax+40h]
0x1800022bc  mov     [rsi+38h], rcx
0x1800022c0  mov     rcx, rsi
0x1800022c3  call    CsrpHandleInlineUserConnect
0x1800022c8  mov     rdx, cs:CsrApiPort
0x1800022cf  lea     rcx, [rsp+78h+arg_0]
0x1800022d7  mov     [rsp+78h+var_38], r14b
0x1800022dc  xor     r9d, r9d
0x1800022df  mov     [rsp+78h+var_40], r15
0x1800022e4  xor     r8d, r8d
0x1800022e7  mov     [rsp+78h+var_48], rsi
0x1800022ec  mov     [rsp+78h+var_50], rbx
0x1800022f1  mov     [rsp+78h+var_58], r15
0x1800022f6  call    cs:__imp_NtAlpcAcceptConnectPort
0x1800022fd  nop     dword ptr [rax+rax+00h]
0x180002302  mov     r15, [rsp+78h+var_28]
0x180002307  mov     edi, eax
0x180002309  mov     r12, [rsp+78h+arg_10]
0x180002311  mov     rsi, [rsp+78h+arg_8]
0x180002319  test    eax, eax
0x18000231b  js      loc_1800023EE
0x180002321  test    r14b, r14b
0x180002324  jz      loc_1800023EE
0x18000232a  mov     rdx, [rsp+78h+arg_0]
0x180002332  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180002339  mov     [rbx+38h], rdx
0x18000233d  mov     rdx, [rbp+10h]
0x180002341  mov     [rbx+40h], rdx
0x180002345  mov     rdx, [rbp+18h]
0x180002349  add     rdx, [rbp+10h]
0x18000234d  mov     [rbx+48h], rdx
0x180002351  or      dword ptr [rbx+5Ch], 8000h
0x180002358  call    cs:__imp_RtlLeaveCriticalSection
0x18000235f  nop     dword ptr [rax+rax+00h]
0x180002364  mov     eax, edi
0x180002366  add     rsp, 58h
0x18000236a  pop     r14
0x18000236c  pop     rdi
0x18000236d  pop     rbp
0x18000236e  pop     rbx
0x18000236f  retn
0x180002371  mov     rdi, r15
0x180002374  mov     rcx, [rsi+8]
0x180002378  call    CsrLocateProcessByClientId
0x18000237d  test    rax, rax
0x180002380  jnz     short loc_1800023DE
0x180002382  mov     rcx, rsi
0x180002385  mov     rbx, r15
0x180002388  call    CsrProcessLazyRegister
0x18000238d  test    eax, eax
0x18000238f  js      loc_1800022A9
0x180002395  mov     edx, [rsi+10h]
0x180002398  shr     rdx, 2
0x18000239c  and     edx, 3FFh
0x1800023a2  shl     rdx, 4
0x1800023a6  add     rdx, r12
0x1800023a9  mov     rcx, [rdx]
0x1800023ac  cmp     rcx, rdx
0x1800023af  jz      short loc_1800023D3
0x1800023b1  mov     rax, [rsi+10h]
0x1800023b5  lea     rdi, [rcx-18h]
0x1800023b9  cmp     [rdi+30h], rax
0x1800023bd  jz      short loc_1800023C4
0x1800023bf  mov     rcx, [rcx]
0x1800023c2  jmp     short loc_1800023AC
0x1800023c4  mov     rax, [rsi+8]
0x1800023c8  cmp     [rdi+28h], rax
0x1800023cc  jnz     short loc_1800023BF
0x1800023ce  jmp     loc_180002281
0x1800023d3  mov     rbx, r15
0x1800023d6  mov     rdi, r15
0x1800023d9  jmp     loc_180002285
0x1800023de  mov     rdx, rsi
0x1800023e1  mov     rcx, rax
0x1800023e4  call    CsrRegisterThread
0x1800023e9  mov     rbx, r15
0x1800023ec  jmp     short loc_18000238D
0x1800023ee  lea     rcx, CsrProcessStructureLock; CriticalSection
0x1800023f5  call    cs:__imp_RtlLeaveCriticalSection
0x1800023fc  nop     dword ptr [rax+rax+00h]
0x180002401  test    rbp, rbp
0x180002404  jz      short loc_18000241F
0x180002406  mov     r8, [rbp+10h]
0x18000240a  xor     edx, edx
0x18000240c  mov     rcx, cs:CsrApiPort
0x180002413  call    cs:__imp_NtAlpcDeleteSectionView
0x18000241a  nop     dword ptr [rax+rax+00h]
0x18000241f  test    edi, edi
0x180002421  jns     loc_180002364
0x180002427  mov     r8d, edi
0x18000242a  lea     rcx, aCsrapihandleco; "CsrApiHandleConnectionRequest"
0x180002431  mov     edx, 903h
0x180002436  call    CsrpLogFailure
0x18000243b  jmp     loc_180002364
0x180002440  mov     rdi, r15
0x180002443  mov     rbx, r15
0x180002446  jmp     loc_1800022A9
```
