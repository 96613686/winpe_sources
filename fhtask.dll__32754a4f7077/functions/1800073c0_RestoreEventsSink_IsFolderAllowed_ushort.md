# RestoreEventsSink::IsFolderAllowed(ushort *)

- ea: `0x1800073c0`
- end: `0x180007476`
- name: `?IsFolderAllowed@RestoreEventsSink@@UEAA_NPEAG@Z`
- size: `182`
- prototype: `char __fastcall(const WCHAR *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180005ea4`
- `0x1800073c0`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800073e6`
- `KERNEL32!CompareStringOrdinal` at `0x18000742c`
- `KERNEL32!CompareStringOrdinal` at `0x1800073e6`
- `KERNEL32!CompareStringOrdinal` at `0x18000742c`

## pseudocode

```c
char __fastcall RestoreEventsSink::IsFolderAllowed(const WCHAR *this, unsigned __int16 *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  const WCHAR *v6; // r8

  if ( CompareStringOrdinal(a2, -1, this + 28, -1, 1) == 2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return 0;
    v5 = 12;
LABEL_10:
    WPP_SF_(v4[2], v5, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids);
    return 0;
  }
  v6 = (const WCHAR *)*((_QWORD *)this + 6);
  if ( v6 && CompareStringOrdinal(a2, -1, v6, -1, 1) == 2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return 0;
    v5 = 13;
    goto LABEL_10;
  }
  return 1;
}

```

## disassembly

```asm
0x1800073c0  mov     [rsp+arg_0], rbx
0x1800073c5  push    rdi
0x1800073c6  sub     rsp, 30h
0x1800073ca  mov     rdi, rdx
0x1800073cd  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800073d5  or      r9d, 0FFFFFFFFh; cchCount2
0x1800073d9  lea     r8, [rcx+38h]; lpString2
0x1800073dd  mov     rbx, rcx
0x1800073e0  or      edx, r9d; cchCount1
0x1800073e3  mov     rcx, rdi; lpString1
0x1800073e6  call    cs:__imp_CompareStringOrdinal
0x1800073ec  cmp     eax, 2
0x1800073ef  jnz     short loc_180007411
0x1800073f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073f8  lea     rax, WPP_GLOBAL_Control
0x1800073ff  cmp     rcx, rax
0x180007402  jz      short loc_180007465
0x180007404  test    byte ptr [rcx+1Ch], 8
0x180007408  jz      short loc_180007465
0x18000740a  mov     edx, 0Ch
0x18000740f  jmp     short loc_180007455
0x180007411  mov     r8, [rbx+30h]; lpString2
0x180007415  test    r8, r8
0x180007418  jz      short loc_180007469
0x18000741a  or      r9d, 0FFFFFFFFh; cchCount2
0x18000741e  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180007426  or      edx, r9d; cchCount1
0x180007429  mov     rcx, rdi; lpString1
0x18000742c  call    cs:__imp_CompareStringOrdinal
0x180007432  cmp     eax, 2
0x180007435  jnz     short loc_180007469
0x180007437  mov     rcx, cs:WPP_GLOBAL_Control
0x18000743e  lea     rax, WPP_GLOBAL_Control
0x180007445  cmp     rcx, rax
0x180007448  jz      short loc_180007465
0x18000744a  test    byte ptr [rcx+1Ch], 8
0x18000744e  jz      short loc_180007465
0x180007450  mov     edx, 0Dh
0x180007455  mov     rcx, [rcx+10h]
0x180007459  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x180007460  call    WPP_SF_
0x180007465  xor     al, al
0x180007467  jmp     short loc_18000746B
0x180007469  mov     al, 1
0x18000746b  mov     rbx, [rsp+38h+arg_0]
0x180007470  add     rsp, 30h
0x180007474  pop     rdi
0x180007475  retn
```
