# CLTApplicationInstances::GetTable(_GUID const &,_GUID const &,void *,void *,ulong,ulong,void *,void * *)

- ea: `0x180025f20`
- end: `0x180026157`
- name: `?GetTable@CLTApplicationInstances@@UEAAJAEBU_GUID@@0PEAX1KK1PEAPEAX@Z`
- size: `567`
- prototype: `__int64 __fastcall(CLTApplicationInstances *__hidden this, const struct _GUID *, const struct _GUID *, void *, void *, unsigned int, unsigned int, void *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180025ce4`
- `0x180025f20`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026031`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180026031`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026117`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026117`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTApplicationInstances::GetTable(
        CLTApplicationInstances *this,
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
  void **v11; // r14
  char *v13; // rax
  GUID v14; // xmm0
  GUID *v15; // rax
  GUID v16; // xmm0
  CLTApplicationInstances *v17; // rcx
  HRESULT Instance; // ebx
  unsigned __int64 v19; // rcx
  struct ISimpleTableDispenser *ppv; // [rsp+50h] [rbp-20h] BYREF
  struct __MIDL___MIDL_itf_stable_0000_0000_0001 *v21; // [rsp+58h] [rbp-18h] BYREF
  __int64 v22; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v23; // [rsp+A8h] [rbp+38h] BYREF

  ppv = 0;
  v22 = 0;
  v10 = 0;
  v21 = 0;
  v23 = 0;
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
  if ( *(_QWORD *)a4 )
  {
    if ( *((_DWORD *)a4 + 2) || *((_DWORD *)a4 + 3) != 1 || *((_DWORD *)a4 + 4) != 72 || *((_DWORD *)a4 + 5) != 16 )
      return 2147942487LL;
    v14 = *(GUID *)*(_QWORD *)a4;
  }
  else
  {
    v14 = GUID_NULL;
  }
  *(GUID *)((char *)this + 24) = v14;
  v15 = (GUID *)*((_QWORD *)a4 + 3);
  if ( v15 )
  {
    if ( *((_DWORD *)a4 + 8) || *((_DWORD *)a4 + 9) != 2 || *((_DWORD *)a4 + 10) != 72 || *((_DWORD *)a4 + 11) != 16 )
      return 2147942487LL;
    v16 = *v15;
  }
  else
  {
    v16 = GUID_NULL;
  }
  *(GUID *)((char *)this + 40) = v16;
  Instance = CoCreateInstance(&CLSID_STDispenser, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
  if ( Instance >= 0 )
  {
    Instance = CLTApplicationInstances::GetSimpleColumnMeta(v17, ppv, &v21, &v23);
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
                       &v22),
          Instance < 0) )
    {
      v10 = v21;
    }
    else
    {
      v10 = v21;
      Instance = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct __MIDL___MIDL_itf_stable_0000_0000_0001 *))(*(_QWORD *)v22 + 24LL))(
                   v22,
                   8,
                   v23,
                   v21);
      if ( Instance >= 0 )
      {
        v19 = ((unsigned __int64)this - 16) & -(__int64)(this != (CLTApplicationInstances *)24);
        *v11 = (void *)v19;
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v19 + 8LL))(v19);
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
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180025f20  mov     [rsp-18h+arg_0], rbx
0x180025f25  mov     [rsp-18h+arg_8], rsi
0x180025f2a  push    rbp
0x180025f2b  push    rdi
0x180025f2c  push    r14
0x180025f2e  mov     rbp, rsp
0x180025f31  sub     rsp, 70h
0x180025f35  mov     rdi, rcx
0x180025f38  mov     [rbp+var_20], 0
0x180025f40  mov     [rbp+var_10], 0
0x180025f48  xor     esi, esi
0x180025f4a  mov     [rbp+var_18], rsi
0x180025f4e  mov     [rbp+arg_18], esi
0x180025f51  mov     r14, [rbp+arg_40]
0x180025f55  mov     [r14], rsi
0x180025f58  cmp     [rbp+arg_28], 1
0x180025f5c  jnz     short loc_180025F7A
0x180025f5e  test    r9, r9
0x180025f61  jz      short loc_180025F7A
0x180025f63  mov     ecx, dword ptr [rbp+arg_20]
0x180025f66  mov     eax, ecx
0x180025f68  sub     eax, 2
0x180025f6b  jz      short loc_180025FA7
0x180025f6d  cmp     eax, 1
0x180025f70  jz      short loc_180025F94
0x180025f72  lea     eax, [rcx-2]
0x180025f75  cmp     eax, 1
0x180025f78  jbe     short loc_180025FA7
0x180025f7a  mov     eax, 80070057h
0x180025f7f  lea     r11, [rsp+70h+var_s0]
0x180025f84  mov     rbx, [r11+20h]
0x180025f88  mov     rsi, [r11+28h]
0x180025f8c  mov     rsp, r11
0x180025f8f  pop     r14
0x180025f91  pop     rdi
0x180025f92  pop     rbp
0x180025f93  retn
0x180025f94  lea     rax, [r9+18h]
0x180025f98  cmp     dword ptr [r9+0Ch], 0F0000002h
0x180025fa0  cmovnz  rax, r9
0x180025fa4  mov     r9, rax
0x180025fa7  mov     rax, [r9]
0x180025faa  test    rax, rax
0x180025fad  jz      short loc_180025FCF
0x180025faf  cmp     [r9+8], esi
0x180025fb3  jnz     short loc_180025F7A
0x180025fb5  cmp     dword ptr [r9+0Ch], 1
0x180025fba  jnz     short loc_180025F7A
0x180025fbc  cmp     dword ptr [r9+10h], 48h ; 'H'
0x180025fc1  jnz     short loc_180025F7A
0x180025fc3  cmp     dword ptr [r9+14h], 10h
0x180025fc8  jnz     short loc_180025F7A
0x180025fca  movups  xmm0, xmmword ptr [rax]
0x180025fcd  jmp     short loc_180025FD6
0x180025fcf  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180025fd6  movdqu  xmmword ptr [rdi+18h], xmm0
0x180025fdb  mov     rax, [r9+18h]
0x180025fdf  test    rax, rax
0x180025fe2  jz      short loc_180026008
0x180025fe4  cmp     [r9+20h], esi
0x180025fe8  jnz     short loc_180025F7A
0x180025fea  cmp     dword ptr [r9+24h], 2
0x180025fef  jnz     short loc_180025F7A
0x180025ff1  cmp     dword ptr [r9+28h], 48h ; 'H'
0x180025ff6  jnz     short loc_180025F7A
0x180025ff8  cmp     dword ptr [r9+2Ch], 10h
0x180025ffd  jnz     loc_180025F7A
0x180026003  movups  xmm0, xmmword ptr [rax]
0x180026006  jmp     short loc_18002600F
0x180026008  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002600f  movdqu  xmmword ptr [rdi+28h], xmm0
0x180026014  lea     rax, [rbp+var_20]
0x180026018  mov     [rsp+70h+ppv], rax; ppv
0x18002601d  lea     r9, IID_ISimpleTableDispenser; riid
0x180026024  xor     edx, edx; pUnkOuter
0x180026026  lea     r8d, [rdx+1]; dwClsContext
0x18002602a  lea     rcx, CLSID_STDispenser; rclsid
0x180026031  call    cs:__imp_CoCreateInstance
0x180026037  mov     ebx, eax
0x180026039  test    eax, eax
0x18002603b  js      loc_180026114
0x180026041  lea     r9, [rbp+arg_18]; unsigned int *
0x180026045  lea     r8, [rbp+var_18]; struct __MIDL___MIDL_itf_stable_0000_0000_0001 **
0x180026049  mov     rdx, [rbp+var_20]; struct ISimpleTableDispenser *
0x18002604d  call    ?GetSimpleColumnMeta@CLTApplicationInstances@@AEAAJPEAUISimpleTableDispenser@@PEAPEAU__MIDL___MIDL_itf_stable_0000_0000_0001@@PEAK@Z; CLTApplicationInstances::GetSimpleColumnMeta(ISimpleTableDispenser *,__MIDL___MIDL_itf_stable_0000_0000_0001 * *,ulong *)
0x180026052  mov     ebx, eax
0x180026054  test    eax, eax
0x180026056  js      loc_180026110
0x18002605c  lea     rsi, [rdi+10h]
0x180026060  mov     rcx, [rbp+var_20]
0x180026064  mov     rax, [rcx]
0x180026067  mov     [rsp+70h+var_38], rsi
0x18002606c  mov     [rsp+70h+var_40], 8
0x180026074  mov     [rsp+70h+var_48], 1
0x18002607c  mov     [rsp+70h+ppv], 0
0x180026085  xor     r9d, r9d
0x180026088  lea     r8, tidMEMORY_SHAPEABLE
0x18002608f  lea     rdx, didMEMORY
0x180026096  mov     rax, [rax+18h]
0x18002609a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002609f  mov     ebx, eax
0x1800260a1  test    eax, eax
0x1800260a3  js      short loc_180026110
0x1800260a5  mov     rcx, [rsi]
0x1800260a8  mov     rax, [rcx]
0x1800260ab  lea     r8, [rbp+var_10]
0x1800260af  lea     rdx, IID_ISimpleTableControl
0x1800260b6  mov     rax, [rax]
0x1800260b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260be  mov     ebx, eax
0x1800260c0  test    eax, eax
0x1800260c2  js      short loc_180026110
0x1800260c4  mov     rcx, [rbp+var_10]
0x1800260c8  mov     rax, [rcx]
0x1800260cb  mov     rsi, [rbp+var_18]
0x1800260cf  mov     r9, rsi
0x1800260d2  mov     r8d, [rbp+arg_18]
0x1800260d6  mov     edx, 8
0x1800260db  mov     rax, [rax+18h]
0x1800260df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260e4  mov     ebx, eax
0x1800260e6  test    eax, eax
0x1800260e8  js      short loc_180026114
0x1800260ea  lea     rax, [rdi-18h]
0x1800260ee  lea     rdx, [rdi-10h]
0x1800260f2  neg     rax
0x1800260f5  sbb     rcx, rcx
0x1800260f8  and     rcx, rdx
0x1800260fb  mov     [r14], rcx
0x1800260fe  mov     rax, [rcx]
0x180026101  mov     rax, [rax+8]
0x180026105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002610a  lock inc dword ptr [rdi+0Ch]
0x18002610e  jmp     short loc_180026114
0x180026110  mov     rsi, [rbp+var_18]
0x180026114  mov     rcx, rsi; pv
0x180026117  call    cs:__imp_CoTaskMemFree
0x18002611d  nop
0x18002611e  mov     rcx, [rbp+var_20]
0x180026122  test    rcx, rcx
0x180026125  jz      short loc_18002613B
0x180026127  mov     rax, [rcx]
0x18002612a  mov     rax, [rax+10h]
0x18002612e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026133  mov     [rbp+var_20], 0
0x18002613b  mov     rcx, [rbp+var_10]
0x18002613f  test    rcx, rcx
0x180026142  jz      short loc_180026150
0x180026144  mov     rax, [rcx]
0x180026147  mov     rax, [rax+10h]
0x18002614b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026150  mov     eax, ebx
0x180026152  jmp     loc_180025F7F
```
