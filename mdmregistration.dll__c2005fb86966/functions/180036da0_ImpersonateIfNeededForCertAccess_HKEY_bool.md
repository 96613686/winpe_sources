# ImpersonateIfNeededForCertAccess(HKEY__ *,bool *)

- ea: `0x180036da0`
- end: `0x180036e98`
- name: `?ImpersonateIfNeededForCertAccess@@YAJPEAUHKEY__@@PEA_N@Z`
- size: `248`
- prototype: `__int64 __fastcall(HKEY, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180034b80`

## callees

- `0x1800026d0`
- `0x180036da0`

## import_xrefs

- `DMCmnUtils!InvStrCmpIW` at `0x180036e15`
- `DMCmnUtils!InvStrCmpIW` at `0x180036e15`
- `DMCmnUtils!DmImpersonate` at `0x180036e5b`
- `DMCmnUtils!DmImpersonate` at `0x180036e5b`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180036df7`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180036e41`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180036df7`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180036e41`

## pseudocode

```c
__int64 __fastcall ImpersonateIfNeededForCertAccess(HKEY a1, bool *a2)
{
  int String; // ebx
  unsigned __int16 v6[264]; // [rsp+30h] [rbp-438h] BYREF
  unsigned __int16 v7[264]; // [rsp+240h] [rbp-228h] BYREF

  if ( a2 )
    *a2 = 0;
  v7[0] = 0;
  v6[0] = 0;
  String = OmaDmRegistryGetString(a1, 0, L"SslCertStore", v6, 0x104u);
  if ( String >= 0 && !InvStrCmpIW(v6, L"User") )
  {
    String = OmaDmRegistryGetString(a1, 0, L"SID", v7, 0x104u);
    if ( String >= 0 )
    {
      String = DmImpersonate(v7);
      if ( String >= 0 )
        *a2 = 1;
    }
  }
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180036da0  mov     [rsp+arg_10], rbx
0x180036da5  mov     [rsp+arg_18], rsi
0x180036daa  push    rdi
0x180036dab  sub     rsp, 460h
0x180036db2  mov     rax, cs:__security_cookie
0x180036db9  xor     rax, rsp
0x180036dbc  mov     [rsp+468h+var_18], rax
0x180036dc4  mov     rdi, rdx
0x180036dc7  mov     rsi, rcx
0x180036dca  test    rdx, rdx
0x180036dcd  jz      short loc_180036DD2
0x180036dcf  mov     byte ptr [rdx], 0
0x180036dd2  xor     eax, eax
0x180036dd4  mov     [rsp+468h+var_448], 104h
0x180036ddc  lea     r9, [rsp+468h+var_438]
0x180036de1  mov     [rsp+468h+var_228], ax
0x180036de9  lea     r8, aSslcertstore; "SslCertStore"
0x180036df0  mov     [rsp+468h+var_438], ax
0x180036df5  xor     edx, edx
0x180036df7  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x180036dfe  nop     dword ptr [rax+rax+00h]
0x180036e03  mov     ebx, eax
0x180036e05  test    eax, eax
0x180036e07  js      short loc_180036E70
0x180036e09  lea     rdx, aUser; "User"
0x180036e10  lea     rcx, [rsp+468h+var_438]
0x180036e15  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x180036e1c  nop     dword ptr [rax+rax+00h]
0x180036e21  test    eax, eax
0x180036e23  jnz     short loc_180036E70
0x180036e25  lea     r9, [rsp+468h+var_228]
0x180036e2d  mov     [rsp+468h+var_448], 104h
0x180036e35  lea     r8, aSid; "SID"
0x180036e3c  xor     edx, edx
0x180036e3e  mov     rcx, rsi
0x180036e41  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x180036e48  nop     dword ptr [rax+rax+00h]
0x180036e4d  mov     ebx, eax
0x180036e4f  test    eax, eax
0x180036e51  js      short loc_180036E70
0x180036e53  lea     rcx, [rsp+468h+var_228]
0x180036e5b  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x180036e62  nop     dword ptr [rax+rax+00h]
0x180036e67  mov     ebx, eax
0x180036e69  test    eax, eax
0x180036e6b  js      short loc_180036E70
0x180036e6d  mov     byte ptr [rdi], 1
0x180036e70  mov     eax, ebx
0x180036e72  mov     rcx, [rsp+468h+var_18]
0x180036e7a  xor     rcx, rsp; StackCookie
0x180036e7d  call    __security_check_cookie
0x180036e82  lea     r11, [rsp+468h+var_8]
0x180036e8a  mov     rbx, [r11+20h]
0x180036e8e  mov     rsi, [r11+28h]
0x180036e92  mov     rsp, r11
0x180036e95  pop     rdi
0x180036e96  retn
```
