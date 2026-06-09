# BthServReplicatePolicies

- ea: `0x18001e1dc`
- end: `0x18001e890`
- name: `BthServReplicatePolicies`
- size: `1716`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001dd58`

## callees

- `0x1800026dc`
- `0x18001e028`
- `0x18001e1dc`
- `0x18001e8b4`
- `0x180034b50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e392`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e590`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e78b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e392`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e590`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001e78b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e26b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e48a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e68c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e26b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e48a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e68c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e2e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e4ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e6f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e2e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e4ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e6f2`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e320`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e424`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e52c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e627`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e725`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e813`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e320`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e424`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e52c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e627`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e725`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e813`

## string_xrefs

- `0x18001e765`: `ServicesAllowedList`
- `0x18001e7bb`: `ServicesAllowedList`
- `0x18001e70a`: `PM_ServicesAllowedList`
- `0x18001e807`: `PM_ServicesAllowedList`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BthServReplicatePolicies(HKEY hKey)
{
  char v1; // di
  int v3; // r15d
  _WORD *lpData; // rsi
  int v5; // ebx
  unsigned __int16 v6; // bx
  _WORD *v7; // rax
  unsigned __int64 v8; // rbx
  int v9; // edx
  int v10; // r8d
  int v11; // edx
  int v12; // r8d
  int v13; // edx
  int v14; // r8d
  void *v15; // rsi
  int v16; // r13d
  int v17; // ebx
  int v18; // ebp
  size_t v19; // rbx
  void *v20; // rax
  int v21; // edx
  int v22; // r8d
  DWORD cbData; // eax
  HKEY v24; // r13
  int v25; // edx
  int v26; // r8d
  int v27; // edx
  int v28; // r8d
  void *v29; // rbp
  int v30; // ebx
  int v31; // r15d
  size_t v32; // rsi
  void *v33; // rax
  int v34; // edx
  int v35; // r8d
  int v36; // edx
  LSTATUS v37; // ebx
  int v38; // r8d
  int v39; // edx
  int v40; // r8d
  unsigned __int16 v42; // [rsp+62h] [rbp-36h]

  v1 = 1;
  BthServPushPolicyValue(hKey, 1);
  BthServPushPolicyValue(hKey, 2);
  BthServPushPolicyValue(hKey, 4);
  BthServPushPolicyValue(hKey, 8);
  BthServPushPolicyValue(hKey, 16);
  BthServPushPolicyValue(hKey, 32);
  BthServPushPolicyValue(hKey, 512);
  BthServPushPolicyValue(hKey, 2048);
  v42 = 0;
  EnterCriticalSection(&g_PolicyLock);
  v3 = -1073741275;
  if ( (dword_180046FA4 & 0x40) != 0 && word_180046F78 )
  {
    v6 = *(_WORD *)algn_180046F7A;
    v7 = o_malloc_0(*(unsigned __int16 *)algn_180046F7A);
    lpData = v7;
    if ( v7 )
    {
      v42 = v6;
      v8 = (unsigned __int16)word_180046F78;
      memcpy_0(v7, Block, (unsigned __int16)word_180046F78);
      lpData[v8 >> 1] = 0;
      v5 = 0;
    }
    else
    {
      v5 = -1073741670;
    }
  }
  else
  {
    lpData = 0;
    v5 = -1073741275;
  }
  LeaveCriticalSection(&g_PolicyLock);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(v9) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
    {
      LOBYTE(v9) = 0;
    }
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    if ( RegSetKeyValueW(hKey, 0, L"PM_LocalDeviceName", 1u, &qword_18003DE90, 2u) < 0 )
    {
      LOBYTE(v13) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          v14,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
    }
  }
  else
  {
    if ( RegSetKeyValueW(hKey, 0, L"PM_LocalDeviceName", 1u, lpData, v42) < 0 )
    {
      LOBYTE(v11) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
    }
    free(lpData);
  }
  v15 = 0;
  v16 = 0;
  EnterCriticalSection(&g_PolicyLock);
  if ( (dword_180046FA4 & 0x80u) != 0 && dword_180046FA8 )
  {
    v18 = dword_180046FA8;
    v19 = 8LL * (unsigned int)dword_180046FA8;
    v20 = o_malloc_0(v19);
    v15 = v20;
    if ( v20 )
    {
      v16 = v18;
      memcpy_0(v20, *(&Block + 1), v19);
      v17 = 0;
    }
    else
    {
      v17 = -1073741670;
    }
  }
  else
  {
    v17 = -1073741275;
  }
  LeaveCriticalSection(&g_PolicyLock);
  if ( v17 < 0 )
  {
    LOBYTE(v21) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    if ( (_BYTE)v21 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v24 = hKey;
    if ( RegSetKeyValueW(hKey, 0, L"PM_DevicesAllowedList", 3u, &qword_18003DE90, 2u) < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (LOBYTE(v27) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
      {
        LOBYTE(v27) = 0;
      }
      if ( (_BYTE)v27 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v27,
          v28,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
    }
  }
  else
  {
    cbData = 8 * v16;
    v24 = hKey;
    if ( RegSetKeyValueW(hKey, 0, L"PM_DevicesAllowedList", 3u, v15, cbData) < 0 )
    {
      LOBYTE(v25) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      if ( (_BYTE)v25 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v25,
          v26,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
    }
    free(v15);
  }
  v29 = 0;
  v30 = 0;
  EnterCriticalSection(&g_PolicyLock);
  if ( (dword_180046FA4 & 0x100) != 0 && dword_180046FAC )
  {
    v31 = dword_180046FAC;
    v32 = 16LL * (unsigned int)dword_180046FAC;
    v33 = o_malloc_0(v32);
    v29 = v33;
    if ( v33 )
    {
      v30 = v31;
      memcpy_0(v33, Src, v32);
      v3 = 0;
    }
    else
    {
      v3 = -1073741670;
    }
  }
  LeaveCriticalSection(&g_PolicyLock);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (LOBYTE(v34) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
    {
      LOBYTE(v34) = 0;
    }
    if ( (_BYTE)v34 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v35) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, v35, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v37 = RegSetKeyValueW(v24, 0, L"PM_ServicesAllowedList", 3u, &qword_18003DE90, 2u);
    if ( v37 < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        v1 = 0;
      if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v39) = v1;
        LOBYTE(v40) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v39,
          v40,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
    }
  }
  else
  {
    v37 = RegSetKeyValueW(v24, 0, L"PM_ServicesAllowedList", 3u, v29, 16 * v30);
    if ( v37 < 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        v1 = 0;
      if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v36) = v1;
        LOBYTE(v38) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v36,
          v38,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
    }
    free(v29);
  }
  return (unsigned int)v37;
}

```

