# MoveToConnectRequestSentState

- ea: `0x140016f4c`
- end: `0x140017073`
- name: `MoveToConnectRequestSentState`
- size: `295`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1400150e0`
- `0x140017550`

## callees

- `0x140002bd8`
- `0x140002f88`
- `0x140005a9c`
- `0x140016f4c`
- `0x140018054`
- `0x14001855c`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140016fcd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140016fcd`

## pseudocode

```c
__int64 __fastcall MoveToConnectRequestSentState(__int64 a1)
{
  char *v2; // rsi
  int v3; // r9d
  unsigned int v4; // edi
  __int64 v5; // r8

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF__guid_(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids, a1 + 364);
    }
  }
  v2 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)SstpFsmGlobalInfo + 1);
  if ( v2 )
  {
    *(_DWORD *)(a1 + 24) = 2;
    LOBYTE(v3) = 1;
    v4 = 259;
    SstpTimerReschedule(a1 + 48, (_DWORD)off_14000A028, a1, v3, dword_14000A020, 0);
    GenerateSstpConnectionRequest(*(unsigned int *)(a1 + 128), v2 + 18, v5, v2 + 16);
    SendControlFrame(a1);
  }
  else
  {
    v4 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->Timer) & 0x84) == 0x84 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
  return v4;
}

```

## disassembly

```asm
0x140016f4c  push    rbx
0x140016f4e  push    rsi
0x140016f4f  push    rdi
0x140016f50  push    r14
0x140016f52  sub     rsp, 38h
0x140016f56  mov     rbx, rcx
0x140016f59  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f60  lea     r14, WPP_GLOBAL_Control
0x140016f67  cmp     rcx, r14
0x140016f6a  jz      short loc_140016FC2
0x140016f6c  mov     eax, [rcx+2Ch]
0x140016f6f  and     eax, 84h
0x140016f74  cmp     al, 84h
0x140016f76  jnz     short loc_140016F8D
0x140016f78  mov     rcx, [rcx+18h]
0x140016f7c  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016f83  mov     edx, 46h ; 'F'
0x140016f88  call    WPP_SF_
0x140016f8d  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f94  cmp     rcx, r14
0x140016f97  jz      short loc_140016FC2
0x140016f99  mov     eax, [rcx+2Ch]
0x140016f9c  test    al, 4
0x140016f9e  jz      short loc_140016FC2
0x140016fa0  cmp     byte ptr [rcx+29h], 3
0x140016fa4  jb      short loc_140016FC2
0x140016fa6  mov     rcx, [rcx+18h]
0x140016faa  lea     r9, [rbx+16Ch]
0x140016fb1  mov     edx, 47h ; 'G'
0x140016fb6  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x140016fbd  call    WPP_SF__guid_
0x140016fc2  mov     rcx, cs:SstpFsmGlobalInfo
0x140016fc9  sub     rcx, 0FFFFFFFFFFFFFF80h; Lookaside
0x140016fcd  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140016fd4  nop     dword ptr [rax+rax+00h]
0x140016fd9  mov     rsi, rax
0x140016fdc  test    rax, rax
0x140016fdf  jnz     short loc_140016FE8
0x140016fe1  mov     edi, 0C000009Ah
0x140016fe6  jmp     short loc_140017037
0x140016fe8  mov     dword ptr [rbx+18h], 2
0x140016fef  lea     rcx, [rbx+30h]
0x140016ff3  mov     eax, cs:dword_14000A020
0x140016ff9  mov     r9b, 1
0x140016ffc  mov     rdx, cs:off_14000A028
0x140017003  mov     r8, rbx
0x140017006  mov     [rsp+58h+var_30], 0
0x14001700b  mov     edi, 103h
0x140017010  mov     [rsp+58h+var_38], eax
0x140017014  call    SstpTimerReschedule
0x140017019  mov     ecx, [rbx+80h]
0x14001701f  lea     r9, [rsi+10h]
0x140017023  lea     rdx, [rsi+12h]
0x140017027  call    GenerateSstpConnectionRequest
0x14001702c  mov     rdx, rsi
0x14001702f  mov     rcx, rbx
0x140017032  call    SendControlFrame
0x140017037  mov     rcx, cs:WPP_GLOBAL_Control
0x14001703e  cmp     rcx, r14
0x140017041  jz      short loc_140017066
0x140017043  mov     edx, [rcx+2Ch]
0x140017046  and     edx, 84h
0x14001704c  cmp     dl, 84h
0x14001704f  jnz     short loc_140017066
0x140017051  mov     rcx, [rcx+18h]
0x140017055  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x14001705c  mov     edx, 48h ; 'H'
0x140017061  call    WPP_SF_
0x140017066  mov     eax, edi
0x140017068  add     rsp, 38h
0x14001706c  pop     r14
0x14001706e  pop     rdi
0x14001706f  pop     rsi
0x140017070  pop     rbx
0x140017071  retn
```
