# ScPnPHandleQueryRemoval

- ea: `0x18000dd30`
- end: `0x18000e105`
- name: `ScPnPHandleQueryRemoval`
- size: `981`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callees

- `0x180004600`
- `0x18000dd30`
- `0x180015398`
- `0x180018b58`
- `0x180018bb4`
- `0x180018d78`
- `0x18001a2c8`
- `0x18001add8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e095`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e095`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e0ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e0ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000de46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000de46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000deea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e000`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000deea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e000`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000debf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e071`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000debf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e071`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000dfed`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000dfed`
- `USER32!UnregisterDeviceNotification` at `0x18000ded8`
- `USER32!UnregisterDeviceNotification` at `0x18000df64`
- `USER32!UnregisterDeviceNotification` at `0x18000ded8`
- `USER32!UnregisterDeviceNotification` at `0x18000df64`

## pseudocode

```c
void __fastcall ScPnPHandleQueryRemoval(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, PTP_WORK Work)
{
  STRSAFE_LPSTR v4; // rcx
  int v5; // r8d
  int v6; // r9d
  char v7; // bl
  STRSAFE_LPSTR v8; // rcx
  int v9; // r15d
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rbp
  __int64 i; // rdi
  HDEVNOTIFY *v14; // rsi
  __int64 v15; // rdx
  void *v16; // rcx
  __int64 v17; // rcx
  char LastError; // al
  int v19; // r9d
  STRSAFE_LPSTR v20; // rcx
  int v21; // edx
  __int64 v22; // rcx
  __int64 v23; // rcx
  HANDLE FileW; // rax
  int v25; // eax
  __int64 v26; // rcx
  void *v27; // rcx

  WppTraceIndent(Instance, 0);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids, WPP_pszIndent);
  }
  if ( !Context )
  {
    WppTraceIndent(v4, 2);
    v7 = 4;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, v5, v6, (__int64)"NULL != pPnpHandler");
    }
    goto LABEL_56;
  }
  if ( !Context[2] )
  {
    v9 = 0;
    WppTraceIndent(v4, 2);
    v7 = 4;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
    {
      WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, v10, v11, (__int64)"NULL != pPnpHandler->hDevNotify");
    }
    goto LABEL_54;
  }
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pScPnPState + 544));
  v9 = 1;
  v12 = 0;
  for ( i = *((_QWORD *)g_pScPnPState + 74); ; i = *(_QWORD *)(i + 240) )
  {
    if ( !i )
      goto LABEL_54;
    v14 = (HDEVNOTIFY *)(i + 224);
    v15 = *(_QWORD *)(i + 224);
    if ( Context[2] == v15 )
      break;
    v12 = i;
  }
  if ( *((_DWORD *)Context + 2) == 32769 )
  {
    v27 = *(void **)(i + 192);
    if ( v27 != (void *)-1LL )
    {
      CloseHandle(v27);
      *(_QWORD *)(i + 192) = -1;
    }
    goto LABEL_54;
  }
  if ( *((_DWORD *)Context + 2) != 32770 )
  {
    if ( *((_DWORD *)Context + 2) != 32771 )
    {
      if ( *((_DWORD *)Context + 2) != 32772 )
      {
        v7 = 120;
        goto LABEL_54;
      }
      v16 = *(void **)(i + 192);
      if ( v16 != (void *)-1LL )
      {
        CloseHandle(v16);
        *(_QWORD *)(i + 192) = -1;
      }
    }
    if ( *v14 )
    {
      if ( !UnregisterDeviceNotification(*v14) )
      {
        WppTraceIndent(v17, 2);
        LastError = GetLastError();
        v7 = LastError;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          v21 = 88;
LABEL_43:
          WPP_SF_sd(
            *((_QWORD *)v20 + 2),
            v21,
            (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
            v19,
            LastError);
          goto LABEL_54;
        }
        goto LABEL_54;
      }
      *v14 = 0;
    }
    v22 = *(_QWORD *)(i + 240);
    if ( v12 )
      *(_QWORD *)(v12 + 240) = v22;
    else
      *((_QWORD *)g_pScPnPState + 74) = v22;
    I_ScPnPFreeDeviceListNode(i, 0);
    goto LABEL_54;
  }
  if ( !v15 )
  {
LABEL_45:
    FileW = CreateFileW(*(LPCWSTR *)(i + 216), 0xC0000000, 3u, 0, 3u, 0, 0);
    *(_QWORD *)(i + 192) = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v7 = GetLastError();
    }
    else
    {
      v25 = I_ScPnPRegisterDeviceHandleNotification(FileW, i + 224);
      v7 = v25;
      if ( v25 )
      {
        WppTraceIndent(v26, 2);
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            87,
            (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
            WPP_pszIndent,
            v7);
        }
      }
    }
    goto LABEL_54;
  }
  if ( UnregisterDeviceNotification(*(HDEVNOTIFY *)(i + 224)) )
  {
    *v14 = 0;
    goto LABEL_45;
  }
  WppTraceIndent(v23, 2);
  LastError = GetLastError();
  v7 = LastError;
  v20 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
  {
    v21 = 86;
    goto LABEL_43;
  }
