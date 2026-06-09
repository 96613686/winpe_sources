# RealtimeProtection::DlpRtpPluginQuery::IsBrowserCacheDisabled(std::optional<bool> &)

- ea: `0x180046808`
- end: `0x18004695c`
- name: `?IsBrowserCacheDisabled@DlpRtpPluginQuery@RealtimeProtection@@YAJAEAV?$optional@_N@std@@@Z`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800464a8`

## callees

- `0x180046808`
- `0x1800809d0`
- `0x18010cb40`

## import_xrefs

- `MpClient!MpConfigGetValue` at `0x1800468ac`
- `MpClient!MpConfigGetValue` at `0x1800468ac`
- `MpClient!MpConfigClose` at `0x1800468fd`
- `MpClient!MpConfigClose` at `0x180046952`
- `MpClient!MpConfigClose` at `0x1800468fd`
- `MpClient!MpConfigClose` at `0x180046952`
- `MpClient!MpConfigOpen` at `0x18004683e`
- `MpClient!MpConfigOpen` at `0x18004683e`

## string_xrefs

- `0x180046833`: `Miscellaneous Configuration`
- `0x180046890`: `DlpDisableBrowserCache`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpRtpPluginQuery::IsBrowserCacheDisabled(__int64 a1)
{
  int v2; // ebx
  __int64 v3; // r8
  __int64 v4; // r9
  _QWORD *v5; // rcx
  PVOID *v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rdx
  int v10; // eax
  unsigned int v11; // [rsp+30h] [rbp-20h] BYREF
  int v12; // [rsp+34h] [rbp-1Ch] BYREF
  int v13; // [rsp+38h] [rbp-18h] BYREF
  __int64 v14; // [rsp+40h] [rbp-10h] BYREF

  v14 = 0;
  v2 = MpConfigOpen(L"Miscellaneous Configuration", &v14);
  if ( v2 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    v6 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 49;
LABEL_11:
      WPP_SF_d(v5[2], v7, WPP_9bce63ce04f53a278728ac7dd0e232b4_Traceguids, (unsigned int)v2);
      goto LABEL_12;
    }
    goto LABEL_12;
  }
  v11 = 0;
  v13 = 0;
  v12 = 4;
  v2 = ((__int64 (__fastcall *)(__int64, const wchar_t *, unsigned int *, int *, int *, _QWORD))MpConfigGetValue)(
         v14,
         L"DlpDisableBrowserCache",
         &v11,
         &v12,
         &v13,
         0);
  if ( v2 < 0 )
  {
LABEL_8:
    v5 = WPP_GLOBAL_Control;
    v6 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 50;
      goto LABEL_11;
    }
LABEL_12:
    if ( v14 )
      MpConfigClose(v14, v6, v3, v4);
    return (unsigned int)v2;
  }
  if ( v11 > 1 )
  {
    v2 = -2147023267;
    goto LABEL_8;
  }
  if ( v12 )
    v10 = v13;
  else
    v10 = 0;
  if ( v2 )
  {
    *(_BYTE *)(a1 + 1) = 0;
  }
  else
  {
    BYTE1(v11) = 1;
    LOBYTE(v11) = v10 != 0;
    *(_WORD *)a1 = v11;
  }
  if ( v14 )
    MpConfigClose(v14, v8, v3, v4);
  return 0;
}

```

## disassembly

