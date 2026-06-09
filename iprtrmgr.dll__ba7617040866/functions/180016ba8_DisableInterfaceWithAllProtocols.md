# DisableInterfaceWithAllProtocols

- ea: `0x180016ba8`
- end: `0x180016d62`
- name: `DisableInterfaceWithAllProtocols`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019540`

## callees

- `0x180011790`
- `0x180016ba8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180016d33`
- `ntdll!RtlReleaseResource` at `0x180016d33`
- `ntdll!RtlAcquireResourceShared` at `0x180016c66`
- `ntdll!RtlAcquireResourceShared` at `0x180016c66`

## string_xrefs

- `0x180016c2a`: `DisableInterfaceWithAllProtocols`
- `0x180016caf`: `DisableInterfaceWithAllProtocols: Couldnt disable %ws with %ws. Error %d`

## pseudocode

```c
__int64 __fastcall DisableInterfaceWithAllProtocols(__int64 a1)
{
  __int128 *v2; // r9
  unsigned int v3; // esi
  _QWORD *i; // rbx
  int v5; // ecx
  __int64 v6; // r8
  __int128 *v7; // r9
  __int64 v9; // [rsp+20h] [rbp-E0h]
  __int128 v10; // [rsp+38h] [rbp-C8h] BYREF
  int v11; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v12; // [rsp+4Ch] [rbp-B4h]
  __int128 v13; // [rsp+5Ch] [rbp-A4h]
  int v14; // [rsp+6Ch] [rbp-94h]
  int v15; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  v11 = 0;
  v12 = 0;
  v14 = 0;
  v13 = 0;
  v10 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v11) = 0;
    v2 = &v10;
    if ( a1 != -688 )
      LODWORD(v2) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"DisableInterfaceWithAllProtocols",
      (_DWORD)v2,
      *(_QWORD *)(a1 + 72),
      (__int64)&v11);
  }
  v3 = 0;
  RtlAcquireResourceShared(&stru_18008C4A0, 1u);
  for ( i = *(_QWORD **)(a1 + 56); i != (_QWORD *)(a1 + 56); i = (_QWORD *)*i )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(i[3] + 144LL))(*(unsigned int *)(a1 + 16), 0, 2);
    if ( v5 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v6 = *(_QWORD *)(a1 + 72);
        LODWORD(v9) = v5;
        LOWORD(v15) = 0;
        LOWORD(v11) = 0;
        FormatRRASErrorString(
          &v15,
          L"DisableInterfaceWithAllProtocols: Couldnt disable %ws with %ws. Error %d",
          v6,
          *(_QWORD *)(i[3] + 32LL),
          v9);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v7 = &v10;
          if ( a1 != -688 )
            LODWORD(v7) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v15,
            (_DWORD)v7,
            *(_QWORD *)(a1 + 72),
            (__int64)&v11);
        }
      }
      v3 = 1003;
    }
  }
  RtlReleaseResource(&stru_18008C4A0);
  return v3;
}

