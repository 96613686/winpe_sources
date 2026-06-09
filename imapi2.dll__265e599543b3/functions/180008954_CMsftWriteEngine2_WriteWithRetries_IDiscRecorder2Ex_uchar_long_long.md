# CMsftWriteEngine2::WriteWithRetries(IDiscRecorder2Ex *,uchar *,long,long)

- ea: `0x180008954`
- end: `0x180008e15`
- name: `?WriteWithRetries@CMsftWriteEngine2@@AEAAJPEAUIDiscRecorder2Ex@@PEAEJJ@Z`
- size: `1217`
- prototype: `__int64 __fastcall(CMsftWriteEngine2 *this, struct IDiscRecorder2Ex *, unsigned __int8 *, int, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008510`

## callees

- `0x180002fc8`
- `0x180008954`
- `0x1800140f4`
- `0x180014134`
- `0x180014180`
- `0x1800141d8`
- `0x18002d220`
- `0x1800365c4`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1800089a6`
- `KERNEL32!GetTickCount` at `0x180008cb5`
- `KERNEL32!GetTickCount` at `0x1800089a6`
- `KERNEL32!GetTickCount` at `0x180008cb5`

## pseudocode

```c
__int64 __fastcall CMsftWriteEngine2::WriteWithRetries(
        CMsftWriteEngine2 *this,
        struct IDiscRecorder2Ex *a2,
        unsigned __int8 *a3,
        int a4,
        unsigned int a5)
{
  __int64 v5; // rax
  int v6; // r14d
  unsigned int v7; // r13d
  signed int v8; // ebx
  int v9; // edi
  char v11; // si
  const struct _GUID *v12; // r8
  struct IDiscRecorder2ExVtbl *lpVtbl; // rax
  HRESULT (__stdcall *SendCommandSendDataToDevice)(IDiscRecorder2Ex *, BYTE *, ULONG, BYTE[18], ULONG, BYTE *, ULONG_IMAPI2_NONZERO); // rax
  int v15; // eax
  unsigned int v16; // edi
  char v17; // r11
  unsigned __int8 v18; // r9
  int i; // eax
  PVOID *v20; // r10
  DWORD v21; // eax
  __int64 v23; // [rsp+28h] [rbp-99h]
  DWORD TickCount; // [rsp+70h] [rbp-51h]
  int v25; // [rsp+74h] [rbp-4Dh]
  __int16 v26; // [rsp+80h] [rbp-41h] BYREF
  int v27; // [rsp+82h] [rbp-3Fh]
  __int16 v28; // [rsp+86h] [rbp-3Bh]
  __int128 *v29; // [rsp+88h] [rbp-39h]
  struct IDiscRecorder2Ex *v30; // [rsp+90h] [rbp-31h]
  unsigned __int8 *v31; // [rsp+98h] [rbp-29h]
  __int128 v32; // [rsp+A0h] [rbp-21h] BYREF
  __int16 v33; // [rsp+B0h] [rbp-11h]
  __int128 v34; // [rsp+B8h] [rbp-9h] BYREF

  v5 = *((_QWORD *)this + 17);
  v6 = 0;
  v7 = 0;
  v31 = a3;
  v8 = 0;
  v30 = a2;
  v9 = *(_DWORD *)(v5 + 40) * a5;
  v11 = 1;
  v25 = v9;
  TickCount = GetTickCount();
  while ( v11 )
  {
    v33 = 0;
    v34 = 0;
    BYTE2(v34) = HIBYTE(a4);
    BYTE3(v34) = BYTE2(a4);
    BYTE4(v34) = BYTE1(a4);
    BYTE7(v34) = BYTE1(a5);
    lpVtbl = v30->lpVtbl;
    v32 = 0;
    LOBYTE(v34) = 42;
    BYTE5(v34) = a4;
    SendCommandSendDataToDevice = lpVtbl->SendCommandSendDataToDevice;
    BYTE8(v34) = a5;
    v15 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int128 *, __int64, __int128 *, int, unsigned __int8 *, int))SendCommandSendDataToDevice)(
            v30,
            &v34,
            10,
            &v32,
            60,
            v31,
            v9);
    v16 = v15;
    if ( v15 == 11141632 )
    {
      v17 = BYTE2(v32);
      v12 = (const struct _GUID *)BYTE12(v32);
      v18 = BYTE13(v32);
      for ( i = 0; i < 2; ++i )
      {
        if ( (*((_BYTE *)&AllowedSenseDuringWrite + 4 * i) == 0xFF
           || *((_BYTE *)&AllowedSenseDuringWrite + 4 * i) == (BYTE2(v32) & 0xF))
          && (*((_BYTE *)&AllowedSenseDuringWrite + 4 * i + 2) == 0xFF
           || *((_BYTE *)&AllowedSenseDuringWrite + 4 * i + 2) == BYTE13(v32))
          && (*((_BYTE *)&AllowedSenseDuringWrite + 4 * i + 1) == 0xFF
           || *((_BYTE *)&AllowedSenseDuringWrite + 4 * i + 1) == BYTE12(v32)) )
        {
          v11 = 1;
          goto LABEL_15;
        }
      }
      v11 = 0;
LABEL_15:
      v20 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
      {
        WPP_SF_ddD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          20,
          &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids,
          BYTE2(v32) & 0xF,
          BYTE12(v32),
          BYTE13(v32));
        v18 = BYTE13(v32);
        LOBYTE(v12) = BYTE12(v32);
        v17 = BYTE2(v32);
        v20 = (PVOID *)WPP_GLOBAL_Control;
      }
      v16 = -1062599935;
      if ( !v11 )
        goto LABEL_31;
    }
    else if ( v15 == -1062600179 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 21, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids, v7);
      }
      v11 = 1;
    }
    else
    {
      if ( v15 >= 0 )
      {
        v11 = 0;
        v16 = 0;
        goto LABEL_62;
      }
      if ( v15 == -2147024841 )
      {
        v18 = BYTE13(v32);
        v11 = 0;
        LOBYTE(v12) = BYTE12(v32);
        v17 = BYTE2(v32);
        v20 = (PVOID *)WPP_GLOBAL_Control;
LABEL_31:
        if ( v20 == &WPP_GLOBAL_Control )
          goto LABEL_37;
        if ( (*((_BYTE *)v20 + 228) & 4) == 0 || *((_BYTE *)v20 + 225) < 3u )
          goto LABEL_36;
        v27 = 0;
        v26 = 18;
        v28 = 0;
        v29 = &v32;
        WPP_SF_dDdDdDDD_HEX_(
          (unsigned int)v20[27],
          v17 & 0xF,
          (unsigned int)&v26,
          a5,
          a5,
          a4,
          a4,
          v16,
          v17 & 0xF,
          (unsigned __int8)v12,
          v18,
          (__int64)&v26);
LABEL_35:
        v20 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_36;
      }
      v11 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
      {
        WPP_SF_dDdDd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          22,
          &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids,
          a5,
          a5,
          a4,
          a4,
          v15);
      }
    }
    v21 = GetTickCount();
    v12 = (const struct _GUID *)TickCount;
    if ( v21 - TickCount < 0x2BF20 )
      goto LABEL_35;
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 3u )
    {
      LODWORD(v23) = v21;
      WPP_SF_dDdDdDdDdD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        23,
        &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids,
        TickCount,
        TickCount,
        v23,
        v21,
        a5,
        a5,
        a4,
        a4,
        v7,
        v7);
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
    v11 = 0;
