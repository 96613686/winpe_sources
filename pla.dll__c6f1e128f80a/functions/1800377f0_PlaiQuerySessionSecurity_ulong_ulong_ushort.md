# PlaiQuerySessionSecurity(ulong,ulong,ushort * *)

- ea: `0x1800377f0`
- end: `0x180037cb0`
- name: `?PlaiQuerySessionSecurity@@YAJKKPEAPEAG@Z`
- size: `1216`
- prototype: `int(unsigned int, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180035ae0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180018420`
- `0x18002b3a0`
- `0x1800377f0`
- `0x18013aee0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180037944`
- `ntdll!RtlNtStatusToDosError` at `0x180037944`
- `ntdll!NtQuerySystemInformation` at `0x180037934`
- `ntdll!NtQuerySystemInformation` at `0x180037934`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037b2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003785f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003785f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037851`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037851`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037c7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037c7e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180037a18`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180037a18`

## string_xrefs

- `0x1800379e6`: `PlaiQuerySessionSecurity`
- `0x180037ac7`: `PlaiQuerySessionSecurity`
- `0x180037c2f`: `PlaiQuerySessionSecurity`

## pseudocode

```c
__int64 __fastcall PlaiQuerySessionSecurity(unsigned int a1, SECURITY_INFORMATION a2, unsigned __int16 **a3)
{
  __int64 v3; // r14
  _DWORD *v6; // rdi
  __int64 v7; // rbx
  HANDLE ProcessHeap; // rax
  _DWORD *v9; // rax
  int v10; // edx
  unsigned __int64 v11; // rcx
  int SystemInformation; // eax
  signed int v13; // eax
  signed int v14; // ebx
  __int64 v15; // rax
  const char *v16; // rdx
  int v17; // r8d
  unsigned __int16 *v18; // rax
  __int64 v19; // rax
  DWORD LastError; // eax
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  int v25; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h] BYREF
  SIZE_T dwBytes; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+88h] [rbp-78h] BYREF
  _DWORD *v29; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v30[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v31[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v32[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v33[64]; // [rsp+220h] [rbp+120h] BYREF

  v3 = a1;
  StringSecurityDescriptor = 0;
  LODWORD(dwBytes) = 24;
  v6 = 0;
  while ( 1 )
  {
    if ( v6 )
      PlaiFree(v6, 1);
    v7 = (unsigned int)dwBytes;
    ProcessHeap = GetProcessHeap();
    v9 = HeapAlloc(ProcessHeap, 0, (unsigned int)v7);
    v10 = xmmword_180169738;
    v6 = v9;
    v11 = qword_180169748;
    v26 = v7;
    v29 = v9;
    v25 = 0;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
    {
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ALLOC, 4, qword_180147320, 1, &v25, 4, &v29, 8, &v26, 8);
      v11 = qword_180169748;
      v10 = xmmword_180169738;
    }
    if ( !v6 )
      break;
    *v6 = 4;
    *((_QWORD *)v6 + 1) = v3;
    v6[1] = a2;
    SystemInformation = NtQuerySystemInformation(SystemPerformanceTraceInformation, v6, dwBytes, (PULONG)&dwBytes);
    if ( SystemInformation >= 0 )
      goto LABEL_20;
    v13 = RtlNtStatusToDosError(SystemInformation);
    v14 = v13;
    if ( v13 > 0 )
      v14 = (unsigned __int16)v13 | 0x80070000;
    if ( v14 != -2147024774 )
    {
      if ( v14 < 0 )
      {
        v25 = 0;
        LODWORD(v26) = v14;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v30, 0x4000000000000800uLL);
          v15 = -1;
          do
            ++v15;
          while ( v30[v15] );
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_ERROR,
            5,
            &v26,
            4,
            qword_180147320,
            1,
            &v25,
            4,
            "PlaiQuerySessionSecurity",
            25);
        }
        goto LABEL_29;
      }
LABEL_20:
      if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v6 + 4, 1u, a2, &StringSecurityDescriptor, 0) )
      {
        v14 = 0;
LABEL_22:
        v18 = PlaiAllocStringEx(StringSecurityDescriptor, v16, v17);
        *a3 = v18;
        if ( !v18 )
        {
          v14 = -2147024882;
          v25 = -2147024882;
          LODWORD(v26) = 0;
          if ( (_DWORD)xmmword_180169738 )
          {
            if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v32, 0x4000000000000800uLL);
              v19 = -1;
              do
                ++v19;
              while ( v32[v19] );
              goto LABEL_28;
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v21 = PlaiHResultFromWin32(LastError);
        v14 = v21;
        if ( v21 >= 0 )
          goto LABEL_22;
        LODWORD(v26) = 0;
        v25 = v21;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v31, 0x4000000000000800uLL);
          v22 = -1;
          do
            ++v22;
          while ( v31[v22] );
LABEL_28:
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_ERROR,
            5,
            &v25,
            4,
            qword_180147320,
            1,
            &v26,
            4,
            "PlaiQuerySessionSecurity",
            25);
        }
      }
LABEL_29:
      PlaiFree(v6, 1);
      goto LABEL_43;
    }
  }
  LODWORD(v26) = 0;
  v25 = -2147024882;
  v14 = -2147024882;
  if ( v10 && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0 && v11 == (v11 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v33, 0x4000000000000800uLL);
    v23 = -1;
    do
      ++v23;
    while ( v33[v23] );
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v25,
      4,
      qword_180147320,
      1,
      &v26,
      4,
      "PlaiQuerySessionSecurity",
      25);
  }
LABEL_43:
  if ( StringSecurityDescriptor )
    LocalFree(StringSecurityDescriptor);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800377f0  mov     [rsp-8+arg_0], rbx
0x1800377f5  push    rbp
0x1800377f6  push    rsi
0x1800377f7  push    rdi
0x1800377f8  push    r12
0x1800377fa  push    r13
0x1800377fc  push    r14
0x1800377fe  push    r15
0x180037800  lea     rbp, [rsp-1B0h]
0x180037808  sub     rsp, 2B0h
0x18003780f  mov     rax, cs:__security_cookie
0x180037816  xor     rax, rsp
0x180037819  mov     [rbp+1E0h+var_40], rax
0x180037820  xor     r12d, r12d
0x180037823  mov     r14d, ecx
0x180037826  mov     r15, r8
0x180037829  mov     [rbp+1E0h+StringSecurityDescriptor], r12
0x18003782d  mov     esi, edx
0x18003782f  mov     dword ptr [rbp+1E0h+dwBytes], 18h
0x180037836  mov     edi, r12d
0x180037839  lea     r13d, [r12+1]
0x18003783e  test    rdi, rdi
0x180037841  jz      short loc_18003784E
0x180037843  mov     edx, r13d; int
0x180037846  mov     rcx, rdi; lpMem
0x180037849  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18003784e  mov     ebx, dword ptr [rbp+1E0h+dwBytes]
0x180037851  call    cs:__imp_GetProcessHeap
0x180037857  mov     r8d, ebx; dwBytes
0x18003785a  xor     edx, edx; dwFlags
0x18003785c  mov     rcx, rax; hHeap
0x18003785f  call    cs:__imp_HeapAlloc
0x180037865  mov     edx, dword ptr cs:xmmword_180169738
0x18003786b  mov     rdi, rax
0x18003786e  mov     rcx, cs:qword_180169748
0x180037875  mov     [rsp+2E0h+var_268], rbx
0x18003787a  mov     [rbp+1E0h+var_250], rax
0x18003787e  mov     [rsp+2E0h+var_270], r12d
0x180037883  test    edx, edx
0x180037885  jz      loc_18003790E
0x18003788b  mov     r8, 4000000000000200h
0x180037895  test    qword ptr cs:xmmword_180169738+8, r8
0x18003789c  jz      short loc_18003790E
0x18003789e  mov     rax, rcx
0x1800378a1  and     rax, r8
0x1800378a4  cmp     rcx, rax
0x1800378a7  jnz     short loc_18003790E
0x1800378a9  mov     ecx, 8
0x1800378ae  lea     rax, [rsp+2E0h+var_268]
0x1800378b3  mov     [rsp+2E0h+var_290], rcx
0x1800378b8  lea     r9, qword_180147320
0x1800378bf  mov     [rsp+2E0h+var_298], rax
0x1800378c4  lea     rdx, PLA_EVENT_ALLOC
0x1800378cb  mov     [rsp+2E0h+var_2A0], rcx
0x1800378d0  lea     rax, [rbp+1E0h+var_250]
0x1800378d4  mov     [rsp+2E0h+var_2A8], rax
0x1800378d9  lea     r8d, [rcx-4]
0x1800378dd  lea     rax, [rsp+2E0h+var_270]
0x1800378e2  mov     [rsp+2E0h+var_2B0], 4
0x1800378eb  mov     [rsp+2E0h+var_2B8], rax
0x1800378f0  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800378f7  mov     [rsp+2E0h+StringSecurityDescriptorLen], r13
0x1800378fc  call    EventingWriteEvent
0x180037901  mov     rcx, cs:qword_180169748
0x180037908  mov     edx, dword ptr cs:xmmword_180169738
0x18003790e  test    rdi, rdi
0x180037911  jz      loc_180037BA3
0x180037917  mov     dword ptr [rdi], 4
0x18003791d  lea     r9, [rbp+1E0h+dwBytes]; ReturnLength
0x180037921  mov     [rdi+8], r14
0x180037925  mov     rdx, rdi; SystemInformation
0x180037928  mov     [rdi+4], esi
0x18003792b  mov     ecx, 1Fh; SystemInformationClass
0x180037930  mov     r8d, dword ptr [rbp+1E0h+dwBytes]; SystemInformationLength
0x180037934  call    cs:__imp_NtQuerySystemInformation
0x18003793a  test    eax, eax
0x18003793c  jns     loc_180037A05
0x180037942  mov     ecx, eax; Status
0x180037944  call    cs:__imp_RtlNtStatusToDosError
0x18003794a  mov     ebx, eax
0x18003794c  test    eax, eax
0x18003794e  jle     short loc_180037959
0x180037950  movzx   ebx, ax
0x180037953  or      ebx, 80070000h
0x180037959  cmp     ebx, 8007007Ah
0x18003795f  jz      loc_18003783E
0x180037965  test    ebx, ebx
0x180037967  jns     loc_180037A05
0x18003796d  cmp     dword ptr cs:xmmword_180169738, r12d
0x180037974  mov     [rsp+2E0h+var_270], r12d
0x180037979  mov     dword ptr [rsp+2E0h+var_268], ebx
0x18003797d  jz      loc_180037B1D
0x180037983  mov     rdx, 4000000000000800h; unsigned __int64
0x18003798d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180037994  jz      loc_180037B1D
0x18003799a  mov     rax, cs:qword_180169748
0x1800379a1  and     rax, rdx
0x1800379a4  cmp     cs:qword_180169748, rax
0x1800379ab  jnz     loc_180037B1D
0x1800379b1  lea     rcx, [rbp+1E0h+var_240]; unsigned __int16 *
0x1800379b5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800379ba  lea     rcx, [rbp+1E0h+var_240]
0x1800379be  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800379c2  inc     rax
0x1800379c5  cmp     [rcx+rax*2], r12w
0x1800379ca  jnz     short loc_1800379C2
0x1800379cc  lea     ecx, [rax+rax]
0x1800379cf  lea     rax, [rbp+1E0h+var_240]
0x1800379d3  add     rcx, 2
0x1800379d7  mov     [rsp+2E0h+var_280], rcx
0x1800379dc  lea     r9, [rsp+2E0h+var_268]
0x1800379e1  mov     [rsp+2E0h+var_288], rax
0x1800379e6  lea     rax, aPlaiquerysessi; "PlaiQuerySessionSecurity"
0x1800379ed  mov     [rsp+2E0h+var_290], 19h
0x1800379f6  mov     [rsp+2E0h+var_298], rax
0x1800379fb  lea     rax, [rsp+2E0h+var_270]
0x180037a00  jmp     loc_180037AE1
0x180037a05  lea     rcx, [rdi+10h]; SecurityDescriptor
0x180037a09  mov     [rsp+2E0h+StringSecurityDescriptorLen], r12; StringSecurityDescriptorLen
0x180037a0e  lea     r9, [rbp+1E0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180037a12  mov     r8d, esi; SecurityInformation
0x180037a15  mov     edx, r13d; RequestedStringSDRevision
0x180037a18  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x180037a1e  test    eax, eax
0x180037a20  jz      loc_180037B2D
0x180037a26  mov     ebx, r12d
0x180037a29  mov     rcx, [rbp+1E0h+StringSecurityDescriptor]; unsigned __int16 *
0x180037a2d  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x180037a32  mov     [r15], rax
0x180037a35  test    rax, rax
0x180037a38  jnz     loc_180037B1D
0x180037a3e  cmp     dword ptr cs:xmmword_180169738, r12d
0x180037a45  mov     eax, 8007000Eh
0x180037a4a  mov     ebx, eax
0x180037a4c  mov     [rsp+2E0h+var_270], eax
0x180037a50  mov     dword ptr [rsp+2E0h+var_268], r12d
0x180037a55  jz      loc_180037B1D
0x180037a5b  mov     rdx, 4000000000000800h; unsigned __int64
0x180037a65  test    qword ptr cs:xmmword_180169738+8, rdx
0x180037a6c  jz      loc_180037B1D
0x180037a72  mov     rax, cs:qword_180169748
0x180037a79  and     rax, rdx
0x180037a7c  cmp     cs:qword_180169748, rax
0x180037a83  jnz     loc_180037B1D
0x180037a89  lea     rcx, [rbp+1E0h+var_140]; unsigned __int16 *
0x180037a90  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180037a95  lea     rcx, [rbp+1E0h+var_140]
0x180037a9c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037aa0  inc     rax
0x180037aa3  cmp     [rcx+rax*2], r12w
0x180037aa8  jnz     short loc_180037AA0
0x180037aaa  lea     ecx, [rax+rax]
0x180037aad  lea     rax, [rbp+1E0h+var_140]
0x180037ab4  add     rcx, 2
0x180037ab8  lea     r9, [rsp+2E0h+var_270]
0x180037abd  mov     [rsp+2E0h+var_280], rcx
0x180037ac2  mov     [rsp+2E0h+var_288], rax
0x180037ac7  lea     rax, aPlaiquerysessi; "PlaiQuerySessionSecurity"
0x180037ace  mov     [rsp+2E0h+var_290], 19h
0x180037ad7  mov     [rsp+2E0h+var_298], rax
0x180037adc  lea     rax, [rsp+2E0h+var_268]
0x180037ae1  mov     ecx, 4
0x180037ae6  lea     rdx, PLA_EVENT_ERROR
0x180037aed  mov     [rsp+2E0h+var_2A0], rcx
0x180037af2  mov     [rsp+2E0h+var_2A8], rax
0x180037af7  lea     rax, qword_180147320
0x180037afe  mov     [rsp+2E0h+var_2B0], r13
0x180037b03  mov     [rsp+2E0h+var_2B8], rax
0x180037b08  lea     r8d, [rcx+1]
0x180037b0c  mov     [rsp+2E0h+StringSecurityDescriptorLen], rcx
0x180037b11  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180037b18  call    EventingWriteEvent
0x180037b1d  mov     edx, r13d; int
0x180037b20  mov     rcx, rdi; lpMem
0x180037b23  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x180037b28  jmp     loc_180037C75
0x180037b2d  call    cs:__imp_GetLastError
0x180037b33  mov     ecx, eax; unsigned int
0x180037b35  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180037b3a  mov     ebx, eax
0x180037b3c  test    eax, eax
0x180037b3e  jns     loc_180037A29
0x180037b44  cmp     dword ptr cs:xmmword_180169738, r12d
0x180037b4b  mov     dword ptr [rsp+2E0h+var_268], r12d
0x180037b50  mov     [rsp+2E0h+var_270], eax
0x180037b54  jz      short loc_180037B1D
0x180037b56  mov     rdx, 4000000000000800h; unsigned __int64
0x180037b60  test    qword ptr cs:xmmword_180169738+8, rdx
0x180037b67  jz      short loc_180037B1D
0x180037b69  mov     rax, cs:qword_180169748
0x180037b70  and     rax, rdx
0x180037b73  cmp     cs:qword_180169748, rax
0x180037b7a  jnz     short loc_180037B1D
0x180037b7c  lea     rcx, [rbp+1E0h+var_1C0]; unsigned __int16 *
0x180037b80  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180037b85  lea     rcx, [rbp+1E0h+var_1C0]
0x180037b89  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037b8d  inc     rax
0x180037b90  cmp     [rcx+rax*2], r12w
0x180037b95  jnz     short loc_180037B8D
0x180037b97  lea     ecx, [rax+rax]
0x180037b9a  lea     rax, [rbp+1E0h+var_1C0]
0x180037b9e  jmp     loc_180037AB4
0x180037ba3  mov     dword ptr [rsp+2E0h+var_268], r12d
0x180037ba8  mov     eax, 8007000Eh
0x180037bad  mov     [rsp+2E0h+var_270], eax
0x180037bb1  mov     ebx, eax
0x180037bb3  test    edx, edx
0x180037bb5  jz      loc_180037C75
0x180037bbb  mov     rdx, 4000000000000800h; unsigned __int64
0x180037bc5  test    qword ptr cs:xmmword_180169738+8, rdx
0x180037bcc  jz      loc_180037C75
0x180037bd2  mov     rax, rcx
0x180037bd5  and     rax, rdx
0x180037bd8  cmp     rcx, rax
0x180037bdb  jnz     loc_180037C75
0x180037be1  lea     rcx, [rbp+1E0h+var_C0]; unsigned __int16 *
0x180037be8  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180037bed  lea     rcx, [rbp+1E0h+var_C0]
0x180037bf4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180037bf8  inc     rax
0x180037bfb  cmp     [rcx+rax*2], r12w
0x180037c00  jnz     short loc_180037BF8
0x180037c02  lea     ecx, [rax+rax]
0x180037c05  add     rcx, 2
0x180037c09  lea     rax, [rbp+1E0h+var_C0]
0x180037c10  mov     [rsp+2E0h+var_280], rcx
0x180037c15  lea     r9, [rsp+2E0h+var_270]
0x180037c1a  mov     [rsp+2E0h+var_288], rax
0x180037c1f  lea     rdx, PLA_EVENT_ERROR
0x180037c26  mov     [rsp+2E0h+var_290], 19h
0x180037c2f  lea     rax, aPlaiquerysessi; "PlaiQuerySessionSecurity"
0x180037c36  mov     [rsp+2E0h+var_298], rax
0x180037c3b  mov     ecx, 4
0x180037c40  mov     [rsp+2E0h+var_2A0], rcx
0x180037c45  lea     rax, [rsp+2E0h+var_268]
0x180037c4a  mov     [rsp+2E0h+var_2A8], rax
0x180037c4f  lea     rax, qword_180147320
0x180037c56  mov     [rsp+2E0h+var_2B0], r13
0x180037c5b  mov     [rsp+2E0h+var_2B8], rax
0x180037c60  lea     r8d, [rcx+1]
0x180037c64  mov     [rsp+2E0h+StringSecurityDescriptorLen], rcx
0x180037c69  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180037c70  call    EventingWriteEvent
0x180037c75  mov     rcx, [rbp+1E0h+StringSecurityDescriptor]; hMem
0x180037c79  test    rcx, rcx
0x180037c7c  jz      short loc_180037C84
0x180037c7e  call    cs:__imp_LocalFree
0x180037c84  mov     eax, ebx
0x180037c86  mov     rcx, [rbp+1E0h+var_40]
0x180037c8d  xor     rcx, rsp; StackCookie
0x180037c90  call    __security_check_cookie
0x180037c95  mov     rbx, [rsp+2E0h+arg_0]
0x180037c9d  add     rsp, 2B0h
0x180037ca4  pop     r15
0x180037ca6  pop     r14
0x180037ca8  pop     r13
0x180037caa  pop     r12
0x180037cac  pop     rdi
0x180037cad  pop     rsi
0x180037cae  pop     rbp
0x180037caf  retn
```
