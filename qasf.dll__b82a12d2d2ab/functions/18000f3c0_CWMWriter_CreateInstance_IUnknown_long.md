# CWMWriter::CreateInstance(IUnknown *,long *)

- ea: `0x18000f3c0`
- end: `0x18000f40c`
- name: `?CreateInstance@CWMWriter@@SAPEAVCUnknown@@PEAUIUnknown@@PEAJ@Z`
- size: `76`
- prototype: `struct CUnknown *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001020`
- `0x18000dfbc`
- `0x18000f3c0`

## pseudocode

```c
struct CUnknown *__fastcall CWMWriter::CreateInstance(struct IUnknown *a1, int *a2)
{
  struct CUnknown *result; // rax
  const unsigned __int16 *v5; // rdx
  struct _GUID v6; // [rsp+30h] [rbp-18h] BYREF

  result = (struct CUnknown *)operator new(0x210u);
  if ( result )
  {
    v6 = CLSID_WMAsfWriter;
    return CWMWriter::CWMWriter(result, v5, a1, &v6, a2);
  }
  return result;
}

```

## disassembly

```asm
0x18000f3c0  mov     [rsp+arg_0], rbx
0x18000f3c5  push    rdi
0x18000f3c6  sub     rsp, 40h
0x18000f3ca  mov     rdi, rcx
0x18000f3cd  mov     rbx, rdx
0x18000f3d0  mov     ecx, 210h; Size
0x18000f3d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f3da  test    rax, rax
0x18000f3dd  jz      short loc_18000F401
0x18000f3df  movups  xmm0, xmmword ptr cs:CLSID_WMAsfWriter.Data1
0x18000f3e6  lea     r9, [rsp+48h+var_18]; struct _GUID *
0x18000f3eb  mov     [rsp+48h+var_28], rbx; int *
0x18000f3f0  mov     r8, rdi; struct IUnknown *
0x18000f3f3  mov     rcx, rax; this
0x18000f3f6  movdqu  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x18000f3fc  call    ??0CWMWriter@@QEAA@PEBGPEAUIUnknown@@U_GUID@@PEAJ@Z; CWMWriter::CWMWriter(ushort const *,IUnknown *,_GUID,long *)
0x18000f401  mov     rbx, [rsp+48h+arg_0]
0x18000f406  add     rsp, 40h
0x18000f40a  pop     rdi
0x18000f40b  retn
```
