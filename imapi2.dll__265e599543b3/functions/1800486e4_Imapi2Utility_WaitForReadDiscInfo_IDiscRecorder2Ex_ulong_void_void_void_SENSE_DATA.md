# Imapi2Utility::WaitForReadDiscInfo(IDiscRecorder2Ex *,ulong,void *,void (*)(void *,_SENSE_DATA *))

- ea: `0x1800486e4`
- end: `0x1800489ca`
- name: `?WaitForReadDiscInfo@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@KPEAXP6AX1PEAU_SENSE_DATA@@@Z@Z`
- size: `742`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, struct IDiscRecorder2Ex *, unsigned int, void *, void (*)(void *, struct _SENSE_DATA *))`
- caller_count: `13`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180018908`
- `0x180018aec`
- `0x180018cd0`
- `0x180018e80`
- `0x1800190f8`
- `0x180019490`
- `0x180019728`
- `0x180019a00`
- `0x180019dc8`
- `0x18001c518`
- `0x1800274f8`
- `0x1800306c0`
- `0x1800369e0`

## callees

- `0x18000ae3c`
- `0x18000f76c`
- `0x1800140f4`
- `0x180016778`
- `0x1800236b4`
- `0x180023790`
- `0x1800486e4`
- `0x180048e6c`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `KERNEL32!Sleep` at `0x180048744`
- `KERNEL32!Sleep` at `0x180048744`

## pseudocode

