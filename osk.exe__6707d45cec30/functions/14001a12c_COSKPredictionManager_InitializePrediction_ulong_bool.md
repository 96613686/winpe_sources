# COSKPredictionManager::InitializePrediction(ulong,bool *)

- ea: `0x14001a12c`
- end: `0x14001a2ab`
- name: `?InitializePrediction@COSKPredictionManager@@AEAAJKPEA_N@Z`
- size: `383`
- prototype: `__int64 __fastcall(COSKPredictionManager *__hidden this, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140019ec8`

## callees

- `0x14000df20`
- `0x14001a0a8`
- `0x14001a12c`
- `0x14001a2b4`
- `0x14001b6f0`
- `0x140025d70`
- `0x140027010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001a1f9`
- `KERNEL32!GetLastError` at `0x14001a1f9`
- `KERNEL32!GetSystemDefaultLocaleName` at `0x14001a1e0`
- `KERNEL32!GetSystemDefaultLocaleName` at `0x14001a1e0`
- `ole32!CoCreateInstance` at `0x14001a186`
- `ole32!CoCreateInstance` at `0x14001a232`
- `ole32!CoCreateInstance` at `0x14001a186`
- `ole32!CoCreateInstance` at `0x14001a232`

## pseudocode

```c
__int64 __fastcall COSKPredictionManager::InitializePrediction(LPVOID *this, __int64 a2, bool *a3)
{
  int inited; // ebx
  HRESULT Instance; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  signed int LastError; // eax
  WCHAR LocaleName[88]; // [rsp+30h] [rbp-D8h] BYREF

  inited = 0;
  *a3 = 0;
  if ( !COSKUtils::ShouldRunSecure() )
  {
    Instance = CoCreateInstance(&CLSID_TPLangMod, 0, 1u, &GUID_357fbe87_6c8e_490d_a059_4746c864ae6f, this + 39);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)this[39] + 152LL))(this[39], 8);
      inited = Instance;
      if ( Instance < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v8 = 11;
          goto LABEL_18;
        }
      }
      else
      {
        if ( GetSystemDefaultLocaleName(LocaleName, 85) <= 0 )
        {
          LastError = GetLastError();
          inited = LastError;
          if ( LastError > 0 )
            inited = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          COSKPredictionManager::InitializePredictionsBasedOnLocale((COSKPredictionManager *)this, LocaleName);
        }
        if ( inited >= 0 )
        {
          inited = CoCreateInstance(
                     &CLSID_CUIAutomation,
                     0,
                     0x17u,
                     &GUID_30cbe57d_d9d0_452a_ab13_7ac5ac4825ee,
                     this + 38);
          if ( inited >= 0 )
          {
            inited = COSKPredictionManager::InitSettings((COSKPredictionManager *)this);
            if ( inited >= 0 )
            {
              *a3 = 1;
              *(_DWORD *)this = 8;
            }
          }
        }
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v8 = 10;
LABEL_18:
        WPP_SF_d(v7[2], v8, WPP_8ca0bf681196307d479db2488c079cf4_Traceguids, (unsigned int)Instance);
      }
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14001a12c  mov     [rsp+arg_8], rbx
0x14001a131  push    rsi
0x14001a132  push    rdi
0x14001a133  push    r14
0x14001a135  sub     rsp, 0F0h
0x14001a13c  mov     rax, cs:__security_cookie
0x14001a143  xor     rax, rsp
0x14001a146  mov     [rsp+108h+var_28], rax
0x14001a14e  xor     ebx, ebx
0x14001a150  mov     r14, r8
0x14001a153  mov     [r8], bl
0x14001a156  mov     rdi, rcx
0x14001a159  call    ?ShouldRunSecure@COSKUtils@@SA_NXZ; COSKUtils::ShouldRunSecure(void)
0x14001a15e  test    al, al
0x14001a160  jnz     loc_14001A285
0x14001a166  lea     rsi, [rdi+138h]
0x14001a16d  xor     edx, edx; pUnkOuter
0x14001a16f  lea     r9, _GUID_357fbe87_6c8e_490d_a059_4746c864ae6f; riid
0x14001a176  mov     [rsp+108h+ppv], rsi; ppv
0x14001a17b  lea     r8d, [rbx+1]; dwClsContext
0x14001a17f  lea     rcx, CLSID_TPLangMod; rclsid
0x14001a186  call    cs:__imp_CoCreateInstance
0x14001a18c  test    eax, eax
0x14001a18e  jns     short loc_14001A1B9
0x14001a190  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a197  lea     rdx, WPP_GLOBAL_Control
0x14001a19e  cmp     rcx, rdx
0x14001a1a1  jz      loc_14001A285
0x14001a1a7  test    byte ptr [rcx+1Ch], 10h
0x14001a1ab  jz      loc_14001A285
0x14001a1b1  lea     edx, [rbx+0Ah]
0x14001a1b4  jmp     loc_14001A272
0x14001a1b9  mov     rcx, [rsi]
0x14001a1bc  mov     esi, 8
0x14001a1c1  mov     edx, esi
0x14001a1c3  mov     rax, [rcx]
0x14001a1c6  mov     rax, [rax+98h]
0x14001a1cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a1d2  mov     ebx, eax
0x14001a1d4  test    eax, eax
0x14001a1d6  js      short loc_14001A254
0x14001a1d8  lea     edx, [rsi+4Dh]; cchLocaleName
0x14001a1db  lea     rcx, [rsp+108h+LocaleName]; lpLocaleName
0x14001a1e0  call    cs:__imp_GetSystemDefaultLocaleName
0x14001a1e6  test    eax, eax
0x14001a1e8  jle     short loc_14001A1F9
0x14001a1ea  lea     rdx, [rsp+108h+LocaleName]; unsigned __int16 *
0x14001a1ef  mov     rcx, rdi; this
0x14001a1f2  call    ?InitializePredictionsBasedOnLocale@COSKPredictionManager@@AEAAXPEAG@Z; COSKPredictionManager::InitializePredictionsBasedOnLocale(ushort *)
0x14001a1f7  jmp     short loc_14001A20E
0x14001a1f9  call    cs:__imp_GetLastError
0x14001a1ff  mov     ebx, eax
0x14001a201  test    eax, eax
0x14001a203  jle     short loc_14001A20E
0x14001a205  movzx   ebx, ax
0x14001a208  or      ebx, 80070000h
0x14001a20e  test    ebx, ebx
0x14001a210  js      short loc_14001A285
0x14001a212  xor     edx, edx; pUnkOuter
0x14001a214  lea     rax, [rdi+130h]
0x14001a21b  lea     r9, _GUID_30cbe57d_d9d0_452a_ab13_7ac5ac4825ee; riid
0x14001a222  mov     [rsp+108h+ppv], rax; ppv
0x14001a227  lea     rcx, CLSID_CUIAutomation; rclsid
0x14001a22e  lea     r8d, [rdx+17h]; dwClsContext
0x14001a232  call    cs:__imp_CoCreateInstance
0x14001a238  mov     ebx, eax
0x14001a23a  test    eax, eax
0x14001a23c  js      short loc_14001A285
0x14001a23e  mov     rcx, rdi; this
0x14001a241  call    ?InitSettings@COSKPredictionManager@@AEAAJXZ; COSKPredictionManager::InitSettings(void)
0x14001a246  mov     ebx, eax
0x14001a248  test    eax, eax
0x14001a24a  js      short loc_14001A285
0x14001a24c  mov     byte ptr [r14], 1
0x14001a250  mov     [rdi], esi
0x14001a252  jmp     short loc_14001A285
0x14001a254  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a25b  lea     rdx, WPP_GLOBAL_Control
0x14001a262  cmp     rcx, rdx
0x14001a265  jz      short loc_14001A285
0x14001a267  test    byte ptr [rcx+1Ch], 1
0x14001a26b  jz      short loc_14001A285
0x14001a26d  mov     edx, 0Bh
0x14001a272  mov     rcx, [rcx+10h]
0x14001a276  lea     r8, WPP_8ca0bf681196307d479db2488c079cf4_Traceguids
0x14001a27d  mov     r9d, eax
0x14001a280  call    WPP_SF_d
0x14001a285  mov     eax, ebx
0x14001a287  mov     rcx, [rsp+108h+var_28]
0x14001a28f  xor     rcx, rsp; StackCookie
0x14001a292  call    __security_check_cookie
0x14001a297  mov     rbx, [rsp+108h+arg_8]
0x14001a29f  add     rsp, 0F0h
0x14001a2a6  pop     r14
0x14001a2a8  pop     rdi
0x14001a2a9  pop     rsi
0x14001a2aa  retn
```
