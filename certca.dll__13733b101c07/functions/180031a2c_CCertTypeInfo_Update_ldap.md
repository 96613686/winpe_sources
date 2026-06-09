# CCertTypeInfo::Update(ldap *)

- ea: `0x180031a2c`
- end: `0x180031af2`
- name: `?Update@CCertTypeInfo@@QEAAJPEAUldap@@@Z`
- size: `198`
- prototype: `__int64 __fastcall(CCertTypeInfo *__hidden this, struct ldap *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002ee20`

## callees

- `0x180003be0`
- `0x180010070`
- `0x180031a2c`
- `0x180033f70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031adf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031adf`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::Update(CCertTypeInfo *this, struct ldap *a2)
{
  bool v3; // cf
  const unsigned __int16 *v4; // rdx
  unsigned int v5; // edi
  unsigned int v6; // r8d
  unsigned __int16 *v7; // r9
  int v8; // eax
  unsigned int v10; // [rsp+20h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES *v11; // [rsp+30h] [rbp-28h]
  DWORD v12; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  *((_DWORD *)this + 14) |= 0x20000u;
  v3 = *((_DWORD *)this + 22) < 2u;
  hKey = 0;
  v12 = 0;
  if ( !v3 )
  {
    if ( (*((_DWORD *)this + 19) & 0x10001) != 0 || *((_DWORD *)this + 21) >= 2u && (*((_DWORD *)this + 17) & 0x40) == 0 )
      *((_DWORD *)this + 17) &= ~0x20u;
    else
      *((_DWORD *)this + 17) |= 0x20u;
  }
  v5 = CCertTypeInfo::_UpdateToDS(this, a2);
  if ( !v5 )
  {
    v8 = ctRegCreateKeyEx(
           (HKEY)((*((_DWORD *)this + 31) != 0) - 0x7FFFFFFFLL),
           v4,
           v6,
           v7,
           v10,
           0xF003Fu,
           v11,
           &hKey,
           &v12);
    v5 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v5 = (unsigned __int16)v8 | 0x80070000;
    }
    else
    {
      v5 = CCertTypeInfo::_BaseUpdateToReg(this, hKey);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180031a2c  mov     [rsp+arg_8], rbx
0x180031a31  push    rdi
0x180031a32  sub     rsp, 50h
0x180031a36  bts     dword ptr [rcx+38h], 11h
0x180031a3b  mov     rbx, rcx
0x180031a3e  cmp     dword ptr [rcx+58h], 2
0x180031a42  mov     [rsp+58h+hKey], 0
0x180031a4b  mov     [rsp+58h+arg_0], 0
0x180031a53  jb      short loc_180031A75
0x180031a55  test    dword ptr [rcx+4Ch], 10001h
0x180031a5c  jnz     short loc_180031A71
0x180031a5e  cmp     dword ptr [rcx+54h], 2
0x180031a62  jb      short loc_180031A6B
0x180031a64  mov     eax, [rcx+44h]
0x180031a67  test    al, 40h
0x180031a69  jz      short loc_180031A71
0x180031a6b  or      dword ptr [rcx+44h], 20h
0x180031a6f  jmp     short loc_180031A75
0x180031a71  and     dword ptr [rcx+44h], 0FFFFFFDFh
0x180031a75  call    ?_UpdateToDS@CCertTypeInfo@@IEAAJPEAUldap@@@Z; CCertTypeInfo::_UpdateToDS(ldap *)
0x180031a7a  mov     edi, eax
0x180031a7c  test    eax, eax
0x180031a7e  jnz     short loc_180031AD5
0x180031a80  mov     eax, [rbx+7Ch]
0x180031a83  neg     eax
0x180031a85  lea     rax, [rsp+58h+arg_0]
0x180031a8a  mov     [rsp+58h+var_18], rax; LPDWORD
0x180031a8f  sbb     rcx, rcx
0x180031a92  neg     rcx
0x180031a95  lea     rax, [rsp+58h+hKey]
0x180031a9a  mov     [rsp+58h+var_20], rax; PHKEY
0x180031a9f  add     rcx, 0FFFFFFFF80000001h; HKEY
0x180031aa6  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x180031aae  call    ?ctRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; ctRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180031ab3  mov     edi, eax
0x180031ab5  test    eax, eax
0x180031ab7  jz      short loc_180031AC6
0x180031ab9  jle     short loc_180031AD5
0x180031abb  movzx   edi, ax
0x180031abe  or      edi, 80070000h
0x180031ac4  jmp     short loc_180031AD5
0x180031ac6  mov     rdx, [rsp+58h+hKey]; hKey
0x180031acb  mov     rcx, rbx; this
0x180031ace  call    ?_BaseUpdateToReg@CCertTypeInfo@@IEAAJPEAUHKEY__@@@Z; CCertTypeInfo::_BaseUpdateToReg(HKEY__ *)
0x180031ad3  mov     edi, eax
0x180031ad5  mov     rcx, [rsp+58h+hKey]; hKey
0x180031ada  test    rcx, rcx
0x180031add  jz      short loc_180031AE5
0x180031adf  call    cs:__imp_RegCloseKey
0x180031ae5  mov     rbx, [rsp+58h+arg_8]
0x180031aea  mov     eax, edi
0x180031aec  add     rsp, 50h
0x180031af0  pop     rdi
0x180031af1  retn
```
