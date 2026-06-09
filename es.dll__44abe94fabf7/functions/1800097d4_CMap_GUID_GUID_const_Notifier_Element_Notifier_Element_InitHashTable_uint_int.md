# CMap<_GUID,_GUID const &,Notifier::Element *,Notifier::Element * &>::InitHashTable(uint,int)

- ea: `0x1800097d4`
- end: `0x180009854`
- name: `?InitHashTable@?$CMap@U_GUID@@AEBU1@PEAUElement@Notifier@@AEAPEAU23@@@QEAAJIH@Z`
- size: `128`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b214`
- `0x18000b568`
- `0x18000b6e4`
- `0x18000cd8c`

## callees

- `0x1800097ac`
- `0x1800097d4`
- `0x1800434c6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009818`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800097f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800097f5`

## pseudocode

```c
__int64 __fastcall CMap<_GUID,_GUID const &,Notifier::Element *,Notifier::Element * &>::InitHashTable(__int64 a1)
{
  unsigned __int64 v2; // rdi
  void *v3; // rax
  __int64 result; // rax

  v2 = (unsigned int)CMap<CString,unsigned short const *,RegRow *,RegRow *>::RoundUpToPrime();
  if ( *(_QWORD *)a1 )
  {
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
  }
  v3 = CoTaskMemAlloc(saturated_mul(v2, 8u));
  *(_QWORD *)a1 = v3;
  if ( !v3 )
    return 2147942414LL;
  memset_0(v3, 0, 8 * v2);
  result = 0;
  *(_DWORD *)(a1 + 8) = v2;
  return result;
}

```

## disassembly

```asm
0x1800097d4  mov     [rsp+arg_0], rbx
0x1800097d9  mov     [rsp+arg_8], rsi
0x1800097de  push    rdi
0x1800097df  sub     rsp, 20h
0x1800097e3  mov     rbx, rcx
0x1800097e6  call    ?RoundUpToPrime@?$CMap@VCString@@PEBGPEAVRegRow@@PEAV2@@@IEBAII@Z; CMap<CString,ushort const *,RegRow *,RegRow *>::RoundUpToPrime(uint)
0x1800097eb  mov     rcx, [rbx]; pv
0x1800097ee  mov     edi, eax
0x1800097f0  test    rcx, rcx
0x1800097f3  jz      short loc_180009802
0x1800097f5  call    cs:__imp_CoTaskMemFree
0x1800097fb  mov     qword ptr [rbx], 0
0x180009802  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180009809  mov     eax, 8
0x18000980e  mul     rdi
0x180009811  cmovb   rax, rcx
0x180009815  mov     rcx, rax; cb
0x180009818  call    cs:__imp_CoTaskMemAlloc
0x18000981e  mov     [rbx], rax
0x180009821  test    rax, rax
0x180009824  jnz     short loc_18000982D
0x180009826  mov     eax, 8007000Eh
0x18000982b  jmp     short loc_180009844
0x18000982d  lea     r8, ds:0[rdi*8]; Size
0x180009835  xor     edx, edx; Val
0x180009837  mov     rcx, rax; void *
0x18000983a  call    memset_0
0x18000983f  xor     eax, eax
0x180009841  mov     [rbx+8], edi
0x180009844  mov     rbx, [rsp+28h+arg_0]
0x180009849  mov     rsi, [rsp+28h+arg_8]
0x18000984e  add     rsp, 20h
0x180009852  pop     rdi
0x180009853  retn
```
