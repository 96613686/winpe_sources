# _EapHost::ECPManager::Run_::_1_::catch$0

- ea: `0x1800158ac`
- end: `0x180015a75`
- name: `_EapHost::ECPManager::Run_::_1_::catch$0`
- size: `457`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x18000bbd8`
- `0x18000c150`
- `0x18000c39c`
- `0x18000c40c`
- `0x1800158ac`
- `0x180017010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180015919`
- `ntdll!EtwEventEnabled` at `0x1800159bb`
- `ntdll!EtwEventEnabled` at `0x180015919`
- `ntdll!EtwEventEnabled` at `0x1800159bb`

## string_xrefs

- `0x1800159c5`: `Too many error happened.  Exiting ECP thread.`

## pseudocode

```c
__int64 __fastcall EapHost::ECPManager::Run_::_1_::catch_0(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  unsigned int v4; // eax
  int v5; // eax
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rax
  unsigned int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  __int64 v12; // rax

  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v3 = *(_QWORD *)(a2 + 72);
  }
  else
  {
    v3 = *(_QWORD *)(a2 + 72);
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids, v4);
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent) )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
    if ( (int)StringCchPrintfA((char *)(a2 + 112), 0x800u, "Caught foundation exception in wait/sync loop, 0x%x", v5) >= 0
      && (byte_180020AC1 & 8) != 0 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_BYTE *)(a2 + 112 + v8) );
      *(_QWORD *)(a2 + 96) = a2 + 112;
      *(_DWORD *)(a2 + 104) = v8 + 1;
      *(_DWORD *)(a2 + 108) = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugErrorEvent,
        v6,
        v7,
        a2 + 80);
    }
  }
  v9 = *(_DWORD *)(a2 + 48) + 1;
  *(_DWORD *)(a2 + 48) = v9;
  if ( v9 <= *(_DWORD *)(*(_QWORD *)(a2 + 56) + 60LL) )
    return 1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
    && (int)StringCchPrintfA((char *)(a2 + 112), 0x800u, "Too many error happened.  Exiting ECP thread.") >= 0
    && (byte_180020AC1 & 8) != 0 )
  {
    v12 = -1;
    do
      ++v12;
    while ( *(_BYTE *)(a2 + 112 + v12) );
    *(_QWORD *)(a2 + 96) = a2 + 112;
    *(_DWORD *)(a2 + 104) = v12 + 1;
    *(_DWORD *)(a2 + 108) = 0;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugErrorEvent,
      v10,
      v11,
      a2 + 80);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1800158ac  mov     [rsp+arg_8], rdx
