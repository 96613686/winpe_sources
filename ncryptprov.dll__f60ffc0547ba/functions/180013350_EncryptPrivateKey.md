# EncryptPrivateKey

- ea: `0x180013350`
- end: `0x1800136f1`
- name: `EncryptPrivateKey`
- size: `929`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, __int64, int, DWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800128ac`
- `0x1800138f4`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000def0`
- `0x180010fac`
- `0x180011548`
- `0x180012568`
- `0x180013350`
- `0x1800398b0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800134d2`
- `ntdll!RtlNtStatusToDosError` at `0x180013608`
- `ntdll!RtlNtStatusToDosError` at `0x1800134d2`
- `ntdll!RtlNtStatusToDosError` at `0x180013608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001354d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001354d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013629`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013629`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800135ab`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800135ab`
- `DPAPI!CryptProtectDataNoUI` at `0x180013539`
- `DPAPI!CryptProtectDataNoUI` at `0x180013539`

## string_xrefs

- `0x1800134ac`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x1800134fc`: `onecore\ds\security\cryptoapi\ncrypt\storage\helpers.c`
- `0x180013446`: `onecore\ds\security\cryptoapi\ncrypt\storage\protect.c`
- `0x18001368b`: `onecore\ds\security\cryptoapi\ncrypt\storage\protect.c`

## pseudocode

