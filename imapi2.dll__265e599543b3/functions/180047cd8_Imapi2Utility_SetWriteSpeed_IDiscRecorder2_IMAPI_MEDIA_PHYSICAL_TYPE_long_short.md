# Imapi2Utility::SetWriteSpeed(IDiscRecorder2 *,_IMAPI_MEDIA_PHYSICAL_TYPE,long,short)

- ea: `0x180047cd8`
- end: `0x180047f81`
- name: `?SetWriteSpeed@Imapi2Utility@@YAJPEAUIDiscRecorder2@@W4_IMAPI_MEDIA_PHYSICAL_TYPE@@JF@Z`
- size: `681`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, struct IDiscRecorder2 *, enum _IMAPI_MEDIA_PHYSICAL_TYPE, int, __int16)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18001d0e0`
- `0x1800300f0`
- `0x1800399b0`

## callees

- `0x1800140f4`
- `0x180042ae0`
- `0x1800431a8`
- `0x1800437fc`
- `0x180043b20`
- `0x180043f38`
- `0x180047948`
- `0x180047cd8`
- `0x180047f88`
- `0x18004a010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180047f3b`
- `KERNEL32!LocalFree` at `0x180047f52`
- `KERNEL32!LocalFree` at `0x180047f68`
- `KERNEL32!LocalFree` at `0x180047f3b`
- `KERNEL32!LocalFree` at `0x180047f52`
- `KERNEL32!LocalFree` at `0x180047f68`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::SetWriteSpeed(
        void (__fastcall ***this)(Imapi2Utility *, GUID *, __int64 *),
        struct IDiscRecorder2 *a2,
        int a3,
        unsigned __int16 a4)
{
  unsigned int v6; // r13d
  Imapi2Utility *v8; // r15
  int CurrentDriveSpeedProperties; // ebx
  unsigned int v11; // r8d
  unsigned __int64 v12; // r9
  int v13; // eax
  unsigned int v14; // r14d
  unsigned int v15; // eax
  unsigned int *v16; // r8
  char v17; // dl
  __int64 v18; // rax
  int v19; // ebx
  int i; // eax
  _QWORD *v21; // rcx
  unsigned int v22; // eax
  __int64 j; // rdi
  __int64 v24; // rdx
  struct IWriteSpeedDescriptor **v25; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v26[2]; // [rsp+38h] [rbp-30h] BYREF
  enum _IMAPI_MEDIA_PHYSICAL_TYPE v27; // [rsp+40h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-20h] BYREF
  HLOCAL v29; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v30; // [rsp+B0h] [rbp+48h] BYREF

  v27 = -1;
  v29 = 0;
  *(_QWORD *)v26 = 0;
  hMem = 0;
  v6 = (unsigned int)a2;
  LODWORD(v25) = 0;
  LOWORD(v30) = 0;
  v8 = 0;
  if ( !this )
    return 2147500035LL;
  if ( a3 <= -2 )
    return 2147942487LL;
  CurrentDriveSpeedProperties = Imapi2Utility::BuildSupportedDescriptorArray(
                                  this,
                                  a2,
                                  &hMem,
                                  (struct IWriteSpeedDescriptor ***)&v29,
                                  (unsigned int **)&v25);
  if ( CurrentDriveSpeedProperties >= 0 )
  {
    v13 = Imapi2Utility::ConvertDescriptorArrayToULONGArray(
            (Imapi2Utility *)hMem,
            (struct IWriteSpeedDescriptor **)(unsigned int)v25,
            (unsigned int)v26,
            (unsigned int **)v12);
    v8 = *(Imapi2Utility **)v26;
    CurrentDriveSpeedProperties = v13;
  }
  HIDWORD(v25) = -1;
  v14 = -1;
  if ( CurrentDriveSpeedProperties >= 0 )
  {
    if ( a3 == -1 )
      goto LABEL_29;
    v15 = Imapi2Utility::SortAndEliminateDuplicates(v8, (unsigned int *)(unsigned int)v25, v11);
    v16 = (unsigned int *)v29;
    v12 = v15;
    LODWORD(v25) = v15;
    v17 = 0;
    v18 = 0;
    if ( (_DWORD)v12 )
    {
      do
      {
        if ( *((_DWORD *)v8 + v18) == a3 )
        {
          v14 = *((_DWORD *)v29 + v18);
          v17 = 1;
          HIDWORD(v25) = v14;
        }
        v18 = (unsigned int)(v18 + 1);
      }
      while ( (unsigned int)v18 < (unsigned int)v12 );
      if ( v17 )
        goto LABEL_29;
    }
    if ( v6 - 2 <= 1 )
    {
      v19 = 75;
    }
    else if ( v6 - 5 <= 6 )
    {
      v19 = 680;
    }
    else
    {
      v19 = -1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v6);
        v16 = (unsigned int *)v29;
        v12 = (unsigned int)v25;
      }
    }
    for ( i = a3; i >= 75; i -= v19 )
      ;
    if ( !i )
    {
      v26[0] = 0;
      if ( (int)Imapi2Utility::FindClosestSectorsPerSecondInSupportedSpeeds(
                  (Imapi2Utility *)v6,
                  (enum _IMAPI_MEDIA_PHYSICAL_TYPE)v8,
                  v16,
                  (unsigned int *)v12,
                  a3,
                  (unsigned int)v26,
                  (unsigned int *)v25) >= 0 )
      {
        v14 = v26[0];
LABEL_29:
        CurrentDriveSpeedProperties = Imapi2Utility::SetCurrentDriveWriteSpeed(
                                        (Imapi2Utility *)this,
                                        (struct IDiscRecorder2 *)v14,
                                        a4 == 0xFFFF,
                                        v12);
        if ( CurrentDriveSpeedProperties >= 0 )
        {
          v26[0] = 0;
          CurrentDriveSpeedProperties = Imapi2Utility::GetCurrentDriveSpeedProperties(
                                          (Imapi2Utility *)this,
                                          (struct IDiscRecorder2 *)v6,
                                          (unsigned int *)&v27,
                                          (_IMAPI_MEDIA_PHYSICAL_TYPE *)v26,
                                          &v30);
          if ( CurrentDriveSpeedProperties >= 0 )
          {
            if ( a3 == v27 )
            {
              CurrentDriveSpeedProperties = (_WORD)v30 != a4 ? 0xAA0005 : 0;
            }
            else if ( a4 == (_WORD)v30 )
            {
              CurrentDriveSpeedProperties = a3 != -1 ? 0xAA0004 : 0;
            }
            else
            {
              CurrentDriveSpeedProperties = (a3 != -1) + 11141125;
            }
          }
        }
        goto LABEL_36;
      }
    }
    CurrentDriveSpeedProperties = Imapi2Utility::FuzzyConvert_SectorsPerSecond2KBps(
                                    (Imapi2Utility *)v6,
                                    (enum _IMAPI_MEDIA_PHYSICAL_TYPE)a3,
                                    (unsigned int)&v25 + 4,
                                    (unsigned int *)v12);
    if ( CurrentDriveSpeedProperties >= 0 )
    {
      v14 = HIDWORD(v25);
      goto LABEL_29;
    }
  }
LABEL_36:
  v21 = hMem;
  if ( hMem )
  {
    v22 = (unsigned int)v25;
    for ( j = 0; (unsigned int)j < v22; j = (unsigned int)(j + 1) )
    {
      v24 = v21[j];
      if ( v24 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v24 + 16LL))(v21[j]);
        *((_QWORD *)hMem + j) = 0;
        v21 = hMem;
        v22 = (unsigned int)v25;
      }
    }
    if ( v21 )
    {
      LocalFree(v21);
      hMem = 0;
    }
  }
  if ( v29 )
  {
    LocalFree(v29);
    v29 = 0;
  }
  if ( v8 )
    LocalFree(v8);
  return (unsigned int)CurrentDriveSpeedProperties;
}

```

