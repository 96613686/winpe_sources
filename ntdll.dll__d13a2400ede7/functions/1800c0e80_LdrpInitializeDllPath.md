# LdrpInitializeDllPath

- ea: `0x1800c0e80`
- end: `0x1800c1048`
- name: `LdrpInitializeDllPath`
- size: `456`
- prototype: ``
- caller_count: `11`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18006fd70`
- `0x1800bfe70`
- `0x1800c0088`
- `0x1800c09fc`
- `0x1800c0ca0`
- `0x1800c19c0`
- `0x1800c25c0`
- `0x1801060b8`
- `0x180107a54`
- `0x180125e90`
- `0x18015bec8`

## callees

- `0x1800165d0`
- `0x18001d490`
- `0x18001eb80`
- `0x180069af8`
- `0x18006f0d0`
- `0x1800c0e80`

## string_xrefs

- `0x1800c0ede`: `DLL search path passed in externally: %ws\n`
- `0x1800c0eea`: `LdrpInitializeDllPath`

## pseudocode

```c
void __fastcall LdrpInitializeDllPath(int *a1, __int64 ArgList, __int64 *a3)
{
  int *v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  _DWORD *SharedData; // rcx
  __int64 v9; // rcx
  char *v10; // rcx
  __int64 v11; // rdi
  char v12; // bl
  char v13; // al
  __int128 v14; // [rsp+30h] [rbp-28h] BYREF
  __int128 v15; // [rsp+40h] [rbp-18h] BYREF

  v4 = a1;
  *(_OWORD *)a3 = 0;
  *((_OWORD *)a3 + 1) = 0;
  *((_OWORD *)a3 + 2) = 0;
  *((_OWORD *)a3 + 3) = 0;
  *((_OWORD *)a3 + 4) = 0;
  *((_OWORD *)a3 + 5) = 0;
  *((_OWORD *)a3 + 6) = 0;
  *((_OWORD *)a3 + 7) = 0;
  if ( (ArgList & 1) != 0 || !ArgList )
  {
    a3[4] = (__int64)a1;
    *((_DWORD *)a3 + 6) = ArgList & 0xFFFFFFFE;
  }
  else
  {
    *a3 = ArgList;
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrutil.c",
      1552,
      (int)"LdrpInitializeDllPath",
      2,
      "DLL search path passed in externally: %ws\n",
      ArgList);
    v15 = 0;
    SharedData = NtCurrentPeb()->SharedData;
    v14 = 0;
    if ( SharedData && *SharedData )
      v9 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v9 = 2147353476;
    if ( *(_BYTE *)v9 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
    {
      v10 = (unsigned int)RtlGetCurrentServiceSessionId(v9, v5, v6, v7)
          ? (char *)NtCurrentPeb()->SharedData + 555
          : (char *)2147353477;
      if ( (*v10 & 0x20) != 0 )
      {
        v11 = *a3;
        if ( !v4 )
          v4 = &dword_18017664C;
        v12 = RtlCreateUnicodeString(&v15, v4);
        v13 = RtlCreateUnicodeString(&v14, v11);
        if ( v12 )
        {
          if ( v13 )
          {
            LdrpLogEtwEvent(5312, 0, 0, 0, (__int64)&v14, (__int64)&v15);
            if ( *((_QWORD *)&v14 + 1) )
              RtlpSysVolFree(*((_QWORD *)&v14 + 1));
          }
          if ( *((_QWORD *)&v15 + 1) )
            RtlpSysVolFree(*((_QWORD *)&v15 + 1));
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800c0e80  mov     [rsp+arg_8], rbx
0x1800c0e85  push    rsi
0x1800c0e86  sub     rsp, 50h
0x1800c0e8a  xorps   xmm0, xmm0
0x1800c0e8d  mov     rbx, r8
0x1800c0e90  mov     rsi, rcx
0x1800c0e93  movups  xmmword ptr [r8], xmm0
0x1800c0e97  movups  xmmword ptr [r8+10h], xmm0
0x1800c0e9c  movups  xmmword ptr [r8+20h], xmm0
0x1800c0ea1  movups  xmmword ptr [r8+30h], xmm0
0x1800c0ea6  movups  xmmword ptr [r8+40h], xmm0
0x1800c0eab  movups  xmmword ptr [r8+50h], xmm0
0x1800c0eb0  movups  xmmword ptr [r8+60h], xmm0
0x1800c0eb5  movups  xmmword ptr [r8+70h], xmm0
0x1800c0eba  test    dl, 1
0x1800c0ebd  jz      short loc_1800C0ED6
0x1800c0ebf  and     edx, 0FFFFFFFEh
0x1800c0ec2  mov     [r8+20h], rsi
0x1800c0ec6  mov     [r8+18h], edx
0x1800c0eca  mov     rbx, [rsp+58h+arg_8]
0x1800c0ecf  add     rsp, 50h
0x1800c0ed3  pop     rsi
0x1800c0ed4  retn
0x1800c0ed6  test    rdx, rdx
0x1800c0ed9  jz      short loc_1800C0EBF
0x1800c0edb  mov     [r8], rdx
0x1800c0ede  lea     rax, aDllSearchPathP; "DLL search path passed in externally: %"...
0x1800c0ee5  mov     qword ptr [rsp+58h+ArgList], rdx; ArgList
0x1800c0eea  lea     r8, aLdrpinitialize_12; "LdrpInitializeDllPath"
0x1800c0ef1  mov     edx, 610h; int
0x1800c0ef6  mov     [rsp+58h+Format], rax; Format
0x1800c0efb  mov     r9d, 2; int
0x1800c0f01  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x1800c0f08  call    LdrpLogInternal
0x1800c0f0d  mov     rax, gs:60h
0x1800c0f16  xorps   xmm0, xmm0
0x1800c0f19  xorps   xmm1, xmm1
0x1800c0f1c  movups  [rsp+58h+var_18], xmm0
0x1800c0f21  mov     rcx, [rax+90h]
0x1800c0f28  movups  [rsp+58h+var_28], xmm1
0x1800c0f2d  test    rcx, rcx
0x1800c0f30  jnz     loc_1800C1019
0x1800c0f36  mov     ecx, 7FFE0384h
0x1800c0f3b  cmp     byte ptr [rcx], 0
0x1800c0f3e  jz      short loc_1800C0ECA
0x1800c0f40  mov     rax, gs:60h
0x1800c0f49  test    byte ptr [rax+378h], 4
0x1800c0f50  jz      loc_1800C0ECA
0x1800c0f56  call    RtlGetCurrentServiceSessionId
0x1800c0f5b  test    eax, eax
0x1800c0f5d  jz      loc_1800C103E
0x1800c0f63  mov     rax, gs:60h
0x1800c0f6c  mov     rcx, [rax+90h]
0x1800c0f73  add     rcx, 22Bh
0x1800c0f7a  test    byte ptr [rcx], 20h
0x1800c0f7d  jz      loc_1800C0ECA
0x1800c0f83  lea     rax, dword_18017664C
0x1800c0f8a  mov     [rsp+58h+arg_0], rdi
0x1800c0f8f  mov     rdi, [rbx]
0x1800c0f92  lea     rcx, [rsp+58h+var_18]
0x1800c0f97  test    rsi, rsi
0x1800c0f9a  cmovz   rsi, rax
0x1800c0f9e  mov     rdx, rsi
0x1800c0fa1  call    RtlCreateUnicodeString
0x1800c0fa6  mov     rdx, rdi
0x1800c0fa9  lea     rcx, [rsp+58h+var_28]
0x1800c0fae  movzx   ebx, al
0x1800c0fb1  call    RtlCreateUnicodeString
0x1800c0fb6  mov     rdi, [rsp+58h+arg_0]
0x1800c0fbb  test    bl, bl
0x1800c0fbd  jz      loc_1800C0ECA
0x1800c0fc3  test    al, al
0x1800c0fc5  jz      short loc_1800C0FFC
0x1800c0fc7  lea     rax, [rsp+58h+var_18]
0x1800c0fcc  mov     ecx, 14C0h
0x1800c0fd1  mov     qword ptr [rsp+58h+ArgList], rax
0x1800c0fd6  xor     r9d, r9d
0x1800c0fd9  lea     rax, [rsp+58h+var_28]
0x1800c0fde  xor     r8d, r8d
0x1800c0fe1  xor     edx, edx
0x1800c0fe3  mov     [rsp+58h+Format], rax
0x1800c0fe8  call    LdrpLogEtwEvent
0x1800c0fed  mov     rcx, qword ptr [rsp+58h+var_28+8]
0x1800c0ff2  test    rcx, rcx
0x1800c0ff5  jz      short loc_1800C0FFC
0x1800c0ff7  call    RtlpSysVolFree
0x1800c0ffc  mov     rcx, qword ptr [rsp+58h+var_18+8]
0x1800c1001  test    rcx, rcx
0x1800c1004  jz      loc_1800C0ECA
0x1800c100a  mov     rbx, [rsp+58h+arg_8]
0x1800c100f  add     rsp, 50h
0x1800c1013  pop     rsi
0x1800c1014  jmp     RtlpSysVolFree
0x1800c1019  cmp     dword ptr [rcx], 0
0x1800c101c  jz      loc_1800C0F36
0x1800c1022  mov     rax, gs:60h
0x1800c102b  mov     rcx, [rax+90h]
0x1800c1032  add     rcx, 22Ah
0x1800c1039  jmp     loc_1800C0F3B
0x1800c103e  mov     ecx, 7FFE0385h
0x1800c1043  jmp     loc_1800C0F7A
```
