# CCertThumbprintsAndSidsMapping::CopySidsToBuffer(wchar_t const *,ulong,tagBLOB *,ulong *)

- ea: `0x18001f5f0`
- end: `0x18001f729`
- name: `?CopySidsToBuffer@CCertThumbprintsAndSidsMapping@@AEAAJPEB_WKPEAUtagBLOB@@PEAK@Z`
- size: `313`
- prototype: `__int64 __fastcall(CCertThumbprintsAndSidsMapping *this, const wchar_t *, unsigned int, struct tagBLOB *, _DWORD *Sid)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001f7b8`

## callees

- `0x180005eb0`
- `0x180011135`
- `0x18001f1a4`
- `0x18001f318`
- `0x18001f5f0`
- `0x18001fae0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f6c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f6c1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f6ab`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001f6ab`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001f68d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001f68d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f6ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f6ee`

## pseudocode

```c
__int64 __fastcall CCertThumbprintsAndSidsMapping::CopySidsToBuffer(
        CCertThumbprintsAndSidsMapping *this,
        const wchar_t *a2,
        unsigned int a3,
        struct tagBLOB *a4,
        _DWORD *Sid)
{
  _DWORD *v5; // r15
  unsigned int v8; // esi
  int Error; // edi
  __int64 v10; // rax
  unsigned int v11; // ebx
  __int64 v12; // rax
  const WCHAR *v13; // rcx
  _DWORD *v14; // rsi
  DWORD LengthSid; // eax
  size_t v16; // rbp
  BYTE *v17; // rax
  __int64 v19; // [rsp+20h] [rbp-78h] BYREF
  __int128 v20; // [rsp+28h] [rbp-70h]
  _BYTE v21[96]; // [rsp+38h] [rbp-60h] BYREF

  v5 = Sid;
  v8 = a3;
  Error = 0;
  *Sid = 0;
  CStringHashKey::CStringHashKey((CStringHashKey *)v21, a2);
  v10 = CTKPLiteHashMap<CStringHashKey,CHashValueStringList>::Lookup((char *)this + 24, v21);
  if ( v10 )
  {
    v19 = v10 + 48;
    v11 = 0;
    v20 = 0;
    v12 = CTPLiteSListIterator<CHashValueStringList,CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>>::operator++(&v19);
    do
    {
      if ( !v12 )
        break;
      if ( v11 < v8 )
      {
        v13 = *(const WCHAR **)(v12 + 24);
        Sid = 0;
        if ( ConvertStringSidToSidW(v13, (PSID *)&Sid) )
        {
          v14 = Sid;
          LengthSid = GetLengthSid(Sid);
          Error = 0;
          v16 = LengthSid;
          if ( LengthSid )
          {
            v17 = (BYTE *)CoTaskMemAlloc(LengthSid);
            a4[v11].pBlobData = v17;
            if ( v17 )
            {
              memcpy_0(v17, v14, v16);
              a4[v11].cbSize = v16;
            }
            else
            {
              Error = -2147024882;
            }
          }
          LocalFree(v14);
          v8 = a3;
          ++v11;
          if ( Error >= 0 )
            ++*v5;
        }
        else
        {
          Error = ResultFromLastError();
        }
      }
      else
      {
        Error = -2147024809;
      }
      v12 = CTPLiteSListIterator<CHashValueStringList,CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>>::operator++(&v19);
    }
    while ( Error >= 0 );
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001f5f0  mov     [rsp+arg_10], r8d
0x18001f5f5  push    rbx
0x18001f5f6  push    rbp
0x18001f5f7  push    rsi
0x18001f5f8  push    rdi
0x18001f5f9  push    r12
0x18001f5fb  push    r13
0x18001f5fd  push    r14
0x18001f5ff  push    r15
0x18001f601  sub     rsp, 58h
0x18001f605  mov     r15, [rsp+98h+Sid]
0x18001f60d  mov     rbx, rcx
0x18001f610  lea     rcx, [rsp+98h+var_60]; this
0x18001f615  mov     r13, r9
0x18001f618  mov     esi, r8d
0x18001f61b  xor     edi, edi
0x18001f61d  mov     dword ptr [r15], 0
0x18001f624  call    ??0CStringHashKey@@QEAA@PEB_W@Z; CStringHashKey::CStringHashKey(wchar_t const *)
0x18001f629  lea     rcx, [rbx+18h]
0x18001f62d  lea     rdx, [rsp+98h+var_60]
0x18001f632  call    ?Lookup@?$CTKPLiteHashMap@VCStringHashKey@@VCHashValueStringList@@@@QEBAPEAVCHashValueStringList@@PEBVCStringHashKey@@@Z; CTKPLiteHashMap<CStringHashKey,CHashValueStringList>::Lookup(CStringHashKey const *)
0x18001f637  test    rax, rax
0x18001f63a  jz      loc_18001F716
0x18001f640  add     rax, 30h ; '0'
0x18001f644  lea     rcx, [rsp+98h+var_78]
0x18001f649  xorps   xmm0, xmm0
0x18001f64c  mov     [rsp+98h+var_78], rax
0x18001f651  xor     ebx, ebx
0x18001f653  movdqu  [rsp+98h+var_70], xmm0
0x18001f659  call    ??E?$CTPLiteSListIterator@VCHashValueStringList@@V?$CTPKeyedLiteSList@VCStringHashKey@@VCHashValueStringList@@@@@@QEAAPEAVCHashValueStringList@@XZ; CTPLiteSListIterator<CHashValueStringList,CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>>::operator++(void)
0x18001f65e  test    rax, rax
0x18001f661  jz      loc_18001F716
0x18001f667  cmp     ebx, esi
0x18001f669  jb      short loc_18001F675
0x18001f66b  mov     edi, 80070057h
0x18001f670  jmp     loc_18001F704
0x18001f675  mov     rcx, [rax+18h]; StringSid
0x18001f679  lea     rdx, [rsp+98h+Sid]; Sid
0x18001f681  mov     [rsp+98h+Sid], 0
0x18001f68d  call    cs:__imp_ConvertStringSidToSidW
0x18001f693  test    eax, eax
0x18001f695  jnz     short loc_18001F6A0
0x18001f697  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001f69c  mov     edi, eax
0x18001f69e  jmp     short loc_18001F704
0x18001f6a0  mov     rsi, [rsp+98h+Sid]
0x18001f6a8  mov     rcx, rsi; pSid
0x18001f6ab  call    cs:__imp_GetLengthSid
0x18001f6b1  xor     edi, edi
0x18001f6b3  mov     ebp, eax
0x18001f6b5  test    eax, eax
0x18001f6b7  jz      short loc_18001F6EB
0x18001f6b9  mov     r14d, ebx
0x18001f6bc  mov     ecx, ebp; cb
0x18001f6be  add     r14, r14
0x18001f6c1  call    cs:__imp_CoTaskMemAlloc
0x18001f6c7  mov     [r13+r14*8+8], rax
0x18001f6cc  test    rax, rax
0x18001f6cf  jnz     short loc_18001F6D8
0x18001f6d1  mov     edi, 8007000Eh
0x18001f6d6  jmp     short loc_18001F6EB
0x18001f6d8  mov     r8, rbp; Size
0x18001f6db  mov     rdx, rsi; Src
0x18001f6de  mov     rcx, rax; void *
0x18001f6e1  call    memcpy_0
0x18001f6e6  mov     [r13+r14*8+0], ebp
0x18001f6eb  mov     rcx, rsi; hMem
0x18001f6ee  call    cs:__imp_LocalFree
0x18001f6f4  mov     esi, [rsp+98h+arg_10]
0x18001f6fb  inc     ebx
0x18001f6fd  test    edi, edi
0x18001f6ff  js      short loc_18001F704
0x18001f701  inc     dword ptr [r15]
0x18001f704  lea     rcx, [rsp+98h+var_78]
0x18001f709  call    ??E?$CTPLiteSListIterator@VCHashValueStringList@@V?$CTPKeyedLiteSList@VCStringHashKey@@VCHashValueStringList@@@@@@QEAAPEAVCHashValueStringList@@XZ; CTPLiteSListIterator<CHashValueStringList,CTPKeyedLiteSList<CStringHashKey,CHashValueStringList>>::operator++(void)
0x18001f70e  test    edi, edi
0x18001f710  jns     loc_18001F65E
0x18001f716  mov     eax, edi
0x18001f718  add     rsp, 58h
0x18001f71c  pop     r15
0x18001f71e  pop     r14
0x18001f720  pop     r13
0x18001f722  pop     r12
0x18001f724  pop     rdi
0x18001f725  pop     rsi
0x18001f726  pop     rbp
0x18001f727  pop     rbx
0x18001f728  retn
```
