# MntUnmount

- ea: `0x140024720`
- end: `0x140024c5a`
- name: `MntUnmount`
- size: `1338`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x140027244`
- `0x1400273f0`

## callees

- `0x140001010`
- `0x1400010c0`
- `0x140001600`
- `0x140014c30`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140015ab8`
- `0x140024720`
- `0x14002d1e4`
- `0x14003aba0`
- `0x14003adc0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x140024ae1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140024b08`
- `ntoskrnl!ExReleaseResourceLite` at `0x140024ae1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140024b08`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140024ab0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140024ab0`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1400247e2`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x1400247e2`
- `ntoskrnl!RtlFreeAnsiString` at `0x140024a11`
- `ntoskrnl!RtlFreeAnsiString` at `0x140024bff`
- `ntoskrnl!RtlFreeAnsiString` at `0x140024a11`
- `ntoskrnl!RtlFreeAnsiString` at `0x140024bff`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140024a9f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140024a9f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024aed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024b14`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024aed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140024b14`
- `rpcxdr!OncRpcSendReplyAndDestroy` at `0x140024ad2`
- `rpcxdr!OncRpcSendReplyAndDestroy` at `0x140024ad2`
- `rpcxdr!OncRpcBuildCall` at `0x1400248f8`
- `rpcxdr!OncRpcBuildCall` at `0x1400248f8`
- `rpcxdr!OncRpcDestroy` at `0x140024bd3`
- `rpcxdr!OncRpcDestroy` at `0x140024be4`
- `rpcxdr!OncRpcDestroy` at `0x140024bd3`
- `rpcxdr!OncRpcDestroy` at `0x140024be4`

## pseudocode

```c
void __fastcall MntUnmount(__int64 a1, const UNICODE_STRING *a2)
{
  __int64 v4; // rax
  __int128 v5; // xmm0
  __int64 v6; // rdi
  int v7; // ebx
  NTSTATUS v8; // eax
  USHORT Length; // ax
  __int64 v10; // rsi
  PCHAR Buffer; // r9
  size_t v12; // rdx
  __int64 v13; // rax
  _DWORD *v14; // rcx
  _QWORD *v15; // rcx
  size_t v16; // rbx
  char *v17; // r9
  char *v18; // r8
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rcx
  int v24; // edx
  int v25; // eax
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  struct _STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  int v28; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v30[12]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v31; // [rsp+E0h] [rbp-20h] BYREF
  int v32; // [rsp+F0h] [rbp-10h]
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+F8h] [rbp-8h] BYREF
  int *v34; // [rsp+118h] [rbp+18h]
  __int64 v35; // [rsp+120h] [rbp+20h]

  v26 = 0;
  v29 = 0;
  DestinationString = 0;
  memset(v30, 0, 0x54u);
  v4 = *(_QWORD *)(a1 + 48);
  v5 = *(_OWORD *)(v4 + 1376);
  v32 = *(_DWORD *)(v4 + 1392);
  v31 = v5;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids, a2);
  v6 = *(_QWORD *)(a1 + 32);
  if ( !v6 )
  {
    v7 = -1073741823;
    goto LABEL_37;
  }
  v8 = RtlUnicodeStringToAnsiString(&DestinationString, a2, 1u);
  v7 = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
LABEL_40:
      if ( (unsigned int)dword_140041028 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn() )
        {
          v28 = v7;
          v34 = &v28;
          v35 = 4;
          tlgWriteTransfer_EtwWriteTransfer(v20, (unsigned __int8 *)&byte_14003E47B, v21, v22, 3u, &v33);
        }
      }
      return;
    }
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        34,
        WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids,
        (unsigned int)v8);
