# ImpersonateIfNeededForCertAccess(HKEY__ *,bool *)

- ea: `0x180056974`
- end: `0x180056a53`
- name: `?ImpersonateIfNeededForCertAccess@@YAJPEAUHKEY__@@PEA_N@Z`
- size: `223`
- prototype: `__int64 __fastcall(HKEY, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001b3ac`

## callees

- `0x18002e1a0`
- `0x180056974`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetString` at `0x1800569cb`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180056a09`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x1800569cb`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180056a09`
- `DMCmnUtils!DmImpersonate` at `0x180056a1d`
- `DMCmnUtils!DmImpersonate` at `0x180056a1d`
- `DMCmnUtils!InvStrCmpIW` at `0x1800569e3`
- `DMCmnUtils!InvStrCmpIW` at `0x1800569e3`

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
0x180056974  mov     [rsp+arg_10], rbx
0x180056979  mov     [rsp+arg_18], rsi
0x18005697e  push    rdi
0x18005697f  sub     rsp, 460h
0x180056986  mov     rax, cs:__security_cookie
0x18005698d  xor     rax, rsp
0x180056990  mov     [rsp+468h+var_18], rax
0x180056998  mov     rdi, rdx
0x18005699b  mov     rsi, rcx
0x18005699e  test    rdx, rdx
0x1800569a1  jz      short loc_1800569A6
0x1800569a3  mov     byte ptr [rdx], 0
0x1800569a6  xor     eax, eax
0x1800569a8  mov     [rsp+468h+var_448], 104h
0x1800569b0  lea     r9, [rsp+468h+var_438]
0x1800569b5  mov     [rsp+468h+var_228], ax
0x1800569bd  lea     r8, aSslcertstore; "SslCertStore"
0x1800569c4  mov     [rsp+468h+var_438], ax
0x1800569c9  xor     edx, edx
0x1800569cb  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x1800569d1  mov     ebx, eax
0x1800569d3  test    eax, eax
0x1800569d5  js      short loc_180056A2C
0x1800569d7  lea     rdx, aUser; "User"
0x1800569de  lea     rcx, [rsp+468h+var_438]
0x1800569e3  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x1800569e9  test    eax, eax
0x1800569eb  jnz     short loc_180056A2C
0x1800569ed  lea     r9, [rsp+468h+var_228]
0x1800569f5  mov     [rsp+468h+var_448], 104h
0x1800569fd  lea     r8, aSid; "SID"
0x180056a04  xor     edx, edx
0x180056a06  mov     rcx, rsi
0x180056a09  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x180056a0f  mov     ebx, eax
0x180056a11  test    eax, eax
0x180056a13  js      short loc_180056A2C
0x180056a15  lea     rcx, [rsp+468h+var_228]
0x180056a1d  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x180056a23  mov     ebx, eax
0x180056a25  test    eax, eax
0x180056a27  js      short loc_180056A2C
0x180056a29  mov     byte ptr [rdi], 1
0x180056a2c  mov     eax, ebx
0x180056a2e  mov     rcx, [rsp+468h+var_18]
0x180056a36  xor     rcx, rsp; StackCookie
0x180056a39  call    __security_check_cookie
0x180056a3e  lea     r11, [rsp+468h+var_8]
0x180056a46  mov     rbx, [r11+20h]
0x180056a4a  mov     rsi, [r11+28h]
0x180056a4e  mov     rsp, r11
0x180056a51  pop     rdi
0x180056a52  retn
```
