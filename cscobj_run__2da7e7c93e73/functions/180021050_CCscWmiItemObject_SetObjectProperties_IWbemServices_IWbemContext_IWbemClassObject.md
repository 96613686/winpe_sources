# CCscWmiItemObject::_SetObjectProperties(IWbemServices *,IWbemContext *,IWbemClassObject *)

- ea: `0x180021050`
- end: `0x18002163a`
- name: `?_SetObjectProperties@CCscWmiItemObject@@MEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@@Z`
- size: `1514`
- prototype: `int(CCscWmiItemObject *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemClassObject *)`
- caller_count: `0`
- callee_count: `10`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x18001ca94`
- `0x18001caf8`
- `0x1800205ec`
- `0x180021050`
- `0x180022dc4`
- `0x1800230ac`
- `0x180023170`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002112f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002119e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002112f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002119e`
- `ntdll!RtlGetLengthWithoutLastFullDosOrNtPathElement` at `0x180021106`
- `ntdll!RtlGetLengthWithoutLastFullDosOrNtPathElement` at `0x180021106`
- `ntdll!RtlInitUnicodeString` at `0x1800210ef`
- `ntdll!RtlInitUnicodeString` at `0x1800210ef`

## string_xrefs

- `0x180021189`: `ParentItemPath`
- `0x1800210c8`: `ItemPath`

## pseudocode

