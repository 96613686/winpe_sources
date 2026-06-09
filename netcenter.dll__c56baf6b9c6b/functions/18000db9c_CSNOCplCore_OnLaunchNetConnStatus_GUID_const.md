# CSNOCplCore::OnLaunchNetConnStatus(_GUID const &)

- ea: `0x18000db9c`
- end: `0x18000dc85`
- name: `?OnLaunchNetConnStatus@CSNOCplCore@@AEAAXAEBU_GUID@@@Z`
- size: `233`
- prototype: `void __fastcall(CSNOCplCore *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d2e4`

## callees

- `0x18000ae44`
- `0x18000db9c`
- `0x180010e9c`
- `0x180014274`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dc39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dbb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dbb6`
- `SHLWAPI!__imp_SHCreateThread` at `0x18000dbef`
- `SHLWAPI!__imp_SHCreateThread` at `0x18000dbef`

## pseudocode

```c
void __fastcall CSNOCplCore::OnLaunchNetConnStatus(CSNOCplCore *this, const struct _GUID *a2)
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
    *((_DWORD *)v4 + 4) = 1;
    *v4 = v6;
    *((_QWORD *)v4 + 3) = CSNOCplCore::GetParentWindow(this);
    if ( !SHCreateThread((LPTHREAD_START_ROUTINE)OnInvokeNetshellCommandThread, v5, 8u, 0) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        Error = ResultFromKnownLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, Error);
      }
      CoTaskMemFree(v5);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, 2147942414LL);
  }
}

```

## disassembly

```asm
0x18000db9c  mov     [rsp+arg_0], rbx
0x18000dba1  mov     [rsp+arg_8], rsi
0x18000dba6  push    rdi
0x18000dba7  sub     rsp, 20h
0x18000dbab  mov     rsi, rcx
0x18000dbae  mov     rdi, rdx
0x18000dbb1  mov     ecx, 20h ; ' '; cb
0x18000dbb6  call    cs:__imp_CoTaskMemAlloc
0x18000dbbc  mov     rbx, rax
0x18000dbbf  test    rax, rax
0x18000dbc2  jz      short loc_18000DC41
0x18000dbc4  movups  xmm0, xmmword ptr [rdi]
0x18000dbc7  mov     rcx, rsi; this
0x18000dbca  mov     dword ptr [rax+10h], 1
0x18000dbd1  movdqu  xmmword ptr [rax], xmm0
0x18000dbd5  call    ?GetParentWindow@CSNOCplCore@@QEAAPEAUHWND__@@XZ; CSNOCplCore::GetParentWindow(void)
0x18000dbda  xor     r9d, r9d; pfnCallback
0x18000dbdd  mov     [rbx+18h], rax
0x18000dbe1  mov     rdx, rbx; pData
0x18000dbe4  lea     rcx, ?OnInvokeNetshellCommandThread@@YAKPEAX@Z; pfnThreadProc
0x18000dbeb  lea     r8d, [r9+8]; flags
0x18000dbef  call    cs:__imp_SHCreateThread
0x18000dbf5  test    eax, eax
0x18000dbf7  jnz     short loc_18000DC75
0x18000dbf9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc00  lea     rax, WPP_GLOBAL_Control
0x18000dc07  cmp     rcx, rax
0x18000dc0a  jz      short loc_18000DC36
0x18000dc0c  test    byte ptr [rcx+1Ch], 2
0x18000dc10  jz      short loc_18000DC36
0x18000dc12  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000dc17  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc1e  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000dc25  mov     edx, 6Bh ; 'k'
0x18000dc2a  mov     r9d, eax
0x18000dc2d  mov     rcx, [rcx+10h]
0x18000dc31  call    WPP_SF_d
0x18000dc36  mov     rcx, rbx; pv
0x18000dc39  call    cs:__imp_CoTaskMemFree
0x18000dc3f  jmp     short loc_18000DC75
0x18000dc41  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc48  lea     rax, WPP_GLOBAL_Control
0x18000dc4f  cmp     rcx, rax
0x18000dc52  jz      short loc_18000DC75
0x18000dc54  test    byte ptr [rcx+1Ch], 2
0x18000dc58  jz      short loc_18000DC75
0x18000dc5a  mov     rcx, [rcx+10h]
0x18000dc5e  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000dc65  mov     edx, 6Ch ; 'l'
0x18000dc6a  mov     r9d, 8007000Eh
0x18000dc70  call    WPP_SF_d
0x18000dc75  mov     rbx, [rsp+28h+arg_0]
0x18000dc7a  mov     rsi, [rsp+28h+arg_8]
0x18000dc7f  add     rsp, 20h
0x18000dc83  pop     rdi
0x18000dc84  retn
```
