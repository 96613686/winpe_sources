# ux::CLauncherMainTaskDialog::~CLauncherMainTaskDialog(void)

- ea: `0x1800099bc`
- end: `0x180009a2a`
- name: `??1CLauncherMainTaskDialog@ux@@UEAA@XZ`
- size: `110`
- prototype: `void __fastcall(ux::CLauncherMainTaskDialog *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180008e20`
- `0x180009be0`
- `0x18001033a`

## callees

- `0x180008ac8`
- `0x1800099bc`
- `0x180011010`

## pseudocode

```c
void __fastcall ux::CLauncherMainTaskDialog::~CLauncherMainTaskDialog(ux::CLauncherMainTaskDialog *this)
{
  volatile signed __int32 *v2; // rdx

  *(_QWORD *)this = &ux::CLauncherMainTaskDialog::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids);
  v2 = (volatile signed __int32 *)(*((_QWORD *)this + 23) - 24LL);
  if ( _InterlockedExchangeAdd(v2 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v2 + 8LL))(*(_QWORD *)v2);
}

```

## disassembly

```asm
0x1800099bc  push    rbx
0x1800099be  sub     rsp, 20h
0x1800099c2  lea     rax, ??_7CLauncherMainTaskDialog@ux@@6B@; const ux::CLauncherMainTaskDialog::`vftable'
0x1800099c9  mov     rbx, rcx
0x1800099cc  mov     [rcx], rax
0x1800099cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099d6  lea     rax, WPP_GLOBAL_Control
0x1800099dd  cmp     rcx, rax
0x1800099e0  jz      short loc_1800099FD
0x1800099e2  test    byte ptr [rcx+1Ch], 8
0x1800099e6  jz      short loc_1800099FD
0x1800099e8  mov     rcx, [rcx+10h]
0x1800099ec  lea     r8, WPP_2da6a91563c532cecd88682c0a3ac2f7_Traceguids
0x1800099f3  mov     edx, 22h ; '"'
0x1800099f8  call    WPP_SF_
0x1800099fd  mov     rdx, [rbx+0B8h]
0x180009a04  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180009a08  or      eax, 0FFFFFFFFh
0x180009a0b  lock xadd [rdx+10h], eax
0x180009a10  sub     eax, 1
0x180009a13  jg      short loc_180009A24
0x180009a15  mov     rcx, [rdx]
0x180009a18  mov     rax, [rcx]
0x180009a1b  mov     rax, [rax+8]
0x180009a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a24  add     rsp, 20h
0x180009a28  pop     rbx
0x180009a29  retn
```
