# FiringAgent::~FiringAgent(void)

- ea: `0x18001dbc0`
- end: `0x18001dd57`
- name: `??1FiringAgent@@AEAA@XZ`
- size: `407`
- prototype: `void __fastcall(FiringAgent *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001d9c0`
- `0x18001db80`

## callees

- `0x18001dbc0`
- `0x18001dd60`
- `0x18001de38`
- `0x18001de98`
- `0x18001def8`
- `0x18001df50`
- `0x18003f080`
- `0x180046010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18001dc18`
- `msvcrt!_resetstkoflw` at `0x18001dc18`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dc58`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dc62`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dc6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dc7c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dc58`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dc62`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dc6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dc7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dc4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dc4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dd3b`

## pseudocode

```c
void __fastcall FiringAgent::~FiringAgent(FiringAgent *this)
{
  __int64 v2; // rcx
  unsigned __int16 i; // di
  __int64 v4; // rax
  void *v5; // rsi
  __int64 v6; // rcx
  _QWORD *v7; // rdi
  __int64 v8; // rcx
  int *v9[2]; // [rsp+58h] [rbp-18h] BYREF

  *(_QWORD *)this = &FiringAgent::`vftable'{for `IMultiInterfaceEventControl'};
  *((_QWORD *)this + 1) = &FiringAgent::`vftable'{for `IEventControl'};
  *((_QWORD *)this + 2) = &FiringAgent::`vftable'{for `IAmAFiringAgent'};
  v2 = *((_QWORD *)this + 16);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  for ( i = 0; i < *((_WORD *)this + 20); ++i )
  {
    v4 = *((_QWORD *)this + 6);
    v5 = *(void **)(v4 + 8LL * i);
    if ( v5 )
    {
      EventInterface::~EventInterface(*(EventInterface **)(v4 + 8LL * i));
      CoTaskMemFree(v5);
    }
  }
  CoTaskMemFree(*((LPVOID *)this + 6));
  SysFreeString(*((BSTR *)this + 12));
  SysFreeString(*((BSTR *)this + 13));
  SysFreeString(*((BSTR *)this + 25));
  SysFreeString(*((BSTR *)this + 26));
  v6 = *((_QWORD *)this + 15);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  while ( *((_DWORD *)this + 38) )
  {
    v7 = (_QWORD *)CList<FiringAgent::AutoUpdateListElement *,FiringAgent::AutoUpdateListElement *>::RemoveHead((char *)this + 136);
    *(_OWORD *)v9 = *(_OWORD *)v7;
    (*(void (__fastcall **)(_QWORD, int **))(**((_QWORD **)this + 4) + 32LL))(*((_QWORD *)this + 4), v9);
    if ( v7 )
    {
      v8 = v7[2];
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      CoTaskMemFree(v7);
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4));
  FiringAgent::CleanupInterfaceInfo(this);
  _InterlockedDecrement(&g_tier1ActiveObjects);
  CList<FiringAgent::AutoUpdateListElement *,FiringAgent::AutoUpdateListElement *>::RemoveAll((char *)this + 136);
  CMap<_GUID,_GUID const &,InterfaceInfo *,InterfaceInfo *>::RemoveAll((char *)this + 56);
}

