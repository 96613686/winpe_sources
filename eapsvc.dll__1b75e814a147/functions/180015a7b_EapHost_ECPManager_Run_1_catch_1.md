# _EapHost::ECPManager::Run_::_1_::catch$1

- ea: `0x180015a7b`
- end: `0x180015c0d`
- name: `_EapHost::ECPManager::Run_::_1_::catch$1`
- size: `402`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000bbd8`
- `0x18000c150`
- `0x18000c39c`
- `0x180015a7b`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180015a96`
- `ntdll!EtwEventEnabled` at `0x180015b54`
- `ntdll!EtwEventEnabled` at `0x180015a96`
- `ntdll!EtwEventEnabled` at `0x180015b54`

## string_xrefs

- `0x180015b5e`: `Too many error happened.  Exiting ECP thread.`

## pseudocode

```c
__int64 __fastcall EapHost::ECPManager::Run_::_1_::catch_1(__int64 a1, __int64 a2)
{
  int v3; // r8d
  int v4; // r9d
  __int64 v5; // rax
  unsigned int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rax

  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
    && (int)StringCchPrintfA((char *)(a2 + 112), 0x800u, "Caught std::exception in wait/sync loop") >= 0
    && (byte_180020AC1 & 8) != 0 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_BYTE *)(a2 + 112 + v5) );
    *(_QWORD *)(a2 + 96) = a2 + 112;
    *(_DWORD *)(a2 + 104) = v5 + 1;
    *(_DWORD *)(a2 + 108) = 0;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugErrorEvent,
      v3,
      v4,
      a2 + 80);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
  v6 = *(_DWORD *)(a2 + 48) + 1;
  *(_DWORD *)(a2 + 48) = v6;
  if ( v6 <= *(_DWORD *)(*(_QWORD *)(a2 + 56) + 60LL) )
    return 1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
    && (int)StringCchPrintfA((char *)(a2 + 112), 0x800u, "Too many error happened.  Exiting ECP thread.") >= 0
    && (byte_180020AC1 & 8) != 0 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(a2 + 112 + v9) );
    *(_QWORD *)(a2 + 96) = a2 + 112;
    *(_DWORD *)(a2 + 104) = v9 + 1;
    *(_DWORD *)(a2 + 108) = 0;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugErrorEvent,
      v7,
      v8,
      a2 + 80);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180015a7b  mov     [rsp+arg_8], rdx
0x180015a80  push    rbp
0x180015a81  sub     rsp, 30h
0x180015a85  mov     rbp, rdx
0x180015a88  lea     rdx, DebugErrorEvent
0x180015a8f  mov     rcx, cs:eaphost_Context
0x180015a96  call    cs:__imp_EtwEventEnabled
0x180015a9c  test    al, al
0x180015a9e  jz      short loc_180015B03
0x180015aa0  lea     r8, aCaughtStdExcep; "Caught std::exception in wait/sync loop"
0x180015aa7  mov     edx, 800h; unsigned __int64
0x180015aac  lea     rcx, [rbp+70h]; char *
0x180015ab0  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180015ab5  test    eax, eax
0x180015ab7  js      short loc_180015B03
0x180015ab9  test    cs:byte_180020AC1, 8
0x180015ac0  jz      short loc_180015B03
0x180015ac2  lea     rcx, [rbp+70h]
0x180015ac6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015aca  inc     rax
0x180015acd  cmp     byte ptr [rcx+rax], 0
0x180015ad1  jnz     short loc_180015ACA
0x180015ad3  inc     eax
0x180015ad5  lea     rcx, [rbp+70h]
0x180015ad9  mov     [rbp+60h], rcx
0x180015add  mov     [rbp+68h], eax
0x180015ae0  mov     dword ptr [rbp+6Ch], 0
0x180015ae7  lea     rax, [rbp+50h]
0x180015aeb  mov     [rsp+38h+var_18], rax
0x180015af0  lea     rdx, DebugErrorEvent
0x180015af7  lea     rcx, eaphost_Context
0x180015afe  call    McGenEventWrite_EtwEventWriteTransfer
0x180015b03  lea     rax, WPP_GLOBAL_Control
0x180015b0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b11  cmp     rcx, rax
0x180015b14  jz      short loc_180015B31
0x180015b16  test    byte ptr [rcx+1Ch], 1
0x180015b1a  jz      short loc_180015B31
0x180015b1c  mov     edx, 13h
0x180015b21  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x180015b28  mov     rcx, [rcx+10h]
0x180015b2c  call    WPP_SF_
0x180015b31  mov     ecx, [rbp+30h]
0x180015b34  inc     ecx
0x180015b36  mov     [rbp+30h], ecx
0x180015b39  mov     rax, [rbp+38h]
0x180015b3d  cmp     ecx, [rax+3Ch]
0x180015b40  jbe     loc_180015BFC
0x180015b46  lea     rdx, DebugErrorEvent
0x180015b4d  mov     rcx, cs:eaphost_Context
0x180015b54  call    cs:__imp_EtwEventEnabled
0x180015b5a  test    al, al
0x180015b5c  jz      short loc_180015BC1
0x180015b5e  lea     r8, aTooManyErrorHa; "Too many error happened.  Exiting ECP t"...
0x180015b65  mov     edx, 800h; unsigned __int64
0x180015b6a  lea     rcx, [rbp+70h]; char *
0x180015b6e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180015b73  test    eax, eax
0x180015b75  js      short loc_180015BC1
0x180015b77  test    cs:byte_180020AC1, 8
0x180015b7e  jz      short loc_180015BC1
0x180015b80  lea     rcx, [rbp+70h]
0x180015b84  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015b88  inc     rax
0x180015b8b  cmp     byte ptr [rcx+rax], 0
0x180015b8f  jnz     short loc_180015B88
0x180015b91  inc     eax
0x180015b93  lea     rcx, [rbp+70h]
0x180015b97  mov     [rbp+60h], rcx
0x180015b9b  mov     [rbp+68h], eax
0x180015b9e  mov     dword ptr [rbp+6Ch], 0
0x180015ba5  lea     rax, [rbp+50h]
0x180015ba9  mov     [rsp+38h+var_18], rax
0x180015bae  lea     rdx, DebugErrorEvent
0x180015bb5  lea     rcx, eaphost_Context
0x180015bbc  call    McGenEventWrite_EtwEventWriteTransfer
0x180015bc1  lea     rax, WPP_GLOBAL_Control
0x180015bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180015bcf  cmp     rcx, rax
0x180015bd2  jz      short loc_180015BF0
0x180015bd4  test    byte ptr [rcx+1Ch], 1
0x180015bd8  jz      short loc_180015BF0
0x180015bda  mov     edx, 14h
0x180015bdf  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x180015be6  mov     rcx, [rcx+10h]
0x180015bea  call    WPP_SF_
0x180015bef  nop
0x180015bf0  mov     rax, 0
0x180015bfa  jmp     short loc_180015C06
0x180015bfc  mov     rax, 1
0x180015c06  add     rsp, 30h
0x180015c0a  pop     rbp
0x180015c0b  retn
```
