# StartList::GetUserValue(ushort *,uint,ATL::CRegKey &)

- ea: `0x14001ef2c`
- end: `0x14001f057`
- name: `?GetUserValue@StartList@@AEAAJPEAGIAEAVCRegKey@ATL@@@Z`
- size: `299`
- prototype: `int(StartList *__hidden this, unsigned __int16 *, unsigned int, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001f728`

## callees

- `0x140007e90`
- `0x14000df20`
- `0x14001c8a8`
- `0x14001ef2c`

## string_xrefs

- `0x14001efc2`: `Configuration`
- `0x14001ef43`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`

## pseudocode

```c
__int64 __fastcall StartList::GetUserValue(
        StartList *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct ATL::CRegKey *a4)
{
  int v6; // ebx
  unsigned int v8; // eax
  unsigned int v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = a3;
  *a2 = 0;
  v6 = ATL::CRegKey::Open(a4, HKEY_CURRENT_USER, StartList::_accessibilityKeyString, 0x20019u);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids,
        (unsigned int)v6);
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
    return (unsigned int)v6;
  }
  else
  {
    v9 = 1024;
    v8 = ATL::CRegKey::QueryStringValue(a4, L"Configuration", a2, &v9);
    if ( v8 == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8 + 35, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v8);
      return 2147942402LL;
    }
    else
    {
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v8);
        *a2 = 0;
      }
      return 0;
    }
  }
}

```

## disassembly

```asm
0x14001ef2c  mov     [rsp+arg_0], rbx
0x14001ef31  mov     [rsp+arg_8], rsi
0x14001ef36  mov     [rsp+arg_10], r8d
0x14001ef3b  push    rdi
0x14001ef3c  sub     rsp, 20h
0x14001ef40  mov     rsi, r9
0x14001ef43  lea     r8, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001ef4a  xor     eax, eax
0x14001ef4c  mov     rdi, rdx
0x14001ef4f  mov     [rdx], ax
0x14001ef52  mov     r9d, 20019h; unsigned int
0x14001ef58  mov     rdx, 0FFFFFFFF80000001h; hKey
0x14001ef5f  mov     rcx, rsi; this
0x14001ef62  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001ef67  mov     ebx, eax
0x14001ef69  test    eax, eax
0x14001ef6b  jz      short loc_14001EFB2
0x14001ef6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ef74  lea     rax, WPP_GLOBAL_Control
0x14001ef7b  cmp     rcx, rax
0x14001ef7e  jz      short loc_14001EF9E
0x14001ef80  test    byte ptr [rcx+1Ch], 8
0x14001ef84  jz      short loc_14001EF9E
0x14001ef86  mov     rcx, [rcx+10h]
0x14001ef8a  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001ef91  mov     edx, 24h ; '$'
0x14001ef96  mov     r9d, ebx
0x14001ef99  call    WPP_SF_d
0x14001ef9e  test    ebx, ebx
0x14001efa0  jle     short loc_14001EFAB
0x14001efa2  movzx   ebx, bx
0x14001efa5  or      ebx, 80070000h
0x14001efab  mov     eax, ebx
0x14001efad  jmp     loc_14001F047
0x14001efb2  lea     r9, [rsp+28h+arg_10]; unsigned int *
0x14001efb7  mov     [rsp+28h+arg_10], 400h
0x14001efbf  mov     r8, rdi; unsigned __int16 *
0x14001efc2  lea     rdx, aConfiguration; "Configuration"
0x14001efc9  mov     rcx, rsi; this
0x14001efcc  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14001efd1  mov     r9d, eax
0x14001efd4  cmp     eax, 2
0x14001efd7  jnz     short loc_14001F00D
0x14001efd9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001efe0  lea     rax, WPP_GLOBAL_Control
0x14001efe7  cmp     rcx, rax
0x14001efea  jz      short loc_14001F006
0x14001efec  test    byte ptr [rcx+1Ch], 8
0x14001eff0  jz      short loc_14001F006
0x14001eff2  mov     rcx, [rcx+10h]
0x14001eff6  lea     edx, [r9+23h]
0x14001effa  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001f001  call    WPP_SF_d
0x14001f006  mov     eax, 80070002h
0x14001f00b  jmp     short loc_14001F047
0x14001f00d  test    r9d, r9d
0x14001f010  jz      short loc_14001F045
0x14001f012  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f019  lea     rax, WPP_GLOBAL_Control
0x14001f020  cmp     rcx, rax
0x14001f023  jz      short loc_14001F040
0x14001f025  test    byte ptr [rcx+1Ch], 8
0x14001f029  jz      short loc_14001F040
0x14001f02b  mov     rcx, [rcx+10h]
0x14001f02f  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001f036  mov     edx, 26h ; '&'
0x14001f03b  call    WPP_SF_d
0x14001f040  xor     eax, eax
0x14001f042  mov     [rdi], ax
0x14001f045  xor     eax, eax
0x14001f047  mov     rbx, [rsp+28h+arg_0]
0x14001f04c  mov     rsi, [rsp+28h+arg_8]
0x14001f051  add     rsp, 20h
0x14001f055  pop     rdi
0x14001f056  retn
```
