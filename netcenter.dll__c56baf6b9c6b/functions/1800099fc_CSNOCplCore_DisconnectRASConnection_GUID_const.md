# CSNOCplCore::DisconnectRASConnection(_GUID const &)

- ea: `0x1800099fc`
- end: `0x180009ae5`
- name: `?DisconnectRASConnection@CSNOCplCore@@AEAAXAEBU_GUID@@@Z`
- size: `233`
- prototype: `void __fastcall(CSNOCplCore *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d2e4`

## callees

- `0x1800099fc`
- `0x18000ae44`
- `0x180010e9c`
- `0x180014274`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009a16`
- `SHLWAPI!__imp_SHCreateThread` at `0x180009a4f`
- `SHLWAPI!__imp_SHCreateThread` at `0x180009a4f`

## pseudocode

```c
void __fastcall CSNOCplCore::DisconnectRASConnection(CSNOCplCore *this, const struct _GUID *a2)
{
  _OWORD *v4; // rax
  void *v5; // rbx
  __int128 v6; // xmm0
  unsigned int Error; // eax

  v4 = CoTaskMemAlloc(0x20u);
  v5 = v4;
  if ( v4 )
  {
    v6 = (__int128)*a2;
    *((_DWORD *)v4 + 4) = 0;
    *v4 = v6;
    *((_QWORD *)v4 + 3) = CSNOCplCore::GetParentWindow(this);
    if ( !SHCreateThread((LPTHREAD_START_ROUTINE)OnInvokeNetshellCommandThread, v5, 8u, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        Error = ResultFromKnownLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, Error);
      }
      CoTaskMemFree(v5);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, 2147942414LL);
  }
}

```

## disassembly

```asm
0x1800099fc  mov     [rsp+arg_0], rbx
0x180009a01  mov     [rsp+arg_8], rsi
0x180009a06  push    rdi
0x180009a07  sub     rsp, 20h
0x180009a0b  mov     rsi, rcx
0x180009a0e  mov     rdi, rdx
0x180009a11  mov     ecx, 20h ; ' '; cb
0x180009a16  call    cs:__imp_CoTaskMemAlloc
0x180009a1c  mov     rbx, rax
0x180009a1f  test    rax, rax
0x180009a22  jz      short loc_180009AA1
0x180009a24  movups  xmm0, xmmword ptr [rdi]
0x180009a27  mov     rcx, rsi; this
0x180009a2a  mov     dword ptr [rax+10h], 0
0x180009a31  movdqu  xmmword ptr [rax], xmm0
0x180009a35  call    ?GetParentWindow@CSNOCplCore@@QEAAPEAUHWND__@@XZ; CSNOCplCore::GetParentWindow(void)
0x180009a3a  xor     r9d, r9d; pfnCallback
0x180009a3d  mov     [rbx+18h], rax
0x180009a41  mov     rdx, rbx; pData
0x180009a44  lea     rcx, ?OnInvokeNetshellCommandThread@@YAKPEAX@Z; pfnThreadProc
0x180009a4b  lea     r8d, [r9+8]; flags
0x180009a4f  call    cs:__imp_SHCreateThread
0x180009a55  test    eax, eax
0x180009a57  jnz     short loc_180009AD5
0x180009a59  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a60  lea     rax, WPP_GLOBAL_Control
0x180009a67  cmp     rcx, rax
0x180009a6a  jz      short loc_180009A96
0x180009a6c  test    byte ptr [rcx+1Ch], 2
0x180009a70  jz      short loc_180009A96
0x180009a72  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180009a77  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a7e  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180009a85  mov     edx, 9Ch
0x180009a8a  mov     r9d, eax
0x180009a8d  mov     rcx, [rcx+10h]
0x180009a91  call    WPP_SF_d
0x180009a96  mov     rcx, rbx; pv
0x180009a99  call    cs:__imp_CoTaskMemFree
0x180009a9f  jmp     short loc_180009AD5
0x180009aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009aa8  lea     rax, WPP_GLOBAL_Control
0x180009aaf  cmp     rcx, rax
0x180009ab2  jz      short loc_180009AD5
0x180009ab4  test    byte ptr [rcx+1Ch], 2
0x180009ab8  jz      short loc_180009AD5
0x180009aba  mov     rcx, [rcx+10h]
0x180009abe  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180009ac5  mov     edx, 9Dh
0x180009aca  mov     r9d, 8007000Eh
0x180009ad0  call    WPP_SF_d
0x180009ad5  mov     rbx, [rsp+28h+arg_0]
0x180009ada  mov     rsi, [rsp+28h+arg_8]
0x180009adf  add     rsp, 20h
0x180009ae3  pop     rdi
0x180009ae4  retn
```
