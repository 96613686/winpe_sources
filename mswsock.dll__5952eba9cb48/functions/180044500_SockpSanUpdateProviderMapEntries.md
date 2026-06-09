# SockpSanUpdateProviderMapEntries

- ea: `0x180044500`
- end: `0x1800447fa`
- name: `SockpSanUpdateProviderMapEntries`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x1800442e8`

## callees

- `0x1800222f0`
- `0x18004345c`
- `0x180044500`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044540`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180044540`
- `ntdll!RtlFreeHeap` at `0x1800447ae`
- `ntdll!RtlFreeHeap` at `0x1800447ae`

## pseudocode

```c
__int64 __fastcall SockpSanUpdateProviderMapEntries(__int64 a1)
{
  _QWORD *v2; // rdi
  __int64 *v3; // r9
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // r14
  int *HeapRoutine; // rbx
  __int64 v8; // r8
  unsigned int v9; // r15d
  _QWORD *v10; // r11
  _QWORD *v11; // r10
  __int64 v12; // r9
  unsigned int i; // edx
  unsigned int j; // edx
  void (__fastcall *v15)(__int64, _QWORD **); // rax
  unsigned int v17; // [rsp+60h] [rbp-19h] BYREF
  unsigned int v18; // [rsp+64h] [rbp-15h] BYREF
  _QWORD *Value; // [rsp+68h] [rbp-11h] BYREF
  __int64 v20; // [rsp+70h] [rbp-9h]
  _BYTE v21[40]; // [rsp+78h] [rbp-1h] BYREF

  v17 = 0;
  v18 = 0;
  Value = TlsGetValue(MSAFD_SockTlsSlot);
  v2 = Value;
  v3 = SockTcp6ProviderInfo;
  v4 = 23;
  Value[3] = 0;
  if ( *(_DWORD *)(a1 + 44) != 23 )
  {
    v3 = SockTcpProviderInfo;
    v4 = 2;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, _DWORD, int, unsigned int *))(a1 + 288))(
         v4,
         1,
         6,
         v3,
         0,
         1,
         &v17);
  v20 = v5;
  v6 = v5;
  if ( v5 != -1 )
  {
    HeapRoutine = (int *)v21;
    if ( (*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _BYTE *, int, unsigned int *, _QWORD, _QWORD, _QWORD, unsigned int *))(a1 + 192))(
           v5,
           1207959574,
           0,
           0,
           v21,
           40,
           &v18,
           0,
           0,
           0,
           &v17) == -1 )
    {
      if ( v17 != 10014 )
        goto LABEL_34;
      HeapRoutine = (int *)SockAllocateHeapRoutine(SockPrivateHeap, 0, v18);
      if ( !HeapRoutine )
      {
        v17 = 8;
        v2[3] = -1;
LABEL_37:
        v15 = *(void (__fastcall **)(__int64, _QWORD **))(a1 + 112);
        LODWORD(Value) = 0;
        v15(v6, &Value);
        return v17;
      }
      if ( (*(unsigned int (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int *, unsigned int, unsigned int *, _QWORD, _QWORD, _QWORD, unsigned int *))(a1 + 192))(
             v6,
             1207959574,
             0,
             0,
             HeapRoutine,
             v18,
             &v18,
             0,
             0,
             0,
             &v17) == -1 )
      {
        if ( !v17 )
          v17 = 10107;
        v2[3] = -1;
        goto LABEL_35;
      }
    }
    v8 = 0;
    if ( *HeapRoutine > 0 )
    {
      v9 = SockSanSubnetCount;
      v10 = SockSanSubnetMap;
      v11 = SockSanV6AddressMap;
      do
      {
        v12 = *(_QWORD *)&HeapRoutine[4 * (int)v8 + 2];
        if ( *(_WORD *)v12 == 2 )
        {
          for ( i = 0; i < v9; ++i )
          {
            if ( *(_DWORD *)(v12 + 4) == HIDWORD(v10[6 * i]) && !v10[6 * i + 5] )
              v10[6 * i + 5] = a1;
          }
        }
        else if ( *(_WORD *)v12 == 23 )
        {
          for ( j = 0; j < SockSanV6AddressCount; ++j )
          {
            if ( *(_QWORD *)(v12 + 16) == v11[3 * j + 1] && *(_QWORD *)(v12 + 8) == v11[3 * j] && !v11[3 * j + 2] )
              v11[3 * j + 2] = a1;
          }
        }
        v8 = (unsigned int)(v8 + 1);
      }
      while ( (int)v8 < *HeapRoutine );
      v2 = Value;
      v6 = v20;
    }
    SockpSanGetRdmaParameters(a1, v6, v8);
LABEL_34:
    v2[3] = -1;
    if ( !HeapRoutine )
      goto LABEL_37;
LABEL_35:
    if ( HeapRoutine != (int *)v21 )
      RtlFreeHeap(SockPrivateHeap, 0, HeapRoutine);
    goto LABEL_37;
  }
  if ( !v17 )
    v17 = 10107;
  v2[3] = -1;
  return v17;
}

