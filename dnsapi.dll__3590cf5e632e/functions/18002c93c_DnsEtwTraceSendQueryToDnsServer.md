# DnsEtwTraceSendQueryToDnsServer

- ea: `0x18002c93c`
- end: `0x18002cddc`
- name: `DnsEtwTraceSendQueryToDnsServer`
- size: `1184`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025fc0`
- `0x1800464f8`
- `0x180050ac8`
- `0x1800a89e0`

## callees

- `0x18002ba40`
- `0x18002bc00`
- `0x18002c93c`
- `0x18003ce84`
- `0x180083954`
- `0x18008b5f0`
- `0x1800cafec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002cd80`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002cd80`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002cbc2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18002cbc2`
- `ntdll!RtlIpv6AddressToStringW` at `0x18002cd01`
- `ntdll!RtlIpv6AddressToStringW` at `0x18002cd01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cdac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cdc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd2a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cdac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cdc4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cadc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cadc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cb2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c9cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c9f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ca23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c9cf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002c9f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002ca23`

## pseudocode

```c
void __fastcall DnsEtwTraceSendQueryToDnsServer(__int64 a1, __int64 a2)
{
  HANDLE ProcessHeap; // rax
  WCHAR *v5; // rdi
  HANDLE v6; // rax
  WCHAR *v7; // r14
  HANDLE v8; // rax
  CHAR *v9; // rax
  CHAR *v10; // rsi
  unsigned int v11; // r13d
  __int64 v12; // r11
  unsigned int v13; // r9d
  unsigned int v14; // ebx
  unsigned int v15; // r12d
  HANDLE v16; // rax
  HANDLE v17; // rax
  HANDLE v18; // rax
  DWORD v19; // r10d
  char v20; // cl
  __int64 v21; // r8
  unsigned int v22; // r8d
  __int64 v23; // rcx
  __int64 v24; // rax
  LPWSTR lpWideCharStr; // [rsp+20h] [rbp-89h]
  __int64 cchWideChar; // [rsp+28h] [rbp-81h]
  DWORD CurrentProcessId; // [rsp+40h] [rbp-69h]
  unsigned __int16 v28; // [rsp+44h] [rbp-65h]
  unsigned int v29; // [rsp+48h] [rbp-61h]
  __int64 v30; // [rsp+50h] [rbp-59h]
  DWORD v31; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v32; // [rsp+60h] [rbp-49h] BYREF
  char v33[16]; // [rsp+70h] [rbp-39h] BYREF
  WCHAR *v34; // [rsp+80h] [rbp-29h]
  int v35; // [rsp+88h] [rbp-21h]
  int v36; // [rsp+8Ch] [rbp-1Dh]
  unsigned int *v37; // [rsp+90h] [rbp-19h]
  __int64 v38; // [rsp+98h] [rbp-11h]
  WCHAR *v39; // [rsp+A0h] [rbp-9h]
  int v40; // [rsp+A8h] [rbp-1h]
  int v41; // [rsp+ACh] [rbp+3h]
  DWORD *v42; // [rsp+B0h] [rbp+7h]
  __int64 v43; // [rsp+B8h] [rbp+Fh]

  if ( a1 && g_DnsIsCache && !*(_DWORD *)(a1 + 664) )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  if ( (Microsoft_Windows_DNS_ClientEnableBits & 4) != 0 && a1 )
  {
    CurrentProcessId = *(_DWORD *)(a1 + 664);
    if ( !CurrentProcessId )
      CurrentProcessId = GetCurrentProcessId();
    ProcessHeap = g_hProcessHeap;
    if ( !g_hProcessHeap )
    {
      ProcessHeap = GetProcessHeap();
      g_hProcessHeap = ProcessHeap;
    }
    v5 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0x84u);
    v6 = g_hProcessHeap;
    if ( !g_hProcessHeap )
    {
      v6 = GetProcessHeap();
      g_hProcessHeap = v6;
    }
    v7 = (WCHAR *)HeapAlloc(v6, 8u, 0x1FEu);
    v8 = g_hProcessHeap;
    if ( !g_hProcessHeap )
    {
      v8 = GetProcessHeap();
      g_hProcessHeap = v8;
    }
    v9 = (CHAR *)HeapAlloc(v8, 8u, 0xFFu);
    v10 = v9;
    if ( v5 )
    {
      if ( v7 )
      {
        if ( v9 )
        {
          v11 = *(_DWORD *)(a1 + 584);
          *v9 = 0;
          if ( v11 )
          {
            v12 = a1 + 712;
            v13 = *(unsigned __int8 *)(a1 + 712);
            v14 = 0;
            v30 = v12;
            v28 = 0;
            v15 = 1;
            while ( v13 )
            {
              v31 = v14 + v13;
              if ( v14 + v13 + 1 >= 0xFF || (v29 = v15 + v13, v32 = v15 + v13 + 1, v32 >= v11) )
              {
                if ( v14 >= 0xFF )
                  goto LABEL_24;
                break;
              }
              memcpy_0(&v10[v14], (const void *)(v12 + v15), v13);
              if ( v29 < v15 )
                goto LABEL_24;
              v19 = v31;
              if ( v31 < v14 )
                goto LABEL_24;
              v12 = v30;
              v15 = v32;
              v13 = *(unsigned __int8 *)(v29 + v30);
              if ( *(_BYTE *)(v29 + v30) )
              {
                v20 = 46;
              }
              else
              {
                if ( v11 > v32 + 1 )
                  v28 = (*(unsigned __int8 *)(v32 + v30) << 8) + *(unsigned __int8 *)(v32 + v30 + 1);
                v20 = 0;
              }
              v10[v31] = v20;
              v14 = v19 + 1;
            }
            if ( v14 && MultiByteToWideChar(0, 0, v10, v14, v7, 255) )
            {
              if ( a2 )
              {
                if ( *(_WORD *)a2 == 2 )
                {
                  v22 = *(_DWORD *)(a2 + 4);
                  LODWORD(cchWideChar) = BYTE2(v22);
                  LODWORD(lpWideCharStr) = BYTE1(v22);
                  Dns_SprintfPointerW(
                    v5,
                    16,
                    L"%u.%u.%u.%u",
                    (unsigned __int8)v22,
                    lpWideCharStr,
                    cchWideChar,
                    HIBYTE(v22));
                }
                else if ( *(_WORD *)a2 == 23 )
                {
                  RtlIpv6AddressToStringW((const struct in6_addr *)(a2 + 8), v5);
                }
                else
                {
                  StringCchPrintfW(v5, 0x41u, L"Invalid DNS_ADDR at %p", a2);
                }
              }
              if ( (Microsoft_Windows_DNS_ClientEnableBits & 4) != 0 )
              {
                v23 = -1;
                v31 = CurrentProcessId;
                v32 = v28;
                v24 = -1;
                do
                  ++v24;
                while ( v7[v24] );
                v34 = v7;
                v35 = 2 * v24 + 2;
                v37 = &v32;
                v36 = 0;
                v38 = 4;
                do
                  ++v23;
                while ( v5[v23] );
                v43 = 4;
                v40 = 2 * v23 + 2;
                v39 = v5;
                v42 = &v31;
                v41 = 0;
                McGenEventWrite_EtwEventWriteTransfer(
                  &DNS_CLIENT_Context,
                  (__int64)DNS_SEND_QUERY_TO_DNSSERVER_EVENT2,
                  v21,
                  5,
                  (__int64)v33);
              }
            }
          }
        }
      }
LABEL_24:
      v16 = g_hProcessHeap;
      if ( !g_hProcessHeap )
      {
        v16 = GetProcessHeap();
        g_hProcessHeap = v16;
      }
      HeapFree(v16, 0, v5);
    }
    if ( v7 )
    {
      v17 = g_hProcessHeap;
      if ( !g_hProcessHeap )
      {
        v17 = GetProcessHeap();
        g_hProcessHeap = v17;
      }
      HeapFree(v17, 0, v7);
    }
    if ( v10 )
    {
      v18 = g_hProcessHeap;
      if ( !g_hProcessHeap )
      {
        v18 = GetProcessHeap();
        g_hProcessHeap = v18;
      }
      HeapFree(v18, 0, v10);
    }
  }
}

