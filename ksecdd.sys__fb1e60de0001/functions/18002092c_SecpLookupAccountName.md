# SecpLookupAccountName

- ea: `0x18002092c`
- end: `0x180020b0b`
- name: `SecpLookupAccountName`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18000bc10`

## callees

- `0x180001a68`
- `0x180007ba8`
- `0x180010a00`
- `0x180010d00`
- `0x18002092c`
- `0x180020e74`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x180020ace`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180020ace`
- `ntoskrnl!RtlCopySid` at `0x180020a87`
- `ntoskrnl!RtlCopySid` at `0x180020a87`
- `ntoskrnl!RtlLengthSid` at `0x180020a68`
- `ntoskrnl!RtlLengthSid` at `0x180020a68`

## pseudocode

```c
__int64 __fastcall SecpLookupAccountName(
        unsigned __int16 *a1,
        UNICODE_STRING *a2,
        _DWORD *a3,
        ULONG *a4,
        PSID DestinationSid,
        _DWORD *a6)
{
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 result; // rax
  size_t v13; // rbx
  const void *v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // ebx
  char *v17; // r15
  ULONG v18; // eax
  ULONG v19; // esi
  UNICODE_STRING SourceString; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v21[72]; // [rsp+30h] [rbp-D0h] BYREF

  memset(v21, 0, 0x1F8u);
  SourceString = 0;
  result = IsOkayToExec(v11, v10);
  if ( (int)result >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 20, WPP_ccfae065783230120d86f1ccbc684434_Traceguids);
    v13 = *a1;
    if ( (unsigned __int16)v13 > 0x120u )
      return 3221225485LL;
    memset(v21, 0, 0xD0u);
    v14 = (const void *)*((_QWORD *)a1 + 1);
    v21[0] = 7340104;
    v21[9] = 216;
    v21[5] = 23;
    LOWORD(v21[6]) = 0;
    v21[7] = 0;
    LOWORD(v21[8]) = v13;
    WORD1(v21[8]) = v13;
    memmove(&v21[27], v14, v13);
    LOWORD(v21[0]) = v13 + 176;
    WORD1(v21[0]) = v13 + 216;
    v16 = CallSPM(v15, v21, v21);
    if ( (v16 & 0x80000000) != 0 )
      return v16;
    v16 = HIDWORD(v21[5]);
    if ( v21[5] < 0 )
      return v16;
    v17 = (char *)v21 + v21[12];
    *a6 = v21[13];
    v18 = RtlLengthSid(v17);
    v19 = v18;
    if ( v18 >= *a4 )
    {
      *a4 = v18;
    }
    else
    {
      RtlCopySid(*a4, DestinationSid, v17);
      *a4 = v19;
      if ( !a2 )
        return v16;
      if ( !LOWORD(v21[10]) )
      {
        a2->Length = 0;
        return v16;
      }
      if ( LOWORD(v21[10]) <= a2->MaximumLength )
      {
        SourceString.Buffer = (wchar_t *)((char *)v21 + v21[11]);
        *(_DWORD *)&SourceString.Length = v21[10];
        RtlCopyUnicodeString(a2, &SourceString);
        return v16;
      }
      *a3 = LOWORD(v21[10]);
      a2->Length = 0;
    }
    return (unsigned int)-1073741789;
  }
  return result;
}

