# LoEapPropertiesLocal

- ea: `0x180018fec`
- end: `0x18001915e`
- name: `LoEapPropertiesLocal`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018a30`

## callees

- `0x180002506`
- `0x180018fec`
- `0x18003a2f0`
- `0x18003aa3c`
- `0x180048048`
- `0x180048f0c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180019120`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180019120`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800190f6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800190f6`
- `USER32!SendMessageW` at `0x180019027`
- `USER32!SendMessageW` at `0x180019027`
- `rtutils!TracePrintfExA` at `0x1800190ea`
- `rtutils!TracePrintfExA` at `0x1800190ea`
- `eappcfg!EapHostPeerInvokeConfigUI` at `0x18001908c`
- `eappcfg!EapHostPeerInvokeConfigUI` at `0x18001908c`

## string_xrefs

- `0x1800190de`: `EapHostPeerInvokeConfigUI returned: 0x%x, mapping to 0x%x.`

## pseudocode

```c
int __fastcall LoEapPropertiesLocal(HWND *a1)
{
  HWND v2; // rcx
  int v3; // eax
  LRESULT ItemDataPtr; // rax
  __int64 v5; // rbx
  HWND v6; // rcx
  DWORD v7; // r9d
  DWORD v8; // edx
  int v9; // edi
  int v10; // ebx
  HGLOBAL v11; // rax
  BYTE *pConfigIn; // [rsp+20h] [rbp-30h]
  EAP_METHOD_TYPE eapMethodType; // [rsp+40h] [rbp-10h] BYREF
  DWORD pdwSizeOfConfigOut; // [rsp+70h] [rbp+20h] BYREF
  BYTE *pData; // [rsp+78h] [rbp+28h] BYREF
  EAP_ERROR *ppEapError; // [rsp+80h] [rbp+30h] BYREF

  pData = 0;
  v2 = a1[48];
  pdwSizeOfConfigOut = 0;
  ppEapError = 0;
  v3 = SendMessageW(v2, 0x147u, 0, 0);
  ItemDataPtr = ComboBox_GetItemDataPtr(a1[48], v3);
  if ( ItemDataPtr )
  {
    v5 = *(_QWORD *)(ItemDataPtr + 16);
    v6 = a1[1];
    v7 = *(_DWORD *)(v5 + 72);
    v8 = *((_DWORD *)*a1 + 7) != 0;
    pConfigIn = *(BYTE **)(v5 + 64);
    eapMethodType = *(EAP_METHOD_TYPE *)(v5 + 8);
    LODWORD(ItemDataPtr) = EapHostPeerInvokeConfigUI(
                             v6,
                             v8,
                             &eapMethodType,
                             v7,
                             pConfigIn,
                             &pdwSizeOfConfigOut,
                             &pData,
                             &ppEapError);
    v9 = ItemDataPtr;
    if ( (_DWORD)ItemDataPtr )
    {
      if ( (_DWORD)ItemDataPtr != 1223 )
      {
        v10 = MapEapHostErrorToRasError((unsigned int)ItemDataPtr);
        LODWORD(ItemDataPtr) = MsgDlgUtil(a1[1], 0xC9u, 0, g_hinstDll, 0x169u);
        if ( g_dwTraceId != -1 )
          LODWORD(ItemDataPtr) = TracePrintfExA(
                                   g_dwTraceId,
                                   0xCu,
                                   "EapHostPeerInvokeConfigUI returned: 0x%x, mapping to 0x%x.",
                                   v9,
                                   v10);
      }
    }
    else
    {
      GlobalFree(*(HGLOBAL *)(v5 + 64));
      *(_QWORD *)(v5 + 64) = 0;
      *(_DWORD *)(v5 + 72) = 0;
      if ( pData )
      {
        if ( pdwSizeOfConfigOut )
        {
          v11 = GlobalAlloc(0x40u, pdwSizeOfConfigOut);
          *(_QWORD *)(v5 + 64) = v11;
          if ( v11 )
          {
            memcpy_0(v11, pData, pdwSizeOfConfigOut);
            *(_DWORD *)(v5 + 72) = pdwSizeOfConfigOut;
          }
        }
      }
      LODWORD(ItemDataPtr) = RasFreeEapMemory(pData);
    }
  }
  return ItemDataPtr;
}

