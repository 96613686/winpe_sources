# PrjfPostNetworkQueryOpen

- ea: `0x140023470`
- end: `0x140023732`
- name: `PrjfPostNetworkQueryOpen`
- size: `706`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000ba20`
- `0x14000bb00`
- `0x14000be80`
- `0x14000d008`
- `0x14000d128`
- `0x140023470`

## import_xrefs

- `FLTMGR!FltReleaseFileNameInformation` at `0x140023704`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140023704`
- `FLTMGR!FltGetFileNameInformation` at `0x1400234ff`
- `FLTMGR!FltGetFileNameInformation` at `0x1400234ff`

## string_xrefs

- `0x140023539`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140023625`: `onecore\base\fs\gvflt\filter\sys\create.c`
- `0x140023683`: `onecore\base\fs\gvflt\filter\sys\create.c`

## pseudocode

```c
__int64 __fastcall PrjfPostNetworkQueryOpen(PFLT_CALLBACK_DATA CallbackData, __int64 a2, __int64 a3, char a4)
{
  _DWORD *EaList; // rbx
  NTSTATUS v8; // eax
  int v9; // edx
  int v10; // r8d
  __int64 v11; // rdx
  int v12; // eax
  int v13; // edx
  int v14; // r8d
  unsigned int v15; // eax
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[48]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v19; // [rsp+98h] [rbp-68h] BYREF
  _DWORD v20[20]; // [rsp+B0h] [rbp-50h] BYREF

  FileNameInformation = 0;
  memset(v18, 0, 44);
  v19 = 0;
  memset(v20, 0, 0x48u);
  if ( (a4 & 1) != 0 )
    return 0;
  if ( CallbackData->IoStatus.Status < 0 )
    goto LABEL_22;
  EaList = CallbackData->Iopb->Parameters.QueryEa.EaList;
  if ( (EaList[12] & 0x400) == 0 )
    return 0;
  v8 = FltGetFileNameInformation(CallbackData, 0x102u, &FileNameInformation);
  if ( v8 < 0 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        v9,
        v10,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        49,
        (__int64)&WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
        200,
        v8);
    }
LABEL_22:
    CallbackData->IoStatus.Status = -1071906812;
    CallbackData->IoStatus.Information = 0;
    goto LABEL_23;
  }
  v11 = *(_QWORD *)(a2 + 24);
  *(_QWORD *)&v18[16] = &FileNameInformation->Name;
  *(_DWORD *)v18 = 48;
  *(_QWORD *)&v18[8] = 0;
  *(_DWORD *)&v18[24] = 512;
  *(_OWORD *)&v18[32] = 0;
  v12 = ((__int64 (__fastcall *)(PFLT_FILTER, __int64, _BYTE *, __int128 *, _DWORD *, int, int, _QWORD))PrjfFltQueryInformationByName)(
          Globals,
          v11,
          v18,
          &v19,
          v20,
          72,
          68,
          0);
  if ( v12 < 0 )
  {
    if ( (xmmword_14001A3D0 & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = xmmword_14001A3D0 & 0x20;
      LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        517,
        v13,
        v14,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        5,
        50,
        (__int64)&WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
        217,
        v12);
    }
    goto LABEL_22;
  }
  if ( (v20[14] & 0x400) == 0 )
  {
    if ( (BYTE8(xmmword_14001A3D0) & 0x20) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = BYTE8(xmmword_14001A3D0) & 0x20;
      LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        773,
        v13,
        v14,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        3,
        5,
        51,
        (__int64)&WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\create.c",
        229);
    }
    goto LABEL_22;
  }
  if ( v20[15] == -1879048164 )
  {
    v15 = v20[14] & 0xFFFFE9FF;
    if ( (v20[14] & 0xFFFFE9FF) == 0 )
      v15 = 128;
    EaList[12] = v15;
    goto LABEL_23;
  }
  if ( v20[15] == -1610612702 )
    goto LABEL_22;
LABEL_23:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return 0;
}

