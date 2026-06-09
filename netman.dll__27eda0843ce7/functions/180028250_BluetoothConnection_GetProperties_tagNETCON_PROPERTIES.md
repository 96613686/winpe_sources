# BluetoothConnection::GetProperties(tagNETCON_PROPERTIES * *)

- ea: `0x180028250`
- end: `0x18002855f`
- name: `?GetProperties@BluetoothConnection@@UEAAJPEAPEAUtagNETCON_PROPERTIES@@@Z`
- size: `783`
- prototype: `__int64 __fastcall(BluetoothConnection *__hidden this, struct tagNETCON_PROPERTIES **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001710`
- `0x180002320`
- `0x18000538c`
- `0x180019200`
- `0x180028250`
- `0x180028c30`
- `0x180028dfc`
- `0x18002926c`
- `0x18002930c`
- `0x1800343dc`
- `0x1800345e8`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800282bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800282bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800284b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800284ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800284d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800284ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800284f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800284b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800284ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800284d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800284ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800284f3`

## pseudocode

```c
__int64 __fastcall BluetoothConnection::GetProperties(BluetoothConnection *this, LPVOID *a2)
{
  bool v2; // zf
  int NetCfgInstGuid; // ebx
  struct tagNETCON_PROPERTIES *v6; // rax
  BluetoothConnection *v7; // rcx
  BluetoothConnection *v8; // rcx
  BluetoothConnection *v9; // rcx
  int v10; // edx
  int v11; // eax
  _DWORD *v12; // rax
  int v13; // ecx
  void *v14; // rcx
  LPWSTR v15; // rcx
  int v17; // [rsp+30h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-28h] BYREF
  LPVOID v19; // [rsp+40h] [rbp-20h] BYREF
  int v20; // [rsp+48h] [rbp-18h] BYREF

  v2 = *((_DWORD *)this + 26) == 0;
  v20 = 0;
  pv = 0;
  v19 = 0;
  v17 = 0;
  if ( v2 )
  {
    NetCfgInstGuid = -2147418113;
LABEL_46:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids,
        (unsigned int)NetCfgInstGuid);
    return (unsigned int)NetCfgInstGuid;
  }
  if ( !a2 )
  {
    NetCfgInstGuid = -2147467261;
    goto LABEL_46;
  }
  v6 = (struct tagNETCON_PROPERTIES *)CoTaskMemAlloc(0x50u);
  *a2 = v6;
  if ( !v6 )
  {
    NetCfgInstGuid = -2147024882;
    goto LABEL_46;
  }
  memset_0(v6, 0, sizeof(struct tagNETCON_PROPERTIES));
  NetCfgInstGuid = HrGetNetCfgInstGuid(
                     *((void **)this + 14),
                     (struct _SP_DEVINFO_DATA *)((char *)this + 120),
                     (struct _GUID *)*a2);
  if ( NetCfgInstGuid )
    goto LABEL_26;
  NetCfgInstGuid = BluetoothConnection::HrQueryRegValue(
                     v7,
                     *((HKEY *)this + 12),
                     c_szConnectionName,
                     (unsigned __int8 **)*a2 + 2);
  if ( NetCfgInstGuid )
    goto LABEL_26;
  NetCfgInstGuid = BluetoothConnection::HrGetDeviceProperty(
                     v8,
                     *((void **)this + 14),
                     (struct _SP_DEVINFO_DATA *)((char *)this + 120),
                     12,
                     (unsigned __int8 **)*a2 + 3);
  if ( NetCfgInstGuid < 0 )
    NetCfgInstGuid = BluetoothConnection::HrGetDeviceProperty(
                       v9,
                       *((void **)this + 14),
                       (struct _SP_DEVINFO_DATA *)((char *)this + 120),
                       0,
                       (unsigned __int8 **)*a2 + 3);
  if ( NetCfgInstGuid )
    goto LABEL_26;
  NetCfgInstGuid = HrGetDeviceStatus(*((_DWORD *)this + 35), (enum tagNETCON_STATUS *)*a2 + 8);
  if ( NetCfgInstGuid )
    goto LABEL_26;
  if ( *((_DWORD *)*a2 + 8) == 2 )
  {
    NetCfgInstGuid = BluetoothConnection::HrIsConnectedToRemote(this, &v17, 0);
    if ( NetCfgInstGuid )
      goto LABEL_26;
    if ( !v17 )
      *((_DWORD *)*a2 + 8) = 7;
  }
  *((_DWORD *)*a2 + 10) = 9;
  v10 = BluetoothConnection::HrEnsureHNetPropertiesCached(this);
  NetCfgInstGuid = v10;
  if ( v10 )
  {
    v11 = 0;
    if ( v10 < 0 )
      goto LABEL_21;
  }
  else
  {
    v11 = *(unsigned __int8 *)(*((_QWORD *)this + 24) + 2LL);
  }
  if ( v11 == 1 )
    *((_DWORD *)*a2 + 10) |= 0x100u;
