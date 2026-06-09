# LdrpFindLoadedDll

- ea: `0x18002c970`
- end: `0x18002d056`
- name: `LdrpFindLoadedDll`
- size: `1766`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, service_task`

## callers

- `0x18002c2f0`
- `0x18002c4b0`

## callees

- `0x18001d490`
- `0x18001dc60`
- `0x18001eb80`
- `0x1800254e0`
- `0x1800259fc`
- `0x180027b80`
- `0x180029fc0`
- `0x18002b47c`
- `0x18002c970`
- `0x18004cef8`
- `0x1800526f0`
- `0x180052720`
- `0x180053150`
- `0x180053dd0`
- `0x180053e34`
- `0x180053f30`
- `0x180054000`
- `0x1800be6e0`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x18002cd29`: `LdrpFindLoadedDllInternal`
- `0x18002cd57`: `LdrpFindLoadedDllInternal`

## pseudocode

```c
__int64 __fastcall LdrpFindLoadedDll(unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  int v6; // edi
  int ArgList; // ebx
  int v9; // r14d
  int v10; // ebx
  __int64 v11; // rdx
  int v12; // r15d
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // r13
  __int64 v21; // rcx
  int v22; // ebx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  int v28; // r15d
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // r13
  char *v34; // rax
  int v35; // r9d
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  int LoadedDllByMappingFile; // eax
  int v45; // eax
  int v46; // ebx
  __int64 v47; // rdx
  char *v48; // rax
  int v49; // r9d
  char *v50; // rax
  int v51; // r9d
  __int64 v52; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v53[2]; // [rsp+60h] [rbp-A8h] BYREF
  int v54; // [rsp+70h] [rbp-98h]
  _OWORD v55[2]; // [rsp+78h] [rbp-90h] BYREF
  __m128i v56; // [rsp+98h] [rbp-70h] BYREF
  __int16 v57; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v58[254]; // [rsp+AAh] [rbp-5Eh] BYREF
  __m128i v59; // [rsp+1A8h] [rbp+A0h] BYREF
  _WORD v60[128]; // [rsp+1B8h] [rbp+B0h] BYREF

  memset_thunk_772440563353939046(v58, 0, 0xFEu);
  v56.m128i_i64[0] = 0x1000000;
  v52 = 0;
  v56.m128i_i64[1] = (__int64)&v57;
  *a3 = 0;
  v57 = 0;
  v6 = 0;
  ArgList = LdrpPreprocessDllName(a1, (unsigned __int16 *)&v56, 0, (_DWORD *)&v52 + 1);
  if ( ArgList < 0 )
    goto LABEL_2;
  v9 = HIDWORD(v52);
  v55[0] = 0;
  memset_thunk_772440563353939046(&v59, 0, 0x110u);
  *a3 = 0;
  if ( (v9 & 0x20) != 0 )
  {
    v55[0] = 0;
    v22 = LdrpHashUnicodeString(&v56);
    RtlAcquireSRWLockShared(&LdrpModuleDatatableLock);
    ArgList = LdrpFindLoadedDllByNameLockHeld((unsigned int)&v56, 0, v9, (_DWORD)a3, v22);
    if ( ArgList < 0 )
    {
      RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v23);
      v28 = 0;
    }
    else
    {
      v6 = *(_DWORD *)(*(_QWORD *)(*a3 + 152LL) + 56LL);
      LODWORD(v52) = v6;
      RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v23);
      v28 = 1;
    }
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v25, v24, v26, v27) )
      v33 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v33 = 2147353476;
    if ( *(_BYTE *)v33 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
    {
      v34 = (unsigned int)RtlGetCurrentServiceSessionId(v30, v29, v31, v32)
          ? (char *)NtCurrentPeb()->SharedData + 555
          : (char *)2147353477;
      if ( (*v34 & 0x20) != 0 )
      {
        v35 = 0;
        if ( !v28 )
          v35 = 3;
        LdrpLogEtwEvent(5280, 0, 0, v35, (__int64)&v56, 0);
      }
    }
    goto LABEL_40;
  }
  v54 = v9 & 0x200;
  if ( (v9 & 0x200) != 0 )
  {
    *(_OWORD *)v53 = 0;
    LdrpGetBaseNameFromFullName(&v56, v53);
    v10 = LdrpHashUnicodeString(v53);
    RtlAcquireSRWLockShared(&LdrpModuleDatatableLock);
    ArgList = LdrpFindLoadedDllByNameLockHeld((unsigned int)v53, (unsigned int)&v56, v9, (_DWORD)a3, v10);
    v12 = 1;
    if ( ArgList < 0 )
    {
      RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v11);
      HIDWORD(v52) = 0;
    }
    else
    {
      v6 = *(_DWORD *)(*(_QWORD *)(*a3 + 152LL) + 56LL);
      LODWORD(v52) = v6;
      RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v11);
      HIDWORD(v52) = 1;
    }
    v20 = 2147353476;
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v14, v13, v15, v16) )
      v21 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v21 = 2147353476;
    if ( *(_BYTE *)v21 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
    {
      v48 = (unsigned int)RtlGetCurrentServiceSessionId(v21, v17, v18, v19)
          ? (char *)NtCurrentPeb()->SharedData + 555
          : (char *)2147353477;
      if ( (*v48 & 0x20) != 0 )
      {
        v49 = 0;
        if ( !HIDWORD(v52) )
          v49 = 3;
        LdrpLogEtwEvent(5280, 0, 0, v49, (__int64)&v56, 0);
      }
    }
    if ( ArgList >= 0 )
      goto LABEL_40;
  }
  else
  {
    v12 = 1;
    v20 = 2147353476;
  }
  v59.m128i_i32[0] = 0x1000000;
  v59.m128i_i64[1] = (__int64)v60;
  v60[0] = 0;
  *(_OWORD *)v53 = 0;
  if ( v54 )
    v45 = LdrpResolveDllName(&v56, &v59, (__int64)v55, v53, v9);
  else
    v45 = LdrpSearchPath((unsigned __int16 *)&v56, a2, 0, 0, &v59, (__int64)v55, (unsigned __int16 *)v53, 0, 0);
  ArgList = v45;
  if ( v45 >= 0 )
  {
    v55[1] = 0;
    v46 = LdrpHashUnicodeString(v55);
    RtlAcquireSRWLockShared(&LdrpModuleDatatableLock);
    ArgList = LdrpFindLoadedDllByNameLockHeld((unsigned int)v55, (unsigned int)v53, v9, (_DWORD)a3, v46);
    if ( ArgList >= 0 )
    {
      v6 = *(_DWORD *)(*(_QWORD *)(*a3 + 152LL) + 56LL);
      LODWORD(v52) = v6;
      RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v47);
    }
    else
    {
      RtlReleaseSRWLockShared(&LdrpModuleDatatableLock, v47);
      v12 = 0;
    }
    if ( (unsigned int)RtlGetCurrentServiceSessionId(v37, v36, v38, v39) )
      v20 = (__int64)NtCurrentPeb()->SharedData + 554;
    if ( *(_BYTE *)v20 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
    {
      v50 = (unsigned int)RtlGetCurrentServiceSessionId(v41, v40, v42, v43)
          ? (char *)NtCurrentPeb()->SharedData + 555
          : (char *)2147353477;
      if ( (*v50 & 0x20) != 0 )
      {
        v51 = 0;
        if ( !v12 )
          v51 = 3;
        LdrpLogEtwEvent(5280, 0, 0, v51, (__int64)v53, 0);
      }
    }
    if ( ArgList == -1073741515 )
    {
      LoadedDllByMappingFile = LdrpFindLoadedDllByMappingFile(&v59, a3, &v52);
      v6 = v52;
      ArgList = LoadedDllByMappingFile;
    }
  }
  if ( v53[1] )
    RtlpSysVolFree(v53[1]);
  if ( v60 != (_WORD *)v59.m128i_i64[1] )
    RtlpSysVolFree(v59.m128i_i64[1]);
  v59.m128i_i32[0] = 0x1000000;
  v59.m128i_i64[1] = (__int64)v60;
  v60[0] = 0;
LABEL_40:
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrfind.c",
    482,
    (int)"LdrpFindLoadedDllInternal",
    4,
    "Status: 0x%08lx\n",
    ArgList);
  LdrpLogInternal((int)"minkernel\\ldr\\ldrfind.c", 483, (int)"LdrpFindLoadedDllInternal", 6, "%x\n", ArgList);
  if ( ArgList >= 0 && v6 < 6 && (NtCurrentTeb()->SameTebFlags & 0x1000) == 0 )
  {
    LdrpDereferenceModule(*a3);
    *a3 = 0;
    LdrpDrainWorkQueue(0);
    ArgList = LdrpFindLoadedDllInternal((char)&v56, v9);
    LdrpDropLastInProgressCount();
    if ( ArgList >= 0 && (_DWORD)v52 != 9 )
    {
      LdrpDereferenceModule(*a3);
      *a3 = 0;
      ArgList = -1073741515;
    }
  }
LABEL_2:
  if ( &v57 != (__int16 *)v56.m128i_i64[1] )
    RtlpSysVolFree(v56.m128i_i64[1]);
  return (unsigned int)ArgList;
}

```

