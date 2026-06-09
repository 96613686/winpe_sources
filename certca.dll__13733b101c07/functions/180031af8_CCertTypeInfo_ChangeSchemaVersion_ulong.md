# CCertTypeInfo::_ChangeSchemaVersion(ulong)

- ea: `0x180031af8`
- end: `0x180031dd5`
- name: `?_ChangeSchemaVersion@CCertTypeInfo@@IEAAJK@Z`
- size: `733`
- prototype: `__int64 __fastcall(CCertTypeInfo *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800315b4`

## callees

- `0x180001920`
- `0x180002ef0`
- `0x180008400`
- `0x18000d520`
- `0x18003148c`
- `0x1800315b4`
- `0x180031af8`
- `0x180032d6c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031dbe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031dbe`

## string_xrefs

- `0x180031b60`: `msPKI-Template-Schema-Version`
- `0x180031c05`: `msPKI-Template-Schema-Version`
- `0x180031b94`: `msPKI-Template-Minor-Revision`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_ChangeSchemaVersion(CCertTypeInfo *this, unsigned int a2)
{
  unsigned int v2; // r14d
  bool v3; // r12
  bool v6; // r15
  int Property; // ebx
  int v8; // eax
  int v9; // eax
  unsigned int v10; // ecx
  HLOCAL hMem; // [rsp+60h] [rbp+40h] BYREF
  unsigned __int16 *v13; // [rsp+68h] [rbp+48h] BYREF
  unsigned __int16 *v14; // [rsp+70h] [rbp+50h] BYREF

  v2 = *((_DWORD *)this + 22);
  v3 = 0;
  hMem = 0;
  v6 = v2 == 2 || v2 >= 4 && (*((_DWORD *)this + 18) & 0x100) != 0;
  v14 = 0;
  if ( v2 || !(unsigned int)IsV2Property(L"msPKI-RA-Application-Policies") )
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
              if ( Property < 0 )
                goto LABEL_25;
              goto LABEL_23;
            }
            v8 = *((_DWORD *)this + 36);
          }
          else
          {
            v8 = *((_DWORD *)this + 22);
          }
        }
        else
        {
          v8 = *((_DWORD *)this + 20);
        }
      }
      else
      {
        v8 = *((_DWORD *)this + 21);
      }
    }
    else
    {
      v8 = *((_DWORD *)this + 16);
    }
    LODWORD(hMem) = v8;
    Property = 0;
  }
  else
  {
    if ( (unsigned int)mylstrcmpNLSub(L"msPKI-RA-Application-Policies", L"msPKI-Template-Schema-Version", -1, 1) )
    {
      Property = -2147023728;
      goto LABEL_25;
    }
    LODWORD(hMem) = 1;
    Property = 0;
  }
LABEL_23:
  if ( hMem )
    v3 = *(_QWORD *)hMem != 0;
LABEL_25:
  if ( a2 == 2 || *((_DWORD *)this + 22) == 2 )
  {
    v9 = CCertTypeInfo::SetPropertyEx(this, L"_internal_use_only_embedded_property", &v14, 0);
    Property = v9;
    if ( v9 )
    {
      v10 = 561709864;
LABEL_53:
      CSPrintErrorLineFile(v10, v9);
      goto LABEL_54;
    }
  }
  if ( v6 )
  {
    if ( a2 != 3 )
      goto LABEL_31;
  }
  else if ( a2 != 2 )
  {
    goto LABEL_31;
  }
  v9 = CCertTypeInfo::SetPropertyEx(this, L"pKIDefaultCSPs", &v14, 0);
  Property = v9;
  if ( v9 )
  {
    v10 = 562299688;
    goto LABEL_53;
  }
  if ( !v6 && a2 == 2 )
  {
    LODWORD(v13) = 2048;
    v9 = CCertTypeInfo::SetPropertyEx(this, L"msPKI-Minimal-Key-Size", &v13, 0);
    Property = v9;
    if ( v9 )
    {
      v10 = 562955048;
      goto LABEL_53;
    }
  }
