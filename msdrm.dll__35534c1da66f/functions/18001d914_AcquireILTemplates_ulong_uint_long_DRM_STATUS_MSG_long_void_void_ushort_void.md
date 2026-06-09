# AcquireILTemplates(ulong,uint,long (*)(_DRM_STATUS_MSG,long,void *,void *),ushort *,void *)

- ea: `0x18001d914`
- end: `0x18001dc23`
- name: `?AcquireILTemplates@@YAJKIP6AJW4_DRM_STATUS_MSG@@JPEAX1@ZPEAG1@Z`
- size: `783`
- prototype: `int(unsigned int, unsigned int, int (*)(enum _DRM_STATUS_MSG, int, void *, void *), unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18001e3e0`

## callees

- `0x180001244`
- `0x180001284`
- `0x180004654`
- `0x180015438`
- `0x180019e28`
- `0x18001a1fc`
- `0x18001d914`
- `0x1800385a0`
- `0x18005f010`

## import_xrefs

- `msvcrt!_beginthreadex` at `0x18001db3e`
- `msvcrt!_beginthreadex` at `0x18001db3e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d9b7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d9b7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d9c2`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d9c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d98a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d98a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dba0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dbca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dba0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dbca`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall AcquireILTemplates(
        DRMOS *a1,
        int a2,
        int (*a3)(enum _DRM_STATUS_MSG, int, void *, void *),
        unsigned __int16 *a4,
        void *a5)
{
  int (*v6)(enum _DRM_STATUS_MSG, int, void *, void *); // r14
  signed int ThreadTermEvent; // ebx
  void *v9; // rax
  void *v10; // r15
  signed int LastError; // eax
  void **v12; // rax
  void **v13; // rsi
  unsigned int v14; // r9d
  HANDLE *v15; // r14
  __int64 v16; // rdx
  unsigned __int16 *v17; // rax
  unsigned __int64 v18; // rcx
  signed __int64 v19; // rbx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rcx
  unsigned __int16 *v22; // rax
  void *v23; // rax
  signed int v24; // eax
  unsigned int ThrdAddr; // [rsp+30h] [rbp-58h] BYREF
  void **v27; // [rsp+38h] [rbp-50h]
  char *v28; // [rsp+40h] [rbp-48h]
  void **v29; // [rsp+48h] [rbp-40h]
  __int64 v30; // [rsp+50h] [rbp-38h]
  unsigned int v31; // [rsp+90h] [rbp+8h]

  v31 = (unsigned int)a1;
  v30 = -2;
  v6 = a3;
  ThrdAddr = 0;
  if ( a3 )
  {
    if ( !a4 && (a2 & 4) == 0 )
    {
      ThreadTermEvent = -2147024809;
      goto LABEL_43;
    }
    v9 = DRMOS::OpenEventA(a1, 1u, (int)L"UDRMAILTCancelEvent", a4);
    v10 = v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      ThreadTermEvent = LastError;
      if ( LastError > 0 )
        ThreadTermEvent = (unsigned __int16)LastError | 0x80070000;
      if ( ThreadTermEvent >= 0 )
        ThreadTermEvent = -2147467259;
      goto LABEL_43;
    }
    if ( (a2 & 4) != 0 )
    {
      ThreadTermEvent = 0;
      SetEvent(v9);
LABEL_40:
      CloseHandle(v10);
LABEL_41:
      if ( ThreadTermEvent >= 0 )
        return (unsigned int)ThreadTermEvent;
      v6 = a3;
LABEL_43:
      ((void (__fastcall *)(__int64, _QWORD, _QWORD, void *))v6)(6, (unsigned int)ThreadTermEvent, 0, a5);
      return (unsigned int)ThreadTermEvent;
    }
    ResetEvent(v9);
    v12 = (void **)operator new(0x38u);
    v13 = v12;
    v29 = v12;
    if ( !v12 )
    {
      ThreadTermEvent = -2147024882;
      goto LABEL_40;
    }
    *(_DWORD *)v12 = 0;
    v12[3] = 0;
    v12[4] = 0;
    v12[5] = 0;
    v12[1] = v6;
    v12[2] = a5;
    v14 = v31;
    *(_DWORD *)v12 = v31;
    v15 = v12 + 5;
    v28 = (char *)(v12 + 5);
    v12[5] = v10;
    *((_DWORD *)v12 + 12) = a2;
    v27 = v12;
    if ( !a4 )
    {
      ThreadTermEvent = -2147024809;
      goto LABEL_36;
    }
    v16 = 0x7FFFFFFF;
    v17 = a4;
    do
    {
      if ( !*v17 )
        break;
      ++v17;
      --v16;
    }
    while ( v16 );
    ThreadTermEvent = v16 == 0 ? 0x80070057 : 0;
    v18 = (0x7FFFFFFF - v16) & -(__int64)(v16 != 0);
    if ( !v16 )
      goto LABEL_36;
    v19 = v18 + 1;
    if ( v18 + 1 < v18 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    if ( v19 < 0 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    v20 = 2LL * (unsigned int)v19;
    v21 = HIDWORD(v19) << 33;
    if ( v21 + v20 < v20 )
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    if ( v21 + v20 )
    {
      v22 = (unsigned __int16 *)operator new(saturated_mul(v19, 2u));
      v13[3] = v22;
      if ( !v22 )
      {
        ThreadTermEvent = -2147024882;
LABEL_36:
        if ( *v15 )
          CloseHandle(*v15);
        operator delete(v13[3]);
        v13[3] = 0;
        operator delete(v13);
        goto LABEL_41;
      }
      ThreadTermEvent = StringCchCopyW(v22, v19, a4);
      if ( ThreadTermEvent < 0 )
        goto LABEL_36;
      v14 = v31;
    }
    ThreadTermEvent = GetThreadTermEvent(v14, 3u, v13 + 4);
    if ( ThreadTermEvent >= 0 )
    {
      v23 = (void *)_beginthreadex(0, 0, (_beginthreadex_proc_type)AILTProc, v13, 0, &ThrdAddr);
      if ( v23 )
      {
        SetThreadInfo(v31, 3u, v23);
        return (unsigned int)ThreadTermEvent;
      }
      v24 = GetLastError();
      ThreadTermEvent = v24;
      if ( v24 > 0 )
        ThreadTermEvent = (unsigned __int16)v24 | 0x80070000;
      if ( ThreadTermEvent >= 0 )
        ThreadTermEvent = -2147467259;
    }
    goto LABEL_36;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x18001d914  mov     rax, rsp
0x18001d917  mov     [rax+18h], r8
0x18001d91b  mov     [rax+8], ecx
0x18001d91e  push    rdi
0x18001d91f  push    r12
0x18001d921  push    r13
0x18001d923  push    r14
0x18001d925  push    r15
0x18001d927  sub     rsp, 60h
0x18001d92b  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x18001d933  mov     [rax+10h], rbx
0x18001d937  mov     [rax+20h], rsi
0x18001d93b  mov     r12, r9
0x18001d93e  mov     r14, r8
0x18001d941  mov     r13d, edx
0x18001d944  xor     edi, edi
0x18001d946  mov     [rax-58h], edi
0x18001d949  test    r8, r8
0x18001d94c  jnz     short loc_18001D958
0x18001d94e  mov     ebx, 80070057h
0x18001d953  jmp     loc_18001DBF5
0x18001d958  mov     ebx, r13d
0x18001d95b  and     ebx, 4
0x18001d95e  test    r12, r12
0x18001d961  jnz     short loc_18001D971
0x18001d963  test    ebx, ebx
0x18001d965  jnz     short loc_18001D971
0x18001d967  mov     ebx, 80070057h
0x18001d96c  jmp     loc_18001DBDC
0x18001d971  lea     r8, ?g_wszPUB_AILTCancelEventName@@3QBGB; "UDRMAILTCancelEvent"
0x18001d978  mov     edx, 1; unsigned int
0x18001d97d  call    ?OpenEventA@DRMOS@@YAPEAXKHPEBG@Z; DRMOS::OpenEventA(ulong,int,ushort const *)
0x18001d982  mov     r15, rax
0x18001d985  test    rax, rax
0x18001d988  jnz     short loc_18001D9AE
0x18001d98a  call    cs:__imp_GetLastError
0x18001d990  mov     ebx, eax
0x18001d992  test    eax, eax
0x18001d994  jle     short loc_18001D99F
0x18001d996  movzx   ebx, ax
0x18001d999  or      ebx, 80070000h
0x18001d99f  mov     eax, 80004005h
0x18001d9a4  test    ebx, ebx
0x18001d9a6  cmovns  ebx, eax
0x18001d9a9  jmp     loc_18001DBDC
0x18001d9ae  mov     rcx, r15; hEvent
0x18001d9b1  test    ebx, ebx
0x18001d9b3  jz      short loc_18001D9C2
0x18001d9b5  mov     ebx, edi
0x18001d9b7  call    cs:__imp_SetEvent
0x18001d9bd  jmp     loc_18001DBC7
0x18001d9c2  call    cs:__imp_ResetEvent
0x18001d9c8  mov     ecx, 38h ; '8'; Size
0x18001d9cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d9d2  mov     rsi, rax
0x18001d9d5  mov     [rsp+88h+var_40], rax
0x18001d9da  test    rax, rax
0x18001d9dd  jz      loc_18001DBC2
0x18001d9e3  mov     [rax], edi
0x18001d9e5  mov     [rax+18h], rdi
0x18001d9e9  mov     [rax+20h], rdi
0x18001d9ed  mov     [rax+28h], rdi
0x18001d9f1  test    rax, rax
0x18001d9f4  jz      loc_18001DBC2
0x18001d9fa  mov     [rax+8], r14
0x18001d9fe  mov     rax, [rsp+88h+arg_20]
0x18001da06  mov     [rsi+10h], rax
0x18001da0a  mov     r9d, [rsp+88h+arg_0]
0x18001da12  mov     [rsi], r9d
0x18001da15  lea     r14, [rsi+28h]
0x18001da19  mov     [rsp+88h+var_48], r14
0x18001da1e  mov     [r14], r15
0x18001da21  mov     r15, rdi
0x18001da24  mov     [rsi+30h], r13d
0x18001da28  mov     [rsp+88h+var_50], rsi
0x18001da2d  test    r12, r12
0x18001da30  jz      loc_18001DB7E
0x18001da36  mov     r8d, 7FFFFFFFh
0x18001da3c  mov     edx, r8d
0x18001da3f  mov     rax, r12
0x18001da42  cmp     [rax], di
0x18001da45  jz      short loc_18001DA51
0x18001da47  add     rax, 2
0x18001da4b  sub     rdx, 1
0x18001da4f  jnz     short loc_18001DA42
0x18001da51  mov     rax, rdx
0x18001da54  neg     rax
0x18001da57  sbb     ecx, ecx
0x18001da59  not     ecx
0x18001da5b  mov     ebx, 80070057h
0x18001da60  and     ebx, ecx
0x18001da62  mov     rax, rdx
0x18001da65  sub     r8, rdx
0x18001da68  neg     rax
0x18001da6b  sbb     rcx, rcx
0x18001da6e  and     rcx, r8
0x18001da71  test    rdx, rdx
0x18001da74  jz      loc_18001DB83
0x18001da7a  lea     rbx, [rcx+1]
0x18001da7e  cmp     rbx, rcx
0x18001da81  jb      loc_18001DC11
0x18001da87  mov     rcx, rbx
0x18001da8a  shr     rcx, 20h
0x18001da8e  mov     rax, rcx
0x18001da91  shr     rax, 1Fh
0x18001da95  test    eax, eax
0x18001da97  jnz     loc_18001DC17
0x18001da9d  mov     eax, ebx
0x18001da9f  add     rax, rax
0x18001daa2  shl     rcx, 21h
0x18001daa6  lea     rdx, [rcx+rax]
0x18001daaa  cmp     rdx, rax
0x18001daad  jb      loc_18001DC1C
0x18001dab3  test    rdx, rdx
0x18001dab6  jz      short loc_18001DB07
0x18001dab8  mov     eax, 2
0x18001dabd  mul     rbx
0x18001dac0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001dac7  cmovb   rax, rcx
0x18001dacb  mov     rcx, rax; Size
0x18001dace  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dad3  mov     [rsi+18h], rax
0x18001dad7  test    rax, rax
0x18001dada  jnz     short loc_18001DAE6
0x18001dadc  mov     ebx, 8007000Eh
0x18001dae1  jmp     loc_18001DB98
0x18001dae6  mov     r8, r12; unsigned __int16 *
0x18001dae9  mov     rdx, rbx; unsigned __int64
0x18001daec  mov     rcx, rax; unsigned __int16 *
0x18001daef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001daf4  mov     ebx, eax
0x18001daf6  test    eax, eax
0x18001daf8  jns     short loc_18001DAFF
0x18001dafa  jmp     loc_18001DB98
0x18001daff  mov     r9d, [rsp+88h+arg_0]
0x18001db07  lea     r8, [rsi+20h]; void **
0x18001db0b  mov     r12d, 3
0x18001db11  mov     edx, r12d; unsigned int
0x18001db14  mov     ecx, r9d; unsigned int
0x18001db17  call    ?GetThreadTermEvent@@YAJKIPEAPEAX@Z; GetThreadTermEvent(ulong,uint,void * *)
0x18001db1c  mov     ebx, eax
0x18001db1e  test    eax, eax
0x18001db20  js      short loc_18001DB98
0x18001db22  lea     rax, [rsp+88h+var_58]
0x18001db27  mov     [rsp+88h+ThrdAddr], rax; ThrdAddr
0x18001db2c  mov     [rsp+88h+InitFlag], edi; InitFlag
0x18001db30  mov     r9, rsi; ArgList
0x18001db33  lea     r8, ?AILTProc@@YAIPEAX@Z; StartAddress
0x18001db3a  xor     edx, edx; StackSize
0x18001db3c  xor     ecx, ecx; Security
0x18001db3e  call    cs:__imp__beginthreadex
0x18001db44  test    rax, rax
0x18001db47  jnz     short loc_18001DB6A
0x18001db49  call    cs:__imp_GetLastError
0x18001db4f  mov     ebx, eax
0x18001db51  test    eax, eax
0x18001db53  jle     short loc_18001DB5E
0x18001db55  movzx   ebx, ax
0x18001db58  or      ebx, 80070000h
0x18001db5e  mov     eax, 80004005h
0x18001db63  test    ebx, ebx
0x18001db65  cmovns  ebx, eax
0x18001db68  jmp     short loc_18001DB98
0x18001db6a  mov     r8, rax; void *
0x18001db6d  mov     edx, r12d; unsigned int
0x18001db70  mov     ecx, [rsp+88h+arg_0]; unsigned int
0x18001db77  call    ?SetThreadInfo@@YAJKIPEAX@Z; SetThreadInfo(ulong,uint,void *)
0x18001db7c  jmp     short loc_18001DBF5
0x18001db7e  mov     ebx, 80070057h
0x18001db83  jmp     short loc_18001DB98
0x18001db85  mov     r14, [rsp+88h+var_48]
0x18001db8a  xor     edi, edi
0x18001db8c  mov     ebx, [rsp+88h+var_54]
0x18001db90  mov     r15d, edi
0x18001db93  mov     rsi, [rsp+88h+var_50]
0x18001db98  cmp     [r14], rdi
0x18001db9b  jz      short loc_18001DBA6
0x18001db9d  mov     rcx, [r14]; hObject
0x18001dba0  call    cs:__imp_CloseHandle
0x18001dba6  mov     rcx, [rsi+18h]; Block
0x18001dbaa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dbaf  mov     [rsi+18h], rdi
0x18001dbb3  mov     rcx, rsi; Block
0x18001dbb6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dbbb  test    r15, r15
0x18001dbbe  jz      short loc_18001DBD0
0x18001dbc0  jmp     short loc_18001DBC7
0x18001dbc2  mov     ebx, 8007000Eh
0x18001dbc7  mov     rcx, r15; hObject
0x18001dbca  call    cs:__imp_CloseHandle
0x18001dbd0  test    ebx, ebx
0x18001dbd2  jns     short loc_18001DBF5
0x18001dbd4  mov     r14, [rsp+88h+arg_10]
0x18001dbdc  mov     r9, [rsp+88h+arg_20]
0x18001dbe4  xor     r8d, r8d
0x18001dbe7  mov     edx, ebx
0x18001dbe9  lea     ecx, [r8+6]
0x18001dbed  mov     rax, r14
0x18001dbf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbf5  mov     eax, ebx
0x18001dbf7  lea     r11, [rsp+88h+var_28]
0x18001dbfc  mov     rbx, [r11+38h]
0x18001dc00  mov     rsi, [r11+48h]
0x18001dc04  mov     rsp, r11
0x18001dc07  pop     r15
0x18001dc09  pop     r14
0x18001dc0b  pop     r13
0x18001dc0d  pop     r12
0x18001dc0f  pop     rdi
0x18001dc10  retn
0x18001dc11  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18001dc17  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x18001dc1c  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
