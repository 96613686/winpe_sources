# CMsftDiscFormat2Erase::WaitForReadDiscInfoToWorkAfterBlank(ulong)

- ea: `0x1800274f8`
- end: `0x1800276f4`
- name: `?WaitForReadDiscInfoToWorkAfterBlank@CMsftDiscFormat2Erase@@AEAAJK@Z`
- size: `508`
- prototype: `__int64 __fastcall(CMsftDiscFormat2Erase *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x180025dd0`

## callees

- `0x1800140f4`
- `0x180016778`
- `0x1800274f8`
- `0x180027d7c`
- `0x180042430`
- `0x1800437d8`
- `0x180048000`
- `0x1800486e4`
- `0x180049880`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2Erase::WaitForReadDiscInfoToWorkAfterBlank(Imapi2Utility **this, unsigned int a2)
{
  int DiscInfo; // ebx
  PVOID *v4; // rcx
  unsigned int v6[2]; // [rsp+40h] [rbp-39h] BYREF
  _DWORD *v7; // [rsp+48h] [rbp-31h]
  __int64 v8; // [rsp+50h] [rbp-29h]
  int v9; // [rsp+58h] [rbp-21h]
  int v10; // [rsp+5Ch] [rbp-1Dh]
  _DWORD v11[2]; // [rsp+60h] [rbp-19h] BYREF
  unsigned int v12; // [rsp+68h] [rbp-11h]

  Imapi2Utility::CTaskTimeEstimator::CTaskTimeEstimator((Imapi2Utility::CTaskTimeEstimator *)v11, a2, 0x10000u);
  v8 = 0;
  v7 = v11;
  v9 = 0;
  *(_QWORD *)v6 = this;
  v10 = 1;
  Imapi2Utility::CTaskTimeEstimator::StartNow((Imapi2Utility::CTaskTimeEstimator *)v11);
  DiscInfo = Imapi2Utility::WaitForReadDiscInfo(
               this[21],
               (struct IDiscRecorder2Ex *)0xE10,
               (__int64)v6,
               (void (__fastcall *)(__int64, union _CDB *))CMsftDiscFormat2Erase::EraseUpdateCallBack);
  Imapi2Utility::CTaskTimeEstimator::EndNow((Imapi2Utility::CTaskTimeEstimator *)v11);
  if ( DiscInfo >= 0 )
  {
    if ( v12 > v11[0] )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 4u )
      {
        WPP_SF_dddd(*((_QWORD *)WPP_GLOBAL_Control + 32), 45, v12 / 0x3E8, v12, v12 / 0x3E8, v11[0], v11[0] / 0x3E8u);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 4u )
    {
      WPP_SF_dddd(*((_QWORD *)WPP_GLOBAL_Control + 32), 44, v12 / 0x3E8, v12, v12 / 0x3E8, v11[0], v11[0] / 0x3E8u);
    }
  }
  else
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 32),
        42,
        &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids,
        (unsigned int)DiscInfo);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11[1] >= 0x36EE80u )
    {
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 268) & 4) != 0 && *((_BYTE *)v4 + 265) >= 3u )
        WPP_SF_(v4[32], 43, &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids);
      return (unsigned int)-2136340218;
    }
  }
  return (unsigned int)DiscInfo;
}

