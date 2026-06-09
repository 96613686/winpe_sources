# DdmAcceptIncomingCall(RasObjPtr<DdmDevice> &,ulong)

- ea: `0x180025f64`
- end: `0x18002619c`
- name: `?DdmAcceptIncomingCall@@YAKAEAV?$RasObjPtr@VDdmDevice@@@@K@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180046270`

## callees

- `0x180007c50`
- `0x180025f64`
- `0x180027598`
- `0x180071cec`
- `0x1800855e8`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `msvcrt!_itow_s` at `0x180025ffa`
- `msvcrt!_itow_s` at `0x1800260c8`
- `msvcrt!_itow_s` at `0x18002612b`
- `msvcrt!_itow_s` at `0x180025ffa`
- `msvcrt!_itow_s` at `0x1800260c8`
- `msvcrt!_itow_s` at `0x18002612b`

## string_xrefs

- `0x180026003`: `AcceptIncomingCall for PortId(%d)`
- `0x180026135`: `AcceptIncomingCall for PortId(%d) passed`

## pseudocode

```c
__int64 __fastcall DdmAcceptIncomingCall(_QWORD *a1, int a2)
{
  _DWORD *v2; // rbx
  int *v4; // rdi
  __int64 v5; // rcx
  int VpnDeviceType; // eax
  __int64 v7; // r9
  int v8; // edx
  int v9; // r8d
  unsigned int v10; // edi
  int v11; // ecx
  __int64 *v12; // rdx
  int v13; // ecx
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v16; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v18; // [rsp+4Ch] [rbp-B4h]
  __int128 v19; // [rsp+5Ch] [rbp-A4h]
  int v20; // [rsp+6Ch] [rbp-94h]
  int v21; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  v2 = (_DWORD *)*a1;
  v15 = 0;
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  *(_DWORD *)Buffer = 0;
  v18 = 0;
  v20 = 0;
  v19 = 0;
  v16 = 0;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v21) = 0;
    v4 = v2 + 24;
    Buffer[0] = 0;
    if ( v2 && *v4 != -1 )
      _itow_s(*v4, Buffer, 0x14u, 10);
    FormatRRASErrorString(&v21, L"AcceptIncomingCall for PortId(%d)", (unsigned int)*v4);
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v21,
        (unsigned int)&v16,
        0,
        (__int64)Buffer);
  }
  v5 = (unsigned int)v2[34];
  v2[299] = a2;
  v2[300] = 2;
  v2[301] = 1;
  VpnDeviceType = GetVpnDeviceType(v5);
  v7 = *((_QWORD *)v2 + 12);
  v2[303] = VpnDeviceType;
  v10 = RasLineAccept(a2, v8, v9, v7, (__int64)&v15);
  if ( v10 )
  {
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v21) = 0;
      Buffer[0] = 0;
      if ( v2 )
      {
        v11 = v2[24];
        if ( v11 != -1 )
          _itow_s(v11, Buffer, 0x14u, 10);
      }
      FormatRRASErrorString(&v21, L"LineAccept for PortId(%d) failed with error 0x%x", (unsigned int)v2[24], v10);
      if ( (byte_1800C8404 & 8) != 0 )
      {
        v12 = RasDdmParamTraceError;
LABEL_20:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (_DWORD)v12,
          (unsigned int)&v21,
          (unsigned int)&v16,
          0,
          (__int64)Buffer);
      }
    }
  }
  else if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v21) = 0;
    Buffer[0] = 0;
    if ( v2 )
    {
      v13 = v2[24];
      if ( v13 != -1 )
        _itow_s(v13, Buffer, 0x14u, 10);
    }
    FormatRRASErrorString(&v21, L"AcceptIncomingCall for PortId(%d) passed", (unsigned int)v2[24]);
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      v12 = RasDdmParamTraceInfo;
      goto LABEL_20;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180025f64  push    rbp
0x180025f66  push    rbx
0x180025f67  push    rsi
0x180025f68  push    rdi
0x180025f69  lea     rbp, [rsp-788h]
0x180025f71  sub     rsp, 888h
0x180025f78  mov     rax, cs:__security_cookie
0x180025f7f  xor     rax, rsp
0x180025f82  mov     [rbp+7A0h+var_30], rax
0x180025f89  mov     rbx, [rcx]
0x180025f8c  mov     esi, edx
0x180025f8e  xor     eax, eax
0x180025f90  mov     [rsp+8A0h+var_870], 0
0x180025f98  xor     edx, edx; Val
0x180025f9a  mov     [rsp+8A0h+var_830], eax
0x180025f9e  lea     rcx, [rsp+8A0h+var_82C]; void *
0x180025fa3  mov     r8d, 7FCh; Size
0x180025fa9  call    memset_0
0x180025fae  xor     eax, eax
0x180025fb0  xorps   xmm0, xmm0
0x180025fb3  test    cs:byte_1800C8404, 10h
0x180025fba  mov     dword ptr [rsp+8A0h+Buffer], eax
0x180025fbe  movups  [rsp+8A0h+var_854], xmm0
0x180025fc3  mov     [rsp+8A0h+var_834], eax
0x180025fc7  movups  [rsp+8A0h+var_844], xmm0
0x180025fcc  movups  [rsp+8A0h+var_868], xmm0
0x180025fd1  jz      short loc_18002604D
0x180025fd3  mov     word ptr [rsp+8A0h+var_830], ax
0x180025fd8  lea     rdi, [rbx+60h]
0x180025fdc  mov     [rsp+8A0h+Buffer], ax
0x180025fe1  test    rbx, rbx
0x180025fe4  jz      short loc_180026000
0x180025fe6  cmp     dword ptr [rdi], 0FFFFFFFFh
0x180025fe9  jz      short loc_180026000
0x180025feb  mov     ecx, [rdi]; Value
0x180025fed  lea     r9d, [rax+0Ah]; Radix
0x180025ff1  lea     r8d, [rax+14h]; BufferCount
0x180025ff5  lea     rdx, [rsp+8A0h+Buffer]; Buffer
0x180025ffa  call    cs:__imp__itow_s
0x180026000  mov     r8d, [rdi]
0x180026003  lea     rdx, aAcceptincoming; "AcceptIncomingCall for PortId(%d)"
0x18002600a  lea     rcx, [rsp+8A0h+var_830]
0x18002600f  call    FormatRRASErrorString
0x180026014  test    cs:byte_1800C8404, 10h
0x18002601b  jz      short loc_18002604D
0x18002601d  lea     rax, [rsp+8A0h+Buffer]
0x180026022  mov     [rsp+8A0h+var_878], rax
0x180026027  lea     r9, [rsp+8A0h+var_868]
0x18002602c  lea     r8, [rsp+8A0h+var_830]
0x180026031  mov     [rsp+8A0h+var_880], 0
0x18002603a  lea     rdx, RasDdmParamTraceInfo
0x180026041  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180026048  call    McTemplateU0zjzz_EventWriteTransfer
0x18002604d  mov     ecx, [rbx+88h]
0x180026053  mov     [rbx+4ACh], esi
0x180026059  mov     dword ptr [rbx+4B0h], 2
0x180026063  mov     dword ptr [rbx+4B4h], 1
0x18002606d  call    ?GetVpnDeviceType@@YA?AW4VPN_DEVICE_TYPE@@K@Z; GetVpnDeviceType(ulong)
0x180026072  mov     r9, [rbx+60h]
0x180026076  mov     ecx, esi
0x180026078  mov     [rbx+4BCh], eax
0x18002607e  lea     rax, [rsp+8A0h+var_870]
0x180026083  mov     [rsp+8A0h+var_880], rax
0x180026088  call    RasLineAccept
0x18002608d  mov     edi, eax
0x18002608f  test    eax, eax
0x180026091  jz      short loc_1800260FC
0x180026093  test    cs:byte_1800C8404, 8
0x18002609a  jz      loc_18002617F
0x1800260a0  xor     ecx, ecx
0x1800260a2  mov     word ptr [rsp+8A0h+var_830], cx
0x1800260a7  mov     [rsp+8A0h+Buffer], cx
0x1800260ac  test    rbx, rbx
0x1800260af  jz      short loc_1800260CE
0x1800260b1  mov     ecx, [rbx+60h]; Value
0x1800260b4  cmp     ecx, 0FFFFFFFFh
0x1800260b7  jz      short loc_1800260CE
0x1800260b9  mov     r9d, 0Ah; Radix
0x1800260bf  lea     rdx, [rsp+8A0h+Buffer]; Buffer
0x1800260c4  lea     r8d, [r9+0Ah]; BufferCount
0x1800260c8  call    cs:__imp__itow_s
0x1800260ce  mov     r8d, [rbx+60h]
0x1800260d2  lea     rdx, aLineacceptForP; "LineAccept for PortId(%d) failed with e"...
0x1800260d9  mov     r9d, edi
0x1800260dc  lea     rcx, [rsp+8A0h+var_830]
0x1800260e1  call    FormatRRASErrorString
0x1800260e6  test    cs:byte_1800C8404, 8
0x1800260ed  jz      loc_18002617F
0x1800260f3  lea     rdx, RasDdmParamTraceError
0x1800260fa  jmp     short loc_180026156
0x1800260fc  test    cs:byte_1800C8404, 10h
0x180026103  jz      short loc_18002617F
0x180026105  xor     eax, eax
0x180026107  mov     word ptr [rsp+8A0h+var_830], ax
0x18002610c  mov     [rsp+8A0h+Buffer], ax
0x180026111  test    rbx, rbx
0x180026114  jz      short loc_180026131
0x180026116  mov     ecx, [rbx+60h]; Value
0x180026119  cmp     ecx, 0FFFFFFFFh
0x18002611c  jz      short loc_180026131
0x18002611e  lea     r9d, [rax+0Ah]; Radix
0x180026122  lea     r8d, [rax+14h]; BufferCount
0x180026126  lea     rdx, [rsp+8A0h+Buffer]; Buffer
0x18002612b  call    cs:__imp__itow_s
0x180026131  mov     r8d, [rbx+60h]
0x180026135  lea     rdx, aAcceptincoming_0; "AcceptIncomingCall for PortId(%d) passe"...
0x18002613c  lea     rcx, [rsp+8A0h+var_830]
0x180026141  call    FormatRRASErrorString
0x180026146  test    cs:byte_1800C8404, 10h
0x18002614d  jz      short loc_18002617F
0x18002614f  lea     rdx, RasDdmParamTraceInfo
0x180026156  lea     rax, [rsp+8A0h+Buffer]
0x18002615b  mov     [rsp+8A0h+var_878], rax
0x180026160  lea     r9, [rsp+8A0h+var_868]
0x180026165  lea     r8, [rsp+8A0h+var_830]
0x18002616a  mov     [rsp+8A0h+var_880], 0
0x180026173  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002617a  call    McTemplateU0zjzz_EventWriteTransfer
0x18002617f  mov     eax, edi
0x180026181  mov     rcx, [rbp+7A0h+var_30]
0x180026188  xor     rcx, rsp; StackCookie
0x18002618b  call    __security_check_cookie
0x180026190  add     rsp, 888h
0x180026197  pop     rdi
0x180026198  pop     rsi
0x180026199  pop     rbx
0x18002619a  pop     rbp
0x18002619b  retn
```
