# CIssuanceLicense::GenerateXMLData(void)

- ea: `0x18000cd4c`
- end: `0x18000cf28`
- name: `?GenerateXMLData@CIssuanceLicense@@QEAAJXZ`
- size: `476`
- prototype: `__int64 __fastcall(CIssuanceLicense *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180005730`
- `0x1800095a0`

## callees

- `0x18000ac5c`
- `0x18000b44c`
- `0x18000b5b4`
- `0x18000ba1c`
- `0x18000bc94`
- `0x18000c088`
- `0x18000c414`
- `0x18000c988`
- `0x18000cd4c`
- `0x180010990`
- `0x18001ef30`
- `0x18001ffd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cdd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cf13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cd71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cdc8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cd71`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000cdc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIssuanceLicense::GenerateXMLData(CIssuanceLicense *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 i; // r15
  CDRMCBase *v4; // rcx
  __int64 v5; // r14
  int v6; // edi
  int ValidityTimeXML; // edi

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( *((_DWORD *)this + 234) )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 34); i = (unsigned int)(i + 1) )
    {
      v4 = *(CDRMCBase **)(*((_QWORD *)this + 16) + 8 * i);
      if ( v4 )
      {
        CDRMCBase::AddRef(v4);
        v5 = *(_QWORD *)(*((_QWORD *)this + 16) + 8 * i);
        if ( v5 )
        {
          v6 = *((_DWORD *)this + 234);
          EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 88));
          *(_DWORD *)(v5 + 128) = v6;
          LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 88));
          CDRMCBase::Release((CDRMCBase *)v5);
        }
      }
    }
  }
  ValidityTimeXML = CIssuanceLicense::GenerateValidityTimeXML(
                      this,
                      (unsigned int *)this + 202,
                      (unsigned __int16 **)this + 100);
  if ( ValidityTimeXML >= 0 )
  {
    ValidityTimeXML = CIssuanceLicense::GenerateReferralInfoXML(
                        this,
                        (unsigned int *)this + 206,
                        (unsigned __int16 **)this + 102);
    if ( ValidityTimeXML >= 0 )
    {
      ValidityTimeXML = CMetaData::GetXML(
                          (CIssuanceLicense *)((char *)this + 208),
                          (unsigned int *)this + 210,
                          (unsigned __int16 **)this + 104);
      if ( ValidityTimeXML >= 0 )
      {
        ValidityTimeXML = CIssuanceLicense::GenerateRightsDataXML(
                            this,
                            (unsigned int *)this + 214,
                            (unsigned __int16 **)this + 106);
        if ( ValidityTimeXML >= 0 )
        {
          ValidityTimeXML = CIssuanceLicense::GenerateApplicationSpecificDataXML(
                              this,
                              (unsigned int *)this + 218,
                              (unsigned __int16 **)this + 108);
          if ( ValidityTimeXML >= 0 )
          {
            ValidityTimeXML = CIssuanceLicense::GenerateUsagePolicyXML(
                                this,
                                (unsigned int *)this + 222,
                                (unsigned __int16 **)this + 110);
            if ( ValidityTimeXML >= 0 )
            {
              ValidityTimeXML = CIssuanceLicense::GenerateRefreshConditionXML(
                                  this,
                                  (unsigned int *)this + 226,
                                  (unsigned __int16 **)this + 112);
              if ( ValidityTimeXML >= 0 )
              {
                ValidityTimeXML = CIssuanceLicense::GenerateNameAndDescriptionXML(
                                    this,
                                    (unsigned int *)this + 230,
                                    (unsigned __int16 **)this + 114);
                if ( ValidityTimeXML >= 0 )
                  ValidityTimeXML = CIssuanceLicense::GenerateIssuedTimeXML(
                                      this,
                                      (unsigned int *)this + 198,
                                      (unsigned __int16 **)this + 98);
              }
            }
          }
        }
      }
    }
  }
  LeaveCriticalSection(v2);
  return (unsigned int)ValidityTimeXML;
}

