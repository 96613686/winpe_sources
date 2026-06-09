# CIssuanceLicense::GetIssuanceLicenseTemplate(uint,ushort *,uint,ushort *,uint,uint *,ushort *)

- ea: `0x18000eb04`
- end: `0x18000eee7`
- name: `?GetIssuanceLicenseTemplate@CIssuanceLicense@@QEAAJIPEAGI0IPEAI0@Z`
- size: `995`
- prototype: `__int64 __usercall@<rax>(CIssuanceLicense *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned __int16 *, unsigned int, unsigned int *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180005730`
- `0x18000dd1c`

## callees

- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x18000af3c`
- `0x18000eb04`
- `0x180017358`
- `0x18005bd72`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eec4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eec4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000eb3f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000eb3f`

## string_xrefs

- `0x18000eb52`: `<XrML version="1.2" xmlns=""><BODY type="Microsoft Rights Template" version="3.0">%s%s%s%s%s<WORK>%s%s%s</WORK>%s%s%s</BODY></XrML>`
- `0x18000eb69`: `<?xml version="1.0"?><XrML version="1.2" xmlns=""><BODY type="Microsoft Rights Label" version="3.0">%s%s%s%s%s<WORK>%s%s%s</WORK>%s%s%s</BODY></XrML>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CIssuanceLicense::GetIssuanceLicenseTemplate(
        CIssuanceLicense *this,
        int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int *a7,
        unsigned __int16 *a8)
{
  int v12; // ecx
  unsigned __int16 *v13; // r12
  unsigned __int16 *v14; // rbp
  unsigned int *v15; // r15
  int v16; // ebx
  int v17; // eax
  unsigned int v18; // r11d
  int v19; // edx
  __int64 v20; // r14
  unsigned __int16 *v21; // rax
  const unsigned __int16 *v22; // r9
  const unsigned __int16 *v23; // r8
  const unsigned __int16 *v24; // r13
  unsigned int *v25; // rax
  const unsigned __int16 *v26; // rdx
  const unsigned __int16 *v27; // rdi
  const unsigned __int16 *v28; // rbx
  const unsigned __int16 *v29; // rcx
  const unsigned __int16 *v30; // rax
  const unsigned __int16 *v31; // r11
  const unsigned __int16 *v32; // r10
  unsigned __int16 *v34; // [rsp+70h] [rbp-58h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+78h] [rbp-50h]
  unsigned __int16 *v36; // [rsp+D0h] [rbp+8h] BYREF
  unsigned int v37; // [rsp+D8h] [rbp+10h] BYREF
  unsigned __int16 *v38; // [rsp+E0h] [rbp+18h]

  v38 = a3;
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( a2 == 1 )
  {
    v34 = L"<XrML version=\"1.2\" xmlns=\"\"><BODY type=\"Microsoft Rights Template\" version=\"3.0\">%s%s%s%s%s<WORK>%s%s"
           "%s</WORK>%s%s%s</BODY></XrML>";
    v12 = 128;
  }
  else if ( a2 == 2 )
  {
    v34 = L"<?xml version=\"1.0\"?><XrML version=\"1.2\" xmlns=\"\"><BODY type=\"Microsoft Rights Label\" version=\"3.0\">"
           "%s%s%s%s%s<WORK>%s%s%s</WORK>%s%s%s</BODY></XrML>";
    v12 = 146;
  }
  else
  {
    v34 = 0;
    v12 = 0;
  }
  v13 = 0;
  v14 = 0;
  v36 = 0;
  v37 = 0;
  v15 = a7;
  if ( !a7 )
    goto LABEL_7;
  if ( a2 == 1 )
  {
    if ( !*((_DWORD *)this + 189) || (v17 = 1, *((_DWORD *)this + 184)) )
      v17 = 0;
    if ( *((_DWORD *)this + 183) && v17 )
    {
      v16 = 0;
      v18 = *((_DWORD *)this + 188) + 1;
      if ( a8 )
      {
        if ( *a7 >= v18 )
        {
          v16 = StringCchCopyW(a8, *a7, *((const unsigned __int16 **)this + 93));
          if ( v16 < 0 )
            goto LABEL_62;
        }
        else
        {
          v16 = -2147024774;
        }
      }
      *v15 = v18;
      goto LABEL_62;
    }
  }
  v19 = *((_DWORD *)this + 210);
  if ( !v19 )
  {
    v16 = -2147168433;
    goto LABEL_62;
  }
  v20 = (unsigned int)(v12
                     + v19
                     + *((_DWORD *)this + 198)
                     + *((_DWORD *)this + 202)
                     + *((_DWORD *)this + 206)
                     + *((_DWORD *)this + 222)
                     + *((_DWORD *)this + 226)
                     + *((_DWORD *)this + 230));
  if ( a3 && (v20 = a4 + (unsigned int)v20, (unsigned int)v20 < a4) )
  {
LABEL_7:
    v16 = -2147024809;
  }
  else
  {
    v16 = 0;
    if ( a2 == 1 )
    {
      v20 = (unsigned int)(*((_DWORD *)this + 214) + *((_DWORD *)this + 218) + v20);
    }
    else if ( a2 == 2 )
    {
      v16 = CIssuanceLicense::GenerateEncryptedRightsXML(this, a5, a6, &v37, 0);
      if ( v16 < 0 )
        goto LABEL_62;
      v20 = v37 + (unsigned int)v20;
    }
    if ( !a8 )
      goto LABEL_61;
    if ( *v15 < (unsigned int)v20 )
    {
      v16 = -2147024774;
      goto LABEL_61;
    }
    if ( a2 != 2 || (v16 = CIssuanceLicense::GenerateEncryptedRightsXML(this, a5, a6, &v37, &v36), v14 = v36, v16 >= 0) )
    {
      v21 = (unsigned __int16 *)operator new[](saturated_mul((unsigned int)v20, 2u));
      v13 = v21;
      if ( !v21 )
      {
        v16 = -2147024882;
        goto LABEL_62;
      }
      memset_0(v21, 0, 2 * v20);
      v22 = &Src;
      if ( a2 != 1 || (v23 = (const unsigned __int16 *)*((_QWORD *)this + 108)) == 0 )
        v23 = &Src;
      v24 = &Src;
      if ( *((_QWORD *)this + 110) )
        v24 = (const unsigned __int16 *)*((_QWORD *)this + 110);
      v25 = (unsigned int *)&Src;
      if ( v14 )
        v25 = (unsigned int *)v14;
      a7 = v25;
      if ( a2 != 1 || (v26 = (const unsigned __int16 *)*((_QWORD *)this + 106)) == 0 )
        v26 = &Src;
      v27 = &Src;
      if ( *((_QWORD *)this + 112) )
        v27 = (const unsigned __int16 *)*((_QWORD *)this + 112);
      v28 = &Src;
      if ( *((_QWORD *)this + 104) )
        v28 = (const unsigned __int16 *)*((_QWORD *)this + 104);
      v29 = &Src;
      if ( *((_QWORD *)this + 102) )
        v29 = (const unsigned __int16 *)*((_QWORD *)this + 102);
      v30 = v38;
      if ( !v38 )
        v30 = &Src;
      v38 = (unsigned __int16 *)v30;
      v31 = &Src;
      if ( *((_QWORD *)this + 114) )
        v31 = (const unsigned __int16 *)*((_QWORD *)this + 114);
      v32 = &Src;
      if ( *((_QWORD *)this + 100) )
        v32 = (const unsigned __int16 *)*((_QWORD *)this + 100);
      if ( *((_QWORD *)this + 98) )
        v22 = (const unsigned __int16 *)*((_QWORD *)this + 98);
      v16 = StringCchPrintfW(v13, (unsigned int)v20, v34, v22, v32, v31, v38, v29, v28, v27, v26, a7, v24, v23);
      if ( v16 >= 0 )
      {
        v16 = StringCchCopyW(a8, *v15, v13);
        if ( v16 >= 0 )
LABEL_61:
          *v15 = v20;
      }
    }
  }
LABEL_62:
  operator delete(v13);
  operator delete(v14);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18000eb04  mov     r11, rsp
0x18000eb07  mov     [r11+18h], r8
0x18000eb0b  push    rbp
0x18000eb0c  push    rsi
0x18000eb0d  push    rdi
0x18000eb0e  push    r12
0x18000eb10  push    r13
0x18000eb12  push    r14
0x18000eb14  push    r15
0x18000eb16  sub     rsp, 90h
0x18000eb1d  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x18000eb25  mov     [r11+20h], rbx
0x18000eb29  mov     ebx, r9d
0x18000eb2c  mov     r13, r8
0x18000eb2f  mov     edi, edx
0x18000eb31  mov     rsi, rcx
0x18000eb34  lea     rax, [rcx+58h]
0x18000eb38  mov     [r11-50h], rax
0x18000eb3c  mov     rcx, rax; lpCriticalSection
0x18000eb3f  call    cs:__imp_EnterCriticalSection
0x18000eb45  nop
0x18000eb46  xor     r8d, r8d
0x18000eb49  lea     r9d, [r8+1]
0x18000eb4d  cmp     edi, r9d
0x18000eb50  jnz     short loc_18000EB64
0x18000eb52  lea     rax, aXrmlVersion12X_0; "<XrML version=\"1.2\" xmlns=\"\"><BODY "...
0x18000eb59  mov     [rsp+0C8h+var_58], rax
0x18000eb5e  lea     ecx, [r9+7Fh]
0x18000eb62  jmp     short loc_18000EB84
0x18000eb64  cmp     edi, 2
0x18000eb67  jnz     short loc_18000EB7C
0x18000eb69  lea     rax, aXmlVersion10Xr; "<?xml version=\"1.0\"?><XrML version=\""...
0x18000eb70  mov     [rsp+0C8h+var_58], rax
0x18000eb75  mov     ecx, 92h
0x18000eb7a  jmp     short loc_18000EB84
0x18000eb7c  mov     [rsp+0C8h+var_58], r8
0x18000eb81  mov     ecx, r8d
0x18000eb84  mov     r12, r8
0x18000eb87  mov     rbp, r8
0x18000eb8a  mov     [rsp+0C8h+arg_0], r8
0x18000eb92  mov     [rsp+0C8h+arg_8], r8d
0x18000eb9a  mov     r15, [rsp+0C8h+arg_30]
0x18000eba2  test    r15, r15
0x18000eba5  jnz     short loc_18000EBB1
0x18000eba7  mov     ebx, 80070057h
0x18000ebac  jmp     loc_18000EEAE
0x18000ebb1  cmp     edi, r9d
0x18000ebb4  jnz     short loc_18000EC22
0x18000ebb6  cmp     [rsi+2F4h], r8d
0x18000ebbd  jz      short loc_18000EBCB
0x18000ebbf  cmp     [rsi+2E0h], r8d
0x18000ebc6  mov     eax, r9d
0x18000ebc9  jz      short loc_18000EBCE
0x18000ebcb  mov     eax, r8d
0x18000ebce  cmp     [rsi+2DCh], r8d
0x18000ebd5  jz      short loc_18000EC22
0x18000ebd7  test    eax, eax
0x18000ebd9  jz      short loc_18000EC22
0x18000ebdb  mov     ebx, r8d
0x18000ebde  mov     r11d, [rsi+2F0h]
0x18000ebe5  inc     r11d
0x18000ebe8  mov     rcx, [rsp+0C8h+arg_38]; unsigned __int16 *
0x18000ebf0  test    rcx, rcx
0x18000ebf3  jz      short loc_18000EC1A
0x18000ebf5  cmp     [r15], r11d
0x18000ebf8  jnb     short loc_18000EC01
0x18000ebfa  mov     ebx, 8007007Ah
0x18000ebff  jmp     short loc_18000EC1A
0x18000ec01  mov     edx, [r15]; unsigned __int64
0x18000ec04  mov     r8, [rsi+2E8h]; unsigned __int16 *
0x18000ec0b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ec10  mov     ebx, eax
0x18000ec12  test    eax, eax
0x18000ec14  js      loc_18000EEAE
0x18000ec1a  mov     [r15], r11d
0x18000ec1d  jmp     loc_18000EEAE
0x18000ec22  mov     edx, [rsi+348h]
0x18000ec28  test    edx, edx
0x18000ec2a  jnz     short loc_18000EC36
0x18000ec2c  mov     ebx, 8004CF4Fh
0x18000ec31  jmp     loc_18000EEAE
0x18000ec36  mov     r14d, [rsi+398h]
0x18000ec3d  add     r14d, [rsi+388h]
0x18000ec44  add     r14d, [rsi+378h]
0x18000ec4b  add     r14d, [rsi+338h]
0x18000ec52  add     r14d, [rsi+328h]
0x18000ec59  add     r14d, [rsi+318h]
0x18000ec60  add     r14d, edx
0x18000ec63  add     r14d, ecx
0x18000ec66  test    r13, r13
0x18000ec69  jz      short loc_18000EC77
0x18000ec6b  add     r14d, ebx
0x18000ec6e  cmp     r14d, ebx
0x18000ec71  jb      loc_18000EBA7
0x18000ec77  mov     ebx, r8d
0x18000ec7a  cmp     edi, r9d
0x18000ec7d  jnz     short loc_18000EC90
0x18000ec7f  mov     eax, [rsi+368h]
0x18000ec85  add     eax, [rsi+358h]
0x18000ec8b  add     r14d, eax
0x18000ec8e  jmp     short loc_18000ECCF
0x18000ec90  cmp     edi, 2
0x18000ec93  jnz     short loc_18000ECCF
0x18000ec95  mov     [rsp+0C8h+var_A8], r8; unsigned __int16 **
0x18000ec9a  lea     r9, [rsp+0C8h+arg_8]; unsigned int *
0x18000eca2  mov     r8d, [rsp+0C8h+arg_28]; unsigned int
0x18000ecaa  mov     rdx, [rsp+0C8h+arg_20]; unsigned __int16 *
0x18000ecb2  mov     rcx, rsi; this
0x18000ecb5  call    ?GenerateEncryptedRightsXML@CIssuanceLicense@@AEAAJPEAGIPEAIPEAPEAG@Z; CIssuanceLicense::GenerateEncryptedRightsXML(ushort *,uint,uint *,ushort * *)
0x18000ecba  mov     ebx, eax
0x18000ecbc  xor     r8d, r8d
0x18000ecbf  test    eax, eax
0x18000ecc1  js      loc_18000EEAE
0x18000ecc7  add     r14d, [rsp+0C8h+arg_8]
0x18000eccf  cmp     [rsp+0C8h+arg_38], r8
0x18000ecd7  jz      loc_18000EEAB
0x18000ecdd  cmp     [r15], r14d
0x18000ece0  jnb     short loc_18000ECEC
0x18000ece2  mov     ebx, 8007007Ah
0x18000ece7  jmp     loc_18000EEAB
0x18000ecec  cmp     edi, 2
0x18000ecef  jnz     short loc_18000ED30
0x18000ecf1  lea     rax, [rsp+0C8h+arg_0]
0x18000ecf9  mov     [rsp+0C8h+var_A8], rax; unsigned __int16 **
0x18000ecfe  lea     r9, [rsp+0C8h+arg_8]; unsigned int *
0x18000ed06  mov     r8d, [rsp+0C8h+arg_28]; unsigned int
0x18000ed0e  mov     rdx, [rsp+0C8h+arg_20]; unsigned __int16 *
0x18000ed16  mov     rcx, rsi; this
0x18000ed19  call    ?GenerateEncryptedRightsXML@CIssuanceLicense@@AEAAJPEAGIPEAIPEAPEAG@Z; CIssuanceLicense::GenerateEncryptedRightsXML(ushort *,uint,uint *,ushort * *)
0x18000ed1e  mov     ebx, eax
0x18000ed20  mov     rbp, [rsp+0C8h+arg_0]
0x18000ed28  test    eax, eax
0x18000ed2a  js      loc_18000EEAE
0x18000ed30  mov     ebx, r14d
0x18000ed33  mov     eax, 2
0x18000ed38  mul     rbx
0x18000ed3b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ed42  cmovb   rax, rcx
0x18000ed46  mov     rcx, rax; unsigned __int64
0x18000ed49  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ed4e  mov     r12, rax
0x18000ed51  test    rax, rax
0x18000ed54  jnz     short loc_18000ED60
0x18000ed56  mov     ebx, 8007000Eh
0x18000ed5b  jmp     loc_18000EEAE
0x18000ed60  lea     r8, [r14+r14]; Size
0x18000ed64  xor     edx, edx; Val
0x18000ed66  mov     rcx, r12; void *
0x18000ed69  call    memset_0
0x18000ed6e  lea     r9, Src
0x18000ed75  cmp     edi, 1
0x18000ed78  jnz     short loc_18000ED86
0x18000ed7a  mov     r8, [rsi+360h]
0x18000ed81  test    r8, r8
0x18000ed84  jnz     short loc_18000ED89
0x18000ed86  mov     r8, r9
0x18000ed89  mov     rax, [rsi+370h]
0x18000ed90  mov     r13, r9
0x18000ed93  test    rax, rax
0x18000ed96  cmovnz  r13, rax
0x18000ed9a  mov     rax, r9
0x18000ed9d  test    rbp, rbp
0x18000eda0  cmovnz  rax, rbp
0x18000eda4  mov     [rsp+0C8h+arg_30], rax
0x18000edac  cmp     edi, 1
0x18000edaf  jnz     short loc_18000EDBD
0x18000edb1  mov     rdx, [rsi+350h]
0x18000edb8  test    rdx, rdx
0x18000edbb  jnz     short loc_18000EDC0
0x18000edbd  mov     rdx, r9
0x18000edc0  mov     rax, [rsi+380h]
0x18000edc7  mov     rdi, r9
0x18000edca  test    rax, rax
0x18000edcd  cmovnz  rdi, rax
0x18000edd1  mov     rax, [rsi+340h]
0x18000edd8  mov     rbx, r9
0x18000eddb  test    rax, rax
0x18000edde  cmovnz  rbx, rax
0x18000ede2  mov     rax, [rsi+330h]
0x18000ede9  mov     rcx, r9
0x18000edec  test    rax, rax
0x18000edef  cmovnz  rcx, rax
0x18000edf3  mov     rax, [rsp+0C8h+arg_10]
0x18000edfb  test    rax, rax
0x18000edfe  cmovz   rax, r9
0x18000ee02  mov     [rsp+0C8h+arg_10], rax
0x18000ee0a  mov     rax, [rsi+390h]
0x18000ee11  mov     r11, r9
0x18000ee14  test    rax, rax
0x18000ee17  cmovnz  r11, rax
0x18000ee1b  mov     rax, [rsi+320h]
0x18000ee22  mov     r10, r9
0x18000ee25  test    rax, rax
0x18000ee28  cmovnz  r10, rax
0x18000ee2c  mov     rax, [rsi+310h]
0x18000ee33  test    rax, rax
0x18000ee36  cmovnz  r9, rax
0x18000ee3a  mov     [rsp+0C8h+var_60], r8
0x18000ee3f  mov     [rsp+0C8h+var_68], r13
0x18000ee44  mov     rax, [rsp+0C8h+arg_30]
0x18000ee4c  mov     [rsp+0C8h+var_70], rax
0x18000ee51  mov     [rsp+0C8h+var_78], rdx
0x18000ee56  mov     [rsp+0C8h+var_80], rdi
0x18000ee5b  mov     [rsp+0C8h+var_88], rbx
0x18000ee60  mov     [rsp+0C8h+var_90], rcx
0x18000ee65  mov     r13, [rsp+0C8h+arg_10]
0x18000ee6d  mov     [rsp+0C8h+var_98], r13
0x18000ee72  mov     [rsp+0C8h+var_A0], r11
0x18000ee77  mov     [rsp+0C8h+var_A8], r10
0x18000ee7c  mov     r8, [rsp+0C8h+var_58]; unsigned __int16 *
0x18000ee81  mov     edx, r14d; unsigned __int64
0x18000ee84  mov     rcx, r12; unsigned __int16 *
0x18000ee87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ee8c  mov     ebx, eax
0x18000ee8e  test    eax, eax
0x18000ee90  js      short loc_18000EEAE
0x18000ee92  mov     edx, [r15]; unsigned __int64
0x18000ee95  mov     r8, r12; unsigned __int16 *
0x18000ee98  mov     rcx, [rsp+0C8h+arg_38]; unsigned __int16 *
0x18000eea0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000eea5  mov     ebx, eax
0x18000eea7  test    eax, eax
0x18000eea9  js      short loc_18000EEAE
0x18000eeab  mov     [r15], r14d
0x18000eeae  mov     rcx, r12; Block
0x18000eeb1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000eeb6  mov     rcx, rbp; Block
0x18000eeb9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000eebe  nop
0x18000eebf  mov     rcx, [rsp+0C8h+lpCriticalSection]; lpCriticalSection
0x18000eec4  call    cs:__imp_LeaveCriticalSection
0x18000eeca  mov     eax, ebx
0x18000eecc  mov     rbx, [rsp+0C8h+arg_18]
0x18000eed4  add     rsp, 90h
0x18000eedb  pop     r15
0x18000eedd  pop     r14
0x18000eedf  pop     r13
0x18000eee1  pop     r12
0x18000eee3  pop     rdi
0x18000eee4  pop     rsi
0x18000eee5  pop     rbp
0x18000eee6  retn
```
