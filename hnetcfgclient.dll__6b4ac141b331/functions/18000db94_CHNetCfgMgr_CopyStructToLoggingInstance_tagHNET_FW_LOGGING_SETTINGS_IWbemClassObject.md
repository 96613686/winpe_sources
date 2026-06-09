# CHNetCfgMgr::CopyStructToLoggingInstance(tagHNET_FW_LOGGING_SETTINGS *,IWbemClassObject *)

- ea: `0x18000db94`
- end: `0x18000dde9`
- name: `?CopyStructToLoggingInstance@CHNetCfgMgr@@IEAAJPEAUtagHNET_FW_LOGGING_SETTINGS@@PEAUIWbemClassObject@@@Z`
- size: `597`
- prototype: `__int64 __fastcall(CHNetCfgMgr *this, struct tagHNET_FW_LOGGING_SETTINGS *, struct IWbemClassObject *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180017bf0`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18000db94`
- `0x18002a61c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18000dc06`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dc06`
- `OLEAUT32!__imp_VariantInit` at `0x18000dbf8`
- `OLEAUT32!__imp_VariantInit` at `0x18000dbf8`
- `OLEAUT32!__imp_VariantClear` at `0x18000dcb3`
- `OLEAUT32!__imp_VariantClear` at `0x18000dcb3`

## pseudocode

