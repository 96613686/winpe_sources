# MbaeDataRecord::Read(void)

- ea: `0x180055b6c`
- end: `0x180055c7b`
- name: `?Read@MbaeDataRecord@@QEAAJXZ`
- size: `271`
- prototype: `__int64 __fastcall(MbaeDataRecord *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002ddd4`

## callees

- `0x180055448`
- `0x180055470`
- `0x180055b6c`
- `0x180055dfc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180055bcf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180055bcf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055c39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055c39`

## pseudocode

```c
__int64 __fastcall MbaeDataRecord::Read(MbaeDataRecord *this)
{
  const WCHAR *v2; // rdx
  HKEY v3; // rcx
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  int Properties; // eax
  _QWORD *v7; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_9d123f00d685301e9656d03877f7f9ac_Traceguids);
  v2 = (const WCHAR *)*((_QWORD *)this + 1);
  v3 = *(HKEY *)this;
  hKey = 0;
  v4 = RegOpenKeyExW(v3, v2, 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_11;
  Properties = MbaeDataRecord::_ReadProperties(this, hKey);
  v5 = Properties;
  if ( Properties >= 0 )
    goto LABEL_11;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_9d123f00d685301e9656d03877f7f9ac_Traceguids,
      (unsigned int)Properties);
LABEL_11:
    v7 = WPP_GLOBAL_Control;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
    WPP_SF_d(v7[2], 15, WPP_9d123f00d685301e9656d03877f7f9ac_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180055b6c  mov     [rsp+arg_8], rbx
0x180055b71  mov     [rsp+arg_10], rsi
0x180055b76  push    rdi
0x180055b77  sub     rsp, 30h
0x180055b7b  mov     rdi, rcx
0x180055b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180055b85  lea     rsi, WPP_GLOBAL_Control
0x180055b8c  cmp     rcx, rsi
0x180055b8f  jz      short loc_180055BAC
0x180055b91  test    byte ptr [rcx+1Ch], 10h
0x180055b95  jz      short loc_180055BAC
0x180055b97  mov     rcx, [rcx+10h]
0x180055b9b  lea     r8, WPP_9d123f00d685301e9656d03877f7f9ac_Traceguids
0x180055ba2  mov     edx, 0Dh
0x180055ba7  call    WPP_SF_
0x180055bac  mov     rdx, [rdi+8]; lpSubKey
0x180055bb0  lea     rax, [rsp+38h+hKey]
0x180055bb5  mov     rcx, [rdi]; hKey
0x180055bb8  mov     r9d, 20019h; samDesired
0x180055bbe  xor     r8d, r8d; ulOptions
0x180055bc1  mov     [rsp+38h+phkResult], rax; phkResult
0x180055bc6  mov     [rsp+38h+hKey], 0
0x180055bcf  call    cs:__imp_RegOpenKeyExW
0x180055bd5  mov     ebx, eax
0x180055bd7  test    eax, eax
0x180055bd9  jle     short loc_180055BE4
0x180055bdb  movzx   ebx, ax
0x180055bde  or      ebx, 80070000h
0x180055be4  test    ebx, ebx
0x180055be6  js      short loc_180055C25
0x180055be8  mov     rdx, [rsp+38h+hKey]; HKEY
0x180055bed  mov     rcx, rdi; this
0x180055bf0  call    ?_ReadProperties@MbaeDataRecord@@IEAAJPEAUHKEY__@@@Z; MbaeDataRecord::_ReadProperties(HKEY__ *)
0x180055bf5  mov     ebx, eax
0x180055bf7  test    eax, eax
0x180055bf9  jns     short loc_180055C25
0x180055bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180055c02  cmp     rcx, rsi
0x180055c05  jz      short loc_180055C2C
0x180055c07  test    byte ptr [rcx+1Ch], 8
0x180055c0b  jz      short loc_180055C2C
0x180055c0d  mov     rcx, [rcx+10h]
0x180055c11  lea     r8, WPP_9d123f00d685301e9656d03877f7f9ac_Traceguids
0x180055c18  mov     edx, 0Eh
0x180055c1d  mov     r9d, eax
0x180055c20  call    WPP_SF_d
0x180055c25  mov     rcx, cs:WPP_GLOBAL_Control
0x180055c2c  mov     rax, [rsp+38h+hKey]
0x180055c31  test    rax, rax
0x180055c34  jz      short loc_180055C46
0x180055c36  mov     rcx, rax; hKey
0x180055c39  call    cs:__imp_RegCloseKey
0x180055c3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180055c46  cmp     rcx, rsi
0x180055c49  jz      short loc_180055C69
0x180055c4b  test    byte ptr [rcx+1Ch], 10h
0x180055c4f  jz      short loc_180055C69
0x180055c51  mov     rcx, [rcx+10h]
0x180055c55  lea     r8, WPP_9d123f00d685301e9656d03877f7f9ac_Traceguids
0x180055c5c  mov     edx, 0Fh
0x180055c61  mov     r9d, ebx
0x180055c64  call    WPP_SF_d
0x180055c69  mov     rsi, [rsp+38h+arg_10]
0x180055c6e  mov     eax, ebx
0x180055c70  mov     rbx, [rsp+38h+arg_8]
0x180055c75  add     rsp, 30h
0x180055c79  pop     rdi
0x180055c7a  retn
```
