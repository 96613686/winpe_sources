# CDims::p_GetWMIBackupTask(ITaskService *,ushort const *,IRegisteredTask * *)

- ea: `0x180009c88`
- end: `0x180009e13`
- name: `?p_GetWMIBackupTask@CDims@@AEAAJPEAUITaskService@@PEBGPEAPEAUIRegisteredTask@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(CDims *__hidden this, struct ITaskService *, const unsigned __int16 *, struct IRegisteredTask **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180009af4`

## callees

- `0x180009c88`
- `0x18000ac8e`
- `0x18000ad30`
- `0x18000c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180009cef`
- `OLEAUT32!__imp_SysAllocString` at `0x180009d48`
- `OLEAUT32!__imp_SysAllocString` at `0x180009cef`
- `OLEAUT32!__imp_SysAllocString` at `0x180009d48`
- `OLEAUT32!__imp_SysFreeString` at `0x180009db0`
- `OLEAUT32!__imp_SysFreeString` at `0x180009db9`
- `OLEAUT32!__imp_SysFreeString` at `0x180009db0`
- `OLEAUT32!__imp_SysFreeString` at `0x180009db9`
- `OLEAUT32!__imp_SysStringLen` at `0x180009d54`
- `OLEAUT32!__imp_SysStringLen` at `0x180009d54`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180009d14`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180009d35`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180009d14`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180009d35`

## string_xrefs

- `0x180009d24`: `UserTask-Roam`
- `0x180009ce8`: `Microsoft\Windows\CertificateServicesClient`

## pseudocode

