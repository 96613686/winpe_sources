# _EapHost::ECPManager::StopNoThrow_::_1_::catch$0

- ea: `0x180015ce1`
- end: `0x180015da9`
- name: `_EapHost::ECPManager::StopNoThrow_::_1_::catch$0`
- size: `200`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000bbd8`
- `0x18000c150`
- `0x18000c39c`
- `0x180015ce1`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180015cfc`
- `ntdll!EtwEventEnabled` at `0x180015cfc`

## string_xrefs

- `0x180015d06`: `Caught Foundation exception while stopping ECP thread`

## pseudocode

```c
__int64 __fastcall EapHost::ECPManager::StopNoThrow_::_1_::catch_0(__int64 a1, __int64 a2)
{
  int v3; // r8d
  int v4; // r9d
  __int64 v5; // rax

  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
    && (int)StringCchPrintfA((char *)(a2 + 80), 0x800u, "Caught Foundation exception while stopping ECP thread") >= 0
    && (byte_180020AC1 & 8) != 0 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_BYTE *)(a2 + 80 + v5) );
    *(_QWORD *)(a2 + 64) = a2 + 80;
    *(_DWORD *)(a2 + 72) = v5 + 1;
    *(_DWORD *)(a2 + 76) = 0;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugErrorEvent,
      v3,
      v4,
      a2 + 48);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180015ce1  mov     [rsp+arg_8], rdx
0x180015ce6  push    rbp
0x180015ce7  sub     rsp, 30h
0x180015ceb  mov     rbp, rdx
0x180015cee  lea     rdx, DebugErrorEvent
0x180015cf5  mov     rcx, cs:eaphost_Context
0x180015cfc  call    cs:__imp_EtwEventEnabled
0x180015d02  test    al, al
0x180015d04  jz      short loc_180015D69
0x180015d06  lea     r8, aCaughtFoundati_0; "Caught Foundation exception while stopp"...
0x180015d0d  mov     edx, 800h; unsigned __int64
0x180015d12  lea     rcx, [rbp+50h]; char *
0x180015d16  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180015d1b  test    eax, eax
0x180015d1d  js      short loc_180015D69
0x180015d1f  test    cs:byte_180020AC1, 8
0x180015d26  jz      short loc_180015D69
0x180015d28  lea     rcx, [rbp+50h]
0x180015d2c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015d30  inc     rax
0x180015d33  cmp     byte ptr [rcx+rax], 0
0x180015d37  jnz     short loc_180015D30
0x180015d39  inc     eax
0x180015d3b  lea     rcx, [rbp+50h]
0x180015d3f  mov     [rbp+40h], rcx
0x180015d43  mov     [rbp+48h], eax
0x180015d46  mov     dword ptr [rbp+4Ch], 0
0x180015d4d  lea     rax, [rbp+30h]
0x180015d51  mov     [rsp+38h+var_18], rax
0x180015d56  lea     rdx, DebugErrorEvent
0x180015d5d  lea     rcx, eaphost_Context
0x180015d64  call    McGenEventWrite_EtwEventWriteTransfer
0x180015d69  lea     rax, WPP_GLOBAL_Control
0x180015d70  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d77  cmp     rcx, rax
0x180015d7a  jz      short loc_180015D98
0x180015d7c  test    byte ptr [rcx+1Ch], 1
0x180015d80  jz      short loc_180015D98
0x180015d82  mov     edx, 0Fh
0x180015d87  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x180015d8e  mov     rcx, [rcx+10h]
0x180015d92  call    WPP_SF_
0x180015d97  nop
0x180015d98  mov     rax, 0
0x180015da2  add     rsp, 30h
0x180015da6  pop     rbp
0x180015da7  retn
```
