# RetrieveOldValue(CADMCOMW *,IMDCOM *,ulong,ulong,ushort const *,_METADATA_RECORD * *)

- ea: `0x18000f468`
- end: `0x18000f727`
- name: `?RetrieveOldValue@@YAJPEAVCADMCOMW@@PEAUIMDCOM@@KKPEBGPEAPEAU_METADATA_RECORD@@@Z`
- size: `703`
- prototype: `__int64 __usercall@<rax>(struct CADMCOMW *@<rcx>, struct IMDCOM *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, const unsigned __int16 *, struct _METADATA_RECORD **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003fd0`
- `0x180009200`

## callees

- `0x18000f30c`
- `0x18000f468`
- `0x18000fb06`
- `0x18000fb1e`
- `0x18000fb50`
- `0x180010010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000f626`
- `KERNEL32!HeapAlloc` at `0x18000f662`
- `KERNEL32!HeapAlloc` at `0x18000f626`
- `KERNEL32!HeapAlloc` at `0x18000f662`
- `KERNEL32!GetProcessHeap` at `0x18000f617`
- `KERNEL32!GetProcessHeap` at `0x18000f654`
- `KERNEL32!GetProcessHeap` at `0x18000f6b2`
- `KERNEL32!GetProcessHeap` at `0x18000f6d4`
- `KERNEL32!GetProcessHeap` at `0x18000f617`
- `KERNEL32!GetProcessHeap` at `0x18000f654`
- `KERNEL32!GetProcessHeap` at `0x18000f6b2`
- `KERNEL32!GetProcessHeap` at `0x18000f6d4`
- `KERNEL32!HeapFree` at `0x18000f6c0`
- `KERNEL32!HeapFree` at `0x18000f6e2`
- `KERNEL32!HeapFree` at `0x18000f6c0`
- `KERNEL32!HeapFree` at `0x18000f6e2`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18000f6fe`
- `IisRTL!??1STRU@@QEAA@XZ` at `0x18000f6fe`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000f5c2`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000f5c2`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x18000f6f4`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x18000f6f4`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000f4b9`
- `IisRTL!??0STRU@@QEAA@XZ` at `0x18000f4b9`

## pseudocode

