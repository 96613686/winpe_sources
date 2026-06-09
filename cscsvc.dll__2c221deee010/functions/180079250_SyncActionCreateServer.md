# SyncActionCreateServer

- ea: `0x180079250`
- end: `0x1800798d9`
- name: `SyncActionCreateServer`
- size: `1673`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, installer_update`

## callees

- `0x180001ad0`
- `0x1800030f0`
- `0x1800032cc`
- `0x1800223c0`
- `0x18002a524`
- `0x18002d8ec`
- `0x18002e1dc`
- `0x1800360c0`
- `0x180036394`
- `0x18003c560`
- `0x18003e928`
- `0x18007291c`
- `0x180072b28`
- `0x180072f5c`
- `0x1800731e0`
- `0x180076be4`
- `0x180076de4`
- `0x180079250`
- `0x18007bd44`
- `0x18007c56c`
- `0x18007d1a0`

## string_xrefs

- `0x1800792cc`: `SyncActionCreateServer: Context: 0x%p FullPath: [%ws] Item: 0x%p Parameter: 0x%p Flags: 0x%x`
- `0x18007932a`: `SyncActionCreateServer: TICA 0x%p TICO: 0x%p CallerContext: 0x%p Result: 0x%x`
- `0x180079408`: `SyncActionCreateServer: SyncCreateUNCPathSpecial failed with %x`
- `0x1800794af`: `SyncActionCreateServer: SyncActionHasFileChanged failed with %x`
- `0x18007980a`: `SyncActionCreateServer: '%ws' has changed locally since enumeration [%x] (disconnected=%d)`
- `0x180079561`: `SyncActionCreateServer: SyncCreateUNCPathServerOnly failed with %x -- retrying without DELETE permissions`
- `0x1800795bf`: `SyncActionCreateServer: SyncCreateUNCPathServerOnly failed with %x`
- `0x180079616`: `SyncActionCreateServer: SyncSetFileDeleted failed with %x`
- `0x180079664`: `SyncActionCreateServer: SyncActionCopyFile failed with %x`
- `0x1800796ee`: `SyncActionCreateServer: SyncActionCopyAttributes failed with %x`
- `0x180079741`: `SyncActionCreateServer: SyncUnSetFileDeleted failed with %x`
- `0x1800797a4`: `SyncActionCreateServer: SyncActionSetOriginalTimeAndMarkClean failed with %x`
- `0x180079893`: `SyncActionCreateServer: Result: 0x%x  Return: %x`

## pseudocode

```c
__int64 __fastcall SyncActionCreateServer(__int64 a1, __int64 a2)
{
  __int64 v2; // r9
  int v4; // ebx
  int v5; // esi
  bool v6; // zf
  int v7; // r14d
  bool v8; // r15
  CObjectMonitor *v9; // rax
  int v10; // r8d
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  unsigned int v15; // r12d
  char v16; // cl
  int v17; // edx
  unsigned int *v18; // r15
  unsigned int HasFileChanged; // eax
  unsigned int v20; // eax
  HANDLE v21; // rcx
  ULONG v23[2]; // [rsp+20h] [rbp-58h]
  int v24; // [rsp+20h] [rbp-58h]
  int v25; // [rsp+28h] [rbp-50h]
  int v26; // [rsp+28h] [rbp-50h]
  HANDLE FileHandle; // [rsp+60h] [rbp-18h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp-10h] BYREF
  __int64 v29; // [rsp+C0h] [rbp+48h] BYREF
  int v30; // [rsp+C8h] [rbp+50h] BYREF
  int v31; // [rsp+D0h] [rbp+58h] BYREF
  int v32; // [rsp+D8h] [rbp+60h] BYREF

  v2 = *(_QWORD *)(a1 + 16);
  Handle = 0;
  FileHandle = 0;
  LOBYTE(v29) = 0;
  v4 = 128;
  v5 = 387;
  v6 = (*(_DWORD *)(v2 + 128) & 0x10) == 0;
  v7 = *(_DWORD *)(v2 + 128) & 0x10;
  v32 = 0;
  v30 = 0;
  v8 = !v6;
  v31 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncActionCreateServer: Context: 0x%p FullPath: [%ws] Item: 0x%p Parameter: 0x%p Flags: 0x%x",
        *(_QWORD *)a1,
        *(_QWORD *)(a1 + 8));
      WPP_SF_qSqqD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        30,
        v10,
        *(_QWORD *)a1,
        *(_QWORD *)(a1 + 8),
        *(_QWORD *)(a1 + 16),
        *(_QWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32));
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 108) & 4) != 0 )
    {
      v23[0] = *(_DWORD *)(a1 + 104);
      SyncTraceOutputInternal(
        L"SyncActionCreateServer: TICA 0x%p TICO: 0x%p CallerContext: 0x%p Result: 0x%x",
        *(_QWORD *)(a1 + 64),
        *(_QWORD *)(a1 + 72),
        *(_QWORD *)(a1 + 96),
        *(_QWORD *)v23);
      WPP_SF_qqqD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        31,
        WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
        *(_QWORD *)(a1 + 64),
        *(_QWORD *)(a1 + 72),
        *(_QWORD *)(a1 + 96),
        *(_DWORD *)(a1 + 104));
    }
  }
  LOBYTE(a2) = v8;
  SyncActionpUpdateActionFlag(a1, a2, &v30, &v31);
  if ( !v7 )
  {
    v4 = 129;
    v5 = 65923;
    if ( (*(_BYTE *)(a1 + 32) & 2) != 0 )
      v4 = 385;
  }
  v12 = SyncCreateUNCPathSpecial(
          &FileHandle,
          v11,
          *(const WCHAR **)(a1 + 8),
          v4,
          5u,
          v25,
          v31,
          1u,
          (char *)&v29,
          0,
          v30);
  v13 = v12;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      SyncTraceOutputInternal(L"SyncActionCreateServer: SyncCreateUNCPathSpecial failed with %x", v12);
      v14 = 32;
