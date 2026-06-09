# CCertTypeInfo::_PersistSchemaVersion(ulong)

- ea: `0x180012f0c`
- end: `0x1800131cc`
- name: `?_PersistSchemaVersion@CCertTypeInfo@@IEAAJK@Z`
- size: `704`
- prototype: `__int64 __fastcall(CCertTypeInfo *this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800315b4`

## callees

- `0x180001920`
- `0x180002ef0`
- `0x180008400`
- `0x18000d520`
- `0x180012f0c`
- `0x1800315b4`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180012fa1`
- `msvcrt!_wcsicmp` at `0x180012fa1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800131b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800131b0`

## string_xrefs

- `0x180012f6b`: `msPKI-Template-Schema-Version`
- `0x180012fcc`: `msPKI-Template-Schema-Version`
- `0x180013053`: `msPKI-Template-Schema-Version`
- `0x180013113`: `msPKI-Template-Schema-Version`
- `0x180012ffd`: `msPKI-Template-Minor-Revision`
- `0x1800130bd`: `msPKI-Template-Minor-Revision`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_PersistSchemaVersion(CCertTypeInfo *this, int a2)
{
  unsigned int Property; // ebx
  int v4; // edx
  int v5; // eax
  int v6; // edx
  unsigned int v7; // ecx
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned __int16 **v11; // [rsp+48h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp+30h] BYREF

  Property = 0;
  LODWORD(v11) = 0;
  hMem = 0;
  v4 = a2 - 2;
  if ( !v4 )
    goto LABEL_10;
  if ( v4 != 1 )
    goto LABEL_46;
  if ( !*((_DWORD *)this + 22) && (unsigned int)IsV2Property(L"msPKI-Asymmetric-Algorithm") )
  {
    if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Asymmetric-Algorithm", L"msPKI-Template-Schema-Version", -1, 1) )
    {
      LODWORD(hMem) = 1;
LABEL_7:
      Property = 0;
      goto LABEL_8;
    }
    Property = -2147023728;
LABEL_27:
    v6 = Property;
    v7 = 556925736;
LABEL_45:
    CSPrintErrorLineFile(v7, v6);
    goto LABEL_46;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Asymmetric-Algorithm", L"msPKI-Template-Minor-Revision", -1, 1) )
  {
    v5 = *((_DWORD *)this + 16);
LABEL_25:
    LODWORD(hMem) = v5;
    goto LABEL_7;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Asymmetric-Algorithm", L"msPKI-RA-Signature", -1, 1) )
  {
    v5 = *((_DWORD *)this + 21);
    goto LABEL_25;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Asymmetric-Algorithm", L"msPKI-Minimal-Key-Size", -1, 1) )
  {
    v5 = *((_DWORD *)this + 20);
    goto LABEL_25;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Asymmetric-Algorithm", L"msPKI-Template-Schema-Version", -1, 1) )
  {
    v5 = *((_DWORD *)this + 22);
    goto LABEL_25;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"msPKI-Asymmetric-Algorithm", L"revision", -1, 1) )
  {
    v5 = *((_DWORD *)this + 36);
    goto LABEL_25;
  }
  Property = CCertTypeInfo::GetProperty(this, L"msPKI-Asymmetric-Algorithm", (unsigned __int16 ***)&hMem);
  if ( Property )
    goto LABEL_27;
LABEL_8:
  if ( !hMem )
    return Property;
  if ( !_wcsicmp(*(const wchar_t **)hMem, L"RSA") )
  {
LABEL_10:
    if ( !*((_DWORD *)this + 22) && (unsigned int)IsV2Property(L"msPKI-Minimal-Key-Size") )
    {
      if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Minimal-Key-Size", L"msPKI-Template-Schema-Version", -1, 1) )
      {
        Property = -2147023728;
LABEL_40:
        v6 = Property;
        v7 = 558039848;
        goto LABEL_45;
      }
LABEL_43:
      LODWORD(v11) = 2048;
      v9 = CCertTypeInfo::SetPropertyEx(this, L"msPKI-Minimal-Key-Size", (unsigned __int16 **)&v11, 0);
      Property = v9;
      if ( !v9 )
        goto LABEL_46;
      v6 = v9;
      v7 = 558433064;
      goto LABEL_45;
    }
    if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Minimal-Key-Size", L"msPKI-Template-Minor-Revision", -1, 1) )
    {
      if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Minimal-Key-Size", L"msPKI-RA-Signature", -1, 1) )
      {
        if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Minimal-Key-Size", L"msPKI-Minimal-Key-Size", -1, 1) )
        {
          if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Minimal-Key-Size", L"msPKI-Template-Schema-Version", -1, 1) )
          {
            if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Minimal-Key-Size", L"revision", -1, 1) )
            {
              Property = CCertTypeInfo::GetProperty(this, L"msPKI-Minimal-Key-Size", &v11);
              if ( Property )
                goto LABEL_40;
              v8 = (unsigned int)v11;
              goto LABEL_42;
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
    LODWORD(v11) = v8;
    Property = 0;
LABEL_42:
    if ( v8 >= 0x800 )
      goto LABEL_46;
    goto LABEL_43;
  }
LABEL_46:
  if ( hMem )
    LocalFree(hMem);
  return Property;
}

```

