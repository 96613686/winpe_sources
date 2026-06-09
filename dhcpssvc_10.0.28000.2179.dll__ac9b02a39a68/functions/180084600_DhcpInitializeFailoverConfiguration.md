# DhcpInitializeFailoverConfiguration

- ea: `0x180084600`
- end: `0x180084cfa`
- name: `DhcpInitializeFailoverConfiguration`
- size: `1786`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config`

## callers

- `0x180025144`

## callees

- `0x1800058bc`
- `0x18001c45c`
- `0x1800247a0`
- `0x180024960`
- `0x18002dd48`
- `0x1800807a0`
- `0x180083ea8`
- `0x180084600`
- `0x18008ae7c`
- `0x180093144`
- `0x1800932a8`
- `0x180096254`
- `0x1800962b0`
- `0x18009e828`
- `0x18009ee38`
- `0x1800a0480`
- `0x1800a0758`
- `0x1800a0bac`
- `0x1800a1004`
- `0x1800a30f0`
- `0x1800a8850`
- `0x1800a8ca4`
- `0x1800a9f84`

## import_xrefs

- `ESENT!JetSetCurrentIndex` at `0x1800846b2`
- `ESENT!JetSetCurrentIndex` at `0x1800846b2`
- `ESENT!JetMove` at `0x1800846e1`
- `ESENT!JetMove` at `0x1800846e1`
- `WS2_32!__imp_htonl` at `0x180084b8d`
- `WS2_32!__imp_htonl` at `0x180084b8d`
- `KERNEL32!HeapAlloc` at `0x180084686`
- `KERNEL32!HeapAlloc` at `0x180084686`
- `KERNEL32!InitializeSRWLock` at `0x180084635`
- `KERNEL32!InitializeSRWLock` at `0x180084635`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800848f8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800848f8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800848e1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800848e1`
- `KERNEL32!EnterCriticalSection` at `0x180084852`
- `KERNEL32!EnterCriticalSection` at `0x1800848a0`
- `KERNEL32!EnterCriticalSection` at `0x180084852`
- `KERNEL32!EnterCriticalSection` at `0x1800848a0`
- `KERNEL32!LeaveCriticalSection` at `0x180084874`
- `KERNEL32!LeaveCriticalSection` at `0x1800848c5`
- `KERNEL32!LeaveCriticalSection` at `0x180084874`
- `KERNEL32!LeaveCriticalSection` at `0x1800848c5`
- `KERNEL32!HeapFree` at `0x180084779`
- `KERNEL32!HeapFree` at `0x180084a66`
- `KERNEL32!HeapFree` at `0x180084c17`
- `KERNEL32!HeapFree` at `0x180084c34`
- `KERNEL32!HeapFree` at `0x180084c52`
- `KERNEL32!HeapFree` at `0x180084c79`
- `KERNEL32!HeapFree` at `0x180084c92`
- `KERNEL32!HeapFree` at `0x180084cb0`
- `KERNEL32!HeapFree` at `0x180084cda`
- `KERNEL32!HeapFree` at `0x180084779`
- `KERNEL32!HeapFree` at `0x180084a66`
- `KERNEL32!HeapFree` at `0x180084c17`
- `KERNEL32!HeapFree` at `0x180084c34`
- `KERNEL32!HeapFree` at `0x180084c52`
- `KERNEL32!HeapFree` at `0x180084c79`
- `KERNEL32!HeapFree` at `0x180084c92`
- `KERNEL32!HeapFree` at `0x180084cb0`
- `KERNEL32!HeapFree` at `0x180084cda`

## string_xrefs

- `0x180084bd2`: `DhcpInitializeFailoverConfiguration`

## pseudocode

```c
LSTATUS DhcpInitializeFailoverConfiguration()
{
  InitializeSRWLock(&FailoverAPILock);
  if ( (unsigned int)DhcpDALJetElementsTotal(DhcpGlobalJetServerSession) )
    return 87;
  else
    return DhcpFailoverReadRegKeyParams();
}

```

## disassembly

