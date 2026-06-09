# TryCreateDevice(CDDPDEV *,_D3DKMT_DISPLAYMODE *,_CDDDXGK_INTERFACE *,int,_WORKERTHREAD_COMMAND)

- ea: `0x140022c28`
- end: `0x140022e5d`
- name: `?TryCreateDevice@@YAXPEAUCDDPDEV@@PEAU_D3DKMT_DISPLAYMODE@@PEAU_CDDDXGK_INTERFACE@@HW4_WORKERTHREAD_COMMAND@@@Z`
- size: `565`
- prototype: `void __fastcall(__int64, __int64, __int64, int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140011510`

## callees

- `0x140021d5c`
- `0x140022c28`
- `0x14002c038`
- `0x14002d088`
- `0x14002d4b4`
- `0x14002e61c`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x140022df6`
- `watchdog!WdLogSingleEntry2` at `0x140022df6`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140022cc2`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140022d23`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140022cc2`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140022d23`
- `watchdog!WdLogSingleEntry0` at `0x140022cac`
- `watchdog!WdLogSingleEntry0` at `0x140022d0d`
- `watchdog!WdLogSingleEntry0` at `0x140022cac`
- `watchdog!WdLogSingleEntry0` at `0x140022d0d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140022e0d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140022e0d`

## pseudocode

```c
void __fastcall TryCreateDevice(__int64 a1, __int64 a2, __int64 a3, int a4, unsigned int a5)
{
  int v5; // edi
  __int64 v10; // rcx
  unsigned __int64 v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  int v15; // eax
  _QWORD *v16; // rax

  v5 = 0;
  if ( (*(_DWORD *)(a1 + 2744) & 0x400) == 0 || (v10 = *(unsigned int *)(a1 + 2520), !(_DWORD)v10) )
  {
LABEL_10:
    if ( *(_DWORD *)(a1 + 2520) )
      goto LABEL_12;
    goto LABEL_11;
  }
  if ( *(_BYTE *)(a1 + 2716) )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(a1 + 120))(v10, 0, *(unsigned int *)(a1 + 784));
    v11 = (unsigned int)(v5 + 1071774976);
    if ( (unsigned int)v11 > 0x39 || (v12 = 0x220000000000001LL, !_bittest64(&v12, v11)) )
    {
      if ( v5 < 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 5131;
        v13 = (_QWORD *)WdLogNewEntry5_WdAssertion();
        v13[3] = gCddImageInfo;
        v13[4] = (unsigned int)dword_14003E570;
        v13[5] = 215857758;
        WdLogGlobalForLineNumber = 5131;
      }
    }
  }
  CDDPDEV::DestroyDevice(a1, a5);
  if ( *(_DWORD *)(a1 + 2520) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 5135;
    v14 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v14[3] = gCddImageInfo;
    v14[4] = (unsigned int)dword_14003E570;
    v14[5] = 215857758;
    WdLogGlobalForLineNumber = 5135;
    goto LABEL_10;
  }
LABEL_11:
  v5 = CreateAndEnableDevice(a1, a2, a3, 0, a5);
LABEL_12:
  if ( v5 < 0 )
  {
    if ( v5 == -1073741130 )
      return;
  }
  else if ( a4 )
  {
    if ( (*(_DWORD *)(a1 + 2744) & 0x100) == 0 && *(_BYTE *)(a1 + 2748) )
    {
      v15 = *(_DWORD *)(a1 + 2744);
      if ( (v15 & 0x800) != 0 )
      {
        *(_DWORD *)(a1 + 2744) = v15 | 0x100;
      }
      else if ( (int)CDDPDEV::InitInternalBitmaps((CDDPDEV *)a1) < 0 )
      {
        CDDPDEV::InvalidateInternalBitmaps(a1, a5);
      }
    }
    return;
  }
  if ( (*(_DWORD *)(a1 + 2744) & 0x200) == 0 )
  {
    WdLogSingleEntry2(4, a1, *(unsigned int *)(a1 + 784));
    WdLogGlobalForLineNumber = 5169;
    v16 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v16[3] = gCddImageInfo;
    v16[4] = (unsigned int)dword_14003E570;
    v16[5] = 215857758;
    WdLogGlobalForLineNumber = 5169;
    *(_DWORD *)(a1 + 2744) |= 0x200u;
    TriggerGdiModeReset(a1, 53);
  }
}

