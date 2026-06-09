# CWwanSvcNotificationManager::ShowNotificationWithAction(int,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_MbaeNotificationManagerServiceKind)

- ea: `0x18002a870`
- end: `0x18002ac22`
- name: `?ShowNotificationWithAction@CWwanSvcNotificationManager@@UEAAJHHPEBG00000W4_MbaeNotificationManagerServiceKind@@@Z`
- size: `946`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800024e0`
- `0x180002efc`
- `0x180009ffc`
- `0x18002a1d0`
- `0x18002a870`

## string_xrefs

- `0x18002aa96`: `Protocol`
- `0x18002ab39`: `Protocol`
- `0x18002aab4`: `<toast scenario="%s" launch="%s"><visual><binding template="ToastGeneric"><text>%s</text><text>%s</text></binding></visual><actions><action activationType="%s" content="%s" arguments="%s"/><action activationType="Background" content="%s" arguments="%s"/></actions></toast>`
- `0x18002ab51`: `<toast scenario="%s" launch="%s"><visual><binding template="ToastGeneric"><text>%s</text><text>%s</text></binding></visual><actions><action activationType="%s" content="%s" arguments="%s"/></actions></toast>`
- `0x18002abbe`: `<toast scenario="%s" launch="%s"><visual><binding template="ToastGeneric"><text>%s</text><text>%s</text></binding></visual></toast>`

## pseudocode

```c
__int64 __fastcall CWwanSvcNotificationManager::ShowNotificationWithAction(
        __int64 a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        wchar_t *a8,
        const wchar_t *a9,
        int a10)
{
  const wchar_t *v10; // r14
  const wchar_t *v11; // r12
  __int64 v12; // rsi
  __int64 v13; // rax
  const wchar_t *v14; // rdi
  const wchar_t *v15; // r9
  __int64 result; // rax
  int v17; // r8d
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned __int16 *v21; // rax
  const wchar_t *v22; // rdx
  const wchar_t *v23; // r9
  unsigned __int16 *v24; // rax
  const wchar_t *v25; // rdx
  const wchar_t *v26; // r9
  const wchar_t *v27; // r9
  unsigned __int16 v31[64]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v32[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v33[1024]; // [rsp+180h] [rbp+80h] BYREF

  v10 = a9;
  memset_0(v33, 0, sizeof(v33));
  memset_0(v32, 0, sizeof(v32));
  memset_0(v31, 0, sizeof(v31));
  v11 = L"0001";
  v12 = -1;
  if ( !a9 )
    goto LABEL_5;
  v13 = -1;
  do
    ++v13;
  while ( a9[v13] );
  if ( !v13 )
LABEL_5:
    v10 = L"0001";
  v14 = L"UnknownSvc";
  if ( a10 )
  {
    switch ( a10 )
    {
      case 1:
        v15 = L"LpaSvc";
        break;
      case 2:
        v15 = L"ImsSvc";
        break;
      case 3:
        v15 = L"UtkSvc";
        break;
      case 4:
        v15 = L"CellArd";
        break;
      default:
        v15 = L"UnknownSvc";
        break;
    }
  }
  else
  {
    v15 = L"WwanSvc";
  }
  result = StringCchPrintfW(v31, 0x40u, aSS_0, v15, v10);
  v17 = a3;
  if ( !a3 )
  {
    if ( a8 )
    {
      v18 = -1;
      do
        ++v18;
      while ( a8[v18] );
      if ( v18 )
        v11 = a8;
    }
    if ( a10 )
    {
      switch ( a10 )
      {
        case 1:
          v14 = L"LpaSvc";
          break;
        case 2:
          v14 = L"ImsSvc";
          break;
        case 3:
          v14 = L"UtkSvc";
          break;
        case 4:
          v14 = L"CellArd";
          break;
      }
    }
    else
    {
      v14 = L"WwanSvc";
    }
    result = StringCchPrintfW(v32, 0x40u, aSS_0, v14, v11);
    v17 = 0;
  }
  if ( (int)result >= 0 )
  {
    if ( !a6 )
      goto LABEL_50;
    v19 = -1;
    do
      ++v19;
    while ( *(_WORD *)(a6 + 2 * v19) );
    if ( v19 )
    {
      if ( !a7 )
        goto LABEL_60;
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)(a7 + 2 * v20) );
      if ( v20 )
      {
        v21 = v32;
        if ( v17 )
          v21 = a8;
        v22 = L"Protocol";
        if ( !v17 )
          v22 = L"Foreground";
        v23 = L"systemDialog";
        if ( !a2 )
          v23 = L"none";
        result = StringCchPrintfW(v33, 0x400u, aToastScenarioS, v23, v31, a4, a5, v22, a6, v21, a7, v31);
LABEL_63:
        if ( (int)result >= 0 )
          return PostNotificationHelper(v33, 0);
        return result;
      }
    }
    else
    {
LABEL_50:
      if ( !a7 )
        goto LABEL_60;
    }
    do
      ++v12;
    while ( *(_WORD *)(a7 + 2 * v12) );
    if ( v12 )
    {
      v24 = v32;
      if ( v17 )
        v24 = a8;
      v25 = L"Protocol";
      v26 = L"systemDialog";
      if ( !v17 )
        v25 = L"Foreground";
      if ( !a2 )
        v26 = L"none";
      result = StringCchPrintfW(v33, 0x400u, aToastScenarioS_0, v26, v31, a4, a5, v25, a6, v24);
      goto LABEL_63;
    }
LABEL_60:
    v27 = L"systemDialog";
    if ( !a2 )
      v27 = L"none";
    result = StringCchPrintfW(v33, 0x400u, aToastScenarioS_1, v27, v31, a4, a5);
    goto LABEL_63;
  }
  return result;
}

