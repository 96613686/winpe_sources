# SecpLookupWellKnownSid

- ea: `0x180027ebc`
- end: `0x180028017`
- name: `SecpLookupWellKnownSid`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x180004190`

## callees

- `0x180001a68`
- `0x180007ba8`
- `0x180007bd8`
- `0x180010980`
- `0x180010c80`
- `0x180020e74`
- `0x180027ebc`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x180027fd2`
- `ntoskrnl!RtlLengthSid` at `0x180027fd2`

## pseudocode

```c
__int64 __fastcall SecpLookupWellKnownSid(int a1, void *a2, ULONG a3, ULONG *a4)
{
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 result; // rax
  __int64 v11; // rcx
  int v12; // edi
  char *v13; // rbx
  ULONG v14; // eax
  ULONG v15; // esi
  _QWORD v16[70]; // [rsp+20h] [rbp-E0h] BYREF

  memset(v16, 0, 0x1F8u);
  result = IsOkayToExec(v9, v8);
  if ( (int)result >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 21, WPP_ccfae065783230120d86f1ccbc684434_Traceguids);
    memset(v16, 0, 0xD0u);
    v16[0] = 5242920;
    LOWORD(v16[6]) = 0;
    v16[7] = 0;
    v16[5] = 24;
    LODWORD(v16[8]) = a1;
    v12 = CallSPM(v11, v16, v16);
    if ( v12 >= 0 )
      v12 = HIDWORD(v16[5]);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        22,
        WPP_ccfae065783230120d86f1ccbc684434_Traceguids,
        (unsigned int)v12);
    if ( v12 >= 0 )
    {
      v13 = (char *)v16[9];
      if ( (unsigned __int64)(v16[9] - 216LL) <= 0x11F )
        v13 = (char *)v16 + v16[9];
      if ( v13 )
      {
        v14 = RtlLengthSid(v13);
        v15 = v14;
        if ( v14 > a3 )
          v12 = -1073741789;
        else
          memmove(a2, v13, v14);
        if ( a4 )
          *a4 = v15;
      }
      else
      {
        return (unsigned int)-1073741811;
      }
    }
    return (unsigned int)v12;
  }
  return result;
}

```

## disassembly

```asm
0x180027ebc  push    rbp
0x180027ebe  push    rbx
0x180027ebf  push    rsi
0x180027ec0  push    rdi
0x180027ec1  push    r12
0x180027ec3  push    r14
0x180027ec5  push    r15
0x180027ec7  lea     rbp, [rsp-120h]
0x180027ecf  sub     rsp, 220h
0x180027ed6  mov     r15d, r8d
0x180027ed9  mov     r12, rdx
0x180027edc  mov     ebx, ecx
0x180027ede  xor     edx, edx; Val
0x180027ee0  mov     r8d, 1F8h; Size
0x180027ee6  lea     rcx, [rsp+250h+var_230]; void *
0x180027eeb  mov     r14, r9
0x180027eee  call    memset
0x180027ef3  call    IsOkayToExec
0x180027ef8  test    eax, eax
0x180027efa  js      loc_180028004
0x180027f00  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f07  lea     rsi, WPP_GLOBAL_Control
0x180027f0e  cmp     rcx, rsi
0x180027f11  jz      short loc_180027F2F
0x180027f13  mov     eax, [rcx+2Ch]
0x180027f16  test    al, 4
0x180027f18  jz      short loc_180027F2F
0x180027f1a  mov     rcx, [rcx+18h]
0x180027f1e  lea     r8, WPP_ccfae065783230120d86f1ccbc684434_Traceguids
0x180027f25  mov     edx, 15h
0x180027f2a  call    WPP_SF_
0x180027f2f  xor     edx, edx; Val
0x180027f31  lea     rcx, [rsp+250h+var_230]; void *
0x180027f36  mov     r8d, 0D0h; Size
0x180027f3c  call    memset
0x180027f41  xor     eax, eax
0x180027f43  mov     [rsp+250h+var_230], 500028h
0x180027f4c  lea     r8, [rsp+250h+var_230]
0x180027f51  mov     [rsp+250h+var_200], ax
0x180027f56  lea     rdx, [rsp+250h+var_230]
0x180027f5b  mov     [rsp+250h+var_1F8], rax
0x180027f60  mov     [rsp+250h+var_208], 18h
0x180027f69  mov     [rsp+250h+var_1F0], ebx
0x180027f6d  call    CallSPM
0x180027f72  test    eax, eax
0x180027f74  mov     edi, eax
0x180027f76  cmovns  edi, dword ptr [rsp+250h+var_208+4]
0x180027f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f82  cmp     rcx, rsi
0x180027f85  jz      short loc_180027FA6
0x180027f87  mov     eax, [rcx+2Ch]
0x180027f8a  test    al, 4
0x180027f8c  jz      short loc_180027FA6
0x180027f8e  mov     rcx, [rcx+18h]
0x180027f92  lea     r8, WPP_ccfae065783230120d86f1ccbc684434_Traceguids
0x180027f99  mov     edx, 16h
0x180027f9e  mov     r9d, edi
0x180027fa1  call    WPP_SF_D
0x180027fa6  test    edi, edi
0x180027fa8  js      short loc_180028002
0x180027faa  mov     rbx, [rsp+250h+Sid]
0x180027faf  lea     rax, [rbx-0D8h]
0x180027fb6  cmp     rax, 11Fh
0x180027fbc  ja      short loc_180027FC3
0x180027fbe  lea     rbx, [rsp+rbx+250h+var_230]
0x180027fc3  test    rbx, rbx
0x180027fc6  jnz     short loc_180027FCF
0x180027fc8  mov     edi, 0C000000Dh
0x180027fcd  jmp     short loc_180028002
0x180027fcf  mov     rcx, rbx; Sid
0x180027fd2  call    cs:__imp_RtlLengthSid
0x180027fd9  nop     dword ptr [rax+rax+00h]
0x180027fde  mov     esi, eax
0x180027fe0  cmp     eax, r15d
0x180027fe3  ja      short loc_180027FF5
0x180027fe5  mov     r8d, esi; Size
0x180027fe8  mov     rdx, rbx; Src
0x180027feb  mov     rcx, r12; void *
0x180027fee  call    memmove
0x180027ff3  jmp     short loc_180027FFA
0x180027ff5  mov     edi, 0C0000023h
0x180027ffa  test    r14, r14
0x180027ffd  jz      short loc_180028002
0x180027fff  mov     [r14], esi
0x180028002  mov     eax, edi
0x180028004  add     rsp, 220h
0x18002800b  pop     r15
0x18002800d  pop     r14
0x18002800f  pop     r12
0x180028011  pop     rdi
0x180028012  pop     rsi
0x180028013  pop     rbx
0x180028014  pop     rbp
0x180028015  retn
```
