# CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)

- ea: `0x1800266f8`
- end: `0x1800267a0`
- name: `?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `12`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800244e0`
- `0x1800246c4`
- `0x180024c78`
- `0x18002c588`
- `0x18002f8cc`
- `0x18003a304`
- `0x18004e0d0`
- `0x18004e3fc`
- `0x18005523c`
- `0x1800591f4`
- `0x18005c3c0`
- `0x18005cbc0`

## callees

- `0x18000683c`
- `0x1800076d4`
- `0x1800266f8`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002673b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002673b`

## string_xrefs

- `0x180026773`: `onecoreuap\internal\shell\inc\cloudexperiencehostcreatebrokeredobjecthelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostCreateElevatedObject(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int ppv; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID v12; // [rsp+78h] [rbp+20h] BYREF

  v12 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  v6 = CoCreateInstance(
         &GUID_ea297d29_fc9f_41ef_a2e0_666891b01c6e,
         0,
         1u,
         &GUID_10316cc3_d36e_46cd_8344_d85f12419862,
         &v12);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, const struct _GUID *, void **))(*(_QWORD *)v12 + 24LL))(
           v12,
           a1,
           a2,
           a3);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v7 = 0;
      goto LABEL_7;
    }
    v8 = 16;
  }
  else
  {
    v8 = 15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostcreatebrokeredobjecthelpers.h",
    (const char *)(unsigned int)v6,
    ppv);
LABEL_7:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  return v7;
}

```

## disassembly

```asm
0x1800266f8  push    rbx
0x1800266fa  push    rbp
0x1800266fb  push    rsi
0x1800266fc  push    rdi
0x1800266fd  sub     rsp, 38h
0x180026701  mov     rdi, r8
0x180026704  mov     rsi, rdx
0x180026707  mov     rbp, rcx
0x18002670a  mov     [rsp+58h+arg_18], 0
0x180026713  lea     rcx, [rsp+58h+arg_18]
0x180026718  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002671d  lea     rax, [rsp+58h+arg_18]
0x180026722  mov     qword ptr [rsp+58h+ppv], rax; int
0x180026727  lea     r9, _GUID_10316cc3_d36e_46cd_8344_d85f12419862; riid
0x18002672e  xor     edx, edx; pUnkOuter
0x180026730  lea     r8d, [rdx+1]; dwClsContext
0x180026734  lea     rcx, _GUID_ea297d29_fc9f_41ef_a2e0_666891b01c6e; rclsid
0x18002673b  call    cs:__imp_CoCreateInstance
0x180026741  mov     ebx, eax
0x180026743  test    eax, eax
0x180026745  jns     short loc_18002674E
0x180026747  mov     edx, 0Fh
0x18002674c  jmp     short loc_180026773
0x18002674e  mov     rcx, [rsp+58h+arg_18]
0x180026753  mov     rax, [rcx]
0x180026756  mov     r9, rdi
0x180026759  mov     r8, rsi
0x18002675c  mov     rdx, rbp
0x18002675f  mov     rax, [rax+18h]
0x180026763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026768  mov     ebx, eax
0x18002676a  test    eax, eax
0x18002676c  jns     short loc_180026789
0x18002676e  mov     edx, 10h; void *
0x180026773  lea     r8, aOnecoreuapInte_9; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x18002677a  mov     r9d, eax; char *
0x18002677d  mov     rcx, [rsp+58h]; this
0x180026782  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026787  jmp     short loc_18002678B
0x180026789  xor     ebx, ebx
0x18002678b  lea     rcx, [rsp+58h+arg_18]
0x180026790  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026795  mov     eax, ebx
0x180026797  add     rsp, 38h
0x18002679b  pop     rdi
0x18002679c  pop     rsi
0x18002679d  pop     rbp
0x18002679e  pop     rbx
0x18002679f  retn
```
