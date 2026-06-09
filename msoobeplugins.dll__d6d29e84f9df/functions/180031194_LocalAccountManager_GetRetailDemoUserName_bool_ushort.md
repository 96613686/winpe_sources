# LocalAccountManager::_GetRetailDemoUserName(bool,ushort * *)

- ea: `0x180031194`
- end: `0x180031395`
- name: `?_GetRetailDemoUserName@LocalAccountManager@@AEAAJ_NPEAPEAG@Z`
- size: `513`
- prototype: `__int64 __fastcall(LocalAccountManager *__hidden this, bool, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002f9a0`
- `0x180030860`

## callees

- `0x180003470`
- `0x180008544`
- `0x180019a38`
- `0x180019a74`
- `0x180031194`
- `0x1800ae4c4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800312b7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800312e2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800312b7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800312e2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031234`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031234`
- `api-ms-win-core-localization-l1-2-2!GetSystemDefaultLocaleName` at `0x18003128f`
- `api-ms-win-core-localization-l1-2-2!GetSystemDefaultLocaleName` at `0x18003128f`

## string_xrefs

- `0x180031325`: `shell\oobe\machine\plugins\localuser\localaccountmanager.cpp`
- `0x180031226`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LocalAccountManager::_GetRetailDemoUserName(
        LocalAccountManager *this,
        unsigned __int8 a2,
        unsigned __int16 **a3)
{
  int v4; // edi
  LSTATUS ValueW; // eax
  bool v6; // sf
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  unsigned int v10; // ebx
  unsigned __int16 *v11; // rax
  int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h]
  __int64 v16; // [rsp+50h] [rbp-B0h]
  DWORD pcbData; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR LocaleName[24]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD pvData[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  v4 = a2;
  *a3 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( a2 )
    goto LABEL_8;
  pcbData = 520;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
             L"Account",
             2u,
             0,
             pvData,
             &pcbData);
  v6 = ValueW < 0;
  if ( ValueW )
  {
    pvData[0] = 0;
    v6 = ValueW < 0;
    if ( ValueW > 0 )
      v6 = 1;
  }
  if ( v6 )
  {
LABEL_8:
    v10 = v4 + 517;
    if ( !(_BYTE)v4 && GetSystemDefaultLocaleName(LocaleName, 20) )
    {
      if ( CompareStringOrdinal(LocaleName, 3, L"vi-", 3, 1) == 2 )
      {
        v10 = 519;
      }
      else if ( CompareStringOrdinal(LocaleName, 3, L"id-", 3, 1) == 2 )
      {
        v10 = 520;
      }
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v14);
    v15 = -1;
    v16 = -1;
    v7 = SHFormatResMessageArgAlloc(g_hInst, v10, &v14);
    v8 = v7;
    if ( v7 < 0 )
    {
      v9 = 302;
      goto LABEL_16;
    }
LABEL_17:
    v11 = v14;
    v14 = 0;
    v16 = 0;
    v15 = 0;
    *a3 = v11;
    v8 = 0;
    goto LABEL_18;
  }
  v7 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         &v14,
         pvData,
         -1);
  v8 = v7;
  if ( v7 >= 0 )
    goto LABEL_17;
  v9 = 284;
LABEL_16:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"shell\\oobe\\machine\\plugins\\localuser\\localaccountmanager.cpp",
    (const char *)(unsigned int)v7,
    pdwType);
LABEL_18:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v14);
  return v8;
}

```

## disassembly

