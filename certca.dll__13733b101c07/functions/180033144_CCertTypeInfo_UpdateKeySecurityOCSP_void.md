# CCertTypeInfo::_UpdateKeySecurityOCSP(void)

- ea: `0x180033144`
- end: `0x18003330d`
- name: `?_UpdateKeySecurityOCSP@CCertTypeInfo@@IEAAJXZ`
- size: `457`
- prototype: `__int64 __fastcall(CCertTypeInfo *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180030224`

## callees

- `0x180001920`
- `0x180002ef0`
- `0x180008400`
- `0x18000d520`
- `0x1800280a0`
- `0x1800315b4`
- `0x180033144`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800332f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800332f7`

## string_xrefs

- `0x18003318b`: `msPKI-Template-Schema-Version`
- `0x18003324c`: `msPKI-Template-Schema-Version`
- `0x1800331ec`: `msPKI-Template-Minor-Revision`
- `0x180033158`: `msPKI-Key-Security-Descriptor`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_UpdateKeySecurityOCSP(CCertTypeInfo *this)
{
  bool v1; // zf
  unsigned __int16 v3; // dx
  int Property; // eax
  unsigned int v5; // ebx
  unsigned int v6; // ecx
  int v7; // eax
  unsigned __int16 *v9[2]; // [rsp+20h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp+28h] BYREF
  unsigned __int16 *v11; // [rsp+60h] [rbp+30h] BYREF

  v1 = *((_DWORD *)this + 22) == 0;
  v9[1] = 0;
  hMem = 0;
  v11 = 0;
  if ( !v1 || !(unsigned int)IsV2Property(L"msPKI-Key-Security-Descriptor") )
  {
    if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-Template-Minor-Revision", -1, 1) )
    {
      if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-RA-Signature", -1, 1) )
      {
        if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-Minimal-Key-Size", -1, 1) )
        {
          if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-Template-Schema-Version", -1, 1) )
          {
            if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"revision", -1, 1) )
            {
              Property = CCertTypeInfo::GetProperty(this, L"msPKI-Key-Security-Descriptor", (unsigned __int16 ***)&hMem);
              if ( !Property )
                goto LABEL_5;
LABEL_22:
              v6 = 505676584;
LABEL_27:
              v5 = Property;
              goto LABEL_28;
            }
            v7 = *((_DWORD *)this + 36);
          }
          else
          {
            v7 = *((_DWORD *)this + 22);
          }
        }
        else
        {
          v7 = *((_DWORD *)this + 20);
        }
      }
      else
      {
        v7 = *((_DWORD *)this + 21);
      }
    }
    else
    {
      v7 = *((_DWORD *)this + 16);
    }
    LODWORD(hMem) = v7;
    goto LABEL_5;
  }
  if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Key-Security-Descriptor", L"msPKI-Template-Schema-Version", -1, 1) )
  {
    Property = -2147023728;
    goto LABEL_22;
  }
  LODWORD(hMem) = 1;
LABEL_5:
  if ( !hMem || !*(_QWORD *)hMem )
  {
    Property = -2147023728;
    v6 = 506069800;
    goto LABEL_27;
  }
  Property = mySetControlFlagsOnSDDL(*(const unsigned __int16 **)hMem, v3, &v11);
  v5 = Property;
  if ( Property )
  {
    v6 = 506528552;
  }
  else
  {
    v9[0] = v11;
    Property = CCertTypeInfo::SetPropertyEx(this, L"msPKI-Key-Security-Descriptor", v9, 0);
    v5 = Property;
    if ( !Property )
    {
      *((_DWORD *)this + 47) = 1;
      v5 = 0;
      goto LABEL_29;
    }
    v6 = 507183912;
  }
LABEL_28:
  CSPrintErrorLineFile(v6, Property);
LABEL_29:
  if ( hMem )
    LocalFree(hMem);
  return v5;
}

```

## disassembly