```

## disassembly

```asm
0x18002092c  push    rbp
0x18002092e  push    rbx
0x18002092f  push    rsi
0x180020930  push    rdi
0x180020931  push    r12
0x180020933  push    r13
0x180020935  push    r14
0x180020937  push    r15
0x180020939  lea     rbp, [rsp-138h]
0x180020941  sub     rsp, 238h
0x180020948  mov     r12, r8
0x18002094b  mov     rdi, rdx
0x18002094e  mov     rsi, rcx
0x180020951  xor     edx, edx; Val
0x180020953  mov     r8d, 1F8h; Size
0x180020959  lea     rcx, [rsp+270h+var_240]; void *
0x18002095e  mov     r14, r9
0x180020961  call    memset
0x180020966  xorps   xmm0, xmm0
0x180020969  movups  xmmword ptr [rsp+270h+SourceString.Length], xmm0
0x18002096e  call    IsOkayToExec
0x180020973  xor     r13d, r13d
0x180020976  test    eax, eax
0x180020978  js      loc_180020AF6
0x18002097e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020985  lea     rax, WPP_GLOBAL_Control
0x18002098c  cmp     rcx, rax
0x18002098f  jz      short loc_1800209AC
0x180020991  mov     eax, [rcx+2Ch]
0x180020994  test    al, 4
0x180020996  jz      short loc_1800209AC
0x180020998  mov     rcx, [rcx+18h]
0x18002099c  lea     edx, [r13+14h]
0x1800209a0  lea     r8, WPP_ccfae065783230120d86f1ccbc684434_Traceguids
0x1800209a7  call    WPP_SF_
0x1800209ac  movzx   ebx, word ptr [rsi]
0x1800209af  mov     eax, 120h
0x1800209b4  cmp     bx, ax
0x1800209b7  jbe     short loc_1800209C3
0x1800209b9  mov     eax, 0C000000Dh
0x1800209be  jmp     loc_180020AF6
0x1800209c3  xor     edx, edx; Val
0x1800209c5  lea     rcx, [rsp+270h+var_240]; void *
0x1800209ca  mov     r8d, 0D0h; Size
0x1800209d0  call    memset
0x1800209d5  mov     rdx, [rsi+8]; Src
0x1800209d9  lea     rcx, [rbp+170h+var_168]; void *
0x1800209dd  mov     r15d, 0D8h
0x1800209e3  mov     [rsp+270h+var_240], 700048h
0x1800209ec  mov     r8, rbx; Size
0x1800209ef  mov     [rsp+270h+var_1F8], r15
0x1800209f4  mov     [rsp+270h+var_218], 17h
0x1800209fd  mov     [rsp+270h+var_210], r13w
0x180020a03  mov     [rsp+270h+var_208], r13
0x180020a08  mov     [rsp+270h+var_200], bx
0x180020a0d  mov     [rsp+270h+var_1FE], bx
0x180020a12  call    memmove
0x180020a17  lea     eax, [r15-28h]
0x180020a1b  add     eax, ebx
0x180020a1d  lea     r8, [rsp+270h+var_240]
0x180020a22  add     bx, r15w
0x180020a26  mov     word ptr [rsp+270h+var_240], ax
0x180020a2b  lea     rdx, [rsp+270h+var_240]
0x180020a30  mov     word ptr [rsp+270h+var_240+2], bx
0x180020a35  call    CallSPM
0x180020a3a  mov     ebx, eax
0x180020a3c  test    eax, eax
0x180020a3e  js      loc_180020AF4
0x180020a44  mov     ebx, dword ptr [rsp+270h+var_218+4]
0x180020a48  test    ebx, ebx
0x180020a4a  js      loc_180020AF4
0x180020a50  mov     rcx, [rbp+170h+arg_28]
0x180020a57  lea     r15, [rsp+270h+var_240]
0x180020a5c  mov     eax, [rbp+170h+var_1D8]
0x180020a5f  add     r15, [rbp+170h+var_1E0]
0x180020a63  mov     [rcx], eax
0x180020a65  mov     rcx, r15; Sid
0x180020a68  call    cs:__imp_RtlLengthSid
0x180020a6f  nop     dword ptr [rax+rax+00h]
0x180020a74  mov     ecx, [r14]; DestinationSidLength
0x180020a77  mov     esi, eax
0x180020a79  cmp     eax, ecx
0x180020a7b  jnb     short loc_180020AEC
0x180020a7d  mov     rdx, [rbp+170h+DestinationSid]; DestinationSid
0x180020a84  mov     r8, r15; SourceSid
0x180020a87  call    cs:__imp_RtlCopySid
0x180020a8e  nop     dword ptr [rax+rax+00h]
0x180020a93  mov     [r14], esi
0x180020a96  test    rdi, rdi
0x180020a99  jz      short loc_180020AF4
0x180020a9b  movzx   edx, [rbp+170h+var_1F0]
0x180020a9f  test    dx, dx
0x180020aa2  jz      short loc_180020AE6
0x180020aa4  cmp     dx, [rdi+2]
0x180020aa8  ja      short loc_180020ADC
0x180020aaa  movzx   eax, [rbp+170h+var_1EE]
0x180020aae  lea     rcx, [rsp+270h+var_240]
0x180020ab3  add     rcx, [rbp+170h+var_1E8]
0x180020ab7  mov     [rsp+270h+SourceString.Buffer], rcx
0x180020abc  mov     rcx, rdi; DestinationString
0x180020abf  mov     [rsp+270h+SourceString.Length], dx
0x180020ac4  lea     rdx, [rsp+270h+SourceString]; SourceString
0x180020ac9  mov     [rsp+270h+SourceString.MaximumLength], ax
0x180020ace  call    cs:__imp_RtlCopyUnicodeString
0x180020ad5  nop     dword ptr [rax+rax+00h]
0x180020ada  jmp     short loc_180020AF4
0x180020adc  mov     [r12], edx
0x180020ae0  mov     [rdi], r13w
0x180020ae4  jmp     short loc_180020AEF
0x180020ae6  mov     [rdi], r13w
0x180020aea  jmp     short loc_180020AF4
0x180020aec  mov     [r14], esi
0x180020aef  mov     ebx, 0C0000023h
0x180020af4  mov     eax, ebx
0x180020af6  add     rsp, 238h
0x180020afd  pop     r15
0x180020aff  pop     r14
0x180020b01  pop     r13
0x180020b03  pop     r12
0x180020b05  pop     rdi
0x180020b06  pop     rsi
0x180020b07  pop     rbx
0x180020b08  pop     rbp
0x180020b09  retn
```
