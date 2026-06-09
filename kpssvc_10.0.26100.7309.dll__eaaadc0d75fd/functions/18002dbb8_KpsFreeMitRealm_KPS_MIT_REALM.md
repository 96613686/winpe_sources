# KpsFreeMitRealm(_KPS_MIT_REALM *)

- ea: `0x18002dbb8`
- end: `0x18002dc46`
- name: `?KpsFreeMitRealm@@YAXPEAU_KPS_MIT_REALM@@@Z`
- size: `142`
- prototype: `void __fastcall(struct _KPS_MIT_REALM *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180028e78`
- `0x18002e330`
- `0x18002eb50`
- `0x18002ed24`
- `0x18002f194`

## callees

- `0x18001ae0c`
- `0x18002dbb8`
- `0x18002dc4c`

## pseudocode

```c
void __fastcall KpsFreeMitRealm(void **a1)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x10u, &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids);
  KpsFreeMitServerList(a1 + 1);
  KpsFreeMitServerList(a1 + 3);
  *(_OWORD *)a1 = 0;
  *((_OWORD *)a1 + 1) = 0;
  a1[4] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x11u, &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids);
}

```

## disassembly

```asm
0x18002dbb8  mov     [rsp+arg_0], rbx
0x18002dbbd  push    rdi
0x18002dbbe  sub     rsp, 20h
0x18002dbc2  mov     rbx, rcx
0x18002dbc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbcc  lea     rdi, WPP_GLOBAL_Control
0x18002dbd3  cmp     rcx, rdi
0x18002dbd6  jz      short loc_18002DBF3
0x18002dbd8  test    byte ptr [rcx+1Ch], 20h
0x18002dbdc  jz      short loc_18002DBF3
0x18002dbde  mov     rcx, [rcx+10h]
0x18002dbe2  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002dbe9  mov     edx, 10h
0x18002dbee  call    WPP_SF_
0x18002dbf3  lea     rcx, [rbx+8]; struct _KPS_MIT_SERVER_LIST *
0x18002dbf7  call    ?KpsFreeMitServerList@@YAXPEAU_KPS_MIT_SERVER_LIST@@@Z; KpsFreeMitServerList(_KPS_MIT_SERVER_LIST *)
0x18002dbfc  lea     rcx, [rbx+18h]; struct _KPS_MIT_SERVER_LIST *
0x18002dc00  call    ?KpsFreeMitServerList@@YAXPEAU_KPS_MIT_SERVER_LIST@@@Z; KpsFreeMitServerList(_KPS_MIT_SERVER_LIST *)
0x18002dc05  xorps   xmm0, xmm0
0x18002dc08  xor     eax, eax
0x18002dc0a  movups  xmmword ptr [rbx], xmm0
0x18002dc0d  movups  xmmword ptr [rbx+10h], xmm0
0x18002dc11  mov     [rbx+20h], rax
0x18002dc15  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc1c  cmp     rcx, rdi
0x18002dc1f  jz      short loc_18002DC3A
0x18002dc21  test    byte ptr [rcx+1Ch], 20h
0x18002dc25  jz      short loc_18002DC3A
0x18002dc27  mov     rcx, [rcx+10h]
0x18002dc2b  lea     edx, [rax+11h]
0x18002dc2e  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002dc35  call    WPP_SF_
0x18002dc3a  mov     rbx, [rsp+28h+arg_0]
0x18002dc3f  add     rsp, 20h
0x18002dc43  pop     rdi
0x18002dc44  retn
```