```c
__int64 __fastcall Imapi2Utility::WaitForReadDiscInfo(
        Imapi2Utility *this,
        struct IDiscRecorder2Ex *a2,
        __int64 a3,
        void (__fastcall *a4)(__int64, union _CDB *))
{
  int v4; // ebx
  char v5; // si
  int v8; // edi
  __int64 (__fastcall *v10)(Imapi2Utility *, __int128 *, __int64, union _CDB *, int, _OWORD *, int, UCHAR *); // rax
  struct _SENSE_DATA *v11; // r9
  int *v12; // r9
  PVOID *v13; // rcx
  PVOID v14; // rcx
  struct _SENSE_DATA v16; // [rsp+50h] [rbp-79h] BYREF
  int v17; // [rsp+62h] [rbp-67h]
  __int16 v18; // [rsp+66h] [rbp-63h]
  union _CDB *v19; // [rsp+68h] [rbp-61h]
  __int16 v20; // [rsp+70h] [rbp-59h] BYREF
  int v21; // [rsp+72h] [rbp-57h]
  __int16 v22; // [rsp+76h] [rbp-53h]
  union _CDB *v23; // [rsp+78h] [rbp-51h]
  union _CDB v24; // [rsp+80h] [rbp-49h] BYREF
  __int16 v25; // [rsp+90h] [rbp-39h]
  __int128 v26; // [rsp+98h] [rbp-31h] BYREF
  _OWORD v27[3]; // [rsp+B0h] [rbp-19h] BYREF

  v4 = 0;
  v5 = 0;
  v27[1] = 0;
  v8 = 1;
  if ( (_DWORD)a2 )
    v8 = (int)a2;
  v27[0] = 0;
  *(_OWORD *)((char *)&v27[1] + 10) = 0;
  do
  {
    if ( v5 || !v8 )
      break;
    Sleep(0x3E8u);
    *(_DWORD *)&v16.Information[1] = 0;
    v25 = 0;
    v10 = *(__int64 (__fastcall **)(Imapi2Utility *, __int128 *, __int64, union _CDB *, int, _OWORD *, int, UCHAR *))(*(_QWORD *)this + 40LL);
    v26 = 0;
    LOBYTE(v26) = 81;
    *(_WORD *)((char *)&v26 + 7) = 10752;
    v24 = 0;
    memset(v27, 0, 42);
    v4 = v10(this, &v26, 10, &v24, 10, v27, 42, &v16.Information[1]);
    if ( v4 == 11141632 )
    {
      if ( Imapi2Utility::IsSenseDataInTable(
             (Imapi2Utility *)&Imapi2Utility::AllowedSenseForLongOperations,
             (struct Imapi2Utility::_SENSE_STUFF *)3,
             (int)&v24,
             v11) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v17 = 0;
          v18 = 0;
          *(_WORD *)&v16.SenseKeySpecific[1] = 18;
          v19 = &v24;
          WPP_SF_DDD_HEX_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v24.CDB16.TransferLength[2],
            (unsigned int)&v16.SenseKeySpecific[1],
            v24.CDB6GENERIC.CommandUniqueBytes[0] & 0xF,
            v24.CDB16.TransferLength[2],
            v24.CDB16.TransferLength[3],
            (__int64)&v16.SenseKeySpecific[1]);
        }
        if ( a4 )
          a4(a3, &v24);
        v4 = 0;
      }
      else
      {
        *(_DWORD *)&v16 = -2147467259;
        Imapi2Utility::TranslateSenseInfoToHResult((Imapi2Utility *)&v26, &v24, &v16, v12);
        v13 = (PVOID *)WPP_GLOBAL_Control;
        v4 = (int)v16;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
            v13 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 && *((_BYTE *)v13 + 25) >= 3u )
          {
            v14 = v13[2];
            v21 = 0;
            v22 = 0;
            v20 = 18;
            v23 = &v24;
            WPP_SF__HEX_(v14, 53, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, &v20);
          }
        }
      }
    }
    else if ( v4 >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
      }
      v5 = 1;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
        (unsigned int)v4);
    }
    --v8;
  }
  while ( v4 >= 0 );
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800486e4  push    rbp
0x1800486e6  push    rbx
0x1800486e7  push    rsi
0x1800486e8  push    rdi
0x1800486e9  push    r12
0x1800486eb  push    r14
0x1800486ed  push    r15
0x1800486ef  lea     rbp, [rsp-27h]
0x1800486f4  sub     rsp, 0F0h
0x1800486fb  mov     rax, cs:__security_cookie
0x180048702  xor     rax, rsp
0x180048705  mov     [rbp+57h+var_40], rax
0x180048709  xorps   xmm0, xmm0
0x18004870c  xor     ebx, ebx
0x18004870e  xor     sil, sil
0x180048711  mov     r14, r9
0x180048714  test    edx, edx
0x180048716  mov     r15, r8
0x180048719  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18004871d  lea     edi, [rbx+1]
0x180048720  mov     r12, rcx
0x180048723  cmovnz  edi, edx
0x180048726  movups  [rbp+57h+var_70], xmm0
0x18004872a  movups  xmmword ptr [rbp+57h+var_60+0Ah], xmm0
0x18004872e  test    sil, sil
0x180048731  jnz     loc_1800489AA
0x180048737  test    edi, edi
0x180048739  jz      loc_1800489AA
0x18004873f  mov     ecx, 3E8h; dwMilliseconds
0x180048744  call    cs:__imp_Sleep
0x18004874a  xor     eax, eax
0x18004874c  mov     dword ptr [rbp+57h+var_D0.Information+1], 0
0x180048753  xorps   xmm1, xmm1
0x180048756  mov     [rbp+57h+var_90], ax
0x18004875a  mov     rax, [r12]
0x18004875e  lea     rcx, [rbp+57h+var_D0.Information+1]
0x180048762  mov     [rsp+120h+var_E8], rcx
0x180048767  lea     r9, [rbp+57h+var_A0]
0x18004876b  lea     rcx, [rbp+57h+var_70]
0x18004876f  mov     dword ptr [rsp+120h+var_F0], 2Ah ; '*'
0x180048777  mov     [rsp+120h+var_F8], rcx
0x18004877c  lea     rdx, [rbp+57h+var_88]
0x180048780  mov     rax, [rax+28h]
0x180048784  mov     ecx, 0Ah
0x180048789  xorps   xmm0, xmm0
0x18004878c  mov     [rsp+120h+var_100], ecx
0x180048790  movups  [rbp+57h+var_88], xmm0
0x180048794  mov     r8d, ecx
0x180048797  mov     byte ptr [rbp+57h+var_88], 51h ; 'Q'
0x18004879b  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x18004879f  mov     rcx, r12
0x1800487a2  mov     word ptr [rbp+57h+var_88+7], 2A00h
0x1800487a8  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x1800487ac  movups  [rbp+57h+var_70], xmm1
0x1800487b0  movups  xmmword ptr [rbp+57h+var_60+0Ah], xmm1
0x1800487b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487b9  mov     ebx, eax
0x1800487bb  cmp     eax, 0AA0200h
0x1800487c0  jnz     loc_18004892C
0x1800487c6  lea     r8, [rbp+57h+var_A0]; int
0x1800487ca  mov     edx, 3; struct Imapi2Utility::_SENSE_STUFF *
0x1800487cf  lea     rcx, ?AllowedSenseForLongOperations@Imapi2Utility@@3PAU_SENSE_STUFF@1@A; this
0x1800487d6  call    ?IsSenseDataInTable@Imapi2Utility@@YAEPEAU_SENSE_STUFF@1@JPEAU_SENSE_DATA@@@Z; Imapi2Utility::IsSenseDataInTable(Imapi2Utility::_SENSE_STUFF *,long,_SENSE_DATA *)
0x1800487db  test    al, al
0x1800487dd  jz      short loc_18004885C
0x1800487df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800487e6  lea     rax, WPP_GLOBAL_Control
0x1800487ed  cmp     rcx, rax
0x1800487f0  jz      short loc_180048841
0x1800487f2  test    byte ptr [rcx+1Ch], 4
0x1800487f6  jz      short loc_180048841
0x1800487f8  cmp     byte ptr [rcx+19h], 5
0x1800487fc  jb      short loc_180048841
0x1800487fe  movzx   r9d, byte ptr [rbp+57h+var_A0+2]
0x180048803  lea     r8, [rbp+57h+var_D0.SenseKeySpecific+1]
0x180048807  xor     eax, eax
0x180048809  mov     [rsp+120h+var_F0], r8
0x18004880e  mov     [rbp+57h+var_BE], eax
0x180048811  and     r9d, 0Fh
0x180048815  mov     [rbp+57h+var_BA], ax
0x180048819  lea     edx, [rax+12h]
0x18004881c  lea     rax, [rbp+57h+var_A0]
0x180048820  mov     word ptr [rbp+57h+var_D0.SenseKeySpecific+1], dx
0x180048824  movzx   edx, byte ptr [rbp+57h+var_A0+0Ch]
0x180048828  mov     [rbp+57h+var_B8], rax
0x18004882c  movzx   eax, byte ptr [rbp+57h+var_A0+0Dh]
0x180048830  mov     rcx, [rcx+10h]
0x180048834  mov     dword ptr [rsp+120h+var_F8], eax
0x180048838  mov     [rsp+120h+var_100], edx
0x18004883c  call    WPP_SF_DDD_HEX_
0x180048841  test    r14, r14
0x180048844  jz      short loc_180048855
0x180048846  lea     rdx, [rbp+57h+var_A0]
0x18004884a  mov     rcx, r15
0x18004884d  mov     rax, r14
0x180048850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048855  xor     ebx, ebx
0x180048857  jmp     loc_1800489A0
0x18004885c  lea     r8, [rbp+57h+var_D0]; struct _SENSE_DATA *
0x180048860  mov     dword ptr [rbp+57h+var_D0.ErrorCode], 80004005h
0x180048867  lea     rdx, [rbp+57h+var_A0]; union _CDB *
0x18004886b  lea     rcx, [rbp+57h+var_88]; this
0x18004886f  call    ?TranslateSenseInfoToHResult@Imapi2Utility@@YA?BEPEBT_CDB@@PEBU_SENSE_DATA@@PEAJ@Z; Imapi2Utility::TranslateSenseInfoToHResult(_CDB const *,_SENSE_DATA const *,long *)
0x180048874  mov     rcx, cs:WPP_GLOBAL_Control
0x18004887b  lea     rax, WPP_GLOBAL_Control
0x180048882  mov     ebx, dword ptr [rbp+57h+var_D0.ErrorCode]
0x180048885  cmp     rcx, rax
0x180048888  jz      loc_1800489A0
0x18004888e  test    byte ptr [rcx+1Ch], 4
0x180048892  jz      short loc_1800488DC
0x180048894  cmp     byte ptr [rcx+19h], 3
0x180048898  jb      short loc_1800488DC
0x18004889a  movzx   r8d, byte ptr [rbp+57h+var_A0+0Ch]
0x18004889f  mov     edx, 34h ; '4'
0x1800488a4  movzx   eax, byte ptr [rbp+57h+var_A0+0Dh]
0x1800488a8  movzx   r9d, byte ptr [rbp+57h+var_A0+2]
0x1800488ad  mov     rcx, [rcx+10h]
0x1800488b1  and     r9d, 0Fh
0x1800488b5  mov     dword ptr [rsp+120h+var_F0], ebx
0x1800488b9  mov     dword ptr [rsp+120h+var_F8], eax
0x1800488bd  mov     [rsp+120h+var_100], r8d
0x1800488c2  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800488c9  call    WPP_SF_DDDd
0x1800488ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800488d5  lea     rax, WPP_GLOBAL_Control
0x1800488dc  cmp     rcx, rax
0x1800488df  jz      loc_1800489A0
0x1800488e5  test    byte ptr [rcx+1Ch], 4
0x1800488e9  jz      loc_1800489A0
0x1800488ef  cmp     byte ptr [rcx+19h], 3
0x1800488f3  jb      loc_1800489A0
0x1800488f9  mov     rcx, [rcx+10h]
0x1800488fd  lea     r9, [rbp+57h+var_B0]
0x180048901  xor     eax, eax
0x180048903  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18004890a  mov     [rbp+57h+var_AE], eax
0x18004890d  mov     [rbp+57h+var_AA], ax
0x180048911  lea     edx, [rax+12h]
0x180048914  mov     [rbp+57h+var_B0], dx
0x180048918  lea     rax, [rbp+57h+var_A0]
0x18004891c  mov     edx, 35h ; '5'
0x180048921  mov     [rbp+57h+var_A8], rax
0x180048925  call    WPP_SF__HEX_
0x18004892a  jmp     short loc_1800489A0
0x18004892c  test    ebx, ebx
0x18004892e  jns     short loc_180048969
0x180048930  mov     rcx, cs:WPP_GLOBAL_Control
0x180048937  lea     rax, WPP_GLOBAL_Control
0x18004893e  cmp     rcx, rax
0x180048941  jz      short loc_1800489A0
0x180048943  test    byte ptr [rcx+1Ch], 4
0x180048947  jz      short loc_1800489A0
0x180048949  cmp     byte ptr [rcx+19h], 3
0x18004894d  jb      short loc_1800489A0
0x18004894f  mov     rcx, [rcx+10h]
0x180048953  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18004895a  mov     edx, 36h ; '6'
0x18004895f  mov     r9d, ebx
0x180048962  call    WPP_SF_d
0x180048967  jmp     short loc_1800489A0
0x180048969  mov     rcx, cs:WPP_GLOBAL_Control
0x180048970  lea     rax, WPP_GLOBAL_Control
0x180048977  cmp     rcx, rax
0x18004897a  jz      short loc_18004899D
0x18004897c  test    byte ptr [rcx+1Ch], 4
0x180048980  jz      short loc_18004899D
0x180048982  cmp     byte ptr [rcx+19h], 5
0x180048986  jb      short loc_18004899D
0x180048988  mov     rcx, [rcx+10h]
0x18004898c  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180048993  mov     edx, 37h ; '7'
0x180048998  call    WPP_SF_
0x18004899d  mov     sil, 1
0x1800489a0  dec     edi
0x1800489a2  test    ebx, ebx
0x1800489a4  jns     loc_18004872E
0x1800489aa  mov     eax, ebx
0x1800489ac  mov     rcx, [rbp+57h+var_40]
0x1800489b0  xor     rcx, rsp; StackCookie
0x1800489b3  call    __security_check_cookie
0x1800489b8  add     rsp, 0F0h
0x1800489bf  pop     r15
0x1800489c1  pop     r14
0x1800489c3  pop     r12
0x1800489c5  pop     rdi
0x1800489c6  pop     rsi
0x1800489c7  pop     rbx
0x1800489c8  pop     rbp
0x1800489c9  retn
```
