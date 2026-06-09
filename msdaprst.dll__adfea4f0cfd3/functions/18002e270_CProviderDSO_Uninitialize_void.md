# CProviderDSO::Uninitialize(void)

- ea: `0x18002e270`
- end: `0x18002e3d8`
- name: `?Uninitialize@CProviderDSO@@UEAAJXZ`
- size: `360`
- prototype: `__int64 __fastcall(CProviderDSO *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001b008`
- `0x18002dca4`
- `0x18002e270`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002e2aa`
- `KERNEL32!GetCurrentThreadId` at `0x18002e2aa`
- `KERNEL32!LeaveCriticalSection` at `0x18002e37d`
- `KERNEL32!LeaveCriticalSection` at `0x18002e3ba`
- `KERNEL32!LeaveCriticalSection` at `0x18002e37d`
- `KERNEL32!LeaveCriticalSection` at `0x18002e3ba`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002e2d2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002e2d2`
- `MSDART!UMSEnterCSWraper` at `0x18002e290`
- `MSDART!UMSEnterCSWraper` at `0x18002e290`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProviderDSO::Uninitialize(CProviderDSO *this)
{
  char *v2; // rbx
  _DWORD *v3; // rdi
  bool v4; // zf
  __int64 v5; // rcx
  int v7; // ecx
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  _BYTE *v12; // rdx
  _BYTE *v13; // rdx
  _BYTE v14[32]; // [rsp+0h] [rbp-78h] BYREF
  __int64 v15; // [rsp+30h] [rbp-48h] BYREF
  _DWORD *v16; // [rsp+38h] [rbp-40h]
  char *v17; // [rsp+40h] [rbp-38h]
  __int64 v18; // [rsp+80h] [rbp+8h]
  __int64 v19; // [rsp+90h] [rbp+18h]
  _DWORD *v20; // [rsp+98h] [rbp+20h]

  v2 = (char *)this + 56;
  UMSEnterCSWraper((char *)this + 56);
  v3 = v2 + 12;
  v16 = v2 + 12;
  if ( !*((_DWORD *)v2 + 3) )
    *((_DWORD *)v2 + 2) = GetCurrentThreadId();
  ++*v3;
  ++*((_DWORD *)v2 + 4);
  v17 = v2;
  SetErrorInfo(0, 0);
  *(GUID *)((char *)this + 104) = IID_IDBInitialize;
  *((_DWORD *)this + 1055) = 0;
  if ( *((_DWORD *)this + 12) )
  {
    if ( (bidGblFlags & 2) != 0 && off_180049EF0[0] )
      bidTraceW(off_180049228[0], 159744, off_180049EF0[0], 2147749381LL, 156);
    try
    {
      ThrowHR(-2147217915);
    }
    catch ( long v15 )
    {
      v12 = v14;
      *((_DWORD *)v12 + 32) = CError::PostErrorIfNone(
                                (CError *)(*((_QWORD *)v12 + 16) + 88LL),
                                *((_DWORD *)v12 + 12),
                                v10);
      goto LABEL_10;
    }
    catch ( ... )
    {
      v13 = v14;
      *((_DWORD *)v13 + 32) = CError::PostErrorIfNone((CError *)(*((_QWORD *)v13 + 16) + 88LL), -2147467259, v11);
LABEL_10:
      v7 = -1;
      --*v20;
      v4 = (*v16)-- == 1;
      v8 = v19;
      if ( v4 )
        *(_DWORD *)(v8 + 8) = v7;
      v9 = *(_QWORD *)v8;
      --*(_DWORD *)(v9 + 48);
      LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 8));
      return (unsigned int)v18;
    }
  }
  (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)this - 2) + 32LL))((char *)this - 16, 0);
  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 2) + 48LL))((char *)this - 16);
  --*((_DWORD *)v2 + 4);
  v4 = (*v3)-- == 1;
  if ( v4 )
    *((_DWORD *)v2 + 2) = -1;
  v5 = *(_QWORD *)v2;
  --*(_DWORD *)(v5 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 8));
  return 0;
}