LABEL_31:
  *((_DWORD *)this + 22) = a2;
  if ( v3 )
  {
    v9 = CCertTypeInfo::SetPropertyEx(this, L"msPKI-RA-Application-Policies", (unsigned __int16 **)hMem, 0);
    Property = v9;
    if ( v9 )
    {
      v10 = 563741480;
      goto LABEL_53;
    }
  }
  if ( v2 == 2 && a2 == 3 )
  {
    v9 = CCertTypeInfo::_SetDefaultKspProperties(this);
    Property = v9;
    if ( v9 )
    {
      v10 = 564462376;
      goto LABEL_53;
    }
    goto LABEL_48;
  }
  if ( a2 < 4 || !v6 )
  {
LABEL_48:
    *((_DWORD *)this + 18) &= ~0x100u;
    goto LABEL_49;
  }
  *((_DWORD *)this + 18) |= 0x100u;
LABEL_49:
  if ( v2 >= 3 && a2 == 2 )
  {
    v9 = CCertTypeInfo::SetFlags(this, 3u, *((_DWORD *)this + 18) & 0xFFFFFFBF);
    Property = v9;
    if ( v9 )
    {
      v10 = 565904168;
      goto LABEL_53;
    }
  }
LABEL_54:
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180031af8  push    rbp
0x180031afa  push    rbx
0x180031afb  push    rsi
0x180031afc  push    rdi
0x180031afd  push    r12
0x180031aff  push    r14
0x180031b01  push    r15
0x180031b03  mov     rbp, rsp
0x180031b06  sub     rsp, 20h
0x180031b0a  mov     r14d, [rcx+58h]
0x180031b0e  xor     r12b, r12b
0x180031b11  mov     [rbp+hMem], 0
0x180031b19  mov     esi, edx
0x180031b1b  mov     rdi, rcx
0x180031b1e  mov     ebx, 1
0x180031b23  cmp     r14d, 2
0x180031b27  jz      short loc_180031B3D
0x180031b29  cmp     r14d, 4
0x180031b2d  jb      short loc_180031B38
0x180031b2f  test    dword ptr [rcx+48h], 100h
0x180031b36  jnz     short loc_180031B3D
0x180031b38  xor     r15b, r15b
0x180031b3b  jmp     short loc_180031B40
0x180031b3d  mov     r15b, bl
0x180031b40  mov     [rbp+arg_10], 0
0x180031b48  test    r14d, r14d
0x180031b4b  jnz     short loc_180031B91
0x180031b4d  lea     rcx, aMspkiRaApplica; "msPKI-RA-Application-Policies"
0x180031b54  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x180031b59  test    eax, eax
0x180031b5b  jz      short loc_180031B91
0x180031b5d  mov     r9b, bl; bool
0x180031b60  lea     rdx, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180031b67  or      r8d, 0FFFFFFFFh; int
0x180031b6b  lea     rcx, aMspkiRaApplica; "msPKI-RA-Application-Policies"
0x180031b72  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180031b77  test    eax, eax
0x180031b79  jnz     short loc_180031B87
0x180031b7b  mov     eax, ebx
0x180031b7d  mov     dword ptr [rbp+hMem], ebx
0x180031b80  xor     ebx, ebx
0x180031b82  jmp     loc_180031C6A
0x180031b87  mov     ebx, 80070490h
0x180031b8c  jmp     loc_180031C7F
0x180031b91  mov     r9b, bl; bool
0x180031b94  lea     rdx, aMspkiTemplateM; "msPKI-Template-Minor-Revision"
0x180031b9b  or      ebx, 0FFFFFFFFh
0x180031b9e  lea     rcx, aMspkiRaApplica; "msPKI-RA-Application-Policies"
0x180031ba5  mov     r8d, ebx; int
0x180031ba8  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180031bad  test    eax, eax
0x180031baf  jnz     short loc_180031BBE
0x180031bb1  mov     eax, [rdi+40h]
0x180031bb4  mov     dword ptr [rbp+hMem], eax
0x180031bb7  xor     ebx, ebx
0x180031bb9  jmp     loc_180031C65
0x180031bbe  mov     r9b, 1; bool
0x180031bc1  lea     rdx, aMspkiRaSignatu; "msPKI-RA-Signature"
0x180031bc8  mov     r8d, ebx; int
0x180031bcb  lea     rcx, aMspkiRaApplica; "msPKI-RA-Application-Policies"
0x180031bd2  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180031bd7  test    eax, eax
0x180031bd9  jnz     short loc_180031BE0
0x180031bdb  mov     eax, [rdi+54h]
0x180031bde  jmp     short loc_180031BB4
0x180031be0  mov     r9b, 1; bool
0x180031be3  lea     rdx, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180031bea  mov     r8d, ebx; int
0x180031bed  lea     rcx, aMspkiRaApplica; "msPKI-RA-Application-Policies"
0x180031bf4  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180031bf9  test    eax, eax
0x180031bfb  jnz     short loc_180031C02
0x180031bfd  mov     eax, [rdi+50h]
0x180031c00  jmp     short loc_180031BB4
0x180031c02  mov     r9b, 1; bool
0x180031c05  lea     rdx, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180031c0c  mov     r8d, ebx; int
0x180031c0f  lea     rcx, aMspkiRaApplica; "msPKI-RA-Application-Policies"
0x180031c16  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180031c1b  test    eax, eax
0x180031c1d  jnz     short loc_180031C24
0x180031c1f  mov     eax, [rdi+58h]
0x180031c22  jmp     short loc_180031BB4
0x180031c24  mov     r9b, 1; bool
0x180031c27  lea     rdx, aRevision_0; "revision"
0x180031c2e  mov     r8d, ebx; int
0x180031c31  lea     rcx, aMspkiRaApplica; "msPKI-RA-Application-Policies"
0x180031c38  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180031c3d  test    eax, eax
0x180031c3f  jnz     short loc_180031C4C
0x180031c41  mov     eax, [rdi+90h]
0x180031c47  jmp     loc_180031BB4
0x180031c4c  lea     r8, [rbp+hMem]; unsigned __int16 ***
0x180031c50  mov     rcx, rdi; this
0x180031c53  lea     rdx, aMspkiRaApplica; "msPKI-RA-Application-Policies"
0x180031c5a  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x180031c5f  mov     ebx, eax
0x180031c61  test    eax, eax
0x180031c63  js      short loc_180031C7F
0x180031c65  mov     eax, 1
0x180031c6a  mov     rcx, [rbp+hMem]
0x180031c6e  test    rcx, rcx
0x180031c71  jz      short loc_180031C7F
0x180031c73  cmp     qword ptr [rcx], 0
0x180031c77  movzx   r12d, r12b
0x180031c7b  cmovnz  r12d, eax
0x180031c7f  cmp     esi, 2
0x180031c82  jz      short loc_180031C8A
0x180031c84  cmp     dword ptr [rdi+58h], 2
0x180031c88  jnz     short loc_180031CB0
0x180031c8a  xor     r9d, r9d; struct ldap *
0x180031c8d  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x180031c91  lea     rdx, aInternalUseOnl; "_internal_use_only_embedded_property"
0x180031c98  mov     rcx, rdi; this
0x180031c9b  call    ?SetPropertyEx@CCertTypeInfo@@QEAAJPEBGPEAX1@Z; CCertTypeInfo::SetPropertyEx(ushort const *,void *,void *)
0x180031ca0  mov     ebx, eax
0x180031ca2  test    eax, eax
0x180031ca4  jz      short loc_180031CB0
0x180031ca6  mov     ecx, 217B0328h
0x180031cab  jmp     loc_180031DAE
0x180031cb0  test    r15b, r15b
0x180031cb3  jz      short loc_180031CEC
0x180031cb5  cmp     esi, 3
0x180031cb8  jz      short loc_180031CF1
0x180031cba  mov     [rdi+58h], esi
0x180031cbd  test    r12b, r12b
0x180031cc0  jz      loc_180031D4F
0x180031cc6  mov     r8, [rbp+hMem]; unsigned __int16 **
0x180031cca  lea     rdx, aMspkiRaApplica; "msPKI-RA-Application-Policies"
0x180031cd1  xor     r9d, r9d; struct ldap *
0x180031cd4  mov     rcx, rdi; this
0x180031cd7  call    ?SetPropertyEx@CCertTypeInfo@@QEAAJPEBGPEAX1@Z; CCertTypeInfo::SetPropertyEx(ushort const *,void *,void *)
0x180031cdc  mov     ebx, eax
0x180031cde  test    eax, eax
0x180031ce0  jz      short loc_180031D4F
0x180031ce2  mov     ecx, 219A0328h
0x180031ce7  jmp     loc_180031DAE
0x180031cec  cmp     esi, 2
0x180031cef  jnz     short loc_180031CBA
0x180031cf1  xor     r9d, r9d; struct ldap *
0x180031cf4  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x180031cf8  lea     rdx, aPkidefaultcsps; "pKIDefaultCSPs"
0x180031cff  mov     rcx, rdi; this
0x180031d02  call    ?SetPropertyEx@CCertTypeInfo@@QEAAJPEBGPEAX1@Z; CCertTypeInfo::SetPropertyEx(ushort const *,void *,void *)
0x180031d07  mov     ebx, eax
0x180031d09  test    eax, eax
0x180031d0b  jz      short loc_180031D17
0x180031d0d  mov     ecx, 21840328h
0x180031d12  jmp     loc_180031DAE
0x180031d17  test    r15b, r15b
0x180031d1a  jnz     short loc_180031CBA
0x180031d1c  cmp     esi, 2
0x180031d1f  jnz     short loc_180031CBA
0x180031d21  xor     r9d, r9d; struct ldap *
0x180031d24  mov     dword ptr [rbp+arg_8], 800h
0x180031d2b  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x180031d2f  mov     rcx, rdi; this
0x180031d32  lea     rdx, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180031d39  call    ?SetPropertyEx@CCertTypeInfo@@QEAAJPEBGPEAX1@Z; CCertTypeInfo::SetPropertyEx(ushort const *,void *,void *)
0x180031d3e  mov     ebx, eax
0x180031d40  test    eax, eax
0x180031d42  jz      loc_180031CBA
0x180031d48  mov     ecx, 218E0328h
0x180031d4d  jmp     short loc_180031DAE
0x180031d4f  cmp     r14d, 2
0x180031d53  jnz     short loc_180031D6F
0x180031d55  cmp     esi, 3
0x180031d58  jnz     short loc_180031D6F
0x180031d5a  mov     rcx, rdi; this
0x180031d5d  call    ?_SetDefaultKspProperties@CCertTypeInfo@@IEAAJXZ; CCertTypeInfo::_SetDefaultKspProperties(void)
0x180031d62  mov     ebx, eax
0x180031d64  test    eax, eax
0x180031d66  jz      short loc_180031D80
0x180031d68  mov     ecx, 21A50328h
0x180031d6d  jmp     short loc_180031DAE
0x180031d6f  cmp     esi, 4
0x180031d72  jb      short loc_180031D80
0x180031d74  test    r15b, r15b
0x180031d77  jz      short loc_180031D80
0x180031d79  bts     dword ptr [rdi+48h], 8
0x180031d7e  jmp     short loc_180031D85
0x180031d80  btr     dword ptr [rdi+48h], 8
0x180031d85  mov     r8d, [rdi+48h]
0x180031d89  cmp     r14d, 3
0x180031d8d  jb      short loc_180031DB5
0x180031d8f  cmp     esi, 2
0x180031d92  jnz     short loc_180031DB5
0x180031d94  and     r8d, 0FFFFFFBFh; unsigned int
0x180031d98  lea     edx, [rsi+1]; unsigned int
0x180031d9b  mov     rcx, rdi; this
0x180031d9e  call    ?SetFlags@CCertTypeInfo@@QEAAJKK@Z; CCertTypeInfo::SetFlags(ulong,ulong)
0x180031da3  mov     ebx, eax
0x180031da5  test    eax, eax
0x180031da7  jz      short loc_180031DB5
0x180031da9  mov     ecx, 21BB0328h; unsigned int
0x180031dae  mov     edx, eax; int
0x180031db0  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180031db5  mov     rcx, [rbp+hMem]; hMem
0x180031db9  test    rcx, rcx
0x180031dbc  jz      short loc_180031DC4
0x180031dbe  call    cs:__imp_LocalFree
0x180031dc4  mov     eax, ebx
0x180031dc6  add     rsp, 20h
0x180031dca  pop     r15
0x180031dcc  pop     r14
0x180031dce  pop     r12
0x180031dd0  pop     rdi
0x180031dd1  pop     rsi
0x180031dd2  pop     rbx
0x180031dd3  pop     rbp
0x180031dd4  retn
```
