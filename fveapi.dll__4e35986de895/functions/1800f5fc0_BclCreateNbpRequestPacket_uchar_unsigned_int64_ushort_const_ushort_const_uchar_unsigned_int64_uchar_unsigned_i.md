# BclCreateNbpRequestPacket(uchar *,unsigned __int64,ushort const *,ushort const *,uchar *,unsigned __int64,uchar *,unsigned __int64,uchar * *,unsigned __int64 *,uint *)

- ea: `0x1800f5fc0`
- end: `0x1800f65ec`
- name: `?BclCreateNbpRequestPacket@@YAJPEAE_KPEBG20101PEAPEAEPEA_KPEAI@Z`
- size: `1580`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int64, unsigned __int16 *, const unsigned __int16 *, unsigned __int8 *, unsigned __int64, unsigned __int8 *Src, unsigned __int64, unsigned __int8 **, unsigned __int64 *, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a5d3c`

## callees

- `0x180038730`
- `0x18004c458`
- `0x18004c678`
- `0x180060196`
- `0x1800601a2`
- `0x1800a4530`
- `0x1800a45cc`
- `0x1800a475c`
- `0x1800f5fc0`
- `0x1800f6ad4`
- `0x1800f6b14`
- `0x1800f6f00`
- `0x1800f71d4`
- `0x1800f7278`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f64b5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f64b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f64f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f650e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6584`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f64f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f650e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6584`

## string_xrefs

- `0x1800f620a`: `onecore\base\ngscb\cornerstone\nkpcommonlib\nbppacket.cpp`
- `0x1800f62ea`: `onecore\base\ngscb\cornerstone\nkpcommonlib\nbppacket.cpp`
- `0x1800f6339`: `onecore\base\ngscb\cornerstone\nkpcommonlib\nbppacket.cpp`
- `0x1800f6377`: `onecore\base\ngscb\cornerstone\nkpcommonlib\nbppacket.cpp`
- `0x1800f63f1`: `onecore\base\ngscb\cornerstone\nkpcommonlib\nbppacket.cpp`
- `0x1800f6547`: `onecore\base\ngscb\cornerstone\nkpcommonlib\nbppacket.cpp`
- `0x1800f65af`: `onecore\base\ngscb\cornerstone\nkpcommonlib\nbppacket.cpp`

## pseudocode

```c
__int64 __fastcall BclCreateNbpRequestPacket(
        unsigned __int8 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int8 *a5,
        unsigned __int64 a6,
        unsigned __int8 *Src,
        unsigned __int64 a8,
        unsigned __int8 **a9,
        unsigned __int64 *a10,
        unsigned int *a11)
{
  __int64 v13; // rdx
  int v14; // eax
  unsigned __int8 v15; // r9
  int v16; // ebx
  __int64 v17; // r9
  size_t v18; // rdi
  int v19; // eax
  int v20; // ebx
  unsigned __int8 v21; // al
  _WORD *v22; // rdi
  __int16 *v23; // rbx
  __int16 *v24; // rbx
  _BYTE *v25; // rcx
  int v26; // eax
  HLOCAL v27; // rcx
  int v28; // eax
  __int64 v29; // rdx
  BclStageOutput *v30; // rcx
  BclStageOutput *v31; // rcx
  DWORD LowPart; // eax
  HLOCAL v33; // rcx
  HLOCAL v34; // rcx
  HLOCAL v36; // rcx
  int v37; // [rsp+20h] [rbp-E0h]
  char *v38; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v39[8]; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v40; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v42; // [rsp+58h] [rbp-A8h] BYREF
  void *v43; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v44; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v45[8]; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL *p_hMem; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 *v47; // [rsp+80h] [rbp-80h] BYREF
  char v48; // [rsp+88h] [rbp-78h]
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp-70h] BYREF
  void *v50; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v51; // [rsp+A0h] [rbp-60h]
  unsigned int *v52; // [rsp+A8h] [rbp-58h]
  unsigned __int8 **v53; // [rsp+B0h] [rbp-50h]
  unsigned __int64 *v54; // [rsp+B8h] [rbp-48h]
  _WORD v55[8]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v56; // [rsp+D0h] [rbp-30h]
  char v57; // [rsp+D2h] [rbp-2Eh] BYREF
  unsigned __int8 v58; // [rsp+D3h] [rbp-2Dh]
  _BYTE v59[268]; // [rsp+D4h] [rbp-2Ch] BYREF
  __int16 v60; // [rsp+1E0h] [rbp+E0h]
  int v61; // [rsp+1E2h] [rbp+E2h] BYREF
  char v62; // [rsp+1E6h] [rbp+E6h]
  char v63; // [rsp+1E7h] [rbp+E7h]
  char v64; // [rsp+1E8h] [rbp+E8h]
  _BYTE v65[263]; // [rsp+1E9h] [rbp+E9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  v51 = a3;
  v43 = a1;
  v53 = a9;
  v54 = a10;
  v52 = a11;
  BclStageOutput::BclStageOutput((BclStageOutput *)v45, 5);
  v55[5] = 82;
  memset_0(v59, 0, 0xFEu);
  memset_0(v65, 0, 0xF9u);
  qmemcpy(v55, "<\tBITLOCKE", 10);
  if ( (a6 & 1) != 0 )
  {
    v13 = 273;
LABEL_44:
    v16 = -2147024809;
    v17 = 2147942487LL;
    goto LABEL_45;
  }
  v39[0] = 0;
  v14 = UIntPtrToUInt8(a6 >> 1, v39);
  v16 = v14;
  if ( v14 < 0 )
  {
    v17 = (unsigned int)v14;
    v13 = 278;
LABEL_45:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\nbppacket.cpp",
      (const char *)v17,
      v37);
    goto LABEL_46;
  }
  v18 = v39[0];
  if ( v39[0] > 0xFCu || (unsigned __int64)v39[0] + 24 > 0xFF )
  {
    v13 = 286;
    goto LABEL_44;
  }
  v56 = 43;
  v39[0] = v15;
  v19 = UIntPtrToUInt8(0x14u, v39);
  v16 = v19;
  if ( v19 < 0 )
  {
    v17 = (unsigned int)v19;
    v13 = 295;
    goto LABEL_45;
  }
  v57 = 1;
  v20 = v39[0];
  v58 = v39[0];
  memcpy_0(v59, Src, v39[0]);
  v21 = v20 + 2 + HIBYTE(v56);
  HIBYTE(v56) = v21;
  *(&v57 + v21) = 2;
  v59[v21 - 1] = v18;
  memcpy_0(&v59[v21], a5, v18);
  HIBYTE(v56) += v18 + 2;
  if ( HIBYTE(v56) != (_DWORD)v18 + v20 + 4 )
  {
    v13 = 313;
    goto LABEL_44;
  }
  v60 = 125;
  if ( (unsigned int)(v18 + 7) > 0xFF )
  {
    v13 = 345;
    goto LABEL_44;
  }
  v61 = 922812416;
  v62 = v18 + 2;
  v63 = 1;
  v64 = v18;
  memcpy_0(v65, &a5[v18], v18);
  HIBYTE(v60) += v18 + 7;
  if ( HIBYTE(v60) != (_DWORD)v18 + 7 )
  {
    v13 = 364;
    goto LABEL_44;
  }
  wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&v50, 0x5C0u);
  v22 = v50;
  if ( !v50 )
  {
    v16 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x176,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\nbppacket.cpp",
      (const char *)0x8007000ELL,
      v37);
