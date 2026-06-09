# RfcommCompleteFdoIrp

- ea: `0x140001c34`
- end: `0x140001d1d`
- name: `RfcommCompleteFdoIrp`
- size: `233`
- prototype: `__int64 __fastcall(PVOID Tag)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000256c`

## callees

- `0x140001c34`
- `0x140004434`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140001cee`
- `ntoskrnl!IofCompleteRequest` at `0x140001cee`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001d07`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140001d07`

## pseudocode

```c
void __fastcall RfcommCompleteFdoIrp(_QWORD *Tag, int a2, __int64 a3)
{
  char *v5; // rdx
  char v7; // cl
  __int64 v8; // rbp
  int v9; // r9d

  v5 = (char *)Tag[23];
  v7 = *v5;
  v8 = *(_QWORD *)(*((_QWORD *)v5 + 5) + 64LL);
  if ( *v5 == 15 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = 105;
      goto LABEL_10;
    }
  }
  else if ( v7 == 22 || v7 == 27 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v9 = 104;
      goto LABEL_10;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v9 = 106;
LABEL_10:
    WPP_RECORDER_SF_cqdi(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)v5, a3, v9);
  }
  *((_DWORD *)Tag + 12) = a2;
  Tag[7] = a3;
  IofCompleteRequest((PIRP)Tag, 2);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v8 + 40), Tag, 0x20u);
}

```

## disassembly

```asm
0x140001c34  push    rbx
0x140001c36  push    rbp
0x140001c37  push    rsi
0x140001c38  push    rdi
0x140001c39  sub     rsp, 58h
0x140001c3d  mov     esi, edx
0x140001c3f  mov     rbx, rcx
0x140001c42  mov     rdx, [rcx+0B8h]
0x140001c49  mov     rdi, r8
0x140001c4c  mov     rax, [rdx+28h]
0x140001c50  mov     cl, [rdx]
0x140001c52  mov     rbp, [rax+40h]
0x140001c56  cmp     cl, 0Fh
0x140001c59  jz      short loc_140001CA7
0x140001c5b  cmp     cl, 16h
0x140001c5e  jz      short loc_140001C8F
0x140001c60  cmp     cl, 1Bh
0x140001c63  jz      short loc_140001C8F
0x140001c65  lea     rax, WPP_RECORDER_INITIALIZED
0x140001c6c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140001c73  jz      short loc_140001CE2
0x140001c75  mov     [rsp+78h+var_38], r8
0x140001c7a  mov     r9d, 6Ah ; 'j'
0x140001c80  mov     [rsp+78h+var_40], esi
0x140001c84  mov     [rsp+78h+var_48], rbx
0x140001c89  mov     [rsp+78h+var_50], cl
0x140001c8d  jmp     short loc_140001CD2
0x140001c8f  lea     rax, WPP_RECORDER_INITIALIZED
0x140001c96  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140001c9d  jz      short loc_140001CE2
0x140001c9f  mov     r9d, 68h ; 'h'
0x140001ca5  jmp     short loc_140001CBD
0x140001ca7  lea     rax, WPP_RECORDER_INITIALIZED
0x140001cae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140001cb5  jz      short loc_140001CE2
0x140001cb7  mov     r9d, 69h ; 'i'
0x140001cbd  mov     al, [rdx+1]
0x140001cc0  mov     [rsp+78h+var_38], rdi
0x140001cc5  mov     [rsp+78h+var_40], esi
0x140001cc9  mov     [rsp+78h+var_48], rbx
0x140001cce  mov     [rsp+78h+var_50], al
0x140001cd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140001cd9  mov     rcx, [rcx+40h]
0x140001cdd  call    WPP_RECORDER_SF_cqdi
0x140001ce2  mov     dl, 2; PriorityBoost
0x140001ce4  mov     [rbx+30h], esi
0x140001ce7  mov     rcx, rbx; Irp
0x140001cea  mov     [rbx+38h], rdi
0x140001cee  call    cs:__imp_IofCompleteRequest
0x140001cf5  nop     dword ptr [rax+rax+00h]
0x140001cfa  lea     rcx, [rbp+28h]; RemoveLock
0x140001cfe  mov     r8d, 20h ; ' '; RemlockSize
0x140001d04  mov     rdx, rbx; Tag
0x140001d07  call    cs:__imp_IoReleaseRemoveLockEx
0x140001d0e  nop     dword ptr [rax+rax+00h]
0x140001d13  add     rsp, 58h
0x140001d17  pop     rdi
0x140001d18  pop     rsi
0x140001d19  pop     rbp
0x140001d1a  pop     rbx
0x140001d1b  retn
```
