# DrOnUserLoggedOn

- ea: `0x14001a41c`
- end: `0x14001a593`
- name: `DrOnUserLoggedOn`
- size: `375`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002acc0`

## callees

- `0x140003064`
- `0x14000324c`
- `0x140011c9c`
- `0x14001a41c`
- `0x14001dc18`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14001a45c`
- `ntoskrnl!ProbeForRead` at `0x14001a45c`
- `ntoskrnl!ProbeForWrite` at `0x14001a474`
- `ntoskrnl!ProbeForWrite` at `0x14001a474`

## pseudocode

```c
__int64 __fastcall DrOnUserLoggedOn(__int64 a1)
{
  volatile void *v2; // rsi
  _QWORD *v3; // rdi
  DrSessionManager *v4; // rcx
  _BYTE v6[40]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF

  memset(v6, 0, 32);
  v7 = 0;
  v2 = *(volatile void **)(a1 + 552);
  v3 = *(_QWORD **)(a1 + 560);
  ProbeForRead(v2, 0x20u, 1u);
  ProbeForWrite(v3, 8u, 1u);
  if ( *(_QWORD *)(a1 + 552) && *(_DWORD *)(a1 + 568) >= 0x20u && *(_DWORD *)(a1 + 572) >= 8u && *(_QWORD *)(a1 + 560) )
  {
    RtlCopyFromUser(v6, (void *)v2, 0x20u);
    DrSessionManager::OnUserLoggedOn(v4, (struct tagCHANNEL_LOGON_IN *)v6, (struct tagCHANNEL_LOGON_OUT *)&v7);
    RtlWriteULong64ToUser(v3, v7);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14001a41c  mov     rax, rsp
0x14001a41f  mov     [rax+10h], rbx
0x14001a423  mov     [rax+18h], rsi
0x14001a427  push    rdi
0x14001a428  sub     rsp, 40h
0x14001a42c  mov     rbx, rcx
0x14001a42f  xorps   xmm0, xmm0
0x14001a432  movups  xmmword ptr [rax-28h], xmm0
0x14001a436  movups  xmmword ptr [rax-18h], xmm0
0x14001a43a  mov     qword ptr [rax+8], 0
0x14001a442  mov     rsi, [rcx+228h]
0x14001a449  mov     rdi, [rcx+230h]
0x14001a450  mov     edx, 20h ; ' '; Length
0x14001a455  lea     r8d, [rdx-1Fh]; Alignment
0x14001a459  mov     rcx, rsi; Address
0x14001a45c  call    cs:__imp_ProbeForRead
0x14001a463  nop     dword ptr [rax+rax+00h]
0x14001a468  mov     edx, 8; Length
0x14001a46d  lea     r8d, [rdx-7]; Alignment
0x14001a471  mov     rcx, rdi; Address
0x14001a474  call    cs:__imp_ProbeForWrite
0x14001a47b  nop     dword ptr [rax+rax+00h]
0x14001a480  cmp     qword ptr [rbx+228h], 0
0x14001a488  jz      loc_14001A51B
0x14001a48e  cmp     dword ptr [rbx+238h], 20h ; ' '
0x14001a495  jb      loc_14001A51B
0x14001a49b  cmp     dword ptr [rbx+23Ch], 8
0x14001a4a2  jb      short loc_14001A51B
0x14001a4a4  cmp     qword ptr [rbx+230h], 0
0x14001a4ac  jz      short loc_14001A51B
0x14001a4ae  mov     r8d, 20h ; ' '; Size
0x14001a4b4  mov     rdx, rsi; Src
0x14001a4b7  lea     rcx, [rsp+48h+var_28]; void *
0x14001a4bc  call    RtlCopyFromUser
0x14001a4c1  nop
0x14001a4c2  lea     r8, [rsp+48h+arg_0]; struct tagCHANNEL_LOGON_OUT *
0x14001a4c7  lea     rdx, [rsp+48h+var_28]; struct tagCHANNEL_LOGON_IN *
0x14001a4cc  call    ?OnUserLoggedOn@DrSessionManager@@QEAAXPEAUtagCHANNEL_LOGON_IN@@PEAUtagCHANNEL_LOGON_OUT@@@Z; DrSessionManager::OnUserLoggedOn(tagCHANNEL_LOGON_IN *,tagCHANNEL_LOGON_OUT *)
0x14001a4d1  nop
0x14001a4d2  mov     rdx, [rsp+48h+arg_0]
0x14001a4d7  mov     rcx, rdi
0x14001a4da  call    RtlWriteULong64ToUser
0x14001a4df  nop
0x14001a4e0  xor     eax, eax
0x14001a4e2  jmp     loc_14001A582
0x14001a4e7  mov     ebx, eax
0x14001a4e9  lea     rax, WPP_GLOBAL_Control
0x14001a4f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a4f7  cmp     rcx, rax
0x14001a4fa  jz      short loc_14001A517
0x14001a4fc  cmp     byte ptr [rcx+29h], 4
0x14001a500  jb      short loc_14001A517
0x14001a502  mov     edx, 18h
0x14001a507  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14001a50e  mov     rcx, [rcx+18h]
0x14001a512  call    WPP_SF_
0x14001a517  mov     eax, ebx
0x14001a519  jmp     short loc_14001A582
0x14001a51b  lea     rax, WPP_GLOBAL_Control
0x14001a522  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a529  cmp     rcx, rax
0x14001a52c  jz      short loc_14001A549
0x14001a52e  cmp     byte ptr [rcx+29h], 2
0x14001a532  jb      short loc_14001A549
0x14001a534  mov     edx, 16h
0x14001a539  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14001a540  mov     rcx, [rcx+18h]
0x14001a544  call    WPP_SF_
0x14001a549  mov     eax, 0C000000Dh
0x14001a54e  jmp     short loc_14001A582
0x14001a550  mov     ebx, eax
0x14001a552  lea     rax, WPP_GLOBAL_Control
0x14001a559  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a560  cmp     rcx, rax
0x14001a563  jz      short loc_14001A580
0x14001a565  cmp     byte ptr [rcx+29h], 4
0x14001a569  jb      short loc_14001A580
0x14001a56b  mov     edx, 17h
0x14001a570  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x14001a577  mov     rcx, [rcx+18h]
0x14001a57b  call    WPP_SF_
0x14001a580  mov     eax, ebx
0x14001a582  mov     rbx, [rsp+48h+arg_8]
0x14001a587  mov     rsi, [rsp+48h+arg_10]
0x14001a58c  add     rsp, 40h
0x14001a590  pop     rdi
0x14001a591  retn
```