```

## disassembly

```asm
0x180018fec  mov     [rsp-18h+arg_18], rbx
0x180018ff1  push    rbp
0x180018ff2  push    rsi
0x180018ff3  push    rdi
0x180018ff4  mov     rbp, rsp
0x180018ff7  sub     rsp, 50h
0x180018ffb  mov     rsi, rcx
0x180018ffe  mov     [rbp+pData], 0
0x180019006  mov     rcx, [rcx+180h]; hWnd
0x18001900d  xor     r9d, r9d; lParam
0x180019010  xor     r8d, r8d; wParam
0x180019013  mov     [rbp+arg_0], 0
0x18001901a  mov     edx, 147h; Msg
0x18001901f  mov     [rbp+arg_10], 0
0x180019027  call    cs:__imp_SendMessageW
0x18001902d  mov     rcx, [rsi+180h]
0x180019034  mov     edx, eax
0x180019036  call    ComboBox_GetItemDataPtr
0x18001903b  test    rax, rax
0x18001903e  jz      loc_18001914E
0x180019044  mov     rbx, [rax+10h]
0x180019048  lea     r8, [rbp+eapMethodType]; eapMethodType
0x18001904c  mov     rax, [rsi]
0x18001904f  xor     edx, edx
0x180019051  mov     rcx, [rsi+8]; hwndParent
0x180019055  movups  xmm0, xmmword ptr [rbx+8]
0x180019059  cmp     [rax+1Ch], edx
0x18001905c  lea     rax, [rbp+arg_10]
0x180019060  mov     r9d, [rbx+48h]; dwSizeOfConfigIn
0x180019064  mov     [rsp+50h+ppEapError], rax; ppEapError
0x180019069  setnz   dl; dwFlags
0x18001906c  lea     rax, [rbp+pData]
0x180019070  mov     [rsp+50h+ppConfigOut], rax; ppConfigOut
0x180019075  lea     rax, [rbp+arg_0]
0x180019079  mov     [rsp+50h+pdwSizeOfConfigOut], rax; pdwSizeOfConfigOut
0x18001907e  mov     rax, [rbx+40h]
0x180019082  mov     [rsp+50h+pConfigIn], rax; pConfigIn
0x180019087  movdqu  xmmword ptr [rbp+eapMethodType.eapType.type], xmm0
0x18001908c  call    cs:__imp_EapHostPeerInvokeConfigUI
0x180019092  mov     edi, eax
0x180019094  test    eax, eax
0x180019096  jz      short loc_1800190F2
0x180019098  cmp     eax, 4C7h
0x18001909d  jz      loc_18001914E
0x1800190a3  mov     ecx, eax
0x1800190a5  call    MapEapHostErrorToRasError
0x1800190aa  mov     r9, cs:g_hinstDll; hInstance
0x1800190b1  xor     r8d, r8d; Arguments
0x1800190b4  mov     rcx, [rsi+8]; hWnd
0x1800190b8  mov     edx, 0C9h; uID
0x1800190bd  mov     ebx, eax
0x1800190bf  mov     dword ptr [rsp+50h+pConfigIn], 169h; UINT
0x1800190c7  call    MsgDlgUtil
0x1800190cc  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800190d2  cmp     ecx, 0FFFFFFFFh
0x1800190d5  jz      short loc_18001914E
0x1800190d7  mov     r9d, edi
0x1800190da  mov     dword ptr [rsp+50h+pConfigIn], ebx
0x1800190de  lea     r8, aEaphostpeerinv_1; "EapHostPeerInvokeConfigUI returned: 0x%"...
0x1800190e5  mov     edx, 0Ch; dwFlags
0x1800190ea  call    cs:__imp_TracePrintfExA
0x1800190f0  jmp     short loc_18001914E
0x1800190f2  mov     rcx, [rbx+40h]; hMem
0x1800190f6  call    cs:__imp_GlobalFree
0x1800190fc  mov     qword ptr [rbx+40h], 0
0x180019104  mov     dword ptr [rbx+48h], 0
0x18001910b  cmp     [rbp+pData], 0
0x180019110  jz      short loc_180019145
0x180019112  mov     eax, [rbp+arg_0]
0x180019115  test    eax, eax
0x180019117  jz      short loc_180019145
0x180019119  mov     edx, eax; dwBytes
0x18001911b  mov     ecx, 40h ; '@'; uFlags
0x180019120  call    cs:__imp_GlobalAlloc
0x180019126  mov     [rbx+40h], rax
0x18001912a  test    rax, rax
0x18001912d  jz      short loc_180019145
0x18001912f  mov     r8d, [rbp+arg_0]; Size
0x180019133  mov     rcx, rax; void *
0x180019136  mov     rdx, [rbp+pData]; Src
0x18001913a  call    memcpy_0
0x18001913f  mov     eax, [rbp+arg_0]
0x180019142  mov     [rbx+48h], eax
0x180019145  mov     rcx, [rbp+pData]; pData
0x180019149  call    RasFreeEapMemory
0x18001914e  mov     rbx, [rsp+50h+arg_18]
0x180019156  add     rsp, 50h
0x18001915a  pop     rdi
0x18001915b  pop     rsi
0x18001915c  pop     rbp
0x18001915d  retn
```
