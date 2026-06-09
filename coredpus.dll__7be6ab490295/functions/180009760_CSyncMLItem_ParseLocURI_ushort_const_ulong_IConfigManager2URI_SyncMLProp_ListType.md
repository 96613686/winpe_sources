# CSyncMLItem::ParseLocURI(ushort const *,ulong,IConfigManager2URI * *,SyncMLProp *,ListType *)

- ea: `0x180009760`
- end: `0x180009c61`
- name: `?ParseLocURI@CSyncMLItem@@CAJPEBGKPEAPEAUIConfigManager2URI@@PEAW4SyncMLProp@@PEAW4ListType@@@Z`
- size: `1281`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct IConfigManager2URI **, enum SyncMLProp *, enum ListType *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008d30`

## callees

- `0x180009760`
- `0x180014330`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009b56`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180009b56`
- `OLEAUT32!__imp_SysFreeString` at `0x180009a5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180009a5c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a4c`
- `DMCmnUtils!InvStrCmpNIW` at `0x1800099e2`
- `DMCmnUtils!InvStrCmpNIW` at `0x180009c22`
- `DMCmnUtils!InvStrCmpNIW` at `0x1800099e2`
- `DMCmnUtils!InvStrCmpNIW` at `0x180009c22`
- `DMCmnUtils!CopyString` at `0x1800097f9`
- `DMCmnUtils!CopyString` at `0x1800097f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000982e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000982e`

## pseudocode

```c
__int64 __fastcall CSyncMLItem::ParseLocURI(
        const unsigned __int16 *a1,
        unsigned int a2,
        struct IConfigManager2URI **a3,
        enum SyncMLProp *a4,
        enum ListType *a5)
{
  HRESULT v6; // ebx
  int v7; // eax
  int v8; // eax
  const unsigned __int16 *v9; // rsi
  BSTR v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // r14
  struct IConfigManager2URI *v15; // rax
  const unsigned __int16 *v17; // rsi
  BSTR v18; // rax
  __int64 v19; // rcx
  unsigned __int64 v20; // rbx
  __int64 v21; // rdi
  __int64 v22; // r14
  LPVOID ppv; // [rsp+38h] [rbp-71h] BYREF
  struct IConfigManager2URI *v24; // [rsp+40h] [rbp-69h] BYREF
  int v25; // [rsp+48h] [rbp-61h] BYREF
  int v26; // [rsp+4Ch] [rbp-5Dh] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-59h] BYREF
  int v28; // [rsp+58h] [rbp-51h] BYREF
  HRESULT v29; // [rsp+5Ch] [rbp-4Dh] BYREF
  struct IConfigManager2URI **v30; // [rsp+60h] [rbp-49h]
  HLOCAL hMem; // [rsp+68h] [rbp-41h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+80h] [rbp-29h] BYREF
  int *v34; // [rsp+90h] [rbp-19h]
  int v35; // [rsp+98h] [rbp-11h]
  int v36; // [rsp+9Ch] [rbp-Dh]
  HRESULT *v37; // [rsp+A0h] [rbp-9h]
  __int64 v38; // [rsp+A8h] [rbp-1h]