0x1800158b1  push    rbx
0x1800158b2  push    rbp
0x1800158b3  sub     rsp, 38h
0x1800158b7  mov     rbp, rdx
0x1800158ba  lea     rcx, WPP_GLOBAL_Control
0x1800158c1  mov     rax, cs:WPP_GLOBAL_Control
0x1800158c8  cmp     rax, rcx
0x1800158cb  jz      short loc_180015907
0x1800158cd  test    byte ptr [rax+1Ch], 1
0x1800158d1  jz      short loc_180015907
0x1800158d3  mov     rbx, [rbp+48h]
0x1800158d7  mov     rax, [rbx]
0x1800158da  mov     rcx, rbx
0x1800158dd  mov     rax, [rax+8]
0x1800158e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158e6  mov     edx, 11h
0x1800158eb  mov     r9d, eax
0x1800158ee  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x1800158f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158fc  mov     rcx, [rcx+10h]
0x180015900  call    WPP_SF_d
0x180015905  jmp     short loc_18001590B
0x180015907  mov     rbx, [rbp+48h]
0x18001590b  lea     rdx, DebugErrorEvent
0x180015912  mov     rcx, cs:eaphost_Context
0x180015919  call    cs:__imp_EtwEventEnabled
0x18001591f  test    al, al
0x180015921  jz      short loc_180015998
0x180015923  mov     rax, [rbx]
0x180015926  mov     rcx, rbx
0x180015929  mov     rax, [rax+8]
0x18001592d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015932  mov     r9d, eax
0x180015935  lea     r8, aCaughtFoundati; "Caught foundation exception in wait/syn"...
0x18001593c  mov     edx, 800h; unsigned __int64
0x180015941  lea     rcx, [rbp+70h]; char *
0x180015945  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001594a  test    eax, eax
0x18001594c  js      short loc_180015998
0x18001594e  test    cs:byte_180020AC1, 8
0x180015955  jz      short loc_180015998
0x180015957  lea     rcx, [rbp+70h]
0x18001595b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001595f  inc     rax
0x180015962  cmp     byte ptr [rcx+rax], 0
0x180015966  jnz     short loc_18001595F
0x180015968  inc     eax
0x18001596a  lea     rcx, [rbp+70h]
0x18001596e  mov     [rbp+60h], rcx
0x180015972  mov     [rbp+68h], eax
0x180015975  mov     dword ptr [rbp+6Ch], 0
0x18001597c  lea     rax, [rbp+50h]
0x180015980  mov     [rsp+48h+var_28], rax
0x180015985  lea     rdx, DebugErrorEvent
0x18001598c  lea     rcx, eaphost_Context
0x180015993  call    McGenEventWrite_EtwEventWriteTransfer
0x180015998  mov     ecx, [rbp+30h]
0x18001599b  inc     ecx
0x18001599d  mov     [rbp+30h], ecx
0x1800159a0  mov     rax, [rbp+38h]
0x1800159a4  cmp     ecx, [rax+3Ch]
0x1800159a7  jbe     loc_180015A63
0x1800159ad  lea     rdx, DebugErrorEvent
0x1800159b4  mov     rcx, cs:eaphost_Context
0x1800159bb  call    cs:__imp_EtwEventEnabled
0x1800159c1  test    al, al
0x1800159c3  jz      short loc_180015A28
0x1800159c5  lea     r8, aTooManyErrorHa; "Too many error happened.  Exiting ECP t"...
0x1800159cc  mov     edx, 800h; unsigned __int64
0x1800159d1  lea     rcx, [rbp+70h]; char *
0x1800159d5  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800159da  test    eax, eax
0x1800159dc  js      short loc_180015A28
0x1800159de  test    cs:byte_180020AC1, 8
0x1800159e5  jz      short loc_180015A28
0x1800159e7  lea     rcx, [rbp+70h]
0x1800159eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800159ef  inc     rax
0x1800159f2  cmp     byte ptr [rcx+rax], 0
0x1800159f6  jnz     short loc_1800159EF
0x1800159f8  inc     eax
0x1800159fa  lea     rcx, [rbp+70h]
0x1800159fe  mov     [rbp+60h], rcx
0x180015a02  mov     [rbp+68h], eax
0x180015a05  mov     dword ptr [rbp+6Ch], 0
0x180015a0c  lea     rax, [rbp+50h]
0x180015a10  mov     [rsp+48h+var_28], rax
0x180015a15  lea     rdx, DebugErrorEvent
0x180015a1c  lea     rcx, eaphost_Context
0x180015a23  call    McGenEventWrite_EtwEventWriteTransfer
0x180015a28  lea     rax, WPP_GLOBAL_Control
0x180015a2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a36  cmp     rcx, rax
0x180015a39  jz      short loc_180015A57
0x180015a3b  test    byte ptr [rcx+1Ch], 1
0x180015a3f  jz      short loc_180015A57
0x180015a41  mov     edx, 12h
0x180015a46  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x180015a4d  mov     rcx, [rcx+10h]
0x180015a51  call    WPP_SF_
0x180015a56  nop
0x180015a57  mov     rax, 0
0x180015a61  jmp     short loc_180015A6D
0x180015a63  mov     rax, 1
0x180015a6d  add     rsp, 38h
0x180015a71  pop     rbp
0x180015a72  pop     rbx
0x180015a73  retn
```
