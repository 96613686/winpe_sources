# SleepStudyReportData::WriteTopOffendersEvent(ulong,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const *)

- ea: `0x180012f80`
- end: `0x1800130e7`
- name: `?WriteTopOffendersEvent@SleepStudyReportData@@QEBAXKKPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180012064`

## callees

- `0x180012f80`
- `0x18001469c`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800130ca`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x1800130ca`

## pseudocode

```c
ULONG __fastcall SleepStudyReportData::WriteTopOffendersEvent(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v6; // r10
  __int64 v7; // r11
  unsigned int v9; // r8d
  int BlockerSize; // eax
  _QWORD *v11; // r9
  __int64 v12; // rax
  __int64 v13; // r8
  unsigned int v14; // r8d
  ULONG v15; // r9d
  _QWORD *v16; // r11
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r8
  unsigned int v20; // r8d
  ULONG v21; // r9d
  _QWORD *v22; // r10
  __int64 v23; // rax
  REGHANDLE v24; // rcx
  __int64 v25; // rax
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-59h] BYREF
  int *v28; // [rsp+30h] [rbp-49h]
  __int64 v29; // [rsp+38h] [rbp-41h]
  _QWORD *v30; // [rsp+40h] [rbp-39h]
  int v31; // [rsp+48h] [rbp-31h]
  int v32; // [rsp+4Ch] [rbp-2Dh]
  int v33; // [rsp+D8h] [rbp+5Fh] BYREF
  int v34; // [rsp+E0h] [rbp+67h] BYREF

  v34 = a3;
  v33 = a2;
  v6 = a6;
  v7 = a5;
  UserData.Ptr = (ULONGLONG)&v33;
  v28 = &v34;
  v9 = 2;
  *(_QWORD *)&UserData.Size = 4;
  v29 = 4;
  if ( a4 )
  {
    BlockerSize = SleepStudyReportData::GetBlockerSize(a4, a2, 2);
    if ( v11[3] > 7u )
      v11 = (_QWORD *)*v11;
    v30 = v11;
    v9 = 3;
    v31 = BlockerSize;
    v32 = 0;
  }
  v12 = 2LL * v9;
  v13 = v9 + 1;
  *(&UserData.Ptr + v12) = (ULONGLONG)&qword_18009A568;
  *((_QWORD *)&UserData.Size + v12) = 2;
  if ( v7 )
  {
    v15 = SleepStudyReportData::GetBlockerSize(v7, a2, v13);
    if ( v16[3] > 7u )
      v16 = (_QWORD *)*v16;
    v17 = 2LL * v14;
    LODWORD(v13) = v14 + 1;
    *(&UserData.Ptr + v17) = (ULONGLONG)v16;
    *(&UserData.Size + 2 * v17) = v15;
    *(&UserData.Reserved + 2 * v17) = 0;
  }
  v18 = (unsigned int)v13;
  v19 = (unsigned int)(v13 + 1);
  v18 *= 2;
  *(&UserData.Ptr + v18) = (ULONGLONG)&qword_18009A568;
  *((_QWORD *)&UserData.Size + v18) = 2;
  if ( v6 )
  {
    v21 = SleepStudyReportData::GetBlockerSize(v6, a2, v19);
    if ( v22[3] > 7u )
      v22 = (_QWORD *)*v22;
    v23 = 2LL * v20;
    LODWORD(v19) = v20 + 1;
    *(&UserData.Ptr + v23) = (ULONGLONG)v22;
    *(&UserData.Size + 2 * v23) = v21;
    *(&UserData.Reserved + 2 * v23) = 0;
  }
  v24 = *(_QWORD *)(a1 + 400);
  v25 = 2LL * (unsigned int)v19;
  *(&UserData.Ptr + v25) = (ULONGLONG)&qword_18009A568;
  *((_QWORD *)&UserData.Size + v25) = 2;
  return EventWrite(v24, &SLEEPSTUDY_EVT_TOP_OFFENDERS_PERFTRACK, v19 + 1, &UserData);
}

```

## disassembly

