# GetSharedSecurityFromDescriptorUnsafe

- ea: `0x1c015152c`
- end: `0x1c015169e`
- name: `GetSharedSecurityFromDescriptorUnsafe`
- size: `370`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1c0151410`
- `0x1c016ab0c`

## callees

- `0x1c000f770`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c006acc0`
- `0x1c0097cc8`
- `0x1c015152c`
- `0x1c01516a4`
- `0x1c01516f4`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01515e4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c01515e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0181b64`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0181b64`
- `ntoskrnl!ExRaiseStatus` at `0x1c0181b52`
- `ntoskrnl!ExRaiseStatus` at `0x1c0181b52`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x1c0151559`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x1c0181a75`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x1c0151559`
- `ntoskrnl!SeValidSecurityDescriptor` at `0x1c0181a75`
- `ntoskrnl!RtlNormalizeSecurityDescriptor` at `0x1c0151611`
- `ntoskrnl!RtlNormalizeSecurityDescriptor` at `0x1c0151611`

## pseudocode

```c
_DWORD *__fastcall GetSharedSecurityFromDescriptorUnsafe(__int64 a1, void *a2, ULONG a3, char a4)
{
  ULONG v5; // esi
  ULONG v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // r15d
  _DWORD *i; // rcx
  _DWORD *CachedSharedSecurityByHashUnsafe; // rdi
  unsigned int v12; // edi
  _DWORD *PoolWithTag; // rax
  void *v14; // r15
  ULONG v15; // eax
  _DWORD *j; // rcx
  __int64 v17; // r14
  int v19; // [rsp+20h] [rbp-20h]
  _DWORD *v20; // [rsp+30h] [rbp-10h] BYREF
  void *Src; // [rsp+78h] [rbp+38h] BYREF
  ULONG v22; // [rsp+80h] [rbp+40h] BYREF

  Src = a2;
  v5 = a3;
  if ( !a3 || !SeValidSecurityDescriptor(a3, a2) )
  {
    if ( a4 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_838d735f45793e0c3968f803c105c9c3_Traceguids, 3221225593LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741703);
      RefsRaiseStatusInternal(a1, 3221225593LL);
      __debugbreak();
    }
    v5 = Length;
    Src = NewDescriptor;
    if ( !SeValidSecurityDescriptor(Length, NewDescriptor) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_838d735f45793e0c3968f803c105c9c3_Traceguids, 3221225485LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741811);
      RefsRaiseStatusInternal(a1, 3221225485LL);
      __debugbreak();
    }
  }
  v7 = v5 >> 2;
  v8 = 0;
  v9 = -1;
  for ( i = Src; v7; --v7 )
    v8 = *i++ + __ROL4__(v8, 3);
  CachedSharedSecurityByHashUnsafe = (_DWORD *)FindCachedSharedSecurityByHashUnsafe(*(_QWORD *)(a1 + 64), Src, v5, v8);
  if ( CachedSharedSecurityByHashUnsafe )
    return CachedSharedSecurityByHashUnsafe;
  v12 = v5 + 20;
  if ( v5 < 0xFFFFFFEC )
    v9 = v5 + 20;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( v12 >= 0x14 )
      goto LABEL_10;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        23,
        WPP_838d735f45793e0c3968f803c105c9c3_Traceguids,
        3221225859LL,
        -1073741675);
  }
  if ( v12 < 0x14 )
  {
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741437);
    ExRaiseStatus(-1073741437);
  }
