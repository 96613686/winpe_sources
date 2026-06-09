# CPnpxPairingHandler::StampDevNodeAsNotPaired(void)

- ea: `0x18000ed14`
- end: `0x18000f018`
- name: `?StampDevNodeAsNotPaired@CPnpxPairingHandler@@IEAAJXZ`
- size: `772`
- prototype: `__int64 __fastcall(CPnpxPairingHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000e9d0`

## callees

- `0x18000bc18`
- `0x18000bce4`
- `0x18000bd30`
- `0x18000ed14`
- `0x18000f198`
- `0x180012e00`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ee55`
- `KERNEL32!GetLastError` at `0x18000eee1`
- `KERNEL32!GetLastError` at `0x18000ef44`
- `KERNEL32!GetLastError` at `0x18000ee55`
- `KERNEL32!GetLastError` at `0x18000eee1`
- `KERNEL32!GetLastError` at `0x18000ef44`
- `ole32!PropVariantClear` at `0x18000ef8c`
- `ole32!PropVariantClear` at `0x18000ef96`
- `ole32!PropVariantClear` at `0x18000ef8c`
- `ole32!PropVariantClear` at `0x18000ef96`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18000ee40`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18000ee40`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18000eed7`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x18000eed7`
- `DEVOBJ!DevObjSetDeviceProperty` at `0x18000ef3a`
- `DEVOBJ!DevObjSetDeviceProperty` at `0x18000ef3a`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18000ef74`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18000ef74`

## pseudocode

```c
__int64 __fastcall CPnpxPairingHandler::StampDevNodeAsNotPaired(CPnpxPairingHandler *this)
{
  __int64 v2; // rcx
  signed int RootDevNode; // ebx
  __int64 DeviceInfoList; // rdi
  int v5; // r9d
  signed int LastError; // eax
  bool v7; // zf
  int v8; // eax
  bool v9; // cf
  _BYTE v11[8]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v12; // [rsp+48h] [rbp-31h] BYREF
  struct tagPROPVARIANT v13; // [rsp+50h] [rbp-29h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+68h] [rbp-11h] BYREF
  _OWORD v15[3]; // [rsp+80h] [rbp+7h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
  v2 = *((_QWORD *)this + 10);
  v12 = 0;
  memset(&pvar, 0, sizeof(pvar));
  memset(&v13, 0, sizeof(v13));
  RootDevNode = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v2 + 48LL))(v2, 0, &v12);
  if ( !RootDevNode )
  {
    RootDevNode = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)v12 + 40LL))(
                    v12,
                    &PKEY_PNPX_GlobalIdentity,
                    &pvar);
    if ( !RootDevNode )
    {
      if ( pvar.vt == 31 && pvar.hVal.QuadPart )
      {
        RootDevNode = GetRootDevNode(&pvar, &v13);
        if ( RootDevNode || v13.vt != 31 || !v13.hVal.QuadPart )
          goto LABEL_35;
        v11[0] = 0;
        memset(v15, 0, sizeof(v15));
        DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
        if ( DeviceInfoList == -1 )
        {
          LastError = GetLastError();
          RootDevNode = LastError;
          if ( (LastError & 0xE0000000) == 0xE0000000 )
          {
            RootDevNode = (unsigned __int16)LastError | 0x800F0000;
          }
          else if ( LastError > 0 )
          {
            RootDevNode = (unsigned __int16)LastError | 0x80070000;
          }
          if ( RootDevNode )
          {
LABEL_33:
            DevObjDestroyDeviceInfoList(DeviceInfoList);
            goto LABEL_35;
          }
        }
        LODWORD(v15[0]) = 48;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_sS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            (unsigned int)&WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids,
            v5,
            v13.hVal.QuadPart);
        if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))DevObjOpenDeviceInfo)(
                             DeviceInfoList,
                             (LARGE_INTEGER)v13.hVal.QuadPart,
                             0,
                             0,
                             v15) )
        {
LABEL_27:
          if ( !(unsigned int)DevObjSetDeviceProperty(DeviceInfoList, v15, &PKEY_DeviceDisplay_IsPaired, 17, v11, 1, 0) )
          {
            RootDevNode = GetLastError();
            if ( (RootDevNode & 0xE0000000) == 0xE0000000 )
            {
              RootDevNode = (unsigned __int16)RootDevNode | 0x800F0000;
            }
            else if ( RootDevNode > 0 )
            {
              RootDevNode = (unsigned __int16)RootDevNode | 0x80070000;
            }
          }
LABEL_32:
          if ( !DeviceInfoList )
            goto LABEL_35;
          goto LABEL_33;
        }
        RootDevNode = GetLastError();
        if ( (RootDevNode & 0xE0000000) == 0xE0000000 )
        {
          RootDevNode = (unsigned __int16)RootDevNode | 0x800F0000;
        }
        else
        {
          v7 = RootDevNode == 0;
          if ( RootDevNode <= 0 )
            goto LABEL_26;
          RootDevNode = (unsigned __int16)RootDevNode | 0x80070000;
        }
        v7 = RootDevNode == 0;
