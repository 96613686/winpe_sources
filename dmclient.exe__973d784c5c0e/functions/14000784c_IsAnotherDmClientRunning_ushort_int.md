# IsAnotherDmClientRunning(ushort *,int *)

- ea: `0x14000784c`
- end: `0x140007c96`
- name: `?IsAnotherDmClientRunning@@YAJPEAGPEAH@Z`
- size: `1098`
- prototype: `__int64 __fastcall(unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000c928`

## callees

- `0x140001418`
- `0x140001840`
- `0x14000784c`
- `0x14000b904`
- `0x1400155a8`
- `0x140019610`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007bbc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007bbc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140007b0a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140007b0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400079a2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400079a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007988`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007c24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007c4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007988`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007c24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007c4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007c3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007c5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007c3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007c5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400079c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400079c4`

## string_xrefs

- `0x140007b79`: `Create instance key result...`

## pseudocode

```c
__int64 __fastcall IsAnotherDmClientRunning(unsigned __int16 *a1, int *a2)
{
  unsigned __int16 *v3; // rbx
  int StateSeparatedSiufMachineRegRoot; // edi
  int v5; // r9d
  unsigned __int16 *v6; // rsi
  HANDLE ProcessHeap; // rax
  __int64 v8; // r14
  int v9; // r8d
  int v10; // r9d
  LSTATUS v11; // eax
  LSTATUS v12; // r13d
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int16 *v15; // rcx
  unsigned __int16 *v16; // rcx
  HANDLE v17; // rax
  HANDLE v18; // rax
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v21; // [rsp+54h] [rbp-ACh] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  const char *v25; // [rsp+70h] [rbp-90h] BYREF
  const char *v26; // [rsp+78h] [rbp-88h] BYREF
  __int64 v27; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[32]; // [rsp+A0h] [rbp-60h] BYREF
  const char *v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v33; // [rsp+D0h] [rbp-30h]
  int v34; // [rsp+D8h] [rbp-28h]
  int v35; // [rsp+DCh] [rbp-24h]
  int *v36; // [rsp+E0h] [rbp-20h]
  __int64 v37; // [rsp+E8h] [rbp-18h]
  DWORD *v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+F8h] [rbp-8h]

  hKey = 0;
  dwDisposition = 0;
  v3 = a1;
  lpMem = 0;
  SystemTime = 0;
  if ( a1 )
    *a1 = 0;
  if ( a2 )
  {
    StateSeparatedSiufMachineRegRoot = GetStateSeparatedSiufMachineRegRoot((unsigned __int16 **)&lpMem);
    if ( StateSeparatedSiufMachineRegRoot >= 0 )
    {
      ProcessHeap = GetProcessHeap();
      v6 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0xA0u);
      if ( v6 )
      {
        GetSystemTime(&SystemTime);
        v8 = 80;
        StateSeparatedSiufMachineRegRoot = StringCchPrintfW(
                                             v6,
                                             0x50u,
                                             L"%s\\DmClientInstanceMutex%04u%02u%02u%02uz",
                                             lpMem,
                                             SystemTime.wYear,
                                             SystemTime.wMonth,
                                             SystemTime.wDay,
                                             SystemTime.wHour);
        if ( StateSeparatedSiufMachineRegRoot >= 0 )
        {
          v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0, 1u, 0xF003Fu, 0, &hKey, &dwDisposition);
          v12 = v11;
          if ( (unsigned int)dword_140028000 > 5 )
          {
            v20 = v11;
            v38 = &v21;
            v36 = &v20;
            v13 = -1;
            v21 = dwDisposition;
            v39 = 4;
            v37 = 4;
            do
              ++v13;
            while ( v6[v13] );
            v35 = 0;
            v34 = 2 * v13 + 2;
            v33 = v6;
            v31 = "Create instance key result...";
            v32 = 30;
            tlgWriteTransfer_EventWriteTransfer(&dword_140028000, &word_140021FA6, 0, 0, 6, v30);
          }
          if ( !v12 )
          {
            RegCloseKey(hKey);
            if ( dwDisposition == 1 )
            {
              if ( v3 )
              {
                v14 = 2147483646;
                v15 = v6;
                do
                {
                  if ( !v14 )
                    break;
                  if ( !*v15 )
                    break;
                  *v3++ = *v15++;
                  --v14;
                  --v8;
                }
                while ( v8 );
                v16 = v3 - 1;
                if ( v8 )
                  v16 = v3;
                *v16 = 0;
              }
            }
            else
            {
              *a2 = 1;
            }
          }
        }
        else if ( (unsigned int)dword_140028000 > 2
               && (qword_140028010 & 0x400000000000LL) != 0
               && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
        {
          v27 = 0x1000000;
          v26 = "IsAnotherDmClientRunning";
          v21 = 131;
          v25 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
          v24 = (__int64)"StringCchPrintfW failed";
          v20 = StateSeparatedSiufMachineRegRoot;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_140028018,
            (unsigned int)byte_14002175B,
            v9,
            v10,
            (__int64)&v24,
            (__int64)&v20,
            (__int64)&v25,
            (__int64)&v26,
            (__int64)&v21,
            (__int64)&v27);
        }
      }
      else
      {
        StateSeparatedSiufMachineRegRoot = -2147024882;
      }
    }
    else
    {
      v6 = 0;
      if ( (unsigned int)dword_140028000 > 2
        && (qword_140028010 & 0x400000000000LL) != 0
        && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
      {
        v24 = 0x1000000;
        v25 = "IsAnotherDmClientRunning";
        v20 = 109;
        v26 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v27 = (__int64)"GetStateSeparatedSiufMachineRegRoot failed";
        v21 = StateSeparatedSiufMachineRegRoot;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140028010,
          (unsigned int)word_140022292,
          qword_140028018,
          v5,
          (__int64)&v27,
          (__int64)&v21,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&v20,
          (__int64)&v24);
      }
    }
    if ( lpMem )
    {
      v17 = GetProcessHeap();
      HeapFree(v17, 0, lpMem);
    }
    if ( v6 )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v6);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)StateSeparatedSiufMachineRegRoot;
}

