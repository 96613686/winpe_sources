# CAppCopy::CopyApplications(void)

- ea: `0x18001854c`
- end: `0x180018617`
- name: `?CopyApplications@CAppCopy@@QEAAJXZ`
- size: `203`
- prototype: `HRESULT __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180018620`

## callees

- `0x1800180c8`
- `0x18001854c`
- `0x18001a558`
- `0x18005551a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001859d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800185d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001859d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800185d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018576`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018576`

## pseudocode

```c
HRESULT __fastcall CAppCopy::CopyApplications(LPVOID *this)
{
  HRESULT result; // eax
  void *v3; // rax
  void *v4; // rax

  result = CoCreateInstance(&clsidSTDISP, 0, 1u, &IID_ISimpleTableDispenser, this + 12);
  if ( result >= 0 )
  {
    v3 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 8), 4u));
    this[7] = v3;
    if ( v3
      && (memset_0(v3, 0, 4LL * *((unsigned int *)this + 8)),
          v4 = CoTaskMemAlloc(saturated_mul(*((unsigned int *)this + 8), 0x10u)),
          (this[6] = v4) != 0) )
    {
      memset_0(v4, 0, 16LL * *((unsigned int *)this + 8));
      result = CAppCopy::CopyApplications2((CAppCopy *)this);
      if ( result >= 0 )
        return CAppCopy::UpdateAllStores((CAppCopy *)this);
    }
    else
    {
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001854c  mov     [rsp+arg_0], rbx
0x180018551  push    rdi
0x180018552  sub     rsp, 30h
0x180018556  lea     rax, [rcx+60h]
0x18001855a  xor     edx, edx; pUnkOuter
0x18001855c  mov     rbx, rcx
0x18001855f  mov     [rsp+38h+ppv], rax; ppv
0x180018564  lea     r9, IID_ISimpleTableDispenser; riid
0x18001856b  lea     rcx, clsidSTDISP; rclsid
0x180018572  lea     r8d, [rdx+1]; dwClsContext
0x180018576  call    cs:__imp_CoCreateInstance
0x18001857c  test    eax, eax
0x18001857e  js      loc_18001860C
0x180018584  mov     ecx, [rbx+20h]
0x180018587  mov     eax, 4
0x18001858c  mul     rcx
0x18001858f  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180018596  cmovb   rax, rdi
0x18001859a  mov     rcx, rax; cb
0x18001859d  call    cs:__imp_CoTaskMemAlloc
0x1800185a3  mov     [rbx+38h], rax
0x1800185a7  test    rax, rax
0x1800185aa  jnz     short loc_1800185B3
0x1800185ac  mov     eax, 8007000Eh
0x1800185b1  jmp     short loc_18001860C
0x1800185b3  mov     r8d, [rbx+20h]
0x1800185b7  xor     edx, edx; Val
0x1800185b9  shl     r8, 2; Size
0x1800185bd  mov     rcx, rax; void *
0x1800185c0  call    memset_0
0x1800185c5  mov     ecx, [rbx+20h]
0x1800185c8  mov     eax, 10h
0x1800185cd  mul     rcx
0x1800185d0  cmovb   rax, rdi
0x1800185d4  mov     rcx, rax; cb
0x1800185d7  call    cs:__imp_CoTaskMemAlloc
0x1800185dd  mov     [rbx+30h], rax
0x1800185e1  test    rax, rax
0x1800185e4  jz      short loc_1800185AC
0x1800185e6  mov     r8d, [rbx+20h]
0x1800185ea  xor     edx, edx; Val
0x1800185ec  shl     r8, 4; Size
0x1800185f0  mov     rcx, rax; void *
0x1800185f3  call    memset_0
0x1800185f8  mov     rcx, rbx; this
0x1800185fb  call    ?CopyApplications2@CAppCopy@@AEAAJXZ; CAppCopy::CopyApplications2(void)
0x180018600  test    eax, eax
0x180018602  js      short loc_18001860C
0x180018604  mov     rcx, rbx; this
0x180018607  call    ?UpdateAllStores@CAppCopy@@AEAAJXZ; CAppCopy::UpdateAllStores(void)
0x18001860c  mov     rbx, [rsp+38h+arg_0]
0x180018611  add     rsp, 30h
0x180018615  pop     rdi
0x180018616  retn
```
