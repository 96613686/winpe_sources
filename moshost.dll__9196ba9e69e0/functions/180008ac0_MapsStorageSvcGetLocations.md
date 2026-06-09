# MapsStorageSvcGetLocations

- ea: `0x180008ac0`
- end: `0x180008c9a`
- name: `MapsStorageSvcGetLocations`
- size: `474`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008898`
- `0x180008938`
- `0x180008ac0`
- `0x18000c720`
- `0x18000d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008c51`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008c51`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008c0c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180008c0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b63`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008b50`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008b50`
- `MosStorage!MosStorageGetLocations` at `0x180008bb2`
- `MosStorage!MosStorageGetLocations` at `0x180008bb2`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008c2c`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008c2c`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008b24`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008bcb`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008b24`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180008bcb`
- `ZTrace_Maps!ZTraceHelper` at `0x180008b9f`
- `ZTrace_Maps!ZTraceHelper` at `0x180008b9f`

## string_xrefs

- `0x180008b80`: `Can't impersonate. Error: 0x%08X`
- `0x180008b96`: `Impersonator<struct ImpersonatorLoggedOnUserTraits>::Impersonator`

## pseudocode

```c
__int64 __fastcall MapsStorageSvcGetLocations(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // edi
  void *v8; // rax
  signed int LastError; // eax
  int Locations; // eax
  unsigned __int64 v11; // rbx
  size_t v12; // r14
  void *v13; // rax
  void *v14; // rsi
  __int64 v15; // rcx
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  void *Src[2]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+48h] [rbp-8h]
  int v20; // [rsp+98h] [rbp+48h] BYREF

  *(_OWORD *)Src = 0;
  v19 = 0;
  v17 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)qword_1800185D0 + 240LL))(qword_1800185D0, &v17);
  if ( v5 < 0 )
  {
    v6 = ZTraceReportPropagationNoThis(v5, "MapsStorageSvcGetLocations", 132);
LABEL_3:
    v7 = v6;
    goto LABEL_17;
  }
  v8 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17);
  v20 = -2147024875;
  if ( v8 )
  {
    if ( ImpersonateLoggedOnUser(v8) )
    {
      v20 = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v20 = LastError;
      if ( LastError < 0 )
        ZTraceHelper(
          0,
          "Impersonator<struct ImpersonatorLoggedOnUserTraits>::Impersonator",
          21,
          &v20,
          "Can't impersonate. Error: 0x%08X",
          LastError);
    }
  }
  else
  {
    v20 = -2147023888;
  }
  Locations = MosStorageGetLocations(Src);
  if ( Locations >= 0 )
  {
    Impersonator<ImpersonatorLoggedOnUserTraits>::~Impersonator<ImpersonatorLoggedOnUserTraits>(&v20);
    v11 = 0xDAB7EC1DD3431B57uLL * (((char *)Src[1] - (char *)Src[0]) >> 4);
    v12 = 16 * (unsigned int)(((char *)Src[1] - (char *)Src[0]) >> 4);
    v13 = malloc(v12);
    v14 = v13;
    if ( !v13 )
    {
      v6 = ZTraceReportOriginationNoThis(-2147024882, "MapsStorageSvcGetLocations", 145);
      goto LABEL_3;
    }
    v7 = 0;
    memcpy_0(v13, Src[0], v12);
    *a2 = v11;
    *a3 = v14;
  }
  else
  {
    v7 = ZTraceReportPropagationNoThis(Locations, "MapsStorageSvcGetLocations", 138);
    Impersonator<ImpersonatorLoggedOnUserTraits>::~Impersonator<ImpersonatorLoggedOnUserTraits>(&v20);
  }
LABEL_17:
  free(0);
  v15 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  std::vector<_STORAGE_DEVICE_DATA>::~vector<_STORAGE_DEVICE_DATA>(Src);
  return v7;
}

```

## disassembly

