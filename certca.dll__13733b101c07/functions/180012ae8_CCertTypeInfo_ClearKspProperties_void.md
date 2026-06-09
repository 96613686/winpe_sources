# CCertTypeInfo::_ClearKspProperties(void)

- ea: `0x180012ae8`
- end: `0x180012dfb`
- name: `?_ClearKspProperties@CCertTypeInfo@@IEAAJXZ`
- size: `787`
- prototype: `__int64 __fastcall(CCertTypeInfo *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003148c`

## callees

- `0x180001920`
- `0x180002ef0`
- `0x180008400`
- `0x18000d520`
- `0x180012ae8`
- `0x1800315b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012dd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012de2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012dd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012de2`

## string_xrefs

- `0x180012b3a`: `msPKI-Template-Schema-Version`
- `0x180012b7e`: `msPKI-Template-Schema-Version`
- `0x180012c39`: `msPKI-Template-Schema-Version`
- `0x180012d0a`: `msPKI-Template-Schema-Version`
- `0x180012bd6`: `msPKI-Template-Minor-Revision`
- `0x180012caa`: `msPKI-Template-Minor-Revision`
- `0x180012b5e`: `msPKI-Key-Security-Descriptor`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_ClearKspProperties(CCertTypeInfo *this)
{
  bool v1; // zf
  unsigned int v3; // eax
  unsigned int Property; // ebx
  unsigned int v5; // ecx
  int v6; // eax
  int v7; // edx
  int v8; // eax
  HLOCAL hMem; // [rsp+58h] [rbp+38h] BYREF
  HLOCAL v11; // [rsp+60h] [rbp+40h] BYREF
  unsigned __int16 *v12; // [rsp+68h] [rbp+48h] BYREF

  v1 = *((_DWORD *)this + 22) == 0;
  v12 = 0;
  hMem = 0;
  v11 = 0;
  if ( !v1 || !(unsigned int)IsV2Property(L"msPKI-RA-Application-Policies") )
  {
    if ( (unsigned int)mylstrcmpNLSub(L"msPKI-RA-Application-Policies", L"msPKI-Template-Minor-Revision", -1, 1) )
    {
      if ( (unsigned int)mylstrcmpNLSub(L"msPKI-RA-Application-Policies", L"msPKI-RA-Signature", -1, 1) )
      {
        if ( (unsigned int)mylstrcmpNLSub(L"msPKI-RA-Application-Policies", L"msPKI-Minimal-Key-Size", -1, 1) )
        {
          if ( (unsigned int)mylstrcmpNLSub(L"msPKI-RA-Application-Policies", L"msPKI-Template-Schema-Version", -1, 1) )
          {
            if ( (unsigned int)mylstrcmpNLSub(L"msPKI-RA-Application-Policies", L"revision", -1, 1) )
            {
              Property = CCertTypeInfo::GetProperty(this, L"msPKI-RA-Application-Policies", (unsigned __int16 ***)&hMem);
              if ( !Property )
                goto LABEL_5;
LABEL_24:
              v7 = Property;
              v5 = 347210536;
LABEL_48:
              CSPrintErrorLineFile(v5, v7);
              goto LABEL_49;
            }
            v6 = *((_DWORD *)this + 36);
          }
          else
          {
            v6 = *((_DWORD *)this + 22);
          }
        }
        else
        {
          v6 = *((_DWORD *)this + 20);
        }
      }
      else
      {
        v6 = *((_DWORD *)this + 21);
      }
    }
    else
    {
      v6 = *((_DWORD *)this + 16);
    }
    LODWORD(hMem) = v6;
    goto LABEL_5;
  }
  if ( (unsigned int)mylstrcmpNLSub(L"msPKI-RA-Application-Policies", L"msPKI-Template-Schema-Version", -1, 1) )
  {
    Property = -2147023728;
    goto LABEL_24;
  }
  LODWORD(hMem) = 1;
LABEL_5:
  if ( !*((_DWORD *)this + 22) && (unsigned int)IsV2Property(L"msPKI-Key-Security-Descriptor") )
  {
    if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-Template-Schema-Version", -1, 1) )
    {
      LODWORD(v11) = 1;
      goto LABEL_9;
    }
    Property = -2147023728;
    goto LABEL_38;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-Template-Minor-Revision", -1, 1) )
  {
    v8 = *((_DWORD *)this + 16);
LABEL_28:
    LODWORD(v11) = v8;
    goto LABEL_9;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-RA-Signature", -1, 1) )
  {
    v8 = *((_DWORD *)this + 21);
    goto LABEL_28;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-Minimal-Key-Size", -1, 1) )
  {
    v8 = *((_DWORD *)this + 20);
    goto LABEL_28;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-Template-Schema-Version", -1, 1) )
  {
    v8 = *((_DWORD *)this + 22);
    goto LABEL_28;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"revision", -1, 1) )
  {
    v8 = *((_DWORD *)this + 36);
    goto LABEL_28;
  }
  Property = CCertTypeInfo::GetProperty(this, L"msPKI-Key-Security-Descriptor", (unsigned __int16 ***)&v11);
  if ( Property )
  {
LABEL_38:
    v7 = Property;
    v5 = 347407144;
    goto LABEL_48;
  }
LABEL_9:
  v3 = CCertTypeInfo::SetPropertyEx(this, L"_internal_use_only_embedded_property", &v12, 0);
  Property = v3;
  if ( v3 )
  {
    v5 = 347669288;
LABEL_47:
    v7 = v3;
    goto LABEL_48;
  }
  if ( hMem )
  {
    if ( *(_QWORD *)hMem )
    {
      v3 = CCertTypeInfo::SetPropertyEx(this, L"msPKI-RA-Application-Policies", (unsigned __int16 **)hMem, 0);
      Property = v3;
      if ( v3 )
      {
        v5 = 348128040;
        goto LABEL_47;
      }
    }
  }
  if ( v11 )
  {
    if ( *(_QWORD *)v11 )
    {
      v3 = CCertTypeInfo::SetPropertyEx(this, L"msPKI-Key-Security-Descriptor", (unsigned __int16 **)v11, 0);
      Property = v3;
      if ( v3 )
      {
        v5 = 348521256;
        goto LABEL_47;
      }
    }
  }
LABEL_49:
  if ( hMem )
    LocalFree(hMem);
  if ( v11 )
    LocalFree(v11);
  return Property;
}

```

## disassembly

```asm
0x180012ae8  mov     [rsp-28h+arg_0], rbx
0x180012aed  push    rbp
0x180012aee  push    rsi
0x180012aef  push    rdi
0x180012af0  push    r12
0x180012af2  push    r15
0x180012af4  mov     rbp, rsp
0x180012af7  sub     rsp, 20h
0x180012afb  cmp     dword ptr [rcx+58h], 0
0x180012aff  lea     r12, aMspkiRaApplica; "msPKI-RA-Application-Policies"
0x180012b06  mov     rdi, rcx
0x180012b09  mov     [rbp+arg_18], 0
0x180012b11  mov     [rbp+hMem], 0
0x180012b19  mov     [rbp+arg_10], 0
0x180012b21  jnz     loc_180012BD3
0x180012b27  mov     rcx, r12; lpString1
0x180012b2a  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x180012b2f  test    eax, eax
0x180012b31  jz      loc_180012BD3
0x180012b37  or      esi, 0FFFFFFFFh
0x180012b3a  lea     rdx, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180012b41  mov     r8d, esi; int
0x180012b44  mov     r9b, 1; bool
0x180012b47  mov     rcx, r12; lpString1
0x180012b4a  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180012b4f  test    eax, eax
0x180012b51  jnz     short loc_180012BC9
0x180012b53  mov     dword ptr [rbp+hMem], 1
0x180012b5a  cmp     dword ptr [rdi+58h], 0
0x180012b5e  lea     r15, aMspkiKeySecuri; "msPKI-Key-Security-Descriptor"
0x180012b65  jnz     loc_180012CA7
0x180012b6b  mov     rcx, r15; lpString1
0x180012b6e  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x180012b73  test    eax, eax
0x180012b75  jz      loc_180012CA7
0x180012b7b  mov     r9b, 1; bool
0x180012b7e  lea     rdx, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180012b85  mov     r8d, esi; int
0x180012b88  mov     rcx, r15; lpString1
0x180012b8b  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180012b90  test    eax, eax
0x180012b92  jnz     loc_180012C9D
0x180012b98  mov     dword ptr [rbp+arg_10], 1
0x180012b9f  xor     r9d, r9d; struct ldap *
0x180012ba2  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x180012ba6  lea     rdx, aInternalUseOnl; "_internal_use_only_embedded_property"
0x180012bad  mov     rcx, rdi; this
0x180012bb0  call    ?SetPropertyEx@CCertTypeInfo@@QEAAJPEBGPEAX1@Z; CCertTypeInfo::SetPropertyEx(ushort const *,void *,void *)
0x180012bb5  mov     ebx, eax
0x180012bb7  test    eax, eax
0x180012bb9  jz      loc_180012D6B
0x180012bbf  mov     ecx, 14B90328h
0x180012bc4  jmp     loc_180012DC3
0x180012bc9  mov     ebx, 80070490h
0x180012bce  jmp     loc_180012C91
0x180012bd3  or      esi, 0FFFFFFFFh
0x180012bd6  lea     rdx, aMspkiTemplateM; "msPKI-Template-Minor-Revision"
0x180012bdd  mov     r8d, esi; int
0x180012be0  mov     r9b, 1; bool
0x180012be3  mov     rcx, r12; lpString1
0x180012be6  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180012beb  test    eax, eax
0x180012bed  jnz     short loc_180012BFA
0x180012bef  mov     eax, [rdi+40h]
0x180012bf2  mov     dword ptr [rbp+hMem], eax
0x180012bf5  jmp     loc_180012B5A
0x180012bfa  mov     r9b, 1; bool
0x180012bfd  lea     rdx, aMspkiRaSignatu; "msPKI-RA-Signature"
0x180012c04  mov     r8d, esi; int
0x180012c07  mov     rcx, r12; lpString1
0x180012c0a  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180012c0f  test    eax, eax
0x180012c11  jnz     short loc_180012C18
0x180012c13  mov     eax, [rdi+54h]
0x180012c16  jmp     short loc_180012BF2
0x180012c18  mov     r9b, 1; bool
0x180012c1b  lea     rdx, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180012c22  mov     r8d, esi; int
0x180012c25  mov     rcx, r12; lpString1
0x180012c28  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180012c2d  test    eax, eax
0x180012c2f  jnz     short loc_180012C36
0x180012c31  mov     eax, [rdi+50h]
0x180012c34  jmp     short loc_180012BF2
0x180012c36  mov     r9b, 1; bool
0x180012c39  lea     rdx, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180012c40  mov     r8d, esi; int
0x180012c43  mov     rcx, r12; lpString1
0x180012c46  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180012c4b  test    eax, eax
0x180012c4d  jnz     short loc_180012C54
0x180012c4f  mov     eax, [rdi+58h]
0x180012c52  jmp     short loc_180012BF2
0x180012c54  mov     r9b, 1; bool
0x180012c57  lea     rdx, aRevision_0; "revision"
0x180012c5e  mov     r8d, esi; int
0x180012c61  mov     rcx, r12; lpString1
0x180012c64  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180012c69  test    eax, eax
0x180012c6b  jnz     short loc_180012C78
0x180012c6d  mov     eax, [rdi+90h]
0x180012c73  jmp     loc_180012BF2
0x180012c78  lea     r8, [rbp+hMem]; unsigned __int16 ***
0x180012c7c  mov     rdx, r12; unsigned __int16 *
0x180012c7f  mov     rcx, rdi; this
0x180012c82  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x180012c87  mov     ebx, eax
0x180012c89  test    eax, eax
0x180012c8b  jz      loc_180012B5A
0x180012c91  mov     edx, ebx
0x180012c93  mov     ecx, 14B20328h
0x180012c98  jmp     loc_180012DC5
0x180012c9d  mov     ebx, 80070490h
0x180012ca2  jmp     loc_180012D62
0x180012ca7  mov     r9b, 1; bool
0x180012caa  lea     rdx, aMspkiTemplateM; "msPKI-Template-Minor-Revision"
0x180012cb1  mov     r8d, esi; int
0x180012cb4  mov     rcx, r15; lpString1
0x180012cb7  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180012cbc  test    eax, eax
0x180012cbe  jnz     short loc_180012CCB
0x180012cc0  mov     eax, [rdi+40h]
0x180012cc3  mov     dword ptr [rbp+arg_10], eax
0x180012cc6  jmp     loc_180012B9F
0x180012ccb  mov     r9b, 1; bool
0x180012cce  lea     rdx, aMspkiRaSignatu; "msPKI-RA-Signature"
0x180012cd5  mov     r8d, esi; int
0x180012cd8  mov     rcx, r15; lpString1
0x180012cdb  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180012ce0  test    eax, eax
0x180012ce2  jnz     short loc_180012CE9
0x180012ce4  mov     eax, [rdi+54h]
0x180012ce7  jmp     short loc_180012CC3
0x180012ce9  mov     r9b, 1; bool
0x180012cec  lea     rdx, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180012cf3  mov     r8d, esi; int
0x180012cf6  mov     rcx, r15; lpString1
0x180012cf9  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180012cfe  test    eax, eax
0x180012d00  jnz     short loc_180012D07
0x180012d02  mov     eax, [rdi+50h]
0x180012d05  jmp     short loc_180012CC3
0x180012d07  mov     r9b, 1; bool
0x180012d0a  lea     rdx, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180012d11  mov     r8d, esi; int
0x180012d14  mov     rcx, r15; lpString1
0x180012d17  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180012d1c  test    eax, eax
0x180012d1e  jnz     short loc_180012D25
0x180012d20  mov     eax, [rdi+58h]
0x180012d23  jmp     short loc_180012CC3
0x180012d25  mov     r9b, 1; bool
0x180012d28  lea     rdx, aRevision_0; "revision"
0x180012d2f  mov     r8d, esi; int
0x180012d32  mov     rcx, r15; lpString1
0x180012d35  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180012d3a  test    eax, eax
0x180012d3c  jnz     short loc_180012D49
0x180012d3e  mov     eax, [rdi+90h]
0x180012d44  jmp     loc_180012CC3
0x180012d49  lea     r8, [rbp+arg_10]; unsigned __int16 ***
0x180012d4d  mov     rdx, r15; unsigned __int16 *
0x180012d50  mov     rcx, rdi; this
0x180012d53  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x180012d58  mov     ebx, eax
0x180012d5a  test    eax, eax
0x180012d5c  jz      loc_180012B9F
0x180012d62  mov     edx, ebx
0x180012d64  mov     ecx, 14B50328h
0x180012d69  jmp     short loc_180012DC5
0x180012d6b  mov     rcx, [rbp+hMem]
0x180012d6f  test    rcx, rcx
0x180012d72  jz      short loc_180012D98
0x180012d74  cmp     qword ptr [rcx], 0
0x180012d78  jz      short loc_180012D98
0x180012d7a  mov     r8, rcx; unsigned __int16 **
0x180012d7d  xor     r9d, r9d; struct ldap *
0x180012d80  mov     rcx, rdi; this
0x180012d83  mov     rdx, r12; unsigned __int16 *
0x180012d86  call    ?SetPropertyEx@CCertTypeInfo@@QEAAJPEBGPEAX1@Z; CCertTypeInfo::SetPropertyEx(ushort const *,void *,void *)
0x180012d8b  mov     ebx, eax
0x180012d8d  test    eax, eax
0x180012d8f  jz      short loc_180012D98
0x180012d91  mov     ecx, 14C00328h
0x180012d96  jmp     short loc_180012DC3
0x180012d98  mov     rcx, [rbp+arg_10]
0x180012d9c  test    rcx, rcx
0x180012d9f  jz      short loc_180012DCA
0x180012da1  cmp     qword ptr [rcx], 0
0x180012da5  jz      short loc_180012DCA
0x180012da7  mov     r8, rcx; unsigned __int16 **
0x180012daa  xor     r9d, r9d; struct ldap *
0x180012dad  mov     rcx, rdi; this
0x180012db0  mov     rdx, r15; unsigned __int16 *
0x180012db3  call    ?SetPropertyEx@CCertTypeInfo@@QEAAJPEBGPEAX1@Z; CCertTypeInfo::SetPropertyEx(ushort const *,void *,void *)
0x180012db8  mov     ebx, eax
0x180012dba  test    eax, eax
0x180012dbc  jz      short loc_180012DCA
0x180012dbe  mov     ecx, 14C60328h; unsigned int
0x180012dc3  mov     edx, eax; int
0x180012dc5  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180012dca  mov     rcx, [rbp+hMem]; hMem
0x180012dce  test    rcx, rcx
0x180012dd1  jz      short loc_180012DD9
0x180012dd3  call    cs:__imp_LocalFree
0x180012dd9  mov     rcx, [rbp+arg_10]; hMem
0x180012ddd  test    rcx, rcx
0x180012de0  jz      short loc_180012DE8
0x180012de2  call    cs:__imp_LocalFree
0x180012de8  mov     eax, ebx
0x180012dea  mov     rbx, [rsp+20h+arg_0]
0x180012def  add     rsp, 20h
0x180012df3  pop     r15
0x180012df5  pop     r12
0x180012df7  pop     rdi
0x180012df8  pop     rsi
0x180012df9  pop     rbp
0x180012dfa  retn
```