```

## disassembly

```asm
0x18002e270  mov     [rsp+arg_0], rcx
0x18002e275  push    rbx
0x18002e276  push    rsi
0x18002e277  push    rdi
0x18002e278  push    r14
0x18002e27a  sub     rsp, 58h
0x18002e27e  mov     r14, rcx
0x18002e281  lea     rbx, [rcx+38h]
0x18002e285  mov     [rsp+78h+arg_10], rbx
0x18002e28d  mov     rcx, rbx
0x18002e290  call    cs:__imp_UMSEnterCSWraper
0x18002e297  nop     dword ptr [rax+rax+00h]
0x18002e29c  lea     rdi, [rbx+0Ch]
0x18002e2a0  mov     [rsp+78h+var_40], rdi
0x18002e2a5  cmp     dword ptr [rdi], 0
0x18002e2a8  jnz     short loc_18002E2B9
0x18002e2aa  call    cs:__imp_GetCurrentThreadId
0x18002e2b1  nop     dword ptr [rax+rax+00h]
0x18002e2b6  mov     [rbx+8], eax
0x18002e2b9  inc     dword ptr [rdi]
0x18002e2bb  lea     rsi, [rbx+10h]
0x18002e2bf  mov     [rsp+78h+arg_18], rsi
0x18002e2c7  inc     dword ptr [rsi]
0x18002e2c9  mov     [rsp+78h+var_38], rbx
0x18002e2ce  xor     edx, edx; perrinfo
0x18002e2d0  xor     ecx, ecx; dwReserved
0x18002e2d2  call    cs:__imp_SetErrorInfo
0x18002e2d9  nop     dword ptr [rax+rax+00h]
0x18002e2de  movups  xmm0, xmmword ptr cs:IID_IDBInitialize.Data1
0x18002e2e5  movdqu  xmmword ptr [r14+68h], xmm0
0x18002e2eb  mov     dword ptr [r14+107Ch], 0
0x18002e2f6  cmp     dword ptr [r14+30h], 0
0x18002e2fb  jbe     short loc_18002E342
0x18002e2fd  test    byte ptr cs:_bidGblFlags, 2
0x18002e304  jz      short loc_18002E338
0x18002e306  mov     rax, cs:off_180049EF0; "<CProviderDSO::Uninitialize|ADO|ERR>  H"...
0x18002e30d  test    rax, rax
0x18002e310  jz      short loc_18002E338
0x18002e312  mov     [rsp+78h+var_58], 9Ch
0x18002e31a  mov     r9d, 80040E05h
0x18002e320  mov     r8, cs:off_180049EF0; "<CProviderDSO::Uninitialize|ADO|ERR>  H"...
0x18002e327  mov     edx, 27000h
0x18002e32c  mov     rcx, cs:off_180049228; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002e333  call    _bidTraceW
0x18002e338  mov     ecx, 80040E05h; int
0x18002e33d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002e342  mov     rax, [r14-10h]
0x18002e346  xor     edx, edx
0x18002e348  lea     rcx, [r14-10h]
0x18002e34c  mov     rax, [rax+20h]
0x18002e350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e355  mov     rax, [r14-10h]
0x18002e359  lea     rcx, [r14-10h]
0x18002e35d  mov     rax, [rax+30h]
0x18002e361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e366  nop
0x18002e367  or      ecx, 0FFFFFFFFh
0x18002e36a  add     [rsi], ecx
0x18002e36c  add     [rdi], ecx
0x18002e36e  jnz     short loc_18002E373
0x18002e370  mov     [rbx+8], ecx
0x18002e373  mov     rcx, [rbx]
0x18002e376  dec     dword ptr [rcx+30h]
0x18002e379  add     rcx, 8; lpCriticalSection
0x18002e37d  call    cs:__imp_LeaveCriticalSection
0x18002e384  nop     dword ptr [rax+rax+00h]
0x18002e389  xor     eax, eax
0x18002e38b  jmp     short loc_18002E3CD
0x18002e38d  jmp     short $+2
0x18002e38f  mov     rax, [rsp+78h+arg_18]
0x18002e397  or      ecx, 0FFFFFFFFh
0x18002e39a  add     [rax], ecx
0x18002e39c  mov     rax, [rsp+78h+var_40]
0x18002e3a1  add     [rax], ecx
0x18002e3a3  mov     rax, [rsp+78h+arg_10]
0x18002e3ab  jnz     short loc_18002E3B0
0x18002e3ad  mov     [rax+8], ecx
0x18002e3b0  mov     rcx, [rax]
0x18002e3b3  dec     dword ptr [rcx+30h]
0x18002e3b6  add     rcx, 8; lpCriticalSection
0x18002e3ba  call    cs:__imp_LeaveCriticalSection
0x18002e3c1  nop     dword ptr [rax+rax+00h]
0x18002e3c6  mov     eax, dword ptr [rsp+78h+arg_0]
0x18002e3cd  add     rsp, 58h
0x18002e3d1  pop     r14
0x18002e3d3  pop     rdi
0x18002e3d4  pop     rsi
0x18002e3d5  pop     rbx
0x18002e3d6  retn
```
