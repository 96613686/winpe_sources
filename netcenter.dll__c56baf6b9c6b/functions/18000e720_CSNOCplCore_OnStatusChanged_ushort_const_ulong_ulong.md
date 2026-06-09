# CSNOCplCore::OnStatusChanged(ushort const *,ulong,ulong)

- ea: `0x18000e720`
- end: `0x18000e988`
- name: `?OnStatusChanged@CSNOCplCore@@UEAAJPEBGKK@Z`
- size: `616`
- prototype: `int(CSNOCplCore *__hidden this, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006b70`
- `0x18000e720`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e763`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e7bb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e815`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e876`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e8ce`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e925`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e763`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e7bb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e815`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e876`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e8ce`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e925`
- `USER32!PostMessageW` at `0x18000e970`
- `USER32!PostMessageW` at `0x18000e970`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::OnStatusChanged(HWND *this, const unsigned __int16 *a2, __int64 a3, int a4)
{
  int v6; // r9d
  UINT v7; // edx

  v6 = a4 - 1;
  if ( v6 )
  {
    if ( v6 == 3 )
    {
      if ( CompareStringOrdinal(a2, -1, L"netprofm", -1, 1) == 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
        v7 = 32770;
LABEL_33:
        PostMessageW(this[19], v7, 0, 0);
        return 0;
      }
      if ( CompareStringOrdinal(a2, -1, L"netman", -1, 1) == 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
        v7 = 32773;
        goto LABEL_33;
      }
      if ( CompareStringOrdinal(a2, -1, L"wlansvc", -1, 1) == 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
        v7 = 32775;
        goto LABEL_33;
      }
    }
  }
  else
  {
    if ( CompareStringOrdinal(a2, -1, L"netprofm", -1, 1) == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
      v7 = 32769;
      goto LABEL_33;
    }
    if ( CompareStringOrdinal(a2, -1, L"netman", -1, 1) == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
      v7 = 32772;
      goto LABEL_33;
    }
    if ( CompareStringOrdinal(a2, -1, L"wlansvc", -1, 1) == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
      v7 = 32774;
      goto LABEL_33;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000e720  mov     [rsp+arg_0], rbx
0x18000e725  mov     [rsp+arg_8], rbp
0x18000e72a  push    rdi
0x18000e72b  sub     rsp, 30h
0x18000e72f  mov     rbp, rdx
0x18000e732  mov     rdi, rcx
0x18000e735  sub     r9d, 1
0x18000e739  jz      loc_18000E85C
0x18000e73f  cmp     r9d, 3
0x18000e743  jnz     loc_18000E976
0x18000e749  or      ebx, 0FFFFFFFFh
0x18000e74c  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000e754  mov     r9d, ebx; cchCount2
0x18000e757  lea     r8, ServiceName; "netprofm"
0x18000e75e  mov     edx, ebx; cchCount1
0x18000e760  mov     rcx, rbp; lpString1
0x18000e763  call    cs:__imp_CompareStringOrdinal
0x18000e769  cmp     eax, 2
0x18000e76c  jnz     short loc_18000E7A4
0x18000e76e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e775  lea     rax, WPP_GLOBAL_Control
0x18000e77c  cmp     rcx, rax
0x18000e77f  jz      short loc_18000E79A
0x18000e781  test    byte ptr [rcx+1Ch], 8
0x18000e785  jz      short loc_18000E79A
0x18000e787  mov     rcx, [rcx+10h]
0x18000e78b  lea     edx, [rbx+38h]
0x18000e78e  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000e795  call    WPP_SF_
0x18000e79a  mov     edx, 8002h
0x18000e79f  jmp     loc_18000E963
0x18000e7a4  mov     r9d, ebx; cchCount2
0x18000e7a7  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000e7af  lea     r8, aNetman; "netman"
0x18000e7b6  mov     edx, ebx; cchCount1
0x18000e7b8  mov     rcx, rbp; lpString1
0x18000e7bb  call    cs:__imp_CompareStringOrdinal
0x18000e7c1  cmp     eax, 2
0x18000e7c4  jnz     short loc_18000E7FE
0x18000e7c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e7cd  lea     rax, WPP_GLOBAL_Control
0x18000e7d4  cmp     rcx, rax
0x18000e7d7  jz      short loc_18000E7F4
0x18000e7d9  test    byte ptr [rcx+1Ch], 8
0x18000e7dd  jz      short loc_18000E7F4
0x18000e7df  mov     rcx, [rcx+10h]
0x18000e7e3  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000e7ea  mov     edx, 38h ; '8'
0x18000e7ef  call    WPP_SF_
0x18000e7f4  mov     edx, 8005h
0x18000e7f9  jmp     loc_18000E963
0x18000e7fe  mov     r9d, ebx; cchCount2
0x18000e801  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000e809  lea     r8, aWlansvc; "wlansvc"
0x18000e810  mov     edx, ebx; cchCount1
0x18000e812  mov     rcx, rbp; lpString1
0x18000e815  call    cs:__imp_CompareStringOrdinal
0x18000e81b  cmp     eax, 2
0x18000e81e  jnz     loc_18000E976
0x18000e824  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e82b  lea     rax, WPP_GLOBAL_Control
0x18000e832  cmp     rcx, rax
0x18000e835  jz      short loc_18000E852
0x18000e837  test    byte ptr [rcx+1Ch], 8
0x18000e83b  jz      short loc_18000E852
0x18000e83d  mov     rcx, [rcx+10h]
0x18000e841  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000e848  mov     edx, 39h ; '9'
0x18000e84d  call    WPP_SF_
0x18000e852  mov     edx, 8007h
0x18000e857  jmp     loc_18000E963
0x18000e85c  or      ebx, 0FFFFFFFFh
0x18000e85f  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000e867  mov     r9d, ebx; cchCount2
0x18000e86a  lea     r8, ServiceName; "netprofm"
0x18000e871  mov     edx, ebx; cchCount1
0x18000e873  mov     rcx, rbp; lpString1
0x18000e876  call    cs:__imp_CompareStringOrdinal
0x18000e87c  cmp     eax, 2
0x18000e87f  jnz     short loc_18000E8B7
0x18000e881  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e888  lea     rax, WPP_GLOBAL_Control
0x18000e88f  cmp     rcx, rax
0x18000e892  jz      short loc_18000E8AD
0x18000e894  test    byte ptr [rcx+1Ch], 8
0x18000e898  jz      short loc_18000E8AD
0x18000e89a  mov     rcx, [rcx+10h]
0x18000e89e  lea     edx, [rbx+3Bh]
0x18000e8a1  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000e8a8  call    WPP_SF_
0x18000e8ad  mov     edx, 8001h
0x18000e8b2  jmp     loc_18000E963
0x18000e8b7  mov     r9d, ebx; cchCount2
0x18000e8ba  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000e8c2  lea     r8, aNetman; "netman"
0x18000e8c9  mov     edx, ebx; cchCount1
0x18000e8cb  mov     rcx, rbp; lpString1
0x18000e8ce  call    cs:__imp_CompareStringOrdinal
0x18000e8d4  cmp     eax, 2
0x18000e8d7  jnz     short loc_18000E90E
0x18000e8d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e8e0  lea     rax, WPP_GLOBAL_Control
0x18000e8e7  cmp     rcx, rax
0x18000e8ea  jz      short loc_18000E907
0x18000e8ec  test    byte ptr [rcx+1Ch], 8
0x18000e8f0  jz      short loc_18000E907
0x18000e8f2  mov     rcx, [rcx+10h]
0x18000e8f6  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000e8fd  mov     edx, 3Bh ; ';'
0x18000e902  call    WPP_SF_
0x18000e907  mov     edx, 8004h
0x18000e90c  jmp     short loc_18000E963
0x18000e90e  mov     r9d, ebx; cchCount2
0x18000e911  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000e919  lea     r8, aWlansvc; "wlansvc"
0x18000e920  mov     edx, ebx; cchCount1
0x18000e922  mov     rcx, rbp; lpString1
0x18000e925  call    cs:__imp_CompareStringOrdinal
0x18000e92b  cmp     eax, 2
0x18000e92e  jnz     short loc_18000E976
0x18000e930  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e937  lea     rax, WPP_GLOBAL_Control
0x18000e93e  cmp     rcx, rax
0x18000e941  jz      short loc_18000E95E
0x18000e943  test    byte ptr [rcx+1Ch], 8
0x18000e947  jz      short loc_18000E95E
0x18000e949  mov     rcx, [rcx+10h]
0x18000e94d  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000e954  mov     edx, 3Ch ; '<'
0x18000e959  call    WPP_SF_
0x18000e95e  mov     edx, 8006h; Msg
0x18000e963  mov     rcx, [rdi+98h]; hWnd
0x18000e96a  xor     r9d, r9d; lParam
0x18000e96d  xor     r8d, r8d; wParam
0x18000e970  call    cs:__imp_PostMessageW
0x18000e976  mov     rbx, [rsp+38h+arg_0]
0x18000e97b  xor     eax, eax
0x18000e97d  mov     rbp, [rsp+38h+arg_8]
0x18000e982  add     rsp, 30h
0x18000e986  pop     rdi
0x18000e987  retn
```
