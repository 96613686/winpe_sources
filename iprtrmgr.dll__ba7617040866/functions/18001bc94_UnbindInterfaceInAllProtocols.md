# UnbindInterfaceInAllProtocols

- ea: `0x18001bc94`
- end: `0x18001be62`
- name: `UnbindInterfaceInAllProtocols`
- size: `462`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001739c`
- `0x180018be4`

## callees

- `0x180011790`
- `0x18001bc94`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18001be3b`
- `ntdll!RtlReleaseResource` at `0x18001be3b`
- `ntdll!RtlAcquireResourceShared` at `0x18001bd76`
- `ntdll!RtlAcquireResourceShared` at `0x18001bd76`

## string_xrefs

- `0x18001bd31`: `Entered: UnbindInterfaceInAllProtocols`
- `0x18001bdbb`: `UnbindInterfaceInAllProtocols: Error %d unbinding %ws in %ws`

## pseudocode

```c
__int64 __fastcall UnbindInterfaceInAllProtocols(__int64 a1)
{
  __int128 *v2; // r15
  bool v3; // zf
  __int128 *v4; // r9
  unsigned int v5; // esi
  _QWORD *i; // rbx
  unsigned int v7; // eax
  __int64 v8; // r9
  __int128 *v9; // r9
  __int128 v11; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v12; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+58h] [rbp-A8h]
  _OWORD v14[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+80h] [rbp-80h] BYREF
  __int128 v16; // [rsp+84h] [rbp-7Ch]
  __int128 v17; // [rsp+94h] [rbp-6Ch]
  int v18; // [rsp+A4h] [rbp-5Ch]
  int v19; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v20[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  v13 = 0;
  v19 = 0;
  v12 = 0;
  memset(v14, 0, sizeof(v14));
  memset_0(v20, 0, sizeof(v20));
  v2 = v14;
  v3 = *(_DWORD *)(a1 + 516) == 0;
  v15 = 0;
  v18 = 0;
  if ( !v3 )
    v2 = &v12;
  v16 = 0;
  v17 = 0;
  v11 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v4 = &v11;
    LOWORD(v15) = 0;
    if ( a1 != -688 )
      LODWORD(v4) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: UnbindInterfaceInAllProtocols",
      (_DWORD)v4,
      *(_QWORD *)(a1 + 72),
      (__int64)&v15);
  }
  v5 = 0;
  RtlAcquireResourceShared(&stru_18008C4A0, 1u);
  for ( i = *(_QWORD **)(a1 + 56); i != (_QWORD *)(a1 + 56); i = (_QWORD *)*i )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int128 *))(i[3] + 144LL))(
           *(unsigned int *)(a1 + 16),
           0,
           0,
           v2);
    if ( v7 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v8 = *(_QWORD *)(a1 + 72);
        LOWORD(v19) = 0;
        LOWORD(v15) = 0;
        FormatRRASErrorString(
          &v19,
          L"UnbindInterfaceInAllProtocols: Error %d unbinding %ws in %ws",
          v7,
          v8,
          *(_QWORD *)(i[3] + 32LL));
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v9 = &v11;
          if ( a1 != -688 )
            LODWORD(v9) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v19,
            (_DWORD)v9,
            *(_QWORD *)(a1 + 72),
            (__int64)&v15);
        }
      }
      v5 = 1003;
    }
  }
  RtlReleaseResource(&stru_18008C4A0);
  return v5;
}

```

## disassembly

