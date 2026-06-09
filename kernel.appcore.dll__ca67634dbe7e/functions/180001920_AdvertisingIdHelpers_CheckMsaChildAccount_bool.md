# AdvertisingIdHelpers::CheckMsaChildAccount(bool *)

- ea: `0x180001920`
- end: `0x180001ae1`
- name: `?CheckMsaChildAccount@AdvertisingIdHelpers@@YAJPEA_N@Z`
- size: `449`
- prototype: `__int64 __fastcall(AdvertisingIdHelpers *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800011a0`
- `0x180001380`

## callees

- `0x180001920`
- `0x180001e20`
- `0x180001ec0`
- `0x180003350`
- `0x180006324`
- `0x180009dd0`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001a17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001ab5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001a17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001ab5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800019ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800019ad`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::CheckMsaChildAccount(AdvertisingIdHelpers *this, void **a2)
{
  int CallingProcessHandle; // eax
  unsigned __int16 *v4; // r8
  unsigned int v5; // ebx
  _WORD *v6; // rdi
  HRESULT v7; // eax
  int v8; // eax
  LPVOID v9; // rcx
  HANDLE v10; // rcx
  int AppcontainerSidFromProcessHandle; // eax
  int ppv; // [rsp+20h] [rbp-148h]
  LPVOID v14; // [rsp+30h] [rbp-138h] BYREF
  int v15; // [rsp+38h] [rbp-130h] BYREF
  HANDLE hObject[2]; // [rsp+40h] [rbp-128h] BYREF
  _WORD v17[128]; // [rsp+50h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  hObject[0] = 0;
  v14 = 0;
  v15 = 0;
  CallingProcessHandle = AdvertisingIdHelpers::GetCallingProcessHandle((AdvertisingIdHelpers *)hObject, a2);
  v5 = CallingProcessHandle;
  if ( CallingProcessHandle < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)CallingProcessHandle,
      ppv);
    Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(&v14);
    v10 = hObject[0];
    if ( (unsigned __int64)hObject[0] - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return v5;
    goto LABEL_11;
  }
  v6 = 0;
  if ( hObject[0] )
  {
    AppcontainerSidFromProcessHandle = AdvertisingIdHelpers::GetAppcontainerSidFromProcessHandle(
                                         (AdvertisingIdHelpers *)hObject[0],
                                         v17,
                                         v4);
    v5 = AppcontainerSidFromProcessHandle;
    if ( AppcontainerSidFromProcessHandle < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1B9,
        (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
        (const char *)(unsigned int)AppcontainerSidFromProcessHandle,
        ppv);
      goto LABEL_8;
    }
    v6 = v17;
  }
  Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(&v14);
  v7 = CoCreateInstance(
         &GUID_ae0db8a9_8183_4fa1_afda_c3506921d7e3,
         0,
         1u,
         &GUID_31140cb5_6b64_48ff_b872_660441ce9e51,
         &v14);
  v5 = v7;
  if ( v7 == -2147467262 || v7 == -2147221164 )
    goto LABEL_7;
  if ( v7 < 0 )
    goto LABEL_8;
  v8 = (*(__int64 (__fastcall **)(LPVOID, _WORD *, int *))(*(_QWORD *)v14 + 24LL))(v14, v6, &v15);
  v5 = v8;
  if ( v8 == -2147023579 || v8 == -2147023728 )
  {
LABEL_7:
    v5 = 0;
    *(_BYTE *)this = 0;
  }
  else if ( v8 >= 0 )
  {
    *(_BYTE *)this = v15 == 0;
  }
LABEL_8:
  v9 = v14;
  if ( v14 )
  {
    v14 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v10 = hObject[0];
  if ( (unsigned __int64)hObject[0] - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
LABEL_11:
    CloseHandle(v10);
  return v5;
}

```

## disassembly

