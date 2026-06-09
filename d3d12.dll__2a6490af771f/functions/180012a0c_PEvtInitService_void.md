# PEvtInitService(void)

- ea: `0x180012a0c`
- end: `0x180012c77`
- name: `?PEvtInitService@@YAJXZ`
- size: `619`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002440`
- `0x1800027d0`

## callees

- `0x180008b50`
- `0x180009188`
- `0x18000be78`
- `0x180012a0c`
- `0x180012d98`
- `0x180013400`
- `0x180013618`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012a33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012be5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012a33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012be5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012c29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012c5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012c29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012c5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 PEvtInitService(void)
{
  unsigned int v0; // ebx
  __int64 v1; // rdx
  __int64 v2; // rcx
  int v3; // ebx
  __int64 v4; // rdi
  unsigned __int64 v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rax
  _DWORD *v8; // rbx
  unsigned __int64 i; // r9
  __int128 v11; // [rsp+20h] [rbp-20h] BYREF
  __int64 v12; // [rsp+30h] [rbp-10h]
  __int64 v13; // [rsp+38h] [rbp-8h]
  unsigned __int64 v14; // [rsp+70h] [rbp+30h] BYREF
  struct _RTL_CRITICAL_SECTION *v15; // [rsp+78h] [rbp+38h]

  v0 = 0;
  v15 = &g_CS_InitService;
  EnterCriticalSection(&g_CS_InitService);
  if ( !g_pPixEvtBuffer )
  {
    v14 = 0;
    v3 = PMemLargeNew(v2, v1, &v14);
    if ( v3 < 0 )
    {
      v0 = -2147483636;
    }
    else
    {
      g_pPixEvtCtrlBlk = g_pPixEvtBuffer;
      g_pStartEvtBlkBuffer = (char *)g_pPixEvtBuffer + 0x20000;
      v4 = v14;
      if ( v14 > 0x20000000 )
        v4 = 0x20000000;
      v5 = ((unsigned __int64)(v4 - 0x20000) >> 14) - 1;
      std::_Vb_val<std::allocator<bool>>::_Vb_val<std::allocator<bool>>(&v11);
      std::vector<bool>::resize(&v11, v5);
      std::vector<unsigned int>::_Tidy(&g_hPEvtAllocateBitMap);
      g_hPEvtAllocateBitMap = v11;
      qword_18001E8C0 = v12;
      v11 = 0;
      v12 = 0;
      v6 = v13;
      v13 = 0;
      qword_18001E8C8 = v6;
      std::vector<unsigned int>::_Tidy(&v11);
      std::_Vb_val<std::allocator<bool>>::_Vb_val<std::allocator<bool>>(&v11);
      std::vector<bool>::resize(&v11, v5);
      std::vector<unsigned int>::_Tidy(&g_hPEvtTransportMap);
      g_hPEvtTransportMap = v11;
      qword_18001E8E0 = v12;
      v11 = 0;
      v12 = 0;
      v7 = v13;
      v13 = 0;
      qword_18001E8E8 = v7;
      std::vector<unsigned int>::_Tidy(&v11);
      if ( v3 == 262513 )
      {
        v2 = *((_QWORD *)g_pPixEvtCtrlBlk + 1027);
      }
      else
      {
        v8 = g_pPixEvtCtrlBlk;
        memset_0(g_pPixEvtCtrlBlk, 0, 0x12478u);
        *v8 = 12;
        v8[3] = v5;
        v8[2] = 1;
        *((_QWORD *)v8 + 1027) = v4;
        v8[1] = 2;
        v8[2186] = 0;
        *((_WORD *)v8 + 4374) = -1;
        *((_WORD *)v8 + 4375) = -1;
        v8[2188] = 0;
        v8[2189] = 0;
        v8[18580] = 0;
        *((_QWORD *)v8 + 9291) = 0;
        EnterCriticalSection(&g_CS_AllocBitMap);
        for ( i = 0; i < qword_18001E8C8; ++i )
          *(_DWORD *)(g_hPEvtAllocateBitMap + 4 * (i >> 5)) &= ~(1 << (i & 0x1F));
        LeaveCriticalSection(&g_CS_AllocBitMap);
      }
      v0 = 0;
    }
  }
  if ( (Microsoft_Graphics_Tools_PixMarkersEnableBits & 1) != 0 )
    PEvtStartServiceEx(v2);
  LeaveCriticalSection(&g_CS_InitService);
  return v0;
}

```

## disassembly