```asm
0x180033144  mov     [rsp-18h+arg_0], rbx
0x180033149  push    rbp
0x18003314a  push    rdi
0x18003314b  push    r14
0x18003314d  mov     rbp, rsp
0x180033150  sub     rsp, 30h
0x180033154  cmp     dword ptr [rcx+58h], 0
0x180033158  lea     r14, aMspkiKeySecuri; "msPKI-Key-Security-Descriptor"
0x18003315f  mov     rdi, rcx
0x180033162  mov     [rbp+var_8], 0
0x18003316a  mov     [rbp+hMem], 0
0x180033172  mov     [rbp+arg_10], 0
0x18003317a  jnz     short loc_1800331E9
0x18003317c  mov     rcx, r14; lpString1
0x18003317f  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x180033184  test    eax, eax
0x180033186  jz      short loc_1800331E9
0x180033188  mov     r9b, 1; bool
0x18003318b  lea     rdx, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180033192  or      r8d, 0FFFFFFFFh; int
0x180033196  mov     rcx, r14; lpString1
0x180033199  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18003319e  test    eax, eax
0x1800331a0  jnz     short loc_1800331DF
0x1800331a2  mov     dword ptr [rbp+hMem], 1
0x1800331a9  mov     rax, [rbp+hMem]
0x1800331ad  test    rax, rax
0x1800331b0  jz      loc_1800332DB
0x1800331b6  mov     rcx, [rax]; unsigned __int16 *
0x1800331b9  test    rcx, rcx
0x1800331bc  jz      loc_1800332DB
0x1800331c2  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x1800331c6  call    ?mySetControlFlagsOnSDDL@@YAJPEBGGPEAPEAG@Z; mySetControlFlagsOnSDDL(ushort const *,ushort,ushort * *)
0x1800331cb  mov     ebx, eax
0x1800331cd  test    eax, eax
0x1800331cf  jz      loc_1800332A6
0x1800331d5  mov     ecx, 1E310328h
0x1800331da  jmp     loc_1800332E7
0x1800331df  mov     eax, 80070490h
0x1800331e4  jmp     loc_18003329F
0x1800331e9  or      ebx, 0FFFFFFFFh
0x1800331ec  lea     rdx, aMspkiTemplateM; "msPKI-Template-Minor-Revision"
0x1800331f3  mov     r8d, ebx; int
0x1800331f6  mov     r9b, 1; bool
0x1800331f9  mov     rcx, r14; lpString1
0x1800331fc  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180033201  test    eax, eax
0x180033203  jnz     short loc_18003320D
0x180033205  mov     eax, [rdi+40h]
0x180033208  mov     dword ptr [rbp+hMem], eax
0x18003320b  jmp     short loc_1800331A9
0x18003320d  mov     r9b, 1; bool
0x180033210  lea     rdx, aMspkiRaSignatu; "msPKI-RA-Signature"
0x180033217  mov     r8d, ebx; int
0x18003321a  mov     rcx, r14; lpString1
0x18003321d  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180033222  test    eax, eax
0x180033224  jnz     short loc_18003322B
0x180033226  mov     eax, [rdi+54h]
0x180033229  jmp     short loc_180033208
0x18003322b  mov     r9b, 1; bool
0x18003322e  lea     rdx, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180033235  mov     r8d, ebx; int
0x180033238  mov     rcx, r14; lpString1
0x18003323b  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180033240  test    eax, eax
0x180033242  jnz     short loc_180033249
0x180033244  mov     eax, [rdi+50h]
0x180033247  jmp     short loc_180033208
0x180033249  mov     r9b, 1; bool
0x18003324c  lea     rdx, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180033253  mov     r8d, ebx; int
0x180033256  mov     rcx, r14; lpString1
0x180033259  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18003325e  test    eax, eax
0x180033260  jnz     short loc_180033267
0x180033262  mov     eax, [rdi+58h]
0x180033265  jmp     short loc_180033208
0x180033267  mov     r9b, 1; bool
0x18003326a  lea     rdx, aRevision_0; "revision"
0x180033271  mov     r8d, ebx; int
0x180033274  mov     rcx, r14; lpString1
0x180033277  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18003327c  test    eax, eax
0x18003327e  jnz     short loc_180033288
0x180033280  mov     eax, [rdi+90h]
0x180033286  jmp     short loc_180033208
0x180033288  lea     r8, [rbp+hMem]; unsigned __int16 ***
0x18003328c  mov     rdx, r14; unsigned __int16 *
0x18003328f  mov     rcx, rdi; this
0x180033292  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x180033297  test    eax, eax
0x180033299  jz      loc_1800331A9
0x18003329f  mov     ecx, 1E240328h
0x1800332a4  jmp     short loc_1800332E5
0x1800332a6  mov     rax, [rbp+arg_10]
0x1800332aa  lea     r8, [rbp+var_10]; unsigned __int16 **
0x1800332ae  xor     r9d, r9d; struct ldap *
0x1800332b1  mov     [rbp+var_10], rax
0x1800332b5  mov     rdx, r14; unsigned __int16 *
0x1800332b8  mov     rcx, rdi; this
0x1800332bb  call    ?SetPropertyEx@CCertTypeInfo@@QEAAJPEBGPEAX1@Z; CCertTypeInfo::SetPropertyEx(ushort const *,void *,void *)
0x1800332c0  mov     ebx, eax
0x1800332c2  test    eax, eax
0x1800332c4  jz      short loc_1800332CD
0x1800332c6  mov     ecx, 1E3B0328h
0x1800332cb  jmp     short loc_1800332E7
0x1800332cd  mov     dword ptr [rdi+0BCh], 1
0x1800332d7  xor     ebx, ebx
0x1800332d9  jmp     short loc_1800332EE
0x1800332db  mov     eax, 80070490h
0x1800332e0  mov     ecx, 1E2A0328h; unsigned int
0x1800332e5  mov     ebx, eax
0x1800332e7  mov     edx, eax; int
0x1800332e9  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800332ee  mov     rcx, [rbp+hMem]; hMem
0x1800332f2  test    rcx, rcx
0x1800332f5  jz      short loc_1800332FD
0x1800332f7  call    cs:__imp_LocalFree
0x1800332fd  mov     eax, ebx
0x1800332ff  mov     rbx, [rsp+30h+arg_0]
0x180033304  add     rsp, 30h
0x180033308  pop     r14
0x18003330a  pop     rdi
0x18003330b  pop     rbp
0x18003330c  retn
```
