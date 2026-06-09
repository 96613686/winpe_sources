# CExposedStream::Read(void *,ulong,ulong *)

- ea: `0x180010710`
- end: `0x180010cdc`
- name: `?Read@CExposedStream@@UEAAJPEAXKPEAK@Z`
- size: `1484`
- prototype: `__int64 __fastcall(CExposedStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180010710`
- `0x180010cf0`
- `0x180016810`
- `0x18001b840`
- `0x18002ea90`
- `0x180032aac`
- `0x180061410`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180010ac4`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x180010ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b0d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010b42`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180010b42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010789`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010948`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010789`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010948`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010aed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010c1f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010aed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180010c1f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010cd1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010cd1`

## pseudocode

```c
__int64 __fastcall CExposedStream::Read(CExposedStream *this, void *a2, unsigned int a3, unsigned int *a4)
{
  __int64 v4; // rdi
  signed int v7; // r12d
  DWORD CurrentThreadId; // esi
  signed __int32 v10; // edx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // r8d
  __int64 v16; // rbx
  int v17; // ecx
  unsigned int v18; // esi
  __int64 v19; // r13
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rdx
  PSStream *v25; // rcx
  DWORD v26; // eax
  __int64 v27; // rcx
  bool v28; // zf
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rdx
  int v32; // ecx
  int v33; // edx
  unsigned int v34; // ebx
  __int64 v35; // r12
  __int64 v36; // rax
  BOOL v37; // r13d
  __int64 *v38; // rsi
  DWORD v39; // eax
  signed int LastError; // eax
  CSmAllocator *v41; // rax
  CSmAllocator *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdi
  unsigned int v46; // eax
  void *v47; // rcx
  __int64 v48; // rax
  unsigned int v49; // [rsp+30h] [rbp-29h] BYREF
  int v50; // [rsp+34h] [rbp-25h] BYREF
  __int64 v51; // [rsp+38h] [rbp-21h] BYREF
  _QWORD *ReservedForOle; // [rsp+40h] [rbp-19h] BYREF
  __int64 v53; // [rsp+48h] [rbp-11h]
  signed int v54; // [rsp+50h] [rbp-9h] BYREF
  __int64 v55; // [rsp+58h] [rbp-1h]
  __int128 v56; // [rsp+60h] [rbp+7h]
  unsigned int v57; // [rsp+C0h] [rbp+67h] BYREF
  void *v58; // [rsp+C8h] [rbp+6Fh]
  unsigned int v59; // [rsp+D0h] [rbp+77h]
  __int64 v60; // [rsp+D8h] [rbp+7Fh] BYREF

  v59 = a3;
  v58 = a2;
  v4 = *((_QWORD *)this + 15);
  v55 = v4;
  v57 = 0;
  v7 = -2147286784;
  v56 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a3 && !a2 )
    return 2147680265LL;
  v53 = v4;
  if ( memcmp_0((char *)this + 64, &GUID_04a45d68_dba8_467d_9aed_e762432212f9, 0x10u) )
  {
    v16 = *((_QWORD *)&v56 + 1);
    v18 = -2147287034;
    v19 = v56;
    goto LABEL_23;
  }
  while ( 1 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v10 = _InterlockedExchangeAdd(*(volatile signed __int32 **)(v4 + 112), 1u);
    v11 = *(_QWORD *)(v4 + 112);
    if ( v10 == -1 )
    {
      *(_DWORD *)(v11 + 4) = 1;
LABEL_8:
      *(_DWORD *)(*(_QWORD *)(v4 + 112) + 8LL) = CurrentThreadId;
LABEL_9:
      v7 = 0;
LABEL_10:
      v12 = *(_QWORD *)(v4 + 88);
      if ( v12 )
      {
        v33 = **(_DWORD **)(v12 + 8);
        if ( v33 != *(_DWORD *)(v12 + 16) )
        {
          v7 = CSharedMemoryBlock::Commit((CSharedMemoryBlock *)v12, v33 - 24);
          if ( v7 < 0 )
            CDfMutex::Release((CDfMutex *)(v4 + 112));
        }
      }
      goto LABEL_11;
    }
    if ( *(_DWORD *)(v11 + 8) == CurrentThreadId )
    {
      ++*(_DWORD *)(v11 + 4);
      goto LABEL_9;
    }
    v39 = WaitForSingleObject(*(HANDLE *)(v4 + 120), 0x124F80u);
    if ( !v39 || v39 == 128 )
    {
      *(_DWORD *)(*(_QWORD *)(v4 + 112) + 4LL) = 1;
      goto LABEL_8;
    }
    if ( v39 == 258 )
    {
      v7 = -2147286784;
      goto LABEL_11;
    }
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 >= 0 )
      goto LABEL_10;