```c
__int64 __fastcall EncryptPrivateKey(
        __int64 a1,
        int a2,
        _QWORD *a3,
        _DWORD *a4,
        int a5,
        int a6,
        __int64 a7,
        int a8,
        DWORD dwMilliseconds)
{
  bool v9; // cf
  __int64 v10; // rcx
  int v11; // r13d
  _DWORD *v12; // rdi
  _QWORD *v13; // rsi
  int v14; // eax
  int v15; // edx
  DWORD LastError; // ebx
  int v17; // r8d
  _QWORD *v18; // rcx
  HANDLE v19; // rdi
  int v20; // r12d
  NTSTATUS v21; // eax
  int v22; // edx
  int v23; // r8d
  NTSTATUS v24; // ebx
  ULONG v25; // eax
  unsigned int v26; // esi
  DWORD v27; // r15d
  int v28; // eax
  NTSTATUS v29; // esi
  void *v30; // rax
  int v31; // edx
  int v32; // r8d
  void *v33; // rbx
  int v34; // eax
  int v36; // [rsp+28h] [rbp-89h]
  char v37; // [rsp+38h] [rbp-79h]
  int v38[2]; // [rsp+58h] [rbp-59h] BYREF
  const char *v39; // [rsp+60h] [rbp-51h]
  void *Src[2]; // [rsp+68h] [rbp-49h] BYREF
  int v41[2]; // [rsp+78h] [rbp-39h] BYREF
  __int64 v42; // [rsp+80h] [rbp-31h]
  int v43[2]; // [rsp+88h] [rbp-29h] BYREF
  __int64 v44; // [rsp+90h] [rbp-21h]
  __int64 v45[2]; // [rsp+98h] [rbp-19h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-9h]
  HANDLE hObject; // [rsp+F8h] [rbp+47h] BYREF
  _QWORD *v48; // [rsp+108h] [rbp+57h]
  _DWORD *v49; // [rsp+110h] [rbp+5Fh]

  v49 = a4;
  v48 = a3;
  v42 = a1;
  v9 = a5 != 0;
  a5 = -a5;
  v10 = a7;
  v46 = 0;
  v41[1] = 0;
  v11 = v9 ? 4 : 1;
  v38[1] = 0;
  v12 = a4;
  v43[1] = 0;
  v13 = a3;
  v14 = a8;
  *(_OWORD *)v45 = 0;
  LODWORD(v45[0]) = 24;
  *(_OWORD *)Src = 0;
  v41[0] = a2;
  v43[0] = a8;
  v44 = a7;
  v38[0] = 17;
  if ( a6 )
  {
    v39 = "xT5rZW5qVVbrvpuA";
    LastError = MyCryptProtectData(
                  (int)v41,
                  (int)L"Private Key",
                  (int)v38,
                  (int)v43,
                  v36,
                  (__int64)v45,
                  v11,
                  dwMilliseconds,
                  (__int64)Src);
    if ( LastError )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v37 = 107;
LABEL_6:
        WPP_SF_sDsd(
          v18[2],
          v15,
          v17,
          (unsigned int)"Status",
          LastError,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\protect.c",
          v37);
        goto LABEL_44;
      }
      goto LABEL_44;
    }
LABEL_39:
    v30 = (void *)SafeAllocaAllocateFromHeap(LODWORD(Src[0]));
    v33 = v30;
    if ( v30 )
    {
      memcpy_0(v30, Src[1], LODWORD(Src[0]));
      v34 = (int)Src[0];
      *v13 = v33;
      LastError = 0;
      *v12 = v34;
    }
    else
    {
      LastError = -2146893810;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v31,
          v32,
          (unsigned int)"Status",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\protect.c",
          139);
    }
    goto LABEL_44;
  }
  v19 = 0;
  v20 = 0;
  v39 = "6jnkd5J3ZdQDtrsu";
  hObject = 0;
  if ( dwMilliseconds )
  {
    v21 = RevertToLocalSystem(&hObject);
    v24 = v21;
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v22,
          v23,
          (unsigned int)"Status",
          v21,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
          122);
      v25 = RtlNtStatusToDosError(v24);
      v19 = hObject;
      LastError = v25;
      goto LABEL_32;
    }
    v19 = hObject;
    v20 = 1;
    v14 = a8;
    v10 = a7;
  }
  v26 = 0;
  v27 = 10;
  while ( !(unsigned int)CryptProtectDataNoUI(v41, L"Private Key Properties", v38, 0, v45, v11, v10, v14, Src) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        v17,
        (unsigned int)"dwSts",
        LastError,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c",
        150);
    if ( LastError == 1717 )
    {
      LastError = 1062;
      goto LABEL_27;
    }
    if ( LastError != 1723 )
      goto LABEL_27;
    if ( v26 >= 5 )
    {
      LastError = 1723;
      goto LABEL_27;
    }
    Sleep(v27);
    v14 = a8;
    v27 *= 2;
    v10 = a7;
    ++v26;
  }
  LastError = 0;
LABEL_27:
  if ( v20 )
  {
    v28 = RevertBackToCallerToken((__int64)v19);
    v29 = v28;
    if ( v28 < 0 )
    {
      DebugTraceError((unsigned int)v28, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\helpers.c", 441);
      if ( !LastError )
        LastError = RtlNtStatusToDosError(v29);
    }
  }
  v13 = v48;
LABEL_32:
  if ( v19 )
    CloseHandle(v19);
  if ( !LastError )
  {
    v12 = v49;
    goto LABEL_39;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v37 = -127;
    goto LABEL_6;
  }
LABEL_44:
  if ( Src[1] )
    LocalFree(Src[1]);
  return LastError;
}

```

## disassembly

