# Imapi2Utility::ReadDataDisc(IDiscRecorder2Ex *,ulong,ulong,long (*)(uchar *,ulong,ulong,ulong,void *,ulong),void *,ulong)

- ea: `0x18000a8ac`
- end: `0x18000ab8c`
- name: `?ReadDataDisc@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@KKP6AJPEAEKKKPEAXK@Z2K@Z`
- size: `736`
- prototype: `__int64 __usercall@<rax>(Imapi2Utility *__hidden this@<rcx>, struct IDiscRecorder2Ex *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, int (*)(unsigned __int8 *, unsigned int, unsigned int, unsigned int, void *, unsigned int), void *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180009984`
- `0x18001d338`
- `0x18001d9bc`

## callees

- `0x18000a8ac`
- `0x18000ae3c`
- `0x180014180`
- `0x180046708`
- `0x18004984a`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18000aa26`
- `KERNEL32!Sleep` at `0x18000aa26`
- `KERNEL32!LocalAlloc` at `0x18000a92d`
- `KERNEL32!LocalAlloc` at `0x18000a92d`
- `KERNEL32!LocalFree` at `0x18000ab64`
- `KERNEL32!LocalFree` at `0x18000ab64`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::ReadDataDisc(
        Imapi2Utility *this,
        struct IDiscRecorder2Ex *a2,
        unsigned int a3,
        unsigned int *a4,
        int (*a5)(unsigned __int8 *, unsigned int, unsigned int, unsigned int, void *, unsigned int),
        void *a6)
{
  unsigned int v7; // r15d
  int lpVtbl_high; // ebx
  unsigned int v9; // r12d
  SIZE_T v10; // rsi
  HLOCAL v11; // rdi
  __int64 v12; // r8
  int v13; // esi
  __int16 v14; // cx
  __int16 v15; // ax
  __int16 v16; // dx
  __int64 v17; // rax
  __int64 (__fastcall *v18)(Imapi2Utility *, __int128 *, __int64, union _CDB *, __int64, HLOCAL, int, unsigned int *); // rax
  int v19; // eax
  int *v20; // r9
  PVOID *v21; // r11
  unsigned int v22; // eax
  __int64 v24; // [rsp+20h] [rbp-99h]
  struct IDiscRecorder2Ex v25; // [rsp+50h] [rbp-69h] BYREF
  __int16 v26; // [rsp+58h] [rbp-61h]
  __int16 v27; // [rsp+5Ah] [rbp-5Fh]
  __int16 v28; // [rsp+5Ch] [rbp-5Dh]
  unsigned int v29; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v30; // [rsp+64h] [rbp-55h]
  int v31; // [rsp+68h] [rbp-51h]
  Imapi2Utility *v32; // [rsp+70h] [rbp-49h]
  int (*v33)(unsigned __int8 *, unsigned int, unsigned int, unsigned int, void *, unsigned int); // [rsp+78h] [rbp-41h]
  unsigned int *v34; // [rsp+80h] [rbp-39h]
  __int128 v35; // [rsp+88h] [rbp-31h] BYREF
  union _CDB v36; // [rsp+98h] [rbp-21h] BYREF
  __int16 v37; // [rsp+A8h] [rbp-11h]

  v32 = this;
  v33 = a5;
  v7 = (unsigned int)a2;
  v34 = a4;
  v25.lpVtbl = 0;
  lpVtbl_high = Imapi2Utility::ReadMediaCapacity(this, &v25, (unsigned int *)&v25.lpVtbl + 1, a4);
  if ( lpVtbl_high < 0 )
    return (unsigned int)lpVtbl_high;
  v9 = 0;
  v29 = 0;
  v10 = (unsigned int)(16 * LODWORD(v25.lpVtbl));
  v11 = LocalAlloc(0x40u, v10);
  v37 = 0;
  v35 = 0;
  v36 = 0;
  if ( v11 )
  {
    memset_0(v11, 0, v10);
    v12 = 10;
    v35 = 0;
    LOBYTE(v35) = 40;
  }
  else
  {
    v12 = 0;
    lpVtbl_high = -2147024882;
  }
  v30 = v12;
  while ( a3 && lpVtbl_high >= 0 )
  {
    v13 = 16;
    if ( a3 < 0x10 )
      v13 = a3;
    v14 = BYTE1(v7);
    v15 = HIBYTE(HIWORD(v7));
    v16 = BYTE1(v13);
    v28 = BYTE1(v13);
    v26 = HIBYTE(HIWORD(v7));
    v27 = BYTE1(v7);
    while ( 1 )
    {
      BYTE4(v35) = v14;
      BYTE2(v35) = v15;
      v17 = *(_QWORD *)v32;
      BYTE7(v35) = v16;
      v18 = *(__int64 (__fastcall **)(Imapi2Utility *, __int128 *, __int64, union _CDB *, __int64, HLOCAL, int, unsigned int *))(v17 + 40);
      v31 = LODWORD(v25.lpVtbl) * v13;
      LODWORD(v24) = 12;
      BYTE3(v35) = BYTE2(v7);
      BYTE5(v35) = v7;
      BYTE8(v35) = v13;
      v19 = v18(v32, &v35, v12, &v36, v24, v11, LODWORD(v25.lpVtbl) * v13, &v29);
      HIDWORD(v25.lpVtbl) = v19;
      lpVtbl_high = v19;
      if ( v19 >= 0 && v19 != 11141632 )
      {
        v21 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_23;
      }
      Sleep(0x3E8u);
      ++v9;
      v21 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_ddD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          134,
          &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
          (unsigned int)lpVtbl_high,
          v7,
          v9);
        v21 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( lpVtbl_high >= 0 && lpVtbl_high != 11141632 )
        goto LABEL_23;
      if ( v9 >= 5 )
        break;
      LOBYTE(v15) = v26;
      LOBYTE(v14) = v27;
      LOBYTE(v16) = v28;
      v12 = v30;
    }
    if ( lpVtbl_high == 11141632 )
    {
      Imapi2Utility::TranslateSenseInfoToHResult(
        (Imapi2Utility *)&v35,
        &v36,
        (const struct _SENSE_DATA *)((char *)&v25.lpVtbl + 4),
        v20);
      lpVtbl_high = HIDWORD(v25.lpVtbl);
    }
LABEL_23:
    if ( lpVtbl_high >= 0 )
    {
      v22 = v29;
      if ( v29 != v31 )
      {
        lpVtbl_high = -2147467259;
        if ( v21 == &WPP_GLOBAL_Control || (*((_BYTE *)v21 + 28) & 4) == 0 || *((_BYTE *)v21 + 25) < 2u )
          goto LABEL_32;
        WPP_SF_ddD(v21[2], 135, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v29, v31, v7);
        v22 = v29;
      }
      if ( lpVtbl_high >= 0 )
      {
        lpVtbl_high = ((__int64 (__fastcall *)(HLOCAL, _QWORD, _QWORD, _QWORD, int (*)(unsigned __int8 *, unsigned int, unsigned int, unsigned int, void *, unsigned int), _DWORD))v34)(
                        v11,
                        v22,
                        v7,
                        LODWORD(v25.lpVtbl),
                        v33,
                        (_DWORD)a6);
        if ( lpVtbl_high >= 0 )
        {
          a3 -= v13;
          v7 += v13;
        }
      }
    }
LABEL_32:
    v12 = v30;
  }
  if ( v11 )
    LocalFree(v11);
  return (unsigned int)lpVtbl_high;
}

```

