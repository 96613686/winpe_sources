# PcapChainDataBuilderGetUserData(ushort *,int *,int *,void *)

- ea: `0x18000eba4`
- end: `0x18000ed8b`
- name: `?PcapChainDataBuilderGetUserData@@YAKPEAGPEAH1PEAX@Z`
- size: `487`
- prototype: `unsigned int __fastcall(STRSAFE_LPWSTR pszDest, int *, int *, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000e608`

## callees

- `0x18000eba4`
- `0x180012920`
- `0x1800133c0`
- `0x180032d70`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ed1e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000ed1e`
- `ntdll!RtlFreeHeap` at `0x18000ecaa`
- `ntdll!RtlFreeHeap` at `0x18000ecaa`
- `ntdll!RtlAllocateHeap` at `0x18000ebfa`
- `ntdll!RtlAllocateHeap` at `0x18000ebfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed56`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18000ec88`
- `api-ms-win-core-kernel32-private-l1-1-0!CheckElevationEnabled` at `0x18000ec88`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000ec24`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000ec24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ecba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ecba`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ec3a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000ec3a`

## string_xrefs

- `0x18000ece1`: `GetTokenInformation failed [%d]`
- `0x18000ed09`: `Failed to copy sid string [%d]`
- `0x18000ed5c`: `Failed to get sid string [%d]`

## pseudocode

```c
__int64 __fastcall PcapChainDataBuilderGetUserData(STRSAFE_LPWSTR pszDest, int *a2, int *a3, void *a4)
{
  unsigned int v8; // ebx
  PSID *Heap; // rsi
  size_t *v10; // r8
  NTSTATUS v11; // eax
  ULONG LastError; // eax
  const char *v14; // r9
  int v15; // r8d
  PDWORD ReturnLength; // [rsp+20h] [rbp-48h]
  DWORD v17; // [rsp+30h] [rbp-38h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-30h] BYREF
  int v19; // [rsp+70h] [rbp+8h] BYREF

  v17 = 0;
  StringSid = 0;
  v19 = 0;
  *pszDest = 0;
  v8 = 8;
  Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x5Cu);
  if ( Heap )
  {
    if ( GetTokenInformation(a4, TokenUser, Heap, 0x5Cu, &v17) )
    {
      if ( ConvertSidToStringSidW(*Heap, &StringSid) )
      {
        if ( StringCopyWorkerW(pszDest, 0x104u, v10, StringSid, (size_t)ReturnLength) < 0 )
        {
          v8 = 111;
          v14 = "Failed to copy sid string [%d]";
          v15 = 296;
          goto LABEL_14;
        }
        v11 = LUAGetUserType(a4, &v19);
        if ( v11 >= 0 )
        {
          *a2 = v19 == 2;
          v8 = CheckElevationEnabled(a3);
          if ( v8 )
            AslLogCallPrintf(
              1,
              (unsigned int)"PcapChainDataBuilderGetUserData",
              319,
              (unsigned int)"Failed to get elevation state");
          goto LABEL_8;
        }
        LastError = RtlNtStatusToDosErrorNoTeb(v11);
        v14 = "Failed to get user type [%d]";
        v15 = 307;
      }
      else
      {
        LastError = GetLastError();
        v14 = "Failed to get sid string [%d]";
        v15 = 288;
      }
    }
    else
    {
      LastError = GetLastError();
      v14 = "GetTokenInformation failed [%d]";
      v15 = 278;
    }
    v8 = LastError;
LABEL_14:
    AslLogCallPrintf(1, (unsigned int)"PcapChainDataBuilderGetUserData", v15, (_DWORD)v14);
LABEL_8:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    goto LABEL_9;
  }
  AslLogCallPrintf(1, (unsigned int)"PcapChainDataBuilderGetUserData", 263, (unsigned int)"Out of memory");
LABEL_9:
  if ( StringSid )
    LocalFree(StringSid);
  return v8;
}

