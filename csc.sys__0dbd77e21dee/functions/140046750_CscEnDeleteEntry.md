# CscEnDeleteEntry

- ea: `0x140046750`
- end: `0x140046aa4`
- name: `CscEnDeleteEntry`
- size: `852`
- prototype: `__int64 __fastcall(__int64, _BYTE *, char)`
- caller_count: `6`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x140026078`
- `0x14004a084`
- `0x14005adbc`
- `0x14005b79c`
- `0x14006a8d0`
- `0x140071c00`

## callees

- `0x1400052c0`
- `0x140005390`
- `0x140007420`
- `0x14000a64c`
- `0x140010e20`
- `0x140017908`
- `0x1400190ec`
- `0x1400197f4`
- `0x140026874`
- `0x14002a780`
- `0x14002d820`
- `0x14002f010`
- `0x140046750`
- `0x140046aac`
- `0x14005c0ec`
- `0x14005c34c`
- `0x14006a32c`
- `0x14006a5e8`
- `0x14007d934`
- `0x1400829e0`
- `0x140089a40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140046a04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046a04`

## pseudocode

```c
__int64 __fastcall CscEnDeleteEntry(__int64 a1, _BYTE *a2, char a3)
{
  char v5; // cl
  int v6; // edi
  int v7; // r9d
  int v8; // esi
  char v9; // si
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  _QWORD *v13; // rcx
  void *v14; // rcx
  __int64 v15; // rcx
  _WORD v17[2]; // [rsp+30h] [rbp-48h] BYREF
  __int16 v18; // [rsp+34h] [rbp-44h] BYREF
  __int64 v19; // [rsp+38h] [rbp-40h] BYREF
  __int128 v20; // [rsp+40h] [rbp-38h] BYREF

  v19 = 0;
  v18 = 0;
  v20 = 0;
  v17[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    if ( a2 )
      v5 = *a2 != 0 ? 89 : 78;
    else
      v5 = 63;
    WPP_SF_qc(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids, a1, v5);
  }
  CscEnpMainAcquireExclusive(a1);
  CscEnpMainAcquireExclusive(*(_QWORD *)(a1 + 24));
  v6 = CscEnpCheckState(a1);
  if ( v6 < 0 )
  {
    v8 = 7288;
    goto LABEL_33;
  }
  if ( (*(_DWORD *)(a1 + 336) & 0x10) != 0 )
  {
    v6 = CscEnpCheckDirectoryEmpty(a1);
    if ( v6 < 0 )
    {
      v8 = 7295;
      goto LABEL_33;
    }
    v9 = 1;
  }
  else
  {
    v9 = 0;
  }
  if ( *(_DWORD *)(a1 + 160) )
  {
    v6 = -1073741757;
    v8 = 7312;
  }
  else
  {
    LOBYTE(v7) = *(_WORD *)(a1 + 264) != 0;
    v6 = CscEnpQuotaPrepare(a1, 4, 0, v7, (__int64)&v20);
    if ( v6 >= 0 )
    {
      v6 = CscEnUserQueryAllPerUserInfo(a1, &v18, v17, 0, a1 + 432);
      if ( v6 >= 0 )
      {
        v6 = CscStOrphanerAddTemporaryFile(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 64LL), *(_QWORD *)(a1 + 144));
        if ( v6 >= 0 )
        {
          if ( v9 )
            CscStTuDeleteKeyFromTunnelCache(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 40LL), *(_QWORD *)(a1 + 136));
          if ( *(_WORD *)(a1 + 264) )
            CscEnDecrementPinnedDescendantCountOnUnpinOrRename((__m128i *)a1, 0);
          CscEnpChangeChildCountEx(*(_QWORD *)(a1 + 24), a1 + 192, 2);
          if ( a3 )
            CscEnpEntryToTunnel(a1);
          LOBYTE(v10) = 1;
          CscEnpDeletePQEntry(a1, v10, 0, 0);
          LOBYTE(v11) = 1;
          CscStorepLowIoSetDeleteDisposition(*(_QWORD *)(a1 + 144), v11);
          CscStorepLowIoClose(*(HANDLE *)(a1 + 144));
          *(_QWORD *)(a1 + 144) = 0;
          CscEnpNotifyItemChangedEx(a1, 32, 0);
          *(_DWORD *)(a1 + 20) |= 8u;
          if ( (*(_DWORD *)(a1 + 20) & 0x20) == 0 )
            v19 = *(_QWORD *)(a1 + 24);
          *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 24);
          *(_QWORD *)(a1 + 24) = 0;
          v12 = *(_QWORD *)(a1 + 96);
          if ( *(_QWORD *)(v12 + 8) != a1 + 96 || (v13 = *(_QWORD **)(a1 + 104), *v13 != a1 + 96) )
            __fastfail(3u);
          *v13 = v12;
          v8 = 0;
          *(_QWORD *)(v12 + 8) = v13;
          *(_BYTE *)(a1 + 440) = 0;
        }
        else
        {
          v8 = 7339;
        }
      }
      else
      {
        v8 = 7331;
      }
    }
    else
    {
      v8 = 7320;
    }
  }
