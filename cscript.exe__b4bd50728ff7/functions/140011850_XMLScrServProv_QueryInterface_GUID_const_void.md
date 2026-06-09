# XMLScrServProv::QueryInterface(_GUID const &,void * *)

- ea: `0x140011850`
- end: `0x1400118bc`
- name: `?QueryInterface@XMLScrServProv@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `108`
- prototype: `__int64 __fastcall(XMLScrServProv *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x140011850`
- `0x140017010`

## pseudocode

```c
__int64 __fastcall XMLScrServProv::QueryInterface(XMLScrServProv *this, const struct _GUID *a2, void **a3)
{
  __int64 v4; // rax
  __int64 v5; // rax

  if ( !a3 )
    return 2147500035LL;
  v4 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v4 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v4 )
    goto LABEL_10;
  v5 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IServiceProvider.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IServiceProvider.Data1 )
    v5 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IServiceProvider.Data4;
  if ( v5 )
  {
    *a3 = 0;
    return 2147500034LL;
  }
  else
  {
LABEL_10:
    *a3 = this;
    (*(void (__fastcall **)(XMLScrServProv *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
}

```

## disassembly

```asm
0x140011850  sub     rsp, 28h
0x140011854  test    r8, r8
0x140011857  jnz     short loc_140011860
0x140011859  mov     eax, 80004003h
0x14001185e  jmp     short loc_1400118B7
0x140011860  mov     rax, [rdx]
0x140011863  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x14001186a  jnz     short loc_140011877
0x14001186c  mov     rax, [rdx+8]
0x140011870  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x140011877  test    rax, rax
0x14001187a  jz      short loc_1400118A6
0x14001187c  mov     rax, [rdx]
0x14001187f  sub     rax, qword ptr cs:IID_IServiceProvider.Data1
0x140011886  jnz     short loc_140011893
0x140011888  mov     rax, [rdx+8]
0x14001188c  sub     rax, qword ptr cs:IID_IServiceProvider.Data4
0x140011893  test    rax, rax
0x140011896  jz      short loc_1400118A6
0x140011898  mov     qword ptr [r8], 0
0x14001189f  mov     eax, 80004002h
0x1400118a4  jmp     short loc_1400118B7
0x1400118a6  mov     [r8], rcx
0x1400118a9  mov     rax, [rcx]
0x1400118ac  mov     rax, [rax+8]
0x1400118b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400118b5  xor     eax, eax
0x1400118b7  add     rsp, 28h
0x1400118bb  retn
```
