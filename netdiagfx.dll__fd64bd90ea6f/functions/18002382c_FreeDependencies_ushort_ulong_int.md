# FreeDependencies(ushort * *,ulong,int)

- ea: `0x18002382c`
- end: `0x180023877`
- name: `?FreeDependencies@@YAXPEAPEAGKH@Z`
- size: `75`
- prototype: `void __fastcall(unsigned __int16 **pv, unsigned int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180023364`

## callees

- `0x18002382c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002384a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002384a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023866`

## pseudocode

```c
void __fastcall FreeDependencies(unsigned __int16 **pv, unsigned int a2, int a3)
{
  __int64 i; // rsi

  for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
  {
    CoTaskMemFree(pv[i]);
    pv[i] = 0;
  }
  if ( a3 )
    CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x18002382c  push    rbx
0x18002382e  push    rbp
0x18002382f  push    rsi
0x180023830  push    rdi
0x180023831  push    r14
0x180023833  sub     rsp, 20h
0x180023837  xor     esi, esi
0x180023839  mov     ebp, r8d
0x18002383c  mov     r14d, edx
0x18002383f  mov     rdi, rcx
0x180023842  test    edx, edx
0x180023844  jz      short loc_18002385F
0x180023846  mov     rcx, [rdi+rsi*8]; pv
0x18002384a  call    cs:__imp_CoTaskMemFree
0x180023850  mov     qword ptr [rdi+rsi*8], 0
0x180023858  inc     esi
0x18002385a  cmp     esi, r14d
0x18002385d  jb      short loc_180023846
0x18002385f  test    ebp, ebp
0x180023861  jz      short loc_18002386C
0x180023863  mov     rcx, rdi; pv
0x180023866  call    cs:__imp_CoTaskMemFree
0x18002386c  add     rsp, 20h
0x180023870  pop     r14
0x180023872  pop     rdi
0x180023873  pop     rsi
0x180023874  pop     rbp
0x180023875  pop     rbx
0x180023876  retn
```
