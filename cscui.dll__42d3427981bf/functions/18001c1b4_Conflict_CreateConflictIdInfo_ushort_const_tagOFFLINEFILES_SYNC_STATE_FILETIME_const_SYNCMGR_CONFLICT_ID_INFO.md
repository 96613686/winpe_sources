# Conflict_CreateConflictIdInfo(ushort const *,tagOFFLINEFILES_SYNC_STATE,_FILETIME const &,SYNCMGR_CONFLICT_ID_INFO *)

- ea: `0x18001c1b4`
- end: `0x18001c3d0`
- name: `?Conflict_CreateConflictIdInfo@@YAJPEBGW4tagOFFLINEFILES_SYNC_STATE@@AEBU_FILETIME@@PEAUSYNCMGR_CONFLICT_ID_INFO@@@Z`
- size: `540`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum tagOFFLINEFILES_SYNC_STATE, const struct _FILETIME *, struct SYNCMGR_CONFLICT_ID_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001d080`

## callees

- `0x180002810`
- `0x180005b70`
- `0x18000735c`
- `0x18001c1b4`
- `0x18004c636`
- `0x18004c670`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c299`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c337`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c299`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c337`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c384`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c394`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c384`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c394`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x18001c267`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x18001c267`

## pseudocode

```c
__int64 __fastcall Conflict_CreateConflictIdInfo(
        const unsigned __int16 *a1,
        DWORD a2,
        const struct _FILETIME *a3,
        struct SYNCMGR_CONFLICT_ID_INFO *a4)
{
  signed int v7; // ebx
  WCHAR *v8; // rcx
  const unsigned __int16 *ConstBuffer; // rax
  __int64 v10; // rdi
  unsigned __int64 v11; // rdi
  void *v12; // rax
  _DWORD *v13; // rsi
  const unsigned __int16 *v14; // rax
  unsigned __int64 v15; // rdi
  _WORD *v16; // rdx
  __int64 v17; // rcx
  _WORD *v18; // rcx
  struct _FILETIME *v19; // rax
  LPVOID pv[2]; // [rsp+20h] [rbp-E0h]
  _WORD v22[260]; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+238h] [rbp+138h]
  WCHAR *v24; // [rsp+240h] [rbp+140h]
  LPWSTR lpsz; // [rsp+248h] [rbp+148h]
  WCHAR *v26; // [rsp+250h] [rbp+150h]
  __int64 v27; // [rsp+258h] [rbp+158h]
  __int64 v28; // [rsp+260h] [rbp+160h]

  v23 = 34078720;
  lpsz = v22;
  v27 = 520;
  v26 = v22;
  v28 = 520;
  v24 = v22;
  v22[0] = 0;
  v7 = CPath::Copy((CPath *)v22, a1);
  if ( v7 < 0 )
    goto LABEL_26;
  v8 = v24;
  if ( lpsz != v26 )
    v8 = lpsz;
  CharLowerW(v8);
  *(_OWORD *)pv = 0;
  ConstBuffer = CPath::_GetConstBuffer((CPath *)v22);
  v10 = -1;
  do
    ++v10;
  while ( ConstBuffer[v10] );
  v11 = 2 * v10 + 2;
  v12 = CoTaskMemAlloc(v11 + 4);
  pv[0] = v12;
  v13 = v12;
  if ( !v12 )
    goto LABEL_21;
  memset_0(v12, 0, v11 + 4);
  *v13 = v11;
  v14 = CPath::_GetConstBuffer((CPath *)v22);
  v15 = v11 >> 1;
  v16 = v13 + 1;
  v7 = -2147024809;
  if ( v15 )
  {
    if ( v15 > 0x7FFFFFFF )
    {
      *v16 = 0;
      goto LABEL_22;
    }
    v17 = 2147483646;
    do
    {
      if ( !v17 )
        break;
      if ( !*v14 )
        break;
      *v16++ = *v14++;
      --v17;
      --v15;
    }
    while ( v15 );
    v18 = v16 - 1;
    if ( v15 )
      v18 = v16;
    v7 = v15 == 0 ? 0x8007007A : 0;
    *v18 = 0;
  }
  if ( v7 >= 0 )
  {
    v19 = (struct _FILETIME *)CoTaskMemAlloc(0x10u);
    pv[1] = v19;
    if ( v19 )
    {
      v19[1] = 0;
      v7 = 0;
      v19->dwLowDateTime = 12;
      v19->dwHighDateTime = a2;
      v19[1] = *a3;
      *a4 = *(struct SYNCMGR_CONFLICT_ID_INFO *)pv;
      goto LABEL_26;
    }
LABEL_21:
    v7 = -2147024882;
  }
