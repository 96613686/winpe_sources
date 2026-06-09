# RasRegisterEntryChangeNotification

- ea: `0x180043290`
- end: `0x180043885`
- name: `RasRegisterEntryChangeNotification`
- size: `1525`
- prototype: `__int64 __usercall@<rax>(PCNZWCH lpString2@<rcx>, __int64, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting`

## callees

- `0x18000ada0`
- `0x180010d10`
- `0x1800111f4`
- `0x1800289e0`
- `0x180043290`
- `0x18004e580`
- `0x18004e984`
- `0x18007e5f0`
- `0x18007ed3c`
- `0x1800a7f04`
- `0x1800a8800`
- `0x1800e0010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180043631`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180043631`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800434e2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800434e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800436a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043727`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800434c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800434c2`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180043695`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x180043695`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180043718`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180043718`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800434d5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800434d5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180043785`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180043785`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180043779`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180043779`

## pseudocode

```c
__int64 __fastcall RasRegisterEntryChangeNotification(
        PCNZWCH lpString2,
        _WORD *a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6)
{
  _QWORD *v10; // rcx
  __int64 v11; // rsi
  __int128 v12; // xmm6
  unsigned int RasmanDllAndInit; // eax
  unsigned int EntryFromSystem; // ebx
  _QWORD *v15; // rcx
  unsigned int *v16; // rdi
  _QWORD *v17; // r12
  void *v18; // rcx
  struct _TP_WAIT *v19; // rcx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int128 *v23; // rcx
  unsigned int *v24; // rax
  HANDLE SemaphoreW; // rax
  int IsEnabledDeviceUsageNoInline; // eax
  void (__stdcall *v27)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WAIT, TP_WAIT_RESULT); // rcx
  struct _TP_WAIT *ThreadpoolWait; // rax
  __int64 v29; // rcx
  __int64 v30; // r8
  __int128 v31; // [rsp+40h] [rbp-68h] BYREF
  __int64 v32; // [rsp+B0h] [rbp+8h] BYREF

  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_a576594392393f475090d0b18cfbf556_Traceguids, a3);
    v10 = WPP_GLOBAL_Control;
  }
  if ( lpString2 && a2 )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x800) != 0 && *((_BYTE *)v10 + 25) >= 6u )
      WPP_SF_SSD(
        v10[2],
        97,
        (unsigned int)WPP_a576594392393f475090d0b18cfbf556_Traceguids,
        (_DWORD)lpString2,
        (__int64)a2,
        a3);
  }
  else if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x800) != 0 && *((_BYTE *)v10 + 25) >= 6u )
  {
    WPP_SF_d(v10[2], 98, WPP_a576594392393f475090d0b18cfbf556_Traceguids, a3);
  }
  v11 = 0;
  v32 = 0;
  v12 = 0;
  DebugInit();
  RasmanDllAndInit = LoadRasmanDllAndInit();
  EntryFromSystem = RasmanDllAndInit;
  if ( !RasmanDllAndInit )
  {
    v16 = 0;
    if ( !lpString2 || !a4 || (v17 = a6) == 0 )
    {
      EntryFromSystem = 87;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return EntryFromSystem;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_41;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_a576594392393f475090d0b18cfbf556_Traceguids, 87);
      v15 = WPP_GLOBAL_Control;
      goto LABEL_31;
    }
    if ( a2 && *a2 )
    {
      EntryFromSystem = ReadEntryFromSystem(lpString2, (__int64)a2, 8u, 0, (size_t *)&v32, 0);
      if ( EntryFromSystem )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          v11 = v32;
          goto LABEL_31;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          102,
          WPP_a576594392393f475090d0b18cfbf556_Traceguids,
          EntryFromSystem);
        v11 = v32;
LABEL_30:
        v15 = WPP_GLOBAL_Control;
