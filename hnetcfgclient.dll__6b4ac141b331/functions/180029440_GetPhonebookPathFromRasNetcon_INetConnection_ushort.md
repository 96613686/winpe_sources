# GetPhonebookPathFromRasNetcon(INetConnection *,ushort * *)

- ea: `0x180029440`
- end: `0x1800294f0`
- name: `?GetPhonebookPathFromRasNetcon@@YAJPEAUINetConnection@@PEAPEAG@Z`
- size: `176`
- prototype: `__int64 __fastcall(struct INetConnection *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ebb0`
- `0x180014bc0`

## callees

- `0x180029440`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294bf`

## pseudocode

```c
__int64 __fastcall GetPhonebookPathFromRasNetcon(struct INetConnection *a1, unsigned __int16 **a2)
{
  struct INetConnectionVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(INetConnection *, const IID *const, void **); // rax
  int v5; // ebx
  void *v6; // rcx
  __int64 v8; // [rsp+20h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+28h] [rbp-30h] BYREF
  __int128 v10; // [rsp+38h] [rbp-20h]

  *a2 = 0;
  lpVtbl = a1->lpVtbl;
  v8 = 0;
  *(_OWORD *)pv = 0;
  QueryInterface = lpVtbl->QueryInterface;
  v10 = 0;
  v5 = ((__int64 (__fastcall *)(struct INetConnection *, GUID *, __int64 *))QueryInterface)(
         a1,
         &GUID_faedcf57_31fe_11d1_aad2_00805fc1270e,
         &v8);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v8 + 24LL))(v8, pv);
    if ( v5 >= 0 )
    {
      v6 = pv[1];
      *a2 = (unsigned __int16 *)pv[0];
      CoTaskMemFree(v6);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180029440  mov     [rsp+arg_10], rbx
0x180029445  push    rdi
0x180029446  sub     rsp, 50h
0x18002944a  mov     rax, cs:__security_cookie
0x180029451  xor     rax, rsp
0x180029454  mov     [rsp+58h+var_10], rax
0x180029459  mov     qword ptr [rdx], 0
0x180029460  lea     r8, [rsp+58h+var_38]
0x180029465  mov     rax, [rcx]
0x180029468  xorps   xmm0, xmm0
0x18002946b  mov     rdi, rdx
0x18002946e  mov     [rsp+58h+var_38], 0
0x180029477  lea     rdx, _GUID_faedcf57_31fe_11d1_aad2_00805fc1270e
0x18002947e  movups  xmmword ptr [rsp+58h+pv], xmm0
0x180029483  mov     rax, [rax]
0x180029486  movups  [rsp+58h+var_20], xmm0
0x18002948b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029490  mov     ebx, eax
0x180029492  test    eax, eax
0x180029494  js      short loc_1800294D6
0x180029496  mov     rcx, [rsp+58h+var_38]
0x18002949b  lea     rdx, [rsp+58h+pv]
0x1800294a0  mov     rax, [rcx]
0x1800294a3  mov     rax, [rax+18h]
0x1800294a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294ac  mov     ebx, eax
0x1800294ae  test    eax, eax
0x1800294b0  js      short loc_1800294C5
0x1800294b2  mov     rax, [rsp+58h+pv]
0x1800294b7  mov     rcx, [rsp+58h+pv+8]; pv
0x1800294bc  mov     [rdi], rax
0x1800294bf  call    cs:__imp_CoTaskMemFree
0x1800294c5  mov     rcx, [rsp+58h+var_38]
0x1800294ca  mov     rax, [rcx]
0x1800294cd  mov     rax, [rax+10h]
0x1800294d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800294d6  mov     eax, ebx
0x1800294d8  mov     rcx, [rsp+58h+var_10]
0x1800294dd  xor     rcx, rsp; StackCookie
0x1800294e0  call    __security_check_cookie
0x1800294e5  mov     rbx, [rsp+58h+arg_10]
0x1800294ea  add     rsp, 50h
0x1800294ee  pop     rdi
0x1800294ef  retn
```
