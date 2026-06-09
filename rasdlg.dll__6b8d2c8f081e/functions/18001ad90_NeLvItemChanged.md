# NeLvItemChanged

- ea: `0x18001ad90`
- end: `0x18001b042`
- name: `NeLvItemChanged`
- size: `690`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a9e0`
- `0x18001b134`

## callees

- `0x18001ab80`
- `0x18001ad90`
- `0x18002797c`
- `0x18004658c`
- `0x18004d0c6`
- `0x18004d110`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001afaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b01f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001afaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b01f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001aef5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001af2d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001af66`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001af90`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001aef5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001af2d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001af66`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001af90`
- `USER32!GetActiveWindow` at `0x18001ae68`
- `USER32!GetActiveWindow` at `0x18001ae68`
- `USER32!SendMessageW` at `0x18001afff`
- `USER32!SendMessageW` at `0x18001afff`
- `USER32!SetWindowTextW` at `0x18001b015`
- `USER32!SetWindowTextW` at `0x18001b015`
- `USER32!EnableWindow` at `0x18001afcd`
- `USER32!EnableWindow` at `0x18001afdc`
- `USER32!EnableWindow` at `0x18001afcd`
- `USER32!EnableWindow` at `0x18001afdc`

## pseudocode

```c
void __fastcall NeLvItemChanged(__int64 a1)
{
  HWND v2; // rcx
  int v3; // ebx
  BOOL v4; // r12d
  int v5; // r15d
  LPARAM v6; // rdi
  __int64 v7; // r14
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rax
  __int64 (__fastcall *v11)(__int64, HWND, __int64, _QWORD); // rbx
  HWND ActiveWindow; // rax
  BOOL v13; // eax
  BOOL v14; // r13d
  __int64 v15; // rcx
  PCNZWCH lpString2; // [rsp+30h] [rbp-38h] BYREF
  __int64 v17; // [rsp+38h] [rbp-30h] BYREF
  LPCWSTR lpString; // [rsp+40h] [rbp-28h] BYREF
  __int128 Buf1; // [rsp+48h] [rbp-20h] BYREF

  lpString = 0;
  v2 = *(HWND *)(a1 + 536);
  v3 = 0;
  v4 = 0;
  LODWORD(lpString2) = 0;
  v5 = 0;
  v6 = 1;
  v7 = PComponentFromCurSel(v2);
  if ( v7 )
  {
    NeEnsureNetshellLoaded(a1);
    if ( *(_QWORD *)(a1 + 1480) )
    {
      if ( (v8 = *(_QWORD *)v7,
            LODWORD(v17) = 0,
            v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(v8 + 56))(v7, &v17),
            v9 >= 0)
        && (v17 & 0x20) != 0
        || (v4 = 1, v9 >= 0) )
      {
        if ( (v17 & 0x80u) != 0LL )
        {
          v10 = *(_QWORD *)v7;
          Buf1 = 0;
          if ( (*(int (__fastcall **)(__int64, __int128 *))(v10 + 80))(v7, &Buf1) >= 0 )
          {
            if ( !memcmp_0(&Buf1, &GUID_DEVCLASS_NETTRANS, 0x10u) )
            {
              v3 = 1;
            }
            else
            {
              v11 = *(__int64 (__fastcall **)(__int64, HWND, __int64, _QWORD))(*(_QWORD *)v7 + 112LL);
              ActiveWindow = GetActiveWindow();
              v3 = v11(v7, ActiveWindow, 1, 0) == 0;
            }
          }
        }
      }
    }
    v13 = ListView_GetCheck(*(HWND *)(a1 + 536), (int)lpString2);
    lpString2 = 0;
    v14 = v13;
    v3 = v13 ? v3 : 0;
    v15 = *(_QWORD *)v7;
    v17 = *(_QWORD *)(*(_QWORD *)a1 + 872LL);
    if ( (*(int (__fastcall **)(__int64, PCNZWCH *))(v15 + 48))(v7, &lpString2) >= 0 )
    {
      if ( CompareStringW(0x7Fu, 1u, L"ms_msclient", -1, lpString2, -1) == 2 )
      {
        *(_DWORD *)(v17 + 260) = v14;
      }
      else if ( CompareStringW(0x7Fu, 1u, L"ms_server", -1, lpString2, -1) == 2 )
      {
        *(_DWORD *)(v17 + 256) = v14;
      }
      if ( CompareStringW(0x7Fu, 1u, L"ms_tcpip", -1, lpString2, -1) != 2
        && CompareStringW(0x7Fu, 1u, L"ms_tcpip6", -1, lpString2, -1) != 2
        && *(_DWORD *)(a1 + 1452) )
      {
        v5 = 1;
      }
      CoTaskMemFree((LPVOID)lpString2);
    }
    (*(void (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v7 + 40LL))(v7, &lpString);
  }
  EnableWindow(*(HWND *)(a1 + 552), v4);
  EnableWindow(*(HWND *)(a1 + 560), v3);
  if ( !v3 || !v5 )
    v6 = 0;
  SendMessageW(*(HWND *)(a1 + 560), 0x160Cu, 0, v6);
  if ( lpString )
  {
    SetWindowTextW(*(HWND *)(a1 + 568), lpString);
    CoTaskMemFree((LPVOID)lpString);
  }
}

