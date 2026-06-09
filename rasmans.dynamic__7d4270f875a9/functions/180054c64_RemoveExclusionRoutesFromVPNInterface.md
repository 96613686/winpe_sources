# RemoveExclusionRoutesFromVPNInterface

- ea: `0x180054c64`
- end: `0x18005516b`
- name: `RemoveExclusionRoutesFromVPNInterface`
- size: `1287`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180055174`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18003372c`
- `0x180053080`
- `0x180054c64`
- `0x180060fa8`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800550fa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800550fa`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180054f38`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180054f38`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x180054e88`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x180055097`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x180054e88`
- `IPHLPAPI!DeleteIpForwardEntry2` at `0x180055097`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x180054f18`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x180054f80`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x180054f18`
- `ext-ms-win-ras-rasapi32-l1-1-0!RasGetEntryPropertiesW` at `0x180054f80`

## pseudocode

```c
__int64 __fastcall RemoveExclusionRoutesFromVPNInterface(__int64 a1)
{
  __int64 v2; // r12
  __int64 v3; // rbx
  __int64 v4; // rsi
  __int64 v5; // r14
  struct _LIST_ENTRY *v6; // rcx
  unsigned int v7; // r15d
  __int64 v8; // rsi
  unsigned int *v9; // rbx
  __int64 v10; // r9
  NTSTATUS v11; // eax
  struct tagRASENTRYW *v12; // rbx
  __int64 v13; // rsi
  struct _LIST_ENTRY *v14; // rcx
  NTSTATUS v15; // eax
  DWORD v17; // [rsp+30h] [rbp-D0h] BYREF
  struct tagRASENTRYW *v18; // [rsp+38h] [rbp-C8h]
  MIB_IPFORWARD_ROW2 Row; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v20[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR WideCharStr[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 42, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
  }
  memset_0(&Row, 0, sizeof(Row));
  v2 = 0;
  v17 = 0;
  StrncpyAtoW(WideCharStr, (LPCCH)(a1 + 184));
  StrncpyAtoW(v20, (LPCCH)(a1 + 445));
  if ( *(char *)(a1 + 112) >= 0 || (v3 = *(_QWORD *)(a1 + 912)) == 0 )
  {
LABEL_36:
    if ( RasGetEntryPropertiesW(WideCharStr, v20, 0, &v17, 0, 0) != 603 )
      goto LABEL_62;
    v18 = (struct tagRASENTRYW *)GlobalAlloc(0x40u, v17);
    v12 = v18;
    if ( !v18 )
      goto LABEL_62;
    v18->dwSize = v17;
    if ( RasGetEntryPropertiesW(WideCharStr, v20, v12, &v17, 0, 0)
      || (v12->dwfOptions2 & 0x80000000) == 0
      || !*(_QWORD *)(a1 + 944)
      || !*(_DWORD *)(a1 + 952) )
    {
LABEL_61:
      GlobalFree(v12);
      goto LABEL_62;
    }
    v13 = 0;
    v14 = WPP_GLOBAL_Control;
    while ( 1 )
    {
      if ( *(_DWORD *)(v2 + 36 * v13 + 4) == 2 || *(_DWORD *)(v2 + 36 * v13 + 4) == 23 )
      {
        CreateRouteEntry(&Row);
        Row.InterfaceIndex = *(_DWORD *)(v2 + 36 * v13 + 32);
        v15 = DeleteIpForwardEntry2(&Row);
        if ( v15 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_59;
          }
          WPP_SF_qD(
            WPP_GLOBAL_Control[1].Flink,
            49,
            WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids,
            *(unsigned int *)(v2 + 36 * v13 + 32),
            v15);
        }
      }
      else
      {
        if ( v14 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(v14[1].Blink) & 0x2000) == 0
          || BYTE1(v14[1].Blink) < 4u )
        {
          goto LABEL_59;
        }
        WPP_SF_d(
          v14[1].Flink,
          48,
          WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids,
          *(unsigned int *)(*(_QWORD *)(a1 + 944) + 36 * v13 + 4));
      }
      v14 = WPP_GLOBAL_Control;
LABEL_59:
      v13 = (unsigned int)(v13 + 1);
      if ( (unsigned int)v13 >= *(_DWORD *)(a1 + 952) )
      {
        v12 = v18;
        goto LABEL_61;
      }
    }
  }
  v4 = *(unsigned int *)(v3 + 88);
  v5 = *(unsigned int *)(v3 + 44);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 43, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, (unsigned int)v5);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (_DWORD)v5 )
  {
    v2 = v3 + v4;
    if ( !(v3 + v4)
      || (unsigned __int64)(36 * v5) > 0xFFFFFFFF
      || *(_DWORD *)(*(_QWORD *)(a1 + 912) + 48LL) < (unsigned int)(36 * v5) )
    {
      if ( v6 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return 0;
      if ( (HIDWORD(v6[1].Blink) & 0x2000) == 0 || BYTE1(v6[1].Blink) < 5u )
        goto LABEL_63;
      WPP_SF_d(v6[1].Flink, 45, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, 111);
      goto LABEL_62;
    }
    v7 = 0;
    v8 = 0;
    while ( 1 )
    {
      v9 = (unsigned int *)(v2 + 36 * v8);
      if ( !v9[7] || !v9[8] )
        goto LABEL_35;
      v10 = v9[1];
      if ( (_DWORD)v10 == 2 || (_DWORD)v10 == 23 )
      {
        CreateRouteEntry(&Row);
        Row.InterfaceIndex = v9[8];
        v11 = DeleteIpForwardEntry2(&Row);
        if ( v11 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_35;
          }
          WPP_SF_qD(WPP_GLOBAL_Control[1].Flink, 47, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v9[8], v11);
        }
      }
      else
      {
        if ( v6 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(v6[1].Blink) & 0x2000) == 0
          || BYTE1(v6[1].Blink) < 4u )
        {
          goto LABEL_35;
        }
        WPP_SF_d(v6[1].Flink, 46, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, v10);
      }
      v6 = WPP_GLOBAL_Control;
LABEL_35:
      ++v7;
      ++v8;
      if ( v7 >= (unsigned int)v5 )
        goto LABEL_36;
    }
  }
  if ( v6 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return 0;
  if ( (HIDWORD(v6[1].Blink) & 0x2000) != 0 && BYTE1(v6[1].Blink) >= 5u )
  {
    WPP_SF_(v6[1].Flink, 44, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids);
LABEL_62:
    v6 = WPP_GLOBAL_Control;
  }
LABEL_63:
  if ( v6 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v6[1].Blink) & 0x2000) != 0
    && BYTE1(v6[1].Blink) >= 6u )
  {
    WPP_SF_d(v6[1].Flink, 50, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180054c64  mov     [rsp-8+arg_8], rbx
0x180054c69  mov     [rsp-8+arg_10], rsi
0x180054c6e  push    rbp
0x180054c6f  push    rdi
0x180054c70  push    r12
0x180054c72  push    r14
0x180054c74  push    r15
0x180054c76  lea     rbp, [rsp-3E0h]
0x180054c7e  sub     rsp, 4E0h
0x180054c85  mov     rax, cs:__security_cookie
0x180054c8c  xor     rax, rsp
0x180054c8f  mov     [rbp+400h+var_30], rax
0x180054c96  mov     rdi, rcx
0x180054c99  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ca0  lea     rax, WPP_GLOBAL_Control
0x180054ca7  mov     r15d, 2000h
0x180054cad  cmp     rcx, rax
0x180054cb0  jz      short loc_180054CD3
0x180054cb2  test    [rcx+1Ch], r15d
0x180054cb6  jz      short loc_180054CD3
0x180054cb8  cmp     byte ptr [rcx+19h], 6
0x180054cbc  jb      short loc_180054CD3
0x180054cbe  mov     rcx, [rcx+10h]
0x180054cc2  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180054cc9  mov     edx, 2Ah ; '*'
0x180054cce  call    WPP_SF_
0x180054cd3  xor     edx, edx; Val
0x180054cd5  lea     rcx, [rsp+500h+Row]; void *
0x180054cda  lea     r8d, [rdx+68h]; Size
0x180054cde  call    memset_0
0x180054ce3  xor     r12d, r12d
0x180054ce6  lea     rdx, [rdi+0B8h]; lpMultiByteStr
0x180054ced  mov     r8d, 105h
0x180054cf3  mov     [rsp+500h+var_4D0], r12d
0x180054cf8  lea     rcx, [rbp+400h+WideCharStr]; lpWideCharStr
0x180054cff  call    StrncpyAtoW
0x180054d04  lea     rdx, [rdi+1BDh]; lpMultiByteStr
0x180054d0b  mov     r8d, 101h
0x180054d11  lea     rcx, [rbp+400h+var_450]; lpWideCharStr
0x180054d15  call    StrncpyAtoW
0x180054d1a  test    byte ptr [rdi+70h], 80h
0x180054d1e  jz      loc_180054EF3
0x180054d24  mov     rbx, [rdi+390h]
0x180054d2b  test    rbx, rbx
0x180054d2e  jz      loc_180054EF3
0x180054d34  mov     esi, [rbx+58h]
0x180054d37  mov     r14d, [rbx+2Ch]
0x180054d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d42  lea     r8, WPP_GLOBAL_Control
0x180054d49  cmp     rcx, r8
0x180054d4c  jz      short loc_180054D80
0x180054d4e  test    [rcx+1Ch], r15d
0x180054d52  jz      short loc_180054D80
0x180054d54  cmp     byte ptr [rcx+19h], 5
0x180054d58  jb      short loc_180054D80
0x180054d5a  mov     rcx, [rcx+10h]
0x180054d5e  lea     edx, [r12+2Bh]
0x180054d63  mov     r9d, r14d
0x180054d66  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180054d6d  call    WPP_SF_d
0x180054d72  mov     rcx, cs:WPP_GLOBAL_Control
0x180054d79  lea     r8, WPP_GLOBAL_Control
0x180054d80  test    r14d, r14d
0x180054d83  jnz     short loc_180054DBB
0x180054d85  cmp     rcx, r8
0x180054d88  jz      loc_18005513D
0x180054d8e  test    [rcx+1Ch], r15d
0x180054d92  jz      loc_180055114
0x180054d98  cmp     byte ptr [rcx+19h], 5
0x180054d9c  jb      loc_180055114
0x180054da2  mov     rcx, [rcx+10h]
0x180054da6  lea     edx, [r14+2Ch]
0x180054daa  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180054db1  call    WPP_SF_
0x180054db6  jmp     loc_180055106
0x180054dbb  mov     r12, rsi
0x180054dbe  add     r12, rbx
0x180054dc1  jz      loc_18005502F
0x180054dc7  lea     rdx, [r14+r14*8]
0x180054dcb  mov     eax, 0FFFFFFFFh
0x180054dd0  shl     rdx, 2
0x180054dd4  cmp     rdx, rax
0x180054dd7  ja      loc_18005502F
0x180054ddd  mov     rax, [rdi+390h]
0x180054de4  cmp     [rax+30h], edx
0x180054de7  jb      loc_18005502F
0x180054ded  xor     r15d, r15d
0x180054df0  test    r14d, r14d
0x180054df3  jz      loc_180054EED
0x180054df9  xor     esi, esi
0x180054dfb  lea     rax, [rsi+rsi*8]
0x180054dff  lea     rbx, [r12+rax*4]
0x180054e03  cmp     dword ptr [rbx+1Ch], 0
0x180054e07  jz      loc_180054EDE
0x180054e0d  cmp     dword ptr [rbx+20h], 0
0x180054e11  jz      loc_180054EDE
0x180054e17  mov     r9d, [rbx+4]
0x180054e1b  cmp     r9d, 2
0x180054e1f  jz      short loc_180054E65
0x180054e21  cmp     r9d, 17h
0x180054e25  jz      short loc_180054E65
0x180054e27  lea     rax, WPP_GLOBAL_Control
0x180054e2e  cmp     rcx, rax
0x180054e31  jz      loc_180054EDE
0x180054e37  test    dword ptr [rcx+1Ch], 2000h
0x180054e3e  jz      loc_180054EDE
0x180054e44  cmp     byte ptr [rcx+19h], 4
0x180054e48  jb      loc_180054EDE
0x180054e4e  mov     rcx, [rcx+10h]
0x180054e52  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180054e59  mov     edx, 2Eh ; '.'
0x180054e5e  call    WPP_SF_d
0x180054e63  jmp     short loc_180054ED7
0x180054e65  mov     r9d, [rdi+354h]
0x180054e6c  lea     rcx, [rsp+500h+Row]; void *
0x180054e71  xor     r8d, r8d
0x180054e74  mov     rdx, rbx
0x180054e77  call    CreateRouteEntry
0x180054e7c  mov     eax, [rbx+20h]
0x180054e7f  lea     rcx, [rsp+500h+Row]; Row
0x180054e84  mov     [rsp+500h+Row.InterfaceIndex], eax
0x180054e88  call    cs:__imp_DeleteIpForwardEntry2
0x180054e8f  nop     dword ptr [rax+rax+00h]
0x180054e94  test    eax, eax
0x180054e96  jz      short loc_180054ED7
0x180054e98  mov     rcx, cs:WPP_GLOBAL_Control
0x180054e9f  lea     rdx, WPP_GLOBAL_Control
0x180054ea6  cmp     rcx, rdx
0x180054ea9  jz      short loc_180054EDE
0x180054eab  test    dword ptr [rcx+1Ch], 2000h
0x180054eb2  jz      short loc_180054EDE
0x180054eb4  cmp     byte ptr [rcx+19h], 2
0x180054eb8  jb      short loc_180054EDE
0x180054eba  mov     r9d, [rbx+20h]
0x180054ebe  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180054ec5  mov     rcx, [rcx+10h]
0x180054ec9  mov     edx, 2Fh ; '/'
0x180054ece  mov     dword ptr [rsp+500h+var_4E0], eax
0x180054ed2  call    WPP_SF_qD
0x180054ed7  mov     rcx, cs:WPP_GLOBAL_Control
0x180054ede  inc     r15d
0x180054ee1  inc     rsi
0x180054ee4  cmp     r15d, r14d
0x180054ee7  jb      loc_180054DFB
0x180054eed  mov     r15d, 2000h
0x180054ef3  mov     [rsp+500h+var_4D8], 0; LPDWORD
0x180054efc  lea     r9, [rsp+500h+var_4D0]; LPDWORD
0x180054f01  xor     r8d, r8d; struct tagRASENTRYW *
0x180054f04  mov     [rsp+500h+var_4E0], 0; LPBYTE
0x180054f0d  lea     rdx, [rbp+400h+var_450]; LPCWSTR
0x180054f11  lea     rcx, [rbp+400h+WideCharStr]; LPCWSTR
0x180054f18  call    cs:__imp_RasGetEntryPropertiesW
0x180054f1f  nop     dword ptr [rax+rax+00h]
0x180054f24  cmp     eax, 25Bh
0x180054f29  jnz     loc_180055106
0x180054f2f  mov     edx, [rsp+500h+var_4D0]; dwBytes
0x180054f33  mov     ecx, 40h ; '@'; uFlags
0x180054f38  call    cs:__imp_GlobalAlloc
0x180054f3f  nop     dword ptr [rax+rax+00h]
0x180054f44  mov     [rsp+500h+var_4C8], rax
0x180054f49  mov     rbx, rax
0x180054f4c  test    rax, rax
0x180054f4f  jz      loc_180055106
0x180054f55  mov     eax, [rsp+500h+var_4D0]
0x180054f59  lea     r9, [rsp+500h+var_4D0]; LPDWORD
0x180054f5e  mov     [rsp+500h+var_4D8], 0; LPDWORD
0x180054f67  lea     rdx, [rbp+400h+var_450]; LPCWSTR
0x180054f6b  mov     r8, rbx; struct tagRASENTRYW *
0x180054f6e  mov     [rbx], eax
0x180054f70  lea     rcx, [rbp+400h+WideCharStr]; LPCWSTR
0x180054f77  mov     [rsp+500h+var_4E0], 0; LPBYTE
0x180054f80  call    cs:__imp_RasGetEntryPropertiesW
0x180054f87  nop     dword ptr [rax+rax+00h]
0x180054f8c  test    eax, eax
0x180054f8e  jnz     loc_1800550F7
0x180054f94  cmp     [rbx+0FD0h], eax
0x180054f9a  jge     loc_1800550F7
0x180054fa0  cmp     qword ptr [rdi+3B0h], 0
0x180054fa8  jz      loc_1800550F7
0x180054fae  mov     eax, [rdi+3B8h]
0x180054fb4  test    eax, eax
0x180054fb6  jz      loc_1800550F7
0x180054fbc  xor     esi, esi
0x180054fbe  test    eax, eax
0x180054fc0  jz      loc_1800550F7
0x180054fc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180054fcd  lea     rbx, WPP_GLOBAL_Control
0x180054fd4  lea     r14, [rsi+rsi*8]
0x180054fd8  cmp     dword ptr [r12+r14*4+4], 2
0x180054fde  jz      loc_18005506A
0x180054fe4  cmp     dword ptr [r12+r14*4+4], 17h
0x180054fea  jz      short loc_18005506A
0x180054fec  cmp     rcx, rbx
0x180054fef  jz      loc_1800550E4
0x180054ff5  test    [rcx+1Ch], r15d
0x180054ff9  jz      loc_1800550E4
0x180054fff  cmp     byte ptr [rcx+19h], 4
0x180055003  jb      loc_1800550E4
0x180055009  mov     r9, [rdi+3B0h]
0x180055010  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180055017  mov     rcx, [rcx+10h]
0x18005501b  mov     edx, 30h ; '0'
0x180055020  mov     r9d, [r9+r14*4+4]
0x180055025  call    WPP_SF_d
0x18005502a  jmp     loc_1800550DD
0x18005502f  cmp     rcx, r8
0x180055032  jz      loc_18005513D
0x180055038  test    [rcx+1Ch], r15d
0x18005503c  jz      loc_180055114
0x180055042  cmp     byte ptr [rcx+19h], 5
0x180055046  jb      loc_180055114
0x18005504c  mov     rcx, [rcx+10h]
0x180055050  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180055057  mov     edx, 2Dh ; '-'
0x18005505c  lea     r9d, [rdx+42h]
0x180055060  call    WPP_SF_d
0x180055065  jmp     loc_180055106
0x18005506a  mov     rax, [rdi+3B0h]
0x180055071  lea     rcx, [rsp+500h+Row]; void *
0x180055076  mov     r9d, [rdi+354h]
0x18005507d  xor     r8d, r8d
0x180055080  lea     rdx, [rax+r14*4]
0x180055084  call    CreateRouteEntry
0x180055089  mov     eax, [r12+r14*4+20h]
0x18005508e  lea     rcx, [rsp+500h+Row]; Row
0x180055093  mov     [rsp+500h+Row.InterfaceIndex], eax
0x180055097  call    cs:__imp_DeleteIpForwardEntry2
0x18005509e  nop     dword ptr [rax+rax+00h]
0x1800550a3  test    eax, eax
0x1800550a5  jz      short loc_1800550DD
0x1800550a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800550ae  cmp     rcx, rbx
0x1800550b1  jz      short loc_1800550E4
0x1800550b3  test    [rcx+1Ch], r15d
0x1800550b7  jz      short loc_1800550E4
0x1800550b9  cmp     byte ptr [rcx+19h], 2
0x1800550bd  jb      short loc_1800550E4
0x1800550bf  mov     r9d, [r12+r14*4+20h]
0x1800550c4  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x1800550cb  mov     rcx, [rcx+10h]
0x1800550cf  mov     edx, 31h ; '1'
0x1800550d4  mov     dword ptr [rsp+500h+var_4E0], eax
0x1800550d8  call    WPP_SF_qD
0x1800550dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800550e4  inc     esi
0x1800550e6  cmp     esi, [rdi+3B8h]
0x1800550ec  jb      loc_180054FD4
0x1800550f2  mov     rbx, [rsp+500h+var_4C8]
0x1800550f7  mov     rcx, rbx; hMem
0x1800550fa  call    cs:__imp_GlobalFree
0x180055101  nop     dword ptr [rax+rax+00h]
0x180055106  mov     rcx, cs:WPP_GLOBAL_Control
0x18005510d  lea     r8, WPP_GLOBAL_Control
0x180055114  cmp     rcx, r8
0x180055117  jz      short loc_18005513D
0x180055119  test    [rcx+1Ch], r15d
0x18005511d  jz      short loc_18005513D
0x18005511f  cmp     byte ptr [rcx+19h], 6
0x180055123  jb      short loc_18005513D
0x180055125  mov     rcx, [rcx+10h]
0x180055129  lea     r8, WPP_a053c0c40cd83cc9614d85683b3f656e_Traceguids
0x180055130  mov     edx, 32h ; '2'
0x180055135  xor     r9d, r9d
0x180055138  call    WPP_SF_d
0x18005513d  xor     eax, eax
0x18005513f  mov     rcx, [rbp+400h+var_30]
0x180055146  xor     rcx, rsp; StackCookie
0x180055149  call    __security_check_cookie
0x18005514e  lea     r11, [rsp+500h+var_20]
0x180055156  mov     rbx, [r11+38h]
0x18005515a  mov     rsi, [r11+40h]
0x18005515e  mov     rsp, r11
0x180055161  pop     r15
0x180055163  pop     r14
0x180055165  pop     r12
0x180055167  pop     rdi
0x180055168  pop     rbp
0x180055169  retn
```