LABEL_46:
    BclStageOutput::~BclStageOutput((BclStageOutput *)v45);
    return (unsigned int)v16;
  }
  memset_0(v50, 0, 0x5C0u);
  v22[120] = v55[0];
  memmove_0(v22 + 121, &v55[1], HIBYTE(v55[0]));
  v23 = (_WORD *)((char *)v22 + HIBYTE(v55[0]) + 242);
  *v23 = v56;
  memmove_0(v23 + 1, &v57, HIBYTE(v56));
  v24 = (__int16 *)((char *)v23 + HIBYTE(v56) + 2);
  *v24 = v60;
  memmove_0(v24 + 1, &v61, HIBYTE(v60));
  v25 = (char *)v24 + HIBYTE(v60) + 2;
  *v25 = -1;
  v42 = 0;
  v26 = ULongLongToULong(v25 - (_BYTE *)v22 + 1, &v42);
  v16 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x192,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\nbppacket.cpp",
      (const char *)(unsigned int)v26,
      v37);
    goto LABEL_19;
  }
  if ( a2 > 0x10 )
  {
    v16 = -2147024883;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x199,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\nbppacket.cpp",
      (const char *)0x8007000DLL,
      (int)"Packet space for physical address is too small. %zu, %zu",
      (const char *)0x10,
      a2);