LABEL_37:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_ZD(
        WPP_GLOBAL_Control->AttachedDevice,
        41,
        (unsigned int)WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids,
        (_DWORD)a2,
        v7);
    goto LABEL_40;
  }
  Length = DestinationString.Length;
  if ( DestinationString.Length == 2 && *DestinationString.Buffer == 47 && DestinationString.Buffer[1] == 33 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids);
    Length = 1;
    DestinationString.Length = 1;
  }
  *(_OWORD *)&v30[1] = DaSystemUnixId;
  LODWORD(v30[0]) = 1;
  *(_OWORD *)&v30[5] = xmmword_1400410F0;
  *(_OWORD *)&v30[3] = xmmword_1400410E0;
  *(_OWORD *)&v30[7] = xmmword_140041100;
  *(_OWORD *)((char *)&v30[8] + 4) = *(__int128 *)((char *)&xmmword_140041100 + 12);
  if ( (int)OncRpcBuildCall(
              &v26,
              v6 + 44,
              *(unsigned int *)(v6 + 8),
              *(unsigned int *)(v6 + 12),
              *(_DWORD *)(v6 + 16),
              3,
              (-Length & 3) + 8 + (unsigned int)Length,
              v30) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids);
    v7 = -1073741670;
LABEL_36:
    RtlFreeAnsiString(&DestinationString);
    goto LABEL_37;
  }
  v10 = v26;
  Buffer = DestinationString.Buffer;
  v12 = DestinationString.Length;
  v13 = *(_QWORD *)(v26 + 72);
  if ( v13 )
    v14 = *(_DWORD **)(v13 + 64);
  else
    v14 = 0;
  *v14 = _byteswap_ulong(DestinationString.Length);
  *(_QWORD *)(*(_QWORD *)(v10 + 72) + 64LL) += 4LL;
  v15 = *(_QWORD **)(v10 + 72);
  if ( v15 )
    v15 = (_QWORD *)v15[8];
  v16 = v12;
  memmove(v15, Buffer, v12);
  *(_QWORD *)(*(_QWORD *)(v10 + 72) + 64LL) += v16;
  XdrNextMod4Boundary(v10);
  v18 = *(char **)(v10 + 72);
  if ( v18 )
    v18 = (char *)*((_QWORD *)v18 + 8);
  if ( v17 != v18 )
    memset(v17, 0, v18 - v17);
  v19 = v26;
  if ( *(int *)(v26 + 264) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids);
      v19 = v26;
    }
    v7 = *(_DWORD *)(v19 + 264);
    goto LABEL_36;
  }
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite(*(PERESOURCE *)v6, 1u);
  if ( *(_DWORD *)(v6 + 8) == 17 && (v23 = *(_QWORD *)(v6 + 24)) != 0 )
  {
    OncRpcSendReplyAndDestroy(v23, 0, v26);
    ExReleaseResourceLite(*(PERESOURCE *)v6);
    KeLeaveCriticalRegion();
  }
  else
  {
    ExReleaseResourceLite(*(PERESOURCE *)v6);
    KeLeaveCriticalRegion();
    v25 = NfsSendWaitReplyWait(*(_QWORD *)(a1 + 48), v24, 0, 0, (__int64)&v31, v6, v26, (__int64)&v29, 0, 0);
    if ( v25 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids, a2);
      if ( v29 )
        OncRpcDestroy(v29);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        38,
        WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids,
        (unsigned int)v25);
    }
    OncRpcDestroy(v26);
    NfsForceDisconnect(v6, 0);
  }
  RtlFreeAnsiString(&DestinationString);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids, a2);
}

