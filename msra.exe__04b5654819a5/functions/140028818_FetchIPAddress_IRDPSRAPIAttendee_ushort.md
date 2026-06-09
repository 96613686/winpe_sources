# FetchIPAddress(IRDPSRAPIAttendee *,ushort * *)

- ea: `0x140028818`
- end: `0x14002899f`
- name: `?FetchIPAddress@@YAJPEAUIRDPSRAPIAttendee@@PEAPEAG@Z`
- size: `391`
- prototype: `__int64 __fastcall(struct IRDPSRAPIAttendee *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002090c`
- `0x1400211f0`
- `0x140021e00`

## callees

- `0x1400187cc`
- `0x140028818`
- `0x140034ce4`
- `0x14004d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14002884d`
- `OLEAUT32!__imp_SysFreeString` at `0x140028979`
- `OLEAUT32!__imp_SysFreeString` at `0x140028988`
- `OLEAUT32!__imp_SysFreeString` at `0x14002884d`
- `OLEAUT32!__imp_SysFreeString` at `0x140028979`
- `OLEAUT32!__imp_SysFreeString` at `0x140028988`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1400288ed`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1400288ed`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1400288ff`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1400288ff`

## string_xrefs

- `0x140028928`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x1400288cd`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FetchIPAddress(struct IRDPSRAPIAttendee *a1, unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  signed int v4; // eax
  CEventLogger *v5; // rcx
  unsigned int v6; // r9d
  int v7; // eax
  unsigned __int16 *v8; // rax
  UINT v9; // eax
  int v11; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  BSTR bstr; // [rsp+68h] [rbp+28h] BYREF
  __int64 v14; // [rsp+70h] [rbp+30h] BYREF
  CEventLogger *v15; // [rsp+78h] [rbp+38h] BYREF

  v14 = 0;
  v15 = 0;
  bstr = 0;
  if ( !a2 )
  {
    SysFreeString(0);
    v3 = -2147467261;
    goto LABEL_20;
  }
  v4 = ((__int64 (__fastcall *)(struct IRDPSRAPIAttendee *, CEventLogger **))a1->lpVtbl->get_ConnectivityInfo)(a1, &v15);
  v3 = v4;
  if ( v4 >= 0 && (v5 = v15) != 0 )
  {
    v4 = (**(__int64 (__fastcall ***)(CEventLogger *, GUID *, __int64 *))v15)(
           v15,
           &GUID_f74049a4_3d06_4028_8193_0a8c29bc2452,
           &v14);
    v3 = v4;
    if ( v4 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v14 + 88LL))(v14, &bstr);
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x101B,
          (unsigned int)"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
          (const char *)(unsigned int)v7,
          v11);
      if ( bstr )
      {
        v9 = SysStringByteLen(bstr);
        v8 = SysAllocStringByteLen((LPCSTR)bstr, v9);
      }
      else
      {
        v8 = 0;
      }
      *a2 = v8;
      v3 = 0;
      goto LABEL_15;
    }
    v6 = 4116;
  }
  else
  {
    v6 = 4110;
  }
  CEventLogger::LogError(v5, &Recoverable_Error, L"base\\diagnosis\\ra\\ui\\commonfunc.cpp", v6, L"FetchIPAddress", v4);
LABEL_15:
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(CEventLogger *))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  SysFreeString(bstr);
LABEL_20:
  SysFreeString(0);
  return v3;
}

```

## disassembly

