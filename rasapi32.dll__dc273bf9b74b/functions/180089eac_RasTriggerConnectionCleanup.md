# RasTriggerConnectionCleanup

- ea: `0x180089eac`
- end: `0x18008a1f1`
- name: `RasTriggerConnectionCleanup`
- size: `837`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180087230`
- `0x18008fec0`
- `0x180090f60`
- `0x180097f4c`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x18008491c`
- `0x180089eac`
- `0x1800a749c`
- `0x1800af490`

## import_xrefs

- `msvcrt!free` at `0x180089fd6`
- `msvcrt!free` at `0x180089ff5`
- `msvcrt!free` at `0x180089fd6`
- `msvcrt!free` at `0x180089ff5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180089f42`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180089f83`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180089f42`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180089f83`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180089f52`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180089f93`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180089f52`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180089f93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a014`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a0a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a0d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a167`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a014`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a0a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a0d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008a167`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008a158`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18008a158`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089f5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089f6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089fa0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089fb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089fc4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089f5f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089f6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089fa0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089fb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180089fc4`
- `WS2_32!__imp_WSACleanup` at `0x18008a02f`
- `WS2_32!__imp_WSACleanup` at `0x18008a02f`
- `eappcfg!EapHostPeerFreeMemory` at `0x18008a075`
- `eappcfg!EapHostPeerFreeMemory` at `0x18008a075`

## pseudocode

```c
void __fastcall RasTriggerConnectionCleanup(__int64 *a1)
{
  _QWORD *v2; // rcx
  __int64 v3; // rbx
  HANDLE *v4; // rdi
  _DWORD *v5; // rsi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  unsigned int v11; // eax
  BYTE *v12; // rcx
  _BYTE *v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rcx
  _BYTE *v16; // rax
  unsigned int v17; // eax
  __int64 v18; // rdx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 695, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 && (v3 = *a1) != 0 )
  {
    v4 = (HANDLE *)(v3 + 10648);
    v5 = (_DWORD *)ValidateHrasconn(*(_QWORD *)(v3 + 10408));
    *(_DWORD *)(v3 + 10616) = 1;
    if ( *(_QWORD *)(v3 + 10664) )
    {
      SetEvent(*v4);
      WaitForSingleObject(*(HANDLE *)(v3 + 10664), 0xFFFFFFFF);
      CloseHandle(*(HANDLE *)(v3 + 10664));
    }
    if ( *v4 )
      CloseHandle(*v4);
    if ( *(_QWORD *)(v3 + 10672) )
    {
      SetEvent(*(HANDLE *)(v3 + 10656));
      WaitForSingleObject(*(HANDLE *)(v3 + 10672), 0xFFFFFFFF);
      CloseHandle(*(HANDLE *)(v3 + 10672));
    }
    v6 = *(void **)(v3 + 10656);
    if ( v6 )
      CloseHandle(v6);
    v7 = *(void **)(v3 + 10680);
    if ( v7 )
      CloseHandle(v7);
    v8 = *(void **)(v3 + 10536);
    if ( v8 )
    {
      free(v8);
      *(_QWORD *)(v3 + 10536) = 0;
      *(_DWORD *)(v3 + 10532) = 0;
    }
    v9 = *(void **)(v3 + 10524);
    if ( v9 )
    {
      free(v9);
      *(_QWORD *)(v3 + 10524) = 0;
      *(_DWORD *)(v3 + 10520) = 0;
    }
    v10 = *(void **)(v3 + 10548);
    if ( v10 )
    {
      LocalFree(v10);
      *(_QWORD *)(v3 + 10548) = 0;
      *(_DWORD *)(v3 + 10544) = 0;
    }
    if ( *(_DWORD *)(v3 + 10608) )
    {
      v11 = WSACleanup();
      if ( v11 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 698, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v11);
        }
      }
    }
    v12 = *(BYTE **)(v3 + 10632);
    if ( v12 )
    {
      EapHostPeerFreeMemory(v12);
      *(_QWORD *)(v3 + 10632) = 0;
    }
    v13 = *(_BYTE **)(v3 + 10432);
    v14 = 2120;
    if ( v13 )
    {
      v15 = 2120;
      do
      {
        *v13++ = 0;
        --v15;
      }
      while ( v15 );
      LocalFree(*(HLOCAL *)(v3 + 10432));
      *(_QWORD *)(v3 + 10432) = 0;
    }
    v16 = *(_BYTE **)(v3 + 10440);
    if ( v16 )
    {
      do
      {
        *v16++ = 0;
        --v14;
      }
      while ( v14 );
      LocalFree(*(HLOCAL *)(v3 + 10440));
      *(_QWORD *)(v3 + 10440) = 0;
    }
    if ( v5 && ((v5[2] & 0x1000) != 0 || v5[1400] == 2 && !v5[2] && !v5[1404]) )
      DwSignalAutoDisconnectToVan((wchar_t *)(v3 + 304));
    v17 = RasRemoveToastNotification(*(_QWORD *)(v3 + 10696));
    if ( v17
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 699, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids, v17);
    }
    GlobalFree(*(HGLOBAL *)(v3 + 10696));
    *(_DWORD *)(v3 + 10556) = 0;
    LocalFree((HLOCAL)v3);
    *a1 = 0;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      v18 = 700;
