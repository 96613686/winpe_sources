# CMFTMultiStreamTypeHandler::~CMFTMultiStreamTypeHandler(void)

- ea: `0x1800c6048`
- end: `0x1800c6332`
- name: `??1CMFTMultiStreamTypeHandler@@UEAA@XZ`
- size: `746`
- prototype: `void __fastcall(CMFTMultiStreamTypeHandler *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001c980`
- `0x1800c63b0`

## callees

- `0x180065ba0`
- `0x1800c6048`
- `0x1800c88fc`
- `0x1800c91e4`
- `0x1800c9210`
- `0x1800c9244`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c606d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c606d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c62a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c62a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c62af`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c62af`

## pseudocode

```c
void __fastcall CMFTMultiStreamTypeHandler::~CMFTMultiStreamTypeHandler(CMFTMultiStreamTypeHandler *this)
{
  __int64 *v2; // r13
  __int64 v3; // rbx
  __int64 v4; // r14
  __int64 v5; // rdx
  unsigned int v6; // ebp
  __int64 v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // r14
  __int64 v10; // rdx
  unsigned int v11; // ebp
  __int64 v12; // rcx
  __int64 *v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 *v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // rsi
  __int64 v20; // rcx

  *(_QWORD *)this = &CMFTMultiStreamTypeHandler::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  v2 = (__int64 *)((char *)this + 16);
  v3 = *((_QWORD *)this + 2);
  if ( 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 3) - v3) >> 3) )
  {
    v4 = 0;
    do
    {
      v5 = *(_QWORD *)(v3 + 24 * v4);
      if ( (*(_QWORD *)(v3 + 24 * v4 + 8) - v5) >> 4 )
      {
        v6 = 0;
        do
        {
          v7 = *(_QWORD *)(v5 + 16LL * v6);
          if ( v7 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
            *(_QWORD *)(*(_QWORD *)(v3 + 24 * v4) + 16LL * v6) = 0;
          }
          v5 = *(_QWORD *)(v3 + 24 * v4);
          ++v6;
        }
        while ( v6 < (unsigned __int64)((*(_QWORD *)(v3 + 24 * v4 + 8) - v5) >> 4) );
      }
      *(_QWORD *)(v3 + 24 * v4 + 8) = v5;
      v4 = (unsigned int)(v4 + 1);
      v3 = *v2;
    }
    while ( (unsigned int)v4 < 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 3) - *((_QWORD *)this + 2)) >> 3) );
  }
  utl::vector<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>,utl::allocator<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>>>::_EraseTail(
    (char *)this + 16,
    v3);
  v8 = *((_QWORD *)this + 5);
  if ( 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 6) - v8) >> 3) )
  {
    v9 = 0;
    do
    {
      v10 = *(_QWORD *)(v8 + 24 * v9);
      if ( (*(_QWORD *)(v8 + 24 * v9 + 8) - v10) >> 4 )
      {
        v11 = 0;
        do
        {
          v12 = *(_QWORD *)(v10 + 16LL * v11);
          if ( v12 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            *(_QWORD *)(*(_QWORD *)(v8 + 24 * v9) + 16LL * v11) = 0;
          }
          v10 = *(_QWORD *)(v8 + 24 * v9);
          ++v11;
        }
        while ( v11 < (unsigned __int64)((*(_QWORD *)(v8 + 24 * v9 + 8) - v10) >> 4) );
      }
      *(_QWORD *)(v8 + 24 * v9 + 8) = v10;
      v9 = (unsigned int)(v9 + 1);
      v8 = *((_QWORD *)this + 5);
    }
    while ( (unsigned int)v9 < 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 6) - v8) >> 3) );
    v2 = (__int64 *)((char *)this + 16);
  }
  utl::vector<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>,utl::allocator<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>>>::_EraseTail(
    (char *)this + 40,
    v8);
  v13 = (__int64 *)((char *)this + 64);
  v14 = *((_QWORD *)this + 8);
  if ( (*((_QWORD *)this + 9) - v14) >> 3 )
  {
    v15 = 0;
    do
    {
      v16 = *(_QWORD *)(v14 + 8 * v15);
      if ( v16 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        *(_QWORD *)(*v13 + 8 * v15) = 0;
      }
      v14 = *v13;
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < (unsigned __int64)((__int64)(*((_QWORD *)this + 9) - *((_QWORD *)this + 8)) >> 3) );
  }
  v17 = (__int64 *)((char *)this + 240);
  *((_QWORD *)this + 9) = v14;
  v18 = *((_QWORD *)this + 30);
  if ( (*((_QWORD *)this + 31) - v18) >> 3 )
  {
    v19 = 0;
    do
    {
      v20 = *(_QWORD *)(v18 + 8 * v19);
      if ( v20 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        *(_QWORD *)(*v17 + 8 * v19) = 0;
      }
      v18 = *v17;
      v19 = (unsigned int)(v19 + 1);
    }
    while ( (unsigned int)v19 < (unsigned __int64)((__int64)(*((_QWORD *)this + 31) - *((_QWORD *)this + 30)) >> 3) );
  }
  *((_QWORD *)this + 31) = v18;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit((char *)this + 240);
  utl::_Tree<unsigned long,utl::pair<unsigned long const,unsigned __int64>,utl::less<unsigned long>,utl::allocator<utl::pair<unsigned long const,unsigned __int64>>,0>::clear((char *)this + 208);
  utl::vector<IMFSample *,utl::allocator<IMFSample *>>::_Uninit((char *)this + 184);
  utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit((char *)this + 160);
  utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit((char *)this + 136);
  utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit((char *)this + 112);
  utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit((char *)this + 88);
  utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit((char *)this + 64);
  utl::vector<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>,utl::allocator<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>>>::_Uninit((char *)this + 40);
  utl::vector<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>,utl::allocator<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>>>::_Uninit(v2);
  *(_QWORD *)this = &CMFTTypeHandler::`vftable';
}

