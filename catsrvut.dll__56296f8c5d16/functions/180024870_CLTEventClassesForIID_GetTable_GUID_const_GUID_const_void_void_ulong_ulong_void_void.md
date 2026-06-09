# CLTEventClassesForIID::GetTable(_GUID const &,_GUID const &,void *,void *,ulong,ulong,void *,void * *)

- ea: `0x180024870`
- end: `0x180024a8e`
- name: `?GetTable@CLTEventClassesForIID@@UEAAJAEBU_GUID@@0PEAX1KK1PEAPEAX@Z`
- size: `542`
- prototype: `__int64 __fastcall(CLTEventClassesForIID *__hidden this, const struct _GUID *, const struct _GUID *, void *, void *, unsigned int, unsigned int, void *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180024638`
- `0x180024870`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024978`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180024978`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024a6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024a6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTEventClassesForIID::GetTable(
        CLTEventClassesForIID *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        char *a4,
        void *a5,
        unsigned int a6,
        unsigned int a7,
        void *a8,
        void **a9)
{
  struct __MIDL___MIDL_itf_stable_0000_0000_0001 *v10; // rsi
  void **v11; // r15
  char *v13; // rax
  GUID *v14; // rax
  GUID v15; // xmm0
  struct ISimpleTableDispenser **v16; // r14
  CLTEventClassesForIID *v17; // rcx
  HRESULT Instance; // ebx
  unsigned __int64 v19; // rcx
  struct __MIDL___MIDL_itf_stable_0000_0000_0001 *v20; // [rsp+50h] [rbp-28h] BYREF
  __int64 v21; // [rsp+58h] [rbp-20h] BYREF
  unsigned int v22; // [rsp+98h] [rbp+20h] BYREF

  v21 = 0;
  v10 = 0;
  v20 = 0;
  v22 = 0;
  v11 = a9;
  *a9 = 0;
  if ( a6 != 1 || !a4 )
    return 2147942487LL;
  if ( (_DWORD)a5 != 2 )
  {
    if ( (_DWORD)a5 == 3 )
    {
      v13 = a4 + 24;
      if ( *((_DWORD *)a4 + 3) != -268435454 )
        v13 = a4;
      a4 = v13;
    }
    else if ( (unsigned int)((_DWORD)a5 - 2) > 1 )
    {
      return 2147942487LL;
    }
  }
  if ( !*(_QWORD *)a4
    || *((_DWORD *)a4 + 2)
    || *((_DWORD *)a4 + 3) != 2
    || *((_DWORD *)a4 + 4) != 72
    || *((_DWORD *)a4 + 5) != 16 )
  {
    return 2147942487LL;
  }
  *((_OWORD *)this + 2) = *(_OWORD *)*(_QWORD *)a4;
  v14 = (GUID *)*((_QWORD *)a4 + 3);
  if ( v14 )
  {
    if ( *((_DWORD *)a4 + 8) || *((_DWORD *)a4 + 9) != 7 || *((_DWORD *)a4 + 10) != 72 || *((_DWORD *)a4 + 11) != 16 )
      return 2147942487LL;
    v15 = *v14;
  }
  else
  {
    v15 = GUID_NULL;
  }
  *((GUID *)this + 3) = v15;
  v16 = (struct ISimpleTableDispenser **)((char *)this + 16);
  Instance = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)this + 2);
  if ( Instance >= 0 )
  {
    Instance = CLTEventClassesForIID::GetSimpleColumnMeta(v17, *v16, &v20, &v22);
    if ( Instance < 0
      || (Instance = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int64 *, __int64 *, _QWORD, _QWORD, int, int, char *))(*(_QWORD *)*v16 + 24LL))(
                       *v16,
                       didMEMORY,
                       tidMEMORY_SHAPEABLE,
                       0,
                       0,
                       1,
                       8,
                       (char *)this + 24),
          Instance < 0)
      || (Instance = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
                       *((_QWORD *)this + 3),
                       &IID_ISimpleTableControl,
                       &v21),
          Instance < 0) )
    {
      v10 = v20;
    }
    else
    {
      v10 = v20;
      Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct __MIDL___MIDL_itf_stable_0000_0000_0001 *))(*(_QWORD *)v21 + 24LL))(
                   v21,
                   8,
                   v22,
                   v20);
      if ( Instance >= 0 )
      {
        v19 = ((unsigned __int64)this - 16) & -(__int64)(this != (CLTEventClassesForIID *)24);
        *v11 = (void *)v19;
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v19 + 8LL))(v19);
        _InterlockedIncrement((volatile signed __int32 *)this + 3);
      }
    }
  }
  CoTaskMemFree(v10);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180024870  mov     rax, rsp
