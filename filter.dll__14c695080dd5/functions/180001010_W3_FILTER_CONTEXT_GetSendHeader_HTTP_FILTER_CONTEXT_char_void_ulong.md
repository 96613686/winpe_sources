# W3_FILTER_CONTEXT::GetSendHeader(_HTTP_FILTER_CONTEXT *,char *,void *,ulong *)

- ea: `0x180001010`
- end: `0x180001317`
- name: `?GetSendHeader@W3_FILTER_CONTEXT@@SAHPEAU_HTTP_FILTER_CONTEXT@@PEADPEAXPEAK@Z`
- size: `775`
- prototype: `__int64 __fastcall(struct _HTTP_FILTER_CONTEXT *, char *, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001010`
- `0x18000c970`
- `0x18000d010`

## import_xrefs

- `msvcrt!_ultoa_s` at `0x18000124e`
- `msvcrt!_ultoa_s` at `0x18000124e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001151`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001151`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180001287`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800012a3`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x180001287`
- `iisutil!?Append@STRA@@QEAAJPEBD@Z` at `0x1800012a3`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x1800012c3`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x1800012c3`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000112b`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x18000112b`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800010fe`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180001199`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x1800010fe`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180001199`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x1800012de`
- `iisutil!?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z` at `0x1800012de`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000115c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001166`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800012f3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800012fd`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000115c`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180001166`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800012f3`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800012fd`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001051`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001069`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001051`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180001069`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000126e`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000126e`

## pseudocode

```c
__int64 __fastcall W3_FILTER_CONTEXT::GetSendHeader(
        struct _HTTP_FILTER_CONTEXT *a1,
        char *a2,
        char *a3,
        unsigned int *a4)
{
  _QWORD *ServerContext; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  int v11; // edx
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // r8
  signed int v15; // ecx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, char *, unsigned __int16 *); // rbx
  char *Str; // rax
  const char *v19; // rax
  __int64 v21; // rax
  _WORD v22[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v23; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 v24; // [rsp+68h] [rbp-98h] BYREF
  const char *v25; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[56]; // [rsp+78h] [rbp-88h] BYREF
  char v27[56]; // [rsp+B0h] [rbp-50h] BYREF
  char Buffer[40]; // [rsp+E8h] [rbp-18h] BYREF
  char v29[128]; // [rsp+110h] [rbp+10h] BYREF
  char v30[128]; // [rsp+190h] [rbp+90h] BYREF

  STRA::STRA((STRA *)v27, v29, 0x80u);
  STRA::STRA((STRA *)v26, v30, 0x80u);
  v24 = 0;
  if ( !a1 || (ServerContext = a1->ServerContext) == 0 || !a2 || !a4 )
  {
    v15 = 87;
    goto LABEL_17;
  }
  v9 = ServerContext[3];
  v10 = 0;
  do
  {
    v11 = (unsigned __int8)a2[v10++];
    v12 = v11 - (unsigned int)(unsigned __int8)aStatus[v10 - 1];
  }
  while ( !(_DWORD)v12 && v10 != 7 );
  if ( (_DWORD)v12 )
  {
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
    if ( (unsigned int)v13 <= 1 || (v14 = (unsigned int)(v13 - 1), a2[v14] != 58) )
    {
      LOWORD(v15) = 87;
      goto LABEL_16;
    }
    v15 = STRA::Copy((STRA *)v27, a2, v14);
    if ( v15 < 0 )
      goto LABEL_19;
    v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 32LL))(v9);
    v17 = *(__int64 (__fastcall **)(__int64, char *, unsigned __int16 *))(*(_QWORD *)v16 + 72LL);
    Str = STRA::QueryStr((STRA *)v27);
    v19 = (const char *)v17(v16, Str, &v24);
    if ( !v19 )
    {
      LOWORD(v15) = 1413;
LABEL_16:
      v15 = (unsigned __int16)v15;
LABEL_17:
      SetLastError(v15);
      STRA::~STRA((STRA *)v26);
      STRA::~STRA((STRA *)v27);
      return 0;
    }
    v15 = STRA::Copy((STRA *)v26, v19, v24);
    if ( v15 < 0 )
    {
LABEL_19:
      if ( (v15 & 0x1FFF0000) != 0x70000 )
        goto LABEL_17;
      goto LABEL_16;
    }
  }
  else
  {
    v22[0] = 0;
    v25 = 0;
    v23 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, __int64, const char *))(*(_QWORD *)v9 + 32LL))(v9, v12, "status");
    (*(void (__fastcall **)(__int64, _WORD *, _QWORD, const char **, unsigned __int16 *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v21 + 184LL))(
      v21,
      v22,
      0,
      &v25,
      &v23,
      0,
      0,
      0,
      0,
      0);
    if ( _ultoa_s(v22[0], Buffer, 0x20u, 10) )
    {
      v15 = -2147467259;
      goto LABEL_17;
    }
    v15 = STRA::Copy((STRA *)v26, "HTTP/1.1 ");
    if ( v15 < 0 )
      goto LABEL_19;
    v15 = STRA::Append((STRA *)v26, Buffer);
    if ( v15 < 0 )
      goto LABEL_19;
    v15 = STRA::Append((STRA *)v26, " ");
    if ( v15 < 0 )
      goto LABEL_19;
    v15 = STRA::Append((STRA *)v26, v25, v23);
    if ( v15 < 0 )
      goto LABEL_19;
  }
  v15 = STRA::CopyToBuffer((STRA *)v26, a3, a4);
  if ( v15 < 0 )
    goto LABEL_19;
  STRA::~STRA((STRA *)v26);
  STRA::~STRA((STRA *)v27);
  return 1;
}

