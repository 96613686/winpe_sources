# PeApply

- ea: `0x18001bae4`
- end: `0x18001c080`
- name: `PeApply`
- size: `1436`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016d50`

## callees

- `0x180012b78`
- `0x180015a78`
- `0x180015f78`
- `0x180017678`
- `0x180018088`
- `0x18001b388`
- `0x18001bae4`
- `0x18001c088`
- `0x18002adf0`
- `0x18002ae0c`
- `0x18003b7f0`
- `0x18003bea0`
- `0x180041c9c`
- `0x180048364`
- `0x180048f0c`
- `0x18004e010`

## import_xrefs

- `RASAPI32!DwSetCustomAuthData` at `0x18001bf2a`
- `RASAPI32!DwSetCustomAuthData` at `0x18001bf2a`
- `RASAPI32!IsValidPbportForVPNStrategy` at `0x18001bd3b`
- `RASAPI32!IsValidPbportForVPNStrategy` at `0x18001bd3b`
- `RASAPI32!CopyToPbport` at `0x18001bd51`
- `RASAPI32!CopyToPbport` at `0x18001bd51`
- `USER32!GetDlgItemInt` at `0x18001be56`
- `USER32!GetDlgItemInt` at `0x18001be56`
- `USER32!SendMessageW` at `0x18001bbc1`
- `USER32!SendMessageW` at `0x18001bbe9`
- `USER32!SendMessageW` at `0x18001bc18`
- `USER32!SendMessageW` at `0x18001bcee`
- `USER32!SendMessageW` at `0x18001bdd5`
- `USER32!SendMessageW` at `0x18001bdf3`
- `USER32!SendMessageW` at `0x18001be18`
- `USER32!SendMessageW` at `0x18001be2d`
- `USER32!SendMessageW` at `0x18001be82`
- `USER32!SendMessageW` at `0x18001be97`
- `USER32!SendMessageW` at `0x18001beb3`
- `USER32!SendMessageW` at `0x18001bbc1`
- `USER32!SendMessageW` at `0x18001bbe9`
- `USER32!SendMessageW` at `0x18001bc18`
- `USER32!SendMessageW` at `0x18001bcee`
- `USER32!SendMessageW` at `0x18001bdd5`
- `USER32!SendMessageW` at `0x18001bdf3`
- `USER32!SendMessageW` at `0x18001be18`
- `USER32!SendMessageW` at `0x18001be2d`
- `USER32!SendMessageW` at `0x18001be82`
- `USER32!SendMessageW` at `0x18001be97`
- `USER32!SendMessageW` at `0x18001beb3`
- `USER32!IsWindowEnabled` at `0x18001bbfe`
- `USER32!IsWindowEnabled` at `0x18001bbfe`
- `USER32!SetFocus` at `0x18001bbcb`
- `USER32!SetFocus` at `0x18001bbcb`
- `rtutils!TracePrintfExA` at `0x18001bb0f`
- `rtutils!TracePrintfExA` at `0x18001bb0f`

## pseudocode

```c
__int64 __fastcall PeApply(HWND hWnd)
{
  LPCWSTR **v2; // rax
  __int64 *v3; // rdi
  LPCWSTR v5; // rsi
  int v6; // edx
  HWND v7; // rcx
  __int64 v8; // r14
  __int64 PhoneNodeFromPhoneList; // rax
  __int64 v10; // rbp
  __int64 v11; // rbx
  HWND v12; // rcx
  void *v13; // rcx
  __int64 i; // rbx
  __int64 v15; // rbp
  __int64 v16; // r14
  __int64 v17; // rax
  __int64 v18; // rbp
  __int64 v19; // rbx
  HWND v20; // rcx
  HWND v21; // rcx
  HWND v22; // rcx
  int v23; // eax
  UINT DlgItemInt; // eax
  int v25; // eax
  __int64 *v26; // rbp
  int v27; // r14d
  __int64 j; // rbp
  __int64 v29; // rbx
  __int64 v30; // rcx
  unsigned int v31; // edx
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rax
  __int64 v36; // rcx
  BOOL Translated; // [rsp+88h] [rbp+10h] BYREF

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "PeApply");
  v2 = (LPCWSTR **)AiContext(hWnd);
  v3 = (__int64 *)v2;
  if ( !v2 )
    return 1003;
  v5 = (*v2)[109];
  if ( (*((_DWORD *)v5 + 6) == 2 || *((_DWORD *)v5 + 6) == 5) && !*((_DWORD *)v5 + 32) )
    ClearCachedCredentials(**v2, (*v2)[1]);
  switch ( *((_DWORD *)v5 + 6) )
  {
    case 1:
      v6 = GeSaveLvDeviceChecks(v3);
      if ( *(_DWORD *)(*v3 + 324) )
      {
        if ( !v6 )
        {
          MsgDlgUtil(hWnd, 0x5F9u, 0, g_hinstDll, 0x169u);
          SendMessageW((HWND)v3[1], 0x465u, 0, v3[3]);
          SetFocus((HWND)v3[7]);
          return 0;
        }
        *((_DWORD *)v5 + 10) = SendMessageW((HWND)v3[11], 0xF0u, 0, 0);
        v7 = (HWND)v3[23];
        if ( v7 )
          *((_DWORD *)v5 + 33) = !IsWindowEnabled(v7) || !(unsigned int)SendMessageW((HWND)v3[23], 0xF0u, 0, 0);
      }
      else
      {
        *((_DWORD *)v5 + 10) = 1;
      }
      GeGetPhoneFields(v3, v3[146]);
      if ( v3[177] )
      {
        DtlSwapLists(*(_QWORD *)(*(_QWORD *)(*v3 + 128) + 120LL));
        *(_DWORD *)(*(_QWORD *)(*v3 + 128) + 180LL) = 1;
      }
      break;
    case 2:
      v8 = *(_QWORD *)(**((_QWORD **)v5 + 4) + 16LL);
      PhoneNodeFromPhoneList = FirstPhoneNodeFromPhoneList(*(_QWORD **)(v8 + 168));
      v10 = PhoneNodeFromPhoneList;
      if ( !PhoneNodeFromPhoneList )
        return 0;
      v11 = *(_QWORD *)(PhoneNodeFromPhoneList + 16);
      Free0(*(void **)(v11 + 16));
      *(_QWORD *)(v11 + 16) = GetText((HWND)v3[24]);
      FirstPhoneNodeToPhoneList(*(_QWORD *)(v8 + 168), v10);
      v12 = (HWND)v3[25];
      if ( v12 && !(unsigned int)SendMessageW(v12, 0xF0u, 0, 0) )
      {
        Free0(*((void **)v5 + 7));
        v13 = (void *)*((_QWORD *)v5 + 8);
        *((_QWORD *)v5 + 7) = 0;
        Free0(v13);
        *((_QWORD *)v5 + 8) = 0;
      }
      for ( i = **(_QWORD **)(*v3 + 880); i; i = *(_QWORD *)(i + 8) )
      {
        v15 = *(_QWORD *)(i + 16);
        if ( *(_DWORD *)(v15 + 40) == 11
          && (unsigned int)IsValidPbportForVPNStrategy(*(_QWORD *)(i + 16), *((unsigned int *)v5 + 42)) )
        {
          CopyToPbport(v8, v15);
          goto LABEL_36;
        }
      }
      break;
    case 5:
      v16 = *(_QWORD *)(**((_QWORD **)v5 + 4) + 16LL);
      v17 = FirstPhoneNodeFromPhoneList(*(_QWORD **)(v16 + 168));
      v18 = v17;
      if ( !v17 )
        return 0;
      v19 = *(_QWORD *)(v17 + 16);
      Free0(*(void **)(v19 + 16));
      *(_QWORD *)(v19 + 16) = GetText((HWND)v3[27]);
      FirstPhoneNodeToPhoneList(*(_QWORD *)(v16 + 168), v18);
      break;
  }
