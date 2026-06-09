# RtlCreateProcessReflection

- ea: `0x180139470`
- end: `0x180139a1b`
- name: `RtlCreateProcessReflection`
- size: `1451`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting`

## callees

- `0x1800d5f80`
- `0x180139470`
- `0x180139a30`
- `0x18015eb60`
- `0x18015eca0`
- `0x18015ecc0`
- `0x18015ede0`
- `0x18015ee00`
- `0x18015eea0`
- `0x18015efe0`
- `0x18015f020`
- `0x18015f260`
- `0x18015f3e0`
- `0x18015f420`
- `0x18015f620`
- `0x18015f630`

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
  __int64 v39; // [rsp+C0h] [rbp-19h] BYREF
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
    goto LABEL_40;
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
    goto LABEL_40;
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
LABEL_39:
      *(_QWORD *)(a6 + 16) = v18;
      *(_QWORD *)(a6 + 24) = *(_QWORD *)(v19 + 80);
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  v39 = v30;
  v12 = NtCreateSection(&v35, 6, 0, &v39, 4, 0x8000000, 0);
  if ( v12 < 0 )
    goto LABEL_40;
  v38 = v30;
  v12 = ZwMapViewOfSection(v35, a1, &v34, 0, v30, 0, &v38, 2, 0, 4);
  if ( v12 >= 0 )
  {
    v12 = ZwMapViewOfSection(v35, -1, &v29, 0, v30, 0, &v38, 2, 0, 4);
    if ( v12 < 0 )
    {
      v29 = 0;
      goto LABEL_40;
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
                  goto LABEL_39;
                }
              }
              else
              {
                v23 = v31;
              }
              v12 = ZwSetEvent(v23, 0);
              goto LABEL_40;
            }
            NtWaitForSingleObject(v7, 0, 0);
          }
          v12 = -1073741823;
        }
      }
    }
LABEL_40:
    if ( v34 )
      NtUnmapViewOfSection(a1);
    goto LABEL_42;
  }
  v34 = 0;
LABEL_42:
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
0x180139470  push    rbp
0x180139472  push    rbx
0x180139473  push    rsi
0x180139474  push    rdi
0x180139475  push    r12
0x180139477  push    r13
0x180139479  push    r14
0x18013947b  push    r15
0x18013947d  lea     rbp, [rsp-0Fh]
0x180139482  sub     rsp, 0E8h
0x180139489  xor     ebx, ebx
0x18013948b  mov     qword ptr [rbp+47h+ProcessInformationLength], 1000h
0x180139493  mov     r15, rcx
0x180139496  mov     [rbp+47h+Handle], rbx
0x18013949a  lea     rcx, [rbp+47h+var_58]
0x18013949e  mov     [rbp+47h+var_B8], rbx
0x1801394a2  mov     esi, ebx
0x1801394a4  mov     [rbp+47h+ProcessInformation], rbx
0x1801394a8  mov     [rbp+47h+var_C0], rbx
0x1801394ac  mov     r13, r9
0x1801394af  mov     [rbp+47h+var_B0], rbx
0x1801394b3  mov     r12, r8
0x1801394b6  mov     [rbp+47h+var_88], rbx
0x1801394ba  mov     r14d, edx
0x1801394bd  mov     [rbp+47h+var_60], rbx
0x1801394c1  mov     [rbp+47h+var_68], rbx
0x1801394c5  mov     [rbp+47h+var_90], rbx
0x1801394c9  mov     [rbp+47h+var_58], rbx
0x1801394cd  mov     [rbp+47h+var_50], rbx
0x1801394d1  mov     [rbp+47h+var_80], rbx
0x1801394d5  mov     [rbp+47h+var_A8], rbx
0x1801394d9  call    ZwQuerySystemTime
0x1801394de  test    r14d, 0FFFFFFE1h
0x1801394e5  jz      short loc_1801394F1
0x1801394e7  mov     eax, 0C00000F0h
0x1801394ec  jmp     loc_180139A06
0x1801394f1  test    r14b, 8
0x1801394f5  jz      short loc_180139506
0x1801394f7  test    r12, r12
0x1801394fa  jz      short loc_180139506
0x1801394fc  mov     eax, 0C00000F3h
0x180139501  jmp     loc_180139A06
0x180139506  mov     rdi, [rbp+47h+arg_28]
0x18013950a  test    rdi, rdi
0x18013950d  jz      short loc_180139519
0x18013950f  xorps   xmm0, xmm0
0x180139512  movups  xmmword ptr [rdi], xmm0
0x180139515  movups  xmmword ptr [rdi+10h], xmm0
0x180139519  mov     dword ptr [rsp+120h+var_F8], 4
0x180139521  lea     r9, [rbp+47h+ProcessInformationLength]
0x180139525  xor     r8d, r8d
0x180139528  mov     dword ptr [rsp+120h+ReturnLength], 3000h
0x180139530  lea     rdx, [rbp+47h+ProcessInformation]
0x180139534  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180139538  call    ZwAllocateVirtualMemory
0x18013953d  mov     ebx, eax
0x18013953f  test    eax, eax
0x180139541  jns     short loc_180139553
0x180139543  xor     r14d, r14d
0x180139546  mov     [rbp+47h+ProcessInformation], r14
0x18013954a  or      r13, 0FFFFFFFFFFFFFFFFh
0x18013954e  jmp     loc_180139986
0x180139553  mov     r9d, [rbp+47h+ProcessInformationLength]; ProcessInformationLength
0x180139557  lea     rax, [rbp+47h+ProcessInformationLength]
0x18013955b  mov     r8, [rbp+47h+ProcessInformation]; ProcessInformation
0x18013955f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180139563  mov     rcx, rbx; ProcessHandle
0x180139566  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18013956b  mov     edx, 1Bh; ProcessInformationClass
0x180139570  call    NtQueryInformationProcess
0x180139575  mov     r9d, 8000h
0x18013957b  mov     qword ptr [rbp+47h+ProcessInformationLength], 1000h
0x180139583  lea     r8, [rbp+47h+ProcessInformationLength]
0x180139587  mov     rcx, rbx
0x18013958a  lea     rdx, [rbp+47h+ProcessInformation]
0x18013958e  call    ZwFreeVirtualMemory
0x180139593  lea     r9, [rbp+47h+var_B0]
0x180139597  mov     dword ptr [rsp+120h+var_F8], 4
0x18013959f  xor     r8d, r8d
0x1801395a2  mov     [rbp+47h+var_B0], 58h ; 'X'
0x1801395aa  lea     rdx, [rbp+47h+var_C0]
0x1801395ae  mov     dword ptr [rsp+120h+ReturnLength], 3000h
0x1801395b6  mov     rcx, rbx
0x1801395b9  call    ZwAllocateVirtualMemory
0x1801395be  mov     ebx, eax
0x1801395c0  test    eax, eax
0x1801395c2  jns     short loc_1801395D0
0x1801395c4  xor     r14d, r14d
0x1801395c7  mov     [rbp+47h+var_C0], r14
0x1801395cb  jmp     loc_18013954A
0x1801395d0  mov     rcx, [rbp+47h+var_C0]
0x1801395d4  mov     rax, [rbp+47h+var_B0]
0x1801395d8  mov     [rcx+18h], r13
0x1801395dc  or      r13, 0FFFFFFFFFFFFFFFFh
0x1801395e0  mov     [rcx+10h], r12
0x1801395e4  mov     r12, [rbp+47h+arg_20]
0x1801395e8  mov     [rcx], rax
0x1801395eb  mov     [rcx+8], r14d
0x1801395ef  mov     [rcx+30h], r12
0x1801395f3  cmp     r15, r13
0x1801395f6  jnz     short loc_180139647
0x1801395f8  or      r14d, 10h
0x1801395fc  mov     [rcx+8], r14d
0x180139600  mov     rcx, [rbp+47h+var_C0]
0x180139604  call    RtlpProcessReflectionStartup
0x180139609  xor     r14d, r14d
0x18013960c  mov     ebx, eax
0x18013960e  test    eax, eax
0x180139610  js      loc_180139986
0x180139616  test    rdi, rdi
0x180139619  jz      loc_180139986
0x18013961f  mov     rax, [rbp+47h+var_C0]
0x180139623  mov     rcx, [rax+38h]
0x180139627  mov     rax, [rbp+47h+var_C0]
0x18013962b  mov     [rdi], rcx
0x18013962e  mov     rcx, [rax+40h]
0x180139632  mov     rax, [rbp+47h+var_C0]
0x180139636  mov     [rdi+8], rcx
0x18013963a  mov     rcx, [rax+48h]
0x18013963e  mov     rax, [rbp+47h+var_C0]
0x180139642  jmp     loc_18013997A
0x180139647  mov     rax, [rbp+47h+var_B0]
0x18013964b  lea     r9, [rbp+47h+var_60]
0x18013964f  xor     r14d, r14d
0x180139652  mov     [rbp+47h+var_60], rax
0x180139656  mov     [rsp+120h+var_F0], r14
0x18013965b  lea     rcx, [rbp+47h+var_88]
0x18013965f  mov     dword ptr [rsp+120h+var_F8], 8000000h
0x180139667  xor     r8d, r8d
0x18013966a  mov     dword ptr [rsp+120h+ReturnLength], 4
0x180139672  lea     edx, [r14+6]
0x180139676  call    NtCreateSection
0x18013967b  mov     ebx, eax
0x18013967d  test    eax, eax
0x18013967f  js      loc_180139986
0x180139685  mov     rax, [rbp+47h+var_B0]
0x180139689  lea     rcx, [rbp+47h+var_68]
0x18013968d  mov     dword ptr [rsp+120h+var_D8], 4
0x180139695  lea     r8, [rbp+47h+var_90]
0x180139699  mov     dword ptr [rsp+120h+var_E0], r14d
0x18013969e  xor     r9d, r9d
0x1801396a1  mov     dword ptr [rsp+120h+var_E8], 2
0x1801396a9  mov     rdx, r15
0x1801396ac  mov     [rsp+120h+var_F0], rcx
0x1801396b1  mov     rcx, [rbp+47h+var_88]
0x1801396b5  mov     [rsp+120h+var_F8], r14
0x1801396ba  mov     [rsp+120h+ReturnLength], rax
0x1801396bf  mov     [rbp+47h+var_68], rax
0x1801396c3  call    ZwMapViewOfSection
0x1801396c8  mov     ebx, eax
0x1801396ca  test    eax, eax
0x1801396cc  jns     short loc_1801396D7
0x1801396ce  mov     [rbp+47h+var_90], r14
0x1801396d2  jmp     loc_180139997
0x1801396d7  mov     rcx, [rbp+47h+var_88]
0x1801396db  lea     rax, [rbp+47h+var_68]
0x1801396df  mov     dword ptr [rsp+120h+var_D8], 4
0x1801396e7  lea     r8, [rbp+47h+var_B8]
0x1801396eb  mov     dword ptr [rsp+120h+var_E0], r14d
0x1801396f0  xor     r9d, r9d
0x1801396f3  mov     dword ptr [rsp+120h+var_E8], 2
0x1801396fb  mov     rdx, r13
0x1801396fe  mov     [rsp+120h+var_F0], rax
0x180139703  mov     rax, [rbp+47h+var_B0]
0x180139707  mov     [rsp+120h+var_F8], r14
0x18013970c  mov     [rsp+120h+ReturnLength], rax
0x180139711  call    ZwMapViewOfSection
0x180139716  mov     ebx, eax
0x180139718  test    eax, eax
0x18013971a  jns     short loc_180139725
0x18013971c  mov     [rbp+47h+var_B8], r14
0x180139720  jmp     loc_180139986
0x180139725  test    rdi, rdi
0x180139728  jz      loc_18013981A
0x18013972e  xor     r9d, r9d
0x180139731  mov     byte ptr [rsp+120h+ReturnLength], r14b
0x180139736  xor     r8d, r8d
0x180139739  lea     rcx, [rbp+47h+var_80]
0x18013973d  mov     edx, 1F0003h
0x180139742  call    ZwCreateEvent
0x180139747  mov     ebx, eax
0x180139749  test    eax, eax
0x18013974b  js      loc_180139986
0x180139751  xor     r9d, r9d
0x180139754  mov     byte ptr [rsp+120h+ReturnLength], r14b
0x180139759  xor     r8d, r8d
0x18013975c  lea     rcx, [rbp+47h+var_A8]
0x180139760  mov     edx, 1F0003h
0x180139765  call    ZwCreateEvent
0x18013976a  mov     ebx, eax
0x18013976c  test    eax, eax
0x18013976e  js      loc_180139986
0x180139774  mov     r9, [rbp+47h+var_C0]
0x180139778  mov     r8, r15
0x18013977b  mov     rdx, [rbp+47h+var_80]
0x18013977f  add     r9, 20h ; ' '
0x180139783  mov     dword ptr [rsp+120h+var_F0], 2
0x18013978b  mov     rcx, r13
0x18013978e  mov     dword ptr [rsp+120h+var_F8], r14d
0x180139793  mov     dword ptr [rsp+120h+ReturnLength], 1F0003h
0x18013979b  call    ZwDuplicateObject
0x1801397a0  mov     ebx, eax
0x1801397a2  test    eax, eax
0x1801397a4  js      loc_180139986
0x1801397aa  mov     r9, [rbp+47h+var_C0]
0x1801397ae  mov     r8, r15
0x1801397b1  mov     rdx, [rbp+47h+var_A8]
0x1801397b5  add     r9, 28h ; '('
0x1801397b9  mov     dword ptr [rsp+120h+var_F0], 2
0x1801397c1  mov     rcx, r13
0x1801397c4  mov     dword ptr [rsp+120h+var_F8], r14d
0x1801397c9  mov     dword ptr [rsp+120h+ReturnLength], 1F0003h
0x1801397d1  call    ZwDuplicateObject
0x1801397d6  mov     ebx, eax
0x1801397d8  test    eax, eax
0x1801397da  js      loc_180139986
0x1801397e0  test    r12, r12
0x1801397e3  jz      short loc_18013981A
0x1801397e5  mov     r9, [rbp+47h+var_C0]
0x1801397e9  mov     r8, r15
0x1801397ec  mov     dword ptr [rsp+120h+var_F0], 2
0x1801397f4  add     r9, 30h ; '0'
0x1801397f8  mov     dword ptr [rsp+120h+var_F8], r14d
0x1801397fd  mov     rdx, r12
0x180139800  mov     rcx, r13
0x180139803  mov     dword ptr [rsp+120h+ReturnLength], 1F0003h
0x18013980b  call    ZwDuplicateObject
0x180139810  mov     ebx, eax
0x180139812  test    eax, eax
0x180139814  js      loc_180139986
0x18013981a  nop
0x18013981b  mov     [rsp+120h+var_D0], r14
0x180139820  mov     rax, [rbp+47h+var_C0]
0x180139824  xor     r9d, r9d
0x180139827  mov     rcx, [rbp+47h+var_B8]
0x18013982b  xor     edx, edx
0x18013982d  movups  xmm0, xmmword ptr [rax]
0x180139830  lea     r12d, [r9+2]
0x180139834  mov     r8d, r12d
0x180139837  movups  xmmword ptr [rcx], xmm0
0x18013983a  movups  xmm1, xmmword ptr [rax+10h]
0x18013983e  movups  xmmword ptr [rcx+10h], xmm1
0x180139842  movups  xmm0, xmmword ptr [rax+20h]
0x180139846  movups  xmmword ptr [rcx+20h], xmm0
0x18013984a  movups  xmm1, xmmword ptr [rax+30h]
0x18013984e  movups  xmmword ptr [rcx+30h], xmm1
0x180139852  movups  xmm0, xmmword ptr [rax+40h]
0x180139856  movups  xmmword ptr [rcx+40h], xmm0
0x18013985a  movsd   xmm1, qword ptr [rax+50h]
0x18013985f  lea     rax, [rbp+47h+Handle]
0x180139863  mov     [rsp+120h+var_D8], rax
0x180139868  movsd   qword ptr [rcx+50h], xmm1
0x18013986d  nop
0x18013986e  mov     rax, [rbp+47h+var_90]
0x180139872  mov     rcx, r15
0x180139875  mov     [rsp+120h+var_E0], rax
0x18013987a  lea     rax, RtlpProcessReflectionStartup
0x180139881  mov     [rsp+120h+var_E8], rax
0x180139886  mov     [rsp+120h+var_F8], r14
0x18013988b  mov     [rsp+120h+ReturnLength], r14
0x180139890  call    RtlpCreateUserThreadEx
0x180139895  mov     rsi, [rbp+47h+Handle]
0x180139899  mov     ebx, eax
0x18013989b  test    eax, eax
0x18013989d  js      loc_180139986
0x1801398a3  test    rdi, rdi
0x1801398a6  jz      loc_180139986
0x1801398ac  mov     rax, [rbp+47h+var_80]
0x1801398b0  lea     r8d, [r12-1]
0x1801398b5  xor     r9d, r9d
0x1801398b8  mov     [rbp+47h+var_70], rax
0x1801398bc  lea     rdx, [rbp+47h+Handle]
0x1801398c0  mov     [rbp+47h+Handle], rsi
0x1801398c4  mov     ecx, r12d
0x1801398c7  mov     [rsp+120h+ReturnLength], r14
0x1801398cc  call    NtWaitForMultipleObjects
0x1801398d1  cmp     eax, 1
0x1801398d4  jz      short loc_1801398E0
0x1801398d6  mov     ebx, 0C0000001h
0x1801398db  jmp     loc_180139986
0x1801398e0  mov     rax, [rbp+47h+var_B8]
0x1801398e4  mov     rcx, [rax+38h]
0x1801398e8  test    rcx, rcx
0x1801398eb  jnz     short loc_1801398FC
0x1801398ed  xor     r8d, r8d; Timeout
0x1801398f0  xor     edx, edx; Alertable
0x1801398f2  mov     rcx, rsi; Handle
0x1801398f5  call    NtWaitForSingleObject
0x1801398fa  jmp     short loc_1801398D6
0x1801398fc  mov     rax, [rbp+47h+var_B8]
0x180139900  mov     ebx, 1FFFFFh
0x180139905  mov     dword ptr [rsp+120h+var_F0], r12d
0x18013990a  mov     r9, rdi
0x18013990d  mov     dword ptr [rsp+120h+var_F8], r14d
0x180139912  mov     r8, r13
0x180139915  mov     rcx, r15
0x180139918  mov     dword ptr [rsp+120h+ReturnLength], ebx
0x18013991c  mov     rdx, [rax+38h]
0x180139920  call    ZwDuplicateObject
0x180139925  test    eax, eax
  ... truncated ...
```
