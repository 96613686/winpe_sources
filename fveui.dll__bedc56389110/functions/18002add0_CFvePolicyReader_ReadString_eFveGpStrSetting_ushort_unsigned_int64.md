# CFvePolicyReader::ReadString(eFveGpStrSetting,ushort * *,unsigned __int64 *)

- ea: `0x18002add0`
- end: `0x18002af2b`
- name: `?ReadString@CFvePolicyReader@@UEBAJW4eFveGpStrSetting@@PEAPEAGPEA_K@Z`
- size: `347`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callees

- `0x180002028`
- `0x1800022d8`
- `0x18002a99c`
- `0x18002add0`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18002ae5f`
- `ADVAPI32!RegGetValueW` at `0x18002aeed`
- `ADVAPI32!RegGetValueW` at `0x18002ae5f`
- `ADVAPI32!RegGetValueW` at `0x18002aeed`

## pseudocode

```c
__int64 __fastcall CFvePolicyReader::ReadString(__int64 a1, int a2, _QWORD *a3, unsigned __int64 *a4)
{
  __int64 v6; // rdi
  int KeyForGpLocation; // ebx
  const WCHAR *v8; // rsi
  LSTATUS ValueW; // eax
  unsigned __int64 v10; // rax
  void *pvData; // rdi
  LSTATUS v12; // eax
  unsigned __int64 v13; // rax
  DWORD pcbData; // [rsp+40h] [rbp-28h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-20h] BYREF
  HKEY hkey[3]; // [rsp+50h] [rbp-18h] BYREF
  DWORD v18; // [rsp+A8h] [rbp+40h] BYREF

  lpSubKey = 0;
  pcbData = 0;
  v18 = 0;
  v6 = 3LL * a2;
  hkey[0] = 0;
  KeyForGpLocation = CFvePolicyReader::GetKeyForGpLocation(a1, g_StringSettingMap[3 * a2], hkey, &lpSubKey);
  if ( KeyForGpLocation >= 0 )
  {
    v8 = (const WCHAR *)g_StringSettingMap[v6 + 1];
    ValueW = RegGetValueW(hkey[0], lpSubKey, v8, 2u, 0, 0, &pcbData);
    KeyForGpLocation = ValueW;
    if ( ValueW > 0 )
      KeyForGpLocation = (unsigned __int16)ValueW | 0x80070000;
    if ( KeyForGpLocation >= 0 )
    {
      if ( pcbData )
      {
        v18 = pcbData;
        v10 = 2 * ((unsigned __int64)pcbData >> 1);
        if ( !is_mul_ok((unsigned __int64)pcbData >> 1, 2u) )
          v10 = -1;
        pvData = operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
        if ( pvData )
        {
          v12 = RegGetValueW(hkey[0], lpSubKey, v8, 2u, 0, pvData, &v18);
          KeyForGpLocation = v12;
          if ( v12 > 0 )
            KeyForGpLocation = (unsigned __int16)v12 | 0x80070000;
          if ( KeyForGpLocation < 0 )
          {
            operator delete(pvData);
          }
          else
          {
            v13 = (unsigned __int64)v18 >> 1;
            *a3 = pvData;
            *a4 = v13;
          }
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
      else
      {
        return (unsigned int)-2147467259;
      }
    }
  }
  return (unsigned int)KeyForGpLocation;
}

```

## disassembly

```asm
0x18002add0  push    rbp
0x18002add2  push    rbx
0x18002add3  push    rsi
0x18002add4  push    rdi
0x18002add5  push    r14
0x18002add7  push    r15
0x18002add9  mov     rbp, rsp
0x18002addc  sub     rsp, 68h
0x18002ade0  movsxd  rax, edx
0x18002ade3  lea     rsi, ?g_StringSettingMap@@3QBU?$POLICY_REGISTRY_INFO@PEBG@@B; POLICY_REGISTRY_INFO<ushort const *> const near * const g_StringSettingMap
0x18002adea  mov     r14, r9
0x18002aded  mov     [rbp+lpSubKey], 0
0x18002adf5  mov     r15, r8
0x18002adf8  mov     [rbp+var_28], 0
0x18002adff  lea     r9, [rbp+lpSubKey]
0x18002ae03  mov     [rbp+arg_8], 0
0x18002ae0a  lea     rdi, [rax+rax*2]
0x18002ae0e  mov     [rbp+hkey], 0
0x18002ae16  mov     edx, [rsi+rdi*8]
0x18002ae19  lea     r8, [rbp+hkey]
0x18002ae1d  call    ?GetKeyForGpLocation@CFvePolicyReader@@AEBAJW4eFveGpSettingsLocation@@PEAPEAUHKEY__@@PEAPEBG@Z; CFvePolicyReader::GetKeyForGpLocation(eFveGpSettingsLocation,HKEY__ * *,ushort const * *)
0x18002ae22  mov     ebx, eax
0x18002ae24  test    eax, eax
0x18002ae26  js      loc_18002AF1C
0x18002ae2c  mov     rsi, [rsi+rdi*8+8]
0x18002ae31  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18002ae35  lea     rax, [rbp+var_28]
0x18002ae39  mov     rcx, [rbp+hkey]; hkey
0x18002ae3d  mov     edi, 2
0x18002ae42  mov     [rsp+68h+pcbData], rax; pcbData
0x18002ae47  mov     r9d, edi; dwFlags
0x18002ae4a  mov     [rsp+68h+pvData], 0; pvData
0x18002ae53  mov     r8, rsi; lpValue
0x18002ae56  mov     [rsp+68h+pdwType], 0; pdwType
0x18002ae5f  call    cs:__imp_RegGetValueW
0x18002ae65  mov     ebx, eax
0x18002ae67  test    eax, eax
0x18002ae69  jle     short loc_18002AE74
0x18002ae6b  movzx   ebx, ax
0x18002ae6e  or      ebx, 80070000h
0x18002ae74  test    ebx, ebx
0x18002ae76  js      loc_18002AF1C
0x18002ae7c  mov     eax, [rbp+var_28]
0x18002ae7f  test    eax, eax
0x18002ae81  jnz     short loc_18002AE8D
0x18002ae83  mov     ebx, 80004005h
0x18002ae88  jmp     loc_18002AF1C
0x18002ae8d  mov     rcx, rax
0x18002ae90  mov     [rbp+arg_8], eax
0x18002ae93  shr     rcx, 1
0x18002ae96  mov     rax, rdi
0x18002ae99  mul     rcx
0x18002ae9c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002aea3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002aeaa  cmovb   rax, rcx
0x18002aeae  mov     rcx, rax; unsigned __int64
0x18002aeb1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002aeb6  mov     rdi, rax
0x18002aeb9  test    rax, rax
0x18002aebc  jnz     short loc_18002AEC5
0x18002aebe  mov     ebx, 8007000Eh
0x18002aec3  jmp     short loc_18002AF1C
0x18002aec5  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18002aec9  lea     rax, [rbp+arg_8]
0x18002aecd  mov     rcx, [rbp+hkey]; hkey
0x18002aed1  mov     r9d, 2; dwFlags
0x18002aed7  mov     [rsp+68h+pcbData], rax; pcbData
0x18002aedc  mov     r8, rsi; lpValue
0x18002aedf  mov     [rsp+68h+pvData], rdi; pvData
0x18002aee4  mov     [rsp+68h+pdwType], 0; pdwType
0x18002aeed  call    cs:__imp_RegGetValueW
0x18002aef3  mov     ebx, eax
0x18002aef5  test    eax, eax
0x18002aef7  jle     short loc_18002AF02
0x18002aef9  movzx   ebx, ax
0x18002aefc  or      ebx, 80070000h
0x18002af02  test    ebx, ebx
0x18002af04  js      short loc_18002AF14
0x18002af06  mov     eax, [rbp+arg_8]
0x18002af09  shr     rax, 1
0x18002af0c  mov     [r15], rdi
0x18002af0f  mov     [r14], rax
0x18002af12  jmp     short loc_18002AF1C
0x18002af14  mov     rcx, rdi; Block
0x18002af17  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002af1c  mov     eax, ebx
0x18002af1e  add     rsp, 68h
0x18002af22  pop     r15
0x18002af24  pop     r14
0x18002af26  pop     rdi
0x18002af27  pop     rsi
0x18002af28  pop     rbx
0x18002af29  pop     rbp
0x18002af2a  retn
```