LABEL_11:
    v54 = v7;
    ReservedForOle = NtCurrentTeb()->ReservedForOle;
    if ( !ReservedForOle )
      InternalTlsAllocData(&ReservedForOle);
    if ( !ReservedForOle[1] )
    {
      v41 = (CSmAllocator *)HeapAlloc(g_hHeap, 0, 0x30u);
      if ( v41 )
      {
        v42 = CSmAllocator::CSmAllocator(v41);
        ReservedForOle[1] = v42;
        if ( v42 )
          goto LABEL_14;
      }
      else
      {
        ReservedForOle[1] = 0;
      }
      ReservedForOle[1] = &g_ErrorSmAllocator;
    }
LABEL_14:
    v13 = *(_QWORD *)(v4 + 88);
    v14 = *(_QWORD *)(v4 + 96);
    v15 = *(_DWORD *)(v4 + 104);
    v16 = ReservedForOle[1];
    *((_QWORD *)&v56 + 1) = v16;
    *(_QWORD *)(v16 + 8) = v13;
    *(_QWORD *)(v16 + 16) = v14;
    if ( v13 )
      v17 = *(_DWORD *)(v13 + 16) - 24;
    else
      v17 = 0;
    *(_DWORD *)(v16 + 32) = v17;
    v18 = v7;
    *(_DWORD *)(v16 + 36) = v15;
    *(_QWORD *)NtCurrentTeb()->ReservedForOle = v14;
    v19 = *(_QWORD *)(v16 + 24);
    *(_QWORD *)&v56 = v19;
    *(_QWORD *)(v16 + 24) = v4;
    if ( v7 < 0 )
      goto LABEL_23;
    v20 = v53;
    v21 = (_QWORD *)*((_QWORD *)this + 14);
    v21[4] = *(_QWORD *)(v53 + 16);
    v21[5] = *(_QWORD *)(v20 + 24);
    v21[6] = *(_QWORD *)(v20 + 32);
    v22 = *((_QWORD *)this + 13);
    v23 = *(_DWORD *)(v22 + 20);
    if ( (v23 & 0x20) != 0 )
      break;
    if ( (v23 & 0x40) == 0 )
    {
      v18 = -2147287035;
      *(_QWORD *)(*((_QWORD *)this + 17) + 16LL) += v57;
      goto LABEL_23;
    }
    v24 = *(_QWORD *)(v22 + 104);
    if ( v24 )
      v25 = (PSStream *)(v24 + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
    else
      v25 = 0;
    v18 = PSStream::ReadAt(v25, *(_QWORD *)(*((_QWORD *)this + 17) + 16LL), v58, v59, &v57);
    *(_QWORD *)(*((_QWORD *)this + 17) + 16LL) += v57;
    if ( v18 != -2147483638 && v18 != -2147286524 )
      goto LABEL_23;
    v34 = 0;
    v59 -= v57;
    LODWORD(v60) = 0;
    v35 = v57;
    v49 = 0;
    v36 = *((_QWORD *)this + 15);
    v37 = v18 == -2147483638;
    v51 = v36;
    v38 = *(__int64 **)(v36 + 72);
    if ( v38 )
    {
      v34 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, unsigned int *))(*v38 + 24))(
              *(_QWORD *)(v36 + 72),
              &v60,
              &v49);
      if ( !v34 )
      {
        CSafeSem::Release((CSafeSem *)&v54);
        v43 = (unsigned int)v60;
        v44 = v49;
        v45 = v51;
        while ( 1 )
        {
          v46 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, BOOL, int))(**((_QWORD **)this + 6) + 40LL))(
                  *((_QWORD *)this + 6),
                  v43,
                  v44,
                  v37,
                  197123);
          v34 = v46;
          if ( v46 != 197121 && v46 != 197123 && v46 )
            goto LABEL_75;
          v47 = *(void **)(v45 + 80);
          v50 = 0;
          WaitForSingleObject(v47, 0xFFFFFFFF);
          (*(void (__fastcall **)(__int64 *, int *))(*v38 + 32))(v38, &v50);
          if ( v50 == 2 )
            break;
          if ( v50 == 1 )
            goto LABEL_77;
          v48 = *v38;
          LODWORD(v51) = 0;
          (*(void (__fastcall **)(__int64 *, __int64 *, __int64 *))(v48 + 24))(v38, &v60, &v51);
          v43 = (unsigned int)v60;
          v44 = v49;
          if ( (unsigned int)v60 >= v49 )
          {
            (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, BOOL, int))(**((_QWORD **)this + 6) + 40LL))(
              *((_QWORD *)this + 6),
              (unsigned int)v60,
              v49,
              v37,
              197121);