LABEL_31:
        if ( v11 )
        {
          DestroyEntryNode(v11);
          v15 = WPP_GLOBAL_Control;
        }
        if ( !EntryFromSystem || !v16 )
          goto LABEL_41;
        v18 = (void *)*((_QWORD *)v16 + 1);
        if ( v18 )
        {
          CloseHandle(v18);
          *((_QWORD *)v16 + 1) = 0;
        }
        v19 = (struct _TP_WAIT *)*((_QWORD *)v16 + 2);
        if ( v19 )
        {
          CloseThreadpoolWait(v19);
          *((_QWORD *)v16 + 2) = 0;
        }
        GlobalFree(v16);
        goto LABEL_40;
      }
      v11 = v32;
      v21 = *(_QWORD *)(v32 + 16);
      if ( !v21 )
      {
        EntryFromSystem = 623;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_31;
        }
        v22 = 103;
LABEL_52:
        WPP_SF_d(v15[2], v22, WPP_a576594392393f475090d0b18cfbf556_Traceguids, EntryFromSystem);
        goto LABEL_30;
      }
      v23 = *(__int128 **)(v21 + 464);
      if ( v23 )
        v12 = *v23;
      if ( (a3 & 1) != 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_a576594392393f475090d0b18cfbf556_Traceguids);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_a576594392393f475090d0b18cfbf556_Traceguids, lpString2);
    }
    v24 = (unsigned int *)GlobalAlloc(0x40u, 0x28u);
    v16 = v24;
    if ( v24 )
    {
      *((_QWORD *)v24 + 3) = a4;
      *((_QWORD *)v24 + 4) = a5;
      SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
      *((_QWORD *)v16 + 1) = SemaphoreW;
      if ( SemaphoreW )
      {
        if ( (Feature_VPN_BugFixes_25C_RasNotification__private_featureState & 0x10) != 0 )
          IsEnabledDeviceUsageNoInline = Feature_VPN_BugFixes_25C_RasNotification__private_featureState & 1;
        else
          IsEnabledDeviceUsageNoInline = Feature_VPN_BugFixes_25C_RasNotification__private_IsEnabledDeviceUsageNoInline();
        v27 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WAIT, TP_WAIT_RESULT))&RasEntryChangeNotificationCallback;
        if ( IsEnabledDeviceUsageNoInline )
          v27 = RasEntryChangeNotificationCallbackNew;
        ThreadpoolWait = CreateThreadpoolWait(v27, v16, 0);
        *((_QWORD *)v16 + 2) = ThreadpoolWait;
        if ( ThreadpoolWait )
        {
          SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)v16 + 1), 0);
          WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)v16 + 2), 0);
          v29 = *((_QWORD *)v16 + 1);
          v31 = v12;
          EntryFromSystem = ((__int64 (__fastcall *)(__int64, PCNZWCH, _WORD *, __int128 *, unsigned int, unsigned int *))g_pRasAddNotificationEx)(
                              v29,
                              lpString2,
                              a2,
                              &v31,
                              a3,
                              v16);
          if ( !EntryFromSystem )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, v30, *v16);
            }
            *v17 = v16;
            goto LABEL_30;
          }
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_31;
          }
          v22 = 108;
        }
        else
        {
          EntryFromSystem = GetLastError();
          if ( !EntryFromSystem )
            goto LABEL_30;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_31;
          }
          v22 = 107;
        }
      }
      else
      {
        EntryFromSystem = GetLastError();
        if ( !EntryFromSystem )
          goto LABEL_30;
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_31;
        }
        v22 = 106;
      }
    }
    else
    {
      EntryFromSystem = 8;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_31;
      }
      v22 = 105;
    }
    goto LABEL_52;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return EntryFromSystem;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_a576594392393f475090d0b18cfbf556_Traceguids, RasmanDllAndInit);
LABEL_40:
    v15 = WPP_GLOBAL_Control;
  }
LABEL_41:
  if ( v15 != &WPP_GLOBAL_Control && (*((_DWORD *)v15 + 7) & 0x800) != 0 && *((_BYTE *)v15 + 25) >= 6u )
    WPP_SF_d(v15[2], 110, WPP_a576594392393f475090d0b18cfbf556_Traceguids, EntryFromSystem);
  return EntryFromSystem;
}

