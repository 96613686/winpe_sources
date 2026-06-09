# EnableInterfaceWithAllProtocols

- ea: `0x180016d68`
- end: `0x180016f2c`
- name: `EnableInterfaceWithAllProtocols`
- size: `452`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019894`
- `0x180022f60`
- `0x1800292bc`

## callees

- `0x180011790`
- `0x180016d68`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180016efd`
- `ntdll!RtlReleaseResource` at `0x180016efd`
- `ntdll!RtlAcquireResourceShared` at `0x180016e26`
- `ntdll!RtlAcquireResourceShared` at `0x180016e26`

## string_xrefs

- `0x180016dea`: `Entered: EnableInterfaceWithAllProtocols`
- `0x180016e79`: `EnableInterfaceWithAllProtocols: Couldnt enable %ws with %ws. Error %d`

## pseudocode

```c
__int64 __fastcall EnableInterfaceWithAllProtocols(__int64 a1)
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
      (unsigned int)L"Entered: EnableInterfaceWithAllProtocols",
      (_DWORD)v2,
      *(_QWORD *)(a1 + 72),
      (__int64)&v11);
  }
  v3 = 0;
  RtlAcquireResourceShared(&stru_18008C4A0, 1u);
  for ( i = *(_QWORD **)(a1 + 56); i != (_QWORD *)(a1 + 56); i = (_QWORD *)*i )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, bool, __int64))(i[3] + 144LL))(
           *(unsigned int *)(a1 + 16),
           *(_DWORD *)(a1 + 168) >= 4u,
           1);
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
          L"EnableInterfaceWithAllProtocols: Couldnt enable %ws with %ws. Error %d",
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
0x180016d68  mov     [rsp-8+arg_8], rbx
0x180016d6d  mov     [rsp-8+arg_10], rsi
0x180016d72  push    rbp
0x180016d73  push    rdi
0x180016d74  push    r14
0x180016d76  lea     rbp, [rsp-780h]
0x180016d7e  sub     rsp, 880h
0x180016d85  mov     rax, cs:__security_cookie
0x180016d8c  xor     rax, rsp
0x180016d8f  mov     [rbp+790h+var_20], rax
0x180016d96  mov     rdi, rcx
0x180016d99  xor     eax, eax
0x180016d9b  lea     rcx, [rsp+890h+var_81C]; void *
0x180016da0  mov     [rsp+890h+var_820], eax
0x180016da4  xor     edx, edx; Val
0x180016da6  mov     r8d, 7FCh; Size
0x180016dac  call    memset_0
0x180016db1  xor     eax, eax
0x180016db3  xorps   xmm0, xmm0
0x180016db6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180016dbd  mov     [rsp+890h+var_848], eax
0x180016dc1  movups  [rsp+890h+var_844], xmm0
0x180016dc6  mov     [rsp+890h+var_824], eax
0x180016dca  movups  [rsp+890h+var_834], xmm0
0x180016dcf  movups  [rsp+890h+var_858], xmm0
0x180016dd4  jz      short loc_180016E1B
0x180016dd6  mov     word ptr [rsp+890h+var_848], ax
0x180016ddb  lea     r9, [rsp+890h+var_858]
0x180016de0  lea     rax, [rdi+2B0h]
0x180016de7  test    rax, rax
0x180016dea  lea     r8, aEnteredEnablei; "Entered: EnableInterfaceWithAllProtocol"...
0x180016df1  lea     rdx, RasRtrmgrParamTraceInfo
0x180016df8  cmovnz  r9, rax
0x180016dfc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016e03  lea     rax, [rsp+890h+var_848]
0x180016e08  mov     [rsp+890h+var_868], rax
0x180016e0d  mov     rax, [rdi+48h]
0x180016e11  mov     [rsp+890h+var_870], rax
0x180016e16  call    McTemplateU0zjzz_EventWriteTransfer
0x180016e1b  xor     esi, esi
0x180016e1d  lea     rcx, stru_18008C4A0; Resource
0x180016e24  mov     dl, 1; Wait
0x180016e26  call    cs:__imp_RtlAcquireResourceShared
0x180016e2c  lea     r14, [rdi+38h]
0x180016e30  mov     rbx, [r14]
0x180016e33  cmp     rbx, r14
0x180016e36  jz      loc_180016EF6
0x180016e3c  mov     rax, [rbx+18h]
0x180016e40  xor     edx, edx
0x180016e42  cmp     dword ptr [rdi+0A8h], 4
0x180016e49  mov     ecx, [rdi+10h]
0x180016e4c  setnb   dl
0x180016e4f  xor     r9d, r9d
0x180016e52  mov     rax, [rax+90h]
0x180016e59  lea     r8d, [r9+1]
0x180016e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e62  mov     ecx, eax
0x180016e64  test    eax, eax
0x180016e66  jz      loc_180016EEE
0x180016e6c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180016e73  jz      short loc_180016EE9
0x180016e75  mov     r8, [rdi+48h]
0x180016e79  lea     rdx, aEnableinterfac; "EnableInterfaceWithAllProtocols: Couldn"...
0x180016e80  xor     eax, eax
0x180016e82  mov     dword ptr [rsp+890h+var_870], ecx
0x180016e86  mov     word ptr [rsp+890h+var_820], ax
0x180016e8b  lea     rcx, [rsp+890h+var_820]
0x180016e90  mov     word ptr [rsp+890h+var_848], ax
0x180016e95  mov     r9, [rbx+18h]
0x180016e99  mov     r9, [r9+20h]
0x180016e9d  call    FormatRRASErrorString
0x180016ea2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180016ea9  jz      short loc_180016EE9
0x180016eab  lea     rax, [rdi+2B0h]
0x180016eb2  test    rax, rax
0x180016eb5  lea     r9, [rsp+890h+var_858]
0x180016eba  lea     r8, [rsp+890h+var_820]
0x180016ebf  cmovnz  r9, rax
0x180016ec3  lea     rdx, RasRtrMgrParamTraceError
0x180016eca  lea     rax, [rsp+890h+var_848]
0x180016ecf  mov     [rsp+890h+var_868], rax
0x180016ed4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016edb  mov     rax, [rdi+48h]
0x180016edf  mov     [rsp+890h+var_870], rax
0x180016ee4  call    McTemplateU0zjzz_EventWriteTransfer
0x180016ee9  mov     esi, 3EBh
0x180016eee  mov     rbx, [rbx]
0x180016ef1  jmp     loc_180016E33
0x180016ef6  lea     rcx, stru_18008C4A0; Resource
0x180016efd  call    cs:__imp_RtlReleaseResource
0x180016f03  mov     eax, esi
0x180016f05  mov     rcx, [rbp+790h+var_20]
0x180016f0c  xor     rcx, rsp; StackCookie
0x180016f0f  call    __security_check_cookie
0x180016f14  lea     r11, [rsp+890h+var_10]
0x180016f1c  mov     rbx, [r11+28h]
0x180016f20  mov     rsi, [r11+30h]
0x180016f24  mov     rsp, r11
0x180016f27  pop     r14
0x180016f29  pop     rdi
0x180016f2a  pop     rbp
0x180016f2b  retn
```