LABEL_54:
  HeapFree(g_hHeap, 0, Context);
  if ( v9 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)g_pScPnPState + 544));
LABEL_56:
  WppTraceIndent(v8, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      89,
      (unsigned int)&WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids,
      WPP_pszIndent,
      v7);
  }
}

```

## disassembly

```asm
0x18000dd30  push    rbx
0x18000dd32  push    rbp
0x18000dd33  push    rsi
0x18000dd34  push    rdi
0x18000dd35  push    r13
0x18000dd37  push    r14
0x18000dd39  push    r15
0x18000dd3b  sub     rsp, 40h
0x18000dd3f  mov     r14, rdx
0x18000dd42  xor     edx, edx
0x18000dd44  call    WppTraceIndent
0x18000dd49  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd50  lea     rdi, WPP_GLOBAL_Control
0x18000dd57  mov     r13d, 2
0x18000dd5d  cmp     rcx, rdi
0x18000dd60  jz      short loc_18000DD89
0x18000dd62  test    [rcx+1Ch], r13b
0x18000dd66  jz      short loc_18000DD89
0x18000dd68  cmp     byte ptr [rcx+19h], 5
0x18000dd6c  jb      short loc_18000DD89
0x18000dd6e  mov     r9, cs:WPP_pszIndent
0x18000dd75  lea     edx, [r13+51h]
0x18000dd79  mov     rcx, [rcx+10h]
0x18000dd7d  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000dd84  call    WPP_SF_s
0x18000dd89  test    r14, r14
0x18000dd8c  jnz     short loc_18000DDDD
0x18000dd8e  mov     edx, r13d
0x18000dd91  call    WppTraceIndent
0x18000dd96  mov     ebx, 80100004h
0x18000dd9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dda2  cmp     rcx, rdi
0x18000dda5  jz      loc_18000E0B4
0x18000ddab  test    byte ptr [rcx+1Ch], 1
0x18000ddaf  jz      loc_18000E0B4
0x18000ddb5  cmp     [rcx+19h], r13b
0x18000ddb9  jb      loc_18000E0B4
0x18000ddbf  mov     rcx, [rcx+10h]
0x18000ddc3  lea     rax, aNullPpnphandle; "NULL != pPnpHandler"
0x18000ddca  lea     edx, [r14+54h]
0x18000ddce  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x18000ddd3  call    WPP_SF_ss
0x18000ddd8  jmp     loc_18000E0B4
0x18000dddd  cmp     qword ptr [r14+10h], 0
0x18000dde2  jnz     short loc_18000DE36
0x18000dde4  xor     r15d, r15d
0x18000dde7  mov     edx, r13d
0x18000ddea  call    WppTraceIndent
0x18000ddef  mov     ebx, 80100004h
0x18000ddf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddfb  cmp     rcx, rdi
0x18000ddfe  jz      loc_18000E089
0x18000de04  test    byte ptr [rcx+1Ch], 1
0x18000de08  jz      loc_18000E089
0x18000de0e  cmp     [rcx+19h], r13b
0x18000de12  jb      loc_18000E089
0x18000de18  mov     rcx, [rcx+10h]
0x18000de1c  lea     rax, aNullPpnphandle_0; "NULL != pPnpHandler->hDevNotify"
0x18000de23  lea     edx, [r15+55h]
0x18000de27  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x18000de2c  call    WPP_SF_ss
0x18000de31  jmp     loc_18000E089
0x18000de36  mov     rcx, cs:g_pScPnPState
0x18000de3d  xor     ebx, ebx
0x18000de3f  add     rcx, 220h; lpCriticalSection
0x18000de46  call    cs:__imp_EnterCriticalSection
0x18000de4c  mov     rax, cs:g_pScPnPState
0x18000de53  lea     r15d, [rbx+1]
0x18000de57  xor     ebp, ebp
0x18000de59  mov     rdi, [rax+250h]
0x18000de60  test    rdi, rdi
0x18000de63  jz      loc_18000E082
0x18000de69  lea     rsi, [rdi+0E0h]
0x18000de70  mov     rdx, [rsi]
0x18000de73  cmp     [r14+10h], rdx
0x18000de77  jz      short loc_18000DE85
0x18000de79  mov     rbp, rdi
0x18000de7c  mov     rdi, [rdi+0F0h]
0x18000de83  jmp     short loc_18000DE60
0x18000de85  mov     ecx, [r14+8]
0x18000de89  sub     ecx, 8001h
0x18000de8f  jz      loc_18000E064
0x18000de95  sub     ecx, r15d
0x18000de98  jz      loc_18000DF5C
0x18000de9e  sub     ecx, r15d
0x18000dea1  jz      short loc_18000DED0
0x18000dea3  cmp     ecx, r15d
0x18000dea6  jz      short loc_18000DEB2
0x18000dea8  mov     ebx, 78h ; 'x'
0x18000dead  jmp     loc_18000E082
0x18000deb2  mov     rcx, [rdi+0C0h]; hObject
0x18000deb9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000debd  jz      short loc_18000DED0
0x18000debf  call    cs:__imp_CloseHandle
0x18000dec5  mov     qword ptr [rdi+0C0h], 0FFFFFFFFFFFFFFFFh
0x18000ded0  mov     rcx, [rsi]; Handle
0x18000ded3  test    rcx, rcx
0x18000ded6  jz      short loc_18000DF2A
0x18000ded8  call    cs:__imp_UnregisterDeviceNotification
0x18000dede  test    eax, eax
0x18000dee0  jnz     short loc_18000DF27
0x18000dee2  mov     edx, r13d
0x18000dee5  call    WppTraceIndent
0x18000deea  call    cs:__imp_GetLastError
0x18000def0  mov     ebx, eax
0x18000def2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000def9  lea     rdi, WPP_GLOBAL_Control
0x18000df00  cmp     rcx, rdi
0x18000df03  jz      loc_18000E089
0x18000df09  test    [rcx+1Ch], r15b
0x18000df0d  jz      loc_18000E089
0x18000df13  cmp     [rcx+19h], r13b
0x18000df17  jb      loc_18000E089
0x18000df1d  mov     edx, 58h ; 'X'
0x18000df22  jmp     loc_18000DFAE
0x18000df27  mov     [rsi], rbx
0x18000df2a  mov     rcx, [rdi+0F0h]
0x18000df31  test    rbp, rbp
0x18000df34  jnz     short loc_18000DF46
0x18000df36  mov     rax, cs:g_pScPnPState
0x18000df3d  mov     [rax+250h], rcx
0x18000df44  jmp     short loc_18000DF4D
0x18000df46  mov     [rbp+0F0h], rcx
0x18000df4d  xor     edx, edx
0x18000df4f  mov     rcx, rdi
0x18000df52  call    I_ScPnPFreeDeviceListNode
0x18000df57  jmp     loc_18000E082
0x18000df5c  test    rdx, rdx
0x18000df5f  jz      short loc_18000DFCA
0x18000df61  mov     rcx, rdx; Handle
0x18000df64  call    cs:__imp_UnregisterDeviceNotification
0x18000df6a  test    eax, eax
0x18000df6c  jnz     short loc_18000DFC7
0x18000df6e  mov     edx, r13d
0x18000df71  call    WppTraceIndent
0x18000df76  call    cs:__imp_GetLastError
0x18000df7c  mov     ebx, eax
0x18000df7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df85  lea     rdi, WPP_GLOBAL_Control
0x18000df8c  cmp     rcx, rdi
0x18000df8f  jz      loc_18000E089
0x18000df95  test    [rcx+1Ch], r15b
0x18000df99  jz      loc_18000E089
0x18000df9f  cmp     [rcx+19h], r13b
0x18000dfa3  jb      loc_18000E089
0x18000dfa9  mov     edx, 56h ; 'V'
0x18000dfae  mov     rcx, [rcx+10h]
0x18000dfb2  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000dfb9  mov     [rsp+78h+dwCreationDisposition], eax
0x18000dfbd  call    WPP_SF_sd
0x18000dfc2  jmp     loc_18000E089
0x18000dfc7  mov     [rsi], rbx
0x18000dfca  mov     rcx, [rdi+0D8h]; lpFileName
0x18000dfd1  mov     r8d, 3; dwShareMode
0x18000dfd7  mov     [rsp+78h+hTemplateFile], rbx; hTemplateFile
0x18000dfdc  xor     r9d, r9d; lpSecurityAttributes
0x18000dfdf  mov     [rsp+78h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18000dfe3  mov     edx, 0C0000000h; dwDesiredAccess
0x18000dfe8  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000dfed  call    cs:__imp_CreateFileW
0x18000dff3  mov     [rdi+0C0h], rax
0x18000dffa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000dffe  jnz     short loc_18000E00A
0x18000e000  call    cs:__imp_GetLastError
0x18000e006  mov     ebx, eax
0x18000e008  jmp     short loc_18000E082
0x18000e00a  mov     rdx, rsi
0x18000e00d  mov     rcx, rax
0x18000e010  call    I_ScPnPRegisterDeviceHandleNotification
0x18000e015  mov     ebx, eax
0x18000e017  test    eax, eax
0x18000e019  jz      short loc_18000E082
0x18000e01b  mov     edx, r13d
0x18000e01e  call    WppTraceIndent
0x18000e023  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e02a  lea     rdi, WPP_GLOBAL_Control
0x18000e031  cmp     rcx, rdi
0x18000e034  jz      short loc_18000E089
0x18000e036  test    [rcx+1Ch], r15b
0x18000e03a  jz      short loc_18000E089
0x18000e03c  cmp     [rcx+19h], r13b
0x18000e040  jb      short loc_18000E089
0x18000e042  mov     r9, cs:WPP_pszIndent
0x18000e049  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000e050  mov     rcx, [rcx+10h]
0x18000e054  mov     edx, 57h ; 'W'
0x18000e059  mov     [rsp+78h+dwCreationDisposition], ebx
0x18000e05d  call    WPP_SF_sD
0x18000e062  jmp     short loc_18000E089
0x18000e064  mov     rcx, [rdi+0C0h]; hObject
0x18000e06b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e06f  jz      short loc_18000E082
0x18000e071  call    cs:__imp_CloseHandle
0x18000e077  mov     qword ptr [rdi+0C0h], 0FFFFFFFFFFFFFFFFh
0x18000e082  lea     rdi, WPP_GLOBAL_Control
0x18000e089  mov     rcx, cs:g_hHeap; hHeap
0x18000e090  mov     r8, r14; lpMem
0x18000e093  xor     edx, edx; dwFlags
0x18000e095  call    cs:__imp_HeapFree
0x18000e09b  test    r15d, r15d
0x18000e09e  jz      short loc_18000E0B4
0x18000e0a0  mov     rcx, cs:g_pScPnPState
0x18000e0a7  add     rcx, 220h; lpCriticalSection
0x18000e0ae  call    cs:__imp_LeaveCriticalSection
0x18000e0b4  mov     edx, 1
0x18000e0b9  call    WppTraceIndent
0x18000e0be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0c5  cmp     rcx, rdi
0x18000e0c8  jz      short loc_18000E0F6
0x18000e0ca  test    [rcx+1Ch], r13b
0x18000e0ce  jz      short loc_18000E0F6
0x18000e0d0  cmp     byte ptr [rcx+19h], 5
0x18000e0d4  jb      short loc_18000E0F6
0x18000e0d6  mov     r9, cs:WPP_pszIndent
0x18000e0dd  lea     r8, WPP_d405ffd8f480304dfdc9bc268e092644_Traceguids
0x18000e0e4  mov     rcx, [rcx+10h]
0x18000e0e8  mov     edx, 59h ; 'Y'
0x18000e0ed  mov     [rsp+78h+dwCreationDisposition], ebx
0x18000e0f1  call    WPP_SF_sD
0x18000e0f6  add     rsp, 40h
0x18000e0fa  pop     r15
0x18000e0fc  pop     r14
0x18000e0fe  pop     r13
0x18000e100  pop     rdi
0x18000e101  pop     rsi
0x18000e102  pop     rbp
0x18000e103  pop     rbx
0x18000e104  retn
```
