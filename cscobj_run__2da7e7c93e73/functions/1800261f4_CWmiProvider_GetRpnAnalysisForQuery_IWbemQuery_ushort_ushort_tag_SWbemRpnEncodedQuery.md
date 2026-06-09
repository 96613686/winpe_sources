# CWmiProvider::_GetRpnAnalysisForQuery(IWbemQuery *,ushort *,ushort *,tag_SWbemRpnEncodedQuery * *)

- ea: `0x1800261f4`
- end: `0x18002632f`
- name: `?_GetRpnAnalysisForQuery@CWmiProvider@@AEAAJPEAUIWbemQuery@@PEAG1PEAPEAUtag_SWbemRpnEncodedQuery@@@Z`
- size: `315`
- prototype: `__int64 __fastcall(CWmiProvider *__hidden this, struct IWbemQuery *, unsigned __int16 *, unsigned __int16 *, struct tag_SWbemRpnEncodedQuery **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002617c`

## callees

- `0x18000f5cc`
- `0x180014068`
- `0x1800261f4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026222`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026222`

## pseudocode

```c
__int64 __fastcall CWmiProvider::_GetRpnAnalysisForQuery(
        CWmiProvider *this,
        struct IWbemQuery *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct tag_SWbemRpnEncodedQuery **a5)
{
  unsigned int v8; // ebx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx

  if ( CompareStringW(0x400u, 0, a3, -1, L"WQL", -1) == 2 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
    {
      WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 71, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids, a4);
    }
    v9 = ((__int64 (__fastcall *)(struct IWbemQuery *, unsigned __int16 *, unsigned __int16 *, _QWORD))a2->lpVtbl->Parse)(
           a2,
           a3,
           a4,
           0);
    v8 = v9;
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        return v8;
      v11 = 73;
    }
    else
    {
      v9 = ((__int64 (__fastcall *)(struct IWbemQuery *, __int64, _QWORD, struct tag_SWbemRpnEncodedQuery **))a2->lpVtbl->GetAnalysis)(
             a2,
             1,
             0,
             a5);
      v8 = v9;
      if ( v9 >= 0 )
        return v8;
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        return v8;
      v11 = 72;
    }
    WPP_SF_d(*(_QWORD *)(v10 + 16), v11, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids, (unsigned int)v9);
    return v8;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 70, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids, a3);
  }
  return (unsigned int)-2147217372;
}

```

## disassembly

```asm
0x1800261f4  push    rbx
0x1800261f6  push    rbp
0x1800261f7  push    rsi
0x1800261f8  push    rdi
0x1800261f9  sub     rsp, 38h
0x1800261fd  mov     rbp, r9
0x180026200  lea     rax, aWql; "WQL"
0x180026207  or      r9d, 0FFFFFFFFh; cchCount1
0x18002620b  mov     rsi, rdx
0x18002620e  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x180026213  xor     edx, edx; dwCmpFlags
0x180026215  mov     ecx, 400h; Locale
0x18002621a  mov     [rsp+58h+lpString2], rax; lpString2
0x18002621f  mov     rbx, r8
0x180026222  call    cs:__imp_CompareStringW
0x180026228  cmp     eax, 2
0x18002622b  jz      short loc_18002626B
0x18002622d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026234  lea     rdi, WPP_GLOBAL_Control
0x18002623b  cmp     rcx, rdi
0x18002623e  jz      short loc_180026261
0x180026240  test    dword ptr [rcx+1Ch], 4000000h
0x180026247  jz      short loc_180026261
0x180026249  mov     rcx, [rcx+10h]
0x18002624d  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180026254  mov     edx, 46h ; 'F'
0x180026259  mov     r9, rbx
0x18002625c  call    WPP_SF_S
0x180026261  mov     ebx, 80041024h
0x180026266  jmp     loc_180026324
0x18002626b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026272  lea     rdi, WPP_GLOBAL_Control
0x180026279  cmp     rcx, rdi
0x18002627c  jz      short loc_18002629F
0x18002627e  test    dword ptr [rcx+1Ch], 4000000h
0x180026285  jz      short loc_18002629F
0x180026287  mov     rcx, [rcx+10h]
0x18002628b  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x180026292  mov     edx, 47h ; 'G'
0x180026297  mov     r9, rbp
0x18002629a  call    WPP_SF_S
0x18002629f  mov     rax, [rsi]
0x1800262a2  xor     r9d, r9d
0x1800262a5  mov     r8, rbp
0x1800262a8  mov     rdx, rbx
0x1800262ab  mov     rcx, rsi
0x1800262ae  mov     rax, [rax+30h]
0x1800262b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262b7  mov     ebx, eax
0x1800262b9  test    eax, eax
0x1800262bb  js      short loc_1800262FA
0x1800262bd  mov     rax, [rsi]
0x1800262c0  xor     r8d, r8d
0x1800262c3  mov     r9, [rsp+58h+arg_20]
0x1800262cb  mov     rcx, rsi
0x1800262ce  mov     rax, [rax+38h]
0x1800262d2  lea     edx, [r8+1]
0x1800262d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800262db  mov     ebx, eax
0x1800262dd  test    eax, eax
0x1800262df  jns     short loc_180026324
0x1800262e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262e8  cmp     rcx, rdi
0x1800262eb  jz      short loc_180026324
0x1800262ed  test    byte ptr [rcx+1Ch], 2
0x1800262f1  jz      short loc_180026324
0x1800262f3  mov     edx, 48h ; 'H'
0x1800262f8  jmp     short loc_180026311
0x1800262fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180026301  cmp     rcx, rdi
0x180026304  jz      short loc_180026324
0x180026306  test    byte ptr [rcx+1Ch], 2
0x18002630a  jz      short loc_180026324
0x18002630c  mov     edx, 49h ; 'I'
0x180026311  mov     rcx, [rcx+10h]
0x180026315  lea     r8, WPP_c6bc03e7edc434bf83e25828c0be9252_Traceguids
0x18002631c  mov     r9d, eax
0x18002631f  call    WPP_SF_d
0x180026324  mov     eax, ebx
0x180026326  add     rsp, 38h
0x18002632a  pop     rdi
0x18002632b  pop     rsi
0x18002632c  pop     rbp
0x18002632d  pop     rbx
0x18002632e  retn
```
