# DdmLegacyDevice::ListenCompleted(void)

- ea: `0x18002bc70`
- end: `0x18002bfe8`
- name: `?ListenCompleted@DdmLegacyDevice@@UEAAKXZ`
- size: `888`
- prototype: `unsigned int __fastcall(DdmLegacyDevice *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x18001f4e0`
- `0x18001f5e0`
- `0x18002bc70`
- `0x18003b8f4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x18002bd14`
- `msvcrt!_itow_s` at `0x18002bd14`
- `KERNEL32!SetEvent` at `0x18002bfbd`
- `KERNEL32!SetEvent` at `0x18002bfbd`
- `rtutils!RouterLogEventStringW` at `0x18002be26`
- `rtutils!RouterLogEventStringW` at `0x18002bf62`
- `rtutils!RouterLogEventStringW` at `0x18002be26`
- `rtutils!RouterLogEventStringW` at `0x18002bf62`
- `rasman!RasFreeBuffer` at `0x18002beaf`
- `rasman!RasFreeBuffer` at `0x18002beaf`
- `rasman!RasGetBuffer` at `0x18002bdcd`
- `rasman!RasGetBuffer` at `0x18002be80`
- `rasman!RasGetBuffer` at `0x18002bdcd`
- `rasman!RasGetBuffer` at `0x18002be80`
- `rasman!RasPortSend` at `0x18002bea2`
- `rasman!RasPortSend` at `0x18002bea2`

## string_xrefs

- `0x18002bd21`: `DdmLegacyDevice::ListenCompleted: Entered, hPort=%ld, fFlags=0x%x`

## pseudocode

```c
__int64 __fastcall DdmLegacyDevice::ListenCompleted(DdmLegacyDevice *this)
{
  struct DdmDeviceTable *Instance; // rax
  unsigned int v3; // r14d
  unsigned int v4; // r13d
  _QWORD *v5; // rdi
  DWORD dwErrorCode; // esi
  bool v7; // zf
  int v9; // r14d
  DWORD v10; // edi
  DWORD v11; // eax
  __int64 v12; // r8
  __int64 v13; // rcx
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR plpszSubStringArray[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v16; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t Buffer[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v18; // [rsp+6Ch] [rbp-94h]
  __int128 v19; // [rsp+7Ch] [rbp-84h]
  int v20; // [rsp+8Ch] [rbp-74h]
  int v21; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v22[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v14 = 0;
  *(_OWORD *)plpszSubStringArray = 0;
  Instance = DdmDeviceTable::GetInstance(0x11u);
  v3 = *((_DWORD *)this + 24);
  v4 = *(_DWORD *)Instance;
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
    Buffer[0] = 0;
    if ( v3 != -1 )
      _itow_s(v3, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v21,
      L"DdmLegacyDevice::ListenCompleted: Entered, hPort=%ld, fFlags=0x%x",
      *((_QWORD *)this + 12),
      *((unsigned int *)this + 33));
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v21,
        (unsigned int)&v16,
        0,
        (__int64)Buffer);
  }
  *((_DWORD *)this + 33) &= 0xFFFFF7FB;
  *((_WORD *)this + 84) = 0;
  *((_WORD *)this + 341) = 0;
  v5 = (_QWORD *)((char *)this + 1208);
  *((_WORD *)this + 620) = 0;
  *((_DWORD *)this + 26) = 1;
  *((_QWORD *)this + 15) = -1;
  *((_QWORD *)this + 149) = 0;
  *((_QWORD *)this + 151) = 0;
  *((_QWORD *)this + 152) = 0;
  *((_DWORD *)this + 309) = 0;
  *((_DWORD *)this + 306) = 1500;
  dwErrorCode = RasGetBuffer((char *)this + 1216, (char *)this + 1224);
  if ( !dwErrorCode )
  {
    v9 = v3 % v4;
    if ( qword_1800C85E0 && qword_1800C85E8 && !*((_WORD *)this + 68) )
    {
      v14 = 1500;
      dwErrorCode = RasGetBuffer((char *)this + 1208, &v14);
      if ( dwErrorCode )
      {
        v7 = dword_1800C84E4 == 0;
        goto LABEL_8;
      }
      if ( !(unsigned int)RasPortSend(*((_QWORD *)this + 12), *v5, 0) )
      {
        v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, void (__fastcall *)(struct _SECURITY_MESSAGE *)))qword_1800C85E0)(
                *((_QWORD *)this + 12),
                *v5,
                v14,
                *((_QWORD *)this + 152),
                *((_DWORD *)this + 306),
                RasSecurityDialogComplete);
        v10 = v11;
        if ( v11 )
        {
          plpszSubStringArray[0] = (LPWSTR)((char *)this + 714);
          if ( dword_1800C84E4 )
            RouterLogEventStringW(hLogHandle, 1u, 0x4E7Eu, 1u, plpszSubStringArray, v11, 2u);
          goto LABEL_19;
        }
        v13 = *((_QWORD *)this + 12);
        *((_DWORD *)this + 33) |= 0x800u;
        *((_DWORD *)this + 300) = 0;
        TimerQRemove(v13, (__int64)SvSecurityTimeout, v12);
        TimerQInsert(*((_QWORD *)this + 12), (unsigned int)dword_1800C84CC, SvSecurityTimeout);
        return 0;
      }
      RasFreeBuffer(*v5);
      *v5 = 0;
    }
    v10 = (*(__int64 (__fastcall **)(DdmLegacyDevice *))(*(_QWORD *)this + 448LL))(this);
    if ( v10 )
    {
LABEL_19:
      (*(void (__fastcall **)(DdmLegacyDevice *))(*(_QWORD *)this + 176LL))(this);
      return v10;
    }
    SetEvent(gblSupervisorEvents[v9 + 6]);
    return 0;
  }
  v7 = dword_1800C84E4 == 0;
LABEL_8:
  plpszSubStringArray[0] = (LPWSTR)((char *)this + 1092);
  plpszSubStringArray[1] = (LPWSTR)((char *)this + 714);
  if ( !v7 )
    RouterLogEventStringW(hLogHandle, 1u, 0x4F24u, 2u, plpszSubStringArray, dwErrorCode, 2u);
  (*(void (__fastcall **)(DdmLegacyDevice *))(*(_QWORD *)this + 176LL))(this);
  return dwErrorCode;
}

```

