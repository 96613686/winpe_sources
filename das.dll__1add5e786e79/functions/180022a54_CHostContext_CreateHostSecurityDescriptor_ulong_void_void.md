# CHostContext::CreateHostSecurityDescriptor(ulong,void *,void * *)

- ea: `0x180022a54`
- end: `0x180022d1d`
- name: `?CreateHostSecurityDescriptor@CHostContext@@IEAAJKPEAXPEAPEAX@Z`
- size: `713`
- prototype: `__int64 __fastcall(CHostContext *this, int, void *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180022624`

## callees

- `0x180007500`
- `0x180022a54`
- `0x18003c7a8`

## import_xrefs

- `ntdll!RtlCreateAcl` at `0x180022b65`
- `ntdll!RtlCreateAcl` at `0x180022b65`
- `ntdll!RtlAddAccessAllowedAce` at `0x180022b7b`
- `ntdll!RtlAddAccessAllowedAce` at `0x180022b91`
- `ntdll!RtlAddAccessAllowedAce` at `0x180022ba5`
- `ntdll!RtlAddAccessAllowedAce` at `0x180022bf8`
- `ntdll!RtlAddAccessAllowedAce` at `0x180022b7b`
- `ntdll!RtlAddAccessAllowedAce` at `0x180022b91`
- `ntdll!RtlAddAccessAllowedAce` at `0x180022ba5`
- `ntdll!RtlAddAccessAllowedAce` at `0x180022bf8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022a81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022bfe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022cd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022cf6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022a81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b23`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022bfe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022cd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022cf6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022ce7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022d04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022ce7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022d04`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022a8f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022b31`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022c0d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022a8f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022b31`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022c0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022bc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022aec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022bc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022c6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ca0`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180022c96`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180022c96`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180022c83`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180022c83`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180022ae2`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180022bbb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180022ae2`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180022bbb`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180022c63`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180022c63`

## string_xrefs

- `0x180022b01`: `error: could not create sid 0x%x\n`
- `0x180022bda`: `error: could not create local system sid 0x%x\n`
- `0x180022a9d`: `error: could not allocate sid memory\n`
- `0x180022b40`: `error: could not allocate acl memory\n`

## pseudocode

```c
__int64 __fastcall CHostContext::CreateHostSecurityDescriptor(CHostContext *this, int a2, void *a3, void **a4)
{
  HANDLE ProcessHeap; // rax
  void *v9; // rax
  void *v10; // rsi
  unsigned int v11; // ebx
  void *v12; // rdi
  int v13; // ebx
  WELL_KNOWN_SID_TYPE v14; // ecx
  signed int v15; // eax
  ULONG v16; // r15d
  HANDLE v17; // rax
  struct _ACL *v18; // rax
  signed int v19; // eax
  HANDLE v20; // rax
  void *v21; // rax
  int v22; // edx
  int v23; // r8d
  signed int LastError; // eax
  int v25; // edx
  int v26; // r8d
  HANDLE v27; // rax
  HANDLE v28; // rax
  DWORD cbSid; // [rsp+98h] [rbp+20h] BYREF

  *a4 = 0;
  cbSid = 68;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 0, 0x44u);
  v10 = v9;
  if ( !v9 )
  {
    v11 = -2147024882;
    wprintf(L"error: could not allocate sid memory\n");
    return v11;
  }
  v12 = 0;
  v13 = a2 - 1;
  if ( !v13 )
  {
    v14 = WinLocalServiceSid;
LABEL_8:
    if ( CreateWellKnownSid(v14, 0, v9, &cbSid) )
    {
      v16 = 4 * cbSid + 40;
      v17 = GetProcessHeap();
      v18 = (struct _ACL *)HeapAlloc(v17, 0, v16);
      *((_QWORD *)this + 10) = v18;
      if ( v18 )
      {
        RtlCreateAcl(v18, v16, 2u);
        RtlAddAccessAllowedAce(*((PACL *)this + 10), 2u, 0x2000000u, v10);
        RtlAddAccessAllowedAce(*((PACL *)this + 10), 2u, 0x1F0003u, v10);
        RtlAddAccessAllowedAce(*((PACL *)this + 10), 2u, 0x40u, v10);
        if ( CreateWellKnownSid(WinLocalSystemSid, 0, v10, &cbSid) )
        {
          RtlAddAccessAllowedAce(*((PACL *)this + 10), 2u, 1u, v10);
          v20 = GetProcessHeap();
          v21 = HeapAlloc(v20, 0, 0x28u);
          v12 = v21;
          if ( v21 )
          {
            if ( InitializeSecurityDescriptor(v21, 1u) && SetSecurityDescriptorDacl(v12, 1, *((PACL *)this + 10), 0) )
            {
              if ( SetSecurityDescriptorOwner(v12, a3, 0) )
              {
                v11 = 0;
                *a4 = v12;
              }
              else
              {
                LastError = GetLastError();
                v11 = LastError;
                if ( LastError > 0 )
                  v11 = (unsigned __int16)LastError | 0x80070000;
                if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                  WPP_RECORDER_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 5),
                    v25,
                    v26,
                    33,
                    &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
                    v11);
              }
            }
            else
            {
              v11 = GetLastError();
            }
          }
          else
          {
            v11 = -2147024882;
            if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 5),
                v22,
                v23,
                32,
                &WPP_061eca0472ca35df833eac72ad0e5963_Traceguids,
                14);
          }
        }
        else
        {
          v19 = GetLastError();
          v11 = v19;
          if ( v19 > 0 )
            v11 = (unsigned __int16)v19 | 0x80070000;
          wprintf(L"error: could not create local system sid 0x%x\n", v11);
        }
      }
      else
      {
        v11 = -2147024882;
        wprintf(L"error: could not allocate acl memory\n");
      }
    }
    else
    {
      v15 = GetLastError();
      v11 = v15;
      if ( v15 > 0 )
        v11 = (unsigned __int16)v15 | 0x80070000;
      wprintf(L"error: could not create sid 0x%x\n", v11);
    }
    goto LABEL_32;
  }
  if ( v13 == 1 )
  {
    v14 = WinNetworkServiceSid;
    goto LABEL_8;
  }
  v11 = -2147024809;
