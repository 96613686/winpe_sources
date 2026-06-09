# DdmModernDevice::MarkPortConnectComplete(void)

- ea: `0x180042f70`
- end: `0x180043283`
- name: `?MarkPortConnectComplete@DdmModernDevice@@UEAAKXZ`
- size: `787`
- prototype: `__int64 __fastcall(DdmModernDevice *this)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180007d00`
- `0x180042f70`
- `0x180045818`
- `0x180075588`
- `0x1800755b8`
- `0x18008cb84`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x180043184`
- `KERNEL32!DeviceIoControl` at `0x180043184`
- `KERNEL32!PostQueuedCompletionStatus` at `0x1800431fd`
- `KERNEL32!PostQueuedCompletionStatus` at `0x1800431fd`
- `KERNEL32!GetLastError` at `0x1800430a2`
- `KERNEL32!GetLastError` at `0x180043194`
- `KERNEL32!GetLastError` at `0x18004320d`
- `KERNEL32!GetLastError` at `0x1800430a2`
- `KERNEL32!GetLastError` at `0x180043194`
- `KERNEL32!GetLastError` at `0x18004320d`

## string_xrefs

- `0x180043033`: `MarkPortConnectComplete`
- `0x18004323a`: `IO completion for PostRecvPkt failed with error 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdmModernDevice::MarkPortConnectComplete(DdmModernDevice *this)
{
  __int64 v2; // rdx
  int v3; // r8d
  __int64 v4; // rcx
  DWORD ID; // edi
  __int64 v6; // rdx
  __int128 v7; // xmm0
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdx
  DWORD BytesReturned; // [rsp+48h] [rbp-C0h] BYREF
  DWORD BytesReturned_8[4]; // [rsp+50h] [rbp-B8h] BYREF
  _DWORD v14[10]; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD OutBuffer[3]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v16; // [rsp+A0h] [rbp-68h]
  __int64 v17; // [rsp+A8h] [rbp-60h]
  int v18; // [rsp+B0h] [rbp-58h]
  __int128 v19; // [rsp+B4h] [rbp-54h]
  int v20; // [rsp+C8h] [rbp-40h] BYREF
  _DWORD v21[27]; // [rsp+CCh] [rbp-3Ch] BYREF
  int v22; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v23[2044]; // [rsp+13Ch] [rbp+34h] BYREF

  BytesReturned = 0;
  memset_0(v21, 0, 0x60u);
  memset_0(OutBuffer, 0, 0x40u);
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  memset(v14, 0, sizeof(v14));
  *(_OWORD *)BytesReturned_8 = 0;
  if ( (byte_1800CF404 & 0x10) != 0 )
  {
    LOWORD(v14[0]) = 0;
    v2 = this ? *((unsigned int *)this + 24) : 0xFFFFFFFFLL;
    ConvertPortNoToString(v14, v2);
    if ( (byte_1800CF404 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)L"MarkPortConnectComplete",
        (unsigned int)BytesReturned_8,
        0,
        (__int64)v14);
  }
  v3 = *((_DWORD *)this + 299);
  v4 = 312LL * *((int *)this + 303);
  v20 = 100;
  ID = RasLineGetID(*(int *)((char *)&dword_1800CFFFC + v4), (int)&dword_1800CFFFC, v3, 4, (wchar_t *)L"NDIS", &v20);
  if ( ID )
  {
    ID = GetLastError();
    if ( (byte_1800CF404 & 8) == 0 )
      return ID;
    v6 = *((unsigned int *)this + 24);
    LOWORD(v22) = 0;
    LOWORD(v14[0]) = 0;
    ConvertPortNoToString(v14, v6);
    FormatRRASErrorString(&v22, L"RasLineGetID failed with error 0x%x", ID);
    goto LABEL_10;
  }
  v7 = *(_OWORD *)((char *)this + 714);
  v8 = *(_QWORD *)((char *)&v21[-1] + v21[4]);
  v16 = *((_QWORD *)this + 12);
  v17 = v16;
  OutBuffer[2] = v8;
  v18 = 16;
  v19 = v7;
  if ( !DeviceIoControl(gblDdmDriverInfo, 0x120000u, OutBuffer, 0x40u, OutBuffer, 0x40u, &BytesReturned, 0) )
  {
    ID = GetLastError();
    if ( (byte_1800CF404 & 8) == 0 )
      return ID;
    v9 = *((unsigned int *)this + 24);
    LOWORD(v22) = 0;
    LOWORD(v14[0]) = 0;
    ConvertPortNoToString(v14, v9);
    FormatRRASErrorString(&v22, L"IOCTL_NDISWAN_MAP_CONNECTION_ID failed with error 0x%x", ID);
    goto LABEL_10;
  }
  *((_QWORD *)this + 14) = OutBuffer[0];
  *((_QWORD *)this + 15) = OutBuffer[1];
  if ( !byte_1800CF998 && !PostQueuedCompletionStatus(CompletionPort, 0, 0, &stru_1800CF8F8) )
  {
    ID = GetLastError();
    if ( (byte_1800CF404 & 8) == 0 )
      return ID;
    v10 = *((unsigned int *)this + 24);
    LOWORD(v22) = 0;
    LOWORD(v14[0]) = 0;
    ConvertPortNoToString(v14, v10);
    FormatRRASErrorString(&v22, L"IO completion for PostRecvPkt failed with error 0x%x", ID);
LABEL_10:
    if ( (byte_1800CF404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v22,
        (unsigned int)BytesReturned_8,
        0,
        (__int64)v14);
    return ID;
  }
  if ( *((_WORD *)this + 68) == 9 )
    DdmModernDevice::SaveIPSecInfo(this);
  return ID;
}

```

## disassembly

```asm
0x180042f70  mov     rax, rsp
0x180042f73  mov     [rax+10h], rbx
0x180042f77  mov     [rax+18h], rsi
0x180042f7b  mov     [rax+20h], rdi
0x180042f7f  push    rbp
0x180042f80  lea     rbp, [rax-848h]
0x180042f87  sub     rsp, 940h
0x180042f8e  mov     rax, cs:__security_cookie
0x180042f95  xor     rax, rsp
0x180042f98  mov     [rbp+840h+var_10], rax
0x180042f9f  xor     esi, esi
0x180042fa1  mov     rbx, rcx
0x180042fa4  xor     edx, edx; Val
0x180042fa6  mov     [rsp+940h+BytesReturned], esi
0x180042faa  lea     rcx, [rbp+840h+var_880+4]; void *
0x180042fae  lea     r8d, [rsi+60h]; Size
0x180042fb2  call    memset_0
0x180042fb7  xor     edx, edx; Val
0x180042fb9  lea     r8d, [rsi+40h]; Size
0x180042fbd  lea     rcx, [rbp+840h+OutBuffer]; void *
0x180042fc1  call    memset_0
0x180042fc6  xor     edx, edx; Val
0x180042fc8  mov     [rbp+840h+var_810], esi
0x180042fcb  mov     r8d, 7FCh; Size
0x180042fd1  lea     rcx, [rbp+840h+var_80C]; void *
0x180042fd5  call    memset_0
0x180042fda  xorps   xmm0, xmm0
0x180042fdd  mov     dword ptr [rsp+940h+var_8EC+4], esi
0x180042fe1  xor     eax, eax
0x180042fe3  test    cs:byte_1800CF404, 10h
0x180042fea  movups  [rsp+940h+var_8EC+8], xmm0
0x180042fef  mov     [rsp+940h+var_8C4], eax
0x180042ff3  movups  xmmword ptr [rsp+940h+var_8DC+8], xmm0
0x180042ff8  movups  xmmword ptr [rsp+940h+BytesReturned+8], xmm0
0x180042ffd  jz      short loc_180043052
0x180042fff  mov     word ptr [rsp+940h+var_8EC+4], si
0x180043004  test    rbx, rbx
0x180043007  jz      short loc_18004300E
0x180043009  mov     edx, [rbx+60h]
0x18004300c  jmp     short loc_180043011
0x18004300e  or      edx, 0FFFFFFFFh
0x180043011  lea     rcx, [rsp+940h+var_8EC+4]
0x180043016  call    ConvertPortNoToString
0x18004301b  test    cs:byte_1800CF404, 10h
0x180043022  jz      short loc_180043052
0x180043024  lea     rax, [rsp+940h+var_8EC+4]
0x180043029  mov     qword ptr [rsp+940h+nOutBufferSize], rax
0x18004302e  lea     r9, [rsp+940h+BytesReturned+8]
0x180043033  lea     r8, aMarkportconnec; "MarkPortConnectComplete"
0x18004303a  mov     [rsp+940h+lpOutBuffer], rsi
0x18004303f  lea     rdx, RasDdmParamTraceInfo
0x180043046  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004304d  call    McTemplateU0zjzz_EventWriteTransfer
0x180043052  movsxd  rax, dword ptr [rbx+4BCh]
0x180043059  lea     rdx, dword_1800CFFFC; int
0x180043060  mov     r8d, [rbx+4ACh]; int
0x180043067  mov     r9d, 4; int
0x18004306d  imul    rcx, rax, 138h
0x180043074  lea     rax, [rbp+840h+var_880]
0x180043078  mov     dword ptr [rbp+840h+var_880], 64h ; 'd'
0x18004307f  mov     qword ptr [rsp+940h+nOutBufferSize], rax; void *
0x180043084  lea     rax, aNdis; "NDIS"
0x18004308b  mov     [rsp+940h+lpOutBuffer], rax; String1
0x180043090  mov     ecx, [rcx+rdx]; int
0x180043093  call    RasLineGetID
0x180043098  mov     edi, eax
0x18004309a  test    eax, eax
0x18004309c  jz      loc_180043123
0x1800430a2  call    cs:__imp_GetLastError
0x1800430a9  nop     dword ptr [rax+rax+00h]
0x1800430ae  test    cs:byte_1800CF404, 8
0x1800430b5  mov     edi, eax
0x1800430b7  jz      loc_180043258
0x1800430bd  mov     edx, [rbx+60h]
0x1800430c0  lea     rcx, [rsp+940h+var_8EC+4]
0x1800430c5  mov     word ptr [rbp+840h+var_810], si
0x1800430c9  mov     word ptr [rsp+940h+var_8EC+4], si
0x1800430ce  call    ConvertPortNoToString
0x1800430d3  lea     rdx, aRaslinegetidFa; "RasLineGetID failed with error 0x%x"
0x1800430da  mov     r8d, edi
0x1800430dd  lea     rcx, [rbp+840h+var_810]
0x1800430e1  call    FormatRRASErrorString
0x1800430e6  test    cs:byte_1800CF404, 8
0x1800430ed  jz      loc_180043258
0x1800430f3  lea     rax, [rsp+940h+var_8EC+4]
0x1800430f8  mov     qword ptr [rsp+940h+nOutBufferSize], rax
0x1800430fd  lea     r9, [rsp+940h+BytesReturned+8]
0x180043102  lea     r8, [rbp+840h+var_810]
0x180043106  mov     [rsp+940h+lpOutBuffer], rsi
0x18004310b  lea     rdx, RasDdmParamTraceError
0x180043112  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180043119  call    McTemplateU0zjzz_EventWriteTransfer
0x18004311e  jmp     loc_180043258
0x180043123  mov     eax, [rbp+840h+var_86C]
0x180043126  lea     r8, [rbp+840h+OutBuffer]; lpInBuffer
0x18004312a  movups  xmm0, xmmword ptr [rbx+2CAh]
0x180043131  mov     [rsp+940h+lpOverlapped], rsi; lpOverlapped
0x180043136  mov     r9d, 40h ; '@'; nInBufferSize
0x18004313c  mov     edx, 120000h; dwIoControlCode
0x180043141  mov     rcx, [rbp+rax+840h+var_880]
0x180043146  mov     rax, [rbx+60h]
0x18004314a  mov     [rbp+840h+var_8A8], rax
0x18004314e  mov     [rbp+840h+var_8A0], rax
0x180043152  lea     rax, [rsp+940h+BytesReturned]
0x180043157  mov     [rsp+940h+lpBytesReturned], rax; lpBytesReturned
0x18004315c  lea     rax, [rbp+840h+OutBuffer]
0x180043160  mov     [rbp+840h+var_8B0], rcx
0x180043164  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x18004316b  mov     [rsp+940h+nOutBufferSize], 40h ; '@'; nOutBufferSize
0x180043173  mov     [rsp+940h+lpOutBuffer], rax; lpOutBuffer
0x180043178  mov     [rbp+840h+var_898], 10h
0x18004317f  movdqu  [rbp+840h+var_894], xmm0
0x180043184  call    cs:__imp_DeviceIoControl
0x18004318b  nop     dword ptr [rax+rax+00h]
0x180043190  test    eax, eax
0x180043192  jnz     short loc_1800431D1
0x180043194  call    cs:__imp_GetLastError
0x18004319b  nop     dword ptr [rax+rax+00h]
0x1800431a0  test    cs:byte_1800CF404, 8
0x1800431a7  mov     edi, eax
0x1800431a9  jz      loc_180043258
0x1800431af  mov     edx, [rbx+60h]
0x1800431b2  lea     rcx, [rsp+940h+var_8EC+4]
0x1800431b7  mov     word ptr [rbp+840h+var_810], si
0x1800431bb  mov     word ptr [rsp+940h+var_8EC+4], si
0x1800431c0  call    ConvertPortNoToString
0x1800431c5  lea     rdx, aIoctlNdiswanMa; "IOCTL_NDISWAN_MAP_CONNECTION_ID failed "...
0x1800431cc  jmp     loc_1800430DA
0x1800431d1  mov     rax, [rbp+840h+OutBuffer]
0x1800431d5  mov     [rbx+70h], rax
0x1800431d9  mov     rax, [rbp+840h+var_8B8]
0x1800431dd  mov     [rbx+78h], rax
0x1800431e1  cmp     cs:byte_1800CF998, sil
0x1800431e8  jnz     short loc_180043246
0x1800431ea  mov     rcx, cs:CompletionPort; CompletionPort
0x1800431f1  lea     r9, stru_1800CF8F8; lpOverlapped
0x1800431f8  xor     r8d, r8d; dwCompletionKey
0x1800431fb  xor     edx, edx; dwNumberOfBytesTransferred
0x1800431fd  call    cs:__imp_PostQueuedCompletionStatus
0x180043204  nop     dword ptr [rax+rax+00h]
0x180043209  test    eax, eax
0x18004320b  jnz     short loc_180043246
0x18004320d  call    cs:__imp_GetLastError
0x180043214  nop     dword ptr [rax+rax+00h]
0x180043219  test    cs:byte_1800CF404, 8
0x180043220  mov     edi, eax
0x180043222  jz      short loc_180043258
0x180043224  mov     edx, [rbx+60h]
0x180043227  lea     rcx, [rsp+940h+var_8EC+4]
0x18004322c  mov     word ptr [rbp+840h+var_810], si
0x180043230  mov     word ptr [rsp+940h+var_8EC+4], si
0x180043235  call    ConvertPortNoToString
0x18004323a  lea     rdx, aIoCompletionFo; "IO completion for PostRecvPkt failed wi"...
0x180043241  jmp     loc_1800430DA
0x180043246  cmp     word ptr [rbx+88h], 9
0x18004324e  jnz     short loc_180043258
0x180043250  mov     rcx, rbx; this
0x180043253  call    ?SaveIPSecInfo@DdmModernDevice@@QEAAXXZ; DdmModernDevice::SaveIPSecInfo(void)
0x180043258  mov     eax, edi
0x18004325a  mov     rcx, [rbp+840h+var_10]
0x180043261  xor     rcx, rsp; StackCookie
0x180043264  call    __security_check_cookie
0x180043269  lea     r11, [rsp+940h+var_s0]
0x180043271  mov     rbx, [r11+18h]
0x180043275  mov     rsi, [r11+20h]
0x180043279  mov     rdi, [r11+28h]
0x18004327d  mov     rsp, r11
0x180043280  pop     rbp
0x180043281  retn
```
