# CSNOCplCore::OnServiceInvalid(ushort const *)

- ea: `0x18000e290`
- end: `0x18000e3d1`
- name: `?OnServiceInvalid@CSNOCplCore@@UEAAJPEBG@Z`
- size: `321`
- prototype: `int(CSNOCplCore *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006b70`
- `0x18000e290`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e2bf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e317`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e36e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e2bf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e317`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000e36e`
- `USER32!PostMessageW` at `0x18000e3b9`
- `USER32!PostMessageW` at `0x18000e3b9`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::OnServiceInvalid(HWND *this, const unsigned __int16 *a2)
{
  UINT v4; // edx

  if ( CompareStringOrdinal(a2, -1, L"netprofm", -1, 1) == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
    v4 = 32769;
LABEL_16:
    PostMessageW(this[19], v4, 0, 0);
    return 0;
  }
  if ( CompareStringOrdinal(a2, -1, L"netman", -1, 1) == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
    v4 = 32772;
    goto LABEL_16;
  }
  if ( CompareStringOrdinal(a2, -1, L"wlansvc", -1, 1) == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
    v4 = 32774;
    goto LABEL_16;
  }
  return 0;
}

```

## disassembly

```asm
0x18000e290  mov     [rsp+arg_0], rbx
0x18000e295  mov     [rsp+arg_8], rbp
0x18000e29a  push    rdi
0x18000e29b  sub     rsp, 30h
0x18000e29f  mov     rdi, rdx
0x18000e2a2  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000e2aa  or      ebp, 0FFFFFFFFh
0x18000e2ad  lea     r8, ServiceName; "netprofm"
0x18000e2b4  mov     rbx, rcx
0x18000e2b7  mov     r9d, ebp; cchCount2
0x18000e2ba  mov     edx, ebp; cchCount1
0x18000e2bc  mov     rcx, rdi; lpString1
0x18000e2bf  call    cs:__imp_CompareStringOrdinal
0x18000e2c5  cmp     eax, 2
0x18000e2c8  jnz     short loc_18000E300
0x18000e2ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2d1  lea     rax, WPP_GLOBAL_Control
0x18000e2d8  cmp     rcx, rax
0x18000e2db  jz      short loc_18000E2F6
0x18000e2dd  test    byte ptr [rcx+1Ch], 2
0x18000e2e1  jz      short loc_18000E2F6
0x18000e2e3  mov     rcx, [rcx+10h]
0x18000e2e7  lea     edx, [rbp+3Eh]
0x18000e2ea  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000e2f1  call    WPP_SF_
0x18000e2f6  mov     edx, 8001h
0x18000e2fb  jmp     loc_18000E3AC
0x18000e300  mov     r9d, ebp; cchCount2
0x18000e303  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000e30b  lea     r8, aNetman; "netman"
0x18000e312  mov     edx, ebp; cchCount1
0x18000e314  mov     rcx, rdi; lpString1
0x18000e317  call    cs:__imp_CompareStringOrdinal
0x18000e31d  cmp     eax, 2
0x18000e320  jnz     short loc_18000E357
0x18000e322  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e329  lea     rax, WPP_GLOBAL_Control
0x18000e330  cmp     rcx, rax
0x18000e333  jz      short loc_18000E350
0x18000e335  test    byte ptr [rcx+1Ch], 2
0x18000e339  jz      short loc_18000E350
0x18000e33b  mov     rcx, [rcx+10h]
0x18000e33f  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000e346  mov     edx, 3Eh ; '>'
0x18000e34b  call    WPP_SF_
0x18000e350  mov     edx, 8004h
0x18000e355  jmp     short loc_18000E3AC
0x18000e357  mov     r9d, ebp; cchCount2
0x18000e35a  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000e362  lea     r8, aWlansvc; "wlansvc"
0x18000e369  mov     edx, ebp; cchCount1
0x18000e36b  mov     rcx, rdi; lpString1
0x18000e36e  call    cs:__imp_CompareStringOrdinal
0x18000e374  cmp     eax, 2
0x18000e377  jnz     short loc_18000E3BF
0x18000e379  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e380  lea     rax, WPP_GLOBAL_Control
0x18000e387  cmp     rcx, rax
0x18000e38a  jz      short loc_18000E3A7
0x18000e38c  test    byte ptr [rcx+1Ch], 2
0x18000e390  jz      short loc_18000E3A7
0x18000e392  mov     rcx, [rcx+10h]
0x18000e396  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000e39d  mov     edx, 3Fh ; '?'
0x18000e3a2  call    WPP_SF_
0x18000e3a7  mov     edx, 8006h; Msg
0x18000e3ac  mov     rcx, [rbx+98h]; hWnd
0x18000e3b3  xor     r9d, r9d; lParam
0x18000e3b6  xor     r8d, r8d; wParam
0x18000e3b9  call    cs:__imp_PostMessageW
0x18000e3bf  mov     rbx, [rsp+38h+arg_0]
0x18000e3c4  xor     eax, eax
0x18000e3c6  mov     rbp, [rsp+38h+arg_8]
0x18000e3cb  add     rsp, 30h
0x18000e3cf  pop     rdi
0x18000e3d0  retn
```