```asm
0x18001bc94  push    rbp
0x18001bc96  push    rbx
0x18001bc97  push    rsi
0x18001bc98  push    rdi
0x18001bc99  push    r14
0x18001bc9b  push    r15
0x18001bc9d  lea     rbp, [rsp-7C8h]
0x18001bca5  sub     rsp, 8C8h
0x18001bcac  mov     rax, cs:__security_cookie
0x18001bcb3  xor     rax, rsp
0x18001bcb6  mov     [rbp+7F0h+var_40], rax
0x18001bcbd  xor     eax, eax
0x18001bcbf  xorps   xmm1, xmm1
0x18001bcc2  mov     rdi, rcx
0x18001bcc5  mov     [rsp+8F0h+var_898], rax
0x18001bcca  xorps   xmm0, xmm0
0x18001bccd  mov     [rbp+7F0h+var_840], eax
0x18001bcd0  lea     rcx, [rbp+7F0h+var_83C]; void *
0x18001bcd4  xor     edx, edx; Val
0x18001bcd6  mov     r8d, 7FCh; Size
0x18001bcdc  movups  [rsp+8F0h+var_8A8], xmm0
0x18001bce1  movups  [rsp+8F0h+var_890], xmm1
0x18001bce6  movups  [rsp+8F0h+var_880], xmm1
0x18001bceb  call    memset_0
0x18001bcf0  xor     eax, eax
0x18001bcf2  lea     r15, [rsp+8F0h+var_890]
0x18001bcf7  cmp     dword ptr [rdi+204h], 0
0x18001bcfe  xorps   xmm0, xmm0
0x18001bd01  mov     [rbp+7F0h+var_870], eax
0x18001bd04  mov     [rbp+7F0h+var_84C], eax
0x18001bd07  lea     rax, [rsp+8F0h+var_8A8]
0x18001bd0c  cmovnz  r15, rax
0x18001bd10  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18001bd17  movups  [rbp+7F0h+var_86C], xmm0
0x18001bd1b  movups  [rbp+7F0h+var_85C], xmm0
0x18001bd1f  movups  [rsp+8F0h+var_8B8], xmm0
0x18001bd24  jz      short loc_18001BD6B
0x18001bd26  xor     eax, eax
0x18001bd28  lea     r9, [rsp+8F0h+var_8B8]
0x18001bd2d  mov     word ptr [rbp+7F0h+var_870], ax
0x18001bd31  lea     r8, aEnteredUnbindi; "Entered: UnbindInterfaceInAllProtocols"
0x18001bd38  lea     rax, [rdi+2B0h]
0x18001bd3f  test    rax, rax
0x18001bd42  lea     rdx, RasRtrmgrParamTraceInfo
0x18001bd49  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001bd50  cmovnz  r9, rax
0x18001bd54  lea     rax, [rbp+7F0h+var_870]
0x18001bd58  mov     [rsp+8F0h+var_8C8], rax
0x18001bd5d  mov     rax, [rdi+48h]
0x18001bd61  mov     [rsp+8F0h+var_8D0], rax
0x18001bd66  call    McTemplateU0zjzz_EventWriteTransfer
0x18001bd6b  xor     esi, esi
0x18001bd6d  lea     rcx, stru_18008C4A0; Resource
0x18001bd74  mov     dl, 1; Wait
0x18001bd76  call    cs:__imp_RtlAcquireResourceShared
0x18001bd7c  lea     r14, [rdi+38h]
0x18001bd80  mov     rbx, [r14]
0x18001bd83  cmp     rbx, r14
0x18001bd86  jz      loc_18001BE34
0x18001bd8c  mov     rax, [rbx+18h]
0x18001bd90  mov     r9, r15
0x18001bd93  mov     ecx, [rdi+10h]
0x18001bd96  xor     r8d, r8d
0x18001bd99  xor     edx, edx
0x18001bd9b  mov     rax, [rax+90h]
0x18001bda2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bda7  mov     r8d, eax
0x18001bdaa  test    eax, eax
0x18001bdac  jz      short loc_18001BE2C
0x18001bdae  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001bdb5  jz      short loc_18001BE27
0x18001bdb7  mov     r9, [rdi+48h]
0x18001bdbb  lea     rdx, aUnbindinterfac; "UnbindInterfaceInAllProtocols: Error %d"...
0x18001bdc2  xor     eax, eax
0x18001bdc4  mov     word ptr [rbp+7F0h+var_840], ax
0x18001bdc8  mov     word ptr [rbp+7F0h+var_870], ax
0x18001bdcc  mov     rax, [rbx+18h]
0x18001bdd0  mov     rcx, [rax+20h]
0x18001bdd4  mov     [rsp+8F0h+var_8D0], rcx
0x18001bdd9  lea     rcx, [rbp+7F0h+var_840]
0x18001bddd  call    FormatRRASErrorString
0x18001bde2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001bde9  jz      short loc_18001BE27
0x18001bdeb  lea     rax, [rdi+2B0h]
0x18001bdf2  test    rax, rax
0x18001bdf5  lea     r9, [rsp+8F0h+var_8B8]
0x18001bdfa  lea     r8, [rbp+7F0h+var_840]
0x18001bdfe  cmovnz  r9, rax
0x18001be02  lea     rdx, RasRtrMgrParamTraceError
0x18001be09  lea     rax, [rbp+7F0h+var_870]
0x18001be0d  mov     [rsp+8F0h+var_8C8], rax
0x18001be12  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001be19  mov     rax, [rdi+48h]
0x18001be1d  mov     [rsp+8F0h+var_8D0], rax
0x18001be22  call    McTemplateU0zjzz_EventWriteTransfer
0x18001be27  mov     esi, 3EBh
0x18001be2c  mov     rbx, [rbx]
0x18001be2f  jmp     loc_18001BD83
0x18001be34  lea     rcx, stru_18008C4A0; Resource
0x18001be3b  call    cs:__imp_RtlReleaseResource
0x18001be41  mov     eax, esi
0x18001be43  mov     rcx, [rbp+7F0h+var_40]
0x18001be4a  xor     rcx, rsp; StackCookie
0x18001be4d  call    __security_check_cookie
0x18001be52  add     rsp, 8C8h
0x18001be59  pop     r15
0x18001be5b  pop     r14
0x18001be5d  pop     rdi
0x18001be5e  pop     rsi
0x18001be5f  pop     rbx
0x18001be60  pop     rbp
0x18001be61  retn
```
