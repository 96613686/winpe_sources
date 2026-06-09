# LdrpComputeLazyDllPath

- ea: `0x1800bf2dc`
- end: `0x1800bf418`
- name: `LdrpComputeLazyDllPath`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800be6e0`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x18001eb80`
- `0x18002b870`
- `0x1800bf2dc`

## string_xrefs

- `0x1800bf362`: `LdrpComputeLazyDllPath`
- `0x1800bf3a8`: `DLL search path computed: %ws\n`
- `0x1800bf3ce`: `Lazy DLL search path computation failed with status: 0x%08lx.\n`
- `0x1800bf3fb`: `Packaged DLL search path computed. Package Dirs: %ws, DllPath: %ws\n`

## pseudocode

```c
__int64 __fastcall LdrpComputeLazyDllPath(__int64 a1)
{
  unsigned int v2; // edi
  int DllPath; // eax
  __int64 ArgList; // rax
  __int64 v6; // rcx
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF

  v7 = 0;
  v9 = 0;
  v8 = 0;
  v2 = 0;
  RtlAcquireSRWLockExclusive(&LdrpPathLock);
  if ( !*(_QWORD *)a1 )
  {
    DllPath = LdrpGetDllPath(
                *(_QWORD *)(a1 + 32),
                *(_DWORD *)(a1 + 24),
                (unsigned int)&v9,
                (unsigned int)&v7,
                a1 + 120,
                a1 + 40,
                (__int64)&v8);
    v2 = DllPath;
    if ( DllPath < 0 )
    {
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrutil.c",
        1588,
        (int)"LdrpComputeLazyDllPath",
        0,
        "Lazy DLL search path computation failed with status: 0x%08lx.\n",
        DllPath);
    }
    else
    {
      *(_QWORD *)(a1 + 8) = v7;
      *(_QWORD *)(a1 + 16) = v8;
      ArgList = v9;
      *(_BYTE *)(a1 + 124) = 1;
      *(_QWORD *)a1 = ArgList;
      v6 = *(_QWORD *)(a1 + 16);
      if ( v6 )
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrutil.c",
          1613,
          (int)"LdrpComputeLazyDllPath",
          2,
          "Packaged DLL search path computed. Package Dirs: %ws, DllPath: %ws\n",
          v6);
      else
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrutil.c",
          1607,
          (int)"LdrpComputeLazyDllPath",
          2,
          "DLL search path computed: %ws\n",
          ArgList);
    }
  }
  RtlReleaseSRWLockExclusive(&LdrpPathLock);
  return v2;
}

```

## disassembly

```asm
0x1800bf2dc  mov     rax, rsp
0x1800bf2df  mov     [rax+20h], rbx
0x1800bf2e3  push    rdi
0x1800bf2e4  sub     rsp, 40h
0x1800bf2e8  mov     rbx, rcx
0x1800bf2eb  mov     qword ptr [rax+8], 0
0x1800bf2f3  lea     rcx, LdrpPathLock
0x1800bf2fa  mov     qword ptr [rax+18h], 0
0x1800bf302  mov     qword ptr [rax+10h], 0
0x1800bf30a  xor     edi, edi
0x1800bf30c  call    RtlAcquireSRWLockExclusive
0x1800bf311  cmp     [rbx], rdi
0x1800bf314  jz      short loc_1800BF330
0x1800bf316  lea     rcx, LdrpPathLock
0x1800bf31d  call    RtlReleaseSRWLockExclusive
0x1800bf322  mov     rbx, [rsp+48h+arg_18]
0x1800bf327  mov     eax, edi
0x1800bf329  add     rsp, 40h
0x1800bf32d  pop     rdi
0x1800bf32e  retn
0x1800bf330  lea     rdx, [rbx+78h]
0x1800bf334  lea     rcx, [rsp+48h+arg_8]
0x1800bf339  mov     [rsp+48h+var_18], rcx
0x1800bf33e  lea     rax, [rbx+28h]
0x1800bf342  mov     rcx, [rbx+20h]
0x1800bf346  lea     r9, [rsp+48h+arg_0]
0x1800bf34b  mov     qword ptr [rsp+48h+ArgList], rax
0x1800bf350  lea     r8, [rsp+48h+arg_10]
0x1800bf355  mov     [rsp+48h+Format], rdx
0x1800bf35a  mov     edx, [rbx+18h]
0x1800bf35d  call    LdrpGetDllPath
0x1800bf362  lea     r8, aLdrpcomputelaz; "LdrpComputeLazyDllPath"
0x1800bf369  mov     edi, eax
0x1800bf36b  test    eax, eax
0x1800bf36d  js      short loc_1800BF3C3
0x1800bf36f  mov     rax, [rsp+48h+arg_0]
0x1800bf374  mov     r9d, 2; int
0x1800bf37a  mov     [rbx+8], rax
0x1800bf37e  mov     rax, [rsp+48h+arg_8]
0x1800bf383  mov     [rbx+10h], rax
0x1800bf387  mov     rax, [rsp+48h+arg_10]
0x1800bf38c  mov     byte ptr [rbx+7Ch], 1
0x1800bf390  mov     [rbx], rax
0x1800bf393  mov     rcx, [rbx+10h]
0x1800bf397  test    rcx, rcx
0x1800bf39a  jnz     short loc_1800BF3EC
0x1800bf39c  mov     qword ptr [rsp+48h+ArgList], rax; ArgList
0x1800bf3a1  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x1800bf3a8  lea     rax, aDllSearchPathC; "DLL search path computed: %ws\n"
0x1800bf3af  mov     edx, 647h; int
0x1800bf3b4  mov     [rsp+48h+Format], rax; Format
0x1800bf3b9  call    LdrpLogInternal
0x1800bf3be  jmp     loc_1800BF316
0x1800bf3c3  mov     dword ptr [rsp+48h+ArgList], eax; ArgList
0x1800bf3c7  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x1800bf3ce  lea     rax, aLazyDllSearchP; "Lazy DLL search path computation failed"...
0x1800bf3d5  xor     r9d, r9d; int
0x1800bf3d8  mov     edx, 634h; int
0x1800bf3dd  mov     [rsp+48h+Format], rax; Format
0x1800bf3e2  call    LdrpLogInternal
0x1800bf3e7  jmp     loc_1800BF316
0x1800bf3ec  mov     [rsp+48h+var_18], rax
0x1800bf3f1  mov     edx, 64Dh; int
0x1800bf3f6  mov     qword ptr [rsp+48h+ArgList], rcx; ArgList
0x1800bf3fb  lea     rax, aPackagedDllSea; "Packaged DLL search path computed. Pack"...
0x1800bf402  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x1800bf409  mov     [rsp+48h+Format], rax; Format
0x1800bf40e  call    LdrpLogInternal
0x1800bf413  jmp     loc_1800BF316
```
