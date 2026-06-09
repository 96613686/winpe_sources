# ChildNodeNames::~ChildNodeNames(void)

- ea: `0x180011120`
- end: `0x18001117d`
- name: `??1ChildNodeNames@@QEAA@XZ`
- size: `93`
- prototype: `void __fastcall(ChildNodeNames *__hidden this)`
- caller_count: `13`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b1e0`
- `0x18000f58c`
- `0x18000f7a4`
- `0x18000f954`
- `0x180010480`
- `0x180010f00`
- `0x180011630`
- `0x1800122f0`
- `0x1800170f0`
- `0x180025d40`
- `0x1800362a7`
- `0x1800364dd`
- `0x180036679`

## callees

- `0x180011120`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011160`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011160`
- `OLEAUT32!__imp_SysFreeString` at `0x180011145`
- `OLEAUT32!__imp_SysFreeString` at `0x180011145`

## pseudocode

```c
void __fastcall ChildNodeNames::~ChildNodeNames(ChildNodeNames *this)
{
  __int64 v1; // rsi
  __int64 i; // rdi

  v1 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
      SysFreeString(*(BSTR *)(v1 + 8 * i));
  }
  if ( *(_QWORD *)this )
    CoTaskMemFree(*(LPVOID *)this);
}

```

## disassembly

```asm
0x180011120  mov     [rsp+arg_0], rbx
0x180011125  mov     [rsp+arg_8], rsi
0x18001112a  push    rdi
0x18001112b  sub     rsp, 20h
0x18001112f  mov     rsi, [rcx]
0x180011132  mov     rbx, rcx
0x180011135  test    rsi, rsi
0x180011138  jz      short loc_180011158
0x18001113a  xor     edi, edi
0x18001113c  cmp     [rcx+8], edi
0x18001113f  jbe     short loc_180011158
0x180011141  mov     rcx, [rsi+rdi*8]; bstrString
0x180011145  call    cs:__imp_SysFreeString
0x18001114c  nop     dword ptr [rax+rax+00h]
0x180011151  inc     edi
0x180011153  cmp     edi, [rbx+8]
0x180011156  jb      short loc_180011141
0x180011158  mov     rcx, [rbx]; pv
0x18001115b  test    rcx, rcx
0x18001115e  jz      short loc_18001116C
0x180011160  call    cs:__imp_CoTaskMemFree
0x180011167  nop     dword ptr [rax+rax+00h]
0x18001116c  mov     rbx, [rsp+28h+arg_0]
0x180011171  mov     rsi, [rsp+28h+arg_8]
0x180011176  add     rsp, 20h
0x18001117a  pop     rdi
0x18001117b  retn
```
