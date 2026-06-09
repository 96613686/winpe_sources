# IsDSInfoNewer(CCertTypeInfo *,_CERT_TYPE_DEFAULT *)

- ea: `0x1800308c0`
- end: `0x180030c0f`
- name: `?IsDSInfoNewer@@YAHPEAVCCertTypeInfo@@PEAU_CERT_TYPE_DEFAULT@@@Z`
- size: `847`
- prototype: `bool __fastcall(struct CCertTypeInfo *this, struct _CERT_TYPE_DEFAULT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180030224`

## callees

- `0x180001920`
- `0x180002ef0`
- `0x18000d520`
- `0x1800308c0`

## string_xrefs

- `0x18003090a`: `msPKI-Template-Schema-Version`
- `0x180030903`: `msPKI-Template-Minor-Revision`

## pseudocode

```c
bool __fastcall IsDSInfoNewer(struct CCertTypeInfo *this, struct _CERT_TYPE_DEFAULT *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // eax
  bool v8; // cf
  unsigned __int16 **v9; // [rsp+60h] [rbp+40h] BYREF
  unsigned __int16 **v10; // [rsp+70h] [rbp+50h] BYREF
  unsigned __int16 **v11; // [rsp+78h] [rbp+58h] BYREF

  LODWORD(v9) = 0;
  LODWORD(v10) = 0;
  LODWORD(v11) = 0;
  if ( !this || !a2 )
    return 1;
  if ( *((_DWORD *)this + 22) || !(unsigned int)IsV2Property(L"msPKI-Template-Schema-Version") )
  {
    v4 = 1;
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
              if ( CCertTypeInfo::GetProperty(this, L"msPKI-Template-Schema-Version", (HLOCAL *)&v9) )
                return 0;
              goto LABEL_19;
            }
            v5 = *((_DWORD *)this + 36);
          }
          else
          {
            v5 = *((_DWORD *)this + 22);
          }
        }
        else
        {
          v5 = *((_DWORD *)this + 20);
        }
      }
      else
      {
        v5 = *((_DWORD *)this + 21);
      }
    }
    else
    {
      v5 = *((_DWORD *)this + 16);
    }
    LODWORD(v9) = v5;
    goto LABEL_19;
  }
  v4 = 1;
  if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Template-Schema-Version", L"msPKI-Template-Schema-Version", -1, 1) )
    return 0;
  LODWORD(v9) = 1;
LABEL_19:
  if ( !*((_DWORD *)this + 22) && (unsigned int)IsV2Property(L"revision") )
  {
    if ( !(unsigned int)mylstrcmpNLSub(L"revision", L"msPKI-Template-Schema-Version", -1, 1) )
    {
      LODWORD(v10) = 1;
      goto LABEL_35;
    }
    return 0;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"revision", L"msPKI-Template-Minor-Revision", -1, 1) )
  {
    v6 = *((_DWORD *)this + 16);
LABEL_25:
    LODWORD(v10) = v6;
    goto LABEL_35;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"revision", L"msPKI-RA-Signature", -1, 1) )
  {
    v6 = *((_DWORD *)this + 21);
    goto LABEL_25;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"revision", L"msPKI-Minimal-Key-Size", -1, 1) )
  {
    v6 = *((_DWORD *)this + 20);
    goto LABEL_25;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"revision", L"msPKI-Template-Schema-Version", -1, 1) )
  {
    v6 = *((_DWORD *)this + 22);
    goto LABEL_25;
  }
  if ( !(unsigned int)mylstrcmpNLSub(L"revision", L"revision", -1, 1) )
  {
    v6 = *((_DWORD *)this + 36);
    goto LABEL_25;
  }
  if ( CCertTypeInfo::GetProperty(this, L"revision", (HLOCAL *)&v10) )
    return 0;
LABEL_35:
  if ( *((_DWORD *)this + 22) || !(unsigned int)IsV2Property(L"msPKI-Template-Minor-Revision") )
  {
    if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Template-Minor-Revision", L"msPKI-Template-Minor-Revision", -1, 1) )
    {
      if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Template-Minor-Revision", L"msPKI-RA-Signature", -1, 1) )
      {
        if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Template-Minor-Revision", L"msPKI-Minimal-Key-Size", -1, 1) )
        {
          if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Template-Minor-Revision", L"msPKI-Template-Schema-Version", -1, 1) )
          {
            if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Template-Minor-Revision", L"revision", -1, 1) )
            {
              if ( CCertTypeInfo::GetProperty(this, L"msPKI-Template-Minor-Revision", (HLOCAL *)&v11) )
                return 0;
              v4 = (unsigned int)v11;
            }
            else
            {
              v4 = *((_DWORD *)this + 36);
            }
          }
          else
          {
            v4 = *((_DWORD *)this + 22);
          }
        }
        else
        {
          v4 = *((_DWORD *)this + 20);
        }
      }
      else
      {
        v4 = *((_DWORD *)this + 21);
      }
    }
    else
    {
      v4 = *((_DWORD *)this + 16);
    }
  }
  else if ( (unsigned int)mylstrcmpNLSub(L"msPKI-Template-Minor-Revision", L"msPKI-Template-Schema-Version", -1, 1) )
  {
    return 0;
  }
  v8 = (unsigned int)v9 < *((_DWORD *)a2 + 25);
  if ( (_DWORD)v9 == *((_DWORD *)a2 + 25) )
  {
    v8 = (unsigned int)v10 < *((_DWORD *)a2 + 18);
    if ( (_DWORD)v10 == *((_DWORD *)a2 + 18) )
      v8 = v4 < *((_DWORD *)a2 + 19);
  }
  return !v8;
}

```