LABEL_21:
  if ( v10 == 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids);
    v12 = *a2;
    NetCfgInstGuid = 0;
    goto LABEL_27;
  }
LABEL_26:
  v12 = *a2;
  if ( !NetCfgInstGuid )
  {
LABEL_27:
    v12[9] = 3;
    *(GUID *)((char *)*a2 + 44) = CLSID_BluetoothConnection;
    *(_OWORD *)((char *)*a2 + 60) = xmmword_18003BD18;
    if ( (*(unsigned int (__fastcall **)(char *, int *, LPVOID *, LPVOID *))(*((_QWORD *)this + 4) + 40LL))(
           (char *)this + 32,
           &v20,
           &pv,
           &v19) )
    {
      *((_DWORD *)*a2 + 10) |= 0x80000u;
    }
    else
    {
      if ( v20 )
      {
        switch ( v20 )
        {
          case 1:
            v13 = 0x10000;
            break;
          case 2:
            v13 = 0x20000;
            break;
          case 3:
            v13 = 0x40000;
            break;
          default:
            v13 = 0x80000;
            break;
        }
      }
      else
      {
        v13 = 0;
      }
      *((_DWORD *)*a2 + 10) |= v13;
      CoTaskMemFree(pv);
      CoTaskMemFree(v19);
    }
    return (unsigned int)NetCfgInstGuid;
  }
  v14 = (void *)*((_QWORD *)v12 + 2);
  if ( v14 )
    CoTaskMemFree(v14);
  v15 = (LPWSTR)*((_QWORD *)*a2 + 3);
  if ( v15 )
    CoTaskMemFree(v15);
  CoTaskMemFree(*a2);
  *a2 = 0;
  if ( NetCfgInstGuid < 0 )
    goto LABEL_46;
  return (unsigned int)NetCfgInstGuid;
}

