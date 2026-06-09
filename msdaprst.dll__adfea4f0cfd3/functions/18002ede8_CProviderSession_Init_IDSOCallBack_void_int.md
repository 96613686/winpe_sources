# CProviderSession::Init(IDSOCallBack *,void *,int)

- ea: `0x18002ede8`
- end: `0x18002ef79`
- name: `?Init@CProviderSession@@QEAAJPEAUIDSOCallBack@@PEAXH@Z`
- size: `401`
- prototype: `__int64 __fastcall(CProviderSession *__hidden this, struct IDSOCallBack *, void *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800143a0`

## callees

- `0x18001b008`
- `0x18002dca4`
- `0x18002e770`
- `0x18002ede8`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002ee2e`
- `KERNEL32!GetCurrentThreadId` at `0x18002ee2e`
- `KERNEL32!LeaveCriticalSection` at `0x18002ef0a`
- `KERNEL32!LeaveCriticalSection` at `0x18002ef5a`
- `KERNEL32!LeaveCriticalSection` at `0x18002ef0a`
- `KERNEL32!LeaveCriticalSection` at `0x18002ef5a`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002ee60`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002ee60`
- `MSDART!UMSEnterCSWraper` at `0x18002ee14`
- `MSDART!UMSEnterCSWraper` at `0x18002ee14`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProviderSession::Init(GUID *this, __int64 (***a2)(void), void *a3)
{
  GUID *v6; // rdi
  unsigned __int8 *v7; // rsi
  int v8; // eax
  unsigned int v9; // r8d
  int v10; // ebx
  bool v11; // zf
  __int64 v12; // rcx
  unsigned int v14; // ebx
  __int64 v15; // rcx
  int v16; // [rsp+30h] [rbp-58h] BYREF
  GUID *v17; // [rsp+38h] [rbp-50h]
  unsigned __int8 *v18; // [rsp+40h] [rbp-48h]
  GUID *v19; // [rsp+48h] [rbp-40h]
  GUID *v20; // [rsp+90h] [rbp+8h]
  int v21; // [rsp+A8h] [rbp+20h]

  v6 = this + 3;
  v20 = this + 3;
  UMSEnterCSWraper(&this[3]);
  v7 = &v6->Data4[4];
  v18 = &v6->Data4[4];
  if ( !*(_DWORD *)&v6->Data4[4] )
    *(_DWORD *)v6->Data4 = GetCurrentThreadId();
  ++*(_DWORD *)v7;
  v17 = v6 + 1;
  ++v6[1].Data1;
  v19 = v6;
  SetErrorInfo(0, 0);
  this[6] = IID_IDSOCallBack;
  *(_DWORD *)&this[263].Data2 = 0;
  try
  {
    v8 = (**a2)();
    v10 = v8;
    if ( v8 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180049EF8 )
          bidTraceW(off_180049230[0], 61440, off_180049EF8, (unsigned int)v8, 60);
      }
      ThrowHR(v10);
    }
    *(_QWORD *)this[282].Data4 = a3;
    this[283].Data1 = 8;
  }
  catch ( long v16 )
  {
    v21 = v16;
    goto LABEL_13;
  }
  catch ( ... )
  {
    v21 = -2147467259;
LABEL_13:
    v14 = CError::PostErrorIfNone((CError *)&this[5], v21, v9);
    --v17->Data1;
    v11 = (*(_DWORD *)v18)-- == 1;
    if ( v11 )
      *(_DWORD *)v20->Data4 = -1;
    v15 = *(_QWORD *)&v20->Data1;
    --*(_DWORD *)(v15 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 8));
    return v14;
  }
  --v6[1].Data1;
  v11 = (*(_DWORD *)v7)-- == 1;
  if ( v11 )
    *(_DWORD *)v6->Data4 = -1;
  v12 = *(_QWORD *)&v6->Data1;
  --*(_DWORD *)(v12 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 8));
  return 0;
}

```

## disassembly

