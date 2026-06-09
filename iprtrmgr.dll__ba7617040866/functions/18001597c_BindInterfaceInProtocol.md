# BindInterfaceInProtocol

- ea: `0x18001597c`
- end: `0x180015ba4`
- name: `BindInterfaceInProtocol`
- size: `552`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180015550`
- `0x180027dc0`

## callees

- `0x180011790`
- `0x18001597c`
- `0x18003793c`
- `0x180053214`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`
- `0x180059010`

## import_xrefs

- `rtutils!RouterLogEventExA` at `0x180015ad3`
- `rtutils!RouterLogEventExA` at `0x180015ad3`

## string_xrefs

- `0x180015a21`: `BindInterfaceInProtocol: Err %d activating mcast on %ws`
- `0x180015b1c`: `BindInterfaceInProtocol: Couldnt bind interface %ws to %ws.Error %d`

## pseudocode

```c
__int64 __fastcall BindInterfaceInProtocol(__int64 a1, __int64 a2, __int64 a3)
{
  DWORD v6; // eax
  DWORD v7; // edi
  __int64 v8; // r9
  __int128 *v9; // r9
  int InterfaceFriendlyName; // eax
  const wchar_t *v11; // rcx
  DWORD v12; // eax
  __int64 v13; // r9
  __int64 v14; // r8
  __int128 *v15; // r9
  __int128 v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v19; // [rsp+54h] [rbp-ACh]
  __int128 v20; // [rsp+64h] [rbp-9Ch]
  int v21; // [rsp+74h] [rbp-8Ch]
  int v22; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v23[2044]; // [rsp+84h] [rbp-7Ch] BYREF
  _BYTE v24[528]; // [rsp+880h] [rbp+780h] BYREF

  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v18 = 0;
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v17 = 0;
  if ( !*(_DWORD *)(a1 + 176) && (*(_DWORD *)(a2 + 60) & 0xC0000000) == 0x40000000 )
  {
    v6 = SetMcastOnIf(a1, 1);
    v7 = v6;
    if ( v6 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v8 = *(_QWORD *)(a1 + 72);
        LOWORD(v22) = 0;
        LOWORD(v18) = 0;
        FormatRRASErrorString(&v22, L"BindInterfaceInProtocol: Err %d activating mcast on %ws", v6, v8);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v9 = &v17;
          if ( a1 != -688 )
            LODWORD(v9) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v22,
            (_DWORD)v9,
            *(_QWORD *)(a1 + 72),
            (__int64)&v18);
        }
      }
      InterfaceFriendlyName = GetInterfaceFriendlyName(*(_QWORD *)(a1 + 72), v24);
      v11 = (const wchar_t *)v24;
      if ( InterfaceFriendlyName )
        v11 = *(const wchar_t **)(a1 + 72);
      RouterLogEventExA(g_hLogHandle, 1u, v7, 0x4EBDu, "%S%S", v11, *(const wchar_t **)(a2 + 32));
      return v7;
    }
    *(_DWORD *)(a1 + 176) = 1;
  }
  v12 = (*(__int64 (__fastcall **)(_QWORD, bool, _QWORD, __int64))(a2 + 144))(
          *(unsigned int *)(a1 + 16),
          *(_DWORD *)(a1 + 168) >= 4u,
          0,
          a3);
  v7 = v12;
  if ( v12 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v13 = *(_QWORD *)(a2 + 32);
      v14 = *(_QWORD *)(a1 + 72);
      LOWORD(v22) = 0;
      LOWORD(v18) = 0;
      FormatRRASErrorString(&v22, L"BindInterfaceInProtocol: Couldnt bind interface %ws to %ws.Error %d", v14, v13, v12);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v15 = &v17;
        if ( a1 != -688 )
          LODWORD(v15) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v22,
          (_DWORD)v15,
          *(_QWORD *)(a1 + 72),
          (__int64)&v18);
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18001597c  push    rbp
0x18001597e  push    rbx
0x18001597f  push    rsi
0x180015980  push    rdi
0x180015981  push    r14
0x180015983  lea     rbp, [rsp-9A0h]
0x18001598b  sub     rsp, 0AA0h
0x180015992  mov     rax, cs:__security_cookie
0x180015999  xor     rax, rsp
0x18001599c  mov     [rbp+9C0h+var_30], rax
0x1800159a3  mov     r14, r8
0x1800159a6  mov     rsi, rdx
0x1800159a9  mov     rbx, rcx
0x1800159ac  xor     eax, eax
0x1800159ae  xor     edx, edx; Val
0x1800159b0  mov     [rbp+9C0h+var_A40], eax
0x1800159b3  mov     r8d, 7FCh; Size
0x1800159b9  lea     rcx, [rbp+9C0h+var_A3C]; void *
0x1800159bd  call    memset_0
0x1800159c2  xor     eax, eax
0x1800159c4  xorps   xmm0, xmm0
0x1800159c7  mov     [rsp+0AC0h+var_A70], eax
0x1800159cb  movups  [rsp+0AC0h+var_A6C], xmm0
0x1800159d0  mov     [rsp+0AC0h+var_A4C], eax
0x1800159d4  movups  [rsp+0AC0h+var_A5C], xmm0
0x1800159d9  movups  [rsp+0AC0h+var_A80], xmm0
0x1800159de  cmp     [rbx+0B0h], eax
0x1800159e4  jnz     loc_180015AE8
0x1800159ea  mov     eax, [rsi+3Ch]
0x1800159ed  and     eax, 0C0000000h
0x1800159f2  cmp     eax, 40000000h
0x1800159f7  jnz     loc_180015AE8
0x1800159fd  mov     edx, 1
0x180015a02  mov     rcx, rbx
0x180015a05  call    SetMcastOnIf
0x180015a0a  mov     edi, eax
0x180015a0c  test    eax, eax
0x180015a0e  jz      loc_180015ADE
0x180015a14  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180015a1b  jz      short loc_180015A85
0x180015a1d  mov     r9, [rbx+48h]
0x180015a21  lea     rdx, aBindinterfacei_1; "BindInterfaceInProtocol: Err %d activat"...
0x180015a28  xor     ecx, ecx
0x180015a2a  mov     r8d, eax
0x180015a2d  mov     word ptr [rbp+9C0h+var_A40], cx
0x180015a31  mov     word ptr [rsp+0AC0h+var_A70], cx
0x180015a36  lea     rcx, [rbp+9C0h+var_A40]
0x180015a3a  call    FormatRRASErrorString
0x180015a3f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180015a46  jz      short loc_180015A85
0x180015a48  lea     rax, [rbx+2B0h]
0x180015a4f  test    rax, rax
0x180015a52  lea     r9, [rsp+0AC0h+var_A80]
0x180015a57  lea     r8, [rbp+9C0h+var_A40]
0x180015a5b  cmovnz  r9, rax
0x180015a5f  lea     rdx, RasRtrMgrParamTraceError
0x180015a66  lea     rax, [rsp+0AC0h+var_A70]
0x180015a6b  mov     [rsp+0AC0h+var_A98], rax
0x180015a70  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015a77  mov     rax, [rbx+48h]
0x180015a7b  mov     [rsp+0AC0h+ptszFormat], rax
0x180015a80  call    McTemplateU0zjzz_EventWriteTransfer
0x180015a85  mov     rcx, [rbx+48h]
0x180015a89  lea     rdx, [rbp+9C0h+var_240]
0x180015a90  call    GetInterfaceFriendlyName
0x180015a95  lea     rcx, [rbp+9C0h+var_240]
0x180015a9c  test    eax, eax
0x180015a9e  jz      short loc_180015AA4
0x180015aa0  mov     rcx, [rbx+48h]
0x180015aa4  mov     rax, [rsi+20h]
0x180015aa8  mov     r9d, 4EBDh; dwMessageId
0x180015aae  mov     [rsp+0AC0h+var_A90], rax
0x180015ab3  mov     r8d, edi; dwErrorCode
0x180015ab6  mov     [rsp+0AC0h+var_A98], rcx
0x180015abb  lea     rax, ptszFormat; "%S%S"
0x180015ac2  mov     rcx, cs:g_hLogHandle; hLogHandle
0x180015ac9  mov     edx, 1; dwEventType
0x180015ace  mov     [rsp+0AC0h+ptszFormat], rax; ptszFormat
0x180015ad3  call    cs:__imp_RouterLogEventExA
0x180015ad9  jmp     loc_180015B85
0x180015ade  mov     dword ptr [rbx+0B0h], 1
0x180015ae8  mov     ecx, [rbx+10h]
0x180015aeb  xor     edx, edx
0x180015aed  cmp     dword ptr [rbx+0A8h], 4
0x180015af4  mov     r9, r14
0x180015af7  mov     rax, [rsi+90h]
0x180015afe  setnb   dl
0x180015b01  xor     r8d, r8d
0x180015b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b09  mov     edi, eax
0x180015b0b  test    eax, eax
0x180015b0d  jz      short loc_180015B85
0x180015b0f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180015b16  jz      short loc_180015B85
0x180015b18  mov     r9, [rsi+20h]
0x180015b1c  lea     rdx, aBindinterfacei_2; "BindInterfaceInProtocol: Couldnt bind i"...
0x180015b23  mov     r8, [rbx+48h]
0x180015b27  xor     ecx, ecx
0x180015b29  mov     word ptr [rbp+9C0h+var_A40], cx
0x180015b2d  mov     word ptr [rsp+0AC0h+var_A70], cx
0x180015b32  lea     rcx, [rbp+9C0h+var_A40]
0x180015b36  mov     dword ptr [rsp+0AC0h+ptszFormat], eax
0x180015b3a  call    FormatRRASErrorString
0x180015b3f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180015b46  jz      short loc_180015B85
0x180015b48  lea     rax, [rbx+2B0h]
0x180015b4f  test    rax, rax
0x180015b52  lea     r9, [rsp+0AC0h+var_A80]
0x180015b57  lea     r8, [rbp+9C0h+var_A40]
0x180015b5b  cmovnz  r9, rax
0x180015b5f  lea     rdx, RasRtrMgrParamTraceError
0x180015b66  lea     rax, [rsp+0AC0h+var_A70]
0x180015b6b  mov     [rsp+0AC0h+var_A98], rax
0x180015b70  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015b77  mov     rax, [rbx+48h]
0x180015b7b  mov     [rsp+0AC0h+ptszFormat], rax
0x180015b80  call    McTemplateU0zjzz_EventWriteTransfer
0x180015b85  mov     eax, edi
0x180015b87  mov     rcx, [rbp+9C0h+var_30]
0x180015b8e  xor     rcx, rsp; StackCookie
0x180015b91  call    __security_check_cookie
0x180015b96  add     rsp, 0AA0h
0x180015b9d  pop     r14
0x180015b9f  pop     rdi
0x180015ba0  pop     rsi
0x180015ba1  pop     rbx
0x180015ba2  pop     rbp
0x180015ba3  retn
```