```

## disassembly

```asm
0x180016ba8  mov     [rsp-8+arg_8], rbx
0x180016bad  mov     [rsp-8+arg_10], rsi
0x180016bb2  push    rbp
0x180016bb3  push    rdi
0x180016bb4  push    r14
0x180016bb6  lea     rbp, [rsp-780h]
0x180016bbe  sub     rsp, 880h
0x180016bc5  mov     rax, cs:__security_cookie
0x180016bcc  xor     rax, rsp
0x180016bcf  mov     [rbp+790h+var_20], rax
0x180016bd6  mov     rdi, rcx
0x180016bd9  xor     eax, eax
0x180016bdb  lea     rcx, [rsp+890h+var_81C]; void *
0x180016be0  mov     [rsp+890h+var_820], eax
0x180016be4  xor     edx, edx; Val
0x180016be6  mov     r8d, 7FCh; Size
0x180016bec  call    memset_0
0x180016bf1  xor     eax, eax
0x180016bf3  xorps   xmm0, xmm0
0x180016bf6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180016bfd  mov     [rsp+890h+var_848], eax
0x180016c01  movups  [rsp+890h+var_844], xmm0
0x180016c06  mov     [rsp+890h+var_824], eax
0x180016c0a  movups  [rsp+890h+var_834], xmm0
0x180016c0f  movups  [rsp+890h+var_858], xmm0
0x180016c14  jz      short loc_180016C5B
0x180016c16  mov     word ptr [rsp+890h+var_848], ax
0x180016c1b  lea     r9, [rsp+890h+var_858]
0x180016c20  lea     rax, [rdi+2B0h]
0x180016c27  test    rax, rax
0x180016c2a  lea     r8, aDisableinterfa; "DisableInterfaceWithAllProtocols"
0x180016c31  lea     rdx, RasRtrmgrParamTraceInfo
0x180016c38  cmovnz  r9, rax
0x180016c3c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016c43  lea     rax, [rsp+890h+var_848]
0x180016c48  mov     [rsp+890h+var_868], rax
0x180016c4d  mov     rax, [rdi+48h]
0x180016c51  mov     [rsp+890h+var_870], rax
0x180016c56  call    McTemplateU0zjzz_EventWriteTransfer
0x180016c5b  xor     esi, esi
0x180016c5d  lea     rcx, stru_18008C4A0; Resource
0x180016c64  mov     dl, 1; Wait
0x180016c66  call    cs:__imp_RtlAcquireResourceShared
0x180016c6c  lea     r14, [rdi+38h]
0x180016c70  mov     rbx, [r14]
0x180016c73  cmp     rbx, r14
0x180016c76  jz      loc_180016D2C
0x180016c7c  mov     rax, [rbx+18h]
0x180016c80  xor     r9d, r9d
0x180016c83  mov     ecx, [rdi+10h]
0x180016c86  xor     edx, edx
0x180016c88  mov     rax, [rax+90h]
0x180016c8f  lea     r8d, [r9+2]
0x180016c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c98  mov     ecx, eax
0x180016c9a  test    eax, eax
0x180016c9c  jz      loc_180016D24
0x180016ca2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180016ca9  jz      short loc_180016D1F
0x180016cab  mov     r8, [rdi+48h]
0x180016caf  lea     rdx, aDisableinterfa_0; "DisableInterfaceWithAllProtocols: Could"...
0x180016cb6  xor     eax, eax
0x180016cb8  mov     dword ptr [rsp+890h+var_870], ecx
0x180016cbc  mov     word ptr [rsp+890h+var_820], ax
0x180016cc1  lea     rcx, [rsp+890h+var_820]
0x180016cc6  mov     word ptr [rsp+890h+var_848], ax
0x180016ccb  mov     r9, [rbx+18h]
0x180016ccf  mov     r9, [r9+20h]
0x180016cd3  call    FormatRRASErrorString
0x180016cd8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180016cdf  jz      short loc_180016D1F
0x180016ce1  lea     rax, [rdi+2B0h]
0x180016ce8  test    rax, rax
0x180016ceb  lea     r9, [rsp+890h+var_858]
0x180016cf0  lea     r8, [rsp+890h+var_820]
0x180016cf5  cmovnz  r9, rax
0x180016cf9  lea     rdx, RasRtrMgrParamTraceError
0x180016d00  lea     rax, [rsp+890h+var_848]
0x180016d05  mov     [rsp+890h+var_868], rax
0x180016d0a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016d11  mov     rax, [rdi+48h]
0x180016d15  mov     [rsp+890h+var_870], rax
0x180016d1a  call    McTemplateU0zjzz_EventWriteTransfer
0x180016d1f  mov     esi, 3EBh
0x180016d24  mov     rbx, [rbx]
0x180016d27  jmp     loc_180016C73
0x180016d2c  lea     rcx, stru_18008C4A0; Resource
0x180016d33  call    cs:__imp_RtlReleaseResource
0x180016d39  mov     eax, esi
0x180016d3b  mov     rcx, [rbp+790h+var_20]
0x180016d42  xor     rcx, rsp; StackCookie
0x180016d45  call    __security_check_cookie
0x180016d4a  lea     r11, [rsp+890h+var_10]
0x180016d52  mov     rbx, [r11+28h]
0x180016d56  mov     rsi, [r11+30h]
0x180016d5a  mov     rsp, r11
0x180016d5d  pop     r14
0x180016d5f  pop     rdi
0x180016d60  pop     rbp
0x180016d61  retn
```
