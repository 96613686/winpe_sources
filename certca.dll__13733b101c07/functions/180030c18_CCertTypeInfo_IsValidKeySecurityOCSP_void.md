# CCertTypeInfo::IsValidKeySecurityOCSP(void)

- ea: `0x180030c18`
- end: `0x180030eb7`
- name: `?IsValidKeySecurityOCSP@CCertTypeInfo@@QEAAHXZ`
- size: `671`
- prototype: `__int64 __fastcall(CCertTypeInfo *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e710`
- `0x180030224`

## callees

- `0x180001920`
- `0x180002ef0`
- `0x180005010`
- `0x18000d520`
- `0x1800270d8`
- `0x180030c18`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030e8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030e9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030e8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030e9e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180030e73`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180030e73`

## string_xrefs

- `0x180030c34`: `msPKI-Template-Schema-Version`
- `0x180030c8e`: `msPKI-Template-Minor-Revision`
- `0x180030d9b`: `msPKI-Template-Minor-Revision`
- `0x180030d62`: `msPKI-Key-Security-Descriptor`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::IsValidKeySecurityOCSP(CCertTypeInfo *this)
{
  unsigned int v2; // edi
  int v3; // eax
  unsigned int v4; // edx
  unsigned int *v5; // r9
  int v6; // eax
  HLOCAL v7; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+28h] [rbp-8h] BYREF
  WORD pControl; // [rsp+68h] [rbp+38h] BYREF
  unsigned __int16 **v12; // [rsp+70h] [rbp+40h] BYREF
  DWORD dwRevision; // [rsp+78h] [rbp+48h] BYREF

  LODWORD(v12) = 0;
  v2 = 1;
  dwRevision = 0;
  pControl = 0;
  hMem = 0;
  pSecurityDescriptor = 0;
  if ( *((_DWORD *)this + 22) || !(unsigned int)IsV2Property(L"msPKI-Template-Schema-Version") )
  {
    if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Template-Schema-Version", L"msPKI-Template-Minor-Revision", -1, 1) )
    {
      if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Template-Schema-Version", L"msPKI-RA-Signature", -1, 1) )
      {
        if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Template-Schema-Version", L"msPKI-Minimal-Key-Size", -1, 1) )
        {
          if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Template-Schema-Version", L"msPKI-Template-Schema-Version", -1, 1) )
          {
            if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Template-Schema-Version", L"revision", -1, 1) )
            {
              if ( CCertTypeInfo::GetProperty(this, L"msPKI-Template-Schema-Version", (HLOCAL *)&v12) )
                goto LABEL_40;
              goto LABEL_17;
            }
            v3 = *((_DWORD *)this + 36);
          }
          else
          {
            v3 = *((_DWORD *)this + 22);
          }
        }
        else
        {
          v3 = *((_DWORD *)this + 20);
        }
      }
      else
      {
        v3 = *((_DWORD *)this + 21);
      }
    }
    else
    {
      v3 = *((_DWORD *)this + 16);
    }
    LODWORD(v12) = v3;
    goto LABEL_17;
  }
  if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Template-Schema-Version", L"msPKI-Template-Schema-Version", -1, 1) )
    goto LABEL_40;
  LODWORD(v12) = 1;