```asm
0x180001920  mov     [rsp+arg_10], rbx
0x180001925  mov     [rsp+arg_18], rbp
0x18000192a  push    rsi
0x18000192b  sub     rsp, 160h
0x180001932  mov     rax, cs:__security_cookie
0x180001939  xor     rax, rsp
0x18000193c  mov     [rsp+168h+var_18], rax
0x180001944  xor     ebp, ebp
0x180001946  mov     rsi, rcx
0x180001949  lea     rcx, [rsp+168h+hObject]; this
0x18000194e  mov     [rsp+168h+hObject], rbp
0x180001953  mov     [rsp+168h+var_138], rbp
0x180001958  mov     [rsp+168h+var_130], ebp
0x18000195c  call    ?GetCallingProcessHandle@AdvertisingIdHelpers@@YAJPEAPEAX@Z; AdvertisingIdHelpers::GetCallingProcessHandle(void * *)
0x180001961  mov     ebx, eax
0x180001963  test    eax, eax
0x180001965  js      loc_180001A7C
0x18000196b  mov     rcx, [rsp+168h+hObject]; this
0x180001970  mov     [rsp+168h+arg_8], rdi
0x180001978  mov     edi, ebp
0x18000197a  test    rcx, rcx
0x18000197d  jnz     loc_180001A62
0x180001983  lea     rcx, [rsp+168h+var_138]
0x180001988  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x18000198d  lea     rax, [rsp+168h+var_138]
0x180001992  xor     edx, edx; pUnkOuter
0x180001994  lea     r9, _GUID_31140cb5_6b64_48ff_b872_660441ce9e51; riid
0x18000199b  mov     qword ptr [rsp+168h+ppv], rax; ppv
0x1800019a0  mov     r8d, 1; dwClsContext
0x1800019a6  lea     rcx, _GUID_ae0db8a9_8183_4fa1_afda_c3506921d7e3; rclsid
0x1800019ad  call    cs:__imp_CoCreateInstance
0x1800019b3  mov     ebx, eax
0x1800019b5  cmp     eax, 80004002h
0x1800019ba  jz      short loc_1800019E9
0x1800019bc  cmp     eax, 80040154h
0x1800019c1  jz      short loc_1800019E9
0x1800019c3  test    eax, eax
0x1800019c5  js      short loc_1800019ED
0x1800019c7  mov     rcx, [rsp+168h+var_138]
0x1800019cc  lea     r8, [rsp+168h+var_130]
0x1800019d1  mov     rdx, rdi
0x1800019d4  mov     rax, [rcx]
0x1800019d7  mov     rax, [rax+18h]
0x1800019db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019e0  mov     ebx, eax
0x1800019e2  cmp     eax, 80070525h
0x1800019e7  jnz     short loc_180001A4C
0x1800019e9  mov     ebx, ebp
0x1800019eb  mov     [rsi], bl
0x1800019ed  mov     rcx, [rsp+168h+var_138]
0x1800019f2  test    rcx, rcx
0x1800019f5  jz      short loc_180001A08
0x1800019f7  mov     [rsp+168h+var_138], rbp
0x1800019fc  mov     rax, [rcx]
0x1800019ff  mov     rax, [rax+10h]
0x180001a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a08  mov     rcx, [rsp+168h+hObject]; hObject
0x180001a0d  lea     rax, [rcx-1]
0x180001a11  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180001a15  ja      short loc_180001A1D
0x180001a17  call    cs:__imp_CloseHandle
0x180001a1d  mov     rdi, [rsp+168h+arg_8]
0x180001a25  mov     eax, ebx
0x180001a27  mov     rcx, [rsp+168h+var_18]
0x180001a2f  xor     rcx, rsp; StackCookie
0x180001a32  call    __security_check_cookie
0x180001a37  lea     r11, [rsp+168h+var_8]
0x180001a3f  mov     rbx, [r11+20h]
0x180001a43  mov     rbp, [r11+28h]
0x180001a47  mov     rsp, r11
0x180001a4a  pop     rsi
0x180001a4b  retn
0x180001a4c  cmp     eax, 80070490h
0x180001a51  jz      short loc_1800019E9
0x180001a53  test    eax, eax
0x180001a55  js      short loc_1800019ED
0x180001a57  cmp     [rsp+168h+var_130], ebp
0x180001a5b  setz    al
0x180001a5e  mov     [rsi], al
0x180001a60  jmp     short loc_1800019ED
0x180001a62  lea     rdx, [rsp+168h+var_118]; void *
0x180001a67  call    ?GetAppcontainerSidFromProcessHandle@AdvertisingIdHelpers@@YAJPEAXPEAGK@Z; AdvertisingIdHelpers::GetAppcontainerSidFromProcessHandle(void *,ushort *,ulong)
0x180001a6c  mov     ebx, eax
0x180001a6e  test    eax, eax
0x180001a70  js      short loc_180001AC0
0x180001a72  lea     rdi, [rsp+168h+var_118]
0x180001a77  jmp     loc_180001983
0x180001a7c  mov     rcx, [rsp+168h]; this
0x180001a84  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180001a8b  mov     r9d, ebx; char *
0x180001a8e  mov     edx, 1B3h; void *
0x180001a93  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180001a98  lea     rcx, [rsp+168h+var_138]
0x180001a9d  call    ?InternalRelease@?$ComPtr@UICallingProcessInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICallingProcessInfo>::InternalRelease(void)
0x180001aa2  mov     rcx, [rsp+168h+hObject]; hObject
0x180001aa7  lea     rdx, [rcx-1]
0x180001aab  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180001aaf  ja      loc_180001A25
0x180001ab5  call    cs:__imp_CloseHandle
0x180001abb  jmp     loc_180001A25
0x180001ac0  mov     rcx, [rsp+168h]; this
0x180001ac8  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180001acf  mov     r9d, ebx; char *
0x180001ad2  mov     edx, 1B9h; void *
0x180001ad7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180001adc  jmp     loc_1800019ED
```
