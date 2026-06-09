# LdrpFindLoadedDll

- ea: `0x18002bc70`
- end: `0x18002c356`
- name: `LdrpFindLoadedDll`
- size: `1766`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, service_task`

## callers

- `0x18002b5f0`
- `0x18002b7b0`

## callees

- `0x18001d490`
- `0x18001dc60`
- `0x18001eb80`
- `0x1800254d0`
- `0x1800259ec`
- `0x180027a70`
- `0x180029eb0`
- `0x18002a770`
- `0x18002bc70`
- `0x180069af8`
- `0x18006f0d0`
- `0x18006f100`
- `0x18006fb30`
- `0x1800707b0`
- `0x180070814`
- `0x180070910`
- `0x1800709e0`
- `0x1800c29c0`
- `0x180162810`
- `0x18016f030`

## string_xrefs

- `0x18002c029`: `LdrpFindLoadedDllInternal`
- `0x18002c057`: `LdrpFindLoadedDllInternal`

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
    RtlAcquireSRWLockShared(LdrpModuleDatatableLock);
    ArgList = LdrpFindLoadedDllByNameLockHeld((unsigned int)&v56, 0, v9, (_DWORD)a3, v22);
    if ( ArgList < 0 )
    {
      RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v23);
      v28 = 0;
    }
    else
    {
      v6 = *(_DWORD *)(*(_QWORD *)(*a3 + 152LL) + 56LL);
      LODWORD(v52) = v6;
      RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v23);
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
    RtlAcquireSRWLockShared(LdrpModuleDatatableLock);
    ArgList = LdrpFindLoadedDllByNameLockHeld((unsigned int)v53, (unsigned int)&v56, v9, (_DWORD)a3, v10);
    v12 = 1;
    if ( ArgList < 0 )
    {
      RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v11);
      HIDWORD(v52) = 0;
    }
    else
    {
      v6 = *(_DWORD *)(*(_QWORD *)(*a3 + 152LL) + 56LL);
      LODWORD(v52) = v6;
      RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v11);
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
    RtlAcquireSRWLockShared(LdrpModuleDatatableLock);
    ArgList = LdrpFindLoadedDllByNameLockHeld((unsigned int)v55, (unsigned int)v53, v9, (_DWORD)a3, v46);
    if ( ArgList >= 0 )
    {
      v6 = *(_DWORD *)(*(_QWORD *)(*a3 + 152LL) + 56LL);
      LODWORD(v52) = v6;
      RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v47);
    }
    else
    {
      RtlReleaseSRWLockShared(LdrpModuleDatatableLock, v47);
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
0x18002bc70  mov     r11, rsp
0x18002bc73  push    rbp
0x18002bc74  push    rbx
0x18002bc75  lea     rbp, [r11-1F8h]
0x18002bc7c  sub     rsp, 2E8h
0x18002bc83  mov     rax, cs:__security_cookie
0x18002bc8a  xor     rax, rsp
0x18002bc8d  mov     [rbp+1F0h+var_40], rax
0x18002bc94  mov     [r11+20h], rsi
0x18002bc98  mov     rbx, rcx
0x18002bc9b  mov     [r11-18h], rdi
0x18002bc9f  lea     rcx, [rbp+1F0h+var_24E]; void *
0x18002bca3  mov     [r11-20h], r12
0x18002bca7  mov     rsi, r8
0x18002bcaa  mov     r12, rdx
0x18002bcad  mov     [r11-28h], r13
0x18002bcb1  xor     eax, eax
0x18002bcb3  xor     edx, edx; Val
0x18002bcb5  mov     r8d, 0FEh; Size
0x18002bcbb  mov     [rbp+1F0h+var_25C], eax
0x18002bcbe  call    memset$thunk$772440563353939046
0x18002bcc3  xor     r13d, r13d
0x18002bcc6  mov     dword ptr [rbp+1F0h+var_260], 1000000h
0x18002bccd  lea     rax, [rbp+1F0h+var_250]
0x18002bcd1  mov     dword ptr [rsp+2F0h+var_2A0], r13d
0x18002bcd6  lea     r9, [rsp+2F0h+var_2A0+4]
0x18002bcdb  mov     [rbp+1F0h+var_258], rax
0x18002bcdf  xor     r8d, r8d
0x18002bce2  mov     dword ptr [rsp+2F0h+var_2A0+4], r13d
0x18002bce7  lea     rdx, [rbp+1F0h+var_260]
0x18002bceb  mov     [rsi], r13
0x18002bcee  mov     rcx, rbx
0x18002bcf1  mov     [rbp+1F0h+var_250], r13w
0x18002bcf6  mov     edi, r13d
0x18002bcf9  call    LdrpPreprocessDllName
0x18002bcfe  mov     ebx, eax
0x18002bd00  test    eax, eax
0x18002bd02  jns     short loc_18002BD52
0x18002bd04  mov     rcx, [rbp+1F0h+var_258]
0x18002bd08  lea     rax, [rbp+1F0h+var_250]
0x18002bd0c  mov     r13, [rsp+2F0h+var_20]
0x18002bd14  mov     r12, [rsp+2F0h+var_18]
0x18002bd1c  mov     rdi, [rsp+2E0h]
0x18002bd24  mov     rsi, [rsp+2F0h+arg_18]
0x18002bd2c  cmp     rax, rcx
0x18002bd2f  jz      short loc_18002BD36
0x18002bd31  call    RtlpSysVolFree
0x18002bd36  mov     eax, ebx
0x18002bd38  mov     rcx, [rbp+1F0h+var_40]
0x18002bd3f  xor     rcx, rsp; StackCookie
0x18002bd42  call    __security_check_cookie
0x18002bd47  add     rsp, 2E8h
0x18002bd4e  pop     rbx
0x18002bd4f  pop     rbp
0x18002bd50  retn
0x18002bd52  xorps   xmm0, xmm0
0x18002bd55  mov     [rsp+2F0h+var_28], r14
0x18002bd5d  mov     r14d, dword ptr [rsp+2F0h+var_2A0+4]
0x18002bd62  lea     rcx, [rbp+1F0h+var_150]; void *
0x18002bd69  xor     edx, edx; Val
0x18002bd6b  mov     [rsp+2F0h+var_30], r15
0x18002bd73  mov     r8d, 110h; Size
0x18002bd79  movups  xmmword ptr [rsp+2F0h+var_288+8], xmm0
0x18002bd7e  call    memset$thunk$772440563353939046
0x18002bd83  mov     [rsi], r13
0x18002bd86  test    r14b, 20h
0x18002bd8a  jnz     loc_18002BE58
0x18002bd90  mov     eax, r14d
0x18002bd93  and     eax, 200h
0x18002bd98  mov     dword ptr [rsp+2F0h+var_288], eax
0x18002bd9c  jz      loc_18002C091
0x18002bda2  xorps   xmm0, xmm0
0x18002bda5  lea     rdx, [rsp+2F0h+var_2A0+8]
0x18002bdaa  lea     rcx, [rbp+1F0h+var_260]
0x18002bdae  movups  xmmword ptr [rsp+2F0h+var_2A0+8], xmm0
0x18002bdb3  call    LdrpGetBaseNameFromFullName
0x18002bdb8  lea     rcx, [rsp+2F0h+var_2A0+8]
0x18002bdbd  call    LdrpHashUnicodeString
0x18002bdc2  lea     rcx, LdrpModuleDatatableLock
0x18002bdc9  mov     ebx, eax
0x18002bdcb  call    RtlAcquireSRWLockShared
0x18002bdd0  mov     r9, rsi
0x18002bdd3  mov     dword ptr [rsp+2F0h+Format], ebx
0x18002bdd7  mov     r8d, r14d
0x18002bdda  lea     rdx, [rbp+1F0h+var_260]
0x18002bdde  lea     rcx, [rsp+2F0h+var_2A0+8]
0x18002bde3  call    LdrpFindLoadedDllByNameLockHeld
0x18002bde8  mov     ebx, eax
0x18002bdea  mov     r15d, 1
0x18002bdf0  test    eax, eax
0x18002bdf2  js      loc_18002C14F
0x18002bdf8  mov     rax, [rsi]
0x18002bdfb  mov     rcx, [rax+98h]
0x18002be02  mov     edi, [rcx+38h]
0x18002be05  lea     rcx, LdrpModuleDatatableLock
0x18002be0c  mov     dword ptr [rsp+2F0h+var_2A0], edi
0x18002be10  call    RtlReleaseSRWLockShared
0x18002be15  mov     dword ptr [rsp+2F0h+var_2A0+4], r15d
0x18002be1a  call    RtlGetCurrentServiceSessionId
0x18002be1f  mov     r13d, 7FFE0384h
0x18002be25  test    eax, eax
0x18002be27  jnz     loc_18002C26B
0x18002be2d  mov     ecx, r13d
0x18002be30  cmp     byte ptr [rcx], 0
0x18002be33  jz      short loc_18002BE4B
0x18002be35  mov     rax, gs:60h
0x18002be3e  test    byte ptr [rax+378h], 4
0x18002be45  jnz     loc_18002C165
0x18002be4b  test    ebx, ebx
0x18002be4d  jns     loc_18002C013
0x18002be53  jmp     loc_18002C09D
0x18002be58  xorps   xmm0, xmm0
0x18002be5b  lea     rcx, [rbp+1F0h+var_260]
0x18002be5f  movups  xmmword ptr [rsp+2F0h+var_288+8], xmm0
0x18002be64  call    LdrpHashUnicodeString
0x18002be69  lea     rcx, LdrpModuleDatatableLock
0x18002be70  mov     ebx, eax
0x18002be72  call    RtlAcquireSRWLockShared
0x18002be77  mov     r9, rsi
0x18002be7a  mov     dword ptr [rsp+2F0h+Format], ebx
0x18002be7e  mov     r8d, r14d
0x18002be81  lea     rcx, [rbp+1F0h+var_260]
0x18002be85  xor     edx, edx
0x18002be87  call    LdrpFindLoadedDllByNameLockHeld
0x18002be8c  mov     ebx, eax
0x18002be8e  test    eax, eax
0x18002be90  js      loc_18002BF4E
0x18002be96  mov     rax, [rsi]
0x18002be99  mov     rcx, [rax+98h]
0x18002bea0  mov     edi, [rcx+38h]
0x18002bea3  lea     rcx, LdrpModuleDatatableLock
0x18002beaa  mov     dword ptr [rsp+2F0h+var_2A0], edi
0x18002beae  call    RtlReleaseSRWLockShared
0x18002beb3  mov     r15d, 1
0x18002beb9  call    RtlGetCurrentServiceSessionId
0x18002bebe  test    eax, eax
0x18002bec0  jnz     loc_18002C1C8
0x18002bec6  mov     r13d, 7FFE0384h
0x18002becc  cmp     byte ptr [r13+0], 0
0x18002bed1  jz      loc_18002C013
0x18002bed7  mov     rax, gs:60h
0x18002bee0  test    byte ptr [rax+378h], 4
0x18002bee7  jz      loc_18002C013
0x18002beed  call    RtlGetCurrentServiceSessionId
0x18002bef2  test    eax, eax
0x18002bef4  jz      loc_18002C1E4
0x18002befa  mov     rax, gs:60h
0x18002bf03  mov     rax, [rax+90h]
0x18002bf0a  add     rax, 22Bh
0x18002bf10  test    byte ptr [rax], 20h
0x18002bf13  jz      loc_18002C013
0x18002bf19  xor     r9d, r9d
0x18002bf1c  mov     qword ptr [rsp+2F0h+ArgList], 0
0x18002bf25  test    r15d, r15d
0x18002bf28  mov     eax, 3
0x18002bf2d  mov     ecx, 14A0h
0x18002bf32  cmovz   r9d, eax
0x18002bf36  lea     rax, [rbp+1F0h+var_260]
0x18002bf3a  xor     r8d, r8d
0x18002bf3d  mov     [rsp+2F0h+Format], rax
0x18002bf42  xor     edx, edx
0x18002bf44  call    LdrpLogEtwEvent
0x18002bf49  jmp     loc_18002C013
0x18002bf4e  lea     rcx, LdrpModuleDatatableLock
0x18002bf55  call    RtlReleaseSRWLockShared
0x18002bf5a  mov     r15d, r13d
0x18002bf5d  jmp     loc_18002BEB9
0x18002bf62  mov     rax, [rsi]
0x18002bf65  mov     rcx, [rax+98h]
0x18002bf6c  mov     edi, [rcx+38h]
0x18002bf6f  lea     rcx, LdrpModuleDatatableLock
0x18002bf76  mov     dword ptr [rsp+2F0h+var_2A0], edi
0x18002bf7a  call    RtlReleaseSRWLockShared
0x18002bf7f  call    RtlGetCurrentServiceSessionId
0x18002bf84  test    eax, eax
0x18002bf86  jnz     loc_18002C330
0x18002bf8c  cmp     byte ptr [r13+0], 0
0x18002bf91  jz      short loc_18002BFA9
0x18002bf93  mov     rax, gs:60h
0x18002bf9c  test    byte ptr [rax+378h], 4
0x18002bfa3  jnz     loc_18002C291
0x18002bfa9  cmp     ebx, 0C0000135h
0x18002bfaf  jnz     short loc_18002BFCB
0x18002bfb1  lea     r8, [rsp+2F0h+var_2A0]
0x18002bfb6  mov     rdx, rsi
0x18002bfb9  lea     rcx, [rbp+1F0h+var_150]
0x18002bfc0  call    LdrpFindLoadedDllByMappingFile
0x18002bfc5  mov     edi, dword ptr [rsp+2F0h+var_2A0]
0x18002bfc9  mov     ebx, eax
0x18002bfcb  mov     rcx, qword ptr [rsp+2F0h+var_290]
0x18002bfd0  test    rcx, rcx
0x18002bfd3  jz      short loc_18002BFDA
0x18002bfd5  call    RtlpSysVolFree
0x18002bfda  mov     rcx, [rbp+1F0h+var_148]
0x18002bfe1  lea     rax, [rbp+1F0h+var_140]
0x18002bfe8  cmp     rax, rcx
0x18002bfeb  jz      short loc_18002BFF2
0x18002bfed  call    RtlpSysVolFree
0x18002bff2  lea     rax, [rbp+1F0h+var_140]
0x18002bff9  mov     dword ptr [rbp+1F0h+var_150], 1000000h
0x18002c003  mov     [rbp+1F0h+var_148], rax
0x18002c00a  xor     eax, eax
0x18002c00c  mov     [rbp+1F0h+var_140], ax
0x18002c013  lea     rax, aStatus0x08lx; "Status: 0x%08lx\n"
0x18002c01a  mov     dword ptr [rsp+2F0h+ArgList], ebx; ArgList
0x18002c01e  mov     r9d, 4; int
0x18002c024  mov     [rsp+2F0h+Format], rax; Format
0x18002c029  lea     r8, aLdrpfindloaded; "LdrpFindLoadedDllInternal"
0x18002c030  mov     edx, 1E2h; int
0x18002c035  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x18002c03c  call    LdrpLogInternal
0x18002c041  lea     rax, asc_180175AB4; "%x\n"
0x18002c048  mov     dword ptr [rsp+2F0h+ArgList], ebx; ArgList
0x18002c04c  mov     r9d, 6; int
0x18002c052  mov     [rsp+2F0h+Format], rax; Format
0x18002c057  lea     r8, aLdrpfindloaded; "LdrpFindLoadedDllInternal"
0x18002c05e  mov     edx, 1E3h; int
0x18002c063  lea     rcx, aMinkernelLdrLd_6; "minkernel\\ldr\\ldrfind.c"
0x18002c06a  call    LdrpLogInternal
0x18002c06f  mov     r15, [rsp+2F0h+var_30]
0x18002c077  test    ebx, ebx
0x18002c079  js      short loc_18002C084
0x18002c07b  cmp     edi, 6
0x18002c07e  jl      loc_18002C1EE
0x18002c084  mov     r14, [rsp+2F0h+var_28]
0x18002c08c  jmp     loc_18002BD04
0x18002c091  mov     r15d, 1
0x18002c097  mov     r13d, 7FFE0384h
0x18002c09d  lea     rax, [rbp+1F0h+var_140]
0x18002c0a4  mov     dword ptr [rbp+1F0h+var_150], 1000000h
0x18002c0ae  mov     [rbp+1F0h+var_148], rax
0x18002c0b5  lea     rcx, [rbp+1F0h+var_260]; ArgList
0x18002c0b9  xor     eax, eax
0x18002c0bb  xorps   xmm0, xmm0
0x18002c0be  mov     [rbp+1F0h+var_140], ax
0x18002c0c5  movups  xmmword ptr [rsp+2F0h+var_2A0+8], xmm0
0x18002c0ca  cmp     dword ptr [rsp+2F0h+var_288], eax
0x18002c0ce  jz      loc_18002C2F3
0x18002c0d4  lea     r9, [rsp+2F0h+var_2A0+8]
0x18002c0d9  mov     dword ptr [rsp+2F0h+Format], r14d; int
0x18002c0de  lea     r8, [rsp+2F0h+var_288+8]
0x18002c0e3  lea     rdx, [rbp+1F0h+var_150]
0x18002c0ea  call    LdrpResolveDllName
0x18002c0ef  mov     ebx, eax
0x18002c0f1  test    eax, eax
0x18002c0f3  js      loc_18002BFCB
0x18002c0f9  xorps   xmm0, xmm0
0x18002c0fc  lea     rcx, [rsp+2F0h+var_288+8]
0x18002c101  movups  [rbp+1F0h+var_270], xmm0
0x18002c105  call    LdrpHashUnicodeString
0x18002c10a  lea     rcx, LdrpModuleDatatableLock
0x18002c111  mov     ebx, eax
0x18002c113  call    RtlAcquireSRWLockShared
0x18002c118  mov     r9, rsi
0x18002c11b  mov     dword ptr [rsp+2F0h+Format], ebx
0x18002c11f  mov     r8d, r14d
0x18002c122  lea     rdx, [rsp+2F0h+var_2A0+8]
0x18002c127  lea     rcx, [rsp+2F0h+var_288+8]
0x18002c12c  call    LdrpFindLoadedDllByNameLockHeld
0x18002c131  mov     ebx, eax
0x18002c133  test    eax, eax
0x18002c135  jns     loc_18002BF62
0x18002c13b  lea     rcx, LdrpModuleDatatableLock
0x18002c142  call    RtlReleaseSRWLockShared
0x18002c147  xor     r15d, r15d
0x18002c14a  jmp     loc_18002BF7F
0x18002c14f  lea     rcx, LdrpModuleDatatableLock
0x18002c156  call    RtlReleaseSRWLockShared
0x18002c15b  mov     dword ptr [rsp+2F0h+var_2A0+4], r13d
0x18002c160  jmp     loc_18002BE1A
0x18002c165  call    RtlGetCurrentServiceSessionId
0x18002c16a  test    eax, eax
0x18002c16c  jz      loc_18002C287
0x18002c172  mov     rax, gs:60h
0x18002c17b  mov     rax, [rax+90h]
0x18002c182  add     rax, 22Bh
0x18002c188  test    byte ptr [rax], 20h
0x18002c18b  jz      loc_18002BE4B
0x18002c191  xor     r9d, r9d
0x18002c194  mov     qword ptr [rsp+2F0h+ArgList], 0
0x18002c19d  cmp     dword ptr [rsp+2F0h+var_2A0+4], r9d
0x18002c1a2  mov     eax, 3
0x18002c1a7  mov     ecx, 14A0h
0x18002c1ac  cmovz   r9d, eax
0x18002c1b0  lea     rax, [rbp+1F0h+var_260]
0x18002c1b4  xor     r8d, r8d
0x18002c1b7  mov     [rsp+2F0h+Format], rax
0x18002c1bc  xor     edx, edx
0x18002c1be  call    LdrpLogEtwEvent
0x18002c1c3  jmp     loc_18002BE4B
0x18002c1c8  mov     rax, gs:60h
0x18002c1d1  mov     r13, [rax+90h]
0x18002c1d8  add     r13, 22Ah
0x18002c1df  jmp     loc_18002BECC
0x18002c1e4  mov     eax, 7FFE0385h
0x18002c1e9  jmp     loc_18002BF10
0x18002c1ee  mov     rax, gs:30h
0x18002c1f7  mov     ecx, 1000h
0x18002c1fc  test    [rax+17EEh], cx
0x18002c203  jnz     loc_18002C084
  ... truncated ...
```
