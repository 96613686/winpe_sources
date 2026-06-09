# RegistryPropertyBag::EncryptedStringProperty::Write(HKEY__ *)

- ea: `0x180056ddc`
- end: `0x180056f02`
- name: `?Write@EncryptedStringProperty@RegistryPropertyBag@@MEAAJPEAUHKEY__@@@Z`
- size: `294`
- prototype: `int(RegistryPropertyBag::EncryptedStringProperty *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180055dc0`

## callees

- `0x180055448`
- `0x180055470`
- `0x180056ddc`
- `0x1800574d4`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x180056e44`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180056e44`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180056ea3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180056ea3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056ec0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056ec0`

## pseudocode

```c
__int64 __fastcall RegistryPropertyBag::EncryptedStringProperty::Write(
        RegistryPropertyBag::EncryptedStringProperty *this,
        HKEY a2)
{
  _QWORD *v4; // rcx
  OLECHAR *v5; // rcx
  UINT v6; // eax
  RegistryPropertyBag::EncryptedStringProperty *v7; // rcx
  int v8; // eax
  BYTE *lpData; // rdi
  int v10; // eax
  HLOCAL hMem; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 cbData; // [rsp+60h] [rbp+18h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( *((_BYTE *)this + 8) )
  {
    v5 = (OLECHAR *)*((_QWORD *)this + 2);
    cbData = 0;
    hMem = 0;
    v6 = SysStringByteLen(v5);
    v8 = RegistryPropertyBag::EncryptedStringProperty::_Encrypt(
           v7,
           v6 + 2LL,
           *((unsigned __int8 **)this + 2),
           &cbData,
           (unsigned __int8 **)&hMem);
    lpData = (BYTE *)hMem;
    *((_DWORD *)this + 7) = v8;
    if ( v8 >= 0 )
    {
      if ( cbData <= 0x1000 )
      {
        v10 = RegSetValueExW(a2, *((LPCWSTR *)this + 4), 0, 3u, lpData, cbData);
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        *((_DWORD *)this + 7) = v10;
      }
      else
      {
        *((_DWORD *)this + 7) = -2147024883;
      }
    }
    if ( lpData )
      LocalFree(lpData);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x10) != 0 )
    WPP_SF_d(v4[2], 19, &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids, *((unsigned int *)this + 7));
  return *((unsigned int *)this + 7);
}

```

## disassembly

```asm
0x180056ddc  mov     [rsp+arg_8], rbx
0x180056de1  push    rsi
0x180056de2  push    rdi
0x180056de3  push    r14
0x180056de5  sub     rsp, 30h
0x180056de9  mov     rsi, rdx
0x180056dec  mov     rbx, rcx
0x180056def  mov     rcx, cs:WPP_GLOBAL_Control
0x180056df6  lea     r14, WPP_GLOBAL_Control
0x180056dfd  cmp     rcx, r14
0x180056e00  jz      short loc_180056E24
0x180056e02  test    byte ptr [rcx+1Ch], 10h
0x180056e06  jz      short loc_180056E24
0x180056e08  mov     rcx, [rcx+10h]
0x180056e0c  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x180056e13  mov     edx, 12h
0x180056e18  call    WPP_SF_
0x180056e1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056e24  cmp     byte ptr [rbx+8], 0
0x180056e28  jz      loc_180056ECD
0x180056e2e  mov     rcx, [rbx+10h]; bstr
0x180056e32  mov     [rsp+48h+arg_10], 0
0x180056e3b  mov     [rsp+48h+hMem], 0
0x180056e44  call    cs:__imp_SysStringByteLen
0x180056e4a  mov     r8, [rbx+10h]; unsigned __int8 *
0x180056e4e  lea     r9, [rsp+48h+arg_10]; unsigned __int64 *
0x180056e53  mov     edx, eax
0x180056e55  lea     rax, [rsp+48h+hMem]
0x180056e5a  add     rdx, 2; unsigned __int64
0x180056e5e  mov     [rsp+48h+lpData], rax; unsigned __int8 **
0x180056e63  call    ?_Encrypt@EncryptedStringProperty@RegistryPropertyBag@@AEAAJ_KPEAEPEA_KPEAPEAE@Z; RegistryPropertyBag::EncryptedStringProperty::_Encrypt(unsigned __int64,uchar *,unsigned __int64 *,uchar * *)
0x180056e68  mov     rdi, [rsp+48h+hMem]
0x180056e6d  mov     [rbx+1Ch], eax
0x180056e70  test    eax, eax
0x180056e72  js      short loc_180056EB8
0x180056e74  mov     rax, [rsp+48h+arg_10]
0x180056e79  cmp     rax, 1000h
0x180056e7f  jbe     short loc_180056E8A
0x180056e81  mov     dword ptr [rbx+1Ch], 8007000Dh
0x180056e88  jmp     short loc_180056EB8
0x180056e8a  mov     rdx, [rbx+20h]; lpValueName
0x180056e8e  mov     r9d, 3; dwType
0x180056e94  mov     [rsp+48h+cbData], eax; cbData
0x180056e98  xor     r8d, r8d; Reserved
0x180056e9b  mov     rcx, rsi; hKey
0x180056e9e  mov     [rsp+48h+lpData], rdi; lpData
0x180056ea3  call    cs:__imp_RegSetValueExW
0x180056ea9  test    eax, eax
0x180056eab  jle     short loc_180056EB5
0x180056ead  movzx   eax, ax
0x180056eb0  or      eax, 80070000h
0x180056eb5  mov     [rbx+1Ch], eax
0x180056eb8  test    rdi, rdi
0x180056ebb  jz      short loc_180056EC6
0x180056ebd  mov     rcx, rdi; hMem
0x180056ec0  call    cs:__imp_LocalFree
0x180056ec6  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ecd  cmp     rcx, r14
0x180056ed0  jz      short loc_180056EF1
0x180056ed2  test    byte ptr [rcx+1Ch], 10h
0x180056ed6  jz      short loc_180056EF1
0x180056ed8  mov     r9d, [rbx+1Ch]
0x180056edc  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x180056ee3  mov     rcx, [rcx+10h]
0x180056ee7  mov     edx, 13h
0x180056eec  call    WPP_SF_d
0x180056ef1  mov     eax, [rbx+1Ch]
0x180056ef4  mov     rbx, [rsp+48h+arg_8]
0x180056ef9  add     rsp, 30h
0x180056efd  pop     r14
0x180056eff  pop     rdi
0x180056f00  pop     rsi
0x180056f01  retn
```
