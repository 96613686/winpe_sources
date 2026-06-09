# ProcessDhcpInform

- ea: `0x180014ff0`
- end: `0x1800151c2`
- name: `ProcessDhcpInform`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x180010cfc`
- `0x180011038`
- `0x180011064`
- `0x180014ff0`
- `0x18002a138`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001517d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015187`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015195`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001517d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015187`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015195`

## string_xrefs

- `0x180015129`: `GetCpIndexFromProtocol(IPCP) failed`

## pseudocode

```c
HLOCAL __fastcall ProcessDhcpInform(__int64 a1)
{
  int v2; // esi
  unsigned int v3; // eax
  __int64 v4; // r8
  const wchar_t *v5; // r8
  __int64 v6; // rcx
  __int64 PCBPointerFromhPort; // rdi
  unsigned int CpIndexFromProtocol; // eax
  __int64 PointerToCPCB; // rcx
  HLOCAL result; // rax
  __int64 v11; // [rsp+28h] [rbp-D8h] BYREF
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[2044]; // [rsp+34h] [rbp-CCh] BYREF

  v11 = 0;
  v12 = 0;
  v2 = 1;
  memset_0(v13, 0, sizeof(v13));
  if ( (byte_18004CF34 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
      L"ProcessDhcpInform");
  v3 = ((__int64 (__fastcall *)(_QWORD, __int64 *))xmmword_18004C480)(*(_QWORD *)(a1 + 24), &v11);
  if ( v3 )
  {
    if ( byte_18004CF33 >= 0 )
      goto LABEL_21;
    v4 = *(_QWORD *)(a1 + 24);
    LOWORD(v12) = 0;
    FormatRRASErrorString(&v12, L"RasBundleGetPort(%d) failed: %d", v4, v3);
    goto LABEL_6;
  }
  PCBPointerFromhPort = GetPCBPointerFromhPort(v11);
  if ( PCBPointerFromhPort )
  {
    CpIndexFromProtocol = GetCpIndexFromProtocol(32801);
    if ( CpIndexFromProtocol == -1 )
    {
      if ( byte_18004CF33 >= 0 )
        goto LABEL_21;
      v5 = L"GetCpIndexFromProtocol(IPCP) failed";
    }
    else
    {
      PointerToCPCB = GetPointerToCPCB(PCBPointerFromhPort, CpIndexFromProtocol);
      if ( PointerToCPCB )
      {
        if ( qword_18004CAA8 && !(unsigned int)qword_18004CAA8(*(_QWORD *)(PointerToCPCB + 16), a1 + 72) )
          v2 = 0;
        goto LABEL_21;
      }
      if ( byte_18004CF33 >= 0 )
        goto LABEL_21;
      v5 = L"GetPointerToCPCB(IPCP) failed";
    }
LABEL_8:
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasPppTraceError,
      v5);
    goto LABEL_21;
  }
  if ( byte_18004CF33 < 0 )
  {
    LOWORD(v12) = 0;
    FormatRRASErrorString(&v12, L"GetPCBPointerFromhPort(%d) failed", v6);
LABEL_6:
    if ( byte_18004CF33 >= 0 )
      goto LABEL_21;
    v5 = (const wchar_t *)&v12;
    goto LABEL_8;
  }
LABEL_21:
  LocalFree(*(HLOCAL *)(a1 + 72));
  result = LocalFree(*(HLOCAL *)(a1 + 112));
  if ( v2 )
    return LocalFree(*(HLOCAL *)(a1 + 88));
  return result;
}