```

## disassembly

```asm
0x140023470  mov     [rsp-8+arg_10], rbx
0x140023475  push    rbp
0x140023476  push    rsi
0x140023477  push    rdi
0x140023478  lea     rbp, [rsp-10h]
0x14002347d  sub     rsp, 110h
0x140023484  mov     rax, cs:__security_cookie
0x14002348b  xor     rax, rsp
0x14002348e  mov     [rbp+20h+var_20], rax
0x140023492  xorps   xmm0, xmm0
0x140023495  mov     [rsp+120h+FileNameInformation], 0
0x14002349e  xor     eax, eax
0x1400234a0  mov     rsi, rdx
0x1400234a3  mov     rdi, rcx
0x1400234a6  xor     edx, edx; Val
0x1400234a8  movups  [rsp+120h+var_A8], xmm0
0x1400234ad  lea     rcx, [rbp+20h+var_70]; void *
0x1400234b1  mov     ebx, r9d
0x1400234b4  lea     r8d, [rax+48h]; Size
0x1400234b8  movups  [rsp+120h+var_B8], xmm0
0x1400234bd  movups  [rbp+20h+var_A8+0Ch], xmm0
0x1400234c1  movups  [rbp+20h+var_88], xmm0
0x1400234c5  call    memset
0x1400234ca  test    bl, 1
0x1400234cd  jnz     loc_140023710
0x1400234d3  cmp     dword ptr [rdi+18h], 0
0x1400234d7  jl      loc_1400236EB
0x1400234dd  mov     rax, [rdi+10h]
0x1400234e1  mov     rbx, [rax+20h]
0x1400234e5  test    dword ptr [rbx+30h], 400h
0x1400234ec  jz      loc_140023710
0x1400234f2  lea     r8, [rsp+120h+FileNameInformation]; FileNameInformation
0x1400234f7  mov     edx, 102h; NameOptions
0x1400234fc  mov     rcx, rdi; CallbackData
0x1400234ff  call    cs:__imp_FltGetFileNameInformation
0x140023506  nop     dword ptr [rax+rax+00h]
0x14002350b  test    eax, eax
0x14002350d  jns     short loc_140023587
0x14002350f  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140023515  lea     rcx, WPP_RECORDER_INITIALIZED
0x14002351c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140023523  setnz   r8b
0x140023527  and     dl, 20h
0x14002352a  jnz     short loc_140023535
0x14002352c  test    r8b, r8b
0x14002352f  jz      loc_1400236EB
0x140023535  mov     [rsp+120h+var_D0], eax
0x140023539  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140023540  mov     [rsp+120h+var_D8], 8C8h
0x140023548  mov     [rsp+120h+var_E0], rax
0x14002354d  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x140023554  mov     [rsp+120h+var_E8], rax
0x140023559  mov     word ptr [rsp+120h+var_F0], 31h ; '1'
0x140023560  mov     r9, cs:WPP_GLOBAL_Control
0x140023567  mov     ecx, 205h
0x14002356c  mov     [rsp+120h+var_F8], 5
0x140023574  mov     byte ptr [rsp+120h+var_100], 2
0x140023579  mov     r9, [r9+40h]
0x14002357d  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140023582  jmp     loc_1400236EB
0x140023587  mov     rax, [rsp+120h+FileNameInformation]
0x14002358c  lea     rcx, [rbp+20h+var_70]
0x140023590  mov     rdx, [rsi+18h]
0x140023594  lea     r9, [rbp+20h+var_88]
0x140023598  mov     [rsp+120h+var_E8], 0
0x1400235a1  lea     r8, [rsp+120h+var_B8]
0x1400235a6  add     rax, 8
0x1400235aa  mov     [rsp+120h+var_F0], 44h ; 'D'
0x1400235b2  mov     qword ptr [rsp+120h+var_A8], rax
0x1400235b7  xorps   xmm0, xmm0
0x1400235ba  mov     rax, cs:PrjfFltQueryInformationByName
0x1400235c1  mov     [rsp+120h+var_F8], 48h ; 'H'
0x1400235c9  mov     [rsp+120h+var_100], rcx
0x1400235ce  mov     rcx, cs:Globals
0x1400235d5  mov     dword ptr [rsp+120h+var_B8], 30h ; '0'
0x1400235dd  mov     qword ptr [rsp+120h+var_B8+8], 0
0x1400235e6  mov     dword ptr [rbp+20h+var_A8+8], 200h
0x1400235ed  movdqu  [rbp+20h+var_98], xmm0
0x1400235f2  call    _guard_dispatch_icall
0x1400235f7  test    eax, eax
0x1400235f9  jns     short loc_140023651
0x1400235fb  mov     dl, byte ptr cs:xmmword_14001A3D0
0x140023601  lea     rcx, WPP_RECORDER_INITIALIZED
0x140023608  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002360f  setnz   r8b
0x140023613  and     dl, 20h
0x140023616  jnz     short loc_140023621
0x140023618  test    r8b, r8b
0x14002361b  jz      loc_1400236EB
0x140023621  mov     [rsp+120h+var_D0], eax
0x140023625  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002362c  mov     [rsp+120h+var_D8], 8D9h
0x140023634  mov     [rsp+120h+var_E0], rax
0x140023639  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x140023640  mov     [rsp+120h+var_E8], rax
0x140023645  mov     word ptr [rsp+120h+var_F0], 32h ; '2'
0x14002364c  jmp     loc_140023560
0x140023651  mov     eax, [rbp+20h+var_38]
0x140023654  bt      eax, 0Ah
0x140023658  jb      short loc_1400236C7
0x14002365a  mov     dl, byte ptr cs:xmmword_14001A3D0+8
0x140023660  lea     rcx, WPP_RECORDER_INITIALIZED
0x140023667  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002366e  setnz   r8b
0x140023672  and     dl, 20h
0x140023675  jnz     short loc_14002367C
0x140023677  test    r8b, r8b
0x14002367a  jz      short loc_1400236EB
0x14002367c  mov     r9, cs:WPP_GLOBAL_Control
0x140023683  lea     rax, aOnecoreBaseFsG_9; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002368a  mov     [rsp+120h+var_D8], 8E5h
0x140023692  mov     ecx, 305h
0x140023697  mov     [rsp+120h+var_E0], rax
0x14002369c  lea     rax, WPP_f1013eb3f82c329044bb9a17796863c5_Traceguids
0x1400236a3  mov     [rsp+120h+var_E8], rax
0x1400236a8  mov     r9, [r9+40h]
0x1400236ac  mov     word ptr [rsp+120h+var_F0], 33h ; '3'
0x1400236b3  mov     [rsp+120h+var_F8], 5
0x1400236bb  mov     byte ptr [rsp+120h+var_100], 3
0x1400236c0  call    WPP_RECORDER_AND_TRACE_SF_sD
0x1400236c5  jmp     short loc_1400236EB
0x1400236c7  cmp     [rbp+20h+var_34], 9000001Ch
0x1400236ce  jnz     short loc_1400236E2
0x1400236d0  and     eax, 0FFFFE9FFh
0x1400236d5  mov     ecx, 80h
0x1400236da  cmovz   eax, ecx
0x1400236dd  mov     [rbx+30h], eax
0x1400236e0  jmp     short loc_1400236FA
0x1400236e2  cmp     [rbp+20h+var_34], 0A0000022h
0x1400236e9  jnz     short loc_1400236FA
0x1400236eb  mov     dword ptr [rdi+18h], 0C01C0004h
0x1400236f2  mov     qword ptr [rdi+20h], 0
0x1400236fa  mov     rcx, [rsp+120h+FileNameInformation]; FileNameInformation
0x1400236ff  test    rcx, rcx
0x140023702  jz      short loc_140023710
0x140023704  call    cs:__imp_FltReleaseFileNameInformation
0x14002370b  nop     dword ptr [rax+rax+00h]
0x140023710  xor     eax, eax
0x140023712  mov     rcx, [rbp+20h+var_20]
0x140023716  xor     rcx, rsp; StackCookie
0x140023719  call    __security_check_cookie
0x14002371e  mov     rbx, [rsp+120h+arg_10]
0x140023726  add     rsp, 110h
0x14002372d  pop     rdi
0x14002372e  pop     rsi
0x14002372f  pop     rbp
0x140023730  retn
```