## disassembly

```asm
0x18002c970  mov     r11, rsp
0x18002c973  push    rbp
0x18002c974  push    rbx
0x18002c975  lea     rbp, [r11-1F8h]
0x18002c97c  sub     rsp, 2E8h
0x18002c983  mov     rax, cs:__security_cookie
0x18002c98a  xor     rax, rsp
0x18002c98d  mov     [rbp+1F0h+var_40], rax
0x18002c994  mov     [r11+20h], rsi
0x18002c998  mov     rbx, rcx
0x18002c99b  mov     [r11-18h], rdi
0x18002c99f  lea     rcx, [rbp+1F0h+var_24E]; void *
0x18002c9a3  mov     [r11-20h], r12
0x18002c9a7  mov     rsi, r8
0x18002c9aa  mov     r12, rdx
0x18002c9ad  mov     [r11-28h], r13
0x18002c9b1  xor     eax, eax
0x18002c9b3  xor     edx, edx; Val
0x18002c9b5  mov     r8d, 0FEh; Size
0x18002c9bb  mov     [rbp+1F0h+var_25C], eax
0x18002c9be  call    memset$thunk$772440563353939046
0x18002c9c3  xor     r13d, r13d
0x18002c9c6  mov     dword ptr [rbp+1F0h+var_260], 1000000h
0x18002c9cd  lea     rax, [rbp+1F0h+var_250]
0x18002c9d1  mov     dword ptr [rsp+2F0h+var_2A0], r13d
0x18002c9d6  lea     r9, [rsp+2F0h+var_2A0+4]
0x18002c9db  mov     [rbp+1F0h+var_258], rax
0x18002c9df  xor     r8d, r8d
0x18002c9e2  mov     dword ptr [rsp+2F0h+var_2A0+4], r13d
0x18002c9e7  lea     rdx, [rbp+1F0h+var_260]
0x18002c9eb  mov     [rsi], r13
0x18002c9ee  mov     rcx, rbx
0x18002c9f1  mov     [rbp+1F0h+var_250], r13w
0x18002c9f6  mov     edi, r13d
0x18002c9f9  call    LdrpPreprocessDllName
0x18002c9fe  mov     ebx, eax
0x18002ca00  test    eax, eax
0x18002ca02  jns     short loc_18002CA52
0x18002ca04  mov     rcx, [rbp+1F0h+var_258]
0x18002ca08  lea     rax, [rbp+1F0h+var_250]
0x18002ca0c  mov     r13, [rsp+2F0h+var_20]
0x18002ca14  mov     r12, [rsp+2F0h+var_18]
0x18002ca1c  mov     rdi, [rsp+2E0h]
0x18002ca24  mov     rsi, [rsp+2F0h+arg_18]
0x18002ca2c  cmp     rax, rcx
0x18002ca2f  jz      short loc_18002CA36
0x18002ca31  call    RtlpSysVolFree
0x18002ca36  mov     eax, ebx
0x18002ca38  mov     rcx, [rbp+1F0h+var_40]
0x18002ca3f  xor     rcx, rsp; StackCookie
0x18002ca42  call    __security_check_cookie
0x18002ca47  add     rsp, 2E8h
0x18002ca4e  pop     rbx
0x18002ca4f  pop     rbp
0x18002ca50  retn
0x18002ca52  xorps   xmm0, xmm0
0x18002ca55  mov     [rsp+2F0h+var_28], r14
0x18002ca5d  mov     r14d, dword ptr [rsp+2F0h+var_2A0+4]
0x18002ca62  lea     rcx, [rbp+1F0h+var_150]; void *
0x18002ca69  xor     edx, edx; Val
0x18002ca6b  mov     [rsp+2F0h+var_30], r15
0x18002ca73  mov     r8d, 110h; Size
0x18002ca79  movups  xmmword ptr [rsp+2F0h+var_288+8], xmm0
0x18002ca7e  call    memset$thunk$772440563353939046
0x18002ca83  mov     [rsi], r13
0x18002ca86  test    r14b, 20h
0x18002ca8a  jnz     loc_18002CB58
0x18002ca90  mov     eax, r14d
0x18002ca93  and     eax, 200h
0x18002ca98  mov     dword ptr [rsp+2F0h+var_288], eax
0x18002ca9c  jz      loc_18002CD91
0x18002caa2  xorps   xmm0, xmm0
0x18002caa5  lea     rdx, [rsp+2F0h+var_2A0+8]
0x18002caaa  lea     rcx, [rbp+1F0h+var_260]
0x18002caae  movups  xmmword ptr [rsp+2F0h+var_2A0+8], xmm0
0x18002cab3  call    LdrpGetBaseNameFromFullName
0x18002cab8  lea     rcx, [rsp+2F0h+var_2A0+8]
0x18002cabd  call    LdrpHashUnicodeString
0x18002cac2  lea     rcx, LdrpModuleDatatableLock
0x18002cac9  mov     ebx, eax
0x18002cacb  call    RtlAcquireSRWLockShared
0x18002cad0  mov     r9, rsi
0x18002cad3  mov     dword ptr [rsp+2F0h+Format], ebx
0x18002cad7  mov     r8d, r14d
0x18002cada  lea     rdx, [rbp+1F0h+var_260]
0x18002cade  lea     rcx, [rsp+2F0h+var_2A0+8]
0x18002cae3  call    LdrpFindLoadedDllByNameLockHeld
0x18002cae8  mov     ebx, eax
0x18002caea  mov     r15d, 1
0x18002caf0  test    eax, eax
0x18002caf2  js      loc_18002CE4F
0x18002caf8  mov     rax, [rsi]
0x18002cafb  mov     rcx, [rax+98h]
0x18002cb02  mov     edi, [rcx+38h]
0x18002cb05  lea     rcx, LdrpModuleDatatableLock
0x18002cb0c  mov     dword ptr [rsp+2F0h+var_2A0], edi
0x18002cb10  call    RtlReleaseSRWLockShared
0x18002cb15  mov     dword ptr [rsp+2F0h+var_2A0+4], r15d
0x18002cb1a  call    RtlGetCurrentServiceSessionId
0x18002cb1f  mov     r13d, 7FFE0384h
0x18002cb25  test    eax, eax
0x18002cb27  jnz     loc_18002CF6B
0x18002cb2d  mov     ecx, r13d
0x18002cb30  cmp     byte ptr [rcx], 0
0x18002cb33  jz      short loc_18002CB4B
0x18002cb35  mov     rax, gs:60h
0x18002cb3e  test    byte ptr [rax+378h], 4
0x18002cb45  jnz     loc_18002CE65
0x18002cb4b  test    ebx, ebx
0x18002cb4d  jns     loc_18002CD13
0x18002cb53  jmp     loc_18002CD9D
0x18002cb58  xorps   xmm0, xmm0
0x18002cb5b  lea     rcx, [rbp+1F0h+var_260]
0x18002cb5f  movups  xmmword ptr [rsp+2F0h+var_288+8], xmm0
0x18002cb64  call    LdrpHashUnicodeString
0x18002cb69  lea     rcx, LdrpModuleDatatableLock
0x18002cb70  mov     ebx, eax
0x18002cb72  call    RtlAcquireSRWLockShared
0x18002cb77  mov     r9, rsi
0x18002cb7a  mov     dword ptr [rsp+2F0h+Format], ebx
0x18002cb7e  mov     r8d, r14d
0x18002cb81  lea     rcx, [rbp+1F0h+var_260]
0x18002cb85  xor     edx, edx
0x18002cb87  call    LdrpFindLoadedDllByNameLockHeld
0x18002cb8c  mov     ebx, eax
0x18002cb8e  test    eax, eax
0x18002cb90  js      loc_18002CC4E
0x18002cb96  mov     rax, [rsi]
0x18002cb99  mov     rcx, [rax+98h]
0x18002cba0  mov     edi, [rcx+38h]
0x18002cba3  lea     rcx, LdrpModuleDatatableLock
0x18002cbaa  mov     dword ptr [rsp+2F0h+var_2A0], edi
0x18002cbae  call    RtlReleaseSRWLockShared
0x18002cbb3  mov     r15d, 1
0x18002cbb9  call    RtlGetCurrentServiceSessionId
0x18002cbbe  test    eax, eax
0x18002cbc0  jnz     loc_18002CEC8
0x18002cbc6  mov     r13d, 7FFE0384h
0x18002cbcc  cmp     byte ptr [r13+0], 0
0x18002cbd1  jz      loc_18002CD13
0x18002cbd7  mov     rax, gs:60h
0x18002cbe0  test    byte ptr [rax+378h], 4
0x18002cbe7  jz      loc_18002CD13
0x18002cbed  call    RtlGetCurrentServiceSessionId
0x18002cbf2  test    eax, eax
0x18002cbf4  jz      loc_18002CEE4
0x18002cbfa  mov     rax, gs:60h
0x18002cc03  mov     rax, [rax+90h]
0x18002cc0a  add     rax, 22Bh
0x18002cc10  test    byte ptr [rax], 20h
0x18002cc13  jz      loc_18002CD13
0x18002cc19  xor     r9d, r9d
0x18002cc1c  mov     qword ptr [rsp+2F0h+ArgList], 0
0x18002cc25  test    r15d, r15d
0x18002cc28  mov     eax, 3
0x18002cc2d  mov     ecx, 14A0h
0x18002cc32  cmovz   r9d, eax
0x18002cc36  lea     rax, [rbp+1F0h+var_260]
0x18002cc3a  xor     r8d, r8d
0x18002cc3d  mov     [rsp+2F0h+Format], rax
0x18002cc42  xor     edx, edx
0x18002cc44  call    LdrpLogEtwEvent
0x18002cc49  jmp     loc_18002CD13
0x18002cc4e  lea     rcx, LdrpModuleDatatableLock
0x18002cc55  call    RtlReleaseSRWLockShared
0x18002cc5a  mov     r15d, r13d
0x18002cc5d  jmp     loc_18002CBB9
0x18002cc62  mov     rax, [rsi]
0x18002cc65  mov     rcx, [rax+98h]
0x18002cc6c  mov     edi, [rcx+38h]
0x18002cc6f  lea     rcx, LdrpModuleDatatableLock
0x18002cc76  mov     dword ptr [rsp+2F0h+var_2A0], edi
0x18002cc7a  call    RtlReleaseSRWLockShared
0x18002cc7f  call    RtlGetCurrentServiceSessionId
0x18002cc84  test    eax, eax
0x18002cc86  jnz     loc_18002D030
0x18002cc8c  cmp     byte ptr [r13+0], 0
0x18002cc91  jz      short loc_18002CCA9
0x18002cc93  mov     rax, gs:60h
0x18002cc9c  test    byte ptr [rax+378h], 4
0x18002cca3  jnz     loc_18002CF91
0x18002cca9  cmp     ebx, 0C0000135h
0x18002ccaf  jnz     short loc_18002CCCB
0x18002ccb1  lea     r8, [rsp+2F0h+var_2A0]
0x18002ccb6  mov     rdx, rsi
0x18002ccb9  lea     rcx, [rbp+1F0h+var_150]
0x18002ccc0  call    LdrpFindLoadedDllByMappingFile
0x18002ccc5  mov     edi, dword ptr [rsp+2F0h+var_2A0]
0x18002ccc9  mov     ebx, eax
0x18002cccb  mov     rcx, qword ptr [rsp+2F0h+var_290]
0x18002ccd0  test    rcx, rcx
0x18002ccd3  jz      short loc_18002CCDA
0x18002ccd5  call    RtlpSysVolFree
0x18002ccda  mov     rcx, [rbp+1F0h+var_148]
0x18002cce1  lea     rax, [rbp+1F0h+var_140]
0x18002cce8  cmp     rax, rcx
0x18002cceb  jz      short loc_18002CCF2
0x18002cced  call    RtlpSysVolFree
0x18002ccf2  lea     rax, [rbp+1F0h+var_140]
0x18002ccf9  mov     dword ptr [rbp+1F0h+var_150], 1000000h
0x18002cd03  mov     [rbp+1F0h+var_148], rax
0x18002cd0a  xor     eax, eax
0x18002cd0c  mov     [rbp+1F0h+var_140], ax
0x18002cd13  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x18002cd1a  mov     dword ptr [rsp+2F0h+ArgList], ebx; ArgList
0x18002cd1e  mov     r9d, 4; int
0x18002cd24  mov     [rsp+2F0h+Format], rax; Format
0x18002cd29  lea     r8, aLdrpfindloaded; "LdrpFindLoadedDllInternal"
0x18002cd30  mov     edx, 1E2h; int
0x18002cd35  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x18002cd3c  call    LdrpLogInternal
0x18002cd41  lea     rax, asc_180175AB4; "%x\n"
0x18002cd48  mov     dword ptr [rsp+2F0h+ArgList], ebx; ArgList
0x18002cd4c  mov     r9d, 6; int
0x18002cd52  mov     [rsp+2F0h+Format], rax; Format
0x18002cd57  lea     r8, aLdrpfindloaded; "LdrpFindLoadedDllInternal"
0x18002cd5e  mov     edx, 1E3h; int
0x18002cd63  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x18002cd6a  call    LdrpLogInternal
0x18002cd6f  mov     r15, [rsp+2F0h+var_30]
0x18002cd77  test    ebx, ebx
0x18002cd79  js      short loc_18002CD84
0x18002cd7b  cmp     edi, 6
0x18002cd7e  jl      loc_18002CEEE
0x18002cd84  mov     r14, [rsp+2F0h+var_28]
0x18002cd8c  jmp     loc_18002CA04
0x18002cd91  mov     r15d, 1
0x18002cd97  mov     r13d, 7FFE0384h
0x18002cd9d  lea     rax, [rbp+1F0h+var_140]
0x18002cda4  mov     dword ptr [rbp+1F0h+var_150], 1000000h
0x18002cdae  mov     [rbp+1F0h+var_148], rax
0x18002cdb5  lea     rcx, [rbp+1F0h+var_260]; ArgList
0x18002cdb9  xor     eax, eax
0x18002cdbb  xorps   xmm0, xmm0
0x18002cdbe  mov     [rbp+1F0h+var_140], ax
0x18002cdc5  movups  xmmword ptr [rsp+2F0h+var_2A0+8], xmm0
0x18002cdca  cmp     dword ptr [rsp+2F0h+var_288], eax
0x18002cdce  jz      loc_18002CFF3
0x18002cdd4  lea     r9, [rsp+2F0h+var_2A0+8]
0x18002cdd9  mov     dword ptr [rsp+2F0h+Format], r14d; int
0x18002cdde  lea     r8, [rsp+2F0h+var_288+8]
0x18002cde3  lea     rdx, [rbp+1F0h+var_150]
0x18002cdea  call    LdrpResolveDllName
0x18002cdef  mov     ebx, eax
0x18002cdf1  test    eax, eax
0x18002cdf3  js      loc_18002CCCB
0x18002cdf9  xorps   xmm0, xmm0
0x18002cdfc  lea     rcx, [rsp+2F0h+var_288+8]
0x18002ce01  movups  [rbp+1F0h+var_270], xmm0
0x18002ce05  call    LdrpHashUnicodeString
0x18002ce0a  lea     rcx, LdrpModuleDatatableLock
0x18002ce11  mov     ebx, eax
0x18002ce13  call    RtlAcquireSRWLockShared
0x18002ce18  mov     r9, rsi
0x18002ce1b  mov     dword ptr [rsp+2F0h+Format], ebx
0x18002ce1f  mov     r8d, r14d
0x18002ce22  lea     rdx, [rsp+2F0h+var_2A0+8]
0x18002ce27  lea     rcx, [rsp+2F0h+var_288+8]
0x18002ce2c  call    LdrpFindLoadedDllByNameLockHeld
0x18002ce31  mov     ebx, eax
0x18002ce33  test    eax, eax
0x18002ce35  jns     loc_18002CC62
0x18002ce3b  lea     rcx, LdrpModuleDatatableLock
0x18002ce42  call    RtlReleaseSRWLockShared
0x18002ce47  xor     r15d, r15d
0x18002ce4a  jmp     loc_18002CC7F
0x18002ce4f  lea     rcx, LdrpModuleDatatableLock
0x18002ce56  call    RtlReleaseSRWLockShared
0x18002ce5b  mov     dword ptr [rsp+2F0h+var_2A0+4], r13d
0x18002ce60  jmp     loc_18002CB1A
0x18002ce65  call    RtlGetCurrentServiceSessionId
0x18002ce6a  test    eax, eax
0x18002ce6c  jz      loc_18002CF87
0x18002ce72  mov     rax, gs:60h
0x18002ce7b  mov     rax, [rax+90h]
0x18002ce82  add     rax, 22Bh
0x18002ce88  test    byte ptr [rax], 20h
0x18002ce8b  jz      loc_18002CB4B
0x18002ce91  xor     r9d, r9d
0x18002ce94  mov     qword ptr [rsp+2F0h+ArgList], 0
0x18002ce9d  cmp     dword ptr [rsp+2F0h+var_2A0+4], r9d
0x18002cea2  mov     eax, 3
0x18002cea7  mov     ecx, 14A0h
0x18002ceac  cmovz   r9d, eax
0x18002ceb0  lea     rax, [rbp+1F0h+var_260]
0x18002ceb4  xor     r8d, r8d
0x18002ceb7  mov     [rsp+2F0h+Format], rax
0x18002cebc  xor     edx, edx
0x18002cebe  call    LdrpLogEtwEvent
0x18002cec3  jmp     loc_18002CB4B
0x18002cec8  mov     rax, gs:60h
0x18002ced1  mov     r13, [rax+90h]
0x18002ced8  add     r13, 22Ah
0x18002cedf  jmp     loc_18002CBCC
0x18002cee4  mov     eax, 7FFE0385h
0x18002cee9  jmp     loc_18002CC10
0x18002ceee  mov     rax, gs:30h
0x18002cef7  mov     ecx, 1000h
0x18002cefc  test    [rax+17EEh], cx
0x18002cf03  jnz     loc_18002CD84
  ... truncated ...
```