```c
__int64 __fastcall RetrieveOldValue(
        struct CADMCOMW *a1,
        struct IMDCOM *a2,
        unsigned int a3,
        int a4,
        unsigned __int16 *a5,
        struct _METADATA_RECORD **a6)
{
  int FullPath; // edi
  __int64 v11; // rax
  __int64 (__fastcall *v12)(struct IMDCOM *, _QWORD, __int64, __int128 *, unsigned int *); // rax
  int v13; // eax
  HANDLE ProcessHeap; // rax
  struct _METADATA_RECORD *v15; // rax
  unsigned int v16; // ebx
  HANDLE v17; // rax
  unsigned __int8 *pbMDData; // rcx
  unsigned __int8 *v19; // rbx
  HANDLE v20; // rax
  void *v21; // rbx
  HANDLE v22; // rax
  unsigned int v24; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v25; // [rsp+38h] [rbp-C8h] BYREF
  SIZE_T dwBytes[2]; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  _BYTE v28[32]; // [rsp+60h] [rbp-A0h] BYREF
  char *v29; // [rsp+80h] [rbp-80h]
  int v30; // [rsp+88h] [rbp-78h]
  __int16 v31; // [rsp+8Ch] [rbp-74h]
  const wchar_t *v32[4]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v33; // [rsp+B0h] [rbp-50h]
  char v34; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v35[271]; // [rsp+D1h] [rbp-2Fh] BYREF

  v24 = 0;
  STRU::STRU((STRU *)v32);
  v27 = 0;
  v25 = 0;
  *(_OWORD *)dwBytes = 0;
  memset_0(v35, 0, 0x107u);
  v34 = 0;
  v29 = &v34;
  v30 = 264;
  v31 = 256;
  if ( !a1 || !a2 || !a6 )
  {
    FullPath = -2147024809;
    if ( !a6 )
      goto LABEL_21;
    goto LABEL_17;
  }
  *a6 = 0;
  FullPath = RetrieveFullPath(a1, a3, a5, v32);
  if ( FullPath >= 0 )
  {
    LODWORD(dwBytes[0]) = v30;
    dwBytes[1] = (SIZE_T)v29;
    v11 = *(_QWORD *)a2;
    LODWORD(v25) = a4;
    *(_QWORD *)((char *)&v25 + 4) = 1;
    v12 = *(__int64 (__fastcall **)(struct IMDCOM *, _QWORD, __int64, __int128 *, unsigned int *))(v11 + 168);
    HIDWORD(v25) = 0;
    LODWORD(v27) = 0;
    v13 = v12(a2, 0, v33, &v25, &v24);
    FullPath = v13;
    if ( v13 >= 0 )
      goto LABEL_12;
    if ( v13 == -2147024893 || v13 == -2146646015 )
    {
      FullPath = 1;
      goto LABEL_21;
    }
    if ( v13 != -2147024774 )
      goto LABEL_17;
    if ( !BUFFER::Resize((BUFFER *)v28, v24) )
      goto LABEL_10;
    dwBytes[1] = (SIZE_T)v29;
    LODWORD(dwBytes[0]) = v30;
    FullPath = (*(__int64 (__fastcall **)(struct IMDCOM *, _QWORD, __int64, __int128 *, unsigned int *))(*(_QWORD *)a2 + 168LL))(
                 a2,
                 0,
                 v33,
                 &v25,
                 &v24);
    if ( FullPath >= 0 )
    {
LABEL_12:
      ProcessHeap = GetProcessHeap();
      v15 = (struct _METADATA_RECORD *)HeapAlloc(ProcessHeap, 0, 0x28u);
      *a6 = v15;
      if ( v15 )
      {
        *(_OWORD *)&v15->dwMDIdentifier = v25;
        *(_OWORD *)&v15->dwMDDataLen = *(_OWORD *)dwBytes;
        *(_QWORD *)&v15->dwMDDataTag = v27;
        v16 = dwBytes[0];
        v17 = GetProcessHeap();
        (*a6)->pbMDData = (unsigned __int8 *)HeapAlloc(v17, 0, v16);
        pbMDData = (*a6)->pbMDData;
        if ( pbMDData )
        {
          memcpy_0(pbMDData, (const void *)dwBytes[1], LODWORD(dwBytes[0]));
          FullPath = 0;
          goto LABEL_21;
        }
      }
LABEL_10:
      FullPath = -2147024882;
    }
  }
LABEL_17:
  if ( *a6 )
  {
    v19 = (*a6)->pbMDData;
    if ( v19 )
    {
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v19);
      (*a6)->pbMDData = 0;
    }
    v21 = *a6;
    v22 = GetProcessHeap();
    HeapFree(v22, 0, v21);
    *a6 = 0;
  }
LABEL_21:
  BUFFER::~BUFFER((BUFFER *)v28);
  STRU::~STRU((STRU *)v32);
  return (unsigned int)FullPath;
}

```

## disassembly

