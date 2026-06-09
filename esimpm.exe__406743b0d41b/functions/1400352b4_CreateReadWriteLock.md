# CreateReadWriteLock

- ea: `0x1400352b4`
- end: `0x140035419`
- name: `CreateReadWriteLock`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140024220`

## callees

- `0x1400352b4`
- `0x1400355d8`
- `0x1400356cc`
- `0x14003570c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140035311`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140035311`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14003532c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14003532c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1400352f9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1400352f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140035320`

## pseudocode

```c
__int64 __fastcall CreateReadWriteLock(__int64 a1)
{
  DWORD LastError; // ebx
  HANDLE EventW; // rax
  _QWORD *v4; // rcx

  LastError = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ae89183a349339de188038c4f0a19280_Traceguids);
  *(_DWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 4) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  *(_DWORD *)(a1 + 4) = 1;
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 56) = EventW;
  if ( EventW
    || (LastError = GetLastError(),
        DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8)),
        *(_DWORD *)(a1 + 4) = 0,
        !LastError) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return LastError;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_13;
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ae89183a349339de188038c4f0a19280_Traceguids, a1);
    goto LABEL_9;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return LastError;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ae89183a349339de188038c4f0a19280_Traceguids, LastError);
LABEL_9:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_13:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_d(v4[2], 14, WPP_ae89183a349339de188038c4f0a19280_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x1400352b4  push    rbx
0x1400352b6  push    rsi
0x1400352b7  push    rdi
0x1400352b8  push    r14
0x1400352ba  sub     rsp, 28h
0x1400352be  mov     rdi, rcx
0x1400352c1  xor     ebx, ebx
0x1400352c3  lea     rsi, WPP_GLOBAL_Control
0x1400352ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400352d1  cmp     rcx, rsi
0x1400352d4  jz      short loc_1400352EF
0x1400352d6  test    byte ptr [rcx+1Ch], 8
0x1400352da  jz      short loc_1400352EF
0x1400352dc  lea     edx, [rbx+0Ah]
0x1400352df  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x1400352e6  mov     rcx, [rcx+10h]
0x1400352ea  call    WPP_SF_
0x1400352ef  mov     [rdi+30h], ebx
0x1400352f2  mov     [rdi+4], ebx
0x1400352f5  lea     rcx, [rdi+8]; lpCriticalSection
0x1400352f9  call    cs:__imp_InitializeCriticalSection
0x1400352ff  nop
0x140035300  mov     dword ptr [rdi+4], 1
0x140035307  xor     r9d, r9d; lpName
0x14003530a  xor     r8d, r8d; bInitialState
0x14003530d  xor     edx, edx; bManualReset
0x14003530f  xor     ecx, ecx; lpEventAttributes
0x140035311  call    cs:__imp_CreateEventW
0x140035317  mov     [rdi+38h], rax
0x14003531b  test    rax, rax
0x14003531e  jnz     short loc_140035378
0x140035320  call    cs:__imp_GetLastError
0x140035326  mov     ebx, eax
0x140035328  lea     rcx, [rdi+8]; lpCriticalSection
0x14003532c  call    cs:__imp_DeleteCriticalSection
0x140035332  mov     dword ptr [rdi+4], 0
0x140035339  test    ebx, ebx
0x14003533b  jz      short loc_140035378
0x14003533d  mov     rcx, cs:WPP_GLOBAL_Control
0x140035344  cmp     rcx, rsi
0x140035347  jz      loc_14003540D
0x14003534d  test    byte ptr [rcx+1Ch], 4
0x140035351  jz      loc_1400353EA
0x140035357  mov     edx, 0Ch
0x14003535c  mov     r9d, ebx
0x14003535f  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x140035366  mov     rcx, [rcx+10h]
0x14003536a  call    WPP_SF_d
0x14003536f  mov     rcx, cs:WPP_GLOBAL_Control
0x140035376  jmp     short loc_1400353EA
0x140035378  mov     rcx, cs:WPP_GLOBAL_Control
0x14003537f  cmp     rcx, rsi
0x140035382  jz      loc_14003540D
0x140035388  test    byte ptr [rcx+1Ch], 2
0x14003538c  jz      short loc_1400353EA
0x14003538e  mov     edx, 0Dh
0x140035393  mov     r9, rdi
0x140035396  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x14003539d  mov     rcx, [rcx+10h]
0x1400353a1  call    WPP_SF_q
0x1400353a6  jmp     short loc_14003536F
0x1400353a8  mov     ebx, 0Eh
0x1400353ad  lea     rax, WPP_GLOBAL_Control
0x1400353b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400353bb  cmp     rcx, rax
0x1400353be  jz      short loc_1400353E3
0x1400353c0  test    byte ptr [rcx+1Ch], 4
0x1400353c4  jz      short loc_1400353E3
0x1400353c6  lea     edx, [rbx-3]
0x1400353c9  mov     r9d, ebx
0x1400353cc  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x1400353d3  mov     rcx, [rcx+10h]
0x1400353d7  call    WPP_SF_d
0x1400353dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400353e3  lea     rsi, WPP_GLOBAL_Control
0x1400353ea  cmp     rcx, rsi
0x1400353ed  jz      short loc_14003540D
0x1400353ef  test    byte ptr [rcx+1Ch], 8
0x1400353f3  jz      short loc_14003540D
0x1400353f5  mov     edx, 0Eh
0x1400353fa  mov     r9d, ebx
0x1400353fd  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x140035404  mov     rcx, [rcx+10h]
0x140035408  call    WPP_SF_d
0x14003540d  mov     eax, ebx
0x14003540f  add     rsp, 28h
0x140035413  pop     r14
0x140035415  pop     rdi
0x140035416  pop     rsi
0x140035417  pop     rbx
0x140035418  retn
```
