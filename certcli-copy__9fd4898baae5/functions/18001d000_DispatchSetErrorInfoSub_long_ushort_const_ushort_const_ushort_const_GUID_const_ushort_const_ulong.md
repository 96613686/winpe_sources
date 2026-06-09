# DispatchSetErrorInfoSub(long,ushort const *,ushort const *,ushort const *,_GUID const *,ushort const *,ulong)

- ea: `0x18001d000`
- end: `0x18001d145`
- name: `?DispatchSetErrorInfoSub@@YAJJPEBG00PEBU_GUID@@0K@Z`
- size: `325`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, IErrorInfo *perrinfo, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000daa0`
- `0x18001ced4`

## callees

- `0x18001d000`
- `0x18003f010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x18001d0ff`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001d0ff`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18001d02e`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18001d02e`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d041`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d072`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d09c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d0c6`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d041`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d072`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d09c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d0c6`

## pseudocode

```c
__int64 __fastcall DispatchSetErrorInfoSub(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const struct _GUID *a5,
        IErrorInfo *perrinfo)
{
  HRESULT v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // ecx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  ICreateErrorInfo *v15; // [rsp+38h] [rbp+10h] BYREF

  v15 = 0;
  perrinfo = 0;
  v8 = CreateErrorInfo(&v15);
  v9 = v8;
  if ( v8 )
  {
    v10 = 10158506;
LABEL_3:
    CSPrintErrorLineFile(v10, v8);
    goto LABEL_16;
  }
  if ( a5 )
  {
    v11 = ((__int64 (__fastcall *)(ICreateErrorInfo *))v15->lpVtbl->SetGUID)(v15);
    if ( v11 )
      CSPrintErrorLineFile(0xA001AAu, v11);
  }
  if ( a4 )
  {
    v12 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))v15->lpVtbl->SetSource)(v15, a4);
    if ( v12 )
      CSPrintErrorLineFile(0xA501AAu, v12);
  }
  if ( a3 )
  {
    v13 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))v15->lpVtbl->SetDescription)(v15, a3);
    if ( v13 )
      CSPrintErrorLineFile(0xAB01AAu, v13);
  }
  v8 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))v15->lpVtbl->QueryInterface)(
         v15,
         &IID_IErrorInfo,
         &perrinfo);
  v9 = v8;
  if ( v8 )
  {
    v10 = 12124586;
    goto LABEL_3;
  }
  SetErrorInfo(0, perrinfo);
  v9 = 0;
LABEL_16:
  if ( perrinfo )
    ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
  if ( v15 )
    ((void (__fastcall *)(ICreateErrorInfo *))v15->lpVtbl->Release)(v15);
  return v9;
}

```

## disassembly

```asm
0x18001d000  mov     rax, rsp
0x18001d003  mov     [rax+8], rbx
0x18001d007  mov     [rax+18h], rsi
0x18001d00b  mov     [rax+10h], rdx
0x18001d00f  push    rdi
0x18001d010  sub     rsp, 20h
0x18001d014  lea     rcx, [rax+10h]; pperrinfo
0x18001d018  mov     qword ptr [rax+10h], 0
0x18001d020  mov     rdi, r9
0x18001d023  mov     qword ptr [rax+30h], 0
0x18001d02b  mov     rsi, r8
0x18001d02e  call    cs:__imp_CreateErrorInfo
0x18001d034  mov     ebx, eax
0x18001d036  test    eax, eax
0x18001d038  jz      short loc_18001D04C
0x18001d03a  mov     ecx, 9B01AAh
0x18001d03f  mov     edx, eax
0x18001d041  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001d047  jmp     loc_18001D107
0x18001d04c  mov     rdx, [rsp+28h+arg_20]
0x18001d051  test    rdx, rdx
0x18001d054  jz      short loc_18001D078
0x18001d056  mov     rcx, [rsp+28h+arg_8]
0x18001d05b  mov     rax, [rcx]
0x18001d05e  mov     rax, [rax+18h]
0x18001d062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d067  test    eax, eax
0x18001d069  jz      short loc_18001D078
0x18001d06b  mov     edx, eax
0x18001d06d  mov     ecx, 0A001AAh
0x18001d072  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001d078  test    rdi, rdi
0x18001d07b  jz      short loc_18001D0A2
0x18001d07d  mov     rcx, [rsp+28h+arg_8]
0x18001d082  mov     rdx, rdi
0x18001d085  mov     rax, [rcx]
0x18001d088  mov     rax, [rax+20h]
0x18001d08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d091  test    eax, eax
0x18001d093  jz      short loc_18001D0A2
0x18001d095  mov     edx, eax
0x18001d097  mov     ecx, 0A501AAh
0x18001d09c  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001d0a2  test    rsi, rsi
0x18001d0a5  jz      short loc_18001D0CC
0x18001d0a7  mov     rcx, [rsp+28h+arg_8]
0x18001d0ac  mov     rdx, rsi
0x18001d0af  mov     rax, [rcx]
0x18001d0b2  mov     rax, [rax+28h]
0x18001d0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0bb  test    eax, eax
0x18001d0bd  jz      short loc_18001D0CC
0x18001d0bf  mov     edx, eax
0x18001d0c1  mov     ecx, 0AB01AAh
0x18001d0c6  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001d0cc  mov     rcx, [rsp+28h+arg_8]
0x18001d0d1  lea     r8, [rsp+28h+perrinfo]
0x18001d0d6  lea     rdx, IID_IErrorInfo
0x18001d0dd  mov     rax, [rcx]
0x18001d0e0  mov     rax, [rax]
0x18001d0e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0e8  mov     ebx, eax
0x18001d0ea  test    eax, eax
0x18001d0ec  jz      short loc_18001D0F8
0x18001d0ee  mov     ecx, 0B901AAh
0x18001d0f3  jmp     loc_18001D03F
0x18001d0f8  mov     rdx, [rsp+28h+perrinfo]; perrinfo
0x18001d0fd  xor     ecx, ecx; dwReserved
0x18001d0ff  call    cs:__imp_SetErrorInfo
0x18001d105  xor     ebx, ebx
0x18001d107  mov     rcx, [rsp+28h+perrinfo]
0x18001d10c  test    rcx, rcx
0x18001d10f  jz      short loc_18001D11D
0x18001d111  mov     rax, [rcx]
0x18001d114  mov     rax, [rax+10h]
0x18001d118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d11d  mov     rcx, [rsp+28h+arg_8]
0x18001d122  test    rcx, rcx
0x18001d125  jz      short loc_18001D133
0x18001d127  mov     rax, [rcx]
0x18001d12a  mov     rax, [rax+10h]
0x18001d12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d133  mov     rsi, [rsp+28h+arg_10]
0x18001d138  mov     eax, ebx
0x18001d13a  mov     rbx, [rsp+28h+arg_0]
0x18001d13f  add     rsp, 20h
0x18001d143  pop     rdi
0x18001d144  retn
```