LABEL_75:
            if ( v34 - 197121 > 2 )
            {
              v4 = v55;
              goto LABEL_65;
            }
LABEL_77:
            v4 = v55;
            goto LABEL_66;
          }
        }
        v34 = -2147286527;
      }
LABEL_46:
      CSafeSem::Release((CSafeSem *)&v54);
      return v34;
    }
LABEL_65:
    if ( v34 )
      goto LABEL_46;
LABEL_66:
    v58 = (char *)v58 + v35;
  }
  v18 = -2147286782;
  *(_QWORD *)(*((_QWORD *)this + 17) + 16LL) += v57;
LABEL_23:
  if ( a4 )
    *a4 = v57;
  if ( v16 )
  {
    if ( v19 )
    {
      v30 = *(_QWORD *)(v19 + 88);
      v31 = *(_QWORD *)(v19 + 96);
      v32 = *(_DWORD *)(v19 + 104);
      *(_QWORD *)(v16 + 8) = v30;
      *(_QWORD *)(v16 + 16) = v31;
      if ( v30 )
        LODWORD(v30) = *(_DWORD *)(v30 + 16) - 24;
      *(_DWORD *)(v16 + 32) = v30;
      *(_DWORD *)(v16 + 36) = v32;
      *(_QWORD *)NtCurrentTeb()->ReservedForOle = v31;
      *(_QWORD *)(v16 + 24) = v19;
    }
    else
    {
      *(_QWORD *)(v16 + 8) = 0;
      *(_QWORD *)(v16 + 16) = 0;
      *(_QWORD *)(v16 + 32) = 0;
      *(_QWORD *)NtCurrentTeb()->ReservedForOle = 0;
      *(_QWORD *)(v16 + 24) = 0;
    }
  }
  if ( v7 >= 0 )
  {
    v26 = GetCurrentThreadId();
    v27 = *(_QWORD *)(v4 + 112);
    if ( *(_DWORD *)(v27 + 8) == v26 )
    {
      v28 = (*(_DWORD *)(v27 + 4))-- == 1;
      v29 = *(_QWORD *)(v4 + 112);
      if ( v28 )
      {
        *(_DWORD *)(v29 + 8) = 0;
        if ( _InterlockedDecrement(*(volatile signed __int32 **)(v4 + 112)) >= 0 )
          SetEvent(*(HANDLE *)(v4 + 120));
      }
      else
      {
        _InterlockedDecrement((volatile signed __int32 *)v29);
      }
    }
  }
  return v18;
}