LABEL_33:
  CscEnpQuotaCommit(a1, v6 >= 0, &v20);
  v14 = *(void **)(a1 + 432);
  if ( v14 )
  {
    ExFreePoolWithTag(v14, 0x21407343u);
    *(_QWORD *)(a1 + 432) = 0;
  }
  v15 = *(_QWORD *)(a1 + 32);
  if ( !v15 )
    v15 = *(_QWORD *)(a1 + 24);
  CscEnpMainRelease(v15);
  CscEnpMainRelease(a1);
  if ( v19 )
    CscEnDereferenceEntry(&v19);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      56,
      WPP_2d57263f6f6237979220aa59cf47311d_Traceguids,
      (unsigned int)v6,
      v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140046750  mov     [rsp+arg_8], rbx
0x140046755  mov     [rsp+arg_10], rbp
0x14004675a  push    rsi
0x14004675b  push    rdi
0x14004675c  push    r12
0x14004675e  sub     rsp, 60h
0x140046762  mov     rax, cs:__security_cookie
0x140046769  xor     rax, rsp
0x14004676c  mov     [rsp+78h+var_28], rax
0x140046771  xor     eax, eax
0x140046773  mov     [rsp+78h+var_40], 0
0x14004677c  xorps   xmm0, xmm0
0x14004677f  mov     [rsp+78h+var_44], ax
0x140046784  movups  [rsp+78h+var_38], xmm0
0x140046789  mov     [rsp+78h+var_48], ax
0x14004678e  mov     bpl, r8b
0x140046791  mov     rbx, rcx
0x140046794  mov     r10, cs:WPP_GLOBAL_Control
0x14004679b  lea     r12, WPP_GLOBAL_Control
0x1400467a2  cmp     r10, r12
0x1400467a5  jz      short loc_1400467E5
0x1400467a7  test    dword ptr [r10+2Ch], 40000h
0x1400467af  jz      short loc_1400467E5
0x1400467b1  test    rdx, rdx
0x1400467b4  jz      short loc_1400467C4
0x1400467b6  mov     al, [rdx]
0x1400467b8  neg     al
0x1400467ba  sbb     ecx, ecx
0x1400467bc  and     ecx, 0Bh
0x1400467bf  add     ecx, 4Eh ; 'N'
0x1400467c2  jmp     short loc_1400467C9
0x1400467c4  mov     ecx, 3Fh ; '?'
0x1400467c9  mov     byte ptr [rsp+78h+var_58], cl
0x1400467cd  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x1400467d4  mov     rcx, [r10+18h]
0x1400467d8  mov     edx, 37h ; '7'
0x1400467dd  mov     r9, rbx
0x1400467e0  call    WPP_SF_qc
0x1400467e5  mov     rcx, rbx
0x1400467e8  call    CscEnpMainAcquireExclusive
0x1400467ed  mov     rcx, [rbx+18h]
0x1400467f1  call    CscEnpMainAcquireExclusive
0x1400467f6  mov     rcx, rbx
0x1400467f9  call    CscEnpCheckState
0x1400467fe  mov     edi, eax
0x140046800  test    eax, eax
0x140046802  jns     short loc_14004680E
0x140046804  mov     esi, 1C78h
0x140046809  jmp     loc_1400469DE
0x14004680e  mov     eax, [rbx+150h]
0x140046814  test    al, 10h
0x140046816  jnz     short loc_14004681D
0x140046818  xor     sil, sil
0x14004681b  jmp     short loc_140046838
0x14004681d  mov     rcx, rbx
0x140046820  call    CscEnpCheckDirectoryEmpty
0x140046825  mov     edi, eax
0x140046827  test    eax, eax
0x140046829  jns     short loc_140046835
0x14004682b  mov     esi, 1C7Fh
0x140046830  jmp     loc_1400469DE
0x140046835  mov     sil, 1
0x140046838  cmp     dword ptr [rbx+0A0h], 0
0x14004683f  jz      short loc_140046850
0x140046841  mov     edi, 0C0000043h
0x140046846  mov     esi, 1C90h
0x14004684b  jmp     loc_1400469DE
0x140046850  movzx   eax, word ptr [rbx+108h]
0x140046857  movzx   ecx, ax
0x14004685a  shr     cx, 8
0x14004685e  test    cl, cl
0x140046860  jnz     short loc_14004686B
0x140046862  test    al, al
0x140046864  jnz     short loc_14004686B
0x140046866  xor     r9b, r9b
0x140046869  jmp     short loc_14004686E
0x14004686b  mov     r9b, 1
0x14004686e  xor     r8d, r8d
0x140046871  lea     rax, [rsp+78h+var_38]
0x140046876  mov     rcx, rbx
0x140046879  mov     [rsp+78h+var_58], rax
0x14004687e  lea     edx, [r8+4]
0x140046882  call    CscEnpQuotaPrepare
0x140046887  mov     edi, eax
0x140046889  test    eax, eax
0x14004688b  jns     short loc_140046897
0x14004688d  mov     esi, 1C98h
0x140046892  jmp     loc_1400469DE
0x140046897  lea     rax, [rbx+1B0h]
0x14004689e  xor     r9d, r9d
0x1400468a1  lea     r8, [rsp+78h+var_48]
0x1400468a6  mov     [rsp+78h+var_58], rax
0x1400468ab  lea     rdx, [rsp+78h+var_44]
0x1400468b0  mov     rcx, rbx
0x1400468b3  call    CscEnUserQueryAllPerUserInfo
0x1400468b8  mov     edi, eax
0x1400468ba  test    eax, eax
0x1400468bc  jns     short loc_1400468C8
0x1400468be  mov     esi, 1CA3h
0x1400468c3  jmp     loc_1400469DE
0x1400468c8  mov     rcx, [rbx+8]
0x1400468cc  mov     rdx, [rbx+90h]
0x1400468d3  mov     rcx, [rcx+40h]
0x1400468d7  call    CscStOrphanerAddTemporaryFile
0x1400468dc  mov     edi, eax
0x1400468de  test    eax, eax
0x1400468e0  jns     short loc_1400468EC
0x1400468e2  mov     esi, 1CABh
0x1400468e7  jmp     loc_1400469DE
0x1400468ec  test    sil, sil
0x1400468ef  jz      short loc_140046905
0x1400468f1  mov     rcx, [rbx+8]
0x1400468f5  mov     rdx, [rbx+88h]
0x1400468fc  mov     rcx, [rcx+28h]
0x140046900  call    CscStTuDeleteKeyFromTunnelCache
0x140046905  movzx   eax, word ptr [rbx+108h]
0x14004690c  movzx   ecx, ax
0x14004690f  shr     cx, 8
0x140046913  test    cl, cl
0x140046915  jnz     short loc_14004691B
0x140046917  test    al, al
0x140046919  jz      short loc_140046925
0x14004691b  xor     edx, edx
0x14004691d  mov     rcx, rbx
0x140046920  call    CscEnDecrementPinnedDescendantCountOnUnpinOrRename
0x140046925  mov     rcx, [rbx+18h]
0x140046929  lea     rdx, [rbx+0C0h]
0x140046930  mov     r8d, 2
0x140046936  call    CscEnpChangeChildCountEx
0x14004693b  test    bpl, bpl
0x14004693e  jz      short loc_140046948
0x140046940  mov     rcx, rbx
0x140046943  call    CscEnpEntryToTunnel
0x140046948  xor     r9d, r9d
0x14004694b  xor     r8d, r8d
0x14004694e  mov     dl, 1
0x140046950  mov     rcx, rbx
0x140046953  call    CscEnpDeletePQEntry
0x140046958  mov     rcx, [rbx+90h]
0x14004695f  mov     dl, 1
0x140046961  call    CscStorepLowIoSetDeleteDisposition
0x140046966  mov     rcx, [rbx+90h]; Handle
0x14004696d  call    CscStorepLowIoClose
0x140046972  xor     r8d, r8d
0x140046975  mov     qword ptr [rbx+90h], 0
0x140046980  mov     rcx, rbx
0x140046983  lea     edx, [r8+20h]
0x140046987  call    CscEnpNotifyItemChangedEx
0x14004698c  or      dword ptr [rbx+14h], 8
0x140046990  mov     eax, [rbx+14h]
0x140046993  test    al, 20h
0x140046995  jnz     short loc_1400469A0
0x140046997  mov     rax, [rbx+18h]
0x14004699b  mov     [rsp+78h+var_40], rax
0x1400469a0  mov     rax, [rbx+18h]
0x1400469a4  mov     [rbx+20h], rax
0x1400469a8  lea     rax, [rbx+60h]
0x1400469ac  mov     qword ptr [rbx+18h], 0
0x1400469b4  mov     rdx, [rax]
0x1400469b7  cmp     [rdx+8], rax
0x1400469bb  jnz     loc_140046A9D
0x1400469c1  mov     rcx, [rax+8]
0x1400469c5  cmp     [rcx], rax
0x1400469c8  jnz     loc_140046A9D
0x1400469ce  mov     [rcx], rdx
0x1400469d1  xor     esi, esi
0x1400469d3  mov     [rdx+8], rcx
0x1400469d7  mov     [rbx+1B8h], sil
0x1400469de  mov     edx, edi
0x1400469e0  lea     r8, [rsp+78h+var_38]
0x1400469e5  shr     edx, 1Fh
0x1400469e8  mov     rcx, rbx
0x1400469eb  xor     dl, 1
0x1400469ee  call    CscEnpQuotaCommit
0x1400469f3  mov     rcx, [rbx+1B0h]; P
0x1400469fa  test    rcx, rcx
0x1400469fd  jz      short loc_140046A1B
0x1400469ff  mov     edx, 21407343h; Tag
0x140046a04  call    cs:__imp_ExFreePoolWithTag
0x140046a0b  nop     dword ptr [rax+rax+00h]
0x140046a10  mov     qword ptr [rbx+1B0h], 0
0x140046a1b  mov     rcx, [rbx+20h]
0x140046a1f  test    rcx, rcx
0x140046a22  jnz     short loc_140046A28
0x140046a24  mov     rcx, [rbx+18h]
0x140046a28  call    CscEnpMainRelease
0x140046a2d  mov     rcx, rbx
0x140046a30  call    CscEnpMainRelease
0x140046a35  cmp     [rsp+78h+var_40], 0
0x140046a3b  jz      short loc_140046A47
0x140046a3d  lea     rcx, [rsp+78h+var_40]
0x140046a42  call    CscEnDereferenceEntry
0x140046a47  mov     rcx, cs:WPP_GLOBAL_Control
0x140046a4e  cmp     rcx, r12
0x140046a51  jz      short loc_140046A78
0x140046a53  test    dword ptr [rcx+2Ch], 40000h
0x140046a5a  jz      short loc_140046A78
0x140046a5c  mov     rcx, [rcx+18h]
0x140046a60  lea     r8, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids
0x140046a67  mov     edx, 38h ; '8'
0x140046a6c  mov     dword ptr [rsp+78h+var_58], esi
0x140046a70  mov     r9d, edi
0x140046a73  call    WPP_SF_Dd
0x140046a78  mov     eax, edi
0x140046a7a  mov     rcx, [rsp+78h+var_28]
0x140046a7f  xor     rcx, rsp; StackCookie
0x140046a82  call    __security_check_cookie
0x140046a87  lea     r11, [rsp+78h+var_18]
0x140046a8c  mov     rbx, [r11+28h]
0x140046a90  mov     rbp, [r11+30h]
0x140046a94  mov     rsp, r11
0x140046a97  pop     r12
0x140046a99  pop     rdi
0x140046a9a  pop     rsi
0x140046a9b  retn
0x140046a9d  mov     ecx, 3
0x140046aa2  int     29h; Win8: RtlFailFast(ecx)
```
