# DockCache::FindDock(ushort const *,Dock * *)

- ea: `0x180011c2c`
- end: `0x180011d7d`
- name: `?FindDock@DockCache@@AEAAJPEBGPEAPEAVDock@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(DockCache *this, const unsigned __int16 *, struct Dock **)`
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a810`
- `0x18000c6e4`
- `0x18000e7d0`
- `0x180011550`
- `0x180011808`
- `0x180011994`
- `0x180011d84`
- `0x180012110`
- `0x1800123fc`
- `0x180012698`
- `0x180012860`
- `0x180012ba0`

## callees

- `0x18000cb40`
- `0x180011c2c`
- `0x180013600`
- `0x18001ca4a`

## import_xrefs

- `msvcrt!wcsstr` at `0x180011c9c`
- `msvcrt!wcsstr` at `0x180011c9c`

## pseudocode

```c
__int64 __fastcall DockCache::FindDock(DockCache *this, const unsigned __int16 *a2, struct Dock **a3)
{
  _QWORD *v6; // rcx
  struct Dock *i; // rbx
  wchar_t *v8; // rax
  int v9; // r8d

  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids,
      (_DWORD)this,
      (__int64)a2);
    v6 = WPP_GLOBAL_Control;
  }
  for ( i = (struct Dock *)*((_QWORD *)this + 5); i != *((struct Dock **)this + 6); i = (struct Dock *)((char *)i + 2936) )
  {
    v8 = wcsstr(a2, L"WirelessDocking#(");
    if ( v8 && i && !wcsncmp_0((const wchar_t *)i, v8, 0x125u) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qqS(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, v9, (_DWORD)this, (char)i, (__int64)a2);
      }
      *a3 = i;
      return 0;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_qqS(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, v9, (_DWORD)this, (char)i, (__int64)a2);
      v6 = WPP_GLOBAL_Control;
    }
  }
  if ( v6 != &WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 3u && (*((_BYTE *)v6 + 28) & 1) != 0 )
    WPP_SF_qS(v6[2], 59, (unsigned int)&WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids, (_DWORD)this, (__int64)a2);
  return 2147943568LL;
}

```

## disassembly

```asm
0x180011c2c  push    rbx
0x180011c2e  push    rsi
0x180011c2f  push    rdi
0x180011c30  push    r14
0x180011c32  push    r15
0x180011c34  sub     rsp, 30h
0x180011c38  mov     r14, r8
0x180011c3b  mov     rsi, rdx
0x180011c3e  mov     rdi, rcx
0x180011c41  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c48  lea     r15, WPP_GLOBAL_Control
0x180011c4f  cmp     rcx, r15
0x180011c52  jz      short loc_180011C84
0x180011c54  cmp     byte ptr [rcx+19h], 3
0x180011c58  jb      short loc_180011C84
0x180011c5a  test    byte ptr [rcx+1Ch], 1
0x180011c5e  jz      short loc_180011C84
0x180011c60  mov     rcx, [rcx+10h]
0x180011c64  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x180011c6b  mov     edx, 38h ; '8'
0x180011c70  mov     [rsp+58h+var_38], rsi
0x180011c75  mov     r9, rdi
0x180011c78  call    WPP_SF_qS
0x180011c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c84  mov     rbx, [rdi+28h]
0x180011c88  cmp     rbx, [rdi+30h]
0x180011c8c  jz      loc_180011D3E
0x180011c92  lea     rdx, aWirelessdockin_0; "WirelessDocking#("
0x180011c99  mov     rcx, rsi; Str
0x180011c9c  call    cs:__imp_wcsstr
0x180011ca2  test    rax, rax
0x180011ca5  jz      short loc_180011CC1
0x180011ca7  test    rbx, rbx
0x180011caa  jz      short loc_180011CC1
0x180011cac  mov     r8d, 125h; MaxCount
0x180011cb2  mov     rdx, rax; String2
0x180011cb5  mov     rcx, rbx; String1
0x180011cb8  call    wcsncmp_0
0x180011cbd  test    eax, eax
0x180011cbf  jz      short loc_180011D04
0x180011cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180011cc8  cmp     rcx, r15
0x180011ccb  jz      short loc_180011CFB
0x180011ccd  cmp     byte ptr [rcx+19h], 4
0x180011cd1  jb      short loc_180011CFB
0x180011cd3  test    byte ptr [rcx+1Ch], 1
0x180011cd7  jz      short loc_180011CFB
0x180011cd9  mov     rcx, [rcx+10h]
0x180011cdd  mov     edx, 3Ah ; ':'
0x180011ce2  mov     [rsp+58h+var_30], rsi
0x180011ce7  mov     r9, rdi
0x180011cea  mov     [rsp+58h+var_38], rbx
0x180011cef  call    WPP_SF_qqS
0x180011cf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011cfb  add     rbx, 0B78h
0x180011d02  jmp     short loc_180011C88
0x180011d04  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d0b  cmp     rcx, r15
0x180011d0e  jz      short loc_180011D37
0x180011d10  cmp     byte ptr [rcx+19h], 3
0x180011d14  jb      short loc_180011D37
0x180011d16  test    byte ptr [rcx+1Ch], 1
0x180011d1a  jz      short loc_180011D37
0x180011d1c  mov     rcx, [rcx+10h]
0x180011d20  mov     edx, 39h ; '9'
0x180011d25  mov     [rsp+58h+var_30], rsi
0x180011d2a  mov     r9, rdi
0x180011d2d  mov     [rsp+58h+var_38], rbx
0x180011d32  call    WPP_SF_qqS
0x180011d37  mov     [r14], rbx
0x180011d3a  xor     eax, eax
0x180011d3c  jmp     short loc_180011D71
0x180011d3e  cmp     rcx, r15
0x180011d41  jz      short loc_180011D6C
0x180011d43  cmp     byte ptr [rcx+19h], 3
0x180011d47  jb      short loc_180011D6C
0x180011d49  test    byte ptr [rcx+1Ch], 1
0x180011d4d  jz      short loc_180011D6C
0x180011d4f  mov     rcx, [rcx+10h]
0x180011d53  lea     r8, WPP_e25d9f3a37553da522cce38d6b52f14d_Traceguids
0x180011d5a  mov     edx, 3Bh ; ';'
0x180011d5f  mov     [rsp+58h+var_38], rsi
0x180011d64  mov     r9, rdi
0x180011d67  call    WPP_SF_qS
0x180011d6c  mov     eax, 80070490h
0x180011d71  add     rsp, 30h
0x180011d75  pop     r15
0x180011d77  pop     r14
0x180011d79  pop     rdi
0x180011d7a  pop     rsi
0x180011d7b  pop     rbx
0x180011d7c  retn
```
