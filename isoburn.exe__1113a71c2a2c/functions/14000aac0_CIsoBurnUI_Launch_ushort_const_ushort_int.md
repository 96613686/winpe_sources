# CIsoBurnUI::Launch(ushort const *,ushort,int)

- ea: `0x14000aac0`
- end: `0x14000ad04`
- name: `?Launch@CIsoBurnUI@@UEAAJPEBGGH@Z`
- size: `580`
- prototype: `int(CIsoBurnUI *__hidden this, const unsigned __int16 *, unsigned __int16, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140001fa0`
- `0x14000469c`
- `0x140004a44`
- `0x140009858`
- `0x14000aac0`
- `0x14000bd48`
- `0x14000f4a0`
- `0x14000f5bc`
- `0x140010010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x14000ac31`
- `KERNEL32!SetLastError` at `0x14000ac31`
- `KERNEL32!EnterCriticalSection` at `0x14000ac66`
- `KERNEL32!EnterCriticalSection` at `0x14000ac66`
- `KERNEL32!LeaveCriticalSection` at `0x14000ac85`
- `KERNEL32!LeaveCriticalSection` at `0x14000ac85`
- `KERNEL32!GetCurrentThreadId` at `0x14000ac56`
- `KERNEL32!GetCurrentThreadId` at `0x14000ac56`
- `USER32!GetDesktopWindow` at `0x14000ac0e`
- `USER32!GetDesktopWindow` at `0x14000ac0e`
- `USER32!DialogBoxParamW` at `0x14000aca6`
- `USER32!DialogBoxParamW` at `0x14000aca6`
- `SHLWAPI!SHRegGetValueW` at `0x14000ab6e`
- `SHLWAPI!SHRegGetValueW` at `0x14000ab6e`

## pseudocode

