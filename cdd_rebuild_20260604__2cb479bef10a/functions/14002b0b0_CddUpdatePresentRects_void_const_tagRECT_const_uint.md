# CddUpdatePresentRects(void * const,tagRECT const * *,uint *)

- ea: `0x14002b0b0`
- end: `0x14002b261`
- name: `?CddUpdatePresentRects@@YAXQEAXPEAPEBUtagRECT@@PEAI@Z`
- size: `433`
- prototype: `void __fastcall(_QWORD *, const struct tagRECT **, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14002b0b0`
- `0x1400371f0`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14002b12f`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14002b12f`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14002b23c`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x14002b23c`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002b0f9`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002b0f9`
- `watchdog!WdLogSingleEntry0` at `0x14002b0e2`
- `watchdog!WdLogSingleEntry0` at `0x14002b0e2`
- `WIN32K!CddEngRectInRgn` at `0x14002b17d`
- `WIN32K!CddEngRectInRgn` at `0x14002b17d`
- `WIN32K!CddEngGetRgnBox` at `0x14002b15c`
- `WIN32K!CddEngGetRgnBox` at `0x14002b15c`
- `WIN32K!CddEngCombineRgn` at `0x14002b1af`
- `WIN32K!CddEngCombineRgn` at `0x14002b1af`
- `WIN32K!CddEngGetRgnData` at `0x14002b1c8`
- `WIN32K!CddEngGetRgnData` at `0x14002b200`
- `WIN32K!CddEngGetRgnData` at `0x14002b1c8`
- `WIN32K!CddEngGetRgnData` at `0x14002b200`
- `WIN32K!EngAllocMem` at `0x14002b1e0`
- `WIN32K!EngAllocMem` at `0x14002b1e0`

## pseudocode

```c
void __fastcall CddUpdatePresentRects(_QWORD *a1, const struct tagRECT **a2, unsigned int *a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rcx
  _QWORD *v8; // rsi
  ULONG RgnData; // ebp
  PVOID v10; // rax
  __int128 v11; // [rsp+20h] [rbp-48h] BYREF

  if ( a1[341] )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 3646;
    v6 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v6[3] = gCddImageInfo;
    v6[4] = (unsigned int)dword_14003E570;
    v6[5] = 215857758;
    WdLogGlobalForLineNumber = 3646;
  }
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(a1[360]);
  if ( *((_BYTE *)a1 + 2736) )
  {
    v7 = a1[359];
    v11 = 0;
    if ( (unsigned int)CddEngGetRgnBox(v7, &v11) > 1 && (unsigned int)CddEngRectInRgn(a1[355], &v11) )
    {
      v8 = a1 + 356;
      if ( (unsigned int)CddEngCombineRgn(a1 + 356, a1[355], a1[359], 4) <= 1 )
      {
        *a3 = 0;
      }
      else
      {
        RgnData = CddEngGetRgnData(*v8, 0, 0);
        v10 = EngAllocMem(0, RgnData, 0x64646344u);
        a1[341] = v10;
        if ( v10 )
        {
          CddEngGetRgnData(*v8, RgnData, v10);
          *a3 = *(_DWORD *)(a1[341] + 8LL);
          *a2 = (const struct tagRECT *)(a1[341] + 32LL);
        }
      }
    }
    *((_BYTE *)a1 + 2736) = 0;
  }
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(a1[360]);
}

```

## disassembly

