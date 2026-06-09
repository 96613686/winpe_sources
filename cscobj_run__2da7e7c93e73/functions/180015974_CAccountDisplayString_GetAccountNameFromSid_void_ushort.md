# CAccountDisplayString::_GetAccountNameFromSid(void *,ushort * *)

- ea: `0x180015974`
- end: `0x180015ab4`
- name: `?_GetAccountNameFromSid@CAccountDisplayString@@AEAAJPEAXPEAPEAG@Z`
- size: `320`
- prototype: `int(CAccountDisplayString *__hidden this, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180014f50`

## callees

- `0x1800084e0`
- `0x1800140c8`
- `0x1800146d4`
- `0x1800157b0`
- `0x180015974`
- `0x18002a680`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015a9d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180015a6f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180015a6f`

## pseudocode

```c
__int64 __fastcall CAccountDisplayString::_GetAccountNameFromSid(
        CAccountDisplayString *this,
        void *a2,
        unsigned __int16 **a3)
{
  int v5; // ebx
  void *v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int16 *v9; // r14
  __int64 v10; // rdi
  void *v11; // rdx
  unsigned __int64 v12; // rdx
  void *v13; // rdi
  void *v14; // rdx
  LPWSTR v15; // rcx
  LPWSTR StringSid; // [rsp+38h] [rbp-8h] BYREF
  enum _SID_NAME_USE v18; // [rsp+80h] [rbp+40h] BYREF
  int v19; // [rsp+84h] [rbp+44h]
  void *lpMem; // [rsp+90h] [rbp+50h] BYREF
  unsigned __int16 *v21; // [rsp+98h] [rbp+58h] BYREF

  v19 = HIDWORD(this);
  *a3 = 0;
  lpMem = 0;
  v21 = 0;
  v18 = 0;
  v5 = CscSec_LookupAccountSid((const unsigned __int16 *)this, a2, &v21, (unsigned __int16 **)&lpMem, &v18);
  if ( v5 < 0 )
  {
    v15 = 0;
    StringSid = 0;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      ConvertSidToStringSidW(a2, &StringSid);
      WPP_SF_SD(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        10,
        (unsigned int)WPP_546654fa3bcd3901976ed382fbfa1007_Traceguids,
        (_DWORD)StringSid,
        v5);
      v15 = StringSid;
    }
    LocalFree(v15);
  }
  else
  {
    v6 = lpMem;
    v7 = -1;
    v8 = -1;
    do
      ++v8;
    while ( *((_WORD *)lpMem + v8) );
    v9 = v21;
    do
      ++v7;
    while ( v21[v7] );
    v10 = v7 + v8;
    lpMem = 0;
    v5 = CscUtil_HeapAllocArray<unsigned short>(v7 + v8 + 2, &lpMem);
    if ( v5 >= 0 )
    {
      v12 = v10 + 2;
      v13 = lpMem;
      v5 = StringCchPrintfW((unsigned __int16 *)lpMem, v12, L"%s\\%s", v6, v9);
      if ( v5 < 0 )
        CscUtil_HeapFree(v13, v11);
      else
        *a3 = (unsigned __int16 *)v13;
    }
    CscUtil_HeapFree(v9, v11);
    CscUtil_HeapFree(v6, v14);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180015974  mov     qword ptr [rsp-38h+arg_0], rcx
0x180015979  push    rbp
0x18001597a  push    rbx
0x18001597b  push    rsi
0x18001597c  push    rdi
0x18001597d  push    r12
0x18001597f  push    r14
0x180015981  push    r15
0x180015983  mov     rbp, rsp
0x180015986  sub     rsp, 40h
0x18001598a  xor     r12d, r12d
0x18001598d  lea     rax, [rbp+arg_0]
0x180015991  mov     [r8], r12
0x180015994  lea     r9, [rbp+lpMem]; unsigned __int16 **
0x180015998  mov     r15, r8
0x18001599b  mov     [rbp+lpMem], r12
0x18001599f  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x1800159a3  mov     [rbp+arg_18], r12
0x1800159a7  mov     rdi, rdx
0x1800159aa  mov     [rbp+arg_0], r12d
0x1800159ae  mov     [rsp+40h+var_20], rax; enum _SID_NAME_USE *
0x1800159b3  call    ?CscSec_LookupAccountSid@@YAJPEBGPEAXPEAPEAG2PEAW4_SID_NAME_USE@@@Z; CscSec_LookupAccountSid(ushort const *,void *,ushort * *,ushort * *,_SID_NAME_USE *)
0x1800159b8  mov     ebx, eax
0x1800159ba  test    eax, eax
0x1800159bc  js      loc_180015A44
0x1800159c2  mov     rsi, [rbp+lpMem]
0x1800159c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800159ca  mov     rcx, rax
0x1800159cd  inc     rcx
0x1800159d0  cmp     [rsi+rcx*2], r12w
0x1800159d5  jnz     short loc_1800159CD
0x1800159d7  mov     r14, [rbp+arg_18]
0x1800159db  inc     rax
0x1800159de  cmp     [r14+rax*2], r12w
0x1800159e3  jnz     short loc_1800159DB
0x1800159e5  lea     rdi, [rax+rcx]
0x1800159e9  mov     [rbp+lpMem], r12
0x1800159ed  lea     rcx, [rdi+2]
0x1800159f1  lea     rdx, [rbp+lpMem]
0x1800159f5  call    ??$CscUtil_HeapAllocArray@G@@YAJ_KPEAPEAG@Z; CscUtil_HeapAllocArray<ushort>(unsigned __int64,ushort * *)
0x1800159fa  mov     ebx, eax
0x1800159fc  test    eax, eax
0x1800159fe  js      short loc_180015A32
0x180015a00  lea     rdx, [rdi+2]; unsigned __int64
0x180015a04  mov     [rsp+40h+var_20], r14
0x180015a09  mov     rdi, [rbp+lpMem]
0x180015a0d  lea     r8, aSS; "%s\\%s"
0x180015a14  mov     rcx, rdi; unsigned __int16 *
0x180015a17  mov     r9, rsi
0x180015a1a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015a1f  mov     ebx, eax
0x180015a21  test    eax, eax
0x180015a23  js      short loc_180015A2A
0x180015a25  mov     [r15], rdi
0x180015a28  jmp     short loc_180015A32
0x180015a2a  mov     rcx, rdi; lpMem
0x180015a2d  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180015a32  mov     rcx, r14; lpMem
0x180015a35  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180015a3a  mov     rcx, rsi; lpMem
0x180015a3d  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180015a42  jmp     short loc_180015AA3
0x180015a44  mov     rcx, r12
0x180015a47  mov     [rbp+var_10], rdi
0x180015a4b  mov     [rbp+StringSid], rcx
0x180015a4f  mov     rax, cs:WPP_GLOBAL_Control
0x180015a56  lea     rdx, WPP_GLOBAL_Control
0x180015a5d  cmp     rax, rdx
0x180015a60  jz      short loc_180015A9D
0x180015a62  test    byte ptr [rax+1Ch], 2
0x180015a66  jz      short loc_180015A9D
0x180015a68  lea     rdx, [rbp+StringSid]; StringSid
0x180015a6c  mov     rcx, rdi; Sid
0x180015a6f  call    cs:__imp_ConvertSidToStringSidW
0x180015a75  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a7c  lea     r8, WPP_546654fa3bcd3901976ed382fbfa1007_Traceguids
0x180015a83  mov     r9, [rbp+StringSid]
0x180015a87  mov     edx, 0Ah
0x180015a8c  mov     dword ptr [rsp+40h+var_20], ebx
0x180015a90  mov     rcx, [rcx+10h]
0x180015a94  call    WPP_SF_SD
0x180015a99  mov     rcx, [rbp+StringSid]; hMem
0x180015a9d  call    cs:__imp_LocalFree
0x180015aa3  mov     eax, ebx
0x180015aa5  add     rsp, 40h
0x180015aa9  pop     r15
0x180015aab  pop     r14
0x180015aad  pop     r12
0x180015aaf  pop     rdi
0x180015ab0  pop     rsi
0x180015ab1  pop     rbx
0x180015ab2  pop     rbp
0x180015ab3  retn
```
