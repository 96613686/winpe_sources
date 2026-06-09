# mwOpenFile

- ea: `0x180004318`
- end: `0x180004500`
- name: `mwOpenFile`
- size: `488`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005170`

## callees

- `0x1800031c4`
- `0x180003208`
- `0x180003514`
- `0x180003a44`
- `0x180003b30`
- `0x180003bc0`
- `0x180003e60`
- `0x180004318`
- `0x180005c29`
- `0x180005c60`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004407`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004407`
- `WINMM!mmioOpenW` at `0x18000438b`
- `WINMM!mmioOpenW` at `0x18000438b`

## pseudocode

```c
__int64 __fastcall mwOpenFile(__int64 a1)
{
  int v2; // eax
  HMMIO v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  int v6; // eax
  _WORD *v8; // rax
  __int64 v9; // rax
  unsigned int v10; // edx
  unsigned int AnyFreeDataNode; // eax
  struct _MMIOINFO pmmioinfo; // [rsp+20h] [rbp-88h] BYREF

  v2 = mwAllocMoreBlockNodes(a1);
  *(_DWORD *)(a1 + 116) = v2;
  if ( v2 != -1 )
  {
    if ( *(_WORD *)(a1 + 256) )
    {
      memset_0(&pmmioinfo, 0, sizeof(pmmioinfo));
      InitMMIOOpen(a1, &pmmioinfo);
      v3 = mmioOpenW((LPWSTR)(a1 + 256), &pmmioinfo, 0x20u);
      *(_QWORD *)(a1 + 80) = v3;
      if ( v3 )
      {
        if ( (unsigned int)ReadWaveHeader(a1) )
        {
          v4 = *(_QWORD *)(a1 + 104);
          v5 = 2LL * *(unsigned int *)(a1 + 116);
          *(_DWORD *)(v4 + 8 * v5 + 4) = *(_DWORD *)(a1 + 76);
          *(_DWORD *)(v4 + 8 * v5 + 8) = *(_DWORD *)(a1 + 76);
          *(_DWORD *)(v4 + 8 * v5 + 12) = -1;
          v6 = mwCheckDevice(a1, *(_DWORD *)(a1 + 28));
          *(_DWORD *)(a1 + 140) = v6;
          if ( !v6 )
            return 1;
        }
      }
      else
      {
        SetMMIOError(a1, pmmioinfo.wErrorRet);
      }
    }
    else
    {
      v8 = LocalAlloc(0x40u, 0x10u);
      *(_QWORD *)(a1 + 168) = v8;
      if ( v8 )
      {
        *v8 = 1;
        *(_WORD *)(*(_QWORD *)(a1 + 168) + 2LL) = 1;
        *(_DWORD *)(*(_QWORD *)(a1 + 168) + 8LL) = 11025;
        *(_DWORD *)(*(_QWORD *)(a1 + 168) + 4LL) = 11025;
        *(_WORD *)(*(_QWORD *)(a1 + 168) + 12LL) = *(_DWORD *)(*(_QWORD *)(a1 + 168) + 4LL)
                                                 / *(_DWORD *)(*(_QWORD *)(a1 + 168) + 8LL);
        *(_WORD *)(*(_QWORD *)(a1 + 168) + 14LL) = 8 * *(_WORD *)(*(_QWORD *)(a1 + 168) + 12LL);
        v9 = *(_QWORD *)(a1 + 168);
        *(_DWORD *)(a1 + 160) = 16;
        v10 = *(unsigned __int16 *)(v9 + 12)
            + 11024
            - ((unsigned int)*(unsigned __int16 *)(v9 + 12) + 11024) % *(unsigned __int16 *)(v9 + 12);
        *(_DWORD *)(a1 + 148) = v10;
        AnyFreeDataNode = mwFindAnyFreeDataNode(a1, v10);
        *(_DWORD *)(a1 + 116) = AnyFreeDataNode;
        if ( AnyFreeDataNode != -1 )
        {
          *(_DWORD *)(a1 + 120) = AnyFreeDataNode;
          *(_DWORD *)(*(_QWORD *)(a1 + 104) + 16LL * AnyFreeDataNode + 12) = -1;
          return 1;
        }
      }
      else
      {
        *(_DWORD *)(a1 + 140) = 264;
      }
    }
    mwCloseFile(a1);
  }
  return 0;
}

