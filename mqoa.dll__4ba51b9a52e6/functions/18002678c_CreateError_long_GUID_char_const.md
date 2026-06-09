# CreateError(long,_GUID *,char const *)

- ea: `0x18002678c`
- end: `0x18002692b`
- name: `?CreateError@@YAJJPEAU_GUID@@PEBD@Z`
- size: `415`
- prototype: `__int64 __fastcall(UINT uID, struct _GUID *, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000cb34`

## callees

- `0x18002678c`
- `0x180026ac8`
- `0x1800273b0`
- `0x180029010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180026891`
- `KERNEL32!MultiByteToWideChar` at `0x180026891`
- `OLEAUT32!__imp_SysFreeString` at `0x180026901`
- `OLEAUT32!__imp_SysFreeString` at `0x180026901`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800268d4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800268d4`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800267dc`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800267dc`

## string_xrefs

- `0x180026826`: `MQUTIL.DLL`
- `0x18002681f`: `ACTIVEDS.DLL`

## pseudocode

```c
__int64 __fastcall CreateError(UINT uID, struct _GUID *a2, const char *a3)
{
  UINT v6; // eax
  const WCHAR *v7; // rdx
  bool v8; // zf
  struct ICreateErrorInfoVtbl *lpVtbl; // rax
  ICreateErrorInfo *pperrinfo; // [rsp+30h] [rbp-D0h] BYREF
  IErrorInfo *perrinfo; // [rsp+38h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR WideCharStr[256]; // [rsp+50h] [rbp-B0h] BYREF

  pperrinfo = 0;
  perrinfo = 0;
  bstrString = 0;
  if ( CreateErrorInfo(&pperrinfo) >= 0 )
  {
    if ( a2 )
      ((void (__fastcall *)(ICreateErrorInfo *, struct _GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, a2);
    v6 = uID & 0x1FFF0000;
    if ( (uID & 0x1FFF0000) == 0 || v6 == 0x40000 || v6 == 458752 )
    {
      v7 = 0;
    }
    else
    {
      v7 = L"ACTIVEDS.DLL";
      if ( v6 == 917504 )
        v7 = L"MQUTIL.DLL";
    }
    v8 = (unsigned int)GetMessageOfId(uID, v7, 1, &bstrString) == 0;
    lpVtbl = pperrinfo->lpVtbl;
    if ( v8 )
    {
      ((void (*)(void))lpVtbl->Release)();
    }
    else
    {
      ((void (__fastcall *)(ICreateErrorInfo *, BSTR))lpVtbl->SetDescription)(pperrinfo, bstrString);
      if ( a3 )
      {
        MultiByteToWideChar(0, 0, a3, -1, WideCharStr, 256);
        ((void (__fastcall *)(ICreateErrorInfo *, WCHAR *))pperrinfo->lpVtbl->SetSource)(pperrinfo, WideCharStr);
      }
      if ( ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
             pperrinfo,
             &IID_IErrorInfo,
             &perrinfo) >= 0 )
      {
        SetErrorInfo(0, perrinfo);
        ((void (__fastcall *)(IErrorInfo *))perrinfo->lpVtbl->Release)(perrinfo);
      }
      ((void (__fastcall *)(ICreateErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
      SysFreeString(bstrString);
    }
  }
  return uID;
}

```

## disassembly

```asm
0x18002678c  mov     [rsp-8+arg_18], rbx
0x180026791  push    rbp
0x180026792  push    rsi
0x180026793  push    rdi
0x180026794  lea     rbp, [rsp-160h]
0x18002679c  sub     rsp, 260h
0x1800267a3  mov     rax, cs:__security_cookie
0x1800267aa  xor     rax, rsp
0x1800267ad  mov     [rbp+170h+var_20], rax
0x1800267b4  mov     ebx, ecx
0x1800267b6  mov     [rsp+270h+pperrinfo], 0
0x1800267bf  lea     rcx, [rsp+270h+pperrinfo]; pperrinfo
0x1800267c4  mov     [rsp+270h+perrinfo], 0
0x1800267cd  mov     rsi, r8
0x1800267d0  mov     [rsp+270h+bstrString], 0
0x1800267d9  mov     rdi, rdx
0x1800267dc  call    cs:__imp_CreateErrorInfo
0x1800267e2  test    eax, eax
0x1800267e4  js      loc_180026907
0x1800267ea  test    rdi, rdi
0x1800267ed  jz      short loc_180026803
0x1800267ef  mov     rcx, [rsp+270h+pperrinfo]
0x1800267f4  mov     rdx, rdi
0x1800267f7  mov     rax, [rcx]
0x1800267fa  mov     rax, [rax+18h]
0x1800267fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026803  mov     eax, ebx
0x180026805  and     eax, 1FFF0000h
0x18002680a  jz      short loc_180026833
0x18002680c  cmp     eax, 40000h
0x180026811  jz      short loc_180026833
0x180026813  cmp     eax, 70000h
0x180026818  jz      short loc_180026833
0x18002681a  cmp     eax, 0E0000h
0x18002681f  lea     rdx, aActivedsDll; "ACTIVEDS.DLL"
0x180026826  lea     rcx, aMqutilDll; "MQUTIL.DLL"
0x18002682d  cmovz   rdx, rcx
0x180026831  jmp     short loc_180026835
0x180026833  xor     edx, edx; lpLibFileName
0x180026835  lea     r9, [rsp+270h+bstrString]; wchar_t **
0x18002683a  mov     r8d, 1; int
0x180026840  mov     ecx, ebx; uID
0x180026842  call    ?GetMessageOfId@@YAHKPEA_WHPEAPEA_W@Z; GetMessageOfId(ulong,wchar_t *,int,wchar_t * *)
0x180026847  mov     rcx, [rsp+270h+pperrinfo]
0x18002684c  test    eax, eax
0x18002684e  mov     rax, [rcx]
0x180026851  jnz     short loc_180026861
0x180026853  mov     rax, [rax+10h]
0x180026857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002685c  jmp     loc_180026907
0x180026861  mov     rdx, [rsp+270h+bstrString]
0x180026866  mov     rax, [rax+28h]
0x18002686a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002686f  test    rsi, rsi
0x180026872  jz      short loc_1800268AD
0x180026874  lea     rax, [rsp+270h+WideCharStr]
0x180026879  mov     [rsp+270h+cchWideChar], 100h; cchWideChar
0x180026881  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180026885  mov     [rsp+270h+lpWideCharStr], rax; lpWideCharStr
0x18002688a  mov     r8, rsi; lpMultiByteStr
0x18002688d  xor     edx, edx; dwFlags
0x18002688f  xor     ecx, ecx; CodePage
0x180026891  call    cs:__imp_MultiByteToWideChar
0x180026897  mov     rcx, [rsp+270h+pperrinfo]
0x18002689c  lea     rdx, [rsp+270h+WideCharStr]
0x1800268a1  mov     rax, [rcx]
0x1800268a4  mov     rax, [rax+20h]
0x1800268a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268ad  mov     rcx, [rsp+270h+pperrinfo]
0x1800268b2  lea     r8, [rsp+270h+perrinfo]
0x1800268b7  lea     rdx, IID_IErrorInfo
0x1800268be  mov     rax, [rcx]
0x1800268c1  mov     rax, [rax]
0x1800268c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268c9  test    eax, eax
0x1800268cb  js      short loc_1800268EB
0x1800268cd  mov     rdx, [rsp+270h+perrinfo]; perrinfo
0x1800268d2  xor     ecx, ecx; dwReserved
0x1800268d4  call    cs:__imp_SetErrorInfo
0x1800268da  mov     rcx, [rsp+270h+perrinfo]
0x1800268df  mov     rax, [rcx]
0x1800268e2  mov     rax, [rax+10h]
0x1800268e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268eb  mov     rcx, [rsp+270h+pperrinfo]
0x1800268f0  mov     rax, [rcx]
0x1800268f3  mov     rax, [rax+10h]
0x1800268f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268fc  mov     rcx, [rsp+270h+bstrString]; bstrString
0x180026901  call    cs:__imp_SysFreeString
0x180026907  mov     eax, ebx
0x180026909  mov     rcx, [rbp+170h+var_20]
0x180026910  xor     rcx, rsp; StackCookie
0x180026913  call    __security_check_cookie
0x180026918  mov     rbx, [rsp+270h+arg_18]
0x180026920  add     rsp, 260h
0x180026927  pop     rdi
0x180026928  pop     rsi
0x180026929  pop     rbp
0x18002692a  retn
```
