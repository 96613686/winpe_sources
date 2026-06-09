# SnapinRecord::GetCOMRegistrationInformation(ushort const *)

- ea: `0x180010d70`
- end: `0x180010fac`
- name: `?GetCOMRegistrationInformation@SnapinRecord@@AEAAJPEBG@Z`
- size: `572`
- prototype: `__int64 __fastcall(SnapinRecord *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006d04`

## callees

- `0x180006730`
- `0x18000715c`
- `0x180007310`
- `0x18000cfbc`
- `0x180010d70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010e1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010e1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f97`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f97`

## string_xrefs

- `0x180010db6`: `CLSID\%s\InprocServer32`

## pseudocode

```c
__int64 __fastcall SnapinRecord::GetCOMRegistrationInformation(SnapinRecord *this, const unsigned __int16 *a2)
{
  int v2; // esi
  int v4; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  int ValueW; // eax
  int v8; // eax
  int v9; // eax
  void **v11; // [rsp+30h] [rbp-28h] BYREF
  LPCWSTR lpSubKey; // [rsp+38h] [rbp-20h]
  __int64 v13; // [rsp+40h] [rbp-18h]
  int v14; // [rsp+48h] [rbp-10h]
  HKEY hKey; // [rsp+A0h] [rbp+48h] BYREF

  v2 = (int)a2;
  hKey = 0;
  v11 = &CStr::`vftable';
  lpSubKey = (LPCWSTR)&CStr::s_rgwchEmptyStringBuffer;
  v13 = 0;
  v14 = 0;
  v4 = CStr::Format((CStr *)&v11, L"CLSID\\%s\\InprocServer32", a2);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = RegOpenKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0x20019u, &hKey);
    v5 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          16,
          (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
          (_DWORD)lpSubKey,
          v5);
    }
    else
    {
      ValueW = SnapinRecord::RegGetValueW(this, hKey, 0, (unsigned __int16 *)this + 532, 0x80u, 0);
      if ( ValueW < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
      {
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          13,
          (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
          v2,
          ValueW);
      }
      v8 = SnapinRecord::RegGetValueW(this, hKey, L"RuntimeVersion", (unsigned __int16 *)this + 788, 0x80u, 2u);
      if ( v8 < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
      {
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          14,
          (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
          v2,
          v8);
      }
      v9 = SnapinRecord::RegGetValueW(this, hKey, L"Assembly", (unsigned __int16 *)this + 660, 0x80u, 2u);
      if ( v9 < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
      {
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          15,
          (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
          v2,
          v9);
      }
      v5 = 1;
    }
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u )
  {
    WPP_SF_Sd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      12,
      (unsigned int)WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids,
      v2,
      v4);
  }
  v11 = &CStr::`vftable';
  CStr::Empty((CStr *)&v11);
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180010d70  push    rbp
0x180010d72  push    rbx
0x180010d73  push    rsi
0x180010d74  push    rdi
0x180010d75  push    r12
0x180010d77  push    r14
0x180010d79  mov     rbp, rsp
0x180010d7c  sub     rsp, 58h
0x180010d80  mov     rsi, rdx
0x180010d83  mov     r14, rcx
0x180010d86  mov     [rbp+hKey], 0
0x180010d8e  lea     r12, ??_7CStr@@6B@; const CStr::`vftable'
0x180010d95  mov     [rbp+var_28], r12
0x180010d99  lea     rax, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x180010da0  mov     [rbp+lpSubKey], rax
0x180010da4  mov     [rbp+var_18], 0
0x180010dac  mov     [rbp+var_10], 0
0x180010db3  mov     r8, rdx
0x180010db6  lea     rdx, aClsidSInprocse; "CLSID\\%s\\InprocServer32"
0x180010dbd  lea     rcx, [rbp+var_28]; this
0x180010dc1  call    ?Format@CStr@@QEAAJPEBGZZ; CStr::Format(ushort const *,...)
0x180010dc6  mov     ebx, eax
0x180010dc8  test    eax, eax
0x180010dca  jns     short loc_180010DFE
0x180010dcc  lea     rdi, WPP_GLOBAL_Control
0x180010dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180010dda  cmp     rcx, rdi
0x180010ddd  jz      loc_180010F81
0x180010de3  cmp     byte ptr [rcx+19h], 3
0x180010de7  jb      loc_180010F81
0x180010ded  mov     edx, 0Ch
0x180010df2  mov     dword ptr [rsp+58h+phkResult], eax
0x180010df6  mov     r9, rsi
0x180010df9  jmp     loc_180010F70
0x180010dfe  lea     rax, [rbp+hKey]
0x180010e02  mov     [rsp+58h+phkResult], rax; phkResult
0x180010e07  mov     r9d, 20019h; samDesired
0x180010e0d  xor     r8d, r8d; ulOptions
0x180010e10  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180010e14  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180010e1b  call    cs:__imp_RegOpenKeyExW
0x180010e21  mov     ebx, eax
0x180010e23  test    eax, eax
0x180010e25  jnz     loc_180010F3F
0x180010e2b  lea     r9, [r14+428h]; unsigned __int16 *
0x180010e32  mov     [rsp+58h+var_30], eax; unsigned int
0x180010e36  mov     ebx, 80h
0x180010e3b  mov     [rsp+58h+phkResult], rbx; unsigned __int64
0x180010e40  xor     r8d, r8d; unsigned __int16 *
0x180010e43  mov     rdx, [rbp+hKey]; HKEY
0x180010e47  mov     rcx, r14; this
0x180010e4a  call    ?RegGetValueW@SnapinRecord@@AEAAJPEAUHKEY__@@PEBGPEAG_KK@Z; SnapinRecord::RegGetValueW(HKEY__ *,ushort const *,ushort *,unsigned __int64,ulong)
0x180010e4f  lea     rdi, WPP_GLOBAL_Control
0x180010e56  test    eax, eax
0x180010e58  jns     short loc_180010E86
0x180010e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e61  cmp     rcx, rdi
0x180010e64  jz      short loc_180010E86
0x180010e66  cmp     byte ptr [rcx+19h], 3
0x180010e6a  jb      short loc_180010E86
0x180010e6c  lea     edx, [rbx-73h]
0x180010e6f  mov     dword ptr [rsp+58h+phkResult], eax
0x180010e73  mov     r9, rsi
0x180010e76  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180010e7d  mov     rcx, [rcx+10h]
0x180010e81  call    WPP_SF_Sd
0x180010e86  lea     r9, [r14+628h]; unsigned __int16 *
0x180010e8d  mov     [rsp+58h+var_30], 2; unsigned int
0x180010e95  mov     [rsp+58h+phkResult], rbx; unsigned __int64
0x180010e9a  lea     r8, aRuntimeversion; "RuntimeVersion"
0x180010ea1  mov     rdx, [rbp+hKey]; HKEY
0x180010ea5  mov     rcx, r14; this
0x180010ea8  call    ?RegGetValueW@SnapinRecord@@AEAAJPEAUHKEY__@@PEBGPEAG_KK@Z; SnapinRecord::RegGetValueW(HKEY__ *,ushort const *,ushort *,unsigned __int64,ulong)
0x180010ead  test    eax, eax
0x180010eaf  jns     short loc_180010EDF
0x180010eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180010eb8  cmp     rcx, rdi
0x180010ebb  jz      short loc_180010EDF
0x180010ebd  cmp     byte ptr [rcx+19h], 5
0x180010ec1  jb      short loc_180010EDF
0x180010ec3  mov     edx, 0Eh
0x180010ec8  mov     dword ptr [rsp+58h+phkResult], eax
0x180010ecc  mov     r9, rsi
0x180010ecf  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180010ed6  mov     rcx, [rcx+10h]
0x180010eda  call    WPP_SF_Sd
0x180010edf  lea     r9, [r14+528h]; unsigned __int16 *
0x180010ee6  mov     [rsp+58h+var_30], 2; unsigned int
0x180010eee  mov     [rsp+58h+phkResult], rbx; unsigned __int64
0x180010ef3  lea     r8, aAssembly; "Assembly"
0x180010efa  mov     rdx, [rbp+hKey]; HKEY
0x180010efe  mov     rcx, r14; this
0x180010f01  call    ?RegGetValueW@SnapinRecord@@AEAAJPEAUHKEY__@@PEBGPEAG_KK@Z; SnapinRecord::RegGetValueW(HKEY__ *,ushort const *,ushort *,unsigned __int64,ulong)
0x180010f06  test    eax, eax
0x180010f08  jns     short loc_180010F38
0x180010f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f11  cmp     rcx, rdi
0x180010f14  jz      short loc_180010F38
0x180010f16  cmp     byte ptr [rcx+19h], 5
0x180010f1a  jb      short loc_180010F38
0x180010f1c  mov     edx, 0Fh
0x180010f21  mov     dword ptr [rsp+58h+phkResult], eax
0x180010f25  mov     r9, rsi
0x180010f28  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180010f2f  mov     rcx, [rcx+10h]
0x180010f33  call    WPP_SF_Sd
0x180010f38  mov     ebx, 1
0x180010f3d  jmp     short loc_180010F81
0x180010f3f  jle     short loc_180010F4A
0x180010f41  movzx   ebx, ax
0x180010f44  or      ebx, 80070000h
0x180010f4a  lea     rdi, WPP_GLOBAL_Control
0x180010f51  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f58  cmp     rcx, rdi
0x180010f5b  jz      short loc_180010F81
0x180010f5d  cmp     byte ptr [rcx+19h], 3
0x180010f61  jb      short loc_180010F81
0x180010f63  mov     edx, 10h
0x180010f68  mov     dword ptr [rsp+58h+phkResult], ebx
0x180010f6c  mov     r9, [rbp+lpSubKey]
0x180010f70  lea     r8, WPP_a70e0d426fb9324c3ac285f554f0ec1d_Traceguids
0x180010f77  mov     rcx, [rcx+10h]
0x180010f7b  call    WPP_SF_Sd
0x180010f80  nop
0x180010f81  mov     [rbp+var_28], r12
0x180010f85  lea     rcx, [rbp+var_28]; this
0x180010f89  call    ?Empty@CStr@@QEAAXXZ; CStr::Empty(void)
0x180010f8e  mov     rcx, [rbp+hKey]; hKey
0x180010f92  test    rcx, rcx
0x180010f95  jz      short loc_180010F9D
0x180010f97  call    cs:__imp_RegCloseKey
0x180010f9d  mov     eax, ebx
0x180010f9f  add     rsp, 58h
0x180010fa3  pop     r14
0x180010fa5  pop     r12
0x180010fa7  pop     rdi
0x180010fa8  pop     rsi
0x180010fa9  pop     rbx
0x180010faa  pop     rbp
0x180010fab  retn
```
