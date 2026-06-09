# FillErrorInfo(ushort const *,ulong)

- ea: `0x180039780`
- end: `0x180039889`
- name: `?FillErrorInfo@@YAJPEBGK@Z`
- size: `265`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180039a74`

## callees

- `0x180039780`
- `0x18003fd88`
- `0x180045020`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x180039854`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180039854`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800397af`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800397af`

## string_xrefs

- `0x1800397fa`: `complib.hlp`

## pseudocode

```c
HRESULT __fastcall FillErrorInfo(const unsigned __int16 *a1, unsigned int a2)
{
  HRESULT result; // eax
  int v3; // ebx
  ICreateErrorInfo *v4; // [rsp+20h] [rbp-48h] BYREF
  IErrorInfo *perrinfo; // [rsp+28h] [rbp-40h] BYREF

  v4 = 0;
  perrinfo = 0;
  result = CreateErrorInfo(&v4);
  if ( result >= 0 )
  {
    v3 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const unsigned __int16 *))v4->lpVtbl->SetDescription)(v4, a1);
    if ( v3 >= 0 )
    {
      v3 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const wchar_t *))v4->lpVtbl->SetHelpFile)(v4, L"complib.hlp");
      if ( v3 >= 0 )
      {
        v3 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))v4->lpVtbl->SetHelpContext)(v4, a2);
        if ( v3 >= 0 )
        {
          v3 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))v4->lpVtbl->QueryInterface)(
                 v4,
                 &IID_IErrorInfo,
                 &perrinfo);
          if ( v3 >= 0 )
            SetErrorInfo(0, perrinfo);
        }
      }
    }
    ((void (__fastcall *)(ICreateErrorInfo *))v4->lpVtbl->Release)(v4);
    if ( perrinfo )
      ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180039780  mov     rax, rsp
0x180039783  mov     [rax+10h], edx
0x180039786  mov     [rax+8], rcx
0x18003978a  push    rbx
0x18003978b  sub     rsp, 60h
0x18003978f  mov     qword ptr [rax-48h], 0
0x180039797  mov     qword ptr [rax-40h], 0
0x18003979f  mov     [rsp+68h+arg_10], 0
0x1800397ab  lea     rcx, [rax-48h]; pperrinfo
0x1800397af  call    cs:__imp_CreateErrorInfo
0x1800397b5  nop
0x1800397b6  jmp     short loc_1800397CE
0x1800397b8  cmp     [rsp+68h+arg_18], 0
0x1800397c0  jz      short loc_1800397C7
0x1800397c2  call    ?HandleStackOverflowAfterCatch@@YAXXZ; HandleStackOverflowAfterCatch(void)
0x1800397c7  mov     eax, dword ptr [rsp+68h+arg_10]
0x1800397ce  test    eax, eax
0x1800397d0  js      loc_180039883
0x1800397d6  mov     rcx, [rsp+68h+var_48]
0x1800397db  mov     rax, [rcx]
0x1800397de  mov     rdx, [rsp+68h+arg_0]
0x1800397e3  mov     rax, [rax+28h]
0x1800397e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800397ec  mov     ebx, eax
0x1800397ee  test    eax, eax
0x1800397f0  js      short loc_18003985A
0x1800397f2  mov     rcx, [rsp+68h+var_48]
0x1800397f7  mov     rax, [rcx]
0x1800397fa  lea     rdx, aComplibHlp; "complib.hlp"
0x180039801  mov     rax, [rax+30h]
0x180039805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003980a  mov     ebx, eax
0x18003980c  test    eax, eax
0x18003980e  js      short loc_18003985A
0x180039810  mov     rcx, [rsp+68h+var_48]
0x180039815  mov     rax, [rcx]
0x180039818  mov     edx, [rsp+68h+arg_8]
0x18003981c  mov     rax, [rax+38h]
0x180039820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039825  mov     ebx, eax
0x180039827  test    eax, eax
0x180039829  js      short loc_18003985A
0x18003982b  mov     rcx, [rsp+68h+var_48]
0x180039830  mov     rax, [rcx]
0x180039833  lea     r8, [rsp+68h+perrinfo]
0x180039838  lea     rdx, IID_IErrorInfo
0x18003983f  mov     rax, [rax]
0x180039842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039847  mov     ebx, eax
0x180039849  test    eax, eax
0x18003984b  js      short loc_18003985A
0x18003984d  mov     rdx, [rsp+68h+perrinfo]; perrinfo
0x180039852  xor     ecx, ecx; dwReserved
0x180039854  call    cs:__imp_SetErrorInfo
0x18003985a  mov     rcx, [rsp+68h+var_48]
0x18003985f  mov     rax, [rcx]
0x180039862  mov     rax, [rax+10h]
0x180039866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003986b  mov     rcx, [rsp+68h+perrinfo]
0x180039870  test    rcx, rcx
0x180039873  jz      short loc_180039881
0x180039875  mov     rax, [rcx]
0x180039878  mov     rax, [rax+10h]
0x18003987c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039881  mov     eax, ebx
0x180039883  add     rsp, 60h
0x180039887  pop     rbx
0x180039888  retn
```
