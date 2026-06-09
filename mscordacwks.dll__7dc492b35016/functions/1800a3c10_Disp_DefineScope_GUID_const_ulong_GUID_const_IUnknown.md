# Disp::DefineScope(_GUID const &,ulong,_GUID const &,IUnknown * *)

- ea: `0x1800a3c10`
- end: `0x1800a3f67`
- name: `?DefineScope@Disp@@UEAAJAEBU_GUID@@K0PEAPEAUIUnknown@@@Z`
- size: `855`
- prototype: `__int64 __fastcall(Disp *__hidden this, const struct _GUID *, unsigned int, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18007262c`
- `0x180079d00`
- `0x1800a3c10`
- `0x1800a47d0`
- `0x1800a48f0`
- `0x1800a4aa4`
- `0x1800a4d4c`
- `0x1800a4df0`
- `0x1800f0d20`
- `0x1800f0d40`
- `0x1800f9348`
- `0x180106100`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800a3d95`
- `KERNEL32!HeapFree` at `0x1800a3e9e`
- `KERNEL32!HeapFree` at `0x1800a3d95`
- `KERNEL32!HeapFree` at `0x1800a3e9e`
- `KERNEL32!GetProcessHeap` at `0x1800a3d80`
- `KERNEL32!GetProcessHeap` at `0x1800a3e89`
- `KERNEL32!GetProcessHeap` at `0x1800a3d80`
- `KERNEL32!GetProcessHeap` at `0x1800a3e89`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800a3cf0`
- `KERNEL32!GetEnvironmentVariableW` at `0x1800a3cf0`

## string_xrefs

