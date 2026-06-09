# CProviderDSO::Initialize(void)

- ea: `0x18002df30`
- end: `0x18002e09b`
- name: `?Initialize@CProviderDSO@@UEAAJXZ`
- size: `363`
- prototype: `__int64 __fastcall(CProviderDSO *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001b008`
- `0x18002dca4`
- `0x18002df30`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002df6a`
- `KERNEL32!GetCurrentThreadId` at `0x18002df6a`
- `KERNEL32!LeaveCriticalSection` at `0x18002e040`
- `KERNEL32!LeaveCriticalSection` at `0x18002e07d`
- `KERNEL32!LeaveCriticalSection` at `0x18002e040`
- `KERNEL32!LeaveCriticalSection` at `0x18002e07d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002df92`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002df92`
- `MSDART!UMSEnterCSWraper` at `0x18002df50`
- `MSDART!UMSEnterCSWraper` at `0x18002df50`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProviderDSO::Initialize(CProviderDSO *this)
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
  if ( *((_DWORD *)this + 20) )
  {
    if ( (bidGblFlags & 2) != 0 && off_180049EE8[0] )
      bidTraceW(off_180049228[0], 126976, off_180049EE8[0], 2147749458LL, 124);
    try
    {
      ThrowHR(-2147217838);
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
  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 2) + 40LL))((char *)this - 16);
  (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this - 2) + 32LL))((char *)this - 16, 1);
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
0x18002df30  mov     [rsp+arg_0], rcx
0x18002df35  push    rbx
0x18002df36  push    rsi
0x18002df37  push    rdi
0x18002df38  push    r14
0x18002df3a  sub     rsp, 58h
0x18002df3e  mov     r14, rcx
0x18002df41  lea     rbx, [rcx+38h]
0x18002df45  mov     [rsp+78h+arg_10], rbx
0x18002df4d  mov     rcx, rbx
0x18002df50  call    cs:__imp_UMSEnterCSWraper
0x18002df57  nop     dword ptr [rax+rax+00h]
0x18002df5c  lea     rdi, [rbx+0Ch]
0x18002df60  mov     [rsp+78h+var_40], rdi
0x18002df65  cmp     dword ptr [rdi], 0
0x18002df68  jnz     short loc_18002DF79
0x18002df6a  call    cs:__imp_GetCurrentThreadId
0x18002df71  nop     dword ptr [rax+rax+00h]
0x18002df76  mov     [rbx+8], eax
0x18002df79  inc     dword ptr [rdi]
0x18002df7b  lea     rsi, [rbx+10h]
0x18002df7f  mov     [rsp+78h+arg_18], rsi
0x18002df87  inc     dword ptr [rsi]
0x18002df89  mov     [rsp+78h+var_38], rbx
0x18002df8e  xor     edx, edx; perrinfo
0x18002df90  xor     ecx, ecx; dwReserved
0x18002df92  call    cs:__imp_SetErrorInfo
0x18002df99  nop     dword ptr [rax+rax+00h]
0x18002df9e  movups  xmm0, xmmword ptr cs:IID_IDBInitialize.Data1
0x18002dfa5  movdqu  xmmword ptr [r14+68h], xmm0
0x18002dfab  mov     dword ptr [r14+107Ch], 0
0x18002dfb6  cmp     dword ptr [r14+50h], 0
0x18002dfbb  jz      short loc_18002E002
0x18002dfbd  test    byte ptr cs:_bidGblFlags, 2
0x18002dfc4  jz      short loc_18002DFF8
0x18002dfc6  mov     rax, cs:off_180049EE8; "<CProviderDSO::Initialize|ADO|ERR>  HRE"...
0x18002dfcd  test    rax, rax
0x18002dfd0  jz      short loc_18002DFF8
0x18002dfd2  mov     [rsp+78h+var_58], 7Ch ; '|'
0x18002dfda  mov     r9d, 80040E52h
0x18002dfe0  mov     r8, cs:off_180049EE8; "<CProviderDSO::Initialize|ADO|ERR>  HRE"...
0x18002dfe7  mov     edx, 1F000h
0x18002dfec  mov     rcx, cs:off_180049228; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002dff3  call    _bidTraceW
0x18002dff8  mov     ecx, 80040E52h; int
0x18002dffd  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002e002  mov     rax, [r14-10h]
0x18002e006  lea     rcx, [r14-10h]
0x18002e00a  mov     rax, [rax+28h]
0x18002e00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e013  mov     rax, [r14-10h]
0x18002e017  mov     edx, 1
0x18002e01c  lea     rcx, [r14-10h]
0x18002e020  mov     rax, [rax+20h]
0x18002e024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e029  nop
0x18002e02a  or      ecx, 0FFFFFFFFh
0x18002e02d  add     [rsi], ecx
0x18002e02f  add     [rdi], ecx
0x18002e031  jnz     short loc_18002E036
0x18002e033  mov     [rbx+8], ecx
0x18002e036  mov     rcx, [rbx]
0x18002e039  dec     dword ptr [rcx+30h]
0x18002e03c  add     rcx, 8; lpCriticalSection
0x18002e040  call    cs:__imp_LeaveCriticalSection
0x18002e047  nop     dword ptr [rax+rax+00h]
0x18002e04c  xor     eax, eax
0x18002e04e  jmp     short loc_18002E090
0x18002e050  jmp     short $+2
0x18002e052  mov     rax, [rsp+78h+arg_18]
0x18002e05a  or      ecx, 0FFFFFFFFh
0x18002e05d  add     [rax], ecx
0x18002e05f  mov     rax, [rsp+78h+var_40]
0x18002e064  add     [rax], ecx
0x18002e066  mov     rax, [rsp+78h+arg_10]
0x18002e06e  jnz     short loc_18002E073
0x18002e070  mov     [rax+8], ecx
0x18002e073  mov     rcx, [rax]
0x18002e076  dec     dword ptr [rcx+30h]
0x18002e079  add     rcx, 8; lpCriticalSection
0x18002e07d  call    cs:__imp_LeaveCriticalSection
0x18002e084  nop     dword ptr [rax+rax+00h]
0x18002e089  mov     eax, dword ptr [rsp+78h+arg_0]
0x18002e090  add     rsp, 58h
0x18002e094  pop     r14
0x18002e096  pop     rdi
0x18002e097  pop     rsi
0x18002e098  pop     rbx
0x18002e099  retn
```
