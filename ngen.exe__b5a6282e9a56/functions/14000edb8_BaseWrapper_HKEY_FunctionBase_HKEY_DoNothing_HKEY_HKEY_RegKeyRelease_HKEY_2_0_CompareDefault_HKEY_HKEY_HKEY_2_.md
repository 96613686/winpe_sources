# BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)

- ea: `0x14000edb8`
- end: `0x14000ee03`
- name: `??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ`
- size: `75`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000fe04`

## callees

- `0x14000edb8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000edde`
- `ADVAPI32!RegCloseKey` at `0x14000edde`

## pseudocode

```c
_QWORD *__fastcall BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
        __int64 a1,
        _QWORD *a2)
{
  *a2 = a1;
  if ( *(_DWORD *)(a1 + 8) )
  {
    RegCloseKey(*(HKEY *)a1);
    *(_DWORD *)(a1 + 8) = 0;
  }
  *(_QWORD *)a1 = 0;
  return a2;
}

```

## disassembly

```asm
0x14000edb8  mov     [rsp+arg_0], rbx
0x14000edbd  mov     [rsp+arg_8], rdx
0x14000edc2  push    rdi
0x14000edc3  sub     rsp, 30h
0x14000edc7  mov     rdi, rdx
0x14000edca  mov     rbx, rcx
0x14000edcd  and     [rsp+38h+var_18], 0
0x14000edd2  mov     [rdx], rcx
0x14000edd5  cmp     dword ptr [rcx+8], 0
0x14000edd9  jz      short loc_14000EDE8
0x14000eddb  mov     rcx, [rcx]; hKey
0x14000edde  call    cs:__imp_RegCloseKey
0x14000ede4  and     dword ptr [rbx+8], 0
0x14000ede8  and     qword ptr [rbx], 0
0x14000edec  mov     [rsp+38h+var_18], 1
0x14000edf4  mov     rax, rdi
0x14000edf7  mov     rbx, [rsp+38h+arg_0]
0x14000edfc  add     rsp, 30h
0x14000ee00  pop     rdi
0x14000ee01  retn
```
