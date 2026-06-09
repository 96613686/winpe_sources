# FwTriggerRearm

- ea: `0x180012e60`
- end: `0x180012f7c`
- name: `FwTriggerRearm`
- size: `284`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000ccd4`
- `0x180012e60`
- `0x180017d1c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180012eb8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180012eb8`

## pseudocode

```c
void __fastcall FwTriggerRearm(__int64 a1)
{
  _BYTE *v2; // rcx
  struct _TP_WAIT *v3; // rax
  void *v4; // rdx
  unsigned int v5; // ebx
  __int64 v6; // rdx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v2 == (_BYTE *)&WPP_GLOBAL_Control )
      return;
    v5 = 87;
    if ( (v2[28] & 1) == 0 )
      goto LABEL_9;
    v6 = 20;
    goto LABEL_14;
  }
  v3 = *(struct _TP_WAIT **)a1;
  if ( !*(_QWORD *)a1 )
  {
    if ( v2 == (_BYTE *)&WPP_GLOBAL_Control )
      return;
    v5 = 87;
    if ( (v2[28] & 1) == 0 )
      goto LABEL_9;
    v6 = 21;
    goto LABEL_14;
  }
  v4 = *(void **)(a1 + 8);
  if ( v4 )
  {
    v5 = 0;
    SetThreadpoolWait(v3, v4, 0);
LABEL_8:
    v2 = WPP_GLOBAL_Control;
    goto LABEL_9;
  }
  if ( v2 == (_BYTE *)&WPP_GLOBAL_Control )
    return;
  v5 = 87;
  if ( (v2[28] & 1) != 0 )
  {
    v6 = 22;
LABEL_14:
    WPP_SF_d(*((_QWORD *)v2 + 2), v6, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids, 87);
    goto LABEL_8;
  }
LABEL_9:
  if ( v2 != (_BYTE *)&WPP_GLOBAL_Control && (v2[28] & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v2 + 2), 23, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids, v5);
}

```

## disassembly

```asm
0x180012e60  mov     [rsp+arg_0], rbx
0x180012e65  mov     [rsp+arg_8], rsi
0x180012e6a  push    rdi
0x180012e6b  sub     rsp, 20h
0x180012e6f  mov     rbx, rcx
0x180012e72  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e79  lea     rdi, WPP_GLOBAL_Control
0x180012e80  lea     rsi, WPP_daa71961c68f3192cca7fdfb2d6e33f5_Traceguids
0x180012e87  cmp     rcx, rdi
0x180012e8a  jz      short loc_180012E92
0x180012e8c  test    byte ptr [rcx+1Ch], 8
0x180012e90  jnz     short loc_180012EF8
0x180012e92  test    rbx, rbx
0x180012e95  jz      short loc_180012EDE
0x180012e97  mov     rax, [rbx]
0x180012e9a  test    rax, rax
0x180012e9d  jz      loc_180012F25
0x180012ea3  mov     rdx, [rbx+8]; h
0x180012ea7  test    rdx, rdx
0x180012eaa  jz      loc_180012F3F
0x180012eb0  xor     ebx, ebx
0x180012eb2  xor     r8d, r8d; pftTimeout
0x180012eb5  mov     rcx, rax; pwa
0x180012eb8  call    cs:__imp_SetThreadpoolWait
0x180012ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ec5  cmp     rcx, rdi
0x180012ec8  jnz     loc_180012F59
0x180012ece  mov     rbx, [rsp+28h+arg_0]
0x180012ed3  mov     rsi, [rsp+28h+arg_8]
0x180012ed8  add     rsp, 20h
0x180012edc  pop     rdi
0x180012edd  retn
0x180012ede  cmp     rcx, rdi
0x180012ee1  jz      short loc_180012ECE
0x180012ee3  test    byte ptr [rcx+1Ch], 1
0x180012ee7  mov     r9d, 57h ; 'W'
0x180012eed  mov     ebx, r9d
0x180012ef0  jz      short loc_180012EC5
0x180012ef2  lea     edx, [r9-43h]
0x180012ef6  jmp     short loc_180012F17
0x180012ef8  mov     rcx, [rcx+10h]
0x180012efc  mov     edx, 13h
0x180012f01  mov     r8, rsi
0x180012f04  call    WPP_SF_
0x180012f09  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f10  jmp     short loc_180012E92
0x180012f12  mov     edx, 16h
0x180012f17  mov     rcx, [rcx+10h]
0x180012f1b  mov     r8, rsi
0x180012f1e  call    WPP_SF_d
0x180012f23  jmp     short loc_180012EBE
0x180012f25  cmp     rcx, rdi
0x180012f28  jz      short loc_180012ECE
0x180012f2a  test    byte ptr [rcx+1Ch], 1
0x180012f2e  mov     r9d, 57h ; 'W'
0x180012f34  mov     ebx, r9d
0x180012f37  jz      short loc_180012EC5
0x180012f39  lea     edx, [r9-42h]
0x180012f3d  jmp     short loc_180012F17
0x180012f3f  cmp     rcx, rdi
0x180012f42  jz      short loc_180012ECE
0x180012f44  test    byte ptr [rcx+1Ch], 1
0x180012f48  mov     r9d, 57h ; 'W'
0x180012f4e  mov     ebx, r9d
0x180012f51  jz      loc_180012EC5
0x180012f57  jmp     short loc_180012F12
0x180012f59  test    byte ptr [rcx+1Ch], 8
0x180012f5d  jz      loc_180012ECE
0x180012f63  mov     rcx, [rcx+10h]
0x180012f67  mov     edx, 17h
0x180012f6c  mov     r9d, ebx
0x180012f6f  mov     r8, rsi
0x180012f72  call    WPP_SF_d
0x180012f77  jmp     loc_180012ECE
```
