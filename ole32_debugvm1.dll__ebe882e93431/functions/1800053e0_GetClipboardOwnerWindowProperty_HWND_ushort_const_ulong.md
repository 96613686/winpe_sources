# GetClipboardOwnerWindowProperty(HWND__ *,ushort const * *,ulong *)

- ea: `0x1800053e0`
- end: `0x180005491`
- name: `?GetClipboardOwnerWindowProperty@@YAJPEAUHWND__@@PEAPEBGPEAK@Z`
- size: `177`
- prototype: `HRESULT __fastcall(HWND__ *hWnd, const wchar_t **pszPackageId, unsigned int *pdwProcessId)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800051e0`
- `0x1800054a0`
- `0x18000cebc`

## callees

- `0x1800053e0`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x18000544f`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x18000544f`
- `USER32!GetPropW` at `0x18000540b`
- `USER32!GetPropW` at `0x18000541e`
- `USER32!GetPropW` at `0x18000540b`
- `USER32!GetPropW` at `0x18000541e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005435`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005435`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000547a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000547a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005489`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005489`

## pseudocode

```c
__int64 __fastcall GetClipboardOwnerWindowProperty(HWND hWnd, wchar_t **pszPackageId, unsigned int *pdwProcessId)
{
  unsigned int v6; // edi
  unsigned int PropW; // ebp
  unsigned __int16 v8; // ax
  ATOM v9; // si
  WCHAR *v10; // rax
  wchar_t *v11; // rbx

  *pszPackageId = 0;
  *pdwProcessId = 0;
  v6 = 0;
  PropW = (unsigned int)GetPropW(hWnd, L"OleClipProcessOwner");
  v8 = (unsigned __int16)GetPropW(hWnd, L"OLEClipPackgeOwner");
  v9 = v8;
  if ( PropW && v8 )
  {
    v10 = (WCHAR *)CoTaskMemAlloc(0x200u);
    v11 = v10;
    if ( v10 )
    {
      if ( GlobalGetAtomNameW(v9, v10, 256) )
      {
        *pszPackageId = v11;
        *pdwProcessId = PropW;
        return v6;
      }
      CoTaskMemFree(v11);
      v6 = -2147418113;
    }
    else
    {
      v6 = -2147024882;
    }
    RoOriginateError(v6, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x1800053e0  push    rbx
0x1800053e2  push    rbp
0x1800053e3  push    rsi
0x1800053e4  push    rdi
0x1800053e5  push    r12
0x1800053e7  push    r14
0x1800053e9  push    r15
0x1800053eb  sub     rsp, 20h
0x1800053ef  xor     r12d, r12d
0x1800053f2  mov     r15, pszPackageId
0x1800053f5  mov     [pszPackageId], r12
0x1800053f8  mov     r14, pdwProcessId
0x1800053fb  lea     pszPackageId, aOleclipprocess; "OleClipProcessOwner"
0x180005402  mov     [pdwProcessId], r12d
0x180005405  mov     rbx, hWnd
0x180005408  mov     edi, r12d
0x18000540b  call    cs:__imp_GetPropW
0x180005411  lea     pszPackageId, aOleclippackgeo; "OLEClipPackgeOwner"
0x180005418  mov     hWnd, rbx; hWnd
0x18000541b  mov     rbp, rax
0x18000541e  call    cs:__imp_GetPropW
0x180005424  mov     rsi, rax
0x180005427  test    ebp, ebp
0x180005429  jz      short loc_18000545F
0x18000542b  test    si, si
0x18000542e  jz      short loc_18000545F
0x180005430  mov     ecx, 200h; cb
0x180005435  call    cs:__imp_CoTaskMemAlloc
0x18000543b  mov     rbx, rax
0x18000543e  test    rax, rax
0x180005441  jz      short loc_180005470
0x180005443  mov     r8d, 100h; nSize
0x180005449  mov     pszPackageId, rax; lpBuffer
0x18000544c  movzx   ecx, si; nAtom
0x18000544f  call    cs:__imp_GlobalGetAtomNameW
0x180005455  test    eax, eax
0x180005457  jz      short loc_180005477
0x180005459  mov     [r15], rbx
0x18000545c  mov     [r14], ebp
0x18000545f  mov     eax, edi
0x180005461  add     rsp, 20h
0x180005465  pop     r15
0x180005467  pop     r14
0x180005469  pop     r12
0x18000546b  pop     rdi
0x18000546c  pop     rsi
0x18000546d  pop     rbp
0x18000546e  pop     rbx
0x18000546f  retn
0x180005470  mov     edi, 8007000Eh
0x180005475  jmp     short loc_180005485
0x180005477  mov     hWnd, rbx; pv
0x18000547a  call    cs:__imp_CoTaskMemFree
0x180005480  mov     edi, 8000FFFFh
0x180005485  xor     edx, edx
0x180005487  mov     ecx, edi
0x180005489  call    cs:__imp_RoOriginateError
0x18000548f  jmp     short loc_18000545F
```
