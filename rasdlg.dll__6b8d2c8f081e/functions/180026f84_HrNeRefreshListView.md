# HrNeRefreshListView

- ea: `0x180026f84`
- end: `0x180027321`
- name: `HrNeRefreshListView`
- size: `925`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001b134`

## callees

- `0x180026e64`
- `0x180026eb0`
- `0x180026f84`
- `0x180027328`
- `0x180040ef8`
- `0x180046510`
- `0x180046764`
- `0x18004d0c6`
- `0x18004d0d2`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800272d5`
- `msvcrt!_wcsicmp` at `0x1800272eb`
- `msvcrt!_wcsicmp` at `0x1800272d5`
- `msvcrt!_wcsicmp` at `0x1800272eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800270d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800270e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027164`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800271fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800272ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800270d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800270e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027164`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800271fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800272ff`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800270b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800270b3`
- `USER32!SendMessageW` at `0x180026fe4`
- `USER32!SendMessageW` at `0x18002712b`
- `USER32!SendMessageW` at `0x18002727c`
- `USER32!SendMessageW` at `0x180026fe4`
- `USER32!SendMessageW` at `0x18002712b`
- `USER32!SendMessageW` at `0x18002727c`
- `SETUPAPI!SetupDiGetClassImageIndex` at `0x180027255`
- `SETUPAPI!SetupDiGetClassImageIndex` at `0x180027255`

## pseudocode

```c
__int64 __fastcall HrNeRefreshListView(__int64 a1)
{
  HWND v2; // rcx
  __int64 v3; // rdx
  int v4; // r13d
  __int64 i; // r15
  __int64 *v6; // rbx
  __int64 v7; // rdi
  HWND v8; // rcx
  int v10; // edi
  int v11; // eax
  int v12; // r14d
  __int64 v13; // rax
  HWND v14; // rcx
  LPCWSTR lpString1; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v16; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v17; // [rsp+2Ch] [rbp-D4h] BYREF
  int ImageIndex; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  LPARAM lParam; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+4Ch] [rbp-B4h]
  int v22; // [rsp+50h] [rbp-B0h]
  LPVOID v23; // [rsp+58h] [rbp-A8h]
  int v24; // [rsp+64h] [rbp-9Ch]
  __int64 *v25; // [rsp+68h] [rbp-98h]
  __int128 Buf1; // [rsp+A0h] [rbp-60h] BYREF
  GUID ClassGuid; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v28[256]; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(v28, 0, sizeof(v28));
  v2 = *(HWND *)(a1 + 536);
  v17 = 0;
  SendMessageW(v2, 0x1009u, 0, 0);
  v4 = HrEnumComponentsForListView(*(__int64 **)(a1 + 1440), v3, v28, &v17);
  if ( v4 >= 0 )
  {
    for ( i = 0; (unsigned int)i < v17; i = (unsigned int)(i + 1) )
    {
      v6 = (__int64 *)v28[i];
      v16 = 0;
      pv = 0;
      lpString1 = 0;
      memset_0(&lParam, 0, 0x58u);
      Buf1 = 0;
      if ( (*(int (__fastcall **)(__int64 *, unsigned int *))(*v6 + 56))(v6, &v16) < 0
        || (v16 & 8) != 0
        || (*(int (__fastcall **)(__int64 *, LPVOID *))(*v6 + 24))(v6, &pv) < 0 )
      {
        goto LABEL_12;
      }
      if ( (*(int (__fastcall **)(__int64 *, LPCWSTR *))(*v6 + 48))(v6, &lpString1) >= 0 )
      {
        v7 = 0;
        while ( lstrcmpW(lpString1, off_180050490[v7]) )
        {
          v7 = (unsigned int)(v7 + 1);
          if ( (unsigned int)v7 >= 5 )
          {
            if ( (_DWORD)v7 == 5 )
            {
              CoTaskMemFree((LPVOID)lpString1);
              goto LABEL_12;
            }
            break;
          }
        }
        CoTaskMemFree((LPVOID)lpString1);
      }
      v10 = (v16 >> 17) & 1;
      if ( *(_DWORD *)(*(_QWORD *)a1 + 28LL)
        && *(_DWORD *)(*(_QWORD *)a1 + 32LL)
        && (*(int (__fastcall **)(__int64 *, __int128 *))(*v6 + 80))(v6, &Buf1) >= 0 )
      {
        if ( memcmp_0(&Buf1, &GUID_DEVCLASS_NETTRANS, 0x10u)
          || (*(int (__fastcall **)(__int64 *, LPCWSTR *))(*v6 + 48))(v6, &lpString1) < 0 )
        {
          goto LABEL_12;
        }
        v11 = DwProtocolFromComponentId(lpString1);
        if ( v11 == 4 || (v12 = 1, v11 == 8) )
          v12 = 0;
        CoTaskMemFree((LPVOID)lpString1);
        if ( v12 )
          goto LABEL_12;
      }
      v23 = pv;
      LODWORD(lParam) = 7;
      v13 = *v6;
      ImageIndex = 0;
      ClassGuid = 0;
      if ( (*(int (__fastcall **)(__int64 *, GUID *))(v13 + 80))(v6, &ClassGuid) >= 0 )
        SetupDiGetClassImageIndex((PSP_CLASSIMAGELIST_DATA)(a1 + 1456), &ClassGuid, &ImageIndex);
      v14 = *(HWND *)(a1 + 536);
      v24 = ImageIndex;
      v25 = v6;
      if ( (unsigned int)SendMessageW(v14, 0x104Du, 0, (LPARAM)&lParam) == -1 )
      {
LABEL_12:
        ReleaseObj(v6);
      }
      else
      {
        NeQueryOrChangeComponentEnabled(a1, v6, 0, 0);
        ListView_SetCheck(*(HWND *)(a1 + 536));
        if ( (*(int (__fastcall **)(__int64 *, LPCWSTR *))(*v6 + 48))(v6, &lpString1) >= 0 )
        {
          if ( !_wcsicmp(lpString1, L"ms_psched") || !_wcsicmp(lpString1, L"ms_NetMon") )
            v10 = 1;
          CoTaskMemFree((LPVOID)lpString1);
        }
        if ( v10 )
          ListView_DisableCheck(*(HWND *)(a1 + 536));
      }
      CoTaskMemFree(pv);
    }
    memset_0(&lParam, 0, 0x58u);
    v8 = *(HWND *)(a1 + 536);
    v22 = 3;
    v21 = 3;
    SendMessageW(v8, 0x102Bu, 0, (LPARAM)&lParam);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180026f84  mov     [rsp-8+arg_8], rbx
0x180026f89  mov     [rsp-8+arg_10], rsi
0x180026f8e  push    rbp
0x180026f8f  push    rdi
0x180026f90  push    r13
0x180026f92  push    r14
0x180026f94  push    r15
0x180026f96  lea     rbp, [rsp-7D0h]
0x180026f9e  sub     rsp, 8D0h
0x180026fa5  mov     rax, cs:__security_cookie
0x180026fac  xor     rax, rsp
0x180026faf  mov     [rbp+7F0h+var_30], rax
0x180026fb6  mov     rsi, rcx
0x180026fb9  xor     edx, edx; Val
0x180026fbb  lea     rcx, [rbp+7F0h+var_830]; void *
0x180026fbf  mov     r8d, 800h; Size
0x180026fc5  call    memset_0
0x180026fca  mov     rcx, [rsi+218h]; hWnd
0x180026fd1  xor     r9d, r9d; lParam
0x180026fd4  xor     r8d, r8d; wParam
0x180026fd7  mov     [rsp+8F0h+var_8C4], 0
0x180026fdf  mov     edx, 1009h; Msg
0x180026fe4  call    cs:__imp_SendMessageW
0x180026fea  mov     rcx, [rsi+5A0h]
0x180026ff1  lea     r9, [rsp+8F0h+var_8C4]
0x180026ff6  lea     r8, [rbp+7F0h+var_830]
0x180026ffa  call    HrEnumComponentsForListView
0x180026fff  mov     r13d, eax
0x180027002  test    eax, eax
0x180027004  js      loc_180027131
0x18002700a  xor     r15d, r15d
0x18002700d  cmp     [rsp+8F0h+var_8C4], r15d
0x180027012  jbe     loc_1800270FA
0x180027018  mov     rbx, [rbp+r15*8+7F0h+var_830]
0x18002701d  lea     rcx, [rsp+8F0h+lParam]; void *
0x180027022  xor     edx, edx; Val
0x180027024  mov     [rsp+8F0h+var_8C8], 0
0x18002702c  mov     [rsp+8F0h+pv], 0
0x180027035  mov     [rsp+8F0h+lpString1], 0
0x18002703e  lea     r8d, [rdx+58h]; Size
0x180027042  call    memset_0
0x180027047  xorps   xmm0, xmm0
0x18002704a  lea     rdx, [rsp+8F0h+var_8C8]
0x18002704f  movups  [rbp+7F0h+Buf1], xmm0
0x180027053  mov     rax, [rbx]
0x180027056  mov     rcx, rbx
0x180027059  mov     rax, [rax+38h]
0x18002705d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027062  test    eax, eax
0x180027064  js      short loc_1800270D9
0x180027066  test    byte ptr [rsp+8F0h+var_8C8], 8
0x18002706b  jnz     short loc_1800270D9
0x18002706d  mov     rax, [rbx]
0x180027070  lea     rdx, [rsp+8F0h+pv]
0x180027075  mov     rcx, rbx
0x180027078  mov     rax, [rax+18h]
0x18002707c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027081  test    eax, eax
0x180027083  js      short loc_1800270D9
0x180027085  mov     rax, [rbx]
0x180027088  lea     rdx, [rsp+8F0h+lpString1]
0x18002708d  mov     rcx, rbx
0x180027090  mov     rax, [rax+30h]
0x180027094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027099  test    eax, eax
0x18002709b  js      loc_18002716A
0x1800270a1  xor     edi, edi
0x1800270a3  mov     rcx, [rsp+8F0h+lpString1]; lpString1
0x1800270a8  lea     rax, off_180050490; "ms_tcpip"
0x1800270af  mov     rdx, [rax+rdi*8]; lpString2
0x1800270b3  call    cs:__imp_lstrcmpW
0x1800270b9  test    eax, eax
0x1800270bb  jz      loc_18002715F
0x1800270c1  inc     edi
0x1800270c3  cmp     edi, 5
0x1800270c6  jb      short loc_1800270A3
0x1800270c8  jnz     loc_18002715F
0x1800270ce  mov     rcx, [rsp+8F0h+lpString1]; pv
0x1800270d3  call    cs:__imp_CoTaskMemFree
0x1800270d9  mov     rcx, rbx
0x1800270dc  call    ReleaseObj
0x1800270e1  mov     rcx, [rsp+8F0h+pv]; pv
0x1800270e6  call    cs:__imp_CoTaskMemFree
0x1800270ec  inc     r15d
0x1800270ef  cmp     r15d, [rsp+8F0h+var_8C4]
0x1800270f4  jb      loc_180027018
0x1800270fa  xor     edx, edx; Val
0x1800270fc  lea     rcx, [rsp+8F0h+lParam]; void *
0x180027101  lea     r8d, [rdx+58h]; Size
0x180027105  call    memset_0
0x18002710a  mov     rcx, [rsi+218h]; hWnd
0x180027111  lea     r9, [rsp+8F0h+lParam]; lParam
0x180027116  mov     eax, 3
0x18002711b  xor     r8d, r8d; wParam
0x18002711e  mov     edx, 102Bh; Msg
0x180027123  mov     [rsp+8F0h+var_8A0], eax
0x180027127  mov     [rsp+8F0h+var_8A4], eax
0x18002712b  call    cs:__imp_SendMessageW
0x180027131  mov     eax, r13d
0x180027134  mov     rcx, [rbp+7F0h+var_30]
0x18002713b  xor     rcx, rsp; StackCookie
0x18002713e  call    __security_check_cookie
0x180027143  lea     r11, [rsp+8F0h+var_20]
0x18002714b  mov     rbx, [r11+38h]
0x18002714f  mov     rsi, [r11+40h]
0x180027153  mov     rsp, r11
0x180027156  pop     r15
0x180027158  pop     r14
0x18002715a  pop     r13
0x18002715c  pop     rdi
0x18002715d  pop     rbp
0x18002715e  retn
0x18002715f  mov     rcx, [rsp+8F0h+lpString1]; pv
0x180027164  call    cs:__imp_CoTaskMemFree
0x18002716a  mov     edi, [rsp+8F0h+var_8C8]
0x18002716e  mov     rax, [rsi]
0x180027171  shr     edi, 11h
0x180027174  and     edi, 1
0x180027177  cmp     dword ptr [rax+1Ch], 0
0x18002717b  jz      loc_18002720D
0x180027181  cmp     dword ptr [rax+20h], 0
0x180027185  jz      loc_18002720D
0x18002718b  mov     rax, [rbx]
0x18002718e  lea     rdx, [rbp+7F0h+Buf1]
0x180027192  mov     rcx, rbx
0x180027195  mov     rax, [rax+50h]
0x180027199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002719e  test    eax, eax
0x1800271a0  js      short loc_18002720D
0x1800271a2  mov     r8d, 10h; Size
0x1800271a8  lea     rdx, GUID_DEVCLASS_NETTRANS; Buf2
0x1800271af  lea     rcx, [rbp+7F0h+Buf1]; Buf1
0x1800271b3  call    memcmp_0
0x1800271b8  test    eax, eax
0x1800271ba  jnz     loc_1800270D9
0x1800271c0  mov     rax, [rbx]
0x1800271c3  lea     rdx, [rsp+8F0h+lpString1]
0x1800271c8  mov     rcx, rbx
0x1800271cb  mov     rax, [rax+30h]
0x1800271cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271d4  test    eax, eax
0x1800271d6  js      loc_1800270D9
0x1800271dc  mov     rcx, [rsp+8F0h+lpString1]; lpString1
0x1800271e1  call    DwProtocolFromComponentId
0x1800271e6  cmp     eax, 4
0x1800271e9  jz      short loc_1800271F6
0x1800271eb  mov     r14d, 1
0x1800271f1  cmp     eax, 8
0x1800271f4  jnz     short loc_1800271F9
0x1800271f6  xor     r14d, r14d
0x1800271f9  mov     rcx, [rsp+8F0h+lpString1]; pv
0x1800271fe  call    cs:__imp_CoTaskMemFree
0x180027204  test    r14d, r14d
0x180027207  jnz     loc_1800270D9
0x18002720d  mov     rax, [rsp+8F0h+pv]
0x180027212  lea     rdx, [rbp+7F0h+ClassGuid]
0x180027216  mov     [rsp+8F0h+var_898], rax
0x18002721b  xorps   xmm0, xmm0
0x18002721e  mov     dword ptr [rsp+8F0h+lParam], 7
0x180027226  mov     rcx, rbx
0x180027229  mov     rax, [rbx]
0x18002722c  mov     [rsp+8F0h+ImageIndex], 0
0x180027234  movups  xmmword ptr [rbp+7F0h+ClassGuid.Data1], xmm0
0x180027238  mov     rax, [rax+50h]
0x18002723c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027241  test    eax, eax
0x180027243  js      short loc_18002725B
0x180027245  lea     rcx, [rsi+5B0h]; ClassImageListData
0x18002724c  lea     r8, [rsp+8F0h+ImageIndex]; ImageIndex
0x180027251  lea     rdx, [rbp+7F0h+ClassGuid]; ClassGuid
0x180027255  call    cs:__imp_SetupDiGetClassImageIndex
0x18002725b  mov     eax, [rsp+8F0h+ImageIndex]
0x18002725f  lea     r9, [rsp+8F0h+lParam]; lParam
0x180027264  mov     rcx, [rsi+218h]; hWnd
0x18002726b  xor     r8d, r8d; wParam
0x18002726e  mov     edx, 104Dh; Msg
0x180027273  mov     [rsp+8F0h+var_88C], eax
0x180027277  mov     [rsp+8F0h+var_888], rbx
0x18002727c  call    cs:__imp_SendMessageW
0x180027282  mov     r14, rax
0x180027285  cmp     eax, 0FFFFFFFFh
0x180027288  jz      loc_1800270D9
0x18002728e  xor     r9d, r9d
0x180027291  xor     r8d, r8d
0x180027294  mov     rdx, rbx
0x180027297  mov     rcx, rsi
0x18002729a  call    NeQueryOrChangeComponentEnabled
0x18002729f  mov     rcx, [rsi+218h]; hWnd
0x1800272a6  mov     r8d, eax
0x1800272a9  mov     edx, r14d
0x1800272ac  call    ListView_SetCheck
0x1800272b1  mov     rdx, [rbx]
0x1800272b4  mov     rcx, rbx
0x1800272b7  mov     rax, [rdx+30h]
0x1800272bb  lea     rdx, [rsp+8F0h+lpString1]
0x1800272c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272c5  test    eax, eax
0x1800272c7  js      short loc_180027305
0x1800272c9  mov     rcx, [rsp+8F0h+lpString1]; String1
0x1800272ce  lea     rdx, aMsPsched; "ms_psched"
0x1800272d5  call    cs:__imp__wcsicmp
0x1800272db  test    eax, eax
0x1800272dd  jz      short loc_1800272F5
0x1800272df  mov     rcx, [rsp+8F0h+lpString1]; String1
0x1800272e4  lea     rdx, aMsNetmon; "ms_NetMon"
0x1800272eb  call    cs:__imp__wcsicmp
0x1800272f1  test    eax, eax
0x1800272f3  jnz     short loc_1800272FA
0x1800272f5  mov     edi, 1
0x1800272fa  mov     rcx, [rsp+8F0h+lpString1]; pv
0x1800272ff  call    cs:__imp_CoTaskMemFree
0x180027305  test    edi, edi
0x180027307  jz      loc_1800270E1
0x18002730d  mov     rcx, [rsi+218h]; hWnd
0x180027314  mov     edx, r14d
0x180027317  call    ListView_DisableCheck
0x18002731c  jmp     loc_1800270E1
```
