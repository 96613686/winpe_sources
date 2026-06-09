# DxgAppCompat::GetAppCompatString(unsigned __int64 *,char *,bool)

- ea: `0x180010d8c`
- end: `0x180010fac`
- name: `?GetAppCompatString@DxgAppCompat@@YAHPEA_KPEAD_N@Z`
- size: `544`
- prototype: `int(DxgAppCompat *__hidden this, unsigned __int64 *, char *, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010ae0`

## callees

- `0x180008d5c`
- `0x18000c335`
- `0x18000de10`
- `0x180010d8c`
- `0x180010ff4`
- `0x180011648`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180010f95`
- `msvcp_win!_Mtx_unlock` at `0x180010f95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180010e2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180010ef8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180010e2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180010ef8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f35`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DxgAppCompat::GetAppCompatString(DxgAppCompat *this, unsigned __int64 *a2, char *a3)
{
  unsigned int v6; // ebx
  const char *v7; // rcx
  char **v8; // rdi
  HKEY v9; // rsi
  unsigned __int64 v10; // r10
  unsigned __int64 v11; // rdx
  unsigned int v12; // r13d
  char *v13; // rcx
  unsigned int v14; // r10d
  char **v15; // rcx
  char **v16; // rdx
  unsigned int v17; // esi
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+50h] BYREF
  void *v20; // [rsp+88h] [rbp+58h]

  LOBYTE(cbData) = (_BYTE)a3;
  if ( !this )
    return 0;
  v6 = 1;
  if ( a2 && *(_QWORD *)this )
    *(_BYTE *)a2 = 0;
  v20 = &DxgAppCompat::gs_critSec;
  std::_Mutex_base::lock((std::_Mutex_base *)&DxgAppCompat::gs_critSec);
  v8 = &DxgAppCompat::g_CompatStringCache;
  if ( !DxgAppCompat::g_AttemptReadString )
  {
    Type = 0;
    cbData = 0;
    v9 = OpenAppRegKey(v7);
    if ( v9 && (RegQueryValueExA(v9, "D3DBehaviors", 0, &Type, 0, &cbData) || Type != 1) )
      cbData = 0;
    v10 = DxgAppCompat::g_ShimmedAppCompatStringBufferLength;
    if ( DxgAppCompat::g_ShimmedAppCompatStringBufferLength + cbData < DxgAppCompat::g_ShimmedAppCompatStringBufferLength )
      cbData = 0;
    v11 = DxgAppCompat::g_ShimmedAppCompatStringBufferLength + cbData;
    if ( v11 )
    {
      std::string::resize(&DxgAppCompat::g_CompatStringCache, v11 - 1);
      v10 = DxgAppCompat::g_ShimmedAppCompatStringBufferLength;
    }
    v12 = 0;
    if ( v10 && DxgAppCompat::g_ShimmedAppCompatString )
    {
      v13 = (char *)&DxgAppCompat::g_CompatStringCache;
      if ( (unsigned __int64)qword_18001E898 > 0xF )
        v13 = DxgAppCompat::g_CompatStringCache;
      if ( (int)StringCchCopyA(v13, v10, DxgAppCompat::g_ShimmedAppCompatString) >= 0 )
      {
        v12 = v14;
        DxgAppCompat::g_bCompatStringExists = 1;
      }
    }
    if ( v9 )
    {
      if ( cbData )
      {
        v15 = &DxgAppCompat::g_CompatStringCache;
        if ( (unsigned __int64)qword_18001E898 > 0xF )
          v15 = (char **)DxgAppCompat::g_CompatStringCache;
        if ( !RegQueryValueExA(v9, "D3DBehaviors", 0, &Type, (LPBYTE)v15 + v12, &cbData) && Type == 1 && cbData )
        {
          if ( v12 )
          {
            v16 = &DxgAppCompat::g_CompatStringCache;
            if ( (unsigned __int64)qword_18001E898 > 0xF )
              v16 = (char **)DxgAppCompat::g_CompatStringCache;
            *((_BYTE *)v16 + v12 - 1) = 59;
          }
          DxgAppCompat::g_bCompatStringExists = 1;
        }
      }
      RegCloseKey(v9);
    }
    DxgAppCompat::g_AttemptReadString = 1;
  }
  if ( DxgAppCompat::g_bCompatStringExists )
  {
    if ( (unsigned __int64)qword_18001E898 > 0xF )
      v8 = (char **)DxgAppCompat::g_CompatStringCache;
    v17 = qword_18001E890 + 1;
    if ( (_DWORD)qword_18001E890 != -1 && v8 && a2 && *(_QWORD *)this >= (unsigned __int64)v17 )
      memcpy_0(a2, v8, v17);
    *(_QWORD *)this = v17;
  }
  else
  {
    v6 = 0;
  }
  _Mtx_unlock((_Mtx_t)&DxgAppCompat::gs_critSec);
  return v6;
}

```

