# DeleteReadWriteLock

- ea: `0x140035420`
- end: `0x1400354ef`
- name: `DeleteReadWriteLock`
- size: `207`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140023ba0`
- `0x140024220`

## callees

- `0x140035420`
- `0x1400355d8`
- `0x1400356cc`
- `0x14003570c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400354a6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400354a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003548e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003548e`

## pseudocode

```c
void __fastcall DeleteReadWriteLock(__int64 a1)
{
  _QWORD *v2; // rcx
  void *v3; // rcx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ae89183a349339de188038c4f0a19280_Traceguids);
      v2 = WPP_GLOBAL_Control;
    }
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 )
      WPP_SF_q(v2[2], 16, WPP_ae89183a349339de188038c4f0a19280_Traceguids, a1);
  }
  v3 = *(void **)(a1 + 56);
  if ( v3 )
  {
    CloseHandle(v3);
    *(_QWORD *)(a1 + 56) = 0;
  }
  if ( *(_DWORD *)(a1 + 4) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    *(_DWORD *)(a1 + 4) = 0;
  }
  *(_DWORD *)(a1 + 48) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_ae89183a349339de188038c4f0a19280_Traceguids, 0);
}

```

## disassembly

```asm
0x140035420  mov     [rsp+arg_0], rbx
0x140035425  push    rsi
0x140035426  sub     rsp, 20h
0x14003542a  mov     rbx, rcx
0x14003542d  mov     rcx, cs:WPP_GLOBAL_Control
0x140035434  lea     rsi, WPP_GLOBAL_Control
0x14003543b  cmp     rcx, rsi
0x14003543e  jz      short loc_140035485
0x140035440  test    byte ptr [rcx+1Ch], 8
0x140035444  jz      short loc_140035462
0x140035446  mov     rcx, [rcx+10h]
0x14003544a  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x140035451  mov     edx, 0Fh
0x140035456  call    WPP_SF_
0x14003545b  mov     rcx, cs:WPP_GLOBAL_Control
0x140035462  cmp     rcx, rsi
0x140035465  jz      short loc_140035485
0x140035467  test    byte ptr [rcx+1Ch], 2
0x14003546b  jz      short loc_140035485
0x14003546d  mov     rcx, [rcx+10h]
0x140035471  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x140035478  mov     edx, 10h
0x14003547d  mov     r9, rbx
0x140035480  call    WPP_SF_q
0x140035485  mov     rcx, [rbx+38h]; hObject
0x140035489  test    rcx, rcx
0x14003548c  jz      short loc_14003549C
0x14003548e  call    cs:__imp_CloseHandle
0x140035494  mov     qword ptr [rbx+38h], 0
0x14003549c  cmp     dword ptr [rbx+4], 0
0x1400354a0  jz      short loc_1400354B3
0x1400354a2  lea     rcx, [rbx+8]; lpCriticalSection
0x1400354a6  call    cs:__imp_DeleteCriticalSection
0x1400354ac  mov     dword ptr [rbx+4], 0
0x1400354b3  mov     dword ptr [rbx+30h], 0
0x1400354ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400354c1  cmp     rcx, rsi
0x1400354c4  jz      short loc_1400354E4
0x1400354c6  test    byte ptr [rcx+1Ch], 8
0x1400354ca  jz      short loc_1400354E4
0x1400354cc  mov     rcx, [rcx+10h]
0x1400354d0  lea     r8, WPP_ae89183a349339de188038c4f0a19280_Traceguids
0x1400354d7  mov     edx, 11h
0x1400354dc  xor     r9d, r9d
0x1400354df  call    WPP_SF_d
0x1400354e4  mov     rbx, [rsp+28h+arg_0]
0x1400354e9  add     rsp, 20h
0x1400354ed  pop     rsi
0x1400354ee  retn
```