## disassembly

```asm
0x18000a8ac  push    rbp
0x18000a8ae  push    rbx
0x18000a8af  push    rsi
0x18000a8b0  push    rdi
0x18000a8b1  push    r12
0x18000a8b3  push    r13
0x18000a8b5  push    r14
0x18000a8b7  push    r15
0x18000a8b9  lea     rbp, [rsp-0Fh]
0x18000a8be  sub     rsp, 0C8h
0x18000a8c5  mov     rax, cs:__security_cookie
0x18000a8cc  xor     rax, rsp
0x18000a8cf  mov     [rbp+47h+var_50], rax
0x18000a8d3  mov     rax, rcx
0x18000a8d6  mov     [rbp+47h+var_90], rcx
0x18000a8da  mov     rcx, [rbp+47h+arg_20]
0x18000a8de  mov     r14d, r8d
0x18000a8e1  mov     [rbp+47h+var_88], rcx
0x18000a8e5  lea     r8, [rbp+47h+var_B0.lpVtbl+4]; unsigned int *
0x18000a8e9  mov     r15d, edx
0x18000a8ec  mov     [rbp+47h+var_80], r9
0x18000a8f0  mov     rcx, rax; this
0x18000a8f3  mov     dword ptr [rbp+47h+var_B0.lpVtbl], 0
0x18000a8fa  lea     rdx, [rbp+47h+var_B0]; struct IDiscRecorder2Ex *
0x18000a8fe  mov     dword ptr [rbp+47h+var_B0.lpVtbl+4], 0
0x18000a905  call    ?ReadMediaCapacity@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAK1@Z; Imapi2Utility::ReadMediaCapacity(IDiscRecorder2Ex *,ulong *,ulong *)
0x18000a90a  mov     ebx, eax
0x18000a90c  test    eax, eax
0x18000a90e  js      loc_18000AB6A
0x18000a914  mov     eax, dword ptr [rbp+47h+var_B0.lpVtbl]
0x18000a917  xor     r12d, r12d
0x18000a91a  shl     eax, 4
0x18000a91d  mov     edx, eax; uBytes
0x18000a91f  mov     [rbp+47h+var_A0], 0
0x18000a926  lea     ecx, [r12+40h]; uFlags
0x18000a92b  mov     esi, eax
0x18000a92d  call    cs:__imp_LocalAlloc
0x18000a933  xorps   xmm0, xmm0
0x18000a936  xorps   xmm1, xmm1
0x18000a939  mov     rdi, rax
0x18000a93c  xor     eax, eax
0x18000a93e  mov     [rbp+47h+var_58], ax
0x18000a942  movups  [rbp+47h+var_78], xmm0
0x18000a946  movups  xmmword ptr [rbp+47h+var_68], xmm1
0x18000a94a  test    rdi, rdi
0x18000a94d  jnz     short loc_18000A959
0x18000a94f  xor     r8d, r8d
0x18000a952  mov     ebx, 8007000Eh
0x18000a957  jmp     short loc_18000A977
0x18000a959  mov     r8, rsi; Size
0x18000a95c  xor     edx, edx; Val
0x18000a95e  mov     rcx, rdi; void *
0x18000a961  call    memset_0
0x18000a966  xorps   xmm0, xmm0
0x18000a969  mov     r8d, 0Ah
0x18000a96f  movups  [rbp+47h+var_78], xmm0
0x18000a973  mov     byte ptr [rbp+47h+var_78], 28h ; '('
0x18000a977  mov     [rbp+47h+var_9C], r8d
0x18000a97b  jmp     loc_18000AB53
0x18000a980  test    ebx, ebx
0x18000a982  js      loc_18000AB5C
0x18000a988  mov     esi, 10h
0x18000a98d  mov     r13d, r15d
0x18000a990  cmp     r14d, esi
0x18000a993  movzx   ecx, r15w
0x18000a997  cmovb   esi, r14d
0x18000a99b  shr     r13d, 10h
0x18000a99f  shr     cx, 8
0x18000a9a3  movzx   eax, r13w
0x18000a9a7  shr     ax, 8
0x18000a9ab  movzx   edx, si
0x18000a9ae  shr     dx, 8
0x18000a9b2  mov     [rbp+47h+var_A4], dx
0x18000a9b6  mov     [rbp+47h+var_A8], ax
0x18000a9ba  mov     [rbp+47h+var_A6], cx
0x18000a9be  mov     r10, [rbp+47h+var_90]
0x18000a9c2  lea     r9, [rbp+47h+var_68]
0x18000a9c6  mov     byte ptr [rbp+47h+var_78+4], cl
0x18000a9c9  mov     ecx, esi
0x18000a9cb  imul    ecx, dword ptr [rbp+47h+var_B0.lpVtbl]
0x18000a9cf  mov     byte ptr [rbp+47h+var_78+2], al
0x18000a9d2  mov     rax, [r10]
0x18000a9d5  mov     byte ptr [rbp+47h+var_78+7], dl
0x18000a9d8  lea     rdx, [rbp+47h+var_A0]
0x18000a9dc  mov     [rsp+100h+var_C8], rdx
0x18000a9e1  lea     rdx, [rbp+47h+var_78]
0x18000a9e5  mov     [rsp+100h+var_D0], ecx
0x18000a9e9  mov     rax, [rax+28h]
0x18000a9ed  mov     [rbp+47h+var_98], ecx
0x18000a9f0  mov     rcx, r10
0x18000a9f3  mov     [rsp+100h+var_D8], rdi
0x18000a9f8  mov     dword ptr [rsp+100h+var_E0], 0Ch
0x18000aa00  mov     byte ptr [rbp+47h+var_78+3], r13b
0x18000aa04  mov     byte ptr [rbp+47h+var_78+5], r15b
0x18000aa08  mov     byte ptr [rbp+47h+var_78+8], sil
0x18000aa0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa11  mov     dword ptr [rbp+47h+var_B0.lpVtbl+4], eax
0x18000aa14  mov     ebx, eax
0x18000aa16  test    eax, eax
0x18000aa18  js      short loc_18000AA21
0x18000aa1a  cmp     eax, 0AA0200h
0x18000aa1f  jnz     short loc_18000AAA0
0x18000aa21  mov     ecx, 3E8h; dwMilliseconds
0x18000aa26  call    cs:__imp_Sleep
0x18000aa2c  inc     r12d
0x18000aa2f  mov     r11, cs:WPP_GLOBAL_Control
0x18000aa36  lea     rax, WPP_GLOBAL_Control
0x18000aa3d  cmp     r11, rax
0x18000aa40  jz      short loc_18000AA79
0x18000aa42  test    byte ptr [r11+1Ch], 4
0x18000aa47  jz      short loc_18000AA79
0x18000aa49  cmp     byte ptr [r11+19h], 2
0x18000aa4e  jb      short loc_18000AA79
0x18000aa50  mov     rcx, [r11+10h]
0x18000aa54  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18000aa5b  mov     edx, 86h
0x18000aa60  mov     dword ptr [rsp+100h+var_D8], r12d
0x18000aa65  mov     r9d, ebx
0x18000aa68  mov     dword ptr [rsp+100h+var_E0], r15d
0x18000aa6d  call    WPP_SF_ddD
0x18000aa72  mov     r11, cs:WPP_GLOBAL_Control
0x18000aa79  test    ebx, ebx
0x18000aa7b  js      short loc_18000AA85
0x18000aa7d  cmp     ebx, 0AA0200h
0x18000aa83  jnz     short loc_18000AAC5
0x18000aa85  cmp     r12d, 5
0x18000aa89  jnb     short loc_18000AAA9
0x18000aa8b  movzx   eax, [rbp+47h+var_A8]
0x18000aa8f  movzx   ecx, [rbp+47h+var_A6]
0x18000aa93  movzx   edx, [rbp+47h+var_A4]
0x18000aa97  mov     r8d, [rbp+47h+var_9C]
0x18000aa9b  jmp     loc_18000A9BE
0x18000aaa0  mov     r11, cs:WPP_GLOBAL_Control
0x18000aaa7  jmp     short loc_18000AAC5
0x18000aaa9  cmp     ebx, 0AA0200h
0x18000aaaf  jnz     short loc_18000AAC5
0x18000aab1  lea     r8, [rbp+47h+var_B0.lpVtbl+4]; struct _SENSE_DATA *
0x18000aab5  lea     rdx, [rbp+47h+var_68]; union _CDB *
0x18000aab9  lea     rcx, [rbp+47h+var_78]; this
0x18000aabd  call    ?TranslateSenseInfoToHResult@Imapi2Utility@@YA?BEPEBT_CDB@@PEBU_SENSE_DATA@@PEAJ@Z; Imapi2Utility::TranslateSenseInfoToHResult(_CDB const *,_SENSE_DATA const *,long *)
0x18000aac2  mov     ebx, dword ptr [rbp+47h+var_B0.lpVtbl+4]
0x18000aac5  test    ebx, ebx
0x18000aac7  js      loc_18000AB4F
0x18000aacd  mov     eax, [rbp+47h+var_A0]
0x18000aad0  mov     ecx, [rbp+47h+var_98]
0x18000aad3  cmp     eax, ecx
0x18000aad5  jz      short loc_18000AB1A
0x18000aad7  mov     ebx, 80004005h
0x18000aadc  lea     rdx, WPP_GLOBAL_Control
0x18000aae3  cmp     r11, rdx
0x18000aae6  jz      short loc_18000AB4F
0x18000aae8  test    byte ptr [r11+1Ch], 4
0x18000aaed  jz      short loc_18000AB4F
0x18000aaef  cmp     byte ptr [r11+19h], 2
0x18000aaf4  jb      short loc_18000AB4F
0x18000aaf6  mov     dword ptr [rsp+100h+var_D8], r15d
0x18000aafb  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18000ab02  mov     dword ptr [rsp+100h+var_E0], ecx
0x18000ab06  mov     edx, 87h
0x18000ab0b  mov     rcx, [r11+10h]
0x18000ab0f  mov     r9d, eax
0x18000ab12  call    WPP_SF_ddD
0x18000ab17  mov     eax, [rbp+47h+var_A0]
0x18000ab1a  test    ebx, ebx
0x18000ab1c  js      short loc_18000AB4F
0x18000ab1e  mov     ecx, dword ptr [rbp+47h+arg_28]
0x18000ab21  mov     edx, eax
0x18000ab23  mov     r9d, dword ptr [rbp+47h+var_B0.lpVtbl]
0x18000ab27  mov     r8d, r15d
0x18000ab2a  mov     rax, [rbp+47h+var_80]
0x18000ab2e  mov     dword ptr [rsp+100h+var_D8], ecx
0x18000ab32  mov     rcx, [rbp+47h+var_88]
0x18000ab36  mov     [rsp+100h+var_E0], rcx
0x18000ab3b  mov     rcx, rdi
0x18000ab3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab43  mov     ebx, eax
0x18000ab45  test    eax, eax
0x18000ab47  js      short loc_18000AB4F
0x18000ab49  sub     r14d, esi
0x18000ab4c  add     r15d, esi
0x18000ab4f  mov     r8d, [rbp+47h+var_9C]
0x18000ab53  test    r14d, r14d
0x18000ab56  jnz     loc_18000A980
0x18000ab5c  test    rdi, rdi
0x18000ab5f  jz      short loc_18000AB6A
0x18000ab61  mov     rcx, rdi; hMem
0x18000ab64  call    cs:__imp_LocalFree
0x18000ab6a  mov     eax, ebx
0x18000ab6c  mov     rcx, [rbp+47h+var_50]
0x18000ab70  xor     rcx, rsp; StackCookie
0x18000ab73  call    __security_check_cookie
0x18000ab78  add     rsp, 0C8h
0x18000ab7f  pop     r15
0x18000ab81  pop     r14
0x18000ab83  pop     r13
0x18000ab85  pop     r12
0x18000ab87  pop     rdi
0x18000ab88  pop     rsi
0x18000ab89  pop     rbx
0x18000ab8a  pop     rbp
0x18000ab8b  retn
```
