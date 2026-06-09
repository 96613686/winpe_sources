# NetTrace::CPersistentTrace::Commit(void)

- ea: `0x180028cdc`
- end: `0x180028efa`
- name: `?Commit@CPersistentTrace@NetTrace@@QEAAJXZ`
- size: `542`
- prototype: `__int64 __fastcall(NetTrace::CPersistentTrace *this, __int64, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180029ea0`

## callees

- `0x180007b48`
- `0x18001f0a4`
- `0x180028cdc`
- `0x180028f00`
- `0x1800290a8`
- `0x180029788`
- `0x180029b74`
- `0x180029e44`
- `0x18002c840`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180028d80`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180028d80`

## pseudocode

```c
__int64 __fastcall NetTrace::CPersistentTrace::Commit(
        NetTrace::CPersistentTrace *this,
        __int64 a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  int v5; // ebx
  int v6; // eax
  int v7; // eax
  unsigned int v8; // r9d
  unsigned int v9; // r9d
  bool v10; // zf
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  unsigned int v19; // [rsp+20h] [rbp-99h]
  unsigned int v20; // [rsp+28h] [rbp-91h]
  struct _SECURITY_ATTRIBUTES *v21; // [rsp+30h] [rbp-89h]
  unsigned int *v22; // [rsp+38h] [rbp-81h]
  HKEY v23[3]; // [rsp+40h] [rbp-79h] BYREF
  __int64 v24; // [rsp+58h] [rbp-61h] BYREF
  OLECHAR sz[64]; // [rsp+60h] [rbp-59h] BYREF

  v5 = *(_DWORD *)this;
  if ( !*(_DWORD *)this )
  {
    v6 = ATL::CRegKey::RecurseDeleteKey(
           (NetTrace::CPersistentTrace *)((char *)this + 8),
           *((const unsigned __int16 **)this + 5));
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v5 == -2147024894 )
      v5 = 0;
  }
  memset(v23, 0, sizeof(v23));
  if ( !v5 )
  {
    v7 = ATL::CRegKey::Create((ATL::CRegKey *)v23, *((HKEY *)this + 1), *((LPCWSTR *)this + 5), a4, v19, v20, v21, v22);
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    if ( !v5 )
    {
      StringFromGUID2((const GUID *const)this + 3, sz, 64);
      v24 = 0;
      v5 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)v23, L"GUID", sz, v8);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v24);
      v10 = v5 == 0;
      if ( v5 > 0 )
      {
        v5 = (unsigned __int16)v5 | 0x80070000;
        v10 = v5 == 0;
      }
      if ( v10 )
      {
        v11 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)v23, L"FileName", *((const unsigned __int16 **)this + 8), v9);
        v5 = v11;
        if ( v11 > 0 )
          v5 = (unsigned __int16)v11 | 0x80070000;
        if ( !v5 )
        {
          v12 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v23, L"LogFileMode", *((_DWORD *)this + 19));
          v5 = v12;
          if ( v12 > 0 )
            v5 = (unsigned __int16)v12 | 0x80070000;
          if ( !v5 )
          {
            v13 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v23, L"MaxFileSize", *((_DWORD *)this + 18));
            v5 = v13;
            if ( v13 > 0 )
              v5 = (unsigned __int16)v13 | 0x80070000;
            if ( !v5 )
            {
              v14 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v23, L"BufferSize", *((_DWORD *)this + 20));
              v5 = v14;
              if ( v14 > 0 )
                v5 = (unsigned __int16)v14 | 0x80070000;
              if ( !v5 )
              {
                v15 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v23, L"MaximumBuffers", *((_DWORD *)this + 21));
                v5 = v15;
                if ( v15 > 0 )
                  v5 = (unsigned __int16)v15 | 0x80070000;
                if ( !v5 )
                {
                  v16 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v23, L"MinimumBuffers", *((_DWORD *)this + 22));
                  v5 = v16;
                  if ( v16 > 0 )
                    v5 = (unsigned __int16)v16 | 0x80070000;
                  if ( !v5 )
                  {
                    v5 = NetTrace::CPersistentTrace::CommitProviders(this, (struct ATL::CRegKey *)v23);
                    if ( !v5 )
                    {
                      v17 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v23, L"Start", *((_DWORD *)this + 8));
                      v5 = v17;
                      if ( v17 > 0 )
                        v5 = (unsigned __int16)v17 | 0x80070000;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  ATL::CRegKey::Close(v23);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180028cdc  push    rbp
0x180028cde  push    rbx
0x180028cdf  push    rdi
0x180028ce0  push    r14
0x180028ce2  lea     rbp, [rsp-3Fh]
0x180028ce7  sub     rsp, 0F8h
0x180028cee  mov     rax, cs:__security_cookie
0x180028cf5  xor     rax, rsp
0x180028cf8  mov     [rbp+57h+var_30], rax
0x180028cfc  mov     rdi, rcx
0x180028cff  mov     ebx, [rcx]
0x180028d01  mov     r14d, 80070000h
0x180028d07  test    ebx, ebx
0x180028d09  jnz     short loc_180028D2F
0x180028d0b  add     rcx, 8; this
0x180028d0f  mov     rdx, [rdi+28h]; unsigned __int16 *
0x180028d13  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180028d18  mov     ebx, eax
0x180028d1a  test    eax, eax
0x180028d1c  jle     short loc_180028D24
0x180028d1e  movzx   ebx, ax
0x180028d21  or      ebx, r14d
0x180028d24  xor     eax, eax
0x180028d26  cmp     ebx, 80070002h
0x180028d2c  cmovz   ebx, eax
0x180028d2f  mov     [rbp+57h+var_D0], 0
0x180028d37  mov     [rbp+57h+var_C8], 0
0x180028d3f  mov     [rbp+57h+var_C0], 0
0x180028d47  test    ebx, ebx
0x180028d49  jnz     loc_180028ED6
0x180028d4f  mov     r8, [rdi+28h]; lpSubKey
0x180028d53  mov     rdx, [rdi+8]; hKey
0x180028d57  lea     rcx, [rbp+57h+var_D0]; this
0x180028d5b  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180028d60  mov     ebx, eax
0x180028d62  test    eax, eax
0x180028d64  jle     short loc_180028D6C
0x180028d66  movzx   ebx, ax
0x180028d69  or      ebx, r14d
0x180028d6c  test    ebx, ebx
0x180028d6e  jnz     loc_180028ED6
0x180028d74  lea     rcx, [rdi+30h]; rguid
0x180028d78  lea     r8d, [rbx+40h]; cchMax
0x180028d7c  lea     rdx, [rbp+57h+sz]; lpsz
0x180028d80  call    cs:__imp_StringFromGUID2
0x180028d86  mov     [rbp+57h+var_B8], 0
0x180028d8e  lea     r8, [rbp+57h+sz]; unsigned __int16 *
0x180028d92  lea     rdx, aGuid_0; "GUID"
0x180028d99  lea     rcx, [rbp+57h+var_D0]; this
0x180028d9d  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180028da2  mov     ebx, eax
0x180028da4  lea     rcx, [rbp+57h+var_B8]
0x180028da8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180028dad  nop
0x180028dae  test    ebx, ebx
0x180028db0  jle     short loc_180028DBA
0x180028db2  movzx   ebx, bx
0x180028db5  or      ebx, r14d
0x180028db8  test    ebx, ebx
0x180028dba  jnz     loc_180028ED6
0x180028dc0  mov     r8, [rdi+40h]; unsigned __int16 *
0x180028dc4  lea     rdx, aFilename; "FileName"
0x180028dcb  lea     rcx, [rbp+57h+var_D0]; this
0x180028dcf  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180028dd4  mov     ebx, eax
0x180028dd6  test    eax, eax
0x180028dd8  jle     short loc_180028DE0
0x180028dda  movzx   ebx, ax
0x180028ddd  or      ebx, r14d
0x180028de0  test    ebx, ebx
0x180028de2  jnz     loc_180028ED6
0x180028de8  mov     r8d, [rdi+4Ch]; unsigned int
0x180028dec  lea     rdx, aLogfilemode; "LogFileMode"
0x180028df3  lea     rcx, [rbp+57h+var_D0]; this
0x180028df7  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180028dfc  mov     ebx, eax
0x180028dfe  test    eax, eax
0x180028e00  jle     short loc_180028E08
0x180028e02  movzx   ebx, ax
0x180028e05  or      ebx, r14d
0x180028e08  test    ebx, ebx
0x180028e0a  jnz     loc_180028ED6
0x180028e10  mov     r8d, [rdi+48h]; unsigned int
0x180028e14  lea     rdx, aMaxfilesize; "MaxFileSize"
0x180028e1b  lea     rcx, [rbp+57h+var_D0]; this
0x180028e1f  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180028e24  mov     ebx, eax
0x180028e26  test    eax, eax
0x180028e28  jle     short loc_180028E30
0x180028e2a  movzx   ebx, ax
0x180028e2d  or      ebx, r14d
0x180028e30  test    ebx, ebx
0x180028e32  jnz     loc_180028ED6
0x180028e38  mov     r8d, [rdi+50h]; unsigned int
0x180028e3c  lea     rdx, aBuffersize; "BufferSize"
0x180028e43  lea     rcx, [rbp+57h+var_D0]; this
0x180028e47  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180028e4c  mov     ebx, eax
0x180028e4e  test    eax, eax
0x180028e50  jle     short loc_180028E58
0x180028e52  movzx   ebx, ax
0x180028e55  or      ebx, r14d
0x180028e58  test    ebx, ebx
0x180028e5a  jnz     short loc_180028ED6
0x180028e5c  mov     r8d, [rdi+54h]; unsigned int
0x180028e60  lea     rdx, aMaximumbuffers; "MaximumBuffers"
0x180028e67  lea     rcx, [rbp+57h+var_D0]; this
0x180028e6b  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180028e70  mov     ebx, eax
0x180028e72  test    eax, eax
0x180028e74  jle     short loc_180028E7C
0x180028e76  movzx   ebx, ax
0x180028e79  or      ebx, r14d
0x180028e7c  test    ebx, ebx
0x180028e7e  jnz     short loc_180028ED6
0x180028e80  mov     r8d, [rdi+58h]; unsigned int
0x180028e84  lea     rdx, aMinimumbuffers; "MinimumBuffers"
0x180028e8b  lea     rcx, [rbp+57h+var_D0]; this
0x180028e8f  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180028e94  mov     ebx, eax
0x180028e96  test    eax, eax
0x180028e98  jle     short loc_180028EA0
0x180028e9a  movzx   ebx, ax
0x180028e9d  or      ebx, r14d
0x180028ea0  test    ebx, ebx
0x180028ea2  jnz     short loc_180028ED6
0x180028ea4  lea     rdx, [rbp+57h+var_D0]; struct ATL::CRegKey *
0x180028ea8  mov     rcx, rdi; this
0x180028eab  call    ?CommitProviders@CPersistentTrace@NetTrace@@AEAAJAEAVCRegKey@ATL@@@Z; NetTrace::CPersistentTrace::CommitProviders(ATL::CRegKey &)
0x180028eb0  mov     ebx, eax
0x180028eb2  test    eax, eax
0x180028eb4  jnz     short loc_180028ED6
0x180028eb6  mov     r8d, [rdi+20h]; unsigned int
0x180028eba  lea     rdx, aStart; "Start"
0x180028ec1  lea     rcx, [rbp+57h+var_D0]; this
0x180028ec5  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180028eca  mov     ebx, eax
0x180028ecc  test    eax, eax
0x180028ece  jle     short loc_180028ED6
0x180028ed0  movzx   ebx, ax
0x180028ed3  or      ebx, r14d
0x180028ed6  lea     rcx, [rbp+57h+var_D0]; this
0x180028eda  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180028edf  mov     eax, ebx
0x180028ee1  mov     rcx, [rbp+57h+var_30]
0x180028ee5  xor     rcx, rsp; StackCookie
0x180028ee8  call    __security_check_cookie
0x180028eed  add     rsp, 0F8h
0x180028ef4  pop     r14
0x180028ef6  pop     rdi
0x180028ef7  pop     rbx
0x180028ef8  pop     rbp
0x180028ef9  retn
```