LABEL_61:
      WPP_SF_(v2[2], v18, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
    }
  }
  else if ( v2 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v2 + 7) & 0x800) != 0 && *((_BYTE *)v2 + 25) >= 2u )
    {
      WPP_SF_(v2[2], 696, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x800) != 0 && *((_BYTE *)v2 + 25) >= 6u )
    {
      v18 = 697;
      goto LABEL_61;
    }
  }
}

```

## disassembly

```asm
0x180089eac  push    rbx
0x180089eae  push    rbp
0x180089eaf  push    rsi
0x180089eb0  push    rdi
0x180089eb1  push    r13
0x180089eb3  push    r14
0x180089eb5  push    r15
0x180089eb7  sub     rsp, 20h
0x180089ebb  mov     r14, rcx
0x180089ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x180089ec5  lea     r13, WPP_GLOBAL_Control
0x180089ecc  mov     r15d, 800h
0x180089ed2  cmp     rcx, r13
0x180089ed5  jz      short loc_180089EFF
0x180089ed7  test    [rcx+1Ch], r15d
0x180089edb  jz      short loc_180089EFF
0x180089edd  cmp     byte ptr [rcx+19h], 6
0x180089ee1  jb      short loc_180089EFF
0x180089ee3  mov     rcx, [rcx+10h]
0x180089ee7  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x180089eee  mov     edx, 2B7h
0x180089ef3  call    WPP_SF_
0x180089ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x180089eff  xor     ebp, ebp
0x180089f01  test    r14, r14
0x180089f04  jz      loc_18008A18F
0x180089f0a  mov     rbx, [r14]
0x180089f0d  test    rbx, rbx
0x180089f10  jz      loc_18008A18F
0x180089f16  mov     rcx, [rbx+28A8h]
0x180089f1d  call    ValidateHrasconn
0x180089f22  lea     rdi, [rbx+2998h]
0x180089f29  mov     rsi, rax
0x180089f2c  mov     dword ptr [rbx+2978h], 1
0x180089f36  cmp     [rbx+29A8h], rbp
0x180089f3d  jz      short loc_180089F65
0x180089f3f  mov     rcx, [rdi]; hEvent
0x180089f42  call    cs:__imp_SetEvent
0x180089f48  mov     rcx, [rbx+29A8h]; hHandle
0x180089f4f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180089f52  call    cs:__imp_WaitForSingleObject
0x180089f58  mov     rcx, [rbx+29A8h]; hObject
0x180089f5f  call    cs:__imp_CloseHandle
0x180089f65  mov     rcx, [rdi]; hObject
0x180089f68  test    rcx, rcx
0x180089f6b  jz      short loc_180089F73
0x180089f6d  call    cs:__imp_CloseHandle
0x180089f73  cmp     [rbx+29B0h], rbp
0x180089f7a  jz      short loc_180089FA6
0x180089f7c  mov     rcx, [rbx+29A0h]; hEvent
0x180089f83  call    cs:__imp_SetEvent
0x180089f89  mov     rcx, [rbx+29B0h]; hHandle
0x180089f90  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180089f93  call    cs:__imp_WaitForSingleObject
0x180089f99  mov     rcx, [rbx+29B0h]; hObject
0x180089fa0  call    cs:__imp_CloseHandle
0x180089fa6  mov     rcx, [rbx+29A0h]; hObject
0x180089fad  test    rcx, rcx
0x180089fb0  jz      short loc_180089FB8
0x180089fb2  call    cs:__imp_CloseHandle
0x180089fb8  mov     rcx, [rbx+29B8h]; hObject
0x180089fbf  test    rcx, rcx
0x180089fc2  jz      short loc_180089FCA
0x180089fc4  call    cs:__imp_CloseHandle
0x180089fca  mov     rcx, [rbx+2928h]; Block
0x180089fd1  test    rcx, rcx
0x180089fd4  jz      short loc_180089FE9
0x180089fd6  call    cs:__imp_free
0x180089fdc  mov     [rbx+2928h], rbp
0x180089fe3  mov     [rbx+2924h], ebp
0x180089fe9  mov     rcx, [rbx+291Ch]; Block
0x180089ff0  test    rcx, rcx
0x180089ff3  jz      short loc_18008A008
0x180089ff5  call    cs:__imp_free
0x180089ffb  mov     [rbx+291Ch], rbp
0x18008a002  mov     [rbx+2918h], ebp
0x18008a008  mov     rcx, [rbx+2934h]; hMem
0x18008a00f  test    rcx, rcx
0x18008a012  jz      short loc_18008A027
0x18008a014  call    cs:__imp_LocalFree
0x18008a01a  mov     [rbx+2934h], rbp
0x18008a021  mov     [rbx+2930h], ebp
0x18008a027  cmp     [rbx+2970h], ebp
0x18008a02d  jz      short loc_18008A069
0x18008a02f  call    cs:__imp_WSACleanup
0x18008a035  test    eax, eax
0x18008a037  jz      short loc_18008A069
0x18008a039  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a040  cmp     rcx, r13
0x18008a043  jz      short loc_18008A069
0x18008a045  test    [rcx+1Ch], r15d
0x18008a049  jz      short loc_18008A069
0x18008a04b  cmp     byte ptr [rcx+19h], 2
0x18008a04f  jb      short loc_18008A069
0x18008a051  mov     rcx, [rcx+10h]
0x18008a055  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008a05c  mov     edx, 2BAh
0x18008a061  mov     r9d, eax
0x18008a064  call    WPP_SF_d
0x18008a069  mov     rcx, [rbx+2988h]; pData
0x18008a070  test    rcx, rcx
0x18008a073  jz      short loc_18008A082
0x18008a075  call    cs:__imp_EapHostPeerFreeMemory
0x18008a07b  mov     [rbx+2988h], rbp
0x18008a082  mov     rax, [rbx+28C0h]
0x18008a089  mov     edi, 848h
0x18008a08e  test    rax, rax
0x18008a091  jz      short loc_18008A0B5
0x18008a093  mov     ecx, edi
0x18008a095  mov     [rax], bpl
0x18008a098  inc     rax
0x18008a09b  sub     rcx, 1
0x18008a09f  jnz     short loc_18008A095
0x18008a0a1  mov     rcx, [rbx+28C0h]; hMem
0x18008a0a8  call    cs:__imp_LocalFree
0x18008a0ae  mov     [rbx+28C0h], rbp
0x18008a0b5  mov     rax, [rbx+28C8h]
0x18008a0bc  test    rax, rax
0x18008a0bf  jz      short loc_18008A0E1
0x18008a0c1  mov     [rax], bpl
0x18008a0c4  inc     rax
0x18008a0c7  sub     rdi, 1
0x18008a0cb  jnz     short loc_18008A0C1
0x18008a0cd  mov     rcx, [rbx+28C8h]; hMem
0x18008a0d4  call    cs:__imp_LocalFree
0x18008a0da  mov     [rbx+28C8h], rbp
0x18008a0e1  test    rsi, rsi
0x18008a0e4  jz      short loc_18008A111
0x18008a0e6  test    dword ptr [rsi+8], 1000h
0x18008a0ed  jnz     short loc_18008A105
0x18008a0ef  cmp     dword ptr [rsi+15E0h], 2
0x18008a0f6  jnz     short loc_18008A111
0x18008a0f8  cmp     [rsi+8], ebp
0x18008a0fb  jnz     short loc_18008A111
0x18008a0fd  cmp     [rsi+15F0h], ebp
0x18008a103  jnz     short loc_18008A111
0x18008a105  lea     rcx, [rbx+130h]; Source
0x18008a10c  call    DwSignalAutoDisconnectToVan
0x18008a111  mov     rcx, [rbx+29C8h]
0x18008a118  call    RasRemoveToastNotification
0x18008a11d  test    eax, eax
0x18008a11f  jz      short loc_18008A151
0x18008a121  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a128  cmp     rcx, r13
0x18008a12b  jz      short loc_18008A151
0x18008a12d  test    [rcx+1Ch], r15d
0x18008a131  jz      short loc_18008A151
0x18008a133  cmp     byte ptr [rcx+19h], 2
0x18008a137  jb      short loc_18008A151
0x18008a139  mov     rcx, [rcx+10h]
0x18008a13d  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008a144  mov     edx, 2BBh
0x18008a149  mov     r9d, eax
0x18008a14c  call    WPP_SF_d
0x18008a151  mov     rcx, [rbx+29C8h]; hMem
0x18008a158  call    cs:__imp_GlobalFree
0x18008a15e  mov     rcx, rbx; hMem
0x18008a161  mov     [rbx+293Ch], ebp
0x18008a167  call    cs:__imp_LocalFree
0x18008a16d  mov     [r14], rbp
0x18008a170  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a177  cmp     rcx, r13
0x18008a17a  jz      short loc_18008A1E2
0x18008a17c  test    [rcx+1Ch], r15d
0x18008a180  jz      short loc_18008A1E2
0x18008a182  cmp     byte ptr [rcx+19h], 6
0x18008a186  jb      short loc_18008A1E2
0x18008a188  mov     edx, 2BCh
0x18008a18d  jmp     short loc_18008A1D2
0x18008a18f  cmp     rcx, r13
0x18008a192  jz      short loc_18008A1E2
0x18008a194  test    [rcx+1Ch], r15d
0x18008a198  jz      short loc_18008A1BC
0x18008a19a  cmp     byte ptr [rcx+19h], 2
0x18008a19e  jb      short loc_18008A1BC
0x18008a1a0  mov     rcx, [rcx+10h]
0x18008a1a4  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008a1ab  mov     edx, 2B8h
0x18008a1b0  call    WPP_SF_
0x18008a1b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18008a1bc  cmp     rcx, r13
0x18008a1bf  jz      short loc_18008A1E2
0x18008a1c1  test    [rcx+1Ch], r15d
0x18008a1c5  jz      short loc_18008A1E2
0x18008a1c7  cmp     byte ptr [rcx+19h], 6
0x18008a1cb  jb      short loc_18008A1E2
0x18008a1cd  mov     edx, 2B9h
0x18008a1d2  mov     rcx, [rcx+10h]
0x18008a1d6  lea     r8, WPP_2c2f7a3ad78e3bc162fb10365b4839b0_Traceguids
0x18008a1dd  call    WPP_SF_
0x18008a1e2  add     rsp, 20h
0x18008a1e6  pop     r15
0x18008a1e8  pop     r14
0x18008a1ea  pop     r13
0x18008a1ec  pop     rdi
0x18008a1ed  pop     rsi
0x18008a1ee  pop     rbp
0x18008a1ef  pop     rbx
0x18008a1f0  retn
```