```asm
0x180031194  mov     [rsp-8+arg_0], rbx
0x180031199  mov     [rsp-8+arg_8], rsi
0x18003119e  push    rbp
0x18003119f  push    rdi
0x1800311a0  push    r12
0x1800311a2  lea     rbp, [rsp-1B0h]
0x1800311aa  sub     rsp, 2B0h
0x1800311b1  mov     rax, cs:__security_cookie
0x1800311b8  xor     rax, rsp
0x1800311bb  mov     [rbp+1C0h+var_20], rax
0x1800311c2  mov     rsi, r8
0x1800311c5  movzx   edi, dl
0x1800311c8  mov     qword ptr [r8], 0
0x1800311cf  mov     [rsp+2C0h+var_280], 0
0x1800311d8  mov     [rsp+2C0h+var_278], 0
0x1800311e1  mov     [rsp+2C0h+var_270], 0
0x1800311ea  mov     r12d, 208h
0x1800311f0  test    dl, dl
0x1800311f2  jnz     loc_18003127A
0x1800311f8  mov     [rsp+2C0h+var_268], r12d
0x1800311fd  lea     rax, [rsp+2C0h+var_268]
0x180031202  mov     [rsp+2C0h+pcbData], rax; pcbData
0x180031207  lea     rax, [rbp+1C0h+var_230]
0x18003120b  mov     [rsp+2C0h+pvData], rax; pvData
0x180031210  mov     [rsp+2C0h+pdwType], 0; pdwType
0x180031219  mov     r9d, 2; dwFlags
0x18003121f  lea     r8, ?c_retailDemoValueDemoAccountName@@3QBGB; "Account"
0x180031226  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003122d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180031234  call    cs:__imp_RegGetValueW
0x18003123a  test    eax, eax
0x18003123c  jz      short loc_180031252
0x18003123e  xor     ecx, ecx
0x180031240  mov     [rbp+1C0h+var_230], cx
0x180031244  test    eax, eax
0x180031246  jle     short loc_180031252
0x180031248  movzx   eax, ax
0x18003124b  or      eax, 80070000h
0x180031250  test    eax, eax
0x180031252  js      short loc_18003127A
0x180031254  or      r8, 0FFFFFFFFFFFFFFFFh
0x180031258  lea     rdx, [rbp+1C0h+var_230]
0x18003125c  lea     rcx, [rsp+2C0h+var_280]
0x180031261  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180031266  mov     ebx, eax
0x180031268  test    eax, eax
0x18003126a  jns     loc_18003133D
0x180031270  mov     edx, 11Ch
0x180031275  jmp     loc_180031325
0x18003127a  lea     ebx, [rdi+205h]
0x180031280  test    dil, dil
0x180031283  jnz     short loc_1800312EF
0x180031285  mov     edx, 14h; cchLocaleName
0x18003128a  lea     rcx, [rsp+2C0h+LocaleName]; lpLocaleName
0x18003128f  call    cs:__imp_GetSystemDefaultLocaleName
0x180031295  test    eax, eax
0x180031297  jz      short loc_1800312EF
0x180031299  mov     dword ptr [rsp+2C0h+pdwType], 1; bIgnoreCase
0x1800312a1  mov     edi, 3
0x1800312a6  mov     r9d, edi; cchCount2
0x1800312a9  lea     r8, aVi; "vi-"
0x1800312b0  mov     edx, edi; cchCount1
0x1800312b2  lea     rcx, [rsp+2C0h+LocaleName]; lpString1
0x1800312b7  call    cs:__imp_CompareStringOrdinal
0x1800312bd  cmp     eax, 2
0x1800312c0  jnz     short loc_1800312C9
0x1800312c2  mov     ebx, 207h
0x1800312c7  jmp     short loc_1800312EF
0x1800312c9  mov     dword ptr [rsp+2C0h+pdwType], 1; int
0x1800312d1  mov     r9d, edi; cchCount2
0x1800312d4  lea     r8, aId; "id-"
0x1800312db  mov     edx, edi; cchCount1
0x1800312dd  lea     rcx, [rsp+2C0h+LocaleName]; lpString1
0x1800312e2  call    cs:__imp_CompareStringOrdinal
0x1800312e8  cmp     eax, 2
0x1800312eb  cmovz   ebx, r12d
0x1800312ef  lea     rcx, [rsp+2C0h+var_280]
0x1800312f4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800312f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800312fd  mov     [rsp+2C0h+var_278], rax
0x180031302  mov     [rsp+2C0h+var_270], rax
0x180031307  lea     r8, [rsp+2C0h+var_280]
0x18003130c  mov     edx, ebx
0x18003130e  mov     rcx, cs:g_hInst
0x180031315  call    SHFormatResMessageArgAlloc
0x18003131a  mov     ebx, eax
0x18003131c  test    eax, eax
0x18003131e  jns     short loc_18003133D
0x180031320  mov     edx, 12Eh; void *
0x180031325  lea     r8, aShellOobeMachi_2; "shell\\oobe\\machine\\plugins\\localuse"...
0x18003132c  mov     r9d, eax; char *
0x18003132f  mov     rcx, [rbp+1C8h]; this
0x180031336  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003133b  jmp     short loc_180031362
0x18003133d  mov     rax, [rsp+2C0h+var_280]
0x180031342  mov     [rsp+2C0h+var_280], 0
0x18003134b  mov     [rsp+2C0h+var_270], 0
0x180031354  mov     [rsp+2C0h+var_278], 0
0x18003135d  mov     [rsi], rax
0x180031360  xor     ebx, ebx
0x180031362  lea     rcx, [rsp+2C0h+var_280]
0x180031367  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003136c  mov     eax, ebx
0x18003136e  mov     rcx, [rbp+1C0h+var_20]
0x180031375  xor     rcx, rsp; StackCookie
0x180031378  call    __security_check_cookie
0x18003137d  lea     r11, [rsp+2C0h+var_10]
0x180031385  mov     rbx, [r11+20h]
0x180031389  mov     rsi, [r11+28h]
0x18003138d  mov     rsp, r11
0x180031390  pop     r12
0x180031392  pop     rdi
0x180031393  pop     rbp
0x180031394  retn
```