```

## disassembly

```asm
0x18000eba4  mov     rax, rsp
0x18000eba7  mov     [rax+10h], rbx
0x18000ebab  mov     [rax+18h], rbp
0x18000ebaf  push    rsi
0x18000ebb0  push    rdi
0x18000ebb1  push    r12
0x18000ebb3  push    r14
0x18000ebb5  push    r15
0x18000ebb7  sub     rsp, 40h
0x18000ebbb  mov     dword ptr [rax-38h], 0
0x18000ebc2  mov     r14, rcx
0x18000ebc5  mov     qword ptr [rax-30h], 0
0x18000ebcd  mov     r15, r8
0x18000ebd0  mov     dword ptr [rax+8], 0
0x18000ebd7  mov     r12, rdx
0x18000ebda  xor     eax, eax
0x18000ebdc  mov     rbp, r9
0x18000ebdf  mov     [rcx], ax
0x18000ebe2  mov     rcx, gs:60h
0x18000ebeb  lea     edi, [rax+5Ch]
0x18000ebee  lea     ebx, [rax+8]
0x18000ebf1  mov     r8d, edi; Size
0x18000ebf4  mov     rcx, [rcx+30h]; HeapHandle
0x18000ebf8  mov     edx, ebx; Flags
0x18000ebfa  call    cs:__imp_RtlAllocateHeap
0x18000ec00  mov     rsi, rax
0x18000ec03  test    rax, rax
0x18000ec06  jz      loc_18000ED33
0x18000ec0c  mov     r9d, edi; TokenInformationLength
0x18000ec0f  lea     rax, [rsp+68h+var_38]
0x18000ec14  lea     edi, [rbx-7]
0x18000ec17  mov     [rsp+68h+ReturnLength], rax; cchToCopy
0x18000ec1c  mov     edx, edi; TokenInformationClass
0x18000ec1e  mov     r8, rsi; TokenInformation
0x18000ec21  mov     rcx, rbp; TokenHandle
0x18000ec24  call    cs:__imp_GetTokenInformation
0x18000ec2a  test    eax, eax
0x18000ec2c  jz      loc_18000ECDB
0x18000ec32  mov     rcx, [rsi]; Sid
0x18000ec35  lea     rdx, [rsp+68h+StringSid]; StringSid
0x18000ec3a  call    cs:__imp_ConvertSidToStringSidW
0x18000ec40  test    eax, eax
0x18000ec42  jz      loc_18000ED56
0x18000ec48  mov     r9, [rsp+68h+StringSid]; pszSrc
0x18000ec4d  mov     edx, 104h; cchDest
0x18000ec52  mov     rcx, r14; pszDest
0x18000ec55  call    StringCopyWorkerW
0x18000ec5a  test    eax, eax
0x18000ec5c  js      loc_18000ED04
0x18000ec62  lea     rdx, [rsp+68h+arg_0]
0x18000ec67  mov     rcx, rbp
0x18000ec6a  call    LUAGetUserType
0x18000ec6f  test    eax, eax
0x18000ec71  js      loc_18000ED1C
0x18000ec77  xor     eax, eax
0x18000ec79  mov     rcx, r15
0x18000ec7c  cmp     [rsp+68h+arg_0], 2
0x18000ec81  setz    al
0x18000ec84  mov     [r12], eax
0x18000ec88  call    cs:__imp_CheckElevationEnabled
0x18000ec8e  mov     ebx, eax
0x18000ec90  test    eax, eax
0x18000ec92  jnz     loc_18000ED6B
0x18000ec98  mov     rcx, gs:60h
0x18000eca1  mov     r8, rsi; P
0x18000eca4  xor     edx, edx; Flags
0x18000eca6  mov     rcx, [rcx+30h]; HeapHandle
0x18000ecaa  call    cs:__imp_RtlFreeHeap
0x18000ecb0  mov     rcx, [rsp+68h+StringSid]; hMem
0x18000ecb5  test    rcx, rcx
0x18000ecb8  jz      short loc_18000ECC0
0x18000ecba  call    cs:__imp_LocalFree
0x18000ecc0  lea     r11, [rsp+68h+var_28]
0x18000ecc5  mov     eax, ebx
0x18000ecc7  mov     rbx, [r11+38h]
0x18000eccb  mov     rbp, [r11+40h]
0x18000eccf  mov     rsp, r11
0x18000ecd2  pop     r15
0x18000ecd4  pop     r14
0x18000ecd6  pop     r12
0x18000ecd8  pop     rdi
0x18000ecd9  pop     rsi
0x18000ecda  retn
0x18000ecdb  call    cs:__imp_GetLastError
0x18000ece1  lea     r9, aGettokeninform_2; "GetTokenInformation failed [%d]"
0x18000ece8  mov     r8d, 116h
0x18000ecee  mov     ebx, eax
0x18000ecf0  mov     dword ptr [rsp+68h+ReturnLength], eax
0x18000ecf4  lea     rdx, aPcapchaindatab_0; "PcapChainDataBuilderGetUserData"
0x18000ecfb  mov     ecx, edi
0x18000ecfd  call    AslLogCallPrintf
0x18000ed02  jmp     short loc_18000EC98
0x18000ed04  mov     ebx, 6Fh ; 'o'
0x18000ed09  lea     r9, aFailedToCopySi; "Failed to copy sid string [%d]"
0x18000ed10  mov     dword ptr [rsp+68h+ReturnLength], ebx
0x18000ed14  mov     r8d, 128h
0x18000ed1a  jmp     short loc_18000ECF4
0x18000ed1c  mov     ecx, eax; Status
0x18000ed1e  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000ed24  lea     r9, aFailedToGetUse_1; "Failed to get user type [%d]"
0x18000ed2b  mov     r8d, 133h
0x18000ed31  jmp     short loc_18000ECEE
0x18000ed33  lea     r9, aOutOfMemory; "Out of memory"
0x18000ed3a  mov     r8d, 107h
0x18000ed40  lea     rdx, aPcapchaindatab_0; "PcapChainDataBuilderGetUserData"
0x18000ed47  mov     ecx, 1
0x18000ed4c  call    AslLogCallPrintf
0x18000ed51  jmp     loc_18000ECB0
0x18000ed56  call    cs:__imp_GetLastError
0x18000ed5c  lea     r9, aFailedToGetSid; "Failed to get sid string [%d]"
0x18000ed63  mov     r8d, 120h
0x18000ed69  jmp     short loc_18000ECEE
0x18000ed6b  lea     r9, aFailedToGetEle; "Failed to get elevation state"
0x18000ed72  mov     r8d, 13Fh
0x18000ed78  lea     rdx, aPcapchaindatab_0; "PcapChainDataBuilderGetUserData"
0x18000ed7f  mov     ecx, edi
0x18000ed81  call    AslLogCallPrintf
0x18000ed86  jmp     loc_18000EC98
```
