# IsAnotherDmClientRunning(ushort *,int *)

- ea: `0x1400076e4`
- end: `0x140007af7`
- name: `?IsAnotherDmClientRunning@@YAJPEAGPEAH@Z`
- size: `1043`
- prototype: `__int64 __fastcall(unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000c47c`

## callees

- `0x140001414`
- `0x14000182c`
- `0x1400076e4`
- `0x14000b5c4`
- `0x140017770`
- `0x1400187e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140007990`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140007990`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007a3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007a3c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007834`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007834`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007820`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007a9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007ab9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007820`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007a9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007ab9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007aae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007ac7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007aae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007ac7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140007850`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140007850`

## string_xrefs

- `0x1400079f9`: `Create instance key result...`

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
          if ( (unsigned int)dword_140027000 > 5 )
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
            tlgWriteTransfer_EventWriteTransfer(&dword_140027000, &word_140020F9E, 0, 0, 6, v30);
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
        else if ( (unsigned int)dword_140027000 > 2
               && (qword_140027010 & 0x400000000000LL) != 0
               && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
        {
          v27 = 0x1000000;
          v26 = "IsAnotherDmClientRunning";
          v21 = 131;
          v25 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
          v24 = (__int64)"StringCchPrintfW failed";
          v20 = StateSeparatedSiufMachineRegRoot;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_140027018,
            (unsigned int)byte_140020753,
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
      if ( (unsigned int)dword_140027000 > 2
        && (qword_140027010 & 0x400000000000LL) != 0
        && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
      {
        v24 = 0x1000000;
        v25 = "IsAnotherDmClientRunning";
        v20 = 109;
        v26 = "onecore\\base\\diagnosis\\feedback\\siuf\\deploymentmgr\\client\\exe\\main.cpp";
        v27 = (__int64)"GetStateSeparatedSiufMachineRegRoot failed";
        v21 = StateSeparatedSiufMachineRegRoot;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          qword_140027010,
          (unsigned int)word_14002128A,
          qword_140027018,
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
0x1400076e4  mov     [rsp-8+arg_10], rbx
0x1400076e9  mov     [rsp-8+arg_18], rsi
0x1400076ee  push    rbp
0x1400076ef  push    rdi
0x1400076f0  push    r13
0x1400076f2  push    r14
0x1400076f4  push    r15
0x1400076f6  lea     rbp, [rsp-10h]
0x1400076fb  sub     rsp, 110h
0x140007702  mov     rax, cs:__security_cookie
0x140007709  xor     rax, rsp
0x14000770c  mov     [rbp+30h+var_30], rax
0x140007710  xor     r13d, r13d
0x140007713  xorps   xmm0, xmm0
0x140007716  mov     [rbp+30h+hKey], r13
0x14000771a  mov     r15, rdx
0x14000771d  mov     [rsp+130h+dwDisposition], r13d
0x140007722  mov     rbx, rcx
0x140007725  mov     [rsp+130h+lpMem], r13
0x14000772a  movups  xmmword ptr [rbp+30h+SystemTime.wYear], xmm0
0x14000772e  test    rcx, rcx
0x140007731  jz      short loc_140007737
0x140007733  mov     [rcx], r13w
0x140007737  test    r15, r15
0x14000773a  jnz     short loc_140007746
0x14000773c  mov     edi, 80004003h
0x140007741  jmp     loc_140007ACD
0x140007746  lea     rcx, [rsp+130h+lpMem]; unsigned __int16 **
0x14000774b  call    ?GetStateSeparatedSiufMachineRegRoot@@YAJPEAPEAG@Z; GetStateSeparatedSiufMachineRegRoot(ushort * *)
0x140007750  mov     edi, eax
0x140007752  test    eax, eax
0x140007754  jns     loc_140007820
0x14000775a  mov     ecx, cs:dword_140027000
0x140007760  mov     rsi, r13
0x140007763  cmp     ecx, 2
0x140007766  jbe     loc_140007A97
0x14000776c  mov     r8, cs:qword_140027018
0x140007773  mov     rdx, 400000000000h
0x14000777d  mov     rcx, cs:qword_140027010
0x140007784  test    rdx, rcx
0x140007787  jz      loc_140007A97
0x14000778d  mov     rax, r8
0x140007790  and     rax, rdx
0x140007793  cmp     rax, r8
0x140007796  jnz     loc_140007A97
0x14000779c  lea     rax, aIsanotherdmcli; "IsAnotherDmClientRunning"
0x1400077a3  mov     [rsp+130h+var_C8], 1000000h
0x1400077ac  mov     [rsp+130h+var_C0], rax
0x1400077b1  lea     rdx, word_14002128A
0x1400077b8  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x1400077bf  mov     [rsp+130h+var_E0], 6Dh ; 'm'
0x1400077c7  mov     [rsp+130h+var_B8], rax
0x1400077cc  lea     rax, aGetstatesepara; "GetStateSeparatedSiufMachineRegRoot fai"...
0x1400077d3  mov     [rbp+30h+var_B0], rax
0x1400077d7  lea     rax, [rsp+130h+var_C8]
0x1400077dc  mov     [rsp+130h+var_E8], rax
0x1400077e1  lea     rax, [rsp+130h+var_E0]
0x1400077e6  mov     [rsp+130h+lpdwDisposition], rax
0x1400077eb  lea     rax, [rsp+130h+var_C0]
0x1400077f0  mov     [rsp+130h+phkResult], rax
0x1400077f5  lea     rax, [rsp+130h+var_B8]
0x1400077fa  mov     [rsp+130h+lpSecurityAttributes], rax
0x1400077ff  lea     rax, [rsp+130h+var_DC]
0x140007804  mov     qword ptr [rsp+130h+samDesired], rax
0x140007809  lea     rax, [rbp+30h+var_B0]
0x14000780d  mov     [rsp+130h+var_DC], edi
0x140007811  mov     qword ptr [rsp+130h+dwOptions], rax
0x140007816  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000781b  jmp     loc_140007A97
0x140007820  call    cs:__imp_GetProcessHeap
0x140007826  mov     edx, 8; dwFlags
0x14000782b  mov     r8d, 0A0h; dwBytes
0x140007831  mov     rcx, rax; hHeap
0x140007834  call    cs:__imp_HeapAlloc
0x14000783a  mov     rsi, rax
0x14000783d  test    rax, rax
0x140007840  jnz     short loc_14000784C
0x140007842  mov     edi, 8007000Eh
0x140007847  jmp     loc_140007A97
0x14000784c  lea     rcx, [rbp+30h+SystemTime]; lpSystemTime
0x140007850  call    cs:__imp_GetSystemTime
0x140007856  movzx   ecx, [rbp+30h+SystemTime.wDay]
0x14000785a  mov     r14d, 50h ; 'P'
0x140007860  movzx   edx, [rbp+30h+SystemTime.wMonth]
0x140007864  movzx   r8d, [rbp+30h+SystemTime.wYear]
0x140007869  movzx   eax, [rbp+30h+SystemTime.wHour]
0x14000786d  mov     r9, [rsp+130h+lpMem]
0x140007872  mov     dword ptr [rsp+130h+phkResult], eax
0x140007876  mov     dword ptr [rsp+130h+lpSecurityAttributes], ecx
0x14000787a  mov     rcx, rsi; unsigned __int16 *
0x14000787d  mov     [rsp+130h+samDesired], edx
0x140007881  mov     edx, r14d; unsigned __int64
0x140007884  mov     [rsp+130h+dwOptions], r8d
0x140007889  lea     r8, aSDmclientinsta; "%s\\DmClientInstanceMutex%04u%02u%02u%0"...
0x140007890  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007895  mov     edi, eax
0x140007897  test    eax, eax
0x140007899  jns     loc_140007958
0x14000789f  mov     eax, cs:dword_140027000
0x1400078a5  cmp     eax, 2
0x1400078a8  jbe     loc_140007A97
0x1400078ae  mov     rcx, cs:qword_140027018
0x1400078b5  mov     rdx, 400000000000h
0x1400078bf  mov     rax, cs:qword_140027010
0x1400078c6  test    rdx, rax
0x1400078c9  jz      loc_140007A97
0x1400078cf  mov     rax, rcx
0x1400078d2  and     rax, rdx
0x1400078d5  cmp     rax, rcx
0x1400078d8  jnz     loc_140007A97
0x1400078de  lea     rax, aIsanotherdmcli; "IsAnotherDmClientRunning"
0x1400078e5  mov     [rbp+30h+var_B0], 1000000h
0x1400078ed  mov     [rsp+130h+var_B8], rax
0x1400078f2  lea     rdx, byte_140020753
0x1400078f9  lea     rax, aOnecoreBaseDia; "onecore\\base\\diagnosis\\feedback\\siu"...
0x140007900  mov     [rsp+130h+var_DC], 83h
0x140007908  mov     [rsp+130h+var_C0], rax
0x14000790d  lea     rax, aStringcchprint_0; "StringCchPrintfW failed"
0x140007914  mov     [rsp+130h+var_C8], rax
0x140007919  lea     rax, [rbp+30h+var_B0]
0x14000791d  mov     [rsp+130h+var_E8], rax
0x140007922  lea     rax, [rsp+130h+var_DC]
0x140007927  mov     [rsp+130h+lpdwDisposition], rax
0x14000792c  lea     rax, [rsp+130h+var_B8]
0x140007931  mov     [rsp+130h+phkResult], rax
0x140007936  lea     rax, [rsp+130h+var_C0]
0x14000793b  mov     [rsp+130h+lpSecurityAttributes], rax
0x140007940  lea     rax, [rsp+130h+var_E0]
0x140007945  mov     qword ptr [rsp+130h+samDesired], rax
0x14000794a  lea     rax, [rsp+130h+var_C8]
0x14000794f  mov     [rsp+130h+var_E0], edi
0x140007953  jmp     loc_140007811
0x140007958  lea     rax, [rsp+130h+dwDisposition]
0x14000795d  xor     r9d, r9d; lpClass
0x140007960  mov     [rsp+130h+lpdwDisposition], rax; lpdwDisposition
0x140007965  xor     r8d, r8d; Reserved
0x140007968  lea     rax, [rbp+30h+hKey]
0x14000796c  mov     rdx, rsi; lpSubKey
0x14000796f  mov     [rsp+130h+phkResult], rax; phkResult
0x140007974  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000797b  mov     [rsp+130h+lpSecurityAttributes], r13; lpSecurityAttributes
0x140007980  mov     [rsp+130h+samDesired], 0F003Fh; samDesired
0x140007988  mov     [rsp+130h+dwOptions], 1; dwOptions
0x140007990  call    cs:__imp_RegCreateKeyExW
0x140007996  mov     ecx, cs:dword_140027000
0x14000799c  mov     r13d, eax
0x14000799f  cmp     ecx, 5
0x1400079a2  jbe     loc_140007A33
0x1400079a8  mov     ecx, [rsp+130h+dwDisposition]
0x1400079ac  xor     edx, edx
0x1400079ae  mov     [rsp+130h+var_E0], eax
0x1400079b2  lea     rax, [rsp+130h+var_DC]
0x1400079b7  mov     [rbp+30h+var_40], rax
0x1400079bb  lea     rax, [rsp+130h+var_E0]
0x1400079c0  mov     [rbp+30h+var_50], rax
0x1400079c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400079c8  mov     [rsp+130h+var_DC], ecx
0x1400079cc  mov     [rbp+30h+var_38], 4
0x1400079d4  mov     [rbp+30h+var_48], 4
0x1400079dc  inc     rax
0x1400079df  cmp     [rsi+rax*2], dx
0x1400079e3  jnz     short loc_1400079DC
0x1400079e5  lea     eax, ds:2[rax*2]
0x1400079ec  mov     [rbp+30h+var_54], edx
0x1400079ef  mov     [rbp+30h+var_58], eax
0x1400079f2  lea     rdx, word_140020F9E
0x1400079f9  lea     rax, aCreateInstance; "Create instance key result..."
0x140007a00  mov     [rbp+30h+var_60], rsi
0x140007a04  mov     [rbp+30h+var_70], rax
0x140007a08  lea     rcx, dword_140027000
0x140007a0f  lea     rax, [rbp+30h+var_90]
0x140007a13  mov     [rbp+30h+var_68], 1Eh
0x140007a1b  mov     qword ptr [rsp+130h+samDesired], rax
0x140007a20  xor     r9d, r9d
0x140007a23  xor     r8d, r8d
0x140007a26  mov     [rsp+130h+dwOptions], 6
0x140007a2e  call    _tlgWriteTransfer_EventWriteTransfer
0x140007a33  test    r13d, r13d
0x140007a36  jnz     short loc_140007A94
0x140007a38  mov     rcx, [rbp+30h+hKey]; hKey
0x140007a3c  call    cs:__imp_RegCloseKey
0x140007a42  xor     r13d, r13d
0x140007a45  cmp     [rsp+130h+dwDisposition], 1
0x140007a4a  jnz     short loc_140007A8B
0x140007a4c  test    rbx, rbx
0x140007a4f  jz      short loc_140007A97
0x140007a51  mov     eax, 7FFFFFFEh
0x140007a56  mov     rcx, rsi
0x140007a59  test    rax, rax
0x140007a5c  jz      short loc_140007A7A
0x140007a5e  movzx   edx, word ptr [rcx]
0x140007a61  test    dx, dx
0x140007a64  jz      short loc_140007A7A
0x140007a66  mov     [rbx], dx
0x140007a69  add     rcx, 2
0x140007a6d  add     rbx, 2
0x140007a71  dec     rax
0x140007a74  sub     r14, 1
0x140007a78  jnz     short loc_140007A59
0x140007a7a  test    r14, r14
0x140007a7d  lea     rcx, [rbx-2]
0x140007a81  cmovnz  rcx, rbx
0x140007a85  mov     [rcx], r13w
0x140007a89  jmp     short loc_140007A97
0x140007a8b  mov     dword ptr [r15], 1
0x140007a92  jmp     short loc_140007A97
0x140007a94  xor     r13d, r13d
0x140007a97  cmp     [rsp+130h+lpMem], r13
0x140007a9c  jz      short loc_140007AB4
0x140007a9e  call    cs:__imp_GetProcessHeap
0x140007aa4  mov     r8, [rsp+130h+lpMem]; lpMem
0x140007aa9  xor     edx, edx; dwFlags
0x140007aab  mov     rcx, rax; hHeap
0x140007aae  call    cs:__imp_HeapFree
0x140007ab4  test    rsi, rsi
0x140007ab7  jz      short loc_140007ACD
0x140007ab9  call    cs:__imp_GetProcessHeap
0x140007abf  mov     r8, rsi; lpMem
0x140007ac2  xor     edx, edx; dwFlags
0x140007ac4  mov     rcx, rax; hHeap
0x140007ac7  call    cs:__imp_HeapFree
0x140007acd  mov     eax, edi
0x140007acf  mov     rcx, [rbp+30h+var_30]
0x140007ad3  xor     rcx, rsp; StackCookie
0x140007ad6  call    __security_check_cookie
0x140007adb  lea     r11, [rsp+130h+var_20]
0x140007ae3  mov     rbx, [r11+40h]
0x140007ae7  mov     rsi, [r11+48h]
0x140007aeb  mov     rsp, r11
0x140007aee  pop     r15
0x140007af0  pop     r14
0x140007af2  pop     r13
0x140007af4  pop     rdi
0x140007af5  pop     rbp
0x140007af6  retn
```
