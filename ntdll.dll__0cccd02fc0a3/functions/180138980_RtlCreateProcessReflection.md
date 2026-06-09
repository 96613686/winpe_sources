# RtlCreateProcessReflection

- ea: `0x180138980`
- end: `0x180138f2b`
- name: `RtlCreateProcessReflection`
- size: `1451`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting`

## callees

- `0x1800d1cd0`
- `0x180138980`
- `0x180138f40`
- `0x18015e350`
- `0x18015e490`
- `0x18015e4b0`
- `0x18015e5d0`
- `0x18015e5f0`
- `0x18015e690`
- `0x18015e7d0`
- `0x18015e810`
- `0x18015ea50`
- `0x18015ebd0`
- `0x18015ec10`
- `0x18015ee10`
- `0x18015ee20`

## pseudocode

```c
__int64 __fastcall RtlCreateProcessReflection(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  HANDLE v7; // rsi
  int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx
  int UserThread; // eax
  HANDLE v23; // rcx
  int v24; // eax
  int ReturnLength; // [rsp+20h] [rbp-B9h]
  int ReturnLengtha; // [rsp+20h] [rbp-B9h]
  int v27; // [rsp+30h] [rbp-A9h]
  __int64 v28; // [rsp+60h] [rbp-79h] BYREF
  __int64 v29; // [rsp+68h] [rbp-71h] BYREF
  __int64 v30; // [rsp+70h] [rbp-69h] BYREF
  HANDLE v31; // [rsp+78h] [rbp-61h] BYREF
  ULONG ProcessInformationLength[2]; // [rsp+80h] [rbp-59h] BYREF
  PVOID ProcessInformation; // [rsp+88h] [rbp-51h] BYREF
  __int64 v34; // [rsp+90h] [rbp-49h] BYREF
  HANDLE v35; // [rsp+98h] [rbp-41h] BYREF
  HANDLE v36; // [rsp+A0h] [rbp-39h] BYREF
  HANDLE Handle[2]; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v38; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v39; // [rsp+C0h] [rbp-19h]
  __int64 v40; // [rsp+C8h] [rbp-11h] BYREF
  _QWORD v41[10]; // [rsp+D0h] [rbp-9h] BYREF

  *(_QWORD *)ProcessInformationLength = 4096;
  Handle[0] = 0;
  v29 = 0;
  v7 = 0;
  ProcessInformation = 0;
  v28 = 0;
  v30 = 0;
  v35 = 0;
  v39 = 0;
  v38 = 0;
  v34 = 0;
  v40 = 0;
  v41[0] = 0;
  v36 = 0;
  v31 = 0;
  ZwQuerySystemTime(&v40);
  if ( (a2 & 0xFFFFFFE1) != 0 )
    return 3221225712LL;
  if ( (a2 & 8) != 0 && a3 )
    return 3221225715LL;
  if ( a6 )
  {
    *(_OWORD *)a6 = 0;
    *(_OWORD *)(a6 + 16) = 0;
  }
  v12 = ZwAllocateVirtualMemory(-1, &ProcessInformation, 0, ProcessInformationLength, 12288, 4);
  if ( v12 < 0 )
  {
    ProcessInformation = 0;
    goto LABEL_41;
  }
  NtQueryInformationProcess(
    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
    ProcessImageFileName,
    ProcessInformation,
    ProcessInformationLength[0],
    ProcessInformationLength);
  *(_QWORD *)ProcessInformationLength = 4096;
  ZwFreeVirtualMemory(-1, &ProcessInformation, ProcessInformationLength, 0x8000);
  v30 = 88;
  v12 = ZwAllocateVirtualMemory(-1, &v28, 0, &v30, 12288, 4);
  if ( v12 < 0 )
  {
    v28 = 0;
    goto LABEL_41;
  }
  v13 = v28;
  v14 = v30;
  *(_QWORD *)(v28 + 24) = a4;
  *(_QWORD *)(v13 + 16) = a3;
  *(_QWORD *)v13 = v14;
  *(_DWORD *)(v13 + 8) = a2;
  *(_QWORD *)(v13 + 48) = a5;
  if ( a1 == -1 )
  {
    *(_DWORD *)(v13 + 8) = a2 | 0x10;
    v12 = RtlpProcessReflectionStartup(v28);
    if ( v12 >= 0 && a6 )
    {
      v15 = v28;
      *(_QWORD *)a6 = *(_QWORD *)(v28 + 56);
      v16 = *(_QWORD *)(v15 + 64);
      v17 = v28;
      *(_QWORD *)(a6 + 8) = v16;
      v18 = *(_QWORD *)(v17 + 72);
      v19 = v28;
LABEL_40:
      *(_QWORD *)(a6 + 16) = v18;
      *(_QWORD *)(a6 + 24) = *(_QWORD *)(v19 + 80);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  v39 = v30;
  v12 = NtCreateSection(&v35, 6, 0);
  if ( v12 < 0 )
    goto LABEL_41;
  v38 = v30;
  v12 = ZwMapViewOfSection(v35, a1, &v34, 0, v30, 0, &v38, 2, 0, 4);
  if ( v12 >= 0 )
  {
    v12 = ZwMapViewOfSection(v35, -1, &v29, 0, v30, 0, &v38, 2, 0, 4);
    if ( v12 < 0 )
    {
      v29 = 0;
      goto LABEL_41;
    }
    if ( !a6
      || (LOBYTE(ReturnLength) = 0, v12 = ZwCreateEvent(&v36, 2031619, 0, 0, ReturnLength), v12 >= 0)
      && (LOBYTE(ReturnLengtha) = 0, v12 = ZwCreateEvent(&v31, 2031619, 0, 0, ReturnLengtha), v12 >= 0)
      && (v12 = ZwDuplicateObject(-1, v36, a1, v28 + 32, 2031619, 0, 2), v12 >= 0)
      && (v12 = ZwDuplicateObject(-1, v31, a1, v28 + 40, 2031619, 0, 2), v12 >= 0)
      && (!a5 || (v12 = ZwDuplicateObject(-1, a5, a1, v28 + 48, 2031619, 0, 2), v12 >= 0)) )
    {
      v20 = v28;
      v21 = v29;
      *(_OWORD *)v29 = *(_OWORD *)v28;
      *(_OWORD *)(v21 + 16) = *(_OWORD *)(v20 + 16);
      *(_OWORD *)(v21 + 32) = *(_OWORD *)(v20 + 32);
      *(_OWORD *)(v21 + 48) = *(_OWORD *)(v20 + 48);
      *(_OWORD *)(v21 + 64) = *(_OWORD *)(v20 + 64);
      *(_QWORD *)(v21 + 80) = *(_QWORD *)(v20 + 80);
      UserThread = RtlpCreateUserThreadEx(
                     a1,
                     0,
                     2,
                     0,
                     0,
                     0,
                     v27,
                     (__int64)RtlpProcessReflectionStartup,
                     v34,
                     (__int64)Handle,
                     0);
      v7 = Handle[0];
      v12 = UserThread;
      if ( UserThread >= 0 )
      {
        if ( a6 )
        {
          Handle[1] = v36;
          if ( (unsigned int)NtWaitForMultipleObjects(2, Handle, 1, 0, 0) == 1 )
          {
            if ( *(_QWORD *)(v29 + 56) )
            {
              if ( (int)ZwDuplicateObject(a1, *(_QWORD *)(v29 + 56), -1, a6, 0x1FFFFF, 0, 2) >= 0 )
              {
                v24 = ZwDuplicateObject(a1, *(_QWORD *)(v29 + 64), -1, a6 + 8, 0x1FFFFF, 0, 2);
                v23 = v31;
                if ( v24 >= 0 )
                {
                  v12 = ZwSetEvent(v31, 0);
                  v18 = *(_QWORD *)(v29 + 72);
                  v19 = v29;
                  goto LABEL_40;
                }
              }
              else
              {
                v23 = v31;
              }
              v12 = ZwSetEvent(v23, 0);
              goto LABEL_41;
            }
            NtWaitForSingleObject(v7, 0, 0);
          }
          v12 = -1073741823;
        }
      }
    }
LABEL_41:
    if ( v34 )
      NtUnmapViewOfSection(a1);
    goto LABEL_43;
  }
  v34 = 0;
LABEL_43:
  if ( v29 )
    NtUnmapViewOfSection(-1);
  if ( v35 )
    NtClose(v35);
  if ( v28 )
    ZwFreeVirtualMemory(-1, &v28, &v30, 0x8000);
  if ( v36 )
    NtClose(v36);
  if ( v31 )
    NtClose(v31);
  if ( v7 )
    NtClose(v7);
  ZwQuerySystemTime(v41);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180138980  push    rbp
0x180138982  push    rbx
0x180138983  push    rsi
0x180138984  push    rdi
0x180138985  push    r12
0x180138987  push    r13
0x180138989  push    r14
0x18013898b  push    r15
0x18013898d  lea     rbp, [rsp-0Fh]
0x180138992  sub     rsp, 0E8h
0x180138999  xor     ebx, ebx
0x18013899b  mov     qword ptr [rbp+47h+ProcessInformationLength], 1000h
0x1801389a3  mov     r15, rcx
0x1801389a6  mov     [rbp+47h+Handle], rbx
0x1801389aa  lea     rcx, [rbp+47h+var_58]
0x1801389ae  mov     [rbp+47h+var_B8], rbx
0x1801389b2  mov     esi, ebx
0x1801389b4  mov     [rbp+47h+ProcessInformation], rbx
0x1801389b8  mov     [rbp+47h+var_C0], rbx
0x1801389bc  mov     r13, r9
0x1801389bf  mov     [rbp+47h+var_B0], rbx
0x1801389c3  mov     r12, r8
0x1801389c6  mov     [rbp+47h+var_88], rbx
0x1801389ca  mov     r14d, edx
0x1801389cd  mov     [rbp+47h+var_60], rbx
0x1801389d1  mov     [rbp+47h+var_68], rbx
0x1801389d5  mov     [rbp+47h+var_90], rbx
0x1801389d9  mov     [rbp+47h+var_58], rbx
0x1801389dd  mov     [rbp+47h+var_50], rbx
0x1801389e1  mov     [rbp+47h+var_80], rbx
0x1801389e5  mov     [rbp+47h+var_A8], rbx
0x1801389e9  call    ZwQuerySystemTime
0x1801389ee  test    r14d, 0FFFFFFE1h
0x1801389f5  jz      short loc_180138A01
0x1801389f7  mov     eax, 0C00000F0h
0x1801389fc  jmp     loc_180138F16
0x180138a01  test    r14b, 8
0x180138a05  jz      short loc_180138A16
0x180138a07  test    r12, r12
0x180138a0a  jz      short loc_180138A16
0x180138a0c  mov     eax, 0C00000F3h
0x180138a11  jmp     loc_180138F16
0x180138a16  mov     rdi, [rbp+47h+arg_28]
0x180138a1a  test    rdi, rdi
0x180138a1d  jz      short loc_180138A29
0x180138a1f  xorps   xmm0, xmm0
0x180138a22  movups  xmmword ptr [rdi], xmm0
0x180138a25  movups  xmmword ptr [rdi+10h], xmm0
0x180138a29  mov     dword ptr [rsp+120h+var_F8], 4
0x180138a31  lea     r9, [rbp+47h+ProcessInformationLength]
0x180138a35  xor     r8d, r8d
0x180138a38  mov     dword ptr [rsp+120h+ReturnLength], 3000h
0x180138a40  lea     rdx, [rbp+47h+ProcessInformation]
0x180138a44  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180138a48  call    ZwAllocateVirtualMemory
0x180138a4d  mov     ebx, eax
0x180138a4f  test    eax, eax
0x180138a51  jns     short loc_180138A63
0x180138a53  xor     r14d, r14d
0x180138a56  mov     [rbp+47h+ProcessInformation], r14
0x180138a5a  or      r13, 0FFFFFFFFFFFFFFFFh
0x180138a5e  jmp     loc_180138E96
0x180138a63  mov     r9d, [rbp+47h+ProcessInformationLength]; ProcessInformationLength
0x180138a67  lea     rax, [rbp+47h+ProcessInformationLength]
0x180138a6b  mov     r8, [rbp+47h+ProcessInformation]; ProcessInformation
0x180138a6f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180138a73  mov     rcx, rbx; ProcessHandle
0x180138a76  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x180138a7b  mov     edx, 1Bh; ProcessInformationClass
0x180138a80  call    NtQueryInformationProcess
0x180138a85  mov     r9d, 8000h
0x180138a8b  mov     qword ptr [rbp+47h+ProcessInformationLength], 1000h
0x180138a93  lea     r8, [rbp+47h+ProcessInformationLength]
0x180138a97  mov     rcx, rbx
0x180138a9a  lea     rdx, [rbp+47h+ProcessInformation]
0x180138a9e  call    ZwFreeVirtualMemory
0x180138aa3  lea     r9, [rbp+47h+var_B0]
0x180138aa7  mov     dword ptr [rsp+120h+var_F8], 4
0x180138aaf  xor     r8d, r8d
0x180138ab2  mov     [rbp+47h+var_B0], 58h ; 'X'
0x180138aba  lea     rdx, [rbp+47h+var_C0]
0x180138abe  mov     dword ptr [rsp+120h+ReturnLength], 3000h
0x180138ac6  mov     rcx, rbx
0x180138ac9  call    ZwAllocateVirtualMemory
0x180138ace  mov     ebx, eax
0x180138ad0  test    eax, eax
0x180138ad2  jns     short loc_180138AE0
0x180138ad4  xor     r14d, r14d
0x180138ad7  mov     [rbp+47h+var_C0], r14
0x180138adb  jmp     loc_180138A5A
0x180138ae0  mov     rcx, [rbp+47h+var_C0]
0x180138ae4  mov     rax, [rbp+47h+var_B0]
0x180138ae8  mov     [rcx+18h], r13
0x180138aec  or      r13, 0FFFFFFFFFFFFFFFFh
0x180138af0  mov     [rcx+10h], r12
0x180138af4  mov     r12, [rbp+47h+arg_20]
0x180138af8  mov     [rcx], rax
0x180138afb  mov     [rcx+8], r14d
0x180138aff  mov     [rcx+30h], r12
0x180138b03  cmp     r15, r13
0x180138b06  jnz     short loc_180138B57
0x180138b08  or      r14d, 10h
0x180138b0c  mov     [rcx+8], r14d
0x180138b10  mov     rcx, [rbp+47h+var_C0]
0x180138b14  call    RtlpProcessReflectionStartup
0x180138b19  xor     r14d, r14d
0x180138b1c  mov     ebx, eax
0x180138b1e  test    eax, eax
0x180138b20  js      loc_180138E96
0x180138b26  test    rdi, rdi
0x180138b29  jz      loc_180138E96
0x180138b2f  mov     rax, [rbp+47h+var_C0]
0x180138b33  mov     rcx, [rax+38h]
0x180138b37  mov     rax, [rbp+47h+var_C0]
0x180138b3b  mov     [rdi], rcx
0x180138b3e  mov     rcx, [rax+40h]
0x180138b42  mov     rax, [rbp+47h+var_C0]
0x180138b46  mov     [rdi+8], rcx
0x180138b4a  mov     rcx, [rax+48h]
0x180138b4e  mov     rax, [rbp+47h+var_C0]
0x180138b52  jmp     loc_180138E8A
0x180138b57  mov     rax, [rbp+47h+var_B0]
0x180138b5b  lea     r9, [rbp+47h+var_60]
0x180138b5f  xor     r14d, r14d
0x180138b62  mov     [rbp+47h+var_60], rax
0x180138b66  mov     [rsp+120h+var_F0], r14
0x180138b6b  lea     rcx, [rbp+47h+var_88]
0x180138b6f  mov     dword ptr [rsp+120h+var_F8], 8000000h
0x180138b77  xor     r8d, r8d
0x180138b7a  mov     dword ptr [rsp+120h+ReturnLength], 4
0x180138b82  lea     edx, [r14+6]
0x180138b86  call    NtCreateSection
0x180138b8b  mov     ebx, eax
0x180138b8d  test    eax, eax
0x180138b8f  js      loc_180138E96
0x180138b95  mov     rax, [rbp+47h+var_B0]
0x180138b99  lea     rcx, [rbp+47h+var_68]
0x180138b9d  mov     dword ptr [rsp+120h+var_D8], 4
0x180138ba5  lea     r8, [rbp+47h+var_90]
0x180138ba9  mov     dword ptr [rsp+120h+var_E0], r14d
0x180138bae  xor     r9d, r9d
0x180138bb1  mov     dword ptr [rsp+120h+var_E8], 2
0x180138bb9  mov     rdx, r15
0x180138bbc  mov     [rsp+120h+var_F0], rcx
0x180138bc1  mov     rcx, [rbp+47h+var_88]
0x180138bc5  mov     [rsp+120h+var_F8], r14
0x180138bca  mov     [rsp+120h+ReturnLength], rax
0x180138bcf  mov     [rbp+47h+var_68], rax
0x180138bd3  call    ZwMapViewOfSection
0x180138bd8  mov     ebx, eax
0x180138bda  test    eax, eax
0x180138bdc  jns     short loc_180138BE7
0x180138bde  mov     [rbp+47h+var_90], r14
0x180138be2  jmp     loc_180138EA7
0x180138be7  mov     rcx, [rbp+47h+var_88]
0x180138beb  lea     rax, [rbp+47h+var_68]
0x180138bef  mov     dword ptr [rsp+120h+var_D8], 4
0x180138bf7  lea     r8, [rbp+47h+var_B8]
0x180138bfb  mov     dword ptr [rsp+120h+var_E0], r14d
0x180138c00  xor     r9d, r9d
0x180138c03  mov     dword ptr [rsp+120h+var_E8], 2
0x180138c0b  mov     rdx, r13
0x180138c0e  mov     [rsp+120h+var_F0], rax
0x180138c13  mov     rax, [rbp+47h+var_B0]
0x180138c17  mov     [rsp+120h+var_F8], r14
0x180138c1c  mov     [rsp+120h+ReturnLength], rax
0x180138c21  call    ZwMapViewOfSection
0x180138c26  mov     ebx, eax
0x180138c28  test    eax, eax
0x180138c2a  jns     short loc_180138C35
0x180138c2c  mov     [rbp+47h+var_B8], r14
0x180138c30  jmp     loc_180138E96
0x180138c35  test    rdi, rdi
0x180138c38  jz      loc_180138D2A
0x180138c3e  xor     r9d, r9d
0x180138c41  mov     byte ptr [rsp+120h+ReturnLength], r14b
0x180138c46  xor     r8d, r8d
0x180138c49  lea     rcx, [rbp+47h+var_80]
0x180138c4d  mov     edx, 1F0003h
0x180138c52  call    ZwCreateEvent
0x180138c57  mov     ebx, eax
0x180138c59  test    eax, eax
0x180138c5b  js      loc_180138E96
0x180138c61  xor     r9d, r9d
0x180138c64  mov     byte ptr [rsp+120h+ReturnLength], r14b
0x180138c69  xor     r8d, r8d
0x180138c6c  lea     rcx, [rbp+47h+var_A8]
0x180138c70  mov     edx, 1F0003h
0x180138c75  call    ZwCreateEvent
0x180138c7a  mov     ebx, eax
0x180138c7c  test    eax, eax
0x180138c7e  js      loc_180138E96
0x180138c84  mov     r9, [rbp+47h+var_C0]
0x180138c88  mov     r8, r15
0x180138c8b  mov     rdx, [rbp+47h+var_80]
0x180138c8f  add     r9, 20h ; ' '
0x180138c93  mov     dword ptr [rsp+120h+var_F0], 2
0x180138c9b  mov     rcx, r13
0x180138c9e  mov     dword ptr [rsp+120h+var_F8], r14d
0x180138ca3  mov     dword ptr [rsp+120h+ReturnLength], 1F0003h
0x180138cab  call    ZwDuplicateObject
0x180138cb0  mov     ebx, eax
0x180138cb2  test    eax, eax
0x180138cb4  js      loc_180138E96
0x180138cba  mov     r9, [rbp+47h+var_C0]
0x180138cbe  mov     r8, r15
0x180138cc1  mov     rdx, [rbp+47h+var_A8]
0x180138cc5  add     r9, 28h ; '('
0x180138cc9  mov     dword ptr [rsp+120h+var_F0], 2
0x180138cd1  mov     rcx, r13
0x180138cd4  mov     dword ptr [rsp+120h+var_F8], r14d
0x180138cd9  mov     dword ptr [rsp+120h+ReturnLength], 1F0003h
0x180138ce1  call    ZwDuplicateObject
0x180138ce6  mov     ebx, eax
0x180138ce8  test    eax, eax
0x180138cea  js      loc_180138E96
0x180138cf0  test    r12, r12
0x180138cf3  jz      short loc_180138D2A
0x180138cf5  mov     r9, [rbp+47h+var_C0]
0x180138cf9  mov     r8, r15
0x180138cfc  mov     dword ptr [rsp+120h+var_F0], 2
0x180138d04  add     r9, 30h ; '0'
0x180138d08  mov     dword ptr [rsp+120h+var_F8], r14d
0x180138d0d  mov     rdx, r12
0x180138d10  mov     rcx, r13
0x180138d13  mov     dword ptr [rsp+120h+ReturnLength], 1F0003h
0x180138d1b  call    ZwDuplicateObject
0x180138d20  mov     ebx, eax
0x180138d22  test    eax, eax
0x180138d24  js      loc_180138E96
0x180138d2a  nop
0x180138d2b  mov     [rsp+120h+var_D0], r14
0x180138d30  mov     rax, [rbp+47h+var_C0]
0x180138d34  xor     r9d, r9d
0x180138d37  mov     rcx, [rbp+47h+var_B8]
0x180138d3b  xor     edx, edx
0x180138d3d  movups  xmm0, xmmword ptr [rax]
0x180138d40  lea     r12d, [r9+2]
0x180138d44  mov     r8d, r12d
0x180138d47  movups  xmmword ptr [rcx], xmm0
0x180138d4a  movups  xmm1, xmmword ptr [rax+10h]
0x180138d4e  movups  xmmword ptr [rcx+10h], xmm1
0x180138d52  movups  xmm0, xmmword ptr [rax+20h]
0x180138d56  movups  xmmword ptr [rcx+20h], xmm0
0x180138d5a  movups  xmm1, xmmword ptr [rax+30h]
0x180138d5e  movups  xmmword ptr [rcx+30h], xmm1
0x180138d62  movups  xmm0, xmmword ptr [rax+40h]
0x180138d66  movups  xmmword ptr [rcx+40h], xmm0
0x180138d6a  movsd   xmm1, qword ptr [rax+50h]
0x180138d6f  lea     rax, [rbp+47h+Handle]
0x180138d73  mov     [rsp+120h+var_D8], rax
0x180138d78  movsd   qword ptr [rcx+50h], xmm1
0x180138d7d  nop
0x180138d7e  mov     rax, [rbp+47h+var_90]
0x180138d82  mov     rcx, r15
0x180138d85  mov     [rsp+120h+var_E0], rax
0x180138d8a  lea     rax, RtlpProcessReflectionStartup
0x180138d91  mov     [rsp+120h+var_E8], rax
0x180138d96  mov     [rsp+120h+var_F8], r14
0x180138d9b  mov     [rsp+120h+ReturnLength], r14
0x180138da0  call    RtlpCreateUserThreadEx
0x180138da5  mov     rsi, [rbp+47h+Handle]
0x180138da9  mov     ebx, eax
0x180138dab  test    eax, eax
0x180138dad  js      loc_180138E96
0x180138db3  test    rdi, rdi
0x180138db6  jz      loc_180138E96
0x180138dbc  mov     rax, [rbp+47h+var_80]
0x180138dc0  lea     r8d, [r12-1]
0x180138dc5  xor     r9d, r9d
0x180138dc8  mov     [rbp+47h+var_70], rax
0x180138dcc  lea     rdx, [rbp+47h+Handle]
0x180138dd0  mov     [rbp+47h+Handle], rsi
0x180138dd4  mov     ecx, r12d
0x180138dd7  mov     [rsp+120h+ReturnLength], r14
0x180138ddc  call    NtWaitForMultipleObjects
0x180138de1  cmp     eax, 1
0x180138de4  jz      short loc_180138DF0
0x180138de6  mov     ebx, 0C0000001h
0x180138deb  jmp     loc_180138E96
0x180138df0  mov     rax, [rbp+47h+var_B8]
0x180138df4  mov     rcx, [rax+38h]
0x180138df8  test    rcx, rcx
0x180138dfb  jnz     short loc_180138E0C
0x180138dfd  xor     r8d, r8d; Timeout
0x180138e00  xor     edx, edx; Alertable
0x180138e02  mov     rcx, rsi; Handle
0x180138e05  call    NtWaitForSingleObject
0x180138e0a  jmp     short loc_180138DE6
0x180138e0c  mov     rax, [rbp+47h+var_B8]
0x180138e10  mov     ebx, 1FFFFFh
0x180138e15  mov     dword ptr [rsp+120h+var_F0], r12d
0x180138e1a  mov     r9, rdi
0x180138e1d  mov     dword ptr [rsp+120h+var_F8], r14d
0x180138e22  mov     r8, r13
0x180138e25  mov     rcx, r15
0x180138e28  mov     dword ptr [rsp+120h+ReturnLength], ebx
0x180138e2c  mov     rdx, [rax+38h]
0x180138e30  call    ZwDuplicateObject
0x180138e35  test    eax, eax
  ... truncated ...
```
