# CSNOCplCore::DisconnectWirelessConnection(_GUID const &,_GUID const &)

- ea: `0x180009aec`
- end: `0x180009c15`
- name: `?DisconnectWirelessConnection@CSNOCplCore@@AEAAJAEBU_GUID@@0@Z`
- size: `297`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, const struct _GUID *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d2e4`

## callees

- `0x180009aec`
- `0x18000ae44`
- `0x1800126b0`
- `0x180014274`

## import_xrefs

- `USER32!SetCursor` at `0x180009b23`
- `USER32!SetCursor` at `0x180009bea`
- `USER32!SetCursor` at `0x180009b23`
- `USER32!SetCursor` at `0x180009bea`
- `USER32!LoadCursorW` at `0x180009b1a`
- `USER32!LoadCursorW` at `0x180009b1a`
- `wlanapi!WlanDisconnect` at `0x180009b52`
- `wlanapi!WlanDisconnect` at `0x180009b52`
- `wlanapi!WlanOpenHandle` at `0x180009b3b`
- `wlanapi!WlanOpenHandle` at `0x180009b3b`
- `wlanapi!WlanCloseHandle` at `0x180009ba3`
- `wlanapi!WlanCloseHandle` at `0x180009ba3`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::DisconnectWirelessConnection(
        CSNOCplCore *this,
        const struct _GUID *a2,
        const struct _GUID *a3)
{
  HCURSOR CursorW; // rax
  HCURSOR v6; // rsi
  signed int v7; // eax
  DWORD v8; // ebx
  signed int v9; // eax
  HWND ParentWindow; // rax
  DWORD pdwNegotiatedVersion; // [rsp+48h] [rbp+10h] BYREF
  int v13; // [rsp+4Ch] [rbp+14h]
  void *phClientHandle; // [rsp+58h] [rbp+20h] BYREF

  v13 = HIDWORD(a2);
  phClientHandle = 0;
  pdwNegotiatedVersion = 0;
  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v6 = SetCursor(CursorW);
  v7 = WlanOpenHandle(1u, 0, &pdwNegotiatedVersion, &phClientHandle);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, v8);
  }
  else
  {
    v9 = WlanDisconnect(phClientHandle, a3, 0);
    if ( v9 )
    {
      v8 = v9 > 0 ? (unsigned __int16)v9 | 0x80070000 : v9;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, v8);
    }
    WlanCloseHandle(phClientHandle, 0);
  }
  SetCursor(v6);
  if ( (v8 & 0x80000000) != 0 )
  {
    ParentWindow = CSNOCplCore::GetParentWindow(this);
    ThrowErrorBox(ParentWindow, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x180009aec  mov     rax, rsp
0x180009aef  mov     [rax+8], rbx
0x180009af3  mov     [rax+10h], rdx
0x180009af7  push    rbp
0x180009af8  push    rsi
0x180009af9  push    rdi
0x180009afa  sub     rsp, 20h
0x180009afe  mov     rbp, rcx
0x180009b01  mov     qword ptr [rax+20h], 0
0x180009b09  xor     ecx, ecx; hInstance
0x180009b0b  mov     dword ptr [rax+10h], 0
0x180009b12  mov     edx, 7F02h; lpCursorName
0x180009b17  mov     rdi, r8
0x180009b1a  call    cs:__imp_LoadCursorW
0x180009b20  mov     rcx, rax; hCursor
0x180009b23  call    cs:__imp_SetCursor
0x180009b29  xor     edx, edx; pReserved
0x180009b2b  lea     r9, [rsp+38h+phClientHandle]; phClientHandle
0x180009b30  lea     r8, [rsp+38h+pdwNegotiatedVersion]; pdwNegotiatedVersion
0x180009b35  mov     rsi, rax
0x180009b38  lea     ecx, [rdx+1]; dwClientVersion
0x180009b3b  call    cs:__imp_WlanOpenHandle
0x180009b41  mov     ebx, eax
0x180009b43  test    eax, eax
0x180009b45  jnz     short loc_180009BAB
0x180009b47  mov     rcx, [rsp+38h+phClientHandle]; hClientHandle
0x180009b4c  xor     r8d, r8d; pReserved
0x180009b4f  mov     rdx, rdi; pInterfaceGuid
0x180009b52  call    cs:__imp_WlanDisconnect
0x180009b58  test    eax, eax
0x180009b5a  jz      short loc_180009B9C
0x180009b5c  jg      short loc_180009B62
0x180009b5e  mov     ebx, eax
0x180009b60  jmp     short loc_180009B6B
0x180009b62  movzx   ebx, ax
0x180009b65  or      ebx, 80070000h
0x180009b6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b72  lea     rax, WPP_GLOBAL_Control
0x180009b79  cmp     rcx, rax
0x180009b7c  jz      short loc_180009B9C
0x180009b7e  test    byte ptr [rcx+1Ch], 2
0x180009b82  jz      short loc_180009B9C
0x180009b84  mov     rcx, [rcx+10h]
0x180009b88  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180009b8f  mov     edx, 9Ah
0x180009b94  mov     r9d, ebx
0x180009b97  call    WPP_SF_d
0x180009b9c  mov     rcx, [rsp+38h+phClientHandle]; hClientHandle
0x180009ba1  xor     edx, edx; pReserved
0x180009ba3  call    cs:__imp_WlanCloseHandle
0x180009ba9  jmp     short loc_180009BE7
0x180009bab  jle     short loc_180009BB6
0x180009bad  movzx   ebx, ax
0x180009bb0  or      ebx, 80070000h
0x180009bb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bbd  lea     rax, WPP_GLOBAL_Control
0x180009bc4  cmp     rcx, rax
0x180009bc7  jz      short loc_180009BE7
0x180009bc9  test    byte ptr [rcx+1Ch], 2
0x180009bcd  jz      short loc_180009BE7
0x180009bcf  mov     rcx, [rcx+10h]
0x180009bd3  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180009bda  mov     edx, 9Bh
0x180009bdf  mov     r9d, ebx
0x180009be2  call    WPP_SF_d
0x180009be7  mov     rcx, rsi; hCursor
0x180009bea  call    cs:__imp_SetCursor
0x180009bf0  test    ebx, ebx
0x180009bf2  jns     short loc_180009C06
0x180009bf4  mov     rcx, rbp; this
0x180009bf7  call    ?GetParentWindow@CSNOCplCore@@QEAAPEAUHWND__@@XZ; CSNOCplCore::GetParentWindow(void)
0x180009bfc  mov     rcx, rax; hWnd
0x180009bff  mov     edx, ebx; dwMessageId
0x180009c01  call    ?ThrowErrorBox@@YAXQEAUHWND__@@J@Z; ThrowErrorBox(HWND__ * const,long)
0x180009c06  mov     eax, ebx
0x180009c08  mov     rbx, [rsp+38h+arg_0]
0x180009c0d  add     rsp, 20h
0x180009c11  pop     rdi
0x180009c12  pop     rsi
0x180009c13  pop     rbp
0x180009c14  retn
```