```c
__int64 __fastcall CHNetCfgMgr::CopyStructToLoggingInstance(
        CHNetCfgMgr *this,
        struct tagHNET_FW_LOGGING_SETTINGS *a2,
        struct IWbemClassObject *a3)
{
  const OLECHAR *v5; // rcx
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  int v11; // eax
  VARIANTARG pvarg; // [rsp+30h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 321, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids);
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v5 = *(const OLECHAR **)a2;
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocString(v5);
  if ( pvarg.llVal )
  {
    v10 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))a3->lpVtbl->Put)(
            a3,
            L"Path",
            0,
            &pvarg,
            0);
    v6 = v10;
    if ( v10 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        323,
        &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids,
        (unsigned int)v10);
    }
    VariantClear(&pvarg);
    if ( v6 )
      goto LABEL_35;
    pvarg.vt = 3;
    pvarg.lVal = *((_DWORD *)a2 + 2);
    v11 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _DWORD))a3->lpVtbl->Put)(
            a3,
            L"MaxFileSize",
            0,
            &pvarg,
            0);
    v6 = v11;
    if ( v11 >= 0 )
    {
      if ( v11 )
      {
LABEL_35:
        v7 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_36;
      }
      v11 = SetBooleanValue(a3, L"LogDroppedPackets", *((_BYTE *)a2 + 12));
      v6 = v11;
      if ( v11 >= 0 )
      {
        if ( v11 )
          goto LABEL_35;
        v11 = SetBooleanValue(a3, L"LogConnections", *((_BYTE *)a2 + 13));
        v6 = v11;
        if ( v11 >= 0 )
          goto LABEL_35;
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v6;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_36;
        v8 = 326;
      }
      else
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return v6;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_36;
        v8 = 325;
      }
    }
    else
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v6;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_36;
      v8 = 324;
    }
    v9 = (unsigned int)v11;
LABEL_34:
    WPP_SF_d(v7[2], v8, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v9);
    goto LABEL_35;
  }
  v6 = -2147024882;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = 322;
    v9 = 2147942414LL;
    goto LABEL_34;
  }
LABEL_36:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 327, &WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000db94  push    rbx
0x18000db96  push    rbp
0x18000db97  push    rsi
0x18000db98  push    r12
0x18000db9a  push    r14
0x18000db9c  push    r15
0x18000db9e  sub     rsp, 58h
0x18000dba2  mov     rsi, r8
0x18000dba5  mov     r14, rdx
0x18000dba8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbaf  lea     r15, WPP_GLOBAL_Control
0x18000dbb6  lea     r12, WPP_bb519a7f6e00393adb8277ba7409b88b_Traceguids
0x18000dbbd  mov     ebp, 8
0x18000dbc2  cmp     rcx, r15
0x18000dbc5  jz      short loc_18000DBE4
0x18000dbc7  test    [rcx+1Ch], bpl
0x18000dbcb  jz      short loc_18000DBE4
0x18000dbcd  cmp     byte ptr [rcx+19h], 6
0x18000dbd1  jb      short loc_18000DBE4
0x18000dbd3  mov     rcx, [rcx+10h]
0x18000dbd7  mov     edx, 141h
0x18000dbdc  mov     r8, r12
0x18000dbdf  call    WPP_SF_
0x18000dbe4  xorps   xmm0, xmm0
0x18000dbe7  lea     rcx, [rsp+88h+pvarg]; pvarg
0x18000dbec  xor     eax, eax
0x18000dbee  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x18000dbf3  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x18000dbf8  call    cs:__imp_VariantInit
0x18000dbfe  mov     rcx, [r14]; psz
0x18000dc01  mov     word ptr [rsp+88h+pvarg], bp
0x18000dc06  call    cs:__imp_SysAllocString
0x18000dc0c  mov     rcx, rax
0x18000dc0f  mov     dword ptr [rsp+88h+pvarg+8], eax
0x18000dc13  sar     rcx, 20h
0x18000dc17  mov     dword ptr [rsp+88h+pvarg+0Ch], ecx
0x18000dc1b  test    rax, rax
0x18000dc1e  jnz     short loc_18000DC56
0x18000dc20  mov     ebx, 8007000Eh
0x18000dc25  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc2c  cmp     rcx, r15
0x18000dc2f  jz      loc_18000DDD9
0x18000dc35  test    [rcx+1Ch], bpl
0x18000dc39  jz      loc_18000DDB4
0x18000dc3f  cmp     byte ptr [rcx+19h], 2
0x18000dc43  jb      loc_18000DDB4
0x18000dc49  mov     edx, 142h
0x18000dc4e  mov     r9d, ebx
0x18000dc51  jmp     loc_18000DDA1
0x18000dc56  mov     rax, [rsi]
0x18000dc59  lea     r9, [rsp+88h+pvarg]
0x18000dc5e  xor     r8d, r8d
0x18000dc61  mov     [rsp+88h+var_68], 0
0x18000dc69  lea     rdx, ?c_wszPath@@3QBGB; "Path"
0x18000dc70  mov     rcx, rsi
0x18000dc73  mov     rax, [rax+28h]
0x18000dc77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc7c  mov     ebx, eax
0x18000dc7e  test    eax, eax
0x18000dc80  jns     short loc_18000DCAE
0x18000dc82  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc89  cmp     rcx, r15
0x18000dc8c  jz      short loc_18000DCAE
0x18000dc8e  test    [rcx+1Ch], bpl
0x18000dc92  jz      short loc_18000DCAE
0x18000dc94  cmp     byte ptr [rcx+19h], 2
0x18000dc98  jb      short loc_18000DCAE
0x18000dc9a  mov     rcx, [rcx+10h]
0x18000dc9e  mov     edx, 143h
0x18000dca3  mov     r9d, eax
0x18000dca6  mov     r8, r12
0x18000dca9  call    WPP_SF_d
0x18000dcae  lea     rcx, [rsp+88h+pvarg]; pvarg
0x18000dcb3  call    cs:__imp_VariantClear
0x18000dcb9  test    ebx, ebx
0x18000dcbb  jnz     loc_18000DDAD
0x18000dcc1  lea     eax, [rbx+3]
0x18000dcc4  mov     [rsp+88h+var_68], ebx
0x18000dcc8  mov     word ptr [rsp+88h+pvarg], ax
0x18000dccd  lea     r9, [rsp+88h+pvarg]
0x18000dcd2  mov     eax, [r14+8]
0x18000dcd6  lea     rdx, ?c_wszMaxFileSize@@3QBGB; "MaxFileSize"
0x18000dcdd  mov     dword ptr [rsp+88h+pvarg+8], eax
0x18000dce1  xor     r8d, r8d
0x18000dce4  mov     rax, [rsi]
0x18000dce7  mov     rcx, rsi
0x18000dcea  mov     rax, [rax+28h]
0x18000dcee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcf3  mov     ebx, eax
0x18000dcf5  test    eax, eax
0x18000dcf7  jns     short loc_18000DD24
0x18000dcf9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd00  cmp     rcx, r15
0x18000dd03  jz      loc_18000DDD9
0x18000dd09  test    [rcx+1Ch], bpl
0x18000dd0d  jz      loc_18000DDB4
0x18000dd13  cmp     byte ptr [rcx+19h], 2
0x18000dd17  jb      loc_18000DDB4
0x18000dd1d  mov     edx, 144h
0x18000dd22  jmp     short loc_18000DD9E
0x18000dd24  jnz     loc_18000DDAD
0x18000dd2a  mov     r8b, [r14+0Ch]; unsigned __int8
0x18000dd2e  lea     rdx, ?c_wszLogDroppedPackets@@3QBGB; "LogDroppedPackets"
0x18000dd35  mov     rcx, rsi; struct IWbemClassObject *
0x18000dd38  call    ?SetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGE@Z; SetBooleanValue(IWbemClassObject *,ushort const *,uchar)
0x18000dd3d  mov     ebx, eax
0x18000dd3f  test    eax, eax
0x18000dd41  jns     short loc_18000DD66
0x18000dd43  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd4a  cmp     rcx, r15
0x18000dd4d  jz      loc_18000DDD9
0x18000dd53  test    [rcx+1Ch], bpl
0x18000dd57  jz      short loc_18000DDB4
0x18000dd59  cmp     byte ptr [rcx+19h], 2
0x18000dd5d  jb      short loc_18000DDB4
0x18000dd5f  mov     edx, 145h
0x18000dd64  jmp     short loc_18000DD9E
0x18000dd66  jnz     short loc_18000DDAD
0x18000dd68  mov     r8b, [r14+0Dh]; unsigned __int8
0x18000dd6c  lea     rdx, ?c_wszLogConnections@@3QBGB; "LogConnections"
0x18000dd73  mov     rcx, rsi; struct IWbemClassObject *
0x18000dd76  call    ?SetBooleanValue@@YAJPEAUIWbemClassObject@@PEBGE@Z; SetBooleanValue(IWbemClassObject *,ushort const *,uchar)
0x18000dd7b  mov     ebx, eax
0x18000dd7d  test    eax, eax
0x18000dd7f  jns     short loc_18000DDAD
0x18000dd81  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd88  cmp     rcx, r15
0x18000dd8b  jz      short loc_18000DDD9
0x18000dd8d  test    [rcx+1Ch], bpl
0x18000dd91  jz      short loc_18000DDB4
0x18000dd93  cmp     byte ptr [rcx+19h], 2
0x18000dd97  jb      short loc_18000DDB4
0x18000dd99  mov     edx, 146h
0x18000dd9e  mov     r9d, eax
0x18000dda1  mov     rcx, [rcx+10h]
0x18000dda5  mov     r8, r12
0x18000dda8  call    WPP_SF_d
0x18000ddad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddb4  cmp     rcx, r15
0x18000ddb7  jz      short loc_18000DDD9
0x18000ddb9  test    [rcx+1Ch], bpl
0x18000ddbd  jz      short loc_18000DDD9
0x18000ddbf  cmp     byte ptr [rcx+19h], 6
0x18000ddc3  jb      short loc_18000DDD9
0x18000ddc5  mov     rcx, [rcx+10h]
0x18000ddc9  mov     edx, 147h
0x18000ddce  mov     r9d, ebx
0x18000ddd1  mov     r8, r12
0x18000ddd4  call    WPP_SF_d
0x18000ddd9  mov     eax, ebx
0x18000dddb  add     rsp, 58h
0x18000dddf  pop     r15
0x18000dde1  pop     r14
0x18000dde3  pop     r12
0x18000dde5  pop     rsi
0x18000dde6  pop     rbp
0x18000dde7  pop     rbx
0x18000dde8  retn
```
