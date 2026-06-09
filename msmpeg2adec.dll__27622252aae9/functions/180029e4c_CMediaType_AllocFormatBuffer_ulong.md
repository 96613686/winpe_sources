# CMediaType::AllocFormatBuffer(ulong)

- ea: `0x180029e4c`
- end: `0x180029ec2`
- name: `?AllocFormatBuffer@CMediaType@@QEAAPEAEK@Z`
- size: `118`
- prototype: `unsigned __int8 *(CMediaType *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000bda0`
- `0x18001d940`

## callees

- `0x180029e4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029e6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029e6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029e9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029e9b`

## pseudocode

```c
unsigned __int8 *__fastcall CMediaType::AllocFormatBuffer(CMediaType *this, unsigned int a2)
{
  unsigned __int8 *result; // rax
  unsigned __int8 *v5; // rsi

  if ( *((_DWORD *)this + 18) == a2 )
    return (unsigned __int8 *)*((_QWORD *)this + 10);
  v5 = (unsigned __int8 *)CoTaskMemAlloc(a2);
  if ( v5 )
  {
    if ( *((_DWORD *)this + 18) )
      CoTaskMemFree(*((LPVOID *)this + 10));
    *((_DWORD *)this + 18) = a2;
    result = v5;
    *((_QWORD *)this + 10) = v5;
  }
  else if ( a2 > *((_DWORD *)this + 18) )
  {
    return 0;
  }
  else
  {
    return (unsigned __int8 *)*((_QWORD *)this + 10);
  }
  return result;
}

```

## disassembly

```asm
0x180029e4c  mov     [rsp+arg_0], rbx
0x180029e51  mov     [rsp+arg_8], rsi
0x180029e56  push    rdi
0x180029e57  sub     rsp, 20h
0x180029e5b  mov     rbx, rcx
0x180029e5e  mov     edi, edx
0x180029e60  cmp     [rcx+48h], edx
0x180029e63  jnz     short loc_180029E6B
0x180029e65  mov     rax, [rcx+50h]
0x180029e69  jmp     short loc_180029EB1
0x180029e6b  mov     rcx, rdi; cb
0x180029e6e  call    cs:__imp_CoTaskMemAlloc
0x180029e75  nop     dword ptr [rax+rax+00h]
0x180029e7a  mov     rsi, rax
0x180029e7d  test    rax, rax
0x180029e80  jnz     short loc_180029E91
0x180029e82  cmp     edi, [rbx+48h]
0x180029e85  ja      short loc_180029E8D
0x180029e87  mov     rax, [rbx+50h]
0x180029e8b  jmp     short loc_180029EB1
0x180029e8d  xor     eax, eax
0x180029e8f  jmp     short loc_180029EB1
0x180029e91  cmp     dword ptr [rbx+48h], 0
0x180029e95  jz      short loc_180029EA7
0x180029e97  mov     rcx, [rbx+50h]; pv
0x180029e9b  call    cs:__imp_CoTaskMemFree
0x180029ea2  nop     dword ptr [rax+rax+00h]
0x180029ea7  mov     [rbx+48h], edi
0x180029eaa  mov     rax, rsi
0x180029ead  mov     [rbx+50h], rsi
0x180029eb1  mov     rbx, [rsp+28h+arg_0]
0x180029eb6  mov     rsi, [rsp+28h+arg_8]
0x180029ebb  add     rsp, 20h
0x180029ebf  pop     rdi
0x180029ec0  retn
```