LABEL_36:
    if ( (v16 & 0x80000000) != 0 )
    {
LABEL_37:
      if ( v6 < 0 )
      {
        if ( v16 == v6 )
        {
          if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 228) & 4) != 0 && *((_BYTE *)v20 + 225) >= 3u )
            WPP_SF_d(v20[27], 26, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids, v16);
        }
        else if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 228) & 4) != 0 && *((_BYTE *)v20 + 225) >= 3u )
        {
          WPP_SF_Dd(v20[27], 27, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids, v16, v6);
        }
      }
      else
      {
        if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 228) & 4) != 0 && *((_BYTE *)v20 + 225) >= 3u )
          WPP_SF_d(v20[27], 25, &WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids, v16);
        v6 = v16;
      }
    }
LABEL_62:
    v8 = 0;
    if ( !v11 )
      v8 = v16;
    v9 = v25;
    ++v7;
    if ( v8 < 0 )
    {
      if ( v6 < 0 )
        v8 = v6;
      break;
    }
  }
  if ( (v8 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v8, (int)&CLSID_MsftWriteEngine2, v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180008954  push    rbp
0x180008956  push    rbx
0x180008957  push    rsi
0x180008958  push    rdi
0x180008959  push    r12
0x18000895b  push    r13
0x18000895d  push    r14
0x18000895f  push    r15
0x180008961  lea     rbp, [rsp-17h]
0x180008966  sub     rsp, 0D8h
0x18000896d  mov     rax, cs:__security_cookie
0x180008974  xor     rax, rsp
0x180008977  mov     [rbp+4Fh+var_48], rax
0x18000897b  mov     rax, [rcx+88h]
0x180008982  xor     r14d, r14d
0x180008985  mov     r12d, [rbp+4Fh+arg_20]
0x180008989  xor     r13d, r13d
0x18000898c  mov     edi, r12d
0x18000898f  mov     [rbp+4Fh+var_78], r8
0x180008993  xor     ebx, ebx
0x180008995  mov     [rbp+4Fh+var_80], rdx
0x180008999  imul    edi, [rax+28h]
0x18000899d  mov     r15d, r9d
0x1800089a0  mov     sil, 1
0x1800089a3  mov     [rbp+4Fh+var_9C], edi
0x1800089a6  call    cs:__imp_GetTickCount
0x1800089ac  mov     [rbp+4Fh+var_A0], eax
0x1800089af  test    sil, sil
0x1800089b2  jz      loc_180008DD5
0x1800089b8  mov     rcx, [rbp+4Fh+var_80]
0x1800089bc  lea     r9, [rbp+4Fh+var_70]
0x1800089c0  mov     rdx, [rbp+4Fh+var_78]
0x1800089c4  xor     eax, eax
0x1800089c6  mov     [rbp+4Fh+var_60], ax
0x1800089ca  xorps   xmm0, xmm0
0x1800089cd  movups  [rbp+4Fh+var_58], xmm0
0x1800089d1  mov     eax, r15d
0x1800089d4  mov     [rsp+110h+var_E0], edi
0x1800089d8  sar     eax, 18h
0x1800089db  xorps   xmm1, xmm1
0x1800089de  mov     byte ptr [rbp+4Fh+var_58+2], al
0x1800089e1  mov     r8d, 0Ah
0x1800089e7  mov     [rsp+110h+var_E8], rdx
0x1800089ec  mov     eax, r15d
0x1800089ef  sar     eax, 10h
0x1800089f2  lea     rdx, [rbp+4Fh+var_58]
0x1800089f6  mov     byte ptr [rbp+4Fh+var_58+3], al
0x1800089f9  mov     eax, r15d
0x1800089fc  sar     eax, 8
0x1800089ff  mov     byte ptr [rbp+4Fh+var_58+4], al
0x180008a02  mov     eax, r12d
0x180008a05  sar     eax, 8
0x180008a08  mov     byte ptr [rbp+4Fh+var_58+7], al
0x180008a0b  mov     rax, [rcx]
0x180008a0e  movups  [rbp+4Fh+var_70], xmm1
0x180008a12  mov     byte ptr [rbp+4Fh+var_58], 2Ah ; '*'
0x180008a16  mov     byte ptr [rbp+4Fh+var_58+5], r15b
0x180008a1a  mov     rax, [rax+20h]
0x180008a1e  mov     byte ptr [rbp+4Fh+var_58+8], r12b
0x180008a22  mov     [rsp+110h+var_F0], 3Ch ; '<'
0x180008a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a2f  mov     edi, eax
0x180008a31  cmp     eax, 0AA0200h
0x180008a36  jnz     loc_180008B10
0x180008a3c  movzx   r11d, byte ptr [rbp+4Fh+var_70+2]
0x180008a41  mov     bl, 0FFh
0x180008a43  movzx   r8d, byte ptr [rbp+4Fh+var_70+0Ch]
0x180008a48  mov     dl, r11b
0x180008a4b  movzx   r9d, byte ptr [rbp+4Fh+var_70+0Dh]
0x180008a50  and     dl, 0Fh
0x180008a53  xor     eax, eax
0x180008a55  cmp     eax, 2
0x180008a58  jge     short loc_180008A95
0x180008a5a  movsxd  rcx, eax
0x180008a5d  lea     r10, ?AllowedSenseDuringWrite@@3PAU_SENSE_STUFF@Imapi2Utility@@A; Imapi2Utility::_SENSE_STUFF near * AllowedSenseDuringWrite
0x180008a64  cmp     [r10+rcx*4], bl
0x180008a68  jz      short loc_180008A70
0x180008a6a  cmp     [r10+rcx*4], dl
0x180008a6e  jnz     short loc_180008A8C
0x180008a70  cmp     [r10+rcx*4+2], bl
0x180008a75  jz      short loc_180008A7E
0x180008a77  cmp     [r10+rcx*4+2], r9b
0x180008a7c  jnz     short loc_180008A8C
0x180008a7e  cmp     [r10+rcx*4+1], bl
0x180008a83  jz      short loc_180008A90
0x180008a85  cmp     [r10+rcx*4+1], r8b
0x180008a8a  jz      short loc_180008A90
0x180008a8c  inc     eax
0x180008a8e  jmp     short loc_180008A55
0x180008a90  mov     sil, 1
0x180008a93  jmp     short loc_180008A98
0x180008a95  xor     sil, sil
0x180008a98  mov     r10, cs:WPP_GLOBAL_Control
0x180008a9f  lea     rbx, WPP_GLOBAL_Control
0x180008aa6  cmp     r10, rbx
0x180008aa9  jz      short loc_180008AFD
0x180008aab  test    byte ptr [r10+0E4h], 4
0x180008ab3  jz      short loc_180008AFD
0x180008ab5  cmp     byte ptr [r10+0E1h], 3
0x180008abd  jb      short loc_180008AFD
0x180008abf  mov     rcx, [r10+0D8h]
0x180008ac6  mov     eax, r9d
0x180008ac9  mov     dword ptr [rsp+110h+var_E8], eax
0x180008acd  mov     r9d, r11d
0x180008ad0  mov     [rsp+110h+var_F0], r8d
0x180008ad5  and     r9d, 0Fh
0x180008ad9  lea     r8, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x180008ae0  mov     edx, 14h
0x180008ae5  call    WPP_SF_ddD
0x180008aea  mov     r9b, byte ptr [rbp+4Fh+var_70+0Dh]
0x180008aee  mov     r8b, byte ptr [rbp+4Fh+var_70+0Ch]
0x180008af2  mov     r11b, byte ptr [rbp+4Fh+var_70+2]
0x180008af6  mov     r10, cs:WPP_GLOBAL_Control
0x180008afd  mov     edi, 0C0AA0301h
0x180008b02  test    sil, sil
0x180008b05  jnz     loc_180008CB5
0x180008b0b  jmp     loc_180008B95
0x180008b10  cmp     eax, 0C0AA020Dh
0x180008b15  jnz     short loc_180008B5F
0x180008b17  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b1e  lea     rbx, WPP_GLOBAL_Control
0x180008b25  cmp     rcx, rbx
0x180008b28  jz      short loc_180008B57
0x180008b2a  test    byte ptr [rcx+0E4h], 4
0x180008b31  jz      short loc_180008B57
0x180008b33  cmp     byte ptr [rcx+0E1h], 4
0x180008b3a  jb      short loc_180008B57
0x180008b3c  mov     rcx, [rcx+0D8h]
0x180008b43  lea     r8, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x180008b4a  mov     edx, 15h
0x180008b4f  mov     r9d, r13d
0x180008b52  call    WPP_SF_d
0x180008b57  mov     sil, 1
0x180008b5a  jmp     loc_180008CB5
0x180008b5f  test    eax, eax
0x180008b61  js      short loc_180008B6D
0x180008b63  xor     sil, sil
0x180008b66  xor     edi, edi
0x180008b68  jmp     loc_180008DB8
0x180008b6d  lea     rbx, WPP_GLOBAL_Control
0x180008b74  cmp     eax, 80070037h
0x180008b79  jnz     loc_180008C66
0x180008b7f  mov     r9b, byte ptr [rbp+4Fh+var_70+0Dh]
0x180008b83  xor     sil, sil
0x180008b86  mov     r8b, byte ptr [rbp+4Fh+var_70+0Ch]
0x180008b8a  mov     r11b, byte ptr [rbp+4Fh+var_70+2]
0x180008b8e  mov     r10, cs:WPP_GLOBAL_Control
0x180008b95  cmp     r10, rbx
0x180008b98  jz      loc_180008C21
0x180008b9e  test    byte ptr [r10+0E4h], 4
0x180008ba6  jz      short loc_180008C19
0x180008ba8  cmp     byte ptr [r10+0E1h], 3
0x180008bb0  jb      short loc_180008C19
0x180008bb2  xor     ecx, ecx
0x180008bb4  movzx   edx, r11b
0x180008bb8  mov     [rbp+4Fh+var_8E], ecx
0x180008bbb  mov     eax, 12h
0x180008bc0  mov     [rbp+4Fh+var_90], ax
0x180008bc4  and     edx, 0Fh
0x180008bc7  lea     rax, [rbp+4Fh+var_70]
0x180008bcb  mov     [rbp+4Fh+var_8A], cx
0x180008bcf  movzx   ecx, r8b
0x180008bd3  lea     r8, [rbp+4Fh+var_90]
0x180008bd7  mov     [rsp+110h+var_B8], r8
0x180008bdc  mov     [rbp+4Fh+var_88], rax
0x180008be0  movzx   eax, r9b
0x180008be4  mov     r9d, r12d
0x180008be7  mov     [rsp+110h+var_C0], eax
0x180008beb  mov     [rsp+110h+var_C8], ecx
0x180008bef  mov     rcx, [r10+0D8h]
0x180008bf6  mov     [rsp+110h+var_D0], edx
0x180008bfa  mov     [rsp+110h+var_D8], edi
0x180008bfe  mov     [rsp+110h+var_E0], r15d
0x180008c03  mov     dword ptr [rsp+110h+var_E8], r15d
0x180008c08  mov     [rsp+110h+var_F0], r12d
0x180008c0d  call    WPP_SF_dDdDdDDD_HEX_
0x180008c12  mov     r10, cs:WPP_GLOBAL_Control
0x180008c19  test    edi, edi
0x180008c1b  jns     loc_180008DB8
0x180008c21  test    r14d, r14d
0x180008c24  js      loc_180008D44
0x180008c2a  cmp     r10, rbx
0x180008c2d  jz      short loc_180008C5E
0x180008c2f  test    byte ptr [r10+0E4h], 4
0x180008c37  jz      short loc_180008C5E
0x180008c39  cmp     byte ptr [r10+0E1h], 3
0x180008c41  jb      short loc_180008C5E
0x180008c43  mov     rcx, [r10+0D8h]
0x180008c4a  lea     r8, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x180008c51  mov     edx, 19h
0x180008c56  mov     r9d, edi
0x180008c59  call    WPP_SF_d
0x180008c5e  mov     r14d, edi
0x180008c61  jmp     loc_180008DB8
0x180008c66  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c6d  mov     sil, 1
0x180008c70  cmp     rcx, rbx
0x180008c73  jz      short loc_180008CB5
0x180008c75  test    byte ptr [rcx+0E4h], 4
0x180008c7c  jz      short loc_180008CB5
0x180008c7e  cmp     byte ptr [rcx+0E1h], 3
0x180008c85  jb      short loc_180008CB5
0x180008c87  mov     rcx, [rcx+0D8h]
0x180008c8e  lea     r8, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x180008c95  mov     [rsp+110h+var_D8], eax
0x180008c99  mov     edx, 16h
0x180008c9e  mov     [rsp+110h+var_E0], r15d
0x180008ca3  mov     r9d, r12d
0x180008ca6  mov     dword ptr [rsp+110h+var_E8], r15d
0x180008cab  mov     [rsp+110h+var_F0], r12d
0x180008cb0  call    WPP_SF_dDdDd
0x180008cb5  call    cs:__imp_GetTickCount
0x180008cbb  mov     r8d, [rbp+4Fh+var_A0]
0x180008cbf  mov     ecx, eax
0x180008cc1  sub     eax, r8d
0x180008cc4  cmp     eax, 2BF20h
0x180008cc9  jb      loc_180008C12
0x180008ccf  mov     r10, cs:WPP_GLOBAL_Control
0x180008cd6  cmp     r10, rbx
0x180008cd9  jz      short loc_180008D3C
0x180008cdb  test    byte ptr [r10+0E4h], 4
0x180008ce3  jz      short loc_180008D3C
0x180008ce5  cmp     byte ptr [r10+0E1h], 3
0x180008ced  jb      short loc_180008D3C
0x180008cef  mov     [rsp+110h+var_B0], r13d
0x180008cf4  mov     r9d, r8d
0x180008cf7  mov     dword ptr [rsp+110h+var_B8], r13d
0x180008cfc  mov     edx, 17h
0x180008d01  mov     [rsp+110h+var_C0], r15d
0x180008d06  mov     [rsp+110h+var_C8], r15d
0x180008d0b  mov     [rsp+110h+var_D0], r12d
0x180008d10  mov     [rsp+110h+var_D8], r12d
0x180008d15  mov     [rsp+110h+var_E0], ecx
0x180008d19  mov     dword ptr [rsp+110h+var_E8], ecx
0x180008d1d  mov     rcx, [r10+0D8h]
0x180008d24  mov     [rsp+110h+var_F0], r8d
0x180008d29  lea     r8, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x180008d30  call    WPP_SF_dDdDdDdDdD
0x180008d35  mov     r10, cs:WPP_GLOBAL_Control
0x180008d3c  xor     sil, sil
0x180008d3f  jmp     loc_180008C19
0x180008d44  cmp     edi, r14d
0x180008d47  jnz     short loc_180008D7F
0x180008d49  cmp     r10, rbx
0x180008d4c  jz      short loc_180008DB8
0x180008d4e  test    byte ptr [r10+0E4h], 4
0x180008d56  jz      short loc_180008DB8
0x180008d58  cmp     byte ptr [r10+0E1h], 3
0x180008d60  jb      short loc_180008DB8
0x180008d62  mov     rcx, [r10+0D8h]
0x180008d69  lea     r8, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x180008d70  mov     edx, 1Ah
0x180008d75  mov     r9d, edi
0x180008d78  call    WPP_SF_d
0x180008d7d  jmp     short loc_180008DB8
0x180008d7f  cmp     r10, rbx
0x180008d82  jz      short loc_180008DB8
0x180008d84  test    byte ptr [r10+0E4h], 4
0x180008d8c  jz      short loc_180008DB8
0x180008d8e  cmp     byte ptr [r10+0E1h], 3
0x180008d96  jb      short loc_180008DB8
0x180008d98  mov     rcx, [r10+0D8h]
0x180008d9f  lea     r8, WPP_2a319e8a90a236e576f9c35cfc5c843e_Traceguids
0x180008da6  mov     edx, 1Bh
0x180008dab  mov     [rsp+110h+var_F0], r14d
0x180008db0  mov     r9d, edi
0x180008db3  call    WPP_SF_Dd
0x180008db8  xor     ebx, ebx
0x180008dba  test    sil, sil
0x180008dbd  cmovz   ebx, edi
0x180008dc0  mov     edi, [rbp+4Fh+var_9C]
0x180008dc3  inc     r13d
0x180008dc6  test    ebx, ebx
0x180008dc8  jns     loc_1800089AF
0x180008dce  test    r14d, r14d
0x180008dd1  cmovs   ebx, r14d
0x180008dd5  mov     ecx, ebx
0x180008dd7  and     ecx, 80FF0000h
0x180008ddd  cmp     ecx, 80AA0000h
0x180008de3  jnz     short loc_180008DF3
0x180008de5  lea     rdx, CLSID_MsftWriteEngine2; int
0x180008dec  mov     ecx, ebx; dwMessageId
0x180008dee  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x180008df3  mov     eax, ebx
0x180008df5  mov     rcx, [rbp+4Fh+var_48]
0x180008df9  xor     rcx, rsp; StackCookie
0x180008dfc  call    __security_check_cookie
0x180008e01  add     rsp, 0D8h
0x180008e08  pop     r15
0x180008e0a  pop     r14
0x180008e0c  pop     r13
0x180008e0e  pop     r12
0x180008e10  pop     rdi
0x180008e11  pop     rsi
0x180008e12  pop     rbx
0x180008e13  pop     rbp
0x180008e14  retn
```
