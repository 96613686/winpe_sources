# CddSessionDataAccessor<CddSessionData>::AddSessionReference(void)

- ea: `0x140034460`
- end: `0x140034546`
- name: `?AddSessionReference@?$CddSessionDataAccessor@UCddSessionData@@@@QEAAJXZ`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140036b30`

## callees

- `0x14001bff8`
- `0x140034460`
- `0x140037640`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdLowResource` at `0x140034510`
- `watchdog!WdLogNewEntry5_WdLowResource` at `0x140034510`
- `watchdog!WdLogSingleEntry0` at `0x1400344f9`
- `watchdog!WdLogSingleEntry0` at `0x1400344f9`
- `WIN32K!W32GetSessionState` at `0x14003446f`
- `WIN32K!W32GetSessionState` at `0x14003446f`

## pseudocode

```c
__int64 __fastcall CddSessionDataAccessor<CddSessionData>::AddSessionReference(__int64 a1, __int64 a2)
{
  __int64 SessionState; // rdi
  _DWORD *v3; // rbx
  _DWORD *v4; // rax
  __int64 result; // rax
  _QWORD *v6; // rax

  SessionState = W32GetSessionState(a1, a2);
  v3 = *(_DWORD **)(SessionState + 72);
  if ( v3 )
    goto LABEL_4;
  v4 = operator new(0xD60u);
  v3 = v4;
  if ( v4 )
  {
    memset(v4, 0, 0xD60u);
    v3[846] = 1;
    v3[842] = -1;
    v3[843] = -1;
    v3[847] = 1;
    v3[850] = 1;
    v3[852] = 1;
    v3[854] = 1;
    *(_QWORD *)(SessionState + 72) = v3;
LABEL_4:
    ++*v3;
    return 0;
  }
  WdLogSingleEntry0(6);
  WdLogGlobalForLineNumber = 102;
  v6 = (_QWORD *)WdLogNewEntry5_WdLowResource();
  v6[3] = gCddImageInfo;
  v6[4] = (unsigned int)dword_14003E570;
  v6[5] = 215857758;
  result = 3221225495LL;
  WdLogGlobalForLineNumber = 102;
  return result;
}

```

## disassembly

```asm
0x140034460  mov     [rsp+arg_0], rbx
0x140034465  mov     [rsp+arg_8], rsi
0x14003446a  push    rdi
0x14003446b  sub     rsp, 20h
0x14003446f  call    cs:__imp_W32GetSessionState
0x140034476  nop     dword ptr [rax+rax+00h]
0x14003447b  mov     rdi, rax
0x14003447e  mov     esi, 1
0x140034483  mov     rbx, [rax+48h]
0x140034487  test    rbx, rbx
0x14003448a  jnz     short loc_1400344DF
0x14003448c  mov     ecx, 0D60h; cjMemSize
0x140034491  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140034496  mov     rbx, rax
0x140034499  test    rax, rax
0x14003449c  jz      short loc_1400344F4
0x14003449e  xor     edx, edx; Val
0x1400344a0  mov     r8d, 0D60h; Size
0x1400344a6  mov     rcx, rax; void *
0x1400344a9  call    memset
0x1400344ae  or      eax, 0FFFFFFFFh
0x1400344b1  mov     [rbx+0D38h], esi
0x1400344b7  mov     [rbx+0D28h], eax
0x1400344bd  mov     [rbx+0D2Ch], eax
0x1400344c3  mov     [rbx+0D3Ch], esi
0x1400344c9  mov     [rbx+0D48h], esi
0x1400344cf  mov     [rbx+0D50h], esi
0x1400344d5  mov     [rbx+0D58h], esi
0x1400344db  mov     [rdi+48h], rbx
0x1400344df  add     [rbx], esi
0x1400344e1  xor     eax, eax
0x1400344e3  mov     rbx, [rsp+28h+arg_0]
0x1400344e8  mov     rsi, [rsp+28h+arg_8]
0x1400344ed  add     rsp, 20h
0x1400344f1  pop     rdi
0x1400344f2  retn
0x1400344f4  mov     ecx, 6
0x1400344f9  call    cs:__imp_WdLogSingleEntry0
0x140034500  nop     dword ptr [rax+rax+00h]
0x140034505  mov     ebx, 66h ; 'f'
0x14003450a  mov     cs:WdLogGlobalForLineNumber, ebx
0x140034510  call    cs:__imp_WdLogNewEntry5_WdLowResource
0x140034517  nop     dword ptr [rax+rax+00h]
0x14003451c  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140034523  mov     [rax+18h], rcx
0x140034527  mov     ecx, cs:dword_14003E570
0x14003452d  mov     [rax+20h], rcx
0x140034531  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140034539  mov     eax, 0C0000017h
0x14003453e  mov     cs:WdLogGlobalForLineNumber, ebx
0x140034544  jmp     short loc_1400344E3
```
