# DdmLegacyDevice::ListenCompleted(void)

- ea: `0x18002ddd0`
- end: `0x18002e16b`
- name: `?ListenCompleted@DdmLegacyDevice@@UEAAKXZ`
- size: `923`
- prototype: `unsigned int __fastcall(DdmLegacyDevice *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180007d00`
- `0x180020130`
- `0x180020260`
- `0x18002ddd0`
- `0x18003d278`
- `0x180075588`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18002e12c`
- `KERNEL32!SetEvent` at `0x18002e12c`
- `rtutils!RouterLogEventStringW` at `0x18002df8d`
- `rtutils!RouterLogEventStringW` at `0x18002e0cb`
- `rtutils!RouterLogEventStringW` at `0x18002df8d`
- `rtutils!RouterLogEventStringW` at `0x18002e0cb`
- `rasman!RasFreeBuffer` at `0x18002e012`
- `rasman!RasFreeBuffer` at `0x18002e012`
- `rasman!RasGetBuffer` at `0x18002df2e`
- `rasman!RasGetBuffer` at `0x18002dfdf`
- `rasman!RasGetBuffer` at `0x18002df2e`
- `rasman!RasGetBuffer` at `0x18002dfdf`
- `rasman!RasPortSend` at `0x18002dfff`
- `rasman!RasPortSend` at `0x18002dfff`

## string_xrefs

- `0x18002de81`: `DdmLegacyDevice::ListenCompleted: Entered, hPort=%ld, fFlags=0x%x`

## pseudocode

```c
__int64 __fastcall DdmLegacyDevice::ListenCompleted(DdmLegacyDevice *this)
{
  int v2; // et2
  int v3; // r14d
  __int64 v4; // rdx
  _QWORD *v5; // rdi
  DWORD dwErrorCode; // esi
  DWORD v8; // edi
  DWORD v9; // eax
  __int64 v10; // rcx
  __int64 v11; // [rsp+48h] [rbp-C0h] BYREF
  LPWSTR plpszSubStringArray; // [rsp+50h] [rbp-B8h] BYREF
  char *v13; // [rsp+58h] [rbp-B0h]
  __int128 v14; // [rsp+60h] [rbp-A8h] BYREF
  _DWORD v15[10]; // [rsp+70h] [rbp-98h] BYREF
  int v16; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v17[2044]; // [rsp+9Ch] [rbp-6Ch] BYREF

  v13 = 0;
  v2 = *((_DWORD *)this + 24) % *(_DWORD *)DdmDeviceTable::GetInstance(0x11u);
  v16 = 0;
  v3 = v2;
  memset_0(v17, 0, sizeof(v17));
  memset(v15, 0, sizeof(v15));
  v14 = 0;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    v4 = *((unsigned int *)this + 24);
    LOWORD(v16) = 0;
    LOWORD(v15[0]) = 0;
    ConvertPortNoToString(v15, v4);
    FormatRRASErrorString(
      &v16,
      L"DdmLegacyDevice::ListenCompleted: Entered, hPort=%ld, fFlags=0x%x",
      *((_QWORD *)this + 12),
      *((unsigned int *)this + 33));
    if ( (byte_1800CF404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v16,
        (unsigned int)&v14,
        0,
        (__int64)v15);
  }
  *((_DWORD *)this + 33) &= 0xFFFFF7FB;
  *((_QWORD *)this + 15) = -1;
  *((_WORD *)this + 84) = 0;
  v5 = (_QWORD *)((char *)this + 1208);
  *((_WORD *)this + 341) = 0;
  *((_WORD *)this + 620) = 0;
  *((_DWORD *)this + 26) = 1;
  *((_QWORD *)this + 149) = 0;
  *((_QWORD *)this + 151) = 0;
  *((_QWORD *)this + 152) = 0;
  *((_DWORD *)this + 309) = 0;
  *((_DWORD *)this + 306) = 1500;
  dwErrorCode = RasGetBuffer((char *)this + 1216, (char *)this + 1224);
  if ( dwErrorCode )
    goto LABEL_5;
  if ( !qword_1800CF5E0 || !qword_1800CF5E8 || *((_WORD *)this + 68) )
    goto LABEL_14;
  LODWORD(v11) = 1500;
  dwErrorCode = RasGetBuffer((char *)this + 1208, &v11);
  if ( !dwErrorCode )
  {
    if ( !(unsigned int)RasPortSend(*((_QWORD *)this + 12), *v5, 0) )
    {
      v9 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, void (__fastcall *)(struct _SECURITY_MESSAGE *)))qword_1800CF5E0)(
             *((_QWORD *)this + 12),
             *v5,
             (unsigned int)v11,
             *((_QWORD *)this + 152),
             *((_DWORD *)this + 306),
             RasSecurityDialogComplete);
      v8 = v9;
      if ( v9 )
      {
        plpszSubStringArray = (LPWSTR)((char *)this + 714);
        if ( dword_1800CF4E4 )
          RouterLogEventStringW(hLogHandle, 1u, 0x4E7Eu, 1u, &plpszSubStringArray, v9, 2u);
        goto LABEL_15;
      }
      v10 = *((_QWORD *)this + 12);
      *((_DWORD *)this + 33) |= 0x800u;
      *((_DWORD *)this + 300) = 0;
      TimerQRemove(v10, SvSecurityTimeout);
      TimerQInsert(*((_QWORD *)this + 12), (unsigned int)dword_1800CF4CC, SvSecurityTimeout);
      return 0;
    }
    RasFreeBuffer(*v5);
    *v5 = 0;