## disassembly

```asm
0x1800308c0  push    rbp
0x1800308c2  push    rbx
0x1800308c3  push    rsi
0x1800308c4  push    rdi
0x1800308c5  push    r12
0x1800308c7  push    r13
0x1800308c9  push    r14
0x1800308cb  mov     rbp, rsp
0x1800308ce  sub     rsp, 20h
0x1800308d2  mov     dword ptr [rbp+arg_0], 0
0x1800308d9  mov     r14, rdx
0x1800308dc  mov     dword ptr [rbp+arg_10], 0
0x1800308e3  mov     rdi, rcx
0x1800308e6  mov     dword ptr [rbp+arg_18], 0
0x1800308ed  test    rcx, rcx
0x1800308f0  jz      loc_180030BFB
0x1800308f6  test    rdx, rdx
0x1800308f9  jz      loc_180030BFB
0x1800308ff  cmp     dword ptr [rcx+58h], 0
0x180030903  lea     r13, aMspkiTemplateM; "msPKI-Template-Minor-Revision"
0x18003090a  lea     r12, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180030911  jnz     short loc_180030948
0x180030913  mov     rcx, r12; lpString1
0x180030916  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x18003091b  test    eax, eax
0x18003091d  jz      short loc_180030948
0x18003091f  mov     ebx, 1
0x180030924  or      esi, 0FFFFFFFFh
0x180030927  mov     r9b, bl; bool
0x18003092a  mov     r8d, esi; int
0x18003092d  mov     rdx, r12; unsigned __int16 *
0x180030930  mov     rcx, r12; lpString1
0x180030933  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030938  test    eax, eax
0x18003093a  jnz     loc_180030B29
0x180030940  mov     dword ptr [rbp+arg_0], ebx
0x180030943  jmp     loc_1800309FE
0x180030948  mov     ebx, 1
0x18003094d  or      esi, 0FFFFFFFFh
0x180030950  mov     r9b, bl; bool
0x180030953  mov     r8d, esi; int
0x180030956  mov     rdx, r13; unsigned __int16 *
0x180030959  mov     rcx, r12; lpString1
0x18003095c  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030961  test    eax, eax
0x180030963  jnz     short loc_180030970
0x180030965  mov     eax, [rdi+40h]
0x180030968  mov     dword ptr [rbp+arg_0], eax
0x18003096b  jmp     loc_1800309FE
0x180030970  mov     r9b, bl; bool
0x180030973  lea     rdx, aMspkiRaSignatu; "msPKI-RA-Signature"
0x18003097a  mov     r8d, esi; int
0x18003097d  mov     rcx, r12; lpString1
0x180030980  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030985  test    eax, eax
0x180030987  jnz     short loc_18003098E
0x180030989  mov     eax, [rdi+54h]
0x18003098c  jmp     short loc_180030968
0x18003098e  mov     r9b, bl; bool
0x180030991  lea     rdx, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180030998  mov     r8d, esi; int
0x18003099b  mov     rcx, r12; lpString1
0x18003099e  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x1800309a3  test    eax, eax
0x1800309a5  jnz     short loc_1800309AC
0x1800309a7  mov     eax, [rdi+50h]
0x1800309aa  jmp     short loc_180030968
0x1800309ac  mov     r9b, bl; bool
0x1800309af  mov     r8d, esi; int
0x1800309b2  mov     rdx, r12; unsigned __int16 *
0x1800309b5  mov     rcx, r12; lpString1
0x1800309b8  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x1800309bd  test    eax, eax
0x1800309bf  jnz     short loc_1800309C6
0x1800309c1  mov     eax, [rdi+58h]
0x1800309c4  jmp     short loc_180030968
0x1800309c6  mov     r9b, bl; bool
0x1800309c9  lea     rdx, aRevision_0; "revision"
0x1800309d0  mov     r8d, esi; int
0x1800309d3  mov     rcx, r12; lpString1
0x1800309d6  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x1800309db  test    eax, eax
0x1800309dd  jnz     short loc_1800309E7
0x1800309df  mov     eax, [rdi+90h]
0x1800309e5  jmp     short loc_180030968
0x1800309e7  lea     r8, [rbp+arg_0]; unsigned __int16 ***
0x1800309eb  mov     rdx, r12; unsigned __int16 *
0x1800309ee  mov     rcx, rdi; this
0x1800309f1  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x1800309f6  test    eax, eax
0x1800309f8  jnz     loc_180030B29
0x1800309fe  cmp     dword ptr [rdi+58h], 0
0x180030a02  jnz     short loc_180030A39
0x180030a04  lea     rcx, aRevision_0; "revision"
0x180030a0b  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x180030a10  test    eax, eax
0x180030a12  jz      short loc_180030A39
0x180030a14  mov     r9b, bl; bool
0x180030a17  lea     rcx, aRevision_0; "revision"
0x180030a1e  mov     r8d, esi; int
0x180030a21  mov     rdx, r12; unsigned __int16 *
0x180030a24  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030a29  test    eax, eax
0x180030a2b  jnz     loc_180030B29
0x180030a31  mov     dword ptr [rbp+arg_10], ebx
0x180030a34  jmp     loc_180030AFE
0x180030a39  mov     r9b, bl; bool
0x180030a3c  lea     rcx, aRevision_0; "revision"
0x180030a43  mov     r8d, esi; int
0x180030a46  mov     rdx, r13; unsigned __int16 *
0x180030a49  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030a4e  test    eax, eax
0x180030a50  jnz     short loc_180030A5D
0x180030a52  mov     eax, [rdi+40h]
0x180030a55  mov     dword ptr [rbp+arg_10], eax
0x180030a58  jmp     loc_180030AFE
0x180030a5d  mov     r9b, bl; bool
0x180030a60  lea     rdx, aMspkiRaSignatu; "msPKI-RA-Signature"
0x180030a67  mov     r8d, esi; int
0x180030a6a  lea     rcx, aRevision_0; "revision"
0x180030a71  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030a76  test    eax, eax
0x180030a78  jnz     short loc_180030A7F
0x180030a7a  mov     eax, [rdi+54h]
0x180030a7d  jmp     short loc_180030A55
0x180030a7f  mov     r9b, bl; bool
0x180030a82  lea     rdx, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180030a89  mov     r8d, esi; int
0x180030a8c  lea     rcx, aRevision_0; "revision"
0x180030a93  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030a98  test    eax, eax
0x180030a9a  jnz     short loc_180030AA1
0x180030a9c  mov     eax, [rdi+50h]
0x180030a9f  jmp     short loc_180030A55
0x180030aa1  mov     r9b, bl; bool
0x180030aa4  lea     rcx, aRevision_0; "revision"
0x180030aab  mov     r8d, esi; int
0x180030aae  mov     rdx, r12; unsigned __int16 *
0x180030ab1  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030ab6  test    eax, eax
0x180030ab8  jnz     short loc_180030ABF
0x180030aba  mov     eax, [rdi+58h]
0x180030abd  jmp     short loc_180030A55
0x180030abf  mov     r9b, bl; bool
0x180030ac2  lea     rdx, aRevision_0; "revision"
0x180030ac9  mov     r8d, esi; int
0x180030acc  lea     rcx, aRevision_0; "revision"
0x180030ad3  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030ad8  test    eax, eax
0x180030ada  jnz     short loc_180030AE7
0x180030adc  mov     eax, [rdi+90h]
0x180030ae2  jmp     loc_180030A55
0x180030ae7  lea     r8, [rbp+arg_10]; unsigned __int16 ***
0x180030aeb  mov     rcx, rdi; this
0x180030aee  lea     rdx, aRevision_0; "revision"
0x180030af5  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x180030afa  test    eax, eax
0x180030afc  jnz     short loc_180030B29
0x180030afe  cmp     dword ptr [rdi+58h], 0
0x180030b02  jnz     short loc_180030B30
0x180030b04  mov     rcx, r13; lpString1
0x180030b07  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x180030b0c  test    eax, eax
0x180030b0e  jz      short loc_180030B30
0x180030b10  mov     r9b, bl; bool
0x180030b13  mov     r8d, esi; int
0x180030b16  mov     rdx, r12; unsigned __int16 *
0x180030b19  mov     rcx, r13; lpString1
0x180030b1c  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030b21  test    eax, eax
0x180030b23  jz      loc_180030BDE
0x180030b29  xor     eax, eax
0x180030b2b  jmp     loc_180030C00
0x180030b30  mov     r9b, bl; bool
0x180030b33  mov     r8d, esi; int
0x180030b36  mov     rdx, r13; unsigned __int16 *
0x180030b39  mov     rcx, r13; lpString1
0x180030b3c  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030b41  test    eax, eax
0x180030b43  jnz     short loc_180030B4D
0x180030b45  mov     ebx, [rdi+40h]
0x180030b48  jmp     loc_180030BDE
0x180030b4d  mov     r9b, bl; bool
0x180030b50  lea     rdx, aMspkiRaSignatu; "msPKI-RA-Signature"
0x180030b57  mov     r8d, esi; int
0x180030b5a  mov     rcx, r13; lpString1
0x180030b5d  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030b62  test    eax, eax
0x180030b64  jnz     short loc_180030B6B
0x180030b66  mov     ebx, [rdi+54h]
0x180030b69  jmp     short loc_180030BDE
0x180030b6b  mov     r9b, bl; bool
0x180030b6e  lea     rdx, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180030b75  mov     r8d, esi; int
0x180030b78  mov     rcx, r13; lpString1
0x180030b7b  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030b80  test    eax, eax
0x180030b82  jnz     short loc_180030B89
0x180030b84  mov     ebx, [rdi+50h]
0x180030b87  jmp     short loc_180030BDE
0x180030b89  mov     r9b, bl; bool
0x180030b8c  mov     r8d, esi; int
0x180030b8f  mov     rdx, r12; unsigned __int16 *
0x180030b92  mov     rcx, r13; lpString1
0x180030b95  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030b9a  test    eax, eax
0x180030b9c  jnz     short loc_180030BA3
0x180030b9e  mov     ebx, [rdi+58h]
0x180030ba1  jmp     short loc_180030BDE
0x180030ba3  mov     r9b, bl; bool
0x180030ba6  lea     rdx, aRevision_0; "revision"
0x180030bad  mov     r8d, esi; int
0x180030bb0  mov     rcx, r13; lpString1
0x180030bb3  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180030bb8  test    eax, eax
0x180030bba  jnz     short loc_180030BC4
0x180030bbc  mov     ebx, [rdi+90h]
0x180030bc2  jmp     short loc_180030BDE
0x180030bc4  lea     r8, [rbp+arg_18]; unsigned __int16 ***
0x180030bc8  mov     rdx, r13; unsigned __int16 *
0x180030bcb  mov     rcx, rdi; this
0x180030bce  call    ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x180030bd3  test    eax, eax
0x180030bd5  jnz     loc_180030B29
0x180030bdb  mov     ebx, dword ptr [rbp+arg_18]
0x180030bde  mov     ecx, dword ptr [rbp+arg_0]
0x180030be1  xor     eax, eax
0x180030be3  cmp     ecx, [r14+64h]
0x180030be7  jnz     short loc_180030BF6
0x180030be9  mov     ecx, dword ptr [rbp+arg_10]
0x180030bec  cmp     ecx, [r14+48h]
0x180030bf0  jnz     short loc_180030BF6
0x180030bf2  cmp     ebx, [r14+4Ch]
0x180030bf6  setnb   al
0x180030bf9  jmp     short loc_180030C00
0x180030bfb  mov     eax, 1
0x180030c00  add     rsp, 20h
0x180030c04  pop     r14
0x180030c06  pop     r13
0x180030c08  pop     r12
0x180030c0a  pop     rdi
0x180030c0b  pop     rsi
0x180030c0c  pop     rbx
0x180030c0d  pop     rbp
0x180030c0e  retn
```
