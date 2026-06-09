# CheckCpsForInactivity

- ea: `0x1800102bc`
- end: `0x180010635`
- name: `CheckCpsForInactivity`
- size: `889`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800181b0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000be68`
- `0x18000deb0`
- `0x18000f780`
- `0x1800102bc`
- `0x18002b0dc`
- `0x180034010`

## import_xrefs

- `rtutils!RouterLogEventA` at `0x1800104d3`
- `rtutils!RouterLogEventA` at `0x1800104d3`
- `rtutils!RouterLogDeregisterA` at `0x1800104eb`
- `rtutils!RouterLogDeregisterA` at `0x1800104eb`
- `rtutils!RouterLogRegisterA` at `0x18001047a`
- `rtutils!RouterLogRegisterA` at `0x18001047a`

## string_xrefs

- `0x180010473`: `RemoteAccess`

## pseudocode

```c
char __fastcall CheckCpsForInactivity(__int64 a1, int a2)
{
  __int64 v4; // r8
  unsigned int v5; // eax
  const wchar_t *v6; // r8
  __int64 v7; // r8
  unsigned int v8; // ecx
  __int64 v9; // r8
  HANDLE v10; // rdi
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // eax
  unsigned int v14; // eax
  unsigned int v16; // [rsp+40h] [rbp-C0h] BYREF
  LPSTR plpszSubStringArray[3]; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[2044]; // [rsp+64h] [rbp-9Ch] BYREF

  v16 = 0;
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  if ( (byte_18004DF34 & 1) != 0 )
  {
    v4 = *(_QWORD *)(a1 + 16);
    LOWORD(v18) = 0;
    FormatRRASErrorString(&v18, L"Time to check Cps for Activity for port %d", v4);
    if ( (byte_18004DF34 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v18);
  }
  v5 = (*((__int64 (__fastcall **)(_QWORD, unsigned int *))&xmmword_18004D420 + 1))(*(_QWORD *)(a1 + 16), &v16);
  if ( v5 )
  {
    if ( byte_18004DF33 < 0 )
    {
      LOWORD(v18) = 0;
      LOBYTE(v5) = FormatRRASErrorString(&v18, L"RasGetTimeSinceLastActivityTime returned %d", v5);
      if ( byte_18004DF33 < 0 )
      {
        v6 = (const wchar_t *)&v18;
LABEL_40:
        LOBYTE(v5) = McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, v6);
        return v5;
      }
    }
    return v5;
  }
  LOBYTE(v5) = byte_18004DF34;
  if ( (byte_18004DF34 & 1) != 0 )
  {
    v7 = *(_QWORD *)(a1 + 16);
    LOWORD(v18) = 0;
    FormatRRASErrorString(&v18, L"Port %d inactive for %d seconds", v7, v16);
    LOBYTE(v5) = byte_18004DF34;
    if ( (byte_18004DF34 & 1) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v18);
      LOBYTE(v5) = byte_18004DF34;
    }
  }
  if ( a2 == 1 )
  {
    v8 = *(_DWORD *)(a1 + 88);
    if ( v16 < v8 )
    {
      LOBYTE(v5) = InsertInTimerQ(*(_DWORD *)(a1 + 64), *(_QWORD *)(a1 + 16), 0, 0, 0, 1, v8 - v16);
      return v5;
    }
    if ( (v5 & 1) != 0 )
    {
      v9 = *(_QWORD *)(a1 + 16);
      LOWORD(v18) = 0;
      FormatRRASErrorString(&v18, L"Disconnecting port %d due to inactivity.", v9);
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v18);
    }
    if ( (*(_BYTE *)(a1 + 56) & 4) == 0 )
    {
      if ( *(_DWORD *)(*(_QWORD *)(a1 + 8) + 1320LL) == 2 )
        v10 = RouterLogRegisterA("RemoteAccess");
      else
        v10 = hLogHandle;
      if ( v10 )
      {
        plpszSubStringArray[0] = (LPSTR)(a1 + 1712);
        plpszSubStringArray[1] = (LPSTR)(a1 + 1665);
        RouterLogEventA(v10, 4u, 0x4F27u, 2u, plpszSubStringArray, 0);
        if ( v10 != hLogHandle )
          RouterLogDeregisterA(v10);
      }
    }
    goto LABEL_23;
  }
  if ( *(_WORD *)(a1 + 60) != 13 || a2 != 7 )
    return v5;
  if ( *(_DWORD *)(a1 + 104) )
  {
    ++*(_DWORD *)(a1 + 108);
    v11 = *(unsigned int *)(a1 + 100);
    if ( *(_DWORD *)(a1 + 108) >= (unsigned int)v11 )
    {
      if ( (byte_18004DF34 & 1) != 0 )
      {
        v12 = *(_QWORD *)(a1 + 16);
        LOWORD(v18) = 0;
        FormatRRASErrorString(
          &v18,
          L"Missed %d consecutive echo responses.  Disconnecting port %d due to no echo responses.",
          v11,
          v12);
        if ( (byte_18004DF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v18);
      }
      *(_QWORD *)(a1 + 104) = 0;
LABEL_23:
      *(_DWORD *)(a1 + 1496) = 926;
      LOBYTE(v5) = FsmClose(a1, 0);
      return v5;
    }
    FsmSendEchoRequest(a1);
    goto LABEL_34;
  }
  v14 = *(_DWORD *)(a1 + 96);
  if ( v16 < v14 )
  {
    v13 = v14 - v16;
    goto LABEL_42;
  }
  v5 = FsmSendEchoRequest(a1);
  if ( v5 )
  {
    *(_DWORD *)(a1 + 104) = 1;
LABEL_34:
    v13 = *(_DWORD *)(a1 + 92);
LABEL_42:
    LOBYTE(v5) = InsertInTimerQ(*(_DWORD *)(a1 + 64), *(_QWORD *)(a1 + 16), 0, 0, 0, 7, v13);
    return v5;
  }
  if ( byte_18004DF33 < 0 )
  {
    v6 = L"Send EchoRequest Failed...";
    goto LABEL_40;
  }
  return v5;
}

