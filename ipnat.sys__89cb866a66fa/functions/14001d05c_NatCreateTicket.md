# NatCreateTicket

- ea: `0x14001d05c`
- end: `0x14001d488`
- name: `NatCreateTicket`
- size: `1068`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x140005780`
- `0x140013550`
- `0x14001daa0`

## callees

- `0x1400021bc`
- `0x140006a08`
- `0x14000fe48`
- `0x140011e00`
- `0x1400123a8`
- `0x1400138fc`
- `0x14001d05c`
- `0x14001e0f8`
- `0x14001ed10`

## pseudocode

```c
__int64 __fastcall NatCreateTicket(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        unsigned int a5,
        int a6,
        int a7,
        __int64 a8,
        unsigned __int16 a9,
        unsigned int *a10,
        unsigned __int16 *a11)
{
  unsigned int v12; // r15d
  __int64 v13; // r14
  unsigned __int16 v15; // r8
  unsigned int *v16; // rdx
  __int64 v17; // rsi
  unsigned __int16 *v18; // rax
  __int64 v19; // rsi
  __int64 v20; // r14
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  unsigned int v24; // esi
  int v25; // r8d
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  _QWORD *v28; // rcx
  __int64 v29; // rax
  _QWORD *v30; // rdx
  _QWORD *v31; // [rsp+60h] [rbp-18h] BYREF
  __int64 v32; // [rsp+68h] [rbp-10h] BYREF

  v12 = a3;
  v13 = (unsigned __int8)a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_dDdDdDdd(WPP_GLOBAL_Control->AttachedDevice, a2, a3, (unsigned __int8)a2, a3, a4, a5, a6, a7, a9);
  }
  v32 = 0;
  v31 = 0;
  if ( a8 )
  {
    if ( *(int *)(a8 + 72) < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return 3221225473LL;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225473LL);
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
      {
        return 3221225473LL;
      }
      v22 = 32;
      goto LABEL_19;
    }
    _InterlockedIncrement((volatile signed __int32 *)(a8 + 76));
  }
  else
  {
    v24 = NatAcquireFromAddressPool(a1, v12, 0, &a8);
    if ( (v24 & 0x80000000) != 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return v24;
      }
      v27 = 33;
LABEL_34:
      WPP_SF_d(v26->AttachedDevice, v27, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, v24);
      return v24;
    }
    LOBYTE(v25) = v13;
    v24 = NatAcquireFromPortPool(a1, a8, v25, a4, (__int64)&a9);
    if ( (v24 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, v24);
      }
      NatDereferenceAddressPoolEntry(a1, a8);
      return v24;
    }
  }
  v15 = a9;
  v16 = a10;
  v17 = a9;
  v18 = a11;
  *a10 = *(_DWORD *)(a8 + 52);
  *v18 = v15;
  v19 = *v16 | (((v13 << 16) | v17) << 32);
  v20 = a5 | (((v13 << 16) | (unsigned __int16)a6) << 32);
  if ( NatLookupTicket(a1, v19, v20, &v32) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_ii(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, v19, v20);
    }
    if ( a8 )
      NatDereferenceAddressPoolEntry(a1, a8);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return 3221225473LL;
    }
    v22 = 36;
LABEL_19:
    WPP_SF_d(v21->AttachedDevice, v22, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225473LL);
    return 3221225473LL;
  }
  NatAllocateBlockWithLimitCheck(&TicketLookasideList, (PVOID *)&v31, 64);
  v28 = v31;
  if ( !v31 )
  {
    v24 = -1073741801;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 3221225495LL);
    }
    if ( a8 )
      NatDereferenceAddressPoolEntry(a1, a8);
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 6u )
    {
      return v24;
    }
    v27 = 38;
    goto LABEL_34;
  }
  v31[2] = v19;
  v28[3] = v20;
  *((_DWORD *)v28 + 12) = a7;
  v28[4] = a8;
  *((_DWORD *)v28 + 10) = v12;
  if ( (v28[6] & 4) != 0 )
    *((_WORD *)v28 + 22) = HIBYTE(a4) | ((unsigned __int8)a4 << 8);
  else
    *((_WORD *)v28 + 22) = a4;
  if ( (a7 & 8) != 0 )
    *((_DWORD *)v28 + 13) = 0;
  v29 = v32;
  v30 = *(_QWORD **)(v32 + 8);
  if ( *v30 != v32 )
    __fastfail(3u);
  *v28 = v32;
  v28[1] = v30;
  *v30 = v28;
  *(_QWORD *)(v29 + 8) = v28;
  v28[7] = MEMORY[0xFFFFF78000000320];
  _InterlockedIncrement(&TicketCount);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14001d05c  push    rbp