```

## disassembly

```asm
0x180010710  mov     [rsp-8+arg_10], r8d
0x180010715  mov     [rsp-8+arg_8], rdx
0x18001071a  push    rbp
0x18001071b  push    rdi
0x18001071c  push    r12
0x18001071e  push    r13
0x180010720  push    r14
0x180010722  push    r15
0x180010724  lea     rbp, [rsp-2Fh]
0x180010729  sub     rsp, 88h
0x180010730  mov     rdi, [rcx+78h]
0x180010734  mov     r15, rcx
0x180010737  xor     ecx, ecx
0x180010739  mov     [rbp+57h+var_58], rdi
0x18001073d  mov     [rbp+57h+arg_0], ecx
0x180010740  xorps   xmm0, xmm0
0x180010743  mov     r14, r9
0x180010746  mov     r12d, 80030100h
0x18001074c  movdqu  [rbp+57h+var_50], xmm0
0x180010751  test    r9, r9
0x180010754  jz      short loc_180010759
0x180010756  mov     [r9], ecx
0x180010759  test    r8d, r8d
0x18001075c  jz      loc_1800109A0
0x180010762  test    rdx, rdx
0x180010765  jnz     loc_1800109A0
0x18001076b  mov     eax, 80030009h
0x180010770  add     rsp, 88h
0x180010777  pop     r15
0x180010779  pop     r14
0x18001077b  pop     r13
0x18001077d  pop     r12
0x18001077f  pop     rdi
0x180010780  pop     rbp
0x180010781  retn
0x180010782  lea     r13, ?g_ErrorSmAllocator@@3VCErrorSmAllocator@@A; CErrorSmAllocator g_ErrorSmAllocator
0x180010789  call    cs:__imp_GetCurrentThreadId
0x18001078f  mov     rcx, [rdi+70h]
0x180010793  mov     edx, 1
0x180010798  mov     esi, eax
0x18001079a  lock xadd [rcx], edx
0x18001079e  mov     rcx, [rdi+70h]
0x1800107a2  add     edx, 1
0x1800107a5  jnz     loc_180010ACF
0x1800107ab  mov     dword ptr [rcx+4], 1
0x1800107b2  mov     rax, [rdi+70h]
0x1800107b6  mov     [rax+8], esi
0x1800107b9  xor     r12d, r12d
0x1800107bc  mov     rcx, [rdi+58h]; this
0x1800107c0  test    rcx, rcx
0x1800107c3  jnz     loc_180010A2C
0x1800107c9  mov     rax, gs:30h
0x1800107d2  mov     [rbp+57h+var_60], r12d
0x1800107d6  mov     rcx, [rax+1758h]
0x1800107dd  mov     [rbp+57h+var_70], rcx
0x1800107e1  test    rcx, rcx
0x1800107e4  jz      loc_180010AC0
0x1800107ea  mov     rax, [rbp+57h+var_70]
0x1800107ee  cmp     qword ptr [rax+8], 0
0x1800107f3  jz      loc_180010B33
0x1800107f9  mov     rax, [rdi+58h]
0x1800107fd  mov     rdx, [rdi+60h]
0x180010801  mov     r8d, [rdi+68h]
0x180010805  mov     rbx, [rbp+57h+var_70]
0x180010809  mov     rbx, [rbx+8]
0x18001080d  mov     qword ptr [rbp+57h+var_50+8], rbx
0x180010811  mov     [rbx+8], rax
0x180010815  mov     [rbx+10h], rdx
0x180010819  test    rax, rax
0x18001081c  jz      loc_1800109E1
0x180010822  mov     ecx, [rax+10h]
0x180010825  sub     ecx, 18h
0x180010828  mov     [rbx+20h], ecx
0x18001082b  mov     esi, r12d
0x18001082e  mov     [rbx+24h], r8d
0x180010832  mov     rax, gs:30h
0x18001083b  mov     rcx, [rax+1758h]
0x180010842  mov     [rcx], rdx
0x180010845  mov     r13, [rbx+18h]
0x180010849  mov     qword ptr [rbp+57h+var_50], r13
0x18001084d  mov     [rbx+18h], rdi
0x180010851  test    r12d, r12d
0x180010854  js      loc_180010900
0x18001085a  mov     rdx, [rbp+57h+var_68]
0x18001085e  mov     rcx, [r15+70h]
0x180010862  mov     rax, [rdx+10h]
0x180010866  mov     [rcx+20h], rax
0x18001086a  mov     rax, [rdx+18h]
0x18001086e  mov     [rcx+28h], rax
0x180010872  mov     rax, [rdx+20h]
0x180010876  mov     [rcx+30h], rax
0x18001087a  mov     rdx, [r15+68h]
0x18001087e  mov     eax, [rdx+14h]
0x180010881  test    al, 20h
0x180010883  jnz     loc_180010CB5
0x180010889  test    al, 40h
0x18001088b  jz      loc_180010BA3
0x180010891  mov     rax, [r15+88h]
0x180010898  mov     rdx, [rdx+68h]
0x18001089c  mov     r10, [rax+10h]
0x1800108a0  test    rdx, rdx
0x1800108a3  jz      loc_180010B9C
0x1800108a9  mov     rax, gs:30h
0x1800108b2  mov     rcx, [rax+1758h]
0x1800108b9  mov     rcx, [rcx]
0x1800108bc  add     rcx, rdx; this
0x1800108bf  mov     r9d, [rbp+57h+arg_10]; unsigned int
0x1800108c3  lea     rax, [rbp+57h+arg_0]
0x1800108c7  mov     r8, [rbp+57h+arg_8]; void *
0x1800108cb  mov     rdx, r10; unsigned __int64
0x1800108ce  mov     [rsp+0B0h+var_90], rax; unsigned int *
0x1800108d3  call    ?ReadAt@PSStream@@QEAAJ_KPEAXKPEAK@Z; PSStream::ReadAt(unsigned __int64,void *,ulong,ulong *)
0x1800108d8  mov     rcx, [r15+88h]
0x1800108df  mov     esi, eax
0x1800108e1  mov     eax, [rbp+57h+arg_0]
0x1800108e4  add     [rcx+10h], rax
0x1800108e8  cmp     esi, 8000000Ah
0x1800108ee  jz      loc_180010A5C
0x1800108f4  cmp     esi, 80030204h
0x1800108fa  jz      loc_180010A5C
0x180010900  test    r14, r14
0x180010903  jz      short loc_18001090B
0x180010905  mov     eax, [rbp+57h+arg_0]
0x180010908  mov     [r14], eax
0x18001090b  test    rbx, rbx
0x18001090e  jz      loc_180010A24
0x180010914  test    r13, r13
0x180010917  jnz     loc_1800109E8
0x18001091d  xor     r14d, r14d
0x180010920  mov     [rbx+8], r14
0x180010924  mov     [rbx+10h], r14
0x180010928  mov     [rbx+20h], r14
0x18001092c  mov     rax, gs:30h
0x180010935  mov     rcx, [rax+1758h]
0x18001093c  mov     [rcx], r14
0x18001093f  mov     [rbx+18h], r14
0x180010943  test    r12d, r12d
0x180010946  js      short loc_18001097F
0x180010948  call    cs:__imp_GetCurrentThreadId
0x18001094e  mov     rcx, [rdi+70h]
0x180010952  cmp     [rcx+8], eax
0x180010955  jnz     short loc_18001097F
0x180010957  sub     dword ptr [rcx+4], 1
0x18001095b  mov     rax, [rdi+70h]
0x18001095f  jnz     loc_180010ADC
0x180010965  mov     [rax+8], r14d
0x180010969  mov     edx, 0FFFFFFFFh
0x18001096e  mov     rcx, [rdi+70h]
0x180010972  lock xadd [rcx], edx
0x180010976  cmp     edx, 1
0x180010979  jns     loc_180010CCD
0x18001097f  mov     eax, esi
0x180010981  mov     rbx, [rsp+0B0h+var_30]
0x180010989  mov     rsi, [rsp+0B0h+var_38]
0x18001098e  add     rsp, 88h
0x180010995  pop     r15
0x180010997  pop     r14
0x180010999  pop     r13
0x18001099b  pop     r12
0x18001099d  pop     rdi
0x18001099e  pop     rbp
0x18001099f  retn
0x1800109a0  mov     [rsp+0B0h+var_30], rbx
0x1800109a8  lea     rcx, [r15+40h]; Buf1
0x1800109ac  mov     r8d, 10h; Size
0x1800109b2  mov     [rsp+0B0h+var_38], rsi
0x1800109b7  lea     rdx, _GUID_04a45d68_dba8_467d_9aed_e762432212f9; Buf2
0x1800109be  mov     [rbp+57h+var_68], rdi
0x1800109c2  call    memcmp_0
0x1800109c7  test    eax, eax
0x1800109c9  jz      loc_180010782
0x1800109cf  mov     rbx, qword ptr [rbp+57h+var_50+8]
0x1800109d3  mov     esi, 80030006h
0x1800109d8  mov     r13, qword ptr [rbp+57h+var_50]
0x1800109dc  jmp     loc_180010900
0x1800109e1  xor     ecx, ecx
0x1800109e3  jmp     loc_180010828
0x1800109e8  mov     rax, [r13+58h]
0x1800109ec  mov     rdx, [r13+60h]
0x1800109f0  mov     ecx, [r13+68h]
0x1800109f4  mov     [rbx+8], rax
0x1800109f8  mov     [rbx+10h], rdx
0x1800109fc  test    rax, rax
0x1800109ff  jz      short loc_180010A07
0x180010a01  mov     eax, [rax+10h]
0x180010a04  sub     eax, 18h
0x180010a07  mov     [rbx+20h], eax
0x180010a0a  mov     [rbx+24h], ecx
0x180010a0d  mov     rax, gs:30h
0x180010a16  mov     rcx, [rax+1758h]
0x180010a1d  mov     [rcx], rdx
0x180010a20  mov     [rbx+18h], r13
0x180010a24  xor     r14d, r14d
0x180010a27  jmp     loc_180010943
0x180010a2c  mov     rax, [rcx+8]
0x180010a30  mov     edx, [rax]
0x180010a32  cmp     edx, [rcx+10h]
0x180010a35  jz      loc_1800107C9
0x180010a3b  add     edx, 0FFFFFFE8h; unsigned int
0x180010a3e  call    ?Commit@CSharedMemoryBlock@@QEAAJK@Z; CSharedMemoryBlock::Commit(ulong)
0x180010a43  mov     r12d, eax
0x180010a46  test    eax, eax
0x180010a48  jns     loc_1800107C9
0x180010a4e  lea     rcx, [rdi+70h]; this
0x180010a52  call    ?Release@CDfMutex@@QEAAXXZ; CDfMutex::Release(void)
0x180010a57  jmp     loc_1800107C9
0x180010a5c  mov     eax, [rbp+57h+arg_0]
0x180010a5f  xor     ebx, ebx
0x180010a61  sub     [rbp+57h+arg_10], eax
0x180010a64  xor     r13d, r13d
0x180010a67  cmp     esi, 8000000Ah
0x180010a6d  mov     dword ptr [rbp+57h+arg_18], ebx
0x180010a70  mov     r12d, eax
0x180010a73  mov     [rbp+57h+var_80], ebx
0x180010a76  mov     rax, [r15+78h]
0x180010a7a  setz    r13b
0x180010a7e  mov     [rbp+57h+var_78], rax
0x180010a82  mov     rsi, [rax+48h]
0x180010a86  test    rsi, rsi
0x180010a89  jz      loc_180010BBB
0x180010a8f  mov     rax, [rsi]
0x180010a92  lea     r8, [rbp+57h+var_80]
0x180010a96  lea     rdx, [rbp+57h+arg_18]
0x180010a9a  mov     rcx, rsi
0x180010a9d  mov     rax, [rax+18h]
0x180010aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aa6  mov     ebx, eax
0x180010aa8  test    eax, eax
0x180010aaa  jz      loc_180010BCC
0x180010ab0  lea     rcx, [rbp+57h+var_60]; this
0x180010ab4  call    ?Release@CSafeSem@@QEAAXXZ; CSafeSem::Release(void)
0x180010ab9  mov     eax, ebx
0x180010abb  jmp     loc_180010981
0x180010ac0  lea     rcx, [rbp+57h+var_70]
0x180010ac4  call    cs:__imp_InternalTlsAllocData
0x180010aca  jmp     loc_1800107EA
0x180010acf  cmp     [rcx+8], esi
0x180010ad2  jnz     short loc_180010AE4
0x180010ad4  inc     dword ptr [rcx+4]
0x180010ad7  jmp     loc_1800107B9
0x180010adc  lock dec dword ptr [rax]
0x180010adf  jmp     loc_18001097F
0x180010ae4  mov     rcx, [rdi+78h]; hHandle
0x180010ae8  mov     edx, 124F80h; dwMilliseconds
0x180010aed  call    cs:__imp_WaitForSingleObject
0x180010af3  test    eax, eax
0x180010af5  jz      loc_180010B8C
0x180010afb  cmp     eax, 80h
0x180010b00  jz      loc_180010B8C
0x180010b06  cmp     eax, 102h
0x180010b0b  jz      short loc_180010B81
0x180010b0d  call    cs:__imp_GetLastError
0x180010b13  mov     r12d, eax
0x180010b16  test    eax, eax
0x180010b18  jle     short loc_180010B25
0x180010b1a  movzx   r12d, ax
0x180010b1e  or      r12d, 80070000h
0x180010b25  test    r12d, r12d
0x180010b28  jns     loc_1800107BC
0x180010b2e  jmp     loc_1800107C9
0x180010b33  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180010b3a  xor     edx, edx; dwFlags
0x180010b3c  mov     r8d, 30h ; '0'; dwBytes
0x180010b42  call    cs:__imp_HeapAlloc
0x180010b48  test    rax, rax
0x180010b4b  jnz     short loc_180010B5B
0x180010b4d  mov     rax, [rbp+57h+var_70]
0x180010b51  mov     qword ptr [rax+8], 0
0x180010b59  jmp     short loc_180010B74
0x180010b5b  mov     rcx, rax; this
0x180010b5e  call    ??0CSmAllocator@@QEAA@XZ; CSmAllocator::CSmAllocator(void)
0x180010b63  mov     rcx, [rbp+57h+var_70]
0x180010b67  mov     [rcx+8], rax
0x180010b6b  test    rax, rax
0x180010b6e  jnz     loc_1800107F9
0x180010b74  mov     rax, [rbp+57h+var_70]
0x180010b78  mov     [rax+8], r13
0x180010b7c  jmp     loc_1800107F9
0x180010b81  mov     r12d, 80030100h
0x180010b87  jmp     loc_1800107C9
0x180010b8c  mov     rax, [rdi+70h]
0x180010b90  mov     dword ptr [rax+4], 1
0x180010b97  jmp     loc_1800107B2
0x180010b9c  xor     ecx, ecx
0x180010b9e  jmp     loc_1800108BF
0x180010ba3  mov     rcx, [r15+88h]
0x180010baa  mov     esi, 80030005h
0x180010baf  mov     eax, [rbp+57h+arg_0]
0x180010bb2  add     [rcx+10h], rax
0x180010bb6  jmp     loc_180010900
0x180010bbb  test    ebx, ebx
0x180010bbd  jnz     loc_180010AB0
0x180010bc3  add     [rbp+57h+arg_8], r12
0x180010bc7  jmp     loc_180010782
0x180010bcc  lea     rcx, [rbp+57h+var_60]; this
0x180010bd0  call    ?Release@CSafeSem@@QEAAXXZ; CSafeSem::Release(void)
0x180010bd5  mov     edx, dword ptr [rbp+57h+arg_18]
0x180010bd8  mov     r8d, [rbp+57h+var_80]
0x180010bdc  mov     rdi, [rbp+57h+var_78]
0x180010be0  mov     rcx, [r15+30h]
  ... truncated ...
```
