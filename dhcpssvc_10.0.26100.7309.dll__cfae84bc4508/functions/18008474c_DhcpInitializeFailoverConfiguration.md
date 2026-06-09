# DhcpInitializeFailoverConfiguration

- ea: `0x18008474c`
- end: `0x180084e3a`
- name: `DhcpInitializeFailoverConfiguration`
- size: `1774`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config`

## callers

- `0x180025bf4`

## callees

- `0x1800058cc`
- `0x18001ceb4`
- `0x180025264`
- `0x180025424`
- `0x18002e738`
- `0x1800808e0`
- `0x180084018`
- `0x18008474c`
- `0x18008ae54`
- `0x180092f64`
- `0x1800930bc`
- `0x18009602c`
- `0x180096080`
- `0x18009db78`
- `0x18009e198`
- `0x18009f7c4`
- `0x18009fa94`
- `0x18009fee0`
- `0x1800a032c`
- `0x1800a23e0`
- `0x1800a7b34`
- `0x1800a7f78`
- `0x1800a9270`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x1800847fd`
- `ESENT!JetSetCurrentIndex` at `0x1800847fd`
- `ESENT!JetMove` at `0x18008482e`
- `ESENT!JetMove` at `0x18008482e`
- `WS2_32!__imp_htonl` at `0x180084ccd`
- `WS2_32!__imp_htonl` at `0x180084ccd`
- `KERNEL32!HeapAlloc` at `0x1800847d1`
- `KERNEL32!HeapAlloc` at `0x1800847d1`
- `KERNEL32!InitializeSRWLock` at `0x18008477d`
- `KERNEL32!InitializeSRWLock` at `0x18008477d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180084a4b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180084a4b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180084a34`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180084a34`
- `KERNEL32!EnterCriticalSection` at `0x1800849a7`
- `KERNEL32!EnterCriticalSection` at `0x1800849f3`
- `KERNEL32!EnterCriticalSection` at `0x1800849a7`
- `KERNEL32!EnterCriticalSection` at `0x1800849f3`
- `KERNEL32!LeaveCriticalSection` at `0x1800849c9`
- `KERNEL32!LeaveCriticalSection` at `0x180084a18`
- `KERNEL32!LeaveCriticalSection` at `0x1800849c9`
- `KERNEL32!LeaveCriticalSection` at `0x180084a18`
- `KERNEL32!HeapFree` at `0x1800848ab`
- `KERNEL32!HeapFree` at `0x180084bb8`
- `KERNEL32!HeapFree` at `0x180084d57`
- `KERNEL32!HeapFree` at `0x180084d74`
- `KERNEL32!HeapFree` at `0x180084d92`
- `KERNEL32!HeapFree` at `0x180084db9`
- `KERNEL32!HeapFree` at `0x180084dd2`
- `KERNEL32!HeapFree` at `0x180084df0`
- `KERNEL32!HeapFree` at `0x180084e1a`
- `KERNEL32!HeapFree` at `0x1800848ab`
- `KERNEL32!HeapFree` at `0x180084bb8`
- `KERNEL32!HeapFree` at `0x180084d57`
- `KERNEL32!HeapFree` at `0x180084d74`
- `KERNEL32!HeapFree` at `0x180084d92`
- `KERNEL32!HeapFree` at `0x180084db9`
- `KERNEL32!HeapFree` at `0x180084dd2`
- `KERNEL32!HeapFree` at `0x180084df0`
- `KERNEL32!HeapFree` at `0x180084e1a`

## string_xrefs

- `0x180084d12`: `DhcpInitializeFailoverConfiguration`

## pseudocode

```c
LSTATUS DhcpInitializeFailoverConfiguration()
{
  LSTATUS v0; // ebx
  LSTATUS result; // eax
  __int64 v2; // [rsp+30h] [rbp-38h]
  LPVOID lpMem; // [rsp+38h] [rbp-30h]
  int v4; // [rsp+C0h] [rbp+58h]

  v4 = 0;
  lpMem = 0;
  v2 = 0;
  InitializeSRWLock(&FailoverAPILock);
  if ( (unsigned int)DhcpDALJetElementsTotal(DhcpGlobalJetServerSession) )
    return 87;
  result = DhcpFailoverReadRegKeyParams();
  v0 = result;
  if ( !result )
    return result;
  return v0;
}

