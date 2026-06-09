# CFveTpm::GetEFIBootMgrFilePathFromBCD(ushort *,ulong)

- ea: `0x1800876fc`
- end: `0x180087a9e`
- name: `?GetEFIBootMgrFilePathFromBCD@CFveTpm@@KAJPEAGK@Z`
- size: `930`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800184ac`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180009130`
- `0x18000aae0`
- `0x18000ba30`
- `0x180018b10`
- `0x1800876fc`
- `0x18009befc`
- `0x18011f010`

## import_xrefs

- `bcd!BcdCloseObject` at `0x180087a25`
- `bcd!BcdCloseObject` at `0x180087a25`
- `bcd!BcdOpenObject` at `0x1800877ef`
- `bcd!BcdOpenObject` at `0x1800877ef`
- `bcd!BcdCloseStore` at `0x180087a44`
- `bcd!BcdCloseStore` at `0x180087a44`
- `bcd!BcdOpenSystemStore` at `0x18008778f`
- `bcd!BcdOpenSystemStore` at `0x18008778f`

## pseudocode

```c
__int64 __fastcall CFveTpm::GetEFIBootMgrFilePathFromBCD(unsigned __int16 *a1, __int64 a2)
{
  int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // rdx
  int v6; // ebx
  PVOID *v7; // rcx
  int v8; // eax
  unsigned int v9; // eax
  unsigned int BcdElementData; // eax
  _DWORD *v11; // rsi
  unsigned int v12; // eax
  void *v13; // rdi
  unsigned int v14; // eax
  unsigned int v16; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v17; // [rsp+34h] [rbp-2Ch] BYREF
  void *v18; // [rsp+38h] [rbp-28h] BYREF
  void *lpMem; // [rsp+40h] [rbp-20h] BYREF
  void *v20; // [rsp+48h] [rbp-18h] BYREF
  __int64 v21; // [rsp+50h] [rbp-10h] BYREF

  lpMem = 0;
  v17 = 0;
  v21 = 0;
  v20 = 0;
  v18 = 0;
  v16 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 677, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids);
  *a1 = 0;
  v3 = BcdOpenSystemStore(&v21, a2);
  v4 = FromNtStatus(v3);
  v6 = v4;
  if ( !v4 )
    goto LABEL_13;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 678, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v4);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 >= 0 )
  {
LABEL_13:
    v8 = BcdOpenObject(v21, &GUID_WINDOWS_BOOTMGR, &v20);
    v9 = FromNtStatus(v8);
    v6 = v9;
    if ( !v9 )
      goto LABEL_14;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 679, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v9);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 >= 0 )
    {
LABEL_14:
      BcdElementData = CFveApiBase::GetBcdElementData(v20, 0x11000001u, &v18, &v16);
      v11 = v18;
      v6 = BcdElementData;
      if ( BcdElementData )
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            680,
            &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
            BcdElementData);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v6 < 0 )
          goto LABEL_51;
      }
      else
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
        WPP_SF_S(v7[2], 681, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v11 + 5);
      v12 = CFveApiBase::GetBcdElementData(v20, 0x12000002u, &lpMem, &v17);
      v13 = lpMem;
      v6 = v12;
      if ( v12 )
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 682, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v12);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v6 < 0 )
          goto LABEL_49;
      }
      else
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( *v11 == 2 )
      {
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
          WPP_SF_S(v7[2], 684, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v13);
        v14 = StringCchPrintfW(a1, 0x104u, L"\\\\.\\GLOBALROOT%s%s", v11 + 5, v13);
        v6 = v14;
        if ( v14 )
        {
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 685, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v14);
            v7 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v6 < 0 )
            goto LABEL_49;
        }
        else
        {
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 )
        {
          WPP_SF_S(v7[2], 686, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, a1);
          goto LABEL_48;
        }
      }
      else
      {
        v6 = -2147023092;
        if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 )
        {
          WPP_SF_d(v7[2], 683, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, 2147944204LL);
LABEL_48:
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
      }
LABEL_49:
      if ( v13 )
      {
        CFveApiBase::FastFree(v13);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_51:
      if ( v11 )
      {
        CFveApiBase::FastFree(v11);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  if ( v20 )
  {
    BcdCloseObject(v20);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v21 )
  {
    BcdCloseStore(v21, v5);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
    WPP_SF_d(v7[2], 687, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800876fc  mov     [rsp-28h+arg_8], rbx
0x180087701  mov     [rsp-28h+arg_10], rsi
0x180087706  push    rbp
0x180087707  push    rdi
0x180087708  push    r12
0x18008770a  push    r13
0x18008770c  push    r14
0x18008770e  mov     rbp, rsp
0x180087711  sub     rsp, 60h
0x180087715  mov     rax, cs:__security_cookie
0x18008771c  xor     rax, rsp
0x18008771f  mov     [rbp+var_8], rax
0x180087723  mov     r14, rcx
0x180087726  mov     [rbp+lpMem], 0
0x18008772e  mov     [rbp+var_2C], 0
0x180087735  mov     [rbp+var_10], 0
0x18008773d  mov     [rbp+var_18], 0
0x180087745  mov     [rbp+var_28], 0
0x18008774d  mov     [rbp+var_30], 0
0x180087754  mov     rcx, cs:WPP_GLOBAL_Control
0x18008775b  lea     r12, WPP_GLOBAL_Control
0x180087762  lea     r13, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x180087769  cmp     rcx, r12
0x18008776c  jz      short loc_180087785
0x18008776e  test    byte ptr [rcx+1Ch], 20h
0x180087772  jz      short loc_180087785
0x180087774  mov     rcx, [rcx+10h]
0x180087778  mov     edx, 2A5h
0x18008777d  mov     r8, r13
0x180087780  call    WPP_SF_
0x180087785  xor     eax, eax
0x180087787  lea     rcx, [rbp+var_10]
0x18008778b  mov     [r14], ax
0x18008778f  call    cs:__imp_BcdOpenSystemStore
0x180087796  nop     dword ptr [rax+rax+00h]
0x18008779b  mov     ecx, eax; int
0x18008779d  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800877a2  mov     ebx, eax
0x1800877a4  mov     dil, 40h ; '@'
0x1800877a7  test    eax, eax
0x1800877a9  jz      short loc_1800877E0
0x1800877ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800877b2  cmp     rcx, r12
0x1800877b5  jz      short loc_1800877D8
0x1800877b7  test    [rcx+1Ch], dil
0x1800877bb  jz      short loc_1800877D8
0x1800877bd  mov     rcx, [rcx+10h]
0x1800877c1  mov     edx, 2A6h
0x1800877c6  mov     r9d, eax
0x1800877c9  mov     r8, r13
0x1800877cc  call    WPP_SF_d
0x1800877d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800877d8  test    ebx, ebx
0x1800877da  js      loc_180087A19
0x1800877e0  mov     rcx, [rbp+var_10]
0x1800877e4  lea     r8, [rbp+var_18]
0x1800877e8  lea     rdx, GUID_WINDOWS_BOOTMGR
0x1800877ef  call    cs:__imp_BcdOpenObject
0x1800877f6  nop     dword ptr [rax+rax+00h]
0x1800877fb  mov     ecx, eax; int
0x1800877fd  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180087802  mov     ebx, eax
0x180087804  test    eax, eax
0x180087806  jz      short loc_18008783D
0x180087808  mov     rcx, cs:WPP_GLOBAL_Control
0x18008780f  cmp     rcx, r12
0x180087812  jz      short loc_180087835
0x180087814  test    [rcx+1Ch], dil
0x180087818  jz      short loc_180087835
0x18008781a  mov     rcx, [rcx+10h]
0x18008781e  mov     edx, 2A7h
0x180087823  mov     r9d, eax
0x180087826  mov     r8, r13
0x180087829  call    WPP_SF_d
0x18008782e  mov     rcx, cs:WPP_GLOBAL_Control
0x180087835  test    ebx, ebx
0x180087837  js      loc_180087A19
0x18008783d  mov     rcx, [rbp+var_18]; void *
0x180087841  lea     r9, [rbp+var_30]; unsigned int *
0x180087845  lea     r8, [rbp+var_28]; void **
0x180087849  mov     edx, 11000001h; unsigned int
0x18008784e  call    ?GetBcdElementData@CFveApiBase@@SAJPEAXKPEAPEAXPEAK@Z; CFveApiBase::GetBcdElementData(void *,ulong,void * *,ulong *)
0x180087853  mov     rsi, [rbp+var_28]
0x180087857  mov     ebx, eax
0x180087859  test    eax, eax
0x18008785b  jz      short loc_180087894
0x18008785d  mov     rcx, cs:WPP_GLOBAL_Control
0x180087864  cmp     rcx, r12
0x180087867  jz      short loc_18008788A
0x180087869  test    [rcx+1Ch], dil
0x18008786d  jz      short loc_18008788A
0x18008786f  mov     rcx, [rcx+10h]
0x180087873  mov     edx, 2A8h
0x180087878  mov     r9d, eax
0x18008787b  mov     r8, r13
0x18008787e  call    WPP_SF_d
0x180087883  mov     rcx, cs:WPP_GLOBAL_Control
0x18008788a  test    ebx, ebx
0x18008788c  js      loc_180087A05
0x180087892  jmp     short loc_18008789B
0x180087894  mov     rcx, cs:WPP_GLOBAL_Control
0x18008789b  cmp     rcx, r12
0x18008789e  jz      short loc_1800878BB
0x1800878a0  test    byte ptr [rcx+1Ch], 8
0x1800878a4  jz      short loc_1800878BB
0x1800878a6  mov     rcx, [rcx+10h]
0x1800878aa  lea     r9, [rsi+14h]
0x1800878ae  mov     edx, 2A9h
0x1800878b3  mov     r8, r13
0x1800878b6  call    WPP_SF_S
0x1800878bb  mov     rcx, [rbp+var_18]; void *
0x1800878bf  lea     r9, [rbp+var_2C]; unsigned int *
0x1800878c3  lea     r8, [rbp+lpMem]; void **
0x1800878c7  mov     edx, 12000002h; unsigned int
0x1800878cc  call    ?GetBcdElementData@CFveApiBase@@SAJPEAXKPEAPEAXPEAK@Z; CFveApiBase::GetBcdElementData(void *,ulong,void * *,ulong *)
0x1800878d1  mov     rdi, [rbp+lpMem]
0x1800878d5  mov     ebx, eax
0x1800878d7  test    eax, eax
0x1800878d9  jz      short loc_180087912
0x1800878db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800878e2  cmp     rcx, r12
0x1800878e5  jz      short loc_180087908
0x1800878e7  test    byte ptr [rcx+1Ch], 40h
0x1800878eb  jz      short loc_180087908
0x1800878ed  mov     rcx, [rcx+10h]
0x1800878f1  mov     edx, 2AAh
0x1800878f6  mov     r9d, eax
0x1800878f9  mov     r8, r13
0x1800878fc  call    WPP_SF_d
0x180087901  mov     rcx, cs:WPP_GLOBAL_Control
0x180087908  test    ebx, ebx
0x18008790a  js      loc_1800879F1
0x180087910  jmp     short loc_180087919
0x180087912  mov     rcx, cs:WPP_GLOBAL_Control
0x180087919  cmp     dword ptr [rsi], 2
0x18008791c  jz      short loc_18008794F
0x18008791e  mov     ebx, 8007070Ch
0x180087923  cmp     rcx, r12
0x180087926  jz      loc_1800879F1
0x18008792c  test    byte ptr [rcx+1Ch], 40h
0x180087930  jz      loc_1800879F1
0x180087936  mov     rcx, [rcx+10h]
0x18008793a  mov     edx, 2ABh
0x18008793f  mov     r9d, ebx
0x180087942  mov     r8, r13
0x180087945  call    WPP_SF_d
0x18008794a  jmp     loc_1800879EA
0x18008794f  cmp     rcx, r12
0x180087952  jz      short loc_18008796E
0x180087954  test    byte ptr [rcx+1Ch], 8
0x180087958  jz      short loc_18008796E
0x18008795a  mov     rcx, [rcx+10h]
0x18008795e  mov     edx, 2ACh
0x180087963  mov     r9, rdi
0x180087966  mov     r8, r13
0x180087969  call    WPP_SF_S
0x18008796e  lea     r9, [rsi+14h]
0x180087972  mov     [rsp+60h+var_40], rdi
0x180087977  lea     r8, aGlobalrootSS_0; "\\\\.\\GLOBALROOT%s%s"
0x18008797e  mov     edx, 104h; unsigned __int64
0x180087983  mov     rcx, r14; unsigned __int16 *
0x180087986  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008798b  mov     ebx, eax
0x18008798d  test    eax, eax
0x18008798f  jz      short loc_1800879C4
0x180087991  mov     rcx, cs:WPP_GLOBAL_Control
0x180087998  cmp     rcx, r12
0x18008799b  jz      short loc_1800879BE
0x18008799d  test    byte ptr [rcx+1Ch], 40h
0x1800879a1  jz      short loc_1800879BE
0x1800879a3  mov     rcx, [rcx+10h]
0x1800879a7  mov     edx, 2ADh
0x1800879ac  mov     r9d, eax
0x1800879af  mov     r8, r13
0x1800879b2  call    WPP_SF_d
0x1800879b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800879be  test    ebx, ebx
0x1800879c0  js      short loc_1800879F1
0x1800879c2  jmp     short loc_1800879CB
0x1800879c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800879cb  cmp     rcx, r12
0x1800879ce  jz      short loc_1800879F1
0x1800879d0  test    byte ptr [rcx+1Ch], 8
0x1800879d4  jz      short loc_1800879F1
0x1800879d6  mov     rcx, [rcx+10h]
0x1800879da  mov     edx, 2AEh
0x1800879df  mov     r9, r14
0x1800879e2  mov     r8, r13
0x1800879e5  call    WPP_SF_S
0x1800879ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800879f1  test    rdi, rdi
0x1800879f4  jz      short loc_180087A05
0x1800879f6  mov     rcx, rdi; lpMem
0x1800879f9  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x1800879fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180087a05  test    rsi, rsi
0x180087a08  jz      short loc_180087A19
0x180087a0a  mov     rcx, rsi; lpMem
0x180087a0d  call    ?FastFree@CFveApiBase@@SAJPEAX@Z; CFveApiBase::FastFree(void *)
0x180087a12  mov     rcx, cs:WPP_GLOBAL_Control
0x180087a19  mov     rax, [rbp+var_18]
0x180087a1d  test    rax, rax
0x180087a20  jz      short loc_180087A38
0x180087a22  mov     rcx, rax
0x180087a25  call    cs:__imp_BcdCloseObject
0x180087a2c  nop     dword ptr [rax+rax+00h]
0x180087a31  mov     rcx, cs:WPP_GLOBAL_Control
0x180087a38  mov     rax, [rbp+var_10]
0x180087a3c  test    rax, rax
0x180087a3f  jz      short loc_180087A57
0x180087a41  mov     rcx, rax
0x180087a44  call    cs:__imp_BcdCloseStore
0x180087a4b  nop     dword ptr [rax+rax+00h]
0x180087a50  mov     rcx, cs:WPP_GLOBAL_Control
0x180087a57  cmp     rcx, r12
0x180087a5a  jz      short loc_180087A76
0x180087a5c  test    byte ptr [rcx+1Ch], 20h
0x180087a60  jz      short loc_180087A76
0x180087a62  mov     rcx, [rcx+10h]
0x180087a66  mov     edx, 2AFh
0x180087a6b  mov     r9d, ebx
0x180087a6e  mov     r8, r13
0x180087a71  call    WPP_SF_d
0x180087a76  mov     eax, ebx
0x180087a78  mov     rcx, [rbp+var_8]
0x180087a7c  xor     rcx, rsp; StackCookie
0x180087a7f  call    __security_check_cookie
0x180087a84  lea     r11, [rsp+60h+var_s0]
0x180087a89  mov     rbx, [r11+38h]
0x180087a8d  mov     rsi, [r11+40h]
0x180087a91  mov     rsp, r11
0x180087a94  pop     r14
0x180087a96  pop     r13
0x180087a98  pop     r12
0x180087a9a  pop     rdi
0x180087a9b  pop     rbp
0x180087a9c  retn
```