```c
__int64 __fastcall CDims::p_GetWMIBackupTask(
        CDims *this,
        struct ITaskService *a2,
        const unsigned __int16 *a3,
        struct IRegisteredTask **a4)
{
  OLECHAR *v6; // rsi
  const WCHAR *v7; // rax
  OLECHAR *v8; // rdi
  HRESULT v9; // ebx
  struct IRegisteredTask *v11; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v12; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-D0h] BYREF

  v11 = 0;
  v12 = 0;
  v6 = 0;
  memset_0(pszPath, 0, 0x20Au);
  if ( a4 )
    *a4 = 0;
  v7 = SysAllocString(L"Microsoft\\Windows\\CertificateServicesClient");
  v8 = (OLECHAR *)v7;
  if ( !v7 )
    goto LABEL_4;
  v9 = PathCchAppend(pszPath, 0x104u, v7);
  if ( v9 >= 0 )
  {
    v9 = PathCchAppend(pszPath, 0x104u, L"UserTask-Roam");
    if ( v9 >= 0 )
    {
      v6 = SysAllocString(L"\\");
      if ( !SysStringLen(v6) )
      {
LABEL_4:
        v9 = -2147024882;
        goto LABEL_11;
      }
      v9 = ((__int64 (__fastcall *)(struct ITaskService *, OLECHAR *, __int64 *))a2->lpVtbl->GetFolder)(a2, v6, &v12);
      if ( !v9 )
      {
        v9 = (*(__int64 (__fastcall **)(__int64, WCHAR *, struct IRegisteredTask **))(*(_QWORD *)v12 + 104LL))(
               v12,
               pszPath,
               &v11);
        if ( !v9 )
        {
          *a4 = v11;
          v11 = 0;
        }
      }
    }
  }
LABEL_11:
  SysFreeString(v8);
  SysFreeString(v6);
  if ( v11 )
    ((void (__fastcall *)(struct IRegisteredTask *))v11->lpVtbl->Release)(v11);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009c88  mov     [rsp-8+arg_0], rbx
0x180009c8d  push    rbp
0x180009c8e  push    rsi
0x180009c8f  push    rdi
0x180009c90  push    r14
0x180009c92  push    r15
0x180009c94  lea     rbp, [rsp-150h]
0x180009c9c  sub     rsp, 250h
0x180009ca3  mov     rax, cs:__security_cookie
0x180009caa  xor     rax, rsp
0x180009cad  mov     [rbp+170h+var_30], rax
0x180009cb4  mov     r14, r9
0x180009cb7  mov     r15, rdx
0x180009cba  mov     [rsp+270h+var_250], 0
0x180009cc3  mov     [rsp+270h+var_248], 0
0x180009ccc  xor     esi, esi
0x180009cce  xor     edx, edx; Val
0x180009cd0  mov     r8d, 20Ah; Size
0x180009cd6  lea     rcx, [rsp+270h+pszPath]; void *
0x180009cdb  call    memset_0
0x180009ce0  test    r14, r14
0x180009ce3  jz      short loc_180009CE8
0x180009ce5  mov     [r14], rsi
0x180009ce8  lea     rcx, psz; "Microsoft\\Windows\\CertificateServices"...
0x180009cef  call    cs:__imp_SysAllocString
0x180009cf5  mov     rdi, rax
0x180009cf8  test    rax, rax
0x180009cfb  jnz     short loc_180009D07
0x180009cfd  mov     ebx, 8007000Eh
0x180009d02  jmp     loc_180009DAD
0x180009d07  mov     r8, rdi; pszMore
0x180009d0a  mov     edx, 104h; cchPath
0x180009d0f  lea     rcx, [rsp+270h+pszPath]; pszPath
0x180009d14  call    cs:__imp_PathCchAppend
0x180009d1a  mov     ebx, eax
0x180009d1c  test    eax, eax
0x180009d1e  js      loc_180009DAD
0x180009d24  lea     r8, c_wszTaskName; "UserTask-Roam"
0x180009d2b  mov     edx, 104h; cchPath
0x180009d30  lea     rcx, [rsp+270h+pszPath]; pszPath
0x180009d35  call    cs:__imp_PathCchAppend
0x180009d3b  mov     ebx, eax
0x180009d3d  test    eax, eax
0x180009d3f  js      short loc_180009DAD
0x180009d41  lea     rcx, asc_18000DDA0; "\\"
0x180009d48  call    cs:__imp_SysAllocString
0x180009d4e  mov     rsi, rax
0x180009d51  mov     rcx, rax; pbstr
0x180009d54  call    cs:__imp_SysStringLen
0x180009d5a  test    eax, eax
0x180009d5c  jz      short loc_180009CFD
0x180009d5e  mov     rax, [r15]
0x180009d61  lea     r8, [rsp+270h+var_248]
0x180009d66  mov     rdx, rsi
0x180009d69  mov     rcx, r15
0x180009d6c  mov     rax, [rax+38h]
0x180009d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d75  mov     ebx, eax
0x180009d77  test    eax, eax
0x180009d79  jnz     short loc_180009DAD
0x180009d7b  mov     rcx, [rsp+270h+var_248]
0x180009d80  mov     rax, [rcx]
0x180009d83  lea     r8, [rsp+270h+var_250]
0x180009d88  lea     rdx, [rsp+270h+pszPath]
0x180009d8d  mov     rax, [rax+68h]
0x180009d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d96  mov     ebx, eax
0x180009d98  test    eax, eax
0x180009d9a  jnz     short loc_180009DAD
0x180009d9c  mov     rax, [rsp+270h+var_250]
0x180009da1  mov     [r14], rax
0x180009da4  mov     [rsp+270h+var_250], 0
0x180009dad  mov     rcx, rdi; bstrString
0x180009db0  call    cs:__imp_SysFreeString
0x180009db6  mov     rcx, rsi; bstrString
0x180009db9  call    cs:__imp_SysFreeString
0x180009dbf  mov     rcx, [rsp+270h+var_250]
0x180009dc4  test    rcx, rcx
0x180009dc7  jz      short loc_180009DD5
0x180009dc9  mov     rax, [rcx]
0x180009dcc  mov     rax, [rax+10h]
0x180009dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dd5  mov     rcx, [rsp+270h+var_248]
0x180009dda  test    rcx, rcx
0x180009ddd  jz      short loc_180009DEB
0x180009ddf  mov     rax, [rcx]
0x180009de2  mov     rax, [rax+10h]
0x180009de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009deb  mov     eax, ebx
0x180009ded  mov     rcx, [rbp+170h+var_30]
0x180009df4  xor     rcx, rsp; StackCookie
0x180009df7  call    __security_check_cookie
0x180009dfc  mov     rbx, [rsp+270h+arg_0]
0x180009e04  add     rsp, 250h
0x180009e0b  pop     r15
0x180009e0d  pop     r14
0x180009e0f  pop     rdi
0x180009e10  pop     rsi
0x180009e11  pop     rbp
0x180009e12  retn
```
