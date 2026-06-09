# CMStream::Init(int,int,_ULARGE_INTEGER)

- ea: `0x18000c7a0`
- end: `0x18000cd01`
- name: `?Init@CMStream@@QEAAJHHT_ULARGE_INTEGER@@@Z`
- size: `1377`
- prototype: `__int64 __fastcall(CMStream *__hidden this, int, int, union _ULARGE_INTEGER)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c588`

## callees

- `0x18000c1d4`
- `0x18000c410`
- `0x18000c7a0`
- `0x18000cd08`
- `0x18000cdd8`
- `0x18000ce70`
- `0x18000ced8`
- `0x18000e18c`
- `0x1800144a0`
- `0x180017c18`
- `0x180018680`
- `0x18001d820`
- `0x18003e378`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cbe5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cbe5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc3c`

## pseudocode

```c
__int64 __fastcall CMStream::Init(CMStream *this, int a2, int a3, union _ULARGE_INTEGER a4)
{
  __int64 v5; // rcx
  unsigned __int64 v6; // r14
  int v8; // r13d
  unsigned int v9; // r12d
  _QWORD *v10; // rcx
  _QWORD *v11; // rcx
  int inited; // edi
  ULONGLONG v13; // r15
  __int16 v14; // cx
  int v15; // r14d
  int v16; // r9d
  bool v17; // cc
  __int64 v18; // rbx
  int v19; // r9d
  struct CSmAllocator *TlsSmAllocator; // rax
  __int64 v21; // rcx
  struct IMalloc *const v22; // rdx
  CDirectStream *v23; // rax
  CDirectStream *v24; // rax
  unsigned int v25; // r8d
  char *v26; // rax
  CDirectStream *v27; // rcx
  unsigned int *v29; // rax
  unsigned int v30; // eax
  __int64 v31; // r9
  unsigned __int64 v32; // r8
  struct ILockBytes **v33; // rcx
  __int64 v34; // r9
  unsigned __int64 v35; // r8
  struct ILockBytes **v36; // rcx
  _OWORD *v37; // r15
  _QWORD *v38; // rcx
  __int64 v39; // rdx
  _OWORD *v40; // rax
  _OWORD *v41; // rcx
  __int128 v42; // xmm1
  unsigned int v43[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v44; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v45; // [rsp+80h] [rbp+40h] BYREF
  int v46; // [rsp+88h] [rbp+48h]
  int v47; // [rsp+90h] [rbp+50h]

  v47 = a3;
  v46 = a2;
  v5 = *(_QWORD *)this;
  v6 = 512;
  v45 = 0;
  v44 = 0;
  v8 = a2;
  v9 = 512;
  if ( v5 )
    v10 = (_QWORD *)(*(_QWORD *)NtCurrentTeb()->ReservedForOle + v5);
  else
    v10 = 0;
  if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v10)(*v10, &IID_IDfReserved1, &v44) >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 56LL))(v44);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  *(_QWORD *)v43 = 0;
  if ( v9 == 512 )
  {
    if ( *(_QWORD *)this )
      v11 = (_QWORD *)(*(_QWORD *)this + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
    else
      v11 = 0;
    inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, __int64, unsigned int *))(*(_QWORD *)*v11 + 24LL))(
               *v11,
               *(_QWORD *)v43,
               (char *)this + 16,
               512,
               &v45);
  }
  else
  {
    v37 = CoTaskMemAlloc(v9);
    if ( !v37 )
      return (unsigned int)-2147287032;
    if ( *(_QWORD *)this )
      v38 = (_QWORD *)(*(_QWORD *)this + *(_QWORD *)NtCurrentTeb()->ReservedForOle);
    else
      v38 = 0;
    inited = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _OWORD *, _QWORD, unsigned int *))(*(_QWORD *)*v38 + 24LL))(
               *v38,
               *(_QWORD *)v43,
               v37,
               v9,
               &v45);
    if ( inited >= 0 && v45 >= 0x200 )
    {
      v39 = 4;
      v40 = (_OWORD *)((char *)this + 16);
      v41 = v37;
      do
      {
        *v40 = *v41;
        v40[1] = v41[1];
        v40[2] = v41[2];
        v40[3] = v41[3];
        v40[4] = v41[4];
        v40[5] = v41[5];
        v40[6] = v41[6];
        v42 = v41[7];
        v41 += 8;
        v40[7] = v42;
        v40 += 8;
        --v39;
      }
      while ( v39 );
    }
    CoTaskMemFree(v37);
    v6 = v9;
    v8 = v46;
  }
  if ( inited == -2147483638 )
    return (unsigned int)-2147286524;
  if ( inited >= 0 )
  {
    LODWORD(v13) = 0;
    if ( v8 )
    {
      v13 = (v6 + a4.QuadPart - 1) / v6 - 1;
      if ( v13 >= 0xFFFFFFFF )
        LODWORD(v13) = -1;
    }
    v14 = *((_WORD *)this + 23);
    *((_DWORD *)this + 132) = 0;
    *((_WORD *)this + 712) = 1 << v14;
    *((_WORD *)this + 713) = v14;
    *((_WORD *)this + 714) = (1 << v14) - 1;
    if ( v45 != v9 )
      return (unsigned int)-2147286789;
    inited = CMSFHeader::Validate((CMStream *)((char *)this + 16));
    if ( inited >= 0 )
    {
      inited = CMStream::InitCommon(this);
      if ( inited >= 0 )
      {
        if ( v8
          && ((v29 = (unsigned int *)((char *)this + 60), *((_DWORD *)this + 22) > (unsigned int)v13)
           || *v29 > (unsigned int)v13) )
        {
          v15 = v47;
          if ( v47 )
            return (unsigned int)-2147286775;
          v30 = *v29;
          v31 = *((unsigned __int16 *)this + 712);
          if ( *((_DWORD *)this + 22) > v30 )
            v30 = *((_DWORD *)this + 22);
          v32 = v31 * (v30 + 1LL);
          if ( v31 + v32 > 0x7FFFFF00 && v32 <= 0x7FFFFFE3 )
            v32 += v31;
          v33 = *(_QWORD *)this
              ? (struct ILockBytes **)(*(_QWORD *)this + *(_QWORD *)NtCurrentTeb()->ReservedForOle)
              : 0LL;
          if ( (int)VerifySectorAvailableAtOffset(*v33, *((unsigned __int16 *)this + 712), v32) < 0 )
            return (unsigned int)-2147286775;
        }
        else
        {
          v15 = v47;
        }
        inited = CDIFat::Init((CMStream *)((char *)this + 752), this, *((_DWORD *)this + 22));
        if ( inited >= 0 )
        {
          inited = CFat::Init((CMStream *)((char *)this + 616), this, *((_DWORD *)this + 15), v16);
          if ( inited >= 0 )
          {
            v17 = *((_WORD *)this + 713) <= 9u;
            v43[0] = 0;
            if ( v17 )
            {
              inited = CFat::GetLength((CMStream *)((char *)this + 616), *((_DWORD *)this + 16), v43);
              if ( inited < 0 )
                return (unsigned int)inited;
              LODWORD(v18) = v43[0];
            }
            else
            {
              v18 = *((unsigned int *)this + 14);
              if ( v8 && (unsigned int)v18 > (unsigned int)v13 )
              {
                if ( v15 )
                  return (unsigned int)-2147286775;
                v34 = *((unsigned __int16 *)this + 712);
                v35 = v34 * (v18 + 1);
                if ( v34 + v35 > 0x7FFFFF00 && v35 <= 0x7FFFFFE3 )
                  v35 += v34;
                v36 = *(_QWORD *)this
                    ? (struct ILockBytes **)(*(_QWORD *)this + *(_QWORD *)NtCurrentTeb()->ReservedForOle)
                    : 0LL;
                if ( (int)VerifySectorAvailableAtOffset(*v36, *((unsigned __int16 *)this + 712), v35) < 0 )
                  return (unsigned int)-2147286775;
              }
            }
            inited = CDirectory::Init((CMStream *)((char *)this + 536), this, v18);
            if ( inited >= 0 )
            {
              inited = CFat::Init((CMStream *)((char *)this + 928), this, *((_DWORD *)this + 20), v19);
              if ( inited >= 0 )
              {
                TlsSmAllocator = GetTlsSmAllocator();
                v21 = (*(__int64 (__fastcall **)(struct CSmAllocator *, _QWORD))(*(_QWORD *)TlsSmAllocator + 24LL))(
                        TlsSmAllocator,
                        *((unsigned __int16 *)this + 712));
                if ( v21 )
                {
                  *(_QWORD *)v43 = 0;
                  *((_QWORD *)this + 171) = v21 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
                  inited = CDirectory::GetSize((CMStream *)((char *)this + 536), 0, (unsigned __int64 *)v43);
                  if ( inited < 0 )
                    return (unsigned int)inited;
                  GetTlsSmAllocator();
                  v23 = (CDirectStream *)CMallocBased::operator new(0xC8u, v22);
                  if ( v23 )
                  {
                    v24 = CDirectStream::CDirectStream(v23, 2u);
                    if ( v24 )
                    {
                      v26 = (char *)v24 - *(_QWORD *)NtCurrentTeb()->ReservedForOle;
                      *((_QWORD *)this + 169) = v26;
                      if ( v26 )
                        v27 = (CDirectStream *)&v26[*(_QWORD *)NtCurrentTeb()->ReservedForOle];
                      else
                        v27 = 0;
                      CDirectStream::InitSystem(v27, this, v25, *(unsigned __int64 *)v43);
                      return (unsigned int)inited;
                    }
                  }
                }
                return (unsigned int)-2147287032;
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000c7a0  mov     [rsp-38h+arg_18], rbx
0x18000c7a5  mov     [rsp-38h+arg_10], r8d
0x18000c7aa  mov     [rsp-38h+arg_8], edx
0x18000c7ae  push    rbp
0x18000c7af  push    rsi
0x18000c7b0  push    rdi
0x18000c7b1  push    r12
0x18000c7b3  push    r13
0x18000c7b5  push    r14
0x18000c7b7  push    r15
0x18000c7b9  mov     rbp, rsp
0x18000c7bc  sub     rsp, 40h
0x18000c7c0  xor     edi, edi
0x18000c7c2  mov     rsi, rcx
0x18000c7c5  mov     rcx, [rcx]
0x18000c7c8  mov     r14d, 200h
0x18000c7ce  mov     [rbp+arg_0], edi
0x18000c7d1  mov     rbx, r9
0x18000c7d4  mov     [rbp+var_8], rdi
0x18000c7d8  mov     r13d, edx
0x18000c7db  mov     r12d, r14d
0x18000c7de  test    rcx, rcx
0x18000c7e1  jz      loc_18000CBCF
0x18000c7e7  mov     rax, gs:30h
0x18000c7f0  mov     r8, [rax+1758h]
0x18000c7f7  add     rcx, [r8]
0x18000c7fa  mov     rcx, [rcx]
0x18000c7fd  lea     r8, [rbp+var_8]
0x18000c801  lea     rdx, IID_IDfReserved1
0x18000c808  mov     rax, [rcx]
0x18000c80b  mov     rax, [rax]
0x18000c80e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c813  test    eax, eax
0x18000c815  js      short loc_18000C83A
0x18000c817  mov     rcx, [rbp+var_8]
0x18000c81b  mov     rax, [rcx]
0x18000c81e  mov     rax, [rax+38h]
0x18000c822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c827  mov     rcx, [rbp+var_8]
0x18000c82b  mov     r12d, eax
0x18000c82e  mov     rdx, [rcx]
0x18000c831  mov     rax, [rdx+10h]
0x18000c835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c83a  mov     qword ptr [rbp+var_10], rdi
0x18000c83e  cmp     r12d, r14d
0x18000c841  jnz     loc_18000CBDF
0x18000c847  mov     rdx, [rsi]
0x18000c84a  test    rdx, rdx
0x18000c84d  jz      loc_18000CBD7
0x18000c853  mov     rax, gs:30h
0x18000c85c  mov     rcx, [rax+1758h]
0x18000c863  mov     rcx, [rcx]
0x18000c866  add     rcx, rdx
0x18000c869  mov     rcx, [rcx]
0x18000c86c  lea     rdx, [rbp+arg_0]
0x18000c870  mov     [rsp+40h+var_20], rdx
0x18000c875  lea     r8, [rsi+10h]
0x18000c879  mov     rdx, qword ptr [rbp+var_10]
0x18000c87d  mov     r9d, r14d
0x18000c880  mov     rax, [rcx]
0x18000c883  mov     rax, [rax+18h]
0x18000c887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c88c  mov     edi, eax
0x18000c88e  cmp     edi, 8000000Ah
0x18000c894  jz      loc_18000CCC6
0x18000c89a  test    edi, edi
0x18000c89c  js      loc_18000CAB4
0x18000c8a2  xor     r15d, r15d
0x18000c8a5  test    r13d, r13d
0x18000c8a8  jz      short loc_18000C8C8
0x18000c8aa  xor     edx, edx
0x18000c8ac  lea     rax, [rbx-1]
0x18000c8b0  add     rax, r14
0x18000c8b3  div     r14
0x18000c8b6  lea     r15, [rax-1]
0x18000c8ba  mov     eax, 0FFFFFFFFh
0x18000c8bf  cmp     r15, rax
0x18000c8c2  jnb     loc_18000CCD0
0x18000c8c8  movzx   ecx, word ptr [rsi+2Eh]
0x18000c8cc  mov     ebx, 1
0x18000c8d1  mov     eax, ebx
0x18000c8d3  mov     dword ptr [rsi+210h], 0
0x18000c8dd  shl     ax, cl
0x18000c8e0  mov     [rsi+590h], ax
0x18000c8e7  sub     ax, bx
0x18000c8ea  mov     [rsi+592h], cx
0x18000c8f1  mov     [rsi+594h], ax
0x18000c8f8  cmp     [rbp+arg_0], r12d
0x18000c8fc  jnz     loc_18000CCD8
0x18000c902  lea     rcx, [rsi+10h]; this
0x18000c906  call    ?Validate@CMSFHeader@@QEBAJXZ; CMSFHeader::Validate(void)
0x18000c90b  mov     edi, eax
0x18000c90d  test    eax, eax
0x18000c90f  js      loc_18000CAB4
0x18000c915  mov     rcx, rsi; this
0x18000c918  call    ?InitCommon@CMStream@@AEAAJXZ; CMStream::InitCommon(void)
0x18000c91d  mov     edi, eax
0x18000c91f  test    eax, eax
0x18000c921  js      loc_18000CAB4
0x18000c927  mov     r12d, 7FFFFFE3h
0x18000c92d  test    r13d, r13d
0x18000c930  jnz     loc_18000CACE
0x18000c936  mov     r14d, [rbp+arg_10]
0x18000c93a  mov     r8d, [rsi+58h]; unsigned int
0x18000c93e  lea     rcx, [rsi+2F0h]; this
0x18000c945  mov     rdx, rsi; struct CMStream *
0x18000c948  call    ?Init@CDIFat@@QEAAJPEAVCMStream@@K@Z; CDIFat::Init(CMStream *,ulong)
0x18000c94d  mov     edi, eax
0x18000c94f  test    eax, eax
0x18000c951  js      loc_18000CAB4
0x18000c957  mov     r8d, [rsi+3Ch]; unsigned int
0x18000c95b  lea     rbx, [rsi+268h]
0x18000c962  mov     rcx, rbx; this
0x18000c965  mov     rdx, rsi; struct CMStream *
0x18000c968  call    ?Init@CFat@@QEAAJPEAVCMStream@@KH@Z; CFat::Init(CMStream *,ulong,int)
0x18000c96d  mov     edi, eax
0x18000c96f  test    eax, eax
0x18000c971  js      loc_18000CAB4
0x18000c977  cmp     word ptr [rsi+592h], 9
0x18000c97f  mov     [rbp+var_10], 0
0x18000c986  ja      loc_18000CB54
0x18000c98c  mov     edx, [rsi+40h]; unsigned int
0x18000c98f  lea     r8, [rbp+var_10]; unsigned int *
0x18000c993  mov     rcx, rbx; this
0x18000c996  call    ?GetLength@CFat@@QEAAJKPEAK@Z; CFat::GetLength(ulong,ulong *)
0x18000c99b  mov     edi, eax
0x18000c99d  test    eax, eax
0x18000c99f  js      loc_18000CAB4
0x18000c9a5  mov     ebx, [rbp+var_10]
0x18000c9a8  lea     r14, [rsi+218h]
0x18000c9af  mov     r8d, ebx; unsigned int
0x18000c9b2  mov     rcx, r14; this
0x18000c9b5  mov     rdx, rsi; struct CMStream *
0x18000c9b8  call    ?Init@CDirectory@@QEAAJPEAVCMStream@@K@Z; CDirectory::Init(CMStream *,ulong)
0x18000c9bd  mov     edi, eax
0x18000c9bf  test    eax, eax
0x18000c9c1  js      loc_18000CAB4
0x18000c9c7  mov     r8d, [rsi+50h]; unsigned int
0x18000c9cb  lea     rcx, [rsi+3A0h]; this
0x18000c9d2  mov     rdx, rsi; struct CMStream *
0x18000c9d5  call    ?Init@CFat@@QEAAJPEAVCMStream@@KH@Z; CFat::Init(CMStream *,ulong,int)
0x18000c9da  mov     edi, eax
0x18000c9dc  test    eax, eax
0x18000c9de  js      loc_18000CAB4
0x18000c9e4  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18000c9e9  movzx   edx, word ptr [rsi+590h]
0x18000c9f0  mov     r8, rax
0x18000c9f3  mov     rcx, [rax]
0x18000c9f6  mov     rax, [rcx+18h]
0x18000c9fa  mov     rcx, r8
0x18000c9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca02  mov     rcx, rax
0x18000ca05  test    rax, rax
0x18000ca08  jz      loc_18000CBC5
0x18000ca0e  mov     rax, gs:30h
0x18000ca17  lea     r8, [rbp+var_10]; unsigned __int64 *
0x18000ca1b  mov     qword ptr [rbp+var_10], 0
0x18000ca23  mov     rdx, [rax+1758h]
0x18000ca2a  sub     rcx, [rdx]
0x18000ca2d  xor     edx, edx; unsigned int
0x18000ca2f  mov     [rsi+558h], rcx
0x18000ca36  mov     rcx, r14; this
0x18000ca39  call    ?GetSize@CDirectory@@QEAAJKPEA_K@Z; CDirectory::GetSize(ulong,unsigned __int64 *)
0x18000ca3e  mov     edi, eax
0x18000ca40  test    eax, eax
0x18000ca42  js      short loc_18000CAB4
0x18000ca44  call    ?GetTlsSmAllocator@@YAAEAVCSmAllocator@@XZ; GetTlsSmAllocator(void)
0x18000ca49  mov     ecx, 0C8h; unsigned __int64
0x18000ca4e  call    ??2CMallocBased@@SAPEAX_KQEAUIMalloc@@@Z; CMallocBased::operator new(unsigned __int64,IMalloc * const)
0x18000ca53  test    rax, rax
0x18000ca56  jz      loc_18000CBC5
0x18000ca5c  mov     edx, 2; unsigned int
0x18000ca61  mov     rcx, rax; this
0x18000ca64  call    ??0CDirectStream@@QEAA@K@Z; CDirectStream::CDirectStream(ulong)
0x18000ca69  test    rax, rax
0x18000ca6c  jz      loc_18000CBC5
0x18000ca72  mov     rcx, gs:30h
0x18000ca7b  mov     rdx, [rcx+1758h]
0x18000ca82  sub     rax, [rdx]
0x18000ca85  mov     [rsi+548h], rax
0x18000ca8c  jz      loc_18000CCFA
0x18000ca92  mov     rcx, gs:30h
0x18000ca9b  mov     rdx, [rcx+1758h]
0x18000caa2  mov     rcx, [rdx]
0x18000caa5  add     rcx, rax; this
0x18000caa8  mov     r9, qword ptr [rbp+var_10]; unsigned __int64
0x18000caac  mov     rdx, rsi; struct CMStream *
0x18000caaf  call    ?InitSystem@CDirectStream@@QEAAXPEAVCMStream@@K_K@Z; CDirectStream::InitSystem(CMStream *,ulong,unsigned __int64)
0x18000cab4  mov     rbx, [rsp+40h+arg_18]
0x18000cabc  mov     eax, edi
0x18000cabe  add     rsp, 40h
0x18000cac2  pop     r15
0x18000cac4  pop     r14
0x18000cac6  pop     r13
0x18000cac8  pop     r12
0x18000caca  pop     rdi
0x18000cacb  pop     rsi
0x18000cacc  pop     rbp
0x18000cacd  retn
0x18000cace  lea     rax, [rsi+3Ch]
0x18000cad2  cmp     [rsi+58h], r15d
0x18000cad6  ja      short loc_18000CAE1
0x18000cad8  cmp     [rax], r15d
0x18000cadb  jbe     loc_18000C936
0x18000cae1  mov     r14d, [rbp+arg_10]
0x18000cae5  test    r14d, r14d
0x18000cae8  jnz     short loc_18000CB4A
0x18000caea  mov     eax, [rax]
0x18000caec  cmp     [rsi+58h], eax
0x18000caef  movzx   r9d, word ptr [rsi+590h]
0x18000caf7  cmova   eax, [rsi+58h]
0x18000cafb  mov     r8d, eax
0x18000cafe  add     r8, rbx
0x18000cb01  imul    r8, r9; unsigned __int64
0x18000cb05  lea     rax, [r9+r8]
0x18000cb09  cmp     rax, 7FFFFF00h
0x18000cb0f  ja      loc_18000CCE2
0x18000cb15  mov     rdx, [rsi]
0x18000cb18  test    rdx, rdx
0x18000cb1b  jz      loc_18000CC53
0x18000cb21  mov     rax, gs:30h
0x18000cb2a  mov     rcx, [rax+1758h]
0x18000cb31  mov     rcx, [rcx]
0x18000cb34  add     rcx, rdx
0x18000cb37  mov     rcx, [rcx]; struct ILockBytes *
0x18000cb3a  mov     edx, r9d; unsigned int
0x18000cb3d  call    ?VerifySectorAvailableAtOffset@@YAJPEAUILockBytes@@K_K@Z; VerifySectorAvailableAtOffset(ILockBytes *,ulong,unsigned __int64)
0x18000cb42  test    eax, eax
0x18000cb44  jns     loc_18000C93A
0x18000cb4a  mov     edi, 80030109h
0x18000cb4f  jmp     loc_18000CAB4
0x18000cb54  mov     ebx, [rsi+38h]
0x18000cb57  test    r13d, r13d
0x18000cb5a  jz      loc_18000C9A8
0x18000cb60  cmp     ebx, r15d
0x18000cb63  jbe     loc_18000C9A8
0x18000cb69  test    r14d, r14d
0x18000cb6c  jnz     short loc_18000CB4A
0x18000cb6e  movzx   r9d, word ptr [rsi+590h]
0x18000cb76  lea     r8, [rbx+1]
0x18000cb7a  imul    r8, r9; unsigned __int64
0x18000cb7e  lea     rax, [r9+r8]
0x18000cb82  cmp     rax, 7FFFFF00h
0x18000cb88  ja      loc_18000CCEE
0x18000cb8e  mov     rdx, [rsi]
0x18000cb91  test    rdx, rdx
0x18000cb94  jz      loc_18000CC5A
0x18000cb9a  mov     rax, gs:30h
0x18000cba3  mov     rcx, [rax+1758h]
0x18000cbaa  mov     rcx, [rcx]
0x18000cbad  add     rcx, rdx
0x18000cbb0  mov     rcx, [rcx]; struct ILockBytes *
0x18000cbb3  mov     edx, r9d; unsigned int
0x18000cbb6  call    ?VerifySectorAvailableAtOffset@@YAJPEAUILockBytes@@K_K@Z; VerifySectorAvailableAtOffset(ILockBytes *,ulong,unsigned __int64)
0x18000cbbb  test    eax, eax
0x18000cbbd  jns     loc_18000C9A8
0x18000cbc3  jmp     short loc_18000CB4A
0x18000cbc5  mov     edi, 80030008h
0x18000cbca  jmp     loc_18000CAB4
0x18000cbcf  mov     rcx, rdi
0x18000cbd2  jmp     loc_18000C7FA
0x18000cbd7  mov     rcx, rdi
0x18000cbda  jmp     loc_18000C869
0x18000cbdf  mov     ecx, r12d; cb
0x18000cbe2  mov     r13d, r12d
0x18000cbe5  call    cs:__imp_CoTaskMemAlloc
0x18000cbeb  mov     r15, rax
0x18000cbee  test    rax, rax
0x18000cbf1  jz      short loc_18000CBC5
0x18000cbf3  mov     rdx, [rsi]
0x18000cbf6  test    rdx, rdx
0x18000cbf9  jz      short loc_18000CC4E
0x18000cbfb  mov     rax, gs:30h
0x18000cc04  mov     rcx, [rax+1758h]
0x18000cc0b  mov     rcx, [rcx]
0x18000cc0e  add     rcx, rdx
0x18000cc11  mov     rcx, [rcx]
0x18000cc14  lea     rdx, [rbp+arg_0]
0x18000cc18  mov     [rsp+40h+var_20], rdx
0x18000cc1d  mov     r9d, r12d
0x18000cc20  mov     rdx, qword ptr [rbp+var_10]
0x18000cc24  mov     r8, r15
0x18000cc27  mov     rax, [rcx]
0x18000cc2a  mov     rax, [rax+18h]
0x18000cc2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc33  mov     edi, eax
0x18000cc35  test    eax, eax
0x18000cc37  jns     short loc_18000CC61
0x18000cc39  mov     rcx, r15; pv
0x18000cc3c  call    cs:__imp_CoTaskMemFree
0x18000cc42  mov     r14, r13
0x18000cc45  mov     r13d, [rbp+arg_8]
0x18000cc49  jmp     loc_18000C88E
0x18000cc4e  mov     rcx, rdi
0x18000cc51  jmp     short loc_18000CC11
0x18000cc53  xor     ecx, ecx
0x18000cc55  jmp     loc_18000CB37
0x18000cc5a  xor     ecx, ecx
0x18000cc5c  jmp     loc_18000CBB0
0x18000cc61  cmp     [rbp+arg_0], r14d
  ... truncated ...
```
