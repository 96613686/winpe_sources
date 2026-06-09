# Microsoft::Windows::MDM::OmadmClient::OmadmAccountManager::StoreUpdatedManagementServerAddressList(ushort const *,tagDMACCOUNTLOOKUPTYPE,ushort const *,unsigned __int64)

- ea: `0x14003f9c0`
- end: `0x14003fb8f`
- name: `?StoreUpdatedManagementServerAddressList@OmadmAccountManager@OmadmClient@MDM@Windows@Microsoft@@UEAAJPEBGW4tagDMACCOUNTLOOKUPTYPE@@0_K@Z`
- size: `463`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003450`
- `0x140003eb4`
- `0x14000e610`
- `0x140013404`
- `0x14003f9c0`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fa83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003fa83`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14003fa73`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14003fa73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fb58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003fb58`
- `omadmapi!__imp_OmaDmFreeAcctInfo` at `0x14003fb41`
- `omadmapi!__imp_OmaDmFreeAcctInfo` at `0x14003fb41`
- `omadmapi!__imp_OmaDmSetValueInStruct` at `0x14003fae4`
- `omadmapi!__imp_OmaDmSetValueInStruct` at `0x14003fae4`

## string_xrefs

- `0x14003fa09`: `StoreUpdatedManagementServerAddressList`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::OmadmAccountManager::StoreUpdatedManagementServerAddressList(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        va_list a4,
        va_list a5)
{
  signed int LastError; // eax
  unsigned int v10; // ebx
  int v11; // eax
  LPWSTR lpBuffer; // [rsp+20h] [rbp-E0h]
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[4]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v16[3]; // [rsp+50h] [rbp-B0h] BYREF
  int v17; // [rsp+68h] [rbp-98h]
  unsigned int *v18; // [rsp+70h] [rbp-90h]
  va_list Arguments[3]; // [rsp+78h] [rbp-88h] BYREF
  char v20; // [rsp+90h] [rbp-70h]
  int v21; // [rsp+A0h] [rbp-60h] BYREF
  char v22[508]; // [rsp+A4h] [rbp-5Ch] BYREF

  v14 = 0;
  v16[0] = 0;
  v16[1] = "StoreUpdatedManagementServerAddressList";
  v16[2] = COmaDmLogger::GetLogger();
  v17 = 2;
  v18 = &v14;
  Arguments[0] = a4;
  Arguments[1] = a5;
  *(_QWORD *)Buffer = 0;
  if ( FormatMessageW(0x2500u, L"%1:%2!d!", 0, 0, Buffer, 0x100u, Arguments) )
  {
    memset_0(v22, 0, sizeof(v22));
    v21 = 512;
    Arguments[2] = (va_list)&v21;
    v20 = 1;
    lpBuffer = *(LPWSTR *)Buffer;
    v11 = OmaDmSetValueInStruct(56, &v21, 0xFFFFFFFFLL);
    v10 = v11;
    v14 = v11;
    if ( v11 >= 0 )
    {
      *(_QWORD *)Buffer = 0;
      v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *, LPWSTR))(**(_QWORD **)(a1 + 8) + 48LL))(
              *(_QWORD *)(a1 + 8),
              a2,
              a3,
              &v21,
              lpBuffer);
      v10 = v11;
      v14 = v11;
      if ( v11 >= 0 )
      {
LABEL_10:
        OmaDmFreeAcctInfo(&v21);
        goto LABEL_11;
      }
      LODWORD(v16[0]) = 21057;
    }
    else
    {
      LODWORD(v16[0]) = 21062;
    }
    HIDWORD(v16[0]) = v11;
    goto LABEL_10;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError > 0 )
    v10 = (unsigned __int16)LastError | 0x80070000;
  v14 = v10;
LABEL_11:
  if ( *(_QWORD *)Buffer )
    LocalFree(*(HLOCAL *)Buffer);
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v16);
  return v10;
}