```asm
0x180012f80  mov     [rsp-8+arg_10], r8d
0x180012f85  mov     [rsp-8+arg_8], edx
0x180012f89  push    rbp
0x180012f8a  push    rbx
0x180012f8b  push    rsi
0x180012f8c  lea     rbp, [rsp-37h]
0x180012f91  sub     rsp, 0B0h
0x180012f98  mov     rax, cs:__security_cookie
0x180012f9f  xor     rax, rsp
0x180012fa2  mov     [rbp+47h+var_20], rax
0x180012fa6  mov     r10, [rbp+47h+arg_28]
0x180012faa  lea     rax, [rbp+47h+arg_8]
0x180012fae  mov     r11, [rbp+47h+arg_20]
0x180012fb2  mov     rbx, rcx
0x180012fb5  mov     [rbp+47h+UserData.Ptr], rax
0x180012fb9  lea     rax, [rbp+47h+arg_10]
0x180012fbd  mov     [rbp+47h+var_90], rax
0x180012fc1  mov     r8d, 2
0x180012fc7  mov     qword ptr [rbp+47h+UserData.Size], 4
0x180012fcf  mov     [rbp+47h+var_88], 4
0x180012fd7  test    r9, r9
0x180012fda  jz      short loc_180013002
0x180012fdc  mov     rcx, r9
0x180012fdf  call    ?GetBlockerSize@SleepStudyReportData@@SAKPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SleepStudyReportData::GetBlockerSize(std::wstring const *)
0x180012fe4  cmp     qword ptr [r9+18h], 7
0x180012fe9  jbe     short loc_180012FEE
0x180012feb  mov     r9, [r9]
0x180012fee  mov     [rbp+47h+var_80], r9
0x180012ff2  mov     r8d, 3
0x180012ff8  mov     [rbp+47h+var_78], eax
0x180012ffb  mov     [rbp+47h+var_74], 0
0x180013002  mov     eax, r8d
0x180013005  lea     rsi, qword_18009A568
0x18001300c  add     rax, rax
0x18001300f  inc     r8d
0x180013012  mov     [rbp+rax*8+47h+UserData.Ptr], rsi
0x180013017  mov     qword ptr [rbp+rax*8+47h+UserData.Size], 2
0x180013020  test    r11, r11
0x180013023  jz      short loc_180013055
0x180013025  mov     rcx, r11
0x180013028  call    ?GetBlockerSize@SleepStudyReportData@@SAKPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SleepStudyReportData::GetBlockerSize(std::wstring const *)
0x18001302d  cmp     qword ptr [r11+18h], 7
0x180013032  mov     r9d, eax
0x180013035  jbe     short loc_18001303A
0x180013037  mov     r11, [r11]
0x18001303a  mov     eax, r8d
0x18001303d  add     rax, rax
0x180013040  inc     r8d
0x180013043  mov     [rbp+rax*8+47h+UserData.Ptr], r11
0x180013048  mov     [rbp+rax*8+47h+UserData.Size], r9d
0x18001304d  mov     dword ptr [rbp+rax*8+47h+UserData.0Ch], 0
0x180013055  mov     eax, r8d
0x180013058  inc     r8d
0x18001305b  add     rax, rax
0x18001305e  mov     [rbp+rax*8+47h+UserData.Ptr], rsi
0x180013063  mov     qword ptr [rbp+rax*8+47h+UserData.Size], 2
0x18001306c  test    r10, r10
0x18001306f  jz      short loc_1800130A1
0x180013071  mov     rcx, r10
0x180013074  call    ?GetBlockerSize@SleepStudyReportData@@SAKPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SleepStudyReportData::GetBlockerSize(std::wstring const *)
0x180013079  cmp     qword ptr [r10+18h], 7
0x18001307e  mov     r9d, eax
0x180013081  jbe     short loc_180013086
0x180013083  mov     r10, [r10]
0x180013086  mov     eax, r8d
0x180013089  add     rax, rax
0x18001308c  inc     r8d
0x18001308f  mov     [rbp+rax*8+47h+UserData.Ptr], r10
0x180013094  mov     [rbp+rax*8+47h+UserData.Size], r9d
0x180013099  mov     dword ptr [rbp+rax*8+47h+UserData.0Ch], 0
0x1800130a1  mov     rcx, [rbx+190h]; RegHandle
0x1800130a8  lea     r9, [rbp+47h+UserData]; UserData
0x1800130ac  mov     eax, r8d
0x1800130af  lea     rdx, SLEEPSTUDY_EVT_TOP_OFFENDERS_PERFTRACK; EventDescriptor
0x1800130b6  add     rax, rax
0x1800130b9  inc     r8d; UserDataCount
0x1800130bc  mov     [rbp+rax*8+47h+UserData.Ptr], rsi
0x1800130c1  mov     qword ptr [rbp+rax*8+47h+UserData.Size], 2
0x1800130ca  call    cs:__imp_EventWrite
0x1800130d0  mov     rcx, [rbp+47h+var_20]
0x1800130d4  xor     rcx, rsp; StackCookie
0x1800130d7  call    __security_check_cookie
0x1800130dc  add     rsp, 0B0h
0x1800130e3  pop     rsi
0x1800130e4  pop     rbx
0x1800130e5  pop     rbp
0x1800130e6  retn
```