LABEL_10:
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)17, v9, 0x53466552u);
  v22 = v5;
  LOBYTE(v19) = 0;
  v14 = PoolWithTag + 5;
  CachedSharedSecurityByHashUnsafe = PoolWithTag;
  v20 = PoolWithTag + 5;
  if ( !(unsigned __int8)RtlNormalizeSecurityDescriptor(&Src, v5, &v20, &v22, v19) )
    goto LABEL_14;
  v8 = 0;
  v15 = v22 >> 2;
  for ( j = v20; v15; --v15 )
    v8 = *j++ + __ROL4__(v8, 3);
  v17 = FindCachedSharedSecurityByHashUnsafe(*(_QWORD *)(a1 + 64), v20, v22, v8);
  if ( !v17 )
  {
LABEL_14:
    *CachedSharedSecurityByHashUnsafe = 0;
    CachedSharedSecurityByHashUnsafe[3] = 0;
    CachedSharedSecurityByHashUnsafe[4] = v5 + 12;
    CachedSharedSecurityByHashUnsafe[2] = v8;
    CachedSharedSecurityByHashUnsafe[1] = RefsSecurityDescriptorFlags(Src);
    memmove(v14, Src, v5);
    return CachedSharedSecurityByHashUnsafe;
  }
  ExFreePoolWithTag(CachedSharedSecurityByHashUnsafe, 0);
  return (_DWORD *)v17;
}