```

## disassembly

```asm
0x1800274f8  push    rbp
0x1800274fa  push    rbx
0x1800274fb  push    rsi
0x1800274fc  push    rdi
0x1800274fd  lea     rbp, [rsp-3Fh]
0x180027502  sub     rsp, 0B8h
0x180027509  mov     rax, cs:__security_cookie
0x180027510  xor     rax, rsp
0x180027513  mov     [rbp+57h+var_30], rax
0x180027517  mov     rbx, rcx
0x18002751a  mov     r8d, 10000h; unsigned int
0x180027520  lea     rcx, [rbp+57h+var_70]; this
0x180027524  call    ??0CTaskTimeEstimator@Imapi2Utility@@QEAA@KK@Z; Imapi2Utility::CTaskTimeEstimator::CTaskTimeEstimator(ulong,ulong)
0x180027529  lea     rax, [rbp+57h+var_70]
0x18002752d  mov     [rbp+57h+var_80], 0
0x180027535  lea     rcx, [rbp+57h+var_70]; this
0x180027539  mov     [rbp+57h+var_88], rax
0x18002753d  mov     [rbp+57h+var_78], 0
0x180027544  mov     qword ptr [rbp+57h+var_90], rbx
0x180027548  mov     [rbp+57h+var_74], 1
0x18002754f  call    ?StartNow@CTaskTimeEstimator@Imapi2Utility@@QEAAXXZ; Imapi2Utility::CTaskTimeEstimator::StartNow(void)
0x180027554  mov     rcx, [rbx+0A8h]; this
0x18002755b  lea     r9, ?EraseUpdateCallBack@CMsftDiscFormat2Erase@@CAXPEAXPEAU_SENSE_DATA@@@Z; void *
0x180027562  lea     r8, [rbp+57h+var_90]; unsigned int
0x180027566  mov     edx, 0E10h; struct IDiscRecorder2Ex *
0x18002756b  call    ?WaitForReadDiscInfo@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@KPEAXP6AX1PEAU_SENSE_DATA@@@Z@Z; Imapi2Utility::WaitForReadDiscInfo(IDiscRecorder2Ex *,ulong,void *,void (*)(void *,_SENSE_DATA *))
0x180027570  lea     rcx, [rbp+57h+var_70]; this
0x180027574  mov     ebx, eax
0x180027576  call    ?EndNow@CTaskTimeEstimator@Imapi2Utility@@QEAAXXZ; Imapi2Utility::CTaskTimeEstimator::EndNow(void)
0x18002757b  test    ebx, ebx
0x18002757d  jns     loc_180027610
0x180027583  mov     rcx, cs:WPP_GLOBAL_Control
0x18002758a  lea     rdi, WPP_GLOBAL_Control
0x180027591  cmp     rcx, rdi
0x180027594  jz      short loc_1800275CA
0x180027596  test    byte ptr [rcx+10Ch], 4
0x18002759d  jz      short loc_1800275CA
0x18002759f  cmp     byte ptr [rcx+109h], 3
0x1800275a6  jb      short loc_1800275CA
0x1800275a8  mov     rcx, [rcx+100h]
0x1800275af  lea     r8, WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids
0x1800275b6  mov     edx, 2Ah ; '*'
0x1800275bb  mov     r9d, ebx
0x1800275be  call    WPP_SF_d
0x1800275c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275ca  cmp     [rbp+57h+var_6C], 36EE80h
0x1800275d1  jb      loc_1800276DA
0x1800275d7  cmp     rcx, rdi
0x1800275da  jz      short loc_180027606
0x1800275dc  test    byte ptr [rcx+10Ch], 4
0x1800275e3  jz      short loc_180027606
0x1800275e5  cmp     byte ptr [rcx+109h], 3
0x1800275ec  jb      short loc_180027606
0x1800275ee  mov     rcx, [rcx+100h]
0x1800275f5  lea     r8, WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids
0x1800275fc  mov     edx, 2Bh ; '+'
0x180027601  call    WPP_SF_
0x180027606  mov     ebx, 80AA0906h
0x18002760b  jmp     loc_1800276DA
0x180027610  mov     r11d, [rbp+57h+var_68]
0x180027614  mov     esi, [rbp+57h+var_70]
0x180027617  cmp     r11d, esi
0x18002761a  ja      short loc_180027674
0x18002761c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027623  lea     rdi, WPP_GLOBAL_Control
0x18002762a  cmp     rcx, rdi
0x18002762d  jz      loc_1800276DA
0x180027633  test    byte ptr [rcx+10Ch], 4
0x18002763a  jz      loc_1800276DA
0x180027640  cmp     byte ptr [rcx+109h], 4
0x180027647  jb      loc_1800276DA
0x18002764d  mov     r8d, 10624DD3h
0x180027653  mov     eax, r8d
0x180027656  mul     esi
0x180027658  mov     eax, r8d
0x18002765b  mov     r10d, edx
0x18002765e  shr     r10d, 6
0x180027662  mul     r11d
0x180027665  mov     [rsp+0D0h+var_A0], r10d
0x18002766a  mov     r8d, edx
0x18002766d  mov     edx, 2Ch ; ','
0x180027672  jmp     short loc_1800276BE
0x180027674  mov     rcx, cs:WPP_GLOBAL_Control
0x18002767b  lea     rdi, WPP_GLOBAL_Control
0x180027682  cmp     rcx, rdi
0x180027685  jz      short loc_1800276DA
0x180027687  test    byte ptr [rcx+10Ch], 4
0x18002768e  jz      short loc_1800276DA
0x180027690  cmp     byte ptr [rcx+109h], 4
0x180027697  jb      short loc_1800276DA
0x180027699  mov     r8d, 10624DD3h
0x18002769f  mov     eax, r8d
0x1800276a2  mul     esi
0x1800276a4  mov     eax, r8d
0x1800276a7  mov     r9d, edx
0x1800276aa  shr     r9d, 6
0x1800276ae  mul     r11d
0x1800276b1  mov     [rsp+0D0h+var_A0], r9d
0x1800276b6  mov     r8d, edx
0x1800276b9  mov     edx, 2Dh ; '-'
0x1800276be  mov     rcx, [rcx+100h]
0x1800276c5  mov     r9d, r11d
0x1800276c8  shr     r8d, 6
0x1800276cc  mov     [rsp+0D0h+var_A8], esi
0x1800276d0  mov     [rsp+0D0h+var_B0], r8d
0x1800276d5  call    WPP_SF_dddd
0x1800276da  mov     eax, ebx
0x1800276dc  mov     rcx, [rbp+57h+var_30]
0x1800276e0  xor     rcx, rsp; StackCookie
0x1800276e3  call    __security_check_cookie
0x1800276e8  add     rsp, 0B8h
0x1800276ef  pop     rdi
0x1800276f0  pop     rsi
0x1800276f1  pop     rbx
0x1800276f2  pop     rbp
0x1800276f3  retn
```