```asm
0x18000f468  push    rbp
0x18000f46a  push    rbx
0x18000f46b  push    rsi
0x18000f46c  push    rdi
0x18000f46d  push    r12
0x18000f46f  push    r14
0x18000f471  push    r15
0x18000f473  lea     rbp, [rsp-0F0h]
0x18000f47b  sub     rsp, 1F0h
0x18000f482  mov     rax, cs:__security_cookie
0x18000f489  xor     rax, rsp
0x18000f48c  mov     [rbp+120h+var_40], rax
0x18000f493  mov     r15, [rbp+120h+arg_20]
0x18000f49a  mov     rdi, rcx
0x18000f49d  mov     rsi, [rbp+120h+arg_28]
0x18000f4a4  lea     rcx, [rbp+120h+var_190]
0x18000f4a8  mov     r12d, r9d
0x18000f4ab  mov     [rsp+220h+var_1F0], 0
0x18000f4b3  mov     r14d, r8d
0x18000f4b6  mov     rbx, rdx
0x18000f4b9  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000f4bf  xorps   xmm0, xmm0
0x18000f4c2  lea     rcx, [rbp+120h+var_14F]; void *
0x18000f4c6  xor     eax, eax
0x18000f4c8  xor     edx, edx; Val
0x18000f4ca  mov     r8d, 107h; Size
0x18000f4d0  mov     [rsp+220h+var_1C8], rax
0x18000f4d5  movups  [rsp+220h+var_1E8], xmm0
0x18000f4da  movups  xmmword ptr [rsp+220h+dwBytes], xmm0
0x18000f4df  call    memset_0
0x18000f4e4  mov     [rbp+120h+var_150], 0
0x18000f4e8  lea     rax, [rbp+120h+var_150]
0x18000f4ec  mov     [rbp+120h+var_1A0], rax
0x18000f4f0  mov     [rbp+120h+var_198], 108h
0x18000f4f7  mov     [rbp+120h+var_194], 100h
0x18000f4fd  test    rdi, rdi
0x18000f500  jz      loc_18000F697
0x18000f506  test    rbx, rbx
0x18000f509  jz      loc_18000F697
0x18000f50f  test    rsi, rsi
0x18000f512  jz      loc_18000F697
0x18000f518  lea     r9, [rbp+120h+var_190]; struct STRU *
0x18000f51c  mov     qword ptr [rsi], 0
0x18000f523  mov     r8, r15; unsigned __int16 *
0x18000f526  mov     edx, r14d; unsigned int
0x18000f529  mov     rcx, rdi; struct CADMCOMW *
0x18000f52c  call    ?RetrieveFullPath@@YAJPEAVCADMCOMW@@KPEBGPEAVSTRU@@@Z; RetrieveFullPath(CADMCOMW *,ulong,ushort const *,STRU *)
0x18000f531  mov     edi, eax
0x18000f533  test    eax, eax
0x18000f535  js      loc_18000F6A1
0x18000f53b  mov     eax, [rbp+120h+var_198]
0x18000f53e  lea     rcx, [rsp+220h+var_1F0]
0x18000f543  mov     r8, [rbp+120h+var_170]
0x18000f547  lea     r9, [rsp+220h+var_1E8]
0x18000f54c  mov     dword ptr [rsp+220h+dwBytes], eax
0x18000f550  mov     r14d, 1
0x18000f556  mov     rax, [rbp+120h+var_1A0]
0x18000f55a  xor     edx, edx
0x18000f55c  mov     [rsp+220h+dwBytes+8], rax
0x18000f561  mov     rax, [rbx]
0x18000f564  mov     [rsp+220h+var_200], rcx
0x18000f569  mov     rcx, rbx
0x18000f56c  mov     dword ptr [rsp+220h+var_1E8], r12d
0x18000f571  mov     qword ptr [rsp+220h+var_1E8+4], r14
0x18000f576  mov     rax, [rax+0A8h]
0x18000f57d  mov     dword ptr [rsp+220h+var_1E8+0Ch], 0
0x18000f585  mov     dword ptr [rsp+220h+var_1C8], 0
0x18000f58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f592  mov     edi, eax
0x18000f594  test    eax, eax
0x18000f596  jns     short loc_18000F617
0x18000f598  cmp     eax, 80070003h
0x18000f59d  jz      loc_18000F692
0x18000f5a3  cmp     eax, 800CC801h
0x18000f5a8  jz      loc_18000F692
0x18000f5ae  cmp     eax, 8007007Ah
0x18000f5b3  jnz     loc_18000F6A1
0x18000f5b9  mov     edx, [rsp+220h+var_1F0]
0x18000f5bd  lea     rcx, [rsp+220h+var_1C0]
0x18000f5c2  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000f5c8  test    al, al
0x18000f5ca  jnz     short loc_18000F5D6
0x18000f5cc  mov     edi, 8007000Eh
0x18000f5d1  jmp     loc_18000F6A1
0x18000f5d6  mov     rax, [rbp+120h+var_1A0]
0x18000f5da  lea     rcx, [rsp+220h+var_1F0]
0x18000f5df  mov     r8, [rbp+120h+var_170]
0x18000f5e3  lea     r9, [rsp+220h+var_1E8]
0x18000f5e8  mov     [rsp+220h+dwBytes+8], rax
0x18000f5ed  xor     edx, edx
0x18000f5ef  mov     eax, [rbp+120h+var_198]
0x18000f5f2  mov     dword ptr [rsp+220h+dwBytes], eax
0x18000f5f6  mov     rax, [rbx]
0x18000f5f9  mov     [rsp+220h+var_200], rcx
0x18000f5fe  mov     rcx, rbx
0x18000f601  mov     rax, [rax+0A8h]
0x18000f608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f60d  mov     edi, eax
0x18000f60f  test    eax, eax
0x18000f611  js      loc_18000F6A1
0x18000f617  call    cs:__imp_GetProcessHeap
0x18000f61d  xor     edx, edx; dwFlags
0x18000f61f  mov     rcx, rax; hHeap
0x18000f622  lea     r8d, [rdx+28h]; dwBytes
0x18000f626  call    cs:__imp_HeapAlloc
0x18000f62c  mov     [rsi], rax
0x18000f62f  test    rax, rax
0x18000f632  jz      short loc_18000F5CC
0x18000f634  movups  xmm0, [rsp+220h+var_1E8]
0x18000f639  movups  xmmword ptr [rax], xmm0
0x18000f63c  movups  xmm1, xmmword ptr [rsp+220h+dwBytes]
0x18000f641  movups  xmmword ptr [rax+10h], xmm1
0x18000f645  movsd   xmm0, [rsp+220h+var_1C8]
0x18000f64b  movsd   qword ptr [rax+20h], xmm0
0x18000f650  mov     ebx, dword ptr [rsp+220h+dwBytes]
0x18000f654  call    cs:__imp_GetProcessHeap
0x18000f65a  mov     r8d, ebx; dwBytes
0x18000f65d  xor     edx, edx; dwFlags
0x18000f65f  mov     rcx, rax; hHeap
0x18000f662  call    cs:__imp_HeapAlloc
0x18000f668  mov     rcx, [rsi]
0x18000f66b  mov     [rcx+18h], rax
0x18000f66f  mov     rax, [rsi]
0x18000f672  mov     rcx, [rax+18h]; void *
0x18000f676  test    rcx, rcx
0x18000f679  jz      loc_18000F5CC
0x18000f67f  mov     r8d, dword ptr [rsp+220h+dwBytes]; Size
0x18000f684  mov     rdx, [rsp+220h+dwBytes+8]; Src
0x18000f689  call    memcpy_0
0x18000f68e  xor     edi, edi
0x18000f690  jmp     short loc_18000F6EF
0x18000f692  mov     edi, r14d
0x18000f695  jmp     short loc_18000F6EF
0x18000f697  mov     edi, 80070057h
0x18000f69c  test    rsi, rsi
0x18000f69f  jz      short loc_18000F6EF
0x18000f6a1  mov     rax, [rsi]
0x18000f6a4  test    rax, rax
0x18000f6a7  jz      short loc_18000F6EF
0x18000f6a9  mov     rbx, [rax+18h]
0x18000f6ad  test    rbx, rbx
0x18000f6b0  jz      short loc_18000F6D1
0x18000f6b2  call    cs:__imp_GetProcessHeap
0x18000f6b8  mov     r8, rbx; lpMem
0x18000f6bb  xor     edx, edx; dwFlags
0x18000f6bd  mov     rcx, rax; hHeap
0x18000f6c0  call    cs:__imp_HeapFree
0x18000f6c6  mov     rax, [rsi]
0x18000f6c9  mov     qword ptr [rax+18h], 0
0x18000f6d1  mov     rbx, [rsi]
0x18000f6d4  call    cs:__imp_GetProcessHeap
0x18000f6da  mov     r8, rbx; lpMem
0x18000f6dd  xor     edx, edx; dwFlags
0x18000f6df  mov     rcx, rax; hHeap
0x18000f6e2  call    cs:__imp_HeapFree
0x18000f6e8  mov     qword ptr [rsi], 0
0x18000f6ef  lea     rcx, [rsp+220h+var_1C0]
0x18000f6f4  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000f6fa  lea     rcx, [rbp+120h+var_190]
0x18000f6fe  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000f704  mov     eax, edi
0x18000f706  mov     rcx, [rbp+120h+var_40]
0x18000f70d  xor     rcx, rsp; StackCookie
0x18000f710  call    __security_check_cookie
0x18000f715  add     rsp, 1F0h
0x18000f71c  pop     r15
0x18000f71e  pop     r14
0x18000f720  pop     r12
0x18000f722  pop     rdi
0x18000f723  pop     rsi
0x18000f724  pop     rbx
0x18000f725  pop     rbp
0x18000f726  retn
```
