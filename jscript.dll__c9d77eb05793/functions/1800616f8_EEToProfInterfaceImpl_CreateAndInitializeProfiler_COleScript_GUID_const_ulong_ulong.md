# EEToProfInterfaceImpl::CreateAndInitializeProfiler(COleScript *,_GUID const &,ulong,ulong)

- ea: `0x1800616f8`
- end: `0x180061805`
- name: `?CreateAndInitializeProfiler@EEToProfInterfaceImpl@@QEAAJPEAVCOleScript@@AEBU_GUID@@KK@Z`
- size: `269`
- prototype: `__int64 __usercall@<rax>(LPVOID *ppv@<rcx>, struct COleScript *@<rdx>, const struct _GUID *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180002598`
- `0x18007db00`

## callees

- `0x180019ce0`
- `0x1800616f8`
- `0x18007b93c`
- `0x180096010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180061758`
- `ole32!CoCreateInstance` at `0x180061758`

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
0x1800616f8  mov     [rsp+arg_8], rbx
0x1800616fd  mov     [rsp+arg_10], rsi
0x180061702  mov     [rsp+arg_0], rcx
0x180061707  push    rdi
0x180061708  sub     rsp, 40h
0x18006170c  mov     esi, r9d
0x18006170f  mov     rax, r8
0x180061712  mov     rbx, rcx
0x180061715  mov     [rsp+48h+var_18], 0
0x18006171d  cmp     qword ptr [rcx], 0
0x180061721  jz      short loc_180061738
0x180061723  mov     eax, 80040200h
0x180061728  mov     rbx, [rsp+48h+arg_8]
0x18006172d  mov     rsi, [rsp+48h+arg_10]
0x180061732  add     rsp, 40h
0x180061736  pop     rdi
0x180061737  retn
0x180061738  lock inc dword ptr [rdx+0A0h]
0x18006173f  mov     [rcx+18h], rdx
0x180061743  mov     [rsp+48h+ppv], rbx; ppv
0x180061748  lea     r9, _GUID_740eca23_7d9d_42e5_ba9d_f8b24b1c7a9b; riid
0x18006174f  xor     edx, edx; pUnkOuter
0x180061751  lea     r8d, [rdx+1]; dwClsContext
0x180061755  mov     rcx, rax; rclsid
0x180061758  call    cs:__imp_CoCreateInstance
0x18006175e  mov     edi, eax
0x180061760  mov     [rsp+48h+var_18], eax
0x180061764  test    eax, eax
0x180061766  js      short loc_1800617A9
0x180061768  test    sil, 1
0x18006176c  jz      short loc_180061775
0x18006176e  mov     dword ptr [rbx+8], 1
0x180061775  test    sil, 2
0x180061779  jz      short loc_180061782
0x18006177b  mov     dword ptr [rbx+0Ch], 1
0x180061782  mov     rcx, [rbx]
0x180061785  mov     rax, [rcx]
0x180061788  mov     edx, [rsp+48h+arg_20]
0x18006178c  mov     rax, [rax+18h]
0x180061790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061795  mov     edi, eax
0x180061797  mov     [rsp+48h+var_18], eax
0x18006179b  test    eax, eax
0x18006179d  js      short loc_1800617A9
0x18006179f  mov     rcx, [rbx+18h]; this
0x1800617a3  call    ?OnProfilerAttach@COleScript@@QEAAJXZ; COleScript::OnProfilerAttach(void)
0x1800617a8  nop
0x1800617a9  test    edi, edi
0x1800617ab  jns     short loc_1800617FE
0x1800617ad  mov     rcx, [rbx+18h]; this
0x1800617b1  test    rcx, rcx
0x1800617b4  jz      short loc_1800617BB
0x1800617b6  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x1800617bb  mov     rcx, [rbx]
0x1800617be  test    rcx, rcx
0x1800617c1  jz      short loc_1800617E0
0x1800617c3  mov     rax, [rcx]
0x1800617c6  mov     edx, edi
0x1800617c8  mov     rax, [rax+20h]
0x1800617cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800617d1  mov     rcx, [rbx]
0x1800617d4  mov     rax, [rcx]
0x1800617d7  mov     rax, [rax+10h]
0x1800617db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800617e0  mov     qword ptr [rbx], 0
0x1800617e7  mov     qword ptr [rbx+18h], 0
0x1800617ef  mov     qword ptr [rbx+0Ch], 0
0x1800617f7  mov     dword ptr [rbx+8], 0
0x1800617fe  mov     eax, edi
0x180061800  jmp     loc_180061728
0x180094ef3  push    rbx
0x180094ef5  push    rbp
0x180094ef6  push    rdi
0x180094ef7  sub     rsp, 30h
0x180094efb  mov     rbp, rdx
0x180094efe  mov     edi, [rbp+30h]
0x180094f01  test    edi, edi
0x180094f03  jns     short loc_180094F65
0x180094f05  mov     rbx, [rbp+50h]
0x180094f09  cmp     qword ptr [rbx+18h], 0
0x180094f0e  jz      short loc_180094F1A
0x180094f10  mov     rcx, [rbx+18h]; this
0x180094f14  call    ?Release@COleScript@@UEAAKXZ; COleScript::Release(void)
0x180094f19  nop
0x180094f1a  cmp     qword ptr [rbx], 0
0x180094f1e  jz      short loc_180094F47
0x180094f20  mov     rax, [rbx]
0x180094f23  mov     r8, [rax]
0x180094f26  mov     edx, edi
0x180094f28  mov     rcx, rax
0x180094f2b  mov     rax, [r8+20h]
0x180094f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094f34  mov     rax, [rbx]
0x180094f37  mov     rcx, [rax]
0x180094f3a  mov     rax, [rcx+10h]
0x180094f3e  mov     rcx, [rbx]
0x180094f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094f46  nop
0x180094f47  mov     qword ptr [rbx], 0
0x180094f4e  mov     qword ptr [rbx+18h], 0
0x180094f56  mov     qword ptr [rbx+0Ch], 0
0x180094f5e  mov     dword ptr [rbx+8], 0
0x180094f65  add     rsp, 30h
0x180094f69  pop     rdi
0x180094f6a  pop     rbp
0x180094f6b  pop     rbx
0x180094f6c  retn
```
