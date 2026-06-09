# DdmAnswerIncomingCall(RasObjPtr<DdmDevice> &)

- ea: `0x1800261a4`
- end: `0x1800263be`
- name: `?DdmAnswerIncomingCall@@YAKAEAV?$RasObjPtr@VDdmDevice@@@@@Z`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180046270`

## callees

- `0x180007c50`
- `0x1800261a4`
- `0x180071cec`
- `0x180085818`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `msvcrt!_itow_s` at `0x18002623a`
- `msvcrt!_itow_s` at `0x1800262e1`
- `msvcrt!_itow_s` at `0x180026344`
- `msvcrt!_itow_s` at `0x18002623a`
- `msvcrt!_itow_s` at `0x1800262e1`
- `msvcrt!_itow_s` at `0x180026344`

## string_xrefs

- `0x180026243`: `AnswerIncomingCall for PortId(%d)`
- `0x18002634e`: `AnswerIncomingCall for PortId(%d) passed`

## pseudocode

```c
__int64 __fastcall DdmAnswerIncomingCall(__int64 *a1)
{
  __int64 v1; // rbx
  int v2; // edx
  int v3; // r8d
  int *v4; // rdi
  unsigned int v5; // edi
  int v6; // ecx
  __int64 *v7; // rdx
  int v8; // ecx
  int v10; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v11; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v13; // [rsp+4Ch] [rbp-B4h]
  __int128 v14; // [rsp+5Ch] [rbp-A4h]
  int v15; // [rsp+6Ch] [rbp-94h]
  int v16; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v17[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v1 = *a1;
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  *(_DWORD *)Buffer = 0;
  v13 = 0;
  v15 = 0;
  v14 = 0;
  v10 = 0;
  v11 = 0;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v16) = 0;
    v4 = (int *)(v1 + 96);
    Buffer[0] = 0;
    if ( v1 && *v4 != -1 )
      _itow_s(*v4, Buffer, 0x14u, 10);
    FormatRRASErrorString(&v16, L"AnswerIncomingCall for PortId(%d)", (unsigned int)*v4);
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v16,
        (unsigned int)&v11,
        0,
        (__int64)Buffer);
  }
  v5 = RasLineAnswer(*(_DWORD *)(v1 + 1196), v2, v3, *(_QWORD *)(v1 + 96), (__int64)&v10);
  if ( v5 )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v16) = 0;
      Buffer[0] = 0;
      if ( v1 )
      {
        v6 = *(_DWORD *)(v1 + 96);
        if ( v6 != -1 )
          _itow_s(v6, Buffer, 0x14u, 10);
      }
      FormatRRASErrorString(&v16, L"LineAnswer for PortId(%d) failed with error 0x%x", *(unsigned int *)(v1 + 96), v5);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v7 = RasDdmParamTraceError;
LABEL_20:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (_DWORD)v7,
          (unsigned int)&v16,
          (unsigned int)&v11,
          0,
          (__int64)Buffer);
      }
    }
  }
  else if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v16) = 0;
    Buffer[0] = 0;
    if ( v1 )
    {
      v8 = *(_DWORD *)(v1 + 96);
      if ( v8 != -1 )
        _itow_s(v8, Buffer, 0x14u, 10);
    }
    FormatRRASErrorString(&v16, L"AnswerIncomingCall for PortId(%d) passed", *(unsigned int *)(v1 + 96));
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v7 = RasDdmParamTraceInfo;
      goto LABEL_20;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800261a4  mov     [rsp-8+arg_8], rbx