LABEL_36:
  if ( v3[4] )
  {
    v20 = (HWND)v3[30];
    Translated = 0;
    if ( v20 )
      *((_DWORD *)v5 + 28) = SendMessageW(v20, 0xF0u, 0, 0);
    v21 = (HWND)v3[33];
    if ( v21 )
      *((_DWORD *)v5 + 31) = SendMessageW(v21, 0xF0u, 0, 0);
    v22 = (HWND)v3[37];
    if ( v22 )
    {
      v23 = SendMessageW(v22, 0x147u, 0, 0);
      *((_DWORD *)v5 + 39) = SendMessageW((HWND)v3[37], 0x150u, v23, 0);
    }
    if ( *(_DWORD *)(*v3 + 28) )
    {
      DlgItemInt = GetDlgItemInt((HWND)v3[4], 1287, &Translated, 0);
      if ( Translated && DlgItemInt <= 0x3B9AC9FF )
        *((_DWORD *)v5 + 37) = DlgItemInt;
      v25 = SendMessageW((HWND)v3[36], 0x147u, 0, 0);
      *((_DWORD *)v5 + 38) = SendMessageW((HWND)v3[36], 0x150u, v25, 0);
      *((_DWORD *)v5 + 40) = SendMessageW((HWND)v3[41], 0xF0u, 0, 0);
    }
  }
  if ( v3[5] )
  {
    if ( *((_DWORD *)v5 + 6) == 1 )
    {
      Free0(*((void **)v5 + 28));
      SuGetInfo(v3 + 166, v5 + 108, v5 + 106, v5 + 112);
    }
    v26 = (__int64 *)v3[73];
    if ( v26 )
    {
      v27 = *((_DWORD *)v5 + 48);
      for ( j = *v26; j; j = *(_QWORD *)(j + 8) )
      {
        v29 = *(_QWORD *)(j + 16);
        *((_DWORD *)v5 + 48) = *(_DWORD *)v29;
        DwSetCustomAuthData(v5, *(unsigned int *)(v29 + 72), *(_QWORD *)(v29 + 64));
        Free0(*(void **)(v29 + 64));
        *(_QWORD *)(v29 + 64) = 0;
      }
      *((_DWORD *)v5 + 48) = v27;
    }
  }
  if ( v3[180] )
  {
    NeSaveBindingChanges(v3);
    if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v3[180] + 40LL))(v3[180]) == 303136
      || *((_DWORD *)v3 + 351)
      || *((_DWORD *)v3 + 352) )
    {
      v30 = v3[185];
      if ( v30 )
        (*(void (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v30 + 32LL))(
          v30,
          v3[1],
          v3 + 188,
          3 - (unsigned int)(*((_DWORD *)v3 + 351) != 0));
    }
  }
  v31 = 0;
  v32 = **((_QWORD **)v5 + 4);
  v33 = v32;
  if ( v32 )
  {
    do
    {
      v34 = *(_QWORD *)(v33 + 16);
      if ( *(_DWORD *)(v34 + 188) && *(_DWORD *)(v34 + 40) == 6 )
        ++v31;
      v33 = *(_QWORD *)(v33 + 8);
    }
    while ( v33 );
    if ( v31 > 1 )
    {
      do
      {
        v35 = *(_QWORD *)(v32 + 16);
        if ( *(_DWORD *)(v35 + 188) && *(_DWORD *)(v35 + 128) )
          *(_DWORD *)(v35 + 128) = 0;
        v32 = *(_QWORD *)(v32 + 8);
      }
      while ( v32 );
    }
  }
  if ( HrasconnFromEntry(**(PCNZWCH **)(*v3 + 64), *((PCNZWCH *)v5 + 1)) )
    MsgDlgUtil((HWND)v3[1], 0xF4u, 0, g_hinstDll, 0x169u);
  v36 = *v3;
  if ( (*(_DWORD *)(*(_QWORD *)(*v3 + 16) + 12LL) & 0x40000000) != 0 )
    EuCommit(v36);
  else
    *(_DWORD *)(v36 + 24) = 1;
  return 1;
}