```

## disassembly

```asm
0x14003f9c0  push    rbp
0x14003f9c2  push    rbx
0x14003f9c3  push    rsi
0x14003f9c4  push    rdi
0x14003f9c5  push    r14
0x14003f9c7  lea     rbp, [rsp-1B0h]
0x14003f9cf  sub     rsp, 2B0h
0x14003f9d6  mov     rax, cs:__security_cookie
0x14003f9dd  xor     rax, rsp
0x14003f9e0  mov     [rbp+1D0h+var_30], rax
0x14003f9e7  mov     rbx, r9
0x14003f9ea  mov     r14d, r8d
0x14003f9ed  mov     rsi, rdx
0x14003f9f0  mov     rdi, rcx
0x14003f9f3  mov     [rsp+2D0h+var_290], 0
0x14003f9fb  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14003fa00  mov     [rsp+2D0h+var_280], 0
0x14003fa09  lea     rcx, aStoreupdatedma; "StoreUpdatedManagementServerAddressList"
0x14003fa10  mov     [rsp+2D0h+var_278], rcx
0x14003fa15  mov     [rsp+2D0h+var_270], rax
0x14003fa1a  mov     [rsp+2D0h+var_268], 2
0x14003fa22  lea     rax, [rsp+2D0h+var_290]
0x14003fa27  mov     [rsp+2D0h+var_260], rax
0x14003fa2c  mov     [rsp+2D0h+var_258], rbx
0x14003fa31  mov     rax, [rbp+1D0h+arg_20]
0x14003fa38  mov     [rbp+1D0h+var_250], rax
0x14003fa3c  mov     qword ptr [rsp+2D0h+Buffer], 0
0x14003fa45  lea     rax, [rsp+2D0h+var_258]
0x14003fa4a  mov     [rsp+2D0h+Arguments], rax; Arguments
0x14003fa4f  mov     [rsp+2D0h+nSize], 100h; nSize
0x14003fa57  lea     rax, [rsp+2D0h+Buffer]
0x14003fa5c  mov     [rsp+2D0h+lpBuffer], rax; lpBuffer
0x14003fa61  xor     r9d, r9d; dwLanguageId
0x14003fa64  xor     r8d, r8d; dwMessageId
0x14003fa67  lea     rdx, ?gc_szManagementServerAddressListFormat@OmadmClient@MDM@Windows@Microsoft@@3QBGB; "%1:%2!d!"
0x14003fa6e  mov     ecx, 2500h; dwFlags
0x14003fa73  call    cs:__imp_FormatMessageW
0x14003fa7a  nop     dword ptr [rax+rax+00h]
0x14003fa7f  test    eax, eax
0x14003fa81  jnz     short loc_14003FAA7
0x14003fa83  call    cs:__imp_GetLastError
0x14003fa8a  nop     dword ptr [rax+rax+00h]
0x14003fa8f  mov     ebx, eax
0x14003fa91  test    eax, eax
0x14003fa93  jle     short loc_14003FA9E
0x14003fa95  movzx   ebx, ax
0x14003fa98  or      ebx, 80070000h
0x14003fa9e  mov     [rsp+2D0h+var_290], ebx
0x14003faa2  jmp     loc_14003FB4E
0x14003faa7  xor     edx, edx; Val
0x14003faa9  mov     r8d, 1FCh; Size
0x14003faaf  lea     rcx, [rbp+1D0h+var_22C]; void *
0x14003fab3  call    memset_0
0x14003fab8  mov     [rbp+1D0h+var_230], 200h
0x14003fabf  lea     rax, [rbp+1D0h+var_230]
0x14003fac3  mov     [rbp+1D0h+var_248], rax
0x14003fac7  mov     [rbp+1D0h+var_240], 1
0x14003facb  mov     rax, qword ptr [rsp+2D0h+Buffer]
0x14003fad0  mov     [rsp+2D0h+lpBuffer], rax
0x14003fad5  xor     r9d, r9d
0x14003fad8  or      r8d, 0FFFFFFFFh
0x14003fadc  lea     rdx, [rbp+1D0h+var_230]
0x14003fae0  lea     ecx, [r9+38h]
0x14003fae4  call    cs:__imp_OmaDmSetValueInStruct
0x14003faeb  nop     dword ptr [rax+rax+00h]
0x14003faf0  mov     ebx, eax
0x14003faf2  mov     [rsp+2D0h+var_290], eax
0x14003faf6  test    eax, eax
0x14003faf8  jns     short loc_14003FB04
0x14003fafa  mov     dword ptr [rsp+2D0h+var_280], 5246h
0x14003fb02  jmp     short loc_14003FB39
0x14003fb04  mov     qword ptr [rsp+2D0h+Buffer], 0
0x14003fb0d  mov     rcx, [rdi+8]
0x14003fb11  mov     rax, [rcx]
0x14003fb14  lea     r9, [rbp+1D0h+var_230]
0x14003fb18  mov     r8d, r14d
0x14003fb1b  mov     rdx, rsi
0x14003fb1e  mov     rax, [rax+30h]
0x14003fb22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fb27  mov     ebx, eax
0x14003fb29  mov     [rsp+2D0h+var_290], eax
0x14003fb2d  test    eax, eax
0x14003fb2f  jns     short loc_14003FB3D
0x14003fb31  mov     dword ptr [rsp+2D0h+var_280], 5241h
0x14003fb39  mov     dword ptr [rsp+2D0h+var_280+4], eax
0x14003fb3d  lea     rcx, [rbp+1D0h+var_230]
0x14003fb41  call    cs:__imp_OmaDmFreeAcctInfo
0x14003fb48  nop     dword ptr [rax+rax+00h]
0x14003fb4d  nop
0x14003fb4e  mov     rcx, qword ptr [rsp+2D0h+Buffer]; hMem
0x14003fb53  test    rcx, rcx
0x14003fb56  jz      short loc_14003FB65
0x14003fb58  call    cs:__imp_LocalFree
0x14003fb5f  nop     dword ptr [rax+rax+00h]
0x14003fb64  nop
0x14003fb65  lea     rcx, [rsp+2D0h+var_280]; this
0x14003fb6a  call    ??1TelemetryInfo@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::TelemetryInfo::~TelemetryInfo(void)
0x14003fb6f  mov     eax, ebx
0x14003fb71  mov     rcx, [rbp+1D0h+var_30]
0x14003fb78  xor     rcx, rsp; StackCookie
0x14003fb7b  call    __security_check_cookie
0x14003fb80  add     rsp, 2B0h
0x14003fb87  pop     r14
0x14003fb89  pop     rdi
0x14003fb8a  pop     rsi
0x14003fb8b  pop     rbx
0x14003fb8c  pop     rbp
0x14003fb8d  retn
```
