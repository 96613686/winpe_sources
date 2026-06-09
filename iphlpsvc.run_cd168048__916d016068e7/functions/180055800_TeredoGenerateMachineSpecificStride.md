# TeredoGenerateMachineSpecificStride

- ea: `0x180055800`
- end: `0x180055b55`
- name: `TeredoGenerateMachineSpecificStride`
- size: `853`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180038120`

## callees

- `0x18000d7b0`
- `0x18004b630`
- `0x1800555b8`
- `0x180055800`
- `0x180055b5c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180055b28`
- `ntdll!RtlNtStatusToDosError` at `0x180055b28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055938`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800559a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055938`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800559a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005591d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005598c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055ae1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055b06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005591d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005598c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055ae1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055b06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055af5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055b1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055af5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055b1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055aa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055aa4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800558b5`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800558b5`
- `bcrypt!BCryptGetProperty` at `0x1800558f9`
- `bcrypt!BCryptGetProperty` at `0x180055977`
- `bcrypt!BCryptGetProperty` at `0x1800558f9`
- `bcrypt!BCryptGetProperty` at `0x180055977`
- `bcrypt!BCryptCreateHash` at `0x1800559d3`
- `bcrypt!BCryptCreateHash` at `0x1800559d3`
- `bcrypt!BCryptHashData` at `0x180055a06`
- `bcrypt!BCryptHashData` at `0x180055a33`
- `bcrypt!BCryptHashData` at `0x180055a06`
- `bcrypt!BCryptHashData` at `0x180055a33`
- `bcrypt!BCryptFinishHash` at `0x180055a53`
- `bcrypt!BCryptFinishHash` at `0x180055a53`
- `bcrypt!BCryptDestroyHash` at `0x180055ad0`
- `bcrypt!BCryptDestroyHash` at `0x180055ad0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180055abb`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180055abb`

## string_xrefs

- `0x1800558ca`: `BCryptOpenAlgorithmProvider failed %d`
- `0x1800559e8`: `BCryptCreateHash failed %d`

## pseudocode

```c
ULONG __fastcall TeredoGenerateMachineSpecificStride(__int64 a1)
{
  UCHAR *v2; // r15
  UCHAR *v3; // rsi
  NTSTATUS MachineId; // eax
  UCHAR *v5; // r14
  NTSTATUS BestOutgoingPhysicalAddress; // ebx
  __int64 v7; // rdi
  NTSTATUS v8; // eax
  NTSTATUS Property; // eax
  unsigned int v10; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int v12; // ebx
  HANDLE v13; // rax
  NTSTATUS v14; // eax
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  HANDLE v17; // rax
  HANDLE v18; // rax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-39h] BYREF
  UCHAR v21[4]; // [rsp+44h] [rbp-35h] BYREF
  ULONG pcbResult; // [rsp+48h] [rbp-31h] BYREF
  ULONG cbInput; // [rsp+4Ch] [rbp-2Dh] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-29h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-21h] BYREF
  PUCHAR pbInput; // [rsp+60h] [rbp-19h] BYREF
  UCHAR v27[16]; // [rsp+68h] [rbp-11h] BYREF
  __int128 v28; // [rsp+78h] [rbp-1h]

  cbInput = 32;
  pbInput = 0;
  phAlgorithm = 0;
  phHash = 0;
  pcbResult = 0;
  v2 = 0;
  *(_DWORD *)v21 = 0;
  v3 = 0;
  *(_DWORD *)pbOutput = 0;
  *(_OWORD *)v27 = 0;
  gTeredoUPnPPortStride = 0;
  v28 = 0;
  MachineId = GetMachineId(&pbInput);
  v5 = pbInput;
  BestOutgoingPhysicalAddress = MachineId;
  if ( !MachineId )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&pbInput[2 * v7] );
    BestOutgoingPhysicalAddress = TeredoGetBestOutgoingPhysicalAddress(a1, v27, &cbInput);
    if ( !BestOutgoingPhysicalAddress )
    {
      v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
      BestOutgoingPhysicalAddress = v8;
      if ( v8 < 0 )
      {
        EventWrite0(0x100000, L"BCryptOpenAlgorithmProvider failed %d", (unsigned int)v8);
        goto LABEL_21;
      }
      Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
      BestOutgoingPhysicalAddress = Property;
      if ( Property < 0 )
        goto LABEL_8;
      v10 = *(_DWORD *)pbOutput;
      ProcessHeap = GetProcessHeap();
      v2 = (UCHAR *)HeapAlloc(ProcessHeap, 8u, v10);
      if ( !v2 )
        goto LABEL_10;
      Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", v21, 4u, &pcbResult, 0);
      BestOutgoingPhysicalAddress = Property;
      if ( Property < 0 )
      {
LABEL_8:
        EventWrite0(0x100000, L"BCryptGetProperty failed %d", (unsigned int)Property);
        goto LABEL_21;
      }
      v12 = *(_DWORD *)v21;
      v13 = GetProcessHeap();
      v3 = (UCHAR *)HeapAlloc(v13, 8u, v12);
      if ( v3 )
      {
        v14 = BCryptCreateHash(phAlgorithm, &phHash, v2, *(ULONG *)pbOutput, 0, 0, 0);
        BestOutgoingPhysicalAddress = v14;
        if ( v14 >= 0 )
        {
          v15 = BCryptHashData(phHash, v5, 2 * v7 + 1, 0);
          BestOutgoingPhysicalAddress = v15;
          if ( v15 < 0 || (v15 = BCryptHashData(phHash, v27, cbInput, 0), BestOutgoingPhysicalAddress = v15, v15 < 0) )
          {
            EventWrite0(0x100000, L"BCryptHashData failed %d", (unsigned int)v15);
          }
          else
          {
            v16 = BCryptFinishHash(phHash, v3, *(ULONG *)v21, 0);
            BestOutgoingPhysicalAddress = v16;
            if ( v16 >= 0 )
            {
              gTeredoUPnPPortStride = (*(_WORD *)v3 & 0x7FFF) + 1;
              EventWrite0(0x100000, L"Machine specific stride is %d", (unsigned __int16)gTeredoUPnPPortStride);
            }
            else
            {
              EventWrite0(0x100000, L"BCryptFinishHash failed %d", (unsigned int)v16);
            }
          }
        }
        else
        {
          EventWrite0(0x100000, L"BCryptCreateHash failed %d", (unsigned int)v14);
        }
      }
      else
      {
LABEL_10:
        BestOutgoingPhysicalAddress = 8;
      }
    }
  }
