# CPersistDSO::GetPropertyInfo(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPINFOSET * *,ushort * *)

- ea: `0x180014980`
- end: `0x180014abf`
- name: `?GetPropertyInfo@CPersistDSO@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPINFOSET@@PEAPEAG@Z`
- size: `319`
- prototype: `int(CPersistDSO *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPINFOSET **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180014980`
- `0x180016584`
- `0x18002bdb8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800149ce`
- `KERNEL32!GetCurrentThreadId` at `0x1800149ce`
- `KERNEL32!LeaveCriticalSection` at `0x180014a95`
- `KERNEL32!LeaveCriticalSection` at `0x180014a95`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800149f3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800149f3`
- `MSDART!UMSEnterCSWraper` at `0x1800149b4`
- `MSDART!UMSEnterCSWraper` at `0x1800149b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistDSO::GetPropertyInfo(
        CPersistDSO *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPINFOSET **a5,
        unsigned __int16 **a6)
{
  CPersistDSO *v9; // rbx
  _QWORD *v10; // r14
  _DWORD *v11; // rdi
  _DWORD *v12; // rsi
  int PropertyInfo; // eax
  unsigned int v14; // r15d
  __int64 v16; // rcx
  int v19; // [rsp+40h] [rbp-58h]
  int v20; // [rsp+40h] [rbp-58h]
  int v21; // [rsp+44h] [rbp-54h] BYREF
  char *v22; // [rsp+48h] [rbp-50h]
  _DWORD *v23; // [rsp+50h] [rbp-48h]
  _DWORD *v24; // [rsp+58h] [rbp-40h]
  _QWORD *v25; // [rsp+60h] [rbp-38h]

  v9 = this;
  v10 = (_QWORD *)((char *)this + 48);
  v22 = (char *)this + 48;
  UMSEnterCSWraper((char *)this + 48);
  v11 = (_DWORD *)((char *)v9 + 60);
  v23 = (_DWORD *)((char *)v9 + 60);
  if ( !*((_DWORD *)v9 + 15) )
    *((_DWORD *)v9 + 14) = GetCurrentThreadId();
  ++*v11;
  v12 = (_DWORD *)((char *)v9 + 64);
  v24 = (_DWORD *)((char *)v9 + 64);
  ++*((_DWORD *)v9 + 16);
  v25 = v10;
  SetErrorInfo(0, 0);
  try
  {
    *((GUID *)v9 + 6) = IID_IDBProperties;
    *((_DWORD *)v9 + 1053) = 0;
    PropertyInfo = CUtlPropInfo::GetPropertyInfo(
                     (CPersistDSO *)((char *)v9 + 4728),
                     a2,
                     a3,
                     a4,
                     a5,
                     a6,
                     (CPersistDSO *)((char *)v9 + 4584));
  }
  catch ( long v21 )
  {
    v19 = v21;
    v12 = v24;
    v11 = v23;
    v10 = v22;
    PropertyInfo = v19;
    v9 = this;
  }
  catch ( ... )
  {
    v20 = -2147467259;
    v12 = v24;
    v11 = v23;
    v10 = v22;
    PropertyInfo = v20;
    v9 = this;
  }
  v14 = Exit(PropertyInfo, 0xBB9u);
  --*v12;
  if ( (*v11)-- == 1 )
    *((_DWORD *)v9 + 14) = -1;
  v16 = *v10;
  --*(_DWORD *)(v16 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 8));
  return v14;
}

