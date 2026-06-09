# GetLastComError(void)

- ea: `0x18000c330`
- end: `0x18000c42f`
- name: `?GetLastComError@@YA?AVCComBSTR@ATL@@XZ`
- size: `255`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004a40`
- `0x1800056e8`
- `0x18000701c`
- `0x18000d830`
- `0x180012e0c`
- `0x1800165b4`

## callees

- `0x180002ac4`
- `0x18000c330`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000c347`
- `OLEAUT32!__imp_SysAllocString` at `0x18000c347`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c3b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c405`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c3b5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c405`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c3a2`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c3a2`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000c3cb`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000c3cb`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000c3d7`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000c3d7`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18000c367`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18000c367`

## pseudocode

```c
BSTR *__fastcall GetLastComError(BSTR *a1)
{
  BSTR v2; // rax
  BSTR v3; // rax
  BSTR v4; // rcx
  UINT v5; // eax
  BSTR pbstr; // [rsp+38h] [rbp+18h] BYREF
  IErrorInfo *pperrinfo; // [rsp+40h] [rbp+20h] BYREF

  v2 = SysAllocString(L"<no description>");
  *a1 = v2;
  if ( !v2 )
    ATL::AtlThrowImpl(-2147024882);
  pperrinfo = 0;
  if ( GetErrorInfo(0, &pperrinfo) >= 0 && pperrinfo )
  {
    pbstr = 0;
    if ( ((int (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo->lpVtbl->GetDescription)(pperrinfo, &pbstr) >= 0
      && SysStringLen(pbstr)
      && *a1 != pbstr )
    {
      SysFreeString(*a1);
      v3 = pbstr;
      if ( pbstr )
      {
        v5 = SysStringByteLen(pbstr);
        v4 = SysAllocStringByteLen((LPCSTR)pbstr, v5);
        v3 = pbstr;
      }
      else
      {
        v4 = 0;
      }
      *a1 = v4;
      if ( v3 && !v4 )
        ATL::AtlThrowImpl(-2147024882);
    }
    ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
    SysFreeString(pbstr);
  }
  return a1;
}

```

## disassembly

```asm
0x18000c330  mov     [rsp-8+arg_0], rbx
0x18000c335  push    rbp
0x18000c336  mov     rbp, rsp
0x18000c339  sub     rsp, 20h
0x18000c33d  mov     rbx, rcx
0x18000c340  lea     rcx, aNoDescription; "<no description>"
0x18000c347  call    cs:__imp_SysAllocString
0x18000c34d  mov     [rbx], rax
0x18000c350  test    rax, rax
0x18000c353  jz      loc_18000C424
0x18000c359  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18000c35d  mov     [rbp+pperrinfo], 0
0x18000c365  xor     ecx, ecx; dwReserved
0x18000c367  call    cs:__imp_GetErrorInfo
0x18000c36d  test    eax, eax
0x18000c36f  js      loc_18000C40B
0x18000c375  mov     rcx, [rbp+pperrinfo]
0x18000c379  test    rcx, rcx
0x18000c37c  jz      loc_18000C40B
0x18000c382  mov     [rbp+pbstr], 0
0x18000c38a  lea     rdx, [rbp+pbstr]
0x18000c38e  mov     rax, [rcx]
0x18000c391  mov     rax, [rax+28h]
0x18000c395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c39a  test    eax, eax
0x18000c39c  js      short loc_18000C3F1
0x18000c39e  mov     rcx, [rbp+pbstr]; pbstr
0x18000c3a2  call    cs:__imp_SysStringLen
0x18000c3a8  test    eax, eax
0x18000c3aa  jz      short loc_18000C3F1
0x18000c3ac  mov     rcx, [rbx]; bstrString
0x18000c3af  cmp     rcx, [rbp+pbstr]
0x18000c3b3  jz      short loc_18000C3F1
0x18000c3b5  call    cs:__imp_SysFreeString
0x18000c3bb  mov     rax, [rbp+pbstr]
0x18000c3bf  test    rax, rax
0x18000c3c2  jnz     short loc_18000C3C8
0x18000c3c4  xor     ecx, ecx
0x18000c3c6  jmp     short loc_18000C3E4
0x18000c3c8  mov     rcx, rax; bstr
0x18000c3cb  call    cs:__imp_SysStringByteLen
0x18000c3d1  mov     rcx, [rbp+pbstr]; psz
0x18000c3d5  mov     edx, eax; len
0x18000c3d7  call    cs:__imp_SysAllocStringByteLen
0x18000c3dd  mov     rcx, rax
0x18000c3e0  mov     rax, [rbp+pbstr]
0x18000c3e4  mov     [rbx], rcx
0x18000c3e7  test    rax, rax
0x18000c3ea  jz      short loc_18000C3F1
0x18000c3ec  test    rcx, rcx
0x18000c3ef  jz      short loc_18000C419
0x18000c3f1  mov     rcx, [rbp+pperrinfo]
0x18000c3f5  mov     rax, [rcx]
0x18000c3f8  mov     rax, [rax+10h]
0x18000c3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c401  mov     rcx, [rbp+pbstr]; bstrString
0x18000c405  call    cs:__imp_SysFreeString
0x18000c40b  mov     rax, rbx
0x18000c40e  mov     rbx, [rsp+20h+arg_0]
0x18000c413  add     rsp, 20h
0x18000c417  pop     rbp
0x18000c418  retn
0x18000c419  mov     ecx, 8007000Eh; int
0x18000c41e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c424  mov     ecx, 8007000Eh; int
0x18000c429  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
