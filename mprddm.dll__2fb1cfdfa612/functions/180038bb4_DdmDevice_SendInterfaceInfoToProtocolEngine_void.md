# DdmDevice::SendInterfaceInfoToProtocolEngine(void)

- ea: `0x180038bb4`
- end: `0x180038ed0`
- name: `?SendInterfaceInfoToProtocolEngine@DdmDevice@@QEAAKXZ`
- size: `796`
- prototype: `unsigned int __fastcall(DdmDevice *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800342d0`

## callees

- `0x180002ba6`
- `0x180007c50`
- `0x18002e0ec`
- `0x18002e268`
- `0x180038bb4`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008c6f0`
- `0x18008e010`

## import_xrefs

- `msvcrt!_itow_s` at `0x180038cd0`
- `msvcrt!_itow_s` at `0x180038d99`
- `msvcrt!_itow_s` at `0x180038cd0`
- `msvcrt!_itow_s` at `0x180038d99`

## string_xrefs

- `0x180038cda`: `DdmDevice::SendInterfaceInfoToProtocolEngine`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdmDevice::SendInterfaceInfoToProtocolEngine(DdmDevice *this)
{
  int v2; // eax
  __int64 *v3; // rsi
  int v4; // ecx
  struct DdmConnectionTable *Instance; // rax
  __int64 v6; // rbx
  char v7; // dl
  int v8; // ecx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // edi
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD Src[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[2784]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+B30h] [rbp+A30h] BYREF
  __int64 v18; // [rsp+B38h] [rbp+A38h]
  __int64 v19; // [rsp+B40h] [rbp+A40h] BYREF
  _BYTE v20[7112]; // [rsp+B48h] [rbp+A48h] BYREF
  __int128 v21; // [rsp+2710h] [rbp+2610h] BYREF
  wchar_t Buffer[2]; // [rsp+2720h] [rbp+2620h] BYREF
  __int128 v23; // [rsp+2724h] [rbp+2624h]
  __int128 v24; // [rsp+2734h] [rbp+2634h]
  int v25; // [rsp+2744h] [rbp+2644h]
  int v26; // [rsp+2750h] [rbp+2650h] BYREF
  _BYTE v27[2044]; // [rsp+2754h] [rbp+2654h] BYREF

  Src[0] = 0;
  Src[1] = 0;
  memset_0(v16, 0, 0xAD8u);
  v2 = (unsigned __int16)*((_DWORD *)this + 34);
  if ( v2 == 15 )
  {
    v3 = (__int64 *)&qword_1800C7518;
  }
  else
  {
    v3 = &qword_1800C7568;
    if ( v2 != 16 )
      v3 = qword_1800C74C8;
  }
  v17 = 10;
  v18 = 0;
  memset_0(&v19, 0, 0x1BD0u);
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  *(_DWORD *)Buffer = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  v21 = 0;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    LOWORD(v26) = 0;
    Buffer[0] = 0;
    v4 = *((_DWORD *)this + 24);
    if ( v4 != -1 )
      _itow_s(v4, Buffer, 0x14u, 10);
    FormatRRASErrorString(
      &v26,
      L"%s (hport: %ld)",
      L"DdmDevice::SendInterfaceInfoToProtocolEngine",
      *((_QWORD *)this + 12));
    if ( (byte_1800C8404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)&v26,
        (unsigned int)&v21,
        0,
        (__int64)Buffer);
  }
  memset_0(Src, 0, 0xAE8u);
  v14 = 0;
  Instance = DdmConnectionTable::GetInstance();
  DdmConnectionTable::FindConnection(Instance, *((_QWORD *)this + 15), &v14);
  v6 = v14;
  if ( v14 )
  {
    (**(void (__fastcall ***)(__int64))g_pIDimInterfaceTable)(g_pIDimInterfaceTable);
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)g_pIDimInterfaceTable + 64LL))(
            g_pIDimInterfaceTable,
            *(_QWORD *)(v6 + 72));
    v12 = v10;
    if ( v10 )
      (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v10 + 368LL))(v10, Src);
    (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)g_pIDimInterfaceTable + 16LL))(
      g_pIDimInterfaceTable,
      v11,
      v12);
    v19 = *((_QWORD *)this + 15);
    v18 = *((_QWORD *)this + 12);
    LODWORD(v17) = 10;
    memcpy_0(v20, Src, 0xAE8u);
    v13 = ((__int64 (__fastcall *)(__int64 *))*v3)(&v17);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 8), 0xFFFFFFFF) == 1 && v6 )
      (**(void (__fastcall ***)(__int64, __int64))v6)(v6, 1);
    return v13;
  }
  else
  {
    v7 = byte_1800C8404;
    if ( (byte_1800C8404 & 0x10) != 0 )
    {
      Buffer[0] = 0;
      v8 = *((_DWORD *)this + 24);
      if ( v8 != -1 )
      {
        _itow_s(v8, Buffer, (unsigned int)(v14 + 20), v14 + 10);
        v7 = byte_1800C8404;
      }
      if ( (v7 & 0x10) != 0 )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDdmParamTraceInfo,
          (unsigned int)L"No ConnObj",
          (unsigned int)&v21,
          0,
          (__int64)Buffer);
    }
    return 1168;
  }
}

```