LABEL_26:
        if ( !v7 )
          goto LABEL_32;
        goto LABEL_27;
      }
      RootDevNode = -2147467259;
    }
  }
LABEL_35:
  PropVariantClear((PROPVARIANT *)&pvar);
  PropVariantClear((PROPVARIANT *)&v13);
  v8 = 0;
  if ( RootDevNode )
    v9 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v9 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v8) = !v9;
    if ( v8 )
      WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids);
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)RootDevNode;
}

```

## disassembly

```asm
0x18000ed14  mov     [rsp-8+arg_8], rbx
0x18000ed19  mov     [rsp-8+arg_10], rsi
0x18000ed1e  push    rbp
0x18000ed1f  push    rdi
0x18000ed20  push    r15
0x18000ed22  lea     rbp, [rsp-47h]
0x18000ed27  sub     rsp, 0C0h
0x18000ed2e  mov     rax, cs:__security_cookie
0x18000ed35  xor     rax, rsp
0x18000ed38  mov     [rbp+57h+var_20], rax
0x18000ed3c  mov     rsi, rcx
0x18000ed3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed46  lea     rdi, WPP_GLOBAL_Control
0x18000ed4d  cmp     rcx, rdi
0x18000ed50  jz      short loc_18000ED72
0x18000ed52  cmp     byte ptr [rcx+19h], 4
0x18000ed56  jb      short loc_18000ED72
0x18000ed58  mov     rcx, [rcx+10h]
0x18000ed5c  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000ed63  mov     edx, 2Fh ; '/'
0x18000ed68  mov     [rsp+0D0h+var_B0], rsi
0x18000ed6d  call    WPP_SF_sq
0x18000ed72  mov     rcx, [rsi+50h]
0x18000ed76  lea     r8, [rbp+57h+var_88]
0x18000ed7a  xor     eax, eax
0x18000ed7c  mov     [rbp+57h+var_88], 0
0x18000ed84  mov     [rbp+57h+var_58], rax
0x18000ed88  xorps   xmm0, xmm0
0x18000ed8b  mov     [rbp+57h+var_70], rax
0x18000ed8f  xorps   xmm1, xmm1
0x18000ed92  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000ed96  xor     edx, edx
0x18000ed98  movups  xmmword ptr [rbp+57h+var_80], xmm1
0x18000ed9c  mov     rax, [rcx]
0x18000ed9f  mov     rax, [rax+30h]
0x18000eda3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eda8  mov     ebx, eax
0x18000edaa  test    eax, eax
0x18000edac  jnz     loc_18000EF88
0x18000edb2  mov     rcx, [rbp+57h+var_88]
0x18000edb6  lea     r8, [rbp+57h+pvar]
0x18000edba  lea     rdx, PKEY_PNPX_GlobalIdentity
0x18000edc1  mov     rax, [rcx]
0x18000edc4  mov     rax, [rax+28h]
0x18000edc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edcd  mov     ebx, eax
0x18000edcf  test    eax, eax
0x18000edd1  jnz     loc_18000EF88
0x18000edd7  lea     edi, [rax+1Fh]
0x18000edda  cmp     di, word ptr [rbp+57h+pvar]
0x18000edde  jnz     loc_18000EF7C
0x18000ede4  cmp     [rbp+57h+pvar+8], 0
0x18000ede9  jz      loc_18000EF7C
0x18000edef  lea     rdx, [rbp+57h+var_80]; struct tagPROPVARIANT *
0x18000edf3  lea     rcx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x18000edf7  call    ?GetRootDevNode@@YAJAEBUtagPROPVARIANT@@PEAU1@@Z; GetRootDevNode(tagPROPVARIANT const &,tagPROPVARIANT *)
0x18000edfc  mov     ebx, eax
0x18000edfe  test    eax, eax
0x18000ee00  jnz     loc_18000EF81
0x18000ee06  cmp     di, word ptr [rbp+57h+var_80]
0x18000ee0a  jnz     loc_18000EF81
0x18000ee10  cmp     [rbp+57h+var_80+8], 0
0x18000ee15  jz      loc_18000EF81
0x18000ee1b  xorps   xmm0, xmm0
0x18000ee1e  mov     [rbp+57h+var_90], al
0x18000ee21  xor     r9d, r9d
0x18000ee24  mov     [rsp+0D0h+var_B0], 0
0x18000ee2d  xor     r8d, r8d
0x18000ee30  xor     edx, edx
0x18000ee32  xor     ecx, ecx
0x18000ee34  movups  [rbp+57h+var_50], xmm0
0x18000ee38  movups  [rbp+57h+var_40], xmm0
0x18000ee3c  movups  [rbp+57h+var_30], xmm0
0x18000ee40  call    cs:__imp_DevObjCreateDeviceInfoList
0x18000ee46  mov     rdi, rax
0x18000ee49  mov     r15d, 0E0000000h
0x18000ee4f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ee53  jnz     short loc_18000EE87
0x18000ee55  call    cs:__imp_GetLastError
0x18000ee5b  mov     ecx, eax
0x18000ee5d  mov     ebx, eax
0x18000ee5f  and     ecx, r15d
0x18000ee62  cmp     ecx, r15d
0x18000ee65  jnz     short loc_18000EE72
0x18000ee67  movzx   ebx, ax
0x18000ee6a  or      ebx, 800F0000h
0x18000ee70  jmp     short loc_18000EE7F
0x18000ee72  test    eax, eax
0x18000ee74  jle     short loc_18000EE7F
0x18000ee76  movzx   ebx, ax
0x18000ee79  or      ebx, 80070000h
0x18000ee7f  test    ebx, ebx
0x18000ee81  jnz     loc_18000EF71
0x18000ee87  mov     edx, 30h ; '0'
0x18000ee8c  mov     dword ptr [rbp+57h+var_50], edx
0x18000ee8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee96  lea     rax, WPP_GLOBAL_Control
0x18000ee9d  cmp     rcx, rax
0x18000eea0  jz      short loc_18000EEC1
0x18000eea2  cmp     byte ptr [rcx+19h], 4
0x18000eea6  jb      short loc_18000EEC1
0x18000eea8  mov     rax, [rbp+57h+var_80+8]
0x18000eeac  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000eeb3  mov     rcx, [rcx+10h]
0x18000eeb7  mov     [rsp+0D0h+var_B0], rax
0x18000eebc  call    WPP_SF_sS
0x18000eec1  mov     rdx, [rbp+57h+var_80+8]
0x18000eec5  lea     rax, [rbp+57h+var_50]
0x18000eec9  xor     r9d, r9d
0x18000eecc  mov     [rsp+0D0h+var_B0], rax
0x18000eed1  xor     r8d, r8d
0x18000eed4  mov     rcx, rdi
0x18000eed7  call    cs:__imp_DevObjOpenDeviceInfo
0x18000eedd  test    eax, eax
0x18000eedf  jnz     short loc_18000EF0D
0x18000eee1  call    cs:__imp_GetLastError
0x18000eee7  mov     ebx, eax
0x18000eee9  and     eax, r15d
0x18000eeec  cmp     eax, r15d
0x18000eeef  jnz     short loc_18000EEFC
0x18000eef1  movzx   ebx, bx
0x18000eef4  or      ebx, 800F0000h
0x18000eefa  jmp     short loc_18000EF09
0x18000eefc  test    ebx, ebx
0x18000eefe  jle     short loc_18000EF0B
0x18000ef00  movzx   ebx, bx
0x18000ef03  or      ebx, 80070000h
0x18000ef09  test    ebx, ebx
0x18000ef0b  jnz     short loc_18000EF6C
0x18000ef0d  mov     [rsp+0D0h+var_A0], 0
0x18000ef15  lea     rax, [rbp+57h+var_90]
0x18000ef19  mov     [rsp+0D0h+var_A8], 1
0x18000ef21  lea     r8, PKEY_DeviceDisplay_IsPaired
0x18000ef28  mov     r9d, 11h
0x18000ef2e  mov     [rsp+0D0h+var_B0], rax
0x18000ef33  lea     rdx, [rbp+57h+var_50]
0x18000ef37  mov     rcx, rdi
0x18000ef3a  call    cs:__imp_DevObjSetDeviceProperty
0x18000ef40  test    eax, eax
0x18000ef42  jnz     short loc_18000EF6C
0x18000ef44  call    cs:__imp_GetLastError
0x18000ef4a  mov     ebx, eax
0x18000ef4c  and     eax, r15d
0x18000ef4f  cmp     eax, r15d
0x18000ef52  jnz     short loc_18000EF5F
0x18000ef54  movzx   ebx, bx
0x18000ef57  or      ebx, 800F0000h
0x18000ef5d  jmp     short loc_18000EF6C
0x18000ef5f  test    ebx, ebx
0x18000ef61  jle     short loc_18000EF6C
0x18000ef63  movzx   ebx, bx
0x18000ef66  or      ebx, 80070000h
0x18000ef6c  test    rdi, rdi
0x18000ef6f  jz      short loc_18000EF81
0x18000ef71  mov     rcx, rdi
0x18000ef74  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18000ef7a  jmp     short loc_18000EF81
0x18000ef7c  mov     ebx, 80004005h
0x18000ef81  lea     rdi, WPP_GLOBAL_Control
0x18000ef88  lea     rcx, [rbp+57h+pvar]; pvar
0x18000ef8c  call    cs:__imp_PropVariantClear
0x18000ef92  lea     rcx, [rbp+57h+var_80]; pvar
0x18000ef96  call    cs:__imp_PropVariantClear
0x18000ef9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efa3  xor     eax, eax
0x18000efa5  test    ebx, ebx
0x18000efa7  jnz     short loc_18000EFAF
0x18000efa9  cmp     byte ptr [rcx+19h], 4
0x18000efad  jmp     short loc_18000EFB3
0x18000efaf  cmp     byte ptr [rcx+19h], 2
0x18000efb3  setnb   al
0x18000efb6  cmp     rcx, rdi
0x18000efb9  jz      short loc_18000EFDD
0x18000efbb  test    eax, eax
0x18000efbd  jz      short loc_18000EFDD
0x18000efbf  mov     rcx, [rcx+10h]
0x18000efc3  lea     r8, WPP_160efe8b59ab37eb2e928118d3f1133b_Traceguids
0x18000efca  mov     edx, 31h ; '1'
0x18000efcf  mov     [rsp+0D0h+var_A8], ebx
0x18000efd3  mov     [rsp+0D0h+var_B0], rsi
0x18000efd8  call    WPP_SF_sqd
0x18000efdd  mov     rcx, [rbp+57h+var_88]
0x18000efe1  test    rcx, rcx
0x18000efe4  jz      short loc_18000EFF2
0x18000efe6  mov     rax, [rcx]
0x18000efe9  mov     rax, [rax+10h]
0x18000efed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eff2  mov     eax, ebx
0x18000eff4  mov     rcx, [rbp+57h+var_20]
0x18000eff8  xor     rcx, rsp; StackCookie
0x18000effb  call    __security_check_cookie
0x18000f000  lea     r11, [rsp+0D0h+var_10]
0x18000f008  mov     rbx, [r11+28h]
0x18000f00c  mov     rsi, [r11+30h]
0x18000f010  mov     rsp, r11
0x18000f013  pop     r15
0x18000f015  pop     rdi
0x18000f016  pop     rbp
0x18000f017  retn
```