```asm
0x180013350  mov     rax, rsp
0x180013353  mov     [rax+10h], rbx
0x180013357  mov     [rax+20h], r9
0x18001335b  mov     [rax+18h], r8
0x18001335f  push    rbp
0x180013360  push    rsi
0x180013361  push    rdi
0x180013362  push    r12
0x180013364  push    r13
0x180013366  push    r14
0x180013368  push    r15
0x18001336a  lea     rbp, [rax-3Fh]
0x18001336e  sub     rsp, 0B0h
0x180013375  xor     eax, eax
0x180013377  mov     [rbp+37h+var_68], rcx
0x18001337b  neg     [rbp+37h+arg_20]
0x18001337e  lea     r15, WPP_GLOBAL_Control
0x180013385  mov     rcx, [rbp+37h+arg_30]
0x180013389  xorps   xmm0, xmm0
0x18001338c  sbb     r13d, r13d
0x18001338f  mov     [rbp+37h+var_40], rax
0x180013393  and     r13d, 3
0x180013397  mov     [rbp+37h+var_6C], eax
0x18001339a  inc     r13d
0x18001339d  mov     [rbp+37h+var_8C], eax
0x1800133a0  cmp     [rbp+37h+arg_28], 0
0x1800133a4  mov     rdi, r9
0x1800133a7  mov     [rbp+37h+var_5C], eax
0x1800133aa  mov     rsi, r8
0x1800133ad  mov     eax, [rbp+37h+arg_38]
0x1800133b0  movups  xmmword ptr [rbp+37h+var_50], xmm0
0x1800133b4  mov     dword ptr [rbp+37h+var_50], 18h
0x1800133bb  movups  xmmword ptr [rbp+37h+Src], xmm0
0x1800133bf  mov     [rbp+37h+var_70], edx
0x1800133c2  mov     [rbp+37h+var_60], eax
0x1800133c5  mov     [rbp+37h+var_58], rcx
0x1800133c9  mov     [rbp+37h+var_90], 11h
0x1800133d0  jz      loc_18001346B
0x1800133d6  lea     rax, aXt5rzw5qvvbrvp; "xT5rZW5qVVbrvpuA"
0x1800133dd  mov     [rbp+37h+var_88], rax
0x1800133e1  lea     r9, [rbp+37h+var_60]; int
0x1800133e5  lea     rax, [rbp+37h+Src]
0x1800133e9  mov     [rsp+40h], rax; __int64
0x1800133ee  lea     r8, [rbp+37h+var_90]; int
0x1800133f2  mov     eax, [rbp+37h+arg_40]
0x1800133f8  lea     rdx, aPrivateKey; "Private Key"
0x1800133ff  mov     [rsp+0E0h+dwMilliseconds], eax; dwMilliseconds
0x180013403  lea     rcx, [rbp+37h+var_70]; int
0x180013407  lea     rax, [rbp+37h+var_50]
0x18001340b  mov     dword ptr [rsp+0E0h+var_B0], r13d; int
0x180013410  mov     [rsp+0E0h+var_B8], rax; __int64
0x180013415  call    MyCryptProtectData
0x18001341a  mov     ebx, eax
0x18001341c  test    eax, eax
0x18001341e  jz      loc_18001365C
0x180013424  mov     rcx, cs:WPP_GLOBAL_Control
0x18001342b  cmp     rcx, r15
0x18001342e  jz      loc_1800136BE
0x180013434  test    byte ptr [rcx+1Ch], 1
0x180013438  jz      loc_1800136BE
0x18001343e  mov     dword ptr [rsp+0E0h+var_B0], 26Bh
0x180013446  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001344d  mov     [rsp+0E0h+var_B8], rax
0x180013452  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180013456  mov     rcx, [rcx+10h]
0x18001345a  lea     r9, aStatus; "Status"
0x180013461  call    WPP_SF_sDsd
0x180013466  jmp     loc_1800136BE
0x18001346b  xor     edi, edi
0x18001346d  lea     rdx, a6jnkd5j3zdqdtr; "6jnkd5J3ZdQDtrsu"
0x180013474  xor     r12d, r12d
0x180013477  mov     [rbp+37h+var_88], rdx
0x18001347b  mov     [rbp+37h+hObject], rdi
0x18001347f  cmp     [rbp+37h+arg_40], edi
0x180013485  jz      short loc_1800134FA
0x180013487  lea     rcx, [rbp+37h+hObject]
0x18001348b  call    RevertToLocalSystem
0x180013490  mov     ebx, eax
0x180013492  test    eax, eax
0x180013494  jz      short loc_1800134E9
0x180013496  mov     rcx, cs:WPP_GLOBAL_Control
0x18001349d  cmp     rcx, r15
0x1800134a0  jz      short loc_1800134D0
0x1800134a2  test    byte ptr [rcx+1Ch], 1
0x1800134a6  jz      short loc_1800134D0
0x1800134a8  mov     rcx, [rcx+10h]
0x1800134ac  lea     r14, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800134b3  mov     dword ptr [rsp+0E0h+var_B0], 17Ah
0x1800134bb  lea     r9, aStatus; "Status"
0x1800134c2  mov     [rsp+0E0h+var_B8], r14
0x1800134c7  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800134cb  call    WPP_SF_sDsd
0x1800134d0  mov     ecx, ebx; Status
0x1800134d2  call    cs:__imp_RtlNtStatusToDosError
0x1800134d9  nop     dword ptr [rax+rax+00h]
0x1800134de  mov     rdi, [rbp+37h+hObject]
0x1800134e2  mov     ebx, eax
0x1800134e4  jmp     loc_180013621
0x1800134e9  mov     rdi, [rbp+37h+hObject]
0x1800134ed  mov     r12d, 1
0x1800134f3  mov     eax, [rbp+37h+arg_38]
0x1800134f6  mov     rcx, [rbp+37h+arg_30]
0x1800134fa  xor     esi, esi
0x1800134fc  lea     r14, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013503  lea     r15d, [rsi+0Ah]
0x180013507  lea     rdx, [rbp+37h+Src]
0x18001350b  xor     r9d, r9d
0x18001350e  mov     [rsp+40h], rdx
0x180013513  lea     r8, [rbp+37h+var_90]
0x180013517  mov     [rsp+0E0h+dwMilliseconds], eax
0x18001351b  lea     rdx, aPrivateKeyProp; "Private Key Properties"
0x180013522  mov     qword ptr [rsp+0E0h+var_B0], rcx
0x180013527  lea     rax, [rbp+37h+var_50]
0x18001352b  mov     dword ptr [rsp+0E0h+var_B8], r13d
0x180013530  lea     rcx, [rbp+37h+var_70]
0x180013534  mov     [rsp+0E0h+var_C0], rax
0x180013539  call    cs:__imp_CryptProtectDataNoUI
0x180013540  nop     dword ptr [rax+rax+00h]
0x180013545  test    eax, eax
0x180013547  jnz     loc_1800135D6
0x18001354d  call    cs:__imp_GetLastError
0x180013554  nop     dword ptr [rax+rax+00h]
0x180013559  mov     ebx, eax
0x18001355b  mov     rcx, cs:WPP_GLOBAL_Control
0x180013562  lea     rax, WPP_GLOBAL_Control
0x180013569  cmp     rcx, rax
0x18001356c  jz      short loc_180013595
0x18001356e  test    byte ptr [rcx+1Ch], 1
0x180013572  jz      short loc_180013595
0x180013574  mov     rcx, [rcx+10h]
0x180013578  lea     r9, aDwsts; "dwSts"
0x18001357f  mov     dword ptr [rsp+0E0h+var_B0], 196h
0x180013587  mov     [rsp+0E0h+var_B8], r14
0x18001358c  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x180013590  call    WPP_SF_sDsd
0x180013595  mov     eax, ebx
0x180013597  sub     eax, 6B5h
0x18001359c  jz      short loc_1800135CF
0x18001359e  cmp     eax, 6
0x1800135a1  jnz     short loc_1800135D8
0x1800135a3  cmp     esi, 5
0x1800135a6  jnb     short loc_1800135C8
0x1800135a8  mov     ecx, r15d; dwMilliseconds
0x1800135ab  call    cs:__imp_Sleep
0x1800135b2  nop     dword ptr [rax+rax+00h]
0x1800135b7  mov     eax, [rbp+37h+arg_38]
0x1800135ba  add     r15d, r15d
0x1800135bd  mov     rcx, [rbp+37h+arg_30]
0x1800135c1  inc     esi
0x1800135c3  jmp     loc_180013507
0x1800135c8  mov     ebx, 6BBh
0x1800135cd  jmp     short loc_1800135D8
0x1800135cf  mov     ebx, 426h
0x1800135d4  jmp     short loc_1800135D8
0x1800135d6  xor     ebx, ebx
0x1800135d8  test    r12d, r12d
0x1800135db  jz      short loc_180013616
0x1800135dd  mov     rcx, rdi
0x1800135e0  call    RevertBackToCallerToken
0x1800135e5  mov     esi, eax
0x1800135e7  test    eax, eax
0x1800135e9  jns     short loc_180013616
0x1800135eb  mov     r9d, 1B9h
0x1800135f1  lea     rdx, aStatus; "Status"
0x1800135f8  mov     r8, r14
0x1800135fb  mov     ecx, eax
0x1800135fd  call    DebugTraceError
0x180013602  test    ebx, ebx
0x180013604  jnz     short loc_180013616
0x180013606  mov     ecx, esi; Status
0x180013608  call    cs:__imp_RtlNtStatusToDosError
0x18001360f  nop     dword ptr [rax+rax+00h]
0x180013614  mov     ebx, eax
0x180013616  mov     rsi, [rbp+37h+arg_10]
0x18001361a  lea     r15, WPP_GLOBAL_Control
0x180013621  test    rdi, rdi
0x180013624  jz      short loc_180013635
0x180013626  mov     rcx, rdi; hObject
0x180013629  call    cs:__imp_CloseHandle
0x180013630  nop     dword ptr [rax+rax+00h]
0x180013635  test    ebx, ebx
0x180013637  jz      short loc_180013658
0x180013639  mov     rcx, cs:WPP_GLOBAL_Control
0x180013640  cmp     rcx, r15
0x180013643  jz      short loc_1800136BE
0x180013645  test    byte ptr [rcx+1Ch], 1
0x180013649  jz      short loc_1800136BE
0x18001364b  mov     dword ptr [rsp+0E0h+var_B0], 281h
0x180013653  jmp     loc_180013446
0x180013658  mov     rdi, [rbp+37h+arg_18]
0x18001365c  mov     ecx, dword ptr [rbp+37h+Src]
0x18001365f  call    SafeAllocaAllocateFromHeap
0x180013664  mov     rbx, rax
0x180013667  test    rax, rax
0x18001366a  jnz     short loc_1800136A4
0x18001366c  mov     ebx, 8009000Eh
0x180013671  mov     rcx, cs:WPP_GLOBAL_Control
0x180013678  cmp     rcx, r15
0x18001367b  jz      short loc_1800136BE
0x18001367d  test    byte ptr [rcx+1Ch], 1
0x180013681  jz      short loc_1800136BE
0x180013683  mov     dword ptr [rsp+0E0h+var_B0], 28Bh
0x18001368b  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013692  mov     [rsp+0E0h+var_B8], rax
0x180013697  mov     dword ptr [rsp+0E0h+var_C0], 8009000Eh
0x18001369f  jmp     loc_180013456
0x1800136a4  mov     r8d, dword ptr [rbp+37h+Src]; Size
0x1800136a8  mov     rcx, rbx; void *
0x1800136ab  mov     rdx, [rbp+37h+Src+8]; Src
0x1800136af  call    memcpy_0
0x1800136b4  mov     eax, dword ptr [rbp+37h+Src]
0x1800136b7  mov     [rsi], rbx
0x1800136ba  xor     ebx, ebx
0x1800136bc  mov     [rdi], eax
0x1800136be  mov     rcx, [rbp+37h+Src+8]; hMem
0x1800136c2  test    rcx, rcx
0x1800136c5  jz      short loc_1800136D3
0x1800136c7  call    cs:__imp_LocalFree
0x1800136ce  nop     dword ptr [rax+rax+00h]
0x1800136d3  mov     eax, ebx
0x1800136d5  mov     rbx, [rsp+0E0h+arg_8]
0x1800136dd  add     rsp, 0B0h
0x1800136e4  pop     r15
0x1800136e6  pop     r14
0x1800136e8  pop     r13
0x1800136ea  pop     r12
0x1800136ec  pop     rdi
0x1800136ed  pop     rsi
0x1800136ee  pop     rbp
0x1800136ef  retn
```
