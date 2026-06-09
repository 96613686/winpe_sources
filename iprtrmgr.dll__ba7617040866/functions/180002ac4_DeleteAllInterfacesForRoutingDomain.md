# DeleteAllInterfacesForRoutingDomain

- ea: `0x180002ac4`
- end: `0x180002eb0`
- name: `DeleteAllInterfacesForRoutingDomain`
- size: `1004`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025eac`

## callees

- `0x180002ac4`
- `0x180002eb8`
- `0x18000ac60`
- `0x180011790`
- `0x180016734`
- `0x180057d48`
- `0x180057dd0`
- `0x180057f48`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180002c23`
- `ntdll!RtlAcquireResourceExclusive` at `0x180002c23`
- `ntdll!RtlReleaseResource` at `0x180002d04`
- `ntdll!RtlReleaseResource` at `0x180002de7`
- `ntdll!RtlReleaseResource` at `0x180002d04`
- `ntdll!RtlReleaseResource` at `0x180002de7`
- `KERNEL32!Sleep` at `0x180002d72`
- `KERNEL32!Sleep` at `0x180002d72`
- `KERNEL32!HeapFree` at `0x180002e32`
- `KERNEL32!HeapFree` at `0x180002e32`

## string_xrefs

- `0x180002b7a`: `DeleteAllInterfacesForRoutingDomain`
- `0x180002e4a`: `DeleteAllInterfacesForRoutingDomain`
- `0x180002bbb`: `DeleteAllInterfacesForRoutingDomain for routing domain (%ws) for Tranport %d`
- `0x180002d1c`: `DeleteAllInterfacesForRoutingDomain: Interface(s) pending disconnect for routing domain(%ws). Sleeping..`
- `0x180002d8f`: `DeleteAllInterfacesForRoutingDomain: No Interface pending disconnect for routing domain(%ws). Exiting`

## pseudocode

