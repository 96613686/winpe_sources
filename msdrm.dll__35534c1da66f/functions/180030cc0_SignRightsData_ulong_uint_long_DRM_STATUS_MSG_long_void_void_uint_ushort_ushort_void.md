# SignRightsData(ulong,uint,long (*)(_DRM_STATUS_MSG,long,void *,void *),uint,ushort *,ushort *,void *)

- ea: `0x180030cc0`
- end: `0x180031105`
- name: `?SignRightsData@@YAJKIP6AJW4_DRM_STATUS_MSG@@JPEAX1@ZIPEAG31@Z`
- size: `1093`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, int (*)(enum _DRM_STATUS_MSG, int, void *, void *), unsigned int, unsigned __int16 *, unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180005fc0`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x180015438`
- `0x180017358`
- `0x180030cc0`
- `0x1800385a0`
- `0x18005bd72`
- `0x18005bdc0`
- `0x18005f010`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x180030ffc`
- `msvcrt!_beginthreadex` at `0x180030ffc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180030dbb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180030dbb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180030dc6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180030dc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031007`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180030d47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180030d47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031052`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031087`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031052`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031087`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=2
__int64 __fastcall SignRightsData(
        int a1,
        char a2,
        int (*a3)(enum _DRM_STATUS_MSG, int, void *, void *),
        __int64 a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        void *a7)
{
  int (*v7)(enum _DRM_STATUS_MSG, int, void *, void *); // r12
  void *v10; // r15
  DWORD CurrentProcessId; // eax
  DRMOS *v12; // rcx
  signed int v13; // ebx
  const unsigned __int16 *v14; // r9
  void *v15; // rax
  void *v16; // r15
  signed int LastError; // eax
  void **v18; // rax
  void **v19; // rsi
  HANDLE *v20; // r14
  __int64 v21; // rdx
  unsigned __int16 *v22; // rax
  unsigned __int64 v23; // r8
  signed __int64 v24; // rbx
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // rcx
  unsigned __int16 *v27; // rax
  __int64 v28; // rcx
  unsigned __int16 *v29; // rax
  unsigned __int64 v30; // rdx
  signed __int64 v31; // r12
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rcx
  unsigned __int16 *v34; // rax
  uintptr_t v35; // rax
  signed int v36; // eax
  void *v37; // rcx
  unsigned int ThrdAddr; // [rsp+40h] [rbp-E8h] BYREF
  int (*v40)(enum _DRM_STATUS_MSG, int, void *, void *); // [rsp+48h] [rbp-E0h]
  void **v41; // [rsp+50h] [rbp-D8h]
  char *v42; // [rsp+58h] [rbp-D0h]
  int (*v43)(enum _DRM_STATUS_MSG, int, void *, void *); // [rsp+68h] [rbp-C0h]
  unsigned __int16 *v44; // [rsp+70h] [rbp-B8h]
  __int64 v45; // [rsp+78h] [rbp-B0h]
  unsigned __int16 v46[56]; // [rsp+80h] [rbp-A8h] BYREF

  v45 = -2;
  v7 = a3;
  v40 = a3;
  v43 = a3;
  v44 = a5;
  v10 = a7;
  ThrdAddr = 0;
  memset_0(v46, 0, 0x64u);
  CurrentProcessId = GetCurrentProcessId();
  v13 = StringCchPrintfW(v46, 0x32u, L"UDRMPublishingSignRL_%lu%lu", CurrentProcessId, a1);
  if ( v13 >= 0 )
  {
    v15 = DRMOS::OpenEventA(v12, 1u, (int)v46, v14);
    v16 = v15;
    if ( !v15 )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      if ( v13 >= 0 )
        v13 = -2147467259;
LABEL_50:
      v10 = a7;
      goto LABEL_51;
    }
    if ( (a2 & 4) != 0 )
    {
      SetEvent(v15);
LABEL_46:
      v37 = v16;
      goto LABEL_47;
    }
    ResetEvent(v15);
    if ( !v7 || !a5 || !a6 )
    {
      v13 = -2147024809;
      goto LABEL_46;
    }
    v18 = (void **)operator new(0x30u);
    v19 = v18;
    v41 = v18;
    if ( !v18 )
    {
      v13 = -2147024882;
      goto LABEL_46;
    }
    *v18 = 0;
    v18[1] = 0;
    *((_DWORD *)v18 + 4) = 0;
    v18[3] = 0;
    v18[4] = 0;
    v18[5] = 0;
    v18[3] = v7;
    v18[4] = a7;
    *((_DWORD *)v18 + 4) = a1;
    v20 = v18 + 5;
    v42 = (char *)(v18 + 5);
    v18[5] = v16;
    v21 = 0x7FFFFFFF;
    v22 = a5;
    v41 = v19;
    do
    {
      if ( !*v22 )
        break;
      ++v22;
      --v21;
    }
    while ( v21 );
    v13 = v21 == 0 ? 0x80070057 : 0;
    v23 = (0x7FFFFFFF - v21) & -(__int64)(v21 != 0);
    if ( v21 )
    {
      v24 = v23 + 1;
      if ( v23 + 1 < v23 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      if ( v24 < 0 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      v25 = 2LL * (unsigned int)v24;
      v26 = HIDWORD(v24) << 33;
      if ( v26 + v25 < v25 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      if ( v26 + v25 )
      {
        v27 = (unsigned __int16 *)operator new(saturated_mul(v24, 2u));
        *v19 = v27;
        if ( !v27 )
        {
          v13 = -2147024882;
          goto LABEL_41;
        }
        v13 = StringCchCopyW(v27, v24, v44);
        if ( v13 < 0 )
          goto LABEL_41;
      }
      v28 = 0x7FFFFFFF;
      v29 = a6;
      do
      {
        if ( !*v29 )
          break;
        ++v29;
        --v28;
      }
      while ( v28 );
      v13 = v28 == 0 ? 0x80070057 : 0;
      v30 = (0x7FFFFFFF - v28) & ((unsigned __int128)-(__int128)(unsigned __int64)v28 >> 64);
      if ( !v28 )
        goto LABEL_41;
      v31 = v30 + 1;
      if ( v30 + 1 < v30 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      if ( v31 < 0 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      v32 = 2LL * (unsigned int)v31;
      v33 = HIDWORD(v31) << 33;
      if ( v33 + v32 < v32 )
        SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
      if ( v33 + v32 )
      {
        v34 = (unsigned __int16 *)operator new(saturated_mul(v31, 2u));
        v19[1] = v34;
        if ( !v34 )
        {
          v13 = -2147024882;
          goto LABEL_41;
        }
        v13 = StringCchCopyW(v34, v31, a6);
        if ( v13 < 0 )
          goto LABEL_41;
      }
      v35 = _beginthreadex(0, 0, SignRightsDataProc, v19, 0, &ThrdAddr);
      if ( v35 )
      {
        v37 = (void *)v35;
LABEL_47:
        CloseHandle(v37);
LABEL_48:
        if ( v13 >= 0 )
          return (unsigned int)v13;
        v7 = v40;
        goto LABEL_50;
      }
      v36 = GetLastError();
      v13 = v36;
      if ( v36 > 0 )
        v13 = (unsigned __int16)v36 | 0x80070000;
      if ( v13 >= 0 )
        v13 = -2147467259;
    }
LABEL_41:
    if ( *v20 )
      CloseHandle(*v20);
    operator delete(*v19);
    operator delete(v19[1]);
    operator delete(v19);
    goto LABEL_48;
  }
LABEL_51:
  if ( v7 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, void *))v7)(4, (unsigned int)v13, 0, v10);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180030cc0  mov     r11, rsp
0x180030cc3  push    rdi
0x180030cc4  push    r12
0x180030cc6  push    r13
0x180030cc8  push    r14
0x180030cca  push    r15
0x180030ccc  sub     rsp, 100h
0x180030cd3  mov     [rsp+128h+var_B0], 0FFFFFFFFFFFFFFFEh
0x180030cdc  mov     [r11+10h], rbx
0x180030ce0  mov     [r11+20h], rsi
0x180030ce4  mov     rax, cs:__security_cookie
0x180030ceb  xor     rax, rsp
0x180030cee  mov     [rsp+128h+var_38], rax
0x180030cf6  mov     r12, r8
0x180030cf9  mov     [rsp+128h+var_E0], r8
0x180030cfe  mov     esi, edx
0x180030d00  mov     r14d, ecx
0x180030d03  mov     [rsp+128h+var_C0], r8
0x180030d08  mov     r13, [rsp+128h+arg_20]
0x180030d10  mov     [rsp+128h+var_B8], r13
0x180030d15  mov     rax, [rsp+128h+arg_28]
0x180030d1d  mov     [rsp+128h+var_F8], rax
0x180030d22  mov     r15, [rsp+128h+arg_30]
0x180030d2a  mov     [rsp+128h+var_F0], r15
0x180030d2f  xor     edi, edi
0x180030d31  mov     [rsp+128h+var_E8], edi
0x180030d35  xor     edx, edx; Val
0x180030d37  lea     r8d, [rdi+64h]; Size
0x180030d3b  lea     rcx, [r11-0A8h]; void *
0x180030d42  call    memset_0
0x180030d47  call    cs:__imp_GetCurrentProcessId
0x180030d4d  mov     r9d, eax
0x180030d50  mov     [rsp+128h+InitFlag], r14d
0x180030d55  lea     r8, ?g_wszPUB_SignCancelEventName@@3QBGB; "UDRMPublishingSignRL_%lu%lu"
0x180030d5c  lea     edx, [rdi+32h]; unsigned __int64
0x180030d5f  lea     rcx, [rsp+128h+var_A8]; unsigned __int16 *
0x180030d67  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030d6c  mov     ebx, eax
0x180030d6e  test    eax, eax
0x180030d70  js      loc_18003109B
0x180030d76  lea     r8, [rsp+128h+var_A8]; int
0x180030d7e  lea     edx, [rdi+1]; unsigned int
0x180030d81  call    ?OpenEventA@DRMOS@@YAPEAXKHPEBG@Z; DRMOS::OpenEventA(ulong,int,ushort const *)
0x180030d86  mov     r15, rax
0x180030d89  test    rax, rax
0x180030d8c  jnz     short loc_180030DB2
0x180030d8e  call    cs:__imp_GetLastError
0x180030d94  mov     ebx, eax
0x180030d96  test    eax, eax
0x180030d98  jle     short loc_180030DA3
0x180030d9a  movzx   ebx, ax
0x180030d9d  or      ebx, 80070000h
0x180030da3  mov     eax, 80004005h
0x180030da8  test    ebx, ebx
0x180030daa  cmovns  ebx, eax
0x180030dad  jmp     loc_180031096
0x180030db2  mov     rcx, r15; hEvent
0x180030db5  test    sil, 4
0x180030db9  jz      short loc_180030DC6
0x180030dbb  call    cs:__imp_SetEvent
0x180030dc1  jmp     loc_180031084
0x180030dc6  call    cs:__imp_ResetEvent
0x180030dcc  test    r12, r12
0x180030dcf  jz      loc_18003107F
0x180030dd5  test    r13, r13
0x180030dd8  jz      loc_18003107F
0x180030dde  cmp     [rsp+128h+var_F8], rdi
0x180030de3  jz      loc_18003107F
0x180030de9  mov     ecx, 30h ; '0'; Size
0x180030dee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030df3  mov     rsi, rax
0x180030df6  mov     [rsp+128h+var_D8], rax
0x180030dfb  test    rax, rax
0x180030dfe  jz      loc_180031078
0x180030e04  mov     [rax], rdi
0x180030e07  mov     [rax+8], rdi
0x180030e0b  mov     [rax+10h], edi
0x180030e0e  mov     [rax+18h], rdi
0x180030e12  mov     [rax+20h], rdi
0x180030e16  mov     [rax+28h], rdi
0x180030e1a  test    rax, rax
0x180030e1d  jz      loc_180031078
0x180030e23  mov     [rax+18h], r12
0x180030e27  mov     rax, [rsp+128h+var_F0]
0x180030e2c  mov     [rsi+20h], rax
0x180030e30  mov     [rsi+10h], r14d
0x180030e34  lea     r14, [rsi+28h]
0x180030e38  mov     [rsp+128h+var_D0], r14
0x180030e3d  mov     [r14], r15
0x180030e40  mov     r15, rdi
0x180030e43  mov     r12d, 7FFFFFFFh
0x180030e49  mov     edx, r12d
0x180030e4c  mov     rax, r13
0x180030e4f  mov     [rsp+128h+var_D8], rsi
0x180030e54  cmp     [rax], di
0x180030e57  jz      short loc_180030E63
0x180030e59  add     rax, 2
0x180030e5d  sub     rdx, 1
0x180030e61  jnz     short loc_180030E54
0x180030e63  mov     rax, rdx
0x180030e66  neg     rax
0x180030e69  sbb     ebx, ebx
0x180030e6b  not     ebx
0x180030e6d  mov     r13d, 80070057h
0x180030e73  and     ebx, r13d
0x180030e76  mov     rax, rdx
0x180030e79  mov     rcx, r12
0x180030e7c  sub     rcx, rdx
0x180030e7f  neg     rax
0x180030e82  sbb     r8, r8
0x180030e85  and     r8, rcx
0x180030e88  test    rdx, rdx
0x180030e8b  jnz     short loc_180030E92
0x180030e8d  jmp     loc_18003104A
0x180030e92  lea     rbx, [r8+1]
0x180030e96  cmp     rbx, r8
0x180030e99  jb      loc_1800310E3
0x180030e9f  mov     rcx, rbx
0x180030ea2  shr     rcx, 20h
0x180030ea6  mov     rax, rcx
0x180030ea9  shr     rax, 1Fh
0x180030ead  test    eax, eax
0x180030eaf  jnz     loc_1800310E9
0x180030eb5  mov     eax, ebx
0x180030eb7  add     rax, rax
0x180030eba  shl     rcx, 21h
0x180030ebe  lea     rdx, [rcx+rax]
0x180030ec2  cmp     rdx, rax
0x180030ec5  jb      loc_1800310EE
0x180030ecb  test    rdx, rdx
0x180030ece  jz      short loc_180030F18
0x180030ed0  mov     eax, 2
0x180030ed5  mul     rbx
0x180030ed8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180030edf  cmovb   rax, rcx
0x180030ee3  mov     rcx, rax; Size
0x180030ee6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030eeb  mov     [rsi], rax
0x180030eee  test    rax, rax
0x180030ef1  jnz     short loc_180030EFD
0x180030ef3  mov     ebx, 8007000Eh
0x180030ef8  jmp     loc_18003104A
0x180030efd  mov     r8, [rsp+128h+var_B8]; unsigned __int16 *
0x180030f02  mov     rdx, rbx; unsigned __int64
0x180030f05  mov     rcx, rax; unsigned __int16 *
0x180030f08  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030f0d  mov     ebx, eax
0x180030f0f  test    eax, eax
0x180030f11  jns     short loc_180030F21
0x180030f13  jmp     loc_18003104A
0x180030f18  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180030f1f  jmp     short loc_180030F25
0x180030f21  or      r8, 0FFFFFFFFFFFFFFFFh
0x180030f25  mov     rcx, r12
0x180030f28  mov     rax, [rsp+128h+var_F8]
0x180030f2d  cmp     [rax], di
0x180030f30  jz      short loc_180030F3C
0x180030f32  add     rax, 2
0x180030f36  sub     rcx, 1
0x180030f3a  jnz     short loc_180030F2D
0x180030f3c  mov     rax, rcx
0x180030f3f  neg     rax
0x180030f42  sbb     ebx, ebx
0x180030f44  not     ebx
0x180030f46  and     ebx, r13d
0x180030f49  mov     rax, rcx
0x180030f4c  sub     r12, rcx
0x180030f4f  neg     rax
0x180030f52  sbb     rdx, rdx
0x180030f55  and     rdx, r12
0x180030f58  test    rcx, rcx
0x180030f5b  jnz     short loc_180030F62
0x180030f5d  jmp     loc_18003104A
0x180030f62  lea     r12, [rdx+1]
0x180030f66  cmp     r12, rdx
0x180030f69  jb      loc_1800310F4
0x180030f6f  mov     rcx, r12
0x180030f72  shr     rcx, 20h
0x180030f76  mov     rax, rcx
0x180030f79  shr     rax, 1Fh
0x180030f7d  test    eax, eax
0x180030f7f  jnz     loc_1800310F9
0x180030f85  mov     eax, r12d
0x180030f88  add     rax, rax
0x180030f8b  shl     rcx, 21h
0x180030f8f  lea     rdx, [rcx+rax]
0x180030f93  cmp     rdx, rax
0x180030f96  jb      loc_1800310FE
0x180030f9c  test    rdx, rdx
0x180030f9f  jz      short loc_180030FE0
0x180030fa1  mov     eax, 2
0x180030fa6  mul     r12
0x180030fa9  cmovb   rax, r8
0x180030fad  mov     rcx, rax; Size
0x180030fb0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030fb5  mov     [rsi+8], rax
0x180030fb9  test    rax, rax
0x180030fbc  jnz     short loc_180030FC8
0x180030fbe  mov     ebx, 8007000Eh
0x180030fc3  jmp     loc_18003104A
0x180030fc8  mov     r8, [rsp+128h+var_F8]; unsigned __int16 *
0x180030fcd  mov     rdx, r12; unsigned __int64
0x180030fd0  mov     rcx, rax; unsigned __int16 *
0x180030fd3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180030fd8  mov     ebx, eax
0x180030fda  test    eax, eax
0x180030fdc  jns     short loc_180030FE0
0x180030fde  jmp     short loc_18003104A
0x180030fe0  lea     rax, [rsp+128h+var_E8]
0x180030fe5  mov     [rsp+128h+ThrdAddr], rax; ThrdAddr
0x180030fea  mov     [rsp+128h+InitFlag], edi; InitFlag
0x180030fee  mov     r9, rsi; ArgList
0x180030ff1  lea     r8, ?SignRightsDataProc@@YAIPEAX@Z; StartAddress
0x180030ff8  xor     edx, edx; StackSize
0x180030ffa  xor     ecx, ecx; Security
0x180030ffc  call    cs:__imp__beginthreadex
0x180031002  test    rax, rax
0x180031005  jnz     short loc_180031028
0x180031007  call    cs:__imp_GetLastError
0x18003100d  mov     ebx, eax
0x18003100f  test    eax, eax
0x180031011  jle     short loc_18003101C
0x180031013  movzx   ebx, ax
0x180031016  or      ebx, 80070000h
0x18003101c  mov     eax, 80004005h
0x180031021  test    ebx, ebx
0x180031023  cmovns  ebx, eax
0x180031026  jmp     short loc_18003104A
0x180031028  mov     rcx, rax
0x18003102b  jmp     short loc_180031087
0x18003102d  mov     rax, [rsp+128h+var_C0]
0x180031032  xor     edi, edi
0x180031034  mov     [rsp+128h+var_E0], rax
0x180031039  mov     rsi, [rsp+128h+var_D8]
0x18003103e  mov     r15d, edi
0x180031041  mov     ebx, dword ptr [rsp+128h+var_F8]
0x180031045  mov     r14, [rsp+128h+var_D0]
0x18003104a  cmp     [r14], rdi
0x18003104d  jz      short loc_180031058
0x18003104f  mov     rcx, [r14]; hObject
0x180031052  call    cs:__imp_CloseHandle
0x180031058  mov     rcx, [rsi]; Block
0x18003105b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031060  mov     rcx, [rsi+8]; Block
0x180031064  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031069  mov     rcx, rsi; Block
0x18003106c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180031071  test    r15, r15
0x180031074  jz      short loc_18003108D
0x180031076  jmp     short loc_180031084
0x180031078  mov     ebx, 8007000Eh
0x18003107d  jmp     short loc_180031084
0x18003107f  mov     ebx, 80070057h
0x180031084  mov     rcx, r15; hObject
0x180031087  call    cs:__imp_CloseHandle
0x18003108d  test    ebx, ebx
0x18003108f  jns     short loc_1800310B4
0x180031091  mov     r12, [rsp+128h+var_E0]
0x180031096  mov     r15, [rsp+128h+var_F0]
0x18003109b  test    r12, r12
0x18003109e  jz      short loc_1800310B4
0x1800310a0  mov     r9, r15
0x1800310a3  xor     r8d, r8d
0x1800310a6  mov     edx, ebx
0x1800310a8  lea     ecx, [r8+4]
0x1800310ac  mov     rax, r12
0x1800310af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310b4  mov     eax, ebx
0x1800310b6  mov     rcx, [rsp+128h+var_38]
0x1800310be  xor     rcx, rsp; StackCookie
0x1800310c1  call    __security_check_cookie
0x1800310c6  lea     r11, [rsp+128h+var_28]
0x1800310ce  mov     rbx, [r11+38h]
0x1800310d2  mov     rsi, [r11+48h]
0x1800310d6  mov     rsp, r11
0x1800310d9  pop     r15
0x1800310db  pop     r14
0x1800310dd  pop     r13
0x1800310df  pop     r12
0x1800310e1  pop     rdi
0x1800310e2  retn
0x1800310e3  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800310e9  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800310ee  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800310f4  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800310f9  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800310fe  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
