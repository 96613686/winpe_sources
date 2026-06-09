# Microsoft::Bluetooth::Services::BthServ::BthpFindSDPPriLangServiceName(_BLUETOOTH_SERVICE_RECORD const *,char *,ulong)

- ea: `0x180026b94`
- end: `0x180026c69`
- name: `?BthpFindSDPPriLangServiceName@BthServ@Services@Bluetooth@Microsoft@@YAKPEBU_BLUETOOTH_SERVICE_RECORD@@PEADK@Z`
- size: `213`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *this, const struct _BLUETOOTH_SERVICE_RECORD *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027ea8`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x180026b94`
- `0x18002aa48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c37`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026c27`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026c27`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BthpFindSDPPriLangServiceName(
        Microsoft::Bluetooth::Services::BthServ *this,
        const struct _BLUETOOTH_SERVICE_RECORD *a2,
        char *a3)
{
  unsigned __int8 *v5; // rdx
  struct IMultiLanguage2 *v6; // rcx
  unsigned int v7; // r8d
  unsigned int String; // ebx
  unsigned int *v10; // [rsp+30h] [rbp-238h]
  int cchWideChar[4]; // [rsp+40h] [rbp-228h] BYREF
  WCHAR WideCharStr[256]; // [rsp+50h] [rbp-218h] BYREF

  memset_0(a2, 0, 0x100u);
  v5 = (unsigned __int8 *)*((unsigned int *)this + 4);
  v6 = (struct IMultiLanguage2 *)*((_QWORD *)this + 1);
  cchWideChar[0] = 256;
  String = Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetString(
             v6,
             v5,
             v7,
             0,
             (unsigned __int16)WideCharStr,
             (unsigned __int16 *)cchWideChar,
             v10);
  if ( !String && !WideCharToMultiByte(0xFDE9u, 0x80u, WideCharStr, cchWideChar[0], (LPSTR)a2, 256, 0, 0) )
    return GetLastError();
  return String;
}

```

## disassembly

```asm
0x180026b94  mov     [rsp+arg_10], rbx
0x180026b99  push    rdi
0x180026b9a  sub     rsp, 260h
0x180026ba1  mov     rax, cs:__security_cookie
0x180026ba8  xor     rax, rsp
0x180026bab  mov     [rsp+268h+var_18], rax
0x180026bb3  mov     rdi, rdx
0x180026bb6  mov     rbx, rcx
0x180026bb9  mov     rcx, rdi; void *
0x180026bbc  xor     edx, edx; Val
0x180026bbe  mov     r8d, 100h; Size
0x180026bc4  call    memset_0
0x180026bc9  mov     edx, [rbx+10h]; unsigned __int8 *
0x180026bcc  lea     rax, [rsp+268h+cchWideChar]
0x180026bd1  mov     rcx, [rbx+8]; this
0x180026bd5  xor     r9d, r9d; struct _SDP_STRING_TYPE_DATA *
0x180026bd8  mov     qword ptr [rsp+268h+cbMultiByte], rax; unsigned __int16 *
0x180026bdd  lea     rax, [rsp+268h+WideCharStr]
0x180026be2  mov     [rsp+268h+lpMultiByteStr], rax; unsigned __int16
0x180026be7  mov     [rsp+268h+cchWideChar], 100h
0x180026bef  call    ?BluetoothSdpGetString@BthServ@Services@Bluetooth@Microsoft@@YAKPEAEKPEAU_SDP_STRING_TYPE_DATA@@GPEAGPEAK@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSdpGetString(uchar *,ulong,_SDP_STRING_TYPE_DATA *,ushort,ushort *,ulong *)
0x180026bf4  mov     ebx, eax
0x180026bf6  test    eax, eax
0x180026bf8  jnz     short loc_180026C45
0x180026bfa  and     [rsp+268h+var_230], 0
0x180026c00  lea     r8, [rsp+268h+WideCharStr]; lpWideCharStr
0x180026c05  and     [rsp+268h+var_238], 0
0x180026c0b  mov     edx, 80h; dwFlags
0x180026c10  mov     r9d, [rsp+268h+cchWideChar]; cchWideChar
0x180026c15  mov     ecx, 0FDE9h; CodePage
0x180026c1a  mov     [rsp+268h+cbMultiByte], 100h; cbMultiByte
0x180026c22  mov     [rsp+268h+lpMultiByteStr], rdi; lpMultiByteStr
0x180026c27  call    cs:__imp_WideCharToMultiByte
0x180026c2e  nop     dword ptr [rax+rax+00h]
0x180026c33  test    eax, eax
0x180026c35  jnz     short loc_180026C45
0x180026c37  call    cs:__imp_GetLastError
0x180026c3e  nop     dword ptr [rax+rax+00h]
0x180026c43  mov     ebx, eax
0x180026c45  mov     eax, ebx
0x180026c47  mov     rcx, [rsp+268h+var_18]
0x180026c4f  xor     rcx, rsp; StackCookie
0x180026c52  call    __security_check_cookie
0x180026c57  mov     rbx, [rsp+268h+arg_10]
0x180026c5f  add     rsp, 260h
0x180026c66  pop     rdi
0x180026c67  retn
```
