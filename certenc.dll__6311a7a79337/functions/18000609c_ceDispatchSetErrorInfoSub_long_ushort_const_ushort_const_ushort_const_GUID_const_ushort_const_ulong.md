# ceDispatchSetErrorInfoSub(long,ushort const *,ushort const *,ushort const *,_GUID const *,ushort const *,ulong)

- ea: `0x18000609c`
- end: `0x180006190`
- name: `?ceDispatchSetErrorInfoSub@@YAJJPEBG00PEBU_GUID@@0K@Z`
- size: `244`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, IErrorInfo *perrinfo, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180005f70`

## callees

- `0x18000609c`
- `0x180009010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18000614c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000614c`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800060ca`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800060ca`

## pseudocode

```c
__int64 __fastcall ceDispatchSetErrorInfoSub(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const struct _GUID *a5,
        IErrorInfo *perrinfo)
{
  unsigned int v8; // ebx
  ICreateErrorInfo *v10; // [rsp+38h] [rbp+10h] BYREF

  v10 = 0;
  perrinfo = 0;
  v8 = CreateErrorInfo(&v10);
  if ( !v8 )
  {
    if ( a5 )
      ((void (__fastcall *)(ICreateErrorInfo *))v10->lpVtbl->SetGUID)(v10);
    if ( a4 )
      ((void (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))v10->lpVtbl->SetSource)(v10, a4);
    if ( a3 )
      ((void (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))v10->lpVtbl->SetDescription)(v10, a3);
    v8 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))v10->lpVtbl->QueryInterface)(
           v10,
           &IID_IErrorInfo,
           &perrinfo);
    if ( !v8 )
      SetErrorInfo(0, perrinfo);
  }
  if ( perrinfo )
    ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
  if ( v10 )
    ((void (__fastcall *)(ICreateErrorInfo *))v10->lpVtbl->Release)(v10);
  return v8;
}

```

## disassembly

```asm
0x18000609c  mov     rax, rsp
0x18000609f  mov     [rax+8], rbx
0x1800060a3  mov     [rax+18h], rsi
0x1800060a7  mov     [rax+10h], rdx
0x1800060ab  push    rdi
0x1800060ac  sub     rsp, 20h
0x1800060b0  lea     rcx, [rax+10h]; pperrinfo
0x1800060b4  mov     qword ptr [rax+10h], 0
0x1800060bc  mov     rsi, r9
0x1800060bf  mov     qword ptr [rax+30h], 0
0x1800060c7  mov     rdi, r8
0x1800060ca  call    cs:__imp_CreateErrorInfo
0x1800060d0  mov     ebx, eax
0x1800060d2  test    eax, eax
0x1800060d4  jnz     short loc_180006152
0x1800060d6  mov     rdx, [rsp+28h+arg_20]
0x1800060db  test    rdx, rdx
0x1800060de  jz      short loc_1800060F1
0x1800060e0  mov     rcx, [rsp+28h+arg_8]
0x1800060e5  mov     rax, [rcx]
0x1800060e8  mov     rax, [rax+18h]
0x1800060ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060f1  test    rsi, rsi
0x1800060f4  jz      short loc_18000610A
0x1800060f6  mov     rcx, [rsp+28h+arg_8]
0x1800060fb  mov     rdx, rsi
0x1800060fe  mov     rax, [rcx]
0x180006101  mov     rax, [rax+20h]
0x180006105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000610a  test    rdi, rdi
0x18000610d  jz      short loc_180006123
0x18000610f  mov     rcx, [rsp+28h+arg_8]
0x180006114  mov     rdx, rdi
0x180006117  mov     rax, [rcx]
0x18000611a  mov     rax, [rax+28h]
0x18000611e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006123  mov     rcx, [rsp+28h+arg_8]
0x180006128  lea     r8, [rsp+28h+perrinfo]
0x18000612d  lea     rdx, IID_IErrorInfo
0x180006134  mov     rax, [rcx]
0x180006137  mov     rax, [rax]
0x18000613a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000613f  mov     ebx, eax
0x180006141  test    eax, eax
0x180006143  jnz     short loc_180006152
0x180006145  mov     rdx, [rsp+28h+perrinfo]; perrinfo
0x18000614a  xor     ecx, ecx; dwReserved
0x18000614c  call    cs:__imp_SetErrorInfo
0x180006152  mov     rcx, [rsp+28h+perrinfo]
0x180006157  test    rcx, rcx
0x18000615a  jz      short loc_180006168
0x18000615c  mov     rax, [rcx]
0x18000615f  mov     rax, [rax+10h]
0x180006163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006168  mov     rcx, [rsp+28h+arg_8]
0x18000616d  test    rcx, rcx
0x180006170  jz      short loc_18000617E
0x180006172  mov     rax, [rcx]
0x180006175  mov     rax, [rax+10h]
0x180006179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000617e  mov     rsi, [rsp+28h+arg_10]
0x180006183  mov     eax, ebx
0x180006185  mov     rbx, [rsp+28h+arg_0]
0x18000618a  add     rsp, 20h
0x18000618e  pop     rdi
0x18000618f  retn
```