```

## disassembly

```asm
0x14000784c  mov     [rsp-8+arg_10], rbx
0x140007851  mov     [rsp-8+arg_18], rsi
0x140007856  push    rbp
0x140007857  push    rdi
0x140007858  push    r13
0x14000785a  push    r14
0x14000785c  push    r15
0x14000785e  lea     rbp, [rsp-10h]
0x140007863  sub     rsp, 110h
0x14000786a  mov     rax, cs:__security_cookie
0x140007871  xor     rax, rsp
0x140007874  mov     [rbp+30h+var_30], rax
0x140007878  xor     r13d, r13d
0x14000787b  xorps   xmm0, xmm0
0x14000787e  mov     [rbp+30h+hKey], r13
0x140007882  mov     r15, rdx
0x140007885  mov     [rsp+130h+dwDisposition], r13d
0x14000788a  mov     rbx, rcx
0x14000788d  mov     [rsp+130h+lpMem], r13
0x140007892  movups  xmmword ptr [rbp+30h+SystemTime.wYear], xmm0
0x140007896  test    rcx, rcx
0x140007899  jz      short loc_14000789F
0x14000789b  mov     [rcx], r13w
0x14000789f  test    r15, r15
0x1400078a2  jnz     short loc_1400078AE
0x1400078a4  mov     edi, 80004003h
0x1400078a9  jmp     loc_140007C6B
0x1400078ae  lea     rcx, [rsp+130h+lpMem]; unsigned __int16 **
0x1400078b3  call    ?GetStateSeparatedSiufMachineRegRoot@@YAJPEAPEAG@Z; GetStateSeparatedSiufMachineRegRoot(ushort * *)
0x1400078b8  mov     edi, eax
0x1400078ba  test    eax, eax
0x1400078bc  jns     loc_140007988
0x1400078c2  mov     ecx, cs:dword_140028000
0x1400078c8  mov     rsi, r13
0x1400078cb  cmp     ecx, 2
0x1400078ce  jbe     loc_140007C1D
0x1400078d4  mov     r8, cs:qword_140028018
0x1400078db  mov     rdx, 400000000000h
0x1400078e5  mov     rcx, cs:qword_140028010
0x1400078ec  test    rdx, rcx
0x1400078ef  jz      loc_140007C1D
0x1400078f5  mov     rax, r8
0x1400078f8  and     rax, rdx
0x1400078fb  cmp     rax, r8
0x1400078fe  jnz     loc_140007C1D
0x140007904  lea     rax, aIsanotherdmcli; "IsAnotherDmClientRunning"
0x14000790b  mov     [rsp+130h+var_C8], 1000000h
0x140007914  mov     [rsp+130h+var_C0], rax
0x140007919  lea     rdx, word_140022292
0x140007920  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140007927  mov     [rsp+130h+var_E0], 6Dh ; 'm'
0x14000792f  mov     [rsp+130h+var_B8], rax
0x140007934  lea     rax, aGetstatesepara; "GetStateSeparatedSiufMachineRegRoot fai"...
0x14000793b  mov     [rbp+30h+var_B0], rax
0x14000793f  lea     rax, [rsp+130h+var_C8]
0x140007944  mov     [rsp+130h+var_E8], rax
0x140007949  lea     rax, [rsp+130h+var_E0]
0x14000794e  mov     [rsp+130h+lpdwDisposition], rax
0x140007953  lea     rax, [rsp+130h+var_C0]
0x140007958  mov     [rsp+130h+phkResult], rax
0x14000795d  lea     rax, [rsp+130h+var_B8]
0x140007962  mov     [rsp+130h+lpSecurityAttributes], rax
0x140007967  lea     rax, [rsp+130h+var_DC]
0x14000796c  mov     qword ptr [rsp+130h+samDesired], rax
0x140007971  lea     rax, [rbp+30h+var_B0]
0x140007975  mov     [rsp+130h+var_DC], edi
0x140007979  mov     qword ptr [rsp+130h+dwOptions], rax
0x14000797e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140007983  jmp     loc_140007C1D
0x140007988  call    cs:__imp_GetProcessHeap
0x14000798f  nop     dword ptr [rax+rax+00h]
0x140007994  mov     edx, 8; dwFlags
0x140007999  mov     r8d, 0A0h; dwBytes
0x14000799f  mov     rcx, rax; hHeap
0x1400079a2  call    cs:__imp_HeapAlloc
0x1400079a9  nop     dword ptr [rax+rax+00h]
0x1400079ae  mov     rsi, rax
0x1400079b1  test    rax, rax
0x1400079b4  jnz     short loc_1400079C0
0x1400079b6  mov     edi, 8007000Eh
0x1400079bb  jmp     loc_140007C1D
0x1400079c0  lea     rcx, [rbp+30h+SystemTime]; lpSystemTime
0x1400079c4  call    cs:__imp_GetSystemTime
0x1400079cb  nop     dword ptr [rax+rax+00h]
0x1400079d0  movzx   ecx, [rbp+30h+SystemTime.wDay]
0x1400079d4  mov     r14d, 50h ; 'P'
0x1400079da  movzx   edx, [rbp+30h+SystemTime.wMonth]
0x1400079de  movzx   r8d, [rbp+30h+SystemTime.wYear]
0x1400079e3  movzx   eax, [rbp+30h+SystemTime.wHour]
0x1400079e7  mov     r9, [rsp+130h+lpMem]
0x1400079ec  mov     dword ptr [rsp+130h+phkResult], eax
0x1400079f0  mov     dword ptr [rsp+130h+lpSecurityAttributes], ecx
0x1400079f4  mov     rcx, rsi; unsigned __int16 *
0x1400079f7  mov     [rsp+130h+samDesired], edx
0x1400079fb  mov     edx, r14d; unsigned __int64
0x1400079fe  mov     [rsp+130h+dwOptions], r8d
0x140007a03  lea     r8, aSDmclientinsta; "%s\\DmClientInstanceMutex%04u%02u%02u%0"...
0x140007a0a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007a0f  mov     edi, eax
0x140007a11  test    eax, eax
0x140007a13  jns     loc_140007AD2
0x140007a19  mov     eax, cs:dword_140028000
0x140007a1f  cmp     eax, 2
0x140007a22  jbe     loc_140007C1D
0x140007a28  mov     rcx, cs:qword_140028018
0x140007a2f  mov     rdx, 400000000000h
0x140007a39  mov     rax, cs:qword_140028010
0x140007a40  test    rdx, rax
0x140007a43  jz      loc_140007C1D
0x140007a49  mov     rax, rcx
0x140007a4c  and     rax, rdx
0x140007a4f  cmp     rax, rcx
0x140007a52  jnz     loc_140007C1D
0x140007a58  lea     rax, aIsanotherdmcli; "IsAnotherDmClientRunning"
0x140007a5f  mov     [rbp+30h+var_B0], 1000000h
0x140007a67  mov     [rsp+130h+var_B8], rax
0x140007a6c  lea     rdx, byte_14002175B
0x140007a73  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140007a7a  mov     [rsp+130h+var_DC], 83h
0x140007a82  mov     [rsp+130h+var_C0], rax
0x140007a87  lea     rax, aStringcchprint_0; "StringCchPrintfW failed"
0x140007a8e  mov     [rsp+130h+var_C8], rax
0x140007a93  lea     rax, [rbp+30h+var_B0]
0x140007a97  mov     [rsp+130h+var_E8], rax
0x140007a9c  lea     rax, [rsp+130h+var_DC]
0x140007aa1  mov     [rsp+130h+lpdwDisposition], rax
0x140007aa6  lea     rax, [rsp+130h+var_B8]
0x140007aab  mov     [rsp+130h+phkResult], rax
0x140007ab0  lea     rax, [rsp+130h+var_C0]
0x140007ab5  mov     [rsp+130h+lpSecurityAttributes], rax
0x140007aba  lea     rax, [rsp+130h+var_E0]
0x140007abf  mov     qword ptr [rsp+130h+samDesired], rax
0x140007ac4  lea     rax, [rsp+130h+var_C8]
0x140007ac9  mov     [rsp+130h+var_E0], edi
0x140007acd  jmp     loc_140007979
0x140007ad2  lea     rax, [rsp+130h+dwDisposition]
0x140007ad7  xor     r9d, r9d; lpClass
0x140007ada  mov     [rsp+130h+lpdwDisposition], rax; lpdwDisposition
0x140007adf  xor     r8d, r8d; Reserved
0x140007ae2  lea     rax, [rbp+30h+hKey]
0x140007ae6  mov     rdx, rsi; lpSubKey
0x140007ae9  mov     [rsp+130h+phkResult], rax; phkResult
0x140007aee  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140007af5  mov     [rsp+130h+lpSecurityAttributes], r13; lpSecurityAttributes
0x140007afa  mov     [rsp+130h+samDesired], 0F003Fh; samDesired
0x140007b02  mov     [rsp+130h+dwOptions], 1; dwOptions
0x140007b0a  call    cs:__imp_RegCreateKeyExW
0x140007b11  nop     dword ptr [rax+rax+00h]
0x140007b16  mov     ecx, cs:dword_140028000
0x140007b1c  mov     r13d, eax
0x140007b1f  cmp     ecx, 5
0x140007b22  jbe     loc_140007BB3
0x140007b28  mov     ecx, [rsp+130h+dwDisposition]
0x140007b2c  xor     edx, edx
0x140007b2e  mov     [rsp+130h+var_E0], eax
0x140007b32  lea     rax, [rsp+130h+var_DC]
0x140007b37  mov     [rbp+30h+var_40], rax
0x140007b3b  lea     rax, [rsp+130h+var_E0]
0x140007b40  mov     [rbp+30h+var_50], rax
0x140007b44  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007b48  mov     [rsp+130h+var_DC], ecx
0x140007b4c  mov     [rbp+30h+var_38], 4
0x140007b54  mov     [rbp+30h+var_48], 4
0x140007b5c  inc     rax
0x140007b5f  cmp     [rsi+rax*2], dx
0x140007b63  jnz     short loc_140007B5C
0x140007b65  lea     eax, ds:2[rax*2]
0x140007b6c  mov     [rbp+30h+var_54], edx
0x140007b6f  mov     [rbp+30h+var_58], eax
0x140007b72  lea     rdx, word_140021FA6
0x140007b79  lea     rax, aCreateInstance; "Create instance key result..."
0x140007b80  mov     [rbp+30h+var_60], rsi
0x140007b84  mov     [rbp+30h+var_70], rax
0x140007b88  lea     rcx, dword_140028000
0x140007b8f  lea     rax, [rbp+30h+var_90]
0x140007b93  mov     [rbp+30h+var_68], 1Eh
0x140007b9b  mov     qword ptr [rsp+130h+samDesired], rax
0x140007ba0  xor     r9d, r9d
0x140007ba3  xor     r8d, r8d
0x140007ba6  mov     [rsp+130h+dwOptions], 6
0x140007bae  call    _tlgWriteTransfer_EventWriteTransfer
0x140007bb3  test    r13d, r13d
0x140007bb6  jnz     short loc_140007C1A
0x140007bb8  mov     rcx, [rbp+30h+hKey]; hKey
0x140007bbc  call    cs:__imp_RegCloseKey
0x140007bc3  nop     dword ptr [rax+rax+00h]
0x140007bc8  xor     r13d, r13d
0x140007bcb  cmp     [rsp+130h+dwDisposition], 1
0x140007bd0  jnz     short loc_140007C11
0x140007bd2  test    rbx, rbx
0x140007bd5  jz      short loc_140007C1D
0x140007bd7  mov     eax, 7FFFFFFEh
0x140007bdc  mov     rcx, rsi
0x140007bdf  test    rax, rax
0x140007be2  jz      short loc_140007C00
0x140007be4  movzx   edx, word ptr [rcx]
0x140007be7  test    dx, dx
0x140007bea  jz      short loc_140007C00
0x140007bec  mov     [rbx], dx
0x140007bef  add     rcx, 2
0x140007bf3  add     rbx, 2
0x140007bf7  dec     rax
0x140007bfa  sub     r14, 1
0x140007bfe  jnz     short loc_140007BDF
0x140007c00  test    r14, r14
0x140007c03  lea     rcx, [rbx-2]
0x140007c07  cmovnz  rcx, rbx
0x140007c0b  mov     [rcx], r13w
0x140007c0f  jmp     short loc_140007C1D
0x140007c11  mov     dword ptr [r15], 1
0x140007c18  jmp     short loc_140007C1D
0x140007c1a  xor     r13d, r13d
0x140007c1d  cmp     [rsp+130h+lpMem], r13
0x140007c22  jz      short loc_140007C46
0x140007c24  call    cs:__imp_GetProcessHeap
0x140007c2b  nop     dword ptr [rax+rax+00h]
0x140007c30  mov     r8, [rsp+130h+lpMem]; lpMem
0x140007c35  xor     edx, edx; dwFlags
0x140007c37  mov     rcx, rax; hHeap
0x140007c3a  call    cs:__imp_HeapFree
0x140007c41  nop     dword ptr [rax+rax+00h]
0x140007c46  test    rsi, rsi
0x140007c49  jz      short loc_140007C6B
0x140007c4b  call    cs:__imp_GetProcessHeap
0x140007c52  nop     dword ptr [rax+rax+00h]
0x140007c57  mov     r8, rsi; lpMem
0x140007c5a  xor     edx, edx; dwFlags
0x140007c5c  mov     rcx, rax; hHeap
0x140007c5f  call    cs:__imp_HeapFree
0x140007c66  nop     dword ptr [rax+rax+00h]
0x140007c6b  mov     eax, edi
0x140007c6d  mov     rcx, [rbp+30h+var_30]
0x140007c71  xor     rcx, rsp; StackCookie
0x140007c74  call    __security_check_cookie
0x140007c79  lea     r11, [rsp+130h+var_20]
0x140007c81  mov     rbx, [r11+40h]
0x140007c85  mov     rsi, [r11+48h]
0x140007c89  mov     rsp, r11
0x140007c8c  pop     r15
0x140007c8e  pop     r14
0x140007c90  pop     r13
0x140007c92  pop     rdi
0x140007c93  pop     rbp
0x140007c94  retn
```