LABEL_14:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v14, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids, v13);
    }
  }
  else
  {
    v15 = (unsigned __int8)v29;
    if ( (_BYTE)v29 )
    {
      v16 = 0;
      v17 = 0;
    }
    else
    {
      v16 = 1;
      v17 = (int)FileHandle;
    }
    v18 = (unsigned int *)(a1 + 104);
    HasFileChanged = SyncActionHasFileChanged(
                       *(_QWORD *)a1,
                       v17,
                       (_DWORD)FileHandle,
                       (_DWORD)FileHandle,
                       v16,
                       1,
                       1,
                       *(_QWORD *)(a1 + 16),
                       a1 + 104,
                       *(_DWORD *)(a1 + 32));
    v13 = HasFileChanged;
    if ( HasFileChanged )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(L"SyncActionCreateServer: SyncActionHasFileChanged failed with %x", HasFileChanged);
        v14 = 33;
        goto LABEL_14;
      }
    }
    else
    {
      if ( (*v18 & 0x100) != 0 || !(_BYTE)v15 )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(
            L"SyncActionCreateServer: '%ws' has changed locally since enumeration [%x] (disconnected=%d)",
            *(_QWORD *)(a1 + 8),
            *v18,
            v15);
          WPP_SF_SdD(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            34,
            (unsigned int)WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
            *(_QWORD *)(a1 + 8),
            *v18,
            v15);
        }
        v13 = -1073741823;
        goto LABEL_65;
      }
      *v18 = 0;
      while ( 1 )
      {
        v13 = SyncCreateUNCPathServerOnly(&Handle, 0, *(const WCHAR **)(a1 + 8), v5, 0, 5u, 2u, v7 != 0 ? 1 : 64);
        if ( v13 != -1073741790 )
          break;
        if ( (v5 & 0x10000) == 0 )
          goto LABEL_32;
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(L"SyncActionCreateServer: SyncCreateUNCPathServerOnly failed with %x -- retrying without DELETE permissions");
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            35,
            WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
            3221225506LL);
        }
        v5 &= ~0x10000u;
      }
      if ( v13 )
      {
LABEL_32:
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(L"SyncActionCreateServer: SyncCreateUNCPathServerOnly failed with %x", v13);
          v14 = 36;
          goto LABEL_14;
        }
        goto LABEL_65;
      }
      if ( !v7 )
      {
        if ( (v5 & 0x10000) != 0 )
        {
          v13 = SyncSetFileDeleted(Handle);
          if ( v13 )
          {
            if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            {
              SyncTraceOutputInternal(L"SyncActionCreateServer: SyncSetFileDeleted failed with %x", v13);
              v14 = 37;
              goto LABEL_14;
            }
            goto LABEL_65;
          }
        }
        v13 = SyncActionCopyFile(a1, FileHandle, Handle);
        if ( v13 )
        {
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            SyncTraceOutputInternal(L"SyncActionCreateServer: SyncActionCopyFile failed with %x", v13);
            v14 = 38;
            goto LABEL_14;
          }
          goto LABEL_65;
        }
        SyncActionpGetRoundupTime(Handle, a1, &v32);
      }
      v13 = SyncActionCopyAttributesWithAdjustment(FileHandle, Handle, 0, 0, 0, 0);
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(L"SyncActionCreateServer: SyncActionCopyAttributes failed with %x", v13);
          v14 = 39;
          goto LABEL_14;
        }
      }
      else if ( !v7 && (v5 & 0x10000) != 0 && (v13 = SyncUnSetFileDeleted(Handle)) != 0 )
      {
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          SyncTraceOutputInternal(L"SyncActionCreateServer: SyncUnSetFileDeleted failed with %x", v13);
          v14 = 40;
          goto LABEL_14;
        }
      }
      else
      {
        SyncItemAddServerEnumInfo(*(_QWORD *)(a1 + 16) + 104LL, 0, a1 + 112);
        v20 = SyncActionSetOriginalTime(FileHandle);
        v13 = v20;
        if ( v20 )
        {
          if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            SyncTraceOutputInternal(
              L"SyncActionCreateServer: SyncActionSetOriginalTimeAndMarkClean failed with %x",
              v20);
            v14 = 41;
            goto LABEL_14;
          }
        }
        else
        {
          LOBYTE(v26) = 1;
          LOBYTE(v24) = 1;
          SyncItemEnumSingleFile(0, FileHandle, FileHandle, 0, v24, v26, a1 + 112);
          SyncItemAddServerEnumInfo(*(_QWORD *)(a1 + 16) + 104LL, 0, a1 + 112);
        }
      }
    }
  }
