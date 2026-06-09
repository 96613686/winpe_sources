# LdrpFindLoadedDllInternal

- ea: `0x180029eb0`
- end: `0x18002a1ee`
- name: `LdrpFindLoadedDllInternal`
- size: `830`
- prototype: `__int64 __usercall@<rax>(char ArgList@<cl>, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, service_task`

## callers

- `0x18002630c`
- `0x18002bc70`

## callees

- `0x18001d490`
- `0x18001eb80`
- `0x180027a70`
- `0x180029eb0`
- `0x18002a2a8`
- `0x18002a770`
- `0x180069af8`
- `0x18006f0d0`
- `0x18006f100`
- `0x18006fb30`
- `0x1800707b0`
- `0x180070814`
- `0x180070910`
- `0x1800c29c0`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x180029fdf`: `LdrpFindLoadedDllInternal`
- `0x18002a00e`: `LdrpFindLoadedDllInternal`

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
    RtlAcquireSRWLockShared(LdrpModuleDatatableLock);
    LoadedDllByNameLockHeld = LdrpFindLoadedDllByNameLockHeld((_DWORD)ArgList, 0, a5, a3, v9);
    if ( LoadedDllByNameLockHeld < 0 )
    {
      RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v10);
      v16 = 0;
    }
    else
    {
      if ( a4 )
        *a4 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 152LL) + 56LL);
      RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v10);
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
0x180029eb0  push    rbp
0x180029eb2  push    rbx
0x180029eb3  push    rsi
0x180029eb4  push    rdi
0x180029eb5  push    r12
0x180029eb7  push    r13
0x180029eb9  push    r14
0x180029ebb  push    r15
0x180029ebd  lea     rbp, [rsp-98h]
0x180029ec5  sub     rsp, 198h
0x180029ecc  mov     rax, cs:__security_cookie
0x180029ed3  xor     rax, rsp
0x180029ed6  mov     [rbp+0D0h+var_50], rax
0x180029edd  mov     r15, r8
0x180029ee0  mov     rdi, rdx
0x180029ee3  mov     rbx, rcx
0x180029ee6  xorps   xmm0, xmm0
0x180029ee9  xor     edx, edx; Val
0x180029eeb  lea     rcx, [rsp+1D0h+var_160]; void *
0x180029ef0  mov     r8d, 110h; Size
0x180029ef6  mov     r14, r9
0x180029ef9  movups  xmmword ptr [rsp+1D0h+var_180], xmm0
0x180029efe  call    memset$thunk$772440563353939046
0x180029f03  mov     r12d, [rbp+0D0h+arg_20]
0x180029f0a  mov     qword ptr [r15], 0
0x180029f11  test    r12b, 20h
0x180029f15  jz      loc_18002A04D
0x180029f1b  xorps   xmm0, xmm0
0x180029f1e  movups  xmmword ptr [rsp+1D0h+var_180], xmm0
0x180029f23  test    rbx, rbx
0x180029f26  jnz     short loc_180029F39
0x180029f28  lea     rdx, [rsp+1D0h+var_180]
0x180029f2d  xor     ecx, ecx
0x180029f2f  call    LdrpGetBaseNameFromFullName
0x180029f34  lea     rbx, [rsp+1D0h+var_180]
0x180029f39  mov     rcx, rbx
0x180029f3c  call    LdrpHashUnicodeString
0x180029f41  lea     rsi, LdrpModuleDatatableLock
0x180029f48  mov     edi, eax
0x180029f4a  mov     rcx, rsi
0x180029f4d  call    RtlAcquireSRWLockShared
0x180029f52  mov     r9, r15
0x180029f55  mov     dword ptr [rsp+1D0h+Format], edi
0x180029f59  mov     r8d, r12d
0x180029f5c  xor     edx, edx
0x180029f5e  mov     rcx, rbx
0x180029f61  call    LdrpFindLoadedDllByNameLockHeld
0x180029f66  mov     r13d, eax
0x180029f69  test    eax, eax
0x180029f6b  js      short loc_180029F91
0x180029f6d  test    r14, r14
0x180029f70  jz      short loc_180029F82
0x180029f72  mov     rax, [r15]
0x180029f75  mov     rcx, [rax+98h]
0x180029f7c  mov     eax, [rcx+38h]
0x180029f7f  mov     [r14], eax
0x180029f82  mov     rcx, rsi
0x180029f85  call    RtlReleaseSRWLockShared
0x180029f8a  mov     edi, 1
0x180029f8f  jmp     short loc_180029F9B
0x180029f91  mov     rcx, rsi
0x180029f94  call    RtlReleaseSRWLockShared
0x180029f99  xor     edi, edi
0x180029f9b  call    RtlGetCurrentServiceSessionId
0x180029fa0  test    eax, eax
0x180029fa2  jnz     loc_18002A190
0x180029fa8  mov     ecx, 7FFE0384h
0x180029fad  cmp     byte ptr [rcx], 0
0x180029fb0  jz      short loc_180029FC8
0x180029fb2  mov     rax, gs:60h
0x180029fbb  test    byte ptr [rax+378h], 4
0x180029fc2  jnz     loc_18002A137
0x180029fc8  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x180029fcf  mov     dword ptr [rsp+1D0h+ArgList], r13d; ArgList
0x180029fd4  mov     r9d, 4; int
0x180029fda  mov     [rsp+1D0h+Format], rax; Format
0x180029fdf  lea     r8, aLdrpfindloaded; "LdrpFindLoadedDllInternal"
0x180029fe6  mov     edx, 1E2h; int
0x180029feb  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x180029ff2  call    LdrpLogInternal
0x180029ff7  lea     rax, asc_180175AB4; "%x\n"
0x180029ffe  mov     dword ptr [rsp+1D0h+ArgList], r13d; ArgList
0x18002a003  mov     r9d, 6; int
0x18002a009  mov     [rsp+1D0h+Format], rax; Format
0x18002a00e  lea     r8, aLdrpfindloaded; "LdrpFindLoadedDllInternal"
0x18002a015  mov     edx, 1E3h; int
0x18002a01a  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x18002a021  call    LdrpLogInternal
0x18002a026  mov     eax, r13d
0x18002a029  mov     rcx, [rbp+0D0h+var_50]
0x18002a030  xor     rcx, rsp; StackCookie
0x18002a033  call    __security_check_cookie
0x18002a038  add     rsp, 198h
0x18002a03f  pop     r15
0x18002a041  pop     r14
0x18002a043  pop     r13
0x18002a045  pop     r12
0x18002a047  pop     rdi
0x18002a048  pop     rsi
0x18002a049  pop     rbx
0x18002a04a  pop     rbp
0x18002a04b  retn
0x18002a04d  mov     esi, r12d
0x18002a050  and     esi, 200h
0x18002a056  jz      short loc_18002A078
0x18002a058  mov     r9, r15
0x18002a05b  mov     [rsp+1D0h+Format], r14
0x18002a060  mov     r8d, r12d
0x18002a063  mov     rdx, rbx
0x18002a066  xor     ecx, ecx
0x18002a068  call    LdrpFindLoadedDllByName
0x18002a06d  mov     r13d, eax
0x18002a070  test    eax, eax
0x18002a072  jns     loc_180029FC8
0x18002a078  lea     rax, [rbp+0D0h+var_150]
0x18002a07c  mov     dword ptr [rsp+1D0h+var_160], 1000000h
0x18002a084  mov     [rsp+1D0h+var_158], rax
0x18002a089  xorps   xmm0, xmm0
0x18002a08c  xor     eax, eax
0x18002a08e  mov     rcx, rbx; ArgList
0x18002a091  mov     [rbp+0D0h+var_150], ax
0x18002a095  movups  xmmword ptr [rsp+1D0h+var_170], xmm0
0x18002a09a  test    esi, esi
0x18002a09c  jz      loc_18002A1B3
0x18002a0a2  lea     r9, [rsp+1D0h+var_170]
0x18002a0a7  mov     dword ptr [rsp+1D0h+Format], r12d; int
0x18002a0ac  lea     r8, [rsp+1D0h+var_180]
0x18002a0b1  lea     rdx, [rsp+1D0h+var_160]
0x18002a0b6  call    LdrpResolveDllName
0x18002a0bb  mov     r13d, eax
0x18002a0be  test    eax, eax
0x18002a0c0  js      short loc_18002A0F9
0x18002a0c2  mov     r9, r15
0x18002a0c5  mov     [rsp+1D0h+Format], r14
0x18002a0ca  mov     r8d, r12d
0x18002a0cd  lea     rdx, [rsp+1D0h+var_170]
0x18002a0d2  lea     rcx, [rsp+1D0h+var_180]
0x18002a0d7  call    LdrpFindLoadedDllByName
0x18002a0dc  mov     r13d, eax
0x18002a0df  cmp     eax, 0C0000135h
0x18002a0e4  jnz     short loc_18002A0F9
0x18002a0e6  mov     r8, r14
0x18002a0e9  lea     rcx, [rsp+1D0h+var_160]
0x18002a0ee  mov     rdx, r15
0x18002a0f1  call    LdrpFindLoadedDllByMappingFile
0x18002a0f6  mov     r13d, eax
0x18002a0f9  mov     rcx, [rsp+1D0h+var_170+8]
0x18002a0fe  test    rcx, rcx
0x18002a101  jz      short loc_18002A108
0x18002a103  call    RtlpSysVolFree
0x18002a108  mov     rcx, [rsp+1D0h+var_158]
0x18002a10d  lea     rax, [rbp+0D0h+var_150]
0x18002a111  cmp     rax, rcx
0x18002a114  jz      short loc_18002A11B
0x18002a116  call    RtlpSysVolFree
0x18002a11b  lea     rax, [rbp+0D0h+var_150]
0x18002a11f  mov     dword ptr [rsp+1D0h+var_160], 1000000h
0x18002a127  mov     [rsp+1D0h+var_158], rax
0x18002a12c  xor     eax, eax
0x18002a12e  mov     [rbp+0D0h+var_150], ax
0x18002a132  jmp     loc_180029FC8
0x18002a137  call    RtlGetCurrentServiceSessionId
0x18002a13c  test    eax, eax
0x18002a13e  jz      short loc_18002A1AC
0x18002a140  mov     rax, gs:60h
0x18002a149  mov     rcx, [rax+90h]
0x18002a150  add     rcx, 22Bh
0x18002a157  test    byte ptr [rcx], 20h
0x18002a15a  jz      loc_180029FC8
0x18002a160  xor     r9d, r9d
0x18002a163  mov     qword ptr [rsp+1D0h+ArgList], 0
0x18002a16c  test    edi, edi
0x18002a16e  mov     [rsp+1D0h+Format], rbx
0x18002a173  mov     eax, 3
0x18002a178  mov     ecx, 14A0h
0x18002a17d  cmovz   r9d, eax
0x18002a181  xor     r8d, r8d
0x18002a184  xor     edx, edx
0x18002a186  call    LdrpLogEtwEvent
0x18002a18b  jmp     loc_180029FC8
0x18002a190  mov     rax, gs:60h
0x18002a199  mov     rcx, [rax+90h]
0x18002a1a0  add     rcx, 22Ah
0x18002a1a7  jmp     loc_180029FAD
0x18002a1ac  mov     ecx, 7FFE0385h
0x18002a1b1  jmp     short loc_18002A157
0x18002a1b3  mov     [rsp+1D0h+var_190], rax; __int64
0x18002a1b8  xor     r9d, r9d
0x18002a1bb  mov     [rsp+1D0h+var_198], rax; __int64
0x18002a1c0  xor     r8d, r8d
0x18002a1c3  lea     rax, [rsp+1D0h+var_170]
0x18002a1c8  mov     rdx, rdi
0x18002a1cb  mov     [rsp+1D0h+var_1A0], rax; __int64
0x18002a1d0  lea     rax, [rsp+1D0h+var_180]
0x18002a1d5  mov     qword ptr [rsp+1D0h+ArgList], rax; __int64
0x18002a1da  lea     rax, [rsp+1D0h+var_160]
0x18002a1df  mov     [rsp+1D0h+Format], rax; __int64
0x18002a1e4  call    LdrpSearchPath
0x18002a1e9  jmp     loc_18002A0BB
```