```

## disassembly

```asm
0x18002a870  push    rbp
0x18002a872  push    rbx
0x18002a873  push    rsi
0x18002a874  push    rdi
0x18002a875  push    r12
0x18002a877  push    r13
0x18002a879  push    r14
0x18002a87b  push    r15
0x18002a87d  lea     rbp, [rsp-898h]
0x18002a885  sub     rsp, 998h
0x18002a88c  mov     rax, cs:__security_cookie
0x18002a893  xor     rax, rsp
0x18002a896  mov     [rbp+8D0h+var_50], rax
0x18002a89d  mov     rax, [rbp+8D0h+arg_38]
0x18002a8a4  lea     rcx, [rbp+8D0h+var_850]; void *
0x18002a8ab  mov     r13, [rbp+8D0h+arg_28]
0x18002a8b2  mov     r15, [rbp+8D0h+arg_30]
0x18002a8b9  mov     r14, [rbp+8D0h+arg_40]
0x18002a8c0  mov     [rsp+9D0h+var_958], rax
0x18002a8c5  mov     rax, [rbp+8D0h+arg_20]
0x18002a8cc  mov     [rsp+9D0h+var_96C], r8d
0x18002a8d1  mov     r8d, 800h; Size
0x18002a8d7  mov     [rsp+9D0h+var_970], edx
0x18002a8db  xor     edx, edx; Val
0x18002a8dd  mov     [rsp+9D0h+var_968], rax
0x18002a8e2  mov     [rsp+9D0h+var_960], r9
0x18002a8e7  call    memset_0
0x18002a8ec  mov     ebx, 80h
0x18002a8f1  lea     rcx, [rbp+8D0h+var_8D0]; void *
0x18002a8f5  mov     r8d, ebx; Size
0x18002a8f8  xor     edx, edx; Val
0x18002a8fa  call    memset_0
0x18002a8ff  mov     r8d, ebx; Size
0x18002a902  lea     rcx, [rbp+8D0h+var_950]; void *
0x18002a906  xor     edx, edx; Val
0x18002a908  call    memset_0
0x18002a90d  xor     edx, edx
0x18002a90f  lea     r12, a0001; "0001"
0x18002a916  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002a91a  test    r14, r14
0x18002a91d  jz      short loc_18002A931
0x18002a91f  mov     rax, rsi
0x18002a922  inc     rax
0x18002a925  cmp     [r14+rax*2], dx
0x18002a92a  jnz     short loc_18002A922
0x18002a92c  test    rax, rax
0x18002a92f  jnz     short loc_18002A934
0x18002a931  mov     r14, r12
0x18002a934  mov     ebx, [rbp+8D0h+arg_48]
0x18002a93a  lea     rdi, aUnknownsvc; "UnknownSvc"
0x18002a941  mov     ecx, ebx
0x18002a943  test    ebx, ebx
0x18002a945  jz      short loc_18002A984
0x18002a947  sub     ecx, 1
0x18002a94a  jz      short loc_18002A97B
0x18002a94c  sub     ecx, 1
0x18002a94f  jz      short loc_18002A972
0x18002a951  sub     ecx, 1
0x18002a954  jz      short loc_18002A969
0x18002a956  cmp     ecx, 1
0x18002a959  jz      short loc_18002A960
0x18002a95b  mov     r9, rdi
0x18002a95e  jmp     short loc_18002A98B
0x18002a960  lea     r9, aCellard; "CellArd"
0x18002a967  jmp     short loc_18002A98B
0x18002a969  lea     r9, aUtksvc; "UtkSvc"
0x18002a970  jmp     short loc_18002A98B
0x18002a972  lea     r9, aImssvc; "ImsSvc"
0x18002a979  jmp     short loc_18002A98B
0x18002a97b  lea     r9, aLpasvc; "LpaSvc"
0x18002a982  jmp     short loc_18002A98B
0x18002a984  lea     r9, aWwansvc; "WwanSvc"
0x18002a98b  lea     r8, aSS_0; "%s;%s"
0x18002a992  mov     [rsp+9D0h+var_9B0], r14
0x18002a997  mov     edx, 40h ; '@'; unsigned __int64
0x18002a99c  lea     rcx, [rbp+8D0h+var_950]; unsigned __int16 *
0x18002a9a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a9a5  mov     r8d, [rsp+9D0h+var_96C]
0x18002a9aa  xor     r10d, r10d
0x18002a9ad  mov     r14, [rsp+9D0h+var_958]
0x18002a9b2  test    r8d, r8d
0x18002a9b5  jnz     loc_18002AA3D
0x18002a9bb  test    r14, r14
0x18002a9be  jz      short loc_18002A9D5
0x18002a9c0  mov     rax, rsi
0x18002a9c3  inc     rax
0x18002a9c6  cmp     [r14+rax*2], r10w
0x18002a9cb  jnz     short loc_18002A9C3
0x18002a9cd  test    rax, rax
0x18002a9d0  jz      short loc_18002A9D5
0x18002a9d2  mov     r12, r14
0x18002a9d5  test    ebx, ebx
0x18002a9d7  jz      short loc_18002AA11
0x18002a9d9  sub     ebx, 1
0x18002a9dc  jz      short loc_18002AA08
0x18002a9de  sub     ebx, 1
0x18002a9e1  jz      short loc_18002A9FF
0x18002a9e3  sub     ebx, 1
0x18002a9e6  jz      short loc_18002A9F6
0x18002a9e8  cmp     ebx, 1
0x18002a9eb  jnz     short loc_18002AA18
0x18002a9ed  lea     rdi, aCellard; "CellArd"
0x18002a9f4  jmp     short loc_18002AA18
0x18002a9f6  lea     rdi, aUtksvc; "UtkSvc"
0x18002a9fd  jmp     short loc_18002AA18
0x18002a9ff  lea     rdi, aImssvc; "ImsSvc"
0x18002aa06  jmp     short loc_18002AA18
0x18002aa08  lea     rdi, aLpasvc; "LpaSvc"
0x18002aa0f  jmp     short loc_18002AA18
0x18002aa11  lea     rdi, aWwansvc; "WwanSvc"
0x18002aa18  mov     r9, rdi
0x18002aa1b  mov     [rsp+9D0h+var_9B0], r12
0x18002aa20  lea     r8, aSS_0; "%s;%s"
0x18002aa27  mov     edx, 40h ; '@'; unsigned __int64
0x18002aa2c  lea     rcx, [rbp+8D0h+var_8D0]; unsigned __int16 *
0x18002aa30  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002aa35  mov     r8d, [rsp+9D0h+var_96C]
0x18002aa3a  xor     r10d, r10d
0x18002aa3d  test    eax, eax
0x18002aa3f  js      loc_18002ABFF
0x18002aa45  test    r13, r13
0x18002aa48  jz      loc_18002AB0F
0x18002aa4e  mov     rax, rsi
0x18002aa51  inc     rax
0x18002aa54  cmp     [r13+rax*2+0], r10w
0x18002aa5a  jnz     short loc_18002AA51
0x18002aa5c  test    rax, rax
0x18002aa5f  jz      loc_18002AB0F
0x18002aa65  test    r15, r15
0x18002aa68  jz      loc_18002ABA1
0x18002aa6e  mov     rax, rsi
0x18002aa71  inc     rax
0x18002aa74  cmp     [r15+rax*2], r10w
0x18002aa79  jnz     short loc_18002AA71
0x18002aa7b  test    rax, rax
0x18002aa7e  jz      loc_18002AB18
0x18002aa84  test    r8d, r8d
0x18002aa87  lea     rcx, aForeground; "Foreground"
0x18002aa8e  lea     rax, [rbp+8D0h+var_8D0]
0x18002aa92  cmovnz  rax, r14
0x18002aa96  lea     rdx, aProtocol; "Protocol"
0x18002aa9d  cmovz   rdx, rcx
0x18002aaa1  lea     r9, aSystemdialog; "systemDialog"
0x18002aaa8  cmp     [rsp+9D0h+var_970], r10d
0x18002aaad  lea     rcx, aNone; "none"
0x18002aab4  lea     r8, aToastScenarioS; "<toast scenario=\"%s\" launch=\"%s\"><v"...
0x18002aabb  cmovz   r9, rcx
0x18002aabf  lea     rcx, [rbp+8D0h+var_950]
0x18002aac3  mov     [rsp+9D0h+var_978], rcx
0x18002aac8  lea     rcx, [rbp+8D0h+var_850]; unsigned __int16 *
0x18002aacf  mov     [rsp+9D0h+var_980], r15
0x18002aad4  mov     [rsp+9D0h+var_988], rax
0x18002aad9  mov     rax, [rsp+9D0h+var_968]
0x18002aade  mov     [rsp+9D0h+var_990], r13
0x18002aae3  mov     [rsp+9D0h+var_998], rdx
0x18002aae8  mov     edx, 400h; unsigned __int64
0x18002aaed  mov     [rsp+9D0h+var_9A0], rax
0x18002aaf2  mov     rax, [rsp+9D0h+var_960]
0x18002aaf7  mov     [rsp+9D0h+var_9A8], rax
0x18002aafc  lea     rax, [rbp+8D0h+var_950]
0x18002ab00  mov     [rsp+9D0h+var_9B0], rax
0x18002ab05  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ab0a  jmp     loc_18002ABED
0x18002ab0f  test    r15, r15
0x18002ab12  jz      loc_18002ABA1
0x18002ab18  inc     rsi
0x18002ab1b  cmp     [r15+rsi*2], r10w
0x18002ab20  jnz     short loc_18002AB18
0x18002ab22  test    rsi, rsi
0x18002ab25  jz      short loc_18002ABA1
0x18002ab27  test    r8d, r8d
0x18002ab2a  lea     rcx, aForeground; "Foreground"
0x18002ab31  lea     rax, [rbp+8D0h+var_8D0]
0x18002ab35  cmovnz  rax, r14
0x18002ab39  lea     rdx, aProtocol; "Protocol"
0x18002ab40  mov     [rsp+9D0h+var_988], rax
0x18002ab45  lea     r9, aSystemdialog; "systemDialog"
0x18002ab4c  mov     rax, [rsp+9D0h+var_968]
0x18002ab51  lea     r8, aToastScenarioS_0; "<toast scenario=\"%s\" launch=\"%s\"><v"...
0x18002ab58  cmovz   rdx, rcx
0x18002ab5c  mov     [rsp+9D0h+var_990], r13
0x18002ab61  cmp     [rsp+9D0h+var_970], r10d
0x18002ab66  lea     rcx, aNone; "none"
0x18002ab6d  mov     [rsp+9D0h+var_998], rdx
0x18002ab72  mov     edx, 400h; unsigned __int64
0x18002ab77  mov     [rsp+9D0h+var_9A0], rax
0x18002ab7c  cmovz   r9, rcx
0x18002ab80  mov     rax, [rsp+9D0h+var_960]
0x18002ab85  lea     rcx, [rbp+8D0h+var_850]; unsigned __int16 *
0x18002ab8c  mov     [rsp+9D0h+var_9A8], rax
0x18002ab91  lea     rax, [rbp+8D0h+var_950]
0x18002ab95  mov     [rsp+9D0h+var_9B0], rax
0x18002ab9a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002ab9f  jmp     short loc_18002ABED
0x18002aba1  mov     rax, [rsp+9D0h+var_968]
0x18002aba6  lea     rcx, aNone; "none"
0x18002abad  cmp     [rsp+9D0h+var_970], r10d
0x18002abb2  lea     r9, aSystemdialog; "systemDialog"
0x18002abb9  mov     [rsp+9D0h+var_9A0], rax
0x18002abbe  lea     r8, aToastScenarioS_1; "<toast scenario=\"%s\" launch=\"%s\"><v"...
0x18002abc5  mov     rax, [rsp+9D0h+var_960]
0x18002abca  cmovz   r9, rcx
0x18002abce  mov     [rsp+9D0h+var_9A8], rax
0x18002abd3  lea     rcx, [rbp+8D0h+var_850]; unsigned __int16 *
0x18002abda  lea     rax, [rbp+8D0h+var_950]
0x18002abde  mov     edx, 400h; unsigned __int64
0x18002abe3  mov     [rsp+9D0h+var_9B0], rax
0x18002abe8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002abed  xor     edx, edx; unsigned __int16 *
0x18002abef  test    eax, eax
0x18002abf1  js      short loc_18002ABFF
0x18002abf3  lea     rcx, [rbp+8D0h+var_850]; unsigned __int16 *
0x18002abfa  call    ?PostNotificationHelper@@YAJPEBG0@Z; PostNotificationHelper(ushort const *,ushort const *)
0x18002abff  mov     rcx, [rbp+8D0h+var_50]
0x18002ac06  xor     rcx, rsp; StackCookie
0x18002ac09  call    __security_check_cookie
0x18002ac0e  add     rsp, 998h
0x18002ac15  pop     r15
0x18002ac17  pop     r14
0x18002ac19  pop     r13
0x18002ac1b  pop     r12
0x18002ac1d  pop     rdi
0x18002ac1e  pop     rsi
0x18002ac1f  pop     rbx
0x18002ac20  pop     rbp
0x18002ac21  retn
```
