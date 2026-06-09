# I_ScPnPCreateNewListNode

- ea: `0x1800197a4`
- end: `0x180019db5`
- name: `I_ScPnPCreateNewListNode`
- size: `1553`
- prototype: `__int64 __fastcall(__int64, DEVINST, _WORD *, const wchar_t *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180004fa0`

## callees

- `0x180004600`
- `0x18000db90`
- `0x180016a66`
- `0x180018b58`
- `0x180018bb4`
- `0x1800197a4`
- `0x18001a2c8`
- `0x18001add8`
- `0x1800243f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019a2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019b2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019c0e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019a2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019b2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180019c0e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019af1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019b10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019af1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019b10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019d5b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x180019971`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x180019971`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_Size` at `0x1800199d8`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_ID_Size` at `0x1800199d8`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x180019a96`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x180019a96`
- `USER32!UnregisterDeviceNotification` at `0x180019d44`
- `USER32!UnregisterDeviceNotification` at `0x180019d44`

## string_xrefs

- `0x180019876`: `NULL != pwszReaderName`
- `0x1800198c1`: `NULL != pwszDevicePath`

## pseudocode

```c
__int64 __fastcall I_ScPnPCreateNewListNode(__int64 a1, DEVINST a2, _WORD *a3, const wchar_t *a4, _QWORD *a5)
{
  __int64 v6; // r15
  int v9; // r8d
  int v10; // r9d
  CONFIGRET Parent; // edi
  STRSAFE_LPSTR v12; // rcx
  int v13; // edx
  const char *v14; // rax
  _QWORD *v15; // r14
  __int64 v16; // rcx
  int v17; // edx
  __int64 v18; // rcx
  void *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  STRSAFE_LPSTR v22; // rcx
  int v23; // edx
  HDEVNOTIFY v24; // r15
  _QWORD *v25; // rax
  __int64 v26; // rcx
  STRSAFE_LPSTR v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  unsigned __int64 v30; // r8
  __int64 v31; // r8
  void *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rcx
  CONFIGRET v35; // eax
  ULONG pulLen; // [rsp+30h] [rbp-38h] BYREF
  DEVNODE pdnDevInst; // [rsp+34h] [rbp-34h] BYREF
  HDEVNOTIFY Handle; // [rsp+38h] [rbp-30h]
  void *v40; // [rsp+40h] [rbp-28h] BYREF
  LPVOID v41; // [rsp+48h] [rbp-20h]
  LPVOID lpMem; // [rsp+50h] [rbp-18h]

  v6 = -1;
  pulLen = 0;
  pdnDevInst = 0;
  Handle = 0;
  v40 = 0;
  if ( a1 == -1 )
  {
    WppTraceIndent(-1, 2);
    Parent = -2146435068;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      v13 = 21;
      v14 = "INVALID_HANDLE_VALUE != hFile";
LABEL_6:
      WPP_SF_ss(*((_QWORD *)v12 + 2), v13, v9, v10, (__int64)v14);
      goto LABEL_88;
    }
    goto LABEL_88;
  }
  if ( a3 )
  {
    if ( !a4 )
    {
      WppTraceIndent(a1, 2);
      Parent = -2146435068;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        v13 = 23;
        v14 = "NULL != pwszDevicePath";
        goto LABEL_6;
      }
      goto LABEL_88;
    }
    if ( !a5 )
    {
      WppTraceIndent(a1, 2);
      Parent = -2146435068;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        v13 = 24;
        v14 = "NULL != ppScPnPDeviceListNode";
        goto LABEL_6;
      }
      goto LABEL_88;
    }
    WppTraceIndent(a1, 0);
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 2) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids, WPP_pszIndent);
    }
    *a5 = 0;
    v15 = 0;
    Parent = CM_Get_Parent(&pdnDevInst, a2, 0);
    if ( Parent )
    {
      WppTraceIndent(v16, 2);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_88;
      }
      v17 = 26;
      goto LABEL_31;
    }
    Parent = CM_Get_Device_ID_Size(&pulLen, pdnDevInst, 0);
    if ( Parent )
    {
      WppTraceIndent(v18, 2);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_88;
      }
      v17 = 27;