```

## disassembly

```asm
0x18000cd4c  push    rbx
0x18000cd4e  push    rbp
0x18000cd4f  push    rsi
0x18000cd50  push    rdi
0x18000cd51  push    r14
0x18000cd53  push    r15
0x18000cd55  sub     rsp, 38h
0x18000cd59  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x18000cd62  mov     rbp, rcx
0x18000cd65  lea     rbx, [rcx+58h]
0x18000cd69  mov     [rsp+68h+arg_0], rbx
0x18000cd6e  mov     rcx, rbx; lpCriticalSection
0x18000cd71  call    cs:__imp_EnterCriticalSection
0x18000cd77  nop
0x18000cd78  xor     r14d, r14d
0x18000cd7b  cmp     [rbp+3A8h], r14d
0x18000cd82  jz      short loc_18000CDF6
0x18000cd84  xor     r15d, r15d
0x18000cd87  cmp     [rbp+88h], r14d
0x18000cd8e  jbe     short loc_18000CDF6
0x18000cd90  cmp     r15d, [rbp+88h]
0x18000cd97  jnb     short loc_18000CDE7
0x18000cd99  mov     rax, [rbp+80h]
0x18000cda0  mov     rcx, [rax+r15*8]; this
0x18000cda4  test    rcx, rcx
0x18000cda7  jz      short loc_18000CDE7
0x18000cda9  call    ?AddRef@CDRMCBase@@QEAAKXZ; CDRMCBase::AddRef(void)
0x18000cdae  mov     rax, [rbp+80h]
0x18000cdb5  mov     r14, [rax+r15*8]
0x18000cdb9  test    r14, r14
0x18000cdbc  jz      short loc_18000CDEA
0x18000cdbe  mov     edi, [rbp+3A8h]
0x18000cdc4  lea     rcx, [r14+58h]; lpCriticalSection
0x18000cdc8  call    cs:__imp_EnterCriticalSection
0x18000cdce  mov     [r14+80h], edi
0x18000cdd5  lea     rcx, [r14+58h]; lpCriticalSection
0x18000cdd9  call    cs:__imp_LeaveCriticalSection
0x18000cddf  mov     rcx, r14; this
0x18000cde2  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000cde7  xor     r14d, r14d
0x18000cdea  inc     r15d
0x18000cded  cmp     r15d, [rbp+88h]
0x18000cdf4  jb      short loc_18000CD99
0x18000cdf6  lea     r8, [rbp+320h]; unsigned __int16 **
0x18000cdfd  lea     rdx, [rbp+328h]; unsigned int *
0x18000ce04  mov     rcx, rbp; this
0x18000ce07  call    ?GenerateValidityTimeXML@CIssuanceLicense@@AEAAJPEAIPEAPEAG@Z; CIssuanceLicense::GenerateValidityTimeXML(uint *,ushort * *)
0x18000ce0c  mov     edi, eax
0x18000ce0e  test    eax, eax
0x18000ce10  js      loc_18000CF02
0x18000ce16  lea     r8, [rbp+330h]; unsigned __int16 **
0x18000ce1d  lea     rdx, [rbp+338h]; unsigned int *
0x18000ce24  mov     rcx, rbp; this
0x18000ce27  call    ?GenerateReferralInfoXML@CIssuanceLicense@@AEAAJPEAIPEAPEAG@Z; CIssuanceLicense::GenerateReferralInfoXML(uint *,ushort * *)
0x18000ce2c  mov     edi, eax
0x18000ce2e  test    eax, eax
0x18000ce30  js      loc_18000CF02
0x18000ce36  lea     r8, [rbp+340h]; unsigned __int16 **
0x18000ce3d  lea     rdx, [rbp+348h]; unsigned int *
0x18000ce44  lea     rcx, [rbp+0D0h]; this
0x18000ce4b  call    ?GetXML@CMetaData@@QEAAJPEAIPEAPEAG@Z; CMetaData::GetXML(uint *,ushort * *)
0x18000ce50  mov     edi, eax
0x18000ce52  test    eax, eax
0x18000ce54  js      loc_18000CF02
0x18000ce5a  lea     r8, [rbp+350h]; unsigned __int16 **
0x18000ce61  lea     rdx, [rbp+358h]; unsigned int *
0x18000ce68  mov     rcx, rbp; this
0x18000ce6b  call    ?GenerateRightsDataXML@CIssuanceLicense@@AEAAJPEAIPEAPEAG@Z; CIssuanceLicense::GenerateRightsDataXML(uint *,ushort * *)
0x18000ce70  mov     edi, eax
0x18000ce72  test    eax, eax
0x18000ce74  js      loc_18000CF02
0x18000ce7a  lea     r8, [rbp+360h]; unsigned __int16 **
0x18000ce81  lea     rdx, [rbp+368h]; unsigned int *
0x18000ce88  mov     rcx, rbp; this
0x18000ce8b  call    ?GenerateApplicationSpecificDataXML@CIssuanceLicense@@AEAAJPEAIPEAPEAG@Z; CIssuanceLicense::GenerateApplicationSpecificDataXML(uint *,ushort * *)
0x18000ce90  mov     edi, eax
0x18000ce92  test    eax, eax
0x18000ce94  js      short loc_18000CF02
0x18000ce96  lea     r8, [rbp+370h]; unsigned __int16 **
0x18000ce9d  lea     rdx, [rbp+378h]; unsigned int *
0x18000cea4  mov     rcx, rbp; this
0x18000cea7  call    ?GenerateUsagePolicyXML@CIssuanceLicense@@AEAAJPEAIPEAPEAG@Z; CIssuanceLicense::GenerateUsagePolicyXML(uint *,ushort * *)
0x18000ceac  mov     edi, eax
0x18000ceae  test    eax, eax
0x18000ceb0  js      short loc_18000CF02
0x18000ceb2  lea     r8, [rbp+380h]; unsigned __int16 **
0x18000ceb9  lea     rdx, [rbp+388h]; unsigned int *
0x18000cec0  mov     rcx, rbp; this
0x18000cec3  call    ?GenerateRefreshConditionXML@CIssuanceLicense@@AEAAJPEAIPEAPEAG@Z; CIssuanceLicense::GenerateRefreshConditionXML(uint *,ushort * *)
0x18000cec8  mov     edi, eax
0x18000ceca  test    eax, eax
0x18000cecc  js      short loc_18000CF02
0x18000cece  lea     r8, [rbp+390h]; unsigned __int16 **
0x18000ced5  lea     rdx, [rbp+398h]; unsigned int *
0x18000cedc  mov     rcx, rbp; this
0x18000cedf  call    ?GenerateNameAndDescriptionXML@CIssuanceLicense@@AEAAJPEAIPEAPEAG@Z; CIssuanceLicense::GenerateNameAndDescriptionXML(uint *,ushort * *)
0x18000cee4  mov     edi, eax
0x18000cee6  test    eax, eax
0x18000cee8  js      short loc_18000CF02
0x18000ceea  lea     r8, [rbp+310h]; unsigned __int16 **
0x18000cef1  lea     rdx, [rbp+318h]; unsigned int *
0x18000cef8  mov     rcx, rbp; this
0x18000cefb  call    ?GenerateIssuedTimeXML@CIssuanceLicense@@AEAAJPEAIPEAPEAG@Z; CIssuanceLicense::GenerateIssuedTimeXML(uint *,ushort * *)
0x18000cf00  mov     edi, eax
0x18000cf02  test    r14, r14
0x18000cf05  jz      short loc_18000CF10
0x18000cf07  mov     rcx, r14; this
0x18000cf0a  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x18000cf0f  nop
0x18000cf10  mov     rcx, rbx; lpCriticalSection
0x18000cf13  call    cs:__imp_LeaveCriticalSection
0x18000cf19  mov     eax, edi
0x18000cf1b  add     rsp, 38h
0x18000cf1f  pop     r15
0x18000cf21  pop     r14
0x18000cf23  pop     rdi
0x18000cf24  pop     rsi
0x18000cf25  pop     rbp
0x18000cf26  pop     rbx
0x18000cf27  retn
```