```asm
0x180012a0c  mov     [rsp-28h+arg_10], rbx
0x180012a11  push    rbp
0x180012a12  push    rsi
0x180012a13  push    rdi
0x180012a14  push    r14
0x180012a16  push    r15
0x180012a18  mov     rbp, rsp
0x180012a1b  sub     rsp, 40h
0x180012a1f  xor     r14d, r14d
0x180012a22  mov     ebx, r14d
0x180012a25  lea     r15, ?g_CS_InitService@@3VCriticalSection@@A; CriticalSection g_CS_InitService
0x180012a2c  mov     [rbp+arg_8], r15
0x180012a30  mov     rcx, r15; lpCriticalSection
0x180012a33  call    cs:__imp_EnterCriticalSection
0x180012a39  nop
0x180012a3a  cmp     cs:?g_pPixEvtBuffer@@3PEAXEA, r14; void * g_pPixEvtBuffer
0x180012a41  jnz     loc_180012C49
0x180012a47  mov     [rbp+arg_0], r14
0x180012a4b  lea     r8, [rbp+arg_0]
0x180012a4f  call    PMemLargeNew
0x180012a54  mov     ebx, eax
0x180012a56  test    eax, eax
0x180012a58  js      loc_180012C44
0x180012a5e  mov     rax, cs:?g_pPixEvtBuffer@@3PEAXEA; void * g_pPixEvtBuffer
0x180012a65  mov     cs:?g_pPixEvtCtrlBlk@@3PEAUPEvtCtrlBlk@@EA, rax; PEvtCtrlBlk * g_pPixEvtCtrlBlk
0x180012a6c  add     rax, 20000h
0x180012a72  mov     cs:?g_pStartEvtBlkBuffer@@3PEAXEA, rax; void * g_pStartEvtBlkBuffer
0x180012a79  mov     rdi, [rbp+arg_0]
0x180012a7d  mov     eax, 20000000h
0x180012a82  cmp     rdi, rax
0x180012a85  cmova   rdi, rax
0x180012a89  lea     rsi, [rdi-20000h]
0x180012a90  shr     rsi, 0Eh
0x180012a94  dec     rsi
0x180012a97  lea     rcx, [rbp+var_20]
0x180012a9b  call    ??0?$_Vb_val@V?$allocator@_N@std@@@std@@QEAA@AEBV?$allocator@_N@1@@Z; std::_Vb_val<std::allocator<bool>>::_Vb_val<std::allocator<bool>>(std::allocator<bool> const &)
0x180012aa0  nop
0x180012aa1  mov     rdx, rsi
0x180012aa4  lea     rcx, [rbp+var_20]
0x180012aa8  call    ?resize@?$vector@_NV?$allocator@_N@std@@@std@@QEAAX_K_N@Z; std::vector<bool>::resize(unsigned __int64,bool)
0x180012aad  nop
0x180012aae  lea     rcx, ?g_hPEvtAllocateBitMap@@3VDynamicBitset@@A; DynamicBitset g_hPEvtAllocateBitMap
0x180012ab5  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180012aba  mov     rax, qword ptr [rbp+var_20]
0x180012abe  mov     qword ptr cs:?g_hPEvtAllocateBitMap@@3VDynamicBitset@@A, rax; DynamicBitset g_hPEvtAllocateBitMap
0x180012ac5  mov     rax, qword ptr [rbp+var_20+8]
0x180012ac9  mov     qword ptr cs:?g_hPEvtAllocateBitMap@@3VDynamicBitset@@A+8, rax; DynamicBitset g_hPEvtAllocateBitMap
0x180012ad0  mov     rax, [rbp+var_10]
0x180012ad4  mov     cs:qword_18001E8C0, rax
0x180012adb  xorps   xmm0, xmm0
0x180012ade  movdqu  [rbp+var_20], xmm0
0x180012ae3  mov     [rbp+var_10], r14
0x180012ae7  mov     rax, [rbp+var_8]
0x180012aeb  mov     [rbp+var_8], r14
0x180012aef  mov     cs:qword_18001E8C8, rax
0x180012af6  lea     rcx, [rbp+var_20]
0x180012afa  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180012aff  lea     rcx, [rbp+var_20]
0x180012b03  call    ??0?$_Vb_val@V?$allocator@_N@std@@@std@@QEAA@AEBV?$allocator@_N@1@@Z; std::_Vb_val<std::allocator<bool>>::_Vb_val<std::allocator<bool>>(std::allocator<bool> const &)
0x180012b08  nop
0x180012b09  mov     rdx, rsi
0x180012b0c  lea     rcx, [rbp+var_20]
0x180012b10  call    ?resize@?$vector@_NV?$allocator@_N@std@@@std@@QEAAX_K_N@Z; std::vector<bool>::resize(unsigned __int64,bool)
0x180012b15  nop
0x180012b16  lea     rcx, ?g_hPEvtTransportMap@@3VDynamicBitset@@A; DynamicBitset g_hPEvtTransportMap
0x180012b1d  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180012b22  mov     rax, qword ptr [rbp+var_20]
0x180012b26  mov     qword ptr cs:?g_hPEvtTransportMap@@3VDynamicBitset@@A, rax; DynamicBitset g_hPEvtTransportMap
0x180012b2d  mov     rax, qword ptr [rbp+var_20+8]
0x180012b31  mov     qword ptr cs:?g_hPEvtTransportMap@@3VDynamicBitset@@A+8, rax; DynamicBitset g_hPEvtTransportMap
0x180012b38  mov     rax, [rbp+var_10]
0x180012b3c  mov     cs:qword_18001E8E0, rax
0x180012b43  xorps   xmm0, xmm0
0x180012b46  movdqu  [rbp+var_20], xmm0
0x180012b4b  mov     [rbp+var_10], r14
0x180012b4f  mov     rax, [rbp+var_8]
0x180012b53  mov     [rbp+var_8], r14
0x180012b57  mov     cs:qword_18001E8E8, rax
0x180012b5e  lea     rcx, [rbp+var_20]
0x180012b62  call    ?_Tidy@?$vector@IV?$allocator@I@std@@@std@@AEAAXXZ; std::vector<uint>::_Tidy(void)
0x180012b67  cmp     ebx, 40171h
0x180012b6d  jz      loc_180012C31
0x180012b73  xor     edx, edx; Val
0x180012b75  mov     r8d, 12478h; Size
0x180012b7b  mov     rbx, cs:?g_pPixEvtCtrlBlk@@3PEAUPEvtCtrlBlk@@EA; PEvtCtrlBlk * g_pPixEvtCtrlBlk
0x180012b82  mov     rcx, rbx; void *
0x180012b85  call    memset_0
0x180012b8a  mov     dword ptr [rbx], 0Ch
0x180012b90  mov     [rbx+0Ch], esi
0x180012b93  mov     dword ptr [rbx+8], 1
0x180012b9a  mov     [rbx+2018h], rdi
0x180012ba1  mov     dword ptr [rbx+4], 2
0x180012ba8  mov     [rbx+2228h], r14d
0x180012baf  mov     eax, 0FFFFh
0x180012bb4  mov     [rbx+222Ch], ax
0x180012bbb  mov     [rbx+222Eh], ax
0x180012bc2  mov     [rbx+2230h], r14d
0x180012bc9  mov     [rbx+2234h], r14d
0x180012bd0  mov     [rbx+12250h], r14d
0x180012bd7  mov     [rbx+12258h], r14
0x180012bde  lea     rcx, ?g_CS_AllocBitMap@@3VCriticalSection@@A; lpCriticalSection
0x180012be5  call    cs:__imp_EnterCriticalSection
0x180012beb  mov     r9d, r14d
0x180012bee  cmp     cs:qword_18001E8C8, r14
0x180012bf5  jbe     short loc_180012C22
0x180012bf7  mov     r8, r9
0x180012bfa  shr     r8, 5
0x180012bfe  mov     rdx, qword ptr cs:?g_hPEvtAllocateBitMap@@3VDynamicBitset@@A; DynamicBitset g_hPEvtAllocateBitMap
0x180012c05  mov     ecx, r9d
0x180012c08  and     ecx, 1Fh
0x180012c0b  mov     eax, [rdx+r8*4]
0x180012c0f  btr     eax, ecx
0x180012c12  mov     [rdx+r8*4], eax
0x180012c16  inc     r9
0x180012c19  cmp     r9, cs:qword_18001E8C8
0x180012c20  jb      short loc_180012BF7
0x180012c22  lea     rcx, ?g_CS_AllocBitMap@@3VCriticalSection@@A; lpCriticalSection
0x180012c29  call    cs:__imp_LeaveCriticalSection
0x180012c2f  jmp     short loc_180012C3F
0x180012c31  mov     rax, cs:?g_pPixEvtCtrlBlk@@3PEAUPEvtCtrlBlk@@EA; PEvtCtrlBlk * g_pPixEvtCtrlBlk
0x180012c38  mov     rcx, [rax+2018h]
0x180012c3f  mov     ebx, r14d
0x180012c42  jmp     short loc_180012C49
0x180012c44  mov     ebx, 8000000Ch
0x180012c49  test    cs:Microsoft_Graphics_Tools_PixMarkersEnableBits, 1
0x180012c50  jz      short loc_180012C58
0x180012c52  call    ?PEvtStartServiceEx@@YAJK@Z; PEvtStartServiceEx(ulong)
0x180012c57  nop
0x180012c58  mov     rcx, r15; lpCriticalSection
0x180012c5b  call    cs:__imp_LeaveCriticalSection
0x180012c61  mov     eax, ebx
0x180012c63  mov     rbx, [rsp+40h+arg_10]
0x180012c6b  add     rsp, 40h
0x180012c6f  pop     r15
0x180012c71  pop     r14
0x180012c73  pop     rdi
0x180012c74  pop     rsi
0x180012c75  pop     rbp
0x180012c76  retn
```