```c
__int64 __fastcall CIsoBurnUI::Launch(CIsoBurnUI *this, const unsigned __int16 *a2, unsigned __int16 a3, int a4)
{
  int v6; // edi
  unsigned int v7; // r8d
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  int Instance; // eax
  __int64 (__fastcall ***v10)(_QWORD, GUID *, char *); // r15
  HWND DesktopWindow; // rbp
  AtlThunkData_t *Data; // rax
  unsigned int v13; // edx
  __int64 v14; // rcx
  DWORD pcbData[4]; // [rsp+40h] [rbp-258h] BYREF
  unsigned __int16 pvData[264]; // [rsp+50h] [rbp-248h] BYREF

  *((_DWORD *)this + 34) = a4;
  v6 = CoAllocString(a2, (unsigned __int16 **)this + 16);
  if ( v6 >= 0 )
  {
    pvData[0] = 0;
    if ( a3 )
    {
      CIsoBurnUI::_GetVolumeNameForDriveLetter(a3, pvData, v7);
    }
    else
    {
      pcbData[0] = 520;
      SHRegGetValueW(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\CD Burning",
        L"CD Recorder Drive",
        2,
        0,
        pvData,
        pcbData);
    }
    if ( !pvData[0] || (v6 = CoAllocString(pvData, (unsigned __int16 **)this + 18), v6 >= 0) )
    {
      *(_QWORD *)pcbData = 0;
      v8 = 0;
      Instance = ATL::CComObject<CIsoBurn>::CreateInstance(pcbData);
      v10 = *(__int64 (__fastcall ****)(_QWORD, GUID *, char *))pcbData;
      v6 = Instance;
      if ( *(_QWORD *)pcbData && *(_QWORD *)pcbData != -56 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)pcbData + 56LL) + 8LL))(*(_QWORD *)pcbData + 56LL);
        v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))(v10 + 7);
      }
      if ( v6 >= 0 )
        v6 = (**v10)(v10, &GUID_1a510992_a9e1_4f66_b088_3651db0591d0, (char *)this + 160);
      if ( v8 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v8)[2])(v8);
      if ( v6 >= 0 )
      {
        DesktopWindow = GetDesktopWindow();
        Data = (AtlThunkData_t *)*((_QWORD *)this + 5);
        if ( Data || (Data = AtlThunk_AllocateData(), (*((_QWORD *)this + 5) = Data) != 0) )
        {
          AtlThunk_InitData(Data, 0, 0);
          if ( this == (CIsoBurnUI *)-16LL )
          {
            ATL::_AtlRaiseException(0xC0000005, v13);
            JUMPOUT(0x14000AD03LL);
          }
          *((_QWORD *)this + 2) = this;
          *((_DWORD *)this + 6) = GetCurrentThreadId();
          EnterCriticalSection(&stru_140016468);
          *((_QWORD *)this + 4) = qword_140016490;
          qword_140016490 = (__int64)this + 16;
          LeaveCriticalSection(&stru_140016468);
          DialogBoxParamW(
            hInstance,
            (LPCWSTR)0xC8,
            DesktopWindow,
            ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc,
            0);
        }
        else
        {
          SetLastError(0xEu);
        }
        v14 = *((_QWORD *)this + 20);
        if ( v14 )
        {
          *((_QWORD *)this + 20) = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000aac0  mov     [rsp+arg_10], rbx
0x14000aac5  mov     [rsp+arg_18], rbp
0x14000aaca  push    rsi
0x14000aacb  push    rdi
0x14000aacc  push    r12
0x14000aace  push    r14
0x14000aad0  push    r15
0x14000aad2  sub     rsp, 270h
0x14000aad9  mov     rax, cs:__security_cookie
0x14000aae0  xor     rax, rsp
0x14000aae3  mov     [rsp+298h+var_38], rax
0x14000aaeb  mov     rax, rdx
0x14000aaee  mov     [rcx+88h], r9d
0x14000aaf5  lea     rdx, [rcx+80h]; unsigned __int16 **
0x14000aafc  mov     rsi, rcx
0x14000aaff  mov     rcx, rax; unsigned __int16 *
0x14000ab02  movzx   ebx, r8w
0x14000ab06  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x14000ab0b  xor     r12d, r12d
0x14000ab0e  mov     edi, eax
0x14000ab10  test    eax, eax
0x14000ab12  js      loc_14000ACCB
0x14000ab18  mov     [rsp+298h+var_248], r12w
0x14000ab1e  test    bx, bx
0x14000ab21  jz      short loc_14000AB32
0x14000ab23  lea     rdx, [rsp+298h+var_248]; unsigned __int16 *
0x14000ab28  movzx   ecx, bx; unsigned __int16
0x14000ab2b  call    ?_GetVolumeNameForDriveLetter@CIsoBurnUI@@CAJGPEAGI@Z; CIsoBurnUI::_GetVolumeNameForDriveLetter(ushort,ushort *,uint)
0x14000ab30  jmp     short loc_14000AB74
0x14000ab32  lea     rax, [rsp+298h+var_258]
0x14000ab37  mov     [rsp+298h+var_258], 208h
0x14000ab3f  mov     [rsp+298h+pcbData], rax; pcbData
0x14000ab44  lea     r8, pszValue; "CD Recorder Drive"
0x14000ab4b  lea     rax, [rsp+298h+var_248]
0x14000ab50  mov     r9d, 2; srrfFlags
0x14000ab56  mov     [rsp+298h+pvData], rax; pvData
0x14000ab5b  lea     rdx, pszSubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14000ab62  mov     rcx, 0FFFFFFFF80000001h; hkey
0x14000ab69  mov     [rsp+298h+pdwType], r12; pdwType
0x14000ab6e  call    cs:__imp_SHRegGetValueW
0x14000ab74  cmp     [rsp+298h+var_248], r12w
0x14000ab7a  jz      short loc_14000AB97
0x14000ab7c  lea     rdx, [rsi+90h]; unsigned __int16 **
0x14000ab83  lea     rcx, [rsp+298h+var_248]; unsigned __int16 *
0x14000ab88  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x14000ab8d  mov     edi, eax
0x14000ab8f  test    eax, eax
0x14000ab91  js      loc_14000ACCB
0x14000ab97  lea     rcx, [rsp+298h+var_258]
0x14000ab9c  mov     qword ptr [rsp+298h+var_258], r12
0x14000aba1  mov     rbx, r12
0x14000aba4  call    ?CreateInstance@?$CComObject@VCIsoBurn@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CIsoBurn>::CreateInstance(ATL::CComObject<CIsoBurn> * *)
0x14000aba9  mov     r15, qword ptr [rsp+298h+var_258]
0x14000abae  mov     edi, eax
0x14000abb0  test    r15, r15
0x14000abb3  jz      short loc_14000ABD0
0x14000abb5  lea     r14, [r15+38h]
0x14000abb9  test    r14, r14
0x14000abbc  jz      short loc_14000ABD0
0x14000abbe  mov     rax, [r14]
0x14000abc1  mov     rcx, r14
0x14000abc4  mov     rax, [rax+8]
0x14000abc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abcd  mov     rbx, r14
0x14000abd0  test    edi, edi
0x14000abd2  js      short loc_14000ABF2
0x14000abd4  mov     rax, [r15]
0x14000abd7  lea     r8, [rsi+0A0h]
0x14000abde  lea     rdx, _GUID_1a510992_a9e1_4f66_b088_3651db0591d0
0x14000abe5  mov     rcx, r15
0x14000abe8  mov     rax, [rax]
0x14000abeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abf0  mov     edi, eax
0x14000abf2  test    rbx, rbx
0x14000abf5  jz      short loc_14000AC06
0x14000abf7  mov     rax, [rbx]
0x14000abfa  mov     rcx, rbx
0x14000abfd  mov     rax, [rax+10h]
0x14000ac01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac06  test    edi, edi
0x14000ac08  js      loc_14000ACCB
0x14000ac0e  call    cs:__imp_GetDesktopWindow
0x14000ac14  mov     rbp, rax
0x14000ac17  mov     rax, [rsi+28h]
0x14000ac1b  test    rax, rax
0x14000ac1e  jnz     short loc_14000AC39
0x14000ac20  call    AtlThunk_AllocateData
0x14000ac25  mov     [rsi+28h], rax
0x14000ac29  test    rax, rax
0x14000ac2c  jnz     short loc_14000AC39
0x14000ac2e  lea     ecx, [rax+0Eh]; dwErrCode
0x14000ac31  call    cs:__imp_SetLastError
0x14000ac37  jmp     short loc_14000ACAC
0x14000ac39  xor     r8d, r8d; FirstParameter
0x14000ac3c  xor     edx, edx; Proc
0x14000ac3e  mov     rcx, rax; Thunk
0x14000ac41  call    AtlThunk_InitData
0x14000ac46  lea     rbx, [rsi+10h]
0x14000ac4a  test    rbx, rbx
0x14000ac4d  jz      loc_14000ACF9
0x14000ac53  mov     [rbx], rsi
0x14000ac56  call    cs:__imp_GetCurrentThreadId
0x14000ac5c  lea     rcx, stru_140016468; lpCriticalSection
0x14000ac63  mov     [rbx+8], eax
0x14000ac66  call    cs:__imp_EnterCriticalSection
0x14000ac6c  mov     rax, cs:qword_140016490
0x14000ac73  lea     rcx, stru_140016468; lpCriticalSection
0x14000ac7a  mov     [rbx+10h], rax
0x14000ac7e  mov     cs:qword_140016490, rbx
0x14000ac85  call    cs:__imp_LeaveCriticalSection
0x14000ac8b  mov     rcx, cs:hInstance; hInstance
0x14000ac92  lea     r9, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x14000ac99  mov     r8, rbp; hWndParent
0x14000ac9c  mov     [rsp+298h+pdwType], r12; dwInitParam
0x14000aca1  mov     edx, 0C8h; lpTemplateName
0x14000aca6  call    cs:__imp_DialogBoxParamW
0x14000acac  mov     rcx, [rsi+0A0h]
0x14000acb3  test    rcx, rcx
0x14000acb6  jz      short loc_14000ACCB
0x14000acb8  mov     [rsi+0A0h], r12
0x14000acbf  mov     rax, [rcx]
0x14000acc2  mov     rax, [rax+10h]
0x14000acc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000accb  mov     eax, edi
0x14000accd  mov     rcx, [rsp+298h+var_38]
0x14000acd5  xor     rcx, rsp; StackCookie
0x14000acd8  call    __security_check_cookie
0x14000acdd  lea     r11, [rsp+298h+var_28]
0x14000ace5  mov     rbx, [r11+40h]
0x14000ace9  mov     rbp, [r11+48h]
0x14000aced  mov     rsp, r11
0x14000acf0  pop     r15
0x14000acf2  pop     r14
0x14000acf4  pop     r12
0x14000acf6  pop     rdi
0x14000acf7  pop     rsi
0x14000acf8  retn
0x14000acf9  mov     ecx, 0C0000005h; unsigned int
0x14000acfe  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