## disassembly

```asm
0x18002bc70  push    rbp
0x18002bc72  push    rbx
0x18002bc73  push    rsi
0x18002bc74  push    rdi
0x18002bc75  push    r12
0x18002bc77  push    r13
0x18002bc79  push    r14
0x18002bc7b  push    r15
0x18002bc7d  lea     rbp, [rsp-7A8h]
0x18002bc85  sub     rsp, 8A8h
0x18002bc8c  mov     rax, cs:__security_cookie
0x18002bc93  xor     rax, rsp
0x18002bc96  mov     [rbp+7E0h+var_50], rax
0x18002bc9d  xor     esi, esi
0x18002bc9f  mov     rbx, rcx
0x18002bca2  xorps   xmm0, xmm0
0x18002bca5  mov     [rsp+8E0h+var_8A0], esi
0x18002bca9  movups  xmmword ptr [rsp+8E0h+var_898], xmm0
0x18002bcae  lea     ecx, [rsi+11h]; unsigned int
0x18002bcb1  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x18002bcb6  mov     r14d, [rbx+60h]
0x18002bcba  lea     rcx, [rbp+7E0h+var_84C]; void *
0x18002bcbe  xor     edx, edx; Val
0x18002bcc0  mov     r8d, 7FCh; Size
0x18002bcc6  mov     r13d, [rax]
0x18002bcc9  mov     [rbp+7E0h+var_850], esi
0x18002bccc  call    memset_0
0x18002bcd1  xorps   xmm0, xmm0
0x18002bcd4  mov     dword ptr [rsp+8E0h+Buffer], esi
0x18002bcd8  xor     eax, eax
0x18002bcda  test    cs:byte_1800C8404, 10h
0x18002bce1  movups  [rsp+8E0h+var_874], xmm0
0x18002bce6  mov     [rbp+7E0h+var_854], eax
0x18002bce9  movups  [rsp+8E0h+var_864], xmm0
0x18002bcee  movups  [rsp+8E0h+var_888], xmm0
0x18002bcf3  jz      short loc_18002BD69
0x18002bcf5  mov     word ptr [rbp+7E0h+var_850], si
0x18002bcf9  mov     [rsp+8E0h+Buffer], si
0x18002bcfe  cmp     r14d, 0FFFFFFFFh
0x18002bd02  jz      short loc_18002BD1A
0x18002bd04  lea     r9d, [rsi+0Ah]; Radix
0x18002bd08  mov     ecx, r14d; Value
0x18002bd0b  lea     r8d, [rsi+14h]; BufferCount
0x18002bd0f  lea     rdx, [rsp+8E0h+Buffer]; Buffer
0x18002bd14  call    cs:__imp__itow_s
0x18002bd1a  mov     r9d, [rbx+84h]
0x18002bd21  lea     rdx, aDdmlegacydevic_11; "DdmLegacyDevice::ListenCompleted: Enter"...
0x18002bd28  mov     r8, [rbx+60h]
0x18002bd2c  lea     rcx, [rbp+7E0h+var_850]
0x18002bd30  call    FormatRRASErrorString
0x18002bd35  test    cs:byte_1800C8404, 10h
0x18002bd3c  jz      short loc_18002BD69
0x18002bd3e  lea     rax, [rsp+8E0h+Buffer]
0x18002bd43  mov     qword ptr [rsp+8E0h+dwErrorCode], rax
0x18002bd48  lea     r9, [rsp+8E0h+var_888]
0x18002bd4d  lea     r8, [rbp+7E0h+var_850]
0x18002bd51  mov     [rsp+8E0h+plpszSubStringArray], rsi
0x18002bd56  lea     rdx, RasDdmParamTraceInfo
0x18002bd5d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002bd64  call    McTemplateU0zjzz_EventWriteTransfer
0x18002bd69  and     dword ptr [rbx+84h], 0FFFFF7FBh
0x18002bd73  lea     r15, [rbx+4C0h]
0x18002bd7a  mov     [rbx+0A8h], si
0x18002bd81  lea     r12, [rbx+4C8h]
0x18002bd88  mov     [rbx+2AAh], si
0x18002bd8f  lea     rdi, [rbx+4B8h]
0x18002bd96  mov     [rbx+4D8h], si
0x18002bd9d  mov     rdx, r12
0x18002bda0  mov     rcx, r15
0x18002bda3  mov     dword ptr [rbx+68h], 1
0x18002bdaa  mov     qword ptr [rbx+78h], 0FFFFFFFFFFFFFFFFh
0x18002bdb2  mov     [rbx+4A8h], rsi
0x18002bdb9  mov     [rdi], rsi
0x18002bdbc  mov     [r15], rsi
0x18002bdbf  mov     [rbx+4D4h], esi
0x18002bdc5  mov     dword ptr [r12], 5DCh
0x18002bdcd  call    cs:__imp_RasGetBuffer
0x18002bdd3  mov     esi, eax
0x18002bdd5  test    eax, eax
0x18002bdd7  jz      short loc_18002BE45
0x18002bdd9  cmp     cs:dword_1800C84E4, 0
0x18002bde0  lea     rcx, [rbx+444h]
0x18002bde7  mov     [rsp+8E0h+var_898], rcx
0x18002bdec  lea     rcx, [rbx+2CAh]
0x18002bdf3  mov     [rsp+8E0h+var_898+8], rcx
0x18002bdf8  jbe     short loc_18002BE2C
0x18002bdfa  mov     rcx, cs:hLogHandle; hLogHandle
0x18002be01  lea     rax, [rsp+8E0h+var_898]
0x18002be06  mov     edx, 1; dwEventType
0x18002be0b  mov     [rsp+8E0h+dwErrorIndex], 2; dwErrorIndex
0x18002be13  mov     [rsp+8E0h+dwErrorCode], esi; dwErrorCode
0x18002be17  mov     r8d, 4F24h; dwMessageId
0x18002be1d  mov     [rsp+8E0h+plpszSubStringArray], rax; plpszSubStringArray
0x18002be22  lea     r9d, [rdx+1]; dwSubStringCount
0x18002be26  call    cs:__imp_RouterLogEventStringW
0x18002be2c  mov     rax, [rbx]
0x18002be2f  mov     rcx, rbx
0x18002be32  mov     rax, [rax+0B0h]
0x18002be39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be3e  mov     eax, esi
0x18002be40  jmp     loc_18002BFC5
0x18002be45  xor     edx, edx
0x18002be47  mov     eax, r14d
0x18002be4a  div     r13d
0x18002be4d  xor     r13d, r13d
0x18002be50  cmp     cs:qword_1800C85E0, r13
0x18002be57  mov     r14d, edx
0x18002be5a  jz      short loc_18002BEB8
0x18002be5c  cmp     cs:qword_1800C85E8, r13
0x18002be63  jz      short loc_18002BEB8
0x18002be65  movzx   eax, word ptr [rbx+88h]
0x18002be6c  test    eax, eax
0x18002be6e  jnz     short loc_18002BEB8
0x18002be70  lea     rdx, [rsp+8E0h+var_8A0]
0x18002be75  mov     [rsp+8E0h+var_8A0], 5DCh
0x18002be7d  mov     rcx, rdi
0x18002be80  call    cs:__imp_RasGetBuffer
0x18002be86  mov     esi, eax
0x18002be88  test    eax, eax
0x18002be8a  jz      short loc_18002BE98
0x18002be8c  cmp     cs:dword_1800C84E4, r13d
0x18002be93  jmp     loc_18002BDE0
0x18002be98  mov     rdx, [rdi]
0x18002be9b  xor     r8d, r8d
0x18002be9e  mov     rcx, [rbx+60h]
0x18002bea2  call    cs:__imp_RasPortSend
0x18002bea8  test    eax, eax
0x18002beaa  jz      short loc_18002BEED
0x18002beac  mov     rcx, [rdi]
0x18002beaf  call    cs:__imp_RasFreeBuffer
0x18002beb5  mov     [rdi], r13
0x18002beb8  mov     rax, [rbx]
0x18002bebb  mov     rcx, rbx
0x18002bebe  mov     rax, [rax+1C0h]
0x18002bec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002beca  mov     edi, eax
0x18002becc  test    eax, eax
0x18002bece  jz      loc_18002BFAE
0x18002bed4  mov     rcx, [rbx]
0x18002bed7  mov     rax, [rcx+0B0h]
0x18002bede  mov     rcx, rbx
0x18002bee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bee6  mov     eax, edi
0x18002bee8  jmp     loc_18002BFC5
0x18002beed  mov     ecx, [r12]
0x18002bef1  lea     rax, ?RasSecurityDialogComplete@@YAXPEAU_SECURITY_MESSAGE@@@Z; RasSecurityDialogComplete(_SECURITY_MESSAGE *)
0x18002bef8  mov     r9, [r15]
0x18002befb  mov     r8d, [rsp+8E0h+var_8A0]
0x18002bf00  mov     rdx, [rdi]
0x18002bf03  mov     qword ptr [rsp+8E0h+dwErrorCode], rax
0x18002bf08  mov     rax, cs:qword_1800C85E0
0x18002bf0f  mov     dword ptr [rsp+8E0h+plpszSubStringArray], ecx
0x18002bf13  mov     rcx, [rbx+60h]
0x18002bf17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf1c  mov     edi, eax
0x18002bf1e  test    eax, eax
0x18002bf20  jz      short loc_18002BF77
0x18002bf22  cmp     cs:dword_1800C84E4, r13d
0x18002bf29  lea     rcx, [rbx+2CAh]
0x18002bf30  mov     [rsp+8E0h+var_898], rcx
0x18002bf35  jbe     short loc_18002BF68
0x18002bf37  mov     rcx, cs:hLogHandle; hLogHandle
0x18002bf3e  mov     edx, 1; dwEventType
0x18002bf43  mov     [rsp+8E0h+dwErrorIndex], 2; dwErrorIndex
0x18002bf4b  mov     r9d, edx; dwSubStringCount
0x18002bf4e  mov     [rsp+8E0h+dwErrorCode], eax; dwErrorCode
0x18002bf52  mov     r8d, 4E7Eh; dwMessageId
0x18002bf58  lea     rax, [rsp+8E0h+var_898]
0x18002bf5d  mov     [rsp+8E0h+plpszSubStringArray], rax; plpszSubStringArray
0x18002bf62  call    cs:__imp_RouterLogEventStringW
0x18002bf68  mov     rax, [rbx]
0x18002bf6b  mov     rax, [rax+0B0h]
0x18002bf72  jmp     loc_18002BEDE
0x18002bf77  mov     rcx, [rbx+60h]
0x18002bf7b  lea     rdx, ?SvSecurityTimeout@@YAXPEAX@Z; SvSecurityTimeout(void *)
0x18002bf82  bts     dword ptr [rbx+84h], 0Bh
0x18002bf8a  mov     [rbx+4B0h], r13d
0x18002bf91  call    TimerQRemove
0x18002bf96  mov     edx, cs:dword_1800C84CC
0x18002bf9c  lea     r8, ?SvSecurityTimeout@@YAXPEAX@Z; SvSecurityTimeout(void *)
0x18002bfa3  mov     rcx, [rbx+60h]
0x18002bfa7  call    TimerQInsert
0x18002bfac  jmp     short loc_18002BFC3
0x18002bfae  mov     rcx, cs:gblSupervisorEvents
0x18002bfb5  lea     eax, [r14+6]
0x18002bfb9  mov     rcx, [rcx+rax*8]; hEvent
0x18002bfbd  call    cs:__imp_SetEvent
0x18002bfc3  xor     eax, eax
0x18002bfc5  mov     rcx, [rbp+7E0h+var_50]
0x18002bfcc  xor     rcx, rsp; StackCookie
0x18002bfcf  call    __security_check_cookie
0x18002bfd4  add     rsp, 8A8h
0x18002bfdb  pop     r15
0x18002bfdd  pop     r14
0x18002bfdf  pop     r13
0x18002bfe1  pop     r12
0x18002bfe3  pop     rdi
0x18002bfe4  pop     rsi
0x18002bfe5  pop     rbx
0x18002bfe6  pop     rbp
0x18002bfe7  retn
```
