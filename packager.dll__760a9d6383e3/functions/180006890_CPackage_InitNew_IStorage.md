# CPackage::InitNew(IStorage *)

- ea: `0x180006890`
- end: `0x1800068f6`
- name: `?InitNew@CPackage@@UEAAJPEAUIStorage@@@Z`
- size: `102`
- prototype: `HRESULT __fastcall(CPackage *this, struct IStorage *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006890`

## import_xrefs

- `ole32!WriteClassStg` at `0x1800068c4`
- `ole32!WriteClassStg` at `0x1800068c4`

## pseudocode

```c
HRESULT __fastcall CPackage::InitNew(CPackage *this, struct IStorage *a2)
{
  HRESULT result; // eax

  result = *((_DWORD *)this + 17) != 0 ? 0x800401F1 : 0;
  if ( !a2 )
    return -2147467261;
  if ( !*((_DWORD *)this + 17) )
  {
    result = WriteClassStg(a2, &CLSID_OldPackage);
    if ( result >= 0 )
    {
      *((_DWORD *)this + 22) = 0;
      *((_DWORD *)this + 28) = 1;
      *((_DWORD *)this + 17) = 1;
      *((_DWORD *)this + 16) = *((_DWORD *)this + 23) != 0 ? 1 : 3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006890  push    rbx
0x180006892  sub     rsp, 20h
0x180006896  mov     eax, [rcx+44h]
0x180006899  mov     r8, rdx
0x18000689c  neg     eax
0x18000689e  mov     rbx, rcx
0x1800068a1  sbb     eax, eax
0x1800068a3  and     eax, 800401F1h
0x1800068a8  test    rdx, rdx
0x1800068ab  jnz     short loc_1800068B4
0x1800068ad  mov     eax, 80004003h
0x1800068b2  jmp     short loc_1800068F0
0x1800068b4  cmp     dword ptr [rcx+44h], 0
0x1800068b8  jnz     short loc_1800068F0
0x1800068ba  lea     rdx, CLSID_OldPackage; rclsid
0x1800068c1  mov     rcx, r8; pStg
0x1800068c4  call    cs:__imp_WriteClassStg
0x1800068ca  test    eax, eax
0x1800068cc  js      short loc_1800068F0
0x1800068ce  mov     ecx, 1
0x1800068d3  mov     dword ptr [rbx+58h], 0
0x1800068da  mov     [rbx+70h], ecx
0x1800068dd  mov     [rbx+44h], ecx
0x1800068e0  mov     ecx, [rbx+5Ch]
0x1800068e3  neg     ecx
0x1800068e5  sbb     edx, edx
0x1800068e7  and     edx, 0FFFFFFFEh
0x1800068ea  add     edx, 3
0x1800068ed  mov     [rbx+40h], edx
0x1800068f0  add     rsp, 20h
0x1800068f4  pop     rbx
0x1800068f5  retn
```
