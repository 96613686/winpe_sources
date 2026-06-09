# CSyncItemInfo::IsConnected(void)

- ea: `0x1800184e0`
- end: `0x18001862b`
- name: `?IsConnected@CSyncItemInfo@@UEAAJXZ`
- size: `331`
- prototype: `__int64 __fastcall(CSyncItemInfo *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800184e0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001860e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001860e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018539`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018539`

## pseudocode

```c
__int64 __fastcall CSyncItemInfo::IsConnected(CSyncItemInfo *this)
{
  __int64 v1; // rcx
  HRESULT v2; // ebx
  BOOL v3; // edi
  LPVOID ppv; // [rsp+30h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-10h] BYREF
  int v7; // [rsp+70h] [rbp+28h] BYREF
  int v8; // [rsp+78h] [rbp+30h] BYREF
  __int64 v9; // [rsp+80h] [rbp+38h] BYREF
  __int64 v10; // [rsp+88h] [rbp+40h] BYREF

  v1 = *((_QWORD *)this + 2);
  pv[0] = 0;
  v2 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v1 + 32LL))(v1, pv);
  if ( v2 >= 0 )
  {
    v3 = 0;
    ppv = 0;
    v2 = CoCreateInstance(&CLSID_OfflineFilesCache, 0, 1u, &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5, &ppv);
    if ( v2 >= 0 )
    {
      v10 = 0;
      v2 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 80LL))(ppv, pv[0], 2, &v10);
      if ( v2 >= 0 )
      {
        v9 = 0;
        v2 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v10)(
               v10,
               &GUID_efb23a09_a867_4be8_83a6_86969a7d0856,
               &v9);
        if ( v2 >= 0 )
        {
          v7 = 0;
          v8 = 0;
          v2 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v9 + 24LL))(v9, &v7, &v8);
          if ( v2 >= 0 )
          {
            if ( v7 == 1 )
            {
              v3 = v8 != 4;
            }
            else if ( v7 == 2 || v7 == 4 )
            {
              v3 = 1;
            }
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoTaskMemFree(pv[0]);
    if ( v2 >= 0 )
      return !v3;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800184e0  push    rbp
0x1800184e2  push    rbx
0x1800184e3  push    rdi
0x1800184e4  push    r14
0x1800184e6  mov     rbp, rsp
0x1800184e9  sub     rsp, 48h
0x1800184ed  mov     rcx, [rcx+10h]
0x1800184f1  lea     rdx, [rbp+pv]
0x1800184f5  mov     [rbp+pv], 0
0x1800184fd  mov     rax, [rcx]
0x180018500  mov     rax, [rax+20h]
0x180018504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018509  mov     ebx, eax
0x18001850b  test    eax, eax
0x18001850d  js      loc_18001861F
0x180018513  xor     edi, edi
0x180018515  lea     rax, [rbp+var_18]
0x180018519  lea     r9, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x180018520  mov     [rbp+var_18], rdi
0x180018524  xor     edx, edx; pUnkOuter
0x180018526  mov     [rsp+48h+ppv], rax; ppv
0x18001852b  lea     rcx, CLSID_OfflineFilesCache; rclsid
0x180018532  lea     r14d, [rdi+1]
0x180018536  mov     r8d, r14d; dwClsContext
0x180018539  call    cs:__imp_CoCreateInstance
0x18001853f  mov     ebx, eax
0x180018541  test    eax, eax
0x180018543  js      loc_18001860A
0x180018549  mov     rcx, [rbp+var_18]
0x18001854d  lea     r9, [rbp+arg_18]
0x180018551  mov     rdx, [rbp+pv]
0x180018555  lea     r8d, [rdi+2]
0x180018559  mov     [rbp+arg_18], rdi
0x18001855d  mov     rax, [rcx]
0x180018560  mov     rax, [rax+50h]
0x180018564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018569  mov     ebx, eax
0x18001856b  test    eax, eax
0x18001856d  js      loc_1800185FA
0x180018573  mov     rcx, [rbp+arg_18]
0x180018577  lea     r8, [rbp+arg_10]
0x18001857b  mov     [rbp+arg_10], rdi
0x18001857f  lea     rdx, _GUID_efb23a09_a867_4be8_83a6_86969a7d0856
0x180018586  mov     rax, [rcx]
0x180018589  mov     rax, [rax]
0x18001858c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018591  mov     ebx, eax
0x180018593  test    eax, eax
0x180018595  js      short loc_1800185EA
0x180018597  mov     rcx, [rbp+arg_10]
0x18001859b  lea     r8, [rbp+arg_8]
0x18001859f  mov     [rbp+arg_0], edi
0x1800185a2  lea     rdx, [rbp+arg_0]
0x1800185a6  mov     [rbp+arg_8], edi
0x1800185a9  mov     rax, [rcx]
0x1800185ac  mov     rax, [rax+18h]
0x1800185b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185b5  mov     ebx, eax
0x1800185b7  test    eax, eax
0x1800185b9  js      short loc_1800185DA
0x1800185bb  mov     ecx, [rbp+arg_0]
0x1800185be  sub     ecx, r14d
0x1800185c1  jz      short loc_1800185D2
0x1800185c3  sub     ecx, r14d
0x1800185c6  jz      short loc_1800185CD
0x1800185c8  cmp     ecx, 2
0x1800185cb  jnz     short loc_1800185DA
0x1800185cd  mov     edi, r14d
0x1800185d0  jmp     short loc_1800185DA
0x1800185d2  cmp     [rbp+arg_8], 4
0x1800185d6  cmovnz  edi, r14d
0x1800185da  mov     rcx, [rbp+arg_10]
0x1800185de  mov     rax, [rcx]
0x1800185e1  mov     rax, [rax+10h]
0x1800185e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185ea  mov     rcx, [rbp+arg_18]
0x1800185ee  mov     rax, [rcx]
0x1800185f1  mov     rax, [rax+10h]
0x1800185f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185fa  mov     rcx, [rbp+var_18]
0x1800185fe  mov     rax, [rcx]
0x180018601  mov     rax, [rax+10h]
0x180018605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001860a  mov     rcx, [rbp+pv]; pv
0x18001860e  call    cs:__imp_CoTaskMemFree
0x180018614  test    ebx, ebx
0x180018616  js      short loc_18001861F
0x180018618  xor     ebx, ebx
0x18001861a  test    edi, edi
0x18001861c  setz    bl
0x18001861f  mov     eax, ebx
0x180018621  add     rsp, 48h
0x180018625  pop     r14
0x180018627  pop     rdi
0x180018628  pop     rbx
0x180018629  pop     rbp
0x18001862a  retn
```
