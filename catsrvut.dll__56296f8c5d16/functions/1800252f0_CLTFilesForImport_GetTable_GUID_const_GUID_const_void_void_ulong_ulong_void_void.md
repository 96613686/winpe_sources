# CLTFilesForImport::GetTable(_GUID const &,_GUID const &,void *,void *,ulong,ulong,void *,void * *)

- ea: `0x1800252f0`
- end: `0x1800254dc`
- name: `?GetTable@CLTFilesForImport@@UEAAJAEBU_GUID@@0PEAX1KK1PEAPEAX@Z`
- size: `492`
- prototype: `__int64 __fastcall(CLTFilesForImport *__hidden this, const struct _GUID *, const struct _GUID *, void *, void *, unsigned int, unsigned int, void *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800250bc`
- `0x1800252f0`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800253b6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800253b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002549c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002549c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTFilesForImport::GetTable(
        CLTFilesForImport *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        char *a4,
        void *a5,
        unsigned int a6,
        unsigned int a7,
        void *a8,
        void **a9)
{
  struct __MIDL___MIDL_itf_stable_0000_0000_0001 *v10; // rdi
  void **v11; // r14
  char *v13; // rax
  CLTFilesForImport *v14; // rcx
  HRESULT Instance; // ebx
  unsigned __int64 v16; // rcx
  struct ISimpleTableDispenser *ppv; // [rsp+50h] [rbp-20h] BYREF
  struct __MIDL___MIDL_itf_stable_0000_0000_0001 *v18; // [rsp+58h] [rbp-18h] BYREF
  __int64 v19; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v20; // [rsp+A8h] [rbp+38h] BYREF

  ppv = 0;
  v19 = 0;
  v10 = 0;
  v18 = 0;
  v20 = 0;
  v11 = a9;
  *a9 = 0;
  if ( a6 != 1 || !a4 )
    return 2147942487LL;
  if ( (_DWORD)a5 != 1 )
  {
    if ( (_DWORD)a5 == 2 )
    {
      v13 = a4 + 24;
      if ( *((_DWORD *)a4 + 3) != -268435454 )
        v13 = a4;
      a4 = v13;
    }
    else if ( (unsigned int)((_DWORD)a5 - 1) > 1 )
    {
      return 2147942487LL;
    }
  }
  if ( !*(_QWORD *)a4 || *((_DWORD *)a4 + 2) || *((_DWORD *)a4 + 3) || *((_DWORD *)a4 + 4) != 130 )
    return 2147942487LL;
  *((_QWORD *)this + 3) = *(_QWORD *)a4;
  Instance = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = CLTFilesForImport::GetSimpleColumnMeta(v14, ppv, &v18, &v20);
    if ( Instance < 0
      || (Instance = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int64 *, __int64 *, _QWORD, _QWORD, int, int, char *))(*(_QWORD *)ppv + 24LL))(
                       ppv,
                       didMEMORY,
                       tidMEMORY_SHAPEABLE,
                       0,
                       0,
                       1,
                       8,
                       (char *)this + 16),
          Instance < 0)
      || (Instance = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 2))(
                       *((_QWORD *)this + 2),
                       &IID_ISimpleTableControl,
                       &v19),
          Instance < 0) )
    {
      v10 = v18;
    }
    else
    {
      v10 = v18;
      Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct __MIDL___MIDL_itf_stable_0000_0000_0001 *))(*(_QWORD *)v19 + 24LL))(
                   v19,
                   8,
                   v20,
                   v18);
      if ( Instance >= 0 )
      {
        v16 = ((unsigned __int64)this - 16) & -(__int64)(this != (CLTFilesForImport *)24);
        *v11 = (void *)v16;
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v16 + 8LL))(v16);
        _InterlockedIncrement((volatile signed __int32 *)this + 3);
      }
    }
  }
  CoTaskMemFree(v10);
  if ( ppv )
  {
    (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800252f0  mov     [rsp-18h+arg_0], rbx
0x1800252f5  mov     [rsp-18h+arg_8], rsi
0x1800252fa  push    rbp
0x1800252fb  push    rdi
0x1800252fc  push    r14
0x1800252fe  mov     rbp, rsp
0x180025301  sub     rsp, 70h
0x180025305  mov     rsi, rcx
0x180025308  mov     [rbp+var_20], 0
0x180025310  mov     [rbp+var_10], 0
0x180025318  xor     edi, edi
0x18002531a  mov     [rbp+var_18], rdi
0x18002531e  mov     [rbp+arg_18], edi
0x180025321  mov     r14, [rbp+arg_40]
0x180025325  mov     [r14], rdi
0x180025328  cmp     [rbp+arg_28], 1
0x18002532c  jnz     short loc_18002534A
0x18002532e  test    r9, r9
0x180025331  jz      short loc_18002534A
0x180025333  mov     ecx, dword ptr [rbp+arg_20]
0x180025336  mov     eax, ecx
0x180025338  sub     eax, 1
0x18002533b  jz      short loc_180025377
0x18002533d  cmp     eax, 1
0x180025340  jz      short loc_180025364
0x180025342  lea     eax, [rcx-1]
0x180025345  cmp     eax, 1
0x180025348  jbe     short loc_180025377
0x18002534a  mov     eax, 80070057h
0x18002534f  lea     r11, [rsp+70h+var_s0]
0x180025354  mov     rbx, [r11+20h]
0x180025358  mov     rsi, [r11+28h]
0x18002535c  mov     rsp, r11
0x18002535f  pop     r14
0x180025361  pop     rdi
0x180025362  pop     rbp
0x180025363  retn
0x180025364  lea     rax, [r9+18h]
0x180025368  cmp     dword ptr [r9+0Ch], 0F0000002h
0x180025370  cmovnz  rax, r9
0x180025374  mov     r9, rax
0x180025377  mov     rax, [r9]
0x18002537a  test    rax, rax
0x18002537d  jz      short loc_18002534A
0x18002537f  cmp     [r9+8], edi
0x180025383  jnz     short loc_18002534A
0x180025385  cmp     [r9+0Ch], edi
0x180025389  jnz     short loc_18002534A
0x18002538b  cmp     dword ptr [r9+10h], 82h
0x180025393  jnz     short loc_18002534A
0x180025395  mov     [rsi+18h], rax
0x180025399  lea     rax, [rbp+var_20]
0x18002539d  mov     [rsp+70h+ppv], rax; ppv
0x1800253a2  lea     r9, IID_ISimpleTableDispenser; riid
0x1800253a9  xor     edx, edx; pUnkOuter
0x1800253ab  lea     r8d, [rdx+1]; dwClsContext
0x1800253af  lea     rcx, CLSID_STDispenser; rclsid
0x1800253b6  call    cs:__imp_CoCreateInstance
0x1800253bc  mov     ebx, eax
0x1800253be  test    eax, eax
0x1800253c0  js      loc_180025499
0x1800253c6  lea     r9, [rbp+arg_18]; unsigned int *
0x1800253ca  lea     r8, [rbp+var_18]; struct __MIDL___MIDL_itf_stable_0000_0000_0001 **
0x1800253ce  mov     rdx, [rbp+var_20]; struct ISimpleTableDispenser *
0x1800253d2  call    ?GetSimpleColumnMeta@CLTFilesForImport@@AEAAJPEAUISimpleTableDispenser@@PEAPEAU__MIDL___MIDL_itf_stable_0000_0000_0001@@PEAK@Z; CLTFilesForImport::GetSimpleColumnMeta(ISimpleTableDispenser *,__MIDL___MIDL_itf_stable_0000_0000_0001 * *,ulong *)
0x1800253d7  mov     ebx, eax
0x1800253d9  test    eax, eax
0x1800253db  js      loc_180025495
0x1800253e1  lea     rdi, [rsi+10h]
0x1800253e5  mov     rcx, [rbp+var_20]
0x1800253e9  mov     rax, [rcx]
0x1800253ec  mov     [rsp+70h+var_38], rdi
0x1800253f1  mov     [rsp+70h+var_40], 8
0x1800253f9  mov     [rsp+70h+var_48], 1
0x180025401  mov     [rsp+70h+ppv], 0
0x18002540a  xor     r9d, r9d
0x18002540d  lea     r8, tidMEMORY_SHAPEABLE
0x180025414  lea     rdx, didMEMORY
0x18002541b  mov     rax, [rax+18h]
0x18002541f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025424  mov     ebx, eax
0x180025426  test    eax, eax
0x180025428  js      short loc_180025495
0x18002542a  mov     rcx, [rdi]
0x18002542d  mov     rax, [rcx]
0x180025430  lea     r8, [rbp+var_10]
0x180025434  lea     rdx, IID_ISimpleTableControl
0x18002543b  mov     rax, [rax]
0x18002543e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025443  mov     ebx, eax
0x180025445  test    eax, eax
0x180025447  js      short loc_180025495
0x180025449  mov     rcx, [rbp+var_10]
0x18002544d  mov     rax, [rcx]
0x180025450  mov     rdi, [rbp+var_18]
0x180025454  mov     r9, rdi
0x180025457  mov     r8d, [rbp+arg_18]
0x18002545b  mov     edx, 8
0x180025460  mov     rax, [rax+18h]
0x180025464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025469  mov     ebx, eax
0x18002546b  test    eax, eax
0x18002546d  js      short loc_180025499
0x18002546f  lea     rax, [rsi-18h]
0x180025473  lea     rdx, [rsi-10h]
0x180025477  neg     rax
0x18002547a  sbb     rcx, rcx
0x18002547d  and     rcx, rdx
0x180025480  mov     [r14], rcx
0x180025483  mov     rax, [rcx]
0x180025486  mov     rax, [rax+8]
0x18002548a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002548f  lock inc dword ptr [rsi+0Ch]
0x180025493  jmp     short loc_180025499
0x180025495  mov     rdi, [rbp+var_18]
0x180025499  mov     rcx, rdi; pv
0x18002549c  call    cs:__imp_CoTaskMemFree
0x1800254a2  nop
0x1800254a3  mov     rcx, [rbp+var_20]
0x1800254a7  test    rcx, rcx
0x1800254aa  jz      short loc_1800254C0
0x1800254ac  mov     rax, [rcx]
0x1800254af  mov     rax, [rax+10h]
0x1800254b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254b8  mov     [rbp+var_20], 0
0x1800254c0  mov     rcx, [rbp+var_10]
0x1800254c4  test    rcx, rcx
0x1800254c7  jz      short loc_1800254D5
0x1800254c9  mov     rax, [rcx]
0x1800254cc  mov     rax, [rax+10h]
0x1800254d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254d5  mov     eax, ebx
0x1800254d7  jmp     loc_18002534F
```
