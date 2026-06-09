# CSyncMLDPU::~CSyncMLDPU(void)

- ea: `0x180004b00`
- end: `0x180004eef`
- name: `??1CSyncMLDPU@@QEAA@XZ`
- size: `1007`
- prototype: `void __fastcall(CSyncMLDPU *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003b10`

## callees

- `0x180002c90`
- `0x180004b00`
- `0x180010ae8`
- `0x180014330`
- `0x1800146e4`
- `0x1800193fc`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180004c38`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180004c38`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004d1c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180004d1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ba6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004b93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ba6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004bdf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004d36`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004d36`

## pseudocode

```c
void __fastcall CSyncMLDPU::~CSyncMLDPU(CSyncMLDPU *this)
{
  unsigned int v2; // ebx
  __int64 v3; // rsi
  __int64 v4; // rcx
  struct CSyncMLCmd **v5; // rbx
  struct CSyncMLCmd **i; // rsi
  __int64 v7; // rcx
  char **v8; // rbx
  char **j; // rsi
  unsigned __int64 v10; // rdx
  char *v11; // rax
  const struct std::nothrow_t *v12; // rdx
  char *v13; // rcx
  __int64 v14; // rax
  const struct std::nothrow_t *v15; // rdx
  void *v16; // rcx
  __int64 v17; // rax
  const struct std::nothrow_t *v18; // rdx
  void *v19; // rcx
  __int64 v20; // rcx
  const struct std::nothrow_t *v21; // rdx
  void *v22; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-40h] BYREF
  char *v25; // [rsp+58h] [rbp-30h]
  int v26; // [rsp+60h] [rbp-28h]
  int v27; // [rsp+64h] [rbp-24h]

  *(_QWORD *)this = &CSyncMLDPU::`vftable'{for `CProvisioningDPU'};
  *((_QWORD *)this + 2) = &CSyncMLDPU::`vftable'{for `IProvisioningSyncMlDPU'};
  CSyncMLDPU::FreePerPkgState(this);
  if ( *((_DWORD *)this + 62) )
  {
    v2 = 0;
    do
    {
      v3 = 8LL * v2;
      v4 = *((_QWORD *)this + 37);
      if ( *(_QWORD *)(v4 + v3) )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v4 + 8LL * v2) + 16LL))(*(_QWORD *)(v4 + 8LL * v2));
        *(_QWORD *)(v3 + *((_QWORD *)this + 37)) = 0;
      }
      ++v2;
    }
    while ( v2 < *((_DWORD *)this + 62) );
    LocalFree(*((HLOCAL *)this + 37));
  }
  LocalFree(*((HLOCAL *)this + 41));
  LocalFree(*((HLOCAL *)this + 42));
  LocalFree(*((HLOCAL *)this + 43));
  LocalFree(*((HLOCAL *)this + 54));
  v5 = (struct CSyncMLCmd **)*((_QWORD *)this + 10);
  for ( i = (struct CSyncMLCmd **)*((_QWORD *)this + 9); i != v5; ++i )
    CSyncMLCmd::DeallocCmd(*i);
  v7 = *((_QWORD *)this + 8);
  if ( v7 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 40LL))(v7, 1);
  if ( byte_18003ED5C )
    EventActivityIdControl(4u, &ActivityId);
  SyncMLDpuActivity = 2;
  if ( (unsigned int)dword_18003E048 > 5
    && (qword_18003E058 & 0x200000000000LL) != 0
    && (qword_18003E060 & 0x200000000000LL) == qword_18003E060 )
  {
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 517;
    EventDescriptor.Keyword = 0x200000000000LL;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    UserData.Size = (unsigned __int16)*off_18003E050;
    UserData.Reserved = 2;
    v25 = &byte_180035F87;
    v26 = 21;
    v27 = 1;
    EventWriteTransfer(RegHandle, &EventDescriptor, &stru_18003ED60, 0, 2u, &UserData);
  }
  _InterlockedDecrement(&dword_18003EBFC);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 472));
  v8 = (char **)*((_QWORD *)this + 56);
  if ( v8 )
  {
    for ( j = (char **)*((_QWORD *)this + 57); v8 != j; v8 += 4 )
    {
      v10 = (unsigned __int64)v8[3];
      if ( v10 > 7 )
      {
        v11 = *v8;
        v12 = (const struct std::nothrow_t *)(2 * v10 + 2);
        if ( (unsigned __int64)v12 < 0x1000 )
        {
          v13 = *v8;
        }
        else
        {
          v13 = (char *)*((_QWORD *)v11 - 1);
          if ( (unsigned __int64)(v11 - v13 - 8) > 0x1F )
            goto LABEL_41;
          v12 = (const struct std::nothrow_t *)((char *)v12 + 39);
        }
        operator delete(v13, v12);
      }
      v8[2] = 0;
      v8[3] = (char *)7;
      *(_WORD *)v8 = 0;
    }
    v14 = *((_QWORD *)this + 56);
    v15 = (const struct std::nothrow_t *)((*((_QWORD *)this + 58) - v14) & 0xFFFFFFFFFFFFFFE0uLL);
    if ( (unsigned __int64)v15 < 0x1000 )
    {
      v16 = (void *)*((_QWORD *)this + 56);
    }
    else
    {
      v16 = *(void **)(v14 - 8);
      if ( (unsigned __int64)(v14 - (_QWORD)v16 - 8) > 0x1F )
        goto LABEL_41;
      v15 = (const struct std::nothrow_t *)((char *)v15 + 39);
    }
    operator delete(v16, v15);
    *((_QWORD *)this + 56) = 0;
    *((_QWORD *)this + 57) = 0;
    *((_QWORD *)this + 58) = 0;
  }
  std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((char *)this + 360);
  v17 = *((_QWORD *)this + 38);
  if ( v17 )
  {
    v18 = (const struct std::nothrow_t *)((*((_QWORD *)this + 40) - v17) & 0xFFFFFFFFFFFFFFF0uLL);
    if ( (unsigned __int64)v18 < 0x1000 )
    {
      v19 = (void *)*((_QWORD *)this + 38);
    }
    else
    {
      v19 = *(void **)(v17 - 8);
      if ( (unsigned __int64)(v17 - (_QWORD)v19 - 8) > 0x1F )
        goto LABEL_41;
      v18 = (const struct std::nothrow_t *)((char *)v18 + 39);
    }
    operator delete(v19, v18);
    *((_QWORD *)this + 38) = 0;
    *((_QWORD *)this + 39) = 0;
    *((_QWORD *)this + 40) = 0;
  }
  v20 = *((_QWORD *)this + 9);
  if ( !v20 )
    return;
  v21 = (const struct std::nothrow_t *)(8 * ((*((_QWORD *)this + 11) - v20) >> 3));
  if ( (unsigned __int64)v21 < 0x1000 )
  {
    v22 = (void *)*((_QWORD *)this + 9);
    goto LABEL_43;
  }
  v22 = *(void **)(v20 - 8);
  if ( (unsigned __int64)(v20 - (_QWORD)v22 - 8) > 0x1F )
