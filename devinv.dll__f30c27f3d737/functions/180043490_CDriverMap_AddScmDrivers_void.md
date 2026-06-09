# CDriverMap::AddScmDrivers(void)

- ea: `0x180043490`
- end: `0x1800438c5`
- name: `?AddScmDrivers@CDriverMap@@QEAAJXZ`
- size: `1077`
- prototype: `__int64 __fastcall(CDriverMap *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task`

## callers

- `0x180044f20`

## callees

- `0x180006210`
- `0x18000624c`
- `0x180006d02`
- `0x180006ec4`
- `0x180007014`
- `0x180043490`
- `0x1800438cc`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043717`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x1800434f6`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180043618`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x1800434f6`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x180043618`

## string_xrefs

- `0x18004352c`: `0x%08x Failed to enumerate services from SCM manager`
- `0x18004372c`: `0x%08x Failed to enumerate services from SCM manager`
- `0x180043805`: `0x%08x Failed to add service (%ws) to service map`
- `0x180043863`: `0x%08x Failed to add service (%ws) to service map`
- `0x180043899`: `0x%08x Failed to add service (%ws) to service map`

## pseudocode

```c
__int64 __fastcall CDriverMap::AddScmDrivers(CDriverMap *this)
{
  SC_HANDLE v2; // rcx
  signed int v3; // eax
  unsigned int v4; // ebx
  FILE *v5; // rax
  FILE *v6; // rax
  FILE *v7; // rax
  SC_HANDLE v8; // rcx
  BYTE *v9; // rax
  BYTE *v10; // rsi
  FILE *v11; // rax
  FILE *v12; // rax
  FILE *v13; // rax
  signed int LastError; // eax
  FILE *v16; // rax
  FILE *v17; // rax
  FILE *v18; // rax
  DWORD i; // r14d
  __int64 v20; // r15
  int v21; // eax
  unsigned int v22; // r12d
  FILE *v23; // rax
  __int64 v24; // rbx
  FILE *v25; // rax
  FILE *v26; // rax
  LPBYTE lpServices; // [rsp+20h] [rbp-30h]
  size_t Size; // [rsp+90h] [rbp+40h] BYREF
  DWORD ServicesReturned; // [rsp+98h] [rbp+48h] BYREF
  DWORD ResumeHandle; // [rsp+A0h] [rbp+50h] BYREF

  v2 = (SC_HANDLE)*((_QWORD *)this + 21);
  LODWORD(Size) = 0;
  ServicesReturned = 0;
  ResumeHandle = 0;
  if ( EnumServicesStatusExW(
         v2,
         SC_ENUM_PROCESS_INFO,
         0xBu,
         3u,
         0,
         0,
         (LPDWORD)&Size,
         &ServicesReturned,
         &ResumeHandle,
         0)
    || GetLastError() == 234 )
  {
    while ( 1 )
    {
      LODWORD(Size) = 2 * Size;
      v9 = (BYTE *)operator new[]((unsigned int)Size, (const struct std::nothrow_t *)std::nothrow);
      v10 = v9;
      if ( !v9 )
      {
        v4 = -2147024888;
        AslLogCallPrintf(2, "CDriverMap::AddScmDrivers", 881, "Out of memory");
        if ( EnableDevInvStdErrLog )
        {
          v11 = o___acrt_iob_func_0(2u);
          fprintf(v11, "Error: %s, %u: ", "CDriverMap::AddScmDrivers", 881);
          v12 = o___acrt_iob_func_0(2u);
          fprintf(v12, "Out of memory");
          v13 = o___acrt_iob_func_0(2u);
          fprintf(v13, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "Out of memory");
        goto LABEL_17;
      }
      memset_0(v9, 0, (unsigned int)Size);
      v8 = (SC_HANDLE)*((_QWORD *)this + 21);
      ResumeHandle = 0;
      if ( EnumServicesStatusExW(
             v8,
             SC_ENUM_PROCESS_INFO,
             0xBu,
             3u,
             v10,
             Size,
             (LPDWORD)&Size,
             &ServicesReturned,
             &ResumeHandle,
             0) )
      {
        break;
      }
      if ( GetLastError() != 234 )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        AslLogCallPrintf(
          2,
          "CDriverMap::AddScmDrivers",
          919,
          "0x%08x Failed to enumerate services from SCM manager",
          v4);
        if ( EnableDevInvStdErrLog )
        {
          v16 = o___acrt_iob_func_0(2u);
          fprintf(v16, "Error: %s, %u: ", "CDriverMap::AddScmDrivers", 919);
          v17 = o___acrt_iob_func_0(2u);
          fprintf(v17, "0x%08x Failed to enumerate services from SCM manager", v4);
          v18 = o___acrt_iob_func_0(2u);
          fprintf(v18, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(0x2000000, "0x%08x Failed to enumerate services from SCM manager", v4);
        goto LABEL_17;
      }
      operator delete(v10);
    }
    for ( i = 0; i < ServicesReturned; ++i )
    {
      v20 = 56LL * i;
      v21 = CDriverMap::AddService(this, *(const unsigned __int16 **)&v10[v20], *(_DWORD *)&v10[v20 + 16]);
      v22 = v21;
      if ( v21 < 0 )
      {
        LODWORD(lpServices) = v21;
        AslLogCallPrintf(
          2,
          "CDriverMap::AddScmDrivers",
          936,
          "0x%08x Failed to add service (%ws) to service map",
          lpServices,
          *(_QWORD *)&v10[v20]);
        if ( EnableDevInvStdErrLog )
        {
          v23 = o___acrt_iob_func_0(2u);
          fprintf(v23, "Warning: %s, %u: ", "CDriverMap::AddScmDrivers", 936);
          v24 = *(_QWORD *)&v10[v20];
          v25 = o___acrt_iob_func_0(2u);
          fprintf(v25, "0x%08x Failed to add service (%ws) to service map", v22, v24);
          v26 = o___acrt_iob_func_0(2u);
          fprintf(v26, "\n");
        }
        if ( g_DeviceMapLogFunction )
          TraceMessageCallback(50331648, "0x%08x Failed to add service (%ws) to service map", v22, *(_QWORD *)&v10[v20]);
      }
    }
    v4 = 0;
LABEL_17:
    if ( v10 )
      operator delete(v10);
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    AslLogCallPrintf(2, "CDriverMap::AddScmDrivers", 863, "0x%08x Failed to enumerate services from SCM manager", v4);
    if ( EnableDevInvStdErrLog )
    {
      v5 = o___acrt_iob_func_0(2u);
      fprintf(v5, "Error: %s, %u: ", "CDriverMap::AddScmDrivers", 863);
      v6 = o___acrt_iob_func_0(2u);
      fprintf(v6, "0x%08x Failed to enumerate services from SCM manager", v4);
      v7 = o___acrt_iob_func_0(2u);
      fprintf(v7, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "0x%08x Failed to enumerate services from SCM manager", v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180043490  mov     r11, rsp
0x180043493  mov     [r11+20h], rbx
0x180043497  push    rbp
0x180043498  push    rsi
0x180043499  push    rdi
0x18004349a  push    r12
0x18004349c  push    r13
0x18004349e  push    r14
0x1800434a0  push    r15
0x1800434a2  mov     rbp, rsp
0x1800434a5  sub     rsp, 50h
0x1800434a9  xor     r15d, r15d
0x1800434ac  lea     rax, [rbp+ResumeHandle]
0x1800434b0  mov     [r11-40h], r15
0x1800434b4  mov     r13, rcx
0x1800434b7  mov     rcx, [rcx+0A8h]; hSCManager
0x1800434be  xor     edx, edx; InfoLevel
0x1800434c0  mov     [r11-48h], rax
0x1800434c4  lea     rax, [rbp+ServicesReturned]
0x1800434c8  mov     [r11-50h], rax
0x1800434cc  lea     edi, [r15+3]
0x1800434d0  lea     rax, [rbp+Size]
0x1800434d4  mov     dword ptr [rbp+Size], r15d
0x1800434d8  mov     [r11-58h], rax
0x1800434dc  lea     r14d, [r15+0Bh]
0x1800434e0  mov     [r11-60h], r15d
0x1800434e4  mov     r9d, edi; dwServiceState
0x1800434e7  mov     r8d, r14d; dwServiceType
0x1800434ea  mov     [r11-68h], r15
0x1800434ee  mov     [rbp+ServicesReturned], r15d
0x1800434f2  mov     [rbp+ResumeHandle], r15d
0x1800434f6  call    cs:__imp_EnumServicesStatusExW
0x1800434fc  mov     ebx, 0EAh
0x180043501  test    eax, eax
0x180043503  jnz     loc_18004363C
0x180043509  call    cs:__imp_GetLastError
0x18004350f  cmp     eax, ebx
0x180043511  jz      loc_18004363C
0x180043517  call    cs:__imp_GetLastError
0x18004351d  mov     ebx, eax
0x18004351f  test    eax, eax
0x180043521  jle     short loc_18004352C
0x180043523  movzx   ebx, ax
0x180043526  or      ebx, 80070000h
0x18004352c  lea     r14, a0x08xFailedToE; "0x%08x Failed to enumerate services fro"...
0x180043533  mov     dword ptr [rsp+50h+lpServices], ebx
0x180043537  mov     esi, 35Fh
0x18004353c  lea     rdx, aCdrivermapAdds_0; "CDriverMap::AddScmDrivers"
0x180043543  mov     edi, 2
0x180043548  mov     r9, r14
0x18004354b  mov     r8d, esi
0x18004354e  mov     ecx, edi
0x180043550  call    AslLogCallPrintf
0x180043555  cmp     cs:EnableDevInvStdErrLog, r15d
0x18004355c  jz      short loc_1800435A9
0x18004355e  mov     ecx, edi; Ix
0x180043560  call    _o___acrt_iob_func_0
0x180043565  mov     rcx, rax; Stream
0x180043568  lea     r8, aCdrivermapAdds_0; "CDriverMap::AddScmDrivers"
0x18004356f  mov     r9d, esi
0x180043572  lea     rdx, Format; "Error: %s, %u: "
0x180043579  call    fprintf
0x18004357e  mov     ecx, edi; Ix
0x180043580  call    _o___acrt_iob_func_0
0x180043585  mov     rcx, rax; Stream
0x180043588  mov     r8d, ebx
0x18004358b  mov     rdx, r14; Format
0x18004358e  call    fprintf
0x180043593  mov     ecx, edi; Ix
0x180043595  call    _o___acrt_iob_func_0
0x18004359a  mov     rcx, rax; Stream
0x18004359d  lea     rdx, asc_18011EAD8; "\n"
0x1800435a4  call    fprintf
0x1800435a9  cmp     cs:g_DeviceMapLogFunction, r15
0x1800435b0  jz      loc_1800436FD
0x1800435b6  mov     r8d, ebx
0x1800435b9  mov     rdx, r14
0x1800435bc  mov     ecx, 2000000h
0x1800435c1  call    TraceMessageCallback
0x1800435c6  jmp     loc_1800436FD
0x1800435cb  mov     r8d, dword ptr [rbp+Size]; Size
0x1800435cf  xor     edx, edx; Val
0x1800435d1  mov     rcx, rsi; void *
0x1800435d4  call    memset_0
0x1800435d9  mov     rcx, [r13+0A8h]; hSCManager
0x1800435e0  lea     rax, [rbp+ResumeHandle]
0x1800435e4  mov     [rsp+50h+pszGroupName], r15; pszGroupName
0x1800435e9  mov     r9d, edi; dwServiceState
0x1800435ec  mov     [rsp+50h+lpResumeHandle], rax; lpResumeHandle
0x1800435f1  mov     r8d, r14d; dwServiceType
0x1800435f4  lea     rax, [rbp+ServicesReturned]
0x1800435f8  mov     [rbp+ResumeHandle], r15d
0x1800435fc  mov     [rsp+50h+lpServicesReturned], rax; lpServicesReturned
0x180043601  xor     edx, edx; InfoLevel
0x180043603  lea     rax, [rbp+Size]
0x180043607  mov     [rsp+50h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18004360c  mov     eax, dword ptr [rbp+Size]
0x18004360f  mov     [rsp+50h+cbBufSize], eax; cbBufSize
0x180043613  mov     [rsp+50h+lpServices], rsi; lpServices
0x180043618  call    cs:__imp_EnumServicesStatusExW
0x18004361e  test    eax, eax
0x180043620  jnz     loc_1800437CC
0x180043626  call    cs:__imp_GetLastError
0x18004362c  cmp     eax, ebx
0x18004362e  jnz     loc_180043717
0x180043634  mov     rcx, rsi; Block
0x180043637  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004363c  mov     eax, dword ptr [rbp+Size]
0x18004363f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180043646  add     eax, eax
0x180043648  mov     ecx, eax; unsigned __int64
0x18004364a  mov     dword ptr [rbp+Size], eax
0x18004364d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180043652  mov     rsi, rax
0x180043655  test    rax, rax
0x180043658  jnz     loc_1800435CB
0x18004365e  lea     r14, aOutOfMemory_0; "Out of memory"
0x180043665  mov     r12d, 371h
0x18004366b  mov     edi, 2
0x180043670  lea     rdx, aCdrivermapAdds_0; "CDriverMap::AddScmDrivers"
0x180043677  mov     r9, r14
0x18004367a  mov     r8d, r12d
0x18004367d  mov     ecx, edi
0x18004367f  mov     ebx, 80070008h
0x180043684  call    AslLogCallPrintf
0x180043689  cmp     cs:EnableDevInvStdErrLog, r15d
0x180043690  jz      short loc_1800436DA
0x180043692  mov     ecx, edi; Ix
0x180043694  call    _o___acrt_iob_func_0
0x180043699  mov     rcx, rax; Stream
0x18004369c  lea     r8, aCdrivermapAdds_0; "CDriverMap::AddScmDrivers"
0x1800436a3  mov     r9d, r12d
0x1800436a6  lea     rdx, Format; "Error: %s, %u: "
0x1800436ad  call    fprintf
0x1800436b2  mov     ecx, edi; Ix
0x1800436b4  call    _o___acrt_iob_func_0
0x1800436b9  mov     rcx, rax; Stream
0x1800436bc  mov     rdx, r14; Format
0x1800436bf  call    fprintf
0x1800436c4  mov     ecx, edi; Ix
0x1800436c6  call    _o___acrt_iob_func_0
0x1800436cb  mov     rcx, rax; Stream
0x1800436ce  lea     rdx, asc_18011EAD8; "\n"
0x1800436d5  call    fprintf
0x1800436da  cmp     cs:g_DeviceMapLogFunction, r15
0x1800436e1  jz      short loc_1800436F0
0x1800436e3  mov     rdx, r14
0x1800436e6  mov     ecx, 2000000h
0x1800436eb  call    TraceMessageCallback
0x1800436f0  test    rsi, rsi
0x1800436f3  jz      short loc_1800436FD
0x1800436f5  mov     rcx, rsi; Block
0x1800436f8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800436fd  mov     eax, ebx
0x1800436ff  mov     rbx, [rsp+50h+arg_18]
0x180043707  add     rsp, 50h
0x18004370b  pop     r15
0x18004370d  pop     r14
0x18004370f  pop     r13
0x180043711  pop     r12
0x180043713  pop     rdi
0x180043714  pop     rsi
0x180043715  pop     rbp
0x180043716  retn
0x180043717  call    cs:__imp_GetLastError
0x18004371d  mov     ebx, eax
0x18004371f  test    eax, eax
0x180043721  jle     short loc_18004372C
0x180043723  movzx   ebx, ax
0x180043726  or      ebx, 80070000h
0x18004372c  lea     r14, a0x08xFailedToE; "0x%08x Failed to enumerate services fro"...
0x180043733  mov     dword ptr [rsp+50h+lpServices], ebx
0x180043737  mov     r12d, 397h
0x18004373d  lea     rdx, aCdrivermapAdds_0; "CDriverMap::AddScmDrivers"
0x180043744  mov     edi, 2
0x180043749  mov     r9, r14
0x18004374c  mov     r8d, r12d
0x18004374f  mov     ecx, edi
0x180043751  call    AslLogCallPrintf
0x180043756  cmp     cs:EnableDevInvStdErrLog, r15d
0x18004375d  jz      short loc_1800437AA
0x18004375f  mov     ecx, edi; Ix
0x180043761  call    _o___acrt_iob_func_0
0x180043766  mov     rcx, rax; Stream
0x180043769  lea     r8, aCdrivermapAdds_0; "CDriverMap::AddScmDrivers"
0x180043770  mov     r9d, r12d
0x180043773  lea     rdx, Format; "Error: %s, %u: "
0x18004377a  call    fprintf
0x18004377f  mov     ecx, edi; Ix
0x180043781  call    _o___acrt_iob_func_0
0x180043786  mov     rcx, rax; Stream
0x180043789  mov     r8d, ebx
0x18004378c  mov     rdx, r14; Format
0x18004378f  call    fprintf
0x180043794  mov     ecx, edi; Ix
0x180043796  call    _o___acrt_iob_func_0
0x18004379b  mov     rcx, rax; Stream
0x18004379e  lea     rdx, asc_18011EAD8; "\n"
0x1800437a5  call    fprintf
0x1800437aa  cmp     cs:g_DeviceMapLogFunction, r15
0x1800437b1  jz      loc_1800436F0
0x1800437b7  mov     r8d, ebx
0x1800437ba  mov     rdx, r14
0x1800437bd  mov     ecx, 2000000h
0x1800437c2  call    TraceMessageCallback
0x1800437c7  jmp     loc_1800436F0
0x1800437cc  mov     r14d, r15d
0x1800437cf  cmp     [rbp+ServicesReturned], r15d
0x1800437d3  jbe     loc_1800438BD
0x1800437d9  mov     edi, 2
0x1800437de  mov     eax, r14d
0x1800437e1  mov     rcx, r13; this
0x1800437e4  imul    r15, rax, 38h ; '8'
0x1800437e8  mov     r8d, [r15+rsi+10h]; unsigned int
0x1800437ed  mov     rdx, [r15+rsi]; unsigned __int16 *
0x1800437f1  call    ?AddService@CDriverMap@@AEAAJPEBGK@Z; CDriverMap::AddService(ushort const *,ulong)
0x1800437f6  mov     r12d, eax
0x1800437f9  test    eax, eax
0x1800437fb  jns     loc_1800438AD
0x180043801  mov     rcx, [r15+rsi]
0x180043805  lea     r9, a0x08xFailedToA_1; "0x%08x Failed to add service (%ws) to s"...
0x18004380c  mov     qword ptr [rsp+50h+cbBufSize], rcx
0x180043811  lea     rdx, aCdrivermapAdds_0; "CDriverMap::AddScmDrivers"
0x180043818  mov     ecx, edi
0x18004381a  mov     dword ptr [rsp+50h+lpServices], eax
0x18004381e  mov     r8d, 3A8h
0x180043824  call    AslLogCallPrintf
0x180043829  cmp     cs:EnableDevInvStdErrLog, 0
0x180043830  jz      short loc_18004388B
0x180043832  mov     ecx, edi; Ix
0x180043834  call    _o___acrt_iob_func_0
0x180043839  mov     rcx, rax; Stream
0x18004383c  lea     r8, aCdrivermapAdds_0; "CDriverMap::AddScmDrivers"
0x180043843  mov     r9d, 3A8h
0x180043849  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x180043850  call    fprintf
0x180043855  mov     rbx, [r15+rsi]
0x180043859  mov     ecx, edi; Ix
0x18004385b  call    _o___acrt_iob_func_0
0x180043860  mov     r9, rbx
0x180043863  lea     rdx, a0x08xFailedToA_1; "0x%08x Failed to add service (%ws) to s"...
0x18004386a  mov     r8d, r12d
0x18004386d  mov     rcx, rax; Stream
0x180043870  call    fprintf
0x180043875  mov     ecx, edi; Ix
0x180043877  call    _o___acrt_iob_func_0
0x18004387c  mov     rcx, rax; Stream
0x18004387f  lea     rdx, asc_18011EAD8; "\n"
0x180043886  call    fprintf
0x18004388b  cmp     cs:g_DeviceMapLogFunction, 0
0x180043893  jz      short loc_1800438AD
0x180043895  mov     r9, [r15+rsi]
0x180043899  lea     rdx, a0x08xFailedToA_1; "0x%08x Failed to add service (%ws) to s"...
0x1800438a0  mov     r8d, r12d
0x1800438a3  mov     ecx, 3000000h
0x1800438a8  call    TraceMessageCallback
0x1800438ad  inc     r14d
0x1800438b0  cmp     r14d, [rbp+ServicesReturned]
0x1800438b4  jb      loc_1800437DE
0x1800438ba  xor     r15d, r15d
0x1800438bd  mov     ebx, r15d
0x1800438c0  jmp     loc_1800436F0
```
