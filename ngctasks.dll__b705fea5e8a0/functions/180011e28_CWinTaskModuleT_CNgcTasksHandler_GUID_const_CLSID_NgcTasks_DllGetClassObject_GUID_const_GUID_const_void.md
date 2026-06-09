# CWinTaskModuleT<CNgcTasksHandler,&_GUID const CLSID_NgcTasks>::DllGetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180011e28`
- end: `0x180011ed9`
- name: `?DllGetClassObject@?$CWinTaskModuleT@VCNgcTasksHandler@@$1?CLSID_NgcTasks@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `177`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015140`

## callees

- `0x18000682c`
- `0x180011e28`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CWinTaskModuleT<CNgcTasksHandler,&_GUID const CLSID_NgcTasks>::DllGetClassObject(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v7; // rax
  unsigned int v8; // edi
  _DWORD *v9; // [rsp+30h] [rbp+8h]

  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  v7 = *(_QWORD *)&CLSID_NgcTasks.Data1 - *a2;
  if ( *(_QWORD *)&CLSID_NgcTasks.Data1 == *a2 )
    v7 = *(_QWORD *)CLSID_NgcTasks.Data4 - a2[1];
  if ( v7 )
  {
    return (unsigned int)-2147221231;
  }
  else
  {
    v9 = operator new(0x10u);
    *(_QWORD *)v9 = &CWinTaskClassFactoryT<CNgcTasksHandler,1>::`vftable';
    v9[2] = 1;
    _InterlockedIncrement(&CWinTaskHandler::s_cInstances);
    v8 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, a3, a4);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return v8;
}

```

## disassembly

```asm
0x180011e28  mov     [rsp+arg_8], rbx
0x180011e2d  mov     [rsp+arg_10], rsi
0x180011e32  mov     [rsp+arg_0], rcx
0x180011e37  push    rdi
0x180011e38  sub     rsp, 20h
0x180011e3c  mov     rdi, r9
0x180011e3f  mov     rsi, r8
0x180011e42  test    r9, r9
0x180011e45  jnz     short loc_180011E4E
0x180011e47  mov     eax, 80070057h
0x180011e4c  jmp     short loc_180011EC9
0x180011e4e  mov     qword ptr [r9], 0
0x180011e55  mov     rax, qword ptr cs:CLSID_NgcTasks.Data1
0x180011e5c  sub     rax, [rdx]
0x180011e5f  jnz     short loc_180011E6C
0x180011e61  mov     rax, qword ptr cs:CLSID_NgcTasks.Data4
0x180011e68  sub     rax, [rdx+8]
0x180011e6c  test    rax, rax
0x180011e6f  jz      short loc_180011E78
0x180011e71  mov     edi, 80040111h
0x180011e76  jmp     short loc_180011EC7
0x180011e78  mov     ecx, 10h; Size
0x180011e7d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011e82  mov     rbx, rax
0x180011e85  mov     [rsp+28h+arg_0], rax
0x180011e8a  lea     rax, ??_7?$CWinTaskClassFactoryT@VCNgcTasksHandler@@$00@@6B@; const CWinTaskClassFactoryT<CNgcTasksHandler,1>::`vftable'
0x180011e91  mov     [rbx], rax
0x180011e94  mov     dword ptr [rbx+8], 1
0x180011e9b  lock inc cs:?s_cInstances@CWinTaskHandler@@0JC; long volatile CWinTaskHandler::s_cInstances
0x180011ea2  mov     rax, [rbx]
0x180011ea5  mov     r8, rdi
0x180011ea8  mov     rdx, rsi
0x180011eab  mov     rcx, rbx
0x180011eae  mov     rax, [rax]
0x180011eb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eb6  mov     edi, eax
0x180011eb8  mov     rcx, [rbx]
0x180011ebb  mov     rax, [rcx+10h]
0x180011ebf  mov     rcx, rbx
0x180011ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ec7  mov     eax, edi
0x180011ec9  mov     rbx, [rsp+28h+arg_8]
0x180011ece  mov     rsi, [rsp+28h+arg_10]
0x180011ed3  add     rsp, 20h
0x180011ed7  pop     rdi
0x180011ed8  retn
```
