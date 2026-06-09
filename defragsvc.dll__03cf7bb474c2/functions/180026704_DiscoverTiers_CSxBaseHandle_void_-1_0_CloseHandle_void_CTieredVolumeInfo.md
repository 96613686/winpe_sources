# DiscoverTiers(CSxBaseHandle<void *,-1,0,&CloseHandle(void *)> &,CTieredVolumeInfo &)

- ea: `0x180026704`
- end: `0x180026a1c`
- name: `?DiscoverTiers@@YAJAEAV?$CSxBaseHandle@PEAX$0?0$0A@$1?CloseHandle@@YAHPEAX@Z@@AEAVCTieredVolumeInfo@@@Z`
- size: `792`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003ac94`
- `0x18006495c`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x180026704`
- `0x1800667e4`
- `0x180066d54`
- `0x180067b0a`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800267df`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026917`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800267df`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180026917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026921`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026921`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002678e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800268c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002678e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800268c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026809`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002693f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800269d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800269e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026809`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002693f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800269d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800269e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiscoverTiers(HANDLE *a1, CTieredVolumeInfo *a2)
{
  char *v4; // rdi
  __int16 v5; // ax
  DWORD nOutBufferSize; // esi
  char *lpOutBuffer; // rbx
  unsigned int v8; // edx
  int v9; // r8d
  unsigned int i; // r9d
  int v11; // eax
  DWORD v12; // esi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned int v17; // ebx
  DWORD BytesReturned; // [rsp+40h] [rbp-49h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-41h] BYREF
  __int16 v21; // [rsp+4Ch] [rbp-3Dh]
  __int16 v22; // [rsp+4Eh] [rbp-3Bh]
  _OWORD InBuffer[2]; // [rsp+80h] [rbp-9h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "DiscoverTiers", 6, 1);
  BytesReturned = 0;
  memset(InBuffer, 0, sizeof(InBuffer));
  v4 = 0;
  v5 = 16;
  if ( (char *)*a1 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    lpOutBuffer = 0;
    LastFailureAsHRESULT = -2147467259;
LABEL_35:
    v22 = v5;
  }
  else
  {
    nOutBufferSize = 10664;
    LastFailureAsHRESULT = 0;
    v21 = 16;
    while ( 1 )
    {
      BytesReturned = 0;
      lpOutBuffer = (char *)CoTaskMemAlloc(nOutBufferSize);
      v5 = 23;
      if ( !lpOutBuffer )
        goto LABEL_32;
      LastFailureAsHRESULT = 0;
      v21 = 23;
      memset_0(lpOutBuffer, 0, nOutBufferSize);
      if ( DeviceIoControl(*a1, 0x902ECu, 0, 0, lpOutBuffer, nOutBufferSize, &BytesReturned, 0) )
        break;
      if ( GetLastError() != 234 )
      {
        v5 = 56;
        goto LABEL_10;
      }
      if ( nOutBufferSize >= 1064 * *((_DWORD *)lpOutBuffer + 3) + 24 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        LastFailureAsHRESULT = -2147418113;
        v5 = 50;
        goto LABEL_35;
      }
      nOutBufferSize = 1064 * *((_DWORD *)lpOutBuffer + 3) + 24;
      CoTaskMemFree(lpOutBuffer);
    }
    v8 = *((_DWORD *)lpOutBuffer + 3);
    if ( v8 != *((_DWORD *)lpOutBuffer + 4) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      LastFailureAsHRESULT = -2147024809;
      v5 = 64;
      goto LABEL_35;
    }
    v9 = 0;
    for ( i = 0; i < v8; ++i )
    {
      v11 = v9 + 1;
      if ( (*(_DWORD *)&lpOutBuffer[1064 * i + 1064] & 0x400000) == 0 )
        v11 = v9;
      v9 = v11;
    }
    if ( v8 - v9 > 1 && (*((_DWORD *)lpOutBuffer + 2) & 0x20000000) == 0 )
    {
      v12 = 352;
      InBuffer[0] = 0x2000000020uLL;
      while ( 1 )
      {
        BytesReturned = 0;
        v4 = (char *)CoTaskMemAlloc(v12);
        v5 = 97;
        if ( !v4 )
          break;
        LastFailureAsHRESULT = 0;
        v21 = 97;
        memset_0(v4, 0, v12);
        if ( DeviceIoControl(*a1, 0x902F0u, InBuffer, 0x20u, v4, v12, &BytesReturned, 0) )
        {
          if ( *((_DWORD *)v4 + 6) != *((_DWORD *)v4 + 7) )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            LastFailureAsHRESULT = -2147024809;
            v5 = 137;
            goto LABEL_35;
          }
          LastFailureAsHRESULT = CTieredVolumeInfo::Initialize(
                                   a2,
                                   (struct _FILE_STORAGE_TIER *)(lpOutBuffer + 24),
                                   *((unsigned int *)lpOutBuffer + 3),
                                   (struct _FILE_STORAGE_TIER_REGION *)(v4 + 32),
                                   *((unsigned int *)v4 + 6));
          v5 = 143;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_35;
          goto LABEL_11;
        }
        if ( GetLastError() != 234 )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14, v13, v15, v16);
          v5 = 129;
          goto LABEL_11;
        }
        if ( v12 >= 32 * (*((_DWORD *)v4 + 6) + 1) )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          LastFailureAsHRESULT = -2147418113;
          v5 = 124;
          goto LABEL_35;
        }
        v12 = 32 * (*((_DWORD *)v4 + 6) + 1);
        CoTaskMemFree(v4);
      }
LABEL_32:
      LastFailureAsHRESULT = -2147024882;
      goto LABEL_35;
    }
    v5 = 84;
LABEL_10:
    LastFailureAsHRESULT = 0;
LABEL_11:
    v21 = v5;
  }
  CoTaskMemFree(lpOutBuffer);
  CoTaskMemFree(v4);
  v17 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v17;
}

```