LABEL_19:
    if ( !v22 )
      goto LABEL_46;
LABEL_42:
    wil::hlocal_secure_deleter::operator()<unsigned char>((__int64)v27, v22);
    goto LABEL_46;
  }
  *((_DWORD *)v22 + 59) = 1666417251;
  *v22 = 257;
  v28 = UIntPtrToUInt8(a2, (unsigned __int8 *)v22 + 2);
  v16 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19F,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\nbppacket.cpp",
      (const char *)(unsigned int)v28,
      v37);
    goto LABEL_42;
  }
  v22[4] = -1;
  memmove_0(v22 + 14, v43, a2);
  v40 = 0;
  hMem = 0;
  v44 = 0;
  v43 = 0;
  p_hMem = &v40;
  v47 = 0;
  v48 = 1;
  v16 = BclIpAddressToByteArray(v51, &v47, &v44);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
  if ( v16 < 0 )
  {
    v29 = 424;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\nbppacket.cpp",
      (const char *)(unsigned int)v16,
      v37);
LABEL_38:
    v36 = hMem;
    hMem = 0;
    if ( v36 )
      LocalFree(v36);
    v27 = v40;
    v40 = 0;
    if ( v27 )
      LocalFree(v27);
    goto LABEL_42;
  }
  p_hMem = &hMem;
  v47 = 0;
  v48 = 1;
  v16 = BclIpAddressToByteArray(a4, &v47, (unsigned __int64 *)&v43);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
  if ( v16 < 0 )
  {
    v29 = 425;
    goto LABEL_27;
  }
  BclStageOutput::LogByteArray(v30, L"CiAddr", (unsigned __int8 *)v40, v44);
  BclStageOutput::LogByteArray(v31, L"SiAddr", (unsigned __int8 *)hMem, (unsigned __int64)v43);
  if ( v44 != 4 || v43 != (void *)4 )
  {
    v16 = -2147024883;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\nbppacket.cpp",
      (const char *)0x8007000DLL,
      (int)"Invalid IP address",
      v38);
    goto LABEL_38;
  }
  *((_DWORD *)v22 + 3) = *(_DWORD *)v40;
  *((_DWORD *)v22 + 4) = *(_DWORD *)v40;
  *((_DWORD *)v22 + 5) = *(_DWORD *)hMem;
  *((_DWORD *)v22 + 6) = 0;
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  LowPart = PerformanceCount.LowPart;
  *((_DWORD *)v22 + 1) = PerformanceCount.LowPart;
  *v52 = LowPart;
  v50 = 0;
  *v53 = (unsigned __int8 *)v22;
  *v54 = v42;
  v33 = hMem;
  hMem = 0;
  if ( v33 )
    LocalFree(v33);
  v34 = v40;
  v40 = 0;
  if ( v34 )
    LocalFree(v34);
  BclStageOutput::~BclStageOutput((BclStageOutput *)v45);
  return 0;
}

