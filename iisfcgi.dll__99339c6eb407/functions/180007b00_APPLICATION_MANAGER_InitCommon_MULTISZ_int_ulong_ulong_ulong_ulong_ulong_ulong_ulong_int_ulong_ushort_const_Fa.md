# APPLICATION_MANAGER::InitCommon(MULTISZ *,int,ulong,ulong,ulong,ulong,ulong,ulong,ulong,int,ulong,ushort const *,FastCgiApplicationStdErrMode)

- ea: `0x180007b00`
- end: `0x180007e16`
- name: `?InitCommon@APPLICATION_MANAGER@@QEAAJPEAVMULTISZ@@HKKKKKKKHKPEBGW4FastCgiApplicationStdErrMode@@@Z`
- size: `790`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000773c`
- `0x180008be8`

## callees

- `0x180001008`
- `0x180001048`
- `0x180003e1c`
- `0x1800042f0`
- `0x180004544`
- `0x1800045e0`
- `0x180007b00`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007bdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007df4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007bdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007d9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007df4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007d1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007d1b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007c31`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007c31`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007c70`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007c70`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x180007d4f`
- `iisutil!?Copy@MULTISZ@@QEAAHAEBV1@@Z` at `0x180007d4f`

## pseudocode

```c
__int64 __fastcall APPLICATION_MANAGER::InitCommon(
        __int64 a1,
        const struct MULTISZ *a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        const unsigned __int16 *a13,
        int a14)
{
  __int64 v14; // rsi
  int v17; // edi
  __int64 v18; // rbp
  int v19; // r14d
  void *v20; // rcx
  volatile signed __int32 *v21; // rsi
  char *v22; // rax
  char *v23; // rdi
  const unsigned __int16 *v24; // rdx
  DWORD v25; // eax
  unsigned int i; // edx
  __int64 v27; // rcx
  volatile signed __int32 *v28; // rsi
  HANDLE hObject; // [rsp+70h] [rbp+8h] BYREF

  v14 = *(_QWORD *)(a1 + 472);
  *(_DWORD *)(a1 + 484) = a5;
  *(_DWORD *)(a1 + 488) = APPLICATION_MANAGER::sm_dwSuggestedMaxApplications;
  v17 = 0;
  v18 = -1;
  *(_DWORD *)(a1 + 452) = a6;
  v19 = 0;
  *(_DWORD *)(a1 + 456) = a7;
  *(_DWORD *)(a1 + 460) = a8;
  *(_DWORD *)(a1 + 464) = a9;
  *(_DWORD *)(a1 + 468) = a10;
  *(_DWORD *)(a1 + 500) = a11;
  *(_DWORD *)(a1 + 508) = a12;
  *(_DWORD *)(a1 + 328) = a14;
  hObject = (HANDLE)-1LL;
  *(_DWORD *)(a1 + 496) = a4;
  *(_DWORD *)(a1 + 480) = 0;
  *(_DWORD *)(a1 + 448) = a3;
  if ( v14 )
  {
    _InterlockedExchange((volatile __int32 *)(v14 + 8), 1);
    v20 = *(void **)(v14 + 80);
    if ( v20 != (void *)-1LL )
    {
      CloseHandle(v20);
      *(_QWORD *)(v14 + 80) = -1;
    }
    v21 = *(volatile signed __int32 **)(a1 + 472);
    if ( _InterlockedExchangeAdd(v21 + 1, 0xFFFFFFFF) == 1 && v21 )
    {
      FILE_LISTENER::~FILE_LISTENER((FILE_LISTENER *)v21);
      operator delete((void *)v21);
    }
    *(_QWORD *)(a1 + 472) = 0;
  }
  if ( a13 )
  {
    v17 = STRU::Copy((STRU *)(a1 + 272), a13);
    if ( v17 >= 0 )
    {
      if ( !*(_DWORD *)(a1 + 320) )
        goto LABEL_14;
      v22 = (char *)operator new(0xD0u);
      v23 = v22;
      if ( v22 )
      {
        *(_QWORD *)(v22 + 4) = 1;
        STRU::STRU((STRU *)(v22 + 16));
        *((_QWORD *)v23 + 10) = -1;
        *((_QWORD *)v23 + 17) = 0;
        *((_QWORD *)v23 + 21) = v23 + 136;
        *((_DWORD *)v23 + 44) = 32;
        *((_WORD *)v23 + 90) = 256;
        *((_QWORD *)v23 + 11) = 0;
        *((_DWORD *)v23 + 32) = 0;
        *((_DWORD *)v23 + 46) = 0;
        *((_QWORD *)v23 + 9) = 0;
        *((_OWORD *)v23 + 6) = 0;
        *((_OWORD *)v23 + 7) = 0;
        *((_QWORD *)v23 + 24) = 0;
        *((_QWORD *)v23 + 25) = 0;
        _InterlockedIncrement(&FILE_LISTENER::sm_cListeners);
        *(_DWORD *)v23 = 1179865932;
        v24 = *(const unsigned __int16 **)(a1 + 304);
        *(_QWORD *)(a1 + 472) = v23;
        if ( (int)FILE_LISTENER::Initialize((FILE_LISTENER *)v23, v24, (struct IFILE_LISTENER_CALLBACK *)a1) >= 0 )
        {
          v17 = FILE_LISTENER::OpenFile(*(FILE_LISTENER **)(a1 + 472), &hObject);
          if ( v17 >= 0 )
          {
            FILE_LISTENER::ListenForChanges(*(FILE_LISTENER **)(a1 + 472));
            CloseHandle(hObject);
            v19 = 1;
          }
          else
          {
            v18 = (__int64)hObject;
            v17 = 0;
            *(_DWORD *)(a1 + 480) = 1;
          }
        }
        else
        {
          *(_DWORD *)(a1 + 480) = 1;
          v17 = 0;
        }
        goto LABEL_14;
      }
      *(_QWORD *)(a1 + 472) = 0;
      v17 = -2147024888;
    }
LABEL_21:
    v28 = *(volatile signed __int32 **)(a1 + 472);
    if ( v28 )
    {
      if ( _InterlockedExchangeAdd(v28 + 1, 0xFFFFFFFF) == 1 )
      {
        FILE_LISTENER::~FILE_LISTENER((FILE_LISTENER *)v28);
        operator delete((void *)v28);
      }
      *(_QWORD *)(a1 + 472) = 0;
    }
    if ( v18 != -1 )
      CloseHandle((HANDLE)v18);
    return (unsigned int)v17;
  }
LABEL_14:
  *(_DWORD *)(a1 + 4520) = 0;
  if ( *(_DWORD *)(a1 + 508) > 0x3E8u )
    *(_DWORD *)(a1 + 508) = 1000;
  v25 = GetTickCount() - 60001;
  for ( i = 0; i < *(_DWORD *)(a1 + 508); *(_DWORD *)(a1 + 4 * v27 + 520) = v25 )
    v27 = i++;
  if ( !MULTISZ::Copy((MULTISZ *)(a1 + 336), a2) )
    v17 = -2147024882;
  if ( !v19 )
    goto LABEL_21;
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180007b00  push    rbx
0x180007b02  push    rbp
0x180007b03  push    rsi
0x180007b04  push    rdi
0x180007b05  push    r12
0x180007b07  push    r13
0x180007b09  push    r14
0x180007b0b  push    r15
0x180007b0d  sub     rsp, 28h
0x180007b11  mov     eax, [rsp+68h+arg_20]
0x180007b18  xor     r12d, r12d
0x180007b1b  mov     rsi, [rcx+1D8h]
0x180007b22  or      r13, 0FFFFFFFFFFFFFFFFh
0x180007b26  mov     [rcx+1E4h], eax
0x180007b2c  mov     r15, rdx
0x180007b2f  mov     eax, cs:?sm_dwSuggestedMaxApplications@APPLICATION_MANAGER@@0KA; ulong APPLICATION_MANAGER::sm_dwSuggestedMaxApplications
0x180007b35  mov     rbx, rcx
0x180007b38  mov     [rcx+1E8h], eax
0x180007b3e  mov     edi, r12d
0x180007b41  mov     eax, [rsp+68h+arg_28]
0x180007b48  mov     rbp, r13
0x180007b4b  mov     [rcx+1C4h], eax
0x180007b51  mov     r14d, r12d
0x180007b54  mov     eax, [rsp+68h+arg_30]
0x180007b5b  mov     [rcx+1C8h], eax
0x180007b61  mov     eax, [rsp+68h+arg_38]
0x180007b68  mov     [rcx+1CCh], eax
0x180007b6e  mov     eax, [rsp+68h+arg_40]
0x180007b75  mov     [rcx+1D0h], eax
0x180007b7b  mov     eax, [rsp+68h+arg_48]
0x180007b82  mov     [rcx+1D4h], eax
0x180007b88  mov     eax, [rsp+68h+arg_50]
0x180007b8f  mov     [rcx+1F4h], eax
0x180007b95  mov     eax, [rsp+68h+arg_58]
0x180007b9c  mov     [rcx+1FCh], eax
0x180007ba2  mov     eax, [rsp+68h+arg_68]
0x180007ba9  mov     [rcx+148h], eax
0x180007baf  mov     [rsp+68h+hObject], r13
0x180007bb4  mov     [rcx+1F0h], r9d
0x180007bbb  mov     [rcx+1E0h], r12d
0x180007bc2  mov     [rcx+1C0h], r8d
0x180007bc9  test    rsi, rsi
0x180007bcc  jz      short loc_180007C19
0x180007bce  lea     eax, [r12+1]
0x180007bd3  xchg    eax, [rsi+8]
0x180007bd6  mov     rcx, [rsi+50h]; hObject
0x180007bda  cmp     rcx, r13
0x180007bdd  jz      short loc_180007BE9
0x180007bdf  call    cs:__imp_CloseHandle
0x180007be5  mov     [rsi+50h], r13
0x180007be9  mov     rsi, [rbx+1D8h]
0x180007bf0  mov     eax, r13d
0x180007bf3  lock xadd [rsi+4], eax
0x180007bf8  add     eax, r13d
0x180007bfb  jnz     short loc_180007C12
0x180007bfd  test    rsi, rsi
0x180007c00  jz      short loc_180007C12
0x180007c02  mov     rcx, rsi; this
0x180007c05  call    ??1FILE_LISTENER@@QEAA@XZ; FILE_LISTENER::~FILE_LISTENER(void)
0x180007c0a  mov     rcx, rsi; Block
0x180007c0d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007c12  mov     [rbx+1D8h], r12
0x180007c19  mov     rdx, [rsp+68h+arg_60]
0x180007c21  test    rdx, rdx
0x180007c24  jz      loc_180007D01
0x180007c2a  lea     rcx, [rbx+110h]
0x180007c31  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180007c37  mov     edi, eax
0x180007c39  test    eax, eax
0x180007c3b  js      loc_180007D64
0x180007c41  cmp     [rbx+140h], r12d
0x180007c48  jz      loc_180007D01
0x180007c4e  mov     ecx, 0D0h; Size
0x180007c53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007c58  mov     rdi, rax
0x180007c5b  test    rax, rax
0x180007c5e  jz      loc_180007E05
0x180007c64  lea     rcx, [rax+10h]
0x180007c68  mov     qword ptr [rax+4], 1
0x180007c70  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180007c76  lea     rcx, [rdi+88h]
0x180007c7d  mov     [rdi+50h], r13
0x180007c81  mov     [rcx], r12
0x180007c84  xorps   xmm0, xmm0
0x180007c87  mov     [rcx+20h], rcx
0x180007c8b  xor     eax, eax
0x180007c8d  mov     dword ptr [rcx+28h], 20h ; ' '
0x180007c94  mov     word ptr [rcx+2Ch], 100h
0x180007c9a  mov     [rdi+58h], r12
0x180007c9e  mov     [rdi+80h], r12d
0x180007ca5  mov     [rdi+0B8h], r12d
0x180007cac  mov     [rdi+48h], rax
0x180007cb0  movups  xmmword ptr [rdi+60h], xmm0
0x180007cb4  movups  xmmword ptr [rdi+70h], xmm0
0x180007cb8  mov     [rdi+0C0h], r12
0x180007cbf  mov     [rdi+0C8h], r12
0x180007cc6  lock inc cs:?sm_cListeners@FILE_LISTENER@@0JA; long FILE_LISTENER::sm_cListeners
0x180007ccd  mov     dword ptr [rdi], 4653534Ch
0x180007cd3  mov     r8, rbx; struct IFILE_LISTENER_CALLBACK *
0x180007cd6  mov     rdx, [rbx+130h]; unsigned __int16 *
0x180007cdd  mov     rcx, rdi; this
0x180007ce0  mov     [rbx+1D8h], rdi
0x180007ce7  call    ?Initialize@FILE_LISTENER@@QEAAJPEBGPEAVIFILE_LISTENER_CALLBACK@@H@Z; FILE_LISTENER::Initialize(ushort const *,IFILE_LISTENER_CALLBACK *,int)
0x180007cec  test    eax, eax
0x180007cee  jns     loc_180007DB5
0x180007cf4  mov     dword ptr [rbx+1E0h], 1
0x180007cfe  mov     edi, r12d
0x180007d01  mov     eax, 3E8h
0x180007d06  mov     [rbx+11A8h], r12d
0x180007d0d  cmp     [rbx+1FCh], eax
0x180007d13  jbe     short loc_180007D1B
0x180007d15  mov     [rbx+1FCh], eax
0x180007d1b  call    cs:__imp_GetTickCount
0x180007d21  sub     eax, 0EA61h
0x180007d26  mov     edx, r12d
0x180007d29  cmp     [rbx+1FCh], r12d
0x180007d30  jbe     short loc_180007D45
0x180007d32  mov     ecx, edx
0x180007d34  inc     edx
0x180007d36  mov     [rbx+rcx*4+208h], eax
0x180007d3d  cmp     edx, [rbx+1FCh]
0x180007d43  jb      short loc_180007D32
0x180007d45  lea     rcx, [rbx+150h]
0x180007d4c  mov     rdx, r15
0x180007d4f  call    cs:__imp_?Copy@MULTISZ@@QEAAHAEBV1@@Z; MULTISZ::Copy(MULTISZ const &)
0x180007d55  test    eax, eax
0x180007d57  mov     ecx, 8007000Eh
0x180007d5c  cmovz   edi, ecx
0x180007d5f  test    r14d, r14d
0x180007d62  jnz     short loc_180007DA2
0x180007d64  mov     rsi, [rbx+1D8h]
0x180007d6b  test    rsi, rsi
0x180007d6e  jz      short loc_180007D94
0x180007d70  mov     eax, r13d
0x180007d73  lock xadd [rsi+4], eax
0x180007d78  add     eax, r13d
0x180007d7b  jnz     short loc_180007D8D
0x180007d7d  mov     rcx, rsi; this
0x180007d80  call    ??1FILE_LISTENER@@QEAA@XZ; FILE_LISTENER::~FILE_LISTENER(void)
0x180007d85  mov     rcx, rsi; Block
0x180007d88  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007d8d  mov     [rbx+1D8h], r12
0x180007d94  cmp     rbp, r13
0x180007d97  jz      short loc_180007DA2
0x180007d99  mov     rcx, rbp; hObject
0x180007d9c  call    cs:__imp_CloseHandle
0x180007da2  mov     eax, edi
0x180007da4  add     rsp, 28h
0x180007da8  pop     r15
0x180007daa  pop     r14
0x180007dac  pop     r13
0x180007dae  pop     r12
0x180007db0  pop     rdi
0x180007db1  pop     rsi
0x180007db2  pop     rbp
0x180007db3  pop     rbx
0x180007db4  retn
0x180007db5  mov     rcx, [rbx+1D8h]; this
0x180007dbc  lea     rdx, [rsp+68h+hObject]; void **
0x180007dc1  call    ?OpenFile@FILE_LISTENER@@QEAAJPEAPEAX@Z; FILE_LISTENER::OpenFile(void * *)
0x180007dc6  mov     edi, eax
0x180007dc8  test    eax, eax
0x180007dca  jns     short loc_180007DE3
0x180007dcc  mov     rbp, [rsp+68h+hObject]
0x180007dd1  mov     edi, r12d
0x180007dd4  mov     dword ptr [rbx+1E0h], 1
0x180007dde  jmp     loc_180007D01
0x180007de3  mov     rcx, [rbx+1D8h]; this
0x180007dea  call    ?ListenForChanges@FILE_LISTENER@@QEAAXXZ; FILE_LISTENER::ListenForChanges(void)
0x180007def  mov     rcx, [rsp+68h+hObject]; hObject
0x180007df4  call    cs:__imp_CloseHandle
0x180007dfa  mov     r14d, 1
0x180007e00  jmp     loc_180007D01
0x180007e05  mov     [rbx+1D8h], r12
0x180007e0c  mov     edi, 80070008h
0x180007e11  jmp     loc_180007D64
```