LABEL_31:
      WPP_SF_sD(
        *((_QWORD *)v12 + 2),
        v17,
        (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
        WPP_pszIndent,
        Parent);
      goto LABEL_88;
    }
    Parent = 8;
    v19 = HeapAlloc(g_hHeap, 8u, 2LL * (pulLen + 1));
    lpMem = v19;
    if ( !v19 )
    {
      WppTraceIndent(v20, 2);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_88;
    }
    v41 = 0;
    Parent = CM_Get_Device_IDW(pdnDevInst, (PWSTR)v19, pulLen, 0);
    if ( Parent )
    {
      WppTraceIndent(v21, 2);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_48;
      }
      v23 = 29;
      goto LABEL_47;
    }
    v25 = HeapAlloc(g_hHeap, 8u, 0xF8u);
    v15 = v25;
    if ( v25 )
    {
      memset_0(v25, 0, 0xF8u);
      v30 = -1;
      do
        ++v30;
      while ( a3[v30] );
      if ( v30 < 0x60 )
      {
        memcpy_0(v15, a3, 2 * v30 + 2);
        v31 = -1;
        do
          ++v31;
        while ( a4[v31] );
        v32 = HeapAlloc(g_hHeap, 8u, 2 * v31 + 2);
        v41 = v32;
        if ( v32 )
        {
          do
            ++v6;
          while ( a4[v6] );
          Parent = StringCchCopyW((STRSAFE_LPWSTR)v32, v6 + 1, a4);
          if ( !Parent )
          {
            v35 = I_ScPnPRegisterDeviceHandleNotification(a1, &v40);
            v12 = 0;
            Parent = v35;
            if ( !v35 )
            {
              v15[26] = lpMem;
              v15[27] = v41;
              v15[28] = v40;
              v15[24] = a1;
              v24 = 0;
              *a5 = v15;
              v15 = 0;
LABEL_84:
              if ( v24 )
                UnregisterDeviceNotification(v24);
              if ( v15 )
                HeapFree(g_hHeap, 0, v15);
              goto LABEL_88;
            }
            WppTraceIndent(0, 2);
            if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[28] & 1) != 0
              && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
            {
              WPP_SF_sD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                34,
                (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
                WPP_pszIndent,
                Parent);
            }
            v24 = v40;
LABEL_49:
            HeapFree(g_hHeap, 0, lpMem);
            if ( v41 )
              HeapFree(g_hHeap, 0, v41);
            goto LABEL_84;
          }
          WppTraceIndent(v34, 2);
          v22 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            || (WPP_GLOBAL_Control[28] & 1) == 0
            || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
          {
LABEL_48:
            v24 = Handle;
            goto LABEL_49;
          }
          v23 = 33;
LABEL_47:
          WPP_SF_sD(
            *((_QWORD *)v22 + 2),
            v23,
            (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
            WPP_pszIndent,
            Parent);
          goto LABEL_48;
        }
        WppTraceIndent(v33, 2);
        Parent = 8;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[28] & 1) == 0
          || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
        {
          goto LABEL_48;
        }
        v28 = 32;
      }
      else
      {
        Parent = 24;
        WppTraceIndent(v29, 2);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[28] & 1) == 0
          || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
        {
          goto LABEL_48;
        }
        v28 = 31;
      }
    }
    else
    {
      WppTraceIndent(v26, 2);
      Parent = 8;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[28] & 1) == 0
        || (unsigned __int8)WPP_GLOBAL_Control[25] < 2u )
      {
        goto LABEL_48;
      }
      v28 = 30;
    }
    WPP_SF_s(*((_QWORD *)v27 + 2), v28, &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids, WPP_pszIndent);
    goto LABEL_48;
  }
  WppTraceIndent(a1, 2);
  Parent = -2146435068;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
  {
    v13 = 22;
    v14 = "NULL != pwszReaderName";
    goto LABEL_6;
  }
