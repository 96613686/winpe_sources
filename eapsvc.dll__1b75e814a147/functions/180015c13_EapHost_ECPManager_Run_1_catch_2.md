# _EapHost::ECPManager::Run_::_1_::catch$2

- ea: `0x180015c13`
- end: `0x180015cdb`
- name: `_EapHost::ECPManager::Run_::_1_::catch$2`
- size: `200`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000bbd8`
- `0x18000c150`
- `0x18000c39c`
- `0x180015c13`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180015c2e`
- `ntdll!EtwEventEnabled` at `0x180015c2e`

## string_xrefs

- `0x180015c38`: `Caught shutdown exception. ECP thread exiting.`

## pseudocode

```c
__int64 __fastcall EapHost::ECPManager::Run_::_1_::catch_2(__int64 a1, __int64 a2)
{
  int v3; // r8d
  int v4; // r9d
  __int64 v5; // rax

  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA((char *)(a2 + 112), 0x800u, "Caught shutdown exception. ECP thread exiting.") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_BYTE *)(a2 + 112 + v5) );
    *(_QWORD *)(a2 + 96) = a2 + 112;
    *(_DWORD *)(a2 + 104) = v5 + 1;
    *(_DWORD *)(a2 + 108) = 0;
    McGenEventWrite_EtwEventWriteTransfer((unsigned int)&eaphost_Context, (unsigned int)DebugInfoEvent, v3, v4, a2 + 80);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180015c13  mov     [rsp+arg_8], rdx
0x180015c18  push    rbp
0x180015c19  sub     rsp, 30h
0x180015c1d  mov     rbp, rdx
0x180015c20  lea     rdx, DebugInfoEvent
0x180015c27  mov     rcx, cs:eaphost_Context
0x180015c2e  call    cs:__imp_EtwEventEnabled
0x180015c34  test    al, al
0x180015c36  jz      short loc_180015C9B
0x180015c38  lea     r8, aCaughtShutdown; "Caught shutdown exception. ECP thread e"...
0x180015c3f  mov     edx, 800h; unsigned __int64
0x180015c44  lea     rcx, [rbp+70h]; char *
0x180015c48  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180015c4d  test    eax, eax
0x180015c4f  js      short loc_180015C9B
0x180015c51  test    cs:Microsoft_Windows_EapHostEnableBits, 80h
0x180015c58  jz      short loc_180015C9B
0x180015c5a  lea     rcx, [rbp+70h]
0x180015c5e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015c62  inc     rax
0x180015c65  cmp     byte ptr [rcx+rax], 0
0x180015c69  jnz     short loc_180015C62
0x180015c6b  inc     eax
0x180015c6d  lea     rcx, [rbp+70h]
0x180015c71  mov     [rbp+60h], rcx
0x180015c75  mov     [rbp+68h], eax
0x180015c78  mov     dword ptr [rbp+6Ch], 0
0x180015c7f  lea     rax, [rbp+50h]
0x180015c83  mov     [rsp+38h+var_18], rax
0x180015c88  lea     rdx, DebugInfoEvent
0x180015c8f  lea     rcx, eaphost_Context
0x180015c96  call    McGenEventWrite_EtwEventWriteTransfer
0x180015c9b  lea     rax, WPP_GLOBAL_Control
0x180015ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ca9  cmp     rcx, rax
0x180015cac  jz      short loc_180015CCA
0x180015cae  test    byte ptr [rcx+1Ch], 4
0x180015cb2  jz      short loc_180015CCA
0x180015cb4  mov     edx, 16h
0x180015cb9  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x180015cc0  mov     rcx, [rcx+10h]
0x180015cc4  call    WPP_SF_
0x180015cc9  nop
0x180015cca  mov     rax, 0
0x180015cd4  add     rsp, 30h
0x180015cd8  pop     rbp
0x180015cd9  retn
```