```

## disassembly

```asm
0x18001dbc0  mov     [rsp+arg_8], rbx
0x18001dbc5  mov     [rsp+arg_10], rsi
0x18001dbca  mov     [rsp+arg_0], rcx
0x18001dbcf  push    rdi
0x18001dbd0  sub     rsp, 50h
0x18001dbd4  mov     rbx, rcx
0x18001dbd7  lea     rax, ??_7FiringAgent@@6BIMultiInterfaceEventControl@@@; const FiringAgent::`vftable'{for `IMultiInterfaceEventControl'}
0x18001dbde  mov     [rcx], rax
0x18001dbe1  lea     rax, ??_7FiringAgent@@6BIEventControl@@@; const FiringAgent::`vftable'{for `IEventControl'}
0x18001dbe8  mov     [rcx+8], rax
0x18001dbec  lea     rax, ??_7FiringAgent@@6BIAmAFiringAgent@@@; const FiringAgent::`vftable'{for `IAmAFiringAgent'}
0x18001dbf3  mov     [rcx+10h], rax
0x18001dbf7  mov     rcx, [rcx+80h]
0x18001dbfe  test    rcx, rcx
0x18001dc01  jz      short loc_18001DC0F
0x18001dc03  mov     rax, [rcx]
0x18001dc06  mov     rax, [rax+10h]
0x18001dc0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc0f  jmp     short loc_18001DC23
0x18001dc11  cmp     eax, 0C00000FDh
0x18001dc16  jnz     short loc_18001DC1E
0x18001dc18  call    cs:__imp__resetstkoflw
0x18001dc1e  mov     rbx, [rsp+58h+arg_0]
0x18001dc23  xor     edi, edi
0x18001dc25  xor     eax, eax
0x18001dc27  cmp     ax, [rbx+28h]
0x18001dc2b  jnb     short loc_18001DC4A
0x18001dc2d  movzx   ecx, di
0x18001dc30  mov     rax, [rbx+30h]
0x18001dc34  mov     rsi, [rax+rcx*8]
0x18001dc38  test    rsi, rsi
0x18001dc3b  jnz     loc_18001DD30
0x18001dc41  inc     di
0x18001dc44  cmp     di, [rbx+28h]
0x18001dc48  jb      short loc_18001DC2D
0x18001dc4a  mov     rcx, [rbx+30h]; pv
0x18001dc4e  call    cs:__imp_CoTaskMemFree
0x18001dc54  mov     rcx, [rbx+60h]; bstrString
0x18001dc58  call    cs:__imp_SysFreeString
0x18001dc5e  mov     rcx, [rbx+68h]; bstrString
0x18001dc62  call    cs:__imp_SysFreeString
0x18001dc68  mov     rcx, [rbx+0C8h]; bstrString
0x18001dc6f  call    cs:__imp_SysFreeString
0x18001dc75  mov     rcx, [rbx+0D0h]; bstrString
0x18001dc7c  call    cs:__imp_SysFreeString
0x18001dc82  mov     rcx, [rbx+78h]
0x18001dc86  test    rcx, rcx
0x18001dc89  jnz     loc_18001DD46
0x18001dc8f  cmp     dword ptr [rbx+98h], 0
0x18001dc96  jnz     short loc_18001DCDC
0x18001dc98  mov     rcx, [rbx+20h]
0x18001dc9c  mov     rax, [rcx]
0x18001dc9f  mov     rax, [rax+10h]
0x18001dca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dca8  mov     rcx, rbx; this
0x18001dcab  call    ?CleanupInterfaceInfo@FiringAgent@@AEAAXXZ; FiringAgent::CleanupInterfaceInfo(void)
0x18001dcb0  lock dec cs:?g_tier1ActiveObjects@@3JA; long g_tier1ActiveObjects
0x18001dcb7  lea     rcx, [rbx+88h]
0x18001dcbe  call    ?RemoveAll@?$CList@PEAUAutoUpdateListElement@FiringAgent@@PEAU12@@@QEAAXXZ; CList<FiringAgent::AutoUpdateListElement *,FiringAgent::AutoUpdateListElement *>::RemoveAll(void)
0x18001dcc3  lea     rcx, [rbx+38h]
0x18001dcc7  call    ?RemoveAll@?$CMap@U_GUID@@AEBU1@PEAVInterfaceInfo@@PEAV2@@@QEAAXXZ; CMap<_GUID,_GUID const &,InterfaceInfo *,InterfaceInfo *>::RemoveAll(void)
0x18001dccc  mov     rbx, [rsp+58h+arg_8]
0x18001dcd1  mov     rsi, [rsp+58h+arg_10]
0x18001dcd6  add     rsp, 50h
0x18001dcda  pop     rdi
0x18001dcdb  retn
0x18001dcdc  lea     rcx, [rbx+88h]
0x18001dce3  call    ?RemoveHead@?$CList@PEAUAutoUpdateListElement@FiringAgent@@PEAU12@@@QEAAPEAUAutoUpdateListElement@FiringAgent@@XZ; CList<FiringAgent::AutoUpdateListElement *,FiringAgent::AutoUpdateListElement *>::RemoveHead(void)
0x18001dce8  mov     rdi, rax
0x18001dceb  movups  xmm0, xmmword ptr [rax]
0x18001dcee  movaps  xmmword ptr [rsp+58h+var_18], xmm0
0x18001dcf3  mov     rcx, [rbx+20h]
0x18001dcf7  mov     rdx, [rcx]
0x18001dcfa  mov     rax, [rdx+20h]
0x18001dcfe  lea     rdx, [rsp+58h+var_18]
0x18001dd03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd08  test    rdi, rdi
0x18001dd0b  jz      short loc_18001DC8F
0x18001dd0d  mov     rcx, [rdi+10h]
0x18001dd11  test    rcx, rcx
0x18001dd14  jz      short loc_18001DD22
0x18001dd16  mov     rax, [rcx]
0x18001dd19  mov     rax, [rax+10h]
0x18001dd1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd22  mov     rcx, rdi; pv
0x18001dd25  call    cs:__imp_CoTaskMemFree
0x18001dd2b  jmp     loc_18001DC8F
0x18001dd30  mov     rcx, rsi; this
0x18001dd33  call    ??1EventInterface@@QEAA@XZ; EventInterface::~EventInterface(void)
0x18001dd38  mov     rcx, rsi; pv
0x18001dd3b  call    cs:__imp_CoTaskMemFree
0x18001dd41  jmp     loc_18001DC41
0x18001dd46  mov     rax, [rcx]
0x18001dd49  mov     rax, [rax+10h]
0x18001dd4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd52  jmp     loc_18001DC8F
0x180044ad0  push    rbp
0x180044ad2  sub     rsp, 30h
0x180044ad6  mov     rbp, rdx
0x180044ad9  lea     rax, [rbp+30h]
0x180044add  mov     [rsp+38h+var_18], rax; int *
0x180044ae2  call    ?MethodCallExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@GAEBU_GUID@@PEBGAEAJ@Z; MethodCallExceptionFilter(_EXCEPTION_POINTERS *,ushort,_GUID const &,ushort const *,long &)
0x180044ae7  nop
0x180044ae8  add     rsp, 30h
0x180044aec  pop     rbp
0x180044aed  retn
```
