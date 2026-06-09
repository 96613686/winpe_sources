# DdmModernDevice::ProcessDialedoutProtocolStopped(_PROTOCOL_RESULT *)

- ea: `0x1800425f0`
- end: `0x1800427d3`
- name: `?ProcessDialedoutProtocolStopped@DdmModernDevice@@UEAAKPEAU_PROTOCOL_RESULT@@@Z`
- size: `483`
- prototype: `unsigned int __fastcall(DdmModernDevice *__hidden this, struct _PROTOCOL_RESULT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x1800425f0`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180042686`
- `msvcrt!_itow_s` at `0x180042728`
- `msvcrt!_itow_s` at `0x180042686`
- `msvcrt!_itow_s` at `0x180042728`

## string_xrefs

- `0x18004268f`: `DdmModernDevice::ProcessDialedoutProtocolStopped`
- `0x180042696`: `%s: Protocol engine stopped for dialed out S2S connection (hport: %ld)`
- `0x180042732`: `PROTOCOL_RES_Stopped. dwError=0x%x. Dicconnecting...`

## pseudocode

```c
__int64 __fastcall DdmModernDevice::ProcessDialedoutProtocolStopped(DdmModernDevice *this, struct _PROTOCOL_RESULT *a2)
{
  int *v4; // rdi
  bool v5; // zf
  int v6; // ecx
  unsigned int v7; // eax
  unsigned int v8; // ecx
  __int64 result; // rax
  __int128 v10; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Buffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v12; // [rsp+44h] [rbp-BCh]
  __int128 v13; // [rsp+54h] [rbp-ACh]
  int v14; // [rsp+64h] [rbp-9Ch]
  int v15; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v15 = 0;
  memset_0(v16, 0, sizeof(v16));
  *(_DWORD *)Buffer = 0;
  v12 = 0;
  v14 = 0;
  v13 = 0;
  v10 = 0;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v15) = 0;
    v4 = (int *)((char *)this + 96);
    Buffer[0] = 0;
    if ( this && *v4 != -1 )
      _itow_s(*v4, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v15,
      L"%s: Protocol engine stopped for dialed out S2S connection (hport: %ld)",
      L"DdmModernDevice::ProcessDialedoutProtocolStopped",
      *(_QWORD *)v4);
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v15,
        (unsigned int)&v10,
        0,
        (__int64)Buffer);
  }
  *((_DWORD *)this + 2864) |= 0x10u;
  v5 = *((_DWORD *)this + 32) == 4;
  *((_DWORD *)this + 2780) = 8193;
  if ( v5 )
  {
    v7 = (*(__int64 (__fastcall **)(DdmModernDevice *, _QWORD))(*(_QWORD *)this + 160LL))(this, 0);
  }
  else
  {
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v6 = *((_DWORD *)this + 24);
      LOWORD(v15) = 0;
      Buffer[0] = 0;
      if ( v6 != -1 )
        _itow_s(v6, Buffer, 0x14u, 10);
      FormatRRASErrorString(&v15, L"PROTOCOL_RES_Stopped. dwError=0x%x. Dicconnecting...", *((unsigned int *)a2 + 2));
      if ( (byte_1800C8404 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)&v15,
          (unsigned int)&v10,
          0,
          (__int64)Buffer);
    }
    v7 = (*(__int64 (__fastcall **)(DdmModernDevice *))(*(_QWORD *)this + 504LL))(this);
  }
  v8 = v7;
  result = 0;
  if ( v8 != 600 )
    return v8;
  return result;
}