```

## disassembly

```asm
0x1800c6048  push    rbx
0x1800c604a  push    rbp
0x1800c604b  push    rsi
0x1800c604c  push    rdi
0x1800c604d  push    r12
0x1800c604f  push    r13
0x1800c6051  push    r14
0x1800c6053  push    r15
0x1800c6055  sub     rsp, 28h
0x1800c6059  lea     rax, ??_7CMFTMultiStreamTypeHandler@@6B@; const CMFTMultiStreamTypeHandler::`vftable'
0x1800c6060  mov     r15, rcx
0x1800c6063  mov     [rcx], rax
0x1800c6066  add     rcx, 130h; lpCriticalSection
0x1800c606d  call    cs:__imp_EnterCriticalSection
0x1800c6073  lea     r13, [r15+10h]
0x1800c6077  mov     rsi, 0AAAAAAAAAAAAAAABh
0x1800c6081  mov     rbx, [r13+0]
0x1800c6085  mov     rax, [r13+8]
0x1800c6089  sub     rax, rbx
0x1800c608c  sar     rax, 3
0x1800c6090  imul    rax, rsi
0x1800c6094  test    rax, rax
0x1800c6097  jz      loc_1800C612B
0x1800c609d  xor     r14d, r14d
0x1800c60a0  lea     rdi, [r14+r14*2]
0x1800c60a4  mov     rdx, [rbx+rdi*8]
0x1800c60a8  mov     rax, [rbx+rdi*8+8]
0x1800c60ad  sub     rax, rdx
0x1800c60b0  sar     rax, 4
0x1800c60b4  test    rax, rax
0x1800c60b7  jz      short loc_1800C6104
0x1800c60b9  xor     ebp, ebp
0x1800c60bb  mov     esi, ebp
0x1800c60bd  add     rsi, rsi
0x1800c60c0  mov     rcx, [rdx+rsi*8]
0x1800c60c4  test    rcx, rcx
0x1800c60c7  jz      short loc_1800C60E1
0x1800c60c9  mov     rax, [rcx]
0x1800c60cc  mov     rax, [rax+10h]
0x1800c60d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c60d5  mov     rax, [rbx+rdi*8]
0x1800c60d9  mov     qword ptr [rax+rsi*8], 0
0x1800c60e1  mov     rdx, [rbx+rdi*8]
0x1800c60e5  inc     ebp
0x1800c60e7  mov     rcx, [rbx+rdi*8+8]
0x1800c60ec  sub     rcx, rdx
0x1800c60ef  mov     eax, ebp
0x1800c60f1  sar     rcx, 4
0x1800c60f5  cmp     rax, rcx
0x1800c60f8  jb      short loc_1800C60BB
0x1800c60fa  mov     rsi, 0AAAAAAAAAAAAAAABh
0x1800c6104  mov     [rbx+rdi*8+8], rdx
0x1800c6109  inc     r14d
0x1800c610c  mov     rbx, [r13+0]
0x1800c6110  mov     rcx, [r13+8]
0x1800c6114  sub     rcx, rbx
0x1800c6117  mov     eax, r14d
0x1800c611a  sar     rcx, 3
0x1800c611e  imul    rcx, rsi
0x1800c6122  cmp     rax, rcx
0x1800c6125  jb      loc_1800C60A0
0x1800c612b  mov     rdx, rbx
0x1800c612e  mov     rcx, r13
0x1800c6131  call    ?_EraseTail@?$vector@V?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@V?$allocator@V?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@@2@@utl@@AEAAXPEAV?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@2@@Z; utl::vector<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>,utl::allocator<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>>>::_EraseTail(utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>> *)
0x1800c6136  lea     r12, [r15+28h]
0x1800c613a  mov     rbx, [r12]
0x1800c613e  mov     rax, [r12+8]
0x1800c6143  sub     rax, rbx
0x1800c6146  sar     rax, 3
0x1800c614a  imul    rax, rsi
0x1800c614e  test    rax, rax
0x1800c6151  jz      loc_1800C61E6
0x1800c6157  xor     r14d, r14d
0x1800c615a  mov     r13, 0AAAAAAAAAAAAAAABh
0x1800c6164  lea     rsi, [r14+r14*2]
0x1800c6168  mov     rdx, [rbx+rsi*8]
0x1800c616c  mov     rax, [rbx+rsi*8+8]
0x1800c6171  sub     rax, rdx
0x1800c6174  sar     rax, 4
0x1800c6178  test    rax, rax
0x1800c617b  jz      short loc_1800C61BE
0x1800c617d  xor     ebp, ebp
0x1800c617f  mov     edi, ebp
0x1800c6181  add     rdi, rdi
0x1800c6184  mov     rcx, [rdx+rdi*8]
0x1800c6188  test    rcx, rcx
0x1800c618b  jz      short loc_1800C61A5
0x1800c618d  mov     rax, [rcx]
0x1800c6190  mov     rax, [rax+10h]
0x1800c6194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6199  mov     rax, [rbx+rsi*8]
0x1800c619d  mov     qword ptr [rax+rdi*8], 0
0x1800c61a5  mov     rdx, [rbx+rsi*8]
0x1800c61a9  inc     ebp
0x1800c61ab  mov     rcx, [rbx+rsi*8+8]
0x1800c61b0  sub     rcx, rdx
0x1800c61b3  mov     eax, ebp
0x1800c61b5  sar     rcx, 4
0x1800c61b9  cmp     rax, rcx
0x1800c61bc  jb      short loc_1800C617F
0x1800c61be  mov     [rbx+rsi*8+8], rdx
0x1800c61c3  inc     r14d
0x1800c61c6  mov     rbx, [r12]
0x1800c61ca  mov     rcx, [r12+8]
0x1800c61cf  sub     rcx, rbx
0x1800c61d2  mov     eax, r14d
0x1800c61d5  sar     rcx, 3
0x1800c61d9  imul    rcx, r13
0x1800c61dd  cmp     rax, rcx
0x1800c61e0  jb      short loc_1800C6164
0x1800c61e2  lea     r13, [r15+10h]
0x1800c61e6  mov     rdx, rbx
0x1800c61e9  mov     rcx, r12
0x1800c61ec  call    ?_EraseTail@?$vector@V?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@V?$allocator@V?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@@2@@utl@@AEAAXPEAV?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@2@@Z; utl::vector<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>,utl::allocator<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>>>::_EraseTail(utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>> *)
0x1800c61f1  lea     rdi, [r15+40h]
0x1800c61f5  mov     rdx, [rdi]
0x1800c61f8  mov     rax, [rdi+8]
0x1800c61fc  sub     rax, rdx
0x1800c61ff  sar     rax, 3
0x1800c6203  test    rax, rax
0x1800c6206  jz      short loc_1800C6241
0x1800c6208  xor     ebx, ebx
0x1800c620a  mov     rcx, [rdx+rbx*8]
0x1800c620e  test    rcx, rcx
0x1800c6211  jz      short loc_1800C622A
0x1800c6213  mov     rax, [rcx]
0x1800c6216  mov     rax, [rax+10h]
0x1800c621a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c621f  mov     rax, [rdi]
0x1800c6222  mov     qword ptr [rax+rbx*8], 0
0x1800c622a  mov     rdx, [rdi]
0x1800c622d  inc     ebx
0x1800c622f  mov     rcx, [rdi+8]
0x1800c6233  sub     rcx, rdx
0x1800c6236  mov     eax, ebx
0x1800c6238  sar     rcx, 3
0x1800c623c  cmp     rax, rcx
0x1800c623f  jb      short loc_1800C620A
0x1800c6241  lea     rbx, [r15+0F0h]
0x1800c6248  mov     [rdi+8], rdx
0x1800c624c  mov     rdx, [rbx]
0x1800c624f  mov     rax, [rbx+8]
0x1800c6253  sub     rax, rdx
0x1800c6256  sar     rax, 3
0x1800c625a  test    rax, rax
0x1800c625d  jz      short loc_1800C6298
0x1800c625f  xor     esi, esi
0x1800c6261  mov     rcx, [rdx+rsi*8]
0x1800c6265  test    rcx, rcx
0x1800c6268  jz      short loc_1800C6281
0x1800c626a  mov     rax, [rcx]
0x1800c626d  mov     rax, [rax+10h]
0x1800c6271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6276  mov     rax, [rbx]
0x1800c6279  mov     qword ptr [rax+rsi*8], 0
0x1800c6281  mov     rdx, [rbx]
0x1800c6284  inc     esi
0x1800c6286  mov     rcx, [rbx+8]
0x1800c628a  sub     rcx, rdx
0x1800c628d  mov     eax, esi
0x1800c628f  sar     rcx, 3
0x1800c6293  cmp     rax, rcx
0x1800c6296  jb      short loc_1800C6261
0x1800c6298  lea     rsi, [r15+130h]
0x1800c629f  mov     [rbx+8], rdx
0x1800c62a3  mov     rcx, rsi; lpCriticalSection
0x1800c62a6  call    cs:__imp_LeaveCriticalSection
0x1800c62ac  mov     rcx, rsi; lpCriticalSection
0x1800c62af  call    cs:__imp_DeleteCriticalSection
0x1800c62b5  mov     rcx, rbx
0x1800c62b8  call    ?_Uninit@?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@AEAAXXZ; utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit(void)
0x1800c62bd  lea     rcx, [r15+0D0h]
0x1800c62c4  call    ?clear@?$_Tree@KU?$pair@$$CBK_K@utl@@U?$less@K@2@V?$allocator@U?$pair@$$CBK_K@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<ulong,utl::pair<ulong const,unsigned __int64>,utl::less<ulong>,utl::allocator<utl::pair<ulong const,unsigned __int64>>,0>::clear(void)
0x1800c62c9  lea     rcx, [r15+0B8h]
0x1800c62d0  call    ?_Uninit@?$vector@PEAUIMFSample@@V?$allocator@PEAUIMFSample@@@utl@@@utl@@AEAAXXZ; utl::vector<IMFSample *,utl::allocator<IMFSample *>>::_Uninit(void)
0x1800c62d5  lea     rcx, [r15+0A0h]
0x1800c62dc  call    ?_Uninit@?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@AEAAXXZ; utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit(void)
0x1800c62e1  lea     rcx, [r15+88h]
0x1800c62e8  call    ?_Uninit@?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@AEAAXXZ; utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit(void)
0x1800c62ed  lea     rcx, [r15+70h]
0x1800c62f1  call    ?_Uninit@?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@AEAAXXZ; utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit(void)
0x1800c62f6  lea     rcx, [r15+58h]
0x1800c62fa  call    ?_Uninit@?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@AEAAXXZ; utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit(void)
0x1800c62ff  mov     rcx, rdi
0x1800c6302  call    ?_Uninit@?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@AEAAXXZ; utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::_Uninit(void)
0x1800c6307  mov     rcx, r12
0x1800c630a  call    ?_Uninit@?$vector@V?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@V?$allocator@V?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>,utl::allocator<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>>>::_Uninit(void)
0x1800c630f  mov     rcx, r13
0x1800c6312  call    ?_Uninit@?$vector@V?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@V?$allocator@V?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>,utl::allocator<utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>>>::_Uninit(void)
0x1800c6317  lea     rax, ??_7CMFTTypeHandler@@6B@; const CMFTTypeHandler::`vftable'
0x1800c631e  mov     [r15], rax
0x1800c6321  add     rsp, 28h
0x1800c6325  pop     r15
0x1800c6327  pop     r14
0x1800c6329  pop     r13
0x1800c632b  pop     r12
0x1800c632d  pop     rdi
0x1800c632e  pop     rsi
0x1800c632f  pop     rbp
0x1800c6330  pop     rbx
0x1800c6331  retn
```