0x180024873  mov     [rax+8], rbx
0x180024877  mov     [rax+10h], rsi
0x18002487b  push    rdi
0x18002487c  push    r14
0x18002487e  push    r15
0x180024880  sub     rsp, 60h
0x180024884  mov     rdi, rcx
0x180024887  mov     qword ptr [rax-20h], 0
0x18002488f  xor     esi, esi
0x180024891  mov     [rax-28h], rsi
0x180024895  mov     [rax+20h], esi
0x180024898  mov     r15, [rsp+78h+arg_40]
0x1800248a0  mov     [r15], rsi
0x1800248a3  cmp     [rsp+78h+arg_28], 1
0x1800248ab  jnz     short loc_1800248CD
0x1800248ad  test    r9, r9
0x1800248b0  jz      short loc_1800248CD
0x1800248b2  mov     ecx, dword ptr [rsp+78h+arg_20]
0x1800248b9  mov     eax, ecx
0x1800248bb  sub     eax, 2
0x1800248be  jz      short loc_1800248FB
0x1800248c0  cmp     eax, 1
0x1800248c3  jz      short loc_1800248E8
0x1800248c5  lea     eax, [rcx-2]
0x1800248c8  cmp     eax, 1
0x1800248cb  jbe     short loc_1800248FB
0x1800248cd  mov     eax, 80070057h
0x1800248d2  lea     r11, [rsp+78h+var_18]
0x1800248d7  mov     rbx, [r11+20h]
0x1800248db  mov     rsi, [r11+28h]
0x1800248df  mov     rsp, r11
0x1800248e2  pop     r15
0x1800248e4  pop     r14
0x1800248e6  pop     rdi
0x1800248e7  retn
0x1800248e8  lea     rax, [r9+18h]
0x1800248ec  cmp     dword ptr [r9+0Ch], 0F0000002h
0x1800248f4  cmovnz  rax, r9
0x1800248f8  mov     r9, rax
0x1800248fb  mov     rax, [r9]
0x1800248fe  test    rax, rax
0x180024901  jz      short loc_1800248CD
0x180024903  cmp     [r9+8], esi
0x180024907  jnz     short loc_1800248CD
0x180024909  cmp     dword ptr [r9+0Ch], 2
0x18002490e  jnz     short loc_1800248CD
0x180024910  cmp     dword ptr [r9+10h], 48h ; 'H'
0x180024915  jnz     short loc_1800248CD
0x180024917  cmp     dword ptr [r9+14h], 10h
0x18002491c  jnz     short loc_1800248CD
0x18002491e  movups  xmm0, xmmword ptr [rax]
0x180024921  movdqu  xmmword ptr [rdi+20h], xmm0
0x180024926  mov     rax, [r9+18h]
0x18002492a  test    rax, rax
0x18002492d  jz      short loc_18002494F
0x18002492f  cmp     [r9+20h], esi
0x180024933  jnz     short loc_1800248CD
0x180024935  cmp     dword ptr [r9+24h], 7
0x18002493a  jnz     short loc_1800248CD
0x18002493c  cmp     dword ptr [r9+28h], 48h ; 'H'
0x180024941  jnz     short loc_1800248CD
0x180024943  cmp     dword ptr [r9+2Ch], 10h
0x180024948  jnz     short loc_1800248CD
0x18002494a  movups  xmm0, xmmword ptr [rax]
0x18002494d  jmp     short loc_180024956
0x18002494f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180024956  movdqu  xmmword ptr [rdi+30h], xmm0
0x18002495b  lea     r14, [rdi+10h]
0x18002495f  mov     [rsp+78h+ppv], r14; ppv
0x180024964  lea     r9, IID_ISimpleTableDispenser; riid
0x18002496b  xor     edx, edx; pUnkOuter
0x18002496d  lea     r8d, [rdx+1]; dwClsContext
0x180024971  lea     rcx, CLSID_STDispenser; rclsid
0x180024978  call    cs:__imp_CoCreateInstance
0x18002497e  mov     ebx, eax
0x180024980  test    eax, eax
0x180024982  js      loc_180024A67
0x180024988  lea     r9, [rsp+78h+arg_18]; unsigned int *
0x180024990  lea     r8, [rsp+78h+var_28]; struct __MIDL___MIDL_itf_stable_0000_0000_0001 **
0x180024995  mov     rdx, [r14]; struct ISimpleTableDispenser *
0x180024998  call    ?GetSimpleColumnMeta@CLTEventClassesForIID@@AEAAJPEAUISimpleTableDispenser@@PEAPEAU__MIDL___MIDL_itf_stable_0000_0000_0001@@PEAK@Z; CLTEventClassesForIID::GetSimpleColumnMeta(ISimpleTableDispenser *,__MIDL___MIDL_itf_stable_0000_0000_0001 * *,ulong *)
0x18002499d  mov     ebx, eax
0x18002499f  test    eax, eax
0x1800249a1  js      loc_180024A62
0x1800249a7  mov     rcx, [r14]
0x1800249aa  lea     rsi, [rdi+18h]
0x1800249ae  mov     rax, [rcx]
0x1800249b1  mov     [rsp+78h+var_40], rsi
0x1800249b6  mov     r14d, 8
0x1800249bc  mov     [rsp+78h+var_48], r14d
0x1800249c1  mov     [rsp+78h+var_50], 1
0x1800249c9  mov     [rsp+78h+ppv], 0
0x1800249d2  xor     r9d, r9d
0x1800249d5  lea     r8, tidMEMORY_SHAPEABLE
0x1800249dc  lea     rdx, didMEMORY
0x1800249e3  mov     rax, [rax+18h]
0x1800249e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249ec  mov     ebx, eax
0x1800249ee  test    eax, eax
0x1800249f0  js      short loc_180024A62
0x1800249f2  mov     rcx, [rsi]
0x1800249f5  mov     rax, [rcx]
0x1800249f8  lea     r8, [rsp+78h+var_20]
0x1800249fd  lea     rdx, IID_ISimpleTableControl
0x180024a04  mov     rax, [rax]
0x180024a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a0c  mov     ebx, eax
0x180024a0e  test    eax, eax
0x180024a10  js      short loc_180024A62
0x180024a12  mov     rcx, [rsp+78h+var_20]
0x180024a17  mov     rax, [rcx]
0x180024a1a  mov     rsi, [rsp+78h+var_28]
0x180024a1f  mov     r9, rsi
0x180024a22  mov     r8d, [rsp+78h+arg_18]
0x180024a2a  mov     edx, r14d
0x180024a2d  mov     rax, [rax+18h]
0x180024a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a36  mov     ebx, eax
0x180024a38  test    eax, eax
0x180024a3a  js      short loc_180024A67
0x180024a3c  lea     rax, [rdi-18h]
0x180024a40  lea     rdx, [rdi-10h]
0x180024a44  neg     rax
0x180024a47  sbb     rcx, rcx
0x180024a4a  and     rcx, rdx
0x180024a4d  mov     [r15], rcx
0x180024a50  mov     rax, [rcx]
0x180024a53  mov     rax, [rax+8]
0x180024a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a5c  lock inc dword ptr [rdi+0Ch]
0x180024a60  jmp     short loc_180024A67
0x180024a62  mov     rsi, [rsp+78h+var_28]
0x180024a67  mov     rcx, rsi; pv
0x180024a6a  call    cs:__imp_CoTaskMemFree
0x180024a70  nop
0x180024a71  mov     rcx, [rsp+78h+var_20]
0x180024a76  test    rcx, rcx
0x180024a79  jz      short loc_180024A87
0x180024a7b  mov     rax, [rcx]
0x180024a7e  mov     rax, [rax+10h]
0x180024a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a87  mov     eax, ebx
0x180024a89  jmp     loc_1800248D2
```