- `0x1800a3ce9`: `COMP_ENC_OPENSCOPE`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Disp::DefineScope(
        Disp *this,
        const struct _GUID *a2,
        int a3,
        const struct _GUID *a4,
        struct IUnknown **a5)
{
  HRESULT NewMD; // ebx
  const struct NoThrow *v8; // rdx
  void *v9; // rdi
  HANDLE ProcessHeap; // rax
  _BYTE *v11; // rdx
  _BYTE *v12; // rdx
  const char *v13; // r8
  void *v14; // rdi
  HANDLE v15; // rax
  RegMeta *v16; // rax
  RegMeta *v17; // rax
  RegMeta *v18; // rdi
  const struct NoThrow *v19; // rdx
  unsigned int v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+58h] [rbp-A8h]
  _OWORD v25[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v26; // [rsp+A0h] [rbp-60h]
  LPVOID lpMem[3]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v28[520]; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t Destination[5]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR Buffer[259]; // [rsp+2DAh] [rbp+1DAh] BYREF

  v25[0] = *((_OWORD *)this + 1);
  v25[1] = *((_OWORD *)this + 2);
  v25[2] = *((_OWORD *)this + 3);
  v26 = *((_OWORD *)this + 4);
  if ( a3 )
  {
    NewMD = -2147024809;
LABEL_36:
    *a5 = 0;
    return (unsigned int)NewMD;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_CLR_v1_MetaData.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)CLSID_CLR_v1_MetaData.Data4 )
  {
    LODWORD(v26) = 1;
  }
  else
  {
    if ( *(_QWORD *)&a2->Data1 != *(_QWORD *)&CLSID_CLR_v2_MetaData.Data1
      || *(_QWORD *)a2->Data4 != *(_QWORD *)CLSID_CLR_v2_MetaData.Data4 )
    {
      NewMD = -2146234105;
      goto LABEL_36;
    }
    LODWORD(v26) = 2;
  }
  wcscpy_s(Destination, 0x105u, L"file:");
  if ( GetEnvironmentVariableW(L"COMP_ENC_OPENSCOPE", Buffer, 0x100u) )
  {
    (*(void (__fastcall **)(Disp *, wchar_t *, __int64, GUID *, __int64 *))(*(_QWORD *)this + 32LL))(
      this,
      Destination,
      1,
      &IID_IMetaDataEmit,
      &v22);
    lpMem[0] = 0;
    lpMem[1] = 0;
    lpMem[2] = (LPVOID)512;
    (*(void (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v22 + 48LL))(v22, 0, &v21);
    NewMD = CQuickMemoryBase<512,128>::ReSizeNoThrow(lpMem, v21);
    if ( NewMD < 0 )
    {
      v9 = lpMem[0];
      if ( lpMem[0] )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v9);
        lpMem[0] = 0;
      }
      goto LABEL_36;
    }
    v11 = v28;
    if ( lpMem[0] )
      v11 = lpMem[0];
    (*(void (__fastcall **)(__int64, _BYTE *, _QWORD))(*(_QWORD *)v22 + 216LL))(v22, v11, v21);
    v23 = 19;
    v24 = 1;
    (*(void (__fastcall **)(Disp *, __int64 *, __int16 *))(*(_QWORD *)this + 48LL))(this, &MetaDataSetUpdate, &v23);
    v24 = 0;
    (*(void (__fastcall **)(Disp *, __int64 *, __int16 *))(*(_QWORD *)this + 48LL))(
      this,
      &MetaDataErrorIfEmitOutOfOrder,
      &v23);
    v12 = v28;
    if ( lpMem[0] )
      v12 = lpMem[0];
    NewMD = (*(__int64 (__fastcall **)(Disp *, _BYTE *, _QWORD, __int64, const struct _GUID *, struct IUnknown **))(*(_QWORD *)this + 40LL))(
              this,
              v12,
              v21,
              1,
              a4,
              a5);
    v13 = "failed";
    if ( NewMD >= 0 )
      v13 = "succeeded";
    printf("Defining scope for EnC using %S %s\n", Buffer, v13);
    v14 = lpMem[0];
    if ( lpMem[0] )
    {
      v15 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v15 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v15;
      }
      HeapFree(v15, 0, v14);
      lpMem[0] = 0;
    }
    if ( NewMD < 0 )
      goto LABEL_36;
  }
  else
  {
    v16 = (RegMeta *)operator new(0x438u, v8);
    if ( !v16 || (v17 = RegMeta::RegMeta(v16), (v18 = v17) == 0) )
    {
      NewMD = -2147024882;
      goto LABEL_36;
    }
    NewMD = RegMeta::SetOption(v17, (struct OptionValue *)v25);
    if ( NewMD < 0
      || (NewMD = RegMeta::CreateNewMD(v18, v19), NewMD < 0)
      || (NewMD = (**(__int64 (__fastcall ***)(RegMeta *, const struct _GUID *, struct IUnknown **))v18)(v18, a4, a5),
          NewMD < 0) )
    {
      RegMeta::~RegMeta(v18);
      operator delete(v18, 0x438u);
      goto LABEL_36;
    }
    return 0;
  }
  return (unsigned int)NewMD;
}

