# CHNetCfgMgr::CopyLoggingInstanceToStruct(IWbemClassObject *,tagHNET_FW_LOGGING_SETTINGS *)

- ea: `0x18000d8ec`
- end: `0x18000db8e`
- name: `?CopyLoggingInstanceToStruct@CHNetCfgMgr@@IEAAJPEAUIWbemClassObject@@PEAUtagHNET_FW_LOGGING_SETTINGS@@@Z`
- size: `674`
- prototype: `__int64 __fastcall(CHNetCfgMgr *this, struct IWbemClassObject *, struct tagHNET_FW_LOGGING_SETTINGS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014520`

## callees

- `0x180005698`
- `0x18000a45c`
- `0x18000a484`
- `0x18000d8ec`
- `0x180028f88`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18000d9cb`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d9cb`
- `OLEAUT32!__imp_VariantClear` at `0x18000da34`
- `OLEAUT32!__imp_VariantClear` at `0x18000dab9`
- `OLEAUT32!__imp_VariantClear` at `0x18000da34`
- `OLEAUT32!__imp_VariantClear` at `0x18000dab9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d9da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d9da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000db49`

## pseudocode

```c
__int64 __fastcall CHNetCfgMgr::CopyLoggingInstanceToStruct(
        CHNetCfgMgr *this,
        struct IWbemClassObject *a2,
        struct tagHNET_FW_LOGGING_SETTINGS *a3)
{
  struct IWbemClassObjectVtbl *lpVtbl; // rax
  int BooleanValue; // eax
  int v7; // ebx
  PVOID *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r15
  unsigned __int16 *v11; // rax
  VARIANTARG pbstr[3]; // [rsp+40h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 314, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
  }
  pbstr[0].pRecInfo = 0;
  *(_OWORD *)a3 = 0;
  lpVtbl = a2->lpVtbl;
  *(_OWORD *)&pbstr[0].vt = 0;
  BooleanValue = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))lpVtbl->Get)(
                   a2,
                   L"Path",
                   0,
                   pbstr,
                   0,
                   0);
  v7 = BooleanValue;
  if ( BooleanValue < 0 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = 315;
LABEL_10:
      WPP_SF_d(v8[2], v9, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)BooleanValue);
LABEL_37:
      v8 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  if ( BooleanValue )
  {
LABEL_40:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_41;
  }
  v10 = SysStringLen(pbstr[0].bstrVal) + 1;
  v11 = (unsigned __int16 *)CoTaskMemAlloc(2 * v10);
  *(_QWORD *)a3 = v11;
  if ( v11 )
  {
    StringCchCopyW(v11, (unsigned int)v10, pbstr[0].bstrVal);
  }
  else
  {
    v7 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 316, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, 2147942414LL);
    }
  }
  VariantClear(pbstr);
  if ( v7 )
  {
    if ( v7 < 0 )
      goto LABEL_37;
    goto LABEL_40;
  }
  BooleanValue = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a2->lpVtbl->Get)(
                   a2,
                   L"MaxFileSize",
                   0,
                   pbstr,
                   0,
                   0);
  v7 = BooleanValue;
  if ( BooleanValue >= 0 )
  {
    if ( !BooleanValue )
    {
      *((_DWORD *)a3 + 2) = pbstr[0].lVal;
      VariantClear(pbstr);
      BooleanValue = GetBooleanValue(a2, L"LogDroppedPackets", (unsigned __int8 *)a3 + 12);
      v7 = BooleanValue;
      if ( BooleanValue >= 0 )
      {
        if ( BooleanValue )
          goto LABEL_40;
        BooleanValue = GetBooleanValue(a2, L"LogConnections", (unsigned __int8 *)a3 + 13);
        v7 = BooleanValue;
        if ( BooleanValue >= 0 )
          goto LABEL_40;
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 319;
          goto LABEL_10;
        }
      }
      else
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = 318;
          goto LABEL_10;
        }
      }
      goto LABEL_38;
    }
    goto LABEL_40;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 317;
    goto LABEL_10;
  }
LABEL_38:
  if ( *(_QWORD *)a3 )
  {
    CoTaskMemFree(*(LPVOID *)a3);
    goto LABEL_40;
  }
LABEL_41:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 && *((_BYTE *)v8 + 25) >= 6u )
    WPP_SF_d(v8[2], 320, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d8ec  push    rbx
0x18000d8ee  push    rsi
0x18000d8ef  push    r13
0x18000d8f1  push    r14
0x18000d8f3  push    r15
0x18000d8f5  sub     rsp, 60h
0x18000d8f9  mov     r14, r8
0x18000d8fc  mov     rsi, rdx
0x18000d8ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d906  lea     r13, WPP_GLOBAL_Control
0x18000d90d  cmp     rcx, r13
0x18000d910  jz      short loc_18000D933
0x18000d912  test    byte ptr [rcx+1Ch], 8
0x18000d916  jz      short loc_18000D933
0x18000d918  cmp     byte ptr [rcx+19h], 6
0x18000d91c  jb      short loc_18000D933
0x18000d91e  mov     rcx, [rcx+10h]
0x18000d922  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000d929  mov     edx, 13Ah
0x18000d92e  call    WPP_SF_
0x18000d933  xor     eax, eax
0x18000d935  mov     [rsp+88h+var_60], 0
0x18000d93e  mov     [rsp+88h+var_38], rax
0x18000d943  lea     r9, [rsp+88h+pbstr]
0x18000d948  xorps   xmm1, xmm1
0x18000d94b  mov     [rsp+88h+var_68], 0
0x18000d954  movups  xmmword ptr [r14], xmm1
0x18000d958  mov     rax, [rsi]
0x18000d95b  lea     rdx, ?c_wszPath@@3QBGB; "Path"
0x18000d962  xorps   xmm0, xmm0
0x18000d965  xor     r8d, r8d
0x18000d968  mov     rcx, rsi
0x18000d96b  movups  xmmword ptr [rsp+88h+pbstr], xmm0
0x18000d970  mov     rax, [rax+20h]
0x18000d974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d979  mov     ebx, eax
0x18000d97b  test    eax, eax
0x18000d97d  jns     short loc_18000D9C0
0x18000d97f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d986  cmp     rcx, r13
0x18000d989  jz      loc_18000DB40
0x18000d98f  test    byte ptr [rcx+1Ch], 8
0x18000d993  jz      loc_18000DB40
0x18000d999  cmp     byte ptr [rcx+19h], 2
0x18000d99d  jb      loc_18000DB40
0x18000d9a3  mov     edx, 13Bh
0x18000d9a8  mov     rcx, [rcx+10h]
0x18000d9ac  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000d9b3  mov     r9d, eax
0x18000d9b6  call    WPP_SF_d
0x18000d9bb  jmp     loc_18000DB39
0x18000d9c0  jnz     loc_18000DB4F
0x18000d9c6  mov     rcx, [rsp+88h+pbstr+8]; pbstr
0x18000d9cb  call    cs:__imp_SysStringLen
0x18000d9d1  inc     eax
0x18000d9d3  mov     r15d, eax
0x18000d9d6  lea     rcx, [rax+rax]; cb
0x18000d9da  call    cs:__imp_CoTaskMemAlloc
0x18000d9e0  mov     [r14], rax
0x18000d9e3  test    rax, rax
0x18000d9e6  jz      short loc_18000D9FA
0x18000d9e8  mov     r8, [rsp+88h+pbstr+8]; unsigned __int16 *
0x18000d9ed  mov     edx, r15d; unsigned __int64
0x18000d9f0  mov     rcx, rax; unsigned __int16 *
0x18000d9f3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d9f8  jmp     short loc_18000DA2F
0x18000d9fa  mov     ebx, 8007000Eh
0x18000d9ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da06  cmp     rcx, r13
0x18000da09  jz      short loc_18000DA2F
0x18000da0b  test    byte ptr [rcx+1Ch], 8
0x18000da0f  jz      short loc_18000DA2F
0x18000da11  cmp     byte ptr [rcx+19h], 2
0x18000da15  jb      short loc_18000DA2F
0x18000da17  mov     rcx, [rcx+10h]
0x18000da1b  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000da22  mov     edx, 13Ch
0x18000da27  mov     r9d, ebx
0x18000da2a  call    WPP_SF_d
0x18000da2f  lea     rcx, [rsp+88h+pbstr]; pvarg
0x18000da34  call    cs:__imp_VariantClear
0x18000da3a  test    ebx, ebx
0x18000da3c  jnz     loc_18000DB37
0x18000da42  mov     rax, [rsi]
0x18000da45  lea     r9, [rsp+88h+pbstr]
0x18000da4a  mov     [rsp+88h+var_60], 0
0x18000da53  lea     rdx, ?c_wszMaxFileSize@@3QBGB; "MaxFileSize"
0x18000da5a  xor     r8d, r8d
0x18000da5d  mov     [rsp+88h+var_68], 0
0x18000da66  mov     rcx, rsi
0x18000da69  mov     rax, [rax+20h]
0x18000da6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da72  mov     ebx, eax
0x18000da74  test    eax, eax
0x18000da76  jns     short loc_18000DAA6
0x18000da78  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da7f  cmp     rcx, r13
0x18000da82  jz      loc_18000DB40
0x18000da88  test    byte ptr [rcx+1Ch], 8
0x18000da8c  jz      loc_18000DB40
0x18000da92  cmp     byte ptr [rcx+19h], 2
0x18000da96  jb      loc_18000DB40
0x18000da9c  mov     edx, 13Dh
0x18000daa1  jmp     loc_18000D9A8
0x18000daa6  jnz     loc_18000DB4F
0x18000daac  mov     eax, dword ptr [rsp+88h+pbstr+8]
0x18000dab0  lea     rcx, [rsp+88h+pbstr]; pvarg
0x18000dab5  mov     [r14+8], eax
0x18000dab9  call    cs:__imp_VariantClear
0x18000dabf  lea     r8, [r14+0Ch]; unsigned __int8 *
0x18000dac3  mov     rcx, rsi; struct IWbemClassObject *
0x18000dac6  lea     rdx, ?c_wszLogDroppedPackets@@3QBGB; "LogDroppedPackets"
0x18000dacd  call    ?GetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGPEAE@Z; GetBooleanValue(IWbemClassObject *,ushort const *,uchar *)
0x18000dad2  mov     ebx, eax
0x18000dad4  test    eax, eax
0x18000dad6  jns     short loc_18000DAFA
0x18000dad8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dadf  cmp     rcx, r13
0x18000dae2  jz      short loc_18000DB40
0x18000dae4  test    byte ptr [rcx+1Ch], 8
0x18000dae8  jz      short loc_18000DB40
0x18000daea  cmp     byte ptr [rcx+19h], 2
0x18000daee  jb      short loc_18000DB40
0x18000daf0  mov     edx, 13Eh
0x18000daf5  jmp     loc_18000D9A8
0x18000dafa  jnz     short loc_18000DB4F
0x18000dafc  lea     r8, [r14+0Dh]; unsigned __int8 *
0x18000db00  mov     rcx, rsi; struct IWbemClassObject *
0x18000db03  lea     rdx, ?c_wszLogConnections@@3QBGB; "LogConnections"
0x18000db0a  call    ?GetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGPEAE@Z; GetBooleanValue(IWbemClassObject *,ushort const *,uchar *)
0x18000db0f  mov     ebx, eax
0x18000db11  test    eax, eax
0x18000db13  jns     short loc_18000DB4F
0x18000db15  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db1c  cmp     rcx, r13
0x18000db1f  jz      short loc_18000DB40
0x18000db21  test    byte ptr [rcx+1Ch], 8
0x18000db25  jz      short loc_18000DB40
0x18000db27  cmp     byte ptr [rcx+19h], 2
0x18000db2b  jb      short loc_18000DB40
0x18000db2d  mov     edx, 13Fh
0x18000db32  jmp     loc_18000D9A8
0x18000db37  jns     short loc_18000DB4F
0x18000db39  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db40  cmp     qword ptr [r14], 0
0x18000db44  jz      short loc_18000DB56
0x18000db46  mov     rcx, [r14]; pv
0x18000db49  call    cs:__imp_CoTaskMemFree
0x18000db4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db56  cmp     rcx, r13
0x18000db59  jz      short loc_18000DB7F
0x18000db5b  test    byte ptr [rcx+1Ch], 8
0x18000db5f  jz      short loc_18000DB7F
0x18000db61  cmp     byte ptr [rcx+19h], 6
0x18000db65  jb      short loc_18000DB7F
0x18000db67  mov     rcx, [rcx+10h]
0x18000db6b  lea     r8, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000db72  mov     edx, 140h
0x18000db77  mov     r9d, ebx
0x18000db7a  call    WPP_SF_d
0x18000db7f  mov     eax, ebx
0x18000db81  add     rsp, 60h
0x18000db85  pop     r15
0x18000db87  pop     r14
0x18000db89  pop     r13
0x18000db8b  pop     rsi
0x18000db8c  pop     rbx
0x18000db8d  retn
```