LABEL_88:
  WppTraceIndent(v12, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      35,
      (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
      WPP_pszIndent,
      Parent);
  }
  return Parent;
}

```

## disassembly

```asm
0x1800197a4  mov     [rsp-40h+arg_0], rcx
0x1800197a9  push    rbp
0x1800197aa  push    rbx
0x1800197ab  push    rsi
0x1800197ac  push    rdi
0x1800197ad  push    r12
0x1800197af  push    r13
0x1800197b1  push    r14
0x1800197b3  push    r15
0x1800197b5  mov     rbp, rsp
0x1800197b8  sub     rsp, 68h
0x1800197bc  mov     edi, edx
0x1800197be  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800197c2  xor     edx, edx
0x1800197c4  mov     r13, r9
0x1800197c7  mov     [rbp+pulLen], edx
0x1800197ca  mov     r12, r8
0x1800197cd  mov     [rbp+pdnDevInst], edx
0x1800197d0  mov     [rbp+Handle], rdx
0x1800197d4  mov     [rbp+var_28], rdx
0x1800197d8  cmp     rcx, r15
0x1800197db  jnz     short loc_180019833
0x1800197dd  lea     ebx, [rdx+2]
0x1800197e0  mov     edx, ebx
0x1800197e2  call    WppTraceIndent
0x1800197e7  mov     edi, 80100004h
0x1800197ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197f3  lea     rsi, WPP_GLOBAL_Control
0x1800197fa  cmp     rcx, rsi
0x1800197fd  jz      loc_180019D61
0x180019803  test    byte ptr [rcx+1Ch], 1
0x180019807  jz      loc_180019D61
0x18001980d  cmp     [rcx+19h], bl
0x180019810  jb      loc_180019D61
0x180019816  lea     edx, [rbx+13h]
0x180019819  lea     rax, aInvalidHandleV_0; "INVALID_HANDLE_VALUE != hFile"
0x180019820  mov     rcx, [rcx+10h]
0x180019824  mov     [rsp+68h+var_48], rax
0x180019829  call    WPP_SF_ss
0x18001982e  jmp     loc_180019D61
0x180019833  test    r12, r12
0x180019836  jnz     short loc_18001987F
0x180019838  lea     ebx, [r12+2]
0x18001983d  mov     edx, ebx
0x18001983f  call    WppTraceIndent
0x180019844  mov     edi, 80100004h
0x180019849  mov     rcx, cs:WPP_GLOBAL_Control
0x180019850  lea     rsi, WPP_GLOBAL_Control
0x180019857  cmp     rcx, rsi
0x18001985a  jz      loc_180019D61
0x180019860  test    byte ptr [rcx+1Ch], 1
0x180019864  jz      loc_180019D61
0x18001986a  cmp     [rcx+19h], bl
0x18001986d  jb      loc_180019D61
0x180019873  lea     edx, [rbx+14h]
0x180019876  lea     rax, aNullPwszreader; "NULL != pwszReaderName"
0x18001987d  jmp     short loc_180019820
0x18001987f  test    r13, r13
0x180019882  jnz     short loc_1800198CD
0x180019884  lea     ebx, [r13+2]
0x180019888  mov     edx, ebx
0x18001988a  call    WppTraceIndent
0x18001988f  mov     edi, 80100004h
0x180019894  mov     rcx, cs:WPP_GLOBAL_Control
0x18001989b  lea     rsi, WPP_GLOBAL_Control
0x1800198a2  cmp     rcx, rsi
0x1800198a5  jz      loc_180019D61
0x1800198ab  test    byte ptr [rcx+1Ch], 1
0x1800198af  jz      loc_180019D61
0x1800198b5  cmp     [rcx+19h], bl
0x1800198b8  jb      loc_180019D61
0x1800198be  lea     edx, [rbx+15h]
0x1800198c1  lea     rax, aNullPwszdevice; "NULL != pwszDevicePath"
0x1800198c8  jmp     loc_180019820
0x1800198cd  mov     r14, [rbp+arg_20]
0x1800198d1  test    r14, r14
0x1800198d4  jnz     short loc_18001991F
0x1800198d6  lea     ebx, [r14+2]
0x1800198da  mov     edx, ebx
0x1800198dc  call    WppTraceIndent
0x1800198e1  mov     edi, 80100004h
0x1800198e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198ed  lea     rsi, WPP_GLOBAL_Control
0x1800198f4  cmp     rcx, rsi
0x1800198f7  jz      loc_180019D61
0x1800198fd  test    byte ptr [rcx+1Ch], 1
0x180019901  jz      loc_180019D61
0x180019907  cmp     [rcx+19h], bl
0x18001990a  jb      loc_180019D61
0x180019910  lea     edx, [rbx+16h]
0x180019913  lea     rax, aNullPpscpnpdev; "NULL != ppScPnPDeviceListNode"
0x18001991a  jmp     loc_180019820
0x18001991f  call    WppTraceIndent
0x180019924  mov     rcx, cs:WPP_GLOBAL_Control
0x18001992b  lea     rsi, WPP_GLOBAL_Control
0x180019932  mov     ebx, 2
0x180019937  cmp     rcx, rsi
0x18001993a  jz      short loc_180019961
0x18001993c  test    [rcx+1Ch], bl
0x18001993f  jz      short loc_180019961
0x180019941  cmp     byte ptr [rcx+19h], 5
0x180019945  jb      short loc_180019961
0x180019947  mov     r9, cs:WPP_pszIndent
0x18001994e  lea     edx, [rbx+17h]
0x180019951  mov     rcx, [rcx+10h]
0x180019955  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18001995c  call    WPP_SF_s
0x180019961  xor     r8d, r8d; ulFlags
0x180019964  mov     qword ptr [r14], 0
0x18001996b  mov     edx, edi; dnDevInst
0x18001996d  lea     rcx, [rbp+pdnDevInst]; pdnDevInst
0x180019971  call    cs:__imp_CM_Get_Parent
0x180019977  xor     r14d, r14d
0x18001997a  mov     edi, eax
0x18001997c  test    eax, eax
0x18001997e  jz      short loc_1800199CE
0x180019980  mov     edx, ebx
0x180019982  call    WppTraceIndent
0x180019987  mov     rcx, cs:WPP_GLOBAL_Control
0x18001998e  cmp     rcx, rsi
0x180019991  jz      loc_180019D61
0x180019997  test    byte ptr [rcx+1Ch], 1
0x18001999b  jz      loc_180019D61
0x1800199a1  cmp     [rcx+19h], bl
0x1800199a4  jb      loc_180019D61
0x1800199aa  lea     edx, [r14+1Ah]
0x1800199ae  mov     r9, cs:WPP_pszIndent
0x1800199b5  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x1800199bc  mov     rcx, [rcx+10h]
0x1800199c0  mov     dword ptr [rsp+68h+var_48], edi
0x1800199c4  call    WPP_SF_sD
0x1800199c9  jmp     loc_180019D61
0x1800199ce  mov     edx, [rbp+pdnDevInst]; dnDevInst
0x1800199d1  lea     rcx, [rbp+pulLen]; pulLen
0x1800199d5  xor     r8d, r8d; ulFlags
0x1800199d8  call    cs:__imp_CM_Get_Device_ID_Size
0x1800199de  mov     edi, eax
0x1800199e0  test    eax, eax
0x1800199e2  jz      short loc_180019A15
0x1800199e4  mov     edx, ebx
0x1800199e6  call    WppTraceIndent
0x1800199eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800199f2  cmp     rcx, rsi
0x1800199f5  jz      loc_180019D61
0x1800199fb  test    byte ptr [rcx+1Ch], 1
0x1800199ff  jz      loc_180019D61
0x180019a05  cmp     [rcx+19h], bl
0x180019a08  jb      loc_180019D61
0x180019a0e  mov     edx, 1Bh
0x180019a13  jmp     short loc_1800199AE
0x180019a15  mov     r8d, [rbp+pulLen]
0x180019a19  mov     edi, 8
0x180019a1e  mov     rcx, cs:g_hHeap; hHeap
0x180019a25  inc     r8d
0x180019a28  add     r8, r8; dwBytes
0x180019a2b  mov     edx, edi; dwFlags
0x180019a2d  call    cs:__imp_HeapAlloc
0x180019a33  mov     [rbp+lpMem], rax
0x180019a37  test    rax, rax
0x180019a3a  jnz     short loc_180019A85
0x180019a3c  mov     edx, ebx
0x180019a3e  call    WppTraceIndent
0x180019a43  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a4a  cmp     rcx, rsi
0x180019a4d  jz      loc_180019D61
0x180019a53  test    byte ptr [rcx+1Ch], 1
0x180019a57  jz      loc_180019D61
0x180019a5d  cmp     [rcx+19h], bl
0x180019a60  jb      loc_180019D61
0x180019a66  mov     r9, cs:WPP_pszIndent
0x180019a6d  lea     edx, [rdi+14h]
0x180019a70  mov     rcx, [rcx+10h]
0x180019a74  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x180019a7b  call    WPP_SF_s
0x180019a80  jmp     loc_180019D61
0x180019a85  mov     r8d, [rbp+pulLen]; BufferLen
0x180019a89  xor     r9d, r9d; ulFlags
0x180019a8c  mov     ecx, [rbp+pdnDevInst]; dnDevInst
0x180019a8f  mov     rdx, rax; Buffer
0x180019a92  mov     [rbp+var_20], r14
0x180019a96  call    cs:__imp_CM_Get_Device_IDW
0x180019a9c  mov     edi, eax
0x180019a9e  test    eax, eax
0x180019aa0  jz      short loc_180019B1B
0x180019aa2  mov     edx, ebx
0x180019aa4  call    WppTraceIndent
0x180019aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ab0  cmp     rcx, rsi
0x180019ab3  jz      short loc_180019AE0
0x180019ab5  test    byte ptr [rcx+1Ch], 1
0x180019ab9  jz      short loc_180019AE0
0x180019abb  cmp     [rcx+19h], bl
0x180019abe  jb      short loc_180019AE0
0x180019ac0  mov     edx, 1Dh
0x180019ac5  mov     r9, cs:WPP_pszIndent
0x180019acc  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x180019ad3  mov     rcx, [rcx+10h]
0x180019ad7  mov     dword ptr [rsp+68h+var_48], edi
0x180019adb  call    WPP_SF_sD
0x180019ae0  mov     r15, [rbp+Handle]
0x180019ae4  mov     r8, [rbp+lpMem]; lpMem
0x180019ae8  xor     edx, edx; dwFlags
0x180019aea  mov     rcx, cs:g_hHeap; hHeap
0x180019af1  call    cs:__imp_HeapFree
0x180019af7  mov     rax, [rbp+var_20]
0x180019afb  test    rax, rax
0x180019afe  jz      loc_180019D3C
0x180019b04  mov     rcx, cs:g_hHeap; hHeap
0x180019b0b  mov     r8, rax; lpMem
0x180019b0e  xor     edx, edx; dwFlags
0x180019b10  call    cs:__imp_HeapFree
0x180019b16  jmp     loc_180019D3C
0x180019b1b  mov     rcx, cs:g_hHeap; hHeap
0x180019b22  mov     edx, 8; dwFlags
0x180019b27  mov     r8d, 0F8h; dwBytes
0x180019b2d  call    cs:__imp_HeapAlloc
0x180019b33  xor     edi, edi
0x180019b35  mov     r14, rax
0x180019b38  test    rax, rax
0x180019b3b  jnz     short loc_180019B7E
0x180019b3d  mov     edx, ebx
0x180019b3f  call    WppTraceIndent
0x180019b44  lea     edi, [r14+8]
0x180019b48  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b4f  cmp     rcx, rsi
0x180019b52  jz      short loc_180019AE0
0x180019b54  test    byte ptr [rcx+1Ch], 1
0x180019b58  jz      short loc_180019AE0
0x180019b5a  cmp     [rcx+19h], bl
0x180019b5d  jb      short loc_180019AE0
0x180019b5f  lea     edx, [rdi+16h]
0x180019b62  mov     r9, cs:WPP_pszIndent
0x180019b69  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x180019b70  mov     rcx, [rcx+10h]
0x180019b74  call    WPP_SF_s
0x180019b79  jmp     loc_180019AE0
0x180019b7e  xor     edx, edx; Val
0x180019b80  mov     r8d, 0F8h; Size
0x180019b86  mov     rcx, r14; void *
0x180019b89  call    memset_0
0x180019b8e  mov     r8, r15
0x180019b91  inc     r8
0x180019b94  cmp     [r12+r8*2], di
0x180019b99  jnz     short loc_180019B91
0x180019b9b  cmp     r8, 60h ; '`'
0x180019b9f  jb      short loc_180019BD5
0x180019ba1  mov     edx, ebx
0x180019ba3  mov     edi, 18h
0x180019ba8  call    WppTraceIndent
0x180019bad  mov     rcx, cs:WPP_GLOBAL_Control
0x180019bb4  cmp     rcx, rsi
0x180019bb7  jz      loc_180019AE0
0x180019bbd  test    byte ptr [rcx+1Ch], 1
0x180019bc1  jz      loc_180019AE0
0x180019bc7  cmp     [rcx+19h], bl
0x180019bca  jb      loc_180019AE0
0x180019bd0  lea     edx, [rdi+7]
0x180019bd3  jmp     short loc_180019B62
0x180019bd5  lea     r8, ds:2[r8*2]; Size
0x180019bdd  mov     rdx, r12; Src
0x180019be0  mov     rcx, r14; void *
0x180019be3  call    memcpy_0
0x180019be8  mov     r8, r15
0x180019beb  inc     r8
0x180019bee  cmp     [r13+r8*2+0], di
0x180019bf4  jnz     short loc_180019BEB
0x180019bf6  mov     rcx, cs:g_hHeap; hHeap
0x180019bfd  lea     r8, ds:2[r8*2]; dwBytes
0x180019c05  mov     r12d, 8
0x180019c0b  mov     edx, r12d; dwFlags
0x180019c0e  call    cs:__imp_HeapAlloc
0x180019c14  mov     [rbp+var_20], rax
0x180019c18  test    rax, rax
0x180019c1b  jnz     short loc_180019C54
0x180019c1d  mov     edx, ebx
0x180019c1f  call    WppTraceIndent
0x180019c24  mov     edi, r12d
0x180019c27  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c2e  cmp     rcx, rsi
0x180019c31  jz      loc_180019AE0
0x180019c37  test    byte ptr [rcx+1Ch], 1
0x180019c3b  jz      loc_180019AE0
0x180019c41  cmp     [rcx+19h], bl
0x180019c44  jb      loc_180019AE0
0x180019c4a  lea     edx, [r12+18h]
0x180019c4f  jmp     loc_180019B62
0x180019c54  inc     r15
0x180019c57  cmp     [r13+r15*2+0], di
0x180019c5d  jnz     short loc_180019C54
0x180019c5f  lea     rdx, [r15+1]; cchDest
0x180019c63  mov     r8, r13; pszSrc
0x180019c66  mov     rcx, rax; pszDest
0x180019c69  call    StringCchCopyW
0x180019c6e  mov     edi, eax
0x180019c70  test    eax, eax
0x180019c72  jz      short loc_180019CA8
0x180019c74  mov     edx, ebx
0x180019c76  call    WppTraceIndent
0x180019c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c82  cmp     rcx, rsi
  ... truncated ...
```