## disassembly

```asm
0x180012f0c  mov     [rsp-18h+arg_0], rbx
0x180012f11  mov     [rsp-18h+arg_18], rdi
0x180012f16  push    rbp
0x180012f17  push    r14
0x180012f19  push    r15
0x180012f1b  mov     rbp, rsp
0x180012f1e  sub     rsp, 20h
0x180012f22  xor     ebx, ebx
0x180012f24  lea     r15, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180012f2b  or      r14d, 0FFFFFFFFh
0x180012f2f  mov     dword ptr [rbp+arg_8], ebx
0x180012f32  mov     [rbp+hMem], rbx
0x180012f36  mov     rdi, rcx
0x180012f39  sub     edx, 2
0x180012f3c  jz      short loc_180012FAF
0x180012f3e  cmp     edx, 1
0x180012f41  jnz     loc_1800131A7
0x180012f47  cmp     dword ptr [rcx+58h], 0
0x180012f4b  lea     rbx, aMspkiAsymmetri; "msPKI-Asymmetric-Algorithm"
0x180012f52  jnz     loc_180012FFA
0x180012f58  mov     rcx, rbx; lpString1
0x180012f5b  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x180012f60  test    eax, eax
0x180012f62  jz      loc_180012FFA
0x180012f68  mov     r9b, 1; bool
0x180012f6b  lea     rdx, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180012f72  mov     r8d, r14d; int
0x180012f75  mov     rcx, rbx; lpString1
0x180012f78  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180012f7d  test    eax, eax
0x180012f7f  jnz     short loc_180012FF0
0x180012f81  mov     dword ptr [rbp+hMem], 1
0x180012f88  xor     ebx, ebx
0x180012f8a  mov     rcx, [rbp+hMem]
0x180012f8e  test    rcx, rcx
0x180012f91  jz      loc_1800131B6
0x180012f97  mov     rcx, [rcx]; String1
0x180012f9a  lea     rdx, aRsa; "RSA"
0x180012fa1  call    cs:__imp__wcsicmp
0x180012fa7  test    eax, eax
0x180012fa9  jnz     loc_1800131A7
0x180012faf  cmp     dword ptr [rdi+58h], 0
0x180012fb3  jnz     loc_1800130BA
0x180012fb9  mov     rcx, r15; lpString1
0x180012fbc  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x180012fc1  test    eax, eax
0x180012fc3  jz      loc_1800130BA
0x180012fc9  mov     r9b, 1; bool
0x180012fcc  lea     rdx, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180012fd3  mov     r8d, r14d; int
0x180012fd6  mov     rcx, r15; lpString1
0x180012fd9  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180012fde  test    eax, eax
0x180012fe0  jz      loc_18001317C
0x180012fe6  mov     ebx, 80070490h
0x180012feb  jmp     loc_180013169
0x180012ff0  mov     ebx, 80070490h
0x180012ff5  jmp     loc_1800130AE
0x180012ffa  mov     r9b, 1; bool
0x180012ffd  lea     rdx, aMspkiTemplateM; "msPKI-Template-Minor-Revision"
0x180013004  mov     r8d, r14d; int
0x180013007  mov     rcx, rbx; lpString1
0x18001300a  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18001300f  test    eax, eax
0x180013011  jnz     short loc_180013018
0x180013013  mov     eax, [rdi+40h]
0x180013016  jmp     short loc_18001308D
0x180013018  mov     r9b, 1; bool
0x18001301b  lea     rdx, aMspkiRaSignatu; "msPKI-RA-Signature"
0x180013022  mov     r8d, r14d; int
0x180013025  mov     rcx, rbx; lpString1
0x180013028  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18001302d  test    eax, eax
0x18001302f  jnz     short loc_180013036
0x180013031  mov     eax, [rdi+54h]
0x180013034  jmp     short loc_18001308D
0x180013036  mov     r9b, 1; bool
0x180013039  mov     r8d, r14d; int
0x18001303c  mov     rdx, r15; unsigned __int16 *
0x18001303f  mov     rcx, rbx; lpString1
0x180013042  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180013047  test    eax, eax
0x180013049  jnz     short loc_180013050
0x18001304b  mov     eax, [rdi+50h]
0x18001304e  jmp     short loc_18001308D
0x180013050  mov     r9b, 1; bool
0x180013053  lea     rdx, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x18001305a  mov     r8d, r14d; int
0x18001305d  mov     rcx, rbx; lpString1
0x180013060  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180013065  test    eax, eax
0x180013067  jnz     short loc_18001306E
0x180013069  mov     eax, [rdi+58h]
0x18001306c  jmp     short loc_18001308D
0x18001306e  mov     r9b, 1; bool
0x180013071  lea     rdx, aRevision_0; "revision"
0x180013078  mov     r8d, r14d; int
0x18001307b  mov     rcx, rbx; lpString1
0x18001307e  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180013083  test    eax, eax
0x180013085  jnz     short loc_180013095
0x180013087  mov     eax, [rdi+90h]
0x18001308d  mov     dword ptr [rbp+hMem], eax
0x180013090  jmp     loc_180012F88
0x180013095  lea     r8, [rbp+hMem]; unsigned __int16 ***
0x180013099  mov     rdx, rbx; unsigned __int16 *
0x18001309c  mov     rcx, rdi; this
0x18001309f  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x1800130a4  mov     ebx, eax
0x1800130a6  test    eax, eax
0x1800130a8  jz      loc_180012F8A
0x1800130ae  mov     edx, ebx
0x1800130b0  mov     ecx, 21320328h
0x1800130b5  jmp     loc_1800131A2
0x1800130ba  mov     r9b, 1; bool
0x1800130bd  lea     rdx, aMspkiTemplateM; "msPKI-Template-Minor-Revision"
0x1800130c4  mov     r8d, r14d; int
0x1800130c7  mov     rcx, r15; lpString1
0x1800130ca  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x1800130cf  test    eax, eax
0x1800130d1  jnz     short loc_1800130D8
0x1800130d3  mov     eax, [rdi+40h]
0x1800130d6  jmp     short loc_18001314D
0x1800130d8  mov     r9b, 1; bool
0x1800130db  lea     rdx, aMspkiRaSignatu; "msPKI-RA-Signature"
0x1800130e2  mov     r8d, r14d; int
0x1800130e5  mov     rcx, r15; lpString1
0x1800130e8  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x1800130ed  test    eax, eax
0x1800130ef  jnz     short loc_1800130F6
0x1800130f1  mov     eax, [rdi+54h]
0x1800130f4  jmp     short loc_18001314D
0x1800130f6  mov     r9b, 1; bool
0x1800130f9  mov     r8d, r14d; int
0x1800130fc  mov     rdx, r15; unsigned __int16 *
0x1800130ff  mov     rcx, r15; lpString1
0x180013102  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180013107  test    eax, eax
0x180013109  jnz     short loc_180013110
0x18001310b  mov     eax, [rdi+50h]
0x18001310e  jmp     short loc_18001314D
0x180013110  mov     r9b, 1; bool
0x180013113  lea     rdx, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x18001311a  mov     r8d, r14d; int
0x18001311d  mov     rcx, r15; lpString1
0x180013120  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180013125  test    eax, eax
0x180013127  jnz     short loc_18001312E
0x180013129  mov     eax, [rdi+58h]
0x18001312c  jmp     short loc_18001314D
0x18001312e  mov     r9b, 1; bool
0x180013131  lea     rdx, aRevision_0; "revision"
0x180013138  mov     r8d, r14d; int
0x18001313b  mov     rcx, r15; lpString1
0x18001313e  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180013143  test    eax, eax
0x180013145  jnz     short loc_180013154
0x180013147  mov     eax, [rdi+90h]
0x18001314d  mov     dword ptr [rbp+arg_8], eax
0x180013150  xor     ebx, ebx
0x180013152  jmp     short loc_180013175
0x180013154  lea     r8, [rbp+arg_8]; unsigned __int16 ***
0x180013158  mov     rdx, r15; unsigned __int16 *
0x18001315b  mov     rcx, rdi; this
0x18001315e  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x180013163  mov     ebx, eax
0x180013165  test    eax, eax
0x180013167  jz      short loc_180013172
0x180013169  mov     edx, ebx
0x18001316b  mov     ecx, 21430328h
0x180013170  jmp     short loc_1800131A2
0x180013172  mov     eax, dword ptr [rbp+arg_8]
0x180013175  cmp     eax, 800h
0x18001317a  jnb     short loc_1800131A7
0x18001317c  xor     r9d, r9d; struct ldap *
0x18001317f  mov     dword ptr [rbp+arg_8], 800h
0x180013186  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x18001318a  mov     rdx, r15; unsigned __int16 *
0x18001318d  mov     rcx, rdi; this
0x180013190  call    ?SetPropertyEx@CCertTypeInfo@@QEAAJPEBGPEAX1@Z; CCertTypeInfo::SetPropertyEx(ushort const *,void *,void *)
0x180013195  mov     ebx, eax
0x180013197  test    eax, eax
0x180013199  jz      short loc_1800131A7
0x18001319b  mov     edx, eax; int
0x18001319d  mov     ecx, 21490328h; unsigned int
0x1800131a2  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800131a7  mov     rcx, [rbp+hMem]; hMem
0x1800131ab  test    rcx, rcx
0x1800131ae  jz      short loc_1800131B6
0x1800131b0  call    cs:__imp_LocalFree
0x1800131b6  mov     rdi, [rsp+20h+arg_18]
0x1800131bb  mov     eax, ebx
0x1800131bd  mov     rbx, [rsp+20h+arg_0]
0x1800131c2  add     rsp, 20h
0x1800131c6  pop     r15
0x1800131c8  pop     r14
0x1800131ca  pop     rbp
0x1800131cb  retn
```