```

## disassembly

```asm
0x1c015152c  mov     [rsp-28h+arg_0], rbx
0x1c0151531  mov     [rsp-28h+Src], rdx
0x1c0151536  push    rbp
0x1c0151537  push    rsi
0x1c0151538  push    rdi
0x1c0151539  push    r14
0x1c015153b  push    r15
0x1c015153d  mov     rbp, rsp
0x1c0151540  sub     rsp, 40h
0x1c0151544  mov     bl, r9b
0x1c0151547  mov     esi, r8d
0x1c015154a  mov     r14, rcx
0x1c015154d  test    r8d, r8d
0x1c0151550  jz      loc_1C01819F6
0x1c0151556  mov     ecx, r8d; Length
0x1c0151559  call    cs:__imp_SeValidSecurityDescriptor
0x1c0151560  nop     dword ptr [rax+rax+00h]
0x1c0151565  test    al, al
0x1c0151567  jz      loc_1C01819F6
0x1c015156d  mov     rdx, [rbp+Src]
0x1c0151571  mov     eax, esi
0x1c0151573  shr     eax, 2
0x1c0151576  xor     ebx, ebx
0x1c0151578  or      r15d, 0FFFFFFFFh
0x1c015157c  mov     rcx, rdx
0x1c015157f  test    eax, eax
0x1c0151581  jz      short loc_1C0151591
0x1c0151583  rol     ebx, 3
0x1c0151586  add     ebx, [rcx]
0x1c0151588  lea     rcx, [rcx+4]
0x1c015158c  add     eax, r15d
0x1c015158f  jnz     short loc_1C0151583
0x1c0151591  mov     rcx, [r14+40h]
0x1c0151595  mov     r9d, ebx
0x1c0151598  mov     r8d, esi
0x1c015159b  call    FindCachedSharedSecurityByHashUnsafe
0x1c01515a0  mov     rdi, rax
0x1c01515a3  test    rax, rax
0x1c01515a6  jnz     loc_1C0151689
0x1c01515ac  lea     edi, [rsi+14h]
0x1c01515af  cmp     edi, 14h
0x1c01515b2  cmovnb  r15d, edi
0x1c01515b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01515bd  lea     rax, WPP_GLOBAL_Control
0x1c01515c4  cmp     rcx, rax
0x1c01515c7  jz      loc_1C0181B23
0x1c01515cd  cmp     edi, 14h
0x1c01515d0  jb      loc_1C0181AF1
0x1c01515d6  mov     edx, r15d; NumberOfBytes
0x1c01515d9  mov     ecx, 11h; PoolType
0x1c01515de  mov     r8d, 53466552h; Tag
0x1c01515e4  call    cs:__imp_ExAllocatePoolWithTag
0x1c01515eb  nop     dword ptr [rax+rax+00h]
0x1c01515f0  lea     r9, [rbp+arg_10]
0x1c01515f4  mov     [rbp+arg_10], esi
0x1c01515f7  lea     r8, [rbp+var_10]
0x1c01515fb  mov     byte ptr [rsp+40h+var_20], 0
0x1c0151600  mov     edx, esi
0x1c0151602  lea     rcx, [rbp+Src]
0x1c0151606  lea     r15, [rax+14h]
0x1c015160a  mov     rdi, rax
0x1c015160d  mov     [rbp+var_10], r15
0x1c0151611  call    cs:__imp_RtlNormalizeSecurityDescriptor
0x1c0151618  nop     dword ptr [rax+rax+00h]
0x1c015161d  test    al, al
0x1c015161f  jz      short loc_1C015165E
0x1c0151621  mov     r8d, [rbp+arg_10]
0x1c0151625  xor     ebx, ebx
0x1c0151627  mov     rdx, [rbp+var_10]
0x1c015162b  mov     eax, r8d
0x1c015162e  shr     eax, 2
0x1c0151631  mov     rcx, rdx
0x1c0151634  test    eax, eax
0x1c0151636  jz      short loc_1C0151646
0x1c0151638  rol     ebx, 3
0x1c015163b  add     ebx, [rcx]
0x1c015163d  lea     rcx, [rcx+4]
0x1c0151641  add     eax, 0FFFFFFFFh
0x1c0151644  jnz     short loc_1C0151638
0x1c0151646  mov     rcx, [r14+40h]
0x1c015164a  mov     r9d, ebx
0x1c015164d  call    FindCachedSharedSecurityByHashUnsafe
0x1c0151652  mov     r14, rax
0x1c0151655  test    rax, rax
0x1c0151658  jnz     loc_1C0181B5F
0x1c015165e  and     dword ptr [rdi], 0
0x1c0151661  lea     eax, [rsi+0Ch]
0x1c0151664  and     dword ptr [rdi+0Ch], 0
0x1c0151668  mov     [rdi+10h], eax
0x1c015166b  mov     [rdi+8], ebx
0x1c015166e  mov     rcx, [rbp+Src]; SecurityDescriptor
0x1c0151672  call    RefsSecurityDescriptorFlags
0x1c0151677  mov     [rdi+4], eax
0x1c015167a  mov     rcx, r15; void *
0x1c015167d  mov     rdx, [rbp+Src]; Src
0x1c0151681  mov     r8d, esi; Size
0x1c0151684  call    memmove
0x1c0151689  mov     rax, rdi
0x1c015168c  mov     rbx, [rsp+40h+arg_0]
0x1c0151691  add     rsp, 40h
0x1c0151695  pop     r15
0x1c0151697  pop     r14
0x1c0151699  pop     rdi
0x1c015169a  pop     rsi
0x1c015169b  pop     rbp
0x1c015169c  retn
0x1c01819f6  test    bl, bl
0x1c01819f8  jz      short loc_1C0181A62
0x1c01819fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0181a01  lea     rax, WPP_GLOBAL_Control
0x1c0181a08  mov     ebx, 0C0000079h
0x1c0181a0d  cmp     rcx, rax
0x1c0181a10  jz      short loc_1C0181A39
0x1c0181a12  test    dword ptr [rcx+2Ch], 100h
0x1c0181a19  jz      short loc_1C0181A39
0x1c0181a1b  cmp     byte ptr [rcx+29h], 4
0x1c0181a1f  jb      short loc_1C0181A39
0x1c0181a21  mov     rcx, [rcx+18h]
0x1c0181a25  lea     r8, WPP_838d735f45793e0c3968f803c105c9c3_Traceguids
0x1c0181a2c  mov     edx, 15h
0x1c0181a31  mov     r9d, ebx
0x1c0181a34  call    WPP_SF_D
0x1c0181a39  mov     al, cs:RefsStatusDebugEnabled
0x1c0181a3f  test    al, al
0x1c0181a41  jz      short loc_1C0181A57
0x1c0181a43  mov     r8d, 8F5h
0x1c0181a49  lea     rdx, aSecursupC; "SecurSup.c"
0x1c0181a50  mov     ecx, ebx; Status
0x1c0181a52  call    RefsStatusDebug
0x1c0181a57  mov     edx, ebx
0x1c0181a59  mov     rcx, r14
0x1c0181a5c  call    RefsRaiseStatusInternal
0x1c0181a61  int     3; Trap to Debugger
0x1c0181a62  mov     rdx, cs:NewDescriptor; SecurityDescriptor
0x1c0181a69  mov     esi, cs:Length
0x1c0181a6f  mov     ecx, esi; Length
0x1c0181a71  mov     [rbp+Src], rdx
0x1c0181a75  call    cs:__imp_SeValidSecurityDescriptor
0x1c0181a7c  nop     dword ptr [rax+rax+00h]
0x1c0181a81  test    al, al
0x1c0181a83  jnz     loc_1C015156D
0x1c0181a89  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0181a90  lea     rax, WPP_GLOBAL_Control
0x1c0181a97  mov     ebx, 0C000000Dh
0x1c0181a9c  cmp     rcx, rax
0x1c0181a9f  jz      short loc_1C0181AC8
0x1c0181aa1  test    dword ptr [rcx+2Ch], 100h
0x1c0181aa8  jz      short loc_1C0181AC8
0x1c0181aaa  cmp     byte ptr [rcx+29h], 4
0x1c0181aae  jb      short loc_1C0181AC8
0x1c0181ab0  mov     rcx, [rcx+18h]
0x1c0181ab4  lea     r8, WPP_838d735f45793e0c3968f803c105c9c3_Traceguids
0x1c0181abb  mov     edx, 16h
0x1c0181ac0  mov     r9d, ebx
0x1c0181ac3  call    WPP_SF_D
0x1c0181ac8  mov     al, cs:RefsStatusDebugEnabled
0x1c0181ace  test    al, al
0x1c0181ad0  jz      short loc_1C0181AE6
0x1c0181ad2  mov     r8d, 8FFh
0x1c0181ad8  lea     rdx, aSecursupC; "SecurSup.c"
0x1c0181adf  mov     ecx, ebx; Status
0x1c0181ae1  call    RefsStatusDebug
0x1c0181ae6  mov     edx, ebx
0x1c0181ae8  mov     rcx, r14
0x1c0181aeb  call    RefsRaiseStatusInternal
0x1c0181af0  int     3; Trap to Debugger
0x1c0181af1  test    dword ptr [rcx+2Ch], 100h
0x1c0181af8  jz      short loc_1C0181B23
0x1c0181afa  cmp     byte ptr [rcx+29h], 4
0x1c0181afe  jb      short loc_1C0181B23
0x1c0181b00  mov     rcx, [rcx+18h]
0x1c0181b04  lea     r8, WPP_838d735f45793e0c3968f803c105c9c3_Traceguids
0x1c0181b0b  mov     edx, 17h
0x1c0181b10  mov     [rsp+40h+var_20], 0C0000095h
0x1c0181b18  mov     r9d, 0C0000183h
0x1c0181b1e  call    WPP_SF_DD
0x1c0181b23  cmp     edi, 14h
0x1c0181b26  jnb     loc_1C01515D6
0x1c0181b2c  mov     al, cs:RefsStatusDebugEnabled
0x1c0181b32  test    al, al
0x1c0181b34  jz      short loc_1C0181B4D
0x1c0181b36  mov     r8d, 91Bh
0x1c0181b3c  lea     rdx, aSecursupC; "SecurSup.c"
0x1c0181b43  mov     ecx, 0C0000183h; Status
0x1c0181b48  call    RefsStatusDebug
0x1c0181b4d  mov     ecx, 0C0000183h; Status
0x1c0181b52  call    cs:__imp_ExRaiseStatus
0x1c0181b5f  xor     edx, edx; Tag
0x1c0181b61  mov     rcx, rdi; P
0x1c0181b64  call    cs:__imp_ExFreePoolWithTag
0x1c0181b6b  nop     dword ptr [rax+rax+00h]
0x1c0181b70  mov     rax, r14
0x1c0181b73  jmp     loc_1C015168C
```
