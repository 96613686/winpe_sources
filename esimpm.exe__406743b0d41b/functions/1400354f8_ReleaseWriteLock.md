# ReleaseWriteLock

- ea: `0x1400354f8`
- end: `0x1400355d1`
- name: `ReleaseWriteLock`
- size: `217`
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

- `0x1400354f8`
- `0x1400355d8`
- `0x140035600`
- `0x1400356cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140035594`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140035594`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140035559`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140035559`

## pseudocode

```c
void __fastcall ReleaseWriteLock(char a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v8; // rbx
  DWORD CurrentThreadId; // eax
  int v10; // r8d

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_ae89183a349339de188038c4f0a19280_Traceguids);
  _InterlockedIncrement((volatile signed __int32 *)(a2 + 48));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    CurrentThreadId = GetCurrentThreadId();
    WPP_SF_Dsdqq(v8, 27, v10, CurrentThreadId, a3, a4, a1, a2);
  }
  *(_DWORD *)(a2 + 80) = a4;
  *(_QWORD *)(a2 + 88) = a3;
  *(_DWORD *)(a2 + 96) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a2 + 8));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_ae89183a349339de188038c4f0a19280_Traceguids, 0);
}

```

## disassembly

```asm
0x1400354f8  push    rbx
0x1400354fa  push    rbp
0x1400354fb  push    rsi
0x1400354fc  push    rdi
0x1400354fd  push    r14
0x1400354ff  push    r15
0x140035501  sub     rsp, 48h
0x140035505  mov     esi, r9d
0x140035508  mov     rbp, r8
0x14003550b  mov     rdi, rdx
0x14003550e  mov     r14, rcx
0x140035511  mov     rcx, cs:WPP_GLOBAL_Control
0x140035518  lea     r15, WPP_GLOBAL_Control
0x14003551f  cmp     rcx, r15
0x140035522  jz      short loc_14003553F
0x140035524  test    byte ptr [rcx+1Ch], 8
0x140035528  jz      short loc_14003553F
0x14003552a  mov     rcx, [rcx+10h]
0x14003552e  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x140035535  mov     edx, 1Ah
0x14003553a  call    WPP_SF_
0x14003553f  lock inc dword ptr [rdi+30h]
0x140035543  mov     rbx, cs:WPP_GLOBAL_Control
0x14003554a  cmp     rbx, r15
0x14003554d  jz      short loc_140035582
0x14003554f  test    byte ptr [rbx+1Ch], 2
0x140035553  jz      short loc_140035582
0x140035555  mov     rbx, [rbx+10h]
0x140035559  call    cs:__imp_GetCurrentThreadId
0x14003555f  mov     [rsp+78h+var_40], rdi
0x140035564  mov     edx, 1Bh
0x140035569  mov     [rsp+78h+var_48], r14
0x14003556e  mov     r9d, eax
0x140035571  mov     [rsp+78h+var_50], esi
0x140035575  mov     rcx, rbx
0x140035578  mov     [rsp+78h+var_58], rbp
0x14003557d  call    WPP_SF_Dsdqq
0x140035582  lea     rcx, [rdi+8]; lpCriticalSection
0x140035586  mov     [rdi+50h], esi
0x140035589  mov     [rdi+58h], rbp
0x14003558d  mov     dword ptr [rdi+60h], 0
0x140035594  call    cs:__imp_LeaveCriticalSection
0x14003559a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400355a1  cmp     rcx, r15
0x1400355a4  jz      short loc_1400355C4
0x1400355a6  test    byte ptr [rcx+1Ch], 8
0x1400355aa  jz      short loc_1400355C4
0x1400355ac  mov     rcx, [rcx+10h]
0x1400355b0  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x1400355b7  mov     edx, 1Ch
0x1400355bc  xor     r9d, r9d
0x1400355bf  call    WPP_SF_d
0x1400355c4  add     rsp, 48h
0x1400355c8  pop     r15
0x1400355ca  pop     r14
0x1400355cc  pop     rdi
0x1400355cd  pop     rsi
0x1400355ce  pop     rbp
0x1400355cf  pop     rbx
0x1400355d0  retn
```