```

## disassembly

```asm
0x140024720  mov     [rsp-8+arg_10], rbx
0x140024725  push    rbp
0x140024726  push    rsi
0x140024727  push    rdi
0x140024728  push    r14
0x14002472a  push    r15
0x14002472c  lea     rbp, [rsp-30h]
0x140024731  sub     rsp, 130h
0x140024738  mov     rax, cs:__security_cookie
0x14002473f  xor     rax, rsp
0x140024742  mov     [rbp+50h+var_28], rax
0x140024746  xor     eax, eax
0x140024748  mov     [rsp+150h+var_100], 0
0x140024751  mov     r14, rdx
0x140024754  mov     [rsp+150h+var_E0], 0
0x14002475d  mov     r15, rcx
0x140024760  mov     [rbp+50h+var_CC], eax
0x140024763  xorps   xmm0, xmm0
0x140024766  lea     rcx, [rbp+50h+var_D0]; void *
0x14002476a  lea     r8d, [rax+54h]; Size
0x14002476e  xor     edx, edx; Val
0x140024770  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x140024775  call    memset
0x14002477a  mov     rax, [r15+30h]
0x14002477e  movups  xmm0, xmmword ptr [rax+560h]
0x140024785  mov     eax, [rax+570h]
0x14002478b  mov     [rbp+50h+var_60], eax
0x14002478e  movups  [rbp+50h+var_70], xmm0
0x140024792  mov     rcx, cs:WPP_GLOBAL_Control
0x140024799  lea     rsi, WPP_GLOBAL_Control
0x1400247a0  cmp     rcx, rsi
0x1400247a3  jz      short loc_1400247C4
0x1400247a5  mov     eax, [rcx+2Ch]
0x1400247a8  test    al, 10h
0x1400247aa  jz      short loc_1400247C4
0x1400247ac  mov     rcx, [rcx+18h]
0x1400247b0  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x1400247b7  mov     edx, 21h ; '!'
0x1400247bc  mov     r9, r14
0x1400247bf  call    WPP_SF_Z
0x1400247c4  mov     rdi, [r15+20h]
0x1400247c8  test    rdi, rdi
0x1400247cb  jnz     short loc_1400247D7
0x1400247cd  mov     ebx, 0C0000001h
0x1400247d2  jmp     loc_140024A1D
0x1400247d7  mov     r8b, 1; AllocateDestinationString
0x1400247da  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x1400247df  mov     rdx, r14; SourceString
0x1400247e2  call    cs:__imp_RtlUnicodeStringToAnsiString
0x1400247e9  nop     dword ptr [rax+rax+00h]
0x1400247ee  mov     ebx, eax
0x1400247f0  test    eax, eax
0x1400247f2  jns     short loc_14002482D
0x1400247f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400247fb  cmp     rcx, rsi
0x1400247fe  jz      loc_140024A4C
0x140024804  mov     edx, [rcx+2Ch]
0x140024807  test    dl, 1
0x14002480a  jz      loc_140024A1D
0x140024810  mov     rcx, [rcx+18h]
0x140024814  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x14002481b  mov     edx, 22h ; '"'
0x140024820  mov     r9d, eax
0x140024823  call    WPP_SF_d
0x140024828  jmp     loc_140024A1D
0x14002482d  movzx   eax, [rsp+150h+DestinationString.Length]
0x140024832  mov     ecx, 2
0x140024837  cmp     cx, ax
0x14002483a  jnz     short loc_14002487E
0x14002483c  mov     rcx, [rsp+150h+DestinationString.Buffer]
0x140024841  cmp     byte ptr [rcx], 2Fh ; '/'
0x140024844  jnz     short loc_14002487E
0x140024846  cmp     byte ptr [rcx+1], 21h ; '!'
0x14002484a  jnz     short loc_14002487E
0x14002484c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024853  cmp     rcx, rsi
0x140024856  jz      short loc_140024874
0x140024858  mov     eax, [rcx+2Ch]
0x14002485b  test    al, 4
0x14002485d  jz      short loc_140024874
0x14002485f  mov     rcx, [rcx+18h]
0x140024863  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x14002486a  mov     edx, 23h ; '#'
0x14002486f  call    WPP_SF_
0x140024874  mov     eax, 1
0x140024879  mov     [rsp+150h+DestinationString.Length], ax
0x14002487e  movaps  xmm0, cs:DaSystemUnixId
0x140024885  lea     rdx, [rdi+2Ch]
0x140024889  movaps  xmm1, cs:xmmword_1400410E0
0x140024890  movzx   ecx, ax
0x140024893  movups  [rbp+50h+var_C8], xmm0
0x140024897  mov     eax, ecx
0x140024899  mov     [rbp+50h+var_D0], 1
0x1400248a0  movaps  xmm0, cs:xmmword_1400410F0
0x1400248a7  neg     eax
0x1400248a9  movups  [rbp+50h+var_A8], xmm0
0x1400248ad  and     eax, 3
0x1400248b0  movups  xmm0, cs:xmmword_140041100+0Ch
0x1400248b7  add     eax, 8
0x1400248ba  add     ecx, eax
0x1400248bc  lea     rax, [rbp+50h+var_D0]
0x1400248c0  movups  [rbp+50h+var_B8], xmm1
0x1400248c4  mov     [rsp+150h+var_118], rax
0x1400248c9  movaps  xmm1, cs:xmmword_140041100
0x1400248d0  movups  [rbp+50h+var_98], xmm1
0x1400248d4  mov     dword ptr [rsp+150h+var_120], ecx
0x1400248d8  lea     rcx, [rsp+150h+var_100]
0x1400248dd  movups  [rbp+50h+var_98+0Ch], xmm0
0x1400248e1  mov     eax, [rdi+10h]
0x1400248e4  mov     r9d, [rdi+0Ch]
0x1400248e8  mov     r8d, [rdi+8]
0x1400248ec  mov     dword ptr [rsp+150h+var_128], 3
0x1400248f4  mov     [rsp+150h+var_130], eax
0x1400248f8  call    cs:__imp_OncRpcBuildCall
0x1400248ff  nop     dword ptr [rax+rax+00h]
0x140024904  test    eax, eax
0x140024906  jns     short loc_14002493A
0x140024908  mov     rcx, cs:WPP_GLOBAL_Control
0x14002490f  cmp     rcx, rsi
0x140024912  jz      short loc_140024930
0x140024914  mov     eax, [rcx+2Ch]
0x140024917  test    al, 1
0x140024919  jz      short loc_140024930
0x14002491b  mov     rcx, [rcx+18h]
0x14002491f  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x140024926  mov     edx, 24h ; '$'
0x14002492b  call    WPP_SF_
0x140024930  mov     ebx, 0C000009Ah
0x140024935  jmp     loc_140024A0C
0x14002493a  mov     rsi, [rsp+150h+var_100]
0x14002493f  mov     r9, [rsp+150h+DestinationString.Buffer]
0x140024944  movzx   edx, [rsp+150h+DestinationString.Length]
0x140024949  mov     rax, [rsi+48h]
0x14002494d  test    rax, rax
0x140024950  jnz     short loc_140024956
0x140024952  xor     ecx, ecx
0x140024954  jmp     short loc_14002495A
0x140024956  mov     rcx, [rax+40h]
0x14002495a  mov     eax, edx
0x14002495c  bswap   eax
0x14002495e  mov     [rcx], eax
0x140024960  mov     rax, [rsi+48h]
0x140024964  add     qword ptr [rax+40h], 4
0x140024969  mov     rcx, [rsi+48h]
0x14002496d  test    rcx, rcx
0x140024970  jz      short loc_140024976
0x140024972  mov     rcx, [rcx+40h]; void *
0x140024976  mov     rbx, rdx
0x140024979  mov     r8, rdx; Size
0x14002497c  mov     rdx, r9; Src
0x14002497f  call    memmove
0x140024984  mov     rax, [rsi+48h]
0x140024988  add     [rax+40h], rbx
0x14002498c  mov     r9, [rsi+48h]
0x140024990  test    r9, r9
0x140024993  jz      short loc_140024999
0x140024995  mov     r9, [r9+40h]
0x140024999  mov     rcx, rsi
0x14002499c  call    XdrNextMod4Boundary
0x1400249a1  mov     r8, [rsi+48h]
0x1400249a5  test    r8, r8
0x1400249a8  jz      short loc_1400249AE
0x1400249aa  mov     r8, [r8+40h]
0x1400249ae  cmp     r9, r8
0x1400249b1  jz      short loc_1400249C0
0x1400249b3  sub     r8, r9; Size
0x1400249b6  xor     edx, edx; Val
0x1400249b8  mov     rcx, r9; void *
0x1400249bb  call    memset
0x1400249c0  mov     rbx, [rsp+150h+var_100]
0x1400249c5  cmp     dword ptr [rbx+108h], 0
0x1400249cc  jge     loc_140024A9F
0x1400249d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400249d9  lea     rsi, WPP_GLOBAL_Control
0x1400249e0  cmp     rcx, rsi
0x1400249e3  jz      short loc_140024A06
0x1400249e5  mov     eax, [rcx+2Ch]
0x1400249e8  test    al, 1
0x1400249ea  jz      short loc_140024A06
0x1400249ec  mov     rcx, [rcx+18h]
0x1400249f0  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x1400249f7  mov     edx, 25h ; '%'
0x1400249fc  call    WPP_SF_
0x140024a01  mov     rbx, [rsp+150h+var_100]
0x140024a06  mov     ebx, [rbx+108h]
0x140024a0c  lea     rcx, [rsp+150h+DestinationString]; AnsiString
0x140024a11  call    cs:__imp_RtlFreeAnsiString
0x140024a18  nop     dword ptr [rax+rax+00h]
0x140024a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140024a24  cmp     rcx, rsi
0x140024a27  jz      short loc_140024A4C
0x140024a29  mov     eax, [rcx+2Ch]
0x140024a2c  test    al, 1
0x140024a2e  jz      short loc_140024A4C
0x140024a30  mov     rcx, [rcx+18h]
0x140024a34  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x140024a3b  mov     edx, 29h ; ')'
0x140024a40  mov     [rsp+150h+var_130], ebx
0x140024a44  mov     r9, r14
0x140024a47  call    WPP_SF_ZD
0x140024a4c  mov     eax, cs:dword_140041028
0x140024a52  cmp     eax, 5
0x140024a55  jbe     loc_140024C36
0x140024a5b  call    _tlgKeywordOn
0x140024a60  test    al, al
0x140024a62  jz      loc_140024C36
0x140024a68  lea     rax, [rsp+150h+var_E8]
0x140024a6d  mov     [rsp+150h+var_E8], ebx
0x140024a71  mov     [rbp+50h+var_38], rax
0x140024a75  lea     rdx, byte_14003E47B; int
0x140024a7c  lea     rax, [rbp+50h+var_58]
0x140024a80  mov     [rbp+50h+var_30], 4
0x140024a88  mov     [rsp+150h+var_128], rax; PEVENT_DATA_DESCRIPTOR
0x140024a8d  mov     [rsp+150h+var_130], 3; ULONG
0x140024a95  call    _tlgWriteTransfer_EtwWriteTransfer
0x140024a9a  jmp     loc_140024C36
0x140024a9f  call    cs:__imp_KeEnterCriticalRegion
0x140024aa6  nop     dword ptr [rax+rax+00h]
0x140024aab  mov     rcx, [rdi]; Resource
0x140024aae  mov     dl, 1; Wait
0x140024ab0  call    cs:__imp_ExAcquireResourceSharedLite
0x140024ab7  nop     dword ptr [rax+rax+00h]
0x140024abc  cmp     dword ptr [rdi+8], 11h
0x140024ac0  jnz     short loc_140024B05
0x140024ac2  mov     rcx, [rdi+18h]
0x140024ac6  test    rcx, rcx
0x140024ac9  jz      short loc_140024B05
0x140024acb  mov     r8, [rsp+150h+var_100]
0x140024ad0  xor     edx, edx
0x140024ad2  call    cs:__imp_OncRpcSendReplyAndDestroy
0x140024ad9  nop     dword ptr [rax+rax+00h]
0x140024ade  mov     rcx, [rdi]; Resource
0x140024ae1  call    cs:__imp_ExReleaseResourceLite
0x140024ae8  nop     dword ptr [rax+rax+00h]
0x140024aed  call    cs:__imp_KeLeaveCriticalRegion
0x140024af4  nop     dword ptr [rax+rax+00h]
0x140024af9  lea     rbx, WPP_GLOBAL_Control
0x140024b00  jmp     loc_140024BFA
0x140024b05  mov     rcx, [rdi]; Resource
0x140024b08  call    cs:__imp_ExReleaseResourceLite
0x140024b0f  nop     dword ptr [rax+rax+00h]
0x140024b14  call    cs:__imp_KeLeaveCriticalRegion
0x140024b1b  nop     dword ptr [rax+rax+00h]
0x140024b20  mov     rcx, [r15+30h]
0x140024b24  lea     rax, [rsp+150h+var_E0]
0x140024b29  mov     [rsp+150h+var_108], 0
0x140024b31  xor     r9d, r9d
0x140024b34  mov     [rsp+150h+var_110], 0
0x140024b39  xor     r8d, r8d
0x140024b3c  mov     [rsp+150h+var_118], rax
0x140024b41  mov     rax, [rsp+150h+var_100]
0x140024b46  mov     [rsp+150h+var_120], rax
0x140024b4b  lea     rax, [rbp+50h+var_70]
0x140024b4f  mov     [rsp+150h+var_128], rdi
0x140024b54  mov     qword ptr [rsp+150h+var_130], rax
0x140024b59  call    NfsSendWaitReplyWait
0x140024b5e  test    eax, eax
0x140024b60  jns     short loc_140024B97
0x140024b62  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b69  lea     rbx, WPP_GLOBAL_Control
0x140024b70  cmp     rcx, rbx
0x140024b73  jz      short loc_140024BDF
0x140024b75  mov     edx, [rcx+2Ch]
0x140024b78  test    dl, 1
0x140024b7b  jz      short loc_140024BDF
0x140024b7d  mov     rcx, [rcx+18h]
0x140024b81  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x140024b88  mov     edx, 26h ; '&'
0x140024b8d  mov     r9d, eax
0x140024b90  call    WPP_SF_d
0x140024b95  jmp     short loc_140024BDF
0x140024b97  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b9e  lea     rbx, WPP_GLOBAL_Control
0x140024ba5  cmp     rcx, rbx
0x140024ba8  jz      short loc_140024BC9
0x140024baa  mov     eax, [rcx+2Ch]
0x140024bad  test    al, 4
0x140024baf  jz      short loc_140024BC9
0x140024bb1  mov     rcx, [rcx+18h]
0x140024bb5  lea     r8, WPP_3a342be9bb9131d4f0c07e258ac9bf8e_Traceguids
0x140024bbc  mov     edx, 27h ; '''
0x140024bc1  mov     r9, r14
0x140024bc4  call    WPP_SF_Z
0x140024bc9  mov     rcx, [rsp+150h+var_E0]
0x140024bce  test    rcx, rcx
0x140024bd1  jz      short loc_140024BDF
0x140024bd3  call    cs:__imp_OncRpcDestroy
0x140024bda  nop     dword ptr [rax+rax+00h]
0x140024bdf  mov     rcx, [rsp+150h+var_100]
0x140024be4  call    cs:__imp_OncRpcDestroy
0x140024beb  nop     dword ptr [rax+rax+00h]
0x140024bf0  xor     edx, edx
0x140024bf2  mov     rcx, rdi
0x140024bf5  call    NfsForceDisconnect
0x140024bfa  lea     rcx, [rsp+150h+DestinationString]; AnsiString
0x140024bff  call    cs:__imp_RtlFreeAnsiString
0x140024c06  nop     dword ptr [rax+rax+00h]
0x140024c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140024c12  cmp     rcx, rbx
0x140024c15  jz      short loc_140024C36
  ... truncated ...
```
