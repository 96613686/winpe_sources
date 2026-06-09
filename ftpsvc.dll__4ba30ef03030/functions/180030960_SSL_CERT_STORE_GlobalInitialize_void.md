# SSL_CERT_STORE::GlobalInitialize(void)

- ea: `0x180030960`
- end: `0x180030b0f`
- name: `?GlobalInitialize@SSL_CERT_STORE@@SAJXZ`
- size: `431`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002f540`

## callees

- `0x180001210`
- `0x180001250`
- `0x180030960`
- `0x180030b18`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800309b3`
- `KERNEL32!CreateEventW` at `0x1800309b3`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180030987`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180030987`
- `KERNEL32!CreateThread` at `0x180030ac9`
- `KERNEL32!CreateThread` at `0x180030ac9`
- `KERNEL32!GetLastError` at `0x180030adb`
- `KERNEL32!GetLastError` at `0x180030adb`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x180030a5a`
- `iisutil!?IsValid@CLKRHashTable@@QEBA_NXZ` at `0x180030a5a`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180030a3d`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x180030a3d`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180030a73`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x180030a73`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 SSL_CERT_STORE::GlobalInitialize(void)
{
  CLKRHashTable *v0; // rbx
  void *v1; // rbx
  unsigned int v2; // ebx
  signed int LastError; // eax

  qword_180061490 = (__int64)&SSL_CERT_STORE::sm_ToBeDeletedListHead;
  SSL_CERT_STORE::sm_ToBeDeletedListHead.Flink = &SSL_CERT_STORE::sm_ToBeDeletedListHead;
  if ( InitializeCriticalSectionAndSpinCount(&SSL_CERT_STORE::sm_csToBeDeletedList, 0x800003E8) )
  {
    SSL_CERT_STORE::sm_fInitcsToBeDeletedList = 1;
    SSL_CERT_STORE::sm_InitStatus = 1;
    SSL_CERT_STORE::sm_hWakeupEvent = CreateEventW(0, 0, 0, 0);
    if ( SSL_CERT_STORE::sm_hWakeupEvent )
    {
      SSL_CERT_STORE::sm_InitStatus = 2;
      v0 = (CLKRHashTable *)operator new(0x48u);
      if ( v0 )
        CLKRHashTable::CLKRHashTable(
          v0,
          "SSL_CERT_STORE_TABLE",
          (unsigned __int64 (*)(const void *))CTypedHashTable<SSL_CERT_STORE_TABLE,SSL_CERT_STORE,unsigned short const *,CLKRHashTable>::_ExtractKey,
          (unsigned int (*)(unsigned __int64))CTypedHashTable<SSL_CERT_STORE_TABLE,SSL_CERT_STORE,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
          (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<SSL_CERT_STORE_TABLE,SSL_CERT_STORE,unsigned short const *,CLKRHashTable>::_EqualKeys,
          (void (*)(const void *, int))CTypedHashTable<SSL_CERT_STORE_TABLE,SSL_CERT_STORE,unsigned short const *,CLKRHashTable>::_AddRefRecord,
          4.0,
          1u,
          0,
          0);
      else
        v0 = 0;
      SSL_CERT_STORE::sm_pCertStoreTable = v0;
      if ( v0 )
      {
        if ( !CLKRHashTable::IsValid(v0) )
        {
          v1 = SSL_CERT_STORE::sm_pCertStoreTable;
          if ( SSL_CERT_STORE::sm_pCertStoreTable )
          {
            CLKRHashTable::~CLKRHashTable((CLKRHashTable *)SSL_CERT_STORE::sm_pCertStoreTable);
            operator delete(v1);
          }
          SSL_CERT_STORE::sm_pCertStoreTable = 0;
          v2 = -2147024888;
LABEL_15:
          SSL_CERT_STORE::GlobalTerminate();
          return v2;
        }
        SSL_CERT_STORE::sm_InitStatus = 3;
        SSL_CERT_STORE::sm_fDeletionThreadShutdown = 0;
        SSL_CERT_STORE::sm_hDeletionThread = CreateThread(
                                               0,
                                               0x3E80u,
                                               (LPTHREAD_START_ROUTINE)SSL_CERT_STORE::DeletionWorkerThread,
                                               0,
                                               0,
                                               0);
        if ( SSL_CERT_STORE::sm_hDeletionThread )
        {
          SSL_CERT_STORE::sm_InitStatus = 4;
          return 0;
        }
      }
    }
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( (v2 & 0x80000000) != 0 )
    goto LABEL_15;
  return v2;
}

```

