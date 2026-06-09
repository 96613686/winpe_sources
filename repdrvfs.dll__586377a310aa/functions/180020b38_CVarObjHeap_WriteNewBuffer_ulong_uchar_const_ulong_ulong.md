# CVarObjHeap::WriteNewBuffer(ulong,uchar const *,ulong *,ulong *)

- ea: `0x180020b38`
- end: `0x180020e54`
- name: `?WriteNewBuffer@CVarObjHeap@@QEAAKKPEBEPEAK1@Z`
- size: `796`
- prototype: `unsigned int __usercall@<eax>(CVarObjHeap *__hidden this@<rcx>, unsigned int@<edx>, const unsigned __int8 *@<r8>, unsigned int *@<r9>, unsigned int *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800203a0`
- `0x180028590`

## callees

- `0x1800012b8`
- `0x18000e000`
- `0x18000f8a0`
- `0x18000f8f0`
- `0x18000fd30`
- `0x180012cd4`
- `0x1800138f4`
- `0x180020b38`
- `0x180020e5c`
- `0x180021754`
- `0x1800218e4`
- `0x180025818`
- `0x18002be34`
- `0x18002ca10`
- `0x18003d184`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x180020c33`
- `wbemcomn!GetMemLogObject` at `0x180020cd8`
- `wbemcomn!GetMemLogObject` at `0x180020d41`
- `wbemcomn!GetMemLogObject` at `0x180020c33`
- `wbemcomn!GetMemLogObject` at `0x180020cd8`
- `wbemcomn!GetMemLogObject` at `0x180020d41`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020c3e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020ce4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020d51`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020c3e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020ce4`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180020d51`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVarObjHeap::WriteNewBuffer(
        CPageFile **this,
        unsigned int a2,
        const unsigned __int8 *a3,
        unsigned int *a4,
        unsigned int *a5)
{
  __int64 v7; // r14
  CPageFile **v8; // rsi
  CPageFile *v10; // r11
  __int64 v11; // r10
  __int64 v12; // r8
  unsigned int v13; // eax
  unsigned int i; // r9d
  __int64 v15; // rdx
  unsigned int v16; // edi
  int v17; // edx
  CVarObjHeap *v18; // rcx
  unsigned int Page; // ebx
  const unsigned __int8 **v20; // rbx
  CMemoryLog *v21; // rax
  CVarObjHeap *v22; // rcx
  __int64 v23; // rdx
  unsigned int v24; // r15d
  CMemoryLog *MemLogObject; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  unsigned __int8 **v28; // rax
  unsigned int v29; // edx
  CMemoryLog *v30; // rax
  unsigned int *v31; // r15
  MemoryPage *v32[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v33; // [rsp+98h] [rbp+50h] BYREF

  v7 = a2;
  v8 = this;
  if ( a2 > 0x1FE0 )
    return CVarObjHeap::AllocateMultiPageBuffer(this, a2, a3, a4, a5);
  v32[0] = 0;
  v32[1] = (MemoryPage *)v32;
  v33 = 0;
  v10 = *this;
  v11 = *((_QWORD *)*this + 41);
  v12 = 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)*this + 42) - v11) >> 3);
  v13 = *((_DWORD *)this + 2);
  for ( i = 0; i < (unsigned int)v12; ++i )
  {
    v15 = v13 % (unsigned int)v12;
    v16 = v13 % (unsigned int)v12;
    if ( *(_DWORD *)(v11 + 24LL * (unsigned int)v15) != -1 )
    {
      this = (CPageFile **)*(unsigned int *)(v11 + 24 * v15 + 8);
      if ( (unsigned __int64)this >= v7 + 16 )
      {
        Page = CPageFile::GetPage(v10, v16, v12, v32);
        if ( !Page )
        {
          v20 = (const unsigned __int8 **)MemoryPage::Copy(v32[0]);
          MemoryPage::Release(v32[0]);
          v32[0] = (MemoryPage *)v20;
          if ( !v20 )
          {
            Page = 14;
            goto LABEL_11;
          }
          Page = CVarObjHeap::ValidatePageFreeSpaceWithAdminPage((CVarObjHeap *)v8, v20[2], v16);
        }
        v24 = 0;
        v33 = 0;
        if ( !Page )
        {
          Page = CVarObjHeap::ValidatePageFreeSpace(v18, *((const unsigned __int8 **)v32[0] + 2), v7, &v33);
          v24 = v33;
        }
        if ( Page == 1359 )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, -1);
          if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, v27, v16, v7 + 16, v24);
          }
          goto LABEL_11;
        }
