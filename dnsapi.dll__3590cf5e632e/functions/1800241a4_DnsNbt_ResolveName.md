# DnsNbt_ResolveName

- ea: `0x1800241a4`
- end: `0x18002454b`
- name: `DnsNbt_ResolveName`
- size: `935`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180049998`

## callees

- `0x1800241a4`
- `0x180024554`
- `0x1800245a0`
- `0x1800249b8`
- `0x18002625c`
- `0x18004a020`
- `0x1800852ec`
- `0x18008b5f0`
- `0x1800dbfe0`
- `0x1800dc9e0`
- `0x1800dd468`
- `0x1800ddb4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024483`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800242ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800242ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800243b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800243b8`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18002443b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18002443b`
- `ntdll!NtDeviceIoControlFile` at `0x180024357`
- `ntdll!NtDeviceIoControlFile` at `0x180024357`

## pseudocode

```c
__int64 __fastcall DnsNbt_ResolveName(
        __int64 a1,
        const WCHAR *a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char **a7)
{
  char **v7; // r15
  char *v12; // rax
  char *v13; // rbx
  DWORD LastError; // edi
  __int64 v15; // rsi
  __int64 v16; // rcx
  const WCHAR *v17; // r8
  __int64 v18; // rdx
  _WORD *v19; // rax
  _WORD *v20; // rcx
  int v21; // r14d
  unsigned int v22; // r13d
  HANDLE v23; // rcx
  DWORD Io; // eax
  NTSTATUS v25; // eax
  int v26; // ecx
  char v27; // r15
  int v29; // edx
  int v30; // ecx
  CHAR MultiByteStr[24]; // [rsp+58h] [rbp-70h] BYREF

  v7 = a7;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_S(1035, 34, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, a2);
  if ( !(unsigned int)DnsNbt_CheckAndConvertName(a2, MultiByteStr) )
  {
    v13 = 0;
    LastError = 123;
    goto LABEL_22;
  }
  v12 = DnsNbt_Open(a3, a4);
  v13 = v12;
  if ( v12 )
  {
    LastError = 0;
    v15 = (__int64)(v12 + 624);
    AddRefQueryBlobEx(a1, "DnsNbt_ResolveName", 1440, 17);
    v16 = 2147483646;
    *((_QWORD *)v13 + 4) = a1;
    v17 = a2;
    *((_DWORD *)v13 + 12) = 1;
    v18 = 256;
    v19 = v13 + 52;
    do
    {
      if ( !v16 )
        break;
      if ( !*v17 )
        break;
      *v19++ = *v17++;
      --v16;
      --v18;
    }
    while ( v18 );
    v20 = v19 - 1;
    if ( v18 )
      v20 = v19;
    *v20 = 0;
    *((_QWORD *)v13 + 76) = Query_NetBiosComplete;
    EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 568));
    v21 = 0;
    v22 = 0;
    if ( *((_DWORD *)v13 + 3) )
    {
      while ( 1 )
      {
        v23 = *(HANDLE *)v15;
        if ( *(_QWORD *)v15 )
        {
          *(_OWORD *)(v15 + 600) = *(_OWORD *)MultiByteStr;
          Io = ThreadPool_CreateIo(
                 v23,
                 (PTP_WIN32_IO_CALLBACK)DnsNbt_IoCompletionCallback,
                 (PVOID)v15,
                 1,
                 (struct _TP_IO **)(v15 + 576));
          LastError = Io;
          if ( Io )
          {
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
              WPP_SF_d(1035, 35, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, Io);
            goto LABEL_17;
          }
          AddRefNbtLookupContext(v13);
          v25 = NtDeviceIoControlFile(
                  *(HANDLE *)v15,
                  0,
                  0,
                  (PVOID)(v15 + 536),
                  (PIO_STATUS_BLOCK)(v15 + 536),
                  0x210096u,
                  (PVOID)(v15 + 592),
                  0x18u,
                  (PVOID)(v15 + 616),
                  0x488u);
          v27 = v25;
          if ( v25 < 0 )
          {
            CancelThreadpoolIo(*(PTP_IO *)(v15 + 576));
            DeRefNbtLookupContext(v13);
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
              WPP_SF_SSd(
                v30,
                38,
                (unsigned int)WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids,
                (_DWORD)a2,
                v15 + 8,
                v27);
            goto LABEL_17;
          }
          ++v21;
          _InterlockedOr((volatile signed __int32 *)(v15 + 584), 1u);
          if ( v25 == 259 )
          {
            if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
            {
              v29 = 36;
              goto LABEL_35;
            }
          }
          else if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          {
            v29 = 37;
LABEL_35:
            WPP_SF_SSq(
              v26,
              v29,
              (unsigned int)WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids,
              (_DWORD)a2,
              v15 + 8,
              v15);
          }
        }
LABEL_17:
        ++v22;
        v15 += 1776;
        if ( v22 >= *((_DWORD *)v13 + 3) )
        {
          v7 = a7;
          break;
        }
      }
    }
    *((_DWORD *)v13 + 10) = v21;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 568));
    if ( v21 )
    {
      LastError = 9506;
LABEL_21:
      AddRefNbtLookupContext(v13);
      *v7 = v13;
      goto LABEL_22;
    }
    if ( !LastError )
    {
      LastError = 4312;
      goto LABEL_22;
    }
  }
  else
  {
    LastError = GetLastError();
  }
  if ( LastError == 9506 && v13 )
    goto LABEL_21;
