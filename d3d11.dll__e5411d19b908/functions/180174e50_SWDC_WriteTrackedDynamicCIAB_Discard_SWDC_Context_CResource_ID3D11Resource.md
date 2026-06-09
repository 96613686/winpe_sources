# SWDC_WriteTrackedDynamicCIAB::Discard(SWDC_Context *,CResource<ID3D11Resource> *)

- ea: `0x180174e50`
- end: `0x180175051`
- name: `?Discard@SWDC_WriteTrackedDynamicCIAB@@QEAAPEAXPEAUSWDC_Context@@PEAV?$CResource@UID3D11Resource@@@@@Z`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1801746f4`

## callees

- `0x1800dd664`
- `0x1801457e4`
- `0x180174e50`
- `0x1801750c0`
- `0x1801754b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180174efc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180174efc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180174edd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180174edd`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180174fe7`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180174fe7`
- `api-ms-win-core-memory-l1-1-1!ResetWriteWatch` at `0x180174f70`
- `api-ms-win-core-memory-l1-1-1!ResetWriteWatch` at `0x180174f70`

## pseudocode

```c
char *__fastcall SWDC_WriteTrackedDynamicCIAB::Discard(__int64 a1, struct SWDC_Context *a2, __int64 a3)
{
  __int64 v6; // r15
  int v7; // edi
  char *v8; // rbx
  SIZE_T v9; // rdi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  char **v13; // rax
  __int64 v14; // rax
  __int64 v15; // r12
  unsigned int v16; // edx
  unsigned int v17; // r14d
  char *v18; // r8
  unsigned __int64 v19; // rdi
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // r9
  __int128 v23; // [rsp+20h] [rbp-58h] BYREF
  _QWORD pExceptionObject[4]; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v25; // [rsp+80h] [rbp+8h]

  v6 = *(_QWORD *)(a3 + 240);
  v7 = *(_DWORD *)(a3 + 328);
  LODWORD(v25) = v7;
  SWDC_WriteTrackedDynamicCIAB::FinalizeTracking((SWDC_WriteTrackedDynamicCIAB *)a1, a2);
  v8 = *(char **)(a1 + 24);
  if ( v8 )
  {
    v9 = *(_QWORD *)(a1 + 32);
  }
  else
  {
    v9 = v7 + dword_18022BA30 - 1 - (v7 + dword_18022BA30 - 1) % (unsigned int)dword_18022BA30;
    v10 = (_QWORD *)((char *)a2 + 200);
    v23 = 0;
    v11 = *((_QWORD *)a2 + 26);
    if ( v11 == *((_QWORD *)a2 + 27) )
      std::vector<std::pair<void *,CResource<ID3D11Resource> *>>::_Emplace_reallocate<std::pair<void *,CResource<ID3D11Resource> *>>(
        v10,
        v11,
        &v23);
    else
      std::vector<std::pair<void *,CResource<ID3D11Resource> *>>::_Emplace_back_with_unused_capacity<std::pair<void *,CResource<ID3D11Resource> *>>(
        v10,
        &v23);
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
    v12 = *(_QWORD *)(v6 + 56);
    if ( *(_QWORD *)(v6 + 48) != v12 )
    {
      v13 = (char **)(v12 - 8);
      v8 = *v13;
      *(_QWORD *)(v6 + 56) = v13;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 8));
    if ( !v8 )
    {
      v8 = (char *)VirtualAlloc(0, v9, 0x203000u, 4u);
      if ( !v8 )
      {
        try
        {
          *((_QWORD *)a2 + 26) -= 16LL;
          pExceptionObject[2] = 0;
          pExceptionObject[1] = "bad allocation";
          pExceptionObject[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)pExceptionObject;
        }
        catch ( std::bad_alloc )
        {
          return 0;
        }
      }
    }
    v14 = *((_QWORD *)a2 + 26);
    *(_QWORD *)(v14 - 16) = v8;
    *(_QWORD *)(v14 - 8) = a3;
  }
  v15 = (_DWORD)v25 + dword_18022BA0C - 1 - ((int)v25 + dword_18022BA0C - 1) % (unsigned int)dword_18022BA0C;
  v16 = (*(_DWORD *)v6 + ((unsigned int)dword_18022BA0C >> 1)) % dword_18022BA0C;
  v17 = *(_DWORD *)v6 + ((unsigned int)dword_18022BA0C >> 1) - v16 - dword_18022BA0C;
  if ( *(_DWORD *)v6 + ((unsigned int)dword_18022BA0C >> 1) - v16 < dword_18022BA0C )
    v17 = *(_DWORD *)v6 + ((unsigned int)dword_18022BA0C >> 1) - v16;
  if ( v17 < (unsigned int)v25 )
    ResetWriteWatch(&v8[v17], (unsigned int)v15 - v17);
  v18 = &v8[v15];
  v19 = v9 - (unsigned int)v15;
  *(_DWORD *)(a1 + 8) = v17;
  if ( v19 < (unsigned int)v25 )
  {
    v21 = 0;
    v20 = v25;
  }
  else
  {
    v20 = v19;
    v21 = v25;
  }
  if ( v19 < (unsigned int)v25 )
    v18 = 0;
  *(_QWORD *)(a1 + 24) = v18;
  if ( v19 < (unsigned int)v25 )
    v20 = v21;
  *(_QWORD *)(a1 + 32) = v20;
  *(_QWORD *)a1 = v8;
  return v8;
}

