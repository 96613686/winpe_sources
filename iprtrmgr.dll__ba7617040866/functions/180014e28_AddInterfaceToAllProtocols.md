# AddInterfaceToAllProtocols

- ea: `0x180014e28`
- end: `0x1800150c1`
- name: `AddInterfaceToAllProtocols`
- size: `665`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022f60`

## callees

- `0x180011790`
- `0x180014e28`
- `0x1800150c8`
- `0x18001e490`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18001508c`
- `ntdll!RtlReleaseResource` at `0x18001508c`
- `ntdll!RtlAcquireResourceShared` at `0x180014f90`
- `ntdll!RtlAcquireResourceShared` at `0x180014f90`

## string_xrefs

- `0x180014ea5`: `Entered: AddInterfaceToAllProtocols`
- `0x180014ef8`: `AddInterfaceToAllProtocols: No interface info for %ws. Not adding to any protocols`
- `0x18001500d`: `AddInterfaceToAllProtocols: Error %d adding %ws to %ws`

## pseudocode

```c
__int64 __fastcall AddInterfaceToAllProtocols(__int64 a1, __int64 a2)
{
  char v4; // al
  __int128 *v5; // r9
  __int64 v6; // r8
  __int128 *v7; // r9
  int v8; // r15d
  int v9; // r12d
  __int64 *v10; // r14
  int v11; // r13d
  __int64 i; // rbx
  _DWORD *PointerToTocEntry; // rax
  __int64 v14; // r8
  __int64 v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // r9
  __int128 *v18; // r9
  __int128 v20; // [rsp+38h] [rbp-870h] BYREF
  int v21; // [rsp+48h] [rbp-860h] BYREF
  __int128 v22; // [rsp+4Ch] [rbp-85Ch]
  __int128 v23; // [rsp+5Ch] [rbp-84Ch]
  int v24; // [rsp+6Ch] [rbp-83Ch]
  int v25; // [rsp+70h] [rbp-838h] BYREF
  _BYTE v26[2044]; // [rsp+74h] [rbp-834h] BYREF

  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v21 = 0;
  v24 = 0;
  v4 = Microsoft_Windows_RRASEnableBits;
  v22 = 0;
  v23 = 0;
  v20 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v5 = &v20;
    LOWORD(v21) = 0;
    if ( a1 != -688 )
      LODWORD(v5) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: AddInterfaceToAllProtocols",
      (_DWORD)v5,
      *(_QWORD *)(a1 + 72),
      (__int64)&v21);
    v4 = Microsoft_Windows_RRASEnableBits;
  }
  if ( a2 )
  {
    v8 = 0;
    v9 = 0;
    v10 = (__int64 *)&g_leProtoCbListV4;
    v11 = 0;
    if ( *(_DWORD *)(a1 + 516) != 1 )
      v10 = &g_leProtoCbListV6;
    RtlAcquireResourceShared(&stru_18008C4A0, 1u);
    for ( i = *v10; (__int64 *)i != v10; i = *(_QWORD *)i )
    {
      PointerToTocEntry = (_DWORD *)GetPointerToTocEntry(*(unsigned int *)(i + 60), a2);
      v14 = 0;
      if ( PointerToTocEntry && PointerToTocEntry[1] )
      {
        v15 = (unsigned int)PointerToTocEntry[3];
        if ( (unsigned int)v15 < *(_DWORD *)(a2 + 4) )
          v14 = a2 + v15;
        v9 = PointerToTocEntry[1];
        v8 = 1280;
        v11 = PointerToTocEntry[2];
      }
      if ( (*(_BYTE *)(i + 64) & 0x10) != 0 || v14 )
      {
        v16 = AddInterfaceToProtocol(a1, i, v14, v8, v9, v11);
        if ( v16 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v17 = *(_QWORD *)(a1 + 72);
            LOWORD(v25) = 0;
            LOWORD(v21) = 0;
            FormatRRASErrorString(
              &v25,
              L"AddInterfaceToAllProtocols: Error %d adding %ws to %ws",
              v16,
              v17,
              *(_QWORD *)(i + 32));
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v18 = &v20;
              if ( a1 != -688 )
                LODWORD(v18) = a1 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrMgrParamTraceError,
                (unsigned int)&v25,
                (_DWORD)v18,
                *(_QWORD *)(a1 + 72),
                (__int64)&v21);
            }
          }
        }
      }
    }
    RtlReleaseResource(&stru_18008C4A0);
  }
  else if ( v4 < 0 )
  {
    v6 = *(_QWORD *)(a1 + 72);
    LOWORD(v25) = 0;
    LOWORD(v21) = 0;
    FormatRRASErrorString(
      &v25,
      L"AddInterfaceToAllProtocols: No interface info for %ws. Not adding to any protocols",
      v6);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v7 = &v20;
      if ( a1 != -688 )
        LODWORD(v7) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v25,
        (_DWORD)v7,
        *(_QWORD *)(a1 + 72),
        (__int64)&v21);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180014e28  mov     [rsp+arg_10], rbx
0x180014e2d  mov     [rsp+arg_18], rsi
0x180014e32  push    rdi
0x180014e33  push    r12
0x180014e35  push    r13
0x180014e37  push    r14
0x180014e39  push    r15
0x180014e3b  sub     rsp, 880h
0x180014e42  mov     rax, cs:__security_cookie
0x180014e49  xor     rax, rsp
0x180014e4c  mov     [rsp+8A8h+var_38], rax
0x180014e54  mov     rsi, rdx
0x180014e57  mov     rdi, rcx
0x180014e5a  xor     eax, eax
0x180014e5c  lea     rcx, [rsp+8A8h+var_834]; void *
0x180014e61  xor     edx, edx; Val
0x180014e63  mov     [rsp+8A8h+var_838], eax
0x180014e67  mov     r8d, 7FCh; Size
0x180014e6d  call    memset_0
0x180014e72  xor     eax, eax
0x180014e74  xorps   xmm0, xmm0
0x180014e77  mov     [rsp+8A8h+var_860], eax
0x180014e7b  mov     [rsp+8A8h+var_83C], eax
0x180014e7f  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180014e86  movups  [rsp+8A8h+var_85C], xmm0
0x180014e8b  movups  [rsp+8A8h+var_84C], xmm0
0x180014e90  movups  [rsp+8A8h+var_870], xmm0
0x180014e95  test    al, 80h
0x180014e97  jz      short loc_180014EE7
0x180014e99  xor     eax, eax
0x180014e9b  lea     r9, [rsp+8A8h+var_870]
0x180014ea0  mov     word ptr [rsp+8A8h+var_860], ax
0x180014ea5  lea     r8, aEnteredAddinte; "Entered: AddInterfaceToAllProtocols"
0x180014eac  lea     rax, [rdi+2B0h]
0x180014eb3  test    rax, rax
0x180014eb6  lea     rdx, RasRtrmgrParamTraceInfo
0x180014ebd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014ec4  cmovnz  r9, rax
0x180014ec8  lea     rax, [rsp+8A8h+var_860]
0x180014ecd  mov     [rsp+8A8h+var_880], rax
0x180014ed2  mov     rax, [rdi+48h]
0x180014ed6  mov     [rsp+8A8h+var_888], rax
0x180014edb  call    McTemplateU0zjzz_EventWriteTransfer
0x180014ee0  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180014ee7  test    rsi, rsi
0x180014eea  jnz     short loc_180014F65
0x180014eec  test    al, al
0x180014eee  jns     loc_180015092
0x180014ef4  mov     r8, [rdi+48h]
0x180014ef8  lea     rdx, aAddinterfaceto_5; "AddInterfaceToAllProtocols: No interfac"...
0x180014eff  xor     eax, eax
0x180014f01  lea     rcx, [rsp+8A8h+var_838]
0x180014f06  mov     word ptr [rsp+8A8h+var_838], ax
0x180014f0b  mov     word ptr [rsp+8A8h+var_860], ax
0x180014f10  call    FormatRRASErrorString
0x180014f15  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180014f1c  jge     loc_180015092
0x180014f22  lea     rax, [rdi+2B0h]
0x180014f29  test    rax, rax
0x180014f2c  lea     r9, [rsp+8A8h+var_870]
0x180014f31  lea     r8, [rsp+8A8h+var_838]
0x180014f36  cmovnz  r9, rax
0x180014f3a  lea     rdx, RasRtrmgrParamTraceInfo
0x180014f41  lea     rax, [rsp+8A8h+var_860]
0x180014f46  mov     [rsp+8A8h+var_880], rax
0x180014f4b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014f52  mov     rax, [rdi+48h]
0x180014f56  mov     [rsp+8A8h+var_888], rax
0x180014f5b  call    McTemplateU0zjzz_EventWriteTransfer
0x180014f60  jmp     loc_180015092
0x180014f65  xor     r15d, r15d
0x180014f68  lea     rax, g_leProtoCbListV6
0x180014f6f  xor     r12d, r12d
0x180014f72  lea     r14, g_leProtoCbListV4
0x180014f79  xor     r13d, r13d
0x180014f7c  lea     rcx, stru_18008C4A0; Resource
0x180014f83  cmp     dword ptr [rdi+204h], 1
0x180014f8a  mov     dl, 1; Wait
0x180014f8c  cmovnz  r14, rax
0x180014f90  call    cs:__imp_RtlAcquireResourceShared
0x180014f96  mov     rbx, [r14]
0x180014f99  cmp     rbx, r14
0x180014f9c  jz      loc_180015085
0x180014fa2  mov     ecx, [rbx+3Ch]
0x180014fa5  mov     rdx, rsi
0x180014fa8  call    GetPointerToTocEntry
0x180014fad  xor     r8d, r8d
0x180014fb0  test    rax, rax
0x180014fb3  jz      short loc_180014FD5
0x180014fb5  cmp     [rax+4], r8d
0x180014fb9  jbe     short loc_180014FD5
0x180014fbb  mov     ecx, [rax+0Ch]
0x180014fbe  cmp     ecx, [rsi+4]
0x180014fc1  jnb     short loc_180014FC7
0x180014fc3  lea     r8, [rsi+rcx]
0x180014fc7  mov     r12d, [rax+4]
0x180014fcb  mov     r15d, 500h
0x180014fd1  mov     r13d, [rax+8]
0x180014fd5  test    byte ptr [rbx+40h], 10h
0x180014fd9  jnz     short loc_180014FE4
0x180014fdb  test    r8, r8
0x180014fde  jz      loc_18001507D
0x180014fe4  mov     dword ptr [rsp+8A8h+var_880], r13d
0x180014fe9  mov     r9d, r15d
0x180014fec  mov     rdx, rbx
0x180014fef  mov     dword ptr [rsp+8A8h+var_888], r12d
0x180014ff4  mov     rcx, rdi
0x180014ff7  call    AddInterfaceToProtocol
0x180014ffc  test    eax, eax
0x180014ffe  jz      short loc_18001507D
0x180015000  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180015007  jz      short loc_18001507D
0x180015009  mov     r9, [rdi+48h]
0x18001500d  lea     rdx, aAddinterfaceto_10; "AddInterfaceToAllProtocols: Error %d ad"...
0x180015014  xor     ecx, ecx
0x180015016  mov     r8d, eax
0x180015019  mov     word ptr [rsp+8A8h+var_838], cx
0x18001501e  mov     word ptr [rsp+8A8h+var_860], cx
0x180015023  mov     rcx, [rbx+20h]
0x180015027  mov     [rsp+8A8h+var_888], rcx
0x18001502c  lea     rcx, [rsp+8A8h+var_838]
0x180015031  call    FormatRRASErrorString
0x180015036  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001503d  jz      short loc_18001507D
0x18001503f  lea     rax, [rdi+2B0h]
0x180015046  test    rax, rax
0x180015049  lea     r9, [rsp+8A8h+var_870]
0x18001504e  lea     r8, [rsp+8A8h+var_838]
0x180015053  cmovnz  r9, rax
0x180015057  lea     rdx, RasRtrMgrParamTraceError
0x18001505e  lea     rax, [rsp+8A8h+var_860]
0x180015063  mov     [rsp+8A8h+var_880], rax
0x180015068  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001506f  mov     rax, [rdi+48h]
0x180015073  mov     [rsp+8A8h+var_888], rax
0x180015078  call    McTemplateU0zjzz_EventWriteTransfer
0x18001507d  mov     rbx, [rbx]
0x180015080  jmp     loc_180014F99
0x180015085  lea     rcx, stru_18008C4A0; Resource
0x18001508c  call    cs:__imp_RtlReleaseResource
0x180015092  xor     eax, eax
0x180015094  mov     rcx, [rsp+8A8h+var_38]
0x18001509c  xor     rcx, rsp; StackCookie
0x18001509f  call    __security_check_cookie
0x1800150a4  lea     r11, [rsp+8A8h+var_28]
0x1800150ac  mov     rbx, [r11+40h]
0x1800150b0  mov     rsi, [r11+48h]
0x1800150b4  mov     rsp, r11
0x1800150b7  pop     r15
0x1800150b9  pop     r14
0x1800150bb  pop     r13
0x1800150bd  pop     r12
0x1800150bf  pop     rdi
0x1800150c0  retn
```
