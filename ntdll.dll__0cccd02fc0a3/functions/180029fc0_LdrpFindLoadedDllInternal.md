# LdrpFindLoadedDllInternal

- ea: `0x180029fc0`
- end: `0x18002a2fe`
- name: `LdrpFindLoadedDllInternal`
- size: `830`
- prototype: `__int64 __usercall@<rax>(char ArgList@<cl>, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, service_task`

## callers

- `0x18002631c`
- `0x18002c970`

## callees

- `0x18001d490`
- `0x18001eb80`
- `0x180027b80`
- `0x180029fc0`
- `0x18002a3b8`
- `0x18002b47c`
- `0x18004cef8`
- `0x1800526f0`
- `0x180052720`
- `0x180053150`
- `0x180053dd0`
- `0x180053e34`
- `0x180053f30`
- `0x1800be6e0`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x18002a0ef`: `LdrpFindLoadedDllInternal`
- `0x18002a11e`: `LdrpFindLoadedDllInternal`

## pseudocode

```c
__int64 __fastcall LdrpFindLoadedDllInternal(__m128i *ArgList, __int64 a2, __int64 a3, _DWORD *a4, int a5)
{
  int v9; // edi
  __int64 v10; // rdx
  int LoadedDllByNameLockHeld; // r13d
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // edi
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rcx
  int v22; // eax
  char *v23; // rcx
  int v24; // r9d
  __int64 v25[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26[2]; // [rsp+60h] [rbp-A0h] BYREF
  __m128i v27; // [rsp+70h] [rbp-90h] BYREF
  _WORD v28[128]; // [rsp+80h] [rbp-80h] BYREF

  *(_OWORD *)v25 = 0;
  memset_thunk_772440563353939046(&v27, 0, 0x110u);
  *(_QWORD *)a3 = 0;
  if ( (a5 & 0x20) != 0 )
  {
    *(_OWORD *)v25 = 0;
    if ( !ArgList )
    {
      LdrpGetBaseNameFromFullName(0, v25);
      ArgList = (__m128i *)v25;
    }
    v9 = LdrpHashUnicodeString(ArgList);
    RtlAcquireSRWLockShared(&LdrpModuleDatatableLock);
    LoadedDllByNameLockHeld = LdrpFindLoadedDllByNameLockHeld((_DWORD)ArgList, 0, a5, a3, v9);
    if ( LoadedDllByNameLockHeld < 0 )
    {
      RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v10);
      v16 = 0;
    }
    else
    {
      if ( a4 )
        *a4 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 152LL) + 56LL);
      RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v10);
      v16 = 1;
    }
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v13, v12, v14, v15) )
      v20 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v20 = 2147353476;
    if ( *(_BYTE *)v20 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
    {
      v23 = (unsigned int)RtlGetCurrentServiceSessionId(v20, v17, v18, v19)
          ? (char *)NtCurrentPeb()->SharedData + 555
          : (char *)2147353477;
      if ( (*v23 & 0x20) != 0 )
      {
        v24 = 0;
        if ( !v16 )
          v24 = 3;
        LdrpLogEtwEvent(5280, 0, 0, v24, (__int64)ArgList, 0);
      }
    }
  }
  else if ( (a5 & 0x200) == 0
         || (LoadedDllByNameLockHeld = LdrpFindLoadedDllByName(0, (_DWORD)ArgList, a5, a3, (__int64)a4),
             LoadedDllByNameLockHeld < 0) )
  {
    v27.m128i_i32[0] = 0x1000000;
    v27.m128i_i64[1] = (__int64)v28;
    v28[0] = 0;
    *(_OWORD *)v26 = 0;
    if ( (a5 & 0x200) != 0 )
      v22 = LdrpResolveDllName(ArgList, &v27, (__int64)v25, v26, a5);
    else
      v22 = LdrpSearchPath((unsigned __int16 *)ArgList, a2, 0, 0, &v27, (__int64)v25, (unsigned __int16 *)v26, 0, 0);
    LoadedDllByNameLockHeld = v22;
    if ( v22 >= 0 )
    {
      LoadedDllByNameLockHeld = LdrpFindLoadedDllByName((unsigned int)v25, (unsigned int)v26, a5, a3, (__int64)a4);
      if ( LoadedDllByNameLockHeld == -1073741515 )
        LoadedDllByNameLockHeld = LdrpFindLoadedDllByMappingFile(&v27, a3, a4);
    }
    if ( v26[1] )
      RtlpSysVolFree(v26[1]);
    if ( v28 != (_WORD *)v27.m128i_i64[1] )
      RtlpSysVolFree(v27.m128i_i64[1]);
    v27.m128i_i32[0] = 0x1000000;
    v27.m128i_i64[1] = (__int64)v28;
    v28[0] = 0;
  }
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrfind.c",
    482,
    (int)"LdrpFindLoadedDllInternal",
    4,
    "Status: 0x%08lx\n",
    LoadedDllByNameLockHeld);
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrfind.c",
    483,
    (int)"LdrpFindLoadedDllInternal",
    6,
    "%x\n",
    LoadedDllByNameLockHeld);
  return (unsigned int)LoadedDllByNameLockHeld;
}