```asm
0x180008ac0  mov     [rsp-28h+arg_0], rbx
0x180008ac5  mov     [rsp-28h+arg_8], rsi
0x180008aca  push    rbp
0x180008acb  push    rdi
0x180008acc  push    r12
0x180008ace  push    r14
0x180008ad0  push    r15
0x180008ad2  mov     rbp, rsp
0x180008ad5  sub     rsp, 50h
0x180008ad9  mov     r15, r8
0x180008adc  mov     r12, rdx
0x180008adf  xorps   xmm0, xmm0
0x180008ae2  movdqu  xmmword ptr [rbp+Src], xmm0
0x180008ae7  mov     [rbp+var_8], 0
0x180008aef  mov     [rbp+var_20], 0
0x180008af7  mov     rcx, cs:qword_1800185D0
0x180008afe  mov     rax, [rcx]
0x180008b01  lea     rdx, [rbp+var_20]
0x180008b05  mov     rax, [rax+0F0h]
0x180008b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b11  test    eax, eax
0x180008b13  jns     short loc_180008B31
0x180008b15  mov     r8d, 84h
0x180008b1b  lea     rdx, aMapsstoragesvc_1; "MapsStorageSvcGetLocations"
0x180008b22  mov     ecx, eax
0x180008b24  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008b2a  mov     edi, eax
0x180008b2c  jmp     loc_180008C4F
0x180008b31  mov     rcx, [rbp+var_20]
0x180008b35  mov     rax, [rcx]
0x180008b38  mov     rax, [rax+18h]
0x180008b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b41  mov     [rbp+arg_18], 80070015h
0x180008b48  test    rax, rax
0x180008b4b  jz      short loc_180008BA7
0x180008b4d  mov     rcx, rax; hToken
0x180008b50  call    cs:__imp_ImpersonateLoggedOnUser
0x180008b56  test    eax, eax
0x180008b58  jz      short loc_180008B63
0x180008b5a  mov     [rbp+arg_18], 0
0x180008b61  jmp     short loc_180008BAE
0x180008b63  call    cs:__imp_GetLastError
0x180008b69  test    eax, eax
0x180008b6b  jle     short loc_180008B75
0x180008b6d  movzx   eax, ax
0x180008b70  or      eax, 80070000h
0x180008b75  mov     [rbp+arg_18], eax
0x180008b78  test    eax, eax
0x180008b7a  jns     short loc_180008BAE
0x180008b7c  mov     [rsp+50h+var_28], eax
0x180008b80  lea     rax, aCanTImpersonat; "Can't impersonate. Error: 0x%08X"
0x180008b87  mov     [rsp+50h+var_30], rax
0x180008b8c  lea     r9, [rbp+arg_18]
0x180008b90  mov     r8d, 15h
0x180008b96  lea     rdx, aImpersonatorSt; "Impersonator<struct ImpersonatorLoggedO"...
0x180008b9d  xor     ecx, ecx
0x180008b9f  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180008ba5  jmp     short loc_180008BAE
0x180008ba7  mov     [rbp+arg_18], 800703F0h
0x180008bae  lea     rcx, [rbp+Src]
0x180008bb2  call    cs:__imp_?MosStorageGetLocations@@YAJPEAV?$vector@U_STORAGE_DEVICE_DATA@@V?$allocator@U_STORAGE_DEVICE_DATA@@@std@@@std@@@Z; MosStorageGetLocations(std::vector<_STORAGE_DEVICE_DATA> *)
0x180008bb8  test    eax, eax
0x180008bba  jns     short loc_180008BDE
0x180008bbc  mov     r8d, 8Ah
0x180008bc2  lea     rdx, aMapsstoragesvc_1; "MapsStorageSvcGetLocations"
0x180008bc9  mov     ecx, eax
0x180008bcb  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180008bd1  mov     edi, eax
0x180008bd3  lea     rcx, [rbp+arg_18]
0x180008bd7  call    ??1?$Impersonator@UImpersonatorLoggedOnUserTraits@@@@QEAA@XZ; Impersonator<ImpersonatorLoggedOnUserTraits>::~Impersonator<ImpersonatorLoggedOnUserTraits>(void)
0x180008bdc  jmp     short loc_180008C4F
0x180008bde  lea     rcx, [rbp+arg_18]
0x180008be2  call    ??1?$Impersonator@UImpersonatorLoggedOnUserTraits@@@@QEAA@XZ; Impersonator<ImpersonatorLoggedOnUserTraits>::~Impersonator<ImpersonatorLoggedOnUserTraits>(void)
0x180008be7  mov     rbx, [rbp+Src+8]
0x180008beb  sub     rbx, [rbp+Src]
0x180008bef  sar     rbx, 4
0x180008bf3  mov     rax, 0DAB7EC1DD3431B57h
0x180008bfd  imul    rbx, rax
0x180008c01  imul    eax, ebx, 670h
0x180008c07  mov     r14d, eax
0x180008c0a  mov     ecx, eax; Size
0x180008c0c  call    cs:__imp_malloc
0x180008c12  mov     rsi, rax
0x180008c15  test    rax, rax
0x180008c18  jnz     short loc_180008C37
0x180008c1a  mov     r8d, 91h
0x180008c20  lea     rdx, aMapsstoragesvc_1; "MapsStorageSvcGetLocations"
0x180008c27  mov     ecx, 8007000Eh
0x180008c2c  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180008c32  jmp     loc_180008B2A
0x180008c37  xor     edi, edi
0x180008c39  mov     r8, r14; Size
0x180008c3c  mov     rdx, [rbp+Src]; Src
0x180008c40  mov     rcx, rsi; void *
0x180008c43  call    memcpy_0
0x180008c48  mov     [r12], ebx
0x180008c4c  mov     [r15], rsi
0x180008c4f  xor     ecx, ecx; Block
0x180008c51  call    cs:__imp_free
0x180008c57  nop
0x180008c58  mov     rcx, [rbp+var_20]
0x180008c5c  test    rcx, rcx
0x180008c5f  jz      short loc_180008C76
0x180008c61  mov     [rbp+var_20], 0
0x180008c69  mov     rax, [rcx]
0x180008c6c  mov     rax, [rax+10h]
0x180008c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c75  nop
0x180008c76  lea     rcx, [rbp+Src]
0x180008c7a  call    ??1?$vector@U_STORAGE_DEVICE_DATA@@V?$allocator@U_STORAGE_DEVICE_DATA@@@std@@@std@@QEAA@XZ; std::vector<_STORAGE_DEVICE_DATA>::~vector<_STORAGE_DEVICE_DATA>(void)
0x180008c7f  mov     eax, edi
0x180008c81  lea     r11, [rsp+50h+var_s0]
0x180008c86  mov     rbx, [r11+30h]
0x180008c8a  mov     rsi, [r11+38h]
0x180008c8e  mov     rsp, r11
0x180008c91  pop     r15
0x180008c93  pop     r14
0x180008c95  pop     r12
0x180008c97  pop     rdi
0x180008c98  pop     rbp
0x180008c99  retn
```