LABEL_14:
    v8 = (*(__int64 (__fastcall **)(DdmLegacyDevice *))(*(_QWORD *)this + 448LL))(this);
    if ( v8 )
    {
LABEL_15:
      (*(void (__fastcall **)(DdmLegacyDevice *))(*(_QWORD *)this + 176LL))(this);
      return v8;
    }
    SetEvent(gblSupervisorEvents[v3 + 6]);
    return 0;
  }
LABEL_5:
  plpszSubStringArray = (LPWSTR)((char *)this + 1092);
  v13 = (char *)this + 714;
  if ( dword_1800CF4E4 )
    RouterLogEventStringW(hLogHandle, 1u, 0x4F24u, 2u, &plpszSubStringArray, dwErrorCode, 2u);
  (*(void (__fastcall **)(DdmLegacyDevice *))(*(_QWORD *)this + 176LL))(this);
  return dwErrorCode;
}

```

## disassembly

```asm
0x18002ddd0  mov     rax, rsp
0x18002ddd3  mov     [rax+10h], rbx
0x18002ddd7  mov     [rax+18h], rsi
0x18002dddb  mov     [rax+20h], rdi
0x18002dddf  push    rbp
0x18002dde0  push    r12
0x18002dde2  push    r13
0x18002dde4  push    r14
0x18002dde6  push    r15
0x18002dde8  lea     rbp, [rax-7C8h]
0x18002ddef  sub     rsp, 8A0h
0x18002ddf6  mov     rax, cs:__security_cookie
0x18002ddfd  xor     rax, rsp
0x18002de00  mov     [rbp+7C0h+var_30], rax
0x18002de07  xor     r13d, r13d
0x18002de0a  mov     rbx, rcx
0x18002de0d  mov     qword ptr [rsp+8C0h+var_870], r13
0x18002de12  lea     ecx, [r13+11h]; unsigned int
0x18002de16  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18002de1b  mov     rcx, rax
0x18002de1e  xor     edx, edx
0x18002de20  mov     eax, [rbx+60h]
0x18002de23  mov     r8d, 7FCh; Size
0x18002de29  div     dword ptr [rcx]
0x18002de2b  lea     rcx, [rbp+7C0h+var_82C]; void *
0x18002de2f  mov     [rbp+7C0h+var_830], r13d
0x18002de33  mov     r14d, edx
0x18002de36  xor     edx, edx; Val
0x18002de38  call    memset_0
0x18002de3d  xorps   xmm0, xmm0
0x18002de40  mov     dword ptr [rsp+8C0h+var_85C+4], r13d
0x18002de45  xor     eax, eax
0x18002de47  test    cs:byte_1800CF404, 10h
0x18002de4e  movups  [rsp+8C0h+var_85C+8], xmm0
0x18002de53  mov     [rbp+7C0h+var_834], eax
0x18002de56  movups  xmmword ptr [rsp+8C0h+var_84C+8], xmm0
0x18002de5b  movups  [rsp+8C0h+var_870+8], xmm0
0x18002de60  jz      short loc_18002DEC9
0x18002de62  mov     edx, [rbx+60h]
0x18002de65  lea     rcx, [rsp+8C0h+var_85C+4]
0x18002de6a  mov     word ptr [rbp+7C0h+var_830], r13w
0x18002de6f  mov     word ptr [rsp+8C0h+var_85C+4], r13w
0x18002de75  call    ConvertPortNoToString
0x18002de7a  mov     r9d, [rbx+84h]
0x18002de81  lea     rdx, aDdmlegacydevic_11; "DdmLegacyDevice::ListenCompleted: Enter"...
0x18002de88  mov     r8, [rbx+60h]
0x18002de8c  lea     rcx, [rbp+7C0h+var_830]
0x18002de90  call    FormatRRASErrorString
0x18002de95  test    cs:byte_1800CF404, 10h
0x18002de9c  jz      short loc_18002DEC9
0x18002de9e  lea     rax, [rsp+8C0h+var_85C+4]
0x18002dea3  mov     qword ptr [rsp+8C0h+dwErrorCode], rax
0x18002dea8  lea     r9, [rsp+8C0h+var_870+8]
0x18002dead  lea     r8, [rbp+7C0h+var_830]
0x18002deb1  mov     [rsp+8C0h+plpszSubStringArray], r13
0x18002deb6  lea     rdx, RasDdmParamTraceInfo
0x18002debd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002dec4  call    McTemplateU0zjzz_EventWriteTransfer
0x18002dec9  and     dword ptr [rbx+84h], 0FFFFF7FBh
0x18002ded3  lea     r15, [rbx+4C0h]
0x18002deda  or      qword ptr [rbx+78h], 0FFFFFFFFFFFFFFFFh
0x18002dedf  lea     r12, [rbx+4C8h]
0x18002dee6  mov     [rbx+0A8h], r13w
0x18002deee  lea     rdi, [rbx+4B8h]
0x18002def5  mov     [rbx+2AAh], r13w
0x18002defd  mov     rdx, r12
0x18002df00  mov     [rbx+4D8h], r13w
0x18002df08  mov     rcx, r15
0x18002df0b  mov     dword ptr [rbx+68h], 1
0x18002df12  mov     [rbx+4A8h], r13
0x18002df19  mov     [rdi], r13
0x18002df1c  mov     [r15], r13
0x18002df1f  mov     [rbx+4D4h], r13d
0x18002df26  mov     dword ptr [r12], 5DCh
0x18002df2e  call    cs:__imp_RasGetBuffer
0x18002df35  nop     dword ptr [rax+rax+00h]
0x18002df3a  mov     esi, eax
0x18002df3c  test    eax, eax
0x18002df3e  jz      short loc_18002DFB2
0x18002df40  cmp     cs:dword_1800CF4E4, r13d
0x18002df47  lea     rcx, [rbx+444h]
0x18002df4e  mov     [rsp+8C0h+var_878], rcx
0x18002df53  lea     rcx, [rbx+2CAh]
0x18002df5a  mov     qword ptr [rsp+8C0h+var_870], rcx
0x18002df5f  jbe     short loc_18002DF99
0x18002df61  mov     rcx, cs:hLogHandle; hLogHandle
0x18002df68  lea     rax, [rsp+8C0h+var_878]
0x18002df6d  mov     edx, 1; dwEventType
0x18002df72  mov     [rsp+8C0h+dwErrorIndex], 2; dwErrorIndex
0x18002df7a  mov     [rsp+8C0h+dwErrorCode], esi; dwErrorCode
0x18002df7e  mov     r8d, 4F24h; dwMessageId
0x18002df84  mov     [rsp+8C0h+plpszSubStringArray], rax; plpszSubStringArray
0x18002df89  lea     r9d, [rdx+1]; dwSubStringCount
0x18002df8d  call    cs:__imp_RouterLogEventStringW
0x18002df94  nop     dword ptr [rax+rax+00h]
0x18002df99  mov     rax, [rbx]
0x18002df9c  mov     rcx, rbx
0x18002df9f  mov     rax, [rax+0B0h]
0x18002dfa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfab  mov     eax, esi
0x18002dfad  jmp     loc_18002E13A
0x18002dfb2  cmp     cs:qword_1800CF5E0, r13
0x18002dfb9  jz      short loc_18002E021
0x18002dfbb  cmp     cs:qword_1800CF5E8, r13
0x18002dfc2  jz      short loc_18002E021
0x18002dfc4  movzx   eax, word ptr [rbx+88h]
0x18002dfcb  test    eax, eax
0x18002dfcd  jnz     short loc_18002E021
0x18002dfcf  lea     rdx, [rsp+8C0h+var_880]
0x18002dfd4  mov     dword ptr [rsp+8C0h+var_880], 5DCh
0x18002dfdc  mov     rcx, rdi
0x18002dfdf  call    cs:__imp_RasGetBuffer
0x18002dfe6  nop     dword ptr [rax+rax+00h]
0x18002dfeb  mov     esi, eax
0x18002dfed  test    eax, eax
0x18002dfef  jnz     loc_18002DF40
0x18002dff5  mov     rdx, [rdi]
0x18002dff8  xor     r8d, r8d
0x18002dffb  mov     rcx, [rbx+60h]
0x18002dfff  call    cs:__imp_RasPortSend
0x18002e006  nop     dword ptr [rax+rax+00h]
0x18002e00b  test    eax, eax
0x18002e00d  jz      short loc_18002E056
0x18002e00f  mov     rcx, [rdi]
0x18002e012  call    cs:__imp_RasFreeBuffer
0x18002e019  nop     dword ptr [rax+rax+00h]
0x18002e01e  mov     [rdi], r13
0x18002e021  mov     rax, [rbx]
0x18002e024  mov     rcx, rbx
0x18002e027  mov     rax, [rax+1C0h]
0x18002e02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e033  mov     edi, eax
0x18002e035  test    eax, eax
0x18002e037  jz      loc_18002E11D
0x18002e03d  mov     rcx, [rbx]
0x18002e040  mov     rax, [rcx+0B0h]
0x18002e047  mov     rcx, rbx
0x18002e04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e04f  mov     eax, edi
0x18002e051  jmp     loc_18002E13A
0x18002e056  mov     ecx, [r12]
0x18002e05a  lea     rax, ?RasSecurityDialogComplete@@YAXPEAU_SECURITY_MESSAGE@@@Z; RasSecurityDialogComplete(_SECURITY_MESSAGE *)
0x18002e061  mov     r9, [r15]
0x18002e064  mov     r8d, dword ptr [rsp+8C0h+var_880]
0x18002e069  mov     rdx, [rdi]
0x18002e06c  mov     qword ptr [rsp+8C0h+dwErrorCode], rax
0x18002e071  mov     rax, cs:qword_1800CF5E0
0x18002e078  mov     dword ptr [rsp+8C0h+plpszSubStringArray], ecx
0x18002e07c  mov     rcx, [rbx+60h]
0x18002e080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e085  mov     edi, eax
0x18002e087  test    eax, eax
0x18002e089  jz      short loc_18002E0E6
0x18002e08b  cmp     cs:dword_1800CF4E4, r13d
0x18002e092  lea     rcx, [rbx+2CAh]
0x18002e099  mov     [rsp+8C0h+var_878], rcx
0x18002e09e  jbe     short loc_18002E0D7
0x18002e0a0  mov     rcx, cs:hLogHandle; hLogHandle
0x18002e0a7  mov     edx, 1; dwEventType
0x18002e0ac  mov     [rsp+8C0h+dwErrorIndex], 2; dwErrorIndex
0x18002e0b4  mov     r9d, edx; dwSubStringCount
0x18002e0b7  mov     [rsp+8C0h+dwErrorCode], eax; dwErrorCode
0x18002e0bb  mov     r8d, 4E7Eh; dwMessageId
0x18002e0c1  lea     rax, [rsp+8C0h+var_878]
0x18002e0c6  mov     [rsp+8C0h+plpszSubStringArray], rax; plpszSubStringArray
0x18002e0cb  call    cs:__imp_RouterLogEventStringW
0x18002e0d2  nop     dword ptr [rax+rax+00h]
0x18002e0d7  mov     rax, [rbx]
0x18002e0da  mov     rax, [rax+0B0h]
0x18002e0e1  jmp     loc_18002E047
0x18002e0e6  mov     rcx, [rbx+60h]
0x18002e0ea  lea     rdx, ?SvSecurityTimeout@@YAXPEAX@Z; SvSecurityTimeout(void *)
0x18002e0f1  bts     dword ptr [rbx+84h], 0Bh
0x18002e0f9  mov     [rbx+4B0h], r13d
0x18002e100  call    TimerQRemove
0x18002e105  mov     edx, cs:dword_1800CF4CC
0x18002e10b  lea     r8, ?SvSecurityTimeout@@YAXPEAX@Z; SvSecurityTimeout(void *)
0x18002e112  mov     rcx, [rbx+60h]
0x18002e116  call    TimerQInsert
0x18002e11b  jmp     short loc_18002E138
0x18002e11d  mov     rcx, cs:gblSupervisorEvents
0x18002e124  lea     eax, [r14+6]
0x18002e128  mov     rcx, [rcx+rax*8]; hEvent
0x18002e12c  call    cs:__imp_SetEvent
0x18002e133  nop     dword ptr [rax+rax+00h]
0x18002e138  xor     eax, eax
0x18002e13a  mov     rcx, [rbp+7C0h+var_30]
0x18002e141  xor     rcx, rsp; StackCookie
0x18002e144  call    __security_check_cookie
0x18002e149  lea     r11, [rsp+8C0h+var_20]
0x18002e151  mov     rbx, [r11+38h]
0x18002e155  mov     rsi, [r11+40h]
0x18002e159  mov     rdi, [r11+48h]
0x18002e15d  mov     rsp, r11
0x18002e160  pop     r15
0x18002e162  pop     r14
0x18002e164  pop     r13
0x18002e166  pop     r12
0x18002e168  pop     rbp
0x18002e169  retn
```