0x1800261a9  mov     [rsp-8+arg_10], rdi
0x1800261ae  push    rbp
0x1800261af  lea     rbp, [rsp-780h]
0x1800261b7  sub     rsp, 880h
0x1800261be  mov     rax, cs:__security_cookie
0x1800261c5  xor     rax, rsp
0x1800261c8  mov     [rbp+780h+var_10], rax
0x1800261cf  mov     rbx, [rcx]
0x1800261d2  xor     eax, eax
0x1800261d4  lea     rcx, [rsp+880h+var_80C]; void *
0x1800261d9  mov     [rsp+880h+var_810], eax
0x1800261dd  xor     edx, edx; Val
0x1800261df  mov     r8d, 7FCh; Size
0x1800261e5  call    memset_0
0x1800261ea  xor     eax, eax
0x1800261ec  xorps   xmm0, xmm0
0x1800261ef  test    cs:byte_1800C8404, 10h
0x1800261f6  mov     dword ptr [rsp+880h+Buffer], eax
0x1800261fa  movups  [rsp+880h+var_834], xmm0
0x1800261ff  mov     [rsp+880h+var_814], eax
0x180026203  movups  [rsp+880h+var_824], xmm0
0x180026208  mov     [rsp+880h+var_850], eax
0x18002620c  movups  [rsp+880h+var_848], xmm0
0x180026211  jz      short loc_18002628D
0x180026213  mov     word ptr [rsp+880h+var_810], ax
0x180026218  lea     rdi, [rbx+60h]
0x18002621c  mov     [rsp+880h+Buffer], ax
0x180026221  test    rbx, rbx
0x180026224  jz      short loc_180026240
0x180026226  cmp     dword ptr [rdi], 0FFFFFFFFh
0x180026229  jz      short loc_180026240
0x18002622b  mov     ecx, [rdi]; Value
0x18002622d  lea     r9d, [rax+0Ah]; Radix
0x180026231  lea     r8d, [rax+14h]; BufferCount
0x180026235  lea     rdx, [rsp+880h+Buffer]; Buffer
0x18002623a  call    cs:__imp__itow_s
0x180026240  mov     r8d, [rdi]
0x180026243  lea     rdx, aAnswerincoming; "AnswerIncomingCall for PortId(%d)"
0x18002624a  lea     rcx, [rsp+880h+var_810]
0x18002624f  call    FormatRRASErrorString
0x180026254  test    cs:byte_1800C8404, 10h
0x18002625b  jz      short loc_18002628D
0x18002625d  lea     rax, [rsp+880h+Buffer]
0x180026262  mov     [rsp+880h+var_858], rax
0x180026267  lea     r9, [rsp+880h+var_848]
0x18002626c  lea     r8, [rsp+880h+var_810]
0x180026271  mov     [rsp+880h+var_860], 0
0x18002627a  lea     rdx, RasDdmParamTraceInfo
0x180026281  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026288  call    McTemplateU0zjzz_EventWriteTransfer
0x18002628d  mov     r9, [rbx+60h]
0x180026291  lea     rax, [rsp+880h+var_850]
0x180026296  mov     ecx, [rbx+4ACh]
0x18002629c  mov     [rsp+880h+var_860], rax
0x1800262a1  call    RasLineAnswer
0x1800262a6  mov     edi, eax
0x1800262a8  test    eax, eax
0x1800262aa  jz      short loc_180026315
0x1800262ac  test    cs:byte_1800C8404, 8
0x1800262b3  jz      loc_180026398
0x1800262b9  xor     ecx, ecx
0x1800262bb  mov     word ptr [rsp+880h+var_810], cx
0x1800262c0  mov     [rsp+880h+Buffer], cx
0x1800262c5  test    rbx, rbx
0x1800262c8  jz      short loc_1800262E7
0x1800262ca  mov     ecx, [rbx+60h]; Value
0x1800262cd  cmp     ecx, 0FFFFFFFFh
0x1800262d0  jz      short loc_1800262E7
0x1800262d2  mov     r9d, 0Ah; Radix
0x1800262d8  lea     rdx, [rsp+880h+Buffer]; Buffer
0x1800262dd  lea     r8d, [r9+0Ah]; BufferCount
0x1800262e1  call    cs:__imp__itow_s
0x1800262e7  mov     r8d, [rbx+60h]
0x1800262eb  lea     rdx, aLineanswerForP; "LineAnswer for PortId(%d) failed with e"...
0x1800262f2  mov     r9d, edi
0x1800262f5  lea     rcx, [rsp+880h+var_810]
0x1800262fa  call    FormatRRASErrorString
0x1800262ff  test    cs:byte_1800C8404, 8
0x180026306  jz      loc_180026398
0x18002630c  lea     rdx, RasDdmParamTraceError
0x180026313  jmp     short loc_18002636F
0x180026315  test    cs:byte_1800C8404, 10h
0x18002631c  jz      short loc_180026398
0x18002631e  xor     eax, eax
0x180026320  mov     word ptr [rsp+880h+var_810], ax
0x180026325  mov     [rsp+880h+Buffer], ax
0x18002632a  test    rbx, rbx
0x18002632d  jz      short loc_18002634A
0x18002632f  mov     ecx, [rbx+60h]; Value
0x180026332  cmp     ecx, 0FFFFFFFFh
0x180026335  jz      short loc_18002634A
0x180026337  lea     r9d, [rax+0Ah]; Radix
0x18002633b  lea     r8d, [rax+14h]; BufferCount
0x18002633f  lea     rdx, [rsp+880h+Buffer]; Buffer
0x180026344  call    cs:__imp__itow_s
0x18002634a  mov     r8d, [rbx+60h]
0x18002634e  lea     rdx, aAnswerincoming_0; "AnswerIncomingCall for PortId(%d) passe"...
0x180026355  lea     rcx, [rsp+880h+var_810]
0x18002635a  call    FormatRRASErrorString
0x18002635f  test    cs:byte_1800C8404, 10h
0x180026366  jz      short loc_180026398
0x180026368  lea     rdx, RasDdmParamTraceInfo
0x18002636f  lea     rax, [rsp+880h+Buffer]
0x180026374  mov     [rsp+880h+var_858], rax
0x180026379  lea     r9, [rsp+880h+var_848]
0x18002637e  lea     r8, [rsp+880h+var_810]
0x180026383  mov     [rsp+880h+var_860], 0
0x18002638c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026393  call    McTemplateU0zjzz_EventWriteTransfer
0x180026398  mov     eax, edi
0x18002639a  mov     rcx, [rbp+780h+var_10]
0x1800263a1  xor     rcx, rsp; StackCookie
0x1800263a4  call    __security_check_cookie
0x1800263a9  lea     r11, [rsp+880h+var_s0]
0x1800263b1  mov     rbx, [r11+18h]
0x1800263b5  mov     rdi, [r11+20h]
0x1800263b9  mov     rsp, r11
0x1800263bc  pop     rbp
0x1800263bd  retn
```