## disassembly

```asm
0x180038bb4  push    rbp
0x180038bb6  push    rbx
0x180038bb7  push    rsi
0x180038bb8  push    rdi
0x180038bb9  lea     rbp, [rsp-2E68h]
0x180038bc1  mov     eax, 2F68h
0x180038bc6  call    _alloca_probe
0x180038bcb  sub     rsp, rax
0x180038bce  mov     rax, cs:__security_cookie
0x180038bd5  xor     rax, rsp
0x180038bd8  mov     [rbp+2E80h+var_30], rax
0x180038bdf  mov     rdi, rcx
0x180038be2  mov     [rsp+2F80h+Src], 0
0x180038beb  mov     [rsp+2F80h+var_2F38], 0
0x180038bf4  xor     edx, edx; Val
0x180038bf6  mov     r8d, 0AD8h; Size
0x180038bfc  lea     rcx, [rsp+2F80h+var_2F30]; void *
0x180038c01  call    memset_0
0x180038c06  mov     eax, [rdi+88h]
0x180038c0c  movzx   eax, ax
0x180038c0f  cmp     eax, 0Fh
0x180038c12  jnz     short loc_180038C1D
0x180038c14  lea     rsi, qword_1800C7518
0x180038c1b  jmp     short loc_180038C32
0x180038c1d  lea     rsi, qword_1800C7568
0x180038c24  lea     rcx, qword_1800C74C8
0x180038c2b  cmp     eax, 10h
0x180038c2e  cmovnz  rsi, rcx
0x180038c32  mov     [rbp+2E80h+var_2450], 0Ah
0x180038c3d  mov     [rbp+2E80h+var_2448], 0
0x180038c48  xor     edx, edx; Val
0x180038c4a  mov     r8d, 1BD0h; Size
0x180038c50  lea     rcx, [rbp+2E80h+var_2440]; void *
0x180038c57  call    memset_0
0x180038c5c  xor     eax, eax
0x180038c5e  mov     [rbp+2E80h+var_830], eax
0x180038c64  xor     edx, edx; Val
0x180038c66  mov     r8d, 7FCh; Size
0x180038c6c  lea     rcx, [rbp+2E80h+var_82C]; void *
0x180038c73  call    memset_0
0x180038c78  xor     eax, eax
0x180038c7a  mov     dword ptr [rbp+2E80h+Buffer], eax
0x180038c80  xorps   xmm0, xmm0
0x180038c83  movups  [rbp+2E80h+var_85C], xmm0
0x180038c8a  movups  [rbp+2E80h+var_84C], xmm0
0x180038c91  mov     [rbp+2E80h+var_83C], eax
0x180038c97  movups  [rbp+2E80h+var_870], xmm0
0x180038c9e  test    cs:byte_1800C8404, 10h
0x180038ca5  jz      loc_180038D33
0x180038cab  mov     word ptr [rbp+2E80h+var_830], ax
0x180038cb2  mov     [rbp+2E80h+Buffer], ax
0x180038cb9  mov     ecx, [rdi+60h]; Value
0x180038cbc  cmp     ecx, 0FFFFFFFFh
0x180038cbf  jz      short loc_180038CD6
0x180038cc1  lea     r9d, [rax+0Ah]; Radix
0x180038cc5  lea     r8d, [rax+14h]; BufferCount
0x180038cc9  lea     rdx, [rbp+2E80h+Buffer]; Buffer
0x180038cd0  call    cs:__imp__itow_s
0x180038cd6  mov     r9, [rdi+60h]
0x180038cda  lea     r8, aDdmdeviceSendi; "DdmDevice::SendInterfaceInfoToProtocolE"...
0x180038ce1  lea     rdx, aSHportLd; "%s (hport: %ld)"
0x180038ce8  lea     rcx, [rbp+2E80h+var_830]
0x180038cef  call    FormatRRASErrorString
0x180038cf4  test    cs:byte_1800C8404, 10h
0x180038cfb  jz      short loc_180038D33
0x180038cfd  lea     rax, [rbp+2E80h+Buffer]
0x180038d04  mov     [rsp+2F80h+var_2F58], rax
0x180038d09  mov     [rsp+2F80h+var_2F60], 0
0x180038d12  lea     r9, [rbp+2E80h+var_870]
0x180038d19  lea     r8, [rbp+2E80h+var_830]
0x180038d20  lea     rdx, RasDdmParamTraceInfo
0x180038d27  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180038d2e  call    McTemplateU0zjzz_EventWriteTransfer
0x180038d33  xor     edx, edx; Val
0x180038d35  mov     r8d, 0AE8h; Size
0x180038d3b  lea     rcx, [rsp+2F80h+Src]; void *
0x180038d40  call    memset_0
0x180038d45  mov     [rsp+2F80h+var_2F50], 0
0x180038d4e  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x180038d53  lea     r8, [rsp+2F80h+var_2F50]
0x180038d58  mov     rdx, [rdi+78h]
0x180038d5c  mov     rcx, rax
0x180038d5f  call    ?FindConnection@DdmConnectionTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmConnection@@@@@Z; DdmConnectionTable::FindConnection(void *,RasObjPtr<DdmConnection> &)
0x180038d64  mov     rbx, [rsp+2F80h+var_2F50]
0x180038d69  test    rbx, rbx
0x180038d6c  jnz     short loc_180038DEB
0x180038d6e  mov     dl, cs:byte_1800C8404
0x180038d74  test    dl, 10h
0x180038d77  jz      short loc_180038DE1
0x180038d79  xor     eax, eax
0x180038d7b  mov     [rbp+2E80h+Buffer], ax
0x180038d82  mov     ecx, [rdi+60h]; Value
0x180038d85  cmp     ecx, 0FFFFFFFFh
0x180038d88  jz      short loc_180038DA5
0x180038d8a  lea     r9d, [rbx+0Ah]; Radix
0x180038d8e  lea     r8d, [rbx+14h]; BufferCount
0x180038d92  lea     rdx, [rbp+2E80h+Buffer]; Buffer
0x180038d99  call    cs:__imp__itow_s
0x180038d9f  mov     dl, cs:byte_1800C8404
0x180038da5  test    dl, 10h
0x180038da8  jz      short loc_180038DE1
0x180038daa  lea     rax, [rbp+2E80h+Buffer]
0x180038db1  mov     [rsp+2F80h+var_2F58], rax
0x180038db6  mov     [rsp+2F80h+var_2F60], 0
0x180038dbf  lea     r9, [rbp+2E80h+var_870]
0x180038dc6  lea     r8, aNoConnobj; "No ConnObj"
0x180038dcd  lea     rdx, RasDdmParamTraceInfo
0x180038dd4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180038ddb  call    McTemplateU0zjzz_EventWriteTransfer
0x180038de0  nop
0x180038de1  mov     eax, 490h
0x180038de6  jmp     loc_180038EB5
0x180038deb  mov     rcx, cs:g_pIDimInterfaceTable
0x180038df2  mov     rax, [rcx]
0x180038df5  mov     rax, [rax]
0x180038df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038dfd  mov     rcx, cs:g_pIDimInterfaceTable
0x180038e04  mov     rax, [rcx]
0x180038e07  mov     rdx, [rbx+48h]
0x180038e0b  mov     rax, [rax+40h]
0x180038e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e14  mov     r8, rax
0x180038e17  test    rax, rax
0x180038e1a  jz      short loc_180038E33
0x180038e1c  mov     rcx, [rax]
0x180038e1f  mov     rax, [rcx+170h]
0x180038e26  lea     rdx, [rsp+2F80h+Src]
0x180038e2b  mov     rcx, r8
0x180038e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e33  mov     rcx, cs:g_pIDimInterfaceTable
0x180038e3a  mov     rax, [rcx]
0x180038e3d  mov     rax, [rax+10h]
0x180038e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e46  mov     rax, [rdi+78h]
0x180038e4a  mov     [rbp+2E80h+var_2440], rax
0x180038e51  mov     rax, [rdi+60h]
0x180038e55  mov     [rbp+2E80h+var_2448], rax
0x180038e5c  mov     dword ptr [rbp+2E80h+var_2450], 0Ah
0x180038e66  lea     rcx, [rbp+2E80h+var_2438]; void *
0x180038e6d  lea     rdx, [rsp+2F80h+Src]; Src
0x180038e72  mov     r8d, 0AE8h; Size
0x180038e78  call    memcpy_0
0x180038e7d  lea     rcx, [rbp+2E80h+var_2450]
0x180038e84  mov     rax, [rsi]
0x180038e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e8c  mov     edi, eax
0x180038e8e  or      edx, 0FFFFFFFFh
0x180038e91  lock xadd [rbx+8], edx
0x180038e96  cmp     edx, 1
0x180038e99  jnz     short loc_180038EB3
0x180038e9b  test    rbx, rbx
0x180038e9e  jz      short loc_180038EB3
0x180038ea0  mov     rdx, [rbx]
0x180038ea3  mov     rax, [rdx]
0x180038ea6  mov     edx, 1
0x180038eab  mov     rcx, rbx
0x180038eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038eb3  mov     eax, edi
0x180038eb5  mov     rcx, [rbp+2E80h+var_30]
0x180038ebc  xor     rcx, rsp; StackCookie
0x180038ebf  call    __security_check_cookie
0x180038ec4  add     rsp, 2F68h
0x180038ecb  pop     rdi
0x180038ecc  pop     rsi
0x180038ecd  pop     rbx
0x180038ece  pop     rbp
0x180038ecf  retn
```
