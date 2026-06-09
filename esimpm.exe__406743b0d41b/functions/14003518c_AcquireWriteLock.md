# AcquireWriteLock

- ea: `0x14003518c`
- end: `0x1400352ac`
- name: `AcquireWriteLock`
- size: `288`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140023034`
- `0x1400230dc`
- `0x140023ba0`
- `0x140035b30`

## callees

- `0x14003518c`
- `0x1400355d8`
- `0x140035600`
- `0x1400356cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003522f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003522f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140035215`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140035215`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400351a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400351a5`

## pseudocode

```c
DWORD __fastcall AcquireWriteLock(char a1, __int64 a2, __int64 a3, int a4)
{
  DWORD CurrentThreadId; // ebp
  int v9; // r8d
  _QWORD *v10; // rcx
  int v11; // r8d
  DWORD result; // eax

  CurrentThreadId = GetCurrentThreadId();
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_ae89183a349339de188038c4f0a19280_Traceguids);
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 )
      WPP_SF_Dsdqq(v10[2], 23, v9, CurrentThreadId, a3, a4, a1, a2);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  result = _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 48), 0xFFFFFFFF);
  if ( (int)(result - 1) >= 0 )
    result = WaitForSingleObject(*(HANDLE *)(a2 + 56), 0xFFFFFFFF);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    result = WPP_SF_Dsdqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v11, CurrentThreadId, a3, a4, a1, a2);
  *(_DWORD *)(a2 + 96) = CurrentThreadId;
  *(_DWORD *)(a2 + 64) = a4;
  *(_QWORD *)(a2 + 72) = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    return WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_ae89183a349339de188038c4f0a19280_Traceguids, 0);
  return result;
}

```

## disassembly

```asm
0x14003518c  push    rbx
0x14003518e  push    rbp
0x14003518f  push    rsi
0x140035190  push    rdi
0x140035191  push    r14
0x140035193  push    r15
0x140035195  sub     rsp, 48h
0x140035199  mov     edi, r9d
0x14003519c  mov     rsi, r8
0x14003519f  mov     rbx, rdx
0x1400351a2  mov     r14, rcx
0x1400351a5  call    cs:__imp_GetCurrentThreadId
0x1400351ab  mov     ebp, eax
0x1400351ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400351b4  lea     r15, WPP_GLOBAL_Control
0x1400351bb  cmp     rcx, r15
0x1400351be  jz      short loc_140035211
0x1400351c0  test    byte ptr [rcx+1Ch], 8
0x1400351c4  jz      short loc_1400351E2
0x1400351c6  mov     rcx, [rcx+10h]
0x1400351ca  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x1400351d1  mov     edx, 16h
0x1400351d6  call    WPP_SF_
0x1400351db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400351e2  cmp     rcx, r15
0x1400351e5  jz      short loc_140035211
0x1400351e7  test    byte ptr [rcx+1Ch], 2
0x1400351eb  jz      short loc_140035211
0x1400351ed  mov     rcx, [rcx+10h]
0x1400351f1  mov     edx, 17h
0x1400351f6  mov     [rsp+78h+var_40], rbx
0x1400351fb  mov     r9d, ebp
0x1400351fe  mov     [rsp+78h+var_48], r14
0x140035203  mov     [rsp+78h+var_50], edi
0x140035207  mov     [rsp+78h+var_58], rsi
0x14003520c  call    WPP_SF_Dsdqq
0x140035211  lea     rcx, [rbx+8]; lpCriticalSection
0x140035215  call    cs:__imp_EnterCriticalSection
0x14003521b  or      eax, 0FFFFFFFFh
0x14003521e  lock xadd [rbx+30h], eax
0x140035223  cmp     eax, 1
0x140035226  js      short loc_140035235
0x140035228  mov     rcx, [rbx+38h]; hHandle
0x14003522c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14003522f  call    cs:__imp_WaitForSingleObject
0x140035235  mov     rcx, cs:WPP_GLOBAL_Control
0x14003523c  cmp     rcx, r15
0x14003523f  jz      short loc_14003526B
0x140035241  test    byte ptr [rcx+1Ch], 2
0x140035245  jz      short loc_14003526B
0x140035247  mov     rcx, [rcx+10h]
0x14003524b  mov     edx, 18h
0x140035250  mov     [rsp+78h+var_40], rbx
0x140035255  mov     r9d, ebp
0x140035258  mov     [rsp+78h+var_48], r14
0x14003525d  mov     [rsp+78h+var_50], edi
0x140035261  mov     [rsp+78h+var_58], rsi
0x140035266  call    WPP_SF_Dsdqq
0x14003526b  mov     [rbx+60h], ebp
0x14003526e  mov     [rbx+40h], edi
0x140035271  mov     [rbx+48h], rsi
0x140035275  mov     rcx, cs:WPP_GLOBAL_Control
0x14003527c  cmp     rcx, r15
0x14003527f  jz      short loc_14003529F
0x140035281  test    byte ptr [rcx+1Ch], 8
0x140035285  jz      short loc_14003529F
0x140035287  mov     rcx, [rcx+10h]
0x14003528b  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x140035292  mov     edx, 19h
0x140035297  xor     r9d, r9d
0x14003529a  call    WPP_SF_d
0x14003529f  add     rsp, 48h
0x1400352a3  pop     r15
0x1400352a5  pop     r14
0x1400352a7  pop     rdi
0x1400352a8  pop     rsi
0x1400352a9  pop     rbp
0x1400352aa  pop     rbx
0x1400352ab  retn
```
