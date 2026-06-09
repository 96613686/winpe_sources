# PlaiQueryFileSecurity(ushort const *,ulong,ushort * *)

- ea: `0x1800d1a24`
- end: `0x1800d1e18`
- name: `?PlaiQueryFileSecurity@@YAJPEBGKPEAPEAG@Z`
- size: `1012`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, SECURITY_INFORMATION SecurityInformation, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18012a080`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180018420`
- `0x18002b3a0`
- `0x1800d1a24`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1c88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1ac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1c88`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800d1abb`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800d1abb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d1de6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d1de6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800d1b73`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x1800d1b73`

## string_xrefs

- `0x1800d1c37`: `PlaiQueryFileSecurity`
- `0x1800d1d95`: `PlaiQueryFileSecurity`

## pseudocode

```c
__int64 __fastcall PlaiQueryFileSecurity(
        LPCWSTR lpFileName,
        SECURITY_INFORMATION SecurityInformation,
        unsigned __int16 **a3)
{
  void *v6; // rdi
  DWORD LastError; // eax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  int *v11; // r9
  int *v12; // rcx
  const char *v13; // rdx
  int v14; // r8d
  unsigned __int16 *v15; // rax
  __int64 v16; // rax
  DWORD v17; // eax
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  int lpnLengthNeeded; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+78h] [rbp-88h] BYREF
  DWORD nLengthNeeded; // [rsp+80h] [rbp-80h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v27[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v28[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v29[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v30[64]; // [rsp+210h] [rbp+110h] BYREF

  nLengthNeeded = 40;
  StringSecurityDescriptor = 0;
  v6 = 0;
  while ( 1 )
  {
    if ( v6 )
      PlaiFree(v6, 1);
    v6 = PlaiAlloc(nLengthNeeded, 1, 0, byte_180147320, lpnLengthNeeded);
    if ( !v6 )
      break;
    if ( GetFileSecurityW(lpFileName, SecurityInformation, v6, nLengthNeeded, &nLengthNeeded) )
      goto LABEL_14;
    LastError = GetLastError();
    v8 = PlaiHResultFromWin32(LastError);
    v9 = v8;
    if ( v8 != -2147024774 )
    {
      if ( v8 < 0 )
      {
        v23 = 0;
        v24 = v8;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v27, 0x4000000000000800uLL);
          v10 = -1;
          do
            ++v10;
          while ( v27[v10] );
          v11 = &v24;
          v12 = &v23;
LABEL_23:
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v11, 4, byte_180147320, 1, v12, 4);
        }
LABEL_24:
        PlaiFree(v6, 1);
        goto LABEL_38;
      }
LABEL_14:
      if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
             v6,
             1u,
             SecurityInformation,
             &StringSecurityDescriptor,
             0) )
      {
        v9 = 0;
LABEL_16:
        v15 = PlaiAllocStringEx(StringSecurityDescriptor, v13, v14);
        *a3 = v15;
        if ( v15 )
          goto LABEL_24;
        v9 = -2147024882;
        v23 = -2147024882;
        v24 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_24;
        }
        PlaiWhoAmI(v29, 0x4000000000000800uLL);
        v16 = -1;
        do
          ++v16;
        while ( v29[v16] );
      }
      else
      {
        v17 = GetLastError();
        v18 = PlaiHResultFromWin32(v17);
        v9 = v18;
        if ( v18 >= 0 )
          goto LABEL_16;
        v24 = 0;
        v23 = v18;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_24;
        }
        PlaiWhoAmI(v28, 0x4000000000000800uLL);
        v19 = -1;
        do
          ++v19;
        while ( v28[v19] );
      }
      v11 = &v23;
      v12 = &v24;
      goto LABEL_23;
    }
  }
  v9 = -2147024882;
  v23 = -2147024882;
  v24 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v30, 0x4000000000000800uLL);
    v20 = -1;
    do
      ++v20;
    while ( v30[v20] );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v23, 4, byte_180147320, 1, &v24, 4);
  }
LABEL_38:
  if ( StringSecurityDescriptor )
    LocalFree(StringSecurityDescriptor);
  return v9;
}

```

## disassembly