```c
LPVOID *__fastcall DeleteAllInterfacesForRoutingDomain(struct _GUID *a1, unsigned int a2)
{
  int v4; // r12d
  __int64 v5; // rdx
  __int128 *v6; // r9
  __int128 *v7; // r9
  __int64 *v8; // rbx
  __int64 v9; // rax
  int v10; // eax
  __int64 *v11; // r14
  LPVOID ***v12; // r11
  LPVOID **v13; // rax
  __int128 *v14; // r9
  __int128 *v15; // r9
  void *v16; // rbx
  LPVOID *result; // rax
  __int64 v18; // rax
  LPVOID lpMem[3]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v20; // [rsp+48h] [rbp-B8h] BYREF
  int v21; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v22; // [rsp+5Ch] [rbp-A4h]
  __int128 v23; // [rsp+6Ch] [rbp-94h]
  int v24; // [rsp+7Ch] [rbp-84h]
  _BYTE v25[80]; // [rsp+80h] [rbp-80h] BYREF
  int v26; // [rsp+D0h] [rbp-30h] BYREF
  char v27[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v4 = a2 == 33;
  memset_0(v25, 0, sizeof(v25));
  v26 = 0;
  *(_OWORD *)lpMem = 0;
  memset_0(v27, 0, sizeof(v27));
  v21 = 0;
  v22 = 0;
  v24 = 0;
  v23 = 0;
  v20 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v21) = 0;
    v6 = &v20;
    if ( a1 )
      LODWORD(v6) = (_DWORD)a1;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"DeleteAllInterfacesForRoutingDomain",
      (_DWORD)v6,
      0,
      (__int64)&v21);
  }
  MprConvertGuidToString(a1, v5, v25);
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v26) = 0;
    LOWORD(v21) = 0;
    FormatRRASErrorString(
      &v26,
      L"DeleteAllInterfacesForRoutingDomain for routing domain (%ws) for Tranport %d",
      v25,
      a2);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v7 = &v20;
      if ( a1 )
        LODWORD(v7) = (_DWORD)a1;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v26,
        (_DWORD)v7,
        0,
        (__int64)&v21);
    }
  }
  lpMem[1] = lpMem;
  lpMem[0] = lpMem;
LABEL_11:
  RtlAcquireResourceExclusive(&Resource, 1u);
  v8 = (__int64 *)::lpMem;
  while ( v8 != &ICBList )
  {
    if ( *((_DWORD *)v8 + 129) != v4 )
      goto LABEL_25;
    v9 = v8[86] - *(_QWORD *)&a1->Data1;
    if ( !v9 )
      v9 = v8[87] - *(_QWORD *)a1->Data4;
    if ( v9 )
    {
LABEL_25:
      v8 = (__int64 *)v8[1];
    }
    else
    {
      if ( *((_DWORD *)v8 + 42) == 4 && (unsigned int)(*((_DWORD *)v8 + 36) - 1) <= 1 )
      {
        RtlReleaseResource(&Resource);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v26) = 0;
          LOWORD(v21) = 0;
          FormatRRASErrorString(
            &v26,
            L"DeleteAllInterfacesForRoutingDomain: Interface(s) pending disconnect for routing domain(%ws). Sleeping..",
            v25);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v14 = &v20;
            if ( a1 )
              LODWORD(v14) = (_DWORD)a1;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v26,
              (_DWORD)v14,
              0,
              (__int64)&v21);
          }
        }
        Sleep(0x1F4u);
        goto LABEL_11;
      }
      v10 = *((_DWORD *)v8 + 36);
      v11 = (__int64 *)v8[1];
      if ( v10 == 5 )
      {
        SetLoopbackInterfaceForRoutingDomain(a1, a2, 0);
      }
      else if ( v10 == 4 )
      {
        SetInternalInterfaceForRoutingDomain(a1, a2, 0);
      }
      RemoveInterfaceFromLists(v8);
      v12 = (LPVOID ***)lpMem[1];
      if ( *(LPVOID **)lpMem[1] != lpMem )
LABEL_42:
        __fastfail(3u);
      v13 = (LPVOID **)v8;
      v8[1] = (__int64)lpMem[1];
      v8 = v11;
      *v13 = lpMem;
      *v12 = v13;
      lpMem[1] = v13;
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v26) = 0;
    LOWORD(v21) = 0;
    FormatRRASErrorString(
      &v26,
      L"DeleteAllInterfacesForRoutingDomain: No Interface pending disconnect for routing domain(%ws). Exiting",
      v25);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v15 = &v20;
      if ( a1 )
        LODWORD(v15) = (_DWORD)a1;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v26,
        (_DWORD)v15,
        0,
        (__int64)&v21);
    }
  }
  RtlReleaseResource(&Resource);
  while ( 1 )
  {
    v16 = lpMem[0];
    result = lpMem;
    if ( lpMem[0] == lpMem )
      break;
    if ( *((LPVOID **)lpMem[0] + 1) != lpMem )
      goto LABEL_42;
    v18 = *(_QWORD *)lpMem[0];
    if ( *(LPVOID *)(*(_QWORD *)lpMem[0] + 8LL) != lpMem[0] )
      goto LABEL_42;
    lpMem[0] = *(LPVOID *)lpMem[0];
    *(_QWORD *)(v18 + 8) = lpMem;
    DeleteSingleInterface((__int64)v16);
    HeapFree(IPRouterHeap, 0, v16);
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v26) = 0;
    result = (LPVOID *)FormatRRASErrorString(&v26, L"Leaving: %ws", L"DeleteAllInterfacesForRoutingDomain");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      return (LPVOID *)McTemplateU0z_EventWriteTransfer(
                         &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                         RasRtrmgrTraceInfo,
                         &v26);
  }
  return result;
}

```

## disassembly

