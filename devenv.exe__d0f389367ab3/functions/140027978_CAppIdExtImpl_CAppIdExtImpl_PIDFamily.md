# CAppIdExtImpl::CAppIdExtImpl(PIDFamily)

- ea: `0x140027978`
- end: `0x140027c1e`
- name: `??0CAppIdExtImpl@@QEAA@W4PIDFamily@@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140027718`

## callees

- `0x140001020`
- `0x140001040`
- `0x140002c10`
- `0x140002f00`
- `0x140027978`
- `0x140027c20`
- `0x140033ab0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140027bdd`
- `ADVAPI32!RegCloseKey` at `0x140027bdd`
- `ADVAPI32!RegOpenKeyExW` at `0x140027b61`
- `ADVAPI32!RegOpenKeyExW` at `0x140027b61`
- `KERNEL32!GetCurrentThreadId` at `0x140027af2`
- `KERNEL32!GetCurrentThreadId` at `0x140027af2`

## string_xrefs

- `0x140027b9b`: `InstallDir`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CAppIdExtImpl::CAppIdExtImpl(__int64 a1)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  HKEY v3; // rdi
  __int64 v4; // r8
  HKEY phkResult; // [rsp+38h] [rbp-D0h] BYREF
  HKEY v7[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v8; // [rsp+50h] [rbp-B8h]
  __int64 v9; // [rsp+58h] [rbp-B0h]
  unsigned __int16 v10[264]; // [rsp+68h] [rbp-A0h] BYREF

  v9 = a1;
  *(_DWORD *)(a1 + 32) = 0;
  *(_OWORD *)(a1 + 40) = 0;
  *(_OWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_BYTE *)(a1 + 80) = 0;
  *(_QWORD *)a1 = &IRegistryFilter::`vftable';
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_DWORD *)(a1 + 120) = 0;
  *(_DWORD *)(a1 + 156) = 0;
  *(_BYTE *)(a1 + 160) = 1;
  *(_QWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(GUID *)(a1 + 124) = GUID_NULL;
  *(GUID *)(a1 + 140) = GUID_NULL;
  *(_QWORD *)(a1 + 200) = 0;
  *(_DWORD *)(a1 + 320) = 0;
  *(_QWORD *)(a1 + 328) = 0;
  *(_QWORD *)(a1 + 336) = 0;
  *(_DWORD *)(a1 + 344) = 0;
  *(_QWORD *)(a1 + 352) = 0;
  *(GUID *)(a1 + 360) = GUID_NULL;
  *(_QWORD *)(a1 + 376) = 0;
  *(_DWORD *)(a1 + 384) = 0;
  *(_QWORD *)(a1 + 392) = 0;
  *(_DWORD *)(a1 + 400) = 0;
  memset_0((void *)(a1 + 208), 0, 0x70u);
  *(_QWORD *)(a1 + 408) = 0;
  *(_QWORD *)(a1 + 416) = 0;
  *(_DWORD *)(a1 + 424) = 0;
  *(_BYTE *)(a1 + 1468) = 0;
  *(_QWORD *)(a1 + 1472) = 0;
  *(_DWORD *)(a1 + 1480) = 2;
  *(_QWORD *)(a1 + 1488) = 0;
  *(_QWORD *)(a1 + 1496) = 0;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  *(_QWORD *)(a1 + 1504) = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                         + 24;
  *(_DWORD *)(a1 + 1512) = GetCurrentThreadId();
  memset_0((void *)(a1 + 428), 0, 0x208u);
  memset_0((void *)(a1 + 948), 0, 0x208u);
  *(_OWORD *)v7 = 0;
  v3 = 0;
  LODWORD(v7[1]) = 0;
  v8 = 0;
  phkResult = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\VisualStudio\\17.0", 0, 0x20019u, &phkResult) )
  {
    v7[0] = phkResult;
    LODWORD(v7[1]) = 0;
    memset_0(v10, 0, 0x208u);
    LODWORD(phkResult) = 260;
    if ( !(unsigned int)ATL::CRegKey::QueryStringValue(
                          (ATL::CRegKey *)v7,
                          L"InstallDir",
                          v10,
                          (unsigned int *)&phkResult) )
    {
      v4 = -1;
      do
        ++v4;
      while ( v10[v4] );
      ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 1504, v10);
    }
    v3 = v7[0];
  }
  if ( v3 )
    RegCloseKey(v3);
  return a1;
}

```

## disassembly

```asm
0x140027978  mov     rax, rsp
0x14002797b  mov     [rax+10h], rbx
0x14002797f  mov     [rax+18h], rsi
0x140027983  mov     [rax+20h], rdi
0x140027987  push    rbp
0x140027988  push    r14
0x14002798a  push    r15
0x14002798c  lea     rbp, [rax-198h]
0x140027993  sub     rsp, 280h
0x14002799a  mov     rax, cs:__security_cookie
0x1400279a1  xor     rax, rsp
0x1400279a4  mov     [rbp+190h+var_20], rax
0x1400279ab  mov     rbx, rcx
0x1400279ae  mov     [rsp+290h+var_240], rcx
0x1400279b3  xor     r14d, r14d
0x1400279b6  mov     [rcx+20h], r14d
0x1400279ba  xorps   xmm0, xmm0
0x1400279bd  xor     eax, eax
0x1400279bf  movups  xmmword ptr [rcx+28h], xmm0
0x1400279c3  movups  xmmword ptr [rcx+38h], xmm0
0x1400279c7  mov     [rcx+48h], rax
0x1400279cb  mov     [rcx+50h], r14b
0x1400279cf  lea     rax, ??_7IRegistryFilter@@6B@; const IRegistryFilter::`vftable'
0x1400279d6  mov     [rcx], rax
0x1400279d9  mov     [rcx+58h], r14
0x1400279dd  mov     [rcx+60h], r14
0x1400279e1  mov     [rcx+68h], r14
0x1400279e5  mov     [rcx+70h], r14
0x1400279e9  mov     [rcx+78h], r14d
0x1400279ed  mov     [rcx+9Ch], r14d
0x1400279f4  mov     byte ptr [rcx+0A0h], 1
0x1400279fb  mov     [rcx+0A8h], r14
0x140027a02  mov     [rcx+0B0h], r14
0x140027a09  mov     [rcx+0B8h], r14
0x140027a10  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140027a17  movdqu  xmmword ptr [rcx+7Ch], xmm0
0x140027a1c  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x140027a23  movdqu  xmmword ptr [rcx+8Ch], xmm1
0x140027a2b  mov     [rcx+0C8h], r14
0x140027a32  mov     [rcx+140h], r14d
0x140027a39  mov     [rcx+148h], r14
0x140027a40  mov     [rcx+150h], r14
0x140027a47  mov     [rcx+158h], r14d
0x140027a4e  mov     [rcx+160h], r14
0x140027a55  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140027a5c  movdqu  xmmword ptr [rcx+168h], xmm0
0x140027a64  mov     [rcx+178h], r14
0x140027a6b  mov     [rcx+180h], r14d
0x140027a72  mov     [rcx+188h], r14
0x140027a79  mov     [rcx+190h], r14d
0x140027a80  add     rcx, 0D0h; void *
0x140027a87  xor     edx, edx; Val
0x140027a89  lea     r8d, [r14+70h]; Size
0x140027a8d  call    memset_0
0x140027a92  mov     [rbx+198h], r14
0x140027a99  mov     [rbx+1A0h], r14
0x140027aa0  mov     [rbx+1A8h], r14d
0x140027aa7  mov     [rbx+5BCh], r14b
0x140027aae  mov     [rbx+5C0h], r14
0x140027ab5  mov     dword ptr [rbx+5C8h], 2
0x140027abf  mov     [rbx+5D0h], r14
0x140027ac6  mov     [rbx+5D8h], r14
0x140027acd  lea     rsi, [rbx+5E0h]
0x140027ad4  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x140027ad9  mov     rcx, rax
0x140027adc  test    rax, rax
0x140027adf  jz      loc_140027C13
0x140027ae5  mov     rax, [rax]
0x140027ae8  call    qword ptr [rax+18h]
0x140027aeb  add     rax, 18h
0x140027aef  mov     [rsi], rax
0x140027af2  call    cs:__imp_GetCurrentThreadId
0x140027af8  mov     [rbx+5E8h], eax
0x140027afe  lea     rcx, [rbx+1ACh]; void *
0x140027b05  mov     r15d, 208h
0x140027b0b  mov     r8d, r15d; Size
0x140027b0e  xor     edx, edx; Val
0x140027b10  call    memset_0
0x140027b15  lea     rcx, [rbx+3B4h]; void *
0x140027b1c  mov     r8d, r15d; Size
0x140027b1f  xor     edx, edx; Val
0x140027b21  call    memset_0
0x140027b26  xorps   xmm0, xmm0
0x140027b29  movups  xmmword ptr [rsp+290h+var_260+8], xmm0
0x140027b2e  mov     edi, r14d
0x140027b31  mov     dword ptr [rsp+290h+var_250], r14d
0x140027b36  mov     [rsp+290h+var_248], r14
0x140027b3b  mov     [rsp+290h+var_260], r14
0x140027b40  lea     rax, [rsp+290h+var_260]
0x140027b45  mov     [rsp+290h+phkResult], rax; phkResult
0x140027b4a  mov     r9d, 20019h; samDesired
0x140027b50  xor     r8d, r8d; ulOptions
0x140027b53  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\VisualStudio\\17.0"
0x140027b5a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140027b61  call    cs:__imp_RegOpenKeyExW
0x140027b67  test    eax, eax
0x140027b69  jnz     short loc_140027BD5
0x140027b6b  mov     rax, [rsp+290h+var_260]
0x140027b70  mov     [rsp+290h+var_260+8], rax
0x140027b75  mov     dword ptr [rsp+290h+var_250], r14d
0x140027b7a  mov     r8d, r15d; Size
0x140027b7d  xor     edx, edx; Val
0x140027b7f  lea     rcx, [rsp+290h+var_230]; void *
0x140027b84  call    memset_0
0x140027b89  mov     dword ptr [rsp+290h+var_260], 104h
0x140027b91  lea     r9, [rsp+290h+var_260]; unsigned int *
0x140027b96  lea     r8, [rsp+290h+var_230]; unsigned __int16 *
0x140027b9b  lea     rdx, aInstalldir; "InstallDir"
0x140027ba2  lea     rcx, [rsp+290h+var_260+8]; this
0x140027ba7  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x140027bac  test    eax, eax
0x140027bae  jnz     short loc_140027BD0
0x140027bb0  lea     rax, [rsp+290h+var_230]
0x140027bb5  or      r8, 0FFFFFFFFFFFFFFFFh
0x140027bb9  inc     r8
0x140027bbc  cmp     [rax+r8*2], r14w
0x140027bc1  jnz     short loc_140027BB9
0x140027bc3  lea     rdx, [rsp+290h+var_230]
0x140027bc8  mov     rcx, rsi
0x140027bcb  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140027bd0  mov     rdi, [rsp+290h+var_260+8]
0x140027bd5  test    rdi, rdi
0x140027bd8  jz      short loc_140027BE4
0x140027bda  mov     rcx, rdi; hKey
0x140027bdd  call    cs:__imp_RegCloseKey
0x140027be3  nop
0x140027be4  mov     rax, rbx
0x140027be7  mov     rcx, [rbp+190h+var_20]
0x140027bee  xor     rcx, rsp; StackCookie
0x140027bf1  call    __security_check_cookie
0x140027bf6  lea     r11, [rsp+290h+var_10]
0x140027bfe  mov     rbx, [r11+28h]
0x140027c02  mov     rsi, [r11+30h]
0x140027c06  mov     rdi, [r11+38h]
0x140027c0a  mov     rsp, r11
0x140027c0d  pop     r15
0x140027c0f  pop     r14
0x140027c11  pop     rbp
0x140027c12  retn
0x140027c13  mov     ecx, 80004005h; int
0x140027c18  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
