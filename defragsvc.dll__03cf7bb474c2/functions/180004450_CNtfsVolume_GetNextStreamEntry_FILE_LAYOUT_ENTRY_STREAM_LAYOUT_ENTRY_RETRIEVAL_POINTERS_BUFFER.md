# CNtfsVolume::_GetNextStreamEntry(_FILE_LAYOUT_ENTRY * *,_STREAM_LAYOUT_ENTRY * *,RETRIEVAL_POINTERS_BUFFER * *)

- ea: `0x180004450`
- end: `0x1800048c6`
- name: `?_GetNextStreamEntry@CNtfsVolume@@EEAAJPEAPEAU_FILE_LAYOUT_ENTRY@@PEAPEAU_STREAM_LAYOUT_ENTRY@@PEAPEAURETRIEVAL_POINTERS_BUFFER@@@Z`
- size: `1142`
- prototype: `__int64 __fastcall(CNtfsVolume *__hidden this, struct _FILE_LAYOUT_ENTRY **, struct _STREAM_LAYOUT_ENTRY **, struct RETRIEVAL_POINTERS_BUFFER **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004450`
- `0x180006400`
- `0x18003ae04`
- `0x180046494`
- `0x18004a92c`
- `0x180067b0a`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800046f8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800046f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004747`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x1800044bc`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x1800044bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000485f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000485f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004574`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000476d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004574`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000476d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNtfsVolume::_GetNextStreamEntry(
        CNtfsVolume *this,
        struct _FILE_LAYOUT_ENTRY **a2,
        struct _STREAM_LAYOUT_ENTRY **a3,
        struct RETRIEVAL_POINTERS_BUFFER **a4)
{
  int ThreadContextRetail; // eax
  CSxGlobalTracer *v9; // rcx
  __int16 v10; // ax
  int NextFileId; // ebx
  void *v12; // rcx
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // rax
  struct RETRIEVAL_POINTERS_BUFFER *v16; // r10
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v22; // rdx
  void *v23; // rax
  DWORD nOutBufferSize; // ebx
  bool v25; // zf
  __int64 v26; // rdx
  DWORD BytesReturned; // [rsp+40h] [rbp-59h] BYREF
  int v28; // [rsp+48h] [rbp-51h] BYREF
  __int64 v29; // [rsp+4Ch] [rbp-4Dh]
  __int16 v30; // [rsp+54h] [rbp-45h]
  const char *v31; // [rsp+58h] [rbp-41h]
  __int128 v32; // [rsp+60h] [rbp-39h] BYREF
  __int64 v33; // [rsp+70h] [rbp-29h]
  int v34; // [rsp+78h] [rbp-21h]
  unsigned __int64 v35; // [rsp+80h] [rbp-19h] BYREF
  __int128 InBuffer; // [rsp+88h] [rbp-11h] BYREF
  __int128 v37; // [rsp+98h] [rbp-1h]

  v28 = 0;
  v29 = 1265;
  v30 = 1;
  v31 = "CNtfsVolume::_GetNextStreamEntry";
  v32 = 0;
  v33 = 0;
  v34 = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)&v32 + 8);
  if ( ThreadContextRetail >= 0 )
  {
    *(_QWORD *)&v32 = *(_QWORD *)(*((_QWORD *)&v32 + 1) + 32LL);
    *(_QWORD *)(*((_QWORD *)&v32 + 1) + 32LL) = &v28;
LABEL_3:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_4;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
      (unsigned int)ThreadContextRetail);
    goto LABEL_3;
  }
LABEL_4:
  if ( v30 )
  {
    if ( v30 == 1 )
    {
      if ( v9 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v9 + 7) & 0x20000000) == 0 )
        goto LABEL_8;
      v22 = 12;