LABEL_17:
  if ( (CCertTypeInfo::GetFlags(this, 1u) & 0x1000) == 0 || (unsigned int)v12 <= 2 )
    goto LABEL_40;
  if ( !*((_DWORD *)this + 22) && (unsigned int)IsV2Property(L"msPKI-Key-Security-Descriptor") )
  {
    if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-Template-Schema-Version", -1, 1) )
    {
      LODWORD(hMem) = 1;
      goto LABEL_35;
    }
LABEL_40:
    v7 = hMem;
    goto LABEL_41;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-Template-Minor-Revision", -1, 1) )
  {
    v6 = *((_DWORD *)this + 16);
LABEL_25:
    LODWORD(hMem) = v6;
    goto LABEL_35;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-RA-Signature", -1, 1) )
  {
    v6 = *((_DWORD *)this + 21);
    goto LABEL_25;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-Minimal-Key-Size", -1, 1) )
  {
    v6 = *((_DWORD *)this + 20);
    goto LABEL_25;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-Template-Schema-Version", -1, 1) )
  {
    v6 = *((_DWORD *)this + 22);
    goto LABEL_25;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"revision", -1, 1) )
  {
    v6 = *((_DWORD *)this + 36);
    goto LABEL_25;
  }
  if ( CCertTypeInfo::GetProperty(this, L"msPKI-Key-Security-Descriptor", &hMem) )
    goto LABEL_40;
LABEL_35:
  v7 = hMem;
  if ( !hMem )
    goto LABEL_43;
  if ( *(_QWORD *)hMem )
  {
    if ( (unsigned int)myConvertStringSecurityDescriptorToSecurityDescriptor(
                         *(const unsigned __int16 **)hMem,
                         v4,
                         &pSecurityDescriptor,
                         v5)
      && GetSecurityDescriptorControl(pSecurityDescriptor, &pControl, &dwRevision) )
    {
      v2 = (pControl >> 12) & 1;
    }
    goto LABEL_40;
  }
LABEL_41:
  if ( v7 )
    LocalFree(v7);
LABEL_43:
  if ( pSecurityDescriptor )
    LocalFree(pSecurityDescriptor);
  return v2;
}

```

## disassembly

```asm
0x180030c18  mov     [rsp-28h+arg_0], rbx
0x180030c1d  push    rbp
0x180030c1e  push    rsi
0x180030c1f  push    rdi
0x180030c20  push    r12
0x180030c22  push    r15
0x180030c24  mov     rbp, rsp
0x180030c27  sub     rsp, 30h
0x180030c2b  xor     eax, eax
0x180030c2d  mov     dword ptr [rbp+arg_10], 0
0x180030c34  lea     r12, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180030c3b  mov     rbx, rcx
0x180030c3e  mov     edi, 1
0x180030c43  mov     [rbp+dwRevision], 0
0x180030c4a  mov     [rbp+pControl], ax
0x180030c4e  mov     [rbp+hMem], rax
0x180030c52  mov     [rbp+pSecurityDescriptor], rax
0x180030c56  cmp     [rcx+58h], eax
0x180030c59  jnz     short loc_180030C8B
0x180030c5b  mov     rcx, r12; lpString1
0x180030c5e  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x180030c63  test    eax, eax
0x180030c65  jz      short loc_180030C8B
0x180030c67  or      esi, 0FFFFFFFFh
0x180030c6a  mov     r9b, dil; bool
0x180030c6d  mov     r8d, esi; int
0x180030c70  mov     rdx, r12; unsigned __int16 *
0x180030c73  mov     rcx, r12; lpString1
0x180030c76  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030c7b  test    eax, eax
0x180030c7d  jnz     loc_180030E86
0x180030c83  mov     dword ptr [rbp+arg_10], edi
0x180030c86  jmp     loc_180030D40
0x180030c8b  or      esi, 0FFFFFFFFh
0x180030c8e  lea     rdx, aMspkiTemplateM; "msPKI-Template-Minor-Revision"
0x180030c95  mov     r8d, esi; int
0x180030c98  mov     r9b, dil; bool
0x180030c9b  mov     rcx, r12; lpString1
0x180030c9e  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030ca3  test    eax, eax
0x180030ca5  jnz     short loc_180030CB2
0x180030ca7  mov     eax, [rbx+40h]
0x180030caa  mov     dword ptr [rbp+arg_10], eax
0x180030cad  jmp     loc_180030D40
0x180030cb2  mov     r9b, dil; bool
0x180030cb5  lea     rdx, aMspkiRaSignatu; "msPKI-RA-Signature"
0x180030cbc  mov     r8d, esi; int
0x180030cbf  mov     rcx, r12; lpString1
0x180030cc2  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030cc7  test    eax, eax
0x180030cc9  jnz     short loc_180030CD0
0x180030ccb  mov     eax, [rbx+54h]
0x180030cce  jmp     short loc_180030CAA
0x180030cd0  mov     r9b, dil; bool
0x180030cd3  lea     rdx, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180030cda  mov     r8d, esi; int
0x180030cdd  mov     rcx, r12; lpString1
0x180030ce0  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030ce5  test    eax, eax
0x180030ce7  jnz     short loc_180030CEE
0x180030ce9  mov     eax, [rbx+50h]
0x180030cec  jmp     short loc_180030CAA
0x180030cee  mov     r9b, dil; bool
0x180030cf1  mov     r8d, esi; int
0x180030cf4  mov     rdx, r12; unsigned __int16 *
0x180030cf7  mov     rcx, r12; lpString1
0x180030cfa  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030cff  test    eax, eax
0x180030d01  jnz     short loc_180030D08
0x180030d03  mov     eax, [rbx+58h]
0x180030d06  jmp     short loc_180030CAA
0x180030d08  mov     r9b, dil; bool
0x180030d0b  lea     rdx, aRevision_0; "revision"
0x180030d12  mov     r8d, esi; int
0x180030d15  mov     rcx, r12; lpString1
0x180030d18  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030d1d  test    eax, eax
0x180030d1f  jnz     short loc_180030D29
0x180030d21  mov     eax, [rbx+90h]
0x180030d27  jmp     short loc_180030CAA
0x180030d29  lea     r8, [rbp+arg_10]; unsigned __int16 ***
0x180030d2d  mov     rdx, r12; unsigned __int16 *
0x180030d30  mov     rcx, rbx; this
0x180030d33  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x180030d38  test    eax, eax
0x180030d3a  jnz     loc_180030E86
0x180030d40  mov     edx, edi; unsigned int
0x180030d42  mov     rcx, rbx; this
0x180030d45  call    ?GetFlags@CCertTypeInfo@@QEAAKK@Z; CCertTypeInfo::GetFlags(ulong)
0x180030d4a  bt      eax, 0Ch
0x180030d4e  jnb     loc_180030E86
0x180030d54  cmp     dword ptr [rbp+arg_10], 2
0x180030d58  jbe     loc_180030E86
0x180030d5e  cmp     dword ptr [rbx+58h], 0
0x180030d62  lea     r15, aMspkiKeySecuri; "msPKI-Key-Security-Descriptor"
0x180030d69  jnz     short loc_180030D98
0x180030d6b  mov     rcx, r15; lpString1
0x180030d6e  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x180030d73  test    eax, eax
0x180030d75  jz      short loc_180030D98
0x180030d77  mov     r9b, dil; bool
0x180030d7a  mov     r8d, esi; int
0x180030d7d  mov     rdx, r12; unsigned __int16 *
0x180030d80  mov     rcx, r15; lpString1
0x180030d83  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030d88  test    eax, eax
0x180030d8a  jnz     loc_180030E86
0x180030d90  mov     dword ptr [rbp+hMem], edi
0x180030d93  jmp     loc_180030E46
0x180030d98  mov     r9b, dil; bool
0x180030d9b  lea     rdx, aMspkiTemplateM; "msPKI-Template-Minor-Revision"
0x180030da2  mov     r8d, esi; int
0x180030da5  mov     rcx, r15; lpString1
0x180030da8  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030dad  test    eax, eax
0x180030daf  jnz     short loc_180030DBC
0x180030db1  mov     eax, [rbx+40h]
0x180030db4  mov     dword ptr [rbp+hMem], eax
0x180030db7  jmp     loc_180030E46
0x180030dbc  mov     r9b, dil; bool
0x180030dbf  lea     rdx, aMspkiRaSignatu; "msPKI-RA-Signature"
0x180030dc6  mov     r8d, esi; int
0x180030dc9  mov     rcx, r15; lpString1
0x180030dcc  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030dd1  test    eax, eax
0x180030dd3  jnz     short loc_180030DDA
0x180030dd5  mov     eax, [rbx+54h]
0x180030dd8  jmp     short loc_180030DB4
0x180030dda  mov     r9b, dil; bool
0x180030ddd  lea     rdx, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180030de4  mov     r8d, esi; int
0x180030de7  mov     rcx, r15; lpString1
0x180030dea  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030def  test    eax, eax
0x180030df1  jnz     short loc_180030DF8
0x180030df3  mov     eax, [rbx+50h]
0x180030df6  jmp     short loc_180030DB4
0x180030df8  mov     r9b, dil; bool
0x180030dfb  mov     r8d, esi; int
0x180030dfe  mov     rdx, r12; unsigned __int16 *
0x180030e01  mov     rcx, r15; lpString1
0x180030e04  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030e09  test    eax, eax
0x180030e0b  jnz     short loc_180030E12
0x180030e0d  mov     eax, [rbx+58h]
0x180030e10  jmp     short loc_180030DB4
0x180030e12  mov     r9b, dil; bool
0x180030e15  lea     rdx, aRevision_0; "revision"
0x180030e1c  mov     r8d, esi; int
0x180030e1f  mov     rcx, r15; lpString1
0x180030e22  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030e27  test    eax, eax
0x180030e29  jnz     short loc_180030E33
0x180030e2b  mov     eax, [rbx+90h]
0x180030e31  jmp     short loc_180030DB4
0x180030e33  lea     r8, [rbp+hMem]; unsigned __int16 ***
0x180030e37  mov     rdx, r15; unsigned __int16 *
0x180030e3a  mov     rcx, rbx; this
0x180030e3d  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x180030e42  test    eax, eax
0x180030e44  jnz     short loc_180030E86
0x180030e46  mov     rcx, [rbp+hMem]
0x180030e4a  test    rcx, rcx
0x180030e4d  jz      short loc_180030E95
0x180030e4f  mov     rax, [rcx]
0x180030e52  test    rax, rax
0x180030e55  jz      short loc_180030E8A
0x180030e57  lea     r8, [rbp+pSecurityDescriptor]; void **
0x180030e5b  mov     rcx, rax; unsigned __int16 *
0x180030e5e  call    ?myConvertStringSecurityDescriptorToSecurityDescriptor@@YAHPEBGKPEAPEAXPEAK@Z; myConvertStringSecurityDescriptorToSecurityDescriptor(ushort const *,ulong,void * *,ulong *)
0x180030e63  test    eax, eax
0x180030e65  jz      short loc_180030E86
0x180030e67  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180030e6b  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180030e6f  lea     rdx, [rbp+pControl]; pControl
0x180030e73  call    cs:__imp_GetSecurityDescriptorControl
0x180030e79  test    eax, eax
0x180030e7b  jz      short loc_180030E86
0x180030e7d  movzx   eax, [rbp+pControl]
0x180030e81  shr     eax, 0Ch
0x180030e84  and     edi, eax
0x180030e86  mov     rcx, [rbp+hMem]; hMem
0x180030e8a  test    rcx, rcx
0x180030e8d  jz      short loc_180030E95
0x180030e8f  call    cs:__imp_LocalFree
0x180030e95  mov     rcx, [rbp+pSecurityDescriptor]; hMem
0x180030e99  test    rcx, rcx
0x180030e9c  jz      short loc_180030EA4
0x180030e9e  call    cs:__imp_LocalFree
0x180030ea4  mov     rbx, [rsp+30h+arg_0]
0x180030ea9  mov     eax, edi
0x180030eab  add     rsp, 30h
0x180030eaf  pop     r15
0x180030eb1  pop     r12
0x180030eb3  pop     rdi
0x180030eb4  pop     rsi
0x180030eb5  pop     rbp
0x180030eb6  retn
```