```asm
0x140028818  push    rbp
0x14002881a  push    rbx
0x14002881b  push    rdi
0x14002881c  mov     rbp, rsp
0x14002881f  sub     rsp, 40h
0x140028823  mov     rdi, rdx
0x140028826  mov     [rbp+arg_10], 0
0x14002882e  mov     [rbp+arg_18], 0
0x140028836  mov     [rbp+var_10], 0
0x14002883e  mov     [rbp+bstr], 0
0x140028846  test    rdx, rdx
0x140028849  jnz     short loc_140028863
0x14002884b  xor     ecx, ecx; bstrString
0x14002884d  call    cs:__imp_SysFreeString
0x140028854  nop     dword ptr [rax+rax+00h]
0x140028859  mov     ebx, 80004003h
0x14002885e  jmp     loc_140028986
0x140028863  mov     rax, [rcx]
0x140028866  lea     rdx, [rbp+arg_18]
0x14002886a  mov     rax, [rax+70h]
0x14002886e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028873  mov     ebx, eax
0x140028875  test    eax, eax
0x140028877  js      loc_140028912
0x14002887d  mov     rcx, [rbp+arg_18]
0x140028881  test    rcx, rcx
0x140028884  jz      loc_140028912
0x14002888a  mov     rax, [rcx]
0x14002888d  lea     r8, [rbp+arg_10]
0x140028891  lea     rdx, _GUID_f74049a4_3d06_4028_8193_0a8c29bc2452
0x140028898  mov     rax, [rax]
0x14002889b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400288a0  mov     ebx, eax
0x1400288a2  test    eax, eax
0x1400288a4  jns     short loc_1400288AE
0x1400288a6  mov     r9d, 1014h
0x1400288ac  jmp     short loc_140028918
0x1400288ae  mov     rcx, [rbp+arg_10]
0x1400288b2  mov     rax, [rcx]
0x1400288b5  lea     rdx, [rbp+bstr]
0x1400288b9  mov     rax, [rax+58h]
0x1400288bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400288c2  mov     rcx, [rbp+18h]; this
0x1400288c6  test    eax, eax
0x1400288c8  jns     short loc_1400288DE
0x1400288ca  mov     r9d, eax; char *
0x1400288cd  lea     r8, aBaseDiagnosisR_1; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x1400288d4  mov     edx, 101Bh; void *
0x1400288d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400288de  cmp     [rbp+bstr], 0
0x1400288e3  jnz     short loc_1400288E9
0x1400288e5  xor     eax, eax
0x1400288e7  jmp     short loc_14002890B
0x1400288e9  mov     rcx, [rbp+bstr]; bstr
0x1400288ed  call    cs:__imp_SysStringByteLen
0x1400288f4  nop     dword ptr [rax+rax+00h]
0x1400288f9  mov     edx, eax; len
0x1400288fb  mov     rcx, [rbp+bstr]; psz
0x1400288ff  call    cs:__imp_SysAllocStringByteLen
0x140028906  nop     dword ptr [rax+rax+00h]
0x14002890b  mov     [rdi], rax
0x14002890e  xor     ebx, ebx
0x140028910  jmp     short loc_14002893B
0x140028912  mov     r9d, 100Eh; unsigned int
0x140028918  mov     [rsp+40h+var_18], eax; unsigned int
0x14002891c  lea     rax, aFetchipaddress; "FetchIPAddress"
0x140028923  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x140028928  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002892f  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140028936  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002893b  mov     rcx, [rbp+arg_10]
0x14002893f  test    rcx, rcx
0x140028942  jz      short loc_140028958
0x140028944  mov     rax, [rcx]
0x140028947  mov     rax, [rax+10h]
0x14002894b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140028950  mov     [rbp+arg_10], 0
0x140028958  mov     rcx, [rbp+arg_18]
0x14002895c  test    rcx, rcx
0x14002895f  jz      short loc_140028975
0x140028961  mov     rax, [rcx]
0x140028964  mov     rax, [rax+10h]
0x140028968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002896d  mov     [rbp+arg_18], 0
0x140028975  mov     rcx, [rbp+bstr]; bstrString
0x140028979  call    cs:__imp_SysFreeString
0x140028980  nop     dword ptr [rax+rax+00h]
0x140028985  nop
0x140028986  xor     ecx, ecx; bstrString
0x140028988  call    cs:__imp_SysFreeString
0x14002898f  nop     dword ptr [rax+rax+00h]
0x140028994  mov     eax, ebx
0x140028996  add     rsp, 40h
0x14002899a  pop     rdi
0x14002899b  pop     rbx
0x14002899c  pop     rbp
0x14002899d  retn
```