LABEL_22:
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 39, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, LastError);
  DeRefNbtLookupContext(v13);
  return LastError;
}

```

## disassembly

```asm
0x1800241a4  push    rbx
0x1800241a6  push    rbp
0x1800241a7  push    rsi
0x1800241a8  push    rdi
0x1800241a9  push    r12
0x1800241ab  push    r13
0x1800241ad  push    r14
0x1800241af  push    r15
0x1800241b1  sub     rsp, 88h
0x1800241b8  mov     rax, cs:__security_cookie
0x1800241bf  xor     rax, rsp
0x1800241c2  mov     [rsp+0C8h+var_58], rax
0x1800241c7  mov     r15, [rsp+0C8h+arg_30]
0x1800241cf  mov     rdi, r9
0x1800241d2  mov     [rsp+0C8h+var_78], r15
0x1800241d7  mov     ebx, r8d
0x1800241da  mov     rbp, rdx
0x1800241dd  mov     r14, rcx
0x1800241e0  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800241e7  jnz     loc_1800244AB
0x1800241ed  mov     r8d, [rsp+0C8h+arg_20]
0x1800241f5  lea     rdx, [rsp+0C8h+MultiByteStr]; lpMultiByteStr
0x1800241fa  mov     rcx, rbp; lpSrcStr
0x1800241fd  call    DnsNbt_CheckAndConvertName
0x180024202  xor     r12d, r12d
0x180024205  test    eax, eax
0x180024207  jz      loc_180024416
0x18002420d  mov     rdx, rdi
0x180024210  mov     ecx, ebx
0x180024212  call    DnsNbt_Open
0x180024217  mov     rbx, rax
0x18002421a  test    rax, rax
0x18002421d  jz      loc_180024483
0x180024223  lea     r9d, [r12+11h]
0x180024228  mov     r8d, 5A0h
0x18002422e  lea     rdx, aDnsnbtResolven; "DnsNbt_ResolveName"
0x180024235  mov     rcx, r14
0x180024238  mov     edi, r12d
0x18002423b  lea     rsi, [rax+270h]
0x180024242  call    AddRefQueryBlobEx
0x180024247  mov     ecx, 7FFFFFFEh
0x18002424c  mov     [rbx+20h], r14
0x180024250  mov     r8, rbp
0x180024253  mov     dword ptr [rbx+30h], 1
0x18002425a  mov     edx, 100h
0x18002425f  lea     rax, [rbx+34h]
0x180024263  test    rcx, rcx
0x180024266  jz      short loc_180024287
0x180024268  movzx   r9d, word ptr [r8]
0x18002426c  test    r9w, r9w
0x180024270  jz      short loc_180024287
0x180024272  mov     [rax], r9w
0x180024276  add     r8, 2
0x18002427a  add     rax, 2
0x18002427e  dec     rcx
0x180024281  sub     rdx, 1
0x180024285  jnz     short loc_180024263
0x180024287  lea     rcx, [rax-2]
0x18002428b  test    rdx, rdx
0x18002428e  cmovnz  rcx, rax
0x180024292  lea     rax, Query_NetBiosComplete
0x180024299  mov     [rcx], r12w
0x18002429d  lea     rcx, [rbx+238h]; lpCriticalSection
0x1800242a4  mov     [rbx+260h], rax
0x1800242ab  call    cs:__imp_EnterCriticalSection
0x1800242b2  nop     dword ptr [rax+rax+00h]
0x1800242b7  mov     r14d, r12d
0x1800242ba  mov     r13d, r12d
0x1800242bd  cmp     [rbx+0Ch], r12d
0x1800242c1  jbe     loc_1800243AD
0x1800242c7  mov     rcx, [rsi]; fl
0x1800242ca  test    rcx, rcx
0x1800242cd  jz      loc_180024394
0x1800242d3  movups  xmm0, xmmword ptr [rsp+0C8h+MultiByteStr]
0x1800242d8  lea     r12, [rsi+240h]
0x1800242df  mov     r9d, 1
0x1800242e5  mov     r8, rsi; pv
0x1800242e8  mov     [rsp+0C8h+IoStatusBlock], r12; __int64
0x1800242ed  lea     rdx, DnsNbt_IoCompletionCallback; pfnio
0x1800242f4  movdqu  xmmword ptr [rsi+258h], xmm0
0x1800242fc  call    ThreadPool_CreateIo
0x180024301  mov     edi, eax
0x180024303  test    eax, eax
0x180024305  jnz     loc_1800244F0
0x18002430b  mov     rcx, rbx
0x18002430e  call    AddRefNbtLookupContext
0x180024313  mov     [rsp+0C8h+OutputBufferLength], 488h; OutputBufferLength
0x18002431b  lea     rax, [rsi+268h]
0x180024322  mov     [rsp+0C8h+OutputBuffer], rax; OutputBuffer
0x180024327  lea     rcx, [rsi+250h]
0x18002432e  mov     [rsp+0C8h+InputBufferLength], 18h; InputBufferLength
0x180024336  lea     r9, [rsi+218h]; ApcContext
0x18002433d  mov     [rsp+0C8h+InputBuffer], rcx; InputBuffer
0x180024342  xor     r8d, r8d; ApcRoutine
0x180024345  mov     rcx, [rsi]; FileHandle
0x180024348  xor     edx, edx; Event
0x18002434a  mov     [rsp+0C8h+IoControlCode], 210096h; IoControlCode
0x180024352  mov     [rsp+0C8h+IoStatusBlock], r9; IoStatusBlock
0x180024357  call    cs:__imp_NtDeviceIoControlFile
0x18002435e  nop     dword ptr [rax+rax+00h]
0x180024363  mov     r15d, eax
0x180024366  test    eax, eax
0x180024368  js      loc_180024437
0x18002436e  inc     r14d
0x180024371  lock or dword ptr [rsi+248h], 1
0x180024379  cmp     eax, 103h
0x18002437e  jnz     loc_180024420
0x180024384  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18002438b  jnz     loc_1800244C9
0x180024391  xor     r12d, r12d
0x180024394  inc     r13d
0x180024397  add     rsi, 6F0h
0x18002439e  cmp     r13d, [rbx+0Ch]
0x1800243a2  jb      loc_1800242C7
0x1800243a8  mov     r15, [rsp+0C8h+var_78]
0x1800243ad  lea     rcx, [rbx+238h]; lpCriticalSection
0x1800243b4  mov     [rbx+28h], r14d
0x1800243b8  call    cs:__imp_LeaveCriticalSection
0x1800243bf  nop     dword ptr [rax+rax+00h]
0x1800243c4  test    r14d, r14d
0x1800243c7  jz      loc_18002451B
0x1800243cd  mov     edi, 2522h
0x1800243d2  mov     rcx, rbx
0x1800243d5  call    AddRefNbtLookupContext
0x1800243da  mov     [r15], rbx
0x1800243dd  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800243e4  jnz     loc_18002452D
0x1800243ea  mov     rcx, rbx; lpMem
0x1800243ed  call    DeRefNbtLookupContext
0x1800243f2  mov     eax, edi
0x1800243f4  mov     rcx, [rsp+0C8h+var_58]
0x1800243f9  xor     rcx, rsp; StackCookie
0x1800243fc  call    __security_check_cookie
0x180024401  add     rsp, 88h
0x180024408  pop     r15
0x18002440a  pop     r14
0x18002440c  pop     r13
0x18002440e  pop     r12
0x180024410  pop     rdi
0x180024411  pop     rsi
0x180024412  pop     rbp
0x180024413  pop     rbx
0x180024414  retn
0x180024416  mov     rbx, r12
0x180024419  mov     edi, 7Bh ; '{'
0x18002441e  jmp     short loc_1800243DD
0x180024420  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180024427  jz      loc_180024391
0x18002442d  mov     edx, 25h ; '%'
0x180024432  jmp     loc_1800244CE
0x180024437  mov     rcx, [r12]; pio
0x18002443b  call    cs:__imp_CancelThreadpoolIo
0x180024442  nop     dword ptr [rax+rax+00h]
0x180024447  mov     rcx, rbx; lpMem
0x18002444a  call    DeRefNbtLookupContext
0x18002444f  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180024456  jz      loc_180024391
0x18002445c  lea     rax, [rsi+8]
0x180024460  mov     [rsp+0C8h+IoControlCode], r15d
0x180024465  mov     edx, 26h ; '&'
0x18002446a  mov     [rsp+0C8h+IoStatusBlock], rax
0x18002446f  mov     r9, rbp
0x180024472  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x180024479  call    WPP_SF_SSd
0x18002447e  jmp     loc_180024391
0x180024483  call    cs:__imp_GetLastError
0x18002448a  nop     dword ptr [rax+rax+00h]
0x18002448f  mov     edi, eax
0x180024491  cmp     edi, 2522h
0x180024497  jnz     loc_1800243DD
0x18002449d  test    rbx, rbx
0x1800244a0  jnz     loc_1800243D2
0x1800244a6  jmp     loc_1800243DD
0x1800244ab  mov     edx, 22h ; '"'
0x1800244b0  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x1800244b7  mov     ecx, 40Bh
0x1800244bc  mov     r9, rbp
0x1800244bf  call    WPP_SF_S
0x1800244c4  jmp     loc_1800241ED
0x1800244c9  mov     edx, 24h ; '$'
0x1800244ce  lea     rax, [rsi+8]
0x1800244d2  mov     qword ptr [rsp+0C8h+IoControlCode], rsi
0x1800244d7  mov     r9, rbp
0x1800244da  mov     [rsp+0C8h+IoStatusBlock], rax
0x1800244df  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x1800244e6  call    WPP_SF_SSq
0x1800244eb  jmp     loc_180024391
0x1800244f0  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800244f7  jz      loc_180024391
0x1800244fd  mov     edx, 23h ; '#'
0x180024502  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x180024509  mov     ecx, 40Bh
0x18002450e  mov     r9d, eax
0x180024511  call    WPP_SF_d
0x180024516  jmp     loc_180024391
0x18002451b  test    edi, edi
0x18002451d  jnz     loc_180024491
0x180024523  mov     edi, 10D8h
0x180024528  jmp     loc_1800243DD
0x18002452d  mov     edx, 27h ; '''
0x180024532  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x180024539  mov     ecx, 40Bh
0x18002453e  mov     r9d, edi
0x180024541  call    WPP_SF_d
0x180024546  jmp     loc_1800243EA
```
