# TeredoGenerateMachineSpecificStride

- ea: `0x180055820`
- end: `0x180055b75`
- name: `TeredoGenerateMachineSpecificStride`
- size: `853`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180038130`

## callees

- `0x18000d7c0`
- `0x18004b5f0`
- `0x1800555d8`
- `0x180055820`
- `0x180055b7c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180055b48`
- `ntdll!RtlNtStatusToDosError` at `0x180055b48`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055958`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800559c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180055958`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800559c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005593d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800559ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055b01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055b26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005593d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800559ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055b01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055b26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055b15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055b3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055b15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055b3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055ac4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180055ac4`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800558d5`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800558d5`
- `bcrypt!BCryptGetProperty` at `0x180055919`
- `bcrypt!BCryptGetProperty` at `0x180055997`
- `bcrypt!BCryptGetProperty` at `0x180055919`
- `bcrypt!BCryptGetProperty` at `0x180055997`
- `bcrypt!BCryptCreateHash` at `0x1800559f3`
- `bcrypt!BCryptCreateHash` at `0x1800559f3`
- `bcrypt!BCryptHashData` at `0x180055a26`
- `bcrypt!BCryptHashData` at `0x180055a53`
- `bcrypt!BCryptHashData` at `0x180055a26`
- `bcrypt!BCryptHashData` at `0x180055a53`
- `bcrypt!BCryptFinishHash` at `0x180055a73`
- `bcrypt!BCryptFinishHash` at `0x180055a73`
- `bcrypt!BCryptDestroyHash` at `0x180055af0`
- `bcrypt!BCryptDestroyHash` at `0x180055af0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180055adb`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180055adb`

## string_xrefs

- `0x1800558ea`: `BCryptOpenAlgorithmProvider failed %d`
- `0x180055a08`: `BCryptCreateHash failed %d`

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
0x180055820  push    rbp
0x180055822  push    rbx
0x180055823  push    rsi
0x180055824  push    rdi
0x180055825  push    r12
0x180055827  push    r13
0x180055829  push    r14
0x18005582b  push    r15
0x18005582d  lea     rbp, [rsp-1Fh]
0x180055832  sub     rsp, 98h
0x180055839  mov     rax, cs:__security_cookie
0x180055840  xor     rax, rsp
0x180055843  mov     [rbp+57h+var_48], rax
0x180055847  xor     r13d, r13d
0x18005584a  mov     [rbp+57h+cbInput], 20h ; ' '
0x180055851  xorps   xmm0, xmm0
0x180055854  mov     [rbp+57h+pbInput], r13
0x180055858  mov     r12, rcx
0x18005585b  mov     [rbp+57h+phAlgorithm], r13
0x18005585f  lea     rcx, [rbp+57h+pbInput]
0x180055863  mov     [rbp+57h+phHash], r13
0x180055867  mov     [rbp+57h+var_88], r13d
0x18005586b  mov     r15d, r13d
0x18005586e  mov     dword ptr [rbp+57h+var_8C], r13d
0x180055872  mov     esi, r13d
0x180055875  mov     dword ptr [rbp+57h+pbOutput], r13d
0x180055879  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18005587d  mov     cs:gTeredoUPnPPortStride, r13w
0x180055885  movups  [rbp+57h+var_58], xmm0
0x180055889  call    GetMachineId
0x18005588e  mov     r14, [rbp+57h+pbInput]
0x180055892  mov     ebx, eax
0x180055894  test    eax, eax
0x180055896  jnz     loc_180055ABC
0x18005589c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800558a0  inc     rdi
0x1800558a3  cmp     [r14+rdi*2], r13w
0x1800558a8  jnz     short loc_1800558A0
0x1800558aa  lea     r8, [rbp+57h+cbInput]
0x1800558ae  mov     rcx, r12
0x1800558b1  lea     rdx, [rbp+57h+var_68]
0x1800558b5  call    TeredoGetBestOutgoingPhysicalAddress
0x1800558ba  mov     ebx, eax
0x1800558bc  test    eax, eax
0x1800558be  jnz     loc_180055ABC
0x1800558c4  xor     r9d, r9d; dwFlags
0x1800558c7  lea     rdx, pszAlgId; "SHA256"
0x1800558ce  xor     r8d, r8d; pszImplementation
0x1800558d1  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x1800558d5  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800558dc  nop     dword ptr [rax+rax+00h]
0x1800558e1  mov     ebx, eax
0x1800558e3  test    eax, eax
0x1800558e5  jns     short loc_1800558F6
0x1800558e7  mov     r8d, eax
0x1800558ea  lea     rdx, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider failed %d"
0x1800558f1  jmp     loc_180055AB2
0x1800558f6  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x1800558fa  lea     rax, [rbp+57h+var_88]
0x1800558fe  mov     [rsp+0D0h+dwFlags], r13d; dwFlags
0x180055903  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180055907  mov     r9d, 4; cbOutput
0x18005590d  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180055912  lea     rdx, pszProperty; "ObjectLength"
0x180055919  call    cs:__imp_BCryptGetProperty
0x180055920  nop     dword ptr [rax+rax+00h]
0x180055925  mov     ebx, eax
0x180055927  test    eax, eax
0x180055929  jns     short loc_18005593A
0x18005592b  mov     r8d, eax
0x18005592e  lea     rdx, aBcryptgetprope_0; "BCryptGetProperty failed %d"
0x180055935  jmp     loc_180055AB2
0x18005593a  mov     ebx, dword ptr [rbp+57h+pbOutput]
0x18005593d  call    cs:__imp_GetProcessHeap
0x180055944  nop     dword ptr [rax+rax+00h]
0x180055949  mov     r12d, 8
0x18005594f  mov     r8d, ebx; dwBytes
0x180055952  mov     rcx, rax; hHeap
0x180055955  mov     edx, r12d; dwFlags
0x180055958  call    cs:__imp_HeapAlloc
0x18005595f  nop     dword ptr [rax+rax+00h]
0x180055964  mov     r15, rax
0x180055967  test    rax, rax
0x18005596a  jnz     short loc_180055974
0x18005596c  mov     ebx, r12d
0x18005596f  jmp     loc_180055ABC
0x180055974  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x180055978  lea     rax, [rbp+57h+var_88]
0x18005597c  mov     [rsp+0D0h+dwFlags], r13d; dwFlags
0x180055981  lea     r8, [rbp+57h+var_8C]; pbOutput
0x180055985  mov     r9d, 4; cbOutput
0x18005598b  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x180055990  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180055997  call    cs:__imp_BCryptGetProperty
0x18005599e  nop     dword ptr [rax+rax+00h]
0x1800559a3  mov     ebx, eax
0x1800559a5  test    eax, eax
0x1800559a7  js      short loc_18005592B
0x1800559a9  mov     ebx, dword ptr [rbp+57h+var_8C]
0x1800559ac  call    cs:__imp_GetProcessHeap
0x1800559b3  nop     dword ptr [rax+rax+00h]
0x1800559b8  mov     r8d, ebx; dwBytes
0x1800559bb  mov     edx, r12d; dwFlags
0x1800559be  mov     rcx, rax; hHeap
0x1800559c1  call    cs:__imp_HeapAlloc
0x1800559c8  nop     dword ptr [rax+rax+00h]
0x1800559cd  mov     rsi, rax
0x1800559d0  test    rax, rax
0x1800559d3  jz      short loc_18005596C
0x1800559d5  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x1800559d9  lea     rdx, [rbp+57h+phHash]; phHash
0x1800559dd  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x1800559e1  mov     r8, r15; pbHashObject
0x1800559e4  mov     [rsp+0D0h+var_A0], r13d; dwFlags
0x1800559e9  mov     [rsp+0D0h+dwFlags], r13d; cbSecret
0x1800559ee  mov     [rsp+0D0h+pcbResult], r13; pbSecret
0x1800559f3  call    cs:__imp_BCryptCreateHash
0x1800559fa  nop     dword ptr [rax+rax+00h]
0x1800559ff  mov     ebx, eax
0x180055a01  test    eax, eax
0x180055a03  jns     short loc_180055A14
0x180055a05  mov     r8d, eax
0x180055a08  lea     rdx, aBcryptcreateha_0; "BCryptCreateHash failed %d"
0x180055a0f  jmp     loc_180055AB2
0x180055a14  mov     rcx, [rbp+57h+phHash]; hHash
0x180055a18  lea     r8d, ds:1[rdi*2]; cbInput
0x180055a20  xor     r9d, r9d; dwFlags
0x180055a23  mov     rdx, r14; pbInput
0x180055a26  call    cs:__imp_BCryptHashData
0x180055a2d  nop     dword ptr [rax+rax+00h]
0x180055a32  mov     ebx, eax
0x180055a34  test    eax, eax
0x180055a36  jns     short loc_180055A44
0x180055a38  mov     r8d, eax
0x180055a3b  lea     rdx, aBcrypthashdata_0; "BCryptHashData failed %d"
0x180055a42  jmp     short loc_180055AB2
0x180055a44  mov     r8d, [rbp+57h+cbInput]; cbInput
0x180055a48  lea     rdx, [rbp+57h+var_68]; pbInput
0x180055a4c  mov     rcx, [rbp+57h+phHash]; hHash
0x180055a50  xor     r9d, r9d; dwFlags
0x180055a53  call    cs:__imp_BCryptHashData
0x180055a5a  nop     dword ptr [rax+rax+00h]
0x180055a5f  mov     ebx, eax
0x180055a61  test    eax, eax
0x180055a63  js      short loc_180055A38
0x180055a65  mov     r8d, dword ptr [rbp+57h+var_8C]; cbOutput
0x180055a69  xor     r9d, r9d; dwFlags
0x180055a6c  mov     rcx, [rbp+57h+phHash]; hHash
0x180055a70  mov     rdx, rsi; pbOutput
0x180055a73  call    cs:__imp_BCryptFinishHash
0x180055a7a  nop     dword ptr [rax+rax+00h]
0x180055a7f  mov     ebx, eax
0x180055a81  test    eax, eax
0x180055a83  jns     short loc_180055A91
0x180055a85  mov     r8d, eax
0x180055a88  lea     rdx, aBcryptfinishha_0; "BCryptFinishHash failed %d"
0x180055a8f  jmp     short loc_180055AB2
0x180055a91  movzx   eax, word ptr [rsi]
0x180055a94  lea     rdx, aMachineSpecifi; "Machine specific stride is %d"
0x180055a9b  mov     ecx, 7FFFh
0x180055aa0  and     ax, cx
0x180055aa3  inc     ax
0x180055aa6  movzx   r8d, ax
0x180055aaa  mov     cs:gTeredoUPnPPortStride, r8w
0x180055ab2  mov     ecx, 100000h
0x180055ab7  call    EventWrite0
0x180055abc  test    r14, r14
0x180055abf  jz      short loc_180055AD0
0x180055ac1  mov     rcx, r14; hMem
0x180055ac4  call    cs:__imp_LocalFree
0x180055acb  nop     dword ptr [rax+rax+00h]
0x180055ad0  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180055ad4  test    rcx, rcx
0x180055ad7  jz      short loc_180055AE7
0x180055ad9  xor     edx, edx; dwFlags
0x180055adb  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180055ae2  nop     dword ptr [rax+rax+00h]
0x180055ae7  mov     rcx, [rbp+57h+phHash]; hHash
0x180055aeb  test    rcx, rcx
0x180055aee  jz      short loc_180055AFC
0x180055af0  call    cs:__imp_BCryptDestroyHash
0x180055af7  nop     dword ptr [rax+rax+00h]
0x180055afc  test    r15, r15
0x180055aff  jz      short loc_180055B21
0x180055b01  call    cs:__imp_GetProcessHeap
0x180055b08  nop     dword ptr [rax+rax+00h]
0x180055b0d  mov     r8, r15; lpMem
0x180055b10  xor     edx, edx; dwFlags
0x180055b12  mov     rcx, rax; hHeap
0x180055b15  call    cs:__imp_HeapFree
0x180055b1c  nop     dword ptr [rax+rax+00h]
0x180055b21  test    rsi, rsi
0x180055b24  jz      short loc_180055B46
0x180055b26  call    cs:__imp_GetProcessHeap
0x180055b2d  nop     dword ptr [rax+rax+00h]
0x180055b32  mov     r8, rsi; lpMem
0x180055b35  xor     edx, edx; dwFlags
0x180055b37  mov     rcx, rax; hHeap
0x180055b3a  call    cs:__imp_HeapFree
0x180055b41  nop     dword ptr [rax+rax+00h]
0x180055b46  mov     ecx, ebx; Status
0x180055b48  call    cs:__imp_RtlNtStatusToDosError
0x180055b4f  nop     dword ptr [rax+rax+00h]
0x180055b54  mov     rcx, [rbp+57h+var_48]
0x180055b58  xor     rcx, rsp; StackCookie
0x180055b5b  call    __security_check_cookie
0x180055b60  add     rsp, 98h
0x180055b67  pop     r15
0x180055b69  pop     r14
0x180055b6b  pop     r13
0x180055b6d  pop     r12
0x180055b6f  pop     rdi
0x180055b70  pop     rsi
0x180055b71  pop     rbx
0x180055b72  pop     rbp
0x180055b73  retn
```