LABEL_32:
  v27 = GetProcessHeap();
  HeapFree(v27, 0, v10);
  if ( (v11 & 0x80000000) != 0 && v12 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v12);
  }
  return v11;
}

```

## disassembly

```asm
0x180022a54  mov     rax, rsp
0x180022a57  push    rbx
0x180022a58  push    rbp
0x180022a59  push    rsi
0x180022a5a  push    rdi
0x180022a5b  push    r12
0x180022a5d  push    r13
0x180022a5f  push    r14
0x180022a61  push    r15
0x180022a63  sub     rsp, 38h
0x180022a67  mov     edi, 44h ; 'D'
0x180022a6c  mov     qword ptr [r9], 0
0x180022a73  mov     [rax+20h], edi
0x180022a76  mov     r14, r9
0x180022a79  mov     r12, r8
0x180022a7c  mov     ebx, edx
0x180022a7e  mov     rbp, rcx
0x180022a81  call    cs:__imp_GetProcessHeap
0x180022a87  mov     r8d, edi; dwBytes
0x180022a8a  xor     edx, edx; dwFlags
0x180022a8c  mov     rcx, rax; hHeap
0x180022a8f  call    cs:__imp_HeapAlloc
0x180022a95  mov     rsi, rax
0x180022a98  test    rax, rax
0x180022a9b  jnz     short loc_180022AB3
0x180022a9d  lea     rcx, aErrorCouldNotA; "error: could not allocate sid memory\n"
0x180022aa4  mov     ebx, 8007000Eh
0x180022aa9  call    wprintf
0x180022aae  jmp     loc_180022D0A
0x180022ab3  xor     edi, edi
0x180022ab5  sub     ebx, 1
0x180022ab8  jz      short loc_180022AD0
0x180022aba  cmp     ebx, 1
0x180022abd  jz      short loc_180022AC9
0x180022abf  mov     ebx, 80070057h
0x180022ac4  jmp     loc_180022CD9
0x180022ac9  mov     ecx, 18h
0x180022ace  jmp     short loc_180022AD5
0x180022ad0  mov     ecx, 17h; WellKnownSidType
0x180022ad5  lea     r9, [rsp+78h+cbSid]; cbSid
0x180022add  mov     r8, rsi; pSid
0x180022ae0  xor     edx, edx; DomainSid
0x180022ae2  call    cs:__imp_CreateWellKnownSid
0x180022ae8  test    eax, eax
0x180022aea  jnz     short loc_180022B14
0x180022aec  call    cs:__imp_GetLastError
0x180022af2  mov     ebx, eax
0x180022af4  test    eax, eax
0x180022af6  jle     short loc_180022B01
0x180022af8  movzx   ebx, ax
0x180022afb  or      ebx, 80070000h
0x180022b01  lea     rcx, aErrorCouldNotC; "error: could not create sid 0x%x\n"
0x180022b08  mov     edx, ebx
0x180022b0a  call    wprintf
0x180022b0f  jmp     loc_180022CD9
0x180022b14  mov     eax, [rsp+78h+cbSid]
0x180022b1b  lea     r15d, ds:28h[rax*4]
0x180022b23  call    cs:__imp_GetProcessHeap
0x180022b29  mov     r8d, r15d; dwBytes
0x180022b2c  xor     edx, edx; dwFlags
0x180022b2e  mov     rcx, rax; hHeap
0x180022b31  call    cs:__imp_HeapAlloc
0x180022b37  mov     [rbp+50h], rax
0x180022b3b  test    rax, rax
0x180022b3e  jnz     short loc_180022B56
0x180022b40  lea     rcx, aErrorCouldNotA_0; "error: could not allocate acl memory\n"
0x180022b47  mov     ebx, 8007000Eh
0x180022b4c  call    wprintf
0x180022b51  jmp     loc_180022CD9
0x180022b56  mov     r13d, 2
0x180022b5c  mov     edx, r15d; AclSize
0x180022b5f  mov     r8d, r13d; AclRevision
0x180022b62  mov     rcx, rax; Acl
0x180022b65  call    cs:__imp_RtlCreateAcl
0x180022b6b  mov     rcx, [rbp+50h]; Acl
0x180022b6f  mov     r9, rsi; Sid
0x180022b72  mov     r8d, 2000000h; AccessMask
0x180022b78  mov     edx, r13d; Revision
0x180022b7b  call    cs:__imp_RtlAddAccessAllowedAce
0x180022b81  mov     rcx, [rbp+50h]; Acl
0x180022b85  mov     r9, rsi; Sid
0x180022b88  mov     r8d, 1F0003h; AccessMask
0x180022b8e  mov     edx, r13d; Revision
0x180022b91  call    cs:__imp_RtlAddAccessAllowedAce
0x180022b97  mov     rcx, [rbp+50h]; Acl
0x180022b9b  lea     r8d, [r13+3Eh]; AccessMask
0x180022b9f  mov     r9, rsi; Sid
0x180022ba2  mov     edx, r13d; Revision
0x180022ba5  call    cs:__imp_RtlAddAccessAllowedAce
0x180022bab  xor     edx, edx; DomainSid
0x180022bad  lea     r9, [rsp+78h+cbSid]; cbSid
0x180022bb5  mov     r8, rsi; pSid
0x180022bb8  lea     ecx, [rdx+16h]; WellKnownSidType
0x180022bbb  call    cs:__imp_CreateWellKnownSid
0x180022bc1  test    eax, eax
0x180022bc3  jnz     short loc_180022BE6
0x180022bc5  call    cs:__imp_GetLastError
0x180022bcb  mov     ebx, eax
0x180022bcd  test    eax, eax
0x180022bcf  jle     short loc_180022BDA
0x180022bd1  movzx   ebx, ax
0x180022bd4  or      ebx, 80070000h
0x180022bda  lea     rcx, aErrorCouldNotC_0; "error: could not create local system si"...
0x180022be1  jmp     loc_180022B08
0x180022be6  mov     rcx, [rbp+50h]; Acl
0x180022bea  mov     ebx, 1
0x180022bef  mov     r8d, ebx; AccessMask
0x180022bf2  mov     r9, rsi; Sid
0x180022bf5  mov     edx, r13d; Revision
0x180022bf8  call    cs:__imp_RtlAddAccessAllowedAce
0x180022bfe  call    cs:__imp_GetProcessHeap
0x180022c04  xor     edx, edx; dwFlags
0x180022c06  lea     r8d, [rbx+27h]; dwBytes
0x180022c0a  mov     rcx, rax; hHeap
0x180022c0d  call    cs:__imp_HeapAlloc
0x180022c13  mov     rdi, rax
0x180022c16  test    rax, rax
0x180022c19  jnz     short loc_180022C5E
0x180022c1b  mov     ebx, 8007000Eh
0x180022c20  lea     rax, WPP_RECORDER_INITIALIZED
0x180022c27  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180022c2e  jz      loc_180022CD9
0x180022c34  lea     r9d, [rdi+20h]; int
0x180022c38  mov     dword ptr [rsp+78h+var_50], 8007000Eh; char
0x180022c40  mov     rcx, cs:WPP_GLOBAL_Control
0x180022c47  lea     rax, WPP_061eca0472ca35df833eac72ad0e5963_Traceguids
0x180022c4e  mov     [rsp+78h+MessageGuid], rax; MessageGuid
0x180022c53  mov     rcx, [rcx+28h]; int
0x180022c57  call    WPP_RECORDER_SF_D
0x180022c5c  jmp     short loc_180022CD9
0x180022c5e  mov     edx, ebx; dwRevision
0x180022c60  mov     rcx, rdi; pSecurityDescriptor
0x180022c63  call    cs:__imp_InitializeSecurityDescriptor
0x180022c69  test    eax, eax
0x180022c6b  jnz     short loc_180022C77
0x180022c6d  call    cs:__imp_GetLastError
0x180022c73  mov     ebx, eax
0x180022c75  jmp     short loc_180022CD9
0x180022c77  mov     r8, [rbp+50h]; pDacl
0x180022c7b  xor     r9d, r9d; bDaclDefaulted
0x180022c7e  mov     edx, ebx; bDaclPresent
0x180022c80  mov     rcx, rdi; pSecurityDescriptor
0x180022c83  call    cs:__imp_SetSecurityDescriptorDacl
0x180022c89  test    eax, eax
0x180022c8b  jz      short loc_180022C6D
0x180022c8d  xor     r8d, r8d; bOwnerDefaulted
0x180022c90  mov     rdx, r12; pOwner
0x180022c93  mov     rcx, rdi; pSecurityDescriptor
0x180022c96  call    cs:__imp_SetSecurityDescriptorOwner
0x180022c9c  test    eax, eax
0x180022c9e  jnz     short loc_180022CD4
0x180022ca0  call    cs:__imp_GetLastError
0x180022ca6  mov     ebx, eax
0x180022ca8  test    eax, eax
0x180022caa  jle     short loc_180022CB5
0x180022cac  movzx   ebx, ax
0x180022caf  or      ebx, 80070000h
0x180022cb5  lea     rax, WPP_RECORDER_INITIALIZED
0x180022cbc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180022cc3  jz      short loc_180022CD9
0x180022cc5  mov     r9d, 21h ; '!'
0x180022ccb  mov     dword ptr [rsp+78h+var_50], ebx
0x180022ccf  jmp     loc_180022C40
0x180022cd4  xor     ebx, ebx
0x180022cd6  mov     [r14], rdi
0x180022cd9  call    cs:__imp_GetProcessHeap
0x180022cdf  mov     r8, rsi; lpMem
0x180022ce2  xor     edx, edx; dwFlags
0x180022ce4  mov     rcx, rax; hHeap
0x180022ce7  call    cs:__imp_HeapFree
0x180022ced  test    ebx, ebx
0x180022cef  jns     short loc_180022D0A
0x180022cf1  test    rdi, rdi
0x180022cf4  jz      short loc_180022D0A
0x180022cf6  call    cs:__imp_GetProcessHeap
0x180022cfc  mov     r8, rdi; lpMem
0x180022cff  xor     edx, edx; dwFlags
0x180022d01  mov     rcx, rax; hHeap
0x180022d04  call    cs:__imp_HeapFree
0x180022d0a  mov     eax, ebx
0x180022d0c  add     rsp, 38h
0x180022d10  pop     r15
0x180022d12  pop     r14
0x180022d14  pop     r13
0x180022d16  pop     r12
0x180022d18  pop     rdi
0x180022d19  pop     rsi
0x180022d1a  pop     rbp
0x180022d1b  pop     rbx
0x180022d1c  retn
```
