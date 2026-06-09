# EventMethod::~EventMethod(void)

- ea: `0x18001dff0`
- end: `0x18001e09c`
- name: `??1EventMethod@@AEAA@XZ`
- size: `172`
- prototype: `void __fastcall(EventMethod *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001df50`

## callees

- `0x18001dff0`
- `0x18003f080`
- `0x180046010`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18001e05c`
- `msvcrt!_resetstkoflw` at `0x18001e05c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e086`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e086`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e037`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e037`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e01c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e02d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e01c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e02d`

## pseudocode

```c
void __fastcall EventMethod::~EventMethod(EventMethod *this)
{
  int i; // edi
  __int64 v3; // rcx
  __int64 v4; // rcx

  for ( i = 0; i < *((_DWORD *)this + 22); ++i )
    CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 12) + 16LL * i));
  CoTaskMemFree(*((LPVOID *)this + 12));
  SysFreeString(*((BSTR *)this + 1));
  v3 = *((_QWORD *)this + 2);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 9);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( *((_DWORD *)this + 16) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x18001dff0  mov     [rsp+arg_8], rbx
0x18001dff5  mov     [rsp+arg_10], rsi
0x18001dffa  mov     [rsp+arg_0], rcx
0x18001dfff  push    rdi
0x18001e000  sub     rsp, 40h
0x18001e004  mov     rbx, rcx
0x18001e007  xor     edi, edi
0x18001e009  cmp     [rcx+58h], edi
0x18001e00c  jle     short loc_18001E029
0x18001e00e  movsxd  rax, edi
0x18001e011  add     rax, rax
0x18001e014  mov     rcx, [rbx+60h]
0x18001e018  mov     rcx, [rcx+rax*8]; pv
0x18001e01c  call    cs:__imp_CoTaskMemFree
0x18001e022  inc     edi
0x18001e024  cmp     edi, [rbx+58h]
0x18001e027  jl      short loc_18001E00E
0x18001e029  mov     rcx, [rbx+60h]; pv
0x18001e02d  call    cs:__imp_CoTaskMemFree
0x18001e033  mov     rcx, [rbx+8]; bstrString
0x18001e037  call    cs:__imp_SysFreeString
0x18001e03d  nop
0x18001e03e  mov     rcx, [rbx+10h]
0x18001e042  test    rcx, rcx
0x18001e045  jz      short loc_18001E053
0x18001e047  mov     rax, [rcx]
0x18001e04a  mov     rax, [rax+10h]
0x18001e04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e053  jmp     short loc_18001E067
0x18001e055  cmp     eax, 0C00000FDh
0x18001e05a  jnz     short loc_18001E062
0x18001e05c  call    cs:__imp__resetstkoflw
0x18001e062  mov     rbx, [rsp+48h+arg_0]
0x18001e067  mov     rcx, [rbx+48h]
0x18001e06b  test    rcx, rcx
0x18001e06e  jz      short loc_18001E07C
0x18001e070  mov     rax, [rcx]
0x18001e073  mov     rax, [rax+10h]
0x18001e077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e07c  lea     rcx, [rbx+18h]; lpCriticalSection
0x18001e080  cmp     dword ptr [rcx+28h], 0
0x18001e084  jz      short loc_18001E08C
0x18001e086  call    cs:__imp_DeleteCriticalSection
0x18001e08c  mov     rbx, [rsp+48h+arg_8]
0x18001e091  mov     rsi, [rsp+48h+arg_10]
0x18001e096  add     rsp, 40h
0x18001e09a  pop     rdi
0x18001e09b  retn
0x180044b00  push    rbp
0x180044b02  sub     rsp, 30h
0x180044b06  mov     rbp, rdx
0x180044b09  lea     rax, [rbp+30h]
0x180044b0d  mov     [rsp+38h+var_18], rax; int *
0x180044b12  call    ?MethodCallExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@GAEBU_GUID@@PEBGAEAJ@Z; MethodCallExceptionFilter(_EXCEPTION_POINTERS *,ushort,_GUID const &,ushort const *,long &)
0x180044b17  nop
0x180044b18  add     rsp, 30h
0x180044b1c  pop     rbp
0x180044b1d  retn
```
