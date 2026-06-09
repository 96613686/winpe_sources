# ATL::CRegKey::QueryGUIDValue(ushort const *,_GUID &)

- ea: `0x18002113c`
- end: `0x1800211e0`
- name: `?QueryGUIDValue@CRegKey@ATL@@QEAAJPEBGAEAU_GUID@@@Z`
- size: `164`
- prototype: `int(ATL::CRegKey *__hidden this, const unsigned __int16 *, struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f71c`
- `0x1800203c0`

## callees

- `0x180007b48`
- `0x18002113c`
- `0x1800211e8`
- `0x18002c840`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800211a8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800211a8`

## string_xrefs

- `0x180021178`: `CLSID`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::QueryGUIDValue(ATL::CRegKey *this, const unsigned __int16 *a2, struct _GUID *a3)
{
  __int64 result; // rax
  unsigned int v5; // ebx
  unsigned int v6[4]; // [rsp+20h] [rbp-A8h] BYREF
  OLECHAR sz[64]; // [rsp+30h] [rbp-98h] BYREF

  v6[0] = 64;
  *a3 = GUID_NULL;
  result = ATL::CRegKey::QueryStringValue(this, L"CLSID", sz, v6);
  if ( !(_DWORD)result )
  {
    if ( sz[0] == 123 )
    {
      *(_QWORD *)v6 = 0;
      if ( CLSIDFromString(sz, a3) >= 0 )
        v5 = 0;
      else
        v5 = 13;
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v6);
      return v5;
    }
    else
    {
      return 13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002113c  push    rbx
0x18002113e  sub     rsp, 0C0h
0x180021145  mov     rax, cs:__security_cookie
0x18002114c  xor     rax, rsp
0x18002114f  mov     [rsp+0C8h+var_18], rax
0x180021157  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002115e  mov     rbx, r8
0x180021161  mov     [rsp+0C8h+var_A8], 40h ; '@'
0x180021169  lea     r9, [rsp+0C8h+var_A8]; unsigned int *
0x18002116e  movdqu  xmmword ptr [r8], xmm0
0x180021173  lea     r8, [rsp+0C8h+sz]; unsigned __int16 *
0x180021178  lea     rdx, aClsid; "CLSID"
0x18002117f  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x180021184  test    eax, eax
0x180021186  jnz     short loc_1800211C7
0x180021188  cmp     [rsp+0C8h+sz], 7Bh ; '{'
0x18002118e  jz      short loc_180021197
0x180021190  mov     eax, 0Dh
0x180021195  jmp     short loc_1800211C7
0x180021197  mov     rdx, rbx; pclsid
0x18002119a  mov     qword ptr [rsp+0C8h+var_A8], 0
0x1800211a3  lea     rcx, [rsp+0C8h+sz]; lpsz
0x1800211a8  call    cs:__imp_CLSIDFromString
0x1800211ae  test    eax, eax
0x1800211b0  jns     short loc_1800211B9
0x1800211b2  mov     ebx, 0Dh
0x1800211b7  jmp     short loc_1800211BB
0x1800211b9  xor     ebx, ebx
0x1800211bb  lea     rcx, [rsp+0C8h+var_A8]
0x1800211c0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800211c5  mov     eax, ebx
0x1800211c7  mov     rcx, [rsp+0C8h+var_18]
0x1800211cf  xor     rcx, rsp; StackCookie
0x1800211d2  call    __security_check_cookie
0x1800211d7  add     rsp, 0C0h
0x1800211de  pop     rbx
0x1800211df  retn
```
