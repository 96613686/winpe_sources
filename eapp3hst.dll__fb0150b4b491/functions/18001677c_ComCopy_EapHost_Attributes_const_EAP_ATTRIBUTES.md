# ComCopy(EapHost::Attributes const &,_EAP_ATTRIBUTES &)

- ea: `0x18001677c`
- end: `0x1800168b9`
- name: `?ComCopy@@YAXAEBVAttributes@EapHost@@AEAU_EAP_ATTRIBUTES@@@Z`
- size: `317`
- prototype: `void __fastcall(const struct EapHost::Attributes *, struct _EAP_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007de0`
- `0x1800168c0`

## callees

- `0x18000213c`
- `0x180005894`
- `0x18001677c`
- `0x18002f4a4`
- `0x18002f4c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800167a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800167a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016802`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016850`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001686c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016850`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001686c`

## pseudocode

```c
void __fastcall ComCopy(const struct EapHost::Attributes *a1, struct _EAP_ATTRIBUTES *a2)
{
  unsigned __int64 v4; // rcx
  SIZE_T v5; // rbx
  EAP_ATTRIBUTE *v6; // rax
  int i; // ebx
  __int64 v8; // r14
  EAP_ATTRIBUTE *pAttribs; // rax
  BYTE *pValue; // rcx
  int j; // esi
  __int64 v12; // rbx
  _QWORD pExceptionObject[9]; // [rsp+20h] [rbp-48h] BYREF

  v4 = *(unsigned int *)a1;
  v5 = 16LL * (unsigned int)v4;
  a2->dwNumberOfAttributes = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v4);
  if ( v5 )
  {
    v6 = (EAP_ATTRIBUTE *)CoTaskMemAlloc(v5);
    a2->pAttribs = v6;
    if ( v6 )
    {
      memset_0(v6, 0, v5);
      for ( i = 0; ; ++i )
      {
        if ( i >= *(_DWORD *)a1 )
          return;
        v8 = i;
        a2->pAttribs[v8].dwLength = *(_DWORD *)(*((_QWORD *)a1 + 1) + 16LL * i + 4);
        a2->pAttribs[v8].eaType = *(_DWORD *)(*((_QWORD *)a1 + 1) + 16LL * i);
        a2->pAttribs[i].pValue = (BYTE *)CoTaskMemAlloc(*(unsigned int *)(*((_QWORD *)a1 + 1) + 16LL * i + 4));
        pAttribs = a2->pAttribs;
        pValue = pAttribs[i].pValue;
        if ( !pValue )
          break;
        memcpy_0(
          pValue,
          *(const void **)(*((_QWORD *)a1 + 1) + 16LL * i + 8),
          *(unsigned int *)(*((_QWORD *)a1 + 1) + 16LL * i + 4));
      }
      if ( pAttribs )
      {
        for ( j = i - 1; j >= 0; a2->pAttribs[v12].pValue = 0 )
        {
          v12 = (unsigned int)j;
          CoTaskMemFree(a2->pAttribs[j--].pValue);
        }
        CoTaskMemFree(a2->pAttribs);
      }
    }
    pExceptionObject[2] = 0;
    pExceptionObject[1] = "bad allocation";
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    *a2 = 0;
    throw (std::bad_alloc *)pExceptionObject;
  }
  a2->pAttribs = 0;
}

```

## disassembly

```asm
0x18001677c  push    rbx
0x18001677e  push    rsi
0x18001677f  push    rdi
0x180016780  push    r14
0x180016782  sub     rsp, 48h
0x180016786  mov     rsi, rcx
0x180016789  mov     rdi, rdx
0x18001678c  mov     ecx, [rcx]
0x18001678e  mov     ebx, ecx
0x180016790  shl     rbx, 4
0x180016794  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180016799  mov     [rdi], eax
0x18001679b  test    rbx, rbx
0x18001679e  jz      loc_1800168A7
0x1800167a4  mov     rcx, rbx; cb
0x1800167a7  call    cs:__imp_CoTaskMemAlloc
0x1800167ad  mov     [rdi+8], rax
0x1800167b1  test    rax, rax
0x1800167b4  jz      loc_180016872
0x1800167ba  mov     r8, rbx; Size
0x1800167bd  xor     edx, edx; Val
0x1800167bf  mov     rcx, rax; void *
0x1800167c2  call    memset_0
0x1800167c7  xor     ebx, ebx
0x1800167c9  cmp     ebx, [rsi]
0x1800167cb  jge     loc_1800168AF
0x1800167d1  mov     rax, [rsi+8]
0x1800167d5  mov     rcx, [rdi+8]
0x1800167d9  movsxd  r14, ebx
0x1800167dc  add     r14, r14
0x1800167df  mov     eax, [rax+r14*8+4]
0x1800167e4  mov     [rcx+r14*8+4], eax
0x1800167e9  mov     rax, [rsi+8]
0x1800167ed  mov     rcx, [rdi+8]
0x1800167f1  mov     eax, [rax+r14*8]
0x1800167f5  mov     [rcx+r14*8], eax
0x1800167f9  mov     rax, [rsi+8]
0x1800167fd  mov     ecx, [rax+r14*8+4]; cb
0x180016802  call    cs:__imp_CoTaskMemAlloc
0x180016808  mov     rcx, [rdi+8]
0x18001680c  mov     [rcx+r14*8+8], rax
0x180016811  mov     rax, [rdi+8]
0x180016815  mov     rcx, [rax+r14*8+8]; void *
0x18001681a  test    rcx, rcx
0x18001681d  jz      short loc_180016836
0x18001681f  mov     rdx, [rsi+8]
0x180016823  mov     r8d, [rdx+r14*8+4]; Size
0x180016828  mov     rdx, [rdx+r14*8+8]; Src
0x18001682d  call    memcpy_0
0x180016832  inc     ebx
0x180016834  jmp     short loc_1800167C9
0x180016836  test    rax, rax
0x180016839  jz      short loc_180016872
0x18001683b  lea     esi, [rbx-1]
0x18001683e  test    esi, esi
0x180016840  js      short loc_180016868
0x180016842  mov     rcx, [rdi+8]
0x180016846  mov     ebx, esi
0x180016848  add     rbx, rbx
0x18001684b  mov     rcx, [rcx+rbx*8+8]; pv
0x180016850  call    cs:__imp_CoTaskMemFree
0x180016856  sub     esi, 1
0x180016859  mov     rax, [rdi+8]
0x18001685d  mov     qword ptr [rax+rbx*8+8], 0
0x180016866  jns     short loc_180016842
0x180016868  mov     rcx, [rdi+8]; pv
0x18001686c  call    cs:__imp_CoTaskMemFree
0x180016872  xorps   xmm0, xmm0
0x180016875  lea     rax, aBadAllocation; "bad allocation"
0x18001687c  movups  [rsp+68h+var_40], xmm0
0x180016881  mov     qword ptr [rsp+68h+var_40], rax
0x180016886  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001688d  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180016894  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180016899  mov     [rsp+68h+pExceptionObject], rax
0x18001689e  movups  xmmword ptr [rdi], xmm0
0x1800168a1  call    _CxxThrowException_0
0x1800168a7  mov     qword ptr [rdi+8], 0
0x1800168af  add     rsp, 48h
0x1800168b3  pop     r14
0x1800168b5  pop     rdi
0x1800168b6  pop     rsi
0x1800168b7  pop     rbx
0x1800168b8  retn
```
