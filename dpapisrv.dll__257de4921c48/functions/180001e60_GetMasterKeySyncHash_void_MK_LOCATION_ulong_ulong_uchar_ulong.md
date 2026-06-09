# GetMasterKeySyncHash(void *,_MK_LOCATION *,ulong,ulong,uchar *,ulong)

- ea: `0x180001e60`
- end: `0x180001fe7`
- name: `?GetMasterKeySyncHash@@YAKPEAXPEAU_MK_LOCATION@@KKPEAEK@Z`
- size: `391`
- prototype: `__int64 __fastcall(void *, struct _MK_LOCATION *, unsigned int, unsigned int, unsigned __int8 *pbOutput)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008c3c`
- `0x180039d90`

## callees

- `0x180001e60`
- `0x180001ff0`
- `0x1800029d0`
- `0x180007f10`
- `0x18001c998`
- `0x18001eb8c`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x180001fb0`
- `bcrypt!BCryptFinishHash` at `0x180001fb0`
- `bcrypt!BCryptDestroyHash` at `0x180001f8e`
- `bcrypt!BCryptDestroyHash` at `0x180001f8e`
- `bcrypt!BCryptCreateHash` at `0x180001ec8`
- `bcrypt!BCryptCreateHash` at `0x180001ec8`
- `ntdll!RtlNtStatusToDosError` at `0x180001ef7`
- `ntdll!RtlNtStatusToDosError` at `0x180001ef7`

## string_xrefs

- `0x180001ee0`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysync.cpp`
- `0x180001f5c`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysync.cpp`

## pseudocode

```c
__int64 __fastcall GetMasterKeySyncHash(
        void *a1,
        struct _MK_LOCATION *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *pbOutput)
{
  void *BCryptProviderHandle; // rax
  ULONG v9; // ebx
  int v10; // edx
  int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rdi
  unsigned int v14; // eax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-38h] BYREF
  BCRYPT_HASH_HANDLE *p_phHash; // [rsp+48h] [rbp-30h] BYREF