LABEL_34:
      WPP_SF_s(*((_QWORD *)v9 + 2), v22, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, v31);
      goto LABEL_8;
    }
    if ( v9 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x20000) != 0 )
    {
      v22 = 13;
      goto LABEL_34;
    }
  }
  else if ( v9 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x8000000) != 0 )
  {
    v22 = 11;
    goto LABEL_34;
  }
LABEL_8:
  InBuffer = 0;
  v37 = 0;
  BytesReturned = 0;
  v35 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v10 = 1281;
  if ( !a2 || (LOWORD(v29) = 1281, v10 = 1282, !a3) )
  {
    NextFileId = -2147024809;
    v28 = -2147024809;
    goto LABEL_17;
  }
  v28 = 0;
  LOWORD(v29) = 1282;
  if ( !*((_DWORD *)this + 98) )
  {
    if ( !*((_DWORD *)this + 96) )
    {
      *(_QWORD *)((char *)&InBuffer + 4) = 12;
      HIDWORD(InBuffer) = 0;
      if ( *((_BYTE *)this + 440) )
      {
        DWORD1(InBuffer) = 13;
        *((_BYTE *)this + 440) = 0;
      }
      while ( 1 )
      {
LABEL_38:
        v23 = (void *)*((_QWORD *)this + 51);
        if ( !v23 )
        {
          v23 = CoTaskMemAlloc(*((unsigned int *)this + 104));
          *((_QWORD *)this + 51) = v23;
          if ( !v23 )
          {
            NextFileId = -2147024882;
            v28 = -2147024882;
            WORD1(v29) = 1330;
            goto LABEL_18;
          }
          v28 = 0;
          LOWORD(v29) = 1330;
        }
        nOutBufferSize = *((_DWORD *)this + 104);
        memset_0(v23, 0, nOutBufferSize);
        if ( DeviceIoControl(
               *((HANDLE *)this + 5),
               0x90277u,
               &InBuffer,
               0x20u,
               *((LPVOID *)this + 51),
               nOutBufferSize,
               &BytesReturned,
               0) )
        {
          break;
        }
        if ( GetLastError() != 122 )
        {
          NextFileId = 1;
          v28 = 1;
          LOWORD(v29) = 1353;
          goto LABEL_18;
        }
        *((_DWORD *)this + 104) *= 2;
        CoTaskMemFree(*((LPVOID *)this + 51));
        *((_QWORD *)this + 51) = 0;
      }
      v25 = BytesReturned == 16;
      *((_DWORD *)this + 98) = BytesReturned - 16;
      if ( !v25 )
      {
        v26 = *((_QWORD *)this + 51) + *(unsigned int *)(*((_QWORD *)this + 51) + 4LL);
        *((_QWORD *)this + 53) = v26;
        *((_QWORD *)this + 54) = v26 + *(unsigned int *)(v26 + 28);
        goto LABEL_21;
      }
      NextFileId = 1;
      v28 = 1;
      LOWORD(v29) = 1370;
      goto LABEL_18;
    }
    NextFileId = CNtfsVolume::_GetNextFileId(this, &v35);
    v28 = NextFileId;
    v10 = 1289;
    if ( NextFileId >= 0 )
    {
      LOWORD(v29) = 1289;
      if ( NextFileId != 1 )
      {
        DWORD1(InBuffer) |= 0xDu;
        DWORD2(InBuffer) = 2;
        LODWORD(InBuffer) = 1;
        *(_QWORD *)&v37 = v35;
        *((_QWORD *)&v37 + 1) = v35;
        goto LABEL_38;
      }
      NextFileId = 1;
      v28 = 1;
      LOWORD(v29) = 1293;
      goto LABEL_18;
    }
LABEL_17:
    WORD1(v29) = v10;
LABEL_18:
    v12 = (void *)*((_QWORD *)this + 51);
    if ( v12 )
    {
      CoTaskMemFree(v12);
      *((_QWORD *)this + 51) = 0;
      *((_DWORD *)this + 98) = 0;
      NextFileId = v28;
    }
    goto LABEL_29;
  }