```

## disassembly

```asm
0x180174e50  mov     [rsp+arg_8], rbx
0x180174e55  mov     [rsp+arg_10], rsi
0x180174e5a  push    rdi
0x180174e5b  push    r12
0x180174e5d  push    r13
0x180174e5f  push    r14
0x180174e61  push    r15
0x180174e63  sub     rsp, 50h
0x180174e67  mov     r13, r8
0x180174e6a  mov     r14, rdx
0x180174e6d  mov     rsi, rcx
0x180174e70  mov     r15, [r8+0F0h]
0x180174e77  mov     edi, [r8+148h]
0x180174e7e  mov     dword ptr [rsp+78h+arg_0], edi
0x180174e85  call    ?FinalizeTracking@SWDC_WriteTrackedDynamicCIAB@@QEAAXPEAUSWDC_Context@@@Z; SWDC_WriteTrackedDynamicCIAB::FinalizeTracking(SWDC_Context *)
0x180174e8a  mov     rbx, [rsi+18h]
0x180174e8e  test    rbx, rbx
0x180174e91  jnz     loc_180175048
0x180174e97  mov     ecx, cs:dword_18022BA30
0x180174e9d  lea     r8d, [rcx-1]
0x180174ea1  add     r8d, edi
0x180174ea4  xor     edx, edx
0x180174ea6  mov     eax, r8d
0x180174ea9  div     ecx
0x180174eab  sub     r8d, edx
0x180174eae  mov     edi, r8d
0x180174eb1  lea     rcx, [r14+0C8h]
0x180174eb8  xorps   xmm0, xmm0
0x180174ebb  movdqu  [rsp+78h+var_58], xmm0
0x180174ec1  mov     rdx, [rcx+8]
0x180174ec5  cmp     rdx, [rcx+10h]
0x180174ec9  jz      loc_180175032
0x180174ecf  lea     rdx, [rsp+78h+var_58]
0x180174ed4  call    ??$_Emplace_back_with_unused_capacity@U?$pair@PEAXPEAV?$CResource@UID3D11Resource@@@@@std@@@?$vector@U?$pair@PEAXPEAV?$CResource@UID3D11Resource@@@@@std@@V?$allocator@U?$pair@PEAXPEAV?$CResource@UID3D11Resource@@@@@std@@@2@@std@@AEAAAEAU?$pair@PEAXPEAV?$CResource@UID3D11Resource@@@@@1@$$QEAU21@@Z; std::vector<std::pair<void *,CResource<ID3D11Resource> *>>::_Emplace_back_with_unused_capacity<std::pair<void *,CResource<ID3D11Resource> *>>(std::pair<void *,CResource<ID3D11Resource> *> &&)
0x180174ed9  lea     rcx, [r15+8]; lpCriticalSection
0x180174edd  call    cs:__imp_EnterCriticalSection
0x180174ee3  mov     rax, [r15+38h]
0x180174ee7  cmp     [r15+30h], rax
0x180174eeb  jz      short loc_180174EF8
0x180174eed  add     rax, 0FFFFFFFFFFFFFFF8h
0x180174ef1  mov     rbx, [rax]
0x180174ef4  mov     [r15+38h], rax
0x180174ef8  lea     rcx, [r15+8]; lpCriticalSection
0x180174efc  call    cs:__imp_LeaveCriticalSection
0x180174f02  test    rbx, rbx
0x180174f05  jz      loc_180174FD6
0x180174f0b  mov     rax, [r14+0D0h]
0x180174f12  mov     [rax-10h], rbx
0x180174f16  mov     [rax-8], r13
0x180174f1a  mov     r9d, cs:dword_18022BA0C
0x180174f21  mov     r13d, dword ptr [rsp+78h+arg_0]
0x180174f29  lea     r12d, [r9-1]
0x180174f2d  add     r12d, r13d
0x180174f30  xor     edx, edx
0x180174f32  mov     eax, r12d
0x180174f35  div     r9d
0x180174f38  sub     r12d, edx
0x180174f3b  mov     r8d, r9d
0x180174f3e  shr     r8d, 1
0x180174f41  mov     eax, [r15]
0x180174f44  add     r8d, eax
0x180174f47  xor     edx, edx
0x180174f49  mov     eax, r8d
0x180174f4c  div     r9d
0x180174f4f  sub     r8d, edx
0x180174f52  mov     r14d, r8d
0x180174f55  sub     r14d, r9d
0x180174f58  cmp     r8d, r9d
0x180174f5b  cmovb   r14d, r8d
0x180174f5f  cmp     r14d, r13d
0x180174f62  jnb     short loc_180174F76
0x180174f64  mov     edx, r12d
0x180174f67  sub     edx, r14d; dwRegionSize
0x180174f6a  mov     ecx, r14d
0x180174f6d  add     rcx, rbx; lpBaseAddress
0x180174f70  call    cs:__imp_ResetWriteWatch
0x180174f76  mov     eax, r12d
0x180174f79  lea     r8, [r12+rbx]
0x180174f7d  sub     rdi, rax
0x180174f80  mov     [rsi+8], r14d
0x180174f84  cmp     rdi, r13
0x180174f87  jb      short loc_180174FC9
0x180174f89  mov     rax, rdi
0x180174f8c  mov     r9, [rsp+78h+arg_0]
0x180174f94  xor     ecx, ecx
0x180174f96  cmp     rdi, r13
0x180174f99  cmovb   r8, rcx
0x180174f9d  mov     [rsi+18h], r8
0x180174fa1  cmovb   rax, r9
0x180174fa5  mov     [rsi+20h], rax
0x180174fa9  mov     [rsi], rbx
0x180174fac  mov     rax, rbx
0x180174faf  lea     r11, [rsp+78h+var_28]
0x180174fb4  mov     rbx, [r11+38h]
0x180174fb8  mov     rsi, [r11+40h]
0x180174fbc  mov     rsp, r11
0x180174fbf  pop     r15
0x180174fc1  pop     r14
0x180174fc3  pop     r13
0x180174fc5  pop     r12
0x180174fc7  pop     rdi
0x180174fc8  retn
0x180174fc9  xor     r9d, r9d
0x180174fcc  mov     rax, [rsp+78h+arg_0]
0x180174fd4  jmp     short loc_180174F94
0x180174fd6  mov     r9d, 4; flProtect
0x180174fdc  mov     r8d, 203000h; flAllocationType
0x180174fe2  mov     rdx, rdi; dwSize
0x180174fe5  xor     ecx, ecx; lpAddress
0x180174fe7  call    cs:__imp_VirtualAlloc
0x180174fed  mov     rbx, rax
0x180174ff0  test    rax, rax
0x180174ff3  jnz     loc_180174F0B
0x180174ff9  add     qword ptr [r14+0D0h], 0FFFFFFFFFFFFFFF0h
0x180175001  xorps   xmm0, xmm0
0x180175004  movups  [rsp+78h+var_40], xmm0
0x180175009  lea     rax, aBadAllocation; "bad allocation"
0x180175010  mov     qword ptr [rsp+78h+var_40], rax
0x180175015  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18017501c  mov     [rsp+78h+pExceptionObject], rax
0x180175021  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180175028  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18017502d  call    _CxxThrowException_0
0x180175032  lea     r8, [rsp+78h+var_58]
0x180175037  call    ??$_Emplace_reallocate@U?$pair@PEAXPEAV?$CResource@UID3D11Resource@@@@@std@@@?$vector@U?$pair@PEAXPEAV?$CResource@UID3D11Resource@@@@@std@@V?$allocator@U?$pair@PEAXPEAV?$CResource@UID3D11Resource@@@@@std@@@2@@std@@AEAAPEAU?$pair@PEAXPEAV?$CResource@UID3D11Resource@@@@@1@QEAU21@$$QEAU21@@Z; std::vector<std::pair<void *,CResource<ID3D11Resource> *>>::_Emplace_reallocate<std::pair<void *,CResource<ID3D11Resource> *>>(std::pair<void *,CResource<ID3D11Resource> *> * const,std::pair<void *,CResource<ID3D11Resource> *> &&)
0x18017503c  jmp     loc_180174ED9
0x180175041  xor     eax, eax
0x180175043  jmp     loc_180174FAF
0x180175048  mov     rdi, [rsi+20h]
0x18017504c  jmp     loc_180174F1A
```