  phHash = 0;
  p_phHash = &phHash;
  BCryptProviderHandle = (void *)GetBCryptProviderHandle(a4);
  if ( !BCryptProviderHandle )
  {
    v9 = 87;
LABEL_18:
    ScopedBCryptHashFree::~ScopedBCryptHashFree((ScopedBCryptHashFree *)&p_phHash);
    return v9;
  }
  v11 = BCryptCreateHash(BCryptProviderHandle, &phHash, 0, 0, 0, 0, 0);
  if ( v11 < 0 )
  {
    v12 = 901;
LABEL_5:
    DebugTraceError(
      (unsigned int)v11,
      "ntStatus",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp",
      v12);
    v9 = RtlNtStatusToDosError(v11);
    goto LABEL_18;
  }
  v9 = 0;
  v13 = 0;
  if ( !a3 )
  {
LABEL_15:
    v11 = BCryptFinishHash(phHash, pbOutput, 0x40u, 0);
    if ( v11 >= 0 )
    {
      v9 = 0;
      goto LABEL_18;
    }
    v12 = 923;
    goto LABEL_5;
  }
  while ( !v9 )
  {
    v14 = HashMasterKeyFile(a1, (struct _MK_LOCATION *)((char *)a2 + 24 * v13), phHash);
    v9 = v14;
    v13 = (unsigned int)(v13 + 1);
    if ( (unsigned int)v13 >= a3 )
    {
      if ( !v14 )
        goto LABEL_15;
      break;
    }
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_sDsd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      v10,
      (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
      (unsigned int)"dwLastError",
      v9,
      (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp",
      148);
  if ( phHash )
    BCryptDestroyHash(phHash);
  return v9;
}

```

## disassembly

```asm
0x180001e60  push    rbx
0x180001e62  push    rbp
0x180001e63  push    rsi
0x180001e64  push    rdi
0x180001e65  push    r14
0x180001e67  sub     rsp, 50h
0x180001e6b  mov     esi, r8d
0x180001e6e  mov     r14, rdx
0x180001e71  mov     rbp, rcx
0x180001e74  mov     [rsp+78h+phHash], 0
0x180001e7d  lea     rax, [rsp+78h+phHash]
0x180001e82  mov     [rsp+78h+var_30], rax
0x180001e87  xor     r8d, r8d
0x180001e8a  xor     edx, edx
0x180001e8c  mov     ecx, r9d; unsigned int
0x180001e8f  call    GetBCryptProviderHandle
0x180001e94  test    rax, rax
0x180001e97  jnz     short loc_180001EA1
0x180001e99  lea     ebx, [rax+57h]
0x180001e9c  jmp     loc_180001FCF
0x180001ea1  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180001ea9  mov     [rsp+78h+cbSecret], 0; cbSecret
0x180001eb1  mov     [rsp+78h+pbSecret], 0; pbSecret
0x180001eba  xor     r9d, r9d; cbHashObject
0x180001ebd  xor     r8d, r8d; pbHashObject
0x180001ec0  lea     rdx, [rsp+78h+phHash]; phHash
0x180001ec5  mov     rcx, rax; hAlgorithm
0x180001ec8  call    cs:__imp_BCryptCreateHash
0x180001ecf  nop     dword ptr [rax+rax+00h]
0x180001ed4  mov     ebx, eax
0x180001ed6  test    eax, eax
0x180001ed8  jns     short loc_180001F0A
0x180001eda  mov     r9d, 385h
0x180001ee0  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180001ee7  lea     rdx, aNtstatus; "ntStatus"
0x180001eee  mov     ecx, ebx
0x180001ef0  call    DebugTraceError
0x180001ef5  mov     ecx, ebx; Status
0x180001ef7  call    cs:__imp_RtlNtStatusToDosError
0x180001efe  nop     dword ptr [rax+rax+00h]
0x180001f03  mov     ebx, eax
0x180001f05  jmp     loc_180001FCF
0x180001f0a  xor     ebx, ebx
0x180001f0c  xor     edi, edi
0x180001f0e  test    esi, esi
0x180001f10  jz      loc_180001F9C
0x180001f16  test    ebx, ebx
0x180001f18  jnz     short loc_180001F3B
0x180001f1a  lea     rcx, [rdi+rdi*2]
0x180001f1e  lea     rdx, [r14+rcx*8]; struct _MK_LOCATION *
0x180001f22  mov     r8, [rsp+78h+phHash]; void *
0x180001f27  mov     rcx, rbp; void *
0x180001f2a  call    ?HashMasterKeyFile@@YAKPEAXPEAU_MK_LOCATION@@0@Z; HashMasterKeyFile(void *,_MK_LOCATION *,void *)
0x180001f2f  mov     ebx, eax
0x180001f31  inc     edi
0x180001f33  cmp     edi, esi
0x180001f35  jb      short loc_180001F16
0x180001f37  test    eax, eax
0x180001f39  jz      short loc_180001F9C
0x180001f3b  lea     rax, WPP_GLOBAL_Control
0x180001f42  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f49  cmp     rcx, rax
0x180001f4c  jz      short loc_180001F84
0x180001f4e  test    byte ptr [rcx+1Ch], 1
0x180001f52  jz      short loc_180001F84
0x180001f54  mov     [rsp+78h+dwFlags], 394h
0x180001f5c  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180001f63  mov     qword ptr [rsp+78h+cbSecret], r8
0x180001f68  mov     dword ptr [rsp+78h+pbSecret], ebx
0x180001f6c  lea     r9, aDwlasterror; "dwLastError"
0x180001f73  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180001f7a  mov     rcx, [rcx+10h]
0x180001f7e  call    WPP_SF_sDsd
0x180001f83  nop
0x180001f84  mov     rcx, [rsp+78h+phHash]; hHash
0x180001f89  test    rcx, rcx
0x180001f8c  jz      short loc_180001FD9
0x180001f8e  call    cs:__imp_BCryptDestroyHash
0x180001f95  nop     dword ptr [rax+rax+00h]
0x180001f9a  jmp     short loc_180001FD9
0x180001f9c  xor     r9d, r9d; dwFlags
0x180001f9f  lea     r8d, [r9+40h]; cbOutput
0x180001fa3  mov     rdx, [rsp+78h+pbOutput]; pbOutput
0x180001fab  mov     rcx, [rsp+78h+phHash]; hHash
0x180001fb0  call    cs:__imp_BCryptFinishHash
0x180001fb7  nop     dword ptr [rax+rax+00h]
0x180001fbc  mov     ebx, eax
0x180001fbe  test    eax, eax
0x180001fc0  jns     short loc_180001FCD
0x180001fc2  mov     r9d, 39Bh
0x180001fc8  jmp     loc_180001EE0
0x180001fcd  xor     ebx, ebx
0x180001fcf  lea     rcx, [rsp+78h+var_30]; this
0x180001fd4  call    ??1ScopedBCryptHashFree@@QEAA@XZ; ScopedBCryptHashFree::~ScopedBCryptHashFree(void)
0x180001fd9  mov     eax, ebx
0x180001fdb  add     rsp, 50h
0x180001fdf  pop     r14
0x180001fe1  pop     rdi
0x180001fe2  pop     rsi
0x180001fe3  pop     rbp
0x180001fe4  pop     rbx
0x180001fe5  retn
```