## disassembly

```asm
0x180010d8c  mov     byte ptr [rsp-38h+cbData], r8b
0x180010d91  push    rbp
0x180010d92  push    rbx
0x180010d93  push    rsi
0x180010d94  push    rdi
0x180010d95  push    r13
0x180010d97  push    r14
0x180010d99  push    r15
0x180010d9b  mov     rbp, rsp
0x180010d9e  sub     rsp, 30h
0x180010da2  mov     r15, rdx
0x180010da5  mov     r14, rcx
0x180010da8  test    rcx, rcx
0x180010dab  jnz     short loc_180010DB4
0x180010dad  xor     eax, eax
0x180010daf  jmp     loc_180010F9D
0x180010db4  mov     ebx, 1
0x180010db9  test    r15, r15
0x180010dbc  jz      short loc_180010DC6
0x180010dbe  cmp     [rcx], rbx
0x180010dc1  jb      short loc_180010DC6
0x180010dc3  mov     byte ptr [rdx], 0
0x180010dc6  lea     r13, ?gs_critSec@DxgAppCompat@@3Vmutex@std@@A; std::mutex DxgAppCompat::gs_critSec
0x180010dcd  mov     [rbp+arg_18], r13
0x180010dd1  mov     rcx, r13; this
0x180010dd4  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180010dd9  nop
0x180010dda  lea     rdi, ?g_CompatStringCache@DxgAppCompat@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string DxgAppCompat::g_CompatStringCache
0x180010de1  cmp     cs:?g_AttemptReadString@DxgAppCompat@@3HA, 0; int DxgAppCompat::g_AttemptReadString
0x180010de8  jnz     loc_180010F48
0x180010dee  mov     [rbp+Type], 0
0x180010df5  mov     [rbp+cbData], 0
0x180010dfc  call    ?OpenAppRegKey@@YAPEAUHKEY__@@PEBD@Z; OpenAppRegKey(char const *)
0x180010e01  mov     rsi, rax
0x180010e04  test    rax, rax
0x180010e07  jz      short loc_180010E42
0x180010e09  lea     rax, [rbp+cbData]
0x180010e0d  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180010e12  mov     [rsp+30h+lpData], 0; lpData
0x180010e1b  lea     r9, [rbp+Type]; lpType
0x180010e1f  xor     r8d, r8d; lpReserved
0x180010e22  lea     rdx, ValueName; "D3DBehaviors"
0x180010e29  mov     rcx, rsi; hKey
0x180010e2c  call    cs:__imp_RegQueryValueExA
0x180010e32  test    eax, eax
0x180010e34  jnz     short loc_180010E3B
0x180010e36  cmp     [rbp+Type], ebx
0x180010e39  jz      short loc_180010E42
0x180010e3b  mov     [rbp+cbData], 0
0x180010e42  mov     eax, [rbp+cbData]
0x180010e45  mov     r10, cs:?g_ShimmedAppCompatStringBufferLength@DxgAppCompat@@3_KA; unsigned __int64 DxgAppCompat::g_ShimmedAppCompatStringBufferLength
0x180010e4c  add     rax, r10
0x180010e4f  cmp     rax, r10
0x180010e52  jnb     short loc_180010E5B
0x180010e54  mov     [rbp+cbData], 0
0x180010e5b  mov     edx, [rbp+cbData]
0x180010e5e  add     rdx, r10
0x180010e61  jz      short loc_180010E75
0x180010e63  dec     rdx
0x180010e66  mov     rcx, rdi
0x180010e69  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x180010e6e  mov     r10, cs:?g_ShimmedAppCompatStringBufferLength@DxgAppCompat@@3_KA; unsigned __int64 DxgAppCompat::g_ShimmedAppCompatStringBufferLength
0x180010e75  xor     r13d, r13d
0x180010e78  test    r10, r10
0x180010e7b  jz      short loc_180010EB1
0x180010e7d  mov     r8, cs:?g_ShimmedAppCompatString@DxgAppCompat@@3PEBDEB; char *
0x180010e84  test    r8, r8
0x180010e87  jz      short loc_180010EB1
0x180010e89  mov     rcx, rdi
0x180010e8c  cmp     cs:qword_18001E898, 0Fh
0x180010e94  cmova   rcx, cs:?g_CompatStringCache@DxgAppCompat@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; char *
0x180010e9c  mov     rdx, r10; unsigned __int64
0x180010e9f  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180010ea4  test    eax, eax
0x180010ea6  js      short loc_180010EB1
0x180010ea8  mov     r13d, r10d
0x180010eab  mov     cs:?g_bCompatStringExists@DxgAppCompat@@3HA, ebx; int DxgAppCompat::g_bCompatStringExists
0x180010eb1  test    rsi, rsi
0x180010eb4  jz      loc_180010F3B
0x180010eba  cmp     [rbp+cbData], 0
0x180010ebe  jz      short loc_180010F32
0x180010ec0  mov     rcx, rdi
0x180010ec3  cmp     cs:qword_18001E898, 0Fh
0x180010ecb  cmova   rcx, cs:?g_CompatStringCache@DxgAppCompat@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string DxgAppCompat::g_CompatStringCache
0x180010ed3  mov     eax, r13d
0x180010ed6  add     rax, rcx
0x180010ed9  lea     rcx, [rbp+cbData]
0x180010edd  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x180010ee2  mov     [rsp+30h+lpData], rax; lpData
0x180010ee7  lea     r9, [rbp+Type]; lpType
0x180010eeb  xor     r8d, r8d; lpReserved
0x180010eee  lea     rdx, ValueName; "D3DBehaviors"
0x180010ef5  mov     rcx, rsi; hKey
0x180010ef8  call    cs:__imp_RegQueryValueExA
0x180010efe  test    eax, eax
0x180010f00  jnz     short loc_180010F32
0x180010f02  cmp     [rbp+Type], ebx
0x180010f05  jnz     short loc_180010F32
0x180010f07  cmp     [rbp+cbData], eax
0x180010f0a  jz      short loc_180010F32
0x180010f0c  test    r13d, r13d
0x180010f0f  jz      short loc_180010F2C
0x180010f11  mov     rdx, rdi
0x180010f14  cmp     cs:qword_18001E898, 0Fh
0x180010f1c  cmova   rdx, cs:?g_CompatStringCache@DxgAppCompat@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string DxgAppCompat::g_CompatStringCache
0x180010f24  lea     eax, [r13-1]
0x180010f28  mov     byte ptr [rax+rdx], 3Bh ; ';'
0x180010f2c  mov     cs:?g_bCompatStringExists@DxgAppCompat@@3HA, ebx; int DxgAppCompat::g_bCompatStringExists
0x180010f32  mov     rcx, rsi; hKey
0x180010f35  call    cs:__imp_RegCloseKey
0x180010f3b  mov     cs:?g_AttemptReadString@DxgAppCompat@@3HA, ebx; int DxgAppCompat::g_AttemptReadString
0x180010f41  lea     r13, ?gs_critSec@DxgAppCompat@@3Vmutex@std@@A; std::mutex DxgAppCompat::gs_critSec
0x180010f48  cmp     cs:?g_bCompatStringExists@DxgAppCompat@@3HA, 0; int DxgAppCompat::g_bCompatStringExists
0x180010f4f  jz      short loc_180010F90
0x180010f51  mov     esi, dword ptr cs:qword_18001E890
0x180010f57  cmp     cs:qword_18001E898, 0Fh
0x180010f5f  cmova   rdi, cs:?g_CompatStringCache@DxgAppCompat@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string DxgAppCompat::g_CompatStringCache
0x180010f67  add     esi, 1
0x180010f6a  jz      short loc_180010F89
0x180010f6c  test    rdi, rdi
0x180010f6f  jz      short loc_180010F89
0x180010f71  test    r15, r15
0x180010f74  jz      short loc_180010F89
0x180010f76  mov     r8d, esi; Size
0x180010f79  cmp     [r14], r8
0x180010f7c  jb      short loc_180010F89
0x180010f7e  mov     rdx, rdi; Src
0x180010f81  mov     rcx, r15; void *
0x180010f84  call    memcpy_0
0x180010f89  mov     eax, esi
0x180010f8b  mov     [r14], rax
0x180010f8e  jmp     short loc_180010F92
0x180010f90  xor     ebx, ebx
0x180010f92  mov     rcx, r13; _Mtx_t
0x180010f95  call    cs:__imp__Mtx_unlock
0x180010f9b  mov     eax, ebx
0x180010f9d  add     rsp, 30h
0x180010fa1  pop     r15
0x180010fa3  pop     r14
0x180010fa5  pop     r13
0x180010fa7  pop     rdi
0x180010fa8  pop     rsi
0x180010fa9  pop     rbx
0x180010faa  pop     rbp
0x180010fab  retn
```
