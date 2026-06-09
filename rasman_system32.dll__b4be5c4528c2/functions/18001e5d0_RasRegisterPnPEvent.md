# RasRegisterPnPEvent

- ea: `0x18001e5d0`
- end: `0x18001e6de`
- name: `RasRegisterPnPEvent`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001e310`
- `0x18001e5d0`
- `0x180021ae4`
- `0x180021b14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e618`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e618`

## pseudocode

```c
__int64 __fastcall RasRegisterPnPEvent(__int64 a1, int a2)
{
  DWORD CurrentProcessId; // eax
  unsigned int v5; // eax
  unsigned int v6; // ebx
  PVOID *v7; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 526, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  CurrentProcessId = GetCurrentProcessId();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      527,
      &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids,
      CurrentProcessId);
  }
  v5 = RasRegisterPnPCommon(a1, 0, 2, a2);
  v6 = v5;
  if ( !v5 )
    goto LABEL_14;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 528, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v5);
LABEL_14:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 529, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18001e5d0  mov     [rsp+arg_0], rbx
0x18001e5d5  mov     [rsp+arg_8], rbp
0x18001e5da  push    rdi
0x18001e5db  sub     rsp, 20h
0x18001e5df  mov     ebx, edx
0x18001e5e1  mov     rdi, rcx
0x18001e5e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5eb  lea     rbp, WPP_GLOBAL_Control
0x18001e5f2  cmp     rcx, rbp
0x18001e5f5  jz      short loc_18001E618
0x18001e5f7  test    byte ptr [rcx+1Ch], 40h
0x18001e5fb  jz      short loc_18001E618
0x18001e5fd  cmp     byte ptr [rcx+19h], 6
0x18001e601  jb      short loc_18001E618
0x18001e603  mov     rcx, [rcx+10h]
0x18001e607  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e60e  mov     edx, 20Eh
0x18001e613  call    WPP_SF_
0x18001e618  call    cs:__imp_GetCurrentProcessId
0x18001e61f  nop     dword ptr [rax+rax+00h]
0x18001e624  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e62b  cmp     rcx, rbp
0x18001e62e  jz      short loc_18001E654
0x18001e630  test    byte ptr [rcx+1Ch], 40h
0x18001e634  jz      short loc_18001E654
0x18001e636  cmp     byte ptr [rcx+19h], 5
0x18001e63a  jb      short loc_18001E654
0x18001e63c  mov     rcx, [rcx+10h]
0x18001e640  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e647  mov     edx, 20Fh
0x18001e64c  mov     r9d, eax
0x18001e64f  call    WPP_SF_d
0x18001e654  xor     edx, edx
0x18001e656  mov     r9d, ebx
0x18001e659  mov     rcx, rdi
0x18001e65c  lea     r8d, [rdx+2]
0x18001e660  call    RasRegisterPnPCommon
0x18001e665  mov     ebx, eax
0x18001e667  test    eax, eax
0x18001e669  jz      short loc_18001E69B
0x18001e66b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e672  cmp     rcx, rbp
0x18001e675  jz      short loc_18001E6CB
0x18001e677  test    byte ptr [rcx+1Ch], 40h
0x18001e67b  jz      short loc_18001E6A2
0x18001e67d  cmp     byte ptr [rcx+19h], 2
0x18001e681  jb      short loc_18001E6A2
0x18001e683  mov     rcx, [rcx+10h]
0x18001e687  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e68e  mov     edx, 210h
0x18001e693  mov     r9d, eax
0x18001e696  call    WPP_SF_d
0x18001e69b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6a2  cmp     rcx, rbp
0x18001e6a5  jz      short loc_18001E6CB
0x18001e6a7  test    byte ptr [rcx+1Ch], 40h
0x18001e6ab  jz      short loc_18001E6CB
0x18001e6ad  cmp     byte ptr [rcx+19h], 6
0x18001e6b1  jb      short loc_18001E6CB
0x18001e6b3  mov     rcx, [rcx+10h]
0x18001e6b7  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001e6be  mov     edx, 211h
0x18001e6c3  mov     r9d, ebx
0x18001e6c6  call    WPP_SF_d
0x18001e6cb  mov     rbp, [rsp+28h+arg_8]
0x18001e6d0  mov     eax, ebx
0x18001e6d2  mov     rbx, [rsp+28h+arg_0]
0x18001e6d7  add     rsp, 20h
0x18001e6db  pop     rdi
0x18001e6dc  retn
```
