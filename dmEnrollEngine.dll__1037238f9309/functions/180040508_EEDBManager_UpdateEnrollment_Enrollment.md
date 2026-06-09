# EEDBManager::UpdateEnrollment(Enrollment *)

- ea: `0x180040508`
- end: `0x1800406c9`
- name: `?UpdateEnrollment@EEDBManager@@QEAAJPEAVEnrollment@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(EEDBManager *__hidden this, struct Enrollment *)`
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000e5dc`
- `0x180034824`
- `0x180034a30`
- `0x1800350b0`
- `0x1800352bc`
- `0x180041c90`

## callees

- `0x180006e00`
- `0x180007040`
- `0x180007120`
- `0x1800071c0`
- `0x18002e1a0`
- `0x180040508`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040675`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040675`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004069d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004069d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004055e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004055e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EEDBManager::UpdateEnrollment(EEDBManager *this, struct Enrollment *a2)
{
  HKEY v3; // rbx
  int v4; // edi
  LSTATUS v5; // eax
  BYTE Data[8]; // [rsp+30h] [rbp-89h] BYREF
  unsigned __int64 v8; // [rsp+38h] [rbp-81h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-79h] BYREF
  HKEY v10; // [rsp+48h] [rbp-71h] BYREF
  wchar_t String1[40]; // [rsp+50h] [rbp-69h] BYREF
  OLECHAR sz; // [rsp+A0h] [rbp-19h] BYREF
  unsigned __int16 v13[39]; // [rsp+A2h] [rbp-17h] BYREF

  *(_DWORD *)Data = 63;
  v3 = 0;
  hKey = 0;
  v10 = 0;
  String1[0] = 0;
  sz = 0;
  if ( StringFromGUID2((const GUID *const)((char *)a2 + 28), &sz, 39) != 39 )
    goto LABEL_13;
  v8 = 0;
  v4 = StringCchLengthW(&sz, 0x27u, &v8);
  if ( v4 < 0 )
    goto LABEL_14;
  if ( v8 - 2 > 0x24 )
    goto LABEL_13;
  v4 = StringCchCopyW(String1, 0x27u, v13);
  if ( v4 < 0 )
    goto LABEL_14;
  v4 = StringCchLengthW(String1, 0x27u, &v8);
  if ( v4 < 0 )
    goto LABEL_14;
  if ( v8 - 2 > 0x24 )
  {
LABEL_13:
    v4 = -2147418113;
    goto LABEL_14;
  }
  String1[v8 - 1] = 0;
  v4 = EEDBManager::OpenEnrollmentHKEY((HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL), String1, 131078, &v10, 0, 0);
  if ( v4 >= 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      v10);
    v4 = (*(__int64 (__fastcall **)(struct Enrollment *, BYTE *))(*(_QWORD *)a2 + 56LL))(a2, Data);
    v3 = hKey;
    if ( v4 >= 0 )
    {
      v5 = RegSetValueExW(hKey, L"EnrollmentState", 0, 4u, Data, 4u);
      if ( v5 )
      {
        if ( v5 > 0 )
          v4 = (unsigned __int16)v5 | 0x80070000;
        else
          v4 = v5;
      }
    }
  }
LABEL_14:
  if ( v3 )
    RegCloseKey(v3);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180040508  mov     [rsp-8+arg_0], rbx
0x18004050d  mov     [rsp-8+arg_10], rsi
0x180040512  push    rbp
0x180040513  push    rdi
0x180040514  push    r15
0x180040516  lea     rbp, [rsp-47h]
0x18004051b  sub     rsp, 100h
0x180040522  mov     rax, cs:__security_cookie
0x180040529  xor     rax, rsp
0x18004052c  mov     [rbp+57h+var_20], rax
0x180040530  mov     rsi, rdx
0x180040533  mov     dword ptr [rsp+110h+Data], 3Fh ; '?'
0x18004053b  xor     ebx, ebx
0x18004053d  mov     [rbp+57h+hKey], rbx
0x180040541  mov     [rbp+57h+var_C8], rbx
0x180040545  xor     eax, eax
0x180040547  mov     [rbp+57h+String1], ax
0x18004054b  mov     [rbp+57h+sz], ax
0x18004054f  lea     rcx, [rdx+1Ch]; rguid
0x180040553  lea     r15d, [rbx+27h]
0x180040557  mov     r8d, r15d; cchMax
0x18004055a  lea     rdx, [rbp+57h+sz]; lpsz
0x18004055e  call    cs:__imp_StringFromGUID2
0x180040564  cmp     eax, r15d
0x180040567  jnz     loc_180040690
0x18004056d  mov     [rsp+110h+var_D8], rbx
0x180040572  lea     r8, [rsp+110h+var_D8]; unsigned __int64 *
0x180040577  mov     edx, r15d; unsigned __int64
0x18004057a  lea     rcx, [rbp+57h+sz]; unsigned __int16 *
0x18004057e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180040583  mov     edi, eax
0x180040585  test    eax, eax
0x180040587  js      loc_180040695
0x18004058d  mov     rax, [rsp+110h+var_D8]
0x180040592  add     rax, 0FFFFFFFFFFFFFFFEh
0x180040596  cmp     rax, 24h ; '$'
0x18004059a  ja      loc_180040690
0x1800405a0  lea     r8, [rbp+57h+var_6E]; unsigned __int16 *
0x1800405a4  mov     edx, r15d; unsigned __int64
0x1800405a7  lea     rcx, [rbp+57h+String1]; unsigned __int16 *
0x1800405ab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800405b0  mov     edi, eax
0x1800405b2  test    eax, eax
0x1800405b4  js      loc_180040695
0x1800405ba  lea     r8, [rsp+110h+var_D8]; unsigned __int64 *
0x1800405bf  mov     edx, r15d; unsigned __int64
0x1800405c2  lea     rcx, [rbp+57h+String1]; unsigned __int16 *
0x1800405c6  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800405cb  mov     edi, eax
0x1800405cd  test    eax, eax
0x1800405cf  js      loc_180040695
0x1800405d5  mov     rcx, [rsp+110h+var_D8]
0x1800405da  lea     rax, [rcx-2]
0x1800405de  cmp     rax, 24h ; '$'
0x1800405e2  ja      loc_180040690
0x1800405e8  xor     eax, eax
0x1800405ea  mov     word ptr [rbp+rcx*2+57h+var_C8+6], ax
0x1800405ef  xor     ecx, ecx
0x1800405f1  mov     eax, 2000h
0x1800405f6  cmp     cs:word_1800AFC84, ax
0x1800405fd  setnz   cl
0x180040600  add     rcx, 0FFFFFFFF80000001h; hKey
0x180040607  mov     qword ptr [rsp+110h+cbData], rbx; unsigned __int64
0x18004060c  mov     [rsp+110h+lpData], rbx; unsigned __int16 *
0x180040611  lea     r9, [rbp+57h+var_C8]; HKEY *
0x180040615  mov     r8d, 20006h; unsigned int
0x18004061b  lea     rdx, [rbp+57h+String1]; String1
0x18004061f  call    ?OpenEnrollmentHKEY@EEDBManager@@SAJPEAUHKEY__@@PEBGKPEAPEAU2@PEAG_K@Z; EEDBManager::OpenEnrollmentHKEY(HKEY__ *,ushort const *,ulong,HKEY__ * *,ushort *,unsigned __int64)
0x180040624  mov     edi, eax
0x180040626  test    eax, eax
0x180040628  js      short loc_180040695
0x18004062a  mov     rdx, [rbp+57h+var_C8]
0x18004062e  lea     rcx, [rbp+57h+hKey]
0x180040632  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180040637  mov     rax, [rsi]
0x18004063a  lea     rdx, [rsp+110h+Data]
0x18004063f  mov     rcx, rsi
0x180040642  mov     rax, [rax+38h]
0x180040646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004064b  mov     edi, eax
0x18004064d  mov     rbx, [rbp+57h+hKey]
0x180040651  test    eax, eax
0x180040653  js      short loc_180040695
0x180040655  lea     r9d, [r15-23h]; dwType
0x180040659  mov     [rsp+110h+cbData], r9d; cbData
0x18004065e  lea     rax, [rsp+110h+Data]
0x180040663  mov     [rsp+110h+lpData], rax; lpData
0x180040668  xor     r8d, r8d; Reserved
0x18004066b  lea     rdx, Value; "EnrollmentState"
0x180040672  mov     rcx, rbx; hKey
0x180040675  call    cs:__imp_RegSetValueExW
0x18004067b  test    eax, eax
0x18004067d  jz      short loc_180040695
0x18004067f  jg      short loc_180040685
0x180040681  mov     edi, eax
0x180040683  jmp     short loc_180040695
0x180040685  movzx   edi, ax
0x180040688  or      edi, 80070000h
0x18004068e  jmp     short loc_180040695
0x180040690  mov     edi, 8000FFFFh
0x180040695  test    rbx, rbx
0x180040698  jz      short loc_1800406A3
0x18004069a  mov     rcx, rbx; hKey
0x18004069d  call    cs:__imp_RegCloseKey
0x1800406a3  mov     eax, edi
0x1800406a5  mov     rcx, [rbp+57h+var_20]
0x1800406a9  xor     rcx, rsp; StackCookie
0x1800406ac  call    __security_check_cookie
0x1800406b1  lea     r11, [rsp+110h+var_10]
0x1800406b9  mov     rbx, [r11+20h]
0x1800406bd  mov     rsi, [r11+30h]
0x1800406c1  mov     rsp, r11
0x1800406c4  pop     r15
0x1800406c6  pop     rdi
0x1800406c7  pop     rbp
0x1800406c8  retn
```
