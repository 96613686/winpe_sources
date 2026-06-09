# Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)

- ea: `0x180004dcc`
- end: `0x180004df3`
- name: `?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ`
- size: `39`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013214`
- `0x1800132a8`
- `0x180013370`
- `0x1800135a0`
- `0x180013bec`
- `0x180013e00`
- `0x180014114`
- `0x180014164`
- `0x180014298`
- `0x180014758`
- `0x1800148a0`
- `0x18001517c`
- `0x180015260`
- `0x180015880`

## callees

- `0x180004dcc`
- `0x18001a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(__int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180004dcc  sub     rsp, 28h
0x180004dd0  mov     rdx, rcx
0x180004dd3  xor     eax, eax
0x180004dd5  mov     rcx, [rcx]
0x180004dd8  test    rcx, rcx
0x180004ddb  jz      short loc_180004DED
0x180004ddd  mov     [rdx], rax
0x180004de0  mov     rax, [rcx]
0x180004de3  mov     rax, [rax+10h]
0x180004de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dec  nop
0x180004ded  add     rsp, 28h
0x180004df1  retn
```
