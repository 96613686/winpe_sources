# Imapi2Utility::SetCurrentDriveWriteSpeed(IDiscRecorder2 *,ulong,ulong)

- ea: `0x180047948`
- end: `0x180047c36`
- name: `?SetCurrentDriveWriteSpeed@Imapi2Utility@@YAJPEAUIDiscRecorder2@@KK@Z`
- size: `750`
- prototype: `int(Imapi2Utility *__hidden this, struct IDiscRecorder2 *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180025dd0`
- `0x180042ae0`
- `0x180047cd8`

## callees

- `0x18000cae8`
- `0x1800140f4`
- `0x180023790`
- `0x180023a14`
- `0x180043bb4`
- `0x180047728`
- `0x180047948`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800479df`
- `KERNEL32!LocalAlloc` at `0x1800479df`
- `KERNEL32!LocalFree` at `0x180047c06`
- `KERNEL32!LocalFree` at `0x180047c06`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Imapi2Utility::SetCurrentDriveWriteSpeed(
        Imapi2Utility *this,
        struct IDiscRecorder2 *a2,
        unsigned int a3)
{
  unsigned int v4; // r15d
  unsigned int v5; // r14d
  unsigned int v6; // esi
  struct IDiscRecorder2Ex *v7; // rdx
  int CurrentDriveSpeed; // ebx
  unsigned int *v9; // r9
  unsigned int *v10; // r9
  char *v11; // rdi
  int v12; // eax
  struct IDiscRecorder2Ex *v13; // rdx
  unsigned int v15; // [rsp+20h] [rbp-59h]
  unsigned __int8 v16[4]; // [rsp+40h] [rbp-39h] BYREF
  Imapi2Utility *v17; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int8 v18[4]; // [rsp+50h] [rbp-29h] BYREF
  _WORD v19[3]; // [rsp+60h] [rbp-19h] BYREF
  __int16 v20; // [rsp+66h] [rbp-13h]
  __int128 *v21; // [rsp+68h] [rbp-11h]
  __int128 v22; // [rsp+70h] [rbp-9h] BYREF
  __int128 v23; // [rsp+80h] [rbp+7h] BYREF
  __int16 v24; // [rsp+90h] [rbp+17h]

  v4 = (unsigned int)a2;
  v17 = 0;
  v5 = -1;
  *(_DWORD *)v18 = -1;
  v6 = -1;
  *(_DWORD *)v16 = -1;
  CurrentDriveSpeed = (**(__int64 (__fastcall ***)(Imapi2Utility *, GUID *, Imapi2Utility **))this)(
                        this,
                        &GUID_27354132_7f64_5b0f_8f00_5d77afbe261e,
                        &v17);
  if ( CurrentDriveSpeed >= 0 )
  {
    LOBYTE(v7) = 1;
    CurrentDriveSpeed = Imapi2Utility::GetCurrentDriveSpeed(v17, v7, v18, v9);
    if ( CurrentDriveSpeed >= 0 )
    {
      CurrentDriveSpeed = Imapi2Utility::GetCurrentDriveSpeed(v17, 0, v16, v10);
      v6 = *(_DWORD *)v16;
    }
  }
  if ( CurrentDriveSpeed >= 0 )
  {
    v11 = (char *)LocalAlloc(0x40u, 0x1Cu);
    if ( !v11 )
      CurrentDriveSpeed = -2147024882;
    if ( CurrentDriveSpeed < 0 )
      goto LABEL_30;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    *(_DWORD *)(v11 + 1) = 0;
    *(_DWORD *)(v11 + 5) = -16777216;
    LOBYTE(v22) = -74;
    *(_WORD *)((char *)&v22 + 9) = 7168;
    *v11 = 8 * (a3 & 3);
    *(_WORD *)(v11 + 9) = -1;
    v11[11] = -1;
    v11[12] = HIBYTE(v6);
    v11[13] = BYTE2(v6);
    v11[14] = BYTE1(v6);
    v11[15] = v6;
    *((_DWORD *)v11 + 4) = -402456576;
    v11[20] = HIBYTE(v4);
    v11[21] = BYTE2(v4);
    v11[22] = BYTE1(v4);
    v11[23] = v4;
    *((_DWORD *)v11 + 6) = -402456576;
    v15 = 10;
    v12 = (*(__int64 (__fastcall **)(Imapi2Utility *, __int128 *, __int64, __int128 *))(*(_QWORD *)v17 + 32LL))(
            v17,
            &v22,
            12,
            &v23);
    v13 = (struct IDiscRecorder2Ex *)&WPP_GLOBAL_Control;
    if ( v12 == 11141632 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v19[0] = 18;
        *(_DWORD *)&v19[1] = 0;
        v20 = 0;
        v21 = &v23;
        WPP_SF__HEX_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v19);
      }
    }
    else if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v19[0] = 18;
        *(_DWORD *)&v19[1] = 0;
        v20 = 0;
        v21 = &v23;
        WPP_SF_d_HEX_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          102,
          (unsigned int)&WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
          v12,
          (__int64)v19);
      }
    }
    else
    {
      *(_DWORD *)v16 = -1;
      LOBYTE(v13) = 1;
      CurrentDriveSpeed = Imapi2Utility::GetCurrentDriveSpeed(v17, v13, v16, (unsigned int *)(unsigned int)v12);
      if ( *(_DWORD *)v16 != *(_DWORD *)v18 || *(_DWORD *)v16 == v4 )
      {
LABEL_30:
        if ( v11 )
          LocalFree(v11);
        goto LABEL_32;
      }
    }
    if ( (v6 & 0xFFFF0000) != 0 )
      v6 = -1;
    if ( (v4 & 0xFFFF0000) == 0 )
      v5 = v4;
    CurrentDriveSpeed = Imapi2Utility::SetCDSpeed(v17, (struct IDiscRecorder2Ex *)v6, v5, a3, v15);
    if ( CurrentDriveSpeed < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        103,
        &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
        (unsigned int)CurrentDriveSpeed);
    }
    goto LABEL_30;
  }
LABEL_32:
  ATL::CComPtrBase<IDiscRecorder2Ex>::~CComPtrBase<IDiscRecorder2Ex>(&v17);
  return (unsigned int)CurrentDriveSpeed;
}

```