```asm
0x180084600  mov     [rsp-40h+arg_0], ecx
0x180084604  push    rbp
0x180084605  push    rbx
0x180084606  push    rsi
0x180084607  push    rdi
0x180084608  push    r12
0x18008460a  push    r13
0x18008460c  push    r14
0x18008460e  push    r15
0x180084610  mov     rbp, rsp
0x180084613  sub     rsp, 58h
0x180084617  xor     r15d, r15d
0x18008461a  mov     ebx, ecx
0x18008461c  lea     rcx, FailoverAPILock; SRWLock
0x180084623  mov     [rbp+arg_10], r15d
0x180084627  mov     r13d, r15d
0x18008462a  mov     [rbp+lpMem], r15
0x18008462e  mov     r12d, r15d
0x180084631  mov     [rbp+var_28], r15
0x180084635  call    cs:__imp_InitializeSRWLock
0x18008463c  nop     dword ptr [rax+rax+00h]
0x180084641  mov     rdi, cs:DhcpGlobalJetServerSession
0x180084648  lea     r9, [rbp+arg_8]
0x18008464c  mov     rcx, rdi; sesid
0x18008464f  mov     [rbp+arg_8], r15d
0x180084653  call    DhcpDALJetElementsTotal
0x180084658  test    eax, eax
0x18008465a  jz      short loc_180084665
0x18008465c  lea     ebx, [r15+57h]
0x180084660  jmp     loc_180084789
0x180084665  mov     r14d, [rbp+arg_8]
0x180084669  test    r14d, r14d
0x18008466c  jz      loc_180084751
0x180084672  mov     rcx, cs:gDhcpHeap; hHeap
0x180084679  lea     r8, [r14+r14*4]
0x18008467d  shl     r8, 4; dwBytes
0x180084681  mov     edx, 8; dwFlags
0x180084686  call    cs:__imp_HeapAlloc
0x18008468d  nop     dword ptr [rax+rax+00h]
0x180084692  mov     rsi, rax
0x180084695  test    rax, rax
0x180084698  jnz     short loc_1800846A2
0x18008469a  lea     ebx, [rax+8]
0x18008469d  jmp     loc_180084789
0x1800846a2  mov     r15, cs:FailoverConfTableHandle
0x1800846a9  xor     r8d, r8d
0x1800846ac  mov     rdx, r15
0x1800846af  mov     rcx, rdi
0x1800846b2  call    cs:__imp_JetSetCurrentIndex
0x1800846b9  nop     dword ptr [rax+rax+00h]
0x1800846be  mov     ecx, eax
0x1800846c0  lea     rdx, aDhcpdaljetprep_0; "DhcpDALJetPrepareSearchEx"
0x1800846c7  call    DhcpDALMapJetError
0x1800846cc  mov     ebx, eax
0x1800846ce  test    eax, eax
0x1800846d0  jnz     short loc_1800846FD
0x1800846d2  xor     r9d, r9d; grbit
0x1800846d5  mov     r8d, 80000000h; cRow
0x1800846db  mov     rdx, r15; tableid
0x1800846de  mov     rcx, rdi; sesid
0x1800846e1  call    cs:__imp_JetMove
0x1800846e8  nop     dword ptr [rax+rax+00h]
0x1800846ed  mov     ecx, eax
0x1800846ef  lea     rdx, aDhcpdaljetprep_1; "DhcpDALJetPrepareSearchEx:MakeKey"
0x1800846f6  call    DhcpDALMapJetError
0x1800846fb  mov     ebx, eax
0x1800846fd  xor     r15d, r15d
0x180084700  test    ebx, ebx
0x180084702  jnz     short loc_18008476D
0x180084704  mov     eax, r15d
0x180084707  mov     rcx, rdi; sesid
0x18008470a  lea     rdx, [rax+rax*4]
0x18008470e  shl     rdx, 4
0x180084712  add     rdx, rsi
0x180084715  call    FailoverDbGetConfiguration
0x18008471a  inc     r15d
0x18008471d  mov     ebx, eax
0x18008471f  test    eax, eax
0x180084721  jnz     short loc_18008476A
0x180084723  mov     rdx, cs:FailoverConfTableHandle
0x18008472a  mov     rcx, rdi
0x18008472d  call    DhcpDALJetNextRecord
0x180084732  test    eax, eax
0x180084734  jz      short loc_180084704
0x180084736  xor     r15d, r15d
0x180084739  cmp     eax, 103h
0x18008473e  mov     ebx, r15d
0x180084741  cmovnz  ebx, eax
0x180084744  test    ebx, ebx
0x180084746  jnz     short loc_18008476D
0x180084748  mov     r13, rsi
0x18008474b  mov     r12d, r14d
0x18008474e  mov     ebx, [rbp+arg_0]
0x180084751  call    DhcpFailoverReadRegKeyParams
0x180084756  mov     edi, eax
0x180084758  test    eax, eax
0x18008475a  jnz     loc_180084BE0
0x180084760  test    r12d, r12d
0x180084763  jnz     short loc_180084790
0x180084765  jmp     loc_180084CE8
0x18008476a  xor     r15d, r15d
0x18008476d  mov     rcx, cs:gDhcpHeap; hHeap
0x180084774  mov     r8, rsi; lpMem
0x180084777  xor     edx, edx; dwFlags
0x180084779  call    cs:__imp_HeapFree
0x180084780  nop     dword ptr [rax+rax+00h]
0x180084785  test    ebx, ebx
0x180084787  jz      short loc_18008474E
0x180084789  mov     eax, ebx
0x18008478b  jmp     loc_180084CE8
0x180084790  call    DhcpFailoverBitmaskInit
0x180084795  mov     edi, eax
0x180084797  test    eax, eax
0x180084799  jz      short loc_1800847AD
0x18008479b  mov     r9d, 4D2h
0x1800847a1  lea     r8, aDhcpfailoverbi; "DhcpFailoverBitmaskInit"
0x1800847a8  jmp     loc_180084BD2
0x1800847ad  mov     rax, cs:g_FailoverEndpoints
0x1800847b4  test    rax, rax
0x1800847b7  jnz     short loc_1800847C7
0x1800847b9  lea     rcx, DhcpScopeFailState
0x1800847c0  mov     cs:gFailStateCallback, rcx
0x1800847c7  cmp     cs:gAAUpdateBitMask, r15
0x1800847ce  jnz     short loc_1800847DE
0x1800847d0  lea     rcx, DhcpAAUpdateAckorAllocBitMasks
0x1800847d7  mov     cs:gAAUpdateBitMask, rcx
0x1800847de  cmp     cs:gAAAllocateAddresses, r15
0x1800847e5  jnz     short loc_1800847F5
0x1800847e7  lea     rcx, DhcpFailoverAddressAllocation
0x1800847ee  mov     cs:gAAAllocateAddresses, rcx
0x1800847f5  lea     rcx, DhcpFailoverVerifyAddress
0x1800847fc  mov     cs:gVerifyAddress, rcx
0x180084803  test    rax, rax
0x180084806  jnz     short loc_180084816
0x180084808  lea     rax, DhcpSetScopeStateToCommDown
0x18008480f  mov     cs:gSetStateCommDownCallback, rax
0x180084816  mov     [rbp+arg_8], r15d
0x18008481a  test    r12d, r12d
0x18008481d  jz      loc_180084BE0
0x180084823  mov     eax, r15d
0x180084826  mov     r8d, 1
0x18008482c  mov     edx, ebx
0x18008482e  lea     rsi, [rax+rax*4]
0x180084832  shl     rsi, 4
0x180084836  add     rsi, r13
0x180084839  mov     rcx, rsi
0x18008483c  call    DhcpFSMAddEndpoint
0x180084841  mov     edi, eax
0x180084843  test    eax, eax
0x180084845  jnz     loc_180084BE0
0x18008484b  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180084852  call    cs:__imp_EnterCriticalSection
0x180084859  nop     dword ptr [rax+rax+00h]
0x18008485e  mov     rdx, [rsi+20h]
0x180084862  lea     r8, [rbp+arg_10]
0x180084866  call    DhcpGetFailoverLastTime
0x18008486b  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180084872  mov     edi, eax
0x180084874  call    cs:__imp_LeaveCriticalSection
0x18008487b  nop     dword ptr [rax+rax+00h]
0x180084880  xor     eax, eax
0x180084882  test    edi, edi
0x180084884  jnz     loc_180084BE0
0x18008488a  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x180084891  mov     r14d, [rbp+arg_10]
0x180084895  mov     rbx, [rsi+20h]
0x180084899  mov     qword ptr [rbp+var_18], rax
0x18008489d  mov     dword ptr [rbp+arg_18], eax
0x1800848a0  call    cs:__imp_EnterCriticalSection
0x1800848a7  nop     dword ptr [rax+rax+00h]
0x1800848ac  lea     r8, [rbp+arg_18]
0x1800848b0  mov     rcx, rbx
0x1800848b3  lea     rdx, [rbp+var_18]
0x1800848b7  call    FSMGetElement
0x1800848bc  mov     rcx, cs:g_FailoverEndpoints; lpCriticalSection
0x1800848c3  mov     edi, eax
0x1800848c5  call    cs:__imp_LeaveCriticalSection
0x1800848cc  nop     dword ptr [rax+rax+00h]
0x1800848d1  test    edi, edi
0x1800848d3  jnz     loc_180084BE0
0x1800848d9  mov     rbx, qword ptr [rbp+var_18]
0x1800848dd  lea     rcx, [rbx+48h]; SRWLock
0x1800848e1  call    cs:__imp_AcquireSRWLockExclusive
0x1800848e8  nop     dword ptr [rax+rax+00h]
0x1800848ed  lea     rcx, [rbx+48h]; SRWLock
0x1800848f1  mov     [rbx+8Ch], r14d
0x1800848f8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800848ff  nop     dword ptr [rax+rax+00h]
0x180084904  mov     rcx, [rsi+20h]
0x180084908  lea     r8, [rbp+lpMem]
0x18008490c  mov     edx, 1000h
0x180084911  call    DhcpFSMGetEndpointParameter
0x180084916  mov     edi, eax
0x180084918  test    eax, eax
0x18008491a  jnz     loc_180084BE0
0x180084920  xor     edi, edi
0x180084922  cmp     [rsi+38h], rdi
0x180084926  jz      loc_180084AE6
0x18008492c  lea     rcx, DhcpGlobalReadWriteLock
0x180084933  call    RwLockAcquireForWrite
0x180084938  mov     rax, [rsi+38h]
0x18008493c  mov     r15d, edi
0x18008493f  mov     r14, [rbp+lpMem]
0x180084943  cmp     [rax], edi
0x180084945  jbe     loc_180084A49
0x18008494b  mov     rax, [rax+8]
0x18008494f  lea     r8, [rbp+var_28]
0x180084953  mov     ecx, r15d
0x180084956  xor     r9d, r9d
0x180084959  mov     [rbp+arg_18], rcx
0x18008495d  mov     [rsp+58h+var_30], rdi
0x180084962  mov     [rsp+58h+var_38], rdi
0x180084967  mov     edx, [rax+rcx*4]
0x18008496a  mov     eax, edx
0x18008496c  mov     rcx, cs:DhcpGlobalThisServer
0x180084973  and     eax, 0F0000000h
0x180084978  cmp     eax, 0E0000000h
0x18008497d  jnz     short loc_180084986
0x18008497f  call    MemServerGetMAddressInfo
0x180084984  jmp     short loc_18008498B
0x180084986  call    MemServerGetUAddressInfo
0x18008498b  xor     edx, edx
0x18008498d  mov     edi, eax
0x18008498f  test    eax, eax
0x180084991  jnz     loc_180084B6E
0x180084997  mov     rbx, [rbp+var_28]
0x18008499b  mov     eax, edx
0x18008499d  mov     dword ptr [rbx+10C4h], 1
0x1800849a7  cmp     [rsi+0Ch], edx
0x1800849aa  setz    al
0x1800849ad  mov     [rbx+10C8h], eax
0x1800849b3  mov     eax, [rsi+18h]
0x1800849b6  mov     [rbx+10D0h], eax
0x1800849bc  mov     eax, edx
0x1800849be  cmp     [rsi+8], edx
0x1800849c1  setz    al
0x1800849c4  mov     [rbx+10CCh], eax
0x1800849ca  movzx   eax, byte ptr [rsi+40h]
0x1800849ce  mov     [rbx+10DCh], eax
0x1800849d4  test    r14, r14
0x1800849d7  jz      short loc_1800849F0
0x1800849d9  movups  xmm0, xmmword ptr [r14]
0x1800849dd  movups  xmmword ptr [rbx+10E0h], xmm0
0x1800849e4  movups  xmm1, xmmword ptr [r14+10h]
0x1800849e9  movups  xmmword ptr [rbx+10F0h], xmm1
0x1800849f0  mov     rcx, [rsi+20h]
0x1800849f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800849f8  inc     rax
0x1800849fb  cmp     [rcx+rax*2], dx
0x1800849ff  jnz     short loc_1800849F8
0x180084a01  lea     eax, ds:2[rax*2]
0x180084a08  mov     ecx, eax; dwBytes
0x180084a0a  mov     edi, eax
0x180084a0c  call    MemAlloc
0x180084a11  mov     [rbx+1100h], rax
0x180084a18  test    rax, rax
0x180084a1b  jz      loc_180084B67
0x180084a21  mov     r8, [rsi+20h]; pszSrc
0x180084a25  mov     edx, edi; cbDest
0x180084a27  mov     rcx, rax; pszDest
0x180084a2a  call    StringCbCopyW
0x180084a2f  xor     edi, edi
0x180084a31  test    eax, eax
0x180084a33  js      loc_180084B4C
0x180084a39  mov     rax, [rsi+38h]
0x180084a3d  inc     r15d
0x180084a40  cmp     r15d, [rax]
0x180084a43  jb      loc_18008494B
0x180084a49  lea     rcx, DhcpGlobalReadWriteLock
0x180084a50  call    RwLockRelease
0x180084a55  test    r14, r14
0x180084a58  jz      short loc_180084A76
0x180084a5a  mov     rcx, cs:gDhcpHeap; hHeap
0x180084a61  mov     r8, r14; lpMem
0x180084a64  xor     edx, edx; dwFlags
0x180084a66  call    cs:__imp_HeapFree
0x180084a6d  nop     dword ptr [rax+rax+00h]
0x180084a72  mov     [rbp+lpMem], rdi
0x180084a76  mov     ebx, [rbp+arg_0]
0x180084a79  cmp     ebx, 1
0x180084a7c  jnz     loc_180084B46
0x180084a82  mov     rax, [rsi+38h]
0x180084a86  mov     ebx, edi
0x180084a88  cmp     [rax], edi
0x180084a8a  jbe     short loc_180084AE2
0x180084a8c  mov     rax, [rax+8]
0x180084a90  lea     r8, [rbp+var_28]
0x180084a94  mov     ecx, ebx
0x180084a96  xor     r9d, r9d
0x180084a99  mov     [rsp+58h+var_30], rdi
0x180084a9e  mov     [rsp+58h+var_38], rdi
0x180084aa3  mov     edx, [rax+rcx*4]
0x180084aa6  mov     eax, edx
0x180084aa8  mov     rcx, cs:DhcpGlobalThisServer
0x180084aaf  and     eax, 0F0000000h
0x180084ab4  cmp     eax, 0E0000000h
0x180084ab9  jnz     short loc_180084AC2
0x180084abb  call    MemServerGetMAddressInfo
0x180084ac0  jmp     short loc_180084AC7
0x180084ac2  call    MemServerGetUAddressInfo
  ... truncated ...
```