```

## disassembly

```asm
0x1800425f0  mov     [rsp-8+arg_10], rbx
0x1800425f5  push    rbp
0x1800425f6  push    rsi
0x1800425f7  push    rdi
0x1800425f8  lea     rbp, [rsp-780h]
0x180042600  sub     rsp, 880h
0x180042607  mov     rax, cs:__security_cookie
0x18004260e  xor     rax, rsp
0x180042611  mov     [rbp+790h+var_20], rax
0x180042618  mov     rsi, rdx
0x18004261b  mov     rbx, rcx
0x18004261e  xor     eax, eax
0x180042620  lea     rcx, [rsp+890h+var_81C]; void *
0x180042625  xor     edx, edx; Val
0x180042627  mov     [rsp+890h+var_820], eax
0x18004262b  mov     r8d, 7FCh; Size
0x180042631  call    memset_0
0x180042636  xor     eax, eax
0x180042638  xorps   xmm0, xmm0
0x18004263b  test    cs:byte_1800C8404, 10h
0x180042642  mov     dword ptr [rsp+890h+Buffer], eax
0x180042646  movups  [rsp+890h+var_84C], xmm0
0x18004264b  mov     [rsp+890h+var_82C], eax
0x18004264f  movups  [rsp+890h+var_83C], xmm0
0x180042654  movups  [rsp+890h+var_860], xmm0
0x180042659  jz      loc_1800426E0
0x18004265f  mov     word ptr [rsp+890h+var_820], ax
0x180042664  lea     rdi, [rbx+60h]
0x180042668  mov     [rsp+890h+Buffer], ax
0x18004266d  test    rbx, rbx
0x180042670  jz      short loc_18004268C
0x180042672  cmp     dword ptr [rdi], 0FFFFFFFFh
0x180042675  jz      short loc_18004268C
0x180042677  mov     ecx, [rdi]; Value
0x180042679  lea     r9d, [rax+0Ah]; Radix
0x18004267d  lea     r8d, [rax+14h]; BufferCount
0x180042681  lea     rdx, [rsp+890h+Buffer]; Buffer
0x180042686  call    cs:__imp__itow_s
0x18004268c  mov     r9, [rdi]
0x18004268f  lea     r8, aDdmmoderndevic_31; "DdmModernDevice::ProcessDialedoutProtoc"...
0x180042696  lea     rdx, aSProtocolEngin_2; "%s: Protocol engine stopped for dialed "...
0x18004269d  lea     rcx, [rsp+890h+var_820]
0x1800426a2  call    FormatRRASErrorString
0x1800426a7  test    cs:byte_1800C8404, 10h
0x1800426ae  jz      short loc_1800426E0
0x1800426b0  lea     rax, [rsp+890h+Buffer]
0x1800426b5  mov     [rsp+890h+var_868], rax
0x1800426ba  lea     r9, [rsp+890h+var_860]
0x1800426bf  lea     r8, [rsp+890h+var_820]
0x1800426c4  mov     [rsp+890h+var_870], 0
0x1800426cd  lea     rdx, RasDdmParamTraceInfo
0x1800426d4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800426db  call    McTemplateU0zjzz_EventWriteTransfer
0x1800426e0  or      dword ptr [rbx+2CC0h], 10h
0x1800426e7  cmp     dword ptr [rbx+80h], 4
0x1800426ee  mov     dword ptr [rbx+2B70h], 2001h
0x1800426f8  jz      loc_180042790
0x1800426fe  test    cs:byte_1800C8404, 10h
0x180042705  jz      short loc_18004277C
0x180042707  mov     ecx, [rbx+60h]; Value
0x18004270a  xor     eax, eax
0x18004270c  mov     word ptr [rsp+890h+var_820], ax
0x180042711  mov     [rsp+890h+Buffer], ax
0x180042716  cmp     ecx, 0FFFFFFFFh
0x180042719  jz      short loc_18004272E
0x18004271b  lea     r9d, [rax+0Ah]; Radix
0x18004271f  lea     r8d, [rax+14h]; BufferCount
0x180042723  lea     rdx, [rsp+890h+Buffer]; Buffer
0x180042728  call    cs:__imp__itow_s
0x18004272e  mov     r8d, [rsi+8]
0x180042732  lea     rdx, aProtocolResSto; "PROTOCOL_RES_Stopped. dwError=0x%x. Dic"...
0x180042739  lea     rcx, [rsp+890h+var_820]
0x18004273e  call    FormatRRASErrorString
0x180042743  test    cs:byte_1800C8404, 10h
0x18004274a  jz      short loc_18004277C
0x18004274c  lea     rax, [rsp+890h+Buffer]
0x180042751  mov     [rsp+890h+var_868], rax
0x180042756  lea     r9, [rsp+890h+var_860]
0x18004275b  lea     r8, [rsp+890h+var_820]
0x180042760  mov     [rsp+890h+var_870], 0
0x180042769  lea     rdx, RasDdmParamTraceInfo
0x180042770  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180042777  call    McTemplateU0zjzz_EventWriteTransfer
0x18004277c  mov     rax, [rbx]
0x18004277f  mov     rcx, rbx
0x180042782  mov     rax, [rax+1F8h]
0x180042789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004278e  jmp     short loc_1800427A4
0x180042790  mov     rax, [rbx]
0x180042793  xor     edx, edx
0x180042795  mov     rcx, rbx
0x180042798  mov     rax, [rax+0A0h]
0x18004279f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427a4  mov     ecx, eax
0x1800427a6  xor     eax, eax
0x1800427a8  cmp     ecx, 258h
0x1800427ae  cmovnz  eax, ecx
0x1800427b1  mov     rcx, [rbp+790h+var_20]
0x1800427b8  xor     rcx, rsp; StackCookie
0x1800427bb  call    __security_check_cookie
0x1800427c0  mov     rbx, [rsp+890h+arg_10]
0x1800427c8  add     rsp, 880h
0x1800427cf  pop     rdi
0x1800427d0  pop     rsi
0x1800427d1  pop     rbp
0x1800427d2  retn
```