LABEL_21:
  v13 = *((_QWORD *)this + 53);
  v14 = *((_QWORD *)this + 54);
  v15 = *(unsigned int *)(v14 + 12);
  if ( (_DWORD)v15 )
    v16 = (struct RETRIEVAL_POINTERS_BUFFER *)(v15 + v14 + 8);
  else
    v16 = 0;
  v17 = *(unsigned int *)(v14 + 4);
  if ( (_DWORD)v17 )
  {
    *((_QWORD *)this + 54) = v14 + v17;
  }
  else
  {
    v18 = *(unsigned int *)(v13 + 4);
    if ( (_DWORD)v18 )
    {
      v19 = (unsigned int)v18;
      v20 = v13 + v18;
      *((_QWORD *)this + 53) = v20;
      *((_QWORD *)this + 54) = v13 + v19 + *(unsigned int *)(v20 + 28);
    }
    else
    {
      *((_DWORD *)this + 98) = 0;
    }
  }
  *a2 = (struct _FILE_LAYOUT_ENTRY *)v13;
  *a3 = (struct _STREAM_LAYOUT_ENTRY *)v14;
  if ( a4 )
    *a4 = v16;
  NextFileId = 0;
  v28 = 0;
LABEL_29:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v28);
  return (unsigned int)NextFileId;
}

