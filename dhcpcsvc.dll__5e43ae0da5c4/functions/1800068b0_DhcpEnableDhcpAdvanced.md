# DhcpEnableDhcpAdvanced

- ea: `0x1800068b0`
- end: `0x180006a16`
- name: `DhcpEnableDhcpAdvanced`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002620`
- `0x180002760`
- `0x1800068b0`
- `0x180006a1c`
- `0x18000f3b8`
- `0x180011784`
- `0x180012850`
- `0x180012a00`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800068f6`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x1800068f6`

## pseudocode

```c
__int64 __fastcall DhcpEnableDhcpAdvanced(__int64 a1, int a2, int a3, float a4, unsigned int a5, int a6)
{
  LPWSTR CommandLineW; // rax
  int v10; // edx
  int v11; // ecx
  int v12; // r8d
  unsigned int v13; // eax
  unsigned int started; // ebx
  __int64 v15; // rdx
  __int64 v16; // r9
  double v18; // [rsp+30h] [rbp-78h]
  _QWORD v19[2]; // [rsp+50h] [rbp-58h] BYREF

  v19[0] = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    v18 = a4;
    WPP_SF_SddggdS(
      v11,
      v10,
      v12,
      a1,
      a2,
      a3,
      SLOBYTE(v18),
      *(_OWORD *)&_mm_cvtps_pd((__m128)a5),
      a6,
      (__int64)CommandLineW);
  }
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    started = 50;
    if ( (xmmword_18001E1E0 & 2) == 0 )
      goto LABEL_13;
    v15 = 55;
    v16 = 50;
    goto LABEL_12;
  }
  v13 = DhcpAdapterNameToIfId(a1, v19);
  started = v13;
  if ( v13 )
  {
    if ( (xmmword_18001E1E0 & 2) == 0 )
      goto LABEL_13;
    v15 = 56;
    v16 = v13;
LABEL_12:
    WPP_SF_d(1025, v15, WPP_e15037783097355a5233924022d92169_Traceguids, v16);
    goto LABEL_13;
  }
  started = DhcpEnableDhcpAdvancedInternal((__int64)v19, a2, a3, a4, a5, a6);
  if ( started == 1722 )
  {
    started = DhcpStartDhcpServiceInternal();
    if ( !started )
      started = DhcpEnableDhcpAdvancedInternal((__int64)v19, a2, a3, a4, a5, a6);
  }
LABEL_13:
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 57, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, a1, started);
  return started;
}

```

## disassembly

```asm
0x1800068b0  push    rbx
0x1800068b2  push    rbp
0x1800068b3  push    rsi
0x1800068b4  push    rdi
0x1800068b5  push    r14
0x1800068b7  sub     rsp, 80h
0x1800068be  movaps  [rsp+0A8h+var_38], xmm6
0x1800068c3  mov     esi, r8d
0x1800068c6  movaps  [rsp+0A8h+var_48], xmm7
0x1800068cb  movaps  xmm6, xmm3
0x1800068ce  mov     ebp, edx
0x1800068d0  mov     [rsp+0A8h+var_58], 0
0x1800068d9  mov     rdi, rcx
0x1800068dc  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800068e3  mov     r14d, [rsp+0A8h+arg_28]
0x1800068eb  movss   xmm7, [rsp+0A8h+arg_20]
0x1800068f4  jz      short loc_18000692C
0x1800068f6  call    cs:__imp_GetCommandLineW
0x1800068fc  mov     [rsp+0A8h+var_60], rax
0x180006901  xorps   xmm1, xmm1
0x180006904  mov     [rsp+0A8h+var_68], r14d
0x180006909  mov     r9, rdi
0x18000690c  cvtps2pd xmm0, xmm7
0x18000690f  cvtss2sd xmm1, xmm6
0x180006913  movsd   [rsp+0A8h+var_70], xmm0
0x180006919  movsd   [rsp+0A8h+var_78], xmm1
0x18000691f  mov     [rsp+0A8h+var_80], esi
0x180006923  mov     [rsp+0A8h+var_88], ebp
0x180006927  call    WPP_SF_SddggdS
0x18000692c  call    DhcpIsFSEGuestSystem
0x180006931  test    eax, eax
0x180006933  jnz     short loc_1800069B1
0x180006935  lea     rdx, [rsp+0A8h+var_58]
0x18000693a  mov     rcx, rdi
0x18000693d  call    DhcpAdapterNameToIfId
0x180006942  mov     ebx, eax
0x180006944  test    eax, eax
0x180006946  jz      short loc_18000695F
0x180006948  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000694f  jz      loc_1800069D6
0x180006955  mov     edx, 38h ; '8'
0x18000695a  mov     r9d, eax
0x18000695d  jmp     short loc_1800069C5
0x18000695f  mov     [rsp+0A8h+var_80], r14d
0x180006964  lea     rcx, [rsp+0A8h+var_58]
0x180006969  movaps  xmm3, xmm6
0x18000696c  movss   [rsp+0A8h+var_88], xmm7
0x180006972  mov     r8d, esi
0x180006975  mov     edx, ebp
0x180006977  call    DhcpEnableDhcpAdvancedInternal
0x18000697c  mov     ebx, eax
0x18000697e  cmp     eax, 6BAh
0x180006983  jnz     short loc_1800069D6
0x180006985  call    DhcpStartDhcpServiceInternal
0x18000698a  mov     ebx, eax
0x18000698c  test    eax, eax
0x18000698e  jnz     short loc_1800069D6
0x180006990  mov     [rsp+0A8h+var_80], r14d
0x180006995  lea     rcx, [rsp+0A8h+var_58]
0x18000699a  movaps  xmm3, xmm6
0x18000699d  movss   [rsp+0A8h+var_88], xmm7
0x1800069a3  mov     r8d, esi
0x1800069a6  mov     edx, ebp
0x1800069a8  call    DhcpEnableDhcpAdvancedInternal
0x1800069ad  mov     ebx, eax
0x1800069af  jmp     short loc_1800069D6
0x1800069b1  mov     ebx, 32h ; '2'
0x1800069b6  test    byte ptr cs:xmmword_18001E1E0, 2
0x1800069bd  jz      short loc_1800069D6
0x1800069bf  lea     edx, [rbx+5]
0x1800069c2  mov     r9d, ebx
0x1800069c5  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800069cc  mov     ecx, 401h
0x1800069d1  call    WPP_SF_d
0x1800069d6  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800069dd  jz      short loc_1800069FC
0x1800069df  mov     edx, 39h ; '9'
0x1800069e4  mov     [rsp+0A8h+var_88], ebx
0x1800069e8  mov     ecx, 404h
0x1800069ed  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800069f4  mov     r9, rdi
0x1800069f7  call    WPP_SF_SD
0x1800069fc  movaps  xmm6, [rsp+0A8h+var_38]
0x180006a01  mov     eax, ebx
0x180006a03  movaps  xmm7, [rsp+0A8h+var_48]
0x180006a08  add     rsp, 80h
0x180006a0f  pop     r14
0x180006a11  pop     rdi
0x180006a12  pop     rsi
0x180006a13  pop     rbp
0x180006a14  pop     rbx
0x180006a15  retn
```
