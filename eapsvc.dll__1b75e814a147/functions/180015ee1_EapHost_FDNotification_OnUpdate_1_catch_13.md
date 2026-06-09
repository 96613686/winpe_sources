# _EapHost::FDNotification::OnUpdate_::_1_::catch$13

- ea: `0x180015ee1`
- end: `0x180015fcf`
- name: `_EapHost::FDNotification::OnUpdate_::_1_::catch$13`
- size: `238`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callees

- `0x18000bbd8`
- `0x18000c150`
- `0x18000c40c`
- `0x180015ee1`
- `0x180017010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180015f12`
- `ntdll!EtwEventEnabled` at `0x180015f12`

## string_xrefs

- `0x180015f1f`: `Got exception while processing FD update notification, 0x%x`

## pseudocode

```c
__int64 __fastcall EapHost::FDNotification::OnUpdate_::_1_::catch_13(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rax

  v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 88) + 8LL))(*(_QWORD *)(a2 + 88));
  *(_DWORD *)(a2 + 56) = v3;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
    && (int)StringCchPrintfA(
              (char *)(a2 + 128),
              0x800u,
              "Got exception while processing FD update notification, 0x%x",
              v3) >= 0
    && (byte_180020AC1 & 8) != 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_BYTE *)(a2 + 128 + v6) );
    *(_QWORD *)(a2 + 112) = a2 + 128;
    *(_DWORD *)(a2 + 120) = v6 + 1;
    *(_DWORD *)(a2 + 124) = 0;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugErrorEvent,
      v4,
      v5,
      a2 + 96);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids, v3);
  return 0;
}

```

## disassembly

```asm
0x180015ee1  mov     [rsp+arg_8], rdx
0x180015ee6  push    rbx
0x180015ee7  push    rbp
0x180015ee8  sub     rsp, 38h
0x180015eec  mov     rbp, rdx
0x180015eef  mov     rcx, [rbp+58h]
0x180015ef3  mov     rax, [rcx]
0x180015ef6  mov     rax, [rax+8]
0x180015efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eff  mov     ebx, eax
0x180015f01  mov     [rbp+38h], eax
0x180015f04  lea     rdx, DebugErrorEvent
0x180015f0b  mov     rcx, cs:eaphost_Context
0x180015f12  call    cs:__imp_EtwEventEnabled
0x180015f18  test    al, al
0x180015f1a  jz      short loc_180015F8B
0x180015f1c  mov     r9d, ebx
0x180015f1f  lea     r8, aGotExceptionWh; "Got exception while processing FD updat"...
0x180015f26  mov     edx, 800h; unsigned __int64
0x180015f2b  lea     rcx, [rbp+80h]; char *
0x180015f32  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180015f37  test    eax, eax
0x180015f39  js      short loc_180015F8B
0x180015f3b  test    cs:byte_180020AC1, 8
0x180015f42  jz      short loc_180015F8B
0x180015f44  lea     rcx, [rbp+80h]
0x180015f4b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015f4f  inc     rax
0x180015f52  cmp     byte ptr [rcx+rax], 0
0x180015f56  jnz     short loc_180015F4F
0x180015f58  inc     eax
0x180015f5a  lea     rcx, [rbp+80h]
0x180015f61  mov     [rbp+70h], rcx
0x180015f65  mov     [rbp+78h], eax
0x180015f68  mov     dword ptr [rbp+7Ch], 0
0x180015f6f  lea     rax, [rbp+60h]
0x180015f73  mov     [rsp+48h+var_28], rax
0x180015f78  lea     rdx, DebugErrorEvent
0x180015f7f  lea     rcx, eaphost_Context
0x180015f86  call    McGenEventWrite_EtwEventWriteTransfer
0x180015f8b  lea     rax, WPP_GLOBAL_Control
0x180015f92  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f99  cmp     rcx, rax
0x180015f9c  jz      short loc_180015FBD
0x180015f9e  test    byte ptr [rcx+1Ch], 1
0x180015fa2  jz      short loc_180015FBD
0x180015fa4  mov     edx, 1Dh
0x180015fa9  mov     r9d, ebx
0x180015fac  lea     r8, WPP_2d706c3a7ef13fee77e66daa8138914c_Traceguids
0x180015fb3  mov     rcx, [rcx+10h]
0x180015fb7  call    WPP_SF_d
0x180015fbc  nop
0x180015fbd  mov     rax, 0
0x180015fc7  add     rsp, 38h
0x180015fcb  pop     rbp
0x180015fcc  pop     rbx
0x180015fcd  retn
```