```asm
0x14002b0b0  push    rbx
0x14002b0b2  push    rbp
0x14002b0b3  push    rsi
0x14002b0b4  push    rdi
0x14002b0b5  push    r14
0x14002b0b7  sub     rsp, 40h
0x14002b0bb  mov     rax, cs:__security_cookie
0x14002b0c2  xor     rax, rsp
0x14002b0c5  mov     [rsp+68h+var_38], rax
0x14002b0ca  cmp     qword ptr [rcx+0AA8h], 0
0x14002b0d2  mov     rdi, r8
0x14002b0d5  mov     r14, rdx
0x14002b0d8  mov     rbx, rcx
0x14002b0db  jz      short loc_14002B128
0x14002b0dd  mov     ecx, 1
0x14002b0e2  call    cs:__imp_WdLogSingleEntry0
0x14002b0e9  nop     dword ptr [rax+rax+00h]
0x14002b0ee  mov     esi, 0E3Eh
0x14002b0f3  mov     cs:WdLogGlobalForLineNumber, esi
0x14002b0f9  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002b100  nop     dword ptr [rax+rax+00h]
0x14002b105  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002b10c  mov     [rax+18h], rcx
0x14002b110  mov     ecx, cs:dword_14003E570
0x14002b116  mov     [rax+20h], rcx
0x14002b11a  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002b122  mov     cs:WdLogGlobalForLineNumber, esi
0x14002b128  mov     rcx, [rbx+0B40h]
0x14002b12f  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14002b136  nop     dword ptr [rax+rax+00h]
0x14002b13b  cmp     byte ptr [rbx+0AB0h], 0
0x14002b142  jz      loc_14002B235
0x14002b148  mov     rcx, [rbx+0B38h]
0x14002b14f  lea     rdx, [rsp+68h+var_48]
0x14002b154  xorps   xmm0, xmm0
0x14002b157  movups  [rsp+68h+var_48], xmm0
0x14002b15c  call    cs:__imp_CddEngGetRgnBox
0x14002b163  nop     dword ptr [rax+rax+00h]
0x14002b168  cmp     eax, 1
0x14002b16b  jbe     loc_14002B22E
0x14002b171  mov     rcx, [rbx+0B18h]
0x14002b178  lea     rdx, [rsp+68h+var_48]
0x14002b17d  call    cs:__imp_CddEngRectInRgn
0x14002b184  nop     dword ptr [rax+rax+00h]
0x14002b189  test    eax, eax
0x14002b18b  jz      loc_14002B22E
0x14002b191  mov     r8, [rbx+0B38h]
0x14002b198  lea     rsi, [rbx+0B20h]
0x14002b19f  mov     rdx, [rbx+0B18h]
0x14002b1a6  mov     rcx, rsi
0x14002b1a9  mov     r9d, 4
0x14002b1af  call    cs:__imp_CddEngCombineRgn
0x14002b1b6  nop     dword ptr [rax+rax+00h]
0x14002b1bb  cmp     eax, 1
0x14002b1be  jbe     short loc_14002B228
0x14002b1c0  mov     rcx, [rsi]
0x14002b1c3  xor     r8d, r8d
0x14002b1c6  xor     edx, edx
0x14002b1c8  call    cs:__imp_CddEngGetRgnData
0x14002b1cf  nop     dword ptr [rax+rax+00h]
0x14002b1d4  mov     r8d, 64646344h; ulTag
0x14002b1da  xor     ecx, ecx; fl
0x14002b1dc  mov     edx, eax; cjMemSize
0x14002b1de  mov     ebp, eax
0x14002b1e0  call    cs:__imp_EngAllocMem
0x14002b1e7  nop     dword ptr [rax+rax+00h]
0x14002b1ec  mov     [rbx+0AA8h], rax
0x14002b1f3  test    rax, rax
0x14002b1f6  jz      short loc_14002B22E
0x14002b1f8  mov     rcx, [rsi]
0x14002b1fb  mov     r8, rax
0x14002b1fe  mov     edx, ebp
0x14002b200  call    cs:__imp_CddEngGetRgnData
0x14002b207  nop     dword ptr [rax+rax+00h]
0x14002b20c  mov     rax, [rbx+0AA8h]
0x14002b213  mov     ecx, [rax+8]
0x14002b216  mov     [rdi], ecx
0x14002b218  mov     rax, [rbx+0AA8h]
0x14002b21f  add     rax, 20h ; ' '
0x14002b223  mov     [r14], rax
0x14002b226  jmp     short loc_14002B22E
0x14002b228  mov     dword ptr [rdi], 0
0x14002b22e  mov     byte ptr [rbx+0AB0h], 0
0x14002b235  mov     rcx, [rbx+0B40h]
0x14002b23c  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x14002b243  nop     dword ptr [rax+rax+00h]
0x14002b248  mov     rcx, [rsp+68h+var_38]
0x14002b24d  xor     rcx, rsp; StackCookie
0x14002b250  call    __security_check_cookie
0x14002b255  add     rsp, 40h
0x14002b259  pop     r14
0x14002b25b  pop     rdi
0x14002b25c  pop     rsi
0x14002b25d  pop     rbp
0x14002b25e  pop     rbx
0x14002b25f  retn
```