LABEL_22:
  if ( v13 )
    CoTaskMemFree(v13);
  if ( pv[1] )
    CoTaskMemFree(pv[1]);
LABEL_26:
  CPath::~CPath((CPath *)v22);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001c1b4  mov     [rsp-8+arg_8], rbx
0x18001c1b9  push    rbp
0x18001c1ba  push    rsi
0x18001c1bb  push    rdi
0x18001c1bc  push    r12
0x18001c1be  push    r13
0x18001c1c0  push    r14
0x18001c1c2  push    r15
0x18001c1c4  lea     rbp, [rsp-180h]
0x18001c1cc  sub     rsp, 280h
0x18001c1d3  mov     rax, cs:__security_cookie
0x18001c1da  xor     rax, rsp
0x18001c1dd  mov     [rbp+1B0h+var_40], rax
0x18001c1e4  mov     r15d, edx
0x18001c1e7  mov     [rbp+1B0h+var_78], 2080000h
0x18001c1f1  mov     edx, 208h
0x18001c1f6  lea     rax, [rsp+2B0h+var_280]
0x18001c1fb  mov     [rbp+1B0h+lpsz], rax
0x18001c202  xor     r13d, r13d
0x18001c205  lea     rax, [rsp+2B0h+var_280]
0x18001c20a  mov     [rbp+1B0h+var_58], rdx
0x18001c211  mov     [rbp+1B0h+var_60], rax
0x18001c218  mov     r12, r9
0x18001c21b  mov     [rbp+1B0h+var_50], rdx
0x18001c222  lea     rax, [rsp+2B0h+var_280]
0x18001c227  mov     rdx, rcx; unsigned __int16 *
0x18001c22a  mov     [rbp+1B0h+var_70], rax
0x18001c231  lea     rcx, [rsp+2B0h+var_280]; this
0x18001c236  mov     [rsp+2B0h+var_280], r13w
0x18001c23c  mov     r14, r8
0x18001c23f  call    ?Copy@CPath@@QEAAJPEBG@Z; CPath::Copy(ushort const *)
0x18001c244  mov     ebx, eax
0x18001c246  test    eax, eax
0x18001c248  js      loc_18001C39A
0x18001c24e  mov     rax, [rbp+1B0h+lpsz]
0x18001c255  cmp     rax, [rbp+1B0h+var_60]
0x18001c25c  mov     rcx, [rbp+1B0h+var_70]
0x18001c263  cmovnz  rcx, rax; lpsz
0x18001c267  call    cs:__imp_CharLowerW
0x18001c26d  xorps   xmm0, xmm0
0x18001c270  lea     rcx, [rsp+2B0h+var_280]; this
0x18001c275  movups  xmmword ptr [rsp+2B0h+pv], xmm0
0x18001c27a  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001c27f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001c283  inc     rdi
0x18001c286  cmp     [rax+rdi*2], r13w
0x18001c28b  jnz     short loc_18001C283
0x18001c28d  lea     rdi, ds:2[rdi*2]
0x18001c295  lea     rcx, [rdi+4]; cb
0x18001c299  call    cs:__imp_CoTaskMemAlloc
0x18001c29f  mov     [rsp+2B0h+pv], rax
0x18001c2a4  mov     rsi, rax
0x18001c2a7  test    rax, rax
0x18001c2aa  jz      loc_18001C377
0x18001c2b0  lea     r8, [rdi+4]; Size
0x18001c2b4  xor     edx, edx; Val
0x18001c2b6  mov     rcx, rax; void *
0x18001c2b9  call    memset_0
0x18001c2be  lea     rcx, [rsp+2B0h+var_280]; this
0x18001c2c3  mov     [rsi], edi
0x18001c2c5  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x18001c2ca  shr     rdi, 1
0x18001c2cd  lea     rdx, [rsi+4]
0x18001c2d1  mov     ebx, 80070057h
0x18001c2d6  jz      loc_18001C36C
0x18001c2dc  cmp     rdi, 7FFFFFFFh
0x18001c2e3  ja      loc_18001C371
0x18001c2e9  mov     ecx, 7FFFFFFEh
0x18001c2ee  test    rcx, rcx
0x18001c2f1  jz      short loc_18001C312
0x18001c2f3  movzx   r8d, word ptr [rax]
0x18001c2f7  test    r8w, r8w
0x18001c2fb  jz      short loc_18001C312
0x18001c2fd  mov     [rdx], r8w
0x18001c301  add     rax, 2
0x18001c305  add     rdx, 2
0x18001c309  dec     rcx
0x18001c30c  sub     rdi, 1
0x18001c310  jnz     short loc_18001C2EE
0x18001c312  test    rdi, rdi
0x18001c315  lea     rcx, [rdx-2]
0x18001c319  cmovnz  rcx, rdx
0x18001c31d  neg     rdi
0x18001c320  sbb     ebx, ebx
0x18001c322  not     ebx
0x18001c324  and     ebx, 8007007Ah
0x18001c32a  mov     [rcx], r13w
0x18001c32e  test    ebx, ebx
0x18001c330  js      short loc_18001C37C
0x18001c332  mov     ecx, 10h; cb
0x18001c337  call    cs:__imp_CoTaskMemAlloc
0x18001c33d  mov     [rsp+2B0h+pv+8], rax
0x18001c342  test    rax, rax
0x18001c345  jz      short loc_18001C377
0x18001c347  mov     [rax+8], r13
0x18001c34b  mov     ebx, r13d
0x18001c34e  movups  xmm0, xmmword ptr [rsp+2B0h+pv]
0x18001c353  mov     dword ptr [rax], 0Ch
0x18001c359  mov     [rax+4], r15d
0x18001c35d  mov     rcx, [r14]
0x18001c360  mov     [rax+8], rcx
0x18001c364  movdqu  xmmword ptr [r12], xmm0
0x18001c36a  jmp     short loc_18001C39A
0x18001c36c  test    rdi, rdi
0x18001c36f  jz      short loc_18001C32E
0x18001c371  mov     [rdx], r13w
0x18001c375  jmp     short loc_18001C37C
0x18001c377  mov     ebx, 8007000Eh
0x18001c37c  test    rsi, rsi
0x18001c37f  jz      short loc_18001C38A
0x18001c381  mov     rcx, rsi; pv
0x18001c384  call    cs:__imp_CoTaskMemFree
0x18001c38a  mov     rcx, [rsp+2B0h+pv+8]; pv
0x18001c38f  test    rcx, rcx
0x18001c392  jz      short loc_18001C39A
0x18001c394  call    cs:__imp_CoTaskMemFree
0x18001c39a  lea     rcx, [rsp+2B0h+var_280]; this
0x18001c39f  call    ??1CPath@@QEAA@XZ; CPath::~CPath(void)
0x18001c3a4  mov     eax, ebx
0x18001c3a6  mov     rcx, [rbp+1B0h+var_40]
0x18001c3ad  xor     rcx, rsp; StackCookie
0x18001c3b0  call    __security_check_cookie
0x18001c3b5  mov     rbx, [rsp+2B0h+arg_8]
0x18001c3bd  add     rsp, 280h
0x18001c3c4  pop     r15
0x18001c3c6  pop     r14
0x18001c3c8  pop     r13
0x18001c3ca  pop     r12
0x18001c3cc  pop     rdi
0x18001c3cd  pop     rsi
0x18001c3ce  pop     rbp
0x18001c3cf  retn
```