## disassembly

```asm
0x180047948  push    rbp
0x18004794a  push    rbx
0x18004794b  push    rsi
0x18004794c  push    rdi
0x18004794d  push    r12
0x18004794f  push    r14
0x180047951  push    r15
0x180047953  lea     rbp, [rsp-27h]
0x180047958  sub     rsp, 0A0h
0x18004795f  mov     rax, cs:__security_cookie
0x180047966  xor     rax, rsp
0x180047969  mov     [rbp+57h+var_38], rax
0x18004796d  mov     r12d, r8d
0x180047970  mov     r15d, edx
0x180047973  mov     [rbp+57h+var_88], 0
0x18004797b  or      r14d, 0FFFFFFFFh
0x18004797f  mov     dword ptr [rbp+57h+var_80], r14d
0x180047983  mov     esi, r14d
0x180047986  mov     dword ptr [rbp+57h+var_90], r14d
0x18004798a  mov     rax, [rcx]
0x18004798d  lea     r8, [rbp+57h+var_88]
0x180047991  lea     rdx, _GUID_27354132_7f64_5b0f_8f00_5d77afbe261e
0x180047998  mov     rax, [rax]
0x18004799b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800479a0  mov     ebx, eax
0x1800479a2  test    eax, eax
0x1800479a4  js      short loc_1800479CF
0x1800479a6  lea     r8, [rbp+57h+var_80]; unsigned __int8
0x1800479aa  mov     dl, 1; struct IDiscRecorder2Ex *
0x1800479ac  mov     rcx, [rbp+57h+var_88]; this
0x1800479b0  call    ?GetCurrentDriveSpeed@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@EPEAK@Z; Imapi2Utility::GetCurrentDriveSpeed(IDiscRecorder2Ex *,uchar,ulong *)
0x1800479b5  mov     ebx, eax
0x1800479b7  test    eax, eax
0x1800479b9  js      short loc_1800479CF
0x1800479bb  lea     r8, [rbp+57h+var_90]; unsigned __int8
0x1800479bf  xor     edx, edx; struct IDiscRecorder2Ex *
0x1800479c1  mov     rcx, [rbp+57h+var_88]; this
0x1800479c5  call    ?GetCurrentDriveSpeed@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@EPEAK@Z; Imapi2Utility::GetCurrentDriveSpeed(IDiscRecorder2Ex *,uchar,ulong *)
0x1800479ca  mov     ebx, eax
0x1800479cc  mov     esi, dword ptr [rbp+57h+var_90]
0x1800479cf  test    ebx, ebx
0x1800479d1  js      loc_180047C0D
0x1800479d7  mov     edx, 1Ch; uBytes
0x1800479dc  lea     ecx, [rdx+24h]; uFlags
0x1800479df  call    cs:__imp_LocalAlloc
0x1800479e5  mov     rdi, rax
0x1800479e8  mov     eax, 8007000Eh
0x1800479ed  test    rdi, rdi
0x1800479f0  cmovz   ebx, eax
0x1800479f3  test    ebx, ebx
0x1800479f5  js      loc_180047BFE
0x1800479fb  xorps   xmm0, xmm0
0x1800479fe  movups  [rbp+57h+var_60], xmm0
0x180047a02  xorps   xmm1, xmm1
0x180047a05  xor     eax, eax
0x180047a07  movups  [rbp+57h+var_50], xmm1
0x180047a0b  mov     [rbp+57h+var_40], ax
0x180047a0f  mov     [rdi+1], eax
0x180047a12  mov     dword ptr [rdi+5], 0FF000000h
0x180047a19  mov     byte ptr [rbp+57h+var_60], 0B6h
0x180047a1d  mov     word ptr [rbp+57h+var_60+9], 1C00h
0x180047a23  mov     al, r12b
0x180047a26  and     al, 3
0x180047a28  shl     al, 3
0x180047a2b  mov     [rdi], al
0x180047a2d  mov     word ptr [rdi+9], 0FFFFh
0x180047a33  mov     byte ptr [rdi+0Bh], 0FFh
0x180047a37  mov     eax, esi
0x180047a39  shr     eax, 18h
0x180047a3c  mov     [rdi+0Ch], al
0x180047a3f  mov     eax, esi
0x180047a41  shr     eax, 10h
0x180047a44  mov     [rdi+0Dh], al
0x180047a47  mov     eax, esi
0x180047a49  shr     eax, 8
0x180047a4c  mov     [rdi+0Eh], al
0x180047a4f  mov     [rdi+0Fh], sil
0x180047a53  mov     dword ptr [rdi+10h], 0E8030000h
0x180047a5a  mov     eax, r15d
0x180047a5d  shr     eax, 18h
0x180047a60  mov     [rdi+14h], al
0x180047a63  mov     eax, r15d
0x180047a66  shr     eax, 10h
0x180047a69  mov     [rdi+15h], al
0x180047a6c  mov     eax, r15d
0x180047a6f  shr     eax, 8
0x180047a72  mov     [rdi+16h], al
0x180047a75  mov     [rdi+17h], r15b
0x180047a79  mov     dword ptr [rdi+18h], 0E8030000h
0x180047a80  mov     rcx, [rbp+57h+var_88]
0x180047a84  mov     rax, [rcx]
0x180047a87  mov     [rsp+0D0h+var_A0], 1Ch
0x180047a8f  mov     [rsp+0D0h+var_A8], rdi
0x180047a94  mov     [rsp+0D0h+var_B0], 0Ah
0x180047a9c  lea     r9, [rbp+57h+var_50]
0x180047aa0  mov     r8d, 0Ch
0x180047aa6  lea     rdx, [rbp+57h+var_60]
0x180047aaa  mov     rax, [rax+20h]
0x180047aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ab3  mov     r9d, eax; unsigned int *
0x180047ab6  mov     al, 4
0x180047ab8  lea     rdx, WPP_GLOBAL_Control
0x180047abf  cmp     r9d, 0AA0200h
0x180047ac6  jnz     short loc_180047B1F
0x180047ac8  mov     rcx, cs:WPP_GLOBAL_Control
0x180047acf  cmp     rcx, rdx
0x180047ad2  jz      loc_180047B9E
0x180047ad8  test    [rcx+1Ch], al
0x180047adb  jz      loc_180047B9E
0x180047ae1  cmp     [rcx+19h], al
0x180047ae4  jb      loc_180047B9E
0x180047aea  mov     eax, 12h
0x180047aef  xor     edx, edx
0x180047af1  mov     word ptr [rbp+57h+var_70], ax
0x180047af5  mov     dword ptr [rbp+57h+var_70+2], edx
0x180047af8  mov     [rbp+57h+var_6A], dx
0x180047afc  lea     rax, [rbp+57h+var_50]
0x180047b00  mov     [rbp+57h+var_68], rax
0x180047b04  mov     edx, 65h ; 'e'
0x180047b09  lea     r9, [rbp+57h+var_70]
0x180047b0d  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180047b14  mov     rcx, [rcx+10h]
0x180047b18  call    WPP_SF__HEX_
0x180047b1d  jmp     short loc_180047B9E
0x180047b1f  test    r9d, r9d
0x180047b22  js      short loc_180047B4F
0x180047b24  mov     dword ptr [rbp+57h+var_90], r14d
0x180047b28  lea     r8, [rbp+57h+var_90]; unsigned __int8
0x180047b2c  mov     dl, 1; struct IDiscRecorder2Ex *
0x180047b2e  mov     rcx, [rbp+57h+var_88]; this
0x180047b32  call    ?GetCurrentDriveSpeed@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@EPEAK@Z; Imapi2Utility::GetCurrentDriveSpeed(IDiscRecorder2Ex *,uchar,ulong *)
0x180047b37  mov     ebx, eax
0x180047b39  mov     eax, dword ptr [rbp+57h+var_90]
0x180047b3c  cmp     eax, dword ptr [rbp+57h+var_80]
0x180047b3f  jnz     loc_180047BFE
0x180047b45  cmp     eax, r15d
0x180047b48  jnz     short loc_180047B9E
0x180047b4a  jmp     loc_180047BFE
0x180047b4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180047b56  cmp     rcx, rdx
0x180047b59  jz      short loc_180047B9E
0x180047b5b  test    [rcx+1Ch], al
0x180047b5e  jz      short loc_180047B9E
0x180047b60  cmp     byte ptr [rcx+19h], 3
0x180047b64  jb      short loc_180047B9E
0x180047b66  mov     eax, 12h
0x180047b6b  xor     edx, edx
0x180047b6d  mov     word ptr [rbp+57h+var_70], ax
0x180047b71  mov     dword ptr [rbp+57h+var_70+2], edx
0x180047b74  mov     [rbp+57h+var_6A], dx
0x180047b78  lea     rax, [rbp+57h+var_50]
0x180047b7c  mov     [rbp+57h+var_68], rax
0x180047b80  mov     edx, 66h ; 'f'
0x180047b85  lea     rax, [rbp+57h+var_70]
0x180047b89  mov     qword ptr [rsp+0D0h+var_B0], rax; unsigned int
0x180047b8e  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180047b95  mov     rcx, [rcx+10h]
0x180047b99  call    WPP_SF_d_HEX_
0x180047b9e  mov     eax, 0FFFF0000h
0x180047ba3  test    eax, esi
0x180047ba5  cmovnz  esi, r14d
0x180047ba9  test    eax, r15d
0x180047bac  cmovz   r14d, r15d
0x180047bb0  mov     r9d, r12d; unsigned int
0x180047bb3  mov     r8d, r14d; unsigned int
0x180047bb6  mov     edx, esi; struct IDiscRecorder2Ex *
0x180047bb8  mov     rcx, [rbp+57h+var_88]; this
0x180047bbc  call    ?SetCDSpeed@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@KKK@Z; Imapi2Utility::SetCDSpeed(IDiscRecorder2Ex *,ulong,ulong,ulong)
0x180047bc1  mov     ebx, eax
0x180047bc3  test    eax, eax
0x180047bc5  jns     short loc_180047BFE
0x180047bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180047bce  lea     rax, WPP_GLOBAL_Control
0x180047bd5  cmp     rcx, rax
0x180047bd8  jz      short loc_180047BFE
0x180047bda  test    byte ptr [rcx+1Ch], 4
0x180047bde  jz      short loc_180047BFE
0x180047be0  cmp     byte ptr [rcx+19h], 2
0x180047be4  jb      short loc_180047BFE
0x180047be6  mov     edx, 67h ; 'g'
0x180047beb  mov     r9d, ebx
0x180047bee  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180047bf5  mov     rcx, [rcx+10h]
0x180047bf9  call    WPP_SF_d
0x180047bfe  test    rdi, rdi
0x180047c01  jz      short loc_180047C0D
0x180047c03  mov     rcx, rdi; hMem
0x180047c06  call    cs:__imp_LocalFree
0x180047c0c  nop
0x180047c0d  lea     rcx, [rbp+57h+var_88]
0x180047c11  call    ??1?$CComPtrBase@UIDiscRecorder2Ex@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDiscRecorder2Ex>::~CComPtrBase<IDiscRecorder2Ex>(void)
0x180047c16  mov     eax, ebx
0x180047c18  mov     rcx, [rbp+57h+var_38]
0x180047c1c  xor     rcx, rsp; StackCookie
0x180047c1f  call    __security_check_cookie
0x180047c24  add     rsp, 0A0h
0x180047c2b  pop     r15
0x180047c2d  pop     r14
0x180047c2f  pop     r12
0x180047c31  pop     rdi
0x180047c32  pop     rsi
0x180047c33  pop     rbx
0x180047c34  pop     rbp
0x180047c35  retn
```