LABEL_65:
  if ( FileHandle )
    SyncCloseFile(FileHandle);
  v21 = Handle;
  if ( Handle )
    SyncCloseFile(Handle);
  if ( !v13 )
    SyncBackpatchUNCPath(v21, *(_QWORD *)(a1 + 8));
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncActionCreateServer: Result: 0x%x  Return: %x", *(unsigned int *)(a1 + 104), v13);
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      42,
      WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids,
      *(unsigned int *)(a1 + 104),
      v13);
  }
  return v13;
}

```

## disassembly

```asm
0x180079250  push    rbp
0x180079252  push    rbx
0x180079253  push    rsi
0x180079254  push    rdi
0x180079255  push    r12
0x180079257  push    r13
0x180079259  push    r14
0x18007925b  push    r15
0x18007925d  mov     rbp, rsp
0x180079260  sub     rsp, 78h
0x180079264  mov     r9, [rcx+10h]
0x180079268  xor     eax, eax
0x18007926a  mov     [rbp+Handle], rax
0x18007926e  mov     rdi, rcx
0x180079271  mov     [rbp+FileHandle], rax
0x180079275  mov     r13d, eax
0x180079278  mov     byte ptr [rbp+arg_0], al
0x18007927b  mov     ebx, 80h
0x180079280  mov     r14d, [r9+80h]
0x180079287  mov     esi, 183h
0x18007928c  and     r14d, 10h
0x180079290  mov     [rbp+arg_18], eax
0x180079293  mov     [rbp+arg_8], eax
0x180079296  setnz   r15b
0x18007929a  mov     [rbp+arg_10], eax
0x18007929d  mov     rax, cs:WPP_GLOBAL_Control
0x1800792a4  lea     r12, WPP_GLOBAL_Control
0x1800792ab  cmp     rax, r12
0x1800792ae  jz      loc_18007937F
0x1800792b4  test    byte ptr [rax+6Ch], 4
0x1800792b8  jz      short loc_18007931C
0x1800792ba  mov     eax, [rcx+20h]
0x1800792bd  mov     r8, [rcx+8]
0x1800792c1  mov     rdx, [rcx]
0x1800792c4  mov     [rsp+78h+var_50], eax
0x1800792c8  mov     rax, [rcx+18h]
0x1800792cc  lea     rcx, aSyncactioncrea_16; "SyncActionCreateServer: Context: 0x%p F"...
0x1800792d3  mov     qword ptr [rsp+78h+var_58], rax
0x1800792d8  call    SyncTraceOutputInternal
0x1800792dd  mov     eax, [rdi+20h]
0x1800792e0  lea     edx, [rbx-62h]
0x1800792e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800792ea  mov     r9, [rdi]
0x1800792ed  mov     dword ptr [rsp+78h+var_40], eax
0x1800792f1  mov     rax, [rdi+18h]
0x1800792f5  mov     rcx, [rcx+60h]
0x1800792f9  mov     [rsp+78h+var_48], rax
0x1800792fe  mov     rax, [rdi+10h]
0x180079302  mov     qword ptr [rsp+78h+var_50], rax
0x180079307  mov     rax, [rdi+8]
0x18007930b  mov     qword ptr [rsp+78h+var_58], rax
0x180079310  call    WPP_SF_qSqqD
0x180079315  mov     rax, cs:WPP_GLOBAL_Control
0x18007931c  cmp     rax, r12
0x18007931f  jz      short loc_18007937F
0x180079321  test    byte ptr [rax+6Ch], 4
0x180079325  jz      short loc_18007937F
0x180079327  mov     eax, [rdi+68h]
0x18007932a  lea     rcx, aSyncactioncrea_5; "SyncActionCreateServer: TICA 0x%p TICO:"...
0x180079331  mov     r9, [rdi+60h]
0x180079335  mov     r8, [rdi+48h]
0x180079339  mov     rdx, [rdi+40h]
0x18007933d  mov     [rsp+78h+var_58], eax
0x180079341  call    SyncTraceOutputInternal
0x180079346  mov     eax, [rdi+68h]
0x180079349  lea     r8, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids
0x180079350  mov     rcx, cs:WPP_GLOBAL_Control
0x180079357  mov     edx, 1Fh
0x18007935c  mov     r9, [rdi+40h]
0x180079360  mov     dword ptr [rsp+78h+var_48], eax
0x180079364  mov     rax, [rdi+60h]
0x180079368  mov     rcx, [rcx+60h]
0x18007936c  mov     qword ptr [rsp+78h+var_50], rax; int
0x180079371  mov     rax, [rdi+48h]
0x180079375  mov     qword ptr [rsp+78h+var_58], rax
0x18007937a  call    WPP_SF_qqqD
0x18007937f  lea     r9, [rbp+arg_10]
0x180079383  mov     dl, r15b
0x180079386  lea     r8, [rbp+arg_8]
0x18007938a  mov     rcx, rdi
0x18007938d  call    SyncActionpUpdateActionFlag
0x180079392  test    r14d, r14d
0x180079395  jnz     short loc_1800793AD
0x180079397  test    byte ptr [rdi+20h], 2
0x18007939b  mov     ebx, 81h
0x1800793a0  mov     eax, 181h
0x1800793a5  mov     esi, 10183h
0x1800793aa  cmovnz  ebx, eax
0x1800793ad  mov     eax, [rbp+arg_8]
0x1800793b0  lea     rcx, [rbp+FileHandle]; FileHandle
0x1800793b4  mov     r8, [rdi+8]
0x1800793b8  mov     r9d, ebx
0x1800793bb  mov     [rsp+78h+var_28], eax; int
0x1800793bf  lea     rax, [rbp+arg_0]
0x1800793c3  mov     [rsp+78h+var_30], r13; __int64
0x1800793c8  mov     [rsp+78h+var_38], rax; __int64
0x1800793cd  mov     eax, [rbp+arg_10]
0x1800793d0  mov     [rsp+78h+var_40], 1; char
0x1800793d5  mov     dword ptr [rsp+78h+var_48], eax; int
0x1800793d9  mov     [rsp+78h+var_58], 5; ULONG
0x1800793e1  call    SyncCreateUNCPathSpecial
0x1800793e6  mov     ebx, eax
0x1800793e8  test    eax, eax
0x1800793ea  jz      short loc_180079438
0x1800793ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800793f3  cmp     rcx, r12
0x1800793f6  jz      loc_180079855
0x1800793fc  test    byte ptr [rcx+6Ch], 1
0x180079400  jz      loc_180079855
0x180079406  mov     edx, eax
0x180079408  lea     rcx, aSyncactioncrea_19; "SyncActionCreateServer: SyncCreateUNCPa"...
0x18007940f  call    SyncTraceOutputInternal
0x180079414  mov     edx, 20h ; ' '
0x180079419  mov     rcx, cs:WPP_GLOBAL_Control
0x180079420  lea     r8, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids
0x180079427  mov     r9d, ebx
0x18007942a  mov     rcx, [rcx+60h]
0x18007942e  call    WPP_SF_d
0x180079433  jmp     loc_180079855
0x180079438  movzx   r12d, byte ptr [rbp+arg_0]
0x18007943d  mov     r8, [rbp+FileHandle]
0x180079441  test    r12b, r12b
0x180079444  jnz     short loc_18007944D
0x180079446  mov     cl, 1
0x180079448  mov     rdx, r8
0x18007944b  jmp     short loc_180079451
0x18007944d  xor     cl, cl
0x18007944f  xor     edx, edx
0x180079451  mov     eax, [rdi+20h]
0x180079454  lea     r15, [rdi+68h]
0x180079458  mov     dword ptr [rsp+78h+var_30], eax
0x18007945c  mov     r9, r8
0x18007945f  mov     rax, [rdi+10h]
0x180079463  mov     [rsp+78h+var_38], r15
0x180079468  mov     qword ptr [rsp+78h+var_40], rax
0x18007946d  mov     byte ptr [rsp+78h+var_48], 1
0x180079472  mov     byte ptr [rsp+78h+var_50], 1
0x180079477  mov     byte ptr [rsp+78h+var_58], cl
0x18007947b  mov     rcx, [rdi]
0x18007947e  call    SyncActionHasFileChanged
0x180079483  mov     ebx, eax
0x180079485  test    eax, eax
0x180079487  jz      short loc_1800794DF
0x180079489  mov     rcx, cs:WPP_GLOBAL_Control
0x180079490  lea     r12, WPP_GLOBAL_Control
0x180079497  cmp     rcx, r12
0x18007949a  jz      loc_180079855
0x1800794a0  mov     r12b, 1
0x1800794a3  test    [rcx+6Ch], r12b
0x1800794a7  jz      loc_18007984E
0x1800794ad  mov     edx, eax
0x1800794af  lea     rcx, aSyncactioncrea_34; "SyncActionCreateServer: SyncActionHasFi"...
0x1800794b6  call    SyncTraceOutputInternal
0x1800794bb  mov     edx, 21h ; '!'
0x1800794c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800794c7  lea     r8, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids
0x1800794ce  mov     r9d, ebx
0x1800794d1  mov     rcx, [rcx+60h]
0x1800794d5  call    WPP_SF_d
0x1800794da  jmp     loc_18007984E
0x1800794df  test    dword ptr [r15], 100h
0x1800794e6  jnz     loc_1800797EE
0x1800794ec  test    r12b, r12b
0x1800794ef  jz      loc_1800797EE
0x1800794f5  mov     [r15], r13d
0x1800794f8  mov     eax, r14d
0x1800794fb  neg     eax
0x1800794fd  mov     r12b, 1
0x180079500  sbb     r15d, r15d
0x180079503  and     r15d, 0FFFFFFC1h
0x180079507  add     r15d, 40h ; '@'
0x18007950b  mov     r8, [rdi+8]
0x18007950f  lea     rcx, [rbp+Handle]
0x180079513  mov     dword ptr [rsp+78h+var_40], r15d
0x180079518  mov     r9d, esi
0x18007951b  mov     dword ptr [rsp+78h+var_48], 2
0x180079523  xor     edx, edx
0x180079525  mov     [rsp+78h+var_50], 5
0x18007952d  mov     [rsp+78h+var_58], r13d
0x180079532  call    SyncCreateUNCPathServerOnly
0x180079537  mov     edx, 0C0000022h
0x18007953c  mov     ebx, eax
0x18007953e  cmp     eax, edx
0x180079540  jnz     short loc_180079598
0x180079542  bt      esi, 10h
0x180079546  jnb     short loc_18007959C
0x180079548  mov     rax, cs:WPP_GLOBAL_Control
0x18007954f  lea     rcx, WPP_GLOBAL_Control
0x180079556  cmp     rax, rcx
0x180079559  jz      short loc_18007958F
0x18007955b  test    [rax+6Ch], r12b
0x18007955f  jz      short loc_18007958F
0x180079561  lea     rcx, aSyncactioncrea_4; "SyncActionCreateServer: SyncCreateUNCPa"...
0x180079568  call    SyncTraceOutputInternal
0x18007956d  mov     rcx, cs:WPP_GLOBAL_Control
0x180079574  lea     r8, WPP_4a8ef9c0e0773e7ea8ccf5f865a94432_Traceguids
0x18007957b  mov     edx, 23h ; '#'
0x180079580  mov     r9d, 0C0000022h
0x180079586  mov     rcx, [rcx+60h]
0x18007958a  call    WPP_SF_d
0x18007958f  btr     esi, 10h
0x180079593  jmp     loc_18007950B
0x180079598  test    ebx, ebx
0x18007959a  jz      short loc_1800795D5
0x18007959c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800795a3  lea     rax, WPP_GLOBAL_Control
0x1800795aa  cmp     rcx, rax
0x1800795ad  jz      loc_18007984E
0x1800795b3  test    [rcx+6Ch], r12b
0x1800795b7  jz      loc_18007984E
0x1800795bd  mov     edx, ebx
0x1800795bf  lea     rcx, aSyncactioncrea_18; "SyncActionCreateServer: SyncCreateUNCPa"...
0x1800795c6  call    SyncTraceOutputInternal
0x1800795cb  mov     edx, 24h ; '$'
0x1800795d0  jmp     loc_1800794C0
0x1800795d5  test    r14d, r14d
0x1800795d8  jnz     loc_18007968E
0x1800795de  bt      esi, 10h
0x1800795e2  jnb     short loc_18007962B
0x1800795e4  mov     rcx, [rbp+Handle]; FileHandle
0x1800795e8  call    SyncSetFileDeleted
0x1800795ed  mov     ebx, eax
0x1800795ef  test    eax, eax
0x1800795f1  jz      short loc_18007962B
0x1800795f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800795fa  lea     rax, WPP_GLOBAL_Control
0x180079601  cmp     rcx, rax
0x180079604  jz      loc_18007984E
0x18007960a  test    [rcx+6Ch], r12b
0x18007960e  jz      loc_18007984E
0x180079614  mov     edx, ebx
0x180079616  lea     rcx, aSyncactioncrea_35; "SyncActionCreateServer: SyncSetFileDele"...
0x18007961d  call    SyncTraceOutputInternal
0x180079622  lea     edx, [r14+25h]
0x180079626  jmp     loc_1800794C0
0x18007962b  mov     r8, [rbp+Handle]
0x18007962f  mov     rcx, rdi
0x180079632  mov     rdx, [rbp+FileHandle]
0x180079636  call    SyncActionCopyFile
0x18007963b  mov     ebx, eax
0x18007963d  test    eax, eax
0x18007963f  jz      short loc_18007967A
0x180079641  mov     rcx, cs:WPP_GLOBAL_Control
0x180079648  lea     rax, WPP_GLOBAL_Control
0x18007964f  cmp     rcx, rax
0x180079652  jz      loc_18007984E
0x180079658  test    [rcx+6Ch], r12b
0x18007965c  jz      loc_18007984E
0x180079662  mov     edx, ebx
0x180079664  lea     rcx, aSyncactioncrea_7; "SyncActionCreateServer: SyncActionCopyF"...
0x18007966b  call    SyncTraceOutputInternal
0x180079670  mov     edx, 26h ; '&'
0x180079675  jmp     loc_1800794C0
0x18007967a  mov     rcx, [rbp+Handle]
0x18007967e  lea     r8, [rbp+arg_18]
0x180079682  mov     rdx, rdi
0x180079685  call    SyncActionpGetRoundupTime
0x18007968a  mov     r13d, [rbp+arg_18]
0x18007968e  mov     r8, [rdi+10h]
0x180079692  mov     r9d, r13d
0x180079695  mov     rdx, [rbp+Handle]; FileHandle
0x180079699  add     r8, 68h ; 'h'
0x18007969d  mov     rcx, [rbp+FileHandle]; hHandle
0x1800796a1  mov     qword ptr [rsp+78h+var_40], 0; __int64
0x1800796aa  mov     [rsp+78h+var_48], 0; __int64
0x1800796b3  mov     [rsp+78h+var_50], 0; int
0x1800796bb  mov     byte ptr [rsp+78h+var_58], 0; char
0x1800796c0  call    SyncActionCopyAttributesWithAdjustment
0x1800796c5  mov     ebx, eax
0x1800796c7  test    eax, eax
0x1800796c9  jz      short loc_180079704
0x1800796cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800796d2  lea     rax, WPP_GLOBAL_Control
0x1800796d9  cmp     rcx, rax
0x1800796dc  jz      loc_18007984E
0x1800796e2  test    [rcx+6Ch], r12b
0x1800796e6  jz      loc_18007984E
0x1800796ec  mov     edx, ebx
0x1800796ee  lea     rcx, aSyncactioncrea_29; "SyncActionCreateServer: SyncActionCopyA"...
0x1800796f5  call    SyncTraceOutputInternal
0x1800796fa  mov     edx, 27h ; '''
0x1800796ff  jmp     loc_1800794C0
0x180079704  test    r14d, r14d
0x180079707  jnz     short loc_180079756
0x180079709  bt      esi, 10h
0x18007970d  jnb     short loc_180079756
0x18007970f  mov     rcx, [rbp+Handle]; FileHandle
0x180079713  call    SyncUnSetFileDeleted
0x180079718  mov     ebx, eax
0x18007971a  test    eax, eax
0x18007971c  jz      short loc_180079756
0x18007971e  mov     rcx, cs:WPP_GLOBAL_Control
0x180079725  lea     rax, WPP_GLOBAL_Control
0x18007972c  cmp     rcx, rax
0x18007972f  jz      loc_18007984E
0x180079735  test    [rcx+6Ch], r12b
0x180079739  jz      loc_18007984E
0x18007973f  mov     edx, ebx
0x180079741  lea     rcx, aSyncactioncrea_17; "SyncActionCreateServer: SyncUnSetFileDe"...
0x180079748  call    SyncTraceOutputInternal
  ... truncated ...
```
