# CUI::UIRecomputeBBarHotzone(void)

- ea: `0x1804c4080`
- end: `0x1804c4547`
- name: `?UIRecomputeBBarHotzone@CUI@@AEAAXXZ`
- size: `1223`
- prototype: `void __fastcall(CUI *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180062200`
- `0x1804bd8f0`

## callees

- `0x18002a334`
- `0x180039ce4`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x1800f47c8`
- `0x18013ec14`
- `0x1804c4080`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1804c4200`
- `KERNEL32!LocalAlloc` at `0x1804c4200`
- `KERNEL32!LocalFree` at `0x1804c448e`
- `KERNEL32!LocalFree` at `0x1804c448e`
- `GDI32!CreateRectRgn` at `0x1804c410c`
- `GDI32!CreateRectRgn` at `0x1804c42df`
- `GDI32!CreateRectRgn` at `0x1804c4408`
- `GDI32!CreateRectRgn` at `0x1804c410c`
- `GDI32!CreateRectRgn` at `0x1804c42df`
- `GDI32!CreateRectRgn` at `0x1804c4408`
- `GDI32!CombineRgn` at `0x1804c442d`
- `GDI32!CombineRgn` at `0x1804c442d`
- `GDI32!DeleteObject` at `0x1804c40b6`
- `GDI32!DeleteObject` at `0x1804c4436`
- `GDI32!DeleteObject` at `0x1804c44a4`
- `GDI32!DeleteObject` at `0x1804c40b6`
- `GDI32!DeleteObject` at `0x1804c4436`
- `GDI32!DeleteObject` at `0x1804c44a4`
- `USER32!GetWindowRect` at `0x1804c40f8`
- `USER32!GetWindowRect` at `0x1804c40f8`

## string_xrefs

- `0x1804c42a6`: `ConfigureLocalSelectedMonitors failed!`

## pseudocode

```c
void __fastcall CUI::UIRecomputeBBarHotzone(CUI *this)
{
  void *v2; // rcx
  unsigned int v3; // eax
  unsigned int v4; // r15d
  HRGN v5; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  void *v9; // r14
  unsigned int v10; // eax
  HLOCAL v11; // rax
  int v12; // edi
  unsigned int v13; // eax
  int v14; // edx
  const char *v15; // rcx
  HRGN RectRgn; // rax
  unsigned int v17; // eax
  int v18; // edx
  unsigned int v19; // r13d
  unsigned int v20; // eax
  HRGN v21; // rax
  HRGN v22; // rdi
  unsigned int v23; // eax
  void *v24; // rcx
  __int64 v25; // [rsp+20h] [rbp-50h]
  struct tagRECT Rect; // [rsp+50h] [rbp-20h] BYREF

  v2 = (void *)*((_QWORD *)this + 352);
  if ( v2 )
  {
    DeleteObject(v2);
    *((_QWORD *)this + 352) = 0;
  }
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 346) + 24LL))(*((_QWORD *)this + 346));
  v4 = v3;
  Rect = 0;
  if ( v3 != 1 )
  {
    v11 = LocalAlloc(0x40u, 32LL * v3);
    v9 = v11;
    if ( !v11 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_47;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 133;
      v8 = "TS_GRAPHICS_MONITOR_DEF";
      goto LABEL_9;
    }
    v12 = (*(__int64 (__fastcall **)(_QWORD, HLOCAL, _QWORD))(**((_QWORD **)this + 346) + 192LL))(
            *((_QWORD *)this + 346),
            v11,
            v4);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 134;
        v15 = "ConfigureLocalSelectedMonitors failed!";
LABEL_24:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          (unsigned int)&WPP_30696c83131034d906bf3fa699a499d7_Traceguids,
          v13,
          (__int64)v15,
          v12);
      }
      goto LABEL_46;
    }
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    *((_QWORD *)this + 352) = RectRgn;
    if ( !RectRgn )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        v18 = 135;
LABEL_30:
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v18,
          (unsigned int)&WPP_30696c83131034d906bf3fa699a499d7_Traceguids,
          v17,
          (__int64)"HRGN");
      }
LABEL_31:
      v12 = -2147024882;
      goto LABEL_46;
    }
    v19 = 0;
    if ( v4 )
    {
      while ( 1 )
      {
        v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagRECT *, _QWORD, void *, unsigned int))(**((_QWORD **)this + 346) + 184LL))(
                *((_QWORD *)this + 346),
                v19,
                &Rect,
                0,
                v9,
                v4);
        if ( v12 < 0 )
          break;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v20 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(v25) = v4;
          WPP_SF_Ddddddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            137,
            &WPP_30696c83131034d906bf3fa699a499d7_Traceguids,
            v20,
            v25,
            v19 + 1,
            Rect.left,
            Rect.top,
            Rect.right,
            Rect.top + 5);
        }
        v21 = CreateRectRgn(Rect.left, Rect.top, Rect.right, Rect.top + 5);
        v22 = v21;
        if ( !v21 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v17 = RdpWppGetCurrentThreadActivityIdPrefix();
            v18 = 138;
            goto LABEL_30;
          }
          goto LABEL_31;
        }
        CombineRgn(*((HRGN *)this + 352), *((HRGN *)this + 352), v21, 2);
        DeleteObject(v22);
        if ( ++v19 >= v4 )
          goto LABEL_40;
      }
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        v14 = 136;
        v15 = "GetLocalMonitorRect failed!";
        goto LABEL_24;
      }
      goto LABEL_46;
    }
LABEL_40:
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_30696c83131034d906bf3fa699a499d7_Traceguids, v23);
    }
LABEL_44:
    if ( !v9 )
      return;
    v12 = 0;
LABEL_46:
    LocalFree(v9);
    if ( v12 >= 0 )
      return;
    goto LABEL_47;
  }
  GetWindowRect(*((HWND *)this + 17), &Rect);
  v5 = CreateRectRgn(Rect.left, Rect.top, Rect.right, Rect.top + 5);
  *((_QWORD *)this + 352) = v5;
  if ( v5 )
  {
    v9 = 0;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        132,
        &WPP_30696c83131034d906bf3fa699a499d7_Traceguids,
        v10,
        Rect.left,
        Rect.top,
        Rect.right,
        Rect.top + 5);
    }
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
    || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_47;
  }
  CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
  v7 = 131;
  v8 = "HRGN";
LABEL_9:
  WPP_SF_Ds(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v7,
    (unsigned int)&WPP_30696c83131034d906bf3fa699a499d7_Traceguids,
    CurrentThreadActivityIdPrefix,
    (__int64)v8);
LABEL_47:
  v24 = (void *)*((_QWORD *)this + 352);
  if ( v24 )
  {
    DeleteObject(v24);
    *((_QWORD *)this + 352) = 0;
  }
}

```

