# EaiSetAggregateConditionsEnabledState

- ea: `0x1800062e0`
- end: `0x18000649c`
- name: `EaiSetAggregateConditionsEnabledState`
- size: `444`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001460`
- `0x180005940`

## callees

- `0x180001970`
- `0x1800062e0`
- `0x1800072e0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000646d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000646d`

## pseudocode

```c
__int64 __fastcall EaiSetAggregateConditionsEnabledState(__int64 a1, unsigned __int8 a2)
{
  int v2; // esi
  __int64 v3; // rdx
  __int64 v6; // rdx
  int v7; // edi
  __int64 v8; // rdx
  int v9; // eax
  int v10; // [rsp+30h] [rbp-89h] BYREF
  int v11; // [rsp+34h] [rbp-85h] BYREF
  _DWORD v12[2]; // [rsp+38h] [rbp-81h] BYREF
  __int128 v13; // [rsp+40h] [rbp-79h] BYREF
  __int64 v14; // [rsp+50h] [rbp-69h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-61h] BYREF
  _QWORD v16[5]; // [rsp+68h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-29h] BYREF
  char *v18; // [rsp+A0h] [rbp-19h]
  int v19; // [rsp+A8h] [rbp-11h]
  int v20; // [rsp+ACh] [rbp-Dh]
  __int64 *v21; // [rsp+B0h] [rbp-9h]
  __int64 v22; // [rsp+B8h] [rbp-1h]
  int *v23; // [rsp+C0h] [rbp+7h]
  __int64 v24; // [rsp+C8h] [rbp+Fh]
  int *v25; // [rsp+D0h] [rbp+17h]
  __int64 v26; // [rsp+D8h] [rbp+1Fh]
  _DWORD *v27; // [rsp+E0h] [rbp+27h]
  __int64 v28; // [rsp+E8h] [rbp+2Fh]

  v2 = a2;
  v3 = *(_QWORD *)(a1 + 56);
  v13 = 0;
  if ( !*(_QWORD *)(v3 + 8) )
    return 0;
  *(_QWORD *)&v13 = a1;
  v16[0] = &v13;
  BYTE8(v13) = v2;
  v6 = *(_QWORD *)(v3 + 8);
  v16[1] = EaiAggregationConditionNextChild;
  v16[4] = EaiSetConditionsEnabledStateVisitNode;
  v16[2] = 0;
  v16[3] = 0;
  v7 = EapTreeTraverse(v16, v6);
  if ( v7 < 0 )
  {
    v8 = *(_QWORD *)(a1 + 56);
    BYTE8(v13) = (_BYTE)v2 == 0;
    v9 = EapTreeTraverse(v16, *(_QWORD *)(v8 + 8));
    if ( (unsigned int)dword_180012000 > 2 )
    {
      v12[0] = v9;
      v21 = &v14;
      v27 = v12;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_180012008;
      v23 = &v10;
      v25 = &v11;
      v14 = a1;
      v22 = 8;
      v10 = v2;
      v24 = 4;
      v11 = v7;
      v26 = 4;
      v28 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_180012008;
      v18 = &byte_18000F2D7;
      UserData.Reserved = 2;
      v19 = 83;
      v20 = 1;
      v12[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800062e0  push    rbp
0x1800062e2  push    rbx
0x1800062e3  push    rsi
0x1800062e4  lea     rbp, [rsp-47h]
0x1800062e9  sub     rsp, 100h
0x1800062f0  mov     rax, cs:__security_cookie
0x1800062f7  xor     rax, rsp
0x1800062fa  mov     [rbp+57h+var_20], rax
0x1800062fe  movzx   esi, dl
0x180006301  xorps   xmm0, xmm0
0x180006304  mov     rdx, [rcx+38h]
0x180006308  mov     rbx, rcx
0x18000630b  movups  [rbp+57h+var_D0], xmm0
0x18000630f  cmp     qword ptr [rdx+8], 0
0x180006314  jnz     short loc_18000631D
0x180006316  xor     eax, eax
0x180006318  jmp     loc_180006485
0x18000631d  lea     rax, [rbp+57h+var_D0]
0x180006321  mov     qword ptr [rbp+57h+var_D0], rbx
0x180006325  mov     [rbp+57h+var_A8], rax
0x180006329  lea     rcx, [rbp+57h+var_A8]
0x18000632d  lea     rax, EaiAggregationConditionNextChild
0x180006334  mov     byte ptr [rbp+57h+var_D0+8], sil
0x180006338  mov     rdx, [rdx+8]
0x18000633c  mov     [rbp+57h+var_A0], rax
0x180006340  lea     rax, EaiSetConditionsEnabledStateVisitNode
0x180006347  mov     [rsp+110h+arg_10], rdi
0x18000634f  mov     [rsp+110h+arg_18], r14
0x180006357  xor     r14d, r14d
0x18000635a  mov     [rbp+57h+var_88], rax
0x18000635e  mov     [rbp+57h+var_98], r14
0x180006362  mov     [rbp+57h+var_90], r14
0x180006366  call    EapTreeTraverse
0x18000636b  mov     edi, eax
0x18000636d  test    eax, eax
0x18000636f  jns     loc_180006473
0x180006375  mov     rdx, [rbx+38h]
0x180006379  lea     rcx, [rbp+57h+var_A8]
0x18000637d  test    sil, sil
0x180006380  setz    byte ptr [rbp+57h+var_D0+8]
0x180006384  mov     rdx, [rdx+8]
0x180006388  call    EapTreeTraverse
0x18000638d  mov     ecx, cs:dword_180012000
0x180006393  cmp     ecx, 2
0x180006396  jbe     loc_180006473
0x18000639c  mov     [rsp+110h+var_D8], eax
0x1800063a0  lea     rcx, [rbp+57h+var_C0]
0x1800063a4  mov     [rbp+57h+var_60], rcx
0x1800063a8  lea     rax, [rsp+110h+var_D8]
0x1800063ad  mov     [rbp+57h+var_30], rax
0x1800063b1  lea     rcx, [rsp+110h+var_E0]
0x1800063b6  movzx   eax, cs:word_18000F2CD
0x1800063bd  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1800063c1  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800063c4  xor     r9d, r9d; RelatedActivityId
0x1800063c7  mov     rax, cs:off_180012008
0x1800063ce  xor     r8d, r8d; ActivityId
0x1800063d1  mov     [rbp+57h+var_80.Ptr], rax
0x1800063d5  mov     [rbp+57h+var_50], rcx
0x1800063d9  lea     rcx, [rsp+110h+var_DC]
0x1800063de  mov     [rbp+57h+var_40], rcx
0x1800063e2  lea     rcx, _TraceLoggingMetadata
0x1800063e9  mov     [rbp+57h+var_C0], rbx
0x1800063ed  mov     [rbp+57h+var_58], 8
0x1800063f5  mov     [rsp+110h+var_E0], esi
0x1800063f9  mov     [rbp+57h+var_48], 4
0x180006401  mov     [rsp+110h+var_DC], edi
0x180006405  mov     [rbp+57h+var_38], 4
0x18000640d  mov     [rbp+57h+var_28], 4
0x180006415  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000641c  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x180006420  movzx   eax, word ptr [rax]
0x180006423  mov     [rbp+57h+var_80.Size], eax
0x180006426  lea     rax, byte_18000F2D7
0x18000642d  mov     [rbp+57h+var_70], rax
0x180006431  lea     rax, _TraceLoggingMetadataEnd
0x180006438  sub     eax, ecx
0x18000643a  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x180006441  mov     [rbp+57h+var_68], 53h ; 'S'
0x180006448  mov     [rbp+57h+var_64], 1
0x18000644f  mov     [rbp+57h+var_D4], eax
0x180006452  mov     eax, [rbp+57h+var_D4]
0x180006455  mov     rcx, cs:RegHandle; RegHandle
0x18000645c  lea     rax, [rbp+57h+var_80]
0x180006460  mov     [rsp+110h+UserData], rax; UserData
0x180006465  mov     [rsp+110h+UserDataCount], 6; UserDataCount
0x18000646d  call    cs:__imp_EventWriteTransfer
0x180006473  mov     r14, [rsp+110h+arg_18]
0x18000647b  mov     eax, edi
0x18000647d  mov     rdi, [rsp+110h+arg_10]
0x180006485  mov     rcx, [rbp+57h+var_20]
0x180006489  xor     rcx, rsp; StackCookie
0x18000648c  call    __security_check_cookie
0x180006491  add     rsp, 100h
0x180006498  pop     rsi
0x180006499  pop     rbx
0x18000649a  pop     rbp
0x18000649b  retn
```
