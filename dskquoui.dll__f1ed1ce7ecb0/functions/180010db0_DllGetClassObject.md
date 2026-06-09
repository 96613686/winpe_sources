# DllGetClassObject

- ea: `0x180010db0`
- end: `0x180010e9e`
- name: `DllGetClassObject`
- size: `238`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001534`
- `0x180006ec0`
- `0x180010db0`
- `0x18001f010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v7; // esi
  char *v8; // rax
  __int64 (__fastcall ***v9)(void *, const IID *const, LPVOID *); // rbx

  if ( !ppv )
    return -2147024809;
  v7 = -2147221231;
  *ppv = 0;
  if ( *(_OWORD *)rclsid == *(_OWORD *)&CLSID_DiskQuotaUI
    || *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_QuotaUIHelper.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_QuotaUIHelper.Data4 )
  {
    try
    {
      v8 = (char *)operator new(0x20u);
      v9 = (__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v8;
      if ( v8 )
      {
        *(_QWORD *)v8 = &DiskQuotaUIClassFactory::`vftable';
        *((_DWORD *)v8 + 2) = 0;
        *(IID *)(v8 + 12) = *rclsid;
        _InterlockedIncrement(&g_cRefThisDll);
      }
      else
      {
        v9 = 0;
      }
      v7 = (**v9)(v9, riid, ppv);
      if ( v7 < 0 )
      {
        *v9 = (__int64 (__fastcall **)(void *, const IID *const, LPVOID *))&DiskQuotaUIClassFactory::`vftable';
        _InterlockedDecrement(&g_cRefThisDll);
        operator delete(v9);
      }
    }
    catch ( CAllocException )
    {
      if ( *ppv )
        *ppv = 0;
      return -2147024882;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180010db0  mov     [rsp+arg_0], rbx
0x180010db5  mov     [rsp+arg_10], r8
0x180010dba  push    rsi
0x180010dbb  push    rdi
0x180010dbc  push    r12
0x180010dbe  push    r14
0x180010dc0  push    r15
0x180010dc2  sub     rsp, 20h
0x180010dc6  mov     r14, r8
0x180010dc9  mov     r12, rdx
0x180010dcc  mov     rdi, rcx
0x180010dcf  test    r8, r8
0x180010dd2  jnz     short loc_180010DDE
0x180010dd4  mov     eax, 80070057h
0x180010dd9  jmp     loc_180010E8C
0x180010dde  mov     esi, 80040111h
0x180010de3  mov     qword ptr [r8], 0
0x180010dea  mov     rax, [rcx]
0x180010ded  cmp     rax, qword ptr cs:CLSID_DiskQuotaUI.Data1
0x180010df4  jnz     short loc_180010E03
0x180010df6  mov     rax, [rcx+8]
0x180010dfa  cmp     rax, qword ptr cs:CLSID_DiskQuotaUI.Data4
0x180010e01  jz      short loc_180010E1C
0x180010e03  mov     rax, [rcx]
0x180010e06  cmp     rax, qword ptr cs:CLSID_QuotaUIHelper.Data1
0x180010e0d  jnz     short loc_180010E84
0x180010e0f  mov     rax, [rcx+8]
0x180010e13  cmp     rax, qword ptr cs:CLSID_QuotaUIHelper.Data4
0x180010e1a  jnz     short loc_180010E84
0x180010e1c  mov     ecx, 20h ; ' '; uBytes
0x180010e21  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010e26  mov     rbx, rax
0x180010e29  lea     r15, ??_7DiskQuotaUIClassFactory@@6B@; const DiskQuotaUIClassFactory::`vftable'
0x180010e30  test    rax, rax
0x180010e33  jz      short loc_180010E50
0x180010e35  mov     [rax], r15
0x180010e38  mov     dword ptr [rax+8], 0
0x180010e3f  movups  xmm0, xmmword ptr [rdi]
0x180010e42  movdqu  xmmword ptr [rax+0Ch], xmm0
0x180010e47  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180010e4e  jmp     short loc_180010E52
0x180010e50  xor     ebx, ebx
0x180010e52  mov     rax, [rbx]
0x180010e55  mov     r8, r14
0x180010e58  mov     rdx, r12
0x180010e5b  mov     rcx, rbx
0x180010e5e  mov     rax, [rax]
0x180010e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e66  mov     esi, eax
0x180010e68  test    eax, eax
0x180010e6a  jns     short loc_180010E84
0x180010e6c  mov     [rbx], r15
0x180010e6f  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180010e76  mov     edx, 20h ; ' '; unsigned __int64
0x180010e7b  mov     rcx, rbx; void *
0x180010e7e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010e83  nop
0x180010e84  jmp     short loc_180010E8A
0x180010e86  mov     esi, dword ptr [rsp+48h+arg_10]
0x180010e8a  mov     eax, esi
0x180010e8c  mov     rbx, [rsp+48h+arg_0]
0x180010e91  add     rsp, 20h
0x180010e95  pop     r15
0x180010e97  pop     r14
0x180010e99  pop     r12
0x180010e9b  pop     rdi
0x180010e9c  pop     rsi
0x180010e9d  retn
```
