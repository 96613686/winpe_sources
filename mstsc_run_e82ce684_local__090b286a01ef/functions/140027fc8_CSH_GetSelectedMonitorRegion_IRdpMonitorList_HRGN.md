# CSH::GetSelectedMonitorRegion(IRdpMonitorList *,HRGN__ * *)

- ea: `0x140027fc8`
- end: `0x1400283b0`
- name: `?GetSelectedMonitorRegion@CSH@@SAJPEAVIRdpMonitorList@@PEAPEAUHRGN__@@@Z`
- size: `1000`
- prototype: `__int64 __fastcall(struct IRdpMonitorList *, HRGN *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400132fc`

## callees

- `0x140004703`
- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000cffc`
- `0x14000d078`
- `0x14001e560`
- `0x14001e610`
- `0x140027fc8`
- `0x140113390`
- `0x140114010`

## import_xrefs

- `GDI32!CombineRgn` at `0x1400281fe`
- `GDI32!CombineRgn` at `0x1400281fe`
- `GDI32!DeleteObject` at `0x1400281b9`
- `GDI32!DeleteObject` at `0x14002836f`
- `GDI32!DeleteObject` at `0x14002837d`
- `GDI32!DeleteObject` at `0x1400281b9`
- `GDI32!DeleteObject` at `0x14002836f`
- `GDI32!DeleteObject` at `0x14002837d`
- `GDI32!CreateRectRgn` at `0x1400281d1`
- `GDI32!CreateRectRgn` at `0x1400281d1`

## pseudocode

```c
__int64 __fastcall CSH::GetSelectedMonitorRegion(struct IRdpMonitorList *a1, HRGN *a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  int v7; // ebx
  unsigned int v8; // eax
  HRGN v9; // rdi
  HRGN v10; // rsi
  unsigned int i; // r14d
  __int64 v12; // rax
  void *v13; // rcx
  DWORD v14; // r9d
  HDC v15; // rcx
  HRGN RectRgn; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v22; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v23; // [rsp+34h] [rbp-CCh] BYREF
  LPARAM v24[2]; // [rsp+38h] [rbp-C8h] BYREF
  int x1[6]; // [rsp+48h] [rbp-B8h] BYREF
  DISPLAY_DEVICEA v26; // [rsp+60h] [rbp-A0h] BYREF

  v22 = 0;
  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 56;
    v6 = "pSelectedMonitors";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_b7ae6d635a30399768ffbc73af776916_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v6);
    return (unsigned int)-2147467261;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467261;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 57;
    v6 = "phrgnSelectedMonitors";
    goto LABEL_6;
  }
  v7 = (*(__int64 (__fastcall **)(struct IRdpMonitorList *, unsigned int *))(*(_QWORD *)a1 + 40LL))(a1, &v22);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        (unsigned int)WPP_b7ae6d635a30399768ffbc73af776916_Traceguids,
        v8,
        (__int64)"GetMonitorCount failed",
        v7);
    }
    return (unsigned int)v7;
  }
  v9 = 0;
  v10 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= v22 )
    {
      *a2 = v10;
      v10 = 0;
      v7 = 0;
      goto LABEL_47;
    }
    v23 = 0;
    memset_0(v26.DeviceName, 0, 0x344u);
    v12 = *(_QWORD *)a1;
    v26.cb = 840;
    *(_OWORD *)x1 = 0;
    v7 = (*(__int64 (__fastcall **)(struct IRdpMonitorList *, _QWORD, DWORD *))(v12 + 32))(a1, i, &v23);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          (unsigned int)WPP_b7ae6d635a30399768ffbc73af776916_Traceguids,
          v20,
          (__int64)"GetMonitorDevNum failed",
          v7);
      }
LABEL_47:
      if ( !v9 )
        goto LABEL_49;
      goto LABEL_48;
    }
    if ( !xEnumDisplayDevices(v13, v23, &v26, v14) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          WPP_b7ae6d635a30399768ffbc73af776916_Traceguids,
          v19,
          -2147418113);
      }
      v7 = -2147418113;
      goto LABEL_47;
    }
    v24[0] = (LPARAM)&v26;
    v24[1] = (LPARAM)x1;
    xEnumDisplayMonitors(v15, 0, GetMonitorRectEnumProc, (LPARAM)v24);
    if ( v9 )
      DeleteObject(v9);
    RectRgn = CreateRectRgn(x1[0], x1[1], x1[2], x1[3]);
    v9 = RectRgn;
    if ( !RectRgn )
      break;
    if ( !v10 )
    {
      v10 = RectRgn;
      v9 = 0;
      continue;
    }
    if ( !CombineRgn(v10, v10, RectRgn, 2) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids, v17);
      }
