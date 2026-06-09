# CMsftDiscFormat2Erase::EraseUpdateCallBack(void *,_SENSE_DATA *)

- ea: `0x1800263d0`
- end: `0x18002662f`
- name: `?EraseUpdateCallBack@CMsftDiscFormat2Erase@@CAXPEAXPEAU_SENSE_DATA@@@Z`
- size: `607`
- prototype: `void __fastcall(void *, struct _SENSE_DATA *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800140f4`
- `0x180014134`
- `0x180016778`
- `0x1800236b4`
- `0x1800263d0`
- `0x180026b20`
- `0x180048d4c`

## pseudocode

```c
void __fastcall CMsftDiscFormat2Erase::EraseUpdateCallBack(void *a1, struct _SENSE_DATA *a2)
{
  unsigned int v2; // edi
  unsigned int v4; // eax
  __int64 v5; // r9
  PVOID *v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // edi
  unsigned int *v9; // rax
  unsigned int v10; // r10d
  __int64 v11; // r9

  v2 = 0;
  if ( (a2->SenseKeySpecific[0] & 0x80u) != 0 )
    v2 = a2->SenseKeySpecific[2] | (a2->SenseKeySpecific[1] << 8);
  if ( !*((_BYTE *)a1 + 20) && v2 < *((_DWORD *)a1 + 4) )
  {
    if ( v2 <= 0x7000 )
    {
      if ( v2 )
      {
        ++*((_DWORD *)a1 + 6);
        v4 = *((_DWORD *)a1 + 7);
        if ( *((_DWORD *)a1 + 6) < v4 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 4u )
          {
            WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 32), 50, &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids);
          }
        }
        else
        {
          v5 = v4 + 1;
          *((_DWORD *)a1 + 7) = v5;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 49, &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids, v5);
          }
        }
        *((_DWORD *)a1 + 4) = 0;
      }
      else
      {
        v2 = 0xFFFF;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 48, &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids);
      }
      *((_BYTE *)a1 + 20) = 1;
      *((_DWORD *)a1 + 4) = 0xFFFF - *((_DWORD *)a1 + 4);
    }
  }
  if ( *((_BYTE *)a1 + 20) )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 51, &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids, v2);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v2 = 0xFFFF - v2;
  }
  else
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = v2 * (*((_DWORD *)a1 + 6) + 1) / *((_DWORD *)a1 + 7);
  v8 = v7;
  if ( v7 && v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 268) & 4) != 0 && *((_BYTE *)v6 + 265) >= 5u )
    WPP_SF_d(v6[32], 52, &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids, v7);
  Imapi2Utility::CTaskTimeEstimator::put_CompletedSteps(*((Imapi2Utility::CTaskTimeEstimator **)a1 + 1), v8);
  v9 = (unsigned int *)*((_QWORD *)a1 + 1);
  v10 = v9[2];
  if ( v10 > 0x2710 )
  {
    v11 = *v9;
    if ( v10 - 10000 > (unsigned int)v11
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 265) >= 3u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 32), 53, &WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids, v11, v10);
    }
  }
  CProxy_DDiscFormat2EraseEvents<CMsftDiscFormat2Erase>::Fire_Update(
    *(_QWORD *)a1 + 24LL,
    *(_DWORD *)(*((_QWORD *)a1 + 1) + 8LL) / 0x3E8u,
    *(_DWORD *)(*((_QWORD *)a1 + 1) + 4LL) / 0x3E8u);
}

```

## disassembly

