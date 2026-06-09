# StartList::GetSessionValue(ushort *,uint,ATL::CRegKey &,bool)

- ea: `0x14001eb30`
- end: `0x14001ec26`
- name: `?GetSessionValue@StartList@@AEBAXPEAGIAEAVCRegKey@ATL@@_N@Z`
- size: `246`
- prototype: `void(StartList *__hidden this, unsigned __int16 *, unsigned int, struct ATL::CRegKey *, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14001dccc`
- `0x14001f728`

## callees

- `0x140007e90`
- `0x140009524`
- `0x14000df20`
- `0x14001c8a8`
- `0x14001caa4`
- `0x14001eb30`

## string_xrefs

- `0x14001ebc6`: `SecureConfiguration`
- `0x14001ebbf`: `Configuration`

## pseudocode

```c
void __fastcall StartList::GetSessionValue(
        StartList *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct ATL::CRegKey *a4,
        bool a5)
{
  LPCWSTR *v7; // rax
  unsigned int v8; // edi
  const unsigned __int16 *v9; // rdx
  unsigned int v10; // eax
  StartList *v11; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v12; // [rsp+50h] [rbp+18h] BYREF

  v12 = a3;
  v11 = this;
  *a2 = 0;
  v7 = (LPCWSTR *)CATUtils::SessionKeyString((__int64)&v11);
  v8 = ATL::CRegKey::Open(a4, HKEY_LOCAL_MACHINE, *v7, 0x2001Fu);
  ATL::CStringData::Release((StartList *)((char *)v11 - 24));
  if ( v8 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v8);
  v12 = 1024;
  v9 = L"SecureConfiguration";
  if ( !a5 )
    v9 = L"Configuration";
  v10 = ATL::CRegKey::QueryStringValue(a4, v9, a2, &v12);
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids, v10);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x14001eb30  mov     r11, rsp
0x14001eb33  mov     [r11+10h], rbx
0x14001eb37  mov     [r11+18h], r8d
0x14001eb3b  mov     [r11+8], rcx
0x14001eb3f  push    rbp
0x14001eb40  push    rsi
0x14001eb41  push    rdi
0x14001eb42  sub     rsp, 20h
0x14001eb46  mov     rsi, r9
0x14001eb49  mov     rbx, rdx
0x14001eb4c  xor     eax, eax
0x14001eb4e  mov     [rdx], ax
0x14001eb51  lea     rcx, [r11+8]
0x14001eb55  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x14001eb5a  mov     r9d, 2001Fh; unsigned int
0x14001eb60  mov     r8, [rax]; lpSubKey
0x14001eb63  mov     rdx, 0FFFFFFFF80000002h; hKey
0x14001eb6a  mov     rcx, rsi; this
0x14001eb6d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001eb72  mov     edi, eax
0x14001eb74  mov     rcx, [rsp+38h+arg_0]
0x14001eb79  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14001eb7d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14001eb82  lea     rbp, WPP_GLOBAL_Control
0x14001eb89  test    edi, edi
0x14001eb8b  jz      short loc_14001EBB7
0x14001eb8d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eb94  cmp     rcx, rbp
0x14001eb97  jz      short loc_14001EBB7
0x14001eb99  test    byte ptr [rcx+1Ch], 8
0x14001eb9d  jz      short loc_14001EBB7
0x14001eb9f  mov     edx, 20h ; ' '
0x14001eba4  mov     r9d, edi
0x14001eba7  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001ebae  mov     rcx, [rcx+10h]
0x14001ebb2  call    WPP_SF_d
0x14001ebb7  mov     [rsp+38h+arg_10], 400h
0x14001ebbf  lea     rax, aConfiguration_1; "Configuration"
0x14001ebc6  lea     rdx, aSecureconfigur_0; "SecureConfiguration"
0x14001ebcd  cmp     [rsp+38h+arg_20], 0
0x14001ebd2  cmovz   rdx, rax; unsigned __int16 *
0x14001ebd6  lea     r9, [rsp+38h+arg_10]; unsigned int *
0x14001ebdb  mov     r8, rbx; unsigned __int16 *
0x14001ebde  mov     rcx, rsi; this
0x14001ebe1  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14001ebe6  test    eax, eax
0x14001ebe8  jz      short loc_14001EC19
0x14001ebea  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ebf1  cmp     rcx, rbp
0x14001ebf4  jz      short loc_14001EC14
0x14001ebf6  test    byte ptr [rcx+1Ch], 8
0x14001ebfa  jz      short loc_14001EC14
0x14001ebfc  mov     edx, 21h ; '!'
0x14001ec01  mov     r9d, eax
0x14001ec04  lea     r8, WPP_0cfc691c390c3581aa6c7b8081e34e7b_Traceguids
0x14001ec0b  mov     rcx, [rcx+10h]
0x14001ec0f  call    WPP_SF_d
0x14001ec14  xor     eax, eax
0x14001ec16  mov     [rbx], ax
0x14001ec19  mov     rbx, [rsp+38h+arg_8]
0x14001ec1e  add     rsp, 20h
0x14001ec22  pop     rdi
0x14001ec23  pop     rsi
0x14001ec24  pop     rbp
0x14001ec25  retn
```
