# LdapProvOpenStore(char const *,ulong,unsigned __int64,ulong,void const *,void *,_CERT_STORE_PROV_INFO *)

- ea: `0x18001d4f0`
- end: `0x18001d5b1`
- name: `?LdapProvOpenStore@@YAHPEBDK_KKPEBXPEAXPEAU_CERT_STORE_PROV_INFO@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(const char *, __int64, __int64, unsigned int, void *, void *, struct _CERT_STORE_PROV_INFO *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180007c00`
- `0x180016a64`
- `0x18001d024`
- `0x18001d4f0`
- `0x18001d698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d59e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d59e`

## pseudocode

```c
__int64 __fastcall LdapProvOpenStore(
        const char *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        void *a5,
        void *a6,
        struct _CERT_STORE_PROV_INFO *a7)
{
  char *v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  const char *v10; // rdx
  unsigned int v11; // r8d
  unsigned __int64 v12; // r9
  unsigned int v13; // edi

  v8 = (char *)operator new(0x78u);
  v9 = (struct _RTL_CRITICAL_SECTION *)v8;
  if ( !v8 )
  {
    SetLastError(0x8007000E);
    return 0;
  }
  *((_QWORD *)v8 + 12) = 0;
  *((_QWORD *)v8 + 13) = 0;
  *((_QWORD *)v8 + 14) = 0;
  *(_OWORD *)(v8 + 40) = 0;
  *(_OWORD *)(v8 + 56) = 0;
  *(_OWORD *)(v8 + 72) = 0;
  *((_QWORD *)v8 + 11) = 0;
  if ( !(unsigned int)Pki_InitializeCriticalSection(v8) )
  {
    CLdapStore::`scalar deleting destructor'(v9);
    return 0;
  }
  v13 = CLdapStore::OpenStore((CLdapStore *)v9, v10, v11, v12, a4, a5, a6, a7);
  if ( !v13 )
    CLdapStore::`scalar deleting destructor'(v9);
  return v13;
}

```

## disassembly

```asm
0x18001d4f0  mov     [rsp+arg_0], rbx
0x18001d4f5  push    rdi
0x18001d4f6  sub     rsp, 40h
0x18001d4fa  mov     ecx, 78h ; 'x'; uBytes
0x18001d4ff  mov     edi, r9d
0x18001d502  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d507  mov     rbx, rax
0x18001d50a  test    rax, rax
0x18001d50d  jz      loc_18001D599
0x18001d513  mov     qword ptr [rax+60h], 0
0x18001d51b  xorps   xmm0, xmm0
0x18001d51e  mov     qword ptr [rax+68h], 0
0x18001d526  mov     rcx, rbx
0x18001d529  mov     qword ptr [rax+70h], 0
0x18001d531  xor     eax, eax
0x18001d533  movups  xmmword ptr [rbx+28h], xmm0
0x18001d537  movups  xmmword ptr [rbx+38h], xmm0
0x18001d53b  movups  xmmword ptr [rbx+48h], xmm0
0x18001d53f  mov     [rbx+58h], rax
0x18001d543  call    Pki_InitializeCriticalSection
0x18001d548  xor     ecx, ecx
0x18001d54a  test    eax, eax
0x18001d54c  setnz   cl
0x18001d54f  test    ecx, ecx
0x18001d551  mov     rcx, rbx; this
0x18001d554  jnz     short loc_18001D55D
0x18001d556  call    ??_GCLdapStore@@QEAAPEAXI@Z; CLdapStore::`scalar deleting destructor'(uint)
0x18001d55b  jmp     short loc_18001D5A4
0x18001d55d  mov     rax, [rsp+48h+arg_30]
0x18001d565  mov     [rsp+48h+var_10], rax; struct _CERT_STORE_PROV_INFO *
0x18001d56a  mov     rax, [rsp+48h+arg_28]
0x18001d56f  mov     [rsp+48h+var_18], rax; void *
0x18001d574  mov     rax, [rsp+48h+arg_20]
0x18001d579  mov     [rsp+48h+var_20], rax; void *
0x18001d57e  mov     [rsp+48h+var_28], edi; unsigned int
0x18001d582  call    ?OpenStore@CLdapStore@@QEAAHPEBDK_KKPEBXPEAXPEAU_CERT_STORE_PROV_INFO@@@Z; CLdapStore::OpenStore(char const *,ulong,unsigned __int64,ulong,void const *,void *,_CERT_STORE_PROV_INFO *)
0x18001d587  mov     edi, eax
0x18001d589  test    eax, eax
0x18001d58b  jnz     short loc_18001D595
0x18001d58d  mov     rcx, rbx; hMem
0x18001d590  call    ??_GCLdapStore@@QEAAPEAXI@Z; CLdapStore::`scalar deleting destructor'(uint)
0x18001d595  mov     eax, edi
0x18001d597  jmp     short loc_18001D5A6
0x18001d599  mov     ecx, 8007000Eh; dwErrCode
0x18001d59e  call    cs:__imp_SetLastError
0x18001d5a4  xor     eax, eax
0x18001d5a6  mov     rbx, [rsp+48h+arg_0]
0x18001d5ab  add     rsp, 40h
0x18001d5af  pop     rdi
0x18001d5b0  retn
```