```

## disassembly

```asm
0x180029fc0  push    rbp
0x180029fc2  push    rbx
0x180029fc3  push    rsi
0x180029fc4  push    rdi
0x180029fc5  push    r12
0x180029fc7  push    r13
0x180029fc9  push    r14
0x180029fcb  push    r15
0x180029fcd  lea     rbp, [rsp-98h]
0x180029fd5  sub     rsp, 198h
0x180029fdc  mov     rax, cs:__security_cookie
0x180029fe3  xor     rax, rsp
0x180029fe6  mov     [rbp+0D0h+var_50], rax
0x180029fed  mov     r15, r8
0x180029ff0  mov     rdi, rdx
0x180029ff3  mov     rbx, rcx
0x180029ff6  xorps   xmm0, xmm0
0x180029ff9  xor     edx, edx; Val
0x180029ffb  lea     rcx, [rsp+1D0h+var_160]; void *
0x18002a000  mov     r8d, 110h; Size
0x18002a006  mov     r14, r9
0x18002a009  movups  xmmword ptr [rsp+1D0h+var_180], xmm0
0x18002a00e  call    memset$thunk$772440563353939046
0x18002a013  mov     r12d, [rbp+0D0h+arg_20]
0x18002a01a  mov     qword ptr [r15], 0
0x18002a021  test    r12b, 20h
0x18002a025  jz      loc_18002A15D
0x18002a02b  xorps   xmm0, xmm0
0x18002a02e  movups  xmmword ptr [rsp+1D0h+var_180], xmm0
0x18002a033  test    rbx, rbx
0x18002a036  jnz     short loc_18002A049
0x18002a038  lea     rdx, [rsp+1D0h+var_180]
0x18002a03d  xor     ecx, ecx
0x18002a03f  call    LdrpGetBaseNameFromFullName
0x18002a044  lea     rbx, [rsp+1D0h+var_180]
0x18002a049  mov     rcx, rbx
0x18002a04c  call    LdrpHashUnicodeString
0x18002a051  lea     rsi, LdrpModuleDatatableLock
0x18002a058  mov     edi, eax
0x18002a05a  mov     rcx, rsi
0x18002a05d  call    RtlAcquireSRWLockShared
0x18002a062  mov     r9, r15
0x18002a065  mov     dword ptr [rsp+1D0h+Format], edi
0x18002a069  mov     r8d, r12d
0x18002a06c  xor     edx, edx
0x18002a06e  mov     rcx, rbx
0x18002a071  call    LdrpFindLoadedDllByNameLockHeld
0x18002a076  mov     r13d, eax
0x18002a079  test    eax, eax
0x18002a07b  js      short loc_18002A0A1
0x18002a07d  test    r14, r14
0x18002a080  jz      short loc_18002A092
0x18002a082  mov     rax, [r15]
0x18002a085  mov     rcx, [rax+98h]
0x18002a08c  mov     eax, [rcx+38h]
0x18002a08f  mov     [r14], eax
0x18002a092  mov     rcx, rsi
0x18002a095  call    RtlReleaseSRWLockShared
0x18002a09a  mov     edi, 1
0x18002a09f  jmp     short loc_18002A0AB
0x18002a0a1  mov     rcx, rsi
0x18002a0a4  call    RtlReleaseSRWLockShared
0x18002a0a9  xor     edi, edi
0x18002a0ab  call    RtlGetCurrentServiceSessionId
0x18002a0b0  test    eax, eax
0x18002a0b2  jnz     loc_18002A2A0
0x18002a0b8  mov     ecx, 7FFE0384h
0x18002a0bd  cmp     byte ptr [rcx], 0
0x18002a0c0  jz      short loc_18002A0D8
0x18002a0c2  mov     rax, gs:60h
0x18002a0cb  test    byte ptr [rax+378h], 4
0x18002a0d2  jnz     loc_18002A247
0x18002a0d8  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x18002a0df  mov     dword ptr [rsp+1D0h+ArgList], r13d; ArgList
0x18002a0e4  mov     r9d, 4; int
0x18002a0ea  mov     [rsp+1D0h+Format], rax; Format
0x18002a0ef  lea     r8, aLdrpfindloaded; "LdrpFindLoadedDllInternal"
0x18002a0f6  mov     edx, 1E2h; int
0x18002a0fb  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x18002a102  call    LdrpLogInternal
0x18002a107  lea     rax, asc_180175AB4; "%x\n"
0x18002a10e  mov     dword ptr [rsp+1D0h+ArgList], r13d; ArgList
0x18002a113  mov     r9d, 6; int
0x18002a119  mov     [rsp+1D0h+Format], rax; Format
0x18002a11e  lea     r8, aLdrpfindloaded; "LdrpFindLoadedDllInternal"
0x18002a125  mov     edx, 1E3h; int
0x18002a12a  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x18002a131  call    LdrpLogInternal
0x18002a136  mov     eax, r13d
0x18002a139  mov     rcx, [rbp+0D0h+var_50]
0x18002a140  xor     rcx, rsp; StackCookie
0x18002a143  call    __security_check_cookie
0x18002a148  add     rsp, 198h
0x18002a14f  pop     r15
0x18002a151  pop     r14
0x18002a153  pop     r13
0x18002a155  pop     r12
0x18002a157  pop     rdi
0x18002a158  pop     rsi
0x18002a159  pop     rbx
0x18002a15a  pop     rbp
0x18002a15b  retn
0x18002a15d  mov     esi, r12d
0x18002a160  and     esi, 200h
0x18002a166  jz      short loc_18002A188
0x18002a168  mov     r9, r15
0x18002a16b  mov     [rsp+1D0h+Format], r14
0x18002a170  mov     r8d, r12d
0x18002a173  mov     rdx, rbx
0x18002a176  xor     ecx, ecx
0x18002a178  call    LdrpFindLoadedDllByName
0x18002a17d  mov     r13d, eax
0x18002a180  test    eax, eax
0x18002a182  jns     loc_18002A0D8
0x18002a188  lea     rax, [rbp+0D0h+var_150]
0x18002a18c  mov     dword ptr [rsp+1D0h+var_160], 1000000h
0x18002a194  mov     [rsp+1D0h+var_158], rax
0x18002a199  xorps   xmm0, xmm0
0x18002a19c  xor     eax, eax
0x18002a19e  mov     rcx, rbx; ArgList
0x18002a1a1  mov     [rbp+0D0h+var_150], ax
0x18002a1a5  movups  xmmword ptr [rsp+1D0h+var_170], xmm0
0x18002a1aa  test    esi, esi
0x18002a1ac  jz      loc_18002A2C3
0x18002a1b2  lea     r9, [rsp+1D0h+var_170]
0x18002a1b7  mov     dword ptr [rsp+1D0h+Format], r12d; int
0x18002a1bc  lea     r8, [rsp+1D0h+var_180]
0x18002a1c1  lea     rdx, [rsp+1D0h+var_160]
0x18002a1c6  call    LdrpResolveDllName
0x18002a1cb  mov     r13d, eax
0x18002a1ce  test    eax, eax
0x18002a1d0  js      short loc_18002A209
0x18002a1d2  mov     r9, r15
0x18002a1d5  mov     [rsp+1D0h+Format], r14
0x18002a1da  mov     r8d, r12d
0x18002a1dd  lea     rdx, [rsp+1D0h+var_170]
0x18002a1e2  lea     rcx, [rsp+1D0h+var_180]
0x18002a1e7  call    LdrpFindLoadedDllByName
0x18002a1ec  mov     r13d, eax
0x18002a1ef  cmp     eax, 0C0000135h
0x18002a1f4  jnz     short loc_18002A209
0x18002a1f6  mov     r8, r14
0x18002a1f9  lea     rcx, [rsp+1D0h+var_160]
0x18002a1fe  mov     rdx, r15
0x18002a201  call    LdrpFindLoadedDllByMappingFile
0x18002a206  mov     r13d, eax
0x18002a209  mov     rcx, [rsp+1D0h+var_170+8]
0x18002a20e  test    rcx, rcx
0x18002a211  jz      short loc_18002A218
0x18002a213  call    RtlpSysVolFree
0x18002a218  mov     rcx, [rsp+1D0h+var_158]
0x18002a21d  lea     rax, [rbp+0D0h+var_150]
0x18002a221  cmp     rax, rcx
0x18002a224  jz      short loc_18002A22B
0x18002a226  call    RtlpSysVolFree
0x18002a22b  lea     rax, [rbp+0D0h+var_150]
0x18002a22f  mov     dword ptr [rsp+1D0h+var_160], 1000000h
0x18002a237  mov     [rsp+1D0h+var_158], rax
0x18002a23c  xor     eax, eax
0x18002a23e  mov     [rbp+0D0h+var_150], ax
0x18002a242  jmp     loc_18002A0D8
0x18002a247  call    RtlGetCurrentServiceSessionId
0x18002a24c  test    eax, eax
0x18002a24e  jz      short loc_18002A2BC
0x18002a250  mov     rax, gs:60h
0x18002a259  mov     rcx, [rax+90h]
0x18002a260  add     rcx, 22Bh
0x18002a267  test    byte ptr [rcx], 20h
0x18002a26a  jz      loc_18002A0D8
0x18002a270  xor     r9d, r9d
0x18002a273  mov     qword ptr [rsp+1D0h+ArgList], 0
0x18002a27c  test    edi, edi
0x18002a27e  mov     [rsp+1D0h+Format], rbx
0x18002a283  mov     eax, 3
0x18002a288  mov     ecx, 14A0h
0x18002a28d  cmovz   r9d, eax
0x18002a291  xor     r8d, r8d
0x18002a294  xor     edx, edx
0x18002a296  call    LdrpLogEtwEvent
0x18002a29b  jmp     loc_18002A0D8
0x18002a2a0  mov     rax, gs:60h
0x18002a2a9  mov     rcx, [rax+90h]
0x18002a2b0  add     rcx, 22Ah
0x18002a2b7  jmp     loc_18002A0BD
0x18002a2bc  mov     ecx, 7FFE0385h
0x18002a2c1  jmp     short loc_18002A267
0x18002a2c3  mov     [rsp+1D0h+var_190], rax; __int64
0x18002a2c8  xor     r9d, r9d
0x18002a2cb  mov     [rsp+1D0h+var_198], rax; __int64
0x18002a2d0  xor     r8d, r8d
0x18002a2d3  lea     rax, [rsp+1D0h+var_170]
0x18002a2d8  mov     rdx, rdi
0x18002a2db  mov     [rsp+1D0h+var_1A0], rax; __int64
0x18002a2e0  lea     rax, [rsp+1D0h+var_180]
0x18002a2e5  mov     qword ptr [rsp+1D0h+ArgList], rax; __int64
0x18002a2ea  lea     rax, [rsp+1D0h+var_160]
0x18002a2ef  mov     [rsp+1D0h+Format], rax; __int64
0x18002a2f4  call    LdrpSearchPath
0x18002a2f9  jmp     loc_18002A1CB
```