  v30 = a3;
  hMem = 0;
  bstrString = 0;
  v28 = 0;
  v26 = 0;
  v25 = 0;
  ppv = 0;
  v24 = 0;
  if ( !a1 )
  {
    v6 = -2147467261;
    goto LABEL_35;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    goto LABEL_35;
  }
  if ( !a3 )
  {
    v6 = -2147467261;
    goto LABEL_35;
  }
  v6 = CopyString(a1, a2, (unsigned __int16 **)&hMem);
  if ( v6 >= 0 )
  {
    v6 = CoCreateInstance(
           &GUID_c196b2be_ba06_4049_8518_322e1e04282b,
           0,
           1u,
           &GUID_4b965405_f21f_4702_95dd_4e81c3d1bb30,
           &ppv);
    if ( v6 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPVOID, HLOCAL))(*(_QWORD *)ppv + 40LL))(ppv, hMem);
      v6 = v7;
      if ( v7 != -2147418113 && v7 != -2147024882 )
      {
        if ( v7 < 0 )
        {
          v6 = -2102788095;
          goto LABEL_35;
        }
        v6 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 136LL))(ppv, &v28);
        if ( v6 >= 0 )
        {
          v6 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 24LL))(ppv, &v25);
          if ( v6 >= 0 )
          {
            if ( v25
              || (v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppv + 208LL))(
                         ppv,
                         0,
                         L".",
                         0),
                  v6 >= 0) )
            {
              v6 = (*(__int64 (__fastcall **)(LPVOID, struct IConfigManager2URI **))(*(_QWORD *)ppv + 224LL))(ppv, &v24);
              if ( v6 >= 0 )
              {
                v6 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)v24 + 32LL))(v24, &v26);
                if ( v6 >= 0 )
                {
                  if ( !v26 )
                  {
LABEL_34:
                    v15 = v24;
                    v24 = 0;
                    *v30 = v15;
                    goto LABEL_35;
                  }
                  v8 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, const unsigned __int16 * near *, BSTR *))(*(_QWORD *)v24 + 128LL))(
                         v24,
                         c_rgszQueryNameType,
                         &bstrString);
                  v6 = v8;
                  if ( v8 >= 0 )
                  {
                    v9 = bstrString;
                    if ( bstrString && *bstrString )
                    {
                      v10 = bstrString;
                      v11 = 0x7FFFFFFF;
                      do
                      {
                        if ( !*v10 )
                          break;
                        ++v10;
                        --v11;
                      }
                      while ( v11 );
                      v12 = 0x7FFFFFFF - v11;
                      if ( v11 )
                      {
                        v13 = 0;
                        while ( 1 )
                        {
                          v14 = 8 * v13 + 255104;
                          if ( !InvStrCmpNIW(v9, *(const unsigned __int16 **)((char *)&_ImageBase + v14), v12)
                            && !*(_WORD *)(*(_QWORD *)((char *)&_ImageBase + v14) + 2 * v12) )
                          {
                            break;
                          }
                          v13 = (unsigned int)(v13 + 1);
                          if ( (int)v13 >= 15 )
                            goto LABEL_31;
                        }
                        v6 = 0;
                        if ( a4 )
                          *(_DWORD *)a4 = v13;
                        goto LABEL_34;
                      }
                    }
LABEL_31:
                    v6 = -2102788095;
                    goto LABEL_35;
                  }
                  if ( v8 == -2147023728 )
                  {
                    if ( (*(int (__fastcall **)(struct IConfigManager2URI *, wchar_t *, BSTR *))(*(_QWORD *)v24 + 128LL))(
                           v24,
                           off_18003E220,
                           &bstrString) >= 0 )
                    {
                      v17 = bstrString;
                      if ( bstrString )
                      {
                        if ( *bstrString )
                        {
                          v18 = bstrString;
                          v19 = 0x7FFFFFFF;
                          do
                          {
                            if ( !*v18 )
                              break;
                            ++v18;
                            --v19;
                          }
                          while ( v19 );
                          v20 = 0x7FFFFFFF - v19;
                          if ( v19 )
                          {
                            v21 = 0;
                            while ( 1 )
                            {
                              v22 = 8 * v21 + 254216;
                              if ( !InvStrCmpNIW(v17, *(const unsigned __int16 **)((char *)&_ImageBase + v22), v20)
                                && !*(_WORD *)(*(_QWORD *)((char *)&_ImageBase + v22) + 2 * v20) )
                              {
                                break;
                              }
                              v21 = (unsigned int)(v21 + 1);
                              if ( (int)v21 >= 2 )
                              {
                                v6 = -2102788095;
                                goto LABEL_35;
                              }
                            }
                            v6 = 0;
                            if ( a5 )
                              *(_DWORD *)a5 = v21;
                            goto LABEL_34;
                          }
                        }
                      }
                    }
                    goto LABEL_31;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_35:
  LocalFree(hMem);
  SysFreeString(bstrString);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v29 = v6;
    v37 = &v29;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v38 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v34 = &dword_18003626C;
    UserData.Reserved = 2;
    v35 = 24;
    v36 = 1;
    LODWORD(v30) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009760  mov     r11, rsp
0x180009763  push    rbp
0x180009764  push    rbx
0x180009765  lea     rbp, [r11-57h]
0x180009769  sub     rsp, 0E8h
0x180009770  mov     rax, cs:__security_cookie
0x180009777  xor     rax, rsp
0x18000977a  mov     [rbp+4Fh+var_48], rax
0x18000977e  mov     [r11-28h], r12
0x180009782  mov     rax, r8
0x180009785  mov     [r11-30h], r13
0x180009789  mov     r12, r9
0x18000978c  mov     r13, [rbp+4Fh+arg_20]
0x180009790  mov     [rbp+4Fh+var_98], rax
0x180009794  mov     [rbp+4Fh+hMem], 0
0x18000979c  mov     [rbp+4Fh+bstrString], 0
0x1800097a4  mov     [rbp+4Fh+var_A0], 0
0x1800097ab  mov     [rbp+4Fh+var_AC], 0
0x1800097b2  mov     [rbp+4Fh+var_B0], 0
0x1800097b9  mov     [rbp+4Fh+var_C0], 0
0x1800097c1  mov     [rbp+4Fh+var_B8], 0
0x1800097c9  test    rcx, rcx
0x1800097cc  jnz     short loc_1800097D8
0x1800097ce  mov     ebx, 80004003h
0x1800097d3  jmp     loc_180009A48
0x1800097d8  test    edx, edx
0x1800097da  jnz     short loc_1800097E6
0x1800097dc  mov     ebx, 80070057h
0x1800097e1  jmp     loc_180009A48
0x1800097e6  test    rax, rax
0x1800097e9  jnz     short loc_1800097F5
0x1800097eb  mov     ebx, 80004003h
0x1800097f0  jmp     loc_180009A48
0x1800097f5  lea     r8, [rbp+4Fh+hMem]
0x1800097f9  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180009800  nop     dword ptr [rax+rax+00h]
0x180009805  mov     ebx, eax
0x180009807  test    eax, eax
0x180009809  js      loc_180009A48
0x18000980f  lea     rax, [rbp+4Fh+var_C0]
0x180009813  xor     edx, edx; pUnkOuter
0x180009815  lea     r9, _GUID_4b965405_f21f_4702_95dd_4e81c3d1bb30; riid
0x18000981c  mov     [rsp+0F0h+ppv], rax; ppv
0x180009821  mov     r8d, 1; dwClsContext
0x180009827  lea     rcx, _GUID_c196b2be_ba06_4049_8518_322e1e04282b; rclsid
0x18000982e  call    cs:__imp_CoCreateInstance
0x180009835  nop     dword ptr [rax+rax+00h]
0x18000983a  mov     ebx, eax
0x18000983c  test    eax, eax
0x18000983e  js      loc_180009A48
0x180009844  mov     rcx, [rbp+4Fh+var_C0]
0x180009848  mov     rdx, [rbp+4Fh+hMem]
0x18000984c  mov     rax, [rcx]
0x18000984f  mov     rax, [rax+28h]
0x180009853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009858  mov     ebx, eax
0x18000985a  cmp     eax, 8000FFFFh
0x18000985f  jz      loc_180009A48
0x180009865  cmp     eax, 8007000Eh
0x18000986a  jz      loc_180009A48
0x180009870  test    eax, eax
0x180009872  jns     short loc_18000987E
0x180009874  mov     ebx, 82AA0001h
0x180009879  jmp     loc_180009A48
0x18000987e  mov     rcx, [rbp+4Fh+var_C0]
0x180009882  lea     rdx, [rbp+4Fh+var_A0]
0x180009886  mov     rax, [rcx]
0x180009889  mov     rax, [rax+88h]
0x180009890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009895  mov     ebx, eax
0x180009897  test    eax, eax
0x180009899  js      loc_180009A48
0x18000989f  mov     rcx, [rbp+4Fh+var_C0]
0x1800098a3  lea     rdx, [rbp+4Fh+var_B0]
0x1800098a7  mov     rax, [rcx]
0x1800098aa  mov     rax, [rax+18h]
0x1800098ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098b3  mov     ebx, eax
0x1800098b5  test    eax, eax
0x1800098b7  js      loc_180009A48
0x1800098bd  cmp     [rbp+4Fh+var_B0], 0
0x1800098c1  jnz     short loc_1800098EC
0x1800098c3  mov     rcx, [rbp+4Fh+var_C0]
0x1800098c7  lea     r8, asc_180034448; "."
0x1800098ce  xor     r9d, r9d
0x1800098d1  xor     edx, edx
0x1800098d3  mov     rax, [rcx]
0x1800098d6  mov     rax, [rax+0D0h]
0x1800098dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098e2  mov     ebx, eax
0x1800098e4  test    eax, eax
0x1800098e6  js      loc_180009A48
0x1800098ec  mov     rcx, [rbp+4Fh+var_C0]
0x1800098f0  lea     rdx, [rbp+4Fh+var_B8]
0x1800098f4  mov     rax, [rcx]
0x1800098f7  mov     rax, [rax+0E0h]
0x1800098fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009903  mov     ebx, eax
0x180009905  test    eax, eax
0x180009907  js      loc_180009A48
0x18000990d  mov     rcx, [rbp+4Fh+var_B8]
0x180009911  lea     rdx, [rbp+4Fh+var_AC]
0x180009915  mov     rax, [rcx]
0x180009918  mov     rax, [rax+20h]
0x18000991c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009921  mov     ebx, eax
0x180009923  test    eax, eax
0x180009925  js      loc_180009A48
0x18000992b  cmp     [rbp+4Fh+var_AC], 0
0x18000992f  mov     [rsp+0E0h], rsi
0x180009937  mov     [rsp+0F0h+var_18], rdi
0x18000993f  mov     [rsp+0F0h+var_30], r14
0x180009947  mov     [rsp+0F0h+var_38], r15
0x18000994f  jz      loc_180009A15
0x180009955  mov     rcx, [rbp+4Fh+var_B8]
0x180009959  lea     r8, [rbp+4Fh+bstrString]
0x18000995d  mov     rdx, cs:?c_rgszQueryNameType@@3PAPEBGA; ushort const * near * c_rgszQueryNameType
0x180009964  mov     rax, [rcx]
0x180009967  mov     rax, [rax+80h]
0x18000996e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009973  mov     ebx, eax
0x180009975  test    eax, eax
0x180009977  js      loc_180009B7B
0x18000997d  mov     rsi, [rbp+4Fh+bstrString]
0x180009981  test    rsi, rsi
0x180009984  jz      loc_180009A03
0x18000998a  xor     eax, eax
0x18000998c  cmp     ax, [rsi]
0x18000998f  jz      short loc_180009A03
0x180009991  test    rsi, rsi
0x180009994  jz      short loc_180009A03
0x180009996  cmp     ax, [rsi]
0x180009999  jz      short loc_180009A03
0x18000999b  mov     ebx, 7FFFFFFFh
0x1800099a0  mov     rax, rsi
0x1800099a3  mov     ecx, ebx
0x1800099a5  cmp     word ptr [rax], 0
0x1800099a9  jz      short loc_1800099B5
0x1800099ab  add     rax, 2
0x1800099af  sub     rcx, 1
0x1800099b3  jnz     short loc_1800099A5
0x1800099b5  sub     rbx, rcx
0x1800099b8  xor     eax, eax
0x1800099ba  test    rcx, rcx
0x1800099bd  cmovz   rbx, rax
0x1800099c1  jz      short loc_180009A03
0x1800099c3  xor     edi, edi
0x1800099c5  lea     r15, __ImageBase
0x1800099cc  nop     dword ptr [rax+00h]
0x1800099d0  lea     r14, ds:3E480h[rdi*8]
0x1800099d8  mov     r8, rbx
0x1800099db  mov     rdx, [r14+r15]
0x1800099df  mov     rcx, rsi
0x1800099e2  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x1800099e9  nop     dword ptr [rax+rax+00h]
0x1800099ee  test    eax, eax
0x1800099f0  jnz     short loc_1800099FC
0x1800099f2  mov     rcx, [r14+r15]
0x1800099f6  cmp     ax, [rcx+rbx*2]
0x1800099fa  jz      short loc_180009A0A
0x1800099fc  inc     edi
0x1800099fe  cmp     edi, 0Fh
0x180009a01  jl      short loc_1800099D0
0x180009a03  mov     ebx, 82AA0001h
0x180009a08  jmp     short loc_180009A28
0x180009a0a  xor     ebx, ebx
0x180009a0c  test    r12, r12
0x180009a0f  jz      short loc_180009A15
0x180009a11  mov     [r12], edi
0x180009a15  mov     rax, [rbp+4Fh+var_B8]
0x180009a19  mov     rcx, [rbp+4Fh+var_98]
0x180009a1d  mov     [rbp+4Fh+var_B8], 0
0x180009a25  mov     [rcx], rax
0x180009a28  mov     r14, [rsp+0F0h+var_30]
0x180009a30  mov     rdi, [rsp+0F0h+var_18]
0x180009a38  mov     rsi, [rsp+0E0h]
0x180009a40  mov     r15, [rsp+0F0h+var_38]
0x180009a48  mov     rcx, [rbp+4Fh+hMem]; hMem
0x180009a4c  call    cs:__imp_LocalFree
0x180009a53  nop     dword ptr [rax+rax+00h]
0x180009a58  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x180009a5c  call    cs:__imp_SysFreeString
0x180009a63  nop     dword ptr [rax+rax+00h]
0x180009a68  mov     rcx, [rbp+4Fh+var_C0]
0x180009a6c  mov     r13, [rsp+0F0h+var_28]
0x180009a74  mov     r12, [rsp+0F0h+var_20]
0x180009a7c  test    rcx, rcx
0x180009a7f  jz      short loc_180009A95
0x180009a81  mov     rax, [rcx]
0x180009a84  mov     rax, [rax+10h]
0x180009a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a8d  mov     [rbp+4Fh+var_C0], 0
0x180009a95  mov     rcx, [rbp+4Fh+var_B8]
0x180009a99  test    rcx, rcx
0x180009a9c  jz      short loc_180009AB2
0x180009a9e  mov     rax, [rcx]
0x180009aa1  mov     rax, [rax+10h]
0x180009aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aaa  mov     [rbp+4Fh+var_B8], 0
0x180009ab2  mov     eax, cs:dword_18003E048
0x180009ab8  cmp     eax, 5
0x180009abb  jbe     loc_180009B62
0x180009ac1  lea     rax, [rbp+4Fh+var_9C]
0x180009ac5  mov     [rbp+4Fh+var_9C], ebx
0x180009ac8  mov     [rbp+4Fh+var_58], rax
0x180009acc  lea     rcx, _TraceLoggingMetadata
0x180009ad3  movzx   eax, cs:word_180036262
0x180009ada  lea     rdx, [rbp+4Fh+EventDescriptor]; EventDescriptor
0x180009ade  mov     dword ptr [rbp+4Fh+EventDescriptor.Level], eax
0x180009ae1  xor     r9d, r9d; RelatedActivityId
0x180009ae4  mov     rax, cs:off_18003E050
0x180009aeb  xor     r8d, r8d; ActivityId
0x180009aee  mov     [rbp+4Fh+UserData.Ptr], rax
0x180009af2  mov     [rbp+4Fh+var_50], 4
0x180009afa  mov     dword ptr [rbp+4Fh+EventDescriptor.Id], 0B000000h
0x180009b01  mov     [rbp+4Fh+EventDescriptor.Keyword], 0
0x180009b09  movzx   eax, word ptr [rax]
0x180009b0c  mov     [rbp+4Fh+UserData.Size], eax
0x180009b0f  lea     rax, dword_18003626C
0x180009b16  mov     [rbp+4Fh+var_68], rax
0x180009b1a  lea     rax, _TraceLoggingMetadataEnd
0x180009b21  sub     eax, ecx
0x180009b23  mov     dword ptr [rbp+4Fh+UserData.0Ch], 2
0x180009b2a  mov     [rbp+4Fh+var_60], 18h
0x180009b31  mov     [rbp+4Fh+var_5C], 1
0x180009b38  mov     dword ptr [rbp+4Fh+var_98], eax
0x180009b3b  mov     eax, dword ptr [rbp+4Fh+var_98]
0x180009b3e  mov     rcx, cs:RegHandle; RegHandle
0x180009b45  lea     rax, [rbp+4Fh+UserData]
0x180009b49  mov     [rsp+28h], rax; UserData
0x180009b4e  mov     dword ptr [rsp+0F0h+ppv], 3; UserDataCount
0x180009b56  call    cs:__imp_EventWriteTransfer
0x180009b5d  nop     dword ptr [rax+rax+00h]
0x180009b62  mov     eax, ebx
0x180009b64  mov     rcx, [rbp+4Fh+var_48]
0x180009b68  xor     rcx, rsp; StackCookie
0x180009b6b  call    __security_check_cookie
0x180009b70  add     rsp, 0E8h
0x180009b77  pop     rbx
0x180009b78  pop     rbp
0x180009b79  retn
0x180009b7b  cmp     eax, 80070490h
0x180009b80  jnz     loc_180009A28
0x180009b86  mov     rcx, [rbp+4Fh+var_B8]
0x180009b8a  lea     r8, [rbp+4Fh+bstrString]
0x180009b8e  mov     rdx, cs:off_18003E220; "list"
0x180009b95  mov     rax, [rcx]
0x180009b98  mov     rax, [rax+80h]
0x180009b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ba4  test    eax, eax
0x180009ba6  js      loc_180009A03
0x180009bac  mov     rsi, [rbp+4Fh+bstrString]
0x180009bb0  test    rsi, rsi
0x180009bb3  jz      loc_180009A03
0x180009bb9  xor     eax, eax
0x180009bbb  cmp     ax, [rsi]
0x180009bbe  jz      loc_180009A03
0x180009bc4  test    rsi, rsi
0x180009bc7  jz      loc_180009A03
0x180009bcd  cmp     ax, [rsi]
0x180009bd0  jz      loc_180009A03
0x180009bd6  mov     ebx, 7FFFFFFFh
0x180009bdb  mov     rax, rsi
0x180009bde  mov     ecx, ebx
0x180009be0  cmp     word ptr [rax], 0
0x180009be4  jz      short loc_180009BF0
0x180009be6  add     rax, 2
0x180009bea  sub     rcx, 1
0x180009bee  jnz     short loc_180009BE0
0x180009bf0  sub     rbx, rcx
0x180009bf3  xor     eax, eax
0x180009bf5  test    rcx, rcx
0x180009bf8  cmovz   rbx, rax
0x180009bfc  jz      loc_180009A03
0x180009c02  xor     edi, edi
0x180009c04  lea     r15, __ImageBase
0x180009c0b  nop     dword ptr [rax+rax+00h]
0x180009c10  lea     r14, ds:3E108h[rdi*8]
0x180009c18  mov     r8, rbx
0x180009c1b  mov     rdx, [r14+r15]
0x180009c1f  mov     rcx, rsi
0x180009c22  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x180009c29  nop     dword ptr [rax+rax+00h]
0x180009c2e  test    eax, eax
0x180009c30  jnz     short loc_180009C3C
0x180009c32  mov     rcx, [r14+r15]
0x180009c36  cmp     ax, [rcx+rbx*2]
0x180009c3a  jz      short loc_180009C4D
0x180009c3c  inc     edi
0x180009c3e  cmp     edi, 2
0x180009c41  jl      short loc_180009C10
0x180009c43  mov     ebx, 82AA0001h
0x180009c48  jmp     loc_180009A28
0x180009c4d  xor     ebx, ebx
0x180009c4f  test    r13, r13
0x180009c52  jz      loc_180009A15
0x180009c58  mov     [r13+0], edi
0x180009c5c  jmp     loc_180009A15
```