LABEL_34:
        if ( Page )
          goto LABEL_11;
        v31 = a5;
        Page = CVarObjHeap::AllocateFromPage(v18, v17, *((unsigned __int8 **)v32[0] + 2), v7, a3, a5);
        if ( Page )
          goto LABEL_11;
        MemoryPage::AddRef(v32[0]);
        Page = CPageFile::PutPage(*v8, v16, 0, v32[0]);
        *((_DWORD *)v8 + 2) = v16;
        if ( Page )
          goto LABEL_11;
        *(_DWORD *)(*((_QWORD *)*v8 + 41) + 24LL * v16 + 8) += -16 - v7;
        *a4 = v16;
        if ( !*v31 )
        {
          Page = 1359;
          CRepositoryCorruption::SetRepositoryCorrupted(2, 0, 0);
          goto LABEL_11;
        }
        Page = CVarObjHeap::ValidatePageFreeSpaceWithAdminPage(
                 (CVarObjHeap *)v8,
                 *((const unsigned __int8 **)v32[0] + 2),
                 v16);
        if ( Page )
        {
LABEL_11:
          v21 = GetMemLogObject();
          CMemoryLog::Write(v21, Page);
        }
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v23 = 15;
LABEL_16:
          WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids, Page);
          goto LABEL_17;
        }
        goto LABEL_17;
      }
    }
    v13 = v15 + 1;
  }
  v28 = (unsigned __int8 **)MemoryPage::AllocatePage((unsigned int)this);
  v32[0] = (MemoryPage *)v28;
  if ( v28 )
  {
    Page = CVarObjHeap::AllocateNewPage(v8, v29, &v33, v28[2]);
    v16 = v33;
    goto LABEL_34;
  }
  v30 = GetMemLogObject();
  Page = 14;
  CMemoryLog::Write(v30, 14);
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v23 = 14;
    goto LABEL_16;
  }
LABEL_17:
  if ( v32[0] )
    MemoryPage::Release(v32[0]);
  return Page;
}