```

## disassembly

```asm
0x1800f5fc0  push    rbp
0x1800f5fc2  push    rbx
0x1800f5fc3  push    rsi
0x1800f5fc4  push    rdi
0x1800f5fc5  push    r12
0x1800f5fc7  push    r13
0x1800f5fc9  push    r14
0x1800f5fcb  push    r15
0x1800f5fcd  lea     rbp, [rsp-208h]
0x1800f5fd5  sub     rsp, 308h
0x1800f5fdc  mov     rax, cs:__security_cookie
0x1800f5fe3  xor     rax, rsp
0x1800f5fe6  mov     [rbp+240h+var_50], rax
0x1800f5fed  mov     r13, r9
0x1800f5ff0  mov     [rbp+240h+var_2A0], r8
0x1800f5ff4  mov     rsi, rdx
0x1800f5ff7  mov     [rsp+340h+var_2E0], rcx
0x1800f5ffc  mov     r15, [rbp+240h+arg_20]
0x1800f6003  mov     r12, [rbp+240h+Src]
0x1800f600a  mov     rax, [rbp+240h+arg_40]
0x1800f6011  mov     [rbp+240h+var_290], rax
0x1800f6015  mov     rax, [rbp+240h+arg_48]
0x1800f601c  mov     [rbp+240h+var_288], rax
0x1800f6020  mov     rax, [rbp+240h+arg_50]
0x1800f6027  mov     [rbp+240h+var_298], rax
0x1800f602b  mov     edx, 5
0x1800f6030  lea     rcx, [rsp+340h+var_2D0]
0x1800f6035  call    ??0BclStageOutput@@QEAA@W4BCL_STAGE_ID@@@Z; BclStageOutput::BclStageOutput(BCL_STAGE_ID)
0x1800f603a  nop
0x1800f603b  mov     [rbp+240h+var_276], 52h ; 'R'
0x1800f6041  xor     edx, edx; Val
0x1800f6043  mov     r8d, 0FEh; Size
0x1800f6049  lea     rcx, [rbp+240h+var_26C]; void *
0x1800f604d  call    memset_0
0x1800f6052  xor     edx, edx; Val
0x1800f6054  mov     r8d, 0F9h; Size
0x1800f605a  lea     rcx, [rbp+240h+var_157]; void *
0x1800f6061  call    memset_0
0x1800f6066  mov     [rbp+240h+var_280], 93Ch
0x1800f606c  mov     rax, 454B434F4C544942h
0x1800f6076  mov     [rbp+240h+var_27E], rax
0x1800f607a  mov     rcx, [rbp+240h+arg_28]
0x1800f6081  test    cl, 1
0x1800f6084  jz      short loc_1800F6090
0x1800f6086  mov     edx, 111h
0x1800f608b  jmp     loc_1800F65A0
0x1800f6090  xor     r9d, r9d
0x1800f6093  mov     [rsp+340h+var_300], r9b
0x1800f6098  shr     rcx, 1; unsigned __int64
0x1800f609b  lea     rdx, [rsp+340h+var_300]; unsigned __int8 *
0x1800f60a0  call    ?UIntPtrToUInt8@@YAJ_KPEAE@Z; UIntPtrToUInt8(unsigned __int64,uchar *)
0x1800f60a5  mov     ebx, eax
0x1800f60a7  test    eax, eax
0x1800f60a9  jns     short loc_1800F60B8
0x1800f60ab  mov     r9d, eax
0x1800f60ae  mov     edx, 116h
0x1800f60b3  jmp     loc_1800F65A8
0x1800f60b8  movzx   edi, [rsp+340h+var_300]
0x1800f60bd  cmp     dil, 0FCh
0x1800f60c1  ja      loc_1800F659B
0x1800f60c7  lea     rax, [rdi+18h]
0x1800f60cb  cmp     rax, 0FFh
0x1800f60d1  ja      loc_1800F659B
0x1800f60d7  mov     [rbp+240h+var_270], 2Bh ; '+'
0x1800f60dd  mov     [rsp+340h+var_300], r9b
0x1800f60e2  lea     rdx, [rsp+340h+var_300]; unsigned __int8 *
0x1800f60e7  mov     ecx, 14h; unsigned __int64
0x1800f60ec  call    ?UIntPtrToUInt8@@YAJ_KPEAE@Z; UIntPtrToUInt8(unsigned __int64,uchar *)
0x1800f60f1  mov     ebx, eax
0x1800f60f3  test    eax, eax
0x1800f60f5  jns     short loc_1800F6104
0x1800f60f7  mov     r9d, eax
0x1800f60fa  mov     edx, 127h
0x1800f60ff  jmp     loc_1800F65A8
0x1800f6104  mov     [rbp+240h+var_26E], 1
0x1800f6108  movzx   ebx, [rsp+340h+var_300]
0x1800f610d  mov     [rbp+240h+var_26D], bl
0x1800f6110  mov     r8d, ebx; Size
0x1800f6113  mov     rdx, r12; Src
0x1800f6116  lea     rcx, [rbp+240h+var_26C]; void *
0x1800f611a  call    memcpy_0
0x1800f611f  lea     ecx, [rbx+2]
0x1800f6122  mov     al, byte ptr [rbp+240h+var_270+1]
0x1800f6125  add     al, cl
0x1800f6127  mov     byte ptr [rbp+240h+var_270+1], al
0x1800f612a  movzx   ecx, al
0x1800f612d  mov     [rbp+rcx+240h+var_26E], 2
0x1800f6132  mov     [rbp+rcx+240h+var_26D], dil
0x1800f6137  lea     rcx, [rbp+rcx+240h+var_26C]; void *
0x1800f613c  mov     r8, rdi; Size
0x1800f613f  mov     rdx, r15; Src
0x1800f6142  call    memcpy_0
0x1800f6147  lea     eax, [rdi+2]
0x1800f614a  mov     cl, byte ptr [rbp+240h+var_270+1]
0x1800f614d  add     cl, al
0x1800f614f  mov     byte ptr [rbp+240h+var_270+1], cl
0x1800f6152  movzx   edx, cl
0x1800f6155  lea     ecx, [rbx+4]
0x1800f6158  add     ecx, edi
0x1800f615a  cmp     edx, ecx
0x1800f615c  jz      short loc_1800F6168
0x1800f615e  mov     edx, 139h
0x1800f6163  jmp     loc_1800F65A0
0x1800f6168  mov     [rbp+240h+var_160], 7Dh ; '}'
0x1800f6171  xor     r12d, r12d
0x1800f6174  lea     ebx, [rdi+7]
0x1800f6177  cmp     ebx, 0FFh
0x1800f617d  jbe     short loc_1800F6189
0x1800f617f  mov     edx, 159h
0x1800f6184  jmp     loc_1800F65A0
0x1800f6189  mov     [rbp+240h+var_15E], 37010000h
0x1800f6193  lea     eax, [rdi+2]
0x1800f6196  mov     [rbp+240h+var_15A], al
0x1800f619c  mov     [rbp+240h+var_159], 1
0x1800f61a3  mov     [rbp+240h+var_158], dil
0x1800f61aa  lea     rdx, [r15+rdi]; Src
0x1800f61ae  mov     r8, rdi; Size
0x1800f61b1  lea     rcx, [rbp+240h+var_157]; void *
0x1800f61b8  call    memcpy_0
0x1800f61bd  add     dil, 7
0x1800f61c1  mov     al, byte ptr [rbp+240h+var_160+1]
0x1800f61c7  add     al, dil
0x1800f61ca  mov     byte ptr [rbp+240h+var_160+1], al
0x1800f61d0  movzx   eax, al
0x1800f61d3  cmp     eax, ebx
0x1800f61d5  jz      short loc_1800F61E1
0x1800f61d7  mov     edx, 16Ch
0x1800f61dc  jmp     loc_1800F65A0
0x1800f61e1  mov     ebx, 5C0h
0x1800f61e6  mov     edx, ebx
0x1800f61e8  lea     rcx, [rbp+240h+var_2A8]
0x1800f61ec  call    ??$make_unique_hlocal_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure_nothrow<uchar [0]>(unsigned __int64)
0x1800f61f1  nop
0x1800f61f2  mov     rdi, [rbp+240h+var_2A8]
0x1800f61f6  test    rdi, rdi
0x1800f61f9  jnz     short loc_1800F6221
0x1800f61fb  mov     rcx, [rbp+248h]; this
0x1800f6202  mov     ebx, 8007000Eh
0x1800f6207  mov     r9d, ebx; char *
0x1800f620a  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f6211  mov     edx, 176h; void *
0x1800f6216  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f621b  nop
0x1800f621c  jmp     loc_1800F65BC
0x1800f6221  mov     r8, rbx; Size
0x1800f6224  xor     edx, edx; Val
0x1800f6226  mov     rcx, rdi; void *
0x1800f6229  call    memset_0
0x1800f622e  mov     al, byte ptr [rbp+240h+var_280]
0x1800f6231  mov     [rdi+0F0h], al
0x1800f6237  mov     al, byte ptr [rbp+240h+var_280+1]
0x1800f623a  mov     [rdi+0F1h], al
0x1800f6240  movzx   r8d, byte ptr [rbp+240h+var_280+1]; Size
0x1800f6245  lea     rcx, [rdi+0F2h]; void *
0x1800f624c  lea     rdx, [rbp+240h+var_27E]; Src
0x1800f6250  call    memmove_0
0x1800f6255  movzx   ebx, byte ptr [rbp+240h+var_280+1]
0x1800f6259  add     rbx, 0F2h
0x1800f6260  add     rbx, rdi
0x1800f6263  mov     al, byte ptr [rbp+240h+var_270]
0x1800f6266  mov     [rbx], al
0x1800f6268  mov     al, byte ptr [rbp+240h+var_270+1]
0x1800f626b  mov     [rbx+1], al
0x1800f626e  movzx   r8d, byte ptr [rbp+240h+var_270+1]; Size
0x1800f6273  lea     rcx, [rbx+2]; void *
0x1800f6277  lea     rdx, [rbp+240h+var_26E]; Src
0x1800f627b  call    memmove_0
0x1800f6280  movzx   eax, byte ptr [rbp+240h+var_270+1]
0x1800f6284  add     rax, 2
0x1800f6288  add     rbx, rax
0x1800f628b  mov     al, byte ptr [rbp+240h+var_160]
0x1800f6291  mov     [rbx], al
0x1800f6293  mov     al, byte ptr [rbp+240h+var_160+1]
0x1800f6299  mov     [rbx+1], al
0x1800f629c  movzx   r8d, byte ptr [rbp+240h+var_160+1]; Size
0x1800f62a4  lea     rcx, [rbx+2]; void *
0x1800f62a8  lea     rdx, [rbp+240h+var_15E]; Src
0x1800f62af  call    memmove_0
0x1800f62b4  movzx   ecx, byte ptr [rbp+240h+var_160+1]
0x1800f62bb  add     rcx, 2
0x1800f62bf  add     rcx, rbx
0x1800f62c2  mov     byte ptr [rcx], 0FFh
0x1800f62c5  mov     [rsp+340h+var_2E8], r12d
0x1800f62ca  sub     rcx, rdi
0x1800f62cd  inc     rcx; unsigned __int64
0x1800f62d0  lea     rdx, [rsp+340h+var_2E8]; unsigned int *
0x1800f62d5  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800f62da  mov     ebx, eax
0x1800f62dc  test    eax, eax
0x1800f62de  jns     short loc_1800F630A
0x1800f62e0  mov     rcx, [rbp+248h]; this
0x1800f62e7  mov     r9d, eax; char *
0x1800f62ea  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f62f1  mov     edx, 192h; void *
0x1800f62f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f62fb  nop
0x1800f62fc  test    rdi, rdi
0x1800f62ff  jz      loc_1800F65BC
0x1800f6305  jmp     loc_1800F6591
0x1800f630a  cmp     rsi, 10h
0x1800f630e  jbe     short loc_1800F634C
0x1800f6310  mov     rcx, [rbp+248h]; this
0x1800f6317  mov     [rsp+340h+var_310], rsi
0x1800f631c  mov     [rsp+340h+var_318], 10h; char *
0x1800f6325  lea     rax, aPacketSpaceFor; "Packet space for physical address is to"...
0x1800f632c  mov     qword ptr [rsp+340h+var_320], rax; int
0x1800f6331  mov     ebx, 8007000Dh
0x1800f6336  mov     r9d, ebx; char *
0x1800f6339  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f6340  mov     edx, 199h; void *
0x1800f6345  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800f634a  jmp     short loc_1800F62FC
0x1800f634c  mov     dword ptr [rdi+0ECh], 63538263h
0x1800f6356  mov     word ptr [rdi], 101h
0x1800f635b  lea     rdx, [rdi+2]; unsigned __int8 *
0x1800f635f  mov     rcx, rsi; unsigned __int64
0x1800f6362  call    ?UIntPtrToUInt8@@YAJ_KPEAE@Z; UIntPtrToUInt8(unsigned __int64,uchar *)
0x1800f6367  mov     ebx, eax
0x1800f6369  test    eax, eax
0x1800f636b  jns     short loc_1800F638D
0x1800f636d  mov     rcx, [rbp+248h]; this
0x1800f6374  mov     r9d, eax; char *
0x1800f6377  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f637e  mov     edx, 19Fh; void *
0x1800f6383  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6388  jmp     loc_1800F6591
0x1800f638d  mov     word ptr [rdi+8], 0FFFFh
0x1800f6393  lea     rcx, [rdi+1Ch]; void *
0x1800f6397  mov     r8, rsi; Size
0x1800f639a  mov     rdx, [rsp+340h+var_2E0]; Src
0x1800f639f  call    memmove_0
0x1800f63a4  mov     [rsp+340h+var_2F8], r12
0x1800f63a9  mov     [rsp+340h+hMem], r12
0x1800f63ae  mov     [rsp+340h+var_2D8], r12
0x1800f63b3  mov     [rsp+340h+var_2E0], r12
0x1800f63b8  lea     rax, [rsp+340h+var_2F8]
0x1800f63bd  mov     [rsp+340h+var_2C8], rax
0x1800f63c2  mov     [rbp+240h+var_2C0], r12
0x1800f63c6  mov     [rbp+240h+var_2B8], 1
0x1800f63ca  lea     r8, [rsp+340h+var_2D8]; unsigned __int64 *
0x1800f63cf  lea     rdx, [rbp+240h+var_2C0]; unsigned __int8 **
0x1800f63d3  mov     rcx, [rbp+240h+var_2A0]; unsigned __int16 *
0x1800f63d7  call    ?BclIpAddressToByteArray@@YAJPEBGPEAPEAEPEA_K@Z; BclIpAddressToByteArray(ushort const *,uchar * *,unsigned __int64 *)
0x1800f63dc  mov     ebx, eax
0x1800f63de  lea     rcx, [rsp+340h+var_2C8]
0x1800f63e3  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800f63e8  test    ebx, ebx
0x1800f63ea  jns     short loc_1800F640C
0x1800f63ec  mov     edx, 1A8h; void *
0x1800f63f1  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f63f8  mov     r9d, ebx; char *
0x1800f63fb  mov     rcx, [rbp+248h]; this
0x1800f6402  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6407  jmp     loc_1800F6559
0x1800f640c  lea     rax, [rsp+340h+hMem]
0x1800f6411  mov     [rsp+340h+var_2C8], rax
0x1800f6416  mov     [rbp+240h+var_2C0], r12
0x1800f641a  mov     [rbp+240h+var_2B8], 1
0x1800f641e  lea     r8, [rsp+340h+var_2E0]; unsigned __int64 *
0x1800f6423  lea     rdx, [rbp+240h+var_2C0]; unsigned __int8 **
0x1800f6427  mov     rcx, r13; unsigned __int16 *
0x1800f642a  call    ?BclIpAddressToByteArray@@YAJPEBGPEAPEAEPEA_K@Z; BclIpAddressToByteArray(ushort const *,uchar * *,unsigned __int64 *)
0x1800f642f  mov     ebx, eax
0x1800f6431  lea     rcx, [rsp+340h+var_2C8]
0x1800f6436  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800f643b  test    ebx, ebx
0x1800f643d  jns     short loc_1800F6446
0x1800f643f  mov     edx, 1A9h
0x1800f6444  jmp     short loc_1800F63F1
0x1800f6446  mov     r9, [rsp+340h+var_2D8]; unsigned __int64
0x1800f644b  mov     r8, [rsp+340h+var_2F8]; unsigned __int8 *
0x1800f6450  lea     rdx, aCiaddr; "CiAddr"
0x1800f6457  call    ?LogByteArray@BclStageOutput@@QEAAXPEBGPEAE_K@Z; BclStageOutput::LogByteArray(ushort const *,uchar *,unsigned __int64)
0x1800f645c  mov     r9, [rsp+340h+var_2E0]; unsigned __int64
0x1800f6461  mov     r8, [rsp+340h+hMem]; unsigned __int8 *
0x1800f6466  lea     rdx, aSiaddr; "SiAddr"
0x1800f646d  call    ?LogByteArray@BclStageOutput@@QEAAXPEBGPEAE_K@Z; BclStageOutput::LogByteArray(ushort const *,uchar *,unsigned __int64)
0x1800f6472  cmp     [rsp+340h+var_2D8], 4
0x1800f6478  jnz     loc_1800F652C
0x1800f647e  cmp     [rsp+340h+var_2E0], 4
0x1800f6484  jnz     loc_1800F652C
0x1800f648a  mov     rax, [rsp+340h+var_2F8]
0x1800f648f  mov     ecx, [rax]
0x1800f6491  mov     [rdi+0Ch], ecx
0x1800f6494  mov     rax, [rsp+340h+var_2F8]
0x1800f6499  mov     ecx, [rax]
0x1800f649b  mov     [rdi+10h], ecx
0x1800f649e  mov     rax, [rsp+340h+hMem]
0x1800f64a3  mov     ecx, [rax]
0x1800f64a5  mov     [rdi+14h], ecx
0x1800f64a8  xor     eax, eax
0x1800f64aa  mov     [rdi+18h], eax
0x1800f64ad  mov     qword ptr [rbp+240h+PerformanceCount], r12
0x1800f64b1  lea     rcx, [rbp+240h+PerformanceCount]; lpPerformanceCount
0x1800f64b5  call    cs:__imp_QueryPerformanceCounter
0x1800f64bc  nop     dword ptr [rax+rax+00h]
0x1800f64c1  mov     eax, dword ptr [rbp+240h+PerformanceCount]
0x1800f64c4  mov     [rdi+4], eax
0x1800f64c7  mov     rcx, [rbp+240h+var_298]
0x1800f64cb  mov     [rcx], eax
  ... truncated ...
```