## disassembly

```asm
0x180030960  push    rbx
0x180030962  sub     rsp, 50h
0x180030966  lea     rax, ?sm_ToBeDeletedListHead@SSL_CERT_STORE@@0U_LIST_ENTRY@@A; _LIST_ENTRY SSL_CERT_STORE::sm_ToBeDeletedListHead
0x18003096d  mov     cs:qword_180061490, rax
0x180030974  mov     cs:?sm_ToBeDeletedListHead@SSL_CERT_STORE@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY SSL_CERT_STORE::sm_ToBeDeletedListHead
0x18003097b  mov     edx, 800003E8h; dwSpinCount
0x180030980  lea     rcx, ?sm_csToBeDeletedList@SSL_CERT_STORE@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180030987  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003098d  test    eax, eax
0x18003098f  jz      loc_180030ADB
0x180030995  mov     cs:?sm_fInitcsToBeDeletedList@SSL_CERT_STORE@@0HA, 1; int SSL_CERT_STORE::sm_fInitcsToBeDeletedList
0x18003099f  mov     cs:?sm_InitStatus@SSL_CERT_STORE@@0W4INIT_STATUS@1@A, 1; SSL_CERT_STORE::INIT_STATUS SSL_CERT_STORE::sm_InitStatus
0x1800309a9  xor     r9d, r9d; lpName
0x1800309ac  xor     r8d, r8d; bInitialState
0x1800309af  xor     edx, edx; bManualReset
0x1800309b1  xor     ecx, ecx; lpEventAttributes
0x1800309b3  call    cs:__imp_CreateEventW
0x1800309b9  mov     cs:?sm_hWakeupEvent@SSL_CERT_STORE@@0PEAXEA, rax; void * SSL_CERT_STORE::sm_hWakeupEvent
0x1800309c0  test    rax, rax
0x1800309c3  jz      loc_180030ADB
0x1800309c9  mov     cs:?sm_InitStatus@SSL_CERT_STORE@@0W4INIT_STATUS@1@A, 2; SSL_CERT_STORE::INIT_STATUS SSL_CERT_STORE::sm_InitStatus
0x1800309d3  mov     ecx, 48h ; 'H'; Size
0x1800309d8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800309dd  mov     rbx, rax
0x1800309e0  mov     [rsp+58h+arg_0], rax
0x1800309e5  test    rax, rax
0x1800309e8  jz      short loc_180030A45
0x1800309ea  mov     [rsp+58h+var_10], 0
0x1800309ef  mov     [rsp+58h+var_18], 0
0x1800309f7  mov     [rsp+58h+var_20], 1
0x1800309ff  movsd   xmm0, cs:__real@4010000000000000
0x180030a07  movsd   [rsp+58h+var_28], xmm0
0x180030a0d  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VSSL_CERT_STORE_TABLE@@VSSL_CERT_STORE@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<SSL_CERT_STORE_TABLE,SSL_CERT_STORE,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x180030a14  mov     [rsp+58h+lpThreadId], rax
0x180030a19  lea     rax, ?_EqualKeys@?$CTypedHashTable@VSSL_CERT_STORE_TABLE@@VSSL_CERT_STORE@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<SSL_CERT_STORE_TABLE,SSL_CERT_STORE,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x180030a20  mov     qword ptr [rsp+58h+dwCreationFlags], rax
0x180030a25  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VSSL_CERT_STORE_TABLE@@VSSL_CERT_STORE@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<SSL_CERT_STORE_TABLE,SSL_CERT_STORE,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x180030a2c  lea     r8, ?_ExtractKey@?$CTypedHashTable@VSSL_CERT_STORE_TABLE@@VSSL_CERT_STORE@@PEBGVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<SSL_CERT_STORE_TABLE,SSL_CERT_STORE,ushort const *,CLKRHashTable>::_ExtractKey(void const *)
0x180030a33  lea     rdx, aSslCertStoreTa; "SSL_CERT_STORE_TABLE"
0x180030a3a  mov     rcx, rbx
0x180030a3d  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x180030a43  jmp     short loc_180030A47
0x180030a45  xor     ebx, ebx
0x180030a47  mov     cs:?sm_pCertStoreTable@SSL_CERT_STORE@@0PEAVSSL_CERT_STORE_TABLE@@EA, rbx; SSL_CERT_STORE_TABLE * SSL_CERT_STORE::sm_pCertStoreTable
0x180030a4e  test    rbx, rbx
0x180030a51  jz      loc_180030ADB
0x180030a57  mov     rcx, rbx
0x180030a5a  call    cs:__imp_?IsValid@CLKRHashTable@@QEBA_NXZ; CLKRHashTable::IsValid(void)
0x180030a60  test    al, al
0x180030a62  jnz     short loc_180030A93
0x180030a64  mov     rbx, cs:?sm_pCertStoreTable@SSL_CERT_STORE@@0PEAVSSL_CERT_STORE_TABLE@@EA; SSL_CERT_STORE_TABLE * SSL_CERT_STORE::sm_pCertStoreTable
0x180030a6b  test    rbx, rbx
0x180030a6e  jz      short loc_180030A81
0x180030a70  mov     rcx, rbx
0x180030a73  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x180030a79  mov     rcx, rbx; Block
0x180030a7c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180030a81  mov     cs:?sm_pCertStoreTable@SSL_CERT_STORE@@0PEAVSSL_CERT_STORE_TABLE@@EA, 0; SSL_CERT_STORE_TABLE * SSL_CERT_STORE::sm_pCertStoreTable
0x180030a8c  mov     ebx, 80070008h
0x180030a91  jmp     short loc_180030AF4
0x180030a93  mov     cs:?sm_InitStatus@SSL_CERT_STORE@@0W4INIT_STATUS@1@A, 3; SSL_CERT_STORE::INIT_STATUS SSL_CERT_STORE::sm_InitStatus
0x180030a9d  mov     cs:?sm_fDeletionThreadShutdown@SSL_CERT_STORE@@0HA, 0; int SSL_CERT_STORE::sm_fDeletionThreadShutdown
0x180030aa7  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x180030ab0  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x180030ab8  xor     r9d, r9d; lpParameter
0x180030abb  lea     r8, ?DeletionWorkerThread@SSL_CERT_STORE@@SAKPEAX@Z; lpStartAddress
0x180030ac2  mov     edx, 3E80h; dwStackSize
0x180030ac7  xor     ecx, ecx; lpThreadAttributes
0x180030ac9  call    cs:__imp_CreateThread
0x180030acf  mov     cs:?sm_hDeletionThread@SSL_CERT_STORE@@0PEAXEA, rax; void * SSL_CERT_STORE::sm_hDeletionThread
0x180030ad6  test    rax, rax
0x180030ad9  jnz     short loc_180030AFB
0x180030adb  call    cs:__imp_GetLastError
0x180030ae1  test    eax, eax
0x180030ae3  mov     ebx, eax
0x180030ae5  jle     short loc_180030AF0
0x180030ae7  movzx   ebx, ax
0x180030aea  or      ebx, 80070000h
0x180030af0  test    ebx, ebx
0x180030af2  jns     short loc_180030B07
0x180030af4  call    ?GlobalTerminate@SSL_CERT_STORE@@SAXXZ; SSL_CERT_STORE::GlobalTerminate(void)
0x180030af9  jmp     short loc_180030B07
0x180030afb  mov     cs:?sm_InitStatus@SSL_CERT_STORE@@0W4INIT_STATUS@1@A, 4; SSL_CERT_STORE::INIT_STATUS SSL_CERT_STORE::sm_InitStatus
0x180030b05  xor     ebx, ebx
0x180030b07  mov     eax, ebx
0x180030b09  add     rsp, 50h
0x180030b0d  pop     rbx
0x180030b0e  retn
```
