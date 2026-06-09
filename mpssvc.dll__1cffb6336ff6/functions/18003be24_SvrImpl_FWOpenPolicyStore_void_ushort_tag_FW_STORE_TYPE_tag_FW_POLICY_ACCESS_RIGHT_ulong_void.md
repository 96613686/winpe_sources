# SvrImpl_FWOpenPolicyStore(void *,ushort,_tag_FW_STORE_TYPE,_tag_FW_POLICY_ACCESS_RIGHT,ulong,void * *)

- ea: `0x18003be24`
- end: `0x18003c22a`
- name: `?SvrImpl_FWOpenPolicyStore@@YAKPEAXGW4_tag_FW_STORE_TYPE@@W4_tag_FW_POLICY_ACCESS_RIGHT@@KPEAPEAX@Z`
- size: `1030`
- prototype: `__int64 __fastcall(void *, __int64, __int64, unsigned int, int, __int64 *)`
- caller_count: `9`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180033b28`
- `0x18003b4a0`
- `0x18003b580`
- `0x18006a41c`
- `0x18006edbc`
- `0x1800a43d8`
- `0x1800b5000`
- `0x1800b6b10`
- `0x1800b7ab8`

## callees

- `0x180008618`
- `0x180009460`
- `0x180009720`
- `0x18000a0c0`
- `0x18000ae9c`
- `0x18000af3c`
- `0x180017110`
- `0x18003be24`
- `0x18005caf8`
- `0x1800b887c`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x18003c20a`
- `fwbase!FwHResultToWindowsError` at `0x18003c20a`
- `fwbase!FwAlloc` at `0x18003bec4`
- `fwbase!FwAlloc` at `0x18003c091`
- `fwbase!FwAlloc` at `0x18003bec4`
- `fwbase!FwAlloc` at `0x18003c091`
- `fwbase!FwFree` at `0x18003c1d8`
- `fwbase!FwFree` at `0x18003c1d8`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x18003c134`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x18003c134`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x18003c1b8`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x18003c1b8`
- `FWPolicyIOMgr!FWGPLock` at `0x18003bfdb`
- `FWPolicyIOMgr!FWGPLock` at `0x18003bfdb`

## string_xrefs

- `0x18003bfbf`: `SvrImpl_FWOpenPolicyStore`
- `0x18003c19d`: `SvrImpl_FWOpenPolicyStore`
- `0x18003c1ae`: `SvrImpl_FWOpenPolicyStore`
- `0x18003c1c5`: `SvrImpl_FWOpenPolicyStore`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWOpenPolicyStore(void *a1, __int64 a2, __int64 a3, unsigned int a4, int a5, __int64 *a6)
{
  __int64 v7; // rsi
  unsigned int v8; // r13d
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 result; // rax
  __int64 v12; // rbp
  int v13; // ebx
  __int64 v14; // r14
  __int64 v15; // rcx
  __int64 v16; // rdx

  v7 = (int)a3;
  v8 = (unsigned __int16)a2;
  v9 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 225, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 4) != 0 )
    {
      WPP_SF_DdDD(*(_QWORD *)(v9 + 16), a2, a3, v8, v7, a4, a5);
      v9 = WPP_GLOBAL_Control;
    }
  }
  if ( a5 == 16 )
  {
    v10 = FwAlloc(40);
    if ( v10 )
    {
      FwMoneisSetAppReadiness(1);
      *(_DWORD *)(v10 + 16) = v7;
      *(_DWORD *)(v10 + 24) = a4;
      *(_DWORD *)(v10 + 28) = 16;
      *(_QWORD *)(v10 + 8) = &qword_18012E2B8[121 * v7];
      *(_WORD *)(v10 + 32) = v8;
      *(_WORD *)(v10 + 34) = v8;
      *a6 = v10;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 228, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, 0);
      return 0;
    }
    else
    {
      *a6 = 0;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 227, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, 14);
      return 14;
    }
  }
  v12 = 0;
  if ( (_DWORD)v7 == 5 || (a5 & 1) == 0 )
  {
    result = FwAcquireRPCSharedLock("SvrImpl_FWOpenPolicyStore");
    if ( (int)result < 0 )
      return result;
    v14 = 0;
    if ( (_DWORD)v7 == 1 )
    {
      v14 = FWGPLock();
      if ( !v14 )
      {
        v13 = -2147024894;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_Ds(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            230,
            (unsigned int)WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
            -2147024894,
            (__int64)"FWGPLock");
        goto LABEL_51;
      }
    }
    v13 = FwLock();
    if ( v13 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          231,
          WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
          (unsigned int)v13);
      goto LABEL_49;
    }
    *a6 = 0;
    v12 = FwAlloc(40);
    if ( v12 )
    {
      if ( a4 == 1 || (((_DWORD)v7 - 1) & 0xFFFFFFFD) != 0 )
      {
        if ( (((_DWORD)v7 - 5) & 0xFFFFFFFB) == 0 || (v13 = FwOpenPolicyStore((unsigned int)v7, a4, 0, v12), v13 >= 0) )
        {
          *(_DWORD *)(v12 + 16) = v7;
          *(_DWORD *)(v12 + 24) = a4;
          *(_DWORD *)(v12 + 28) = a5;
          *(_QWORD *)(v12 + 8) = &qword_18012E2B8[121 * v7];
          *(_WORD *)(v12 + 32) = v8;
          *(_WORD *)(v12 + 34) = v8;
          *a6 = v12;
          goto LABEL_48;
        }
        v15 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_48;
        v16 = 234;
      }
      else
      {
        v13 = -2147024891;
        v15 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_48;
        v16 = 233;
      }
    }
    else
    {
      v13 = -2147024882;
      v15 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_48;
      v16 = 232;
    }
    WPP_SF_d(*(_QWORD *)(v15 + 16), v16, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, (unsigned int)v13);
