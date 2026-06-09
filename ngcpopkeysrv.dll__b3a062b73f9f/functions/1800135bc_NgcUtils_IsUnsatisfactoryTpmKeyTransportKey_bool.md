# NgcUtils::IsUnsatisfactoryTpmKeyTransportKey(bool *)

- ea: `0x1800135bc`
- end: `0x180013684`
- name: `?IsUnsatisfactoryTpmKeyTransportKey@NgcUtils@@YAJPEA_N@Z`
- size: `200`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011f94`

## callees

- `0x18001069c`
- `0x1800133cc`
- `0x1800134f8`
- `0x1800135bc`
- `0x180023d74`

## string_xrefs

- `0x1800135e0`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`
- `0x180013624`: `onecore\ds\security\ngc\utils\common\lib\tpmutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::IsUnsatisfactoryTpmKeyTransportKey(NgcUtils *this, bool *a2)
{
  int IsInsecureTpm; // eax
  struct __NCRYPT_PCP_TPM_FW_VERSION_INFO *v4; // r8
  int Tpm20FirmwareInformation; // eax
  __int64 i; // rcx
  wchar_t String1[4]; // [rsp+20h] [rbp-18h] BYREF
  __int16 v9; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF

  *(_BYTE *)this = 0;
  LOBYTE(v11) = 0;
  IsInsecureTpm = NgcUtils::IsInsecureTpm((NgcUtils *)&v11, a2);
  if ( IsInsecureTpm < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
      (const char *)(unsigned int)IsInsecureTpm,
      *(int *)String1);
  if ( (_BYTE)v11 )
  {
LABEL_12:
    *(_BYTE *)this = 1;
  }
  else
  {
    *(_QWORD *)String1 = 0;
    v9 = 0;
    v11 = 0;
    Tpm20FirmwareInformation = NgcUtils::GetTpm20FirmwareInformation(
                                 (NgcUtils *)String1,
                                 (unsigned __int16 *const)&v11,
                                 v4);
    if ( Tpm20FirmwareInformation < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tpmutils.cpp",
        (const char *)(unsigned int)Tpm20FirmwareInformation,
        *(int *)String1);
    if ( !wcscmp_0(String1, L"NTZ") )
    {
      for ( i = 0; (unsigned int)i < 5; i = (unsigned int)(i + 1) )
      {
        if ( (_WORD)v11 == LOWORD(qword_18002AAB0[i]) && WORD1(v11) == WORD1(qword_18002AAB0[i]) )
          goto LABEL_12;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800135bc  push    rbx
0x1800135be  sub     rsp, 30h
0x1800135c2  mov     rbx, rcx
0x1800135c5  mov     byte ptr [rcx], 0
0x1800135c8  lea     rcx, [rsp+38h+arg_0]; this
0x1800135cd  mov     byte ptr [rsp+38h+arg_0], 0
0x1800135d2  call    ?IsInsecureTpm@NgcUtils@@YAJPEA_N@Z; NgcUtils::IsInsecureTpm(bool *)
0x1800135d7  test    eax, eax
0x1800135d9  jns     short loc_1800135F4
0x1800135db  mov     rcx, [rsp+38h]; this
0x1800135e0  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800135e7  mov     r9d, eax; char *
0x1800135ea  mov     edx, 6Fh ; 'o'; void *
0x1800135ef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800135f4  cmp     byte ptr [rsp+38h+arg_0], 0
0x1800135f9  jnz     short loc_180013679
0x1800135fb  xor     eax, eax
0x1800135fd  lea     rdx, [rsp+38h+arg_0]; unsigned __int16 *
0x180013602  lea     rcx, [rsp+38h+String1]; this
0x180013607  mov     qword ptr [rsp+38h+String1], rax; int
0x18001360c  mov     [rsp+38h+var_10], ax
0x180013611  mov     [rsp+38h+arg_0], rax
0x180013616  call    ?GetTpm20FirmwareInformation@NgcUtils@@YAJQEAGPEAU__NCRYPT_PCP_TPM_FW_VERSION_INFO@@@Z; NgcUtils::GetTpm20FirmwareInformation(ushort * const,__NCRYPT_PCP_TPM_FW_VERSION_INFO *)
0x18001361b  test    eax, eax
0x18001361d  jns     short loc_180013638
0x18001361f  mov     rcx, [rsp+38h]; this
0x180013624  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001362b  mov     r9d, eax; char *
0x18001362e  mov     edx, 7Bh ; '{'; void *
0x180013633  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180013638  lea     rdx, aNtz; "NTZ"
0x18001363f  lea     rcx, [rsp+38h+String1]; String1
0x180013644  call    wcscmp_0
0x180013649  test    eax, eax
0x18001364b  jnz     short loc_18001367C
0x18001364d  mov     rax, [rsp+38h+arg_0]
0x180013652  lea     r9, qword_18002AAB0
0x180013659  movzx   r8d, word ptr [rsp+38h+arg_0+2]
0x18001365f  xor     ecx, ecx
0x180013661  cmp     ecx, 5
0x180013664  jnb     short loc_18001367C
0x180013666  cmp     ax, [r9+rcx*8]
0x18001366b  jnz     short loc_180013675
0x18001366d  cmp     r8w, [r9+rcx*8+2]
0x180013673  jz      short loc_180013679
0x180013675  inc     ecx
0x180013677  jmp     short loc_180013661
0x180013679  mov     byte ptr [rbx], 1
0x18001367c  xor     eax, eax
0x18001367e  add     rsp, 30h
0x180013682  pop     rbx
0x180013683  retn
```