0x14001d05e  push    rbx
0x14001d05f  push    rsi
0x14001d060  push    rdi
0x14001d061  push    r12
0x14001d063  push    r13
0x14001d065  push    r14
0x14001d067  push    r15
0x14001d069  mov     rbp, rsp
0x14001d06c  sub     rsp, 78h
0x14001d070  movzx   ebx, r9w
0x14001d074  mov     r15d, r8d
0x14001d077  movzx   r14d, dl
0x14001d07b  mov     rdi, rcx
0x14001d07e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d085  lea     rsi, WPP_GLOBAL_Control
0x14001d08c  mov     r12d, [rbp+arg_30]
0x14001d090  mov     r13d, [rbp+arg_28]
0x14001d094  cmp     rcx, rsi
0x14001d097  jz      short loc_14001D0D7
0x14001d099  mov     eax, [rcx+2Ch]
0x14001d09c  test    al, 1
0x14001d09e  jz      short loc_14001D0D7
0x14001d0a0  cmp     byte ptr [rcx+29h], 6
0x14001d0a4  jb      short loc_14001D0D7
0x14001d0a6  movzx   eax, [rbp+arg_40]
0x14001d0ad  mov     r9d, r14d
0x14001d0b0  mov     rcx, [rcx+18h]
0x14001d0b4  mov     [rsp+78h+var_30], eax
0x14001d0b8  mov     eax, [rbp+arg_20]
0x14001d0bb  mov     [rsp+78h+var_38], r12d
0x14001d0c0  mov     [rsp+78h+var_40], r13d
0x14001d0c5  mov     [rsp+78h+var_48], eax
0x14001d0c9  mov     [rsp+78h+var_50], ebx
0x14001d0cd  mov     dword ptr [rsp+78h+var_58], r8d
0x14001d0d2  call    WPP_SF_dDdDdDdd
0x14001d0d7  mov     rax, [rbp+arg_38]
0x14001d0de  xor     ecx, ecx
0x14001d0e0  mov     [rbp+var_10], rcx
0x14001d0e4  mov     [rbp+var_18], rcx
0x14001d0e8  test    rax, rax
0x14001d0eb  jz      loc_14001D24B
0x14001d0f1  cmp     [rax+48h], ecx
0x14001d0f4  jl      loc_14001D1F7
0x14001d0fa  lock inc dword ptr [rax+4Ch]
0x14001d0fe  movzx   r8d, [rbp+arg_40]
0x14001d106  lea     r9, [rbp+var_10]
0x14001d10a  mov     rax, [rbp+arg_38]
0x14001d111  mov     rdx, [rbp+arg_48]
0x14001d118  movzx   esi, r8w
0x14001d11c  mov     ecx, [rax+34h]
0x14001d11f  mov     rax, [rbp+arg_50]
0x14001d126  mov     [rdx], ecx
0x14001d128  mov     rcx, r14
0x14001d12b  shl     rcx, 10h
0x14001d12f  or      rsi, rcx
0x14001d132  movzx   r14d, r13w
0x14001d136  mov     [rax], r8w
0x14001d13a  or      r14, rcx
0x14001d13d  mov     eax, [rdx]
0x14001d13f  mov     rcx, rdi
0x14001d142  shl     rsi, 20h
0x14001d146  or      rsi, rax
0x14001d149  shl     r14, 20h
0x14001d14d  mov     eax, [rbp+arg_20]
0x14001d150  mov     rdx, rsi
0x14001d153  or      r14, rax
0x14001d156  mov     r8, r14
0x14001d159  call    NatLookupTicket
0x14001d15e  test    rax, rax
0x14001d161  jz      loc_14001D31A
0x14001d167  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d16e  lea     rbx, WPP_GLOBAL_Control
0x14001d175  cmp     rcx, rbx
0x14001d178  jz      short loc_14001D1A4
0x14001d17a  mov     eax, [rcx+2Ch]
0x14001d17d  test    al, 1
0x14001d17f  jz      short loc_14001D1A4
0x14001d181  cmp     byte ptr [rcx+29h], 2
0x14001d185  jb      short loc_14001D1A4
0x14001d187  mov     rcx, [rcx+18h]
0x14001d18b  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001d192  mov     edx, 23h ; '#'
0x14001d197  mov     [rsp+78h+var_58], r14
0x14001d19c  mov     r9, rsi
0x14001d19f  call    WPP_SF_ii
0x14001d1a4  mov     rdx, [rbp+arg_38]
0x14001d1ab  test    rdx, rdx
0x14001d1ae  jz      short loc_14001D1B8
0x14001d1b0  mov     rcx, rdi
0x14001d1b3  call    NatDereferenceAddressPoolEntry
0x14001d1b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d1bf  cmp     rcx, rbx
0x14001d1c2  jz      short loc_14001D1ED
0x14001d1c4  mov     edx, [rcx+2Ch]
0x14001d1c7  test    dl, 1
0x14001d1ca  jz      short loc_14001D1ED
0x14001d1cc  cmp     byte ptr [rcx+29h], 6
0x14001d1d0  jb      short loc_14001D1ED
0x14001d1d2  mov     edx, 24h ; '$'
0x14001d1d7  mov     rcx, [rcx+18h]
0x14001d1db  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001d1e2  mov     r9d, 0C0000001h
0x14001d1e8  call    WPP_SF_d
0x14001d1ed  mov     eax, 0C0000001h
0x14001d1f2  jmp     loc_14001D476
0x14001d1f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d1fe  cmp     rcx, rsi
0x14001d201  jz      short loc_14001D1ED
0x14001d203  mov     eax, [rcx+2Ch]
0x14001d206  test    al, 1
0x14001d208  jz      short loc_14001D22B
0x14001d20a  cmp     byte ptr [rcx+29h], 2
0x14001d20e  jb      short loc_14001D22B
0x14001d210  mov     rcx, [rcx+18h]
0x14001d214  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001d21b  mov     edx, 1Fh
0x14001d220  mov     r9d, 0C0000001h
0x14001d226  call    WPP_SF_d
0x14001d22b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d232  cmp     rcx, rsi
0x14001d235  jz      short loc_14001D1ED
0x14001d237  mov     eax, [rcx+2Ch]
0x14001d23a  test    al, 1
0x14001d23c  jz      short loc_14001D1ED
0x14001d23e  cmp     byte ptr [rcx+29h], 6
0x14001d242  jb      short loc_14001D1ED
0x14001d244  mov     edx, 20h ; ' '
0x14001d249  jmp     short loc_14001D1D7
0x14001d24b  lea     r9, [rbp+arg_38]
0x14001d252  xor     r8d, r8d
0x14001d255  mov     edx, r15d
0x14001d258  mov     rcx, rdi
0x14001d25b  call    NatAcquireFromAddressPool
0x14001d260  mov     esi, eax
0x14001d262  test    eax, eax
0x14001d264  jns     short loc_14001D2A5
0x14001d266  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d26d  lea     rbx, WPP_GLOBAL_Control
0x14001d274  cmp     rcx, rbx
0x14001d277  jz      short loc_14001D29E
0x14001d279  mov     eax, [rcx+2Ch]
0x14001d27c  test    al, 1
0x14001d27e  jz      short loc_14001D29E
0x14001d280  cmp     byte ptr [rcx+29h], 2
0x14001d284  jb      short loc_14001D29E
0x14001d286  mov     edx, 21h ; '!'
0x14001d28b  mov     rcx, [rcx+18h]
0x14001d28f  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001d296  mov     r9d, esi
0x14001d299  call    WPP_SF_d
0x14001d29e  mov     eax, esi
0x14001d2a0  jmp     loc_14001D476
0x14001d2a5  mov     rdx, [rbp+arg_38]
0x14001d2ac  lea     rax, [rbp+arg_40]
0x14001d2b3  movzx   r9d, bx
0x14001d2b7  mov     [rsp+78h+var_58], rax
0x14001d2bc  mov     r8b, r14b
0x14001d2bf  mov     rcx, rdi
0x14001d2c2  call    NatAcquireFromPortPool
0x14001d2c7  mov     esi, eax
0x14001d2c9  test    eax, eax
0x14001d2cb  jns     loc_14001D0FE
0x14001d2d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d2d8  lea     rbx, WPP_GLOBAL_Control
0x14001d2df  cmp     rcx, rbx
0x14001d2e2  jz      short loc_14001D309
0x14001d2e4  mov     eax, [rcx+2Ch]
0x14001d2e7  test    al, 1
0x14001d2e9  jz      short loc_14001D309
0x14001d2eb  cmp     byte ptr [rcx+29h], 2
0x14001d2ef  jb      short loc_14001D309
0x14001d2f1  mov     rcx, [rcx+18h]
0x14001d2f5  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001d2fc  mov     edx, 22h ; '"'
0x14001d301  mov     r9d, esi
0x14001d304  call    WPP_SF_d
0x14001d309  mov     rdx, [rbp+arg_38]
0x14001d310  mov     rcx, rdi
0x14001d313  call    NatDereferenceAddressPoolEntry
0x14001d318  jmp     short loc_14001D29E
0x14001d31a  mov     r8d, 40h ; '@'
0x14001d320  lea     rdx, [rbp+var_18]
0x14001d324  lea     rcx, TicketLookasideList; Lookaside
0x14001d32b  call    NatAllocateBlockWithLimitCheck
0x14001d330  mov     rcx, [rbp+var_18]
0x14001d334  test    rcx, rcx
0x14001d337  jnz     loc_14001D3BE
0x14001d33d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d344  lea     rbx, WPP_GLOBAL_Control
0x14001d34b  mov     esi, 0C0000017h
0x14001d350  cmp     rcx, rbx
0x14001d353  jz      short loc_14001D37A
0x14001d355  mov     eax, [rcx+2Ch]
0x14001d358  test    al, 1
0x14001d35a  jz      short loc_14001D37A
0x14001d35c  cmp     byte ptr [rcx+29h], 2
0x14001d360  jb      short loc_14001D37A
0x14001d362  mov     rcx, [rcx+18h]
0x14001d366  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001d36d  mov     edx, 25h ; '%'
0x14001d372  mov     r9d, esi
0x14001d375  call    WPP_SF_d
0x14001d37a  mov     rdx, [rbp+arg_38]
0x14001d381  test    rdx, rdx
0x14001d384  jz      short loc_14001D38E
0x14001d386  mov     rcx, rdi
0x14001d389  call    NatDereferenceAddressPoolEntry
0x14001d38e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d395  cmp     rcx, rbx
0x14001d398  jz      loc_14001D29E
0x14001d39e  mov     edx, [rcx+2Ch]
0x14001d3a1  test    dl, 1
0x14001d3a4  jz      loc_14001D29E
0x14001d3aa  cmp     byte ptr [rcx+29h], 6
0x14001d3ae  jb      loc_14001D29E
0x14001d3b4  mov     edx, 26h ; '&'
0x14001d3b9  jmp     loc_14001D28B
0x14001d3be  mov     [rcx+10h], rsi
0x14001d3c2  mov     [rcx+18h], r14
0x14001d3c6  mov     [rcx+30h], r12d
0x14001d3ca  mov     rax, [rbp+arg_38]
0x14001d3d1  mov     [rcx+20h], rax
0x14001d3d5  mov     [rcx+28h], r15d
0x14001d3d9  mov     eax, [rcx+30h]
0x14001d3dc  test    al, 4
0x14001d3de  jz      short loc_14001D3F4
0x14001d3e0  movzx   eax, bl
0x14001d3e3  shl     ax, 8
0x14001d3e7  shr     bx, 8
0x14001d3eb  or      ax, bx
0x14001d3ee  mov     [rcx+2Ch], ax
0x14001d3f2  jmp     short loc_14001D3F8
0x14001d3f4  mov     [rcx+2Ch], bx
0x14001d3f8  test    r12b, 8
0x14001d3fc  jz      short loc_14001D405
0x14001d3fe  mov     dword ptr [rcx+34h], 0
0x14001d405  mov     rax, [rbp+var_10]
0x14001d409  mov     rdx, [rax+8]
0x14001d40d  cmp     [rdx], rax
0x14001d410  jz      short loc_14001D419
0x14001d412  mov     ecx, 3
0x14001d417  int     29h; Win8: RtlFailFast(ecx)
0x14001d419  mov     [rcx], rax
0x14001d41c  mov     [rcx+8], rdx
0x14001d420  mov     [rdx], rcx
0x14001d423  mov     [rax+8], rcx
0x14001d427  mov     rax, ds:0FFFFF78000000320h
0x14001d431  mov     [rcx+38h], rax
0x14001d435  lock inc cs:TicketCount
0x14001d43c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d443  lea     rbx, WPP_GLOBAL_Control
0x14001d44a  cmp     rcx, rbx
0x14001d44d  jz      short loc_14001D474
0x14001d44f  mov     eax, [rcx+2Ch]
0x14001d452  test    al, 1
0x14001d454  jz      short loc_14001D474
0x14001d456  cmp     byte ptr [rcx+29h], 6
0x14001d45a  jb      short loc_14001D474
0x14001d45c  mov     rcx, [rcx+18h]
0x14001d460  lea     r8, WPP_7bd61f7e30ad3adb41e85a1a6fd66ec1_Traceguids
0x14001d467  mov     edx, 27h ; '''
0x14001d46c  xor     r9d, r9d
0x14001d46f  call    WPP_SF_d
0x14001d474  xor     eax, eax
0x14001d476  add     rsp, 78h
0x14001d47a  pop     r15
0x14001d47c  pop     r14
0x14001d47e  pop     r13
0x14001d480  pop     r12
0x14001d482  pop     rdi
0x14001d483  pop     rsi
0x14001d484  pop     rbx
0x14001d485  pop     rbp
0x14001d486  retn
```
