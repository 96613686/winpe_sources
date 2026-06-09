# EEToProfInterfaceImpl::CreateAndInitializeProfiler(COleScript *,_GUID const &,ulong,ulong)

- ea: `0x180062938`
- end: `0x180062a4c`
- name: `?CreateAndInitializeProfiler@EEToProfInterfaceImpl@@QEAAJPEAVCOleScript@@AEBU_GUID@@KK@Z`
- size: `276`
- prototype: `__int64 __usercall@<rax>(LPVOID *ppv@<rcx>, struct COleScript *@<rdx>, const struct _GUID *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18003ff3c`
- `0x18007f430`

## callees

- `0x180016d00`
- `0x180062938`
- `0x18007d18c`
- `0x180098010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180062999`
- `ole32!CoCreateInstance` at `0x180062999`

## pseudocode

```c
__int64 __fastcall EEToProfInterfaceImpl::CreateAndInitializeProfiler(
        LPVOID *ppv,
        struct COleScript *a2,
        const struct _GUID *a3,
        char a4,
        unsigned int a5)
{
  HRESULT Instance; // edi
  COleScript *v9; // rcx

  if ( *ppv )
    return 2147746304LL;
  _InterlockedIncrement((volatile signed __int32 *)a2 + 40);
  ppv[3] = a2;
  Instance = CoCreateInstance(a3, 0, 1u, &GUID_740eca23_7d9d_42e5_ba9d_f8b24b1c7a9b, ppv);
  if ( Instance >= 0 )
  {
    if ( (a4 & 1) != 0 )
      *((_DWORD *)ppv + 2) = 1;
    if ( (a4 & 2) != 0 )
      *((_DWORD *)ppv + 3) = 1;
    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 24LL))(*ppv, a5);
    if ( Instance >= 0 )
      COleScript::OnProfilerAttach((COleScript *)ppv[3]);
  }
  if ( Instance < 0 )
  {
    v9 = (COleScript *)ppv[3];
    if ( v9 )
      COleScript::Release(v9);
    if ( *ppv )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*ppv + 32LL))(*ppv, (unsigned int)Instance);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*ppv + 16LL))(*ppv);
    }
    *ppv = 0;
    ppv[3] = 0;
    *(LPVOID *)((char *)ppv + 12) = 0;
    *((_DWORD *)ppv + 2) = 0;
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180062938  mov     [rsp+arg_8], rbx
0x18006293d  mov     [rsp+arg_10], rsi
0x180062942  mov     [rsp+arg_0], rcx
0x180062947  push    rdi
0x180062948  sub     rsp, 40h
0x18006294c  mov     esi, r9d
0x18006294f  mov     rax, r8
0x180062952  mov     rbx, rcx
0x180062955  mov     [rsp+48h+var_18], 0
0x18006295d  cmp     qword ptr [rcx], 0
0x180062961  jz      short loc_180062979
0x180062963  mov     eax, 80040200h
0x180062968  mov     rbx, [rsp+48h+arg_8]
0x18006296d  mov     rsi, [rsp+48h+arg_10]
0x180062972  add     rsp, 40h
0x180062976  pop     rdi
0x180062977  retn
0x180062979  lock inc dword ptr [rdx+0A0h]
0x180062980  mov     [rcx+18h], rdx
0x180062984  mov     [rsp+48h+ppv], rbx; ppv
0x180062989  lea     r9, _GUID_740eca23_7d9d_42e5_ba9d_f8b24b1c7a9b; riid
0x180062990  xor     edx, edx; pUnkOuter
0x180062992  lea     r8d, [rdx+1]; dwClsContext
0x180062996  mov     rcx, rax; rclsid
0x180062999  call    cs:__imp_CoCreateInstance
0x1800629a0  nop     dword ptr [rax+rax+00h]
0x1800629a5  mov     edi, eax
0x1800629a7  mov     [rsp+48h+var_18], eax
0x1800629ab  test    eax, eax
0x1800629ad  js      short loc_1800629F0
0x1800629af  test    sil, 1
0x1800629b3  jz      short loc_1800629BC
0x1800629b5  mov     dword ptr [rbx+8], 1
0x1800629bc  test    sil, 2
0x1800629c0  jz      short loc_1800629C9
0x1800629c2  mov     dword ptr [rbx+0Ch], 1
0x1800629c9  mov     rcx, [rbx]
0x1800629cc  mov     rax, [rcx]
0x1800629cf  mov     edx, [rsp+48h+arg_20]
0x1800629d3  mov     rax, [rax+18h]
0x1800629d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800629dc  mov     edi, eax
0x1800629de  mov     [rsp+48h+var_18], eax
0x1800629e2  test    eax, eax
0x1800629e4  js      short loc_1800629F0
0x1800629e6  mov     rcx, [rbx+18h]; this
0x1800629ea  call    ?OnProfilerAttach@COleScript@@QEAAJXZ; COleScript::OnProfilerAttach(void)
0x1800629ef  nop
0x1800629f0  test    edi, edi
0x1800629f2  jns     short loc_180062A45
0x1800629f4  mov     rcx, [rbx+18h]; this
0x1800629f8  test    rcx, rcx
0x1800629fb  jz      short loc_180062A02
0x1800629fd  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x180062a02  mov     rcx, [rbx]
0x180062a05  test    rcx, rcx
0x180062a08  jz      short loc_180062A27
0x180062a0a  mov     rax, [rcx]
0x180062a0d  mov     edx, edi
0x180062a0f  mov     rax, [rax+20h]
0x180062a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a18  mov     rcx, [rbx]
0x180062a1b  mov     rax, [rcx]
0x180062a1e  mov     rax, [rax+10h]
0x180062a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a27  mov     qword ptr [rbx], 0
0x180062a2e  mov     qword ptr [rbx+18h], 0
0x180062a36  mov     qword ptr [rbx+0Ch], 0
0x180062a3e  mov     dword ptr [rbx+8], 0
0x180062a45  mov     eax, edi
0x180062a47  jmp     loc_180062968
0x180097323  push    rbx
0x180097325  push    rbp
0x180097326  push    rdi
0x180097327  sub     rsp, 30h
0x18009732b  mov     rbp, rdx
0x18009732e  mov     edi, [rbp+30h]
0x180097331  test    edi, edi
0x180097333  jns     short loc_180097395
0x180097335  mov     rbx, [rbp+50h]
0x180097339  cmp     qword ptr [rbx+18h], 0
0x18009733e  jz      short loc_18009734A
0x180097340  mov     rcx, [rbx+18h]; this
0x180097344  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x180097349  nop
0x18009734a  cmp     qword ptr [rbx], 0
0x18009734e  jz      short loc_180097377
0x180097350  mov     rax, [rbx]
0x180097353  mov     r8, [rax]
0x180097356  mov     edx, edi
0x180097358  mov     rcx, rax
0x18009735b  mov     rax, [r8+20h]
0x18009735f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097364  mov     rax, [rbx]
0x180097367  mov     rcx, [rax]
0x18009736a  mov     rax, [rcx+10h]
0x18009736e  mov     rcx, [rbx]
0x180097371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097376  nop
0x180097377  mov     qword ptr [rbx], 0
0x18009737e  mov     qword ptr [rbx+18h], 0
0x180097386  mov     qword ptr [rbx+0Ch], 0
0x18009738e  mov     dword ptr [rbx+8], 0
0x180097395  add     rsp, 30h
0x180097399  pop     rdi
0x18009739a  pop     rbp
0x18009739b  pop     rbx
0x18009739c  retn
```