```asm
0x18002ede8  mov     [rsp+arg_18], r9d
0x18002eded  push    rbx
0x18002edee  push    rsi
0x18002edef  push    rdi
0x18002edf0  push    r12
0x18002edf2  push    r13
0x18002edf4  push    r14
0x18002edf6  push    r15
0x18002edf8  sub     rsp, 50h
0x18002edfc  mov     r12, r8
0x18002edff  mov     r13, rdx
0x18002ee02  mov     r15, rcx
0x18002ee05  lea     rdi, [rcx+30h]
0x18002ee09  mov     [rsp+88h+arg_0], rdi
0x18002ee11  mov     rcx, rdi
0x18002ee14  call    cs:__imp_UMSEnterCSWraper
0x18002ee1b  nop     dword ptr [rax+rax+00h]
0x18002ee20  lea     rsi, [rdi+0Ch]
0x18002ee24  mov     [rsp+88h+var_48], rsi
0x18002ee29  cmp     dword ptr [rsi], 0
0x18002ee2c  jnz     short loc_18002EE3D
0x18002ee2e  call    cs:__imp_GetCurrentThreadId
0x18002ee35  nop     dword ptr [rax+rax+00h]
0x18002ee3a  mov     [rdi+8], eax
0x18002ee3d  inc     dword ptr [rsi]
0x18002ee3f  lea     r14, [rdi+10h]
0x18002ee43  mov     [rsp+88h+var_50], r14
0x18002ee48  inc     dword ptr [r14]
0x18002ee4b  mov     [rsp+88h+var_40], rdi
0x18002ee50  lea     rbx, [r15+50h]
0x18002ee54  mov     [rsp+88h+arg_8], rbx
0x18002ee5c  xor     edx, edx; perrinfo
0x18002ee5e  xor     ecx, ecx; dwReserved
0x18002ee60  call    cs:__imp_SetErrorInfo
0x18002ee67  nop     dword ptr [rax+rax+00h]
0x18002ee6c  movups  xmm0, xmmword ptr cs:?IID_IDSOCallBack@@3U_GUID@@B.Data1; _GUID const IID_IDSOCallBack ...
0x18002ee73  movdqu  xmmword ptr [rbx+10h], xmm0
0x18002ee78  mov     dword ptr [rbx+1024h], 0
0x18002ee82  mov     rax, [r13+0]
0x18002ee86  lea     r8, [r15+48h]
0x18002ee8a  lea     rdx, ?IID_IDSOCallBack@@3U_GUID@@B; _GUID const IID_IDSOCallBack
0x18002ee91  mov     rcx, r13
0x18002ee94  mov     rax, [rax]
0x18002ee97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ee9c  mov     ebx, eax
0x18002ee9e  test    eax, eax
0x18002eea0  jns     short loc_18002EEE1
0x18002eea2  test    byte ptr cs:_bidGblFlags, 2
0x18002eea9  jz      short loc_18002EEDA
0x18002eeab  mov     rcx, cs:off_180049EF8; "<CProviderSession::Init|ADO|ERR>  HRESU"...
0x18002eeb2  test    rcx, rcx
0x18002eeb5  jz      short loc_18002EEDA
0x18002eeb7  mov     [rsp+88h+var_68], 3Ch ; '<'
0x18002eebf  mov     r9d, eax
0x18002eec2  mov     r8, cs:off_180049EF8; "<CProviderSession::Init|ADO|ERR>  HRESU"...
0x18002eec9  mov     edx, 0F000h
0x18002eece  mov     rcx, cs:off_180049230; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002eed5  call    _bidTraceW
0x18002eeda  mov     ecx, ebx; int
0x18002eedc  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002eee1  mov     [r15+11A8h], r12
0x18002eee8  mov     dword ptr [r15+11B0h], 8
0x18002eef3  or      edx, 0FFFFFFFFh
0x18002eef6  add     [r14], edx
0x18002eef9  add     [rsi], edx
0x18002eefb  jnz     short loc_18002EF00
0x18002eefd  mov     [rdi+8], edx
0x18002ef00  mov     rcx, [rdi]
0x18002ef03  dec     dword ptr [rcx+30h]
0x18002ef06  add     rcx, 8; lpCriticalSection
0x18002ef0a  call    cs:__imp_LeaveCriticalSection
0x18002ef11  nop     dword ptr [rax+rax+00h]
0x18002ef16  xor     eax, eax
0x18002ef18  jmp     short loc_18002EF68
0x18002ef1a  jmp     short $+2
0x18002ef1c  mov     edx, [rsp+88h+arg_18]; int
0x18002ef23  mov     rcx, [rsp+88h+arg_8]; this
0x18002ef2b  call    ?PostErrorIfNone@CError@@QEAAJJK@Z; CError::PostErrorIfNone(long,ulong)
0x18002ef30  mov     ebx, eax
0x18002ef32  or      edx, 0FFFFFFFFh
0x18002ef35  mov     rcx, [rsp+88h+var_50]
0x18002ef3a  add     [rcx], edx
0x18002ef3c  mov     rcx, [rsp+88h+var_48]
0x18002ef41  add     [rcx], edx
0x18002ef43  mov     rcx, [rsp+88h+arg_0]
0x18002ef4b  jnz     short loc_18002EF50
0x18002ef4d  mov     [rcx+8], edx
0x18002ef50  mov     rcx, [rcx]
0x18002ef53  dec     dword ptr [rcx+30h]
0x18002ef56  add     rcx, 8; lpCriticalSection
0x18002ef5a  call    cs:__imp_LeaveCriticalSection
0x18002ef61  nop     dword ptr [rax+rax+00h]
0x18002ef66  mov     eax, ebx
0x18002ef68  add     rsp, 50h
0x18002ef6c  pop     r15
0x18002ef6e  pop     r14
0x18002ef70  pop     r13
0x18002ef72  pop     r12
0x18002ef74  pop     rdi
0x18002ef75  pop     rsi
0x18002ef76  pop     rbx
0x18002ef77  retn
```