```asm
0x180046808  mov     [rsp-8+arg_8], rbx
0x18004680d  mov     [rsp-8+arg_10], rdi
0x180046812  push    rbp
0x180046813  mov     rbp, rsp
0x180046816  sub     rsp, 50h
0x18004681a  mov     rax, cs:__security_cookie
0x180046821  xor     rax, rsp
0x180046824  mov     [rbp+var_8], rax
0x180046828  mov     rdi, rcx
0x18004682b  mov     [rbp+var_10], 0
0x180046833  lea     rcx, aMiscellaneousC_0; "Miscellaneous Configuration"
0x18004683a  lea     rdx, [rbp+var_10]
0x18004683e  call    cs:__imp_MpConfigOpen
0x180046844  mov     ebx, eax
0x180046846  test    eax, eax
0x180046848  jns     short loc_180046872
0x18004684a  mov     rcx, cs:WPP_GLOBAL_Control
0x180046851  lea     rdx, WPP_GLOBAL_Control
0x180046858  cmp     rcx, rdx
0x18004685b  jz      loc_1800468F4
0x180046861  test    byte ptr [rcx+1Ch], 1
0x180046865  jz      loc_1800468F4
0x18004686b  mov     edx, 31h ; '1'
0x180046870  jmp     short loc_1800468E1
0x180046872  mov     rcx, [rbp+var_10]
0x180046876  lea     rax, [rbp+var_18]
0x18004687a  mov     [rsp+50h+var_28], 0
0x180046883  lea     r9, [rbp+var_1C]
0x180046887  lea     r8, [rbp+var_20]
0x18004688b  mov     [rsp+50h+var_30], rax
0x180046890  lea     rdx, aDlpdisablebrow; "DlpDisableBrowserCache"
0x180046897  mov     [rbp+var_20], 0
0x18004689e  mov     [rbp+var_18], 0
0x1800468a5  mov     [rbp+var_1C], 4
0x1800468ac  call    cs:__imp_MpConfigGetValue
0x1800468b2  mov     ebx, eax
0x1800468b4  test    eax, eax
0x1800468b6  js      short loc_1800468C3
0x1800468b8  cmp     [rbp+var_20], 1
0x1800468bc  jbe     short loc_180046921
0x1800468be  mov     ebx, 8007065Dh
0x1800468c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800468ca  lea     rdx, WPP_GLOBAL_Control
0x1800468d1  cmp     rcx, rdx
0x1800468d4  jz      short loc_1800468F4
0x1800468d6  test    byte ptr [rcx+1Ch], 1
0x1800468da  jz      short loc_1800468F4
0x1800468dc  mov     edx, 32h ; '2'
0x1800468e1  mov     rcx, [rcx+10h]
0x1800468e5  lea     r8, WPP_9bce63ce04f53a278728ac7dd0e232b4_Traceguids
0x1800468ec  mov     r9d, ebx
0x1800468ef  call    WPP_SF_d
0x1800468f4  mov     rcx, [rbp+var_10]
0x1800468f8  test    rcx, rcx
0x1800468fb  jz      short loc_180046903
0x1800468fd  call    cs:__imp_MpConfigClose
0x180046903  mov     eax, ebx
0x180046905  mov     rcx, [rbp+var_8]
0x180046909  xor     rcx, rsp; StackCookie
0x18004690c  call    __security_check_cookie
0x180046911  mov     rbx, [rsp+50h+arg_8]
0x180046916  mov     rdi, [rsp+50h+arg_10]
0x18004691b  add     rsp, 50h
0x18004691f  pop     rbp
0x180046920  retn
0x180046921  cmp     [rbp+var_1C], 0
0x180046925  jnz     short loc_18004692B
0x180046927  xor     eax, eax
0x180046929  jmp     short loc_18004692E
0x18004692b  mov     eax, [rbp+var_18]
0x18004692e  test    ebx, ebx
0x180046930  jnz     short loc_180046945
0x180046932  test    eax, eax
0x180046934  mov     byte ptr [rbp+var_20+1], 1
0x180046938  setnz   byte ptr [rbp+var_20]
0x18004693c  movzx   eax, word ptr [rbp+var_20]
0x180046940  mov     [rdi], ax
0x180046943  jmp     short loc_180046949
0x180046945  mov     byte ptr [rdi+1], 0
0x180046949  mov     rcx, [rbp+var_10]
0x18004694d  test    rcx, rcx
0x180046950  jz      short loc_180046958
0x180046952  call    cs:__imp_MpConfigClose
0x180046958  xor     eax, eax
0x18004695a  jmp     short loc_180046905
```
