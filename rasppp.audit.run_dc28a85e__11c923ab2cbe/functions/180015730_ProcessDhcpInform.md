# ProcessDhcpInform

- ea: `0x180015730`
- end: `0x180015915`
- name: `ProcessDhcpInform`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180011230`
- `0x1800115a0`
- `0x1800115d0`
- `0x180015730`
- `0x18002b0dc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800158e1`

## string_xrefs

- `0x180015869`: `GetCpIndexFromProtocol(IPCP) failed`

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
  if ( (byte_18004DF34 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
      L"ProcessDhcpInform");
  v3 = ((__int64 (__fastcall *)(_QWORD, __int64 *))xmmword_18004D480)(*(_QWORD *)(a1 + 24), &v11);
  if ( v3 )
  {
    if ( byte_18004DF33 >= 0 )
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
      if ( byte_18004DF33 >= 0 )
        goto LABEL_21;
      v5 = L"GetCpIndexFromProtocol(IPCP) failed";
    }
    else
    {
      PointerToCPCB = GetPointerToCPCB(PCBPointerFromhPort, CpIndexFromProtocol);
      if ( PointerToCPCB )
      {
        if ( qword_18004DAA8 && !(unsigned int)qword_18004DAA8(*(_QWORD *)(PointerToCPCB + 16), a1 + 72) )
          v2 = 0;
        goto LABEL_21;
      }
      if ( byte_18004DF33 >= 0 )
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
  if ( byte_18004DF33 < 0 )
  {
    LOWORD(v12) = 0;
    FormatRRASErrorString(&v12, L"GetPCBPointerFromhPort(%d) failed", v6);
LABEL_6:
    if ( byte_18004DF33 >= 0 )
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
0x180015730  mov     [rsp-8+arg_8], rbx
0x180015735  mov     [rsp-8+arg_10], rsi
0x18001573a  push    rbp
0x18001573b  push    rdi
0x18001573c  push    r15
0x18001573e  lea     rbp, [rsp-740h]
0x180015746  sub     rsp, 840h
0x18001574d  mov     rax, cs:__security_cookie
0x180015754  xor     rax, rsp
0x180015757  mov     [rbp+750h+var_20], rax
0x18001575e  mov     rbx, rcx
0x180015761  mov     [rsp+850h+var_828], 0
0x18001576a  xor     eax, eax
0x18001576c  lea     rcx, [rsp+850h+var_81C]; void *
0x180015771  xor     edx, edx; Val
0x180015773  mov     [rsp+850h+var_820], eax
0x180015777  mov     r8d, 7FCh; Size
0x18001577d  mov     esi, 1
0x180015782  call    memset_0
0x180015787  test    cs:byte_18004DF34, sil
0x18001578e  lea     r15, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015795  jz      short loc_1800157AD
0x180015797  lea     r8, aProcessdhcpinf; "ProcessDhcpInform"
0x18001579e  mov     rcx, r15
0x1800157a1  lea     rdx, RasPppTraceInfo
0x1800157a8  call    McTemplateU0z_EventWriteTransfer
0x1800157ad  mov     rcx, [rbx+18h]
0x1800157b1  lea     rdx, [rsp+850h+var_828]
0x1800157b6  mov     rax, qword ptr cs:xmmword_18004D480
0x1800157bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157c2  test    eax, eax
0x1800157c4  jz      short loc_180015818
0x1800157c6  cmp     cs:byte_18004DF33, 0
0x1800157cd  jge     loc_1800158B9
0x1800157d3  mov     r8, [rbx+18h]
0x1800157d7  lea     rdx, aRasbundlegetpo; "RasBundleGetPort(%d) failed: %d"
0x1800157de  xor     ecx, ecx
0x1800157e0  mov     r9d, eax
0x1800157e3  mov     word ptr [rsp+850h+var_820], cx
0x1800157e8  lea     rcx, [rsp+850h+var_820]
0x1800157ed  call    FormatRRASErrorString
0x1800157f2  cmp     cs:byte_18004DF33, 0
0x1800157f9  jge     loc_1800158B9
0x1800157ff  lea     r8, [rsp+850h+var_820]
0x180015804  lea     rdx, RasPppTraceError
0x18001580b  mov     rcx, r15
0x18001580e  call    McTemplateU0z_EventWriteTransfer
0x180015813  jmp     loc_1800158B9
0x180015818  mov     rcx, [rsp+850h+var_828]
0x18001581d  call    GetPCBPointerFromhPort
0x180015822  mov     rdi, rax
0x180015825  test    rax, rax
0x180015828  jnz     short loc_180015851
0x18001582a  cmp     cs:byte_18004DF33, al
0x180015830  jge     loc_1800158B9
0x180015836  mov     r8, rcx
0x180015839  mov     word ptr [rsp+850h+var_820], ax
0x18001583e  lea     rcx, [rsp+850h+var_820]
0x180015843  lea     rdx, aGetpcbpointerf; "GetPCBPointerFromhPort(%d) failed"
0x18001584a  call    FormatRRASErrorString
0x18001584f  jmp     short loc_1800157F2
0x180015851  mov     ecx, 8021h
0x180015856  call    GetCpIndexFromProtocol
0x18001585b  cmp     eax, 0FFFFFFFFh
0x18001585e  jnz     short loc_180015872
0x180015860  test    cs:byte_18004DF33, 80h
0x180015867  jz      short loc_1800158B9
0x180015869  lea     r8, aGetcpindexfrom; "GetCpIndexFromProtocol(IPCP) failed"
0x180015870  jmp     short loc_180015804
0x180015872  mov     edx, eax
0x180015874  mov     rcx, rdi
0x180015877  call    GetPointerToCPCB
0x18001587c  mov     rcx, rax
0x18001587f  test    rax, rax
0x180015882  jnz     short loc_180015899
0x180015884  test    cs:byte_18004DF33, 80h
0x18001588b  jz      short loc_1800158B9
0x18001588d  lea     r8, aGetpointertocp; "GetPointerToCPCB(IPCP) failed"
0x180015894  jmp     loc_180015804
0x180015899  mov     rax, cs:qword_18004DAA8
0x1800158a0  test    rax, rax
0x1800158a3  jz      short loc_1800158B9
0x1800158a5  mov     rcx, [rcx+10h]
0x1800158a9  lea     rdx, [rbx+48h]
0x1800158ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158b2  xor     edx, edx
0x1800158b4  test    eax, eax
0x1800158b6  cmovz   esi, edx
0x1800158b9  mov     rcx, [rbx+48h]; hMem
0x1800158bd  call    cs:__imp_LocalFree
0x1800158c4  nop     dword ptr [rax+rax+00h]
0x1800158c9  mov     rcx, [rbx+70h]; hMem
0x1800158cd  call    cs:__imp_LocalFree
0x1800158d4  nop     dword ptr [rax+rax+00h]
0x1800158d9  test    esi, esi
0x1800158db  jz      short loc_1800158ED
0x1800158dd  mov     rcx, [rbx+58h]; hMem
0x1800158e1  call    cs:__imp_LocalFree
0x1800158e8  nop     dword ptr [rax+rax+00h]
0x1800158ed  mov     rcx, [rbp+750h+var_20]
0x1800158f4  xor     rcx, rsp; StackCookie
0x1800158f7  call    __security_check_cookie
0x1800158fc  lea     r11, [rsp+850h+var_10]
0x180015904  mov     rbx, [r11+28h]
0x180015908  mov     rsi, [r11+30h]
0x18001590c  mov     rsp, r11
0x18001590f  pop     r15
0x180015911  pop     rdi
0x180015912  pop     rbp
0x180015913  retn
```