```asm
0x180002ac4  mov     [rsp-8+arg_10], rbx
0x180002ac9  push    rbp
0x180002aca  push    rsi
0x180002acb  push    rdi
0x180002acc  push    r12
0x180002ace  push    r13
0x180002ad0  push    r14
0x180002ad2  push    r15
0x180002ad4  lea     rbp, [rsp-7E0h]
0x180002adc  sub     rsp, 8E0h
0x180002ae3  mov     rax, cs:__security_cookie
0x180002aea  xor     rax, rsp
0x180002aed  mov     [rbp+810h+var_40], rax
0x180002af4  xor     r13d, r13d
0x180002af7  mov     r15d, edx
0x180002afa  cmp     edx, 21h ; '!'
0x180002afd  mov     rdi, rcx
0x180002b00  mov     r12d, r13d
0x180002b03  lea     rcx, [rbp+810h+var_890]; void *
0x180002b07  setz    r12b
0x180002b0b  xor     edx, edx; Val
0x180002b0d  lea     r8d, [r13+50h]; Size
0x180002b11  call    memset_0
0x180002b16  xorps   xmm0, xmm0
0x180002b19  mov     [rbp+810h+var_840], r13d
0x180002b1d  xor     edx, edx; Val
0x180002b1f  lea     rcx, [rbp+810h+var_83C]; void *
0x180002b23  mov     r8d, 7FCh; Size
0x180002b29  movups  xmmword ptr [rsp+910h+lpMem], xmm0
0x180002b2e  call    memset_0
0x180002b33  xorps   xmm0, xmm0
0x180002b36  mov     [rsp+910h+var_8B8], r13d
0x180002b3b  xor     eax, eax
0x180002b3d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180002b44  movups  [rsp+910h+var_8B4], xmm0
0x180002b49  mov     [rsp+910h+var_894], eax
0x180002b4d  movups  [rsp+910h+var_8A4], xmm0
0x180002b52  movups  [rsp+910h+var_8C8], xmm0
0x180002b57  jz      short loc_180002B94
0x180002b59  test    rdi, rdi
0x180002b5c  mov     word ptr [rsp+910h+var_8B8], r13w
0x180002b62  lea     rax, [rsp+910h+var_8B8]
0x180002b67  mov     [rsp+910h+var_8E8], rax
0x180002b6c  lea     r9, [rsp+910h+var_8C8]
0x180002b71  cmovnz  r9, rdi
0x180002b75  mov     [rsp+910h+var_8F0], r13
0x180002b7a  lea     r8, aDeleteallinter_1; "DeleteAllInterfacesForRoutingDomain"
0x180002b81  lea     rdx, RasRtrmgrParamTraceInfo
0x180002b88  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002b8f  call    McTemplateU0zjzz_EventWriteTransfer
0x180002b94  lea     r8, [rbp+810h+var_890]
0x180002b98  mov     rcx, rdi
0x180002b9b  call    MprConvertGuidToString
0x180002ba0  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180002ba7  jge     short loc_180002C06
0x180002ba9  mov     r9d, r15d
0x180002bac  mov     word ptr [rbp+810h+var_840], r13w
0x180002bb1  lea     r8, [rbp+810h+var_890]
0x180002bb5  mov     word ptr [rsp+910h+var_8B8], r13w
0x180002bbb  lea     rdx, aDeleteallinter_3; "DeleteAllInterfacesForRoutingDomain for"...
0x180002bc2  lea     rcx, [rbp+810h+var_840]
0x180002bc6  call    FormatRRASErrorString
0x180002bcb  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180002bd2  jge     short loc_180002C06
0x180002bd4  test    rdi, rdi
0x180002bd7  lea     rax, [rsp+910h+var_8B8]
0x180002bdc  mov     [rsp+910h+var_8E8], rax
0x180002be1  lea     r9, [rsp+910h+var_8C8]
0x180002be6  cmovnz  r9, rdi
0x180002bea  mov     [rsp+910h+var_8F0], r13
0x180002bef  lea     r8, [rbp+810h+var_840]
0x180002bf3  lea     rdx, RasRtrmgrParamTraceInfo
0x180002bfa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002c01  call    McTemplateU0zjzz_EventWriteTransfer
0x180002c06  lea     rax, [rsp+910h+lpMem]
0x180002c0b  mov     [rsp+910h+lpMem+8], rax
0x180002c10  lea     rax, [rsp+910h+lpMem]
0x180002c15  mov     [rsp+910h+lpMem], rax
0x180002c1a  mov     dl, 1; Wait
0x180002c1c  lea     rcx, Resource; Resource
0x180002c23  call    cs:__imp_RtlAcquireResourceExclusive
0x180002c29  mov     rbx, cs:lpMem
0x180002c30  lea     rax, ICBList
0x180002c37  cmp     rbx, rax
0x180002c3a  jz      loc_180002D7D
0x180002c40  cmp     [rbx+204h], r12d
0x180002c47  jnz     loc_180002CF4
0x180002c4d  mov     rax, [rbx+2B0h]
0x180002c54  sub     rax, [rdi]
0x180002c57  jnz     short loc_180002C64
0x180002c59  mov     rax, [rbx+2B8h]
0x180002c60  sub     rax, [rdi+8]
0x180002c64  test    rax, rax
0x180002c67  jnz     loc_180002CF4
0x180002c6d  cmp     dword ptr [rbx+0A8h], 4
0x180002c74  jnz     short loc_180002C83
0x180002c76  mov     eax, [rbx+90h]
0x180002c7c  dec     eax
0x180002c7e  cmp     eax, 1
0x180002c81  jbe     short loc_180002CFD
0x180002c83  mov     eax, [rbx+90h]
0x180002c89  lea     rsi, [rbx+8]
0x180002c8d  mov     r14, [rsi]
0x180002c90  cmp     eax, 5
0x180002c93  jnz     short loc_180002CA5
0x180002c95  xor     r8d, r8d; struct _ICB *
0x180002c98  mov     edx, r15d; unsigned int
0x180002c9b  mov     rcx, rdi; struct _GUID *
0x180002c9e  call    SetLoopbackInterfaceForRoutingDomain
0x180002ca3  jmp     short loc_180002CB8
0x180002ca5  cmp     eax, 4
0x180002ca8  jnz     short loc_180002CB8
0x180002caa  xor     r8d, r8d; struct _ICB *
0x180002cad  mov     edx, r15d; unsigned int
0x180002cb0  mov     rcx, rdi; struct _GUID *
0x180002cb3  call    SetInternalInterfaceForRoutingDomain
0x180002cb8  mov     rcx, rbx
0x180002cbb  call    RemoveInterfaceFromLists
0x180002cc0  mov     r11, [rsp+910h+lpMem+8]
0x180002cc5  lea     rax, [rsp+910h+lpMem]
0x180002cca  cmp     [r11], rax
0x180002ccd  jnz     loc_180002E3A
0x180002cd3  mov     rax, rbx
0x180002cd6  mov     [rsi], r11
0x180002cd9  lea     rdx, [rsp+910h+lpMem]
0x180002cde  mov     rcx, rbx
0x180002ce1  mov     rbx, r14
0x180002ce4  mov     [rax], rdx
0x180002ce7  mov     [r11], rax
0x180002cea  mov     [rsp+910h+lpMem+8], rax
0x180002cef  jmp     loc_180002C30
0x180002cf4  mov     rbx, [rbx+8]
0x180002cf8  jmp     loc_180002C30
0x180002cfd  lea     rcx, Resource; Resource
0x180002d04  call    cs:__imp_RtlReleaseResource
0x180002d0a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180002d11  jge     short loc_180002D6D
0x180002d13  lea     r8, [rbp+810h+var_890]
0x180002d17  mov     word ptr [rbp+810h+var_840], r13w
0x180002d1c  lea     rdx, aDeleteallinter_0; "DeleteAllInterfacesForRoutingDomain: In"...
0x180002d23  mov     word ptr [rsp+910h+var_8B8], r13w
0x180002d29  lea     rcx, [rbp+810h+var_840]
0x180002d2d  call    FormatRRASErrorString
0x180002d32  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180002d39  jge     short loc_180002D6D
0x180002d3b  test    rdi, rdi
0x180002d3e  lea     rax, [rsp+910h+var_8B8]
0x180002d43  mov     [rsp+910h+var_8E8], rax
0x180002d48  lea     r9, [rsp+910h+var_8C8]
0x180002d4d  cmovnz  r9, rdi
0x180002d51  mov     [rsp+910h+var_8F0], r13
0x180002d56  lea     r8, [rbp+810h+var_840]
0x180002d5a  lea     rdx, RasRtrmgrParamTraceInfo
0x180002d61  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002d68  call    McTemplateU0zjzz_EventWriteTransfer
0x180002d6d  mov     ecx, 1F4h; dwMilliseconds
0x180002d72  call    cs:__imp_Sleep
0x180002d78  jmp     loc_180002C1A
0x180002d7d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180002d84  jge     short loc_180002DE0
0x180002d86  lea     r8, [rbp+810h+var_890]
0x180002d8a  mov     word ptr [rbp+810h+var_840], r13w
0x180002d8f  lea     rdx, aDeleteallinter; "DeleteAllInterfacesForRoutingDomain: No"...
0x180002d96  mov     word ptr [rsp+910h+var_8B8], r13w
0x180002d9c  lea     rcx, [rbp+810h+var_840]
0x180002da0  call    FormatRRASErrorString
0x180002da5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180002dac  jge     short loc_180002DE0
0x180002dae  test    rdi, rdi
0x180002db1  lea     rax, [rsp+910h+var_8B8]
0x180002db6  mov     [rsp+910h+var_8E8], rax
0x180002dbb  lea     r9, [rsp+910h+var_8C8]
0x180002dc0  cmovnz  r9, rdi
0x180002dc4  mov     [rsp+910h+var_8F0], r13
0x180002dc9  lea     r8, [rbp+810h+var_840]
0x180002dcd  lea     rdx, RasRtrmgrParamTraceInfo
0x180002dd4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002ddb  call    McTemplateU0zjzz_EventWriteTransfer
0x180002de0  lea     rcx, Resource; Resource
0x180002de7  call    cs:__imp_RtlReleaseResource
0x180002ded  mov     rbx, [rsp+910h+lpMem]
0x180002df2  lea     rax, [rsp+910h+lpMem]
0x180002df7  cmp     rbx, rax
0x180002dfa  jz      short loc_180002E41
0x180002dfc  lea     rax, [rsp+910h+lpMem]
0x180002e01  cmp     [rbx+8], rax
0x180002e05  jnz     short loc_180002E3A
0x180002e07  mov     rax, [rbx]
0x180002e0a  cmp     [rax+8], rbx
0x180002e0e  jnz     short loc_180002E3A
0x180002e10  lea     rcx, [rsp+910h+lpMem]
0x180002e15  mov     [rsp+910h+lpMem], rax
0x180002e1a  mov     [rax+8], rcx
0x180002e1e  mov     rcx, rbx
0x180002e21  call    DeleteSingleInterface
0x180002e26  mov     rcx, cs:IPRouterHeap; hHeap
0x180002e2d  mov     r8, rbx; lpMem
0x180002e30  xor     edx, edx; dwFlags
0x180002e32  call    cs:__imp_HeapFree
0x180002e38  jmp     short loc_180002DED
0x180002e3a  mov     ecx, 3
0x180002e3f  int     29h; Win8: RtlFailFast(ecx)
0x180002e41  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180002e48  jge     short loc_180002E86
0x180002e4a  lea     r8, aDeleteallinter_1; "DeleteAllInterfacesForRoutingDomain"
0x180002e51  mov     word ptr [rbp+810h+var_840], r13w
0x180002e56  lea     rdx, aLeavingWs; "Leaving: %ws"
0x180002e5d  lea     rcx, [rbp+810h+var_840]
0x180002e61  call    FormatRRASErrorString
0x180002e66  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r13b
0x180002e6d  jge     short loc_180002E86
0x180002e6f  lea     r8, [rbp+810h+var_840]
0x180002e73  lea     rdx, RasRtrmgrTraceInfo
0x180002e7a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002e81  call    McTemplateU0z_EventWriteTransfer
0x180002e86  mov     rcx, [rbp+810h+var_40]
0x180002e8d  xor     rcx, rsp; StackCookie
0x180002e90  call    __security_check_cookie
0x180002e95  mov     rbx, [rsp+910h+arg_10]
0x180002e9d  add     rsp, 8E0h
0x180002ea4  pop     r15
0x180002ea6  pop     r14
0x180002ea8  pop     r13
0x180002eaa  pop     r12
0x180002eac  pop     rdi
0x180002ead  pop     rsi
0x180002eae  pop     rbp
0x180002eaf  retn
```