```

## disassembly

```asm
0x180028250  mov     [rsp-18h+arg_10], rbx
0x180028255  mov     [rsp-18h+arg_18], rsi
0x18002825a  push    rbp
0x18002825b  push    rdi
0x18002825c  push    r14
0x18002825e  mov     rbp, rsp
0x180028261  sub     rsp, 60h
0x180028265  mov     rax, cs:__security_cookie
0x18002826c  xor     rax, rsp
0x18002826f  mov     [rbp+var_10], rax
0x180028273  cmp     dword ptr [rcx+68h], 0
0x180028277  mov     rdi, rdx
0x18002827a  mov     rsi, rcx
0x18002827d  mov     [rbp+var_18], 0
0x180028284  mov     [rbp+pv], 0
0x18002828c  mov     [rbp+var_20], 0
0x180028294  mov     [rbp+var_30], 0
0x18002829b  jnz     short loc_1800282A7
0x18002829d  mov     ebx, 8000FFFFh
0x1800282a2  jmp     loc_18002850B
0x1800282a7  test    rdi, rdi
0x1800282aa  jnz     short loc_1800282B6
0x1800282ac  mov     ebx, 80004003h
0x1800282b1  jmp     loc_18002850B
0x1800282b6  mov     ebx, 50h ; 'P'
0x1800282bb  mov     ecx, ebx; cb
0x1800282bd  call    cs:__imp_CoTaskMemAlloc
0x1800282c3  mov     [rdi], rax
0x1800282c6  test    rax, rax
0x1800282c9  jz      loc_180028506
0x1800282cf  mov     r8d, ebx; Size
0x1800282d2  xor     edx, edx; Val
0x1800282d4  mov     rcx, rax; void *
0x1800282d7  call    memset_0
0x1800282dc  mov     r8, [rdi]; struct _GUID *
0x1800282df  lea     r14, [rsi+78h]
0x1800282e3  mov     rcx, [rsi+70h]; void *
0x1800282e7  mov     rdx, r14; struct _SP_DEVINFO_DATA *
0x1800282ea  call    ?HrGetNetCfgInstGuid@@YAJPEAXPEAU_SP_DEVINFO_DATA@@PEAU_GUID@@@Z; HrGetNetCfgInstGuid(void *,_SP_DEVINFO_DATA *,_GUID *)
0x1800282ef  mov     ebx, eax
0x1800282f1  test    eax, eax
0x1800282f3  jnz     loc_180028422
0x1800282f9  mov     r9, [rdi]
0x1800282fc  lea     r8, ?c_szConnectionName@@3PAGA; "Name"
0x180028303  mov     rdx, [rsi+60h]; HKEY
0x180028307  add     r9, 10h; unsigned __int8 **
0x18002830b  call    ?HrQueryRegValue@BluetoothConnection@@AEAAJPEAUHKEY__@@PEAGPEAPEAE@Z; BluetoothConnection::HrQueryRegValue(HKEY__ *,ushort *,uchar * *)
0x180028310  mov     ebx, eax
0x180028312  test    eax, eax
0x180028314  jnz     loc_180028422
0x18002831a  mov     rax, [rdi]
0x18002831d  lea     r9d, [rbx+0Ch]; unsigned int
0x180028321  mov     rdx, [rsi+70h]; void *
0x180028325  add     rax, 18h
0x180028329  mov     r8, r14; struct _SP_DEVINFO_DATA *
0x18002832c  mov     [rsp+60h+var_40], rax; unsigned __int8 **
0x180028331  call    ?HrGetDeviceProperty@BluetoothConnection@@AEAAJPEAXPEAU_SP_DEVINFO_DATA@@KPEAPEAE@Z; BluetoothConnection::HrGetDeviceProperty(void *,_SP_DEVINFO_DATA *,ulong,uchar * *)
0x180028336  mov     ebx, eax
0x180028338  test    eax, eax
0x18002833a  jns     short loc_180028359
0x18002833c  mov     rax, [rdi]
0x18002833f  xor     r9d, r9d; unsigned int
0x180028342  mov     rdx, [rsi+70h]; void *
0x180028346  add     rax, 18h
0x18002834a  mov     r8, r14; struct _SP_DEVINFO_DATA *
0x18002834d  mov     [rsp+60h+var_40], rax; unsigned __int8 **
0x180028352  call    ?HrGetDeviceProperty@BluetoothConnection@@AEAAJPEAXPEAU_SP_DEVINFO_DATA@@KPEAPEAE@Z; BluetoothConnection::HrGetDeviceProperty(void *,_SP_DEVINFO_DATA *,ulong,uchar * *)
0x180028357  mov     ebx, eax
0x180028359  test    ebx, ebx
0x18002835b  jnz     loc_180028422
0x180028361  mov     rdx, [rdi]
0x180028364  mov     ecx, [rsi+8Ch]; dnDevInst
0x18002836a  add     rdx, 20h ; ' '; enum tagNETCON_STATUS *
0x18002836e  call    ?HrGetDeviceStatus@@YAJKPEAW4tagNETCON_STATUS@@@Z; HrGetDeviceStatus(ulong,tagNETCON_STATUS *)
0x180028373  mov     ebx, eax
0x180028375  test    eax, eax
0x180028377  jnz     loc_180028422
0x18002837d  mov     rax, [rdi]
0x180028380  cmp     dword ptr [rax+20h], 2
0x180028384  jnz     short loc_1800283AE
0x180028386  xor     r8d, r8d; unsigned __int8 *
0x180028389  lea     rdx, [rbp+var_30]; int *
0x18002838d  mov     rcx, rsi; this
0x180028390  call    ?HrIsConnectedToRemote@BluetoothConnection@@AEAAJPEAHQEAE@Z; BluetoothConnection::HrIsConnectedToRemote(int *,uchar * const)
0x180028395  mov     ebx, eax
0x180028397  test    eax, eax
0x180028399  jnz     loc_180028422
0x18002839f  cmp     [rbp+var_30], eax
0x1800283a2  jnz     short loc_1800283AE
0x1800283a4  mov     rax, [rdi]
0x1800283a7  mov     dword ptr [rax+20h], 7
0x1800283ae  mov     rax, [rdi]
0x1800283b1  mov     rcx, rsi; this
0x1800283b4  mov     dword ptr [rax+28h], 9
0x1800283bb  call    ?HrEnsureHNetPropertiesCached@BluetoothConnection@@AEAAJXZ; BluetoothConnection::HrEnsureHNetPropertiesCached(void)
0x1800283c0  mov     edx, eax
0x1800283c2  mov     ebx, eax
0x1800283c4  test    eax, eax
0x1800283c6  jnz     short loc_1800283D5
0x1800283c8  mov     rcx, [rsi+0C0h]
0x1800283cf  movzx   eax, byte ptr [rcx+2]
0x1800283d3  jmp     short loc_1800283DB
0x1800283d5  xor     eax, eax
0x1800283d7  test    edx, edx
0x1800283d9  js      short loc_1800283E8
0x1800283db  cmp     eax, 1
0x1800283de  jnz     short loc_1800283E8
0x1800283e0  mov     rax, [rdi]
0x1800283e3  bts     dword ptr [rax+28h], 8
0x1800283e8  cmp     edx, 1
0x1800283eb  jnz     short loc_180028422
0x1800283ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283f4  lea     rax, WPP_GLOBAL_Control
0x1800283fb  cmp     rcx, rax
0x1800283fe  jz      short loc_18002841B
0x180028400  test    byte ptr [rcx+1Ch], 8
0x180028404  jz      short loc_18002841B
0x180028406  mov     rcx, [rcx+10h]
0x18002840a  lea     r8, WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids
0x180028411  mov     edx, 2Fh ; '/'
0x180028416  call    WPP_SF_
0x18002841b  mov     rax, [rdi]
0x18002841e  xor     ebx, ebx
0x180028420  jmp     short loc_18002842D
0x180028422  mov     rax, [rdi]
0x180028425  test    ebx, ebx
0x180028427  jnz     loc_1800284CF
0x18002842d  movups  xmm1, cs:xmmword_18003BD18
0x180028434  mov     dword ptr [rax+24h], 3
0x18002843b  lea     rcx, [rsi+20h]
0x18002843f  mov     rax, [rdi]
0x180028442  lea     r9, [rbp+var_20]
0x180028446  movups  xmm0, xmmword ptr cs:CLSID_BluetoothConnection.Data1
0x18002844d  lea     r8, [rbp+pv]
0x180028451  lea     rdx, [rbp+var_18]
0x180028455  movdqu  xmmword ptr [rax+2Ch], xmm0
0x18002845a  mov     rax, [rdi]
0x18002845d  movdqu  xmmword ptr [rax+3Ch], xmm1
0x180028462  mov     rax, [rcx]
0x180028465  mov     rax, [rax+28h]
0x180028469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002846e  test    eax, eax
0x180028470  jnz     short loc_1800284C2
0x180028472  mov     ecx, [rbp+var_18]
0x180028475  test    ecx, ecx
0x180028477  jz      short loc_1800284A4
0x180028479  sub     ecx, 1
0x18002847c  jz      short loc_18002849D
0x18002847e  sub     ecx, 1
0x180028481  jz      short loc_180028496
0x180028483  cmp     ecx, 1
0x180028486  jz      short loc_18002848F
0x180028488  mov     ecx, 80000h
0x18002848d  jmp     short loc_1800284A6
0x18002848f  mov     ecx, 40000h
0x180028494  jmp     short loc_1800284A6
0x180028496  mov     ecx, 20000h
0x18002849b  jmp     short loc_1800284A6
0x18002849d  mov     ecx, 10000h
0x1800284a2  jmp     short loc_1800284A6
0x1800284a4  xor     ecx, ecx
0x1800284a6  mov     rax, [rdi]
0x1800284a9  or      [rax+28h], ecx
0x1800284ac  mov     rcx, [rbp+pv]; pv
0x1800284b0  call    cs:__imp_CoTaskMemFree
0x1800284b6  mov     rcx, [rbp+var_20]; pv
0x1800284ba  call    cs:__imp_CoTaskMemFree
0x1800284c0  jmp     short loc_18002853C
0x1800284c2  mov     rax, [rdi]
0x1800284c5  mov     ecx, 80000h
0x1800284ca  or      [rax+28h], ecx
0x1800284cd  jmp     short loc_18002853C
0x1800284cf  mov     rcx, [rax+10h]; pv
0x1800284d3  test    rcx, rcx
0x1800284d6  jz      short loc_1800284DE
0x1800284d8  call    cs:__imp_CoTaskMemFree
0x1800284de  mov     rax, [rdi]
0x1800284e1  mov     rcx, [rax+18h]; pv
0x1800284e5  test    rcx, rcx
0x1800284e8  jz      short loc_1800284F0
0x1800284ea  call    cs:__imp_CoTaskMemFree
0x1800284f0  mov     rcx, [rdi]; pv
0x1800284f3  call    cs:__imp_CoTaskMemFree
0x1800284f9  mov     qword ptr [rdi], 0
0x180028500  test    ebx, ebx
0x180028502  jns     short loc_18002853C
0x180028504  jmp     short loc_18002850B
0x180028506  mov     ebx, 8007000Eh
0x18002850b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028512  lea     rax, WPP_GLOBAL_Control
0x180028519  cmp     rcx, rax
0x18002851c  jz      short loc_18002853C
0x18002851e  test    byte ptr [rcx+1Ch], 1
0x180028522  jz      short loc_18002853C
0x180028524  mov     rcx, [rcx+10h]
0x180028528  lea     r8, WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids
0x18002852f  mov     edx, 30h ; '0'
0x180028534  mov     r9d, ebx
0x180028537  call    WPP_SF_d
0x18002853c  mov     eax, ebx
0x18002853e  mov     rcx, [rbp+var_10]
0x180028542  xor     rcx, rsp; StackCookie
0x180028545  call    __security_check_cookie
0x18002854a  lea     r11, [rsp+60h+var_s0]
0x18002854f  mov     rbx, [r11+30h]
0x180028553  mov     rsi, [r11+38h]
0x180028557  mov     rsp, r11
0x18002855a  pop     r14
0x18002855c  pop     rdi
0x18002855d  pop     rbp
0x18002855e  retn
```