```

## disassembly

```asm
0x180004318  mov     [rsp+arg_8], rbx
0x18000431d  mov     [rsp+arg_10], rsi
0x180004322  push    rdi
0x180004323  sub     rsp, 0A0h
0x18000432a  mov     rax, cs:__security_cookie
0x180004331  xor     rax, rsp
0x180004334  mov     [rsp+0A8h+var_18], rax
0x18000433c  mov     rbx, rcx
0x18000433f  call    mwAllocMoreBlockNodes
0x180004344  mov     [rbx+74h], eax
0x180004347  cmp     eax, 0FFFFFFFFh
0x18000434a  jz      loc_1800044D9
0x180004350  lea     rdi, [rbx+100h]
0x180004357  xor     esi, esi
0x180004359  cmp     [rdi], si
0x18000435c  jz      loc_1800043FF
0x180004362  xor     edx, edx; Val
0x180004364  lea     r8d, [rsi+64h]; Size
0x180004368  lea     rcx, [rsp+0A8h+pmmioinfo]; void *
0x18000436d  call    memset_0
0x180004372  lea     rdx, [rsp+0A8h+pmmioinfo]
0x180004377  mov     rcx, rbx
0x18000437a  call    InitMMIOOpen
0x18000437f  lea     r8d, [rsi+20h]; fdwOpen
0x180004383  mov     rcx, rdi; pszFileName
0x180004386  lea     rdx, [rsp+0A8h+pmmioinfo]; pmmioinfo
0x18000438b  call    cs:__imp_mmioOpenW
0x180004391  mov     [rbx+50h], rax
0x180004395  mov     rcx, rbx
0x180004398  test    rax, rax
0x18000439b  jnz     short loc_1800043AB
0x18000439d  mov     edx, [rsp+0A8h+pmmioinfo.wErrorRet]
0x1800043a1  call    SetMMIOError
0x1800043a6  jmp     loc_1800044D1
0x1800043ab  call    ReadWaveHeader
0x1800043b0  test    eax, eax
0x1800043b2  jz      loc_1800044D1
0x1800043b8  mov     r8d, [rbx+74h]
0x1800043bc  mov     rcx, rbx
0x1800043bf  mov     rdx, [rbx+68h]
0x1800043c3  add     r8, r8
0x1800043c6  mov     eax, [rbx+4Ch]
0x1800043c9  mov     [rdx+r8*8+4], eax
0x1800043ce  mov     eax, [rbx+4Ch]
0x1800043d1  mov     [rdx+r8*8+8], eax
0x1800043d6  mov     dword ptr [rdx+r8*8+0Ch], 0FFFFFFFFh
0x1800043df  mov     edx, [rbx+1Ch]
0x1800043e2  call    mwCheckDevice
0x1800043e7  mov     [rbx+8Ch], eax
0x1800043ed  test    eax, eax
0x1800043ef  jnz     loc_1800044D1
0x1800043f5  mov     eax, 1
0x1800043fa  jmp     loc_1800044DB
0x1800043ff  mov     edx, 10h; uBytes
0x180004404  lea     ecx, [rdx+30h]; uFlags
0x180004407  call    cs:__imp_LocalAlloc
0x18000440d  mov     [rbx+0A8h], rax
0x180004414  test    rax, rax
0x180004417  jz      loc_1800044C7
0x18000441d  xor     edx, edx
0x18000441f  mov     ecx, 2B11h
0x180004424  mov     edi, 1
0x180004429  mov     [rax], di
0x18000442c  mov     rax, [rbx+0A8h]
0x180004433  mov     [rax+2], di
0x180004437  mov     rax, [rbx+0A8h]
0x18000443e  mov     [rax+8], ecx
0x180004441  mov     rax, [rbx+0A8h]
0x180004448  mov     [rax+4], ecx
0x18000444b  mov     rcx, [rbx+0A8h]
0x180004452  mov     eax, [rcx+4]
0x180004455  div     dword ptr [rcx+8]
0x180004458  xor     edx, edx
0x18000445a  mov     [rcx+0Ch], ax
0x18000445e  mov     rcx, [rbx+0A8h]
0x180004465  movzx   eax, word ptr [rcx+0Ch]
0x180004469  shl     ax, 3
0x18000446d  mov     [rcx+0Eh], ax
0x180004471  mov     rax, [rbx+0A8h]
0x180004478  mov     dword ptr [rbx+0A0h], 10h
0x180004482  movzx   ecx, word ptr [rax+0Ch]
0x180004486  lea     r8d, [rcx+2B10h]
0x18000448d  mov     eax, r8d
0x180004490  div     ecx
0x180004492  mov     rcx, rbx
0x180004495  sub     r8d, edx
0x180004498  mov     edx, r8d
0x18000449b  mov     [rbx+94h], r8d
0x1800044a2  call    mwFindAnyFreeDataNode
0x1800044a7  mov     [rbx+74h], eax
0x1800044aa  cmp     eax, 0FFFFFFFFh
0x1800044ad  jz      short loc_1800044D1
0x1800044af  mov     ecx, eax
0x1800044b1  mov     [rbx+78h], eax
0x1800044b4  add     rcx, rcx
0x1800044b7  mov     rax, [rbx+68h]
0x1800044bb  mov     dword ptr [rax+rcx*8+0Ch], 0FFFFFFFFh
0x1800044c3  mov     eax, edi
0x1800044c5  jmp     short loc_1800044DB
0x1800044c7  mov     dword ptr [rbx+8Ch], 108h
0x1800044d1  mov     rcx, rbx
0x1800044d4  call    mwCloseFile
0x1800044d9  xor     eax, eax
0x1800044db  mov     rcx, [rsp+0A8h+var_18]
0x1800044e3  xor     rcx, rsp; StackCookie
0x1800044e6  call    __security_check_cookie
0x1800044eb  lea     r11, [rsp+0A8h+var_8]
0x1800044f3  mov     rbx, [r11+18h]
0x1800044f7  mov     rsi, [r11+20h]
0x1800044fb  mov     rsp, r11
0x1800044fe  pop     rdi
0x1800044ff  retn
```