```

## disassembly

```asm
0x180014ff0  mov     [rsp-8+arg_8], rbx
0x180014ff5  mov     [rsp-8+arg_10], rsi
0x180014ffa  push    rbp
0x180014ffb  push    rdi
0x180014ffc  push    r15
0x180014ffe  lea     rbp, [rsp-740h]
0x180015006  sub     rsp, 840h
0x18001500d  mov     rax, cs:__security_cookie
0x180015014  xor     rax, rsp
0x180015017  mov     [rbp+750h+var_20], rax
0x18001501e  mov     rbx, rcx
0x180015021  mov     [rsp+850h+var_828], 0
0x18001502a  xor     eax, eax
0x18001502c  lea     rcx, [rsp+850h+var_81C]; void *
0x180015031  xor     edx, edx; Val
0x180015033  mov     [rsp+850h+var_820], eax
0x180015037  mov     r8d, 7FCh; Size
0x18001503d  mov     esi, 1
0x180015042  call    memset_0
0x180015047  test    cs:byte_18004CF34, sil
0x18001504e  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015055  jz      short loc_18001506D
0x180015057  lea     r8, aProcessdhcpinf; "ProcessDhcpInform"
0x18001505e  mov     rcx, r15
0x180015061  lea     rdx, RasPppTraceInfo
0x180015068  call    McTemplateU0z_EventWriteTransfer
0x18001506d  mov     rcx, [rbx+18h]
0x180015071  lea     rdx, [rsp+850h+var_828]
0x180015076  mov     rax, qword ptr cs:xmmword_18004C480
0x18001507d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015082  test    eax, eax
0x180015084  jz      short loc_1800150D8
0x180015086  cmp     cs:byte_18004CF33, 0
0x18001508d  jge     loc_180015179
0x180015093  mov     r8, [rbx+18h]
0x180015097  lea     rdx, aRasbundlegetpo; "RasBundleGetPort(%d) failed: %d"
0x18001509e  xor     ecx, ecx
0x1800150a0  mov     r9d, eax
0x1800150a3  mov     word ptr [rsp+850h+var_820], cx
0x1800150a8  lea     rcx, [rsp+850h+var_820]
0x1800150ad  call    FormatRRASErrorString
0x1800150b2  cmp     cs:byte_18004CF33, 0
0x1800150b9  jge     loc_180015179
0x1800150bf  lea     r8, [rsp+850h+var_820]
0x1800150c4  lea     rdx, RasPppTraceError
0x1800150cb  mov     rcx, r15
0x1800150ce  call    McTemplateU0z_EventWriteTransfer
0x1800150d3  jmp     loc_180015179
0x1800150d8  mov     rcx, [rsp+850h+var_828]
0x1800150dd  call    GetPCBPointerFromhPort
0x1800150e2  mov     rdi, rax
0x1800150e5  test    rax, rax
0x1800150e8  jnz     short loc_180015111
0x1800150ea  cmp     cs:byte_18004CF33, al
0x1800150f0  jge     loc_180015179
0x1800150f6  mov     r8, rcx
0x1800150f9  mov     word ptr [rsp+850h+var_820], ax
0x1800150fe  lea     rcx, [rsp+850h+var_820]
0x180015103  lea     rdx, aGetpcbpointerf; "GetPCBPointerFromhPort(%d) failed"
0x18001510a  call    FormatRRASErrorString
0x18001510f  jmp     short loc_1800150B2
0x180015111  mov     ecx, 8021h
0x180015116  call    GetCpIndexFromProtocol
0x18001511b  cmp     eax, 0FFFFFFFFh
0x18001511e  jnz     short loc_180015132
0x180015120  test    cs:byte_18004CF33, 80h
0x180015127  jz      short loc_180015179
0x180015129  lea     r8, aGetcpindexfrom; "GetCpIndexFromProtocol(IPCP) failed"
0x180015130  jmp     short loc_1800150C4
0x180015132  mov     edx, eax
0x180015134  mov     rcx, rdi
0x180015137  call    GetPointerToCPCB
0x18001513c  mov     rcx, rax
0x18001513f  test    rax, rax
0x180015142  jnz     short loc_180015159
0x180015144  test    cs:byte_18004CF33, 80h
0x18001514b  jz      short loc_180015179
0x18001514d  lea     r8, aGetpointertocp; "GetPointerToCPCB(IPCP) failed"
0x180015154  jmp     loc_1800150C4
0x180015159  mov     rax, cs:qword_18004CAA8
0x180015160  test    rax, rax
0x180015163  jz      short loc_180015179
0x180015165  mov     rcx, [rcx+10h]
0x180015169  lea     rdx, [rbx+48h]
0x18001516d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015172  xor     edx, edx
0x180015174  test    eax, eax
0x180015176  cmovz   esi, edx
0x180015179  mov     rcx, [rbx+48h]; hMem
0x18001517d  call    cs:__imp_LocalFree
0x180015183  mov     rcx, [rbx+70h]; hMem
0x180015187  call    cs:__imp_LocalFree
0x18001518d  test    esi, esi
0x18001518f  jz      short loc_18001519B
0x180015191  mov     rcx, [rbx+58h]; hMem
0x180015195  call    cs:__imp_LocalFree
0x18001519b  mov     rcx, [rbp+750h+var_20]
0x1800151a2  xor     rcx, rsp; StackCookie
0x1800151a5  call    __security_check_cookie
0x1800151aa  lea     r11, [rsp+850h+var_10]
0x1800151b2  mov     rbx, [r11+28h]
0x1800151b6  mov     rsi, [r11+30h]
0x1800151ba  mov     rsp, r11
0x1800151bd  pop     r15
0x1800151bf  pop     rdi
0x1800151c0  pop     rbp
0x1800151c1  retn
```
