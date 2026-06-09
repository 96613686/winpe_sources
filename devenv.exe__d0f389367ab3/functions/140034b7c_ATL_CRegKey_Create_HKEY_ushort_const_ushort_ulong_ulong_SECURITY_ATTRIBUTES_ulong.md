# ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)

- ea: `0x140034b7c`
- end: `0x140034c52`
- name: `?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z`
- size: `214`
- prototype: `int(ATL::CRegKey *__hidden this, HKEY, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001b484`
- `0x140050940`

## callees

- `0x140034a70`
- `0x140034b7c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140034c2c`
- `ADVAPI32!RegCloseKey` at `0x140034c2c`
- `ADVAPI32!RegCreateKeyExW` at `0x140034c03`
- `ADVAPI32!RegCreateKeyExW` at `0x140034c03`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Create(
        ATL::CRegKey *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        DWORD a5,
        REGSAM samDesired,
        struct _SECURITY_ATTRIBUTES *a7,
        unsigned int *a8)
{
  __int16 v8; // di
  ATL::CAtlTransactionManager *v10; // rcx
  LSTATUS v11; // eax
  unsigned int v12; // ecx
  unsigned __int16 *dwOptions; // [rsp+20h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES *phkResult; // [rsp+38h] [rbp-20h]
  HKEY v16; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int16 *lpdwDisposition; // [rsp+78h] [rbp+20h] BYREF

  lpdwDisposition = a4;
  v16 = 0;
  v8 = samDesired;
  v10 = (ATL::CAtlTransactionManager *)*((_QWORD *)this + 2);
  if ( v10 )
    v11 = ATL::CAtlTransactionManager::RegCreateKeyExW(
            v10,
            a2,
            a3,
            (__int64)a4,
            dwOptions,
            a5,
            samDesired,
            phkResult,
            &v16,
            (unsigned int *)&lpdwDisposition);
  else
    v11 = RegCreateKeyExW(a2, a3, 0, 0, a5, samDesired, 0, &v16, (LPDWORD)&lpdwDisposition);
  v12 = v11;
  if ( !v11 )
  {
    if ( a8 )
      *a8 = (unsigned int)lpdwDisposition;
    v12 = 0;
    if ( *(_QWORD *)this )
      v12 = RegCloseKey(*(HKEY *)this);
    *(_QWORD *)this = v16;
    *((_DWORD *)this + 2) = v8 & 0x300;
  }
  return v12;
}

```

## disassembly

```asm
0x140034b7c  mov     rax, rsp
0x140034b7f  mov     [rax+10h], rbx
0x140034b83  mov     [rax+20h], r9
0x140034b87  push    rdi
0x140034b88  sub     rsp, 50h
0x140034b8c  and     qword ptr [rax+8], 0
0x140034b91  lea     rax, [rax+20h]
0x140034b95  mov     edi, [rsp+58h+arg_28]
0x140034b9c  mov     rbx, rcx
0x140034b9f  mov     rcx, [rcx+10h]; this
0x140034ba3  mov     r10, r8
0x140034ba6  mov     r11, rdx
0x140034ba9  test    rcx, rcx
0x140034bac  jz      short loc_140034BD3
0x140034bae  mov     [rsp+58h+var_10], rax; unsigned int *
0x140034bb3  lea     rax, [rsp+58h+arg_0]
0x140034bb8  mov     [rsp+58h+lpdwDisposition], rax; HKEY *
0x140034bbd  mov     eax, [rsp+58h+arg_20]
0x140034bc4  mov     [rsp+58h+var_28], edi; unsigned int
0x140034bc8  mov     [rsp+58h+samDesired], eax; unsigned int
0x140034bcc  call    ?RegCreateKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEBGKPEAGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU3@PEAK@Z; ATL::CAtlTransactionManager::RegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x140034bd1  jmp     short loc_140034C09
0x140034bd3  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x140034bd8  xor     r9d, r9d; lpClass
0x140034bdb  lea     rax, [rsp+58h+arg_0]
0x140034be0  xor     r8d, r8d; Reserved
0x140034be3  mov     [rsp+58h+phkResult], rax; phkResult
0x140034be8  mov     rdx, r10; lpSubKey
0x140034beb  and     qword ptr [rsp+58h+var_28], 0
0x140034bf1  mov     rcx, r11; hKey
0x140034bf4  mov     eax, [rsp+58h+arg_20]
0x140034bfb  mov     [rsp+58h+samDesired], edi; samDesired
0x140034bff  mov     dword ptr [rsp+58h+dwOptions], eax; dwOptions
0x140034c03  call    cs:__imp_RegCreateKeyExW
0x140034c09  mov     ecx, eax
0x140034c0b  test    eax, eax
0x140034c0d  jnz     short loc_140034C45
0x140034c0f  mov     rcx, [rsp+58h+arg_38]
0x140034c17  test    rcx, rcx
0x140034c1a  jz      short loc_140034C22
0x140034c1c  mov     eax, dword ptr [rsp+58h+arg_18]
0x140034c20  mov     [rcx], eax
0x140034c22  xor     ecx, ecx
0x140034c24  cmp     [rbx], rcx
0x140034c27  jz      short loc_140034C34
0x140034c29  mov     rcx, [rbx]; hKey
0x140034c2c  call    cs:__imp_RegCloseKey
0x140034c32  mov     ecx, eax
0x140034c34  mov     rax, [rsp+58h+arg_0]
0x140034c39  and     edi, 300h
0x140034c3f  mov     [rbx], rax
0x140034c42  mov     [rbx+8], edi
0x140034c45  mov     rbx, [rsp+58h+arg_8]
0x140034c4a  mov     eax, ecx
0x140034c4c  add     rsp, 50h
0x140034c50  pop     rdi
0x140034c51  retn
```