## disassembly

```asm
0x180047cd8  push    rbp
0x180047cda  push    rbx
0x180047cdb  push    rsi
0x180047cdc  push    rdi
0x180047cdd  push    r12
0x180047cdf  push    r13
0x180047ce1  push    r14
0x180047ce3  push    r15
0x180047ce5  mov     rbp, rsp
0x180047ce8  sub     rsp, 68h
0x180047cec  xor     r14d, r14d
0x180047cef  mov     [rbp+var_28], 0FFFFFFFFh
0x180047cf6  mov     [rbp+var_18], r14
0x180047cfa  movzx   esi, r9w
0x180047cfe  mov     qword ptr [rbp+var_30], r14
0x180047d02  mov     edi, r8d
0x180047d05  mov     [rbp+hMem], r14
0x180047d09  mov     r13d, edx
0x180047d0c  mov     dword ptr [rbp+var_38], r14d
0x180047d10  mov     r12, rcx
0x180047d13  mov     word ptr [rbp+arg_0], r14w
0x180047d18  mov     r15d, r14d
0x180047d1b  test    rcx, rcx
0x180047d1e  jnz     short loc_180047D2A
0x180047d20  mov     eax, 80004003h
0x180047d25  jmp     loc_180047F70
0x180047d2a  cmp     edi, 0FFFFFFFEh
0x180047d2d  jg      short loc_180047D39
0x180047d2f  mov     eax, 80070057h
0x180047d34  jmp     loc_180047F70
0x180047d39  lea     rax, [rbp+var_38]
0x180047d3d  lea     r9, [rbp+var_18]; struct IWriteSpeedDescriptor ***
0x180047d41  mov     [rsp+68h+var_48], rax; unsigned int **
0x180047d46  lea     r8, [rbp+hMem]; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x180047d4a  call    ?BuildSupportedDescriptorArray@Imapi2Utility@@YAJPEAUIDiscRecorder2@@W4_IMAPI_MEDIA_PHYSICAL_TYPE@@PEAPEAPEAUIWriteSpeedDescriptor@@PEAPEAKPEAK@Z; Imapi2Utility::BuildSupportedDescriptorArray(IDiscRecorder2 *,_IMAPI_MEDIA_PHYSICAL_TYPE,IWriteSpeedDescriptor * * *,ulong * *,ulong *)
0x180047d4f  mov     ebx, eax
0x180047d51  test    eax, eax
0x180047d53  js      short loc_180047D6B
0x180047d55  mov     edx, dword ptr [rbp+var_38]; struct IWriteSpeedDescriptor **
0x180047d58  lea     r8, [rbp+var_30]; unsigned int
0x180047d5c  mov     rcx, [rbp+hMem]; this
0x180047d60  call    ?ConvertDescriptorArrayToULONGArray@Imapi2Utility@@YAJPEAPEAUIWriteSpeedDescriptor@@KPEAPEAK@Z; Imapi2Utility::ConvertDescriptorArrayToULONGArray(IWriteSpeedDescriptor * *,ulong,ulong * *)
0x180047d65  mov     r15, qword ptr [rbp+var_30]
0x180047d69  mov     ebx, eax
0x180047d6b  or      eax, 0FFFFFFFFh
0x180047d6e  mov     dword ptr [rbp+var_38+4], eax
0x180047d71  mov     r14d, eax
0x180047d74  test    ebx, ebx
0x180047d76  js      loc_180047EF3
0x180047d7c  cmp     edi, eax
0x180047d7e  jz      loc_180047E76
0x180047d84  mov     edx, dword ptr [rbp+var_38]; unsigned int *
0x180047d87  mov     rcx, r15; this
0x180047d8a  call    ?SortAndEliminateDuplicates@Imapi2Utility@@YAKPEAKK@Z; Imapi2Utility::SortAndEliminateDuplicates(ulong *,ulong)
0x180047d8f  mov     r8, [rbp+var_18]; unsigned int *
0x180047d93  mov     r9d, eax; unsigned int *
0x180047d96  mov     dword ptr [rbp+var_38], eax
0x180047d99  xor     dl, dl
0x180047d9b  xor     eax, eax
0x180047d9d  test    r9d, r9d
0x180047da0  jz      short loc_180047DC1
0x180047da2  cmp     [r15+rax*4], edi
0x180047da6  jnz     short loc_180047DB2
0x180047da8  mov     r14d, [r8+rax*4]
0x180047dac  mov     dl, 1
0x180047dae  mov     dword ptr [rbp+var_38+4], r14d
0x180047db2  inc     eax
0x180047db4  cmp     eax, r9d
0x180047db7  jb      short loc_180047DA2
0x180047db9  test    dl, dl
0x180047dbb  jnz     loc_180047E76
0x180047dc1  lea     eax, [r13-2]
0x180047dc5  cmp     eax, 1
0x180047dc8  jbe     short loc_180047E1E
0x180047dca  lea     eax, [r13-5]
0x180047dce  cmp     eax, 6
0x180047dd1  jbe     short loc_180047E17
0x180047dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180047dda  lea     rax, WPP_GLOBAL_Control
0x180047de1  or      ebx, 0FFFFFFFFh
0x180047de4  cmp     rcx, rax
0x180047de7  jz      short loc_180047E23
0x180047de9  test    byte ptr [rcx+1Ch], 4
0x180047ded  jz      short loc_180047E23
0x180047def  cmp     byte ptr [rcx+19h], 2
0x180047df3  jb      short loc_180047E23
0x180047df5  mov     rcx, [rcx+10h]
0x180047df9  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180047e00  mov     edx, 76h ; 'v'
0x180047e05  mov     r9d, r13d
0x180047e08  call    WPP_SF_d
0x180047e0d  mov     r8, [rbp+var_18]
0x180047e11  mov     r9d, dword ptr [rbp+var_38]
0x180047e15  jmp     short loc_180047E23
0x180047e17  mov     ebx, 2A8h
0x180047e1c  jmp     short loc_180047E23
0x180047e1e  mov     ebx, 4Bh ; 'K'
0x180047e23  mov     eax, edi
0x180047e25  cmp     edi, 4Bh ; 'K'
0x180047e28  jl      short loc_180047E31
0x180047e2a  sub     eax, ebx
0x180047e2c  cmp     eax, 4Bh ; 'K'
0x180047e2f  jge     short loc_180047E2A
0x180047e31  test    eax, eax
0x180047e33  jnz     short loc_180047E5A
0x180047e35  mov     [rbp+var_30], eax
0x180047e38  mov     rdx, r15; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x180047e3b  lea     rax, [rbp+var_30]
0x180047e3f  mov     ecx, r13d; this
0x180047e42  mov     qword ptr [rsp+68h+var_40], rax; unsigned int
0x180047e47  mov     dword ptr [rsp+68h+var_48], edi; unsigned int
0x180047e4b  call    ?FindClosestSectorsPerSecondInSupportedSpeeds@Imapi2Utility@@YAJW4_IMAPI_MEDIA_PHYSICAL_TYPE@@PEAK1KK1@Z; Imapi2Utility::FindClosestSectorsPerSecondInSupportedSpeeds(_IMAPI_MEDIA_PHYSICAL_TYPE,ulong *,ulong *,ulong,ulong,ulong *)
0x180047e50  test    eax, eax
0x180047e52  js      short loc_180047E5A
0x180047e54  mov     r14d, [rbp+var_30]
0x180047e58  jmp     short loc_180047E76
0x180047e5a  lea     r8, [rbp+var_38+4]; unsigned int
0x180047e5e  mov     edx, edi; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x180047e60  mov     ecx, r13d; this
0x180047e63  call    ?FuzzyConvert_SectorsPerSecond2KBps@Imapi2Utility@@YAJW4_IMAPI_MEDIA_PHYSICAL_TYPE@@KPEAK@Z; Imapi2Utility::FuzzyConvert_SectorsPerSecond2KBps(_IMAPI_MEDIA_PHYSICAL_TYPE,ulong,ulong *)
0x180047e68  mov     ebx, eax
0x180047e6a  test    eax, eax
0x180047e6c  js      loc_180047EF3
0x180047e72  mov     r14d, dword ptr [rbp+var_38+4]
0x180047e76  xor     r8d, r8d
0x180047e79  mov     edx, r14d; struct IDiscRecorder2 *
0x180047e7c  cmp     si, 0FFFFh
0x180047e80  mov     rcx, r12; this
0x180047e83  setz    r8b; unsigned int
0x180047e87  call    ?SetCurrentDriveWriteSpeed@Imapi2Utility@@YAJPEAUIDiscRecorder2@@KK@Z; Imapi2Utility::SetCurrentDriveWriteSpeed(IDiscRecorder2 *,ulong,ulong)
0x180047e8c  mov     ebx, eax
0x180047e8e  test    eax, eax
0x180047e90  js      short loc_180047EF3
0x180047e92  lea     rax, [rbp+arg_0]
0x180047e96  mov     [rbp+var_30], 0
0x180047e9d  lea     r9, [rbp+var_30]; unsigned int *
0x180047ea1  mov     [rsp+68h+var_48], rax; unsigned int *
0x180047ea6  lea     r8, [rbp+var_28]; enum _IMAPI_MEDIA_PHYSICAL_TYPE
0x180047eaa  mov     edx, r13d; struct IDiscRecorder2 *
0x180047ead  mov     rcx, r12; this
0x180047eb0  call    ?GetCurrentDriveSpeedProperties@Imapi2Utility@@YAJPEAUIDiscRecorder2@@W4_IMAPI_MEDIA_PHYSICAL_TYPE@@PEAK2PEAF@Z; Imapi2Utility::GetCurrentDriveSpeedProperties(IDiscRecorder2 *,_IMAPI_MEDIA_PHYSICAL_TYPE,ulong *,ulong *,short *)
0x180047eb5  mov     ebx, eax
0x180047eb7  test    eax, eax
0x180047eb9  js      short loc_180047EF3
0x180047ebb  cmp     edi, [rbp+var_28]
0x180047ebe  jnz     short loc_180047ED1
0x180047ec0  sub     si, word ptr [rbp+arg_0]
0x180047ec4  neg     si
0x180047ec7  sbb     ebx, ebx
0x180047ec9  and     ebx, 0AA0005h
0x180047ecf  jmp     short loc_180047EF3
0x180047ed1  cmp     si, word ptr [rbp+arg_0]
0x180047ed5  jnz     short loc_180047EE5
0x180047ed7  inc     edi
0x180047ed9  neg     edi
0x180047edb  sbb     ebx, ebx
0x180047edd  and     ebx, 0AA0004h
0x180047ee3  jmp     short loc_180047EF3
0x180047ee5  xor     ebx, ebx
0x180047ee7  cmp     edi, 0FFFFFFFFh
0x180047eea  setnz   bl
0x180047eed  add     ebx, 0AA0005h
0x180047ef3  mov     rcx, [rbp+hMem]
0x180047ef7  test    rcx, rcx
0x180047efa  jz      short loc_180047F49
0x180047efc  mov     eax, dword ptr [rbp+var_38]
0x180047eff  xor     edi, edi
0x180047f01  test    eax, eax
0x180047f03  jz      short loc_180047F36
0x180047f05  mov     rdx, [rcx+rdi*8]
0x180047f09  test    rdx, rdx
0x180047f0c  jz      short loc_180047F30
0x180047f0e  mov     rax, [rdx]
0x180047f11  mov     rcx, rdx
0x180047f14  mov     rax, [rax+10h]
0x180047f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f1d  mov     rax, [rbp+hMem]
0x180047f21  mov     qword ptr [rax+rdi*8], 0
0x180047f29  mov     rcx, [rbp+hMem]; hMem
0x180047f2d  mov     eax, dword ptr [rbp+var_38]
0x180047f30  inc     edi
0x180047f32  cmp     edi, eax
0x180047f34  jb      short loc_180047F05
0x180047f36  test    rcx, rcx
0x180047f39  jz      short loc_180047F49
0x180047f3b  call    cs:__imp_LocalFree
0x180047f41  mov     [rbp+hMem], 0
0x180047f49  mov     rcx, [rbp+var_18]; hMem
0x180047f4d  test    rcx, rcx
0x180047f50  jz      short loc_180047F60
0x180047f52  call    cs:__imp_LocalFree
0x180047f58  mov     [rbp+var_18], 0
0x180047f60  test    r15, r15
0x180047f63  jz      short loc_180047F6E
0x180047f65  mov     rcx, r15; hMem
0x180047f68  call    cs:__imp_LocalFree
0x180047f6e  mov     eax, ebx
0x180047f70  add     rsp, 68h
0x180047f74  pop     r15
0x180047f76  pop     r14
0x180047f78  pop     r13
0x180047f7a  pop     r12
0x180047f7c  pop     rdi
0x180047f7d  pop     rsi
0x180047f7e  pop     rbx
0x180047f7f  pop     rbp
0x180047f80  retn
```