```

## disassembly

```asm
0x1800a3c10  mov     [rsp-8+arg_8], rbx
0x1800a3c15  push    rbp
0x1800a3c16  push    rsi
0x1800a3c17  push    rdi
0x1800a3c18  push    r14
0x1800a3c1a  push    r15
0x1800a3c1c  lea     rbp, [rsp-3F0h]
0x1800a3c24  sub     rsp, 4F0h
0x1800a3c2b  mov     rax, cs:__security_cookie
0x1800a3c32  xor     rax, rsp
0x1800a3c35  mov     [rbp+410h+var_30], rax
0x1800a3c3c  mov     r15, r9
0x1800a3c3f  mov     rdi, rcx
0x1800a3c42  mov     r14, [rbp+410h+arg_20]
0x1800a3c49  movups  xmm0, xmmword ptr [rcx+10h]
0x1800a3c4d  movaps  [rsp+510h+var_4A0], xmm0
0x1800a3c52  movups  xmm1, xmmword ptr [rcx+20h]
0x1800a3c56  movaps  [rbp+410h+var_490], xmm1
0x1800a3c5a  movups  xmm0, xmmword ptr [rcx+30h]
0x1800a3c5e  movaps  [rbp+410h+var_480], xmm0
0x1800a3c62  movups  xmm1, xmmword ptr [rcx+40h]
0x1800a3c66  movaps  [rbp+410h+var_470], xmm1
0x1800a3c6a  test    r8d, r8d
0x1800a3c6d  jz      short loc_1800A3C79
0x1800a3c6f  mov     ebx, 80070057h
0x1800a3c74  jmp     loc_1800A3F3B
0x1800a3c79  mov     rax, [rdx]
0x1800a3c7c  mov     esi, 1
0x1800a3c81  cmp     rax, qword ptr cs:CLSID_CLR_v1_MetaData.Data1
0x1800a3c88  jnz     short loc_1800A3C9C
0x1800a3c8a  mov     rax, [rdx+8]
0x1800a3c8e  cmp     rax, qword ptr cs:CLSID_CLR_v1_MetaData.Data4
0x1800a3c95  jnz     short loc_1800A3C9C
0x1800a3c97  mov     dword ptr [rbp+410h+var_470], esi
0x1800a3c9a  jmp     short loc_1800A3CC4
0x1800a3c9c  mov     rax, [rdx]
0x1800a3c9f  cmp     rax, qword ptr cs:CLSID_CLR_v2_MetaData.Data1
0x1800a3ca6  jnz     loc_1800A3F36
0x1800a3cac  mov     rax, [rdx+8]
0x1800a3cb0  cmp     rax, qword ptr cs:CLSID_CLR_v2_MetaData.Data4
0x1800a3cb7  jnz     loc_1800A3F36
0x1800a3cbd  mov     dword ptr [rbp+410h+var_470], 2
0x1800a3cc4  lea     r8, aFile_1; "file:"
0x1800a3ccb  mov     edx, 105h; SizeInWords
0x1800a3cd0  lea     rcx, [rbp+410h+Destination]; Destination
0x1800a3cd7  call    wcscpy_s
0x1800a3cdc  mov     r8d, 100h; nSize
0x1800a3ce2  lea     rdx, [rbp+410h+Buffer]; lpBuffer
0x1800a3ce9  lea     rcx, aCompEncOpensco; "COMP_ENC_OPENSCOPE"
0x1800a3cf0  call    cs:__imp_GetEnvironmentVariableW
0x1800a3cf6  test    eax, eax
0x1800a3cf8  jz      loc_1800A3EB6
0x1800a3cfe  mov     rax, [rdi]
0x1800a3d01  lea     rcx, [rsp+510h+var_4C8]
0x1800a3d06  mov     [rsp+510h+var_4F0], rcx
0x1800a3d0b  lea     r9, IID_IMetaDataEmit
0x1800a3d12  mov     r8d, esi
0x1800a3d15  lea     rdx, [rbp+410h+Destination]
0x1800a3d1c  mov     rcx, rdi
0x1800a3d1f  mov     rax, [rax+20h]
0x1800a3d23  call    cs:__guard_dispatch_icall_fptr
0x1800a3d29  and     [rbp+410h+lpMem], 0
0x1800a3d2e  and     [rbp+410h+var_458], 0
0x1800a3d33  mov     [rbp+410h+var_450], 200h
0x1800a3d3b  mov     rcx, [rsp+510h+var_4C8]
0x1800a3d40  mov     rax, [rcx]
0x1800a3d43  lea     r8, [rsp+510h+var_4D0]
0x1800a3d48  xor     edx, edx
0x1800a3d4a  mov     rax, [rax+30h]
0x1800a3d4e  call    cs:__guard_dispatch_icall_fptr
0x1800a3d54  mov     edx, [rsp+510h+var_4D0]
0x1800a3d58  lea     rcx, [rbp+410h+lpMem]
0x1800a3d5c  call    ?ReSizeNoThrow@?$CQuickMemoryBase@$0CAA@$0IA@@@QEAAJ_K@Z; CQuickMemoryBase<512,128>::ReSizeNoThrow(unsigned __int64)
0x1800a3d61  mov     ebx, eax
0x1800a3d63  test    eax, eax
0x1800a3d65  jns     short loc_1800A3DA5
0x1800a3d67  mov     rdi, [rbp+410h+lpMem]
0x1800a3d6b  test    rdi, rdi
0x1800a3d6e  jz      loc_1800A3F3B
0x1800a3d74  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800a3d7b  test    rax, rax
0x1800a3d7e  jnz     short loc_1800A3D8D
0x1800a3d80  call    cs:__imp_GetProcessHeap
0x1800a3d86  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800a3d8d  mov     r8, rdi; lpMem
0x1800a3d90  xor     edx, edx; dwFlags
0x1800a3d92  mov     rcx, rax; hHeap
0x1800a3d95  call    cs:__imp_HeapFree
0x1800a3d9b  and     [rbp+410h+lpMem], 0
0x1800a3da0  jmp     loc_1800A3F3B
0x1800a3da5  lea     rdx, [rbp+410h+var_448]
0x1800a3da9  mov     rax, [rbp+410h+lpMem]
0x1800a3dad  test    rax, rax
0x1800a3db0  cmovnz  rdx, rax
0x1800a3db4  mov     rcx, [rsp+510h+var_4C8]
0x1800a3db9  mov     rax, [rcx]
0x1800a3dbc  mov     r8d, [rsp+510h+var_4D0]
0x1800a3dc1  mov     rax, [rax+0D8h]
0x1800a3dc8  call    cs:__guard_dispatch_icall_fptr
0x1800a3dce  mov     eax, 13h
0x1800a3dd3  mov     [rsp+510h+var_4C0], ax
0x1800a3dd8  mov     [rsp+510h+var_4B8], esi
0x1800a3ddc  mov     rax, [rdi]
0x1800a3ddf  lea     r8, [rsp+510h+var_4C0]
0x1800a3de4  lea     rdx, MetaDataSetUpdate
0x1800a3deb  mov     rcx, rdi
0x1800a3dee  mov     rax, [rax+30h]
0x1800a3df2  call    cs:__guard_dispatch_icall_fptr
0x1800a3df8  and     [rsp+510h+var_4B8], 0
0x1800a3dfd  mov     rax, [rdi]
0x1800a3e00  lea     r8, [rsp+510h+var_4C0]
0x1800a3e05  lea     rdx, MetaDataErrorIfEmitOutOfOrder
0x1800a3e0c  mov     rcx, rdi
0x1800a3e0f  mov     rax, [rax+30h]
0x1800a3e13  call    cs:__guard_dispatch_icall_fptr
0x1800a3e19  lea     rdx, [rbp+410h+var_448]
0x1800a3e1d  mov     rax, [rbp+410h+lpMem]
0x1800a3e21  test    rax, rax
0x1800a3e24  cmovnz  rdx, rax
0x1800a3e28  mov     rax, [rdi]
0x1800a3e2b  mov     [rsp+510h+var_4E8], r14
0x1800a3e30  mov     [rsp+510h+var_4F0], r15
0x1800a3e35  mov     r9d, esi
0x1800a3e38  mov     r8d, [rsp+510h+var_4D0]
0x1800a3e3d  mov     rcx, rdi
0x1800a3e40  mov     rax, [rax+28h]
0x1800a3e44  call    cs:__guard_dispatch_icall_fptr
0x1800a3e4a  mov     ebx, eax
0x1800a3e4c  lea     rax, aSucceeded; "succeeded"
0x1800a3e53  lea     r8, aFailed; "failed"
0x1800a3e5a  test    ebx, ebx
0x1800a3e5c  cmovns  r8, rax
0x1800a3e60  lea     rdx, [rbp+410h+Buffer]
0x1800a3e67  lea     rcx, aDefiningScopeF; "Defining scope for EnC using %S %s\n"
0x1800a3e6e  call    printf
0x1800a3e73  nop
0x1800a3e74  mov     rdi, [rbp+410h+lpMem]
0x1800a3e78  test    rdi, rdi
0x1800a3e7b  jz      short loc_1800A3EA9
0x1800a3e7d  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800a3e84  test    rax, rax
0x1800a3e87  jnz     short loc_1800A3E96
0x1800a3e89  call    cs:__imp_GetProcessHeap
0x1800a3e8f  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800a3e96  mov     r8, rdi; lpMem
0x1800a3e99  xor     edx, edx; dwFlags
0x1800a3e9b  mov     rcx, rax; hHeap
0x1800a3e9e  call    cs:__imp_HeapFree
0x1800a3ea4  and     [rbp+410h+lpMem], 0
0x1800a3ea9  test    ebx, ebx
0x1800a3eab  jns     loc_1800A3F3F
0x1800a3eb1  jmp     loc_1800A3F3B
0x1800a3eb6  mov     ecx, 438h; dwBytes
0x1800a3ebb  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x1800a3ec0  test    rax, rax
0x1800a3ec3  jz      short loc_1800A3F2F
0x1800a3ec5  mov     rcx, rax; this
0x1800a3ec8  call    ??0RegMeta@@QEAA@XZ; RegMeta::RegMeta(void)
0x1800a3ecd  mov     rdi, rax
0x1800a3ed0  test    rax, rax
0x1800a3ed3  jz      short loc_1800A3F2F
0x1800a3ed5  lea     rdx, [rsp+510h+var_4A0]; struct OptionValue *
0x1800a3eda  mov     rcx, rax; this
0x1800a3edd  call    ?SetOption@RegMeta@@QEAAJPEAUOptionValue@@@Z; RegMeta::SetOption(OptionValue *)
0x1800a3ee2  mov     ebx, eax
0x1800a3ee4  mov     rsi, rdi
0x1800a3ee7  test    eax, eax
0x1800a3ee9  js      short loc_1800A3F18
0x1800a3eeb  mov     rcx, rdi; this
0x1800a3eee  call    ?CreateNewMD@RegMeta@@QEAAJXZ; RegMeta::CreateNewMD(void)
0x1800a3ef3  mov     ebx, eax
0x1800a3ef5  test    eax, eax
0x1800a3ef7  js      short loc_1800A3F18
0x1800a3ef9  mov     rax, [rdi]
0x1800a3efc  mov     r8, r14
0x1800a3eff  mov     rdx, r15
0x1800a3f02  mov     rcx, rdi
0x1800a3f05  mov     rax, [rax]
0x1800a3f08  call    cs:__guard_dispatch_icall_fptr
0x1800a3f0e  mov     ebx, eax
0x1800a3f10  test    eax, eax
0x1800a3f12  js      short loc_1800A3F18
0x1800a3f14  xor     ebx, ebx
0x1800a3f16  jmp     short loc_1800A3F3F
0x1800a3f18  mov     rcx, rsi; this
0x1800a3f1b  call    ??1RegMeta@@QEAA@XZ; RegMeta::~RegMeta(void)
0x1800a3f20  mov     edx, 438h; unsigned __int64
0x1800a3f25  mov     rcx, rsi; void *
0x1800a3f28  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800a3f2d  jmp     short loc_1800A3F3B
0x1800a3f2f  mov     ebx, 8007000Eh
0x1800a3f34  jmp     short loc_1800A3F3B
0x1800a3f36  mov     ebx, 80131107h
0x1800a3f3b  and     qword ptr [r14], 0
0x1800a3f3f  mov     eax, ebx
0x1800a3f41  mov     rcx, [rbp+410h+var_30]
0x1800a3f48  xor     rcx, rsp; StackCookie
0x1800a3f4b  call    __security_check_cookie
0x1800a3f50  mov     rbx, [rsp+510h+arg_8]
0x1800a3f58  add     rsp, 4F0h
0x1800a3f5f  pop     r15
0x1800a3f61  pop     r14
0x1800a3f63  pop     rdi
0x1800a3f64  pop     rsi
0x1800a3f65  pop     rbp
0x1800a3f66  retn
```