```asm
0x1800d1a24  mov     [rsp-8+arg_18], rbx
0x1800d1a29  push    rbp
0x1800d1a2a  push    rsi
0x1800d1a2b  push    rdi
0x1800d1a2c  push    r12
0x1800d1a2e  push    r13
0x1800d1a30  push    r14
0x1800d1a32  push    r15
0x1800d1a34  lea     rbp, [rsp-1A0h]
0x1800d1a3c  sub     rsp, 2A0h
0x1800d1a43  mov     rax, cs:__security_cookie
0x1800d1a4a  xor     rax, rsp
0x1800d1a4d  mov     [rbp+1D0h+var_40], rax
0x1800d1a54  xor     r12d, r12d
0x1800d1a57  mov     [rbp+1D0h+nLengthNeeded], 28h ; '('
0x1800d1a5e  mov     r15, r8
0x1800d1a61  mov     [rbp+1D0h+StringSecurityDescriptor], r12
0x1800d1a65  mov     esi, edx
0x1800d1a67  mov     r14, rcx
0x1800d1a6a  mov     edi, r12d
0x1800d1a6d  lea     r13d, [r12+1]
0x1800d1a72  lea     rbx, byte_180147320
0x1800d1a79  test    rdi, rdi
0x1800d1a7c  jz      short loc_1800D1A89
0x1800d1a7e  mov     edx, r13d; int
0x1800d1a81  mov     rcx, rdi; lpMem
0x1800d1a84  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x1800d1a89  mov     ecx, [rbp+1D0h+nLengthNeeded]; dwBytes
0x1800d1a8c  mov     r9, rbx; char *
0x1800d1a8f  xor     r8d, r8d; int
0x1800d1a92  mov     edx, r13d; int
0x1800d1a95  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800d1a9a  mov     rdi, rax
0x1800d1a9d  test    rax, rax
0x1800d1aa0  jz      loc_1800D1CFE
0x1800d1aa6  mov     r9d, [rbp+1D0h+nLengthNeeded]; nLength
0x1800d1aaa  lea     rax, [rbp+1D0h+nLengthNeeded]
0x1800d1aae  mov     r8, rdi; pSecurityDescriptor
0x1800d1ab1  mov     [rsp+2D0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800d1ab6  mov     edx, esi; RequestedInformation
0x1800d1ab8  mov     rcx, r14; lpFileName
0x1800d1abb  call    cs:__imp_GetFileSecurityW
0x1800d1ac1  test    eax, eax
0x1800d1ac3  jnz     loc_1800D1B61
0x1800d1ac9  call    cs:__imp_GetLastError
0x1800d1acf  mov     ecx, eax; unsigned int
0x1800d1ad1  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800d1ad6  mov     ebx, eax
0x1800d1ad8  cmp     eax, 8007007Ah
0x1800d1add  jz      short loc_1800D1A72
0x1800d1adf  test    eax, eax
0x1800d1ae1  jns     short loc_1800D1B61
0x1800d1ae3  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d1aea  mov     [rsp+2D0h+var_260], r12d
0x1800d1aef  mov     [rsp+2D0h+var_258], eax
0x1800d1af3  jz      loc_1800D1C78
0x1800d1af9  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d1b03  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d1b0a  jz      loc_1800D1C78
0x1800d1b10  mov     rax, cs:qword_180169748
0x1800d1b17  and     rax, rdx
0x1800d1b1a  cmp     cs:qword_180169748, rax
0x1800d1b21  jnz     loc_1800D1C78
0x1800d1b27  lea     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x1800d1b2b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d1b30  lea     rcx, [rbp+1D0h+var_240]
0x1800d1b34  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d1b38  inc     rax
0x1800d1b3b  cmp     [rcx+rax*2], r12w
0x1800d1b40  jnz     short loc_1800D1B38
0x1800d1b42  lea     ecx, [rax+rax]
0x1800d1b45  add     rcx, 2
0x1800d1b49  lea     rax, [rbp+1D0h+var_240]
0x1800d1b4d  mov     [rsp+2D0h+var_270], rcx
0x1800d1b52  lea     r9, [rsp+2D0h+var_258]
0x1800d1b57  lea     rcx, [rsp+2D0h+var_260]
0x1800d1b5c  jmp     loc_1800D1C22
0x1800d1b61  lea     r9, [rbp+1D0h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800d1b65  mov     [rsp+2D0h+lpnLengthNeeded], r12; StringSecurityDescriptorLen
0x1800d1b6a  mov     r8d, esi; SecurityInformation
0x1800d1b6d  mov     edx, r13d; RequestedStringSDRevision
0x1800d1b70  mov     rcx, rdi; SecurityDescriptor
0x1800d1b73  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800d1b79  test    eax, eax
0x1800d1b7b  jz      loc_1800D1C88
0x1800d1b81  mov     ebx, r12d
0x1800d1b84  mov     rcx, [rbp+1D0h+StringSecurityDescriptor]; unsigned __int16 *
0x1800d1b88  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x1800d1b8d  mov     [r15], rax
0x1800d1b90  test    rax, rax
0x1800d1b93  jnz     loc_1800D1C78
0x1800d1b99  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d1ba0  mov     eax, 8007000Eh
0x1800d1ba5  mov     ebx, eax
0x1800d1ba7  mov     [rsp+2D0h+var_260], eax
0x1800d1bab  mov     [rsp+2D0h+var_258], r12d
0x1800d1bb0  jz      loc_1800D1C78
0x1800d1bb6  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d1bc0  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d1bc7  jz      loc_1800D1C78
0x1800d1bcd  mov     rax, cs:qword_180169748
0x1800d1bd4  and     rax, rdx
0x1800d1bd7  cmp     cs:qword_180169748, rax
0x1800d1bde  jnz     loc_1800D1C78
0x1800d1be4  lea     rcx, [rbp+1D0h+var_140]; unsigned __int16 *
0x1800d1beb  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d1bf0  lea     rcx, [rbp+1D0h+var_140]
0x1800d1bf7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d1bfb  inc     rax
0x1800d1bfe  cmp     [rcx+rax*2], r12w
0x1800d1c03  jnz     short loc_1800D1BFB
0x1800d1c05  lea     ecx, [rax+rax]
0x1800d1c08  lea     rax, [rbp+1D0h+var_140]
0x1800d1c0f  add     rcx, 2
0x1800d1c13  lea     r9, [rsp+2D0h+var_260]
0x1800d1c18  mov     [rsp+2D0h+var_270], rcx
0x1800d1c1d  lea     rcx, [rsp+2D0h+var_258]
0x1800d1c22  mov     [rsp+2D0h+var_278], rax
0x1800d1c27  lea     rdx, PLA_EVENT_ERROR
0x1800d1c2e  mov     [rsp+2D0h+var_280], 16h
0x1800d1c37  lea     rax, aPlaiqueryfiles; "PlaiQueryFileSecurity"
0x1800d1c3e  mov     [rsp+2D0h+var_288], rax
0x1800d1c43  mov     eax, 4
0x1800d1c48  mov     [rsp+2D0h+var_290], rax
0x1800d1c4d  mov     [rsp+2D0h+var_298], rcx
0x1800d1c52  lea     rcx, byte_180147320
0x1800d1c59  mov     [rsp+2D0h+var_2A0], r13
0x1800d1c5e  mov     [rsp+2D0h+var_2A8], rcx
0x1800d1c63  lea     r8d, [rax+1]
0x1800d1c67  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800d1c6e  mov     [rsp+2D0h+lpnLengthNeeded], rax
0x1800d1c73  call    EventingWriteEvent
0x1800d1c78  mov     edx, r13d; int
0x1800d1c7b  mov     rcx, rdi; lpMem
0x1800d1c7e  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x1800d1c83  jmp     loc_1800D1DDD
0x1800d1c88  call    cs:__imp_GetLastError
0x1800d1c8e  mov     ecx, eax; unsigned int
0x1800d1c90  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800d1c95  mov     ebx, eax
0x1800d1c97  test    eax, eax
0x1800d1c99  jns     loc_1800D1B84
0x1800d1c9f  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d1ca6  mov     [rsp+2D0h+var_258], r12d
0x1800d1cab  mov     [rsp+2D0h+var_260], eax
0x1800d1caf  jz      short loc_1800D1C78
0x1800d1cb1  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d1cbb  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d1cc2  jz      short loc_1800D1C78
0x1800d1cc4  mov     rax, cs:qword_180169748
0x1800d1ccb  and     rax, rdx
0x1800d1cce  cmp     cs:qword_180169748, rax
0x1800d1cd5  jnz     short loc_1800D1C78
0x1800d1cd7  lea     rcx, [rbp+1D0h+var_1C0]; unsigned __int16 *
0x1800d1cdb  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d1ce0  lea     rcx, [rbp+1D0h+var_1C0]
0x1800d1ce4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d1ce8  inc     rax
0x1800d1ceb  cmp     [rcx+rax*2], r12w
0x1800d1cf0  jnz     short loc_1800D1CE8
0x1800d1cf2  lea     ecx, [rax+rax]
0x1800d1cf5  lea     rax, [rbp+1D0h+var_1C0]
0x1800d1cf9  jmp     loc_1800D1C0F
0x1800d1cfe  cmp     dword ptr cs:xmmword_180169738, r12d
0x1800d1d05  mov     eax, 8007000Eh
0x1800d1d0a  mov     ebx, eax
0x1800d1d0c  mov     [rsp+2D0h+var_260], eax
0x1800d1d10  mov     [rsp+2D0h+var_258], r12d
0x1800d1d15  jz      loc_1800D1DDD
0x1800d1d1b  mov     rdx, 4000000000000800h; unsigned __int64
0x1800d1d25  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800d1d2c  jz      loc_1800D1DDD
0x1800d1d32  mov     rax, cs:qword_180169748
0x1800d1d39  and     rax, rdx
0x1800d1d3c  cmp     cs:qword_180169748, rax
0x1800d1d43  jnz     loc_1800D1DDD
0x1800d1d49  lea     rcx, [rbp+1D0h+var_C0]; unsigned __int16 *
0x1800d1d50  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800d1d55  lea     rcx, [rbp+1D0h+var_C0]
0x1800d1d5c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d1d60  inc     rax
0x1800d1d63  cmp     [rcx+rax*2], r12w
0x1800d1d68  jnz     short loc_1800D1D60
0x1800d1d6a  lea     ecx, [rax+rax]
0x1800d1d6d  add     rcx, 2
0x1800d1d71  lea     rax, [rbp+1D0h+var_C0]
0x1800d1d78  mov     [rsp+2D0h+var_270], rcx
0x1800d1d7d  lea     r9, [rsp+2D0h+var_260]
0x1800d1d82  mov     [rsp+2D0h+var_278], rax
0x1800d1d87  lea     rcx, [rsp+2D0h+var_258]
0x1800d1d8c  mov     [rsp+2D0h+var_280], 16h
0x1800d1d95  lea     rax, aPlaiqueryfiles; "PlaiQueryFileSecurity"
0x1800d1d9c  mov     [rsp+2D0h+var_288], rax
0x1800d1da1  lea     rdx, PLA_EVENT_ERROR
0x1800d1da8  mov     eax, 4
0x1800d1dad  mov     [rsp+2D0h+var_290], rax
0x1800d1db2  mov     [rsp+2D0h+var_298], rcx
0x1800d1db7  lea     rcx, byte_180147320
0x1800d1dbe  mov     [rsp+2D0h+var_2A0], r13
0x1800d1dc3  mov     [rsp+2D0h+var_2A8], rcx
0x1800d1dc8  lea     r8d, [rax+1]
0x1800d1dcc  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800d1dd3  mov     [rsp+2D0h+lpnLengthNeeded], rax
0x1800d1dd8  call    EventingWriteEvent
0x1800d1ddd  mov     rcx, [rbp+1D0h+StringSecurityDescriptor]; hMem
0x1800d1de1  test    rcx, rcx
0x1800d1de4  jz      short loc_1800D1DEC
0x1800d1de6  call    cs:__imp_LocalFree
0x1800d1dec  mov     eax, ebx
0x1800d1dee  mov     rcx, [rbp+1D0h+var_40]
0x1800d1df5  xor     rcx, rsp; StackCookie
0x1800d1df8  call    __security_check_cookie
0x1800d1dfd  mov     rbx, [rsp+2D0h+arg_18]
0x1800d1e05  add     rsp, 2A0h
0x1800d1e0c  pop     r15
0x1800d1e0e  pop     r14
0x1800d1e10  pop     r13
0x1800d1e12  pop     r12
0x1800d1e14  pop     rdi
0x1800d1e15  pop     rsi
0x1800d1e16  pop     rbp
0x1800d1e17  retn
```