## disassembly

```asm
0x180026704  mov     [rsp-8+arg_10], rbx
0x180026709  push    rbp
0x18002670a  push    rsi
0x18002670b  push    rdi
0x18002670c  push    r12
0x18002670e  push    r13
0x180026710  push    r14
0x180026712  push    r15
0x180026714  lea     rbp, [rsp-27h]
0x180026719  sub     rsp, 0B0h
0x180026720  mov     rax, cs:__security_cookie
0x180026727  xor     rax, rsp
0x18002672a  mov     [rbp+57h+var_40], rax
0x18002672e  mov     r12, rdx
0x180026731  mov     r15, rcx
0x180026734  mov     r9d, 1; unsigned __int16
0x18002673a  lea     r8d, [r9+5]; unsigned __int16
0x18002673e  lea     rdx, aDiscovertiers; "DiscoverTiers"
0x180026745  lea     rcx, [rbp+57h+var_98]; this
0x180026749  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002674e  nop
0x18002674f  xor     r13d, r13d
0x180026752  mov     [rbp+57h+BytesReturned], r13d
0x180026756  xorps   xmm0, xmm0
0x180026759  movups  [rbp+57h+InBuffer], xmm0
0x18002675d  movups  [rbp+57h+var_50], xmm0
0x180026761  mov     edi, r13d
0x180026764  mov     rax, [r15]
0x180026767  dec     rax
0x18002676a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002676e  lea     eax, [r13+10h]
0x180026772  ja      loc_1800269C7
0x180026778  mov     esi, 29A8h
0x18002677d  mov     [rbp+57h+var_98], r13d
0x180026781  mov     [rbp+57h+var_94], ax
0x180026785  mov     [rbp+57h+BytesReturned], r13d
0x180026789  mov     r14d, esi
0x18002678c  mov     ecx, esi; cb
0x18002678e  call    cs:__imp_CoTaskMemAlloc
0x180026794  mov     rbx, rax
0x180026797  test    rax, rax
0x18002679a  mov     eax, 17h
0x18002679f  jz      loc_1800269B4
0x1800267a5  mov     [rbp+57h+var_98], r13d
0x1800267a9  mov     [rbp+57h+var_94], ax
0x1800267ad  mov     r8d, r14d; Size
0x1800267b0  xor     edx, edx; Val
0x1800267b2  mov     rcx, rbx; void *
0x1800267b5  call    memset_0
0x1800267ba  mov     [rsp+0E0h+lpOverlapped], r13; lpOverlapped
0x1800267bf  lea     rax, [rbp+57h+BytesReturned]
0x1800267c3  mov     [rsp+0E0h+lpBytesReturned], rax; lpBytesReturned
0x1800267c8  mov     [rsp+0E0h+nOutBufferSize], esi; nOutBufferSize
0x1800267cc  mov     [rsp+0E0h+lpOutBuffer], rbx; lpOutBuffer
0x1800267d1  xor     r9d, r9d; nInBufferSize
0x1800267d4  xor     r8d, r8d; lpInBuffer
0x1800267d7  mov     edx, 902ECh; dwIoControlCode
0x1800267dc  mov     rcx, [r15]; hDevice
0x1800267df  call    cs:__imp_DeviceIoControl
0x1800267e5  test    eax, eax
0x1800267e7  jnz     short loc_18002683C
0x1800267e9  call    cs:__imp_GetLastError
0x1800267ef  cmp     eax, 0EAh
0x1800267f4  jnz     short loc_18002682A
0x1800267f6  imul    eax, [rbx+0Ch], 428h
0x1800267fd  add     eax, 18h
0x180026800  cmp     esi, eax
0x180026802  jnb     short loc_180026814
0x180026804  mov     esi, eax
0x180026806  mov     rcx, rbx; pv
0x180026809  call    cs:__imp_CoTaskMemFree
0x18002680f  jmp     loc_180026785
0x180026814  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180026819  mov     [rbp+57h+var_98], 8000FFFFh
0x180026820  mov     eax, 32h ; '2'
0x180026825  jmp     loc_1800269D1
0x18002682a  mov     eax, 38h ; '8'
0x18002682f  mov     [rbp+57h+var_98], r13d
0x180026833  mov     [rbp+57h+var_94], ax
0x180026837  jmp     loc_1800269D5
0x18002683c  mov     edx, [rbx+0Ch]
0x18002683f  cmp     edx, [rbx+10h]
0x180026842  jz      short loc_18002685A
0x180026844  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180026849  mov     [rbp+57h+var_98], 80070057h
0x180026850  mov     eax, 40h ; '@'
0x180026855  jmp     loc_1800269D1
0x18002685a  mov     r8d, r13d
0x18002685d  mov     r9d, r13d
0x180026860  test    edx, edx
0x180026862  jz      short loc_18002688C
0x180026864  mov     eax, r9d
0x180026867  inc     rax
0x18002686a  imul    rax, 428h
0x180026871  mov     ecx, [rax+rbx]
0x180026874  bt      rcx, 16h
0x180026879  lea     eax, [r8+1]
0x18002687d  cmovnb  eax, r8d
0x180026881  mov     r8d, eax
0x180026884  inc     r9d
0x180026887  cmp     r9d, edx
0x18002688a  jb      short loc_180026864
0x18002688c  sub     edx, r8d
0x18002688f  cmp     edx, 1
0x180026892  jbe     loc_1800269BD
0x180026898  test    dword ptr [rbx+8], 20000000h
0x18002689f  jnz     loc_1800269BD
0x1800268a5  mov     esi, 160h
0x1800268aa  mov     eax, 20h ; ' '
0x1800268af  mov     dword ptr [rbp+57h+InBuffer+4], eax
0x1800268b2  mov     dword ptr [rbp+57h+InBuffer], eax
0x1800268b5  mov     qword ptr [rbp+57h+InBuffer+8], r13
0x1800268b9  mov     [rbp+57h+BytesReturned], r13d
0x1800268bd  mov     r14d, esi
0x1800268c0  mov     ecx, esi; cb
0x1800268c2  call    cs:__imp_CoTaskMemAlloc
0x1800268c8  mov     rdi, rax
0x1800268cb  test    rax, rax
0x1800268ce  mov     eax, 61h ; 'a'
0x1800268d3  jz      loc_1800269B4
0x1800268d9  mov     [rbp+57h+var_98], r13d
0x1800268dd  mov     [rbp+57h+var_94], ax
0x1800268e1  mov     r8d, r14d; Size
0x1800268e4  xor     edx, edx; Val
0x1800268e6  mov     rcx, rdi; void *
0x1800268e9  call    memset_0
0x1800268ee  mov     [rsp+0E0h+lpOverlapped], r13; lpOverlapped
0x1800268f3  lea     rax, [rbp+57h+BytesReturned]
0x1800268f7  mov     [rsp+0E0h+lpBytesReturned], rax; lpBytesReturned
0x1800268fc  mov     [rsp+0E0h+nOutBufferSize], esi; nOutBufferSize
0x180026900  mov     [rsp+0E0h+lpOutBuffer], rdi; lpOutBuffer
0x180026905  mov     r9d, 20h ; ' '; nInBufferSize
0x18002690b  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18002690f  mov     edx, 902F0h; dwIoControlCode
0x180026914  mov     rcx, [r15]; hDevice
0x180026917  call    cs:__imp_DeviceIoControl
0x18002691d  test    eax, eax
0x18002691f  jnz     short loc_18002696F
0x180026921  call    cs:__imp_GetLastError
0x180026927  cmp     eax, 0EAh
0x18002692c  jnz     short loc_18002695D
0x18002692e  mov     eax, [rdi+18h]
0x180026931  inc     eax
0x180026933  shl     eax, 5
0x180026936  cmp     esi, eax
0x180026938  jnb     short loc_18002694A
0x18002693a  mov     esi, eax
0x18002693c  mov     rcx, rdi; pv
0x18002693f  call    cs:__imp_CoTaskMemFree
0x180026945  jmp     loc_1800268B9
0x18002694a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002694f  mov     [rbp+57h+var_98], 8000FFFFh
0x180026956  mov     eax, 7Ch ; '|'
0x18002695b  jmp     short loc_1800269D1
0x18002695d  call    GetLastFailureAsHRESULT
0x180026962  mov     [rbp+57h+var_98], eax
0x180026965  mov     eax, 81h
0x18002696a  jmp     loc_180026833
0x18002696f  mov     eax, [rdi+18h]
0x180026972  cmp     eax, [rdi+1Ch]
0x180026975  jz      short loc_18002698A
0x180026977  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002697c  mov     [rbp+57h+var_98], 80070057h
0x180026983  mov     eax, 89h
0x180026988  jmp     short loc_1800269D1
0x18002698a  lea     r9, [rdi+20h]; struct _FILE_STORAGE_TIER_REGION *
0x18002698e  mov     r8d, [rbx+0Ch]; unsigned __int64
0x180026992  lea     rdx, [rbx+18h]; struct _FILE_STORAGE_TIER *
0x180026996  mov     [rsp+0E0h+lpOutBuffer], rax; unsigned __int64
0x18002699b  mov     rcx, r12; this
0x18002699e  call    ?Initialize@CTieredVolumeInfo@@QEAAJPEAU_FILE_STORAGE_TIER@@_KPEAU_FILE_STORAGE_TIER_REGION@@1@Z; CTieredVolumeInfo::Initialize(_FILE_STORAGE_TIER *,unsigned __int64,_FILE_STORAGE_TIER_REGION *,unsigned __int64)
0x1800269a3  mov     [rbp+57h+var_98], eax
0x1800269a6  test    eax, eax
0x1800269a8  mov     eax, 8Fh
0x1800269ad  js      short loc_1800269D1
0x1800269af  jmp     loc_180026833
0x1800269b4  mov     [rbp+57h+var_98], 8007000Eh
0x1800269bb  jmp     short loc_1800269D1
0x1800269bd  mov     eax, 54h ; 'T'
0x1800269c2  jmp     loc_18002682F
0x1800269c7  mov     rbx, r13
0x1800269ca  mov     [rbp+57h+var_98], 80004005h
0x1800269d1  mov     [rbp+57h+var_92], ax
0x1800269d5  mov     rcx, rbx; pv
0x1800269d8  call    cs:__imp_CoTaskMemFree
0x1800269de  mov     rcx, rdi; pv
0x1800269e1  call    cs:__imp_CoTaskMemFree
0x1800269e7  mov     ebx, [rbp+57h+var_98]
0x1800269ea  lea     rcx, [rbp+57h+var_98]; this
0x1800269ee  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800269f3  mov     eax, ebx
0x1800269f5  mov     rcx, [rbp+57h+var_40]
0x1800269f9  xor     rcx, rsp; StackCookie
0x1800269fc  call    __security_check_cookie
0x180026a01  mov     rbx, [rsp+0E0h+arg_10]
0x180026a09  add     rsp, 0B0h
0x180026a10  pop     r15
0x180026a12  pop     r14
0x180026a14  pop     r13
0x180026a16  pop     r12
0x180026a18  pop     rdi
0x180026a19  pop     rsi
0x180026a1a  pop     rbp
0x180026a1b  retn
```