```

## disassembly

```asm
0x180043290  push    rbx
0x180043292  push    rbp
0x180043293  push    rsi
0x180043294  push    rdi
0x180043295  push    r12
0x180043297  push    r13
0x180043299  push    r14
0x18004329b  push    r15
0x18004329d  sub     rsp, 68h
0x1800432a1  movaps  [rsp+0A8h+var_58], xmm6
0x1800432a6  mov     r13, r9
0x1800432a9  mov     r15d, r8d
0x1800432ac  mov     rbp, rdx
0x1800432af  mov     r14, rcx
0x1800432b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800432b9  lea     rax, WPP_GLOBAL_Control
0x1800432c0  cmp     rcx, rax
0x1800432c3  jz      short loc_1800432FA
0x1800432c5  test    dword ptr [rcx+1Ch], 800h
0x1800432cc  jz      short loc_1800432FA
0x1800432ce  cmp     byte ptr [rcx+19h], 6
0x1800432d2  jb      short loc_1800432FA
0x1800432d4  mov     rcx, [rcx+10h]
0x1800432d8  mov     r9d, r8d
0x1800432db  lea     r8, WPP_a576594392393f475090d0b18cfbf556_Traceguids
0x1800432e2  mov     edx, 60h ; '`'
0x1800432e7  call    WPP_SF_d
0x1800432ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800432f3  lea     rax, WPP_GLOBAL_Control
0x1800432fa  xor     r12d, r12d
0x1800432fd  test    r14, r14
0x180043300  jz      short loc_18004333F
0x180043302  test    rbp, rbp
0x180043305  jz      short loc_18004333F
0x180043307  cmp     rcx, rax
0x18004330a  jz      short loc_18004336B
0x18004330c  test    dword ptr [rcx+1Ch], 800h
0x180043313  jz      short loc_18004336B
0x180043315  cmp     byte ptr [rcx+19h], 6
0x180043319  jb      short loc_18004336B
0x18004331b  mov     rcx, [rcx+10h]
0x18004331f  lea     edx, [r12+61h]
0x180043324  mov     dword ptr [rsp+0A8h+var_80], r15d
0x180043329  lea     r8, WPP_a576594392393f475090d0b18cfbf556_Traceguids
0x180043330  mov     r9, r14
0x180043333  mov     [rsp+0A8h+var_88], rbp
0x180043338  call    WPP_SF_SSD
0x18004333d  jmp     short loc_18004336B
0x18004333f  cmp     rcx, rax
0x180043342  jz      short loc_18004336B
0x180043344  test    dword ptr [rcx+1Ch], 800h
0x18004334b  jz      short loc_18004336B
0x18004334d  cmp     byte ptr [rcx+19h], 6
0x180043351  jb      short loc_18004336B
0x180043353  mov     rcx, [rcx+10h]
0x180043357  lea     r8, WPP_a576594392393f475090d0b18cfbf556_Traceguids
0x18004335e  mov     edx, 62h ; 'b'
0x180043363  mov     r9d, r15d
0x180043366  call    WPP_SF_d
0x18004336b  mov     rsi, r12
0x18004336e  mov     [rsp+0A8h+arg_0], r12
0x180043376  xorps   xmm6, xmm6
0x180043379  call    DebugInit
0x18004337e  call    LoadRasmanDllAndInit
0x180043383  mov     ebx, eax
0x180043385  test    eax, eax
0x180043387  jz      short loc_1800433D4
0x180043389  mov     rcx, cs:WPP_GLOBAL_Control
0x180043390  lea     rbp, WPP_GLOBAL_Control
0x180043397  cmp     rcx, rbp
0x18004339a  jz      loc_18004351B
0x1800433a0  test    dword ptr [rcx+1Ch], 800h
0x1800433a7  jz      loc_1800434EF
0x1800433ad  cmp     byte ptr [rcx+19h], 2
0x1800433b1  jb      loc_1800434EF
0x1800433b7  mov     rcx, [rcx+10h]
0x1800433bb  lea     r8, WPP_a576594392393f475090d0b18cfbf556_Traceguids
0x1800433c2  mov     edx, 63h ; 'c'
0x1800433c7  mov     r9d, eax
0x1800433ca  call    WPP_SF_d
0x1800433cf  jmp     loc_1800434E8
0x1800433d4  mov     rdi, r12
0x1800433d7  test    r14, r14
0x1800433da  jz      loc_180043830
0x1800433e0  test    r13, r13
0x1800433e3  jz      loc_180043830
0x1800433e9  mov     r12, [rsp+0A8h+arg_28]
0x1800433f1  xor     eax, eax
0x1800433f3  test    r12, r12
0x1800433f6  jz      loc_180043830
0x1800433fc  test    rbp, rbp
0x1800433ff  jz      loc_1800435EF
0x180043405  cmp     [rbp+0], ax
0x180043409  jz      loc_1800435EF
0x18004340f  mov     [rsp+0A8h+var_80], rax; __int64
0x180043414  xor     r9d, r9d
0x180043417  lea     rax, [rsp+0A8h+arg_0]
0x18004341f  mov     rdx, rbp
0x180043422  mov     rcx, r14; lpString2
0x180043425  mov     [rsp+0A8h+var_88], rax; __int64
0x18004342a  lea     r8d, [r9+8]
0x18004342e  call    ReadEntryFromSystem
0x180043433  mov     ebx, eax
0x180043435  test    eax, eax
0x180043437  jz      loc_180043540
0x18004343d  mov     rcx, cs:WPP_GLOBAL_Control
0x180043444  lea     rax, WPP_GLOBAL_Control
0x18004344b  cmp     rcx, rax
0x18004344e  jz      loc_180043533
0x180043454  test    dword ptr [rcx+1Ch], 800h
0x18004345b  jz      loc_180043533
0x180043461  cmp     byte ptr [rcx+19h], 2
0x180043465  jb      loc_180043533
0x18004346b  mov     rcx, [rcx+10h]
0x18004346f  lea     r8, WPP_a576594392393f475090d0b18cfbf556_Traceguids
0x180043476  mov     edx, 66h ; 'f'
0x18004347b  mov     r9d, ebx
0x18004347e  call    WPP_SF_d
0x180043483  mov     rsi, [rsp+0A8h+arg_0]
0x18004348b  mov     rcx, cs:WPP_GLOBAL_Control
0x180043492  lea     rbp, WPP_GLOBAL_Control
0x180043499  xor     r12d, r12d
0x18004349c  test    rsi, rsi
0x18004349f  jz      short loc_1800434B0
0x1800434a1  mov     rcx, rsi
0x1800434a4  call    DestroyEntryNode
0x1800434a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800434b0  test    ebx, ebx
0x1800434b2  jz      short loc_1800434EF
0x1800434b4  test    rdi, rdi
0x1800434b7  jz      short loc_1800434EF
0x1800434b9  mov     rcx, [rdi+8]; hObject
0x1800434bd  test    rcx, rcx
0x1800434c0  jz      short loc_1800434CC
0x1800434c2  call    cs:__imp_CloseHandle
0x1800434c8  mov     [rdi+8], r12
0x1800434cc  mov     rcx, [rdi+10h]; pwa
0x1800434d0  test    rcx, rcx
0x1800434d3  jz      short loc_1800434DF
0x1800434d5  call    cs:__imp_CloseThreadpoolWait
0x1800434db  mov     [rdi+10h], r12
0x1800434df  mov     rcx, rdi; hMem
0x1800434e2  call    cs:__imp_GlobalFree
0x1800434e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800434ef  cmp     rcx, rbp
0x1800434f2  jz      short loc_18004351B
0x1800434f4  test    dword ptr [rcx+1Ch], 800h
0x1800434fb  jz      short loc_18004351B
0x1800434fd  cmp     byte ptr [rcx+19h], 6
0x180043501  jb      short loc_18004351B
0x180043503  mov     rcx, [rcx+10h]
0x180043507  lea     r8, WPP_a576594392393f475090d0b18cfbf556_Traceguids
0x18004350e  mov     edx, 6Eh ; 'n'
0x180043513  mov     r9d, ebx
0x180043516  call    WPP_SF_d
0x18004351b  movaps  xmm6, [rsp+0A8h+var_58]
0x180043520  mov     eax, ebx
0x180043522  add     rsp, 68h
0x180043526  pop     r15
0x180043528  pop     r14
0x18004352a  pop     r13
0x18004352c  pop     r12
0x18004352e  pop     rdi
0x18004352f  pop     rsi
0x180043530  pop     rbp
0x180043531  pop     rbx
0x180043532  retn
0x180043533  mov     rsi, [rsp+0A8h+arg_0]
0x18004353b  jmp     loc_180043492
0x180043540  mov     rsi, [rsp+0A8h+arg_0]
0x180043548  mov     rax, [rsi+10h]
0x18004354c  test    rax, rax
0x18004354f  jnz     short loc_1800435A1
0x180043551  mov     ebx, 26Fh
0x180043556  mov     rcx, cs:WPP_GLOBAL_Control
0x18004355d  lea     rax, WPP_GLOBAL_Control
0x180043564  cmp     rcx, rax
0x180043567  jz      loc_180043492
0x18004356d  test    dword ptr [rcx+1Ch], 800h
0x180043574  jz      loc_180043492
0x18004357a  cmp     byte ptr [rcx+19h], 2
0x18004357e  jb      loc_180043492
0x180043584  mov     edx, 67h ; 'g'
0x180043589  mov     rcx, [rcx+10h]
0x18004358d  lea     r8, WPP_a576594392393f475090d0b18cfbf556_Traceguids
0x180043594  mov     r9d, ebx
0x180043597  call    WPP_SF_d
0x18004359c  jmp     loc_18004348B
0x1800435a1  mov     rcx, [rax+1D0h]
0x1800435a8  test    rcx, rcx
0x1800435ab  jz      short loc_1800435B0
0x1800435ad  movups  xmm6, xmmword ptr [rcx]
0x1800435b0  test    r15b, 1
0x1800435b4  jz      short loc_180043629
0x1800435b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800435bd  lea     rax, WPP_GLOBAL_Control
0x1800435c4  cmp     rcx, rax
0x1800435c7  jz      short loc_180043629
0x1800435c9  test    dword ptr [rcx+1Ch], 800h
0x1800435d0  jz      short loc_180043629
0x1800435d2  cmp     byte ptr [rcx+19h], 5
0x1800435d6  jb      short loc_180043629
0x1800435d8  mov     rcx, [rcx+10h]
0x1800435dc  lea     r8, WPP_a576594392393f475090d0b18cfbf556_Traceguids
0x1800435e3  mov     edx, 68h ; 'h'
0x1800435e8  call    WPP_SF_
0x1800435ed  jmp     short loc_180043629
0x1800435ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800435f6  lea     rax, WPP_GLOBAL_Control
0x1800435fd  cmp     rcx, rax
0x180043600  jz      short loc_180043629
0x180043602  test    dword ptr [rcx+1Ch], 800h
0x180043609  jz      short loc_180043629
0x18004360b  cmp     byte ptr [rcx+19h], 5
0x18004360f  jb      short loc_180043629
0x180043611  mov     rcx, [rcx+10h]
0x180043615  lea     r8, WPP_a576594392393f475090d0b18cfbf556_Traceguids
0x18004361c  mov     edx, 65h ; 'e'
0x180043621  mov     r9, r14
0x180043624  call    WPP_SF_S
0x180043629  mov     edx, 28h ; '('; dwBytes
0x18004362e  lea     ecx, [rdx+18h]; uFlags
0x180043631  call    cs:__imp_GlobalAlloc
0x180043637  mov     rdi, rax
0x18004363a  test    rax, rax
0x18004363d  jnz     short loc_180043678
0x18004363f  lea     ebx, [rax+8]
0x180043642  mov     rcx, cs:WPP_GLOBAL_Control
0x180043649  lea     rax, WPP_GLOBAL_Control
0x180043650  cmp     rcx, rax
0x180043653  jz      loc_180043492
0x180043659  test    dword ptr [rcx+1Ch], 800h
0x180043660  jz      loc_180043492
0x180043666  cmp     byte ptr [rcx+19h], 2
0x18004366a  jb      loc_180043492
0x180043670  lea     edx, [rdi+69h]
0x180043673  jmp     loc_180043589
0x180043678  mov     [rax+18h], r13
0x18004367c  xor     r9d, r9d; lpName
0x18004367f  mov     rax, [rsp+0A8h+arg_20]
0x180043687  xor     edx, edx; lInitialCount
0x180043689  xor     ecx, ecx; lpSemaphoreAttributes
0x18004368b  mov     [rdi+20h], rax
0x18004368f  mov     r8d, 7FFFFFFFh; lMaximumCount
0x180043695  call    cs:__imp_CreateSemaphoreW
0x18004369b  mov     [rdi+8], rax
0x18004369f  test    rax, rax
0x1800436a2  jnz     short loc_1800436EC
0x1800436a4  call    cs:__imp_GetLastError
0x1800436aa  mov     ebx, eax
0x1800436ac  test    eax, eax
0x1800436ae  jz      loc_18004348B
0x1800436b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800436bb  lea     rax, WPP_GLOBAL_Control
0x1800436c2  cmp     rcx, rax
0x1800436c5  jz      loc_180043492
0x1800436cb  test    dword ptr [rcx+1Ch], 800h
0x1800436d2  jz      loc_180043492
0x1800436d8  cmp     byte ptr [rcx+19h], 2
0x1800436dc  jb      loc_180043492
0x1800436e2  mov     edx, 6Ah ; 'j'
0x1800436e7  jmp     loc_180043589
0x1800436ec  mov     eax, cs:Feature_VPN_BugFixes_25C_RasNotification__private_featureState
0x1800436f2  test    al, 10h
0x1800436f4  jz      short loc_1800436FB
0x1800436f6  and     eax, 1
0x1800436f9  jmp     short loc_180043700
0x1800436fb  call    Feature_VPN_BugFixes_25C_RasNotification__private_IsEnabledDeviceUsageNoInline
0x180043700  xor     r8d, r8d; pcbe
0x180043703  lea     rcx, RasEntryChangeNotificationCallback
0x18004370a  mov     rdx, rdi; pv
0x18004370d  test    eax, eax
0x18004370f  jz      short loc_180043718
0x180043711  lea     rcx, RasEntryChangeNotificationCallbackNew; pfnwa
0x180043718  call    cs:__imp_CreateThreadpoolWait
0x18004371e  mov     [rdi+10h], rax
0x180043722  test    rax, rax
0x180043725  jnz     short loc_18004376F
0x180043727  call    cs:__imp_GetLastError
0x18004372d  mov     ebx, eax
0x18004372f  test    eax, eax
0x180043731  jz      loc_18004348B
0x180043737  mov     rcx, cs:WPP_GLOBAL_Control
0x18004373e  lea     rax, WPP_GLOBAL_Control
0x180043745  cmp     rcx, rax
0x180043748  jz      loc_180043492
0x18004374e  test    dword ptr [rcx+1Ch], 800h
0x180043755  jz      loc_180043492
0x18004375b  cmp     byte ptr [rcx+19h], 2
0x18004375f  jb      loc_180043492
0x180043765  mov     edx, 6Bh ; 'k'
0x18004376a  jmp     loc_180043589
0x18004376f  mov     rdx, [rdi+8]; h
0x180043773  xor     r8d, r8d; pftTimeout
0x180043776  mov     rcx, rax; pwa
0x180043779  call    cs:__imp_SetThreadpoolWait
0x18004377f  mov     rcx, [rdi+10h]; pwa
0x180043783  xor     edx, edx; fCancelPendingCallbacks
0x180043785  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18004378b  mov     rcx, [rdi+8]
  ... truncated ...
```
