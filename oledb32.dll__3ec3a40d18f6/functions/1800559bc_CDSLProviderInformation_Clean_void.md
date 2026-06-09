# CDSLProviderInformation::Clean(void)

- ea: `0x1800559bc`
- end: `0x180055a9f`
- name: `?Clean@CDSLProviderInformation@@QEAAXXZ`
- size: `227`
- prototype: `void __fastcall(CDSLProviderInformation *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x18004a7b0`
- `0x18004baa0`

## callees

- `0x180011bcc`
- `0x180051efc`
- `0x180055520`
- `0x1800559bc`
- `0x18005640c`
- `0x180087010`

## import_xrefs

- `MSDART!mpFree` at `0x180055a75`
- `MSDART!mpFree` at `0x180055a75`
- `ole32!CoTaskMemFree` at `0x180055a33`
- `ole32!CoTaskMemFree` at `0x180055a51`
- `ole32!CoTaskMemFree` at `0x180055a86`
- `ole32!CoTaskMemFree` at `0x180055a33`
- `ole32!CoTaskMemFree` at `0x180055a51`
- `ole32!CoTaskMemFree` at `0x180055a86`

## pseudocode

```c
void __fastcall CDSLProviderInformation::Clean(CDSLProviderInformation *this)
{
  CDSLPageHolder *v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  CCMProviderInfo *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  __int64 i; // rdi

  v2 = (CDSLPageHolder *)*((_QWORD *)this + 10);
  if ( v2 )
  {
    if ( *((_QWORD *)v2 - 1) )
      CDSLPageHolder::`vector deleting destructor'(v2, 3u);
    else
      operator delete((char *)v2 - 8);
  }
  v3 = *((_QWORD *)this + 12);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  *((_QWORD *)this + 12) = 0;
  TDSLSetArray<CDSLPropertySupplementSet,CDSLPropertySupplement>::Free((char *)this + 16);
  v7 = (CCMProviderInfo *)*((_QWORD *)this + 1);
  if ( v7 )
  {
    CCMProviderInfo::Release(v7);
    *((_QWORD *)this + 1) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 5);
  if ( v8 )
  {
    CoTaskMemFree(v8);
    *((_QWORD *)this + 5) = 0;
    *((_DWORD *)this + 12) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 7);
  if ( v9 )
  {
    CoTaskMemFree(v9);
    *((_QWORD *)this + 7) = 0;
  }
  if ( *((_QWORD *)this + 8) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 18); i = (unsigned int)(i + 1) )
      mpFree(*(_QWORD *)(*((_QWORD *)this + 8) + 8 * i), v4, v5, v6);
    CoTaskMemFree(*((LPVOID *)this + 8));
    *((_QWORD *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x1800559bc  mov     [rsp+arg_0], rbx
0x1800559c1  push    rdi
0x1800559c2  sub     rsp, 20h
0x1800559c6  mov     rbx, rcx
0x1800559c9  mov     rcx, [rcx+50h]; this
0x1800559cd  test    rcx, rcx
0x1800559d0  jz      short loc_1800559EE
0x1800559d2  cmp     qword ptr [rcx-8], 0
0x1800559d7  jz      short loc_1800559E5
0x1800559d9  mov     edx, 3; unsigned int
0x1800559de  call    ??_ECDSLPageHolder@@UEAAPEAXI@Z; CDSLPageHolder::`vector deleting destructor'(uint)
0x1800559e3  jmp     short loc_1800559EE
0x1800559e5  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1800559e9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800559ee  mov     rcx, [rbx+60h]
0x1800559f2  test    rcx, rcx
0x1800559f5  jz      short loc_180055A03
0x1800559f7  mov     rax, [rcx]
0x1800559fa  mov     rax, [rax+10h]
0x1800559fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055a03  lea     rcx, [rbx+10h]
0x180055a07  mov     qword ptr [rbx+60h], 0
0x180055a0f  call    ?Free@?$TDSLSetArray@VCDSLPropertySupplementSet@@VCDSLPropertySupplement@@@@QEAAXH@Z; TDSLSetArray<CDSLPropertySupplementSet,CDSLPropertySupplement>::Free(int)
0x180055a14  mov     rcx, [rbx+8]; this
0x180055a18  test    rcx, rcx
0x180055a1b  jz      short loc_180055A2A
0x180055a1d  call    ?Release@CCMProviderInfo@@QEAAKXZ; CCMProviderInfo::Release(void)
0x180055a22  mov     qword ptr [rbx+8], 0
0x180055a2a  mov     rcx, [rbx+28h]; pv
0x180055a2e  test    rcx, rcx
0x180055a31  jz      short loc_180055A48
0x180055a33  call    cs:__imp_CoTaskMemFree
0x180055a39  mov     qword ptr [rbx+28h], 0
0x180055a41  mov     dword ptr [rbx+30h], 0
0x180055a48  mov     rcx, [rbx+38h]; pv
0x180055a4c  test    rcx, rcx
0x180055a4f  jz      short loc_180055A5F
0x180055a51  call    cs:__imp_CoTaskMemFree
0x180055a57  mov     qword ptr [rbx+38h], 0
0x180055a5f  cmp     qword ptr [rbx+40h], 0
0x180055a64  jz      short loc_180055A94
0x180055a66  xor     edi, edi
0x180055a68  cmp     [rbx+48h], edi
0x180055a6b  jbe     short loc_180055A82
0x180055a6d  mov     rcx, [rbx+40h]
0x180055a71  mov     rcx, [rcx+rdi*8]
0x180055a75  call    cs:__imp_mpFree
0x180055a7b  inc     edi
0x180055a7d  cmp     edi, [rbx+48h]
0x180055a80  jb      short loc_180055A6D
0x180055a82  mov     rcx, [rbx+40h]; pv
0x180055a86  call    cs:__imp_CoTaskMemFree
0x180055a8c  mov     qword ptr [rbx+40h], 0
0x180055a94  mov     rbx, [rsp+28h+arg_0]
0x180055a99  add     rsp, 20h
0x180055a9d  pop     rdi
0x180055a9e  retn
```