```

## disassembly

```asm
0x180004450  push    rbp
0x180004452  push    rbx
0x180004453  push    rsi
0x180004454  push    rdi
0x180004455  push    r12
0x180004457  push    r13
0x180004459  push    r14
0x18000445b  push    r15
0x18000445d  lea     rbp, [rsp-1Fh]
0x180004462  sub     rsp, 0B8h
0x180004469  mov     rax, cs:__security_cookie
0x180004470  xor     rax, rsp
0x180004473  mov     [rbp+57h+var_48], rax
0x180004477  mov     r14, r9
0x18000447a  mov     rsi, r8
0x18000447d  mov     rdi, rdx
0x180004480  mov     r15, rcx
0x180004483  xor     r12d, r12d
0x180004486  mov     [rbp+57h+var_A8], r12d
0x18000448a  mov     [rbp+57h+var_A4], 4F1h
0x180004492  mov     r13d, 1
0x180004498  mov     [rbp+57h+var_9C], r13w
0x18000449d  lea     rax, aCntfsvolumeGet_4; "CNtfsVolume::_GetNextStreamEntry"
0x1800044a4  mov     [rbp+57h+var_98], rax
0x1800044a8  xorps   xmm0, xmm0
0x1800044ab  movdqu  [rbp+57h+var_90], xmm0
0x1800044b0  mov     [rbp+57h+var_80], r12
0x1800044b4  mov     [rbp+57h+var_78], r12d
0x1800044b8  lea     rcx, [rbp+57h+var_90+8]
0x1800044bc  call    cs:__imp_SxTracerGetThreadContextRetail
0x1800044c2  lea     rbx, WPP_GLOBAL_Control
0x1800044c9  test    eax, eax
0x1800044cb  js      loc_1800047AC
0x1800044d1  mov     rcx, qword ptr [rbp+57h+var_90+8]
0x1800044d5  mov     rax, [rcx+20h]
0x1800044d9  mov     qword ptr [rbp+57h+var_90], rax
0x1800044dd  lea     rax, [rbp+57h+var_A8]
0x1800044e1  mov     [rcx+20h], rax
0x1800044e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800044ec  movzx   eax, [rbp+57h+var_9C]
0x1800044f0  test    ax, ax
0x1800044f3  jz      loc_1800047E3
0x1800044f9  cmp     ax, r13w
0x1800044fd  jnz     loc_180004641
0x180004503  cmp     rcx, rbx
0x180004506  jz      short loc_180004515
0x180004508  test    dword ptr [rcx+1Ch], 20000000h
0x18000450f  jnz     loc_180004803
0x180004515  xorps   xmm0, xmm0
0x180004518  movups  [rbp+57h+InBuffer], xmm0
0x18000451c  movups  [rbp+57h+var_58], xmm0
0x180004520  mov     [rbp+57h+BytesReturned], r12d
0x180004524  mov     [rbp+57h+var_70], r12
0x180004528  test    rdi, rdi
0x18000452b  jz      short loc_180004530
0x18000452d  mov     [rdi], r12
0x180004530  test    rsi, rsi
0x180004533  jz      short loc_180004538
0x180004535  mov     [rsi], r12
0x180004538  test    r14, r14
0x18000453b  jz      short loc_180004540
0x18000453d  mov     [r14], r12
0x180004540  mov     eax, 501h
0x180004545  test    rdi, rdi
0x180004548  jz      short loc_180004558
0x18000454a  mov     word ptr [rbp+57h+var_A4], ax
0x18000454e  mov     eax, 502h
0x180004553  test    rsi, rsi
0x180004556  jnz     short loc_18000458D
0x180004558  mov     ebx, 80070057h
0x18000455d  mov     [rbp+57h+var_A8], ebx
0x180004560  mov     word ptr [rbp+57h+var_A4+2], ax
0x180004564  mov     rcx, [r15+198h]; pv
0x18000456b  test    rcx, rcx
0x18000456e  jz      loc_180004605
0x180004574  call    cs:__imp_CoTaskMemFree
0x18000457a  mov     [r15+198h], r12
0x180004581  mov     [r15+188h], r12d
0x180004588  mov     ebx, [rbp+57h+var_A8]
0x18000458b  jmp     short loc_180004605
0x18000458d  mov     [rbp+57h+var_A8], r12d
0x180004591  mov     word ptr [rbp+57h+var_A4], ax
0x180004595  cmp     dword ptr [r15+188h], 0
0x18000459d  jbe     loc_180004675
0x1800045a3  mov     r9, [r15+1A8h]
0x1800045aa  mov     r8, [r15+1B0h]
0x1800045b1  mov     eax, [r8+0Ch]
0x1800045b5  test    eax, eax
0x1800045b7  jz      loc_1800048BD
0x1800045bd  lea     r10, [r8+8]
0x1800045c1  add     r10, rax
0x1800045c4  mov     eax, [r8+4]
0x1800045c8  test    eax, eax
0x1800045ca  jnz     short loc_180004635
0x1800045cc  mov     eax, [r9+4]
0x1800045d0  test    eax, eax
0x1800045d2  jz      loc_18000473B
0x1800045d8  mov     ecx, eax
0x1800045da  add     rax, r9
0x1800045dd  mov     [r15+1A8h], rax
0x1800045e4  mov     edx, [rax+1Ch]
0x1800045e7  add     rdx, rcx
0x1800045ea  add     rdx, r9
0x1800045ed  mov     [r15+1B0h], rdx
0x1800045f4  mov     [rdi], r9
0x1800045f7  mov     [rsi], r8
0x1800045fa  test    r14, r14
0x1800045fd  jnz     short loc_180004630
0x1800045ff  mov     ebx, r12d
0x180004602  mov     [rbp+57h+var_A8], ebx
0x180004605  lea     rcx, [rbp+57h+var_A8]; this
0x180004609  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000460e  mov     eax, ebx
0x180004610  mov     rcx, [rbp+57h+var_48]
0x180004614  xor     rcx, rsp; StackCookie
0x180004617  call    __security_check_cookie
0x18000461c  add     rsp, 0B8h
0x180004623  pop     r15
0x180004625  pop     r14
0x180004627  pop     r13
0x180004629  pop     r12
0x18000462b  pop     rdi
0x18000462c  pop     rsi
0x18000462d  pop     rbx
0x18000462e  pop     rbp
0x18000462f  retn
0x180004630  mov     [r14], r10
0x180004633  jmp     short loc_1800045FF
0x180004635  add     rax, r8
0x180004638  mov     [r15+1B0h], rax
0x18000463f  jmp     short loc_1800045F4
0x180004641  cmp     rcx, rbx
0x180004644  jz      loc_180004515
0x18000464a  test    dword ptr [rcx+1Ch], 20000h
0x180004651  jz      loc_180004515
0x180004657  mov     edx, 0Dh
0x18000465c  mov     r9, [rbp+57h+var_98]
0x180004660  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x180004667  mov     rcx, [rcx+10h]
0x18000466b  call    WPP_SF_s
0x180004670  jmp     loc_180004515
0x180004675  cmp     dword ptr [r15+180h], 0
0x18000467d  jnz     loc_18000480D
0x180004683  mov     qword ptr [rbp+57h+InBuffer+4], 0Ch
0x18000468b  mov     dword ptr [rbp+57h+InBuffer+0Ch], r12d
0x18000468f  cmp     byte ptr [r15+1B8h], 0
0x180004697  jnz     loc_180004844
0x18000469d  mov     r13d, 532h
0x1800046a3  mov     rax, [r15+198h]
0x1800046aa  test    rax, rax
0x1800046ad  jz      loc_180004858
0x1800046b3  mov     ebx, [r15+1A0h]
0x1800046ba  mov     r8d, ebx; Size
0x1800046bd  xor     edx, edx; Val
0x1800046bf  mov     rcx, rax; void *
0x1800046c2  call    memset_0
0x1800046c7  mov     [rsp+0F0h+lpOverlapped], r12; lpOverlapped
0x1800046cc  lea     rax, [rbp+57h+BytesReturned]
0x1800046d0  mov     [rsp+0F0h+lpBytesReturned], rax; lpBytesReturned
0x1800046d5  mov     [rsp+0F0h+nOutBufferSize], ebx; nOutBufferSize
0x1800046d9  mov     rax, [r15+198h]
0x1800046e0  mov     [rsp+0F0h+lpOutBuffer], rax; lpOutBuffer
0x1800046e5  mov     r9d, 20h ; ' '; nInBufferSize
0x1800046eb  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x1800046ef  mov     edx, 90277h; dwIoControlCode
0x1800046f4  mov     rcx, [r15+28h]; hDevice
0x1800046f8  call    cs:__imp_DeviceIoControl
0x1800046fe  test    eax, eax
0x180004700  jz      short loc_180004747
0x180004702  mov     eax, [rbp+57h+BytesReturned]
0x180004705  add     eax, 0FFFFFFF0h
0x180004708  mov     [r15+188h], eax
0x18000470f  jz      loc_1800048A7
0x180004715  mov     rcx, [r15+198h]
0x18000471c  mov     edx, [rcx+4]
0x18000471f  add     rdx, rcx
0x180004722  mov     [r15+1A8h], rdx
0x180004729  mov     eax, [rdx+1Ch]
0x18000472c  add     rax, rdx
0x18000472f  mov     [r15+1B0h], rax
0x180004736  jmp     loc_1800045A3
0x18000473b  mov     [r15+188h], r12d
0x180004742  jmp     loc_1800045F4
0x180004747  call    cs:__imp_GetLastError
0x18000474d  cmp     eax, 7Ah ; 'z'
0x180004750  jnz     loc_180004891
0x180004756  mov     eax, [r15+1A0h]
0x18000475d  add     eax, eax
0x18000475f  mov     [r15+1A0h], eax
0x180004766  mov     rcx, [r15+198h]; pv
0x18000476d  call    cs:__imp_CoTaskMemFree
0x180004773  mov     [r15+198h], r12
0x18000477a  jmp     loc_1800046A3
0x18000477f  mov     word ptr [rbp+57h+var_A4], ax
0x180004783  cmp     ebx, 1
0x180004786  jz      loc_180004830
0x18000478c  or      dword ptr [rbp+57h+InBuffer+4], 0Dh
0x180004790  mov     dword ptr [rbp+57h+InBuffer+8], 2
0x180004797  mov     dword ptr [rbp+57h+InBuffer], r13d
0x18000479b  mov     rax, [rbp+57h+var_70]
0x18000479f  mov     qword ptr [rbp+57h+var_58], rax
0x1800047a3  mov     qword ptr [rbp+57h+var_58+8], rax
0x1800047a7  jmp     loc_18000469D
0x1800047ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047b3  cmp     rcx, rbx
0x1800047b6  jz      loc_1800044EC
0x1800047bc  test    [rcx+1Ch], r13b
0x1800047c0  jz      loc_1800044EC
0x1800047c6  mov     edx, 0Ah
0x1800047cb  mov     r9d, eax
0x1800047ce  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x1800047d5  mov     rcx, [rcx+10h]
0x1800047d9  call    WPP_SF_d
0x1800047de  jmp     loc_1800044E5
0x1800047e3  cmp     rcx, rbx
0x1800047e6  jz      loc_180004515
0x1800047ec  test    dword ptr [rcx+1Ch], 8000000h
0x1800047f3  jz      loc_180004515
0x1800047f9  mov     edx, 0Bh
0x1800047fe  jmp     loc_18000465C
0x180004803  mov     edx, 0Ch
0x180004808  jmp     loc_18000465C
0x18000480d  lea     rdx, [rbp+57h+var_70]; unsigned __int64 *
0x180004811  mov     rcx, r15; this
0x180004814  call    ?_GetNextFileId@CNtfsVolume@@AEAAJPEA_K@Z; CNtfsVolume::_GetNextFileId(unsigned __int64 *)
0x180004819  mov     ebx, eax
0x18000481b  mov     [rbp+57h+var_A8], eax
0x18000481e  test    eax, eax
0x180004820  mov     eax, 509h
0x180004825  js      loc_180004560
0x18000482b  jmp     loc_18000477F
0x180004830  mov     ebx, r13d
0x180004833  mov     [rbp+57h+var_A8], ebx
0x180004836  mov     eax, 50Dh
0x18000483b  mov     word ptr [rbp+57h+var_A4], ax
0x18000483f  jmp     loc_180004564
0x180004844  mov     dword ptr [rbp+57h+InBuffer+4], 0Dh
0x18000484b  mov     byte ptr [r15+1B8h], 0
0x180004853  jmp     loc_18000469D
0x180004858  mov     ecx, [r15+1A0h]; cb
0x18000485f  call    cs:__imp_CoTaskMemAlloc
0x180004865  mov     [r15+198h], rax
0x18000486c  test    rax, rax
0x18000486f  jz      short loc_18000487F
0x180004871  mov     [rbp+57h+var_A8], r12d
0x180004875  mov     word ptr [rbp+57h+var_A4], r13w
0x18000487a  jmp     loc_1800046B3
0x18000487f  mov     ebx, 8007000Eh
0x180004884  mov     [rbp+57h+var_A8], ebx
0x180004887  mov     word ptr [rbp+57h+var_A4+2], r13w
0x18000488c  jmp     loc_180004564
0x180004891  mov     ebx, 1
0x180004896  mov     [rbp+57h+var_A8], ebx
0x180004899  mov     eax, 549h
0x18000489e  mov     word ptr [rbp+57h+var_A4], ax
0x1800048a2  jmp     loc_180004564
0x1800048a7  mov     ebx, 1
0x1800048ac  mov     [rbp+57h+var_A8], ebx
0x1800048af  mov     eax, 55Ah
0x1800048b4  mov     word ptr [rbp+57h+var_A4], ax
0x1800048b8  jmp     loc_180004564
0x1800048bd  mov     r10, r12
0x1800048c0  jmp     loc_1800045C4
```