```

## disassembly

```asm
0x180001010  push    rbp
0x180001012  push    rbx
0x180001013  push    rsi
0x180001014  push    rdi
0x180001015  push    r14
0x180001017  lea     rbp, [rsp-120h]
0x18000101f  sub     rsp, 220h
0x180001026  mov     rax, cs:__security_cookie
0x18000102d  xor     rax, rsp
0x180001030  mov     [rbp+140h+var_30], rax
0x180001037  mov     r14, r8
0x18000103a  mov     rbx, rdx
0x18000103d  mov     rdi, rcx
0x180001040  lea     rdx, [rbp+140h+var_130]
0x180001044  mov     r8d, 80h
0x18000104a  lea     rcx, [rbp+140h+var_190]
0x18000104e  mov     rsi, r9
0x180001051  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180001057  mov     r8d, 80h
0x18000105d  lea     rdx, [rbp+140h+var_B0]
0x180001064  lea     rcx, [rsp+240h+var_1C8]
0x180001069  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000106f  xor     eax, eax
0x180001071  mov     [rsp+240h+var_1D8], ax
0x180001076  test    rdi, rdi
0x180001079  jz      loc_18000130D
0x18000107f  mov     rax, [rdi+8]
0x180001083  test    rax, rax
0x180001086  jz      loc_18000130D
0x18000108c  test    rbx, rbx
0x18000108f  jz      loc_18000130D
0x180001095  test    rsi, rsi
0x180001098  jz      loc_18000130D
0x18000109e  mov     rdi, [rax+18h]
0x1800010a2  lea     r8, aStatus; "status"
0x1800010a9  xor     eax, eax
0x1800010ab  nop     dword ptr [rax+rax+00h]
0x1800010b0  movzx   edx, byte ptr [rbx+rax]
0x1800010b4  inc     rax
0x1800010b7  movzx   ecx, byte ptr [r8+rax-1]
0x1800010bd  sub     edx, ecx
0x1800010bf  jnz     short loc_1800010C7
0x1800010c1  cmp     rax, 7
0x1800010c5  jnz     short loc_1800010B0
0x1800010c7  test    edx, edx
0x1800010c9  jz      loc_1800011C0
0x1800010cf  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800010d6  inc     rax
0x1800010d9  cmp     byte ptr [rbx+rax], 0
0x1800010dd  jnz     short loc_1800010D6
0x1800010df  cmp     eax, 1
0x1800010e2  jbe     loc_1800011B9
0x1800010e8  lea     r8d, [rax-1]
0x1800010ec  cmp     byte ptr [r8+rbx], 3Ah ; ':'
0x1800010f1  jnz     loc_1800011B9
0x1800010f7  mov     rdx, rbx
0x1800010fa  lea     rcx, [rbp+140h+var_190]
0x1800010fe  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x180001104  mov     ecx, eax
0x180001106  test    eax, eax
0x180001108  js      loc_1800011A9
0x18000110e  mov     rax, [rdi]
0x180001111  mov     rcx, rdi
0x180001114  mov     rax, [rax+20h]
0x180001118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000111d  mov     rdi, rax
0x180001120  mov     rcx, [rax]
0x180001123  mov     rbx, [rcx+48h]
0x180001127  lea     rcx, [rbp+140h+var_190]
0x18000112b  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180001131  lea     r8, [rsp+240h+var_1D8]
0x180001136  mov     rcx, rdi
0x180001139  mov     rdx, rax
0x18000113c  mov     rax, rbx
0x18000113f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001144  test    rax, rax
0x180001147  jnz     short loc_18000118B
0x180001149  mov     ecx, 80070585h
0x18000114e  movzx   ecx, cx; dwErrCode
0x180001151  call    cs:__imp_SetLastError
0x180001157  lea     rcx, [rsp+240h+var_1C8]
0x18000115c  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001162  lea     rcx, [rbp+140h+var_190]
0x180001166  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x18000116c  xor     eax, eax
0x18000116e  mov     rcx, [rbp+140h+var_30]
0x180001175  xor     rcx, rsp; StackCookie
0x180001178  call    __security_check_cookie
0x18000117d  add     rsp, 220h
0x180001184  pop     r14
0x180001186  pop     rdi
0x180001187  pop     rsi
0x180001188  pop     rbx
0x180001189  pop     rbp
0x18000118a  retn
0x18000118b  movzx   r8d, [rsp+240h+var_1D8]
0x180001191  lea     rcx, [rsp+240h+var_1C8]
0x180001196  mov     rdx, rax
0x180001199  call    cs:__imp_?Copy@STRA@@QEAAJPEBDK@Z; STRA::Copy(char const *,ulong)
0x18000119f  mov     ecx, eax
0x1800011a1  test    eax, eax
0x1800011a3  jns     loc_1800012D3
0x1800011a9  mov     eax, ecx
0x1800011ab  and     eax, 1FFF0000h
0x1800011b0  cmp     eax, 70000h
0x1800011b5  jz      short loc_18000114E
0x1800011b7  jmp     short loc_180001151
0x1800011b9  mov     ecx, 80070057h
0x1800011be  jmp     short loc_18000114E
0x1800011c0  xor     eax, eax
0x1800011c2  mov     rcx, rdi
0x1800011c5  mov     [rsp+240h+var_1E0], ax
0x1800011ca  mov     [rsp+240h+var_1D0], rax
0x1800011cf  mov     [rsp+240h+var_1DC], ax
0x1800011d4  mov     rax, [rdi]
0x1800011d7  mov     rax, [rax+20h]
0x1800011db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011e0  mov     [rsp+240h+var_1F8], 0
0x1800011e9  lea     r9, [rsp+240h+var_1D0]
0x1800011ee  mov     [rsp+240h+var_200], 0
0x1800011f7  lea     rdx, [rsp+240h+var_1E0]
0x1800011fc  mov     r10, rax
0x1800011ff  mov     [rsp+240h+var_208], 0
0x180001208  mov     rcx, [rax]
0x18000120b  xor     r8d, r8d
0x18000120e  mov     [rsp+240h+var_210], 0
0x180001217  mov     [rsp+240h+var_218], 0
0x180001220  mov     rax, [rcx+0B8h]
0x180001227  lea     rcx, [rsp+240h+var_1DC]
0x18000122c  mov     [rsp+240h+var_220], rcx
0x180001231  mov     rcx, r10
0x180001234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001239  movzx   ecx, [rsp+240h+var_1E0]; Value
0x18000123e  lea     rdx, [rbp+140h+Buffer]; Buffer
0x180001242  mov     r9d, 0Ah; Radix
0x180001248  mov     r8d, 20h ; ' '; BufferCount
0x18000124e  call    cs:__imp__ultoa_s
0x180001254  test    eax, eax
0x180001256  jz      short loc_180001262
0x180001258  mov     ecx, 80004005h
0x18000125d  jmp     loc_180001151
0x180001262  lea     rdx, Str2; "HTTP/1.1 "
0x180001269  lea     rcx, [rsp+240h+var_1C8]
0x18000126e  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180001274  mov     ecx, eax
0x180001276  test    eax, eax
0x180001278  js      loc_1800011A9
0x18000127e  lea     rdx, [rbp+140h+Buffer]
0x180001282  lea     rcx, [rsp+240h+var_1C8]
0x180001287  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x18000128d  mov     ecx, eax
0x18000128f  test    eax, eax
0x180001291  js      loc_1800011A9
0x180001297  lea     rdx, asc_18000EE88; " "
0x18000129e  lea     rcx, [rsp+240h+var_1C8]
0x1800012a3  call    cs:__imp_?Append@STRA@@QEAAJPEBD@Z; STRA::Append(char const *)
0x1800012a9  mov     ecx, eax
0x1800012ab  test    eax, eax
0x1800012ad  js      loc_1800011A9
0x1800012b3  movzx   r8d, [rsp+240h+var_1DC]
0x1800012b9  lea     rcx, [rsp+240h+var_1C8]
0x1800012be  mov     rdx, [rsp+240h+var_1D0]
0x1800012c3  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x1800012c9  mov     ecx, eax
0x1800012cb  test    eax, eax
0x1800012cd  js      loc_1800011A9
0x1800012d3  mov     r8, rsi
0x1800012d6  lea     rcx, [rsp+240h+var_1C8]
0x1800012db  mov     rdx, r14
0x1800012de  call    cs:__imp_?CopyToBuffer@STRA@@QEBAJPEADPEAK@Z; STRA::CopyToBuffer(char *,ulong *)
0x1800012e4  mov     ecx, eax
0x1800012e6  test    eax, eax
0x1800012e8  js      loc_1800011A9
0x1800012ee  lea     rcx, [rsp+240h+var_1C8]
0x1800012f3  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800012f9  lea     rcx, [rbp+140h+var_190]
0x1800012fd  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180001303  mov     eax, 1
0x180001308  jmp     loc_18000116E
0x18000130d  mov     ecx, 57h ; 'W'
0x180001312  jmp     loc_180001151
```
