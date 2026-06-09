# SSI_REQUEST::IsExecDisabled(void)

- ea: `0x180004998`
- end: `0x180004af5`
- name: `?IsExecDisabled@SSI_REQUEST@@QEAAHXZ`
- size: `349`
- prototype: `__int64 __fastcall(SSI_REQUEST *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004afc`

## callees

- `0x180004998`
- `0x180006010`

## string_xrefs

- `0x180004a36`: `system.webServer/serverSideInclude`

## pseudocode

```c
__int64 __fastcall SSI_REQUEST::IsExecDisabled(SSI_REQUEST *this)
{
  __int64 v2; // rcx
  __int64 (__fastcall ***v3)(_QWORD); // rax
  __int64 v4; // rbx
  int (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rax
  unsigned int *v7; // rsi
  int v8; // ebx
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF
  __int64 v10; // [rsp+58h] [rbp+10h] BYREF

  if ( *((_DWORD *)this + 196) )
  {
    v7 = (unsigned int *)((char *)this + 780);
  }
  else
  {
    v2 = *((_QWORD *)this + 1);
    v10 = 0;
    v9 = 0;
    v3 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 160LL))(v2);
    v4 = (**v3)(v3);
    v5 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
    if ( (**v5)(v5, &IID_INativeConfigurationSystem, &v10) < 0 )
      return 1;
    if ( (*(int (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v10 + 24LL))(
           v10,
           L"system.webServer/serverSideInclude",
           v4,
           &v9,
           0,
           0) < 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      return 1;
    }
    v7 = (unsigned int *)((char *)this + 780);
    v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v9 + 72LL))(
           v9,
           L"ssiExecDisable",
           (char *)this + 780,
           0,
           0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v8 < 0 )
      return 1;
    *((_DWORD *)this + 196) = 1;
  }
  return *v7;
}

```

## disassembly

```asm
0x180004998  mov     rax, rsp
0x18000499b  mov     [rax+18h], rbx
0x18000499f  mov     [rax+20h], rsi
0x1800049a3  push    rdi
0x1800049a4  sub     rsp, 40h
0x1800049a8  cmp     dword ptr [rcx+310h], 0
0x1800049af  mov     rdi, rcx
0x1800049b2  jnz     loc_180004ADC
0x1800049b8  mov     rcx, [rcx+8]
0x1800049bc  mov     qword ptr [rax+10h], 0
0x1800049c4  mov     qword ptr [rax+8], 0
0x1800049cc  mov     rax, [rcx]
0x1800049cf  mov     rax, [rax+0A0h]
0x1800049d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049db  mov     rdx, rax
0x1800049de  mov     rcx, [rax]
0x1800049e1  mov     rax, [rcx]
0x1800049e4  mov     rcx, rdx
0x1800049e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ec  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x1800049f3  mov     rbx, rax
0x1800049f6  mov     rdx, [rcx]
0x1800049f9  mov     rax, [rdx+38h]
0x1800049fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a02  mov     r9, rax
0x180004a05  lea     r8, [rsp+48h+arg_8]
0x180004a0a  lea     rdx, IID_INativeConfigurationSystem
0x180004a11  mov     rcx, [rax]
0x180004a14  mov     rax, [rcx]
0x180004a17  mov     rcx, r9
0x180004a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a1f  test    eax, eax
0x180004a21  js      short loc_180004A6A
0x180004a23  mov     rcx, [rsp+48h+arg_8]
0x180004a28  lea     r9, [rsp+48h+arg_0]
0x180004a2d  mov     [rsp+48h+var_20], 0
0x180004a36  lea     rdx, aSystemWebserve; "system.webServer/serverSideInclude"
0x180004a3d  mov     r8, rbx
0x180004a40  mov     [rsp+48h+var_28], 0
0x180004a49  mov     rax, [rcx]
0x180004a4c  mov     rax, [rax+18h]
0x180004a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a55  test    eax, eax
0x180004a57  jns     short loc_180004A71
0x180004a59  mov     rcx, [rsp+48h+arg_8]
0x180004a5e  mov     rax, [rcx]
0x180004a61  mov     rax, [rax+10h]
0x180004a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a6a  mov     eax, 1
0x180004a6f  jmp     short loc_180004AE5
0x180004a71  mov     rcx, [rsp+48h+arg_0]
0x180004a76  lea     rsi, [rdi+30Ch]
0x180004a7d  xor     r9d, r9d
0x180004a80  mov     [rsp+48h+var_28], 0
0x180004a89  mov     r8, rsi
0x180004a8c  lea     rdx, aSsiexecdisable; "ssiExecDisable"
0x180004a93  mov     rax, [rcx]
0x180004a96  mov     rax, [rax+48h]
0x180004a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a9f  mov     rcx, [rsp+48h+arg_0]
0x180004aa4  mov     ebx, eax
0x180004aa6  mov     rdx, [rcx]
0x180004aa9  mov     rax, [rdx+10h]
0x180004aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ab2  mov     rcx, [rsp+48h+arg_8]
0x180004ab7  mov     [rsp+48h+arg_0], 0
0x180004ac0  mov     rdx, [rcx]
0x180004ac3  mov     rax, [rdx+10h]
0x180004ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004acc  test    ebx, ebx
0x180004ace  js      short loc_180004A6A
0x180004ad0  mov     dword ptr [rdi+310h], 1
0x180004ada  jmp     short loc_180004AE3
0x180004adc  lea     rsi, [rcx+30Ch]
0x180004ae3  mov     eax, [rsi]
0x180004ae5  mov     rbx, [rsp+48h+arg_10]
0x180004aea  mov     rsi, [rsp+48h+arg_18]
0x180004aef  add     rsp, 40h
0x180004af3  pop     rdi
0x180004af4  retn
```