```

## disassembly

```asm
0x18001bae4  push    rbx
0x18001bae6  push    rbp
0x18001bae7  push    rsi
0x18001bae8  push    rdi
0x18001bae9  push    r12
0x18001baeb  push    r13
0x18001baed  push    r14
0x18001baef  push    r15
0x18001baf1  sub     rsp, 38h
0x18001baf5  mov     rbx, rcx
0x18001baf8  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001bafe  cmp     ecx, 0FFFFFFFFh
0x18001bb01  jz      short loc_18001BB15
0x18001bb03  lea     r8, aPeapply; "PeApply"
0x18001bb0a  mov     edx, 0Ch; dwFlags
0x18001bb0f  call    cs:__imp_TracePrintfExA
0x18001bb15  mov     rcx, rbx
0x18001bb18  call    AiContext
0x18001bb1d  xor     r15d, r15d
0x18001bb20  mov     rdi, rax
0x18001bb23  test    rax, rax
0x18001bb26  jnz     short loc_18001BB32
0x18001bb28  mov     eax, 3EBh
0x18001bb2d  jmp     loc_18001C06F
0x18001bb32  mov     rcx, [rax]
0x18001bb35  mov     rsi, [rcx+368h]
0x18001bb3c  cmp     dword ptr [rsi+18h], 2
0x18001bb40  jz      short loc_18001BB48
0x18001bb42  cmp     dword ptr [rsi+18h], 5
0x18001bb46  jnz     short loc_18001BB5D
0x18001bb48  cmp     [rsi+80h], r15d
0x18001bb4f  jnz     short loc_18001BB5D
0x18001bb51  mov     rdx, [rcx+8]; LPCWSTR
0x18001bb55  mov     rcx, [rcx]; LPCWSTR
0x18001bb58  call    ClearCachedCredentials
0x18001bb5d  mov     r12d, 1
0x18001bb63  mov     r13d, 0F0h
0x18001bb69  cmp     [rsi+18h], r12d
0x18001bb6d  jnz     loc_18001BC80
0x18001bb73  mov     rcx, rdi
0x18001bb76  call    GeSaveLvDeviceChecks
0x18001bb7b  mov     edx, eax
0x18001bb7d  mov     rax, [rdi]
0x18001bb80  mov     ecx, [rax+144h]
0x18001bb86  test    ecx, ecx
0x18001bb88  jz      loc_18001BC34
0x18001bb8e  test    edx, edx
0x18001bb90  jnz     short loc_18001BBD8
0x18001bb92  mov     r9, cs:g_hinstDll; hInstance
0x18001bb99  xor     r8d, r8d; Arguments
0x18001bb9c  mov     edx, 5F9h; uID
0x18001bba1  mov     [rsp+78h+var_58], 169h; UINT
0x18001bba9  mov     rcx, rbx; hWnd
0x18001bbac  call    MsgDlgUtil
0x18001bbb1  mov     r9, [rdi+18h]; lParam
0x18001bbb5  xor     r8d, r8d; wParam
0x18001bbb8  mov     rcx, [rdi+8]; hWnd
0x18001bbbc  mov     edx, 465h; Msg
0x18001bbc1  call    cs:__imp_SendMessageW
0x18001bbc7  mov     rcx, [rdi+38h]; hWnd
0x18001bbcb  call    cs:__imp_SetFocus
0x18001bbd1  xor     eax, eax
0x18001bbd3  jmp     loc_18001C06F
0x18001bbd8  test    ecx, ecx
0x18001bbda  jz      short loc_18001BC34
0x18001bbdc  mov     rcx, [rdi+58h]; hWnd
0x18001bbe0  xor     r9d, r9d; lParam
0x18001bbe3  xor     r8d, r8d; wParam
0x18001bbe6  mov     edx, r13d; Msg
0x18001bbe9  call    cs:__imp_SendMessageW
0x18001bbef  mov     [rsi+28h], eax
0x18001bbf2  mov     rcx, [rdi+0B8h]; hWnd
0x18001bbf9  test    rcx, rcx
0x18001bbfc  jz      short loc_18001BC38
0x18001bbfe  call    cs:__imp_IsWindowEnabled
0x18001bc04  test    eax, eax
0x18001bc06  jz      short loc_18001BC2B
0x18001bc08  mov     rcx, [rdi+0B8h]; hWnd
0x18001bc0f  xor     r9d, r9d; lParam
0x18001bc12  xor     r8d, r8d; wParam
0x18001bc15  mov     edx, r13d; Msg
0x18001bc18  call    cs:__imp_SendMessageW
0x18001bc1e  test    eax, eax
0x18001bc20  jz      short loc_18001BC2B
0x18001bc22  mov     [rsi+84h], r15d
0x18001bc29  jmp     short loc_18001BC38
0x18001bc2b  mov     [rsi+84h], r12d
0x18001bc32  jmp     short loc_18001BC38
0x18001bc34  mov     [rsi+28h], r12d
0x18001bc38  mov     rdx, [rdi+490h]
0x18001bc3f  mov     rcx, rdi
0x18001bc42  call    GeGetPhoneFields
0x18001bc47  mov     rdx, [rdi+588h]
0x18001bc4e  test    rdx, rdx
0x18001bc51  jz      loc_18001BDAE
0x18001bc57  mov     rax, [rdi]
0x18001bc5a  mov     rcx, [rax+80h]
0x18001bc61  mov     rcx, [rcx+78h]
0x18001bc65  call    DtlSwapLists
0x18001bc6a  mov     rcx, [rdi]
0x18001bc6d  mov     rax, [rcx+80h]
0x18001bc74  mov     [rax+0B4h], r12d
0x18001bc7b  jmp     loc_18001BDAE
0x18001bc80  cmp     dword ptr [rsi+18h], 2
0x18001bc84  jnz     loc_18001BD59
0x18001bc8a  mov     rax, [rsi+20h]
0x18001bc8e  mov     rcx, [rax]
0x18001bc91  mov     r14, [rcx+10h]
0x18001bc95  mov     rcx, [r14+0A8h]
0x18001bc9c  call    FirstPhoneNodeFromPhoneList
0x18001bca1  mov     rbp, rax
0x18001bca4  test    rax, rax
0x18001bca7  jz      loc_18001BBD1
0x18001bcad  mov     rbx, [rax+10h]
0x18001bcb1  mov     rcx, [rbx+10h]
0x18001bcb5  call    Free0
0x18001bcba  mov     rcx, [rdi+0C0h]; hWnd
0x18001bcc1  call    GetText
0x18001bcc6  mov     [rbx+10h], rax
0x18001bcca  mov     rdx, rbp
0x18001bccd  mov     rcx, [r14+0A8h]
0x18001bcd4  call    FirstPhoneNodeToPhoneList
0x18001bcd9  mov     rcx, [rdi+0C8h]; hWnd
0x18001bce0  test    rcx, rcx
0x18001bce3  jz      short loc_18001BD12
0x18001bce5  xor     r9d, r9d; lParam
0x18001bce8  xor     r8d, r8d; wParam
0x18001bceb  mov     edx, r13d; Msg
0x18001bcee  call    cs:__imp_SendMessageW
0x18001bcf4  test    eax, eax
0x18001bcf6  jnz     short loc_18001BD12
0x18001bcf8  mov     rcx, [rsi+38h]
0x18001bcfc  call    Free0
0x18001bd01  mov     rcx, [rsi+40h]
0x18001bd05  mov     [rsi+38h], r15
0x18001bd09  call    Free0
0x18001bd0e  mov     [rsi+40h], r15
0x18001bd12  mov     rax, [rdi]
0x18001bd15  mov     rcx, [rax+370h]
0x18001bd1c  mov     rbx, [rcx]
0x18001bd1f  test    rbx, rbx
0x18001bd22  jz      loc_18001BDAE
0x18001bd28  mov     rbp, [rbx+10h]
0x18001bd2c  cmp     dword ptr [rbp+28h], 0Bh
0x18001bd30  jnz     short loc_18001BD45
0x18001bd32  mov     edx, [rsi+0A8h]
0x18001bd38  mov     rcx, rbp
0x18001bd3b  call    cs:__imp_IsValidPbportForVPNStrategy
0x18001bd41  test    eax, eax
0x18001bd43  jnz     short loc_18001BD4B
0x18001bd45  mov     rbx, [rbx+8]
0x18001bd49  jmp     short loc_18001BD1F
0x18001bd4b  mov     rdx, rbp
0x18001bd4e  mov     rcx, r14
0x18001bd51  call    cs:__imp_CopyToPbport
0x18001bd57  jmp     short loc_18001BDAE
0x18001bd59  cmp     dword ptr [rsi+18h], 5
0x18001bd5d  jnz     short loc_18001BDAE
0x18001bd5f  mov     rax, [rsi+20h]
0x18001bd63  mov     rcx, [rax]
0x18001bd66  mov     r14, [rcx+10h]
0x18001bd6a  mov     rcx, [r14+0A8h]
0x18001bd71  call    FirstPhoneNodeFromPhoneList
0x18001bd76  mov     rbp, rax
0x18001bd79  test    rax, rax
0x18001bd7c  jz      loc_18001BBD1
0x18001bd82  mov     rbx, [rax+10h]
0x18001bd86  mov     rcx, [rbx+10h]
0x18001bd8a  call    Free0
0x18001bd8f  mov     rcx, [rdi+0D8h]; hWnd
0x18001bd96  call    GetText
0x18001bd9b  mov     [rbx+10h], rax
0x18001bd9f  mov     rdx, rbp
0x18001bda2  mov     rcx, [r14+0A8h]
0x18001bda9  call    FirstPhoneNodeToPhoneList
0x18001bdae  cmp     [rdi+20h], r15
0x18001bdb2  jz      loc_18001BEBF
0x18001bdb8  mov     rcx, [rdi+0F0h]; hWnd
0x18001bdbf  mov     [rsp+78h+Translated], r15d
0x18001bdc7  test    rcx, rcx
0x18001bdca  jz      short loc_18001BDDE
0x18001bdcc  xor     r9d, r9d; lParam
0x18001bdcf  xor     r8d, r8d; wParam
0x18001bdd2  mov     edx, r13d; Msg
0x18001bdd5  call    cs:__imp_SendMessageW
0x18001bddb  mov     [rsi+70h], eax
0x18001bdde  mov     rcx, [rdi+108h]; hWnd
0x18001bde5  test    rcx, rcx
0x18001bde8  jz      short loc_18001BDFC
0x18001bdea  xor     r9d, r9d; lParam
0x18001bded  xor     r8d, r8d; wParam
0x18001bdf0  mov     edx, r13d; Msg
0x18001bdf3  call    cs:__imp_SendMessageW
0x18001bdf9  mov     [rsi+7Ch], eax
0x18001bdfc  mov     rcx, [rdi+128h]; hWnd
0x18001be03  mov     ebx, 147h
0x18001be08  lea     ebp, [rbx+9]
0x18001be0b  test    rcx, rcx
0x18001be0e  jz      short loc_18001BE39
0x18001be10  xor     r9d, r9d; lParam
0x18001be13  xor     r8d, r8d; wParam
0x18001be16  mov     edx, ebx; Msg
0x18001be18  call    cs:__imp_SendMessageW
0x18001be1e  mov     rcx, [rdi+128h]; hWnd
0x18001be25  xor     r9d, r9d; lParam
0x18001be28  movsxd  r8, eax; wParam
0x18001be2b  mov     edx, ebp; Msg
0x18001be2d  call    cs:__imp_SendMessageW
0x18001be33  mov     [rsi+9Ch], eax
0x18001be39  mov     rax, [rdi]
0x18001be3c  cmp     [rax+1Ch], r15d
0x18001be40  jz      short loc_18001BEBF
0x18001be42  mov     rcx, [rdi+20h]; hDlg
0x18001be46  lea     r8, [rsp+78h+Translated]; lpTranslated
0x18001be4e  xor     r9d, r9d; bSigned
0x18001be51  mov     edx, 507h; nIDDlgItem
0x18001be56  call    cs:__imp_GetDlgItemInt
0x18001be5c  cmp     [rsp+78h+Translated], r15d
0x18001be64  jz      short loc_18001BE73
0x18001be66  cmp     eax, 3B9AC9FFh
0x18001be6b  ja      short loc_18001BE73
0x18001be6d  mov     [rsi+94h], eax
0x18001be73  mov     rcx, [rdi+120h]; hWnd
0x18001be7a  xor     r9d, r9d; lParam
0x18001be7d  xor     r8d, r8d; wParam
0x18001be80  mov     edx, ebx; Msg
0x18001be82  call    cs:__imp_SendMessageW
0x18001be88  mov     rcx, [rdi+120h]; hWnd
0x18001be8f  xor     r9d, r9d; lParam
0x18001be92  movsxd  r8, eax; wParam
0x18001be95  mov     edx, ebp; Msg
0x18001be97  call    cs:__imp_SendMessageW
0x18001be9d  mov     [rsi+98h], eax
0x18001bea3  xor     r9d, r9d; lParam
0x18001bea6  mov     rcx, [rdi+148h]; hWnd
0x18001bead  xor     r8d, r8d; wParam
0x18001beb0  mov     edx, r13d; Msg
0x18001beb3  call    cs:__imp_SendMessageW
0x18001beb9  mov     [rsi+0A0h], eax
0x18001bebf  cmp     [rdi+28h], r15
0x18001bec3  jz      loc_18001BF4D
0x18001bec9  cmp     [rsi+18h], r12d
0x18001becd  jnz     short loc_18001BEFB
0x18001becf  lea     rbx, [rsi+0E0h]
0x18001bed6  mov     rcx, [rbx]
0x18001bed9  call    Free0
0x18001bede  lea     r8, [rsi+0D4h]
0x18001bee5  mov     r9, rbx
0x18001bee8  lea     rdx, [rsi+0D8h]
0x18001beef  lea     rcx, [rdi+530h]
0x18001bef6  call    SuGetInfo
0x18001befb  mov     rbp, [rdi+248h]
0x18001bf02  test    rbp, rbp
0x18001bf05  jz      short loc_18001BF4D
0x18001bf07  mov     r14d, [rsi+0C0h]
0x18001bf0e  mov     rbp, [rbp+0]
0x18001bf12  jmp     short loc_18001BF41
0x18001bf14  mov     rbx, [rbp+10h]
0x18001bf18  mov     rcx, rsi
0x18001bf1b  mov     eax, [rbx]
0x18001bf1d  mov     [rsi+0C0h], eax
0x18001bf23  mov     r8, [rbx+40h]
0x18001bf27  mov     edx, [rbx+48h]
0x18001bf2a  call    cs:__imp_DwSetCustomAuthData
0x18001bf30  mov     rcx, [rbx+40h]
0x18001bf34  call    Free0
0x18001bf39  mov     [rbx+40h], r15
0x18001bf3d  mov     rbp, [rbp+8]
0x18001bf41  test    rbp, rbp
0x18001bf44  jnz     short loc_18001BF14
0x18001bf46  mov     [rsi+0C0h], r14d
0x18001bf4d  cmp     [rdi+5A0h], r15
0x18001bf54  jz      short loc_18001BFBC
0x18001bf56  mov     rcx, rdi
0x18001bf59  call    NeSaveBindingChanges
0x18001bf5e  mov     rcx, [rdi+5A0h]
0x18001bf65  mov     rax, [rcx]
0x18001bf68  mov     rax, [rax+28h]
0x18001bf6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf71  cmp     eax, 4A020h
0x18001bf76  jz      short loc_18001BF8A
0x18001bf78  cmp     [rdi+57Ch], r15d
0x18001bf7f  jnz     short loc_18001BF8A
0x18001bf81  cmp     [rdi+580h], r15d
0x18001bf88  jz      short loc_18001BFBC
0x18001bf8a  mov     rcx, [rdi+5C8h]
0x18001bf91  test    rcx, rcx
0x18001bf94  jz      short loc_18001BFBC
0x18001bf96  mov     eax, [rdi+57Ch]
0x18001bf9c  lea     r8, [rdi+5E0h]
0x18001bfa3  mov     r10, [rcx]
0x18001bfa6  neg     eax
0x18001bfa8  mov     rdx, [rdi+8]
0x18001bfac  sbb     r9d, r9d
0x18001bfaf  add     r9d, 3
0x18001bfb3  mov     rax, [r10+20h]
0x18001bfb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfbc  mov     rax, [rsi+20h]
0x18001bfc0  mov     edx, r15d
0x18001bfc3  mov     rcx, [rax]
  ... truncated ...
```