## disassembly

```asm
0x18001e1dc  mov     rax, rsp
0x18001e1df  mov     [rax+10h], rbx
0x18001e1e3  mov     [rax+18h], rbp
0x18001e1e7  mov     [rax+20h], rsi
0x18001e1eb  mov     [rax+8], rcx
0x18001e1ef  push    rdi
0x18001e1f0  push    r12
0x18001e1f2  push    r13
0x18001e1f4  push    r14
0x18001e1f6  push    r15
0x18001e1f8  sub     rsp, 70h
0x18001e1fc  mov     edi, 1
0x18001e201  mov     r13, rcx
0x18001e204  mov     edx, edi
0x18001e206  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001e20b  lea     edx, [rdi+1]
0x18001e20e  mov     rcx, r13
0x18001e211  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001e216  lea     edx, [rdi+3]
0x18001e219  mov     rcx, r13
0x18001e21c  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001e221  lea     edx, [rdi+7]
0x18001e224  mov     rcx, r13
0x18001e227  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001e22c  lea     edx, [rdi+0Fh]
0x18001e22f  mov     rcx, r13
0x18001e232  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001e237  lea     edx, [rdi+1Fh]
0x18001e23a  mov     rcx, r13
0x18001e23d  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001e242  mov     edx, 200h
0x18001e247  mov     rcx, r13
0x18001e24a  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001e24f  mov     edx, 800h
0x18001e254  mov     rcx, r13
0x18001e257  call    ?BthServPushPolicyValue@@YAXPEAUHKEY__@@W4BthPolicy@@@Z; BthServPushPolicyValue(HKEY__ *,BthPolicy)
0x18001e25c  xorps   xmm0, xmm0
0x18001e25f  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e266  movups  xmmword ptr [rsp+98h+var_38], xmm0
0x18001e26b  call    cs:__imp_EnterCriticalSection
0x18001e272  nop     dword ptr [rax+rax+00h]
0x18001e277  xor     r12d, r12d
0x18001e27a  mov     r15d, 0C0000225h
0x18001e280  test    byte ptr cs:dword_180046FA4, 40h
0x18001e287  jz      short loc_18001E293
0x18001e289  cmp     word ptr cs:ymmword_180046F70+8, r12w
0x18001e291  jnz     short loc_18001E29D
0x18001e293  mov     rsi, [rsp+98h+var_38+8]
0x18001e298  mov     ebx, r15d
0x18001e29b  jmp     short loc_18001E2E1
0x18001e29d  lea     rbp, ymmword_180046F70+8
0x18001e2a4  movzx   ebx, word ptr [rbp+2]
0x18001e2a8  mov     ecx, ebx; Size
0x18001e2aa  call    _o_malloc_0
0x18001e2af  mov     rsi, rax
0x18001e2b2  test    rax, rax
0x18001e2b5  jz      short loc_18001E2DC
0x18001e2b7  mov     rdx, [rbp+8]; Src
0x18001e2bb  mov     rcx, rax; void *
0x18001e2be  mov     word ptr [rsp+98h+var_38+2], bx
0x18001e2c3  movzx   ebx, word ptr [rbp+0]
0x18001e2c7  mov     r8d, ebx; Size
0x18001e2ca  call    memcpy_0
0x18001e2cf  shr     rbx, 1
0x18001e2d2  mov     [rsi+rbx*2], r12w
0x18001e2d7  mov     ebx, r12d
0x18001e2da  jmp     short loc_18001E2E1
0x18001e2dc  mov     ebx, 0C000009Ah
0x18001e2e1  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e2e8  call    cs:__imp_LeaveCriticalSection
0x18001e2ef  nop     dword ptr [rax+rax+00h]
0x18001e2f4  lea     rax, qword_18003DE90
0x18001e2fb  test    ebx, ebx
0x18001e2fd  js      loc_18001E3A3
0x18001e303  movzx   eax, word ptr [rsp+98h+var_38+2]
0x18001e308  lea     r8, aPmLocaldevicen; "PM_LocalDeviceName"
0x18001e30f  mov     [rsp+98h+cbData], eax; cbData
0x18001e313  mov     r9d, edi; dwType
0x18001e316  xor     edx, edx; lpSubKey
0x18001e318  mov     [rsp+98h+lpData], rsi; lpData
0x18001e31d  mov     rcx, r13; hKey
0x18001e320  call    cs:__imp_RegSetKeyValueW
0x18001e327  nop     dword ptr [rax+rax+00h]
0x18001e32c  lea     r14, WPP_GLOBAL_Control
0x18001e333  lea     r12, WPP_RECORDER_INITIALIZED
0x18001e33a  test    eax, eax
0x18001e33c  jns     short loc_18001E38F
0x18001e33e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e345  cmp     rcx, r14
0x18001e348  jz      short loc_18001E355
0x18001e34a  cmp     byte ptr [rcx+19h], 2
0x18001e34e  jb      short loc_18001E355
0x18001e350  mov     dl, dil
0x18001e353  jmp     short loc_18001E357
0x18001e355  xor     dl, dl
0x18001e357  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001e35e  setnz   r8b
0x18001e362  test    dl, dl
0x18001e364  jnz     short loc_18001E36B
0x18001e366  test    r8b, r8b
0x18001e369  jz      short loc_18001E38F
0x18001e36b  mov     r9, [rcx+28h]
0x18001e36f  lea     rbp, aLocaldevicenam; "LocalDeviceName"
0x18001e376  mov     rcx, [rcx+10h]
0x18001e37a  mov     [rsp+98h+var_48], eax
0x18001e37e  mov     [rsp+98h+var_50], rbp
0x18001e383  mov     [rsp+98h+var_68], 0Ch
0x18001e38a  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001e38f  mov     rcx, rsi; Block
0x18001e392  call    cs:__imp_free
0x18001e399  nop     dword ptr [rax+rax+00h]
0x18001e39e  jmp     loc_18001E47E
0x18001e3a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3aa  lea     r14, WPP_GLOBAL_Control
0x18001e3b1  cmp     rcx, r14
0x18001e3b4  jz      short loc_18001E3BF
0x18001e3b6  cmp     byte ptr [rcx+19h], 3
0x18001e3ba  mov     dl, dil
0x18001e3bd  jnb     short loc_18001E3C2
0x18001e3bf  mov     dl, r12b
0x18001e3c2  lea     r12, WPP_RECORDER_INITIALIZED
0x18001e3c9  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001e3d0  lea     rbp, aLocaldevicenam; "LocalDeviceName"
0x18001e3d7  setnz   r8b
0x18001e3db  test    dl, dl
0x18001e3dd  jnz     short loc_18001E3E4
0x18001e3df  test    r8b, r8b
0x18001e3e2  jz      short loc_18001E408
0x18001e3e4  mov     r9, [rcx+28h]
0x18001e3e8  mov     rcx, [rcx+10h]
0x18001e3ec  mov     [rsp+98h+var_48], ebx
0x18001e3f0  mov     [rsp+98h+var_50], rbp
0x18001e3f5  mov     [rsp+98h+var_68], 0Dh
0x18001e3fc  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001e401  lea     rax, qword_18003DE90
0x18001e408  mov     [rsp+98h+cbData], 2; cbData
0x18001e410  lea     r8, aPmLocaldevicen; "PM_LocalDeviceName"
0x18001e417  mov     r9d, edi; dwType
0x18001e41a  mov     [rsp+98h+lpData], rax; lpData
0x18001e41f  xor     edx, edx; lpSubKey
0x18001e421  mov     rcx, r13; hKey
0x18001e424  call    cs:__imp_RegSetKeyValueW
0x18001e42b  nop     dword ptr [rax+rax+00h]
0x18001e430  test    eax, eax
0x18001e432  jns     short loc_18001E47E
0x18001e434  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e43b  cmp     rcx, r14
0x18001e43e  jz      short loc_18001E44B
0x18001e440  cmp     byte ptr [rcx+19h], 2
0x18001e444  jb      short loc_18001E44B
0x18001e446  mov     dl, dil
0x18001e449  jmp     short loc_18001E44D
0x18001e44b  xor     dl, dl
0x18001e44d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001e454  setnz   r8b
0x18001e458  test    dl, dl
0x18001e45a  jnz     short loc_18001E461
0x18001e45c  test    r8b, r8b
0x18001e45f  jz      short loc_18001E47E
0x18001e461  mov     r9, [rcx+28h]
0x18001e465  mov     rcx, [rcx+10h]
0x18001e469  mov     [rsp+98h+var_48], eax
0x18001e46d  mov     [rsp+98h+var_50], rbp
0x18001e472  mov     [rsp+98h+var_68], 0Eh
0x18001e479  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001e47e  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e485  xor     esi, esi
0x18001e487  xor     r13d, r13d
0x18001e48a  call    cs:__imp_EnterCriticalSection
0x18001e491  nop     dword ptr [rax+rax+00h]
0x18001e496  test    byte ptr cs:dword_180046FA4, 80h
0x18001e49d  jz      short loc_18001E4A9
0x18001e49f  mov     eax, cs:dword_180046FA8
0x18001e4a5  test    eax, eax
0x18001e4a7  jnz     short loc_18001E4AE
0x18001e4a9  mov     ebx, r15d
0x18001e4ac  jmp     short loc_18001E4E6
0x18001e4ae  mov     rbx, rax
0x18001e4b1  mov     rbp, rax
0x18001e4b4  shl     rbx, 3
0x18001e4b8  mov     rcx, rbx; Size
0x18001e4bb  call    _o_malloc_0
0x18001e4c0  mov     rsi, rax
0x18001e4c3  test    rax, rax
0x18001e4c6  jz      short loc_18001E4E1
0x18001e4c8  mov     rdx, qword ptr cs:ymmword_180046F70+18h; Src
0x18001e4cf  mov     r8, rbx; Size
0x18001e4d2  mov     rcx, rax; void *
0x18001e4d5  mov     r13d, ebp
0x18001e4d8  call    memcpy_0
0x18001e4dd  xor     ebx, ebx
0x18001e4df  jmp     short loc_18001E4E6
0x18001e4e1  mov     ebx, 0C000009Ah
0x18001e4e6  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e4ed  call    cs:__imp_LeaveCriticalSection
0x18001e4f4  nop     dword ptr [rax+rax+00h]
0x18001e4f9  test    ebx, ebx
0x18001e4fb  js      loc_18001E5A3
0x18001e501  lea     eax, ds:0[r13*8]
0x18001e509  mov     r9d, 3; dwType
0x18001e50f  mov     r13, [rsp+98h+hKey]
0x18001e517  lea     r8, aPmDevicesallow; "PM_DevicesAllowedList"
0x18001e51e  mov     [rsp+98h+cbData], eax; cbData
0x18001e522  mov     rcx, r13; hKey
0x18001e525  xor     edx, edx; lpSubKey
0x18001e527  mov     [rsp+98h+lpData], rsi; lpData
0x18001e52c  call    cs:__imp_RegSetKeyValueW
0x18001e533  nop     dword ptr [rax+rax+00h]
0x18001e538  test    eax, eax
0x18001e53a  jns     short loc_18001E58D
0x18001e53c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e543  cmp     rcx, r14
0x18001e546  jz      short loc_18001E553
0x18001e548  cmp     byte ptr [rcx+19h], 2
0x18001e54c  jb      short loc_18001E553
0x18001e54e  mov     dl, dil
0x18001e551  jmp     short loc_18001E555
0x18001e553  xor     dl, dl
0x18001e555  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001e55c  setnz   r8b
0x18001e560  test    dl, dl
0x18001e562  jnz     short loc_18001E569
0x18001e564  test    r8b, r8b
0x18001e567  jz      short loc_18001E58D
0x18001e569  mov     r9, [rcx+28h]
0x18001e56d  lea     rbp, aDevicesallowed; "DevicesAllowedList"
0x18001e574  mov     rcx, [rcx+10h]
0x18001e578  mov     [rsp+98h+var_48], eax
0x18001e57c  mov     [rsp+98h+var_50], rbp
0x18001e581  mov     [rsp+98h+var_68], 0Fh
0x18001e588  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001e58d  mov     rcx, rsi; Block
0x18001e590  call    cs:__imp_free
0x18001e597  nop     dword ptr [rax+rax+00h]
0x18001e59c  xor     esi, esi
0x18001e59e  jmp     loc_18001E680
0x18001e5a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5aa  cmp     rcx, r14
0x18001e5ad  jz      short loc_18001E5BC
0x18001e5af  cmp     byte ptr [rcx+19h], 3
0x18001e5b3  jb      short loc_18001E5BC
0x18001e5b5  mov     dl, dil
0x18001e5b8  xor     esi, esi
0x18001e5ba  jmp     short loc_18001E5C1
0x18001e5bc  xor     esi, esi
0x18001e5be  mov     dl, sil
0x18001e5c1  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001e5c8  lea     rbp, aDevicesallowed; "DevicesAllowedList"
0x18001e5cf  setnz   r8b
0x18001e5d3  test    dl, dl
0x18001e5d5  jnz     short loc_18001E5DC
0x18001e5d7  test    r8b, r8b
0x18001e5da  jz      short loc_18001E5F9
0x18001e5dc  mov     r9, [rcx+28h]
0x18001e5e0  mov     rcx, [rcx+10h]
0x18001e5e4  mov     [rsp+98h+var_48], ebx
0x18001e5e8  mov     [rsp+98h+var_50], rbp
0x18001e5ed  mov     [rsp+98h+var_68], 10h
0x18001e5f4  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001e5f9  mov     r13, [rsp+98h+hKey]
0x18001e601  lea     rax, qword_18003DE90
0x18001e608  mov     rcx, r13; hKey
0x18001e60b  mov     [rsp+98h+cbData], 2; cbData
0x18001e613  mov     r9d, 3; dwType
0x18001e619  mov     [rsp+98h+lpData], rax; lpData
0x18001e61e  lea     r8, aPmDevicesallow; "PM_DevicesAllowedList"
0x18001e625  xor     edx, edx; lpSubKey
0x18001e627  call    cs:__imp_RegSetKeyValueW
0x18001e62e  nop     dword ptr [rax+rax+00h]
0x18001e633  test    eax, eax
0x18001e635  jns     short loc_18001E680
0x18001e637  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e63e  cmp     rcx, r14
0x18001e641  jz      short loc_18001E64C
0x18001e643  cmp     byte ptr [rcx+19h], 2
0x18001e647  mov     dl, dil
0x18001e64a  jnb     short loc_18001E64F
0x18001e64c  mov     dl, sil
0x18001e64f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001e656  setnz   r8b
0x18001e65a  test    dl, dl
0x18001e65c  jnz     short loc_18001E663
0x18001e65e  test    r8b, r8b
0x18001e661  jz      short loc_18001E680
0x18001e663  mov     r9, [rcx+28h]
0x18001e667  mov     rcx, [rcx+10h]
0x18001e66b  mov     [rsp+98h+var_48], eax
0x18001e66f  mov     [rsp+98h+var_50], rbp
0x18001e674  mov     [rsp+98h+var_68], 11h
0x18001e67b  call    WPP_RECORDER_AND_TRACE_SF_sSD
0x18001e680  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e687  mov     rbp, rsi
0x18001e68a  mov     ebx, esi
0x18001e68c  call    cs:__imp_EnterCriticalSection
0x18001e693  nop     dword ptr [rax+rax+00h]
0x18001e698  test    cs:dword_180046FA4, 100h
0x18001e6a2  jz      short loc_18001E6EB
0x18001e6a4  mov     eax, cs:dword_180046FAC
0x18001e6aa  test    eax, eax
0x18001e6ac  jz      short loc_18001E6EB
  ... truncated ...
```