## disassembly

```asm
0x1804c4080  mov     [rsp-28h+arg_8], rbx
0x1804c4085  mov     [rsp-28h+arg_10], rsi
0x1804c408a  push    rbp
0x1804c408b  push    rdi
0x1804c408c  push    r13
0x1804c408e  push    r14
0x1804c4090  push    r15
0x1804c4092  mov     rbp, rsp
0x1804c4095  sub     rsp, 70h
0x1804c4099  mov     rax, cs:__security_cookie
0x1804c40a0  xor     rax, rsp
0x1804c40a3  mov     [rbp+var_10], rax
0x1804c40a7  mov     rsi, rcx
0x1804c40aa  mov     rcx, [rcx+0B00h]; ho
0x1804c40b1  test    rcx, rcx
0x1804c40b4  jz      short loc_1804C40C7
0x1804c40b6  call    cs:__imp_DeleteObject
0x1804c40bc  mov     qword ptr [rsi+0B00h], 0
0x1804c40c7  mov     rcx, [rsi+0AD0h]
0x1804c40ce  mov     rax, [rcx]
0x1804c40d1  mov     rax, [rax+18h]
0x1804c40d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804c40da  mov     r15d, eax
0x1804c40dd  xorps   xmm0, xmm0
0x1804c40e0  movups  xmmword ptr [rbp+Rect.left], xmm0
0x1804c40e4  cmp     eax, 1
0x1804c40e7  jnz     loc_1804C41F4
0x1804c40ed  mov     rcx, [rsi+88h]; hWnd
0x1804c40f4  lea     rdx, [rbp+Rect]; lpRect
0x1804c40f8  call    cs:__imp_GetWindowRect
0x1804c40fe  mov     edx, [rbp+Rect.top]; y1
0x1804c4101  mov     r8d, [rbp+Rect.right]; x2
0x1804c4105  mov     ecx, [rbp+Rect.left]; x1
0x1804c4108  lea     r9d, [rdx+5]; y2
0x1804c410c  call    cs:__imp_CreateRectRgn
0x1804c4112  mov     [rsi+0B00h], rax
0x1804c4119  test    rax, rax
0x1804c411c  jnz     short loc_1804C417E
0x1804c411e  mov     rax, cs:WPP_GLOBAL_Control
0x1804c4125  lea     rbx, WPP_GLOBAL_Control
0x1804c412c  cmp     rax, rbx
0x1804c412f  jz      loc_1804C4498
0x1804c4135  test    byte ptr [rax+1Ch], 8
0x1804c4139  jz      loc_1804C4498
0x1804c413f  cmp     byte ptr [rax+19h], 2
0x1804c4143  jb      loc_1804C4498
0x1804c4149  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804c414e  mov     edx, 83h
0x1804c4153  lea     rcx, aHrgn_0; "HRGN"
0x1804c415a  mov     [rsp+70h+var_50], rcx
0x1804c415f  lea     r8, WPP_30696c83131034d906bf3fa699a499d7_Traceguids
0x1804c4166  mov     rcx, cs:WPP_GLOBAL_Control
0x1804c416d  mov     r9d, eax
0x1804c4170  mov     rcx, [rcx+10h]
0x1804c4174  call    WPP_SF_Ds
0x1804c4179  jmp     loc_1804C4498
0x1804c417e  mov     rax, cs:WPP_GLOBAL_Control
0x1804c4185  lea     rbx, WPP_GLOBAL_Control
0x1804c418c  xor     r14d, r14d
0x1804c418f  cmp     rax, rbx
0x1804c4192  jz      loc_1804C4484
0x1804c4198  test    byte ptr [rax+1Ch], 1
0x1804c419c  jz      loc_1804C4484
0x1804c41a2  cmp     byte ptr [rax+19h], 5
0x1804c41a6  jb      loc_1804C4484
0x1804c41ac  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804c41b1  mov     r8d, [rbp+Rect.top]
0x1804c41b5  mov     edx, 84h
0x1804c41ba  mov     r9d, eax
0x1804c41bd  lea     ecx, [r8+5]
0x1804c41c1  mov     [rsp+70h+var_38], ecx
0x1804c41c5  mov     ecx, [rbp+Rect.right]
0x1804c41c8  mov     [rsp+70h+var_40], ecx
0x1804c41cc  mov     ecx, [rbp+Rect.left]
0x1804c41cf  mov     [rsp+70h+var_48], r8d
0x1804c41d4  lea     r8, WPP_30696c83131034d906bf3fa699a499d7_Traceguids
0x1804c41db  mov     dword ptr [rsp+70h+var_50], ecx
0x1804c41df  mov     rcx, cs:WPP_GLOBAL_Control
0x1804c41e6  mov     rcx, [rcx+10h]
0x1804c41ea  call    WPP_SF_Ddddd
0x1804c41ef  jmp     loc_1804C4484
0x1804c41f4  mov     rdx, r15
0x1804c41f7  mov     ecx, 40h ; '@'; uFlags
0x1804c41fc  shl     rdx, 5; uBytes
0x1804c4200  call    cs:__imp_LocalAlloc
0x1804c4206  mov     r14, rax
0x1804c4209  test    rax, rax
0x1804c420c  jnz     short loc_1804C424F
0x1804c420e  mov     rax, cs:WPP_GLOBAL_Control
0x1804c4215  lea     rbx, WPP_GLOBAL_Control
0x1804c421c  cmp     rax, rbx
0x1804c421f  jz      loc_1804C4498
0x1804c4225  test    byte ptr [rax+1Ch], 8
0x1804c4229  jz      loc_1804C4498
0x1804c422f  cmp     byte ptr [rax+19h], 2
0x1804c4233  jb      loc_1804C4498
0x1804c4239  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804c423e  mov     edx, 85h
0x1804c4243  lea     rcx, aTsGraphicsMoni; "TS_GRAPHICS_MONITOR_DEF"
0x1804c424a  jmp     loc_1804C415A
0x1804c424f  mov     rcx, [rsi+0AD0h]
0x1804c4256  mov     r8d, r15d
0x1804c4259  mov     rdx, r14
0x1804c425c  mov     rax, [rcx]
0x1804c425f  mov     rax, [rax+0C0h]
0x1804c4266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804c426b  mov     edi, eax
0x1804c426d  test    eax, eax
0x1804c426f  jns     short loc_1804C42D5
0x1804c4271  mov     rax, cs:WPP_GLOBAL_Control
0x1804c4278  lea     rbx, WPP_GLOBAL_Control
0x1804c427f  cmp     rax, rbx
0x1804c4282  jz      loc_1804C448B
0x1804c4288  test    byte ptr [rax+1Ch], 8
0x1804c428c  jz      loc_1804C448B
0x1804c4292  cmp     byte ptr [rax+19h], 2
0x1804c4296  jb      loc_1804C448B
0x1804c429c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804c42a1  mov     edx, 86h
0x1804c42a6  lea     rcx, aConfigurelocal; "ConfigureLocalSelectedMonitors failed!"
0x1804c42ad  mov     [rsp+70h+var_48], edi
0x1804c42b1  lea     r8, WPP_30696c83131034d906bf3fa699a499d7_Traceguids
0x1804c42b8  mov     [rsp+70h+var_50], rcx
0x1804c42bd  mov     r9d, eax
0x1804c42c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1804c42c7  mov     rcx, [rcx+10h]
0x1804c42cb  call    WPP_SF_DsD
0x1804c42d0  jmp     loc_1804C448B
0x1804c42d5  xor     r9d, r9d; y2
0x1804c42d8  xor     r8d, r8d; x2
0x1804c42db  xor     edx, edx; y1
0x1804c42dd  xor     ecx, ecx; x1
0x1804c42df  call    cs:__imp_CreateRectRgn
0x1804c42e5  mov     [rsi+0B00h], rax
0x1804c42ec  test    rax, rax
0x1804c42ef  jnz     short loc_1804C434A
0x1804c42f1  mov     rax, cs:WPP_GLOBAL_Control
0x1804c42f8  lea     rbx, WPP_GLOBAL_Control
0x1804c42ff  cmp     rax, rbx
0x1804c4302  jz      short loc_1804C4340
0x1804c4304  test    byte ptr [rax+1Ch], 8
0x1804c4308  jz      short loc_1804C4340
0x1804c430a  cmp     byte ptr [rax+19h], 2
0x1804c430e  jb      short loc_1804C4340
0x1804c4310  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804c4315  mov     edx, 87h
0x1804c431a  lea     rcx, aHrgn_0; "HRGN"
0x1804c4321  mov     r9d, eax
0x1804c4324  mov     [rsp+70h+var_50], rcx
0x1804c4329  lea     r8, WPP_30696c83131034d906bf3fa699a499d7_Traceguids
0x1804c4330  mov     rcx, cs:WPP_GLOBAL_Control
0x1804c4337  mov     rcx, [rcx+10h]
0x1804c433b  call    WPP_SF_Ds
0x1804c4340  mov     edi, 8007000Eh
0x1804c4345  jmp     loc_1804C448B
0x1804c434a  xor     r13d, r13d
0x1804c434d  lea     rbx, WPP_GLOBAL_Control
0x1804c4354  test    r15d, r15d
0x1804c4357  jz      loc_1804C4448
0x1804c435d  mov     rcx, [rsi+0AD0h]
0x1804c4364  lea     r8, [rbp+Rect]
0x1804c4368  mov     [rsp+70h+var_48], r15d
0x1804c436d  xor     r9d, r9d
0x1804c4370  mov     edx, r13d
0x1804c4373  mov     [rsp+70h+var_50], r14
0x1804c4378  mov     rax, [rcx]
0x1804c437b  mov     rax, [rax+0B8h]
0x1804c4382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804c4387  mov     edi, eax
0x1804c4389  test    eax, eax
0x1804c438b  js      loc_1804C450D
0x1804c4391  mov     rax, cs:WPP_GLOBAL_Control
0x1804c4398  cmp     rax, rbx
0x1804c439b  jz      short loc_1804C43FA
0x1804c439d  test    byte ptr [rax+1Ch], 1
0x1804c43a1  jz      short loc_1804C43FA
0x1804c43a3  cmp     byte ptr [rax+19h], 5
0x1804c43a7  jb      short loc_1804C43FA
0x1804c43a9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804c43ae  mov     r8d, [rbp+Rect.top]
0x1804c43b2  lea     r9d, [r13+1]
0x1804c43b6  mov     edx, 89h
0x1804c43bb  lea     ecx, [r8+5]
0x1804c43bf  mov     [rsp+70h+var_28], ecx
0x1804c43c3  mov     ecx, [rbp+Rect.right]
0x1804c43c6  mov     [rsp+70h+var_30], ecx
0x1804c43ca  mov     ecx, [rbp+Rect.left]
0x1804c43cd  mov     [rsp+70h+var_38], r8d
0x1804c43d2  lea     r8, WPP_30696c83131034d906bf3fa699a499d7_Traceguids
0x1804c43d9  mov     [rsp+70h+var_40], ecx
0x1804c43dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1804c43e4  mov     [rsp+70h+var_48], r9d
0x1804c43e9  mov     r9d, eax
0x1804c43ec  mov     dword ptr [rsp+70h+var_50], r15d
0x1804c43f1  mov     rcx, [rcx+10h]
0x1804c43f5  call    WPP_SF_Ddddddd
0x1804c43fa  mov     edx, [rbp+Rect.top]; y1
0x1804c43fd  mov     r8d, [rbp+Rect.right]; x2
0x1804c4401  mov     ecx, [rbp+Rect.left]; x1
0x1804c4404  lea     r9d, [rdx+5]; y2
0x1804c4408  call    cs:__imp_CreateRectRgn
0x1804c440e  mov     rdi, rax
0x1804c4411  test    rax, rax
0x1804c4414  jz      loc_1804C44DA
0x1804c441a  mov     rcx, [rsi+0B00h]; hrgnDst
0x1804c4421  mov     r9d, 2; iMode
0x1804c4427  mov     rdx, rcx; hrgnSrc1
0x1804c442a  mov     r8, rax; hrgnSrc2
0x1804c442d  call    cs:__imp_CombineRgn
0x1804c4433  mov     rcx, rdi; ho
0x1804c4436  call    cs:__imp_DeleteObject
0x1804c443c  inc     r13d
0x1804c443f  cmp     r13d, r15d
0x1804c4442  jb      loc_1804C435D
0x1804c4448  mov     rax, cs:WPP_GLOBAL_Control
0x1804c444f  cmp     rax, rbx
0x1804c4452  jz      short loc_1804C4484
0x1804c4454  test    byte ptr [rax+1Ch], 1
0x1804c4458  jz      short loc_1804C4484
0x1804c445a  cmp     byte ptr [rax+19h], 5
0x1804c445e  jb      short loc_1804C4484
0x1804c4460  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804c4465  mov     rcx, cs:WPP_GLOBAL_Control
0x1804c446c  lea     r8, WPP_30696c83131034d906bf3fa699a499d7_Traceguids
0x1804c4473  mov     edx, 8Bh
0x1804c4478  mov     r9d, eax
0x1804c447b  mov     rcx, [rcx+10h]
0x1804c447f  call    WPP_SF_d
0x1804c4484  test    r14, r14
0x1804c4487  jz      short loc_1804C44B5
0x1804c4489  xor     edi, edi
0x1804c448b  mov     rcx, r14; hMem
0x1804c448e  call    cs:__imp_LocalFree
0x1804c4494  test    edi, edi
0x1804c4496  jns     short loc_1804C44B5
0x1804c4498  mov     rcx, [rsi+0B00h]; ho
0x1804c449f  test    rcx, rcx
0x1804c44a2  jz      short loc_1804C44B5
0x1804c44a4  call    cs:__imp_DeleteObject
0x1804c44aa  mov     qword ptr [rsi+0B00h], 0
0x1804c44b5  mov     rcx, [rbp+var_10]
0x1804c44b9  xor     rcx, rsp; StackCookie
0x1804c44bc  call    __security_check_cookie
0x1804c44c1  lea     r11, [rsp+70h+var_s0]
0x1804c44c6  mov     rbx, [r11+38h]
0x1804c44ca  mov     rsi, [r11+40h]
0x1804c44ce  mov     rsp, r11
0x1804c44d1  pop     r15
0x1804c44d3  pop     r14
0x1804c44d5  pop     r13
0x1804c44d7  pop     rdi
0x1804c44d8  pop     rbp
0x1804c44d9  retn
0x1804c44da  mov     rax, cs:WPP_GLOBAL_Control
0x1804c44e1  cmp     rax, rbx
0x1804c44e4  jz      loc_1804C4340
0x1804c44ea  test    byte ptr [rax+1Ch], 8
0x1804c44ee  jz      loc_1804C4340
0x1804c44f4  cmp     byte ptr [rax+19h], 2
0x1804c44f8  jb      loc_1804C4340
0x1804c44fe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804c4503  mov     edx, 8Ah
0x1804c4508  jmp     loc_1804C431A
0x1804c450d  mov     rax, cs:WPP_GLOBAL_Control
0x1804c4514  cmp     rax, rbx
0x1804c4517  jz      loc_1804C448B
0x1804c451d  test    byte ptr [rax+1Ch], 8
0x1804c4521  jz      loc_1804C448B
0x1804c4527  cmp     byte ptr [rax+19h], 2
0x1804c452b  jb      loc_1804C448B
0x1804c4531  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1804c4536  mov     edx, 88h
0x1804c453b  lea     rcx, aGetlocalmonito; "GetLocalMonitorRect failed!"
0x1804c4542  jmp     loc_1804C42AD
```