```

## disassembly

```asm
0x140022c28  push    rbx
0x140022c2a  push    rbp
0x140022c2b  push    rsi
0x140022c2c  push    rdi
0x140022c2d  push    r14
0x140022c2f  push    r15
0x140022c31  sub     rsp, 38h
0x140022c35  mov     esi, [rsp+68h+arg_20]
0x140022c3c  xor     edi, edi
0x140022c3e  test    dword ptr [rcx+0AB8h], 400h
0x140022c48  mov     ebp, r9d
0x140022c4b  mov     r14, r8
0x140022c4e  mov     r15, rdx
0x140022c51  mov     rbx, rcx
0x140022c54  jz      loc_140022D56
0x140022c5a  mov     ecx, [rcx+9D8h]
0x140022c60  test    ecx, ecx
0x140022c62  jz      loc_140022D56
0x140022c68  cmp     [rbx+0A9Ch], dil
0x140022c6f  jz      loc_140022CF5
0x140022c75  mov     rax, [rbx+78h]
0x140022c79  xor     edx, edx
0x140022c7b  mov     r8d, [rbx+310h]
0x140022c82  call    _guard_dispatch_icall
0x140022c87  mov     edi, eax
0x140022c89  add     eax, 3FE1FD00h
0x140022c8e  cmp     eax, 39h ; '9'
0x140022c91  ja      short loc_140022CA3
0x140022c93  mov     rcx, 220000000000001h
0x140022c9d  bt      rcx, rax
0x140022ca1  jb      short loc_140022CF5
0x140022ca3  test    edi, edi
0x140022ca5  jns     short loc_140022CF5
0x140022ca7  mov     ecx, 1
0x140022cac  call    cs:__imp_WdLogSingleEntry0
0x140022cb3  nop     dword ptr [rax+rax+00h]
0x140022cb8  mov     cs:WdLogGlobalForLineNumber, 140Bh
0x140022cc2  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140022cc9  nop     dword ptr [rax+rax+00h]
0x140022cce  mov     rdx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140022cd5  mov     [rax+18h], rdx
0x140022cd9  mov     edx, cs:dword_14003E570
0x140022cdf  mov     [rax+20h], rdx
0x140022ce3  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140022ceb  mov     cs:WdLogGlobalForLineNumber, 140Bh
0x140022cf5  mov     edx, esi
0x140022cf7  mov     rcx, rbx
0x140022cfa  call    ?DestroyDevice@CDDPDEV@@QEAAXW4_WORKERTHREAD_COMMAND@@@Z; CDDPDEV::DestroyDevice(_WORKERTHREAD_COMMAND)
0x140022cff  cmp     dword ptr [rbx+9D8h], 0
0x140022d06  jz      short loc_140022D5F
0x140022d08  mov     ecx, 1
0x140022d0d  call    cs:__imp_WdLogSingleEntry0
0x140022d14  nop     dword ptr [rax+rax+00h]
0x140022d19  mov     cs:WdLogGlobalForLineNumber, 140Fh
0x140022d23  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140022d2a  nop     dword ptr [rax+rax+00h]
0x140022d2f  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140022d36  mov     [rax+18h], rcx
0x140022d3a  mov     ecx, cs:dword_14003E570
0x140022d40  mov     [rax+20h], rcx
0x140022d44  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140022d4c  mov     cs:WdLogGlobalForLineNumber, 140Fh
0x140022d56  cmp     dword ptr [rbx+9D8h], 0
0x140022d5d  jnz     short loc_140022D76
0x140022d5f  xor     r9d, r9d
0x140022d62  mov     [rsp+68h+var_48], esi
0x140022d66  mov     r8, r14
0x140022d69  mov     rdx, r15
0x140022d6c  mov     rcx, rbx
0x140022d6f  call    ?CreateAndEnableDevice@@YAJPEAUCDDPDEV@@PEAU_D3DKMT_DISPLAYMODE@@PEAU_CDDDXGK_INTERFACE@@HW4_WORKERTHREAD_COMMAND@@@Z; CreateAndEnableDevice(CDDPDEV *,_D3DKMT_DISPLAYMODE *,_CDDDXGK_INTERFACE *,int,_WORKERTHREAD_COMMAND)
0x140022d74  mov     edi, eax
0x140022d76  test    edi, edi
0x140022d78  js      short loc_140022DD2
0x140022d7a  test    ebp, ebp
0x140022d7c  jz      short loc_140022DDA
0x140022d7e  mov     ecx, 100h
0x140022d83  test    [rbx+0AB8h], ecx
0x140022d89  jnz     loc_140022E4F
0x140022d8f  mov     al, [rbx+0ABCh]
0x140022d95  test    al, al
0x140022d97  jz      loc_140022E4F
0x140022d9d  mov     eax, [rbx+0AB8h]
0x140022da3  bt      eax, 0Bh
0x140022da7  jnb     short loc_140022DB6
0x140022da9  or      eax, ecx
0x140022dab  mov     [rbx+0AB8h], eax
0x140022db1  jmp     loc_140022E4F
0x140022db6  mov     rcx, rbx; this
0x140022db9  call    ?InitInternalBitmaps@CDDPDEV@@QEAAJXZ; CDDPDEV::InitInternalBitmaps(void)
0x140022dbe  test    eax, eax
0x140022dc0  jns     loc_140022E4F
0x140022dc6  mov     edx, esi
0x140022dc8  mov     rcx, rbx
0x140022dcb  call    ?InvalidateInternalBitmaps@CDDPDEV@@QEAAXW4_WORKERTHREAD_COMMAND@@@Z; CDDPDEV::InvalidateInternalBitmaps(_WORKERTHREAD_COMMAND)
0x140022dd0  jmp     short loc_140022E4F
0x140022dd2  cmp     edi, 0C00002B6h
0x140022dd8  jz      short loc_140022E4F
0x140022dda  mov     esi, 200h
0x140022ddf  test    [rbx+0AB8h], esi
0x140022de5  jnz     short loc_140022E4F
0x140022de7  mov     r8d, [rbx+310h]
0x140022dee  mov     rdx, rbx
0x140022df1  mov     ecx, 4
0x140022df6  call    cs:__imp_WdLogSingleEntry2
0x140022dfd  nop     dword ptr [rax+rax+00h]
0x140022e02  mov     edi, 1431h
0x140022e07  mov     cs:WdLogGlobalForLineNumber, edi
0x140022e0d  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140022e14  nop     dword ptr [rax+rax+00h]
0x140022e19  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140022e20  mov     edx, 35h ; '5'
0x140022e25  mov     [rax+18h], rcx
0x140022e29  mov     ecx, cs:dword_14003E570
0x140022e2f  mov     [rax+20h], rcx
0x140022e33  mov     rcx, rbx
0x140022e36  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140022e3e  mov     cs:WdLogGlobalForLineNumber, edi
0x140022e44  or      [rbx+0AB8h], esi
0x140022e4a  call    ?TriggerGdiModeReset@@YAXPEAUCDDPDEV@@W4_DXGK_DIAG_CODE_POINT_TYPE@@@Z; TriggerGdiModeReset(CDDPDEV *,_DXGK_DIAG_CODE_POINT_TYPE)
0x140022e4f  add     rsp, 38h
0x140022e53  pop     r15
0x140022e55  pop     r14
0x140022e57  pop     rdi
0x140022e58  pop     rsi
0x140022e59  pop     rbp
0x140022e5a  pop     rbx
0x140022e5b  retn
```