```

## disassembly

```asm
0x180020b38  push    rbp
0x180020b3a  push    rbx
0x180020b3b  push    rsi
0x180020b3c  push    rdi
0x180020b3d  push    r12
0x180020b3f  push    r13
0x180020b41  push    r14
0x180020b43  push    r15
0x180020b45  mov     rbp, rsp
0x180020b48  sub     rsp, 48h
0x180020b4c  mov     r13, r9
0x180020b4f  mov     r12, r8
0x180020b52  mov     r14d, edx
0x180020b55  mov     rsi, rcx
0x180020b58  cmp     edx, 1FE0h
0x180020b5e  jbe     short loc_180020B76
0x180020b60  mov     rax, [rbp+arg_20]
0x180020b64  mov     [rsp+48h+var_28], rax; unsigned int *
0x180020b69  mov     edx, r14d; unsigned int
0x180020b6c  call    ?AllocateMultiPageBuffer@CVarObjHeap@@IEAAKKPEBEPEAK1@Z; CVarObjHeap::AllocateMultiPageBuffer(ulong,uchar const *,ulong *,ulong *)
0x180020b71  jmp     loc_180020C85
0x180020b76  mov     [rbp+var_18], 0
0x180020b7e  lea     rax, [rbp+var_18]
0x180020b82  mov     [rbp+var_10], rax
0x180020b86  mov     [rbp+arg_8], 0
0x180020b8d  mov     r11, [rcx]
0x180020b90  mov     r10, [r11+148h]
0x180020b97  mov     r8, [r11+150h]
0x180020b9e  sub     r8, r10
0x180020ba1  sar     r8, 3
0x180020ba5  mov     rax, 0AAAAAAAAAAAAAAABh
0x180020baf  imul    r8, rax; unsigned int
0x180020bb3  mov     eax, [rcx+8]
0x180020bb6  xor     r9d, r9d
0x180020bb9  lea     rdi, WPP_GLOBAL_Control
0x180020bc0  cmp     r9d, r8d
0x180020bc3  jnb     loc_180020D33
0x180020bc9  xor     edx, edx
0x180020bcb  div     r8d
0x180020bce  mov     edi, edx
0x180020bd0  lea     rax, [rdx+rdx*2]
0x180020bd4  cmp     dword ptr [r10+rax*8], 0FFFFFFFFh
0x180020bd9  jz      short loc_180020BE9
0x180020bdb  mov     ecx, [r10+rax*8+8]
0x180020be0  lea     rax, [r14+10h]
0x180020be4  cmp     rcx, rax
0x180020be7  jnb     short loc_180020BF1
0x180020be9  inc     r9d
0x180020bec  lea     eax, [rdx+1]
0x180020bef  jmp     short loc_180020BB9
0x180020bf1  lea     r9, [rbp+var_18]; struct MemoryPage **
0x180020bf5  mov     edx, edi; unsigned int
0x180020bf7  mov     rcx, r11; this
0x180020bfa  call    ?GetPage@CPageFile@@QEAAKKKPEAPEAVMemoryPage@@@Z; CPageFile::GetPage(ulong,ulong,MemoryPage * *)
0x180020bff  mov     ebx, eax
0x180020c01  test    eax, eax
0x180020c03  jnz     loc_180020CA7
0x180020c09  mov     rcx, [rbp+var_18]; this
0x180020c0d  call    ?Copy@MemoryPage@@QEAAPEAV1@XZ; MemoryPage::Copy(void)
0x180020c12  mov     rbx, rax
0x180020c15  mov     rcx, [rbp+var_18]; this
0x180020c19  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x180020c1e  mov     [rbp+var_18], rbx
0x180020c22  test    rbx, rbx
0x180020c25  jnz     short loc_180020C96
0x180020c27  mov     ebx, 0Eh
0x180020c2c  lea     rsi, WPP_GLOBAL_Control
0x180020c33  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180020c39  mov     edx, ebx
0x180020c3b  mov     rcx, rax
0x180020c3e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180020c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c4b  cmp     rcx, rsi
0x180020c4e  jz      short loc_180020C75
0x180020c50  test    byte ptr [rcx+1Ch], 1
0x180020c54  jz      short loc_180020C75
0x180020c56  cmp     byte ptr [rcx+19h], 2
0x180020c5a  jb      short loc_180020C75
0x180020c5c  mov     edx, 0Fh
0x180020c61  mov     r9d, ebx
0x180020c64  lea     r8, WPP_b7b50d5ee7be30eff10c755ffc7afd48_Traceguids
0x180020c6b  mov     rcx, [rcx+10h]
0x180020c6f  call    WPP_SF_d
0x180020c74  nop
0x180020c75  mov     rcx, [rbp+var_18]; this
0x180020c79  test    rcx, rcx
0x180020c7c  jz      short loc_180020C83
0x180020c7e  call    ?Release@MemoryPage@@QEAAJXZ; MemoryPage::Release(void)
0x180020c83  mov     eax, ebx
0x180020c85  add     rsp, 48h
0x180020c89  pop     r15
0x180020c8b  pop     r14
0x180020c8d  pop     r13
0x180020c8f  pop     r12
0x180020c91  pop     rdi
0x180020c92  pop     rsi
0x180020c93  pop     rbx
0x180020c94  pop     rbp
0x180020c95  retn
0x180020c96  mov     r8d, edi; unsigned int
0x180020c99  mov     rdx, [rbx+10h]; unsigned __int8 *
0x180020c9d  mov     rcx, rsi; this
0x180020ca0  call    ?ValidatePageFreeSpaceWithAdminPage@CVarObjHeap@@QEAAKPEBEK@Z; CVarObjHeap::ValidatePageFreeSpaceWithAdminPage(uchar const *,ulong)
0x180020ca5  mov     ebx, eax
0x180020ca7  xor     r15d, r15d
0x180020caa  mov     [rbp+arg_8], r15d
0x180020cae  test    ebx, ebx
0x180020cb0  jnz     short loc_180020CCC
0x180020cb2  lea     r9, [rbp+arg_8]; unsigned int *
0x180020cb6  mov     r8d, r14d; unsigned int
0x180020cb9  mov     rdx, [rbp+var_18]
0x180020cbd  mov     rdx, [rdx+10h]; unsigned __int8 *
0x180020cc1  call    ?ValidatePageFreeSpace@CVarObjHeap@@IEAAKPEBEKPEAK@Z; CVarObjHeap::ValidatePageFreeSpace(uchar const *,ulong,ulong *)
0x180020cc6  mov     ebx, eax
0x180020cc8  mov     r15d, [rbp+arg_8]
0x180020ccc  cmp     ebx, 54Fh
0x180020cd2  jnz     loc_180020D97
0x180020cd8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180020cde  or      edx, 0FFFFFFFFh
0x180020ce1  mov     rcx, rax
0x180020ce4  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180020cea  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cf1  lea     rsi, WPP_GLOBAL_Control
0x180020cf8  cmp     rcx, rsi
0x180020cfb  jz      loc_180020C33
0x180020d01  test    byte ptr [rcx+1Ch], 1
0x180020d05  jz      loc_180020C33
0x180020d0b  cmp     byte ptr [rcx+19h], 2
0x180020d0f  jb      loc_180020C33
0x180020d15  lea     eax, [r14+10h]
0x180020d19  mov     dword ptr [rsp+48h+var_20], r15d
0x180020d1e  mov     dword ptr [rsp+48h+var_28], eax
0x180020d22  mov     r9d, edi
0x180020d25  mov     rcx, [rcx+10h]
0x180020d29  call    WPP_SF_DDD
0x180020d2e  jmp     loc_180020C33
0x180020d33  call    ?AllocatePage@MemoryPage@@SAPEAV1@K@Z; MemoryPage::AllocatePage(ulong)
0x180020d38  mov     [rbp+var_18], rax
0x180020d3c  test    rax, rax
0x180020d3f  jnz     short loc_180020D82
0x180020d41  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180020d47  mov     ebx, 0Eh
0x180020d4c  mov     edx, ebx
0x180020d4e  mov     rcx, rax
0x180020d51  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180020d57  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d5e  cmp     rcx, rdi
0x180020d61  jz      loc_180020C75
0x180020d67  test    byte ptr [rcx+1Ch], 1
0x180020d6b  jz      loc_180020C75
0x180020d71  cmp     byte ptr [rcx+19h], 2
0x180020d75  jb      loc_180020C75
0x180020d7b  mov     edx, ebx
0x180020d7d  jmp     loc_180020C61
0x180020d82  mov     r9, [rax+10h]; unsigned __int8 *
0x180020d86  lea     r8, [rbp+arg_8]; unsigned int *
0x180020d8a  mov     rcx, rsi; this
0x180020d8d  call    ?AllocateNewPage@CVarObjHeap@@IEAAKKPEAKPEAE@Z; CVarObjHeap::AllocateNewPage(ulong,ulong *,uchar *)
0x180020d92  mov     ebx, eax
0x180020d94  mov     edi, [rbp+arg_8]
0x180020d97  test    ebx, ebx
0x180020d99  jnz     loc_180020C2C
0x180020d9f  mov     r15, [rbp+arg_20]
0x180020da3  mov     [rsp+48h+var_20], r15; unsigned int *
0x180020da8  mov     [rsp+48h+var_28], r12; unsigned __int8 *
0x180020dad  mov     r9d, r14d; unsigned int
0x180020db0  mov     r8, [rbp+var_18]
0x180020db4  mov     r8, [r8+10h]; unsigned __int8 *
0x180020db8  call    ?AllocateFromPage@CVarObjHeap@@IEAAKKPEAEKPEBEPEAK@Z; CVarObjHeap::AllocateFromPage(ulong,uchar *,ulong,uchar const *,ulong *)
0x180020dbd  mov     ebx, eax
0x180020dbf  test    eax, eax
0x180020dc1  jnz     loc_180020C2C
0x180020dc7  mov     rcx, [rbp+var_18]; this
0x180020dcb  call    ?AddRef@MemoryPage@@QEAAJXZ; MemoryPage::AddRef(void)
0x180020dd0  mov     r9, [rbp+var_18]; struct MemoryPage *
0x180020dd4  xor     r8d, r8d; unsigned int
0x180020dd7  mov     edx, edi; unsigned int
0x180020dd9  mov     rcx, [rsi]; this
0x180020ddc  call    ?PutPage@CPageFile@@QEAAKKKPEAVMemoryPage@@@Z; CPageFile::PutPage(ulong,ulong,MemoryPage *)
0x180020de1  mov     ebx, eax
0x180020de3  mov     [rsi+8], edi
0x180020de6  test    eax, eax
0x180020de8  jnz     loc_180020C2C
0x180020dee  mov     eax, edi
0x180020df0  lea     rdx, [rax+rax*2]
0x180020df4  mov     rax, [rsi]
0x180020df7  mov     rcx, [rax+148h]
0x180020dfe  mov     eax, 0FFFFFFF0h
0x180020e03  sub     eax, r14d
0x180020e06  add     [rcx+rdx*8+8], eax
0x180020e0a  mov     [r13+0], edi
0x180020e0e  cmp     [r15], ebx
0x180020e11  jnz     short loc_180020E2A
0x180020e13  mov     ebx, 54Fh
0x180020e18  xor     r8d, r8d; unsigned int
0x180020e1b  xor     edx, edx; bool
0x180020e1d  lea     ecx, [rdx+2]; int
0x180020e20  call    ?SetRepositoryCorrupted@CRepositoryCorruption@@SAJJ_NK@Z; CRepositoryCorruption::SetRepositoryCorrupted(long,bool,ulong)
0x180020e25  jmp     loc_180020C2C
0x180020e2a  mov     r8d, edi; unsigned int
0x180020e2d  mov     rdx, [rbp+var_18]
0x180020e31  mov     rdx, [rdx+10h]; unsigned __int8 *
0x180020e35  mov     rcx, rsi; this
0x180020e38  call    ?ValidatePageFreeSpaceWithAdminPage@CVarObjHeap@@QEAAKPEBEK@Z; CVarObjHeap::ValidatePageFreeSpaceWithAdminPage(uchar const *,ulong)
0x180020e3d  mov     ebx, eax
0x180020e3f  lea     rsi, WPP_GLOBAL_Control
0x180020e46  test    eax, eax
0x180020e48  jnz     loc_180020C33
0x180020e4e  jmp     loc_180020C44
```