```c
__int64 __fastcall CCscWmiItemObject::_SetObjectProperties(
        CCscWmiItemObject *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        struct IWbemClassObject *a4)
{
  __int64 v8; // rcx
  int v9; // eax
  int v10; // ebx
  const unsigned __int16 *v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 (__fastcall ***v14)(_QWORD, GUID *, struct _UNICODE_STRING *); // rcx
  __int64 v15; // rcx
  __int64 v16; // rdx
  CCscWmiItemObject *v17; // rcx
  CCscWmiItemObject *v18; // rcx
  CCscWmiItemObject *v19; // rcx
  CCscWmiItemObject *v20; // rcx
  CCscWmiItemObject *v21; // rcx
  CCscWmiItemObject *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rdx
  PCWSTR SourceString; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-20h] BYREF
  __int64 LengthOut; // [rsp+90h] [rbp+38h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 55, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids);
  }
  v8 = *((_QWORD *)this + 2);
  SourceString = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v8 + 32LL))(v8, &SourceString);
  v10 = v9;
  if ( v9 < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return (unsigned int)v10;
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      goto LABEL_57;
    v24 = 56;
    goto LABEL_55;
  }
  v10 = WmiProp_SetStringProperty(a4, L"ItemPath", SourceString);
  if ( v10 >= 0 )
  {
    v11 = SourceString;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, SourceString);
    LODWORD(LengthOut) = 0;
    if ( RtlGetLengthWithoutLastFullDosOrNtPathElement(0, &DestinationString.Length, (PULONG)&LengthOut) >= 0 )
      v11 += (unsigned int)LengthOut;
    v10 = WmiProp_SetStringProperty(a4, L"ItemName", v11);
  }
  CoTaskMemFree((LPVOID)SourceString);
  SourceString = 0;
  if ( v10 < 0 )
    goto LABEL_56;
  v12 = *((_QWORD *)this + 2);
  LengthOut = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 40LL))(v12, &LengthOut);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( (_WORD)v9 != 50 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return (unsigned int)v10;
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_57;
      v24 = 59;
      goto LABEL_55;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 58, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids);
    }
  }
  else
  {
    v10 = (*(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)LengthOut + 32LL))(LengthOut, &SourceString);
    if ( v10 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          57,
          WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
          (unsigned int)v10);
    }
    else
    {
      v10 = WmiProp_SetStringProperty(a4, L"ParentItemPath", SourceString);
      CoTaskMemFree((LPVOID)SourceString);
      SourceString = 0;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)LengthOut + 16LL))(LengthOut);
    if ( v10 < 0 )
      goto LABEL_56;
  }
  v13 = *((_QWORD *)this + 2);
  LODWORD(LengthOut) = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 24LL))(v13, &LengthOut);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v10 = WmiProp_SetUint32Property(a4, L"ItemType", LengthOut);
    if ( v10 >= 0 )
    {
      v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct _UNICODE_STRING *))*((_QWORD *)this + 2);
      *(_QWORD *)&DestinationString.Length = 0;
      v10 = (**v14)(v14, &GUID_8dfadead_26c2_4eff_8a72_6b50723d9a00, &DestinationString);
      if ( v10 < 0 )
      {
        if ( v10 == -2147467262 )
          v10 = 0;
        goto LABEL_39;
      }
      LODWORD(LengthOut) = 0;
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)&DestinationString.Length + 72LL))(
              *(_QWORD *)&DestinationString.Length,
              &LengthOut);
      if ( v10 < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
          goto LABEL_36;
        v16 = 61;
      }
      else
      {
        v10 = WmiProp_SetBooleanProperty(a4, L"Encrypted", LengthOut);
        if ( v10 < 0 )
        {
LABEL_36:
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&DestinationString.Length + 16LL))(*(_QWORD *)&DestinationString.Length);
LABEL_39:
          if ( v10 >= 0 )
          {
            CCscWmiItemAuxObject::CCscWmiItemAuxObject(
              (CCscWmiItemAuxObject *)&DestinationString,
              L"Win32_OfflineFilesFileSysInfo",
              *((struct IOfflineFilesItem **)this + 2));
            *(_QWORD *)&DestinationString.Length = &CCscWmiFileSysInfoObject::`vftable';
            v10 = CCscWmiItemObject::_SetAuxInfoObject(
                    v17,
                    a2,
                    a3,
                    a4,
                    (struct CCscWmiItemAuxObject *)&DestinationString,
                    L"FileSysInfo");
            CCscWmiItemAuxObject::~CCscWmiItemAuxObject((CCscWmiItemAuxObject *)&DestinationString);
            if ( v10 >= 0 )
            {
              CCscWmiItemAuxObject::CCscWmiItemAuxObject(
                (CCscWmiItemAuxObject *)&DestinationString,
                L"Win32_OfflineFilesPinInfo",
                *((struct IOfflineFilesItem **)this + 2));
              *(_QWORD *)&DestinationString.Length = &CCscWmiPinInfoObject::`vftable';
              v10 = CCscWmiItemObject::_SetAuxInfoObject(
                      v18,
                      a2,
                      a3,
                      a4,
                      (struct CCscWmiItemAuxObject *)&DestinationString,
                      L"PinInfo");
              CCscWmiItemAuxObject::~CCscWmiItemAuxObject((CCscWmiItemAuxObject *)&DestinationString);
              if ( v10 >= 0 )
              {
                CCscWmiItemAuxObject::CCscWmiItemAuxObject(
                  (CCscWmiItemAuxObject *)&DestinationString,
                  L"Win32_OfflineFilesChangeInfo",
                  *((struct IOfflineFilesItem **)this + 2));
                *(_QWORD *)&DestinationString.Length = &CCscWmiChangeInfoObject::`vftable';
                v10 = CCscWmiItemObject::_SetAuxInfoObject(
                        v19,
                        a2,
                        a3,
                        a4,
                        (struct CCscWmiItemAuxObject *)&DestinationString,
                        L"ChangeInfo");
                CCscWmiItemAuxObject::~CCscWmiItemAuxObject((CCscWmiItemAuxObject *)&DestinationString);
                if ( v10 >= 0 )
                {
                  CCscWmiItemAuxObject::CCscWmiItemAuxObject(
                    (CCscWmiItemAuxObject *)&DestinationString,
                    L"Win32_OfflineFilesDirtyInfo",
                    *((struct IOfflineFilesItem **)this + 2));
                  *(_QWORD *)&DestinationString.Length = &CCscWmiDirtyInfoObject::`vftable';
                  v10 = CCscWmiItemObject::_SetAuxInfoObject(
                          v20,
                          a2,
                          a3,
                          a4,
                          (struct CCscWmiItemAuxObject *)&DestinationString,
                          L"DirtyInfo");
                  CCscWmiItemAuxObject::~CCscWmiItemAuxObject((CCscWmiItemAuxObject *)&DestinationString);
                  if ( v10 >= 0 )
                  {
                    CCscWmiItemAuxObject::CCscWmiItemAuxObject(
                      (CCscWmiItemAuxObject *)&DestinationString,
                      L"Win32_OfflineFilesConnectionInfo",
                      *((struct IOfflineFilesItem **)this + 2));
                    *(_QWORD *)&DestinationString.Length = &CCscWmiConnectionInfoObject::`vftable';
                    v10 = CCscWmiItemObject::_SetAuxInfoObject(
                            v21,
                            a2,
                            a3,
                            a4,
                            (struct CCscWmiItemAuxObject *)&DestinationString,
                            L"ConnectionInfo");
                    CCscWmiItemAuxObject::~CCscWmiItemAuxObject((CCscWmiItemAuxObject *)&DestinationString);
                    if ( v10 >= 0 )
                    {
                      CCscWmiItemAuxObject::CCscWmiItemAuxObject(
                        (CCscWmiItemAuxObject *)&DestinationString,
                        L"Win32_OfflineFilesSuspendInfo",
                        *((struct IOfflineFilesItem **)this + 2));
                      *(_QWORD *)&DestinationString.Length = &CCscWmiSuspendInfoObject::`vftable';
                      v10 = CCscWmiItemObject::_SetAuxInfoObject(
                              v22,
                              a2,
                              a3,
                              a4,
                              (struct CCscWmiItemAuxObject *)&DestinationString,
                              L"SuspendInfo");
                      CCscWmiItemAuxObject::~CCscWmiItemAuxObject((CCscWmiItemAuxObject *)&DestinationString);
                    }
                  }
                }
              }
            }
          }
          goto LABEL_56;
        }
        v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)&DestinationString.Length + 64LL))(
                *(_QWORD *)&DestinationString.Length,
                &LengthOut);
        if ( v10 >= 0 )
        {
          v10 = WmiProp_SetBooleanProperty(a4, L"Sparse", LengthOut);
          goto LABEL_36;
        }
        v15 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
          goto LABEL_36;
        v16 = 62;
      }
      WPP_SF_d(*(_QWORD *)(v15 + 16), v16, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v10);
      goto LABEL_36;
    }
LABEL_56:
    v23 = WPP_GLOBAL_Control;
    goto LABEL_57;
  }
  v23 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)v10;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    v24 = 60;
LABEL_55:
    WPP_SF_d(*(_QWORD *)(v23 + 16), v24, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v9);
    goto LABEL_56;
  }
LABEL_57:
  if ( (_UNKNOWN *)v23 != &WPP_GLOBAL_Control && (*(_DWORD *)(v23 + 28) & 0x4000000) != 0 )
    WPP_SF_d(*(_QWORD *)(v23 + 16), 63, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180021050  push    rbp
0x180021052  push    rbx
0x180021053  push    rsi
0x180021054  push    r12
0x180021056  push    r14
0x180021058  push    r15
0x18002105a  mov     rbp, rsp
0x18002105d  sub     rsp, 58h
0x180021061  mov     rsi, r9
0x180021064  mov     r15, r8
0x180021067  mov     r12, rdx
0x18002106a  mov     r14, rcx
0x18002106d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021074  lea     rax, WPP_GLOBAL_Control
0x18002107b  cmp     rcx, rax
0x18002107e  jz      short loc_18002109E
0x180021080  test    dword ptr [rcx+1Ch], 4000000h
0x180021087  jz      short loc_18002109E
0x180021089  mov     rcx, [rcx+10h]
0x18002108d  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x180021094  mov     edx, 37h ; '7'
0x180021099  call    WPP_SF_
0x18002109e  mov     rcx, [r14+10h]
0x1800210a2  lea     rdx, [rbp+SourceString]
0x1800210a6  mov     [rbp+SourceString], 0
0x1800210ae  mov     rax, [rcx]
0x1800210b1  mov     rax, [rax+20h]
0x1800210b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210ba  mov     ebx, eax
0x1800210bc  test    eax, eax
0x1800210be  js      loc_1800215CC
0x1800210c4  mov     r8, [rbp+SourceString]; unsigned __int16 *
0x1800210c8  lea     rdx, CSCWMI_STR_PROP_ITEMPATH; "ItemPath"
0x1800210cf  mov     rcx, rsi; struct IWbemClassObject *
0x1800210d2  call    ?WmiProp_SetStringProperty@@YAJPEAUIWbemClassObject@@PEBG1@Z; WmiProp_SetStringProperty(IWbemClassObject *,ushort const *,ushort const *)
0x1800210d7  mov     ebx, eax
0x1800210d9  test    eax, eax
0x1800210db  js      short loc_18002112B
0x1800210dd  mov     rbx, [rbp+SourceString]
0x1800210e1  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800210e5  xorps   xmm0, xmm0
0x1800210e8  mov     rdx, rbx; SourceString
0x1800210eb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800210ef  call    cs:__imp_RtlInitUnicodeString
0x1800210f5  lea     r8, [rbp+LengthOut]; LengthOut
0x1800210f9  mov     dword ptr [rbp+LengthOut], 0
0x180021100  lea     rdx, [rbp+DestinationString]; Path
0x180021104  xor     ecx, ecx; Flags
0x180021106  call    cs:__imp_RtlGetLengthWithoutLastFullDosOrNtPathElement
0x18002110c  test    eax, eax
0x18002110e  js      short loc_180021117
0x180021110  mov     eax, dword ptr [rbp+LengthOut]
0x180021113  lea     rbx, [rbx+rax*2]
0x180021117  mov     r8, rbx; unsigned __int16 *
0x18002111a  lea     rdx, CSCWMI_STR_PROP_ITEMNAME; "ItemName"
0x180021121  mov     rcx, rsi; struct IWbemClassObject *
0x180021124  call    ?WmiProp_SetStringProperty@@YAJPEAUIWbemClassObject@@PEBG1@Z; WmiProp_SetStringProperty(IWbemClassObject *,ushort const *,ushort const *)
0x180021129  mov     ebx, eax
0x18002112b  mov     rcx, [rbp+SourceString]; pv
0x18002112f  call    cs:__imp_CoTaskMemFree
0x180021135  mov     [rbp+SourceString], 0
0x18002113d  test    ebx, ebx
0x18002113f  js      loc_1800211F3
0x180021145  mov     rcx, [r14+10h]
0x180021149  lea     rdx, [rbp+LengthOut]
0x18002114d  mov     [rbp+LengthOut], 0
0x180021155  mov     rax, [rcx]
0x180021158  mov     rax, [rax+28h]
0x18002115c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021161  mov     ebx, eax
0x180021163  test    eax, eax
0x180021165  js      loc_1800211FF
0x18002116b  mov     rcx, [rbp+LengthOut]
0x18002116f  lea     rdx, [rbp+SourceString]
0x180021173  mov     rax, [rcx]
0x180021176  mov     rax, [rax+20h]
0x18002117a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002117f  mov     ebx, eax
0x180021181  test    eax, eax
0x180021183  js      short loc_1800211AE
0x180021185  mov     r8, [rbp+SourceString]; unsigned __int16 *
0x180021189  lea     rdx, CSCWMI_STR_PROP_PARENTITEMPATH; "ParentItemPath"
0x180021190  mov     rcx, rsi; struct IWbemClassObject *
0x180021193  call    ?WmiProp_SetStringProperty@@YAJPEAUIWbemClassObject@@PEBG1@Z; WmiProp_SetStringProperty(IWbemClassObject *,ushort const *,ushort const *)
0x180021198  mov     rcx, [rbp+SourceString]; pv
0x18002119c  mov     ebx, eax
0x18002119e  call    cs:__imp_CoTaskMemFree
0x1800211a4  mov     [rbp+SourceString], 0
0x1800211ac  jmp     short loc_1800211DF
0x1800211ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211b5  lea     rax, WPP_GLOBAL_Control
0x1800211bc  cmp     rcx, rax
0x1800211bf  jz      short loc_1800211DF
0x1800211c1  test    byte ptr [rcx+1Ch], 2
0x1800211c5  jz      short loc_1800211DF
0x1800211c7  mov     rcx, [rcx+10h]
0x1800211cb  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x1800211d2  mov     edx, 39h ; '9'
0x1800211d7  mov     r9d, ebx
0x1800211da  call    WPP_SF_d
0x1800211df  mov     rcx, [rbp+LengthOut]
0x1800211e3  mov     rax, [rcx]
0x1800211e6  mov     rax, [rax+10h]
0x1800211ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211ef  test    ebx, ebx
0x1800211f1  jns     short loc_18002123A
0x1800211f3  lea     rsi, WPP_GLOBAL_Control
0x1800211fa  jmp     loc_1800215FD
0x1800211ff  cmp     ax, 32h ; '2'
0x180021203  jnz     loc_1800215AC
0x180021209  mov     rcx, cs:WPP_GLOBAL_Control
0x180021210  lea     rax, WPP_GLOBAL_Control
0x180021217  cmp     rcx, rax
0x18002121a  jz      short loc_18002123A
0x18002121c  test    dword ptr [rcx+1Ch], 4000000h
0x180021223  jz      short loc_18002123A
0x180021225  mov     rcx, [rcx+10h]
0x180021229  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x180021230  mov     edx, 3Ah ; ':'
0x180021235  call    WPP_SF_
0x18002123a  mov     rcx, [r14+10h]
0x18002123e  lea     rdx, [rbp+LengthOut]
0x180021242  mov     dword ptr [rbp+LengthOut], 0
0x180021249  mov     rax, [rcx]
0x18002124c  mov     rax, [rax+18h]
0x180021250  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021255  mov     ebx, eax
0x180021257  test    eax, eax
0x180021259  js      loc_180021588
0x18002125f  mov     r8d, dword ptr [rbp+LengthOut]; unsigned int
0x180021263  lea     rdx, CSCWMI_STR_PROP_ITEMTYPE; "ItemType"
0x18002126a  mov     rcx, rsi; struct IWbemClassObject *
0x18002126d  call    ?WmiProp_SetUint32Property@@YAJPEAUIWbemClassObject@@PEBGK@Z; WmiProp_SetUint32Property(IWbemClassObject *,ushort const *,ulong)
0x180021272  mov     ebx, eax
0x180021274  test    eax, eax
0x180021276  js      loc_1800211F3
0x18002127c  mov     rcx, [r14+10h]
0x180021280  lea     r8, [rbp+DestinationString]
0x180021284  mov     qword ptr [rbp+DestinationString.Length], 0
0x18002128c  lea     rdx, _GUID_8dfadead_26c2_4eff_8a72_6b50723d9a00
0x180021293  mov     rax, [rcx]
0x180021296  mov     rax, [rax]
0x180021299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002129e  mov     ebx, eax
0x1800212a0  test    eax, eax
0x1800212a2  js      loc_18002137A
0x1800212a8  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x1800212ac  lea     rdx, [rbp+LengthOut]
0x1800212b0  mov     dword ptr [rbp+LengthOut], 0
0x1800212b7  mov     rax, [rcx]
0x1800212ba  mov     rax, [rax+48h]
0x1800212be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212c3  mov     ebx, eax
0x1800212c5  test    eax, eax
0x1800212c7  js      short loc_180021337
0x1800212c9  mov     r8d, dword ptr [rbp+LengthOut]; int
0x1800212cd  lea     rdx, CSCWMI_STR_PROP_ENCRYPTED; "Encrypted"
0x1800212d4  mov     rcx, rsi; struct IWbemClassObject *
0x1800212d7  call    ?WmiProp_SetBooleanProperty@@YAJPEAUIWbemClassObject@@PEBGH@Z; WmiProp_SetBooleanProperty(IWbemClassObject *,ushort const *,int)
0x1800212dc  mov     ebx, eax
0x1800212de  test    eax, eax
0x1800212e0  js      loc_180021368
0x1800212e6  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x1800212ea  lea     rdx, [rbp+LengthOut]
0x1800212ee  mov     rax, [rcx]
0x1800212f1  mov     rax, [rax+40h]
0x1800212f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212fa  mov     ebx, eax
0x1800212fc  test    eax, eax
0x1800212fe  js      short loc_180021317
0x180021300  mov     r8d, dword ptr [rbp+LengthOut]; int
0x180021304  lea     rdx, CSCWMI_STR_PROP_SPARSE; "Sparse"
0x18002130b  mov     rcx, rsi; struct IWbemClassObject *
0x18002130e  call    ?WmiProp_SetBooleanProperty@@YAJPEAUIWbemClassObject@@PEBGH@Z; WmiProp_SetBooleanProperty(IWbemClassObject *,ushort const *,int)
0x180021313  mov     ebx, eax
0x180021315  jmp     short loc_180021368
0x180021317  mov     rcx, cs:WPP_GLOBAL_Control
0x18002131e  lea     rax, WPP_GLOBAL_Control
0x180021325  cmp     rcx, rax
0x180021328  jz      short loc_180021368
0x18002132a  test    byte ptr [rcx+1Ch], 2
0x18002132e  jz      short loc_180021368
0x180021330  mov     edx, 3Eh ; '>'
0x180021335  jmp     short loc_180021355
0x180021337  mov     rcx, cs:WPP_GLOBAL_Control
0x18002133e  lea     rax, WPP_GLOBAL_Control
0x180021345  cmp     rcx, rax
0x180021348  jz      short loc_180021368
0x18002134a  test    byte ptr [rcx+1Ch], 2
0x18002134e  jz      short loc_180021368
0x180021350  mov     edx, 3Dh ; '='
0x180021355  mov     rcx, [rcx+10h]
0x180021359  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x180021360  mov     r9d, ebx
0x180021363  call    WPP_SF_d
0x180021368  mov     rcx, qword ptr [rbp+DestinationString.Length]
0x18002136c  mov     rax, [rcx]
0x18002136f  mov     rax, [rax+10h]
0x180021373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021378  jmp     short loc_180021385
0x18002137a  xor     eax, eax
0x18002137c  cmp     ebx, 80004002h
0x180021382  cmovz   ebx, eax
0x180021385  test    ebx, ebx
0x180021387  js      loc_1800211F3
0x18002138d  mov     r8, [r14+10h]; struct IOfflineFilesItem *
0x180021391  lea     rdx, CSCWMI_STR_OFFLINEFILESFILESYSINFO; "Win32_OfflineFilesFileSysInfo"
0x180021398  lea     rcx, [rbp+DestinationString]; this
0x18002139c  call    ??0CCscWmiItemAuxObject@@QEAA@PEBGPEAUIOfflineFilesItem@@@Z; CCscWmiItemAuxObject::CCscWmiItemAuxObject(ushort const *,IOfflineFilesItem *)
0x1800213a1  lea     rax, ??_7CCscWmiFileSysInfoObject@@6B@; const CCscWmiFileSysInfoObject::`vftable'
0x1800213a8  mov     r9, rsi; struct IWbemClassObject *
0x1800213ab  mov     qword ptr [rbp+DestinationString.Length], rax
0x1800213af  mov     r8, r15; struct IWbemContext *
0x1800213b2  lea     rax, CSCWMI_STR_PROP_FILESYSINFO; "FileSysInfo"
0x1800213b9  mov     rdx, r12; struct IWbemServices *
0x1800213bc  mov     [rsp+58h+var_30], rax; unsigned __int16 *
0x1800213c1  lea     rax, [rbp+DestinationString]
0x1800213c5  mov     [rsp+58h+var_38], rax; struct CCscWmiItemAuxObject *
0x1800213ca  call    ?_SetAuxInfoObject@CCscWmiItemObject@@IEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@AEAVCCscWmiItemAuxObject@@PEBG@Z; CCscWmiItemObject::_SetAuxInfoObject(IWbemServices *,IWbemContext *,IWbemClassObject *,CCscWmiItemAuxObject &,ushort const *)
0x1800213cf  lea     rcx, [rbp+DestinationString]; this
0x1800213d3  mov     ebx, eax
0x1800213d5  call    ??1CCscWmiItemAuxObject@@UEAA@XZ; CCscWmiItemAuxObject::~CCscWmiItemAuxObject(void)
0x1800213da  test    ebx, ebx
0x1800213dc  js      loc_1800211F3
0x1800213e2  mov     r8, [r14+10h]; struct IOfflineFilesItem *
0x1800213e6  lea     rdx, CSCWMI_STR_OFFLINEFILESPININFO; "Win32_OfflineFilesPinInfo"
0x1800213ed  lea     rcx, [rbp+DestinationString]; this
0x1800213f1  call    ??0CCscWmiItemAuxObject@@QEAA@PEBGPEAUIOfflineFilesItem@@@Z; CCscWmiItemAuxObject::CCscWmiItemAuxObject(ushort const *,IOfflineFilesItem *)
0x1800213f6  lea     rax, ??_7CCscWmiPinInfoObject@@6B@; const CCscWmiPinInfoObject::`vftable'
0x1800213fd  mov     r9, rsi; struct IWbemClassObject *
0x180021400  mov     qword ptr [rbp+DestinationString.Length], rax
0x180021404  mov     r8, r15; struct IWbemContext *
0x180021407  lea     rax, CSCWMI_STR_PROP_PININFO; "PinInfo"
0x18002140e  mov     rdx, r12; struct IWbemServices *
0x180021411  mov     [rsp+58h+var_30], rax; unsigned __int16 *
0x180021416  lea     rax, [rbp+DestinationString]
0x18002141a  mov     [rsp+58h+var_38], rax; struct CCscWmiItemAuxObject *
0x18002141f  call    ?_SetAuxInfoObject@CCscWmiItemObject@@IEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@AEAVCCscWmiItemAuxObject@@PEBG@Z; CCscWmiItemObject::_SetAuxInfoObject(IWbemServices *,IWbemContext *,IWbemClassObject *,CCscWmiItemAuxObject &,ushort const *)
0x180021424  lea     rcx, [rbp+DestinationString]; this
0x180021428  mov     ebx, eax
0x18002142a  call    ??1CCscWmiItemAuxObject@@UEAA@XZ; CCscWmiItemAuxObject::~CCscWmiItemAuxObject(void)
0x18002142f  test    ebx, ebx
0x180021431  js      loc_1800211F3
0x180021437  mov     r8, [r14+10h]; struct IOfflineFilesItem *
0x18002143b  lea     rdx, CSCWMI_STR_OFFLINEFILESCHANGEINFO; "Win32_OfflineFilesChangeInfo"
0x180021442  lea     rcx, [rbp+DestinationString]; this
0x180021446  call    ??0CCscWmiItemAuxObject@@QEAA@PEBGPEAUIOfflineFilesItem@@@Z; CCscWmiItemAuxObject::CCscWmiItemAuxObject(ushort const *,IOfflineFilesItem *)
0x18002144b  lea     rax, ??_7CCscWmiChangeInfoObject@@6B@; const CCscWmiChangeInfoObject::`vftable'
0x180021452  mov     r9, rsi; struct IWbemClassObject *
0x180021455  mov     qword ptr [rbp+DestinationString.Length], rax
0x180021459  mov     r8, r15; struct IWbemContext *
0x18002145c  lea     rax, CSCWMI_STR_PROP_CHANGEINFO; "ChangeInfo"
0x180021463  mov     rdx, r12; struct IWbemServices *
0x180021466  mov     [rsp+58h+var_30], rax; unsigned __int16 *
0x18002146b  lea     rax, [rbp+DestinationString]
0x18002146f  mov     [rsp+58h+var_38], rax; struct CCscWmiItemAuxObject *
0x180021474  call    ?_SetAuxInfoObject@CCscWmiItemObject@@IEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@AEAVCCscWmiItemAuxObject@@PEBG@Z; CCscWmiItemObject::_SetAuxInfoObject(IWbemServices *,IWbemContext *,IWbemClassObject *,CCscWmiItemAuxObject &,ushort const *)
0x180021479  lea     rcx, [rbp+DestinationString]; this
0x18002147d  mov     ebx, eax
0x18002147f  call    ??1CCscWmiItemAuxObject@@UEAA@XZ; CCscWmiItemAuxObject::~CCscWmiItemAuxObject(void)
0x180021484  test    ebx, ebx
0x180021486  js      loc_1800211F3
0x18002148c  mov     r8, [r14+10h]; struct IOfflineFilesItem *
0x180021490  lea     rdx, CSCWMI_STR_OFFLINEFILESDIRTYINFO; "Win32_OfflineFilesDirtyInfo"
0x180021497  lea     rcx, [rbp+DestinationString]; this
0x18002149b  call    ??0CCscWmiItemAuxObject@@QEAA@PEBGPEAUIOfflineFilesItem@@@Z; CCscWmiItemAuxObject::CCscWmiItemAuxObject(ushort const *,IOfflineFilesItem *)
0x1800214a0  lea     rax, ??_7CCscWmiDirtyInfoObject@@6B@; const CCscWmiDirtyInfoObject::`vftable'
0x1800214a7  mov     r9, rsi; struct IWbemClassObject *
0x1800214aa  mov     qword ptr [rbp+DestinationString.Length], rax
0x1800214ae  mov     r8, r15; struct IWbemContext *
0x1800214b1  lea     rax, CSCWMI_STR_PROP_DIRTYINFO; "DirtyInfo"
0x1800214b8  mov     rdx, r12; struct IWbemServices *
0x1800214bb  mov     [rsp+58h+var_30], rax; unsigned __int16 *
0x1800214c0  lea     rax, [rbp+DestinationString]
0x1800214c4  mov     [rsp+58h+var_38], rax; struct CCscWmiItemAuxObject *
0x1800214c9  call    ?_SetAuxInfoObject@CCscWmiItemObject@@IEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@AEAVCCscWmiItemAuxObject@@PEBG@Z; CCscWmiItemObject::_SetAuxInfoObject(IWbemServices *,IWbemContext *,IWbemClassObject *,CCscWmiItemAuxObject &,ushort const *)
0x1800214ce  lea     rcx, [rbp+DestinationString]; this
0x1800214d2  mov     ebx, eax
0x1800214d4  call    ??1CCscWmiItemAuxObject@@UEAA@XZ; CCscWmiItemAuxObject::~CCscWmiItemAuxObject(void)
0x1800214d9  test    ebx, ebx
0x1800214db  js      loc_1800211F3
0x1800214e1  mov     r8, [r14+10h]; struct IOfflineFilesItem *
0x1800214e5  lea     rdx, CSCWMI_STR_OFFLINEFILESCONNECTIONINFO; "Win32_OfflineFilesConnectionInfo"
0x1800214ec  lea     rcx, [rbp+DestinationString]; this
0x1800214f0  call    ??0CCscWmiItemAuxObject@@QEAA@PEBGPEAUIOfflineFilesItem@@@Z; CCscWmiItemAuxObject::CCscWmiItemAuxObject(ushort const *,IOfflineFilesItem *)
0x1800214f5  lea     rax, ??_7CCscWmiConnectionInfoObject@@6B@; const CCscWmiConnectionInfoObject::`vftable'
0x1800214fc  mov     r9, rsi; struct IWbemClassObject *
0x1800214ff  mov     qword ptr [rbp+DestinationString.Length], rax
0x180021503  mov     r8, r15; struct IWbemContext *
0x180021506  lea     rax, CSCWMI_STR_PROP_CONNECTIONINFO; "ConnectionInfo"
0x18002150d  mov     rdx, r12; struct IWbemServices *
0x180021510  mov     [rsp+58h+var_30], rax; unsigned __int16 *
0x180021515  lea     rax, [rbp+DestinationString]
0x180021519  mov     [rsp+58h+var_38], rax; struct CCscWmiItemAuxObject *
0x18002151e  call    ?_SetAuxInfoObject@CCscWmiItemObject@@IEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemClassObject@@AEAVCCscWmiItemAuxObject@@PEBG@Z; CCscWmiItemObject::_SetAuxInfoObject(IWbemServices *,IWbemContext *,IWbemClassObject *,CCscWmiItemAuxObject &,ushort const *)
0x180021523  lea     rcx, [rbp+DestinationString]; this
0x180021527  mov     ebx, eax
0x180021529  call    ??1CCscWmiItemAuxObject@@UEAA@XZ; CCscWmiItemAuxObject::~CCscWmiItemAuxObject(void)
0x18002152e  test    ebx, ebx
0x180021530  js      loc_1800211F3
  ... truncated ...
```