```

## disassembly

```asm
0x18008474c  mov     [rsp-40h+arg_0], ecx
0x180084750  push    rbp
0x180084751  push    rbx
0x180084752  push    rsi
0x180084753  push    rdi
0x180084754  push    r12
0x180084756  push    r13
0x180084758  push    r14
0x18008475a  push    r15
0x18008475c  mov     rbp, rsp
0x18008475f  sub     rsp, 68h
0x180084763  xor     ebx, ebx
0x180084765  lea     rcx, FailoverAPILock; SRWLock
0x18008476c  mov     r13d, ebx
0x18008476f  mov     [rbp+arg_10], ebx
0x180084772  mov     r12d, ebx
0x180084775  mov     [rbp+lpMem], rbx
0x180084779  mov     [rbp+var_38], rbx
0x18008477d  call    cs:__imp_InitializeSRWLock
0x180084784  nop     dword ptr [rax+rax+00h]
0x180084789  mov     rdi, cs:DhcpGlobalJetServerSession
0x180084790  lea     r9, [rbp+arg_8]
0x180084794  mov     rcx, rdi; sesid
0x180084797  mov     [rbp+arg_8], ebx
0x18008479a  call    DhcpDALJetElementsTotal
0x18008479f  test    eax, eax
0x1800847a1  jz      short loc_1800847AC
0x1800847a3  lea     ebx, [r13+57h]
0x1800847a7  jmp     loc_180084E26
0x1800847ac  mov     r14d, [rbp+arg_8]
0x1800847b0  mov     r15d, 8
0x1800847b6  test    r14d, r14d
0x1800847b9  jz      loc_1800848C0
0x1800847bf  mov     rcx, cs:gDhcpHeap; hHeap
0x1800847c6  lea     r8, [r14+r14*4]
0x1800847ca  shl     r8, 4; dwBytes
0x1800847ce  mov     edx, r15d; dwFlags
0x1800847d1  call    cs:__imp_HeapAlloc
0x1800847d8  nop     dword ptr [rax+rax+00h]
0x1800847dd  mov     rsi, rax
0x1800847e0  test    rax, rax
0x1800847e3  jnz     short loc_1800847ED
0x1800847e5  mov     ebx, r15d
0x1800847e8  jmp     loc_180084E26
0x1800847ed  mov     r15, cs:FailoverConfTableHandle
0x1800847f4  xor     r8d, r8d
0x1800847f7  mov     rdx, r15
0x1800847fa  mov     rcx, rdi
0x1800847fd  call    cs:__imp_JetSetCurrentIndex
0x180084804  nop     dword ptr [rax+rax+00h]
0x180084809  mov     ecx, eax
0x18008480b  lea     rdx, aDhcpdaljetprep_0; "DhcpDALJetPrepareSearchEx"
0x180084812  call    DhcpDALMapJetError
0x180084817  mov     ebx, eax
0x180084819  xor     eax, eax
0x18008481b  test    ebx, ebx
0x18008481d  jnz     short loc_18008489D
0x18008481f  xor     r9d, r9d; grbit
0x180084822  mov     r8d, 80000000h; cRow
0x180084828  mov     rdx, r15; tableid
0x18008482b  mov     rcx, rdi; sesid
0x18008482e  call    cs:__imp_JetMove
0x180084835  nop     dword ptr [rax+rax+00h]
0x18008483a  mov     ecx, eax
0x18008483c  lea     rdx, aDhcpdaljetprep_1; "DhcpDALJetPrepareSearchEx:MakeKey"
0x180084843  call    DhcpDALMapJetError
0x180084848  mov     ebx, eax
0x18008484a  xor     eax, eax
0x18008484c  test    ebx, ebx
0x18008484e  jnz     short loc_18008489D
0x180084850  mov     r15d, eax
0x180084853  mov     eax, r15d
0x180084856  mov     rcx, rdi; sesid
0x180084859  lea     rdx, [rax+rax*4]
0x18008485d  shl     rdx, 4
0x180084861  add     rdx, rsi
0x180084864  call    FailoverDbGetConfiguration
0x180084869  inc     r15d
0x18008486c  mov     ebx, eax
0x18008486e  test    eax, eax
0x180084870  jnz     short loc_18008489D
0x180084872  mov     rdx, cs:FailoverConfTableHandle
0x180084879  mov     rcx, rdi
0x18008487c  call    DhcpDALJetNextRecord
0x180084881  test    eax, eax
0x180084883  jz      short loc_180084853
0x180084885  xor     edi, edi
0x180084887  cmp     eax, 103h
0x18008488c  mov     ebx, edi
0x18008488e  cmovnz  ebx, eax
0x180084891  test    ebx, ebx
0x180084893  jnz     short loc_18008489F
0x180084895  mov     r13, rsi
0x180084898  mov     r12d, r14d
0x18008489b  jmp     short loc_1800848C2
0x18008489d  xor     edi, edi
0x18008489f  mov     rcx, cs:gDhcpHeap; hHeap
0x1800848a6  mov     r8, rsi; lpMem
0x1800848a9  xor     edx, edx; dwFlags
0x1800848ab  call    cs:__imp_HeapFree
0x1800848b2  nop     dword ptr [rax+rax+00h]
0x1800848b7  test    ebx, ebx
0x1800848b9  jz      short loc_1800848C2
0x1800848bb  jmp     loc_180084E26
0x1800848c0  xor     edi, edi
0x1800848c2  call    DhcpFailoverReadRegKeyParams
0x1800848c7  mov     ebx, eax
0x1800848c9  test    eax, eax
0x1800848cb  jnz     loc_180084D20
0x1800848d1  test    r12d, r12d
0x1800848d4  jz      loc_180084E28
0x1800848da  call    DhcpFailoverBitmaskInit
0x1800848df  mov     ebx, eax
0x1800848e1  test    eax, eax
0x1800848e3  jz      short loc_1800848F7
0x1800848e5  mov     r9d, 4D2h
0x1800848eb  lea     r8, aDhcpfailoverbi; "DhcpFailoverBitmaskInit"
0x1800848f2  jmp     loc_180084D12
0x1800848f7  mov     rax, cs:g_FailoverEndpoints
0x1800848fe  test    rax, rax
0x180084901  jnz     short loc_180084911
0x180084903  lea     rcx, DhcpScopeFailState
0x18008490a  mov     cs:gFailStateCallback, rcx
0x180084911  cmp     cs:gAAUpdateBitMask, rdi
0x180084918  jnz     short loc_180084928
0x18008491a  lea     rcx, DhcpAAUpdateAckorAllocBitMasks
0x180084921  mov     cs:gAAUpdateBitMask, rcx
0x180084928  cmp     cs:gAAAllocateAddresses, rdi
0x18008492f  jnz     short loc_18008493F
0x180084931  lea     rcx, DhcpFailoverAddressAllocation
0x180084938  mov     cs:gAAAllocateAddresses, rcx
0x18008493f  lea     rcx, DhcpFailoverVerifyAddress
0x180084946  mov     cs:gVerifyAddress, rcx
0x18008494d  test    rax, rax
0x180084950  jnz     short loc_180084960
0x180084952  lea     rax, DhcpSetScopeStateToCommDown
0x180084959  mov     cs:gSetStateCommDownCallback, rax
0x180084960  mov     [rbp+arg_8], edi
0x180084963  mov     r15d, edi
0x180084966  test    r12d, r12d
0x180084969  jz      loc_180084D20
0x18008496f  lea     rsi, [r13+38h]
0x180084973  mov     edx, [rbp+arg_0]
0x180084976  mov     r8d, 1
0x18008497c  mov     eax, r15d
0x18008497f  lea     rax, [rax+rax*4]
0x180084983  shl     rax, 4
0x180084987  add     rax, r13
0x18008498a  mov     rcx, rax
0x18008498d  mov     [rbp+var_18], rax
0x180084991  call    DhcpFSMAddEndpoint
0x180084996  mov     ebx, eax
0x180084998  test    eax, eax
0x18008499a  jnz     loc_180084D20
0x1800849a0  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800849a7  call    cs:__imp_EnterCriticalSection
0x1800849ae  nop     dword ptr [rax+rax+00h]
0x1800849b3  mov     rdx, [rsi-18h]
0x1800849b7  lea     r8, [rbp+arg_10]
0x1800849bb  call    DhcpGetFailoverLastTime
0x1800849c0  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x1800849c7  mov     ebx, eax
0x1800849c9  call    cs:__imp_LeaveCriticalSection
0x1800849d0  nop     dword ptr [rax+rax+00h]
0x1800849d5  test    ebx, ebx
0x1800849d7  jnz     loc_180084D20
0x1800849dd  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800849e4  mov     r14d, [rbp+arg_10]
0x1800849e8  mov     rbx, [rsi-18h]
0x1800849ec  mov     qword ptr [rbp+var_28], rdi
0x1800849f0  mov     [rbp+arg_18], edi
0x1800849f3  call    cs:__imp_EnterCriticalSection
0x1800849fa  nop     dword ptr [rax+rax+00h]
0x1800849ff  lea     r8, [rbp+arg_18]
0x180084a03  mov     rcx, rbx
0x180084a06  lea     rdx, [rbp+var_28]
0x180084a0a  call    FSMGetElement
0x180084a0f  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x180084a16  mov     ebx, eax
0x180084a18  call    cs:__imp_LeaveCriticalSection
0x180084a1f  nop     dword ptr [rax+rax+00h]
0x180084a24  test    ebx, ebx
0x180084a26  jnz     loc_180084D20
0x180084a2c  mov     rbx, qword ptr [rbp+var_28]
0x180084a30  lea     rcx, [rbx+48h]; SRWLock
0x180084a34  call    cs:__imp_AcquireSRWLockExclusive
0x180084a3b  nop     dword ptr [rax+rax+00h]
0x180084a40  lea     rcx, [rbx+48h]; SRWLock
0x180084a44  mov     [rbx+8Ch], r14d
0x180084a4b  call    cs:__imp_ReleaseSRWLockExclusive
0x180084a52  nop     dword ptr [rax+rax+00h]
0x180084a57  mov     rcx, [rsi-18h]
0x180084a5b  lea     r8, [rbp+lpMem]
0x180084a5f  mov     edx, 1000h
0x180084a64  call    DhcpFSMGetEndpointParameter
0x180084a69  xor     edi, edi
0x180084a6b  mov     ebx, eax
0x180084a6d  test    eax, eax
0x180084a6f  jnz     loc_180084D20
0x180084a75  cmp     [rsi], rdi
0x180084a78  jz      loc_180084C30
0x180084a7e  lea     rcx, DhcpGlobalReadWriteLock
0x180084a85  call    RwLockAcquireForWrite
0x180084a8a  mov     rax, [rsi]
0x180084a8d  mov     r15d, edi
0x180084a90  mov     r14, [rbp+lpMem]
0x180084a94  cmp     [rax], edi
0x180084a96  jbe     loc_180084B9B
0x180084a9c  xor     r11d, r11d
0x180084a9f  mov     rax, [rax+8]
0x180084aa3  lea     r8, [rbp+var_38]
0x180084aa7  mov     rcx, cs:DhcpGlobalThisServer
0x180084aae  xor     r9d, r9d
0x180084ab1  mov     edi, r15d
0x180084ab4  mov     [rsp+68h+var_40], r11
0x180084ab9  mov     [rsp+68h+var_48], r11
0x180084abe  mov     edx, [rax+rdi*4]
0x180084ac1  mov     eax, edx
0x180084ac3  and     eax, 0F0000000h
0x180084ac8  cmp     eax, 0E0000000h
0x180084acd  jnz     short loc_180084AD6
0x180084acf  call    MemServerGetMAddressInfo
0x180084ad4  jmp     short loc_180084ADB
0x180084ad6  call    MemServerGetUAddressInfo
0x180084adb  xor     edx, edx
0x180084add  mov     ebx, eax
0x180084adf  test    eax, eax
0x180084ae1  jnz     loc_180084CB2
0x180084ae7  mov     rdi, [rbp+var_38]
0x180084aeb  mov     eax, edx
0x180084aed  mov     dword ptr [rdi+10C4h], 1
0x180084af7  cmp     [rsi-2Ch], edx
0x180084afa  setz    al
0x180084afd  mov     [rdi+10C8h], eax
0x180084b03  mov     eax, [rsi-20h]
0x180084b06  mov     [rdi+10D0h], eax
0x180084b0c  mov     eax, edx
0x180084b0e  cmp     [rsi-30h], edx
0x180084b11  setz    al
0x180084b14  mov     [rdi+10CCh], eax
0x180084b1a  movzx   eax, byte ptr [rsi+8]
0x180084b1e  mov     [rdi+10DCh], eax
0x180084b24  test    r14, r14
0x180084b27  jz      short loc_180084B40
0x180084b29  movups  xmm0, xmmword ptr [r14]
0x180084b2d  movups  xmmword ptr [rdi+10E0h], xmm0
0x180084b34  movups  xmm1, xmmword ptr [r14+10h]
0x180084b39  movups  xmmword ptr [rdi+10F0h], xmm1
0x180084b40  mov     rcx, [rsi-18h]
0x180084b44  or      rax, 0FFFFFFFFFFFFFFFFh
0x180084b48  inc     rax
0x180084b4b  cmp     [rcx+rax*2], dx
0x180084b4f  jnz     short loc_180084B48
0x180084b51  lea     eax, ds:2[rax*2]
0x180084b58  mov     ecx, eax; dwBytes
0x180084b5a  mov     ebx, eax
0x180084b5c  call    MemAlloc
0x180084b61  xor     r11d, r11d
0x180084b64  mov     [rdi+1100h], rax
0x180084b6b  test    rax, rax
0x180084b6e  jz      loc_180084CAB
0x180084b74  mov     r8, [rsi-18h]; pszSrc
0x180084b78  mov     edx, ebx; cbDest
0x180084b7a  mov     rcx, rax; pszDest
0x180084b7d  call    StringCbCopyW
0x180084b82  test    eax, eax
0x180084b84  js      loc_180084C91
0x180084b8a  mov     rax, [rsi]
0x180084b8d  inc     r15d
0x180084b90  cmp     r15d, [rax]
0x180084b93  jb      loc_180084A9F
0x180084b99  xor     edi, edi
0x180084b9b  lea     rcx, DhcpGlobalReadWriteLock
0x180084ba2  call    RwLockRelease
0x180084ba7  test    r14, r14
0x180084baa  jz      short loc_180084BC8
0x180084bac  mov     rcx, cs:gDhcpHeap; hHeap
0x180084bb3  mov     r8, r14; lpMem
0x180084bb6  xor     edx, edx; dwFlags
0x180084bb8  call    cs:__imp_HeapFree
0x180084bbf  nop     dword ptr [rax+rax+00h]
0x180084bc4  mov     [rbp+lpMem], rdi
0x180084bc8  cmp     [rbp+arg_0], 1
0x180084bcc  jnz     short loc_180084C2C
0x180084bce  mov     rax, [rsi]
0x180084bd1  mov     ebx, edi
0x180084bd3  cmp     [rax], edi
0x180084bd5  jbe     short loc_180084C2C
0x180084bd7  mov     rax, [rax+8]
0x180084bdb  lea     r8, [rbp+var_38]
0x180084bdf  mov     ecx, ebx
0x180084be1  xor     r9d, r9d
0x180084be4  mov     [rsp+68h+var_40], rdi
0x180084be9  mov     [rsp+68h+var_48], rdi
0x180084bee  mov     edx, [rax+rcx*4]
0x180084bf1  mov     eax, edx
0x180084bf3  mov     rcx, cs:DhcpGlobalThisServer
0x180084bfa  and     eax, 0F0000000h
0x180084bff  cmp     eax, 0E0000000h
0x180084c04  jnz     short loc_180084C0D
  ... truncated ...
```
