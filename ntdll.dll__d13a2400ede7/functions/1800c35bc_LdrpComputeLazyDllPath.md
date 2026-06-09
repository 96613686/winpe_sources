# LdrpComputeLazyDllPath

- ea: `0x1800c35bc`
- end: `0x1800c36f8`
- name: `LdrpComputeLazyDllPath`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c29c0`

## callees

- `0x180017e90`
- `0x1800183a0`
- `0x18001eb80`
- `0x18002ab70`
- `0x1800c35bc`

## string_xrefs

- `0x1800c3642`: `LdrpComputeLazyDllPath`
- `0x1800c3688`: `DLL search path computed: %ws\n`
- `0x1800c36ae`: `Lazy DLL search path computation failed with status: 0x%08lx.\n`
- `0x1800c36db`: `Packaged DLL search path computed. Package Dirs: %ws, DllPath: %ws\n`

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
0x1800c35bc  mov     rax, rsp
0x1800c35bf  mov     [rax+20h], rbx
0x1800c35c3  push    rdi
0x1800c35c4  sub     rsp, 40h
0x1800c35c8  mov     rbx, rcx
0x1800c35cb  mov     qword ptr [rax+8], 0
0x1800c35d3  lea     rcx, LdrpPathLock
0x1800c35da  mov     qword ptr [rax+18h], 0
0x1800c35e2  mov     qword ptr [rax+10h], 0
0x1800c35ea  xor     edi, edi
0x1800c35ec  call    RtlAcquireSRWLockExclusive
0x1800c35f1  cmp     [rbx], rdi
0x1800c35f4  jz      short loc_1800C3610
0x1800c35f6  lea     rcx, LdrpPathLock
0x1800c35fd  call    RtlReleaseSRWLockExclusive
0x1800c3602  mov     rbx, [rsp+48h+arg_18]
0x1800c3607  mov     eax, edi
0x1800c3609  add     rsp, 40h
0x1800c360d  pop     rdi
0x1800c360e  retn
0x1800c3610  lea     rdx, [rbx+78h]
0x1800c3614  lea     rcx, [rsp+48h+arg_8]
0x1800c3619  mov     [rsp+48h+var_18], rcx
0x1800c361e  lea     rax, [rbx+28h]
0x1800c3622  mov     rcx, [rbx+20h]
0x1800c3626  lea     r9, [rsp+48h+arg_0]
0x1800c362b  mov     qword ptr [rsp+48h+ArgList], rax
0x1800c3630  lea     r8, [rsp+48h+arg_10]
0x1800c3635  mov     [rsp+48h+Format], rdx
0x1800c363a  mov     edx, [rbx+18h]
0x1800c363d  call    LdrpGetDllPath
0x1800c3642  lea     r8, aLdrpcomputelaz; "LdrpComputeLazyDllPath"
0x1800c3649  mov     edi, eax
0x1800c364b  test    eax, eax
0x1800c364d  js      short loc_1800C36A3
0x1800c364f  mov     rax, [rsp+48h+arg_0]
0x1800c3654  mov     r9d, 2; int
0x1800c365a  mov     [rbx+8], rax
0x1800c365e  mov     rax, [rsp+48h+arg_8]
0x1800c3663  mov     [rbx+10h], rax
0x1800c3667  mov     rax, [rsp+48h+arg_10]
0x1800c366c  mov     byte ptr [rbx+7Ch], 1
0x1800c3670  mov     [rbx], rax
0x1800c3673  mov     rcx, [rbx+10h]
0x1800c3677  test    rcx, rcx
0x1800c367a  jnz     short loc_1800C36CC
0x1800c367c  mov     qword ptr [rsp+48h+ArgList], rax; ArgList
0x1800c3681  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x1800c3688  lea     rax, aDllSearchPathC; "DLL search path computed: %ws\n"
0x1800c368f  mov     edx, 647h; int
0x1800c3694  mov     [rsp+48h+Format], rax; Format
0x1800c3699  call    LdrpLogInternal
0x1800c369e  jmp     loc_1800C35F6
0x1800c36a3  mov     dword ptr [rsp+48h+ArgList], eax; ArgList
0x1800c36a7  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x1800c36ae  lea     rax, aLazyDllSearchP; "Lazy DLL search path computation failed"...
0x1800c36b5  xor     r9d, r9d; int
0x1800c36b8  mov     edx, 634h; int
0x1800c36bd  mov     [rsp+48h+Format], rax; Format
0x1800c36c2  call    LdrpLogInternal
0x1800c36c7  jmp     loc_1800C35F6
0x1800c36cc  mov     [rsp+48h+var_18], rax
0x1800c36d1  mov     edx, 64Dh; int
0x1800c36d6  mov     qword ptr [rsp+48h+ArgList], rcx; ArgList
0x1800c36db  lea     rax, aPackagedDllSea; "Packaged DLL search path computed. Pack"...
0x1800c36e2  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x1800c36e9  mov     [rsp+48h+Format], rax; Format
0x1800c36ee  call    LdrpLogInternal
0x1800c36f3  jmp     loc_1800C35F6
```
