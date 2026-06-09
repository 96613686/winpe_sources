# CCorSvcMgr::MultiprocCompile(bool)

- ea: `0x180026b78`
- end: `0x1800270ae`
- name: `?MultiprocCompile@CCorSvcMgr@@AEAAX_N@Z`
- size: `1334`
- prototype: `void __fastcall(CCorSvcMgr *__hidden this, bool)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180023bcc`

## callees

- `0x180002468`
- `0x1800139cc`
- `0x180013a78`
- `0x180013b9c`
- `0x180025110`
- `0x180026b78`
- `0x18002bcd8`
- `0x18003000c`
- `0x1800304ec`
- `0x180030568`
- `0x180030ab8`
- `0x180030d84`
- `0x180031e08`
- `0x18003303c`
- `0x180034fd4`
- `0x18003dc50`
- `0x18003f280`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180026e75`
- `KERNEL32!WaitForSingleObject` at `0x180026e75`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CCorSvcMgr::MultiprocCompile(CCorSvcMgr *this, char a2)
{
  char v2; // r14
  char *v4; // r12
  int v5; // eax
  char *v6; // r15
  unsigned int v7; // edx
  __int64 v8; // rax
  void **v9; // rcx
  int v10; // r8d
  struct LogicalImage *ReadyCompilationJob; // r13
  SString *v12; // rbx
  const unsigned __int16 *v13; // rdx
  char *v14; // rax
  char *v15; // rbx
  SString *v16; // r14
  const unsigned __int16 *v17; // rdx
  _DWORD *v18; // rax
  unsigned int v19; // ecx
  unsigned int v20; // edx
  void **v21; // rax
  int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // edx
  void **v25; // rax
  unsigned int v26; // ecx
  __int64 v27; // rdx
  int *v28; // r14
  __int64 i; // rbx
  __int64 v30; // rdi
  __int64 v31; // r8
  const struct SBuffer *v32; // rbx
  SBuffer *v33; // rdi
  unsigned int v34; // r13d
  unsigned int v35; // edi
  int v36; // ebx
  __int64 v37; // rcx
  _QWORD v38[3]; // [rsp+20h] [rbp-89h] BYREF
  _DWORD v39[2]; // [rsp+38h] [rbp-71h] BYREF
  int v40; // [rsp+40h] [rbp-69h]
  void *lpMem; // [rsp+48h] [rbp-61h]
  _QWORD v42[3]; // [rsp+50h] [rbp-59h] BYREF
  _QWORD v43[6]; // [rsp+68h] [rbp-41h] BYREF
  __int128 v44; // [rsp+98h] [rbp-11h]
  __int128 v45; // [rsp+A8h] [rbp-1h]

  v2 = a2;
  v4 = 0;
LABEL_2:
  while ( 1 )
  {
    v5 = *((_DWORD *)this + 316);
    if ( v5 < 0 && *((_DWORD *)this + 317) == (_DWORD)v4 )
      break;
    if ( v5 == -2147024784 || (unsigned int)CCorSvcMgr::IsInterruptRequested((BSTR *)this) )
      break;
    v6 = (char *)this + 352;
    v7 = *((_DWORD *)this + 89);
    if ( v7 >= *((_DWORD *)this + 88) )
    {
      v8 = (unsigned int)v4;
      if ( !v7 )
        goto LABEL_47;
      v9 = (void **)((char *)this + 384);
      while ( *v9 != v4 )
      {
        v8 = (unsigned int)(v8 + 1);
        v9 += 7;
        if ( (unsigned int)v8 >= v7 )
          goto LABEL_47;
      }
      if ( !(CCorSvcMgr *)((char *)this + 56 * v8 + 360) )
        goto LABEL_47;
    }
    v10 = (int)v4;
    LOBYTE(v10) = *((_DWORD *)this + 56) / 0x18u == 0;
    ReadyCompilationJob = WorkQueue::GetReadyCompilationJob(
                            (CCorSvcMgr *)((char *)this + 104),
                            (CCorSvcMgr *)((char *)this + 224),
                            v10);
    if ( ReadyCompilationJob )
    {
      v12 = (SString *)*((_QWORD *)ReadyCompilationJob + 13);
      if ( v12 || (v12 = (SString *)*((_QWORD *)ReadyCompilationJob + 11)) != 0 )
      {
        SString::ConvertToUnicode(v12);
        v13 = (const unsigned __int16 *)*((_QWORD *)v12 + 2);
      }
      else
      {
        v13 = (const unsigned __int16 *)v4;
      }
      v39[0] = 2;
      v39[1] = 2;
      v40 = 16;
      lpMem = (void *)&SString::s_EmptyBuffer;
      SString::Set((SString *)v39, v13);
      SString::ConvertToUnicode((SString *)v39);
      v38[0] = 0x200000002LL;
      LODWORD(v38[1]) = 16;
      v38[2] = &SString::s_EmptyBuffer;
      SString::Set((SString *)v38, (const unsigned __int16 *)lpMem);
      SArray<SString,0>::Append((CCorSvcMgr *)((char *)this + 224), (struct SBuffer *)v38);
      if ( (v40 & 8) != 0 )
        operator delete(lpMem);
      v14 = (char *)operator new(0x40u);
      v15 = v14;
      if ( v14 )
      {
        *(_QWORD *)v14 = &CompilationTask::`vftable';
        *((_DWORD *)v14 + 6) = 2;
        *((_DWORD *)v14 + 7) = 2;
        *((_DWORD *)v14 + 8) = 16;
        *((_QWORD *)v14 + 5) = &SString::s_EmptyBuffer;
        *((_QWORD *)v14 + 1) = this;
        *((_QWORD *)v14 + 2) = ReadyCompilationJob;
        v16 = (SString *)*((_QWORD *)ReadyCompilationJob + 13);
        if ( v16 || (v16 = (SString *)*((_QWORD *)ReadyCompilationJob + 11)) != 0 )
        {
          SString::ConvertToUnicode(v16);
          v17 = (const unsigned __int16 *)*((_QWORD *)v16 + 2);
        }
        else
        {
          v17 = (const unsigned __int16 *)v4;
        }
        SString::Set((SString *)(v15 + 24), v17);
        *((_DWORD *)v15 + 12) = (_DWORD)v4;
        v18 = operator new(0x20u);
        v43[3] = v18;
        if ( v18 )
        {
          *(_QWORD *)v18 = &MultiprocLogger::`vftable';
          v18[2] = 1;
        }
        else
        {
          v18 = v4;
        }
        *((_QWORD *)v15 + 7) = v18;
        v2 = a2;
      }
      else
      {
        v15 = v4;
      }
      ThreadPool::StartTask((CCorSvcMgr *)((char *)this + 352), (struct WorkerTask *)v15);
    }
    else
    {
      if ( !v2 )
        goto LABEL_37;
      if ( *((_DWORD *)this + 26) < 8u )
      {
        v19 = (unsigned int)v4;
        v20 = *((_DWORD *)this + 89);
        if ( !v20 )
          goto LABEL_37;
        v21 = (void **)((char *)this + 384);
        while ( *v21 == v4 )
        {
          ++v19;
          v21 += 7;
          if ( v19 >= v20 )
            goto LABEL_37;
        }
      }
LABEL_47:
      WaitForSingleObject(*((HANDLE *)this + 157), 0xFFFFFFFF);
      while ( 1 )
      {
        v26 = (unsigned int)v4;
        v2 = a2;
        if ( *((_DWORD *)v6 + 1) <= (unsigned int)v4 )
          break;
        while ( 1 )
        {
          v27 = 56LL * v26;
          if ( *(_DWORD *)&v6[v27 + 40] != (_DWORD)v4 )
          {
            v4 = *(char **)&v6[v27 + 32];
            if ( v4 )
              break;
          }
          if ( ++v26 >= *((_DWORD *)v6 + 1) )
          {
            v2 = a2;
            goto LABEL_2;
          }
        }
        *(_QWORD *)&v6[v27 + 32] = 0;
        v28 = (int *)((char *)this + 224);
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned int)i >= *v28 / 0x18u )
            ThrowHR(-2147418113);
          v30 = (unsigned int)i;
          if ( (unsigned int)SString::Equals(
                               (SString *)(*((_QWORD *)this + 30) + 24 * i),
                               (const struct SString *)(v4 + 24)) )
            break;
        }
        v31 = *((_QWORD *)this + 30);
        v32 = (const struct SBuffer *)(v31 + 24LL * (*v28 / 0x18u - 1));
        v33 = (SBuffer *)(v31 + 24 * v30);
        SBuffer::Set(v33, v32);
        *((_DWORD *)v33 + 2) = *((_DWORD *)v32 + 2) & 7 | *((_DWORD *)v33 + 2) & 0xFFFFFEF8;
        v34 = *v28 / 0x18u;
        v35 = v34 - 1;
        if ( !v34 )
        {
          if ( (*((_BYTE *)this + 232) & 0x10) != 0 )
            SBuffer::ReallocateBuffer((char *)this + 224, *((unsigned int *)this + 57), 1);
          *(_QWORD *)&v44 = *((_QWORD *)this + 30);
          *(_OWORD *)&v38[1] = v44;
          v42[0] = v38[0];
          v42[2] = *(_OWORD *)&_mm_unpackhi_pd(*(__m128d *)&v38[1], *(__m128d *)&v38[1]);
          v42[1] = v44;
          SArray<SString,0>::ConstructBuffer((char *)this + 224, v42, 0xFFFFFFFFLL);
        }
        v36 = 24 * v35;
        if ( 24 * v35 > *((_DWORD *)this + 57) )
          SBuffer::ReallocateBuffer((char *)this + 224, (unsigned int)v36, 1);
        *v28 = v36;
        if ( v34 > v35 )
        {
          if ( (*((_BYTE *)this + 232) & 0x10) != 0 )
            SBuffer::ReallocateBuffer((char *)this + 224, *((unsigned int *)this + 57), 1);
          *(_QWORD *)&v45 = *((_QWORD *)this + 30);
          *(_OWORD *)&v38[1] = v45;
          v43[0] = v38[0];
          v43[2] = *(_OWORD *)&_mm_unpackhi_pd(*(__m128d *)&v38[1], *(__m128d *)&v38[1]);
          v43[1] = v45 + v36;
          SArray<SString,0>::DestructBuffer((char *)this + 224, v43, 1);
        }
        v43[4] = v4;
        *(_QWORD *)v4 = &CompilationTask::`vftable';
        v37 = *((_QWORD *)v4 + 7);
        if ( v37 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
        v43[5] = v4 + 24;
        if ( (v4[32] & 8) != 0 )
          operator delete(*((void **)v4 + 5));
        operator delete(v4);
        v4 = 0;
      }
    }
  }
  v6 = (char *)this + 352;
  v23 = (unsigned int)v4;
  v24 = *((_DWORD *)this + 89);
  if ( v24 )
  {
    v25 = (void **)((char *)this + 384);
    while ( *v25 == v4 )
    {
      ++v23;
      v25 += 7;
      if ( v23 >= v24 )
        goto LABEL_45;
    }
    goto LABEL_47;
  }