LABEL_41:
    __fastfail(5u);
  v21 = (const struct std::nothrow_t *)((char *)v21 + 39);
LABEL_43:
  operator delete(v22, v21);
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
}

```

## disassembly

```asm
0x180004b00  mov     [rsp+arg_8], rbx
0x180004b05  mov     [rsp+arg_10], rbp
0x180004b0a  push    rsi
0x180004b0b  push    rdi
0x180004b0c  push    r14
0x180004b0e  sub     rsp, 70h
0x180004b12  mov     rax, cs:__security_cookie
0x180004b19  xor     rax, rsp
0x180004b1c  mov     [rsp+88h+var_20], rax
0x180004b21  mov     rdi, rcx
0x180004b24  lea     rax, ??_7CSyncMLDPU@@6BCProvisioningDPU@@@; const CSyncMLDPU::`vftable'{for `CProvisioningDPU'}
0x180004b2b  mov     [rcx], rax
0x180004b2e  lea     rax, ??_7CSyncMLDPU@@6BIProvisioningSyncMlDPU@@@; const CSyncMLDPU::`vftable'{for `IProvisioningSyncMlDPU'}
0x180004b35  mov     [rcx+10h], rax
0x180004b39  call    ?FreePerPkgState@CSyncMLDPU@@AEAAXXZ; CSyncMLDPU::FreePerPkgState(void)
0x180004b3e  mov     eax, [rdi+0F8h]
0x180004b44  xor     ebp, ebp
0x180004b46  test    eax, eax
0x180004b48  jz      short loc_180004B9F
0x180004b4a  mov     ebx, ebp
0x180004b4c  nop     dword ptr [rax+00h]
0x180004b50  mov     eax, ebx
0x180004b52  lea     rsi, ds:0[rax*8]
0x180004b5a  mov     rcx, [rdi+128h]
0x180004b61  cmp     [rcx+rsi], rbp
0x180004b65  jz      short loc_180004B82
0x180004b67  mov     rcx, [rcx+rsi]
0x180004b6b  mov     rax, [rcx]
0x180004b6e  mov     rax, [rax+10h]
0x180004b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b77  mov     rax, [rdi+128h]
0x180004b7e  mov     [rsi+rax], rbp
0x180004b82  inc     ebx
0x180004b84  cmp     ebx, [rdi+0F8h]
0x180004b8a  jb      short loc_180004B50
0x180004b8c  mov     rcx, [rdi+128h]; hMem
0x180004b93  call    cs:__imp_LocalFree
0x180004b9a  nop     dword ptr [rax+rax+00h]
0x180004b9f  mov     rcx, [rdi+148h]; hMem
0x180004ba6  call    cs:__imp_LocalFree
0x180004bad  nop     dword ptr [rax+rax+00h]
0x180004bb2  mov     rcx, [rdi+150h]; hMem
0x180004bb9  call    cs:__imp_LocalFree
0x180004bc0  nop     dword ptr [rax+rax+00h]
0x180004bc5  mov     rcx, [rdi+158h]; hMem
0x180004bcc  call    cs:__imp_LocalFree
0x180004bd3  nop     dword ptr [rax+rax+00h]
0x180004bd8  mov     rcx, [rdi+1B0h]; hMem
0x180004bdf  call    cs:__imp_LocalFree
0x180004be6  nop     dword ptr [rax+rax+00h]
0x180004beb  mov     rbx, [rdi+50h]
0x180004bef  mov     rsi, [rdi+48h]
0x180004bf3  cmp     rsi, rbx
0x180004bf6  jz      short loc_180004C09
0x180004bf8  mov     rcx, [rsi]; struct CSyncMLCmd *
0x180004bfb  call    ?DeallocCmd@CSyncMLCmd@@SAXPEAV1@@Z; CSyncMLCmd::DeallocCmd(CSyncMLCmd *)
0x180004c00  add     rsi, 8
0x180004c04  cmp     rsi, rbx
0x180004c07  jnz     short loc_180004BF8
0x180004c09  mov     rcx, [rdi+40h]
0x180004c0d  test    rcx, rcx
0x180004c10  jz      short loc_180004C23
0x180004c12  mov     rax, [rcx]
0x180004c15  mov     edx, 1
0x180004c1a  mov     rax, [rax+28h]
0x180004c1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c23  cmp     cs:byte_18003ED5C, bpl
0x180004c2a  jz      short loc_180004C44
0x180004c2c  lea     rdx, ActivityId; ActivityId
0x180004c33  mov     ecx, 4; ControlCode
0x180004c38  call    cs:__imp_EventActivityIdControl
0x180004c3f  nop     dword ptr [rax+rax+00h]
0x180004c44  mov     cs:?SyncMLDpuActivity@@3V?$TraceLoggingThreadActivity@$1?g_hSyncMLTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@A, 2; TraceLoggingThreadActivity<&_tlgProvider_t const * const g_hSyncMLTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider> SyncMLDpuActivity
0x180004c4e  mov     eax, cs:dword_18003E048
0x180004c54  cmp     eax, 5
0x180004c57  jbe     loc_180004D28
0x180004c5d  mov     rcx, cs:qword_18003E060
0x180004c64  mov     rax, cs:qword_18003E058
0x180004c6b  mov     rdx, 200000000000h
0x180004c75  test    rdx, rax
0x180004c78  jz      loc_180004D28
0x180004c7e  mov     rax, rcx
0x180004c81  and     rax, rdx
0x180004c84  cmp     rax, rcx
0x180004c87  jnz     loc_180004D28
0x180004c8d  mov     dword ptr [rsp+88h+EventDescriptor.Id], 0B000000h
0x180004c95  movzx   eax, cs:word_180035F7D
0x180004c9c  mov     dword ptr [rsp+88h+EventDescriptor.Level], eax
0x180004ca0  mov     [rsp+88h+EventDescriptor.Keyword], rdx
0x180004ca5  mov     rax, cs:off_18003E050
0x180004cac  mov     [rsp+88h+var_40.Ptr], rax
0x180004cb1  movzx   eax, word ptr [rax]
0x180004cb4  mov     [rsp+88h+var_40.Size], eax
0x180004cb8  mov     dword ptr [rsp+88h+var_40.0Ch], 2
0x180004cc0  lea     rax, byte_180035F87
0x180004cc7  mov     [rsp+88h+var_30], rax
0x180004ccc  mov     [rsp+88h+var_28], 15h
0x180004cd4  mov     [rsp+88h+var_24], 1
0x180004cdc  lea     rax, _TraceLoggingMetadataEnd
0x180004ce3  lea     rcx, _TraceLoggingMetadata
0x180004cea  sub     eax, ecx
0x180004cec  mov     [rsp+88h+var_58], eax
0x180004cf0  mov     eax, [rsp+88h+var_58]
0x180004cf4  lea     rax, [rsp+88h+var_40]
0x180004cf9  mov     [rsp+88h+UserData], rax; UserData
0x180004cfe  mov     [rsp+88h+UserDataCount], 2; UserDataCount
0x180004d06  xor     r9d, r9d; RelatedActivityId
0x180004d09  lea     r8, stru_18003ED60; ActivityId
0x180004d10  lea     rdx, [rsp+88h+EventDescriptor]; EventDescriptor
0x180004d15  mov     rcx, cs:RegHandle; RegHandle
0x180004d1c  call    cs:__imp_EventWriteTransfer
0x180004d23  nop     dword ptr [rax+rax+00h]
0x180004d28  lock dec cs:dword_18003EBFC
0x180004d2f  lea     rcx, [rdi+1D8h]; lpCriticalSection
0x180004d36  call    cs:__imp_DeleteCriticalSection
0x180004d3d  nop     dword ptr [rax+rax+00h]
0x180004d42  mov     rbx, [rdi+1C0h]
0x180004d49  test    rbx, rbx
0x180004d4c  jz      loc_180004E0F
0x180004d52  mov     rsi, [rdi+1C8h]
0x180004d59  cmp     rbx, rsi
0x180004d5c  jz      short loc_180004DB9
0x180004d5e  xchg    ax, ax
0x180004d60  mov     rdx, [rbx+18h]
0x180004d64  cmp     rdx, 7
0x180004d68  jbe     short loc_180004DA1
0x180004d6a  mov     rax, [rbx]
0x180004d6d  lea     rdx, ds:2[rdx*2]; struct std::nothrow_t *
0x180004d75  cmp     rdx, 1000h
0x180004d7c  jb      short loc_180004D99
0x180004d7e  mov     rcx, [rax-8]
0x180004d82  sub     rax, rcx
0x180004d85  sub     rax, 8
0x180004d89  cmp     rax, 1Fh
0x180004d8d  ja      loc_180004EAE
0x180004d93  add     rdx, 27h ; '''
0x180004d97  jmp     short loc_180004D9C
0x180004d99  mov     rcx, rax; void *
0x180004d9c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004da1  mov     [rbx+10h], rbp
0x180004da5  mov     qword ptr [rbx+18h], 7
0x180004dad  mov     [rbx], bp
0x180004db0  add     rbx, 20h ; ' '
0x180004db4  cmp     rbx, rsi
0x180004db7  jnz     short loc_180004D60
0x180004db9  mov     rax, [rdi+1C0h]
0x180004dc0  mov     rdx, [rdi+1D0h]
0x180004dc7  sub     rdx, rax
0x180004dca  and     rdx, 0FFFFFFFFFFFFFFE0h; struct std::nothrow_t *
0x180004dce  cmp     rdx, 1000h
0x180004dd5  jb      short loc_180004DF2
0x180004dd7  mov     rcx, [rax-8]
0x180004ddb  sub     rax, rcx
0x180004dde  sub     rax, 8
0x180004de2  cmp     rax, 1Fh
0x180004de6  ja      loc_180004EAE
0x180004dec  add     rdx, 27h ; '''
0x180004df0  jmp     short loc_180004DF5
0x180004df2  mov     rcx, rax; void *
0x180004df5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004dfa  mov     [rdi+1C0h], rbp
0x180004e01  mov     [rdi+1C8h], rbp
0x180004e08  mov     [rdi+1D0h], rbp
0x180004e0f  lea     rcx, [rdi+168h]
0x180004e16  call    ??1?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180004e1b  mov     rax, [rdi+130h]
0x180004e22  test    rax, rax
0x180004e25  jz      short loc_180004E72
0x180004e27  mov     rdx, [rdi+140h]
0x180004e2e  sub     rdx, rax
0x180004e31  and     rdx, 0FFFFFFFFFFFFFFF0h; struct std::nothrow_t *
0x180004e35  cmp     rdx, 1000h
0x180004e3c  jb      short loc_180004E55
0x180004e3e  mov     rcx, [rax-8]
0x180004e42  sub     rax, rcx
0x180004e45  sub     rax, 8
0x180004e49  cmp     rax, 1Fh
0x180004e4d  ja      short loc_180004EAE
0x180004e4f  add     rdx, 27h ; '''
0x180004e53  jmp     short loc_180004E58
0x180004e55  mov     rcx, rax; void *
0x180004e58  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004e5d  mov     [rdi+130h], rbp
0x180004e64  mov     [rdi+138h], rbp
0x180004e6b  mov     [rdi+140h], rbp
0x180004e72  mov     rcx, [rdi+48h]
0x180004e76  test    rcx, rcx
0x180004e79  jz      short loc_180004ECC
0x180004e7b  mov     rax, [rdi+58h]
0x180004e7f  sub     rax, rcx
0x180004e82  sar     rax, 3
0x180004e86  lea     rdx, ds:0[rax*8]; struct std::nothrow_t *
0x180004e8e  cmp     rdx, 1000h
0x180004e95  jb      short loc_180004EB5
0x180004e97  mov     rax, [rcx-8]
0x180004e9b  sub     rcx, rax
0x180004e9e  sub     rcx, 8
0x180004ea2  cmp     rcx, 1Fh
0x180004ea6  ja      short loc_180004EAE
0x180004ea8  add     rdx, 27h ; '''
0x180004eac  jmp     short loc_180004EB8
0x180004eae  mov     ecx, 5
0x180004eb3  int     29h; Win8: RtlFailFast(ecx)
0x180004eb5  mov     rax, rcx
0x180004eb8  mov     rcx, rax; void *
0x180004ebb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004ec0  mov     [rdi+48h], rbp
0x180004ec4  mov     [rdi+50h], rbp
0x180004ec8  mov     [rdi+58h], rbp
0x180004ecc  mov     rcx, [rsp+88h+var_20]
0x180004ed1  xor     rcx, rsp; StackCookie
0x180004ed4  call    __security_check_cookie
0x180004ed9  lea     r11, [rsp+88h+var_18]
0x180004ede  mov     rbx, [r11+28h]
0x180004ee2  mov     rbp, [r11+30h]
0x180004ee6  mov     rsp, r11
0x180004ee9  pop     r14
0x180004eeb  pop     rdi
0x180004eec  pop     rsi
0x180004eed  retn
```
