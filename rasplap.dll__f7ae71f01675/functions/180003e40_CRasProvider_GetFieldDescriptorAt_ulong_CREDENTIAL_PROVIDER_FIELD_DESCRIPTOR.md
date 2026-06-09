# CRasProvider::GetFieldDescriptorAt(ulong,_CREDENTIAL_PROVIDER_FIELD_DESCRIPTOR * *)

- ea: `0x180003e40`
- end: `0x180003ee1`
- name: `?GetFieldDescriptorAt@CRasProvider@@UEAAJKPEAPEAU_CREDENTIAL_PROVIDER_FIELD_DESCRIPTOR@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(CRasProvider *__hidden this, unsigned int, struct _CREDENTIAL_PROVIDER_FIELD_DESCRIPTOR **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180003e40`
- `0x180005380`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180003e63`
- `ole32!CoTaskMemAlloc` at `0x180003e63`
- `ole32!CoTaskMemFree` at `0x180003ebb`
- `ole32!CoTaskMemFree` at `0x180003ebb`

## pseudocode

```c
__int64 __fastcall CRasProvider::GetFieldDescriptorAt(
        CRasProvider *this,
        unsigned int a2,
        struct _CREDENTIAL_PROVIDER_FIELD_DESCRIPTOR **a3)
{
  __int64 v3; // rdi
  struct _CREDENTIAL_PROVIDER_FIELD_DESCRIPTOR *v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // r8
  int v8; // edi

  v3 = a2;
  if ( !a3 || a2 >= 0xC )
    return 2147942487LL;
  v5 = (struct _CREDENTIAL_PROVIDER_FIELD_DESCRIPTOR *)CoTaskMemAlloc(0x20u);
  if ( v5 )
  {
    v6 = (unsigned int)dword_18000E360[v3];
    v7 = 4LL * (unsigned int)v3;
    v5->dwFieldID = qword_1800120E0[v7];
    v5->cpft = HIDWORD(qword_1800120E0[v7]);
    v5->pszLabel = 0;
    v8 = StringResourceStringCoAllocCopy(v6);
    if ( v8 < 0 )
    {
      CoTaskMemFree(v5);
    }
    else
    {
      *a3 = v5;
      return 0;
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180003e40  mov     [rsp+arg_0], rbx
0x180003e45  mov     [rsp+arg_8], rsi
0x180003e4a  push    rdi
0x180003e4b  sub     rsp, 20h
0x180003e4f  mov     edi, edx
0x180003e51  mov     rsi, r8
0x180003e54  test    r8, r8
0x180003e57  jz      short loc_180003ECC
0x180003e59  cmp     edi, 0Ch
0x180003e5c  jnb     short loc_180003ECC
0x180003e5e  mov     ecx, 20h ; ' '; cb
0x180003e63  call    cs:__imp_CoTaskMemAlloc
0x180003e69  mov     rbx, rax
0x180003e6c  test    rax, rax
0x180003e6f  jz      short loc_180003EC3
0x180003e71  lea     rax, __ImageBase
0x180003e78  mov     r8d, edi
0x180003e7b  mov     ecx, ds:rva dword_18000E360[rax+rdi*4]
0x180003e82  shl     r8, 5
0x180003e86  mov     edx, [r8+rax+120E0h]
0x180003e8e  mov     [rbx], edx
0x180003e90  mov     edx, [r8+rax+120E4h]
0x180003e98  mov     [rbx+4], edx
0x180003e9b  lea     rdx, [rbx+8]
0x180003e9f  mov     qword ptr [rdx], 0
0x180003ea6  call    _StringResourceStringCoAllocCopy
0x180003eab  mov     edi, eax
0x180003ead  test    eax, eax
0x180003eaf  js      short loc_180003EB8
0x180003eb1  mov     [rsi], rbx
0x180003eb4  xor     edi, edi
0x180003eb6  jmp     short loc_180003EC8
0x180003eb8  mov     rcx, rbx; pv
0x180003ebb  call    cs:__imp_CoTaskMemFree
0x180003ec1  jmp     short loc_180003EC8
0x180003ec3  mov     edi, 8007000Eh
0x180003ec8  mov     eax, edi
0x180003eca  jmp     short loc_180003ED1
0x180003ecc  mov     eax, 80070057h
0x180003ed1  mov     rbx, [rsp+28h+arg_0]
0x180003ed6  mov     rsi, [rsp+28h+arg_8]
0x180003edb  add     rsp, 20h
0x180003edf  pop     rdi
0x180003ee0  retn
```