LABEL_48:
      DeleteObject(v9);
      goto LABEL_49;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids, v18);
  }
LABEL_49:
  if ( v10 )
    DeleteObject(v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140027fc8  mov     [rsp-8+arg_10], rbx
0x140027fcd  mov     [rsp-8+arg_18], rsi
0x140027fd2  push    rbp
0x140027fd3  push    rdi
0x140027fd4  push    r12
0x140027fd6  push    r14
0x140027fd8  push    r15
0x140027fda  lea     rbp, [rsp-2C0h]
0x140027fe2  sub     rsp, 3C0h
0x140027fe9  mov     rax, cs:__security_cookie
0x140027ff0  xor     rax, rsp
0x140027ff3  mov     [rbp+2E0h+var_30], rax
0x140027ffa  mov     [rsp+3E0h+var_3B0], 0
0x140028002  mov     r12, rdx
0x140028005  mov     r15, rcx
0x140028008  test    rcx, rcx
0x14002800b  jnz     short loc_140028065
0x14002800d  mov     rcx, cs:WPP_GLOBAL_Control
0x140028014  lea     rax, WPP_GLOBAL_Control
0x14002801b  cmp     rcx, rax
0x14002801e  jz      short loc_14002805B
0x140028020  test    byte ptr [rcx+1Ch], 8
0x140028024  jz      short loc_14002805B
0x140028026  cmp     byte ptr [rcx+19h], 2
0x14002802a  jb      short loc_14002805B
0x14002802c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140028031  lea     edx, [r15+38h]
0x140028035  lea     rcx, aPselectedmonit; "pSelectedMonitors"
0x14002803c  mov     [rsp+3E0h+var_3C0], rcx
0x140028041  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x140028048  mov     rcx, cs:WPP_GLOBAL_Control
0x14002804f  mov     r9d, eax
0x140028052  mov     rcx, [rcx+10h]
0x140028056  call    WPP_SF_Ds
0x14002805b  mov     ebx, 80004003h
0x140028060  jmp     loc_140028383
0x140028065  test    r12, r12
0x140028068  jnz     short loc_14002809C
0x14002806a  mov     rcx, cs:WPP_GLOBAL_Control
0x140028071  lea     rax, WPP_GLOBAL_Control
0x140028078  cmp     rcx, rax
0x14002807b  jz      short loc_14002805B
0x14002807d  test    byte ptr [rcx+1Ch], 8
0x140028081  jz      short loc_14002805B
0x140028083  cmp     byte ptr [rcx+19h], 2
0x140028087  jb      short loc_14002805B
0x140028089  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002808e  lea     edx, [r12+39h]
0x140028093  lea     rcx, aPhrgnselectedm; "phrgnSelectedMonitors"
0x14002809a  jmp     short loc_14002803C
0x14002809c  mov     rax, [rcx]
0x14002809f  lea     rdx, [rsp+3E0h+var_3B0]
0x1400280a4  mov     rax, [rax+28h]
0x1400280a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400280ad  mov     ebx, eax
0x1400280af  test    eax, eax
0x1400280b1  jns     short loc_140028117
0x1400280b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400280ba  lea     rax, WPP_GLOBAL_Control
0x1400280c1  cmp     rcx, rax
0x1400280c4  jz      loc_140028383
0x1400280ca  test    byte ptr [rcx+1Ch], 8
0x1400280ce  jz      loc_140028383
0x1400280d4  cmp     byte ptr [rcx+19h], 2
0x1400280d8  jb      loc_140028383
0x1400280de  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400280e3  lea     rcx, aGetmonitorcoun; "GetMonitorCount failed"
0x1400280ea  mov     [rsp+3E0h+var_3B8], ebx
0x1400280ee  mov     [rsp+3E0h+var_3C0], rcx
0x1400280f3  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x1400280fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140028101  mov     edx, 3Ah ; ':'
0x140028106  mov     r9d, eax
0x140028109  mov     rcx, [rcx+10h]
0x14002810d  call    WPP_SF_DsD
0x140028112  jmp     loc_140028383
0x140028117  xor     edi, edi
0x140028119  xor     esi, esi
0x14002811b  xor     r14d, r14d
0x14002811e  cmp     r14d, [rsp+3E0h+var_3B0]
0x140028123  jnb     loc_14002835F
0x140028129  xor     edx, edx; Val
0x14002812b  mov     [rsp+3E0h+var_3AC], 0
0x140028133  mov     r8d, 344h; Size
0x140028139  lea     rcx, [rsp+3E0h+var_380.DeviceName]; void *
0x14002813e  call    memset_0
0x140028143  mov     rax, [r15]
0x140028146  lea     r8, [rsp+3E0h+var_3AC]
0x14002814b  xorps   xmm0, xmm0
0x14002814e  mov     [rsp+3E0h+var_380.cb], 348h
0x140028156  mov     edx, r14d
0x140028159  mov     rcx, r15
0x14002815c  movups  xmmword ptr [rsp+3E0h+x1], xmm0
0x140028161  mov     rax, [rax+20h]
0x140028165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002816a  mov     ebx, eax
0x14002816c  test    eax, eax
0x14002816e  js      loc_14002830A
0x140028174  mov     edx, [rsp+3E0h+var_3AC]; DWORD
0x140028178  lea     r8, [rsp+3E0h+var_380]; PDISPLAY_DEVICE
0x14002817d  call    xEnumDisplayDevices
0x140028182  test    eax, eax
0x140028184  jz      loc_1400282B8
0x14002818a  lea     rax, [rsp+3E0h+var_380]
0x14002818f  xor     edx, edx; LPCRECT
0x140028191  mov     [rsp+3E0h+var_3A8], rax
0x140028196  lea     r9, [rsp+3E0h+var_3A8]; LPARAM
0x14002819b  lea     rax, [rsp+3E0h+x1]
0x1400281a0  lea     r8, ?GetMonitorRectEnumProc@@YAHPEAUHMONITOR__@@PEAUHDC__@@PEAUtagRECT@@_J@Z; MONITORENUMPROC
0x1400281a7  mov     [rsp+3E0h+var_3A0], rax
0x1400281ac  call    xEnumDisplayMonitors
0x1400281b1  test    rdi, rdi
0x1400281b4  jz      short loc_1400281BF
0x1400281b6  mov     rcx, rdi; ho
0x1400281b9  call    cs:__imp_DeleteObject
0x1400281bf  mov     r9d, [rsp+3E0h+x1+0Ch]; y2
0x1400281c4  mov     r8d, [rsp+3E0h+x1+8]; x2
0x1400281c9  mov     edx, [rsp+3E0h+x1+4]; y1
0x1400281cd  mov     ecx, [rsp+3E0h+x1]; x1
0x1400281d1  call    cs:__imp_CreateRectRgn
0x1400281d7  mov     rdi, rax
0x1400281da  test    rax, rax
0x1400281dd  jz      loc_140028264
0x1400281e3  test    rsi, rsi
0x1400281e6  jnz     short loc_1400281EF
0x1400281e8  mov     rsi, rax
0x1400281eb  xor     edi, edi
0x1400281ed  jmp     short loc_140028208
0x1400281ef  mov     r9d, 2; iMode
0x1400281f5  mov     r8, rax; hrgnSrc2
0x1400281f8  mov     rdx, rsi; hrgnSrc1
0x1400281fb  mov     rcx, rsi; hrgnDst
0x1400281fe  call    cs:__imp_CombineRgn
0x140028204  test    eax, eax
0x140028206  jz      short loc_140028210
0x140028208  inc     r14d
0x14002820b  jmp     loc_14002811E
0x140028210  mov     rcx, cs:WPP_GLOBAL_Control
0x140028217  lea     rax, WPP_GLOBAL_Control
0x14002821e  cmp     rcx, rax
0x140028221  jz      loc_14002836C
0x140028227  test    byte ptr [rcx+1Ch], 8
0x14002822b  jz      loc_14002836C
0x140028231  cmp     byte ptr [rcx+19h], 2
0x140028235  jb      loc_14002836C
0x14002823b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140028240  mov     rcx, cs:WPP_GLOBAL_Control
0x140028247  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x14002824e  mov     edx, 3Eh ; '>'
0x140028253  mov     r9d, eax
0x140028256  mov     rcx, [rcx+10h]
0x14002825a  call    WPP_SF_d
0x14002825f  jmp     loc_14002836C
0x140028264  mov     rcx, cs:WPP_GLOBAL_Control
0x14002826b  lea     rax, WPP_GLOBAL_Control
0x140028272  cmp     rcx, rax
0x140028275  jz      loc_140028375
0x14002827b  test    byte ptr [rcx+1Ch], 8
0x14002827f  jz      loc_140028375
0x140028285  cmp     byte ptr [rcx+19h], 2
0x140028289  jb      loc_140028375
0x14002828f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140028294  mov     rcx, cs:WPP_GLOBAL_Control
0x14002829b  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x1400282a2  mov     edx, 3Dh ; '='
0x1400282a7  mov     r9d, eax
0x1400282aa  mov     rcx, [rcx+10h]
0x1400282ae  call    WPP_SF_d
0x1400282b3  jmp     loc_140028375
0x1400282b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400282bf  lea     rax, WPP_GLOBAL_Control
0x1400282c6  cmp     rcx, rax
0x1400282c9  jz      short loc_140028303
0x1400282cb  test    byte ptr [rcx+1Ch], 8
0x1400282cf  jz      short loc_140028303
0x1400282d1  cmp     byte ptr [rcx+19h], 2
0x1400282d5  jb      short loc_140028303
0x1400282d7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400282dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400282e3  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x1400282ea  mov     edx, 3Ch ; '<'
0x1400282ef  mov     dword ptr [rsp+3E0h+var_3C0], 8000FFFFh
0x1400282f7  mov     r9d, eax
0x1400282fa  mov     rcx, [rcx+10h]
0x1400282fe  call    WPP_SF_Dd
0x140028303  mov     ebx, 8000FFFFh
0x140028308  jmp     short loc_140028367
0x14002830a  mov     rcx, cs:WPP_GLOBAL_Control
0x140028311  lea     rax, WPP_GLOBAL_Control
0x140028318  cmp     rcx, rax
0x14002831b  jz      short loc_140028367
0x14002831d  test    byte ptr [rcx+1Ch], 8
0x140028321  jz      short loc_140028367
0x140028323  cmp     byte ptr [rcx+19h], 2
0x140028327  jb      short loc_140028367
0x140028329  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002832e  lea     rcx, aGetmonitordevn; "GetMonitorDevNum failed"
0x140028335  mov     [rsp+3E0h+var_3B8], ebx
0x140028339  mov     [rsp+3E0h+var_3C0], rcx
0x14002833e  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x140028345  mov     rcx, cs:WPP_GLOBAL_Control
0x14002834c  mov     edx, 3Bh ; ';'
0x140028351  mov     r9d, eax
0x140028354  mov     rcx, [rcx+10h]
0x140028358  call    WPP_SF_DsD
0x14002835d  jmp     short loc_140028367
0x14002835f  mov     [r12], rsi
0x140028363  xor     esi, esi
0x140028365  xor     ebx, ebx
0x140028367  test    rdi, rdi
0x14002836a  jz      short loc_140028375
0x14002836c  mov     rcx, rdi; ho
0x14002836f  call    cs:__imp_DeleteObject
0x140028375  test    rsi, rsi
0x140028378  jz      short loc_140028383
0x14002837a  mov     rcx, rsi; ho
0x14002837d  call    cs:__imp_DeleteObject
0x140028383  mov     eax, ebx
0x140028385  mov     rcx, [rbp+2E0h+var_30]
0x14002838c  xor     rcx, rsp; StackCookie
0x14002838f  call    __security_check_cookie
0x140028394  lea     r11, [rsp+3E0h+var_20]
0x14002839c  mov     rbx, [r11+40h]
0x1400283a0  mov     rsi, [r11+48h]
0x1400283a4  mov     rsp, r11
0x1400283a7  pop     r15
0x1400283a9  pop     r14
0x1400283ab  pop     r12
0x1400283ad  pop     rdi
0x1400283ae  pop     rbp
0x1400283af  retn
```