LABEL_45:
  if ( (unsigned int)CCorSvcMgr::IsInterruptRequested((BSTR *)this) )
    ThrowHR(-2146230784);
LABEL_37:
  v22 = *((_DWORD *)this + 316);
  if ( v22 < 0 && *((_DWORD *)this + 317) == (_DWORD)v4 || v22 == -2147024784 )
    ThrowHR(v22);
}

```

## disassembly

```asm
0x180026b78  mov     [rsp-8+arg_8], dl
0x180026b7c  push    rbp
0x180026b7d  push    rbx
0x180026b7e  push    rsi
0x180026b7f  push    rdi
0x180026b80  push    r12
0x180026b82  push    r13
0x180026b84  push    r14
0x180026b86  push    r15
0x180026b88  lea     rbp, [rsp-1Fh]
0x180026b8d  sub     rsp, 0C8h
0x180026b94  mov     r14b, dl
0x180026b97  mov     rsi, rcx
0x180026b9a  xor     r12d, r12d
0x180026b9d  mov     r13, 0AAAAAAAAAAAAAAABh
0x180026ba7  mov     eax, [rsi+4F0h]
0x180026bad  test    eax, eax
0x180026baf  jns     short loc_180026BBE
0x180026bb1  cmp     [rsi+4F4h], r12d
0x180026bb8  jz      loc_180026E25
0x180026bbe  cmp     eax, 80070070h
0x180026bc3  jz      loc_180026E25
0x180026bc9  mov     rcx, rsi; this
0x180026bcc  call    ?IsInterruptRequested@CCorSvcMgr@@AEAAHXZ; CCorSvcMgr::IsInterruptRequested(void)
0x180026bd1  test    eax, eax
0x180026bd3  jnz     loc_180026E25
0x180026bd9  lea     r15, [rsi+160h]
0x180026be0  mov     edx, [r15+4]
0x180026be4  cmp     edx, [r15]
0x180026be7  jb      short loc_180026C1D
0x180026be9  mov     eax, r12d
0x180026bec  test    edx, edx
0x180026bee  jz      loc_180026E6B
0x180026bf4  lea     rcx, [r15+20h]
0x180026bf8  cmp     [rcx], r12
0x180026bfb  jz      short loc_180026C0C
0x180026bfd  inc     eax
0x180026bff  add     rcx, 38h ; '8'
0x180026c03  cmp     eax, edx
0x180026c05  jb      short loc_180026BF8
0x180026c07  jmp     loc_180026E6B
0x180026c0c  imul    rcx, rax, 38h ; '8'
0x180026c10  lea     rax, [r15+8]
0x180026c14  add     rax, rcx
0x180026c17  jz      loc_180026E6B
0x180026c1d  lea     rdi, [rsi+0E0h]
0x180026c24  mov     ecx, [rdi]
0x180026c26  mov     rax, r13
0x180026c29  mul     rcx
0x180026c2c  shr     rdx, 4
0x180026c30  mov     r8d, r12d
0x180026c33  test    edx, edx
0x180026c35  setz    r8b; int
0x180026c39  mov     rdx, rdi; struct LogicalImageCompilationList *
0x180026c3c  lea     rcx, [rsi+68h]; this
0x180026c40  call    ?GetReadyCompilationJob@WorkQueue@@QEAAPEAVLogicalImage@@PEAVLogicalImageCompilationList@@H@Z; WorkQueue::GetReadyCompilationJob(LogicalImageCompilationList *,int)
0x180026c45  mov     r13, rax
0x180026c48  test    rax, rax
0x180026c4b  jz      loc_180026DBC
0x180026c51  lea     rax, [rsp+100h+var_E0]
0x180026c56  mov     [rbp+57h+arg_0], rax
0x180026c5a  mov     rbx, [r13+68h]
0x180026c5e  test    rbx, rbx
0x180026c61  jnz     short loc_180026C71
0x180026c63  mov     rbx, [r13+58h]
0x180026c67  test    rbx, rbx
0x180026c6a  jnz     short loc_180026C71
0x180026c6c  mov     rdx, r12
0x180026c6f  jmp     short loc_180026C7D
0x180026c71  mov     rcx, rbx; this
0x180026c74  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180026c79  mov     rdx, [rbx+10h]; unsigned __int16 *
0x180026c7d  mov     ebx, 2
0x180026c82  mov     [rbp+57h+var_C8], ebx
0x180026c85  mov     [rbp+57h+var_C4], ebx
0x180026c88  mov     [rbp+57h+var_C0], 10h
0x180026c8f  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180026c96  mov     [rbp+57h+lpMem], rax
0x180026c9a  lea     rcx, [rbp+57h+var_C8]; this
0x180026c9e  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180026ca3  nop
0x180026ca4  lea     rcx, [rbp+57h+var_C8]; this
0x180026ca8  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180026cad  mov     dword ptr [rsp+100h+var_E0], ebx
0x180026cb1  mov     dword ptr [rsp+100h+var_E0+4], ebx
0x180026cb5  mov     dword ptr [rsp+100h+var_E0+8], 10h
0x180026cbd  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180026cc4  mov     qword ptr [rbp+57h+var_E0+10h], rax
0x180026cc8  mov     rdx, [rbp+57h+lpMem]; unsigned __int16 *
0x180026ccc  lea     rcx, [rsp+100h+var_E0]; this
0x180026cd1  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180026cd6  nop
0x180026cd7  lea     rdx, [rsp+100h+var_E0]; struct SBuffer *
0x180026cdc  mov     rcx, rdi; this
0x180026cdf  call    ?Append@?$SArray@VSString@@$0A@@@QEAAXVSString@@@Z; SArray<SString,0>::Append(SString)
0x180026ce4  nop
0x180026ce5  test    byte ptr [rbp+57h+var_C0], 8
0x180026ce9  jz      short loc_180026CF4
0x180026ceb  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180026cef  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026cf4  mov     ecx, 40h ; '@'; dwBytes
0x180026cf9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026cfe  mov     rbx, rax
0x180026d01  mov     [rbp+57h+arg_10], rax
0x180026d05  test    rax, rax
0x180026d08  jz      loc_180026DA9
0x180026d0e  lea     rax, ??_7CompilationTask@@6B@; const CompilationTask::`vftable'
0x180026d15  mov     [rbx], rax
0x180026d18  lea     rdi, [rbx+18h]
0x180026d1c  mov     [rbp+57h+arg_18], rdi
0x180026d20  mov     dword ptr [rdi], 2
0x180026d26  mov     dword ptr [rdi+4], 2
0x180026d2d  mov     dword ptr [rdi+8], 10h
0x180026d34  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x180026d3b  mov     [rdi+10h], rax
0x180026d3f  mov     [rbx+8], rsi
0x180026d43  mov     [rbx+10h], r13
0x180026d47  mov     r14, [r13+68h]
0x180026d4b  test    r14, r14
0x180026d4e  jnz     short loc_180026D5E
0x180026d50  mov     r14, [r13+58h]
0x180026d54  test    r14, r14
0x180026d57  jnz     short loc_180026D5E
0x180026d59  mov     rdx, r12
0x180026d5c  jmp     short loc_180026D6A
0x180026d5e  mov     rcx, r14; this
0x180026d61  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180026d66  mov     rdx, [r14+10h]; unsigned __int16 *
0x180026d6a  mov     rcx, rdi; this
0x180026d6d  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180026d72  mov     [rbx+30h], r12d
0x180026d76  mov     ecx, 20h ; ' '; dwBytes
0x180026d7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026d80  mov     [rbp+57h+var_80], rax
0x180026d84  test    rax, rax
0x180026d87  jz      short loc_180026D9C
0x180026d89  lea     rcx, ??_7MultiprocLogger@@6B@; const MultiprocLogger::`vftable'
0x180026d90  mov     [rax], rcx
0x180026d93  mov     dword ptr [rax+8], 1
0x180026d9a  jmp     short loc_180026D9F
0x180026d9c  mov     rax, r12
0x180026d9f  mov     [rbx+38h], rax
0x180026da3  mov     r14b, [rbp+57h+arg_8]
0x180026da7  jmp     short loc_180026DAC
0x180026da9  mov     rbx, r12
0x180026dac  mov     rdx, rbx; struct WorkerTask *
0x180026daf  mov     rcx, r15; this
0x180026db2  call    ?StartTask@ThreadPool@@QEAAXPEAVWorkerTask@@@Z; ThreadPool::StartTask(WorkerTask *)
0x180026db7  jmp     loc_180026B9D
0x180026dbc  test    r14b, r14b
0x180026dbf  jz      short loc_180026DEE
0x180026dc1  cmp     dword ptr [rsi+68h], 8
0x180026dc5  jnb     loc_180026E61
0x180026dcb  mov     ecx, r12d
0x180026dce  mov     edx, [rsi+164h]
0x180026dd4  test    edx, edx
0x180026dd6  jz      short loc_180026DEE
0x180026dd8  lea     rax, [rsi+180h]
0x180026ddf  cmp     [rax], r12
0x180026de2  jnz     short loc_180026E61
0x180026de4  inc     ecx
0x180026de6  add     rax, 38h ; '8'
0x180026dea  cmp     ecx, edx
0x180026dec  jb      short loc_180026DDF
0x180026dee  mov     ecx, [rsi+4F0h]; int
0x180026df4  test    ecx, ecx
0x180026df6  jns     short loc_180026E05
0x180026df8  cmp     [rsi+4F4h], r12d
0x180026dff  jz      loc_1800270A8
0x180026e05  cmp     ecx, 80070070h
0x180026e0b  jz      loc_1800270A8
0x180026e11  add     rsp, 0C8h
0x180026e18  pop     r15
0x180026e1a  pop     r14
0x180026e1c  pop     r13
0x180026e1e  pop     r12
0x180026e20  pop     rdi
0x180026e21  pop     rsi
0x180026e22  pop     rbx
0x180026e23  pop     rbp
0x180026e24  retn
0x180026e25  lea     r15, [rsi+160h]
0x180026e2c  mov     ecx, r12d
0x180026e2f  mov     edx, [rsi+164h]
0x180026e35  test    edx, edx
0x180026e37  jz      short loc_180026E4F
0x180026e39  lea     rax, [rsi+180h]
0x180026e40  cmp     [rax], r12
0x180026e43  jnz     short loc_180026E6B
0x180026e45  inc     ecx
0x180026e47  add     rax, 38h ; '8'
0x180026e4b  cmp     ecx, edx
0x180026e4d  jb      short loc_180026E40
0x180026e4f  mov     rcx, rsi; this
0x180026e52  call    ?IsInterruptRequested@CCorSvcMgr@@AEAAHXZ; CCorSvcMgr::IsInterruptRequested(void)
0x180026e57  test    eax, eax
0x180026e59  jnz     loc_18002709D
0x180026e5f  jmp     short loc_180026DEE
0x180026e61  mov     r13, 0AAAAAAAAAAAAAAABh
0x180026e6b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180026e6e  mov     rcx, [rsi+4E8h]; hHandle
0x180026e75  call    cs:__imp_WaitForSingleObject
0x180026e7b  mov     ecx, r12d
0x180026e7e  cmp     [r15+4], r12d
0x180026e82  mov     r14b, [rbp+57h+arg_8]
0x180026e86  jbe     loc_180026BA7
0x180026e8c  mov     eax, ecx
0x180026e8e  imul    rdx, rax, 38h ; '8'
0x180026e92  cmp     [rdx+r15+28h], r12d
0x180026e97  jz      short loc_180026EA3
0x180026e99  mov     r12, [rdx+r15+20h]
0x180026e9e  test    r12, r12
0x180026ea1  jnz     short loc_180026EB4
0x180026ea3  inc     ecx
0x180026ea5  cmp     ecx, [r15+4]
0x180026ea9  jb      short loc_180026E8C
0x180026eab  mov     r14b, [rbp+57h+arg_8]
0x180026eaf  jmp     loc_180026BA7
0x180026eb4  and     qword ptr [rdx+r15+20h], 0
0x180026eba  lea     r14, [rsi+0E0h]
0x180026ec1  xor     ebx, ebx
0x180026ec3  mov     ecx, [r14]
0x180026ec6  mov     rax, r13
0x180026ec9  mul     rcx
0x180026ecc  shr     rdx, 4
0x180026ed0  cmp     ebx, edx
0x180026ed2  jnb     loc_180027092
0x180026ed8  mov     edi, ebx
0x180026eda  lea     rcx, [rbx+rbx*2]
0x180026ede  mov     rax, [r14+10h]
0x180026ee2  lea     rcx, [rax+rcx*8]; this
0x180026ee6  lea     rdx, [r12+18h]; struct SString *
0x180026eeb  call    ?Equals@SString@@QEBAHAEBV1@@Z; SString::Equals(SString const &)
0x180026ef0  test    eax, eax
0x180026ef2  jnz     short loc_180026EF8
0x180026ef4  inc     ebx
0x180026ef6  jmp     short loc_180026EC3
0x180026ef8  mov     r8, [r14+10h]
0x180026efc  mov     ecx, [r14]
0x180026eff  mov     rax, r13
0x180026f02  mul     rcx
0x180026f05  shr     rdx, 4
0x180026f09  dec     edx
0x180026f0b  lea     rcx, [rdx+rdx*2]
0x180026f0f  lea     rbx, [r8+rcx*8]
0x180026f13  lea     rax, [rdi+rdi*2]
0x180026f17  lea     rdi, [r8+rax*8]
0x180026f1b  mov     rdx, rbx; struct SBuffer *
0x180026f1e  mov     rcx, rdi; this
0x180026f21  call    ?Set@SBuffer@@QEAAXAEBV1@@Z; SBuffer::Set(SBuffer const &)
0x180026f26  mov     ecx, [rbx+8]
0x180026f29  and     ecx, 7
0x180026f2c  mov     eax, [rdi+8]
0x180026f2f  and     eax, 0FFFFFFF8h
0x180026f32  or      eax, ecx
0x180026f34  btr     eax, 8
0x180026f38  mov     [rdi+8], eax
0x180026f3b  mov     ecx, [r14]
0x180026f3e  mov     rax, r13
0x180026f41  mul     rcx
0x180026f44  mov     r13, rdx
0x180026f47  shr     r13, 4
0x180026f4b  lea     edi, [r13-1]
0x180026f4f  cmp     edi, r13d
0x180026f52  jbe     short loc_180026FB8
0x180026f54  test    byte ptr [r14+8], 10h
0x180026f59  jz      short loc_180026F6D
0x180026f5b  mov     r8d, 1
0x180026f61  mov     edx, [r14+4]
0x180026f65  mov     rcx, r14
0x180026f68  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180026f6d  mov     rdx, [r14+10h]
0x180026f71  mov     qword ptr [rbp+57h+var_68], rdx
0x180026f75  movups  xmm1, [rbp+57h+var_68]
0x180026f79  movups  xmmword ptr [rsp+100h+var_E0+8], xmm1
0x180026f7e  movups  xmm0, xmmword ptr [rsp+100h+var_E0]
0x180026f83  movups  [rbp+57h+var_B0], xmm0
0x180026f87  unpckhpd xmm1, xmm1
0x180026f8b  movsd   [rbp+57h+var_A0], xmm1
0x180026f90  lea     eax, ds:0[r13*2]
0x180026f98  add     eax, r13d
0x180026f9b  shl     eax, 3
0x180026f9e  movsxd  rcx, eax
0x180026fa1  add     rcx, rdx
0x180026fa4  mov     qword ptr [rbp+57h+var_B0+8], rcx
0x180026fa8  or      r8d, 0FFFFFFFFh
0x180026fac  lea     rdx, [rbp+57h+var_B0]
0x180026fb0  mov     rcx, r14
0x180026fb3  call    ?ConstructBuffer@?$SArray@VSString@@$0A@@@AEAAXAEBVIterator@1@I@Z; SArray<SString,0>::ConstructBuffer(SArray<SString,0>::Iterator const &,uint)
0x180026fb8  lea     ebx, [rdi+rdi*2]
0x180026fbb  shl     ebx, 3
0x180026fbe  cmp     ebx, [r14+4]
0x180026fc2  jbe     short loc_180026FD4
0x180026fc4  mov     r8d, 1
0x180026fca  mov     edx, ebx
0x180026fcc  mov     rcx, r14
0x180026fcf  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180026fd4  mov     [r14], ebx
0x180026fd7  cmp     r13d, edi
0x180026fda  jbe     short loc_180027034
  ... truncated ...
```