```

## disassembly

```asm
0x18002c93c  mov     [rsp-8+arg_10], rbx
0x18002c941  push    rbp
0x18002c942  push    rsi
0x18002c943  push    rdi
0x18002c944  push    r12
0x18002c946  push    r13
0x18002c948  push    r14
0x18002c94a  push    r15
0x18002c94c  lea     rbp, [rsp-27h]
0x18002c951  sub     rsp, 0D0h
0x18002c958  mov     rax, cs:__security_cookie
0x18002c95f  xor     rax, rsp
0x18002c962  mov     [rbp+57h+var_40], rax
0x18002c966  xor     r12d, r12d
0x18002c969  mov     r15, rdx
0x18002c96c  mov     rbx, rcx
0x18002c96f  test    rcx, rcx
0x18002c972  jz      short loc_18002C98A
0x18002c974  cmp     cs:g_DnsIsCache, r12d
0x18002c97b  jz      short loc_18002C98A
0x18002c97d  cmp     [rcx+298h], r12d
0x18002c984  jz      loc_18002CD76
0x18002c98a  test    byte ptr cs:Microsoft_Windows_DNS_ClientEnableBits, 4
0x18002c991  jz      loc_18002CB3A
0x18002c997  test    rbx, rbx
0x18002c99a  jz      loc_18002CB3A
0x18002c9a0  mov     ecx, [rbx+298h]
0x18002c9a6  mov     [rbp+57h+var_C0], ecx
0x18002c9a9  test    ecx, ecx
0x18002c9ab  jz      loc_18002CD80
0x18002c9b1  mov     rax, cs:g_hProcessHeap
0x18002c9b8  test    rax, rax
0x18002c9bb  jz      loc_18002CD94
0x18002c9c1  mov     esi, 8
0x18002c9c6  mov     rcx, rax; hHeap
0x18002c9c9  mov     edx, esi; dwFlags
0x18002c9cb  lea     r8d, [rsi+7Ch]; dwBytes
0x18002c9cf  call    cs:__imp_HeapAlloc
0x18002c9d6  nop     dword ptr [rax+rax+00h]
0x18002c9db  mov     rdi, rax
0x18002c9de  mov     rax, cs:g_hProcessHeap
0x18002c9e5  test    rax, rax
0x18002c9e8  jz      loc_18002CDAC
0x18002c9ee  mov     r8d, 1FEh; dwBytes
0x18002c9f4  mov     edx, esi; dwFlags
0x18002c9f6  mov     rcx, rax; hHeap
0x18002c9f9  call    cs:__imp_HeapAlloc
0x18002ca00  nop     dword ptr [rax+rax+00h]
0x18002ca05  mov     r14, rax
0x18002ca08  mov     rax, cs:g_hProcessHeap
0x18002ca0f  test    rax, rax
0x18002ca12  jz      loc_18002CDC4
0x18002ca18  mov     r8d, 0FFh; dwBytes
0x18002ca1e  mov     edx, esi; dwFlags
0x18002ca20  mov     rcx, rax; hHeap
0x18002ca23  call    cs:__imp_HeapAlloc
0x18002ca2a  nop     dword ptr [rax+rax+00h]
0x18002ca2f  mov     rsi, rax
0x18002ca32  test    rdi, rdi
0x18002ca35  jz      loc_18002CAE8
0x18002ca3b  test    r14, r14
0x18002ca3e  jz      loc_18002CAC4
0x18002ca44  test    rax, rax
0x18002ca47  jz      short loc_18002CAC4
0x18002ca49  mov     r13d, [rbx+248h]
0x18002ca50  mov     [rax], r12b
0x18002ca53  test    r13d, r13d
0x18002ca56  jz      short loc_18002CAC4
0x18002ca58  lea     r11, [rbx+2C8h]
0x18002ca5f  xor     eax, eax
0x18002ca61  movzx   r9d, byte ptr [r11]
0x18002ca65  mov     ebx, r12d
0x18002ca68  mov     [rbp+57h+var_B0], r11
0x18002ca6c  mov     [rbp+57h+var_BC], eax
0x18002ca6f  lea     r12d, [rax+1]
0x18002ca73  test    r9d, r9d
0x18002ca76  jz      loc_18002CBA0
0x18002ca7c  lea     eax, [rbx+r9]
0x18002ca80  mov     [rbp+57h+var_A8], eax
0x18002ca83  inc     eax
0x18002ca85  cmp     eax, 0FFh
0x18002ca8a  jnb     loc_18002CB94
0x18002ca90  lea     eax, [r12+r9]
0x18002ca94  mov     [rbp+57h+var_B8], eax
0x18002ca97  inc     eax
0x18002ca99  mov     [rbp+57h+var_A0], eax
0x18002ca9c  cmp     eax, r13d
0x18002ca9f  jnb     loc_18002CB94
0x18002caa5  mov     edx, r12d
0x18002caa8  mov     ecx, ebx
0x18002caaa  add     rdx, r11; Src
0x18002caad  add     rcx, rsi; void *
0x18002cab0  mov     r8d, r9d; Size
0x18002cab3  call    memcpy_0
0x18002cab8  mov     eax, [rbp+57h+var_B8]
0x18002cabb  cmp     eax, r12d
0x18002cabe  jnb     loc_18002CB62
0x18002cac4  mov     rax, cs:g_hProcessHeap
0x18002cacb  test    rax, rax
0x18002cace  jz      loc_18002CD12
0x18002cad4  mov     r8, rdi; lpMem
0x18002cad7  xor     edx, edx; dwFlags
0x18002cad9  mov     rcx, rax; hHeap
0x18002cadc  call    cs:__imp_HeapFree
0x18002cae3  nop     dword ptr [rax+rax+00h]
0x18002cae8  test    r14, r14
0x18002caeb  jz      short loc_18002CB11
0x18002caed  mov     rax, cs:g_hProcessHeap
0x18002caf4  test    rax, rax
0x18002caf7  jz      loc_18002CD2A
0x18002cafd  mov     r8, r14; lpMem
0x18002cb00  xor     edx, edx; dwFlags
0x18002cb02  mov     rcx, rax; hHeap
0x18002cb05  call    cs:__imp_HeapFree
0x18002cb0c  nop     dword ptr [rax+rax+00h]
0x18002cb11  test    rsi, rsi
0x18002cb14  jz      short loc_18002CB3A
0x18002cb16  mov     rax, cs:g_hProcessHeap
0x18002cb1d  test    rax, rax
0x18002cb20  jz      loc_18002CD42
0x18002cb26  mov     r8, rsi; lpMem
0x18002cb29  xor     edx, edx; dwFlags
0x18002cb2b  mov     rcx, rax; hHeap
0x18002cb2e  call    cs:__imp_HeapFree
0x18002cb35  nop     dword ptr [rax+rax+00h]
0x18002cb3a  mov     rcx, [rbp+57h+var_40]
0x18002cb3e  xor     rcx, rsp; StackCookie
0x18002cb41  call    __security_check_cookie
0x18002cb46  mov     rbx, [rsp+100h+arg_10]
0x18002cb4e  add     rsp, 0D0h
0x18002cb55  pop     r15
0x18002cb57  pop     r14
0x18002cb59  pop     r13
0x18002cb5b  pop     r12
0x18002cb5d  pop     rdi
0x18002cb5e  pop     rsi
0x18002cb5f  pop     rbp
0x18002cb60  retn
0x18002cb62  mov     r10d, [rbp+57h+var_A8]
0x18002cb66  cmp     r10d, ebx
0x18002cb69  jb      loc_18002CAC4
0x18002cb6f  mov     r11, [rbp+57h+var_B0]
0x18002cb73  mov     r12d, [rbp+57h+var_A0]
0x18002cb77  movzx   r9d, byte ptr [rax+r11]
0x18002cb7c  test    r9d, r9d
0x18002cb7f  jz      loc_18002CCC6
0x18002cb85  mov     cl, 2Eh ; '.'
0x18002cb87  mov     [r10+rsi], cl
0x18002cb8b  lea     ebx, [r10+1]
0x18002cb8f  jmp     loc_18002CA73
0x18002cb94  cmp     ebx, 0FFh
0x18002cb9a  jnb     loc_18002CAC4
0x18002cba0  xor     r12d, r12d
0x18002cba3  test    ebx, ebx
0x18002cba5  jz      loc_18002CAC4
0x18002cbab  mov     dword ptr [rsp+100h+cchWideChar], 0FFh; cchWideChar
0x18002cbb3  mov     r9d, ebx; cbMultiByte
0x18002cbb6  mov     r8, rsi; lpMultiByteStr
0x18002cbb9  mov     [rsp+100h+lpWideCharStr], r14; lpWideCharStr
0x18002cbbe  xor     edx, edx; dwFlags
0x18002cbc0  xor     ecx, ecx; CodePage
0x18002cbc2  call    cs:__imp_MultiByteToWideChar
0x18002cbc9  nop     dword ptr [rax+rax+00h]
0x18002cbce  test    eax, eax
0x18002cbd0  jz      loc_18002CAC4
0x18002cbd6  test    r15, r15
0x18002cbd9  jz      short loc_18002CC28
0x18002cbdb  cmp     word ptr [r15], 2
0x18002cbe0  jnz     loc_18002CCF3
0x18002cbe6  mov     r8d, [r15+4]
0x18002cbea  mov     eax, r8d
0x18002cbed  shr     eax, 10h
0x18002cbf0  mov     r10d, r8d
0x18002cbf3  movzx   edx, al
0x18002cbf6  mov     eax, r8d
0x18002cbf9  shr     eax, 8
0x18002cbfc  movzx   ecx, al
0x18002cbff  shr     r10d, 18h
0x18002cc03  mov     [rsp+100h+var_D0], r10d
0x18002cc08  mov     dword ptr [rsp+100h+cchWideChar], edx
0x18002cc0c  lea     edx, [r12+10h]
0x18002cc11  mov     dword ptr [rsp+100h+lpWideCharStr], ecx
0x18002cc15  mov     rcx, rdi
0x18002cc18  movzx   r9d, r8b
0x18002cc1c  lea     r8, aUUUU; "%u.%u.%u.%u"
0x18002cc23  call    Dns_SprintfPointerW
0x18002cc28  mov     edx, 4
0x18002cc2d  test    byte ptr cs:Microsoft_Windows_DNS_ClientEnableBits, dl
0x18002cc33  jz      loc_18002CAC4
0x18002cc39  mov     eax, [rbp+57h+var_C0]
0x18002cc3c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002cc40  mov     [rbp+57h+var_A8], eax
0x18002cc43  mov     eax, [rbp+57h+var_BC]
0x18002cc46  movzx   eax, ax
0x18002cc49  mov     [rbp+57h+var_A0], eax
0x18002cc4c  mov     rax, rcx
0x18002cc4f  inc     rax
0x18002cc52  cmp     [r14+rax*2], r12w
0x18002cc57  jnz     short loc_18002CC4F
0x18002cc59  lea     eax, ds:2[rax*2]
0x18002cc60  mov     [rbp+57h+var_80], r14
0x18002cc64  mov     [rbp+57h+var_78], eax
0x18002cc67  lea     rax, [rbp+57h+var_A0]
0x18002cc6b  mov     [rbp+57h+var_70], rax
0x18002cc6f  mov     [rbp+57h+var_74], r12d
0x18002cc73  mov     [rbp+57h+var_68], rdx
0x18002cc77  inc     rcx
0x18002cc7a  cmp     [rdi+rcx*2], r12w
0x18002cc7f  jnz     short loc_18002CC77
0x18002cc81  lea     eax, ds:2[rcx*2]
0x18002cc88  mov     [rbp+57h+var_48], rdx
0x18002cc8c  mov     [rbp+57h+var_58], eax
0x18002cc8f  lea     rdx, DNS_SEND_QUERY_TO_DNSSERVER_EVENT2
0x18002cc96  lea     rax, [rbp+57h+var_A8]
0x18002cc9a  mov     [rbp+57h+var_60], rdi
0x18002cc9e  mov     [rbp+57h+var_50], rax
0x18002cca2  lea     rcx, DNS_CLIENT_Context
0x18002cca9  lea     rax, [rbp+57h+var_90]
0x18002ccad  mov     [rbp+57h+var_54], r12d
0x18002ccb1  mov     r9d, 5
0x18002ccb7  mov     [rsp+100h+lpWideCharStr], rax
0x18002ccbc  call    McGenEventWrite_EtwEventWriteTransfer
0x18002ccc1  jmp     loc_18002CAC4
0x18002ccc6  lea     eax, [r12+1]
0x18002cccb  cmp     r13d, eax
0x18002ccce  jbe     short loc_18002CCEC
0x18002ccd0  movzx   edx, byte ptr [r12+r11]
0x18002ccd5  mov     eax, 100h
0x18002ccda  movzx   r8d, byte ptr [r12+r11+1]
0x18002cce0  imul    edx, eax
0x18002cce3  add     r8w, dx
0x18002cce7  mov     word ptr [rbp+57h+var_BC], r8w
0x18002ccec  xor     cl, cl
0x18002ccee  jmp     loc_18002CB87
0x18002ccf3  cmp     word ptr [r15], 17h
0x18002ccf8  jnz     short loc_18002CD5A
0x18002ccfa  lea     rcx, [r15+8]; Addr
0x18002ccfe  mov     rdx, rdi; S
0x18002cd01  call    cs:__imp_RtlIpv6AddressToStringW
0x18002cd08  nop     dword ptr [rax+rax+00h]
0x18002cd0d  jmp     loc_18002CC28
0x18002cd12  call    cs:__imp_GetProcessHeap
0x18002cd19  nop     dword ptr [rax+rax+00h]
0x18002cd1e  mov     cs:g_hProcessHeap, rax
0x18002cd25  jmp     loc_18002CAD4
0x18002cd2a  call    cs:__imp_GetProcessHeap
0x18002cd31  nop     dword ptr [rax+rax+00h]
0x18002cd36  mov     cs:g_hProcessHeap, rax
0x18002cd3d  jmp     loc_18002CAFD
0x18002cd42  call    cs:__imp_GetProcessHeap
0x18002cd49  nop     dword ptr [rax+rax+00h]
0x18002cd4e  mov     cs:g_hProcessHeap, rax
0x18002cd55  jmp     loc_18002CB26
0x18002cd5a  mov     r9, r15
0x18002cd5d  lea     r8, aInvalidDnsAddr; "Invalid DNS_ADDR at %p"
0x18002cd64  mov     edx, 41h ; 'A'; cchDest
0x18002cd69  mov     rcx, rdi; pszDest
0x18002cd6c  call    StringCchPrintfW
0x18002cd71  jmp     loc_18002CC28
0x18002cd76  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002cd7b  jmp     loc_18002C98A
0x18002cd80  call    cs:__imp_GetCurrentProcessId
0x18002cd87  nop     dword ptr [rax+rax+00h]
0x18002cd8c  mov     [rbp+57h+var_C0], eax
0x18002cd8f  jmp     loc_18002C9B1
0x18002cd94  call    cs:__imp_GetProcessHeap
0x18002cd9b  nop     dword ptr [rax+rax+00h]
0x18002cda0  mov     cs:g_hProcessHeap, rax
0x18002cda7  jmp     loc_18002C9C1
0x18002cdac  call    cs:__imp_GetProcessHeap
0x18002cdb3  nop     dword ptr [rax+rax+00h]
0x18002cdb8  mov     cs:g_hProcessHeap, rax
0x18002cdbf  jmp     loc_18002C9EE
0x18002cdc4  call    cs:__imp_GetProcessHeap
0x18002cdcb  nop     dword ptr [rax+rax+00h]
0x18002cdd0  mov     cs:g_hProcessHeap, rax
0x18002cdd7  jmp     loc_18002CA18
```