```

## disassembly

```asm
0x180014980  mov     [rsp+arg_8], rbx
0x180014985  mov     [rsp+arg_10], rsi
0x18001498a  mov     [rsp+arg_0], rcx
0x18001498f  push    rdi
0x180014990  push    r12
0x180014992  push    r13
0x180014994  push    r14
0x180014996  push    r15
0x180014998  sub     rsp, 70h
0x18001499c  mov     r15, r9
0x18001499f  mov     r12, r8
0x1800149a2  mov     r13d, edx
0x1800149a5  mov     rbx, rcx
0x1800149a8  lea     r14, [rcx+30h]
0x1800149ac  mov     [rsp+98h+var_50], r14
0x1800149b1  mov     rcx, r14
0x1800149b4  call    cs:__imp_UMSEnterCSWraper
0x1800149bb  nop     dword ptr [rax+rax+00h]
0x1800149c0  lea     rdi, [rbx+3Ch]
0x1800149c4  mov     [rsp+98h+var_48], rdi
0x1800149c9  cmp     dword ptr [rdi], 0
0x1800149cc  jnz     short loc_1800149DD
0x1800149ce  call    cs:__imp_GetCurrentThreadId
0x1800149d5  nop     dword ptr [rax+rax+00h]
0x1800149da  mov     [rbx+38h], eax
0x1800149dd  inc     dword ptr [rdi]
0x1800149df  lea     rsi, [rbx+40h]
0x1800149e3  mov     [rsp+98h+var_40], rsi
0x1800149e8  inc     dword ptr [rsi]
0x1800149ea  mov     [rsp+98h+var_38], r14
0x1800149ef  xor     edx, edx; perrinfo
0x1800149f1  xor     ecx, ecx; dwReserved
0x1800149f3  call    cs:__imp_SetErrorInfo
0x1800149fa  nop     dword ptr [rax+rax+00h]
0x1800149ff  movups  xmm0, xmmword ptr cs:IID_IDBProperties.Data1
0x180014a06  movdqu  xmmword ptr [rbx+60h], xmm0
0x180014a0b  mov     dword ptr [rbx+1074h], 0
0x180014a15  lea     rax, [rbx+11E8h]
0x180014a1c  lea     rcx, [rbx+1278h]; this
0x180014a23  mov     [rsp+98h+var_68], rax; struct CBidGenericBase *
0x180014a28  mov     rax, [rsp+98h+arg_28]
0x180014a30  mov     [rsp+98h+var_70], rax; unsigned __int16 **
0x180014a35  mov     rax, [rsp+98h+arg_20]
0x180014a3d  mov     [rsp+98h+var_78], rax; struct tagDBPROPINFOSET **
0x180014a42  mov     r9, r15; unsigned int *
0x180014a45  mov     r8, r12; struct tagDBPROPIDSET *
0x180014a48  mov     edx, r13d; unsigned int
0x180014a4b  call    ?GetPropertyInfo@CUtlPropInfo@@QEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPINFOSET@@PEAPEAGAEBVCBidGenericBase@@@Z; CUtlPropInfo::GetPropertyInfo(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPINFOSET * *,ushort * *,CBidGenericBase const &)
0x180014a50  nop
0x180014a51  jmp     short loc_180014A70
0x180014a53  jmp     short $+2
0x180014a55  mov     rsi, [rsp+98h+var_40]
0x180014a5a  mov     rdi, [rsp+98h+var_48]
0x180014a5f  mov     r14, [rsp+98h+var_50]
0x180014a64  mov     eax, [rsp+98h+var_58]
0x180014a68  mov     rbx, [rsp+98h+arg_0]
0x180014a70  mov     edx, 0BB9h; unsigned int
0x180014a75  mov     ecx, eax; int
0x180014a77  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180014a7c  mov     r15d, eax
0x180014a7f  or      eax, 0FFFFFFFFh
0x180014a82  add     [rsi], eax
0x180014a84  add     [rdi], eax
0x180014a86  jnz     short loc_180014A8B
0x180014a88  mov     [rbx+38h], eax
0x180014a8b  mov     rcx, [r14]
0x180014a8e  dec     dword ptr [rcx+30h]
0x180014a91  add     rcx, 8; lpCriticalSection
0x180014a95  call    cs:__imp_LeaveCriticalSection
0x180014a9c  nop     dword ptr [rax+rax+00h]
0x180014aa1  mov     eax, r15d
0x180014aa4  lea     r11, [rsp+98h+var_28]
0x180014aa9  mov     rbx, [r11+38h]
0x180014aad  mov     rsi, [r11+40h]
0x180014ab1  mov     rsp, r11
0x180014ab4  pop     r15
0x180014ab6  pop     r14
0x180014ab8  pop     r13
0x180014aba  pop     r12
0x180014abc  pop     rdi
0x180014abd  retn
```
