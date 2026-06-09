# CSNOCplCore::StartServiceMonitors(void)

- ea: `0x180011c38`
- end: `0x180011e46`
- name: `?StartServiceMonitors@CSNOCplCore@@AEAAXXZ`
- size: `526`
- prototype: `void __fastcall(CSNOCplCore *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000bf2c`

## callees

- `0x18000400c`
- `0x180008e14`
- `0x180011c38`
- `0x180012408`
- `0x180014274`
- `0x18001431c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180011da7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180011da7`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180011d87`
- `api-ms-win-service-private-l1-1-0!SubscribeServiceChangeNotifications` at `0x180011d87`

## pseudocode

```c
void __fastcall CSNOCplCore::StartServiceMonitors(CSNOCplCore *this, PVOID *a2)
{
  signed int v3; // ebx
  __int64 v4; // r14
  char *v5; // rax
  PVOID *v6; // rcx
  _QWORD *v7; // rsi
  char *v8; // rax
  char *v9; // rdi
  const unsigned __int16 *v10; // r8
  int v11; // eax
  int v12; // eax
  unsigned __int16 *v13; // [rsp+30h] [rbp-50h]
  char *v14; // [rsp+38h] [rbp-48h]
  _DWORD v15[2]; // [rsp+40h] [rbp-40h]
  const WCHAR *v16; // [rsp+48h] [rbp-38h]
  char *v17; // [rsp+50h] [rbp-30h]
  int v18; // [rsp+58h] [rbp-28h]
  const WCHAR *v19; // [rsp+60h] [rbp-20h]
  char *v20; // [rsp+68h] [rbp-18h]
  int v21; // [rsp+70h] [rbp-10h]

  v13 = L"netprofm";
  v3 = 0;
  v4 = 0;
  v14 = (char *)this + 264;
  v15[0] = 9;
  v16 = L"netman";
  v17 = (char *)this + 272;
  v19 = L"wlansvc";
  v5 = (char *)this + 280;
  v18 = 9;
  v21 = 9;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  v20 = v5;
  while ( (unsigned int)v4 < 3 )
  {
    v7 = *(_QWORD **)&v15[6 * v4 - 2];
    v8 = (char *)DirectUI::HAllocAndZero((DirectUI *)0x230, (unsigned __int64)a2);
    v9 = v8;
    if ( !v8 )
    {
      *v7 = 0;
      v3 = -2147024882;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      break;
    }
    v10 = (&v13)[3 * v4];
    *(_QWORD *)v8 = &CServiceMonitor::`vftable';
    *(_QWORD *)(v8 + 524) = 0;
    *((_QWORD *)v8 + 67) = 0;
    *((_QWORD *)v8 + 69) = 0;
    *((_QWORD *)v8 + 68) = ((unsigned __int64)this + 104) & -(__int64)(this != 0);
    *((_WORD *)v8 + 4) = 0;
    if ( v10 )
      StringCchCopyW((unsigned __int16 *)v8 + 4, 0x101u, v10);
    *v7 = v9;
    if ( *((_QWORD *)v9 + 68) )
    {
      *((_DWORD *)v9 + 132) = v15[6 * v4];
      v11 = CServiceMonitor::AttachToService((const WCHAR *)v9);
      v3 = v11;
      if ( v11 >= 0 )
      {
        v12 = SubscribeServiceChangeNotifications(
                *((_QWORD *)v9 + 67),
                2,
                CServiceMonitor::OnStatusChanged,
                v9,
                v9 + 552);
        if ( v12 )
        {
          if ( v12 > 0 )
            v3 = (unsigned __int16)v12 | 0x80070000;
          else
            v3 = v12;
          CloseServiceHandle(*((SC_HANDLE *)v9 + 67));
        }
        if ( v3 >= 0 )
          goto LABEL_19;
        LOBYTE(v11) = v3;
      }
    }
    else
    {
      LOBYTE(v11) = 3;
      v3 = -2147467261;
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
    a2 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_20;
    WPP_SF_SD(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, (_DWORD)v10, (unsigned int)(&v13)[3 * v4], v11);
LABEL_19:
    v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
    v4 = (unsigned int)(v4 + 1);
    if ( v3 < 0 )
      break;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
    WPP_SF_d(v6[2], 23, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, (unsigned int)v3);
}

```

## disassembly

```asm
0x180011c38  push    rbp
0x180011c3a  push    rbx
0x180011c3b  push    rsi
0x180011c3c  push    rdi
0x180011c3d  push    r13
0x180011c3f  push    r14
0x180011c41  push    r15
0x180011c43  mov     rbp, rsp
0x180011c46  sub     rsp, 80h
0x180011c4d  mov     r13, rcx
0x180011c50  lea     rax, ServiceName; "netprofm"
0x180011c57  mov     [rbp+var_50], rax
0x180011c5b  xor     ebx, ebx
0x180011c5d  lea     rax, [rcx+108h]
0x180011c64  xor     r14d, r14d
0x180011c67  mov     [rbp+var_48], rax
0x180011c6b  mov     ecx, 9
0x180011c70  lea     rax, aNetman; "netman"
0x180011c77  mov     [rbp+var_40], ecx
0x180011c7a  mov     [rbp+var_38], rax
0x180011c7e  lea     rax, [r13+110h]
0x180011c85  mov     [rbp+var_30], rax
0x180011c89  lea     rax, aWlansvc; "wlansvc"
0x180011c90  mov     [rbp+var_20], rax
0x180011c94  lea     rax, [r13+118h]
0x180011c9b  mov     [rbp+var_28], ecx
0x180011c9e  mov     [rbp+var_10], ecx
0x180011ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ca8  mov     [rbp+var_18], rax
0x180011cac  cmp     r14d, 3
0x180011cb0  jnb     loc_180011E0A
0x180011cb6  lea     r15, [r14+r14*2]
0x180011cba  mov     ecx, 230h; this
0x180011cbf  mov     rsi, [rbp+r15*8+var_48]
0x180011cc4  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x180011cc9  mov     rdi, rax
0x180011ccc  test    rax, rax
0x180011ccf  jz      loc_180011DF7
0x180011cd5  mov     r8, [rbp+r15*8+var_50]; unsigned __int16 *
0x180011cda  lea     rax, ??_7CServiceMonitor@@6B@; const CServiceMonitor::`vftable'
0x180011ce1  mov     [rdi], rax
0x180011ce4  lea     r9, [r13+68h]
0x180011ce8  mov     rcx, r13
0x180011ceb  mov     qword ptr [rdi+20Ch], 0
0x180011cf6  neg     rcx
0x180011cf9  mov     qword ptr [rdi+218h], 0
0x180011d04  lea     rcx, [rdi+8]; unsigned __int16 *
0x180011d08  mov     qword ptr [rdi+228h], 0
0x180011d13  sbb     rdx, rdx
0x180011d16  xor     eax, eax
0x180011d18  and     rdx, r9
0x180011d1b  mov     [rdi+220h], rdx
0x180011d22  mov     [rcx], ax
0x180011d25  test    r8, r8
0x180011d28  jz      short loc_180011D34
0x180011d2a  mov     edx, 101h; unsigned __int64
0x180011d2f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180011d34  mov     [rsi], rdi
0x180011d37  cmp     qword ptr [rdi+220h], 0
0x180011d3f  jnz     short loc_180011D4C
0x180011d41  mov     ecx, 80004003h
0x180011d46  mov     eax, ecx
0x180011d48  mov     ebx, ecx
0x180011d4a  jmp     short loc_180011DB3
0x180011d4c  mov     eax, [rbp+r15*8+var_40]
0x180011d51  mov     rcx, rdi; this
0x180011d54  mov     [rdi+210h], eax
0x180011d5a  call    ?AttachToService@CServiceMonitor@@IEAAJXZ; CServiceMonitor::AttachToService(void)
0x180011d5f  mov     ebx, eax
0x180011d61  test    eax, eax
0x180011d63  js      short loc_180011DB3
0x180011d65  mov     rcx, [rdi+218h]
0x180011d6c  lea     rax, [rdi+228h]
0x180011d73  mov     r9, rdi
0x180011d76  mov     [rsp+80h+var_60], rax
0x180011d7b  lea     r8, ?OnStatusChanged@CServiceMonitor@@KAXKPEAX@Z; CServiceMonitor::OnStatusChanged(ulong,void *)
0x180011d82  mov     edx, 2
0x180011d87  call    cs:__imp_SubscribeServiceChangeNotifications
0x180011d8d  test    eax, eax
0x180011d8f  jz      short loc_180011DAD
0x180011d91  jg      short loc_180011D97
0x180011d93  mov     ebx, eax
0x180011d95  jmp     short loc_180011DA0
0x180011d97  movzx   ebx, ax
0x180011d9a  or      ebx, 80070000h
0x180011da0  mov     rcx, [rdi+218h]; hSCObject
0x180011da7  call    cs:__imp_CloseServiceHandle
0x180011dad  test    ebx, ebx
0x180011daf  jns     short loc_180011DE3
0x180011db1  mov     eax, ebx
0x180011db3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011dba  lea     rdx, WPP_GLOBAL_Control
0x180011dc1  cmp     rcx, rdx
0x180011dc4  jz      short loc_180011DEA
0x180011dc6  test    byte ptr [rcx+1Ch], 2
0x180011dca  jz      short loc_180011DEA
0x180011dcc  mov     r9, [rbp+r15*8+var_50]
0x180011dd1  mov     edx, 16h
0x180011dd6  mov     rcx, [rcx+10h]
0x180011dda  mov     dword ptr [rsp+80h+var_60], eax
0x180011dde  call    WPP_SF_SD
0x180011de3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011dea  inc     r14d
0x180011ded  test    ebx, ebx
0x180011def  jns     loc_180011CAC
0x180011df5  jmp     short loc_180011E0A
0x180011df7  mov     qword ptr [rsi], 0
0x180011dfe  mov     ebx, 8007000Eh
0x180011e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e0a  lea     rax, WPP_GLOBAL_Control
0x180011e11  cmp     rcx, rax
0x180011e14  jz      short loc_180011E34
0x180011e16  test    byte ptr [rcx+1Ch], 8
0x180011e1a  jz      short loc_180011E34
0x180011e1c  mov     rcx, [rcx+10h]
0x180011e20  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180011e27  mov     edx, 17h
0x180011e2c  mov     r9d, ebx
0x180011e2f  call    WPP_SF_d
0x180011e34  add     rsp, 80h
0x180011e3b  pop     r15
0x180011e3d  pop     r14
0x180011e3f  pop     r13
0x180011e41  pop     rdi
0x180011e42  pop     rsi
0x180011e43  pop     rbx
0x180011e44  pop     rbp
0x180011e45  retn
```