```

## disassembly

```asm
0x1800102bc  mov     [rsp-8+arg_8], rbx
0x1800102c1  mov     [rsp-8+arg_10], rdi
0x1800102c6  push    rbp
0x1800102c7  push    r14
0x1800102c9  push    r15
0x1800102cb  lea     rbp, [rsp-770h]
0x1800102d3  sub     rsp, 870h
0x1800102da  mov     rax, cs:__security_cookie
0x1800102e1  xor     rax, rsp
0x1800102e4  mov     [rbp+780h+var_20], rax
0x1800102eb  mov     edi, edx
0x1800102ed  mov     [rsp+880h+var_840], 0
0x1800102f5  mov     rbx, rcx
0x1800102f8  xor     eax, eax
0x1800102fa  xor     edx, edx; Val
0x1800102fc  mov     [rsp+880h+var_820], eax
0x180010300  lea     rcx, [rsp+880h+var_81C]; void *
0x180010305  mov     r8d, 7FCh; Size
0x18001030b  call    memset_0
0x180010310  mov     r14d, 1
0x180010316  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001031d  test    cs:byte_18004DF34, r14b
0x180010324  jz      short loc_18001035F
0x180010326  mov     r8, [rbx+10h]
0x18001032a  lea     rdx, aTimeToCheckCps; "Time to check Cps for Activity for port"...
0x180010331  xor     eax, eax
0x180010333  lea     rcx, [rsp+880h+var_820]
0x180010338  mov     word ptr [rsp+880h+var_820], ax
0x18001033d  call    FormatRRASErrorString
0x180010342  test    cs:byte_18004DF34, r14b
0x180010349  jz      short loc_18001035F
0x18001034b  lea     r8, [rsp+880h+var_820]
0x180010350  mov     rcx, r15
0x180010353  lea     rdx, RasPppTraceInfo
0x18001035a  call    McTemplateU0z_EventWriteTransfer
0x18001035f  mov     rcx, [rbx+10h]
0x180010363  lea     rdx, [rsp+880h+var_840]
0x180010368  mov     rax, qword ptr cs:xmmword_18004D420+8
0x18001036f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010374  test    eax, eax
0x180010376  jz      short loc_1800103B7
0x180010378  cmp     cs:byte_18004DF33, 0
0x18001037f  jge     loc_18001060C
0x180010385  xor     ecx, ecx
0x180010387  lea     rdx, aRasgettimesinc; "RasGetTimeSinceLastActivityTime returne"...
0x18001038e  mov     word ptr [rsp+880h+var_820], cx
0x180010393  mov     r8d, eax
0x180010396  lea     rcx, [rsp+880h+var_820]
0x18001039b  call    FormatRRASErrorString
0x1800103a0  cmp     cs:byte_18004DF33, 0
0x1800103a7  jge     loc_18001060C
0x1800103ad  lea     r8, [rsp+880h+var_820]
0x1800103b2  jmp     loc_1800105D1
0x1800103b7  mov     al, cs:byte_18004DF34
0x1800103bd  test    r14b, al
0x1800103c0  jz      short loc_180010408
0x1800103c2  mov     r9d, [rsp+880h+var_840]
0x1800103c7  lea     rdx, aPortDInactiveF; "Port %d inactive for %d seconds"
0x1800103ce  mov     r8, [rbx+10h]
0x1800103d2  lea     rcx, [rsp+880h+var_820]
0x1800103d7  xor     eax, eax
0x1800103d9  mov     word ptr [rsp+880h+var_820], ax
0x1800103de  call    FormatRRASErrorString
0x1800103e3  mov     al, cs:byte_18004DF34
0x1800103e9  test    r14b, al
0x1800103ec  jz      short loc_180010408
0x1800103ee  lea     r8, [rsp+880h+var_820]
0x1800103f3  mov     rcx, r15
0x1800103f6  lea     rdx, RasPppTraceInfo
0x1800103fd  call    McTemplateU0z_EventWriteTransfer
0x180010402  mov     al, cs:byte_18004DF34
0x180010408  cmp     edi, r14d
0x18001040b  jnz     loc_180010522
0x180010411  mov     ecx, [rbx+58h]
0x180010414  cmp     [rsp+880h+var_840], ecx
0x180010418  jb      loc_180010510
0x18001041e  test    r14b, al
0x180010421  jz      short loc_18001045C
0x180010423  mov     r8, [rbx+10h]
0x180010427  lea     rdx, aDisconnectingP; "Disconnecting port %d due to inactivity"...
0x18001042e  xor     eax, eax
0x180010430  lea     rcx, [rsp+880h+var_820]
0x180010435  mov     word ptr [rsp+880h+var_820], ax
0x18001043a  call    FormatRRASErrorString
0x18001043f  test    cs:byte_18004DF34, r14b
0x180010446  jz      short loc_18001045C
0x180010448  lea     r8, [rsp+880h+var_820]
0x18001044d  mov     rcx, r15
0x180010450  lea     rdx, RasPppTraceInfo
0x180010457  call    McTemplateU0z_EventWriteTransfer
0x18001045c  test    byte ptr [rbx+38h], 4
0x180010460  jnz     loc_1800104F7
0x180010466  mov     rax, [rbx+8]
0x18001046a  cmp     dword ptr [rax+528h], 2
0x180010471  jnz     short loc_18001048B
0x180010473  lea     rcx, szSource; "RemoteAccess"
0x18001047a  call    cs:__imp_RouterLogRegisterA
0x180010481  nop     dword ptr [rax+rax+00h]
0x180010486  mov     rdi, rax
0x180010489  jmp     short loc_180010492
0x18001048b  mov     rdi, cs:hLogHandle
0x180010492  test    rdi, rdi
0x180010495  jz      short loc_1800104F7
0x180010497  lea     rax, [rbx+6B0h]
0x18001049e  mov     [rsp+880h+dwErrorCode], 0; dwErrorCode
0x1800104a6  mov     [rsp+880h+var_838], rax
0x1800104ab  mov     edx, 4; dwEventType
0x1800104b0  lea     rax, [rbx+681h]
0x1800104b7  mov     r8d, 4F27h; dwMessageId
0x1800104bd  mov     [rsp+880h+var_830], rax
0x1800104c2  mov     rcx, rdi; hLogHandle
0x1800104c5  lea     rax, [rsp+880h+var_838]
0x1800104ca  lea     r9d, [rdx-2]; dwSubStringCount
0x1800104ce  mov     [rsp+880h+plpszSubStringArray], rax; plpszSubStringArray
0x1800104d3  call    cs:__imp_RouterLogEventA
0x1800104da  nop     dword ptr [rax+rax+00h]
0x1800104df  cmp     rdi, cs:hLogHandle
0x1800104e6  jz      short loc_1800104F7
0x1800104e8  mov     rcx, rdi; hLogHandle
0x1800104eb  call    cs:__imp_RouterLogDeregisterA
0x1800104f2  nop     dword ptr [rax+rax+00h]
0x1800104f7  xor     edx, edx
0x1800104f9  mov     dword ptr [rbx+5D8h], 39Eh
0x180010503  mov     rcx, rbx
0x180010506  call    FsmClose
0x18001050b  jmp     loc_18001060C
0x180010510  sub     ecx, [rsp+880h+var_840]
0x180010514  mov     [rsp+880h+var_850], ecx
0x180010518  mov     [rsp+880h+dwErrorCode], r14d
0x18001051d  jmp     loc_1800105F2
0x180010522  cmp     word ptr [rbx+3Ch], 0Dh
0x180010527  jnz     loc_18001060C
0x18001052d  cmp     edi, 7
0x180010530  jnz     loc_18001060C
0x180010536  cmp     dword ptr [rbx+68h], 0
0x18001053a  jz      short loc_1800105A6
0x18001053c  add     [rbx+6Ch], r14d
0x180010540  mov     r8d, [rbx+64h]
0x180010544  cmp     [rbx+6Ch], r8d
0x180010548  jb      short loc_180010599
0x18001054a  test    cs:byte_18004DF34, r14b
0x180010551  jz      short loc_18001058C
0x180010553  mov     r9, [rbx+10h]
0x180010557  lea     rdx, aMissedDConsecu; "Missed %d consecutive echo responses.  "...
0x18001055e  xor     eax, eax
0x180010560  lea     rcx, [rsp+880h+var_820]
0x180010565  mov     word ptr [rsp+880h+var_820], ax
0x18001056a  call    FormatRRASErrorString
0x18001056f  test    cs:byte_18004DF34, r14b
0x180010576  jz      short loc_18001058C
0x180010578  lea     r8, [rsp+880h+var_820]
0x18001057d  mov     rcx, r15
0x180010580  lea     rdx, RasPppTraceInfo
0x180010587  call    McTemplateU0z_EventWriteTransfer
0x18001058c  mov     qword ptr [rbx+68h], 0
0x180010594  jmp     loc_1800104F7
0x180010599  mov     rcx, rbx
0x18001059c  call    FsmSendEchoRequest
0x1800105a1  mov     eax, [rbx+5Ch]
0x1800105a4  jmp     short loc_1800105E6
0x1800105a6  mov     eax, [rbx+60h]
0x1800105a9  cmp     [rsp+880h+var_840], eax
0x1800105ad  jb      short loc_1800105E2
0x1800105af  mov     rcx, rbx
0x1800105b2  call    FsmSendEchoRequest
0x1800105b7  test    eax, eax
0x1800105b9  jz      short loc_1800105C1
0x1800105bb  mov     [rbx+68h], r14d
0x1800105bf  jmp     short loc_1800105A1
0x1800105c1  test    cs:byte_18004DF33, 80h
0x1800105c8  jz      short loc_18001060C
0x1800105ca  lea     r8, aSendEchoreques; "Send EchoRequest Failed..."
0x1800105d1  lea     rdx, RasPppTraceError
0x1800105d8  mov     rcx, r15
0x1800105db  call    McTemplateU0z_EventWriteTransfer
0x1800105e0  jmp     short loc_18001060C
0x1800105e2  sub     eax, [rsp+880h+var_840]
0x1800105e6  mov     [rsp+880h+var_850], eax
0x1800105ea  mov     [rsp+880h+dwErrorCode], 7
0x1800105f2  mov     rdx, [rbx+10h]
0x1800105f6  xor     r9d, r9d
0x1800105f9  mov     ecx, [rbx+40h]
0x1800105fc  xor     r8d, r8d
0x1800105ff  mov     dword ptr [rsp+880h+plpszSubStringArray], 0
0x180010607  call    InsertInTimerQ
0x18001060c  mov     rcx, [rbp+780h+var_20]
0x180010613  xor     rcx, rsp; StackCookie
0x180010616  call    __security_check_cookie
0x18001061b  lea     r11, [rsp+880h+var_10]
0x180010623  mov     rbx, [r11+28h]
0x180010627  mov     rdi, [r11+30h]
0x18001062b  mov     rsp, r11
0x18001062e  pop     r15
0x180010630  pop     r14
0x180010632  pop     rbp
0x180010633  retn
```