```asm
0x1800263d0  push    rbx
0x1800263d2  push    rsi
0x1800263d3  push    rdi
0x1800263d4  push    r12
0x1800263d6  push    r15
0x1800263d8  sub     rsp, 40h
0x1800263dc  xor     edi, edi
0x1800263de  mov     rbx, rcx
0x1800263e1  cmp     [rdx+0Fh], dil
0x1800263e5  jge     short loc_1800263F4
0x1800263e7  movzx   edi, byte ptr [rdx+10h]
0x1800263eb  movzx   eax, byte ptr [rdx+11h]
0x1800263ef  shl     edi, 8
0x1800263f2  or      edi, eax
0x1800263f4  cmp     byte ptr [rcx+14h], 0
0x1800263f8  lea     r15, WPP_GLOBAL_Control
0x1800263ff  mov     esi, 0FFFFh
0x180026404  lea     r12, WPP_8ddcedaf23bb30f41053135f0cc3ba6f_Traceguids
0x18002640b  jnz     loc_180026506
0x180026411  mov     r8d, [rcx+10h]
0x180026415  cmp     edi, r8d
0x180026418  jnb     loc_180026506
0x18002641e  cmp     edi, 7000h
0x180026424  jbe     short loc_180026469
0x180026426  mov     rcx, cs:WPP_GLOBAL_Control
0x18002642d  cmp     rcx, r15
0x180026430  jz      short loc_180026458
0x180026432  test    byte ptr [rcx+10Ch], 4
0x180026439  jz      short loc_180026458
0x18002643b  cmp     byte ptr [rcx+109h], 3
0x180026442  jb      short loc_180026458
0x180026444  mov     rcx, [rcx+100h]
0x18002644b  mov     edx, 30h ; '0'
0x180026450  mov     r8, r12
0x180026453  call    WPP_SF_
0x180026458  mov     eax, esi
0x18002645a  mov     byte ptr [rbx+14h], 1
0x18002645e  sub     eax, [rbx+10h]
0x180026461  mov     [rbx+10h], eax
0x180026464  jmp     loc_180026506
0x180026469  test    edi, edi
0x18002646b  jz      loc_180026504
0x180026471  inc     dword ptr [rcx+18h]
0x180026474  mov     r9d, [rcx+18h]
0x180026478  mov     eax, [rcx+1Ch]
0x18002647b  cmp     r9d, eax
0x18002647e  jb      short loc_1800264BC
0x180026480  lea     r9d, [rax+1]
0x180026484  mov     [rcx+1Ch], r9d
0x180026488  mov     rcx, cs:WPP_GLOBAL_Control
0x18002648f  cmp     rcx, r15
0x180026492  jz      short loc_1800264FB
0x180026494  test    byte ptr [rcx+10Ch], 4
0x18002649b  jz      short loc_1800264FB
0x18002649d  cmp     byte ptr [rcx+109h], 3
0x1800264a4  jb      short loc_1800264FB
0x1800264a6  mov     rcx, [rcx+100h]
0x1800264ad  mov     edx, 31h ; '1'
0x1800264b2  mov     r8, r12
0x1800264b5  call    WPP_SF_d
0x1800264ba  jmp     short loc_1800264FB
0x1800264bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800264c3  cmp     rcx, r15
0x1800264c6  jz      short loc_1800264FB
0x1800264c8  test    byte ptr [rcx+10Ch], 4
0x1800264cf  jz      short loc_1800264FB
0x1800264d1  cmp     byte ptr [rcx+109h], 4
0x1800264d8  jb      short loc_1800264FB
0x1800264da  mov     rcx, [rcx+100h]
0x1800264e1  mov     edx, 32h ; '2'
0x1800264e6  mov     [rsp+68h+var_38], r8d
0x1800264eb  mov     r8, r12
0x1800264ee  mov     [rsp+68h+var_40], edi
0x1800264f2  mov     [rsp+68h+var_48], eax
0x1800264f6  call    WPP_SF_DDDd
0x1800264fb  mov     dword ptr [rbx+10h], 0
0x180026502  jmp     short loc_180026506
0x180026504  mov     edi, esi
0x180026506  cmp     byte ptr [rbx+14h], 0
0x18002650a  jz      short loc_18002654E
0x18002650c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026513  cmp     rcx, r15
0x180026516  jz      short loc_180026548
0x180026518  test    byte ptr [rcx+10Ch], 4
0x18002651f  jz      short loc_180026548
0x180026521  cmp     byte ptr [rcx+109h], 5
0x180026528  jb      short loc_180026548
0x18002652a  mov     rcx, [rcx+100h]
0x180026531  mov     edx, 33h ; '3'
0x180026536  mov     r9d, edi
0x180026539  mov     r8, r12
0x18002653c  call    WPP_SF_d
0x180026541  mov     rcx, cs:WPP_GLOBAL_Control
0x180026548  sub     esi, edi
0x18002654a  mov     edi, esi
0x18002654c  jmp     short loc_180026555
0x18002654e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026555  mov     eax, [rbx+18h]
0x180026558  xor     edx, edx
0x18002655a  inc     eax
0x18002655c  imul    eax, edi
0x18002655f  div     dword ptr [rbx+1Ch]
0x180026562  mov     edi, eax
0x180026564  test    eax, eax
0x180026566  jz      short loc_180026596
0x180026568  cmp     rcx, r15
0x18002656b  jz      short loc_180026596
0x18002656d  test    byte ptr [rcx+10Ch], 4
0x180026574  jz      short loc_180026596
0x180026576  cmp     byte ptr [rcx+109h], 5
0x18002657d  jb      short loc_180026596
0x18002657f  mov     rcx, [rcx+100h]
0x180026586  mov     edx, 34h ; '4'
0x18002658b  mov     r9d, eax
0x18002658e  mov     r8, r12
0x180026591  call    WPP_SF_d
0x180026596  mov     rcx, [rbx+8]; this
0x18002659a  mov     edx, edi; unsigned int
0x18002659c  call    ?put_CompletedSteps@CTaskTimeEstimator@Imapi2Utility@@QEAAXK@Z; Imapi2Utility::CTaskTimeEstimator::put_CompletedSteps(ulong)
0x1800265a1  mov     rax, [rbx+8]
0x1800265a5  mov     r10d, [rax+8]
0x1800265a9  cmp     r10d, 2710h
0x1800265b0  jbe     short loc_1800265F8
0x1800265b2  mov     r9d, [rax]
0x1800265b5  lea     eax, [r10-2710h]
0x1800265bc  cmp     eax, r9d
0x1800265bf  jbe     short loc_1800265F8
0x1800265c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800265c8  cmp     rcx, r15
0x1800265cb  jz      short loc_1800265F8
0x1800265cd  test    byte ptr [rcx+10Ch], 4
0x1800265d4  jz      short loc_1800265F8
0x1800265d6  cmp     byte ptr [rcx+109h], 3
0x1800265dd  jb      short loc_1800265F8
0x1800265df  mov     rcx, [rcx+100h]
0x1800265e6  mov     edx, 35h ; '5'
0x1800265eb  mov     r8, r12
0x1800265ee  mov     [rsp+68h+var_48], r10d
0x1800265f3  call    WPP_SF_Dd
0x1800265f8  mov     rcx, [rbx+8]
0x1800265fc  mov     r9d, 10624DD3h
0x180026602  mov     eax, r9d
0x180026605  mul     dword ptr [rcx+4]
0x180026608  mov     eax, r9d
0x18002660b  mov     r8d, edx
0x18002660e  mul     dword ptr [rcx+8]
0x180026611  mov     rcx, [rbx]
0x180026614  shr     edx, 6
0x180026617  add     rcx, 18h
0x18002661b  shr     r8d, 6
0x18002661f  add     rsp, 40h
0x180026623  pop     r15
0x180026625  pop     r12
0x180026627  pop     rdi
0x180026628  pop     rsi
0x180026629  pop     rbx
0x18002662a  jmp     ?Fire_Update@?$CProxy_DDiscFormat2EraseEvents@VCMsftDiscFormat2Erase@@@@QEAAXJJ@Z; CProxy_DDiscFormat2EraseEvents<CMsftDiscFormat2Erase>::Fire_Update(long,long)
```