```

## disassembly

```asm
0x18001ad90  push    rbp
0x18001ad92  push    rbx
0x18001ad93  push    rsi
0x18001ad94  push    rdi
0x18001ad95  push    r12
0x18001ad97  push    r13
0x18001ad99  push    r14
0x18001ad9b  push    r15
0x18001ad9d  mov     rbp, rsp
0x18001ada0  sub     rsp, 68h
0x18001ada4  mov     rax, cs:__security_cookie
0x18001adab  xor     rax, rsp
0x18001adae  mov     [rbp+var_10], rax
0x18001adb2  mov     rsi, rcx
0x18001adb5  mov     [rbp+lpString], 0
0x18001adbd  mov     rcx, [rcx+218h]; hWnd
0x18001adc4  lea     rdx, [rbp+var_38]
0x18001adc8  xor     ebx, ebx
0x18001adca  xor     r12d, r12d
0x18001adcd  mov     dword ptr [rbp+var_38], ebx
0x18001add0  xor     r15d, r15d
0x18001add3  call    PComponentFromCurSel
0x18001add8  lea     edi, [rbx+1]
0x18001addb  mov     r14, rax
0x18001adde  test    rax, rax
0x18001ade1  jz      loc_18001AFC3
0x18001ade7  mov     rcx, rsi
0x18001adea  call    NeEnsureNetshellLoaded
0x18001adef  cmp     [rsi+5C8h], rbx
0x18001adf6  jz      loc_18001AE8D
0x18001adfc  mov     rcx, [r14]
0x18001adff  lea     rdx, [rbp+var_30]
0x18001ae03  mov     dword ptr [rbp+var_30], ebx
0x18001ae06  mov     rax, [rcx+38h]
0x18001ae0a  mov     rcx, r14
0x18001ae0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae12  test    eax, eax
0x18001ae14  js      short loc_18001AE1C
0x18001ae16  test    byte ptr [rbp+var_30], 20h
0x18001ae1a  jnz     short loc_18001AE23
0x18001ae1c  mov     r12d, edi
0x18001ae1f  test    eax, eax
0x18001ae21  js      short loc_18001AE8D
0x18001ae23  test    byte ptr [rbp+var_30], 80h
0x18001ae27  jz      short loc_18001AE8D
0x18001ae29  mov     rax, [r14]
0x18001ae2c  lea     rdx, [rbp+Buf1]
0x18001ae30  xorps   xmm0, xmm0
0x18001ae33  mov     rcx, r14
0x18001ae36  movups  [rbp+Buf1], xmm0
0x18001ae3a  mov     rax, [rax+50h]
0x18001ae3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae43  test    eax, eax
0x18001ae45  js      short loc_18001AE8D
0x18001ae47  mov     r8d, 10h; Size
0x18001ae4d  lea     rdx, GUID_DEVCLASS_NETTRANS; Buf2
0x18001ae54  lea     rcx, [rbp+Buf1]; Buf1
0x18001ae58  call    memcmp_0
0x18001ae5d  test    eax, eax
0x18001ae5f  jz      short loc_18001AE8B
0x18001ae61  mov     rax, [r14]
0x18001ae64  mov     rbx, [rax+70h]
0x18001ae68  call    cs:__imp_GetActiveWindow
0x18001ae6e  xor     r9d, r9d
0x18001ae71  mov     r8d, edi
0x18001ae74  mov     rdx, rax
0x18001ae77  mov     rcx, r14
0x18001ae7a  mov     rax, rbx
0x18001ae7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae82  xor     ebx, ebx
0x18001ae84  test    eax, eax
0x18001ae86  setz    bl
0x18001ae89  jmp     short loc_18001AE8D
0x18001ae8b  mov     ebx, edi
0x18001ae8d  mov     edx, dword ptr [rbp+var_38]
0x18001ae90  mov     rcx, [rsi+218h]
0x18001ae97  call    ListView_GetCheck
0x18001ae9c  mov     ecx, eax
0x18001ae9e  mov     [rbp+var_38], r15
0x18001aea2  neg     ecx
0x18001aea4  mov     r13d, eax
0x18001aea7  mov     rcx, [rsi]
0x18001aeaa  sbb     edx, edx
0x18001aeac  and     ebx, edx
0x18001aeae  lea     rdx, [rbp+var_38]
0x18001aeb2  mov     rax, [rcx+368h]
0x18001aeb9  mov     rcx, [r14]
0x18001aebc  mov     [rbp+var_30], rax
0x18001aec0  mov     rax, [rcx+30h]
0x18001aec4  mov     rcx, r14
0x18001aec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aecc  test    eax, eax
0x18001aece  js      loc_18001AFB0
0x18001aed4  mov     rax, [rbp+var_38]
0x18001aed8  lea     r8, String1; "ms_msclient"
0x18001aedf  or      ecx, 0FFFFFFFFh
0x18001aee2  mov     edx, edi; dwCmpFlags
0x18001aee4  mov     [rsp+68h+cchCount2], ecx; cchCount2
0x18001aee8  mov     r9d, ecx; cchCount1
0x18001aeeb  mov     ecx, 7Fh; Locale
0x18001aef0  mov     [rsp+68h+lpString2], rax; lpString2
0x18001aef5  call    cs:__imp_CompareStringW
0x18001aefb  cmp     eax, 2
0x18001aefe  jnz     short loc_18001AF0D
0x18001af00  mov     rax, [rbp+var_30]
0x18001af04  mov     [rax+104h], r13d
0x18001af0b  jmp     short loc_18001AF43
0x18001af0d  mov     rax, [rbp+var_38]
0x18001af11  lea     r8, aMsServer; "ms_server"
0x18001af18  or      r9d, 0FFFFFFFFh; cchCount1
0x18001af1c  mov     edx, edi; dwCmpFlags
0x18001af1e  mov     [rsp+68h+cchCount2], r9d; cchCount2
0x18001af23  mov     ecx, 7Fh; Locale
0x18001af28  mov     [rsp+68h+lpString2], rax; lpString2
0x18001af2d  call    cs:__imp_CompareStringW
0x18001af33  cmp     eax, 2
0x18001af36  jnz     short loc_18001AF43
0x18001af38  mov     rax, [rbp+var_30]
0x18001af3c  mov     [rax+100h], r13d
0x18001af43  mov     rax, [rbp+var_38]
0x18001af47  lea     r8, aMsTcpip; "ms_tcpip"
0x18001af4e  or      r13d, 0FFFFFFFFh
0x18001af52  mov     edx, edi; dwCmpFlags
0x18001af54  mov     [rsp+68h+cchCount2], r13d; cchCount2
0x18001af59  mov     r9d, r13d; cchCount1
0x18001af5c  mov     ecx, 7Fh; Locale
0x18001af61  mov     [rsp+68h+lpString2], rax; lpString2
0x18001af66  call    cs:__imp_CompareStringW
0x18001af6c  cmp     eax, 2
0x18001af6f  jz      short loc_18001AFA6
0x18001af71  mov     rax, [rbp+var_38]
0x18001af75  lea     r8, aMsTcpip6; "ms_tcpip6"
0x18001af7c  mov     [rsp+68h+cchCount2], r13d; cchCount2
0x18001af81  mov     r9d, r13d; cchCount1
0x18001af84  mov     edx, edi; dwCmpFlags
0x18001af86  mov     [rsp+68h+lpString2], rax; lpString2
0x18001af8b  mov     ecx, 7Fh; Locale
0x18001af90  call    cs:__imp_CompareStringW
0x18001af96  cmp     eax, 2
0x18001af99  jz      short loc_18001AFA6
0x18001af9b  cmp     [rsi+5ACh], r15d
0x18001afa2  cmovnz  r15d, edi
0x18001afa6  mov     rcx, [rbp+var_38]; pv
0x18001afaa  call    cs:__imp_CoTaskMemFree
0x18001afb0  mov     rax, [r14]
0x18001afb3  lea     rdx, [rbp+lpString]
0x18001afb7  mov     rcx, r14
0x18001afba  mov     rax, [rax+28h]
0x18001afbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afc3  mov     rcx, [rsi+228h]; hWnd
0x18001afca  mov     edx, r12d; bEnable
0x18001afcd  call    cs:__imp_EnableWindow
0x18001afd3  mov     rcx, [rsi+230h]; hWnd
0x18001afda  mov     edx, ebx; bEnable
0x18001afdc  call    cs:__imp_EnableWindow
0x18001afe2  test    ebx, ebx
0x18001afe4  jz      short loc_18001AFEB
0x18001afe6  test    r15d, r15d
0x18001afe9  jnz     short loc_18001AFED
0x18001afeb  xor     edi, edi
0x18001afed  mov     rcx, [rsi+230h]; hWnd
0x18001aff4  mov     r9, rdi; lParam
0x18001aff7  xor     r8d, r8d; wParam
0x18001affa  mov     edx, 160Ch; Msg
0x18001afff  call    cs:__imp_SendMessageW
0x18001b005  mov     rdx, [rbp+lpString]; lpString
0x18001b009  test    rdx, rdx
0x18001b00c  jz      short loc_18001B025
0x18001b00e  mov     rcx, [rsi+238h]; hWnd
0x18001b015  call    cs:__imp_SetWindowTextW
0x18001b01b  mov     rcx, [rbp+lpString]; pv
0x18001b01f  call    cs:__imp_CoTaskMemFree
0x18001b025  mov     rcx, [rbp+var_10]
0x18001b029  xor     rcx, rsp; StackCookie
0x18001b02c  call    __security_check_cookie
0x18001b031  add     rsp, 68h
0x18001b035  pop     r15
0x18001b037  pop     r14
0x18001b039  pop     r13
0x18001b03b  pop     r12
0x18001b03d  pop     rdi
0x18001b03e  pop     rsi
0x18001b03f  pop     rbx
0x18001b040  pop     rbp
0x18001b041  retn
```
