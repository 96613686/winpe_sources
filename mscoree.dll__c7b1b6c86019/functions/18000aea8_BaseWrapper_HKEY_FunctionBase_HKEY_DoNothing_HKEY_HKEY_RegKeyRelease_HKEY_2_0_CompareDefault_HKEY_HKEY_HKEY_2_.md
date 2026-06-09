# BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(void)

- ea: `0x18000aea8`
- end: `0x18000aedf`
- name: `??I?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA?AVTypedAddressInitHolder@0@XZ`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008f00`
- `0x18000a884`
- `0x18000aa50`
- `0x18000ac2c`
- `0x18000af8c`
- `0x180032c00`

## callees

- `0x18000aea8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000aec4`
- `ADVAPI32!RegCloseKey` at `0x18000aec4`

## pseudocode

```c
_QWORD *__fastcall BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::operator&(
        __int64 a1,
        _QWORD *a2)
{
  bool v2; // zf

  v2 = *(_DWORD *)(a1 + 8) == 0;
  *a2 = a1;
  if ( !v2 )
  {
    RegCloseKey(*(HKEY *)a1);
    *(_DWORD *)(a1 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18000aea8  mov     [rsp+arg_0], rbx
0x18000aead  push    rdi
0x18000aeae  sub     rsp, 20h
0x18000aeb2  cmp     dword ptr [rcx+8], 0
0x18000aeb6  mov     rdi, rdx
0x18000aeb9  mov     rbx, rcx
0x18000aebc  mov     [rdx], rcx
0x18000aebf  jz      short loc_18000AED1
0x18000aec1  mov     rcx, [rcx]; hKey
0x18000aec4  call    cs:__imp_RegCloseKey
0x18000aeca  mov     dword ptr [rbx+8], 0
0x18000aed1  mov     rbx, [rsp+28h+arg_0]
0x18000aed6  mov     rax, rdi
0x18000aed9  add     rsp, 20h
0x18000aedd  pop     rdi
0x18000aede  retn
```
