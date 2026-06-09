# CMachineSettings::OnChangedReplicationSharePath(RSTableMetaEntry *,int,void *,void * *)

- ea: `0x180035a90`
- end: `0x180035c1e`
- name: `?OnChangedReplicationSharePath@CMachineSettings@@QEAAJPEAURSTableMetaEntry@@HPEAXPEAPEAX@Z`
- size: `398`
- prototype: `int(CMachineSettings *__hidden this, struct RSTableMetaEntry *, int, void *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180001e60`
- `0x1800352e4`
- `0x180035a90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035bad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035bd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035bad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035bd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035b05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035bbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035b05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035bbb`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180035b1b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180035b1b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180035be1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180035be1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035c04`
- `MPR!WNetGetUniversalNameW` at `0x180035b49`
- `MPR!WNetGetUniversalNameW` at `0x180035b49`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMachineSettings::OnChangedReplicationSharePath(
        CTmpMemoryCache **this,
        struct RSTableMetaEntry *a2,
        int a3,
        const WCHAR *a4,
        void **a5)
{
  unsigned int v7; // ebx
  void **v8; // r15
  unsigned __int64 v9; // rax
  const unsigned __int16 **v10; // rdi
  HRESULT v11; // r14d
  int v12; // esi
  DWORD UniversalNameW; // eax
  __int64 v14; // rsi
  unsigned __int16 *v15; // rax
  __int64 result; // rax
  DWORD BufferSize; // [rsp+80h] [rbp+18h] BYREF

  v7 = 0;
  v8 = a5;
  *a5 = 0;
  if ( !a3 )
  {
    if ( a4 )
    {
      v9 = -1;
      do
        ++v9;
      while ( a4[v9] );
      if ( v9 >= 2 && *a4 != 92 && a4[1] != 92 )
      {
        BufferSize = 546;
        v10 = (const unsigned __int16 **)CoTaskMemAlloc(0x222u);
        v7 = v10 == 0 ? 0x8007000E : 0;
        v11 = CoImpersonateClient();
        if ( v10 )
        {
          v12 = 0;
          while ( 1 )
          {
            while ( 1 )
            {
              if ( v12 )
                goto LABEL_21;
              UniversalNameW = WNetGetUniversalNameW(a4, 2u, v10, &BufferSize);
              if ( UniversalNameW )
                break;
              v14 = -1;
              do
                ++v14;
              while ( (*v10)[v14] );
              if ( v14 )
              {
                v15 = (unsigned __int16 *)CTmpMemoryCache::AllocBlock(this[36], 2 * v14 + 2);
                *v8 = v15;
                if ( v15 )
                  v7 = StringCchCopyW(v15, v14 + 1, *v10);
                else
                  v7 = -2147024882;
              }
LABEL_27:
              v12 = 1;
            }
            if ( UniversalNameW != 234 )
            {
              GetLastError();
              v7 = -2147418113;
              goto LABEL_27;
            }
            CoTaskMemFree(v10);
            v10 = (const unsigned __int16 **)CoTaskMemAlloc(BufferSize);
            if ( !v10 )
            {
              v7 = -2147024882;
              break;
            }
          }
        }
LABEL_21:
        CoTaskMemFree(v10);
        if ( !v11 )
          CoRevertToSelf();
      }
    }
  }
  result = 0;
  if ( v7 == -2147024882 )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x180035a90  push    rbx
0x180035a92  push    rbp
0x180035a93  push    rsi
0x180035a94  push    rdi
0x180035a95  push    r12
0x180035a97  push    r13
0x180035a99  push    r14
0x180035a9b  push    r15
0x180035a9d  sub     rsp, 28h
0x180035aa1  mov     rbp, r9
0x180035aa4  mov     r13, rcx
0x180035aa7  xor     r12d, r12d
0x180035aaa  mov     ebx, r12d
0x180035aad  mov     r15, [rsp+68h+arg_20]
0x180035ab5  mov     [r15], r12
0x180035ab8  test    r8d, r8d
0x180035abb  jnz     loc_180035BE7
0x180035ac1  test    r9, r9
0x180035ac4  jz      loc_180035BE7
0x180035aca  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035ace  inc     rax
0x180035ad1  cmp     [r9+rax*2], r12w
0x180035ad6  jnz     short loc_180035ACE
0x180035ad8  cmp     rax, 2
0x180035adc  jb      loc_180035BE7
0x180035ae2  cmp     word ptr [r9], 5Ch ; '\'
0x180035ae7  jz      loc_180035BE7
0x180035aed  cmp     word ptr [r9+2], 5Ch ; '\'
0x180035af3  jz      loc_180035BE7
0x180035af9  mov     ecx, 222h; cb
0x180035afe  mov     [rsp+68h+BufferSize], ecx
0x180035b05  call    cs:__imp_CoTaskMemAlloc
0x180035b0b  mov     rdi, rax
0x180035b0e  neg     rax
0x180035b11  sbb     ebx, ebx
0x180035b13  not     ebx
0x180035b15  and     ebx, 8007000Eh
0x180035b1b  call    cs:__imp_CoImpersonateClient
0x180035b21  mov     r14d, eax
0x180035b24  test    rdi, rdi
0x180035b27  jz      loc_180035BD2
0x180035b2d  mov     esi, r12d
0x180035b30  test    esi, esi
0x180035b32  jnz     loc_180035BD2
0x180035b38  lea     r9, [rsp+68h+BufferSize]; lpBufferSize
0x180035b40  mov     r8, rdi; lpBuffer
0x180035b43  lea     edx, [rsi+2]; dwInfoLevel
0x180035b46  mov     rcx, rbp; lpLocalPath
0x180035b49  call    cs:__imp_WNetGetUniversalNameW
0x180035b4f  test    eax, eax
0x180035b51  jnz     short loc_180035BA3
0x180035b53  mov     rax, [rdi]
0x180035b56  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180035b5a  inc     rsi
0x180035b5d  cmp     [rax+rsi*2], r12w
0x180035b62  jnz     short loc_180035B5A
0x180035b64  test    rsi, rsi
0x180035b67  jz      loc_180035C14
0x180035b6d  lea     rdx, ds:2[rsi*2]; unsigned __int64
0x180035b75  mov     rcx, [r13+120h]; this
0x180035b7c  call    ?AllocBlock@CTmpMemoryCache@@QEAAPEAX_K@Z; CTmpMemoryCache::AllocBlock(unsigned __int64)
0x180035b81  mov     [r15], rax
0x180035b84  test    rax, rax
0x180035b87  jz      short loc_180035B9C
0x180035b89  lea     rdx, [rsi+1]; unsigned __int64
0x180035b8d  mov     r8, [rdi]; unsigned __int16 *
0x180035b90  mov     rcx, rax; unsigned __int16 *
0x180035b93  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035b98  mov     ebx, eax
0x180035b9a  jmp     short loc_180035C14
0x180035b9c  mov     ebx, 8007000Eh
0x180035ba1  jmp     short loc_180035C14
0x180035ba3  cmp     eax, 0EAh
0x180035ba8  jnz     short loc_180035C04
0x180035baa  mov     rcx, rdi; pv
0x180035bad  call    cs:__imp_CoTaskMemFree
0x180035bb3  nop
0x180035bb4  mov     ecx, [rsp+68h+BufferSize]; cb
0x180035bbb  call    cs:__imp_CoTaskMemAlloc
0x180035bc1  mov     rdi, rax
0x180035bc4  test    rax, rax
0x180035bc7  jnz     loc_180035B30
0x180035bcd  mov     ebx, 8007000Eh
0x180035bd2  mov     rcx, rdi; pv
0x180035bd5  call    cs:__imp_CoTaskMemFree
0x180035bdb  nop
0x180035bdc  test    r14d, r14d
0x180035bdf  jnz     short loc_180035BE7
0x180035be1  call    cs:__imp_CoRevertToSelf
0x180035be7  mov     eax, r12d
0x180035bea  cmp     ebx, 8007000Eh
0x180035bf0  cmovz   eax, ebx
0x180035bf3  add     rsp, 28h
0x180035bf7  pop     r15
0x180035bf9  pop     r14
0x180035bfb  pop     r13
0x180035bfd  pop     r12
0x180035bff  pop     rdi
0x180035c00  pop     rsi
0x180035c01  pop     rbp
0x180035c02  pop     rbx
0x180035c03  retn
0x180035c04  call    cs:__imp_GetLastError
0x180035c0a  mov     ebx, 8000FFFFh
0x180035c0f  test    rdi, rdi
0x180035c12  jz      short loc_180035BD2
0x180035c14  mov     esi, 1
0x180035c19  jmp     loc_180035B30
```