LABEL_48:
    FwUnlockInternal(a1, "SvrImpl_FWOpenPolicyStore");
LABEL_49:
    if ( v14 )
      FWGPUnlockEx(v14, "SvrImpl_FWOpenPolicyStore");
    goto LABEL_51;
  }
  v13 = -2147024809;
  if ( (_UNKNOWN *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 1) != 0 )
    WPP_SF_d(*(_QWORD *)(v9 + 16), 229, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, 2147942487LL);
LABEL_51:
  FwReleaseRPCSharedLock("SvrImpl_FWOpenPolicyStore");
  if ( v13 < 0 )
    FwFree(v12);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      235,
      WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
      (unsigned int)v13);
  return FwHResultToWindowsError((unsigned int)v13);
}

```

## disassembly

```asm
0x18003be24  mov     [rsp+arg_8], rbx
0x18003be29  mov     [rsp+arg_10], rbp
0x18003be2e  mov     [rsp+arg_0], rcx
0x18003be33  push    rsi
0x18003be34  push    r12
0x18003be36  push    r13
0x18003be38  push    r14
0x18003be3a  push    r15
0x18003be3c  sub     rsp, 40h
0x18003be40  mov     r12d, r9d
0x18003be43  movsxd  rsi, r8d
0x18003be46  movzx   r13d, dx
0x18003be4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003be51  lea     r14, WPP_GLOBAL_Control
0x18003be58  mov     r15d, [rsp+68h+arg_20]
0x18003be60  lea     rbp, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18003be67  cmp     rcx, r14
0x18003be6a  jz      short loc_18003BEB6
0x18003be6c  test    byte ptr [rcx+1Ch], 8
0x18003be70  jz      short loc_18003BE8A
0x18003be72  mov     rcx, [rcx+10h]
0x18003be76  mov     edx, 0E1h
0x18003be7b  mov     r8, rbp
0x18003be7e  call    WPP_SF_
0x18003be83  mov     rcx, cs:WPP_GLOBAL_Control
0x18003be8a  cmp     rcx, r14
0x18003be8d  jz      short loc_18003BEB6
0x18003be8f  test    byte ptr [rcx+1Ch], 4
0x18003be93  jz      short loc_18003BEB6
0x18003be95  mov     rcx, [rcx+10h]
0x18003be99  mov     r9d, r13d
0x18003be9c  mov     [rsp+68h+var_38], r15d
0x18003bea1  mov     [rsp+68h+var_40], r12d
0x18003bea6  mov     dword ptr [rsp+68h+var_48], esi
0x18003beaa  call    WPP_SF_DdDD
0x18003beaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003beb6  cmp     r15d, 10h
0x18003beba  jnz     loc_18003BF7D
0x18003bec0  lea     ecx, [r15+18h]
0x18003bec4  call    cs:__imp_FwAlloc
0x18003beca  mov     rbx, rax
0x18003becd  test    rax, rax
0x18003bed0  jnz     short loc_18003BF0E
0x18003bed2  mov     rax, [rsp+68h+arg_28]
0x18003beda  mov     [rax], rbx
0x18003bedd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bee4  lea     ebx, [r15-2]
0x18003bee8  cmp     rcx, r14
0x18003beeb  jz      short loc_18003BF07
0x18003beed  test    byte ptr [rcx+1Ch], 4
0x18003bef1  jz      short loc_18003BF07
0x18003bef3  mov     rcx, [rcx+10h]
0x18003bef7  mov     edx, 0E3h
0x18003befc  mov     r9d, ebx
0x18003beff  mov     r8, rbp
0x18003bf02  call    WPP_SF_d
0x18003bf07  mov     eax, ebx
0x18003bf09  jmp     loc_18003C210
0x18003bf0e  mov     ecx, 1
0x18003bf13  call    FwMoneisSetAppReadiness
0x18003bf18  lea     rax, qword_18012E2B8
0x18003bf1f  mov     [rbx+10h], esi
0x18003bf22  imul    rcx, rsi, 3C8h
0x18003bf29  mov     [rbx+18h], r12d
0x18003bf2d  add     rcx, rax
0x18003bf30  mov     dword ptr [rbx+1Ch], 10h
0x18003bf37  mov     rax, [rsp+68h+arg_28]
0x18003bf3f  mov     [rbx+8], rcx
0x18003bf43  mov     [rbx+20h], r13w
0x18003bf48  mov     [rbx+22h], r13w
0x18003bf4d  mov     [rax], rbx
0x18003bf50  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bf57  cmp     rcx, r14
0x18003bf5a  jz      short loc_18003BF76
0x18003bf5c  test    byte ptr [rcx+1Ch], 4
0x18003bf60  jz      short loc_18003BF76
0x18003bf62  mov     rcx, [rcx+10h]
0x18003bf66  mov     edx, 0E4h
0x18003bf6b  xor     r9d, r9d
0x18003bf6e  mov     r8, rbp
0x18003bf71  call    WPP_SF_d
0x18003bf76  xor     eax, eax
0x18003bf78  jmp     loc_18003C210
0x18003bf7d  xor     ebp, ebp
0x18003bf7f  cmp     esi, 5
0x18003bf82  jz      short loc_18003BFBF
0x18003bf84  test    r15b, 1
0x18003bf88  jz      short loc_18003BFBF
0x18003bf8a  mov     ebx, 80070057h
0x18003bf8f  cmp     rcx, r14
0x18003bf92  jz      loc_18003C1C5
0x18003bf98  test    byte ptr [rcx+1Ch], 1
0x18003bf9c  jz      loc_18003C1C5
0x18003bfa2  mov     rcx, [rcx+10h]
0x18003bfa6  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18003bfad  mov     edx, 0E5h
0x18003bfb2  mov     r9d, ebx
0x18003bfb5  call    WPP_SF_d
0x18003bfba  jmp     loc_18003C1C5
0x18003bfbf  lea     rcx, aSvrimplFwopenp; "SvrImpl_FWOpenPolicyStore"
0x18003bfc6  call    FwAcquireRPCSharedLock
0x18003bfcb  test    eax, eax
0x18003bfcd  js      loc_18003C210
0x18003bfd3  xor     r14d, r14d
0x18003bfd6  cmp     esi, 1
0x18003bfd9  jnz     short loc_18003C038
0x18003bfdb  call    cs:__imp_FWGPLock
0x18003bfe1  mov     r14, rax
0x18003bfe4  test    rax, rax
0x18003bfe7  jnz     short loc_18003C038
0x18003bfe9  mov     ebx, 80070002h
0x18003bfee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bff5  lea     r14, WPP_GLOBAL_Control
0x18003bffc  cmp     rcx, r14
0x18003bfff  jz      loc_18003C1C5
0x18003c005  test    [rcx+1Ch], sil
0x18003c009  jz      loc_18003C1C5
0x18003c00f  mov     rcx, [rcx+10h]
0x18003c013  lea     rax, aFwgplock_0; "FWGPLock"
0x18003c01a  mov     edx, 0E6h
0x18003c01f  mov     [rsp+68h+var_48], rax
0x18003c024  mov     r9d, ebx
0x18003c027  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18003c02e  call    WPP_SF_Ds
0x18003c033  jmp     loc_18003C1C5
0x18003c038  call    FwLock
0x18003c03d  mov     ebx, eax
0x18003c03f  test    eax, eax
0x18003c041  jns     short loc_18003C081
0x18003c043  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c04a  lea     rax, WPP_GLOBAL_Control
0x18003c051  cmp     rcx, rax
0x18003c054  jz      loc_18003C1A9
0x18003c05a  test    byte ptr [rcx+1Ch], 1
0x18003c05e  jz      loc_18003C1A9
0x18003c064  mov     rcx, [rcx+10h]
0x18003c068  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18003c06f  mov     edx, 0E7h
0x18003c074  mov     r9d, ebx
0x18003c077  call    WPP_SF_d
0x18003c07c  jmp     loc_18003C1A9
0x18003c081  mov     rax, [rsp+68h+arg_28]
0x18003c089  mov     ecx, 28h ; '('
0x18003c08e  mov     [rax], rbp
0x18003c091  call    cs:__imp_FwAlloc
0x18003c097  mov     rbp, rax
0x18003c09a  test    rax, rax
0x18003c09d  jnz     short loc_18003C0E2
0x18003c09f  mov     ebx, 8007000Eh
0x18003c0a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c0ab  lea     rax, WPP_GLOBAL_Control
0x18003c0b2  cmp     rcx, rax
0x18003c0b5  jz      loc_18003C198
0x18003c0bb  test    byte ptr [rcx+1Ch], 1
0x18003c0bf  jz      loc_18003C198
0x18003c0c5  mov     edx, 0E8h
0x18003c0ca  mov     rcx, [rcx+10h]
0x18003c0ce  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18003c0d5  mov     r9d, ebx
0x18003c0d8  call    WPP_SF_d
0x18003c0dd  jmp     loc_18003C198
0x18003c0e2  cmp     r12d, 1
0x18003c0e6  jz      short loc_18003C11F
0x18003c0e8  lea     eax, [rsi-1]
0x18003c0eb  test    eax, 0FFFFFFFDh
0x18003c0f0  jnz     short loc_18003C11F
0x18003c0f2  mov     ebx, 80070005h
0x18003c0f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c0fe  lea     rax, WPP_GLOBAL_Control
0x18003c105  cmp     rcx, rax
0x18003c108  jz      loc_18003C198
0x18003c10e  test    byte ptr [rcx+1Ch], 1
0x18003c112  jz      loc_18003C198
0x18003c118  mov     edx, 0E9h
0x18003c11d  jmp     short loc_18003C0CA
0x18003c11f  lea     eax, [rsi-5]
0x18003c122  test    eax, 0FFFFFFFBh
0x18003c127  jz      short loc_18003C163
0x18003c129  mov     r9, rbp
0x18003c12c  xor     r8d, r8d
0x18003c12f  mov     edx, r12d
0x18003c132  mov     ecx, esi
0x18003c134  call    cs:__imp_FwOpenPolicyStore
0x18003c13a  mov     ebx, eax
0x18003c13c  test    eax, eax
0x18003c13e  jns     short loc_18003C163
0x18003c140  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c147  lea     rax, WPP_GLOBAL_Control
0x18003c14e  cmp     rcx, rax
0x18003c151  jz      short loc_18003C198
0x18003c153  test    byte ptr [rcx+1Ch], 1
0x18003c157  jz      short loc_18003C198
0x18003c159  mov     edx, 0EAh
0x18003c15e  jmp     loc_18003C0CA
0x18003c163  lea     rax, qword_18012E2B8
0x18003c16a  mov     [rbp+10h], esi
0x18003c16d  imul    rcx, rsi, 3C8h
0x18003c174  mov     [rbp+18h], r12d
0x18003c178  add     rcx, rax
0x18003c17b  mov     [rbp+1Ch], r15d
0x18003c17f  mov     rax, [rsp+68h+arg_28]
0x18003c187  mov     [rbp+8], rcx
0x18003c18b  mov     [rbp+20h], r13w
0x18003c190  mov     [rbp+22h], r13w
0x18003c195  mov     [rax], rbp
0x18003c198  mov     rcx, [rsp+68h+arg_0]; void *
0x18003c19d  lea     rdx, aSvrimplFwopenp; "SvrImpl_FWOpenPolicyStore"
0x18003c1a4  call    FwUnlockInternal
0x18003c1a9  test    r14, r14
0x18003c1ac  jz      short loc_18003C1BE
0x18003c1ae  lea     rdx, aSvrimplFwopenp; "SvrImpl_FWOpenPolicyStore"
0x18003c1b5  mov     rcx, r14
0x18003c1b8  call    cs:__imp_FWGPUnlockEx
0x18003c1be  lea     r14, WPP_GLOBAL_Control
0x18003c1c5  lea     rcx, aSvrimplFwopenp; "SvrImpl_FWOpenPolicyStore"
0x18003c1cc  call    FwReleaseRPCSharedLock
0x18003c1d1  test    ebx, ebx
0x18003c1d3  jns     short loc_18003C1DE
0x18003c1d5  mov     rcx, rbp
0x18003c1d8  call    cs:__imp_FwFree
0x18003c1de  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c1e5  cmp     rcx, r14
0x18003c1e8  jz      short loc_18003C208
0x18003c1ea  test    byte ptr [rcx+1Ch], 8
0x18003c1ee  jz      short loc_18003C208
0x18003c1f0  mov     rcx, [rcx+10h]
0x18003c1f4  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x18003c1fb  mov     edx, 0EBh
0x18003c200  mov     r9d, ebx
0x18003c203  call    WPP_SF_d
0x18003c208  mov     ecx, ebx
0x18003c20a  call    cs:__imp_FwHResultToWindowsError
0x18003c210  lea     r11, [rsp+68h+var_28]
0x18003c215  mov     rbx, [r11+38h]
0x18003c219  mov     rbp, [r11+40h]
0x18003c21d  mov     rsp, r11
0x18003c220  pop     r15
0x18003c222  pop     r14
0x18003c224  pop     r13
0x18003c226  pop     r12
0x18003c228  pop     rsi
0x18003c229  retn
```