LABEL_21:
  if ( v5 )
    LocalFree(v5);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v2 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v2);
  }
  if ( v3 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v3);
  }
  return RtlNtStatusToDosError(BestOutgoingPhysicalAddress);
}

```

## disassembly

```asm
0x180055800  push    rbp
0x180055802  push    rbx
0x180055803  push    rsi
0x180055804  push    rdi
0x180055805  push    r12
0x180055807  push    r13
0x180055809  push    r14
0x18005580b  push    r15
0x18005580d  lea     rbp, [rsp-1Fh]
0x180055812  sub     rsp, 98h
0x180055819  mov     rax, cs:__security_cookie
0x180055820  xor     rax, rsp
0x180055823  mov     [rbp+57h+var_48], rax
0x180055827  xor     r13d, r13d
0x18005582a  mov     [rbp+57h+cbInput], 20h ; ' '
0x180055831  xorps   xmm0, xmm0
0x180055834  mov     [rbp+57h+pbInput], r13
0x180055838  mov     r12, rcx
0x18005583b  mov     [rbp+57h+phAlgorithm], r13
0x18005583f  lea     rcx, [rbp+57h+pbInput]
0x180055843  mov     [rbp+57h+phHash], r13
0x180055847  mov     [rbp+57h+var_88], r13d
0x18005584b  mov     r15d, r13d
0x18005584e  mov     dword ptr [rbp+57h+var_8C], r13d
0x180055852  mov     esi, r13d
0x180055855  mov     dword ptr [rbp+57h+pbOutput], r13d
0x180055859  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18005585d  mov     cs:gTeredoUPnPPortStride, r13w
0x180055865  movups  [rbp+57h+var_58], xmm0
0x180055869  call    GetMachineId
0x18005586e  mov     r14, [rbp+57h+pbInput]
0x180055872  mov     ebx, eax
0x180055874  test    eax, eax
0x180055876  jnz     loc_180055A9C
0x18005587c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180055880  inc     rdi
0x180055883  cmp     [r14+rdi*2], r13w
0x180055888  jnz     short loc_180055880
0x18005588a  lea     r8, [rbp+57h+cbInput]
0x18005588e  mov     rcx, r12
0x180055891  lea     rdx, [rbp+57h+var_68]
0x180055895  call    TeredoGetBestOutgoingPhysicalAddress
0x18005589a  mov     ebx, eax
0x18005589c  test    eax, eax
0x18005589e  jnz     loc_180055A9C
0x1800558a4  xor     r9d, r9d; dwFlags
0x1800558a7  lea     rdx, pszAlgId; "SHA256"
0x1800558ae  xor     r8d, r8d; pszImplementation
0x1800558b1  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x1800558b5  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800558bc  nop     dword ptr [rax+rax+00h]
0x1800558c1  mov     ebx, eax
0x1800558c3  test    eax, eax
0x1800558c5  jns     short loc_1800558D6
0x1800558c7  mov     r8d, eax
0x1800558ca  lea     rdx, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider failed %d"
0x1800558d1  jmp     loc_180055A92
0x1800558d6  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x1800558da  lea     rax, [rbp+57h+var_88]
0x1800558de  mov     [rsp+0D0h+dwFlags], r13d; dwFlags
0x1800558e3  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x1800558e7  mov     r9d, 4; cbOutput
0x1800558ed  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x1800558f2  lea     rdx, pszProperty; "ObjectLength"
0x1800558f9  call    cs:__imp_BCryptGetProperty
0x180055900  nop     dword ptr [rax+rax+00h]
0x180055905  mov     ebx, eax
0x180055907  test    eax, eax
0x180055909  jns     short loc_18005591A
0x18005590b  mov     r8d, eax
0x18005590e  lea     rdx, aBcryptgetprope_0; "BCryptGetProperty failed %d"
0x180055915  jmp     loc_180055A92
0x18005591a  mov     ebx, dword ptr [rbp+57h+pbOutput]
0x18005591d  call    cs:__imp_GetProcessHeap
0x180055924  nop     dword ptr [rax+rax+00h]
0x180055929  mov     r12d, 8
0x18005592f  mov     r8d, ebx; dwBytes
0x180055932  mov     rcx, rax; hHeap
0x180055935  mov     edx, r12d; dwFlags
0x180055938  call    cs:__imp_HeapAlloc
0x18005593f  nop     dword ptr [rax+rax+00h]
0x180055944  mov     r15, rax
0x180055947  test    rax, rax
0x18005594a  jnz     short loc_180055954
0x18005594c  mov     ebx, r12d
0x18005594f  jmp     loc_180055A9C
0x180055954  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x180055958  lea     rax, [rbp+57h+var_88]
0x18005595c  mov     [rsp+0D0h+dwFlags], r13d; dwFlags
0x180055961  lea     r8, [rbp+57h+var_8C]; pbOutput
0x180055965  mov     r9d, 4; cbOutput
0x18005596b  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180055970  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180055977  call    cs:__imp_BCryptGetProperty
0x18005597e  nop     dword ptr [rax+rax+00h]
0x180055983  mov     ebx, eax
0x180055985  test    eax, eax
0x180055987  js      short loc_18005590B
0x180055989  mov     ebx, dword ptr [rbp+57h+var_8C]
0x18005598c  call    cs:__imp_GetProcessHeap
0x180055993  nop     dword ptr [rax+rax+00h]
0x180055998  mov     r8d, ebx; dwBytes
0x18005599b  mov     edx, r12d; dwFlags
0x18005599e  mov     rcx, rax; hHeap
0x1800559a1  call    cs:__imp_HeapAlloc
0x1800559a8  nop     dword ptr [rax+rax+00h]
0x1800559ad  mov     rsi, rax
0x1800559b0  test    rax, rax
0x1800559b3  jz      short loc_18005594C
0x1800559b5  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x1800559b9  lea     rdx, [rbp+57h+phHash]; phHash
0x1800559bd  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800559c1  mov     r8, r15; pbHashObject
0x1800559c4  mov     [rsp+0D0h+var_A0], r13d; dwFlags
0x1800559c9  mov     [rsp+0D0h+dwFlags], r13d; cbSecret
0x1800559ce  mov     [rsp+0D0h+pcbResult], r13; pbSecret
0x1800559d3  call    cs:__imp_BCryptCreateHash
0x1800559da  nop     dword ptr [rax+rax+00h]
0x1800559df  mov     ebx, eax
0x1800559e1  test    eax, eax
0x1800559e3  jns     short loc_1800559F4
0x1800559e5  mov     r8d, eax
0x1800559e8  lea     rdx, aBcryptcreateha_0; "BCryptCreateHash failed %d"
0x1800559ef  jmp     loc_180055A92
0x1800559f4  mov     rcx, [rbp+57h+phHash]; hHash
0x1800559f8  lea     r8d, ds:1[rdi*2]; cbInput
0x180055a00  xor     r9d, r9d; dwFlags
0x180055a03  mov     rdx, r14; pbInput
0x180055a06  call    cs:__imp_BCryptHashData
0x180055a0d  nop     dword ptr [rax+rax+00h]
0x180055a12  mov     ebx, eax
0x180055a14  test    eax, eax
0x180055a16  jns     short loc_180055A24
0x180055a18  mov     r8d, eax
0x180055a1b  lea     rdx, aBcrypthashdata_0; "BCryptHashData failed %d"
0x180055a22  jmp     short loc_180055A92
0x180055a24  mov     r8d, [rbp+57h+cbInput]; cbInput
0x180055a28  lea     rdx, [rbp+57h+var_68]; pbInput
0x180055a2c  mov     rcx, [rbp+57h+phHash]; hHash
0x180055a30  xor     r9d, r9d; dwFlags
0x180055a33  call    cs:__imp_BCryptHashData
0x180055a3a  nop     dword ptr [rax+rax+00h]
0x180055a3f  mov     ebx, eax
0x180055a41  test    eax, eax
0x180055a43  js      short loc_180055A18
0x180055a45  mov     r8d, dword ptr [rbp+57h+var_8C]; cbOutput
0x180055a49  xor     r9d, r9d; dwFlags
0x180055a4c  mov     rcx, [rbp+57h+phHash]; hHash
0x180055a50  mov     rdx, rsi; pbOutput
0x180055a53  call    cs:__imp_BCryptFinishHash
0x180055a5a  nop     dword ptr [rax+rax+00h]
0x180055a5f  mov     ebx, eax
0x180055a61  test    eax, eax
0x180055a63  jns     short loc_180055A71
0x180055a65  mov     r8d, eax
0x180055a68  lea     rdx, aBcryptfinishha_0; "BCryptFinishHash failed %d"
0x180055a6f  jmp     short loc_180055A92
0x180055a71  movzx   eax, word ptr [rsi]
0x180055a74  lea     rdx, aMachineSpecifi; "Machine specific stride is %d"
0x180055a7b  mov     ecx, 7FFFh
0x180055a80  and     ax, cx
0x180055a83  inc     ax
0x180055a86  movzx   r8d, ax
0x180055a8a  mov     cs:gTeredoUPnPPortStride, r8w
0x180055a92  mov     ecx, 100000h
0x180055a97  call    EventWrite0
0x180055a9c  test    r14, r14
0x180055a9f  jz      short loc_180055AB0
0x180055aa1  mov     rcx, r14; hMem
0x180055aa4  call    cs:__imp_LocalFree
0x180055aab  nop     dword ptr [rax+rax+00h]
0x180055ab0  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180055ab4  test    rcx, rcx
0x180055ab7  jz      short loc_180055AC7
0x180055ab9  xor     edx, edx; dwFlags
0x180055abb  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180055ac2  nop     dword ptr [rax+rax+00h]
0x180055ac7  mov     rcx, [rbp+57h+phHash]; hHash
0x180055acb  test    rcx, rcx
0x180055ace  jz      short loc_180055ADC
0x180055ad0  call    cs:__imp_BCryptDestroyHash
0x180055ad7  nop     dword ptr [rax+rax+00h]
0x180055adc  test    r15, r15
0x180055adf  jz      short loc_180055B01
0x180055ae1  call    cs:__imp_GetProcessHeap
0x180055ae8  nop     dword ptr [rax+rax+00h]
0x180055aed  mov     r8, r15; lpMem
0x180055af0  xor     edx, edx; dwFlags
0x180055af2  mov     rcx, rax; hHeap
0x180055af5  call    cs:__imp_HeapFree
0x180055afc  nop     dword ptr [rax+rax+00h]
0x180055b01  test    rsi, rsi
0x180055b04  jz      short loc_180055B26
0x180055b06  call    cs:__imp_GetProcessHeap
0x180055b0d  nop     dword ptr [rax+rax+00h]
0x180055b12  mov     r8, rsi; lpMem
0x180055b15  xor     edx, edx; dwFlags
0x180055b17  mov     rcx, rax; hHeap
0x180055b1a  call    cs:__imp_HeapFree
0x180055b21  nop     dword ptr [rax+rax+00h]
0x180055b26  mov     ecx, ebx; Status
0x180055b28  call    cs:__imp_RtlNtStatusToDosError
0x180055b2f  nop     dword ptr [rax+rax+00h]
0x180055b34  mov     rcx, [rbp+57h+var_48]
0x180055b38  xor     rcx, rsp; StackCookie
0x180055b3b  call    __security_check_cookie
0x180055b40  add     rsp, 98h
0x180055b47  pop     r15
0x180055b49  pop     r14
0x180055b4b  pop     r13
0x180055b4d  pop     r12
0x180055b4f  pop     rdi
0x180055b50  pop     rsi
0x180055b51  pop     rbx
0x180055b52  pop     rbp
0x180055b53  retn
```