```

## disassembly

```asm
0x180044500  mov     [rsp-8+arg_8], rbx
0x180044505  mov     [rsp-8+arg_10], rsi
0x18004450a  push    rbp
0x18004450b  push    rdi
0x18004450c  push    r13
0x18004450e  push    r14
0x180044510  push    r15
0x180044512  lea     rbp, [rsp-37h]
0x180044517  sub     rsp, 0B0h
0x18004451e  mov     rax, cs:__security_cookie
0x180044525  xor     rax, rsp
0x180044528  mov     [rbp+57h+var_30], rax
0x18004452c  mov     rsi, rcx
0x18004452f  xor     r13d, r13d
0x180044532  mov     ecx, cs:MSAFD_SockTlsSlot; dwTlsIndex
0x180044538  mov     [rbp+57h+var_70], r13d
0x18004453c  mov     [rbp+57h+var_6C], r13d
0x180044540  call    cs:__imp_TlsGetValue
0x180044547  nop     dword ptr [rax+rax+00h]
0x18004454c  lea     edx, [r13+17h]
0x180044550  mov     [rbp+57h+var_68], rax
0x180044554  mov     rdi, rax
0x180044557  lea     r9, SockTcp6ProviderInfo
0x18004455e  mov     ecx, edx
0x180044560  lea     r8d, [r13+6]
0x180044564  mov     [rax+18h], r13
0x180044568  lea     rax, SockTcpProviderInfo
0x18004456f  cmp     [rsi+2Ch], edx
0x180044572  cmovnz  r9, rax
0x180044576  lea     eax, [rdx-15h]
0x180044579  cmovnz  ecx, eax
0x18004457c  lea     rax, [rbp+57h+var_70]
0x180044580  mov     [rsp+0D0h+var_A0], rax
0x180044585  lea     eax, [rdx-16h]
0x180044588  mov     [rsp+0D0h+var_A8], eax
0x18004458c  mov     edx, eax
0x18004458e  mov     rax, [rsi+120h]
0x180044595  mov     dword ptr [rsp+0D0h+var_B0], r13d
0x18004459a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004459f  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800445a3  mov     [rbp+57h+var_60], rax
0x1800445a7  mov     r14, rax
0x1800445aa  cmp     rax, r15
0x1800445ad  jnz     short loc_1800445C5
0x1800445af  cmp     [rbp+57h+var_70], r13d
0x1800445b3  jnz     short loc_1800445BC
0x1800445b5  mov     [rbp+57h+var_70], 277Bh
0x1800445bc  mov     [rdi+18h], r15
0x1800445c0  jmp     loc_1800447CE
0x1800445c5  lea     rax, [rbp+57h+var_70]
0x1800445c9  xor     r9d, r9d
0x1800445cc  mov     [rsp+0D0h+var_80], rax
0x1800445d1  lea     rbx, [rbp+57h+var_58]
0x1800445d5  mov     [rsp+0D0h+var_88], r13
0x1800445da  lea     rax, [rbp+57h+var_6C]
0x1800445de  mov     [rsp+0D0h+var_90], r13
0x1800445e3  xor     r8d, r8d
0x1800445e6  mov     [rsp+0D0h+var_98], r13
0x1800445eb  mov     edx, 48000016h
0x1800445f0  mov     [rsp+0D0h+var_A0], rax
0x1800445f5  mov     rcx, r14
0x1800445f8  lea     rax, [rbp+57h+var_58]
0x1800445fc  mov     [rsp+0D0h+var_A8], 28h ; '('
0x180044604  mov     [rsp+0D0h+var_B0], rax
0x180044609  mov     rax, [rsi+0C0h]
0x180044610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044615  cmp     eax, r15d
0x180044618  jnz     loc_1800446BE
0x18004461e  cmp     [rbp+57h+var_70], 271Eh
0x180044625  jnz     loc_180044790
0x18004462b  mov     r8d, [rbp+57h+var_6C]
0x18004462f  xor     edx, edx
0x180044631  mov     rcx, cs:SockPrivateHeap
0x180044638  mov     rax, cs:SockAllocateHeapRoutine
0x18004463f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044644  mov     rbx, rax
0x180044647  test    rax, rax
0x18004464a  jnz     short loc_18004465C
0x18004464c  mov     [rbp+57h+var_70], 8
0x180044653  mov     [rdi+18h], r15
0x180044657  jmp     loc_1800447BA
0x18004465c  mov     ecx, [rbp+57h+var_6C]
0x18004465f  lea     rax, [rbp+57h+var_70]
0x180044663  mov     [rsp+0D0h+var_80], rax
0x180044668  xor     r9d, r9d
0x18004466b  mov     [rsp+0D0h+var_88], r13
0x180044670  lea     rax, [rbp+57h+var_6C]
0x180044674  mov     [rsp+0D0h+var_90], r13
0x180044679  xor     r8d, r8d
0x18004467c  mov     [rsp+0D0h+var_98], r13
0x180044681  mov     edx, 48000016h
0x180044686  mov     [rsp+0D0h+var_A0], rax
0x18004468b  mov     rax, [rsi+0C0h]
0x180044692  mov     [rsp+0D0h+var_A8], ecx
0x180044696  mov     rcx, r14
0x180044699  mov     [rsp+0D0h+var_B0], rbx
0x18004469e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800446a3  cmp     eax, r15d
0x1800446a6  jnz     short loc_1800446BE
0x1800446a8  cmp     [rbp+57h+var_70], r13d
0x1800446ac  jnz     short loc_1800446B5
0x1800446ae  mov     [rbp+57h+var_70], 277Bh
0x1800446b5  mov     [rdi+18h], r15
0x1800446b9  jmp     loc_180044799
0x1800446be  mov     r8d, r13d
0x1800446c1  cmp     [rbx], r13d
0x1800446c4  jle     loc_180044785
0x1800446ca  mov     r15d, cs:SockSanSubnetCount
0x1800446d1  mov     edi, 2
0x1800446d6  mov     r11, cs:SockSanSubnetMap
0x1800446dd  mov     r10, cs:SockSanV6AddressMap
0x1800446e4  lea     r14d, [rdi+15h]
0x1800446e8  movsxd  rax, r8d
0x1800446eb  add     rax, rax
0x1800446ee  mov     r9, [rbx+rax*8+8]
0x1800446f3  cmp     [r9], di
0x1800446f7  jnz     short loc_18004472A
0x1800446f9  mov     edx, r13d
0x1800446fc  test    r15d, r15d
0x1800446ff  jz      short loc_18004476D
0x180044701  mov     eax, edx
0x180044703  lea     rcx, [rax+rax*2]
0x180044707  add     rcx, rcx
0x18004470a  mov     eax, [r11+rcx*8+4]
0x18004470f  cmp     [r9+4], eax
0x180044713  jnz     short loc_180044721
0x180044715  cmp     [r11+rcx*8+28h], r13
0x18004471a  jnz     short loc_180044721
0x18004471c  mov     [r11+rcx*8+28h], rsi
0x180044721  inc     edx
0x180044723  cmp     edx, r15d
0x180044726  jb      short loc_180044701
0x180044728  jmp     short loc_18004476D
0x18004472a  cmp     [r9], r14w
0x18004472e  jnz     short loc_18004476D
0x180044730  cmp     cs:SockSanV6AddressCount, r13d
0x180044737  mov     edx, r13d
0x18004473a  jbe     short loc_18004476D
0x18004473c  mov     eax, edx
0x18004473e  lea     rcx, [rax+rax*2]
0x180044742  mov     rax, [r10+rcx*8+8]
0x180044747  cmp     [r9+10h], rax
0x18004474b  jnz     short loc_180044763
0x18004474d  mov     rax, [r10+rcx*8]
0x180044751  cmp     [r9+8], rax
0x180044755  jnz     short loc_180044763
0x180044757  cmp     [r10+rcx*8+10h], r13
0x18004475c  jnz     short loc_180044763
0x18004475e  mov     [r10+rcx*8+10h], rsi
0x180044763  inc     edx
0x180044765  cmp     edx, cs:SockSanV6AddressCount
0x18004476b  jb      short loc_18004473C
0x18004476d  inc     r8d
0x180044770  cmp     r8d, [rbx]
0x180044773  jl      loc_1800446E8
0x180044779  mov     rdi, [rbp+57h+var_68]
0x18004477d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180044781  mov     r14, [rbp+57h+var_60]
0x180044785  mov     rdx, r14
0x180044788  mov     rcx, rsi
0x18004478b  call    SockpSanGetRdmaParameters
0x180044790  mov     [rdi+18h], r15
0x180044794  test    rbx, rbx
0x180044797  jz      short loc_1800447BA
0x180044799  lea     rax, [rbp+57h+var_58]
0x18004479d  cmp     rbx, rax
0x1800447a0  jz      short loc_1800447BA
0x1800447a2  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800447a9  mov     r8, rbx; P
0x1800447ac  xor     edx, edx; Flags
0x1800447ae  call    cs:__imp_RtlFreeHeap
0x1800447b5  nop     dword ptr [rax+rax+00h]
0x1800447ba  mov     rax, [rsi+70h]
0x1800447be  lea     rdx, [rbp+57h+var_68]
0x1800447c2  mov     rcx, r14
0x1800447c5  mov     dword ptr [rbp+57h+var_68], r13d
0x1800447c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800447ce  mov     eax, [rbp+57h+var_70]
0x1800447d1  mov     rcx, [rbp+57h+var_30]
0x1800447d5  xor     rcx, rsp; StackCookie
0x1800447d8  call    __security_check_cookie
0x1800447dd  lea     r11, [rsp+0D0h+var_20]
0x1800447e5  mov     rbx, [r11+38h]
0x1800447e9  mov     rsi, [r11+40h]
0x1800447ed  mov     rsp, r11
0x1800447f0  pop     r15
0x1800447f2  pop     r14
0x1800447f4  pop     r13
0x1800447f6  pop     rdi
0x1800447f7  pop     rbp
0x1800447f8  retn
```
