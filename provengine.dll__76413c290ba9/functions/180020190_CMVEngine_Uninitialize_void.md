# CMVEngine::Uninitialize(void)

- ea: `0x180020190`
- end: `0x180020285`
- name: `?Uninitialize@CMVEngine@@UEAAJXZ`
- size: `245`
- prototype: `__int64 __fastcall(CMVEngine *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010d34`

## callees

- `0x1800010c8`
- `0x180013280`
- `0x180020190`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18002024b`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18002024b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMVEngine::Uninitialize(CMVEngine *this)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rdi
  __int64 *v4; // rdi
  __int64 *i; // rbx
  __int64 v6; // rcx
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+30h] [rbp-38h] BYREF

  if ( (unsigned int)dword_18005A000 > 5 )
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18005A000, (unsigned __int8 *)word_18004ECEA, 0, 0, 2u, &v8);
  v2 = (_QWORD *)*((_QWORD *)this + 7);
  v3 = (_QWORD *)*((_QWORD *)this + 8);
  while ( v2 != v3 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 32LL))(*v2);
    ++v2;
  }
  v4 = (__int64 *)*((_QWORD *)this + 8);
  for ( i = (__int64 *)*((_QWORD *)this + 7); i != v4; ++i )
  {
    v6 = *i;
    if ( *i )
    {
      *i = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  *((_QWORD *)this + 8) = *((_QWORD *)this + 7);
  if ( *((_QWORD *)this + 18) )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    *((_QWORD *)this + 18) = 0;
  }
  CMVEngine::CleanupSequenceHiveFiles(this);
  return 0;
}

```

## disassembly

```asm
0x180020190  mov     r11, rsp
0x180020193  mov     [r11+10h], rbx
0x180020197  mov     [r11+18h], rsi
0x18002019b  push    rdi
0x18002019c  sub     rsp, 60h
0x1800201a0  mov     rax, cs:__security_cookie
0x1800201a7  xor     rax, rsp
0x1800201aa  mov     [rsp+68h+var_18], rax
0x1800201af  mov     rsi, rcx
0x1800201b2  mov     eax, cs:dword_18005A000
0x1800201b8  cmp     eax, 5
0x1800201bb  jbe     short loc_1800201E6
0x1800201bd  lea     rax, [r11-38h]
0x1800201c1  mov     [r11-40h], rax
0x1800201c5  mov     [rsp+68h+var_48], 2
0x1800201cd  xor     r9d, r9d
0x1800201d0  xor     r8d, r8d
0x1800201d3  lea     rdx, word_18004ECEA
0x1800201da  lea     rcx, dword_18005A000
0x1800201e1  call    _tlgWriteTransfer_EventWriteTransfer
0x1800201e6  mov     rbx, [rsi+38h]
0x1800201ea  mov     rdi, [rsi+40h]
0x1800201ee  cmp     rbx, rdi
0x1800201f1  jz      short loc_180020208
0x1800201f3  mov     rcx, [rbx]
0x1800201f6  mov     rax, [rcx]
0x1800201f9  mov     rax, [rax+20h]
0x1800201fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020202  add     rbx, 8
0x180020206  jmp     short loc_1800201EE
0x180020208  mov     rdi, [rsi+40h]
0x18002020c  mov     rbx, [rsi+38h]
0x180020210  jmp     short loc_180020232
0x180020212  mov     rcx, [rbx]
0x180020215  test    rcx, rcx
0x180020218  jz      short loc_18002022E
0x18002021a  mov     qword ptr [rbx], 0
0x180020221  mov     rax, [rcx]
0x180020224  mov     rax, [rax+10h]
0x180020228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002022d  nop
0x18002022e  add     rbx, 8
0x180020232  cmp     rbx, rdi
0x180020235  jnz     short loc_180020212
0x180020237  mov     rax, [rsi+38h]
0x18002023b  mov     [rsi+40h], rax
0x18002023f  mov     rcx, [rsi+90h]
0x180020246  test    rcx, rcx
0x180020249  jz      short loc_18002025C
0x18002024b  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180020251  mov     qword ptr [rsi+90h], 0
0x18002025c  mov     rcx, rsi; this
0x18002025f  call    ?CleanupSequenceHiveFiles@CMVEngine@@AEAAJXZ; CMVEngine::CleanupSequenceHiveFiles(void)
0x180020264  xor     eax, eax
0x180020266  mov     rcx, [rsp+68h+var_18]
0x18002026b  xor     rcx, rsp; StackCookie
0x18002026e  call    __security_check_cookie
0x180020273  lea     r11, [rsp+68h+var_8]
0x180020278  mov     rbx, [r11+18h]
0x18002027c  mov     rsi, [r11+20h]
0x180020280  mov     rsp, r11
0x180020283  pop     rdi
0x180020284  retn
```
