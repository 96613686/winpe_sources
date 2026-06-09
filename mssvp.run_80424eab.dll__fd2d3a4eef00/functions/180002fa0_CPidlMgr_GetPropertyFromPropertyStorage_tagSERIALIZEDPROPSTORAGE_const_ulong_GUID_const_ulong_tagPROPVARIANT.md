# CPidlMgr::GetPropertyFromPropertyStorage(tagSERIALIZEDPROPSTORAGE const *,ulong,_GUID const &,ulong,tagPROPVARIANT *)

- ea: `0x180002fa0`
- end: `0x1800030c2`
- name: `?GetPropertyFromPropertyStorage@CPidlMgr@@QEAAJPEFBUtagSERIALIZEDPROPSTORAGE@@KAEBU_GUID@@KPEAUtagPROPVARIANT@@@Z`
- size: `290`
- prototype: `__int64 __fastcall(CPidlMgr *__hidden this, const struct tagSERIALIZEDPROPSTORAGE *, unsigned int, const struct _GUID *, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003a10`
- `0x180028788`

## callees

- `0x180002fa0`
- `0x180006270`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003033`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003033`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall CPidlMgr::GetPropertyFromPropertyStorage(
        CPidlMgr *this,
        const struct tagSERIALIZEDPROPSTORAGE *a2,
        unsigned int a3,
        const struct _GUID *a4,
        unsigned int a5,
        struct tagPROPVARIANT *a6)
{
  __int64 v10; // rcx
  __int64 v11; // rcx
  _QWORD *v12; // rbx
  HRESULT result; // eax
  __int128 v14; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v15; // [rsp+40h] [rbp-48h]

  if ( *(const struct tagSERIALIZEDPROPSTORAGE **)this != a2 )
  {
    v10 = *((_QWORD *)this + 2);
    if ( v10 )
    {
      *((_QWORD *)this + 2) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    v11 = *((_QWORD *)this + 3);
    if ( v11 )
    {
      *((_QWORD *)this + 3) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  v12 = (_QWORD *)((char *)this + 16);
  if ( *((_QWORD *)this + 2)
    || (result = CoCreateInstance(
                   &CLSID_InMemoryPropertyStore,
                   0,
                   1u,
                   &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                   (LPVOID *)this + 2),
        result >= 0) )
  {
    if ( *((_QWORD *)this + 3)
      || (result = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v12)(
                     *v12,
                     &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917,
                     (char *)this + 24),
          result >= 0) )
    {
      result = (*(__int64 (__fastcall **)(_QWORD, const struct tagSERIALIZEDPROPSTORAGE *, _QWORD))(**((_QWORD **)this + 3)
                                                                                                  + 32LL))(
                 *((_QWORD *)this + 3),
                 a2,
                 a3);
      if ( result >= 0 )
      {
        v14 = (__int128)*a4;
        v15 = a5;
        return (*(__int64 (__fastcall **)(_QWORD, __int128 *, struct tagPROPVARIANT *))(*(_QWORD *)*v12 + 40LL))(
                 *v12,
                 &v14,
                 a6);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002fa0  push    rbx
0x180002fa2  push    rbp
0x180002fa3  push    rsi
0x180002fa4  push    rdi
0x180002fa5  push    r12
0x180002fa7  push    r14
0x180002fa9  push    r15
0x180002fab  sub     rsp, 50h
0x180002faf  mov     rax, cs:__security_cookie
0x180002fb6  xor     rax, rsp
0x180002fb9  mov     [rsp+88h+var_40], rax
0x180002fbe  mov     r14, r9
0x180002fc1  mov     ebp, r8d
0x180002fc4  mov     rsi, rdx
0x180002fc7  mov     rdi, rcx
0x180002fca  mov     r15, [rsp+88h+arg_28]
0x180002fd2  xor     r12d, r12d
0x180002fd5  cmp     [rcx], rdx
0x180002fd8  jz      short loc_18000300E
0x180002fda  mov     rcx, [rcx+10h]
0x180002fde  test    rcx, rcx
0x180002fe1  jz      short loc_180002FF4
0x180002fe3  mov     [rdi+10h], r12
0x180002fe7  mov     rax, [rcx]
0x180002fea  mov     rax, [rax+10h]
0x180002fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ff3  nop
0x180002ff4  mov     rcx, [rdi+18h]
0x180002ff8  test    rcx, rcx
0x180002ffb  jz      short loc_18000300E
0x180002ffd  mov     [rdi+18h], r12
0x180003001  mov     rax, [rcx]
0x180003004  mov     rax, [rax+10h]
0x180003008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000300d  nop
0x18000300e  lea     rbx, [rdi+10h]
0x180003012  cmp     qword ptr [rbx], 0
0x180003016  jnz     short loc_18000303D
0x180003018  mov     [rsp+88h+ppv], rbx; ppv
0x18000301d  lea     r9, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180003024  xor     edx, edx; pUnkOuter
0x180003026  mov     r8d, 1; dwClsContext
0x18000302c  lea     rcx, CLSID_InMemoryPropertyStore; rclsid
0x180003033  call    cs:__imp_CoCreateInstance
0x180003039  test    eax, eax
0x18000303b  js      short loc_1800030A6
0x18000303d  cmp     qword ptr [rdi+18h], 0
0x180003042  jnz     short loc_180003061
0x180003044  mov     rcx, [rbx]
0x180003047  mov     rax, [rcx]
0x18000304a  lea     r8, [rdi+18h]
0x18000304e  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x180003055  mov     rax, [rax]
0x180003058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000305d  test    eax, eax
0x18000305f  js      short loc_1800030A6
0x180003061  mov     rcx, [rdi+18h]
0x180003065  mov     rax, [rcx]
0x180003068  mov     r8d, ebp
0x18000306b  mov     rdx, rsi
0x18000306e  mov     rax, [rax+20h]
0x180003072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003077  test    eax, eax
0x180003079  js      short loc_1800030A6
0x18000307b  movups  xmm0, xmmword ptr [r14]
0x18000307f  movups  [rsp+88h+var_58], xmm0
0x180003084  mov     eax, [rsp+88h+arg_20]
0x18000308b  mov     [rsp+88h+var_48], eax
0x18000308f  mov     rcx, [rbx]
0x180003092  mov     rax, [rcx]
0x180003095  mov     r8, r15
0x180003098  lea     rdx, [rsp+88h+var_58]
0x18000309d  mov     rax, [rax+28h]
0x1800030a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a6  mov     rcx, [rsp+88h+var_40]
0x1800030ab  xor     rcx, rsp; StackCookie
0x1800030ae  call    __security_check_cookie
0x1800030b3  add     rsp, 50h
0x1800030b7  pop     r15
0x1800030b9  pop     r14
0x1800030bb  pop     r12
0x1800030bd  pop     rdi
0x1800030be  pop     rsi
0x1800030bf  pop     rbp
0x1800030c0  pop     rbx
0x1800030c1  retn
```
